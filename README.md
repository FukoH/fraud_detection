

## 目标

电商网站经常交易巨额资金。每当大量资金被转移，就有欺诈活动的风险，例如用户被盗刷信用卡，诈骗，洗钱等等。
机器学习善于解决识别欺诈的问题，可以构建机器学习模型来识别欺诈活动。
本文目标是构建一个机器学习模型，该模型可以预测新用户的第一笔交易是否具有欺诈性。

### 任务列表

一些思路：
- 对于每个用户，根据数字 IP 地址确定他的国家/地区。
- 建立一个模型来预测一项活动是否具有欺诈性。false postive和false negative会如何影响模型选择？
- 需要解释模型。不是从数学的角度来看（老板并不关心），而是从用户的角度。哪些类型的用户更有可能被归类为有风险？他们的特点是什么？
- 假设模型已经训练好了，可以使用它来实时预测活动是否具有欺诈性。从产品的角度来看，如何根据模型输出，构建出怎样的不同的用户体验？

## 数据

有两张表

- 交易信息表，记录了每个用户的第一笔交易信息
    - user_id ：用户的 ID。用户唯一
    - signup_time ：用户创建帐户的时间（格林威治标准时间）
    - purchase_time ：用户购买商品的时间（GMT时间）
    - purchase_value ：所购商品的成本（美元）
    - device_id ：设备ID。您可以假设它在设备上是唯一的。即交易具有相同的设备 ID 表示使用相同的物理设备
    - source：用户营销渠道：广告、搜索引擎优化、直接（即直接输入到网站浏览器上的网站地址）。
    - browser ：用户使用的浏览器。
    - sex：用户性别：男/女
    - age：用户年龄
    - ip_address : 用户数字ip地址
    - class: 我们预测的目标，1表示具有欺诈性，0表示没有


- IP地址映射表，根据IP地址的上下界来确定所属的国家
    - lower_bound_ip_address ：该国家/地区的数字 IP 地址的下限
    - upper_bound_ip_address ：该国家/地区的数字 IP 地址的上限
    - country : 对应的国家。如果用户的 ip 地址的值在上限和下限之间，那么他就位于这个国家。
