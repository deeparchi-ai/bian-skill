---
name: bian
version: 1.0.0
description: BIAN (Banking Industry Architecture Network) standard for banking service landscape. Provides service domain catalog, API design standards, and implementation guidance for banking architecture. Use this skill for banking architecture design, service domain modeling, banking API design, core banking modernization, or Open Banking implementation.
author: DeepArchi
license: MIT
keywords:
  - bian
  - banking
  - service-domain
  - open-banking
  - financial-services
  - api-banking
  - deeparchi
---

# BIAN Skill - 银行业架构网络

## 概述

BIAN (Banking Industry Architecture Network) 是银行业务能力的标准化语义框架，提供标准化的银行服务景观。

## 何时使用

当用户需要：
- 了解或应用 BIAN 银行业架构标准
- 设计银行业务能力模型
- 定义银行服务域 (Service Domain)
- 设计银行 API 和服务接口
- 规划银行核心系统现代化
- 实施 Open Banking

## 快速开始

1. 参考 `README.md` 了解 BIAN 核心概念
2. 查看 `references/service-domain-catalog.md` 了解完整服务域
3. 使用 `references/api-design-guide.md` 设计 API
4. 参考 `assets/bian-service-landscape.drawio` 查看服务景观

## 核心功能

- **服务景观**：11 大业务领域、300+ 服务域
- **服务操作**：标准化的操作类型（Initiate, Execute, Retrieve...）
- **API 标准**：RESTful API 设计规范
- **映射指南**：与 ArchiMate、TOGAF 的映射
- **实施路径**：渐进式采用建议

## BIAN 层次结构

```
Business Area (11个)
    └── Business Domain (~50个)
            └── Service Domain (300+个)
                    └── Service Operation (标准动作)
```

## 核心业务领域

| 业务领域 | 英文名 | 描述 |
|---------|--------|------|
| 参考数据 | Reference Data | 主数据和参考数据管理 |
| 销售服务 | Sales & Service | 客户关系和销售 |
| 运营执行 | Operations | 日常业务操作 |
| 风险合规 | Risk & Compliance | 风险和合规管理 |
| 财务会计 | Finance | 财务和会计 |
| 业务支持 | Business Support | 业务支持功能 |
| 产品 | Products | 银行产品管理 |
| 渠道 | Channels | 客户交互渠道 |

## 服务域速查

```
Customer Management:
  - Customer Profile Management
  - Customer Relationship Management
  - Customer Offer

Party Data:
  - Party Reference Data Directory
  - Party Authentication
  - Party Lifecycle Management

Payment:
  - Payment Order
  - Payment Execution
  - Card Transaction

Products:
  - Current Account
  - Savings Account
  - Loan
  - Credit Card
```

## API 端点格式

```
/{service-domain}/{sd-ref-id}/{behavior-qualifier}/{bq-ref-id}/{action}

示例:
GET /customer-profile/CPR123/retrieve
POST /payment-order/initiate
PUT /current-account/CA001/deposit/DEP002/execute
```

## 资源文件

- `README.md` - 完整技能文档
- `EXAMPLES.md` - 使用示例
- `assets/bian-service-landscape.drawio` - 服务景观图
- `references/service-domain-catalog.md` - 服务域目录
- `references/api-design-guide.md` - API 设计指南
- `references/mapping-guide.md` - 映射指南

## 相关链接

- [BIAN Official Website](https://bian.org/)
- [BIAN API Portal](https://portal.bian.org/)
- [DeepArchi 架构管理平台](https://deeparchi.com)
