# OSSEM

[![Open Source Love](https://badges.frapsoft.com/os/v3/open-source.svg?v=103)](https://github.com/ellerbrock/open-source-badges/)
![Open_Threat_Research Community](https://img.shields.io/badge/Open_Threat_Research-Community-brightgreen.svg)
[![Twitter](https://img.shields.io/twitter/follow/OSSEM_Project.svg?style=social&label=Follow)](https://twitter.com/OSSEM_Project)

开源安全事件元数据(OSSEM)是一个由社区主导的项目，主要关注于来自不同数据源和操作系统的安全事件日志的文档化和标准化。这些安全事件以字典的形式记录，在验证威胁检测模型时，可以参考其做数据源映射与分析。此外，该项目还提供了一个通用数据模型(CDM)，数据工程师可以在数据规范化过程中使用该模型，以允许安全分析师跨不同数据源查询和分析数据。最后，该项目还提供了关于特定数据源中确定性的结构和关系的文档，以促进数据分析的发展。

<img src="resources/images/OSSEM_logo.png" width=300>

## 官方网站: https://ossemproject.com/intro.html

# 目标

* 定义并分享通用数据模型，以提高对安全事件日志进行数据标准化和转换的效率
* 定义并分享安全事件日志的数据结构和关系
* 以字典的形式向社区提供多种安全事件日志的详细信息
* 帮助人们了解更多类型的安全事件日志(Windows，Linux，MacOS，Azure，AWS等等)
* 玩得开心点，在检测时多想想你的SIEM中的数据结构！!

# 项目结构

主要有三个文件夹:

* **通用数据模型 (CDM)**:
  * 通过提供解析安全事件日志的标准方法来促进数据集的规范化
  * 它由多种数据源中特定的[实体](https://github.com/OTRF/OSSEM-CDM/tree/master/schemas/entities)构成
  * 每个实体的定义及其各自的属性(字段名称)大多是通用性描述，可以帮助加快事件日志的解析过程.
  * 除了数据[实体](https://github.com/OTRF/OSSEM-CDM/tree/master/schemas/entities)之外, 它还提供了[实体表](https://github.com/OTRF/OSSEM-CDM/tree/master/schemas/tables)的概念来聚合公共实体，这些实体可用于解析具有相似上下文的多个数据源。例如，HTTP、Port 和 UserAgent 实体可用于标准化数据，提供在网络环境中捕获的网络流量元数据的相关上下文
* **数据字典 (DD)**:
  * 包含按操作系统和各个数据源分类的多种安全事件日志的具体信息
  * 每个[字典](https://github.com/OTRF/OSSEM-DD)描述单个事件日志及其对应的事件字段名称
  * 它提供了便于在团队中创建数据WIKI的基础概念
* **检测模型 (DM)**:
  * 专注于以数据对象的形式定义所需的数据以及相互之间的[关系](https://github.com/OTRF/OSSEM-DM/tree/main/relationships)，以促进数据分析的创建并验证对攻击技术的检测
  * 最初是为了扩展ATT&CK数据源的定义而开发的
    * [MITRE ATT&CKcon 2018: Hunters ATT&CKing with the Data](https://youtu.be/QCDBjFJ_C3g)
    * [MITRE ATT&CKcon 2.0: Ready to ATT&CK? Bring Your Own Data (BYOD) and Validate Your Data Analytics!](https://youtu.be/eM0c_Gil-38)
  * 该项目的初期工作已迁移到ATT&CK，并由 [@Cyb3rPandah](https://twitter.com/Cyb3rPandaH) 改进
    * [ATT&CK数据源定义, 第一部分: 增强现状](https://medium.com/mitre-attack/defining-attack-data-sources-part-i-4c39e581454f)
    * [ATT&CK数据源定义, 第二部分: 操作方法论](https://medium.com/mitre-attack/defining-attack-data-sources-part-ii-1fc98738ba5b)
    * 项目的[这部分](https://github.com/OTRF/OSSEM-DM/tree/main/use-cases/mitre_attack)考虑了一个用于扩展[ATT&CK数据源对象](https://github.com/mitre-attack/attack-datasources)的用例

# 作者

* Roberto Rodriguez [@Cyb3rWard0g](https://twitter.com/Cyb3rWard0g)

# 译者
* 慕长风 [@Moofeng](https://twitter.com/M0ofeng)

# 当前提交者

* Jose Luis Rodriguez [@Cyb3rPandaH](https://twitter.com/Cyb3rPandaH)
* Nate Guagenti [@neu5ron](https://twitter.com/neu5ron)
* Ricardo Dias [@hxnoyd](https://twitter.com/hxnoyd)

# 应用的项目

* [HELK](https://github.com/Cyb3rWard0g/HELK)
* [Azure Sentinel Normalization](https://docs.microsoft.com/en-us/azure/sentinel/normalization-schema)

# 其它资料

* [准备好狩猎了吗? 首先, 让我看看你的数据！](https://cyberwardog.blogspot.com/2017/12/ready-to-hunt-first-show-me-your-data.html)
* [Windows 10 中的新内容，1507和1511版本](https://docs.microsoft.com/en-us/windows/whats-new/whats-new-windows-10-version-1507-and-1511#bkmk-lsass)
* [下载 Windows 的安全审计事件(电子表格)](https://www.microsoft.com/en-us/download/details.aspx?id=50034)
* [高级安全审计策略设置](https://docs.microsoft.com/en-us/windows/security/threat-protection/auditing/advanced-security-audit-policy-settings)
* [监测 Active Directory 的入侵痕迹](https://docs.microsoft.com/en-us/windows-server/identity/ad-ds/plan/security-best-practices/monitoring-active-directory-for-signs-of-compromise#audit-account-management)
* [审计策略建议](https://docs.microsoft.com/en-us/windows-server/identity/ad-ds/plan/security-best-practices/audit-policy-recommendations)
* [使用 Windows Event Forwarding 来帮助进行入侵检测](https://docs.microsoft.com/en-us/windows/security/threat-protection/use-windows-event-forwarding-to-assist-in-intrusion-detection)
* [最低限度的审计策略建议](https://docs.microsoft.com/en-us/windows/security/threat-protection/use-windows-event-forwarding-to-assist-in-intrusion-detection#a-href-idbkmk-appendixaaappendix-a---minimum-recommended-minimum-audit-policy)
* [Windows ITPro 文档 - 威胁保护](https://github.com/MicrosoftDocs/windows-itpro-docs/tree/master/windows/security/threat-protection)
