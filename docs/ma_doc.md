## MA(X, N)

求 X 在 N 周期内的简单移动平均。

![](http://fxcodebase.com/wiki/images/math/d/2/f/d2f270e23f2b0ea60b507f4b3c4e56d6.png)

優化
如果已知之前的移動平均值，則無需計算總和。您只需將最早的值從之前的結果中扣除，然後加上新值：

![](http://fxcodebase.com/wiki/images/math/7/9/3/7939971a56e55a5d1128f73047d7fd18.png)

计算方法：`MA=(A1+A2+A3+A4+A5)/5` 求 A 在 5 个周期内的简单移动平均

## EMA(X, N)

表示求 X 在 N 周期内的平滑移动平均。（指数加权）

指数移动平均线公式计算数据的移动平均值，该公式对一段时间内的最新数据赋予较大权重，对较旧数据赋予较小权重。 此公式与加权移动平均线公式相比，可以更快地生成反映市场趋势的移动平均线。

此公式可平滑数据序列。 这使变动数据更易于分析。

經典 EMA 公式為：

![](http://fxcodebase.com/wiki/images/math/9/3/0/93053c024e4b10d2b788835d4c017268.png)

其中

![](http://fxcodebase.com/wiki/images/math/7/f/4/7f43ebda03cef0c2c1125de202b8c8f5.png)

计算方法：`EMA(X,N)=[2*X+(N-1)*EMA(X,(N-1))]/(N+1)` 其中 `EMA(X,(N-1))` 为第 `(N-1)` 天的 EMA 值

## SMA(X, N, M)

得到 X 在 N 个周期内的移动平均，M 为权重（M 为常数）。

计算方法：`SMA(N)=SMA(N-1)*(N-M)/N+X(N)*M/N`

## TRMA

求 X 在 N 周期内的三角移动平均。

## TSMA

求 X 在 N 周期内的时间序列移动平均。

计算方法：`TSMA(X,N)=FOCAST(X,N)+SLOPE(X,N)`

## SAR - (PSAR)

PSAR 是由 Welles Wilder 开发的指标，其中 P 代表抛物线和 SAR 代表止损和反转。该指标有助于评估股票走势的方向。

它是如何工作的？

PSAR，或抛物线止损和反向，是一种流行的指标，主要由交易者用来确定给定资产的未来短期动能。

PSAR 指标形成抛物线，由小点组成，高于或低于交易价格。当抛物线低于股价时，抛物线作为支撑和止点区域，同时表明看涨趋势价格行动。当股票价格低于一个点时，就会形成 止损 / 卖出 / 卖空的触发形式。

抛物线 SAR（PSAR）指标使用最近的极端（最高和最低）价格（EP）以及加速因子（AF）来确定指示点将出现的位置。

抛物线 SAR 计算如下：

```
上升趋势：PSAR = 此前 PSAR + AF 之前（现有 EP - 前 PSAR）

下降趋势：PSAR = 此前 PSAR - 前 AF（现有 PSAR - 前 EP）

Uptrend: PSAR = Prior PSAR + Prior AF (Prior EP – Prior PSAR)

Downtrend: PSAR = Prior PSAR – Prior AF (Prior PSAR – Prior EP)
```

(EP = Highest high for an uptrend, and lowest low for a downtrend updated each time a new EP is reached.

AF = Default of 0.02, increasing by 0.02 each time a new EP is reached, with a maximum of 0.20.)
