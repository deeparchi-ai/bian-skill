# BIAN Skill - 使用示例

## 示例 1：银行服务域设计

### 场景

需要基于 BIAN 设计零售银行的核心服务域。

### 输入

"帮我基于 BIAN 设计零售银行核心服务域架构"

### 输出

```markdown
# 零售银行 BIAN 服务域架构

## 1. 服务域全景

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                     Retail Banking Service Domains                           │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                              │
│  客户管理层                                                                  │
│  ┌─────────────┐ ┌─────────────┐ ┌─────────────┐ ┌─────────────┐          │
│  │ Customer    │ │ Customer    │ │ Customer    │ │ Customer    │          │
│  │ Profile     │ │ Relationship│ │ Offer       │ │ Behavioral  │          │
│  │ Management  │ │ Management  │ │             │ │ Insights    │          │
│  └─────────────┘ └─────────────┘ └─────────────┘ └─────────────┘          │
│                                                                              │
│  ════════════════════════════════════════════════════════════════════════  │
│                                                                              │
│  产品层                                                                      │
│  ┌─────────────┐ ┌─────────────┐ ┌─────────────┐ ┌─────────────┐          │
│  │ Current     │ │ Savings     │ │ Consumer    │ │ Credit      │          │
│  │ Account     │ │ Account     │ │ Loan        │ │ Card        │          │
│  └─────────────┘ └─────────────┘ └─────────────┘ └─────────────┘          │
│                                                                              │
│  ┌─────────────┐ ┌─────────────┐ ┌─────────────┐                          │
│  │ Mortgage    │ │ Term        │ │ Investment  │                          │
│  │             │ │ Deposit     │ │ Portfolio   │                          │
│  └─────────────┘ └─────────────┘ └─────────────┘                          │
│                                                                              │
│  ════════════════════════════════════════════════════════════════════════  │
│                                                                              │
│  交易处理层                                                                  │
│  ┌─────────────┐ ┌─────────────┐ ┌─────────────┐ ┌─────────────┐          │
│  │ Payment     │ │ Payment     │ │ Card        │ │ Direct      │          │
│  │ Order       │ │ Execution   │ │ Transaction │ │ Debit       │          │
│  └─────────────┘ └─────────────┘ └─────────────┘ └─────────────┘          │
│                                                                              │
│  ════════════════════════════════════════════════════════════════════════  │
│                                                                              │
│  支撑服务层                                                                  │
│  ┌─────────────┐ ┌─────────────┐ ┌─────────────┐ ┌─────────────┐          │
│  │ Party       │ │ Product     │ │ Regulatory  │ │ Customer    │          │
│  │ Reference   │ │ Directory   │ │ Compliance  │ │ Billing     │          │
│  │ Data        │ │             │ │             │ │             │          │
│  └─────────────┘ └─────────────┘ └─────────────┘ └─────────────┘          │
│                                                                              │
└─────────────────────────────────────────────────────────────────────────────┘
```

## 2. 核心服务域详细设计

### 2.1 Customer Profile Management

**功能描述**: 管理客户基本信息和偏好设置

**服务操作**:
| 操作 | HTTP 方法 | 端点 | 描述 |
|------|----------|------|------|
| Initiate | POST | /customer-profile/initiate | 创建客户档案 |
| Update | PUT | /customer-profile/{id}/update | 更新档案信息 |
| Retrieve | GET | /customer-profile/{id}/retrieve | 获取档案信息 |
| Control | PUT | /customer-profile/{id}/control | 控制档案状态 |

**数据模型**:
```json
{
  "customerProfileRecord": {
    "customerReference": "string",
    "partyReference": "string",
    "customerName": "string",
    "customerType": "Individual|Corporate",
    "demographics": {
      "dateOfBirth": "date",
      "gender": "string",
      "nationality": "string",
      "residency": "string"
    },
    "preferences": {
      "communicationChannel": "string",
      "language": "string",
      "marketingConsent": "boolean"
    },
    "contactInfo": {
      "email": "string",
      "phone": "string",
      "address": {}
    }
  }
}
```

### 2.2 Current Account

**功能描述**: 管理活期账户

**服务操作**:
| 操作 | HTTP 方法 | 端点 | 描述 |
|------|----------|------|------|
| Initiate | POST | /current-account/initiate | 开立账户 |
| Update | PUT | /current-account/{id}/update | 更新账户 |
| Retrieve | GET | /current-account/{id}/retrieve | 查询账户 |
| Execute | POST | /current-account/{id}/deposit/execute | 存款 |
| Execute | POST | /current-account/{id}/withdrawal/execute | 取款 |

