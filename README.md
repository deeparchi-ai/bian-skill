> **🤖 AI-Maintained** — This repository is maintained by AI agents. Human commits (perhaps) zero. Liability (certainly) none. Fun (definitely) infinite.

1|# BIAN Skill - 银行业架构网络
2|
3|## 概述
4|
5|BIAN (Banking Industry Architecture Network) 是一个独立的、会员驱动的非营利组织，致力于建立银行业务能力的标准化语义框架。BIAN 提供了一个标准化的银行服务景观，帮助银行实现 IT 架构的互操作性和灵活性。
6|
7|## 何时使用
8|
9|当用户需要：
10|- 了解或应用 BIAN 银行业架构标准
11|- 设计银行业务能力模型
12|- 定义银行服务域 (Service Domain)
13|- 设计银行 API 和服务接口
14|- 规划银行核心系统现代化
15|- 建立银行业务与 IT 的对齐
16|
17|## BIAN 核心概念
18|
19|### BIAN 服务景观
20|
21|```
22|┌─────────────────────────────────────────────────────────────────────────────┐
23|│                        BIAN Service Landscape                                │
24|├─────────────────────────────────────────────────────────────────────────────┤
25|│                                                                              │
26|│  Business Area (业务领域)                                                    │
27|│  ┌─────────────────────────────────────────────────────────────────────┐   │
28|│  │  Reference Data    │  Sales & Service  │  Operations  │  Risk & ...  │   │
29|│  └─────────────────────────────────────────────────────────────────────┘   │
30|│                                    │                                         │
31|│                                    ▼                                         │
32|│  Business Domain (业务域)                                                    │
33|│  ┌─────────────────────────────────────────────────────────────────────┐   │
34|│  │  Customer Mgmt  │  Product Mgmt  │  Channel Mgmt  │  Party Mgmt     │   │
35|│  └─────────────────────────────────────────────────────────────────────┘   │
36|│                                    │                                         │
37|│                                    ▼                                         │
38|│  Service Domain (服务域)                                                     │
39|│  ┌─────────────────────────────────────────────────────────────────────┐   │
40|│  │  Customer       │  Party          │  Product       │  Account       │   │
41|│  │  Profile        │  Reference      │  Directory     │  Management    │   │
42|│  │  Management     │  Data Directory │                │                │   │
43|│  └─────────────────────────────────────────────────────────────────────┘   │
44|│                                    │                                         │
45|│                                    ▼                                         │
46|│  Service Operations (服务操作)                                               │
47|│  ┌─────────────────────────────────────────────────────────────────────┐   │
48|│  │  Initiate  │  Execute  │  Request  │  Retrieve  │  Update  │ ...   │   │
49|│  └─────────────────────────────────────────────────────────────────────┘   │
50|│                                                                              │
51|└─────────────────────────────────────────────────────────────────────────────┘
52|```
53|
54|### BIAN 层次结构
55|
56|| 层次 | 描述 | 数量 |
57||------|------|------|
58|| **Business Area** | 最高层业务分类 | 11 个 |
59|| **Business Domain** | 业务领域分组 | ~50 个 |
60|| **Service Domain** | 核心能力单元 | ~300+ 个 |
61|| **Service Operation** | 具体服务操作 | 标准化动作 |
62|
63|---
64|
65|## 11 大业务领域 (Business Areas)
66|
67|### 1. Reference Data (参考数据)
68|
69|管理银行运营所需的参考数据和主数据。
70|
71|**关键服务域**:
72|- Party Reference Data Directory
73|- Product Directory
74|- Location Data Management
75|- Market Data Service
76|
77|---
78|
79|### 2. Sales & Service (销售与服务)
80|
81|管理客户关系和销售活动。
82|
83|**关键服务域**:
84|- Customer Relationship Management
85|- Customer Offer
86|- Sales Product Agreement
87|- Customer Surveys
88|
89|---
90|
91|### 3. Operations & Execution (运营与执行)
92|
93|执行银行日常业务操作。
94|
95|**关键服务域**:
96|- Payment Order
97|- Payment Execution
98|- Card Transaction
99|- Trade Execution
100|
101|---
102|
103|### 4. Risk & Compliance (风险与合规)
104|
105|管理风险和合规要求。
106|
107|**关键服务域**:
108|- Credit Risk Assessment
109|- Market Risk Assessment
110|- Operational Risk Assessment
111|- Regulatory Compliance
112|
113|---
114|
115|### 5. Finance & Accounting (财务与会计)
116|
117|管理财务和会计活动。
118|
119|**关键服务域**:
120|- Financial Accounting
121|- General Ledger
122|- Product Profit & Loss
123|- Financial Statement Assessment
124|
125|---
126|
127|### 6. Business Support (业务支持)
128|
129|提供业务支持功能。
130|
131|**关键服务域**:
132|- Customer Billing
133|- Collections
134|- Correspondence Management
135|- Customer Workbench
136|
137|---
138|
139|### 7. Products (产品)
140|
141|管理银行产品和服务。
142|
143|**关键服务域**:
144|- Savings Account
145|- Current Account
146|- Loan
147|- Credit Card
148|- Mortgage
149|- Investment Portfolio
150|
151|---
152|
153|### 8. Channels (渠道)
154|
155|管理客户交互渠道。
156|
157|**关键服务域**:
158|- Branch Operations
159|- ATM Operations
160|- E-Branch Operations
161|- Contact Center Operations
162|
163|---
164|
165|### 9. Business Development (业务发展)
166|
167|支持业务发展和创新。
168|
169|**关键服务域**:
170|- Product Design
171|- Campaign Management
172|- Market Analysis
173|- Competitive Analysis
174|
175|---
176|
177|### 10. Corporate Services (企业服务)
178|
179|管理企业级服务。
180|
181|**关键服务域**:
182|- Human Resource Management
183|- Facilities Management
184|- IT Operations
185|- Security Administration
186|
187|---
188|
189|### 11. Business Direction (业务方向)
190|
191|战略规划和业务管理。
192|
193|**关键服务域**:
194|- Business Architecture
195|- Strategic Planning
196|- Enterprise Governance
197|- Business Development Strategy
198|
199|---
200|
201|## 核心服务域详解
202|
203|### Customer Management (客户管理)
204|
205|```
206|┌─────────────────────────────────────────────────────────────────────────────┐
207|│                       Customer Management Domain                             │
208|├─────────────────────────────────────────────────────────────────────────────┤
209|│                                                                              │
210|│  ┌─────────────────────┐    ┌─────────────────────┐                        │
211|│  │ Customer Profile    │    │ Customer Relationship│                        │
212|│  │ Management          │    │ Management           │                        │
213|│  │                     │    │                      │                        │
214|│  │ • Profile Data      │    │ • Relationship Status│                        │
215|│  │ • Preferences       │    │ • Interaction History│                        │
216|│  │ • Demographics      │    │ • Satisfaction Score │                        │
217|│  └─────────────────────┘    └─────────────────────┘                        │
218|│                                                                              │
219|│  ┌─────────────────────┐    ┌─────────────────────┐                        │
220|│  │ Customer Offer      │    │ Customer Access      │                        │
221|│  │ Management          │    │ Entitlement          │                        │
222|│  │                     │    │                      │                        │
223|│  │ • Product Offers    │    │ • Authentication     │                        │
224|│  │ • Personalization   │    │ • Authorization      │                        │
225|│  │ • Campaign Targeting│    │ • Channel Access     │                        │
226|│  └─────────────────────┘    └─────────────────────┘                        │
227|│                                                                              │
228|│  ┌─────────────────────┐    ┌─────────────────────┐                        │
229|│  │ Customer Behavioral │    │ Customer Credit      │                        │
230|│  │ Insights            │    │ Rating               │                        │
231|│  │                     │    │                      │                        │
232|│  │ • Behavior Analysis │    │ • Credit Score       │                        │
233|│  │ • Predictive Models │    │ • Risk Assessment    │                        │
234|│  │ • Segmentation      │    │ • Credit Limit       │                        │
235|│  └─────────────────────┘    └─────────────────────┘                        │
236|│                                                                              │
237|└─────────────────────────────────────────────────────────────────────────────┘
238|```
239|
240|---
241|
242|### Party Data Management (当事方数据管理)
243|
244|```
245|┌─────────────────────────────────────────────────────────────────────────────┐
246|│                        Party Data Management Domain                          │
247|├─────────────────────────────────────────────────────────────────────────────┤
248|│                                                                              │
249|│  ┌─────────────────────┐    ┌─────────────────────┐                        │
250|│  │ Party Reference     │    │ Party Authentication │                        │
251|│  │ Data Directory      │    │                      │                        │
252|│  │                     │    │ • Identity Verify    │                        │
253|│  │ • Party Registry    │    │ • KYC/AML Check      │                        │
254|│  │ • Entity Resolution │    │ • Document Verify    │                        │
255|│  │ • Golden Record     │    │                      │                        │
256|│  └─────────────────────┘    └─────────────────────┘                        │
257|│                                                                              │
258|│  ┌─────────────────────┐    ┌─────────────────────┐                        │
259|│  │ Party Lifecycle     │    │ Party Data Quality   │                        │
260|│  │ Management          │    │ Management           │                        │
261|│  │                     │    │                      │                        │
262|│  │ • Onboarding        │    │ • Data Validation    │                        │
263|│  │ • Maintenance       │    │ • Deduplication      │                        │
264|│  │ • Offboarding       │    │ • Enrichment         │                        │
265|│  └─────────────────────┘    └─────────────────────┘                        │
266|│                                                                              │
267|└─────────────────────────────────────────────────────────────────────────────┘
268|```
269|
270|---
271|
272|### Payment Services (支付服务)
273|
274|```
275|┌─────────────────────────────────────────────────────────────────────────────┐
276|│                         Payment Services Domain                              │
277|├─────────────────────────────────────────────────────────────────────────────┤
278|│                                                                              │
279|│  ┌─────────────────────┐    ┌─────────────────────┐                        │
280|│  │ Payment Order       │    │ Payment Execution    │                        │
281|│  │                     │    │                      │                        │
282|│  │ • Order Initiation  │───►│ • Clearing           │                        │
283|│  │ • Validation        │    │ • Settlement         │                        │
284|│  │ • Authorization     │    │ • Reconciliation     │                        │
285|│  └─────────────────────┘    └─────────────────────┘                        │
286|│           │                          │                                       │
287|│           ▼                          ▼                                       │
288|│  ┌─────────────────────┐    ┌─────────────────────┐                        │
289|│  │ Payment Network     │    │ Correspondent       │                        │
290|│  │                     │    │ Bank Operations     │                        │
291|│  │ • SWIFT             │    │                      │                        │
292|│  │ • ACH               │    │ • Nostro/Vostro     │                        │
293|│  │ • SEPA              │    │ • FX Settlement      │                        │
294|│  └─────────────────────┘    └─────────────────────┘                        │
295|│                                                                              │
296|└─────────────────────────────────────────────────────────────────────────────┘
297|```
298|
299|---
300|
301|## BIAN 服务操作 (Service Operations)
302|
303|### 标准化操作类型
304|
305|| 操作 | 描述 | 示例 |
306||------|------|------|
307|| **Initiate** | 创建新实例 | 发起贷款申请 |
308|| **Create** | 创建数据记录 | 创建客户档案 |
309|| **Register** | 注册到系统 | 注册新产品 |
310|| **Evaluate** | 评估判断 | 评估信用风险 |
311|| **Provide** | 提供服务 | 提供账户信息 |
312|| **Update** | 更新数据 | 更新客户地址 |
313|| **Control** | 控制操作 | 控制交易限额 |
314|| **Execute** | 执行处理 | 执行支付 |
315|| **Request** | 发起请求 | 请求账户余额 |
316|| **Retrieve** | 查询数据 | 检索交易历史 |
317|| **Notify** | 发送通知 | 通知交易完成 |
318|| **Authorize** | 授权操作 | 授权大额转账 |
319|
320|### 服务操作模式
321|
322|```
323|┌─────────────────────────────────────────────────────────────────────────────┐
324|│                      Service Operation Pattern                               │
325|├─────────────────────────────────────────────────────────────────────────────┤
326|│                                                                              │
327|│  请求模式:                                                                   │
328|│  ┌─────────────┐    ┌─────────────┐    ┌─────────────┐                     │
329|│  │  Consumer   │───►│  Service    │───►│  Provider   │                     │
330|│  │             │◄───│  Domain     │◄───│             │                     │
331|│  └─────────────┘    └─────────────┘    └─────────────┘                     │
332|│                                                                              │
333|│  事件模式:                                                                   │
334|│  ┌─────────────┐    ┌─────────────┐    ┌─────────────┐                     │
335|│  │  Publisher  │───►│   Event     │───►│ Subscriber  │                     │
336|│  │             │    │   Bus       │    │             │                     │
337|│  └─────────────┘    └─────────────┘    └─────────────┘                     │
338|│                                                                              │
339|└─────────────────────────────────────────────────────────────────────────────┘
340|```
341|
342|---
343|
344|## BIAN API 标准
345|
346|### RESTful API 设计
347|
348|BIAN 定义了标准化的 API 端点结构：
349|
350|```
351|/{service-domain}/{sd-reference-id}/{behavior-qualifier}/{bq-reference-id}/{action}
352|
353|示例:
354|/customer-profile/CPR123/identity/ID456/retrieve
355|/payment-order/PO789/execute
356|/current-account/CA001/deposit/DEP002/update
357|```
358|
359|### API 组件
360|
361|| 组件 | 描述 | 示例 |
362||------|------|------|
363|| Service Domain | 服务域标识 | customer-profile |
364|| SD Reference ID | 服务域实例 ID | CPR123 |
365|| Behavior Qualifier | 行为限定符 | identity, balance |
366|| BQ Reference ID | 行为限定符实例 ID | ID456 |
367|| Action | 操作动作 | retrieve, update |
368|
369|### 标准请求/响应格式
370|
371|```json
372|// 请求示例: 检索客户档案
373|GET /customer-profile/CPR123/retrieve
374|
375|// 响应示例
376|{
377|  "customerProfileRecord": {
378|    "customerReference": "CPR123",
379|    "customerName": "张三",
380|    "customerType": "Individual",
381|    "customerProfile": {
382|      "demographics": {
383|        "dateOfBirth": "1985-06-15",
384|        "nationality": "CN"
385|      },
386|      "preferences": {
387|        "communicationChannel": "Email",
388|        "language": "zh-CN"
389|      }
390|    }
391|  }
392|}
393|```
394|
395|---
396|
397|## BIAN 与其他框架的关系
398|
399|### BIAN 与 TOGAF
400|
401|| 维度 | BIAN | TOGAF |
402||------|------|-------|
403|| **范围** | 银行业专属 | 通用企业架构 |
404|| **层次** | 业务能力和服务 | 全架构层次 |
405|| **标准化** | 预定义服务域 | 方法论框架 |
406|| **互补** | 提供银行业务内容 | 提供架构方法 |
407|
408|### BIAN 与 ArchiMate
409|
410|BIAN 服务域可以映射到 ArchiMate 元素：
411|
412|| BIAN 概念 | ArchiMate 元素 |
413||-----------|---------------|
414|| Business Area | Business Function (L1) |
415|| Business Domain | Business Function (L2) |
416|| Service Domain | Business Service |
417|| Service Operation | Business Process |
418|
419|### BIAN 与 IT4IT
420|
421|| 维度 | BIAN | IT4IT |
422||------|------|-------|
423|| **范围** | 银行业务能力 | IT 管理能力 |
424|| **互补** | 定义业务服务 | 管理 IT 服务 |
425|
426|---
427|
428|## 实施指南
429|
430|### 实施路径
431|
432|```
433|┌─────────────────────────────────────────────────────────────────────────────┐
434|│                      BIAN Implementation Roadmap                             │
435|├─────────────────────────────────────────────────────────────────────────────┤
436|│                                                                              │
437|│  Phase 1: 评估和规划                                                         │
438|│  ├── 当前架构评估                                                            │
439|│  ├── BIAN 服务域映射                                                         │
440|│  ├── 差距分析                                                                │
441|│  └── 实施路线图制定                                                          │
442|│                                                                              │
443|│  Phase 2: 核心能力建设                                                       │
444|│  ├── Party Data Management                                                  │
445|│  ├── Customer Management                                                    │
446|│  ├── Product Directory                                                      │
447|│  └── Account Management                                                     │
448|│                                                                              │
449|│  Phase 3: 交易能力建设                                                       │
450|│  ├── Payment Services                                                       │
451|│  ├── Card Services                                                          │
452|│  ├── Loan Services                                                          │
453|│  └── Investment Services                                                    │
454|│                                                                              │
455|│  Phase 4: 高级能力建设                                                       │
456|│  ├── Risk Management                                                        │
457|│  ├── Compliance                                                             │
458|│  ├── Analytics                                                              │
459|│  └── Open Banking APIs                                                      │
460|│                                                                              │
461|└─────────────────────────────────────────────────────────────────────────────┘
462|```
463|
464|### 服务域优先级矩阵
465|
466|| 优先级 | 服务域 | 原因 |
467||--------|--------|------|
468|| **P0** | Party Reference Data | 基础主数据 |
469|| **P0** | Customer Profile | 客户核心数据 |
470|| **P0** | Current Account | 核心产品 |
471|| **P1** | Payment Order | 核心交易 |
472|| **P1** | Product Directory | 产品管理 |
473|| **P1** | Customer Offer | 销售支持 |
474|| **P2** | Credit Risk | 风险管理 |
475|| **P2** | Regulatory Compliance | 合规要求 |
476|| **P3** | Customer Insights | 高级分析 |
477|
478|---
479|
480|## 最佳实践
481|
482|### 1. 渐进式采用
483|
484|```
485|建议:
486|- 从核心服务域开始
487|- 逐步扩展到完整景观
488|- 保持与现有系统的集成
489|- 避免大爆炸式改造
490|```
491|
492|### 2. API 优先设计
493|
494|```
495|建议:
496|- 采用 BIAN API 标准
497|- 设计可重用的 API
498|- 建立 API 治理
499|- 支持 Open Banking
500|```
501|