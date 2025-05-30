---
lab:
  title: 实验室 2：创建统一的客户配置文件
---

# 实验室 2：创建统一的客户配置文件
在本实验室中，你将学习如何：
- 将数据从原始数据源合并到客户配置文件中
- 选择主键 
- 创建匹配规则
- 定义搜索和筛选索引和活动

目标是找出 **Contoso Retail** 在各种数据源中拥有多少唯一客户配置文件。

## 练习 1：统一数据
### 任务 1：将联系人映射到常见数据类型
1. 登录到 **Customer Insights - Data**。

1. 在左侧导航菜单上，展开“**数据**”，然后选择“**统一**”。 选择“开始”。

1. 选择“**选择表和列**”。

1. 选择表示客户配置文件的表 – **联系人（电子商务）** 和**客户（会员）**。 选择“应用”。

1. 现在将显示根据标准模型类型对源表进行的映射。 您可以在表中查看类型。

1. 必须为已引入的每个实体选择 **“主键”**。 主键必须是唯一引用。 对于**电子商务联系人**，选择 **ContactId** 作为主键。

1. **电子商务联系人**数据包含一个名为“**电子邮件订阅者**”的列，由于名称的原因，该列将被映射到错误的类型，即 **Identity.Service.Email**。 打开此列的下拉列表，然后选择空选项（无/空）。 如果不执行此操作，那么默认系统行为是将此字段与我们不需要的**电子邮件**字段合并。

1. 选择“**表**”下的“**会员客户**”，然后将 **LoyaltyId** 设置为主键。

1. 选择左上角的“**保存源列**”。

1. 再次选择“**下一步**”和“**下一步**”，以跳过重复检查并进入“**匹配规则**”步骤。

### 任务 2：指定匹配顺序
下一阶段，我们必须选择合并配置文件的顺序。 你将能够合并属性，以确保统一配置文件的完整性以及用于这些属性的源的优先级。

1. 应选择最完整或最准确的配置文件源作为**主要（第一个）源**。 验证“**联系人: 电子商务**”是否为主要（第一个）源。

1. 验证“**客户: 会员**”是否为列表中的第二个源。 

1. 验证两个数据源是否都选中了“**包括所有记录**”。

### 任务 3：创建匹配规则
1. “**客户: 会员**”行上有一个警告指示器。 选择“+ 添加规则”。****

1. 使用 **FullName** 添加第一个条件：
    - 对于“**联系人: 电子商务**”表，选择 **FullName** 字段。
    - 对于“**客户: 会员**”表，选择 **FullName** 字段。
    - 将“**规范化**”下拉列表留空。
    - 将“**精度级别**”设置为“**基本**”。
    - 使用滑块将“**精度值**”设置为“**精确**”。
    - 为“**规则名称**”输入名称 **FullName, Email**。

1. 依次选择“**+ 添加**”和“**添加条件**”，为电子邮件地址添加第二个条件。
    - 对于“**联系人: 电子商务**”表，选择“**电子邮件**”字段。
    - 对于“**客户: 会员**”表，选择“**电子邮件**”字段。
    - 将“**规范化**”下拉列表留空。
    - 将“**精度级别**”设置为“**基本**”。
    - 将“**精度值**”设置为“**精确**”。

1. 选择“完成”。****

1. 选择**下一步**。

1. 在“**统一数据视图**”屏幕上，我们不会进行任何更改。 选择“**下一步**”，进入审阅屏幕。

1. 在“**审阅**”屏幕上，选择“**创建客户配置文件**”。 Customer Insights 现在正在匹配来自您的所有客户信息来源的客户数据，以根据您的规则确定您将拥有多少个唯一的客户配置文件。 创建配置文件可能需要一些时间。

祝贺你！ 你已成功统一 **Customer Insights** 中多个来源的数据，以创建可用于深入了解整个客户群的**统一客户配置文件**。

## 练习 2：配置搜索和筛选索引和活动
在本练习中，我们将设置**搜索和筛选**条件，使 Customer Insights 用户能够搜索统一的客户配置文件。 之后，我们将配置活动。