**数据模型**:
```json
{
  "currentAccountFacility": {
    "productInstanceReference": "string",
    "customerReference": "string",
    "accountNumber": "string",
    "accountType": "Checking|Premium",
    "accountCurrency": "string",
    "accountBalance": {
      "availableBalance": "number",
      "ledgerBalance": "number",
      "holdAmount": "number"
    },
    "accountStatus": "Active|Dormant|Closed",
    "interestRate": "number",
    "overdraftLimit": "number"
  }
}
```

### 2.3 Payment Order

**功能描述**: 管理支付订单

**服务操作**:
| 操作 | HTTP 方法 | 端点 | 描述 |
|------|----------|------|------|
| Initiate | POST | /payment-order/initiate | 发起支付 |
| Update | PUT | /payment-order/{id}/update | 更新支付 |
| Retrieve | GET | /payment-order/{id}/retrieve | 查询支付 |
| Execute | POST | /payment-order/{id}/execute | 执行支付 |

**数据模型**:
```json
{
  "paymentOrderTransaction": {
    "paymentOrderReference": "string",
    "payerReference": "string",
    "payerBankReference": "string",
    "payeeReference": "string",
    "payeeBankReference": "string",
    "amount": {
      "value": "number",
      "currency": "string"
    },
    "paymentType": "Transfer|DirectDebit|StandingOrder",
    "paymentPurpose": "string",
    "valueDate": "date",
    "status": "Pending|Completed|Failed"
  }
}
```

## 3. 服务域关系

```
┌─────────────────────────────────────────────────────────────────┐
│                    Service Domain Relationships                  │
├─────────────────────────────────────────────────────────────────┤
│                                                                  │
│  Customer Profile ◄───────────────────────► Party Reference     │
│        │                                          │              │
│        │ owns                                     │ validates    │
│        ▼                                          ▼              │
│  Current Account ◄────────────────────────► Payment Order       │
│        │                                          │              │
│        │ executes                                 │ settles      │
│        ▼                                          ▼              │
│  Card Transaction ◄───────────────────────► Payment Execution   │
│                                                                  │
└─────────────────────────────────────────────────────────────────┘
```

## 4. 实施优先级

| 阶段 | 服务域 | 优先级 | 依赖 |
|------|--------|--------|------|
| Phase 1 | Party Reference Data | P0 | - |
| Phase 1 | Customer Profile | P0 | Party Reference |
| Phase 1 | Product Directory | P0 | - |
| Phase 2 | Current Account | P0 | Customer, Product |
| Phase 2 | Savings Account | P1 | Customer, Product |
| Phase 2 | Payment Order | P0 | Account |
| Phase 3 | Consumer Loan | P1 | Customer, Account |
| Phase 3 | Credit Card | P1 | Customer, Account |
| Phase 4 | Customer Insights | P2 | All above |
```

---

## 示例 2：BIAN API 设计

### 场景

需要为客户管理设计 BIAN 标准 API。

### 输入

"帮我设计客户管理的 BIAN API"

### 输出

```markdown
# Customer Management API Design

## 1. API 概览

### 1.1 Customer Profile Management

**Base Path**: `/customer-profile`

| Operation | Method | Endpoint | Description |
|-----------|--------|----------|-------------|
| Initiate | POST | /customer-profile/initiate | 创建客户档案 |
| Update | PUT | /customer-profile/{cr-reference-id}/update | 更新档案 |
| Retrieve | GET | /customer-profile/{cr-reference-id}/retrieve | 获取档案 |
| Control | PUT | /customer-profile/{cr-reference-id}/control | 控制状态 |
| Request | POST | /customer-profile/{cr-reference-id}/request | 请求服务 |

### 1.2 Behavior Qualifiers

| BQ | Description | Operations |
|----|-------------|------------|
| Alert | 客户提醒 | Retrieve, Update |
| Preference | 偏好设置 | Retrieve, Update |
| Status | 状态信息 | Retrieve |
| Rating | 客户评级 | Retrieve |

## 2. API 详细设计

### 2.1 创建客户档案

**Endpoint**: `POST /customer-profile/initiate`

