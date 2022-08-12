{
 "cells": [
  {
   "cell_type": "markdown",
   "metadata": {
    "toc": true
   },
   "source": [
    "<h1>Table of Contents<span class=\"tocSkip\"></span></h1>\n",
    "<div class=\"toc\"><ul class=\"toc-item\"><li><span><a href=\"#目标\" data-toc-modified-id=\"目标-1\"><span class=\"toc-item-num\">1&nbsp;&nbsp;</span>目标</a></span></li><li><span><a href=\"#背景描述\" data-toc-modified-id=\"背景描述-2\"><span class=\"toc-item-num\">2&nbsp;&nbsp;</span>背景描述</a></span><ul class=\"toc-item\"><li><span><a href=\"#任务列表\" data-toc-modified-id=\"任务列表-2.1\"><span class=\"toc-item-num\">2.1&nbsp;&nbsp;</span>任务列表</a></span></li></ul></li><li><span><a href=\"#数据\" data-toc-modified-id=\"数据-3\"><span class=\"toc-item-num\">3&nbsp;&nbsp;</span>数据</a></span></li></ul></div>"
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "## 目标\n",
    "\n",
    "电商网站经常交易巨额资金。每当大量资金被转移，就有欺诈活动的风险，例如用户被盗刷信用卡，诈骗，洗钱等等。\n",
    "机器学习善于解决识别欺诈的问题，可以构建机器学习模型来识别欺诈活动。\n",
    "本文目标是构建一个机器学习模型，该模型可以预测新用户的第一笔交易是否具有欺诈性。"
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "## 背景描述\n",
    "\n",
    "A 公司是一个卖手工服装的电商。\n",
    "我们需要构建一个模型来预测用户是否在进行一些非法活动。对于数据科学家来说，这是一项非常常见的任务。\n",
    "基于用户在网站上的第一笔交易的信息，判断交易是**“欺诈”**还是**“非欺诈”**。"
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "### 任务列表\n",
    "\n",
    "一些思路：\n",
    "- 对于每个用户，根据数字 IP 地址确定他的国家/地区。\n",
    "- 建立一个模型来预测一项活动是否具有欺诈性。false postive和false negative会如何影响模型选择？\n",
    "- 需要解释模型。不是从数学的角度来看（老板并不关心），而是从用户的角度。哪些类型的用户更有可能被归类为有风险？他们的特点是什么？\n",
    "- 假设模型已经训练好了，可以使用它来实时预测活动是否具有欺诈性。从产品的角度来看，如何根据模型输出，构建出怎样的不同的用户体验？"
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "## 数据\n",
    "\n",
    "有两张表\n",
    "\n",
    "- 交易信息表，记录了每个用户的第一笔交易信息\n",
    "    - user_id ：用户的 ID。用户唯一\n",
    "    - signup_time ：用户创建帐户的时间（格林威治标准时间）\n",
    "    - purchase_time ：用户购买商品的时间（GMT时间）\n",
    "    - purchase_value ：所购商品的成本（美元）\n",
    "    - device_id ：设备ID。您可以假设它在设备上是唯一的。即交易具有相同的设备 ID 表示使用相同的物理设备\n",
    "    - source：用户营销渠道：广告、搜索引擎优化、直接（即直接输入到网站浏览器上的网站地址）。\n",
    "    - browser ：用户使用的浏览器。\n",
    "    - sex：用户性别：男/女\n",
    "    - age：用户年龄\n",
    "    - ip_address : 用户数字ip地址\n",
    "    - class: 我们预测的目标，1表示具有欺诈性，0表示没有\n",
    "\n"
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "- IP地址映射表，根据IP地址的上下界来确定所属的国家\n",
    "    - lower_bound_ip_address ：该国家/地区的数字 IP 地址的下限\n",
    "    - upper_bound_ip_address ：该国家/地区的数字 IP 地址的上限\n",
    "    - country : 对应的国家。如果用户的 ip 地址的值在上限和下限之间，那么他就位于这个国家。"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "metadata": {},
   "outputs": [],
   "source": []
  }
 ],
 "metadata": {
  "kernelspec": {
   "display_name": "Python 3",
   "language": "python",
   "name": "python3"
  },
  "language_info": {
   "codemirror_mode": {
    "name": "ipython",
    "version": 3
   },
   "file_extension": ".py",
   "mimetype": "text/x-python",
   "name": "python",
   "nbconvert_exporter": "python",
   "pygments_lexer": "ipython3",
   "version": "3.7.0"
  },
  "toc": {
   "base_numbering": 1,
   "nav_menu": {},
   "number_sections": true,
   "sideBar": true,
   "skip_h1_title": true,
   "title_cell": "Table of Contents",
   "title_sidebar": "Contents",
   "toc_cell": true,
   "toc_position": {
    "height": "calc(100% - 180px)",
    "left": "10px",
    "top": "150px",
    "width": "273.188px"
   },
   "toc_section_display": true,
   "toc_window_display": true
  }
 },
 "nbformat": 4,
 "nbformat_minor": 2
}