### 任务 1：配置搜索列和筛选索引 
1. 在 **Customer Insights** 中，从左侧导航菜单中选择“**客户**”。

1. 选择“**搜索和筛选器索引**”。 默认情况下，某些字段已添加。 从工具栏中选择“**+添加**”。

1. 选择 **CustomerId、FirstName、LastName、FullName、DateOfBirth、EMail、PostCode、ContactId (eCommerce_Contacts) 和 LoyaltyId**（如果尚未选中）。 取消选择任何其他已选中的字段。 选择“应用”。

1. 选择“保存”。

1. 选择“运行”。

1. 在 **Customer Insights** 中，从左侧导航菜单中选择“**客户**”。 应会显示一组客户卡片，表示**统一配置文件**。 可以展开卡片以查看有关客户的详细信息或按各种字段对卡片进行排序。 通过选择工具栏上的“**展开卡片**”和“**排序依据**”来尝试此操作。

1. 可以使用“**搜索客户**”来搜索与统一客户配置文件相关的文本属性。 （例如， 搜索“1”将搜索所有文本属性，并返回匹配项和部分匹配项。）

### 任务 2：创建活动
1. 在 **Customer Insights** 中，展开左侧导航菜单上的“**数据 > 活动**”，然后选择“**+ 配置活动**”。

1. 单击“**选择表**”。

1. 选择“**购买: 电子商务**”和“**购买: PoS**”表，然后选择“**添加**”。

1. 对于“**购买: 电子商务**”，配置如下：
    - 将“**活动类型**”设置为 **SalesOrder**。
    - 将“**主键**”设置为 **PurchaseId**。

1. 对于“**购买: PoS**”，配置如下：
    - 将“**活动类型**”设置为 **SalesOrder**。
    - 将“**主键**”设置为 **PurchaseId**。

1. 选择**下一步**。
   
1. 配置“**电子商务: 购买**”，如下所示：
    - 输入 **OnlinePurchase** 以获取**活动名称**。
    - 填写以下字段（对于未提及的任何字段，请留空）：
        - **时间戳**：PurchasedOn
        - **事件活动**：ActivityTypeDisplay
        - **其他详细信息**：主题
        - **是否在客户配置文件的时间线中显示此活动？** 是
        - **图标**：选择购物袋。
        - **是否为活动的属性设置映射字段类型？** 是，并按如下所示进行配置：
            - **销售订单 ID**：PurchaseID
            - **订单数据**：PurchasedOn
            - **销售额**：TotalPrice

1. 配置“**PoS: 购买**”，如下所示：
    - 输入 **PoSPurchase** 以获取 **活动名称**。
    - 填写以下字段（对于未提及的任何字段，请留空）：
        - **时间戳**：PurchasedOn
        - **事件活动**：ActivityTypeDisplay
        - **其他详细信息**：主题
        - **是否在客户配置文件的时间线中显示此活动？** 是
        - **图标**：选择购物袋。
        - **是否为活动的属性设置映射字段类型？** 是，并按如下所示进行配置：
            - **销售订单 ID**：PurchaseID
            - **订单数据**：PurchasedOn
            - **销售额**：TotalPrice

1. 选择**下一步**。

1. 在“**配置活动关系**”屏幕上，选中“**电子商务: 购买**”，然后选择“**+ 添加关系**”。

1. 在“**添加关系路径**”窗格中，设置以下值：
    - **外键**：ContactId
    - **表单名称**：联系人：电子商务
    - **关系名称**：eCommPurchasesToContacts
    - 选择“应用”。

1. 选择“**PoS: 购买**”。 选择“+ 添加关系”。

1. 在“**添加关系路径**”窗格中，设置以下值：
    - **外键**：LoyaltyId
    - **表单名称**：客户：会员
    - **关系名称**：PoSPurchasesToLoyalty
    - 选择“应用”。

1. 选择**下一步**。

1. 选择“**创建活动**”。

1. 等待**活动**刷新并统一。