**Request**:
```json
{
  "customerProfileInitiation": {
    "partyReference": "PTY-001",
    "customerType": "Individual",
    "customerName": {
      "firstName": "张",
      "lastName": "三",
      "fullName": "张三"
    },
    "demographics": {
      "dateOfBirth": "1985-06-15",
      "gender": "Male",
      "nationality": "CN",
      "idType": "ID_CARD",
      "idNumber": "110101198506150011"
    },
    "contactInfo": {
      "email": "zhangsan@example.com",
      "mobile": "+86-13800138000",
      "address": {
        "streetAddress": "朝阳区xxx街道",
        "city": "北京",
        "postalCode": "100000",
        "country": "CN"
      }
    },
    "preferences": {
      "language": "zh-CN",
      "communicationChannel": "Email",
      "marketingConsent": true
    }
  }
}
```

**Response** (201 Created):
```json
{
  "customerProfileRecord": {
    "customerProfileReference": "CPR-20250124-001",
    "customerReference": "CUS-001",
    "partyReference": "PTY-001",
    "status": "Active",
    "createdDate": "2025-01-24T10:00:00Z",
    "customerProfileInitiation": {
      // ... 返回创建的数据
    }
  }
}
```

### 2.2 获取客户档案

**Endpoint**: `GET /customer-profile/{cr-reference-id}/retrieve`

**Path Parameters**:
- `cr-reference-id`: 客户档案引用 ID

**Query Parameters**:
- `includePreferences`: boolean (可选)
- `includeRating`: boolean (可选)

**Response** (200 OK):
```json
{
  "customerProfileRecord": {
    "customerProfileReference": "CPR-20250124-001",
    "customerReference": "CUS-001",
    "partyReference": "PTY-001",
    "customerType": "Individual",
    "customerName": {
      "firstName": "张",
      "lastName": "三",
      "fullName": "张三"
    },
    "demographics": { ... },
    "contactInfo": { ... },
    "preferences": { ... },
    "status": "Active",
    "createdDate": "2025-01-24T10:00:00Z",
    "lastUpdatedDate": "2025-01-24T10:00:00Z"
  }
}
```

### 2.3 更新客户偏好

**Endpoint**: `PUT /customer-profile/{cr-reference-id}/preference/{bq-reference-id}/update`

**Request**:
```json
{
  "preferenceUpdate": {
    "language": "en-US",
    "communicationChannel": "SMS",
    "marketingConsent": false,
    "notificationPreferences": {
      "transactionAlert": true,
      "promotionalOffer": false,
      "accountStatement": "Monthly"
    }
  }
}
```

**Response** (200 OK):
```json
{
  "preferenceRecord": {
    "preferenceReference": "PREF-001",
    "customerProfileReference": "CPR-20250124-001",
    "status": "Updated",
    "updatedDate": "2025-01-24T11:00:00Z",
    "preferenceUpdate": { ... }
  }
}
```

## 3. 错误处理

### 3.1 标准错误响应

```json
{
  "error": {
    "code": "CUSTOMER_NOT_FOUND",
    "message": "Customer profile not found",
    "details": {
      "customerProfileReference": "CPR-INVALID"
    },
    "timestamp": "2025-01-24T10:00:00Z",
    "traceId": "abc123"
  }
}
```

### 3.2 错误代码

| Code | HTTP Status | Description |
|------|-------------|-------------|
| CUSTOMER_NOT_FOUND | 404 | 客户不存在 |
| INVALID_REQUEST | 400 | 请求参数错误 |
| DUPLICATE_CUSTOMER | 409 | 客户已存在 |
| UNAUTHORIZED | 401 | 未授权 |
| INTERNAL_ERROR | 500 | 内部错误 |

## 4. OpenAPI 规范片段

