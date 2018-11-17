## MA(X, N)

求 X 在 N 周期内的简单移动平均。

计算方法：`MA=(A1+A2+A3+A4+A5)/5` 求 A 在 5 个周期内的简单移动平均

## EMA(X, N)

表示求 X 在 N 周期内的平滑移动平均。（指数加权）

计算方法：`EMA(X,N)=[2*X+(N-1)*EMA(X,(N-1))]/(N+1)` 其中 EMA(X,(N-1)) 为第 (N-1) 天的 EMA 值

## SMA(X, N, M)

得到 X 在 N 个周期内的移动平均，M 为权重（M 为常数）。

计算方法：`SMA(N)=SMA(N-1)*(N-M)/N+X(N)*M/N`

## TRMA

求 X 在 N 周期内的三角移动平均。

## TSMA

求 X 在 N 周期内的时间序列移动平均。

计算方法：`TSMA(X,N)=FOCAST(X,N)+SLOPE(X,N)`
