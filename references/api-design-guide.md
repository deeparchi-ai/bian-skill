# BIAN API 设计指南

本指南描述 BIAN 标准 API 的设计规范。

## API 端点结构

### 标准格式

```
/{service-domain}/{sd-reference-id}/{behavior-qualifier}/{bq-reference-id}/{action}
```

### 组件说明

| 组件 | 描述 | 示例 |
|------|------|------|
| service-domain | 服务域名称（kebab-case） | customer-profile |
| sd-reference-id | 服务域控制记录 ID | CR-001 |
| behavior-qualifier | 行为限定符 | preference, balance |
| bq-reference-id | 行为限定符实例 ID | BQ-001 |
| action | 服务操作 | initiate, retrieve |

---

## 服务操作 (Service Operations)

### 标准操作

| 操作 | HTTP 方法 | 描述 |
|------|----------|------|
| Initiate | POST | 创建新的控制记录实例 |
| Create | POST | 创建数据记录 |
| Register | POST | 注册到系统 |
| Evaluate | POST | 评估和分析 |
| Provide | POST | 提供服务 |
| Update | PUT | 更新现有记录 |
| Control | PUT | 控制操作状态 |
| Execute | POST | 执行处理 |
| Request | POST | 发起服务请求 |
| Retrieve | GET | 查询获取数据 |
| Notify | POST | 发送通知 |
| Authorize | POST | 授权操作 |
| Grant | POST | 授予权限 |
| Capture | POST | 捕获数据 |
| Exchange | POST | 交换数据 |

### 操作-HTTP 方法映射

```
创建类操作:
  Initiate  → POST /{service-domain}/initiate
  Create    → POST /{service-domain}/{id}/{bq}/create
  Register  → POST /{service-domain}/{id}/register

查询类操作:
  Retrieve  → GET /{service-domain}/{id}/retrieve
  Retrieve  → GET /{service-domain}/{id}/{bq}/{bq-id}/retrieve

更新类操作:
  Update    → PUT /{service-domain}/{id}/update
  Update    → PUT /{service-domain}/{id}/{bq}/{bq-id}/update
  Control   → PUT /{service-domain}/{id}/control

执行类操作:
  Execute   → POST /{service-domain}/{id}/execute
  Execute   → POST /{service-domain}/{id}/{bq}/{bq-id}/execute
  Request   → POST /{service-domain}/{id}/request
```

---

## 请求/响应格式

### 请求头

```http
Content-Type: application/json
Accept: application/json
Authorization: Bearer {token}
X-Request-ID: {uuid}
X-Correlation-ID: {uuid}
```

### 请求体结构

```json
{
  "{serviceDomainAction}": {
    "{property1}": "value1",
    "{property2}": {
      "{nestedProperty}": "value"
    }
  }
}
```

### 响应体结构

```json
{
  "{serviceDomainRecord}": {
    "{referenceId}": "string",
    "{property1}": "value1",
    "{status}": "string",
    "{timestamp}": "datetime"
  }
}
```

---

## 示例 API

### Customer Profile Management

#### Initiate Customer Profile

```http
POST /customer-profile/initiate
Content-Type: application/json

{
  "customerProfileInitiation": {
    "partyReference": "PTY-001",
    "customerType": "Individual",
    "customerName": {
      "firstName": "John",
      "lastName": "Doe"
    }
  }
}
```

**Response (201)**:
```json
{
  "customerProfileRecord": {
    "customerProfileReference": "CPR-001",
    "status": "Active",
    "createdDateTime": "2025-01-24T10:00:00Z"
  }
}
```

#### Retrieve Customer Profile

```http
GET /customer-profile/CPR-001/retrieve
```

**Response (200)**:
```json
{
  "customerProfileRecord": {
    "customerProfileReference": "CPR-001",
    "partyReference": "PTY-001",
    "customerType": "Individual",
    "customerName": {
      "firstName": "John",
      "lastName": "Doe"
    },
    "status": "Active"
  }
}
```

#### Update Customer Preference (BQ)

```http
PUT /customer-profile/CPR-001/preference/PREF-001/update
Content-Type: application/json

{
  "preferenceUpdate": {
    "communicationChannel": "Email",
    "language": "en-US"
  }
}
```

### Current Account

#### Initiate Account

```http
POST /current-account/initiate
Content-Type: application/json

{
  "currentAccountInitiation": {
    "customerReference": "CUS-001",
    "productReference": "PRD-CHECKING",
    "accountCurrency": "USD"
  }
}
```

#### Execute Deposit (BQ)

```http
POST /current-account/CA-001/deposit/execute
Content-Type: application/json

{
  "depositExecution": {
    "amount": {
      "value": 1000.00,
      "currency": "USD"
    },
    "depositType": "Cash",
    "valueDate": "2025-01-24"
  }
}
```

### Payment Order

#### Initiate Payment

```http
POST /payment-order/initiate
Content-Type: application/json

{
  "paymentOrderInitiation": {
    "payerAccountReference": "ACC-001",
    "payeeAccountReference": "ACC-002",
    "amount": {
      "value": 500.00,
      "currency": "USD"
    },
    "paymentType": "Domestic",
    "valueDate": "2025-01-24"
  }
}
```

#### Execute Payment

```http
POST /payment-order/PO-001/execute
```

---

## 错误处理

### 错误响应格式

```json
{
  "error": {
    "code": "ERROR_CODE",
    "message": "Human readable message",
    "details": {
      "field": "fieldName",
      "reason": "Specific reason"
    },
    "timestamp": "2025-01-24T10:00:00Z",
    "traceId": "trace-uuid"
  }
}
```

### 标准错误代码

| HTTP Status | Code | 描述 |
|-------------|------|------|
| 400 | INVALID_REQUEST | 请求参数无效 |
| 401 | UNAUTHORIZED | 未授权 |
| 403 | FORBIDDEN | 禁止访问 |
| 404 | NOT_FOUND | 资源不存在 |
| 409 | CONFLICT | 资源冲突 |
| 422 | VALIDATION_ERROR | 业务验证失败 |
| 500 | INTERNAL_ERROR | 内部错误 |
| 503 | SERVICE_UNAVAILABLE | 服务不可用 |

---

## 分页

### 请求参数

```
GET /service-domain/{id}/transactions?
  page=1&
  pageSize=20&
  sortBy=transactionDate&
  sortOrder=desc
```

### 响应格式

```json
{
  "transactions": [...],
  "pagination": {
    "page": 1,
    "pageSize": 20,
    "totalPages": 10,
    "totalRecords": 200
  },
  "links": {
    "self": "/transactions?page=1",
    "first": "/transactions?page=1",
    "prev": null,
    "next": "/transactions?page=2",
    "last": "/transactions?page=10"
  }
}
```

---

## 版本控制

### URL 版本

```
/v1/customer-profile/{id}/retrieve
/v2/customer-profile/{id}/retrieve
```

### Header 版本

```http
Accept: application/vnd.bian.v1+json
```

---

## 安全要求

### 认证

- OAuth 2.0
- OpenID Connect
- mTLS（双向 TLS）

### 授权

- Scope-based access control
- Role-based access control

### 数据保护

- TLS 1.2+
- 敏感数据加密
- 数据脱敏