```yaml
openapi: 3.0.0
info:
  title: BIAN Customer Profile Management API
  version: 1.0.0

paths:
  /customer-profile/initiate:
    post:
      summary: Create customer profile
      operationId: initiateCustomerProfile
      requestBody:
        required: true
        content:
          application/json:
            schema:
              $ref: '#/components/schemas/CustomerProfileInitiation'
      responses:
        '201':
          description: Created
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/CustomerProfileRecord'
        '400':
          $ref: '#/components/responses/BadRequest'

  /customer-profile/{cr-reference-id}/retrieve:
    get:
      summary: Retrieve customer profile
      operationId: retrieveCustomerProfile
      parameters:
        - name: cr-reference-id
          in: path
          required: true
          schema:
            type: string
      responses:
        '200':
          description: Success
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/CustomerProfileRecord'
        '404':
          $ref: '#/components/responses/NotFound'

components:
  schemas:
    CustomerProfileInitiation:
      type: object
      properties:
        partyReference:
          type: string
        customerType:
          type: string
          enum: [Individual, Corporate]
        customerName:
          $ref: '#/components/schemas/CustomerName'
        demographics:
          $ref: '#/components/schemas/Demographics'
        contactInfo:
          $ref: '#/components/schemas/ContactInfo'
```
```

---

## 示例 3：服务域映射

### 场景

需要将现有银行系统映射到 BIAN 服务域。

### 输入

"帮我把现有核心银行系统映射到 BIAN 服务域"

### 输出

```markdown
# 核心银行系统 BIAN 映射

## 1. 现有系统分析

### 1.1 当前系统模块

| 系统模块 | 功能 | 技术栈 |
|---------|------|--------|
| CIF | 客户信息管理 | COBOL/DB2 |
| DDA | 活期账户 | COBOL/DB2 |
| SAV | 储蓄账户 | COBOL/DB2 |
| LOAN | 贷款管理 | COBOL/DB2 |
| CARD | 卡片管理 | Java/Oracle |
| PAYMENT | 支付清算 | Java/Oracle |
| GL | 总账 | COBOL/DB2 |

## 2. BIAN 服务域映射

### 2.1 映射矩阵

| 现有模块 | BIAN 服务域 | 映射类型 | 差距 |
|---------|------------|---------|------|
| CIF | Party Reference Data Directory | 1:1 | 缺少 Entity Resolution |
| CIF | Customer Profile Management | 1:1 | 缺少偏好管理 |
| DDA | Current Account | 1:1 | - |
| SAV | Savings Account | 1:1 | - |
| LOAN | Consumer Loan | 1:N | 拆分为多个服务域 |
| CARD | Credit Card | 1:1 | 缺少虚拟卡 |
| CARD | Debit Card | 1:1 | - |
| PAYMENT | Payment Order | 1:1 | - |
| PAYMENT | Payment Execution | 1:1 | - |
| GL | Financial Accounting | 1:1 | - |

### 2.2 详细映射

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                        CIF System Mapping                                    │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                              │
│  CIF 模块功能                        BIAN 服务域                             │
│  ┌─────────────────┐                ┌─────────────────┐                    │
│  │ 客户基本信息     │ ─────────────► │ Party Reference │                    │
│  │ - 姓名          │                │ Data Directory  │                    │
│  │ - 证件          │                └─────────────────┘                    │
│  │ - 地址          │                                                        │
│  └─────────────────┘                ┌─────────────────┐                    │
│                                     │ Customer Profile│                    │
│  ┌─────────────────┐ ─────────────► │ Management      │                    │
│  │ 客户偏好        │                └─────────────────┘                    │
│  │ - 通知方式      │                                                        │
│  │ - 语言          │                ┌─────────────────┐                    │
│  └─────────────────┘                │ Customer        │                    │
│                       ─────────────► │ Relationship    │                    │
│  ┌─────────────────┐                │ Management      │                    │
│  │ 客户关系        │                └─────────────────┘                    │
│  │ - 客户经理      │                                                        │
│  │ - 关系状态      │                                                        │
│  └─────────────────┘                                                        │
│                                                                              │
└─────────────────────────────────────────────────────────────────────────────┘
```

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                        LOAN System Mapping                                   │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                              │
│  LOAN 模块功能                       BIAN 服务域                             │
│  ┌─────────────────┐                ┌─────────────────┐                    │
│  │ 消费贷款        │ ─────────────► │ Consumer Loan   │                    │
│  └─────────────────┘                └─────────────────┘                    │
│                                                                              │
│  ┌─────────────────┐                ┌─────────────────┐                    │
│  │ 房贷           │ ─────────────► │ Mortgage        │                    │
│  └─────────────────┘                └─────────────────┘                    │
│                                                                              │
│  ┌─────────────────┐                ┌─────────────────┐                    │
│  │ 信用评估        │ ─────────────► │ Credit Risk     │                    │
│  │                │                │ Assessment      │                    │
│  └─────────────────┘                └─────────────────┘                    │
│                                                                              │
│  ┌─────────────────┐                ┌─────────────────┐                    │
│  │ 贷款定价        │ ─────────────► │ Product Pricing │                    │
│  │                │                │                 │                    │
│  └─────────────────┘                └─────────────────┘                    │
│                                                                              │
└─────────────────────────────────────────────────────────────────────────────┘
```

