# BIAN Skill - 银行业架构网络

## 概述

BIAN (Banking Industry Architecture Network) 是一个独立的、会员驱动的非营利组织，致力于建立银行业务能力的标准化语义框架。BIAN 提供了一个标准化的银行服务景观，帮助银行实现 IT 架构的互操作性和灵活性。

## 何时使用

当用户需要：
- 了解或应用 BIAN 银行业架构标准
- 设计银行业务能力模型
- 定义银行服务域 (Service Domain)
- 设计银行 API 和服务接口
- 规划银行核心系统现代化
- 建立银行业务与 IT 的对齐

## BIAN 核心概念

### BIAN 服务景观

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                        BIAN Service Landscape                                │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                              │
│  Business Area (业务领域)                                                    │
│  ┌─────────────────────────────────────────────────────────────────────┐   │
│  │  Reference Data    │  Sales & Service  │  Operations  │  Risk & ...  │   │
│  └─────────────────────────────────────────────────────────────────────┘   │
│                                    │                                         │
│                                    ▼                                         │
│  Business Domain (业务域)                                                    │
│  ┌─────────────────────────────────────────────────────────────────────┐   │
│  │  Customer Mgmt  │  Product Mgmt  │  Channel Mgmt  │  Party Mgmt     │   │
│  └─────────────────────────────────────────────────────────────────────┘   │
│                                    │                                         │
│                                    ▼                                         │
│  Service Domain (服务域)                                                     │
│  ┌─────────────────────────────────────────────────────────────────────┐   │
│  │  Customer       │  Party          │  Product       │  Account       │   │
│  │  Profile        │  Reference      │  Directory     │  Management    │   │
│  │  Management     │  Data Directory │                │                │   │
│  └─────────────────────────────────────────────────────────────────────┘   │
│                                    │                                         │
│                                    ▼                                         │
│  Service Operations (服务操作)                                               │
│  ┌─────────────────────────────────────────────────────────────────────┐   │
│  │  Initiate  │  Execute  │  Request  │  Retrieve  │  Update  │ ...   │   │
│  └─────────────────────────────────────────────────────────────────────┘   │
│                                                                              │
└─────────────────────────────────────────────────────────────────────────────┘
```

### BIAN 层次结构

| 层次 | 描述 | 数量 |
|------|------|------|
| **Business Area** | 最高层业务分类 | 11 个 |
| **Business Domain** | 业务领域分组 | ~50 个 |
| **Service Domain** | 核心能力单元 | ~300+ 个 |
| **Service Operation** | 具体服务操作 | 标准化动作 |

---

## 11 大业务领域 (Business Areas)

### 1. Reference Data (参考数据)

管理银行运营所需的参考数据和主数据。

**关键服务域**:
- Party Reference Data Directory
- Product Directory
- Location Data Management
- Market Data Service

---

### 2. Sales & Service (销售与服务)

管理客户关系和销售活动。

**关键服务域**:
- Customer Relationship Management
- Customer Offer
- Sales Product Agreement
- Customer Surveys

---

### 3. Operations & Execution (运营与执行)

执行银行日常业务操作。

**关键服务域**:
- Payment Order
- Payment Execution
- Card Transaction
- Trade Execution

---

### 4. Risk & Compliance (风险与合规)

管理风险和合规要求。

**关键服务域**:
- Credit Risk Assessment
- Market Risk Assessment
- Operational Risk Assessment
- Regulatory Compliance

---

### 5. Finance & Accounting (财务与会计)

管理财务和会计活动。

**关键服务域**:
- Financial Accounting
- General Ledger
- Product Profit & Loss
- Financial Statement Assessment

---

### 6. Business Support (业务支持)

提供业务支持功能。

**关键服务域**:
- Customer Billing
- Collections
- Correspondence Management
- Customer Workbench

---

### 7. Products (产品)

管理银行产品和服务。

**关键服务域**:
- Savings Account
- Current Account
- Loan
- Credit Card
- Mortgage
- Investment Portfolio

---

### 8. Channels (渠道)

管理客户交互渠道。

**关键服务域**:
- Branch Operations
- ATM Operations
- E-Branch Operations
- Contact Center Operations

---

### 9. Business Development (业务发展)

支持业务发展和创新。

**关键服务域**:
- Product Design
- Campaign Management
- Market Analysis
- Competitive Analysis

---

### 10. Corporate Services (企业服务)

管理企业级服务。

**关键服务域**:
- Human Resource Management
- Facilities Management
- IT Operations
- Security Administration

---

### 11. Business Direction (业务方向)

战略规划和业务管理。

**关键服务域**:
- Business Architecture
- Strategic Planning
- Enterprise Governance
- Business Development Strategy

---

## 核心服务域详解

### Customer Management (客户管理)

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                       Customer Management Domain                             │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                              │
│  ┌─────────────────────┐    ┌─────────────────────┐                        │
│  │ Customer Profile    │    │ Customer Relationship│                        │
│  │ Management          │    │ Management           │                        │
│  │                     │    │                      │                        │
│  │ • Profile Data      │    │ • Relationship Status│                        │
│  │ • Preferences       │    │ • Interaction History│                        │
│  │ • Demographics      │    │ • Satisfaction Score │                        │
│  └─────────────────────┘    └─────────────────────┘                        │
│                                                                              │
│  ┌─────────────────────┐    ┌─────────────────────┐                        │
│  │ Customer Offer      │    │ Customer Access      │                        │
│  │ Management          │    │ Entitlement          │                        │
│  │                     │    │                      │                        │
│  │ • Product Offers    │    │ • Authentication     │                        │
│  │ • Personalization   │    │ • Authorization      │                        │
│  │ • Campaign Targeting│    │ • Channel Access     │                        │
│  └─────────────────────┘    └─────────────────────┘                        │
│                                                                              │
│  ┌─────────────────────┐    ┌─────────────────────┐                        │
│  │ Customer Behavioral │    │ Customer Credit      │                        │
│  │ Insights            │    │ Rating               │                        │
│  │                     │    │                      │                        │
│  │ • Behavior Analysis │    │ • Credit Score       │                        │
│  │ • Predictive Models │    │ • Risk Assessment    │                        │
│  │ • Segmentation      │    │ • Credit Limit       │                        │
│  └─────────────────────┘    └─────────────────────┘                        │
│                                                                              │
└─────────────────────────────────────────────────────────────────────────────┘
```

