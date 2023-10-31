---
title: "Disagreement in the Equity Options Market and Stock Returns"
author: 
  - "Benjamin Golez and Garrick Aden-Buie"
  - "汇报人：陈伟涛"
date: '2023-10-31'
output:
  xaringan::moon_reader:
    css: xaringan-themer.css
    lib_dir: libs
    nature:
      highlightStyle: github
      highlightLines: true
      countIncrementalSlides: false
      
      
---
<script src="/rmarkdown-libs/fabric/fabric.min.js"></script>
<link href="/rmarkdown-libs/xaringanExtra-scribble/scribble.css" rel="stylesheet" />
<script src="/rmarkdown-libs/xaringanExtra-scribble/scribble.js"></script>
<script>document.addEventListener('DOMContentLoaded', function() { window.xeScribble = new Scribble({"pen_color":["#FF0000"],"pen_size":3,"eraser_size":30,"palette":[]}) })</script>
<script src="/rmarkdown-libs/kePrint/kePrint.js"></script>
<link href="/rmarkdown-libs/lightable/lightable.css" rel="stylesheet" />
<script src="/rmarkdown-libs/kePrint/kePrint.js"></script>
<link href="/rmarkdown-libs/lightable/lightable.css" rel="stylesheet" />







background-image: url(https://github.com/chen-weitao/logo/blob/main/xiaohui.jpg?raw=true)
background-size: 100px
background-position: 90% 8%

## 结论

- [slide link](/Disagreement.html)投资者分歧降低股票未来收益率

- 盈利与预期偏差，投资者分歧和未来预期收益率的相关性

- 在高贝塔、难以卖空的股票中更明显，二者相关性

---

background-image: url(https://github.com/chen-weitao/logo/blob/main/xiaohui.jpg?raw=true)
background-size: 100px
background-position: 90% 8%

## 数据来源
- Chicago Board of Options Exchange (CBOE)

  International Securities Exchange (ISE)

- 交易者

1. Customers：散户和机构投资者（对冲基金）

2. Firms：Proprietary Trading Desks(和做市商的相关性0.44)

---

background-image: url(https://github.com/chen-weitao/logo/blob/main/xiaohui.jpg?raw=true)
background-size: 100px
background-position: 90% 8%

## 核心变量

- 将投资者分歧定义为合成股票多头敞口和空头敞口的抵消程度
`$$\small\\Disagreement=Min(POS,NEG)$$`



`$$POS=\small\sum{\left| {{\Delta }^{Call}} \right|\left( O{{B}^{Call}}+C{{B}^{Call}} \right)+\left| {{\Delta }^{Put}} \right|\left( O{{S}^{Put}}+C{{S}^{Put}} \right)}$$`

`$$NEG=\small\sum{\left| {{\Delta }^{Put}} \right|\left( O{{B}^{Put}}+C{{B}^{Put}} \right)+\left| {{\Delta }^{Call}} \right|\left( O{{S}^{Call}}+C{{S}^{Call}} \right)}$$`
- 标准化
`$$Disagreement=\small\frac{Min(POS,NEG)}{Max(POS,NEG)}$$`
- 去除开盘卖出看涨期权的成交量
`$$DisagreementSC=\small\frac{Min(POS,NE{{G}^{SC}})}{Max(POS,NE{{G}^{SC}})}$$`

`$$NE{{G}^{SC}}=\small\sum{\left| {{\Delta }^{Put}} \right|\left( O{{B}^{Put}}+C{{B}^{Put}} \right)+\left| {{\Delta }^{Call}} \right|\left( C{{S}^{Call}} \right)}$$`
---

background-image: url(https://github.com/chen-weitao/logo/blob/main/xiaohui.jpg?raw=true)
background-size: 100px
background-position: 90% 8%

## 控制变量

- 经标准化后的投资者方向性指标

`$$Directional=\small\left\{ \begin{array}{*{35}{l}}
   [Max(POS,NEG)-Min(POS,NEG)] & \text{ }if\text{ }POS\ge NEG  \\
   [Max(POS,NEG)-Min(POS,NEG)]\times -(1) & \text{ }if\text{ }POS<NEG  \\
\end{array} \right.$$`

`$$Directional=\small\frac{Directional}{Max(POS,NEG)}$$`

- 其余投资者分歧指标：分析师预测离散度、换手率和共同基金持股分散度

- 和股票特征相关的指标：市值、账面市值比、异质性波动率、动量和机构持有量等

- 和期权特征相关的指标：期权未平仓量、期权交易量、Put-call交易量比值、隐含波动率、隐含偏度和Call-put波动率价差等

---

background-image: url(https://github.com/chen-weitao/logo/blob/main/xiaohui.jpg?raw=true)
background-size: 100px
background-position: 90% 8%

## 描述性统计


<table class="table table-striped table-hover table-condensed" style="font-size: 18px; margin-left: auto; margin-right: auto;">
<caption style="font-size: initial !important;">(\#tab:unnamed-chunk-1)表1 描述性统计</caption>
 <thead>
  <tr>
   <th style="text-align:left;">  </th>
   <th style="text-align:right;"> Mean </th>
   <th style="text-align:right;"> Median </th>
   <th style="text-align:right;"> Min </th>
   <th style="text-align:right;"> Max </th>
   <th style="text-align:right;"> SD </th>
   <th style="text-align:right;"> N </th>
  </tr>
 </thead>
<tbody>
  <tr grouplength="5"><td colspan="7" style="border-bottom: 1px solid;"><strong>A. All stocks</strong></td></tr>
<tr>
   <td style="text-align:left;padding-left: 2em;" indentlevel="1"> Disagreement </td>
   <td style="text-align:right;"> 0.33 </td>
   <td style="text-align:right;"> 0.32 </td>
   <td style="text-align:right;"> 0.00 </td>
   <td style="text-align:right;"> 1.00 </td>
   <td style="text-align:right;"> 0.24 </td>
   <td style="text-align:right;"> 326099 </td>
  </tr>
  <tr>
   <td style="text-align:left;padding-left: 2em;" indentlevel="1"> Directional </td>
   <td style="text-align:right;"> -0.03 </td>
   <td style="text-align:right;"> -0.03 </td>
   <td style="text-align:right;"> -1.00 </td>
   <td style="text-align:right;"> 1.00 </td>
   <td style="text-align:right;"> 0.49 </td>
   <td style="text-align:right;"> 326099 </td>
  </tr>
  <tr>
   <td style="text-align:left;padding-left: 2em;" indentlevel="1"> AnalystDis </td>
   <td style="text-align:right;"> 0.02 </td>
   <td style="text-align:right;"> 0.00 </td>
   <td style="text-align:right;"> 0.00 </td>
   <td style="text-align:right;"> 37.82 </td>
   <td style="text-align:right;"> 0.25 </td>
   <td style="text-align:right;"> 283460 </td>
  </tr>
  <tr>
   <td style="text-align:left;padding-left: 2em;" indentlevel="1"> StockTurn </td>
   <td style="text-align:right;"> 0.26 </td>
   <td style="text-align:right;"> 0.19 </td>
   <td style="text-align:right;"> 0.00 </td>
   <td style="text-align:right;"> 230.75 </td>
   <td style="text-align:right;"> 0.50 </td>
   <td style="text-align:right;"> 326097 </td>
  </tr>
  <tr>
   <td style="text-align:left;padding-left: 2em;" indentlevel="1"> MFDis </td>
   <td style="text-align:right;"> 0.01 </td>
   <td style="text-align:right;"> 0.01 </td>
   <td style="text-align:right;"> 0.00 </td>
   <td style="text-align:right;"> 0.13 </td>
   <td style="text-align:right;"> 0.00 </td>
   <td style="text-align:right;"> 314767 </td>
  </tr>
  <tr grouplength="5"><td colspan="7" style="border-bottom: 1px solid;"><strong>B. 500 largest stocks</strong></td></tr>
<tr>
   <td style="text-align:left;padding-left: 2em;" indentlevel="1"> Disagreement </td>
   <td style="text-align:right;"> 0.48 </td>
   <td style="text-align:right;"> 0.50 </td>
   <td style="text-align:right;"> 0.00 </td>
   <td style="text-align:right;"> 1.00 </td>
   <td style="text-align:right;"> 0.21 </td>
   <td style="text-align:right;"> 79174 </td>
  </tr>
  <tr>
   <td style="text-align:left;padding-left: 2em;" indentlevel="1"> Directional </td>
   <td style="text-align:right;"> -0.07 </td>
   <td style="text-align:right;"> -0.07 </td>
   <td style="text-align:right;"> -1.00 </td>
   <td style="text-align:right;"> 1.00 </td>
   <td style="text-align:right;"> 0.34 </td>
   <td style="text-align:right;"> 79174 </td>
  </tr>
  <tr>
   <td style="text-align:left;padding-left: 2em;" indentlevel="1"> AnalystDis </td>
   <td style="text-align:right;"> 0.00 </td>
   <td style="text-align:right;"> 0.00 </td>
   <td style="text-align:right;"> 0.00 </td>
   <td style="text-align:right;"> 0.60 </td>
   <td style="text-align:right;"> 0.01 </td>
   <td style="text-align:right;"> 77346 </td>
  </tr>
  <tr>
   <td style="text-align:left;padding-left: 2em;" indentlevel="1"> StockTurn </td>
   <td style="text-align:right;"> 0.22 </td>
   <td style="text-align:right;"> 0.17 </td>
   <td style="text-align:right;"> 0.01 </td>
   <td style="text-align:right;"> 8.76 </td>
   <td style="text-align:right;"> 0.19 </td>
   <td style="text-align:right;"> 79174 </td>
  </tr>
  <tr>
   <td style="text-align:left;padding-left: 2em;" indentlevel="1"> MFDis </td>
   <td style="text-align:right;"> 0.01 </td>
   <td style="text-align:right;"> 0.01 </td>
   <td style="text-align:right;"> 0.00 </td>
   <td style="text-align:right;"> 0.07 </td>
   <td style="text-align:right;"> 0.00 </td>
   <td style="text-align:right;"> 78135 </td>
  </tr>
</tbody>
</table>

---

background-image: url(https://github.com/chen-weitao/logo/blob/main/xiaohui.jpg?raw=true)
background-size: 100px
background-position: 90% 8%

## 相关系数

<table class="table table-striped table-hover table-condensed" style="font-size: 15.5px; margin-left: auto; margin-right: auto;">
<caption style="font-size: initial !important;">(\#tab:unnamed-chunk-2)表2 相关系数表</caption>
 <thead>
  <tr>
   <th style="text-align:left;">  </th>
   <th style="text-align:right;"> Disagreement </th>
   <th style="text-align:right;"> Directional </th>
   <th style="text-align:right;"> AnalystDis </th>
   <th style="text-align:right;"> StockTurn </th>
   <th style="text-align:right;"> MFDis </th>
  </tr>
 </thead>
<tbody>
  <tr grouplength="6"><td colspan="6" style="border-bottom: 1px solid;"><strong>A. All stocks</strong></td></tr>
<tr>
   <td style="text-align:left;padding-left: 2em;" indentlevel="1"> Disagreement </td>
   <td style="text-align:right;"> 1.00 </td>
   <td style="text-align:right;"> 0.01 </td>
   <td style="text-align:right;"> -0.01 </td>
   <td style="text-align:right;"> 0.14 </td>
   <td style="text-align:right;"> 0.17 </td>
  </tr>
  <tr>
   <td style="text-align:left;padding-left: 2em;" indentlevel="1"> Directional </td>
   <td style="text-align:right;"> 0.01 </td>
   <td style="text-align:right;"> 1.00 </td>
   <td style="text-align:right;"> 0.02 </td>
   <td style="text-align:right;"> 0.01 </td>
   <td style="text-align:right;"> -0.05 </td>
  </tr>
  <tr>
   <td style="text-align:left;padding-left: 2em;" indentlevel="1"> AnalystDis </td>
   <td style="text-align:right;"> -0.01 </td>
   <td style="text-align:right;"> 0.02 </td>
   <td style="text-align:right;"> 1.00 </td>
   <td style="text-align:right;"> 0.02 </td>
   <td style="text-align:right;"> -0.04 </td>
  </tr>
  <tr>
   <td style="text-align:left;padding-left: 2em;" indentlevel="1"> StockTurn </td>
   <td style="text-align:right;"> 0.14 </td>
   <td style="text-align:right;"> 0.01 </td>
   <td style="text-align:right;"> 0.02 </td>
   <td style="text-align:right;"> 1.00 </td>
   <td style="text-align:right;"> -0.05 </td>
  </tr>
  <tr>
   <td style="text-align:left;padding-left: 2em;" indentlevel="1"> MFDis </td>
   <td style="text-align:right;"> 0.17 </td>
   <td style="text-align:right;"> -0.05 </td>
   <td style="text-align:right;"> -0.04 </td>
   <td style="text-align:right;"> -0.05 </td>
   <td style="text-align:right;"> 0.49 </td>
  </tr>
  <tr>
   <td style="text-align:left;padding-left: 2em;" indentlevel="1"> log(Size) </td>
   <td style="text-align:right;"> 0.37 </td>
   <td style="text-align:right;"> -0.10 </td>
   <td style="text-align:right;"> -0.09 </td>
   <td style="text-align:right;"> -0.05 </td>
   <td style="text-align:right;"> 0.49 </td>
  </tr>
  <tr grouplength="6"><td colspan="6" style="border-bottom: 1px solid;"><strong>B. 500 largest stocks</strong></td></tr>
<tr>
   <td style="text-align:left;padding-left: 2em;" indentlevel="1"> Disagreement </td>
   <td style="text-align:right;"> 1.00 </td>
   <td style="text-align:right;"> 0.15 </td>
   <td style="text-align:right;"> 0.05 </td>
   <td style="text-align:right;"> 0.22 </td>
   <td style="text-align:right;"> 0.19 </td>
  </tr>
  <tr>
   <td style="text-align:left;padding-left: 2em;" indentlevel="1"> Directional </td>
   <td style="text-align:right;"> 0.15 </td>
   <td style="text-align:right;"> 1.00 </td>
   <td style="text-align:right;"> 0.02 </td>
   <td style="text-align:right;"> 0.06 </td>
   <td style="text-align:right;"> 0.02 </td>
  </tr>
  <tr>
   <td style="text-align:left;padding-left: 2em;" indentlevel="1"> AnalystDis </td>
   <td style="text-align:right;"> 0.05 </td>
   <td style="text-align:right;"> 0.02 </td>
   <td style="text-align:right;"> 1.00 </td>
   <td style="text-align:right;"> 0.17 </td>
   <td style="text-align:right;"> -0.04 </td>
  </tr>
  <tr>
   <td style="text-align:left;padding-left: 2em;" indentlevel="1"> StockTurn </td>
   <td style="text-align:right;"> 0.22 </td>
   <td style="text-align:right;"> 0.06 </td>
   <td style="text-align:right;"> 0.17 </td>
   <td style="text-align:right;"> 1.00 </td>
   <td style="text-align:right;"> -0.11 </td>
  </tr>
  <tr>
   <td style="text-align:left;padding-left: 2em;" indentlevel="1"> MFDis </td>
   <td style="text-align:right;"> 0.19 </td>
   <td style="text-align:right;"> 0.02 </td>
   <td style="text-align:right;"> -0.04 </td>
   <td style="text-align:right;"> -0.11 </td>
   <td style="text-align:right;"> 1.00 </td>
  </tr>
  <tr>
   <td style="text-align:left;padding-left: 2em;" indentlevel="1"> log(Size) </td>
   <td style="text-align:right;"> 0.37 </td>
   <td style="text-align:right;"> 0.01 </td>
   <td style="text-align:right;"> -0.13 </td>
   <td style="text-align:right;"> -0.30 </td>
   <td style="text-align:right;"> 0.44 </td>
  </tr>
</tbody>
</table>
---

background-image: url(https://github.com/chen-weitao/logo/blob/main/xiaohui.jpg?raw=true)
background-size: 100px
background-position: 90% 8%

## 投资组合收益率

<img src="https://github.com/chen-weitao/logo/blob/main/2023-10-29_214550.png?raw=true" width="100%" style="display: block; margin: auto;" />

---

background-image: url(https://github.com/chen-weitao/logo/blob/main/xiaohui.jpg?raw=true)
background-size: 100px
background-position: 90% 8%

## 投资组合收益率

<img src="https://github.com/chen-weitao/logo/blob/main/2023-10-29_215525.png?raw=true" width="100%" style="display: block; margin: auto;" />

---

background-image: url(https://github.com/chen-weitao/logo/blob/main/xiaohui.jpg?raw=true)
background-size: 100px
background-position: 90% 8%

## Fama-MacBeth对下月收益率

<img src="https://github.com/chen-weitao/logo/blob/main/2023-10-29_223552.png?raw=true" width="100%" style="display: block; margin: auto;" />
---

background-image: url(https://github.com/chen-weitao/logo/blob/main/xiaohui.jpg?raw=true)
background-size: 100px
background-position: 90% 8%

## Fama-MacBeth对下月收益率

<img src="https://github.com/chen-weitao/logo/blob/main/2023-10-29_223746.png?raw=true" width="100%" style="display: block; margin: auto;" />

---

background-image: url(https://github.com/chen-weitao/logo/blob/main/xiaohui.jpg?raw=true)
background-size: 100px
background-position: 90% 8%

## 影响机制

- Atmaz and Basak (2018)认为盈利偏差影响分歧和预期收益率的关系

- 基于季节性随机游走的盈利意外定义（Earnings Surprise,  `\(SUE\)`）：
`$$SUE_{i,q}^{SRW\text{ }}=\frac{{{E}_{i,q}}-E_{i,q-4}^{\text{ }}}{{{P}_{i,q}}}$$`
其中，  `\(i\)` 是某个公司； `\(q\)` 是某个季度；  `\({E}_{i,q}\)` 是当季度每股盈利； `\({E}_{i,q-4}\)` 是去年同季度的每股盈利； `\({P}_{i,q}\)`是财报发布前20天的股价； `\({SRW}\)`是季节性随机游走（Seasonal Random Walk）

- 基于分析师预测（ `\(Analyst\)`）来定义盈利意外：
`$$SUE_{i,q}^{Analyst\text{ }}=\frac{{{E}_{i,q}}-E_{i,q}^{Analyst\text{ }}}{{{P}_{i,q}}}$$`
其中， `\({E}_{i,q}^{Analyst}\)` 是分析师盈利预测平均值，其余定义不变

---

background-image: url(https://github.com/chen-weitao/logo/blob/main/xiaohui.jpg?raw=true)
background-size: 100px
background-position: 90% 8%

## 影响机制

- Hong and Sraer (2016)认为负向效应在高beta的股票中更为显著

- 回归方程如下：
`$$\begin{align}
  &  CAR\text{ }{{[1,5]}_{i,t}}={{\alpha }^{High\text{ }}}Hig{{h}_{i,t}}+{{\alpha }^{Medium\text{ }}}Mediu{{m}_{i,t}}+{{\alpha }^{Low\text{ }}}Lo{{w}_{i,t}} \\ 
 & \,\,+{{\beta }^{Dis\times High\text{ }}}Disagreemen{{t}_{i,t-1}}\times Hig{{h}_{i,t}} \\ 
 & \,\,+{{\beta }^{Dis\times Medium\text{ }}}Disagreemen{{t}_{i,t-1}}\times Mediu{{m}_{i,t}} \\ 
 & \,\,+{{\beta }^{Dis\times Low\text{ }}}Disagreemen{{t}_{i,t-1}}\times Lo{{w}_{i,t}}+Control{{s}_{i,t}}+{{\varepsilon }_{i,t}}  
\end{align}$$`

- CAR（Cumulative Abnormal Returns）为财报发布日后第1至5天的累计超额收益（相对于市场风险）

- Disagreement为财报发布日前10天的平均分歧（不包括平值期权）

- High、Medium和Low为虚拟变量，分别表示两个指标SUE前20%、中间40%和最后20%的交集

---

background-image: url(https://github.com/chen-weitao/logo/blob/main/xiaohui.jpg?raw=true)
background-size: 100px
background-position: 90% 8%

## 按beta分类的回归结果

<img src="https://github.com/chen-weitao/logo/blob/main/2023-10-29_233741.png?raw=true" width="100%" style="display: block; margin: auto;" />

---

background-image: url(https://github.com/chen-weitao/logo/blob/main/xiaohui.jpg?raw=true)
background-size: 100px
background-position: 90% 8%

## 按beta分类的回归结果

<img src="https://github.com/chen-weitao/logo/blob/main/2023-10-29_234358.png?raw=true" width="100%" style="display: block; margin: auto;" />

---

background-image: url(https://github.com/chen-weitao/logo/blob/main/xiaohui.jpg?raw=true)
background-size: 100px
background-position: 90% 8%

## 按beta分类的回归结果

<img src="https://github.com/chen-weitao/logo/blob/main/2023-10-29_234417.png?raw=true" width="100%" style="display: block; margin: auto;" />

---

background-image: url(https://github.com/chen-weitao/logo/blob/main/xiaohui.jpg?raw=true)
background-size: 100px
background-position: 90% 8%

## Nagel (2005)机构持有量理论

<img src="https://github.com/chen-weitao/logo/blob/main/2023-10-29_234924.png?raw=true" width="95%" style="display: block; margin: auto;" />

---

background-image: url(https://github.com/chen-weitao/logo/blob/main/xiaohui.jpg?raw=true)
background-size: 100px
background-position: 90% 8%

## Nagel (2005)机构持有量理论

<img src="https://github.com/chen-weitao/logo/blob/main/2023-10-29_234948.png?raw=true" width="95%" style="display: block; margin: auto;" />

---

background-image: url(https://github.com/chen-weitao/logo/blob/main/xiaohui.jpg?raw=true)
background-size: 100px
background-position: 90% 8%

## 稳健性检验

- 稳健性检验前（左）和稳健性检验后（右）：

.pull-left[
1. 月平均成交量；

1. 成交量加权组合收益率；

1. 月度频率；

1. 用CAPM模型计算CAR；

1. 没有考虑另外的分歧差异；

]

.pull-right[
1. 持仓量（相关系数0.77）；

1. 平均加权组合收益率；

1. 周度频率；

1. 用五因子模型计算CAR；

1. 增加控制变量，即期权交易量在不同在值程度上的离散程度；

]


---

background-image: url(https://github.com/chen-weitao/logo/blob/main/xiaohui.jpg?raw=true)
background-size: 100px
background-position: 90% 8%

## 参考文献

1. Atmaz, A., & Basak, S. Belief dispersion in the stock market. *Journal of Finance*, 2018, 73(3): 1225–1279.

2. Golez, B., & Goyenko, R. Disagreement in the equity options market and stock returns. *The Review of Financial Studies*, 2022, 35(3): 1443–1479.

3. Hong, H., & Sraer. D. A. Speculative betas. *Journal of Finance*, 2016, 71(5): 2095–2144.

4. Nagel, S. Short sales, institutional investors and the cross-section of stock returns. *Journal of Financial*, 2005, 78(2): 277–309.

---

class: center, middle

# 谢谢
本幻灯片发布于 <u>[**GitHub**](https://github.com/chen-weitao/Presentation1101) <u>