## 3. 差距分析

### 3.1 功能差距

| BIAN 服务域 | 现有能力 | 差距 | 优先级 |
|------------|---------|------|--------|
| Customer Behavioral Insights | 无 | 需新建 | P2 |
| Customer Offer | 部分 | 需增强 | P1 |
| Party Authentication | 部分 | 需增强 KYC | P0 |
| Open Banking API | 无 | 需新建 | P1 |
| Real-time Payment | 部分 | 需增强 | P1 |

### 3.2 技术差距

| 方面 | 现状 | 目标 | 差距 |
|------|------|------|------|
| API 标准 | 内部私有 | BIAN RESTful | 需要 API 层 |
| 数据格式 | 固定长度 | JSON | 需要转换层 |
| 集成方式 | 批量/MQ | 事件驱动 | 需要 Event Bus |
| 部署模式 | 单体 | 微服务 | 渐进式拆分 |

## 4. 迁移策略

### 4.1 分阶段迁移

```
Phase 1: API 网关层
┌─────────────────────────────────────────────────────────────────┐
│  BIAN API Gateway                                                │
│  ┌─────────────────────────────────────────────────────────┐   │
│  │ /customer-profile/* │ /current-account/* │ /payment/*   │   │
│  └─────────────────────────────────────────────────────────┘   │
│                              │                                   │
│                              ▼                                   │
│  ┌─────────────────────────────────────────────────────────┐   │
│  │                Anti-Corruption Layer                     │   │
│  │          (协议转换、数据映射、格式转换)                    │   │
│  └─────────────────────────────────────────────────────────┘   │
│                              │                                   │
│                              ▼                                   │
│  ┌─────────────────────────────────────────────────────────┐   │
│  │              Legacy Core Banking System                  │   │
│  │         CIF │ DDA │ SAV │ LOAN │ PAYMENT │ GL           │   │
│  └─────────────────────────────────────────────────────────┘   │
└─────────────────────────────────────────────────────────────────┘
```

### 4.2 渐进式替换

```
Phase 2-4: 服务域逐步独立

┌──────────────┐     ┌──────────────┐     ┌──────────────┐
│ New Customer │     │ New Payment  │     │ New Account  │
│ Service      │     │ Service      │     │ Service      │
└──────┬───────┘     └──────┬───────┘     └──────┬───────┘
       │                    │                    │
       │    Event Bus       │                    │
       └────────────────────┴────────────────────┘
                            │
       ┌────────────────────┴────────────────────┐
       │        Legacy (Shrinking)               │
       │         DDA │ SAV │ LOAN │ GL           │
       └─────────────────────────────────────────┘
```
```

---

## 示例 4：Open Banking API 设计

### 场景

需要基于 BIAN 设计 Open Banking API。

### 输入

"帮我基于 BIAN 设计 Open Banking API"

### 输出

```markdown
# Open Banking API Design (BIAN-based)

## 1. API 分类

### 1.1 按 PSD2 要求分类

| 类别 | BIAN 服务域 | API |
|------|------------|-----|
| **Account Information** | Current Account, Savings Account | 账户信息查询 |
| **Payment Initiation** | Payment Order | 支付发起 |
| **Confirmation of Funds** | Current Account | 资金确认 |

### 1.2 API 端点设计

```
Open Banking APIs (BIAN-aligned)

Account Information:
├── GET  /accounts                           # 账户列表
├── GET  /accounts/{id}                      # 账户详情
├── GET  /accounts/{id}/balances             # 账户余额
├── GET  /accounts/{id}/transactions         # 交易记录
└── GET  /accounts/{id}/statements           # 账单

Payment Initiation:
├── POST /payment-initiation/domestic        # 国内转账
├── POST /payment-initiation/international   # 跨境转账
├── GET  /payment-initiation/{id}/status     # 支付状态
└── DELETE /payment-initiation/{id}          # 撤销支付

Confirmation of Funds:
└── POST /funds-confirmation                 # 资金确认
```

## 2. 账户信息 API

### 2.1 获取账户列表

**BIAN Mapping**: Current Account → Retrieve