---

### Party Data Management (当事方数据管理)

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                        Party Data Management Domain                          │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                              │
│  ┌─────────────────────┐    ┌─────────────────────┐                        │
│  │ Party Reference     │    │ Party Authentication │                        │
│  │ Data Directory      │    │                      │                        │
│  │                     │    │ • Identity Verify    │                        │
│  │ • Party Registry    │    │ • KYC/AML Check      │                        │
│  │ • Entity Resolution │    │ • Document Verify    │                        │
│  │ • Golden Record     │    │                      │                        │
│  └─────────────────────┘    └─────────────────────┘                        │
│                                                                              │
│  ┌─────────────────────┐    ┌─────────────────────┐                        │
│  │ Party Lifecycle     │    │ Party Data Quality   │                        │
│  │ Management          │    │ Management           │                        │
│  │                     │    │                      │                        │
│  │ • Onboarding        │    │ • Data Validation    │                        │
│  │ • Maintenance       │    │ • Deduplication      │                        │
│  │ • Offboarding       │    │ • Enrichment         │                        │
│  └─────────────────────┘    └─────────────────────┘                        │
│                                                                              │
└─────────────────────────────────────────────────────────────────────────────┘
```

---

### Payment Services (支付服务)

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                         Payment Services Domain                              │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                              │
│  ┌─────────────────────┐    ┌─────────────────────┐                        │
│  │ Payment Order       │    │ Payment Execution    │                        │
│  │                     │    │                      │                        │
│  │ • Order Initiation  │───►│ • Clearing           │                        │
│  │ • Validation        │    │ • Settlement         │                        │
│  │ • Authorization     │    │ • Reconciliation     │                        │
│  └─────────────────────┘    └─────────────────────┘                        │
│           │                          │                                       │
│           ▼                          ▼                                       │
│  ┌─────────────────────┐    ┌─────────────────────┐                        │
│  │ Payment Network     │    │ Correspondent       │                        │
│  │                     │    │ Bank Operations     │                        │
│  │ • SWIFT             │    │                      │                        │
│  │ • ACH               │    │ • Nostro/Vostro     │                        │
│  │ • SEPA              │    │ • FX Settlement      │                        │
│  └─────────────────────┘    └─────────────────────┘                        │
│                                                                              │
└─────────────────────────────────────────────────────────────────────────────┘
```

