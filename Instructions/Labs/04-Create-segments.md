---
lab:
  title: 实验室 4：创建客户细分
---

# 实验室 4：创建客户细分

在本实验室中，你将学习如何：
- 根据客户资料创建客户细分
- 使用度量值创建客户细分
- 从头开始创建客户细分

## 练习 1：从多个源创建客户细分 
### 任务 1：根据客户资料创建客户细分
在此第一个任务中，我们将基于客户资料创建客户细分。 我们将确定居住在得克萨斯州的任何客户。 

1. 展开“**见解**”，然后从左侧导航菜单中选择“**客户细分**”。

1. 选择“**+ 新建 > 从客户资料创建**”。

1. 对于“**字段**”，请选择“**州**”和“**值**”，选择“**得克萨斯州**”。

1. 选择“查看”****。

1. 将客户细分命名为“**德克萨斯州客户**”，并验证“**输出表单名称**”是否已自动填充为 **CustomersFromTexas**。

1. 选择“保存”。

### 任务 2：使用度量值创建客户细分 
Contoso Coffee Marketing 希望推出新的促销活动。 根据历史数据，营销部门已确定，他们希望针对在线购买价值高于平均水平的“在家自制”客户开展营销活动。 这次我们将使用“**从度量值创建**”选项创建客户细分。 

1. 从左侧导航菜单中选择“**见解 > 客户细分**”。

1. 选择“**+ 新建 > 从度量值创建**”。

1. 选择“**平均商店购买 ($) **”特性。

1. 将“**运算符**”设置为“**大于**”。

1. 将“**值**”设置为 **100**。 该图应按百分位数填充“**平均 Web 购买 ($)**”。

1. 选择“查看”****。

1. 将客户细分命名为“**卓越客户**”，并验证“**输出表单名称**”是否已自动填充为“**卓越客户**”。

1. 选择“保存”。

### 任务 3：从头开始创建客户细分
每个季节，Contoso Coffee 都会推出不同的促销活动。 今年，他们希望推出“秋季降价促销”，旨在销售年底剩余的机型。 他们新推出了冷萃咖啡，希望以高于平均店内购买的 X 一代为目标。 由于此客户细分需要多个条件，我们将从头开始创建。

1. 从左侧导航菜单中选择“**见解 > 客户细分**”。 选择“**+ 新建 > 生成自己的**”。

1. 在“**无标题客户细分**”标题文本旁边，选择“**编辑详细信息**”，并将“**名称**”更改为“**秋季清仓促销**”。

1. 验证“**输出实体名称**”是否已自动填充为 **FallCloseoutPromotion**，然后选择“**完成**”。

1. 使用屏幕右侧的“**添加到规则 1**”窗格，展开“**客户：CustomerInsights**”并选择“**DateofBitrh**”。 

1. 选择“**is**”和“**on or after**”，然后输入日期为 **1/1/1965**。

1. 使用“**and**”限定符添加另一个条件。

1. 将此条件设置为：**DateOfBirth** is **on or before 12/31/1979**。

1. 使用“**and**”限定符添加另一个条件。 

1. 展开 **Customer_Measure: CustomerInsights**。

1. 选择“**平均 Web 购买 ($)**”度量值并将其添加到“**规则 1**”。 

1. Select“**is**”和“**greater than or equal to 125**”。

1. 使用“**and**”限定符添加另一个条件。 

1. 在“**输入特性名称或从面板中添加**”字段中，输入“**性别**”，然后从显示的列表中选择它。 

1. 选择“**is**”和“**equal to male**”。

1. 选中“**忽略大小写**”复选框。

1. 在“**规则 1**”下，选择“**+ 添加规则**”。 

1. 选择“**联合**”框并将其更改为“**例外**”。

1. 在“**添加到规则 2**”窗格中，展开“**客户：CustomerInsights**”，然后选择“**州**”。 

1. 选择 **is** 和 **equal to Florida**。

1. 选择“保存”。

1. 选择“运行”。