**Endpoint**: `GET /accounts`

**Headers**:
```
Authorization: Bearer {access_token}
x-fapi-interaction-id: {uuid}
x-customer-user-agent: {user-agent}
```

**Response**:
```json
{
  "accounts": [
    {
      "accountId": "ACC-001",
      "accountType": "CurrentAccount",
      "accountSubType": "Checking",
      "status": "Active",
      "currency": "CNY",
      "nickname": "工资账户",
      "accountHolder": {
        "name": "张三"
      },
      "servicer": {
        "schemeName": "BICFI",
        "identification": "ABOCCNBJ"
      }
    }
  ],
  "links": {
    "self": "/accounts"
  },
  "meta": {
    "totalPages": 1
  }
}
```

### 2.2 获取账户余额

**BIAN Mapping**: Current Account → Balance BQ → Retrieve

**Endpoint**: `GET /accounts/{accountId}/balances`

**Response**:
```json
{
  "accountId": "ACC-001",
  "balances": [
    {
      "balanceType": "AvailableBalance",
      "amount": {
        "value": "10000.00",
        "currency": "CNY"
      },
      "creditDebitIndicator": "Credit",
      "dateTime": "2025-01-24T10:00:00Z"
    },
    {
      "balanceType": "LedgerBalance",
      "amount": {
        "value": "10500.00",
        "currency": "CNY"
      },
      "creditDebitIndicator": "Credit",
      "dateTime": "2025-01-24T10:00:00Z"
    }
  ]
}
```

## 3. 支付发起 API

### 3.1 发起国内转账

**BIAN Mapping**: Payment Order → Initiate

**Endpoint**: `POST /payment-initiation/domestic`

**Request**:
```json
{
  "paymentInitiation": {
    "instructionIdentification": "INS-001",
    "endToEndIdentification": "E2E-001",
    "instructedAmount": {
      "value": "1000.00",
      "currency": "CNY"
    },
    "debtorAccount": {
      "schemeName": "IBAN",
      "identification": "CN1234567890"
    },
    "creditorAccount": {
      "schemeName": "IBAN",
      "identification": "CN0987654321",
      "name": "李四"
    },
    "creditorAgent": {
      "schemeName": "BICFI",
      "identification": "ICBCCNBJ"
    },
    "remittanceInformation": {
      "unstructured": "转账备注"
    }
  }
}
```

**Response** (201 Created):
```json
{
  "paymentId": "PAY-20250124-001",
  "status": "AcceptedTechnicalValidation",
  "creationDateTime": "2025-01-24T10:00:00Z",
  "links": {
    "self": "/payment-initiation/domestic/PAY-20250124-001",
    "status": "/payment-initiation/PAY-20250124-001/status"
  }
}
```

## 4. 安全要求

### 4.1 认证授权

```
OAuth 2.0 + OpenID Connect

Authorization Flow:
1. TPP → ASPSP: Authorization Request
2. ASPSP → PSU: Authentication & Consent
3. PSU → ASPSP: Grant Consent
4. ASPSP → TPP: Authorization Code
5. TPP → ASPSP: Token Request
6. ASPSP → TPP: Access Token
```

### 4.2 证书要求

| 证书类型 | 用途 |
|---------|------|
| QWAC | TLS 客户端认证 |
| QSEAL | 请求签名 |

### 4.3 同意管理

```json
{
  "consent": {
    "consentId": "CON-001",
    "status": "Authorised",
    "permissions": [
      "ReadAccountsBasic",
      "ReadAccountsDetail",
      "ReadBalances",
      "ReadTransactionsBasic"
    ],
    "expirationDateTime": "2025-07-24T00:00:00Z",
    "transactionFromDateTime": "2024-01-24T00:00:00Z"
  }
}
```

## 5. BIAN 到 Open Banking 映射

| BIAN 服务域 | Open Banking API | 操作映射 |
|------------|-----------------|---------|
| Current Account | /accounts | Retrieve → GET |
| Current Account.Balance | /accounts/{id}/balances | Retrieve → GET |
| Current Account.Transaction | /accounts/{id}/transactions | Retrieve → GET |
| Payment Order | /payment-initiation | Initiate → POST |
| Payment Order | /payment-initiation/{id}/status | Retrieve → GET |
```

这些示例展示了 BIAN Skill 在不同场景下的应用，包括服务域设计、API 设计、系统映射和 Open Banking 实现。