---

## BIAN 服务操作 (Service Operations)

### 标准化操作类型

| 操作 | 描述 | 示例 |
|------|------|------|
| **Initiate** | 创建新实例 | 发起贷款申请 |
| **Create** | 创建数据记录 | 创建客户档案 |
| **Register** | 注册到系统 | 注册新产品 |
| **Evaluate** | 评估判断 | 评估信用风险 |
| **Provide** | 提供服务 | 提供账户信息 |
| **Update** | 更新数据 | 更新客户地址 |
| **Control** | 控制操作 | 控制交易限额 |
| **Execute** | 执行处理 | 执行支付 |
| **Request** | 发起请求 | 请求账户余额 |
| **Retrieve** | 查询数据 | 检索交易历史 |
| **Notify** | 发送通知 | 通知交易完成 |
| **Authorize** | 授权操作 | 授权大额转账 |

### 服务操作模式

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                      Service Operation Pattern                               │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                              │
│  请求模式:                                                                   │
│  ┌─────────────┐    ┌─────────────┐    ┌─────────────┐                     │
│  │  Consumer   │───►│  Service    │───►│  Provider   │                     │
│  │             │◄───│  Domain     │◄───│             │                     │
│  └─────────────┘    └─────────────┘    └─────────────┘                     │
│                                                                              │
│  事件模式:                                                                   │
│  ┌─────────────┐    ┌─────────────┐    ┌─────────────┐                     │
│  │  Publisher  │───►│   Event     │───►│ Subscriber  │                     │
│  │             │    │   Bus       │    │             │                     │
│  └─────────────┘    └─────────────┘    └─────────────┘                     │
│                                                                              │
└─────────────────────────────────────────────────────────────────────────────┘
```

---

## BIAN API 标准

### RESTful API 设计

BIAN 定义了标准化的 API 端点结构：

```
/{service-domain}/{sd-reference-id}/{behavior-qualifier}/{bq-reference-id}/{action}

示例:
/customer-profile/CPR123/identity/ID456/retrieve
/payment-order/PO789/execute
/current-account/CA001/deposit/DEP002/update
```

### API 组件

| 组件 | 描述 | 示例 |
|------|------|------|
| Service Domain | 服务域标识 | customer-profile |
| SD Reference ID | 服务域实例 ID | CPR123 |
| Behavior Qualifier | 行为限定符 | identity, balance |
| BQ Reference ID | 行为限定符实例 ID | ID456 |
| Action | 操作动作 | retrieve, update |

### 标准请求/响应格式

```json
// 请求示例: 检索客户档案
GET /customer-profile/CPR123/retrieve

