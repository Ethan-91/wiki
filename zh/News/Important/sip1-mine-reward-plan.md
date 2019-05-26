# SIP1: 奖励改进计划 (BETANET-R5 版本内容)



## 上线时间

* **2019年1月25日 北京时间24时之前**



## 概要

* 保持10亿代币总量不变。
* 将矿工份额从25%提升到 (75+5)%。
* 基于通缩模型，4年减半，开采时间为101.5年。
* 缩减团队份额到10%，并与矿工同比释放。
* 缩减可融资份额到10%。
* 软分叉BetaNet网络。
* 销毁ERC20中的90%代币。



## 分叉时间

* 从75000块开始，第8天(1月27日)24时之前。

  块号：$ 130000 $

* 本次分叉为软分叉，有利于矿工。



## SERO Protocol 代币分配原则

* 总共发行10亿SERO代币
  * BetaNet网络调整为总量9亿代币，其中包括：
    * 标准矿工奖励由 7.5亿 SERO 分101.5年挖出。
    * 矿工社区奖励  0.5亿 SERO 与标准矿工奖励同比释放。
    * 团队份额 1亿  SERO 与标准矿工奖励同比释放。
  * 用于早期融资的SERO ERC20智能合约中，销毁90%的Token。
  * MainNet上线后，ERC20和BetaNet中都1:1映射到MainNet。



## 标准矿工奖励

* $[130000, 3057600)$ 相差2937600块（大约17个月）
  * 每块奖励为 66.77350574 SERO。
* $[3057600,\infty)$
  * 初始每块奖励为 33.38675287 SERO。
  * 每隔8294400个块奖励减半。
  * 直到9亿的代币完全挖掘出来。



## 难度与奖励关系

* 分为五级目标难度
  * $[0, 3.4亿)$
    * 块奖励为 1 SERO

  * $[3.4亿, 17亿)$
    * 块奖励为 `5.6+((难度-3.4) * 1.647)`

  * $[17亿, 40亿)$
    * 块奖励为 `28+((难度-17) * 0.217)`

  * $[40亿, 170亿)$
    * 块奖励为 `33+((难度-40) * 0.259)`

  * $[170亿,\infty )$
    * 块奖励为 `66.77350574`



## 奖励计算方法

* $Rreward_{ori}=66.773505743000000000$



* $Current \ni  [130000, 3057600) $
  * $Reward_{std}=Reward_{ori}$
* $ Current \ni [3057600, \infty) $
  * $rate_{reward}=1+[ (Current-3057600)/8294400 ]$
  * $Reward_{std}=Reward _{ori} >> rate_{reward}$



* $Diff \ni [170,\infty )$
  * $ Reward_{mine} = Reward_{std} $

* $Diff \ni  [1,3.4)$
  * $ Reward_{mine} = 1 $

* $Diff \ni  [3.4,17) $
  * $ Reward_{mine} = \frac{5.6+[1.647 \cdot (Diff-3.4)]}{Reward_{ori}} \cdot Reward_{std} $

* $Diff \ni  [17,40) $
  *  $ Reward_{mine} = \frac{28+[0.217 \cdot (Diff-17)]}{Reward_{ori}} \cdot Reward_{std} $

* $Diff \ni  [40,170) $
  * $ Reward_{mine} = \frac{33+[0.259 \cdot (Diff-40)]}{Reward_{ori}} \cdot Reward_{std} $



* $Reward_{community}=\frac{Reward_{std}}{15}$ （每5760块结算一次）

* $Reward_{team}=\frac{Reward_{mine} \cdot 2}{15}$ （每5760块结算一次）