// 响应示例
{
  "customerProfileRecord": {
    "customerReference": "CPR123",
    "customerName": "张三",
    "customerType": "Individual",
    "customerProfile": {
      "demographics": {
        "dateOfBirth": "1985-06-15",
        "nationality": "CN"
      },
      "preferences": {
        "communicationChannel": "Email",
        "language": "zh-CN"
      }
    }
  }
}
```

---

## BIAN 与其他框架的关系

### BIAN 与 TOGAF

| 维度 | BIAN | TOGAF |
|------|------|-------|
| **范围** | 银行业专属 | 通用企业架构 |
| **层次** | 业务能力和服务 | 全架构层次 |
| **标准化** | 预定义服务域 | 方法论框架 |
| **互补** | 提供银行业务内容 | 提供架构方法 |

### BIAN 与 ArchiMate

BIAN 服务域可以映射到 ArchiMate 元素：

| BIAN 概念 | ArchiMate 元素 |
|-----------|---------------|
| Business Area | Business Function (L1) |
| Business Domain | Business Function (L2) |
| Service Domain | Business Service |
| Service Operation | Business Process |

### BIAN 与 IT4IT

| 维度 | BIAN | IT4IT |
|------|------|-------|
| **范围** | 银行业务能力 | IT 管理能力 |
| **互补** | 定义业务服务 | 管理 IT 服务 |

---

## 实施指南

### 实施路径

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                      BIAN Implementation Roadmap                             │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                              │
│  Phase 1: 评估和规划                                                         │
│  ├── 当前架构评估                                                            │
│  ├── BIAN 服务域映射                                                         │
│  ├── 差距分析                                                                │
│  └── 实施路线图制定                                                          │
│                                                                              │
│  Phase 2: 核心能力建设                                                       │
│  ├── Party Data Management                                                  │
│  ├── Customer Management                                                    │
│  ├── Product Directory                                                      │
│  └── Account Management                                                     │
│                                                                              │
│  Phase 3: 交易能力建设                                                       │
│  ├── Payment Services                                                       │
│  ├── Card Services                                                          │
│  ├── Loan Services                                                          │
│  └── Investment Services                                                    │
│                                                                              │
│  Phase 4: 高级能力建设                                                       │
│  ├── Risk Management                                                        │
│  ├── Compliance                                                             │
│  ├── Analytics                                                              │
│  └── Open Banking APIs                                                      │
│                                                                              │
└─────────────────────────────────────────────────────────────────────────────┘
```

### 服务域优先级矩阵

| 优先级 | 服务域 | 原因 |
|--------|--------|------|
| **P0** | Party Reference Data | 基础主数据 |
| **P0** | Customer Profile | 客户核心数据 |
| **P0** | Current Account | 核心产品 |
| **P1** | Payment Order | 核心交易 |
| **P1** | Product Directory | 产品管理 |
| **P1** | Customer Offer | 销售支持 |
| **P2** | Credit Risk | 风险管理 |
| **P2** | Regulatory Compliance | 合规要求 |
| **P3** | Customer Insights | 高级分析 |

---

## 最佳实践

### 1. 渐进式采用

```
建议:
- 从核心服务域开始
- 逐步扩展到完整景观
- 保持与现有系统的集成
- 避免大爆炸式改造
```

### 2. API 优先设计

```
建议:
- 采用 BIAN API 标准
- 设计可重用的 API
- 建立 API 治理
- 支持 Open Banking
```

### 3. 数据驱动

```
建议:
- 建立主数据管理
- 统一数据模型
- 确保数据质量
- 实现数据共享
```

### 4. 微服务架构

```
建议:
- 每个服务域独立部署
- 松耦合设计
- 事件驱动集成
- 容器化部署
```

---

## 资源文件

### 模板文件
- `assets/bian-service-landscape.drawio` - BIAN 服务景观图

### 参考文档
- `references/service-domain-catalog.md` - 服务域目录
- `references/api-design-guide.md` - API 设计指南
- `references/mapping-guide.md` - 映射指南

---

## 常见问题

### Q1: BIAN 和自定义服务域如何平衡？

A: 
- 优先使用 BIAN 标准服务域
- 对于本地化需求，可以扩展服务域
- 保持命名和语义的一致性
- 记录扩展和偏离

### Q2: 如何处理遗留系统？

A: 
- 使用反腐层 (ACL) 封装遗留系统
- 逐步迁移到 BIAN 服务域
- 保持业务连续性
- 建立清晰的迁移路径

### Q3: BIAN 如何支持 Open Banking？

A: 
- BIAN API 标准与 Open Banking 对齐
- 服务域支持 PSD2 等法规要求
- 提供标准化的第三方集成接口
- 支持同意管理和访问控制

### Q4: 小型银行是否需要完整实施 BIAN？

A: 
- 不需要完整实施
- 选择核心服务域
- 根据业务优先级逐步采用
- 关注最高价值的能力

---

## 更新日志

- **v1.0.0** (2025-01-24): 初始版本
  - BIAN 服务景观和层次结构
  - 11 大业务领域
  - 核心服务域详解
  - 服务操作标准
  - API 设计指南
  - 实施最佳实践

## 相关资源

- [BIAN Official Website](https://bian.org/)
- [BIAN API Portal](https://portal.bian.org/)
- [BIAN Service Landscape](https://bian.org/servicelandscape/)
- [DeepArchi 架构管理平台](https://deeparchi.com)
