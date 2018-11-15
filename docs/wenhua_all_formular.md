# K线形态

## K线 K线

``` cpp
DRAWKLINE(0.75,COLORRED,1,COLORCYAN,0);
```

## BAR 竹线

``` cpp
OPEN,BAMBOOLINE;
```

## TOWER 宝塔线

``` cpp
TOWER;
```

## CLOSE 收盘价线

``` cpp
CLOSE;
```

## WK 文华k线图

``` cpp
DRAWKLINE2(0.75,COLORRED,1,COLORCYAN,0);
```

# 趋势分析

## MA组合 移动平均线组合

``` cpp
//该模型仅仅用来示范如何根据指标编写简单的模型
//用户需要根据自己交易经验，进行修改后再实际应用!!!
// //后为文字说明，编写模型时不用写出
MA1:MA(CLOSE,N1);
MA2:MA(CLOSE,N2);
MA3:MA(CLOSE,N3);
MA4:MA(CLOSE,N4);
MA5:MA(CLOSE,N5);
MA6:MA(CLOSE,N6);//定义6条均线
```

## BOLL 布林通道线

``` cpp
//该模型仅仅用来示范如何根据指标编写简单的模型
//用户需要根据自己交易经验，进行修改后再实际应用!!!
// //后为文字说明，编写模型时不用写出
MA1:MA(CLOSE,N1);
MA2:MA(CLOSE,N2);
MA3:MA(CLOSE,N3);
MA4:MA(CLOSE,N4);
MA5:MA(CLOSE,N5);
MA6:MA(CLOSE,N6);//定义6条均线
```

## CDP 逆势操作

``` cpp
//该模型仅仅用来示范如何根据指标编写简单的模型
//用户需要根据自己交易经验，进行修改后再实际应用!!!
// //后为文字说明，编写模型时不用写出
PT  := REF(HIGH,1)-REF(LOW,1);//求一个周期前的最高价与最低价的差值
CDP := (REF(HIGH,1) + REF(LOW,1) + REF(CLOSE,1))/3;//求前一个周期的最高价，最低价，收盘价三者的简单平均
AH  : MA(CDP + PT,N);//CDP与PT的和在N个周期内的简单移动平均
AL  : MA(CDP - PT,N);//CDP与PT的差在N个周期内的简单移动平均
NH  :MA(2*CDP-LOW,N);//2倍的CDP与最低价的差在N个周期内的简单移动平均
NL  :MA(2*CDP-HIGH,N);//2倍的CDP与最高价的差在N个周期内的简单移动平均
```

## ENV Envalops

``` cpp
//该模型仅仅用来示范如何根据指标编写简单的模型
//用户需要根据自己交易经验，进行修改后再实际应用!!!
// //后为文字说明，编写模型时不用写出
UPPER : MA(CLOSE,N1)*(1+N2/100);//N1个周期收盘价均值与(1+N2/100)之积，定义为UPPER
LOWER : MA(CLOSE,N1)*(1-N2/100);//N1个周期收盘价均值与(1-N2/100)之积，定义为LOWER

```

## HCL 均线通道

``` cpp
//该模型仅仅用来示范如何根据指标编写简单的模型
//用户需要根据自己交易经验，进行修改后再实际应用!!!
// //后为文字说明，编写模型时不用写出
MAH:MA(HIGH,N);//最高价的N周期平均
MAL:MA(LOW,N);//最低价的N周期平均
MAC:MA(CLOSE,N);//收盘价的N周期平均
```

## MIKE 麦克指标

``` cpp
//该模型仅仅用来示范如何根据指标编写简单的模型
//用户需要根据自己交易经验，进行修改后再实际应用!!!
// //后为文字说明，编写模型时不用写出
TYP:=(HIGH+LOW+CLOSE)/3;//当根K线的最高值最低值收盘价的简单均值定义为TYP。
LL:=LLV(LOW,N);//N个周期的最低值
HH:=HHV(HIGH,N);//N个周期的最高值
WR:TYP+(TYP-LL);
MR:TYP+(HH-LL);
SR:2*HH-LL;
WS:TYP-(HH-TYP);
MS:TYP-(HH-LL);
SS:2*LL-HH;
```

## PUBU 瀑布线

``` cpp
//该模型仅仅用来示范如何根据指标编写简单的模型
//用户需要根据自己交易经验，进行修改后再实际应用!!!
// //后为文字说明，编写模型时不用写出
PB1:(EMA(CLOSE,M1)+MA(CLOSE,M1*2)+MA(CLOSE,M1*4))/3;
PB2:(EMA(CLOSE,M2)+MA(CLOSE,M2*2)+MA(CLOSE,M2*4))/3;
PB3:(EMA(CLOSE,M3)+MA(CLOSE,M3*2)+MA(CLOSE,M3*4))/3;
PB4:(EMA(CLOSE,M4)+MA(CLOSE,M4*2)+MA(CLOSE,M4*4))/3;
PB5:(EMA(CLOSE,M5)+MA(CLOSE,M5*2)+MA(CLOSE,M5*4))/3;
PB6:(EMA(CLOSE,M6)+MA(CLOSE,M6*2)+MA(CLOSE,M6*4))/3; //定义6条瀑布线
```

## SAR 止损点

``` cpp
//该模型仅仅用来示范如何根据指标编写简单的模型
//用户需要根据自己交易经验，进行修改后再实际应用!!!
// //后为文字说明，编写模型时不用写出
STEP1:=STEP/100;
MVALUE1:=MVALUE/100;
SARLINE:SAR(N,STEP1,MVALUE1),CIRCLEDOT;//N个周期的抛物转向，步长为STEP1，极限值为MVALUE1.
//参数优化不支持对小数进行优化。如果需要进行参数优化，可以对模型源码进行修改，将模型源码中的小数参数乘以0.1或者0.01等，然后将参数列表中的小数参数数值乘以10或者100变为整数即可
```

## SP 日内均价线

``` cpp
SETTLE;


```

## BBI 多空指数

``` cpp
//该模型仅仅用来示范如何根据指标编写简单的模型
//用户需要根据自己交易经验，进行修改后再实际应用!!!
// //后为文字说明，编写模型时不用写出
BBI1:(MA(CLOSE,N1)+MA(CLOSE,N2)+MA(CLOSE,N3)+MA(CLOSE,N4))/4;//求N1周期，N2周期，N3周期，N4周期收盘价均线的简单平均
```

## DKX 多空线

``` cpp
//该模型仅仅用来示范如何根据指标编写简单的模型
//用户需要根据自己交易经验，进行修改后再实际应用!!!
// //后为文字说明，编写模型时不用写出
A:=(3*C+L+O+H)/6;//3倍收盘价与最高价、最低价、开盘价之和的均值。
B:(20*A+19*REF(A,1)+18*REF(A,2)+17*REF(A,3)+16*REF(A,4)+15*REF(A,5)+14*REF(A,6)+13*REF(A,7)+12*REF(A,8)+11*REF(A,9)+10*REF(A,10)+9*REF(A,11)+8*REF(A,12)+7*REF(A,13)+6*REF(A,14)+5*REF(A,15)+4*REF(A,16)+3*REF(A,17)+2*REF(A,18)+REF(A,20))/210;
//对A值做加权均值计算。
D:MA(B,M);//对B值做10周期平均计算。
```

## SAR1 止损点

``` cpp
//该模型仅仅用来示范如何根据指标编写简单的模型
//用户需要根据自己交易经验，进行修改后再实际应用!!!
// //后为文字说明，编写模型时不用写出
STEP1:=STEP/100;
MVALUE1:=MVALUE/10;
SARLINE:SAR1(N,STEP1,MVALUE1),CIRCLEDOT;//N个周期的抛物转向，步长为STEP1，极限值为MVALUE1.
//参数优化不支持对小数进行优化。如果需要进行参数优化，可以对模型源码进行修改，将模型源码中的小数参数乘以0.1或者0.01等，然后将参数列表中的小数参数数值乘以10或者100变为整数即可
```

## WTD 文华通道线

``` cpp
MA(CLOSE,M);
A:=(ASK1*ASK1VOL+ASK2*ASK2VOL+ASK3*ASK3VOL+ASK4*ASK4VOL+ASK5*ASK5VOL)/(ASK1VOL+ASK2VOL+ASK3VOL+ASK4VOL+ASK5VOL);
B:=(BID1*BID1VOL+BID2*BID2VOL+BID3*BID3VOL+BID4*BID4VOL+BID5*BID5VOL)/(BID1VOL+BID2VOL+BID3VOL+BID4VOL+BID5VOL);
DRAWCOLORLINE(RISING(N),MA(A,M),COLORRED,COLORGREEN);
DRAWCOLORLINE(RISING(N),MA(B,M),COLORRED,COLORGREEN);
```

## BBIBOLL 多空布林线

``` cpp
BBIBOLL:(MA(C,3)+MA(C,6)+MA(C,12)+MA(C,24))/4;
UPR:BBIBOLL+M*STD(BBIBOLL,N);
DWN:BBIBOLL-M*STD(BBIBOLL,N);
```

# 摆动分析

## ADTM 动态买卖气指标

``` cpp
//该模型仅仅用来示范如何根据指标编写简单的模型
//用户需要根据自己交易经验，进行修改后再实际应用!!!
// //后为文字说明，编写模型时不用写出
DTM:=IFELSE(OPEN<=REF(OPEN,1),0,MAX((HIGH-OPEN),(OPEN-REF(OPEN,1))));//如果开盘价小于等于一个周期前的开盘价，DTM取值为0，否则取最高价减去开盘价和开盘价减去前一个周期开盘价这两个差值中的最大值
DBM:=IFELSE(OPEN>=REF(OPEN,1),0,MAX((OPEN-LOW),(OPEN-REF(OPEN,1))));//如果开盘价大于等于一个周期前的开盘价，DBM取值为0，否则取开盘价减去最低价和开盘价减去前一个周期开盘价这两个差值中的最大值
STM:=SUM(DTM,N);//求N个周期内的DTM的总和
SBM:=SUM(DBM,N);//求N个周期内的DBM的总和
ADTM:IFELSE(STM>SBM,(STM-SBM)/STM,IFELSE(STM=SBM,0,(STM-SBM)/SBM));//如果STM大于SBM，ADTM取值为(STM-SBM)/STM，如果STM等于SBM，ADTM取值为0,如果STM小于SBM，ADTM取值为(STM-SBM)/SBM
ADTMMA:MA(ADTM,M);//求M个周期内的ADTM的简单移动平均
```

## ARBR 人气意愿指标

``` cpp
//该模型仅仅用来示范如何根据指标编写简单的模型
//用户需要根据自己交易经验，进行修改后再实际应用!!!
// //后为文字说明，编写模型时不用写出
AR : SUM(HIGH-OPEN,N)/SUM(OPEN-LOW,N)*100;//N个周期内的最高价减去开盘价的和与N个周期内的开盘价减去最低价的和的百分比
BR : SUM(MAX(0,HIGH-REF(CLOSE,1)),N)/SUM(MAX(0,REF(CLOSE,1)-LOW),N)*100;//取最高价减去一个周期前的收盘价的与0中的最大值，求和，取一个周期前的收盘价减去最低价与0中的最大值，求和，两个和的百分比
```

## ASI 振动升降指标

``` cpp
//该模型仅仅用来示范如何根据指标编写简单的模型
//用户需要根据自己交易经验，进行修改后再实际应用!!!
// //后为文字说明，编写模型时不用写出
LC:=REF(CLOSE,1);//一个周期前的收盘价
AA:=ABS(HIGH-LC);//最高价与一个周期前的收盘价的差值的绝对值
BB:=ABS(LOW-LC);//最低价与一个周期前的收盘价的差值的绝对值
CC:=ABS(HIGH-REF(LOW,1));//最高价与一个周期前的最低价的差值的绝对值
DD:=ABS(LC-REF(OPEN,1));//一个周期前的收盘价与一个周期前的开盘价的差值的绝对值
R:=IFELSE(AA>BB&&AA>CC,AA+BB/2+DD/4,IFELSE(BB>CC&&BB>AA,BB+AA/2+DD/4,CC+DD/4));//如果AA>BB&&AA>CC,R取值为AA+BB/2+DD/4,如果BB>CC&&BB>AA,R取值为BB+AA/2+DD/4,否则R取值为CC+DD/4
X:=(CLOSE-LC+(CLOSE-OPEN)/2+LC-REF(OPEN,1));//最新价减去一个周期前的收盘价加上开盘价与最新价的二分之一，再加上一个周期前的收盘价与开盘价的差值
SI:=16*X/R*MAX(AA,BB);
ASI:SUM(SI,0);//从本地数据第一个数据开始求SI的总和
```

## ATR 真实波幅

``` cpp
//该模型仅仅用来示范如何根据指标编写简单的模型
//用户需要根据自己交易经验，进行修改后再实际应用!!!
// //后为文字说明，编写模型时不用写出
TR : MAX(MAX((HIGH-LOW),ABS(REF(CLOSE,1)-HIGH)),ABS(REF(CLOSE,1)-LOW));//求最高价减去最低价，一个周期前的收盘价减去最高价的绝对值，一个周期前的收盘价减去最低价的绝对值，这三个值中的最大值
ATR : MA(TR,N),COLORYELLOW;//求N个周期内的TR的简单移动平均
```

## B3612 三减六日乖离

``` cpp
//该模型仅仅用来示范如何根据指标编写简单的模型
//用户需要根据自己交易经验，进行修改后再实际应用!!!
// //后为文字说明，编写模型时不用写出
B36 : MA(CLOSE,3)-MA(CLOSE,6);//3周期收盘价均线减去6周期收盘价均线
B612 : MA(CLOSE,6)-MA(CLOSE,12);//6周期收盘价均线减去12周期收盘价均线
```

## BIAS 乖离率

``` cpp
//该模型仅仅用来示范如何根据指标编写简单的模型
//用户需要根据自己交易经验，进行修改后再实际应用!!!
// //后为文字说明，编写模型时不用写出
BIAS1:(CLOSE-MA(CLOSE,L1))/MA(CLOSE,L1)*100;//收盘价减去收盘价在L1周期内的简单移动平均，除以收盘价在L1周期内的简单移动平均乘以100；
BIAS2:(CLOSE-MA(CLOSE,L2))/MA(CLOSE,L2)*100;//同上
BIAS3:(CLOSE-MA(CLOSE,L3))/MA(CLOSE,L3)*100;//同上
```

## CCI 顺势指标

``` cpp
//该模型仅仅用来示范如何根据指标编写简单的模型
//用户需要根据自己交易经验，进行修改后再实际应用!!!
// //后为文字说明，编写模型时不用写出
TYP:=(CLOSE+HIGH+LOW)/3;//求最新价，最高价和最低价三者的简单平均
CCI:(TYP-MA(TYP,N))/(0.015*AVEDEV(TYP,N));//TYP与TYP的N周期平均值做差，该差值与TYP在N个周期内的0.015倍的平均绝对偏差值做比值
```

## CR CR能量指标

``` cpp
//该模型仅仅用来示范如何根据指标编写简单的模型
//用户需要根据自己交易经验，进行修改后再实际应用!!!
// //后为文字说明，编写模型时不用写出
MID := (HIGH+LOW+CLOSE)/3;//求最新价，最高价和最低价三者的简单平均
CR:SUM(MAX(0,HIGH-REF(MID,1)),N)/SUM(MAX(0,REF(MID,1)-LOW),N)*100;//取最高价减去一个周期前的MID的与0中的最大值，求和，取一个周期前的MID减去最低价与0中的最大值，求和，两个和的百分比
CRMA1:REF(MA(CR,M1),M1/2.5+1);//取(M1/2.5+1)个周期前的M1周期CR简单平均值
CRMA2:REF(MA(CR,M2),M2/2.5+1);//取(M2/2.5+1)个周期前的M2周期CR简单平均值
CRMA3:REF(MA(CR,M3),M3/2.5+1);//取(M3/2.5+1)个周期前的M3周期CR简单平均值
CRMA4:REF(MA(CR,M4),M4/2.5+1);//取(M4/2.5+1)个周期前的M4周期CR简单平均值
```

## DBCD 异同离差乖离率

``` cpp
//该模型仅仅用来示范如何根据指标编写简单的模型
//用户需要根据自己交易经验，进行修改后再实际应用!!!
// //后为文字说明，编写模型时不用写出
BIAS:=(CLOSE-MA(CLOSE,N))/MA(CLOSE,N);//收盘价减收盘价在N个周期内的简单移动平均比收盘价在N个周期内的简单移动平均；
DIF:=(BIAS-REF(BIAS,M));//BIAS减M个周期前的BIAS;
DBCD:SMA(DIF,T,1);//DIF在T个周期内的移动平均
MM:MA(DBCD,5);//DBCD在5个周期内的简单移动平均
```

## DDI 方向标准离差指数

``` cpp
//该模型仅仅用来示范如何根据指标编写简单的模型
//用户需要根据自己交易经验，进行修改后再实际应用!!!
// //后为文字说明，编写模型时不用写出
TR:=MAX(ABS(HIGH-REF(HIGH,1)),ABS(LOW-REF(LOW,1)));//（最高价-前一周期最高价）的绝对值与（最低价-前一周期最低价）的绝对值两者之间较大者定义为TR
DMZ:=IFELSE((HIGH+LOW)<=(REF(HIGH,1)+REF(LOW,1)),0,MAX(ABS(HIGH-REF(HIGH,1)),ABS(LOW-REF(LOW,1))));//如果（最高价+最低价）<=（前一周期最高价+前一周期最低价），DMZ返回0，否则返回TR
DMF:=IFELSE((HIGH+LOW)>=(REF(HIGH,1)+REF(LOW,1)),0,MAX(ABS(HIGH-REF(HIGH,1)),ABS(LOW-REF(LOW,1))));//如果（最高价+最低价）>=（前一周期最高价+前一周期最低价），DMF返回0，否则返回TR
DIZ:=SUM(DMZ,N)/(SUM(DMZ,N)+SUM(DMF,N));//N个周期DMZ之和与（N个周期DMZ的和+N个周期DMF的和）作比值
DIF:=SUM(DMF,N)/(SUM(DMF,N)+SUM(DMZ,N));//N个周期DMF的和与（N个周期DMF的和+N个周期DMZ的和）作比值
DDI:=DIZ-DIF;//DIZ与DIF的差值定义为DDI
DDI,COLORSTICK;
ADDI:SMA(DDI,N1,M);//DDI在N1个周期内权重为M的加权平均
AD:MA(ADDI,M1);//ADDI在M1个周期内的简单移动平均
```

## DMA 平均线差

``` cpp
//该模型仅仅用来示范如何根据指标编写简单的模型
//用户需要根据自己交易经验，进行修改后再实际应用!!!
// //后为文字说明，编写模型时不用写出
DDD : MA(CLOSE,SHORT)-MA(CLOSE,LONG);//短周期收盘价均值与长周期收盘价均值做差
AMA : MA(DDD,M);//M个周期的DDD均值
```

## DMI 趋向指标

``` cpp
//该模型仅仅用来示范如何根据指标编写简单的模型
//用户需要根据自己交易经验，进行修改后再实际应用!!!
// //后为文字说明，编写模型时不用写出
TR := SUM(MAX(MAX(HIGH-LOW,ABS(HIGH-REF(CLOSE,1))),ABS(LOW-REF(CLOSE,1))),N);//最高价与最低价做差，最高价与前一周期收盘价做差，最低价与前一周期收盘价作差，在上述三个数据中取绝对值最大者，对该最大值做N周期累加求和。。
HD := HIGH-REF(HIGH,1);//最高价与前一周期最高价做差
LD := REF(LOW,1)-LOW;//前一周期最低价与最低价做差
DMP:= SUM(IFELSE(HD>0 && HD>LD,HD,0),N);//如果HD>0并且HD>LD,取HD否则取0,对取值做N周期累加求和。
DMM:= SUM(IFELSE(LD>0 && LD>HD,LD,0),N);//如果LD>0并且LD>HD,取LD否则取0,对取值做N周期累加求和。
PDI: DMP*100/TR;
MDI: DMM*100/TR;
ADX: MA(ABS(MDI-PDI)/(MDI+PDI)*100,M);//MDI与PDI差的绝对值与(MDI+PDI)*100做比值，取该比值的M个周期均值。
ADXR:(ADX+REF(ADX,M))/2;
BACKGROUNDSTYLE(1);
```

## KD 随机指标

``` cpp
//该模型仅仅用来示范如何根据指标编写简单的模型
//用户需要根据自己交易经验，进行修改后再实际应用!!!
// //后为文字说明，编写模型时不用写出
RSV:=(CLOSE-LLV(LOW,N))/(HHV(HIGH,N)-LLV(LOW,N))*100;//收盘价与N周期最低值做差，N周期最高值与N周期最低值做差，两差之间做比值定义为RSV
K:SMA(RSV,M1,1);//RSV的移动平均
D:SMA(K,M2,1);//K值的移动平均
```

## KDJ 随机指标

``` cpp
//该模型仅仅用来示范如何根据指标编写简单的模型
//用户需要根据自己交易经验，进行修改后再实际应用!!!
// //后为文字说明，编写模型时不用写出
RSV:=(CLOSE-LLV(LOW,N))/(HHV(HIGH,N)-LLV(LOW,N))*100;//收盘价与N周期最低值做差，N周期最高值与N周期最低值做差，两差之间做比值。
K:SMA(RSV,M1,1);//RSV的移动平均值
D:SMA(K,M2,1);//K的移动平均值
J:3*K-2*D;
BACKGROUNDSTYLE(1);
```

## LWR 威廉指标

``` cpp
//该模型仅仅用来示范如何根据指标编写简单的模型
//用户需要根据自己交易经验，进行修改后再实际应用!!!
// //后为文字说明，编写模型时不用写出
RSV:= (CLOSE-HHV(HIGH,N))/(HHV(HIGH,N)-LLV(LOW,N))*100;//收盘价与N周期最高值做差，N周期最高值与N周期最低值做差，两差值间做比值。
LWR1:SMA(RSV,M1,1);//RSV的移动平均
LWR2:SMA(LWR1,M2,1);//LWR1的移动平均
```

## MACD 平滑移动平均线

``` cpp
//该模型仅仅用来示范如何根据指标编写简单的模型
//用户需要根据自己交易经验，进行修改后再实际应用!!!
// //后为文字说明，编写模型时不用写出
DIFF : EMA(CLOSE,SHORT) - EMA(CLOSE,LONG);//短周期与长周期的收盘价的指数平滑移动平均值做差。
DEA  : EMA(DIFF,M);//DIFF的M个周期指数平滑移动平均
2*(DIFF-DEA),COLORSTICK;//DIFF减DEA的2倍画柱状线


```

## MASS Mass Index

``` cpp
//该模型仅仅用来示范如何根据指标编写简单的模型
//用户需要根据自己交易经验，进行修改后再实际应用!!!
// //后为文字说明，编写模型时不用写出
MASS:SUM(EMA((HIGH-LOW),N1)/EMA(EMA((HIGH-LOW),N1),N1),N2);//N1个周期最高值与最低值之差做指数平滑移动平均，该平均值与N1个周期该均值的指数平滑移动平均值做比，计算该比值的N2个周期的累加求和。
```

## MFI 资金流量指标

``` cpp
//该模型仅仅用来示范如何根据指标编写简单的模型
//用户需要根据自己交易经验，进行修改后再实际应用!!!
// //后为文字说明，编写模型时不用写出
MASS:SUM(EMA((HIGH-LOW),N1)/EMA(EMA((HIGH-LOW),N1),N1),N2);//N1个周期最高值与最低值之差做指数平滑移动平均，该平均值与N1个周期该均值的指数平滑移动平均值做比，计算该比值的N2个周期的累加求和。
```

## MI 动量指标

``` cpp
//该模型仅仅用来示范如何根据指标编写简单的模型
//用户需要根据自己交易经验，进行修改后再实际应用!!!
// //后为文字说明，编写模型时不用写出
A:CLOSE-REF(CLOSE,N);//收盘价与N周期前收盘价做差
MI:SMA(A,N,1);//A的移动平均
```

## MICD 异同离差动力指数

``` cpp
//该模型仅仅用来示范如何根据指标编写简单的模型
//用户需要根据自己交易经验，进行修改后再实际应用!!!
// //后为文字说明，编写模型时不用写出
MI:=CLOSE-REF(CLOSE,1);//收盘价与前一周期收盘价之差
AMI:=SMA(MI,N,1);//MI的移动平均值
DIF:MA(REF(AMI,1),N1)-MA(REF(AMI,1),N2);//前一周期AMI的N1周期均值与前一周期AMI的N2周期均值之间做差。
MICD:SMA(DIF,10,1);//DIF的移动平均值
```

## MTM MTM动力指标

``` cpp
//该模型仅仅用来示范如何根据指标编写简单的模型
//用户需要根据自己交易经验，进行修改后再实际应用!!!
// //后为文字说明，编写模型时不用写出
MTM : CLOSE-REF(CLOSE,N);//收盘价与N周期前收盘价做差
MTMMA : MA(MTM,N1);//MTM的N1周期简单均值。
```

## PRICEOSC Price Oscillator

``` cpp
//该模型仅仅用来示范如何根据指标编写简单的模型
//用户需要根据自己交易经验，进行修改后再实际应用!!!
// //后为文字说明，编写模型时不用写出
PRICEOSC:(MA(CLOSE,SHORT)-MA(CLOSE,LONG))/MA(CLOSE,SHORT)*100;//短周期与长周期均值做差，该差与短周期均值之间做比值。
```

## PSY 心理线

``` cpp
//该模型仅仅用来示范如何根据指标编写简单的模型
//用户需要根据自己交易经验，进行修改后再实际应用!!!
// //后为文字说明，编写模型时不用写出
PSY:COUNT(CLOSE>REF(CLOSE,1),N)/N*100;//N个周期内满足收盘价大于一个周期前的收盘价的周期数，比N*100；
PSYMA:MA(PSY,M);//PSY在M个周期内的简单移动平均；
```

## QHLSR 阻力指标

``` cpp
//该模型仅仅用来示范如何根据指标编写简单的模型
//用户需要根据自己交易经验，进行修改后再实际应用!!!
// //后为文字说明，编写模型时不用写出
QHL:=(CLOSE-REF(CLOSE,1))-(VOL-REF(VOL,1))*(REF(HIGH,1)-REF(LOW,1))/REF(VOL,1);//收盘价减去上根K线的收盘价的差值 减去当前成交量减去上根成交量的差值乘以上根的高点减上根的低点的积除以上根的成交量；
A:=SUM(IFELSE(QHL>0,QHL,0),5);//如果QHL>0 则返回QHL的值 否则返回0，统计五周期内的和。
E:=SUM(IFELSE(QHL>0,QHL,0),10);//如果QHL>0 则返回QHL的值 否则返回0，统计十周期内的和。
B:=ABS(SUM(IFELSE(QHL<0,QHL,0),5));//如果QHL<0 则返回QHL的值 否则返回0，统计五周期内的和，结果取绝对值。
F:=ABS(SUM(IFELSE(QHL<0,QHL,0),10));//如果QHL<0 则返回QHL的值 否则返回0，统计十周期内的和，结果取绝对值。
D:=A/(A+B);//A除以A+B的和；
G:=E/(E+F);//E除以E+F的和；
QHL5:IFELSE(SUM(IFELSE(QHL>0,1,0),5)=5,1,IFELSE(SUM(IFELSE(QHL<0,1,0),5)=5,0,D));//如果5周期内连续满足QHL，则返回1，否则当五周期内连续满足QHL<0时，返回0，否则返回D值；
QHL10:G;
```

## RC 变化率指数

``` cpp
//该模型仅仅用来示范如何根据指标编写简单的模型
//用户需要根据自己交易经验，进行修改后再实际应用!!!
// //后为文字说明，编写模型时不用写出
RC:=CLOSE/REF(CLOSE,N);//收盘价与N周期前的收盘价做比。
ARC:SMA(REF(RC,1),N,1);//前一周期的RC值做移动平均
```

## RCCD 异同离差变化率指数

``` cpp
//该模型仅仅用来示范如何根据指标编写简单的模型
//用户需要根据自己交易经验，进行修改后再实际应用!!!
// //后为文字说明，编写模型时不用写出
RC:=CLOSE/REF(CLOSE,N);//当前价格除以N周期前的收盘价；
ARC:=SMA(REF(RC,1),N,1);//一周期前的RC的以1为权重的移动平均；
DIF:MA(REF(ARC,1),N1)-MA(REF(ARC,1),N2);//N1个周期的一周期前的ARC的简单移动平均与N2周期内前一周期的ARC的简单移动平均的差值；
RCCD:SMA(DIF,N,1);//DIF的N周期的以1为权重的移动平均；
```

## ROC 变动速率

``` cpp
//该模型仅仅用来示范如何根据指标编写简单的模型
//用户需要根据自己交易经验，进行修改后再实际应用!!!
// //后为文字说明，编写模型时不用写出
ROC:(CLOSE-REF(CLOSE,N))/REF(CLOSE,N)*100;//收盘价与N周期前收盘价做差，该差值与N周期前收盘价做比值，定义为ROC。
ROCMA:MA(ROC,M);
BACKGROUNDSTYLE(2);
```

## RSI 相对强弱指标(Relative Strenth Index)

``` cpp
//该模型仅仅用来示范如何根据指标编写简单的模型
//用户需要根据自己交易经验，进行修改后再实际应用!!!
// //后为文字说明，编写模型时不用写出
LC := REF(CLOSE,1);//前一周期收盘价
RSI1:SMA(MAX(CLOSE-LC,0),N1,1)/SMA(ABS(CLOSE-LC),N1,1)*100;//当根K线收盘价与前一周期收盘价做差，在该差值与0之间取最大值，做N1周期移动平均。收盘价与前一周期收盘价做差值，取该差值的N1周期移动平均值，两平均值之间做比值。
RSI2:SMA(MAX(CLOSE-LC,0),N2,1)/SMA(ABS(CLOSE-LC),N2,1)*100;//当根K线收盘价与前一周期收盘价做差，在该差值与0之间取最大值，做N2周期移动平均。收盘价与前一周期收盘价做差值，取该差值的N2周期移动平均值，两平均值之间做比值。
BACKGROUNDSTYLE(0);
```

## SLOWKD 慢速KD

``` cpp
//该模型仅仅用来示范如何根据指标编写简单的模型
//用户需要根据自己交易经验，进行修改后再实际应用!!!
RSV:= (CLOSE-LLV(LOW,N))/(HHV(HIGH,N)-LLV(LOW,N))*100;//收盘价与N周期最高值做差，N周期最高值与N周期最低值做差，两差之间做比值。
FASTK:=SMA(RSV,M1,1);//RSV的移动平均值
K:SMA(FASTK,M2,1);//FASTK的移动平均值
D:SMA(K,M3,1);//K的移动平均值

```

## SRDM 动向速度比率

``` cpp
//该模型仅仅用来示范如何根据指标编写简单的模型
//用户需要根据自己交易经验，进行修改后再实际应用!!!
// //后为文字说明，编写模型时不用写出
DMZ:=IFELSE((HIGH+LOW)<=(REF(HIGH,1)+REF(LOW,1)),0,MAX(ABS(HIGH-REF(HIGH,1)),ABS(LOW-REF(LOW,1))));
//如果高点加低点的价格小于等于昨天的高点加低点的价格，则返回0，否则返回 当根K线的高点与上根K线的高点的差值的绝对值与当根K线的低点与上根K线的低点的绝对值中较大者；
DMF:=IFELSE((HIGH+LOW)>=(REF(HIGH,1)+REF(LOW,1)),0,MAX(ABS(HIGH-REF(HIGH,1)),ABS(LOW-REF(LOW,1))));
//如果当根K线的高点加低点的价格大于等于昨天的高点加低点的价格，则返回0，否则返回 当根K线的高点与上根K线的高点的差值的绝对值与当根K线的低点与上根K线的低点的绝对值中较大者；
ADMZ:=MA(DMZ,10);//DMZ值的10日简单移动平均；
ADMF:=MA(DMF,10);//DMF值的10日简单移动平均；
SRDM:IFELSE(ADMZ>ADMF,(ADMZ-ADMF)/ADMZ,IFELSE(ADMZ=ADMF,0,(ADMZ-ADMF)/ADMF));//如果ADMZ>ADMF，则返回(ADMZ-ADMF)/ADMZ，否则当ADMZ=ADMF时返回0，小于时返回(ADMZ-ADMF)/ADMF;
ASRDM:SMA(SRDM,N,1);//SRDM值的N日以1为权重的移动平均；
```

## SRMI MI修正指标

``` cpp
//该模型仅仅用来示范如何根据指标编写简单的模型
//用户需要根据自己交易经验，进行修改后再实际应用!!!
// //后为文字说明，编写模型时不用写出
A:IFELSE(CLOSE<REF(CLOSE,N),(CLOSE-REF(CLOSE,N))/REF(CLOSE,N),IFELSE(CLOSE=REF(CLOSE,N),0,(CLOSE-REF(CLOSE,N))/CLOSE));
//如果当前价格小于N周期前的收盘价，则返回(CLOSE-REF(CLOSE,N))/REF(CLOSE,N)的值，如果当前价格大于等于N周期前的收盘价，则当等于的时候返回0，大于的时候返回(CLOSE-REF(CLOSE,N))/CLOSE);
MI:SMA(A,N,1);//A的N周期的以1为权重的移动平均；
```

## WR 威廉指标(William's %R)

``` cpp
//该模型仅仅用来示范如何根据指标编写简单的模型
//用户需要根据自己交易经验，进行修改后再实际应用!!!
// //后为文字说明，编写模型时不用写出
WR:-100*(HHV(HIGH,N)-CLOSE)/(HHV(HIGH,N)-LLV(LOW,N));//N周期内最高价与收盘价之差与N周期内最高价和最低价之差之间的比值，取负。
```

## ZDZB 筑底指标

``` cpp
//该模型仅仅用来示范如何根据指标编写简单的模型
//用户需要根据自己交易经验，进行修改后再实际应用!!!
// //后为文字说明，编写模型时不用写出
A:=COUNT(CLOSE>=REF(CLOSE,1),N1)/COUNT(CLOSE<REF(CLOSE,1),N1);//N1周期内CLOSE>=REF(CLOSE,1)的次数与N1周期内CLOSE<REF(CLOSE,1)的次数的比值；
B:MA(A,N2);//N2周期内的A的简单移动平均；
D:MA(A,N3);//N3周期内的A的简单移动平均；
```

## DPO 区间震荡线

``` cpp
//该模型仅仅用来示范如何根据指标编写简单的模型
//用户需要根据自己交易经验，进行修改后再实际应用!!!
// //后为文字说明，编写模型时不用写出
DPO:CLOSE-REF(MA(CLOSE,20),11);//收盘价与11个周期前的20周期均值做差
```

## LON长线 长线指标

``` cpp
//该模型仅仅用来示范如何根据指标编写简单的模型
//用户需要根据自己交易经验，进行修改后再实际应用!!!
// //后为文字说明，编写模型时不用写出
TB:=IFELSE(HIGH>REF(CLOSE,1),HIGH-REF(CLOSE,1)+CLOSE-LOW,CLOSE-LOW);//若最高价大于前收盘价则取当根K线下影线与当根K线幅度的和，否则取当根K线下影线长度
TS:=IFELSE(REF(CLOSE,1)>LOW,REF(CLOSE,1)-LOW+HIGH-CLOSE,HIGH-CLOSE);//若前收盘价大于最低价则取当根K线上影线与当根K线幅度的和，否则取当根K线上影线长度
VOL1:=(TB-TS)*VOL/(TB+TS)/10000;//TB与TS差值和成交量求积在与TB和TS的和做商
VOL10:=DMA(VOL1,0.1);//取得VOL1的0.1动态均值
VOL11:=DMA(VOL1,0.05);//取的VOL1的0.05动态均值
RES1:=VOL10-VOL11;//取VOL10与VOL11的差
LON:SUM(RES1,0),COLORSTICK;//取得历史所有K线的RES1的和
MA1:MA(LON,10);//取LON的10周期均值。

```

## SHORT短线 短线指标

``` cpp
//该模型仅仅用来示范如何根据指标编写简单的模型
//用户需要根据自己交易经验，进行修改后再实际应用!!!
// //后为文字说明，编写模型时不用写出
TB:=IFELSE(HIGH>REF(CLOSE,1),HIGH-REF(CLOSE,1)+CLOSE-LOW,CLOSE-LOW);//若最高价大于前收盘价则取当根K线下影线与当根K线幅度的和，否则取当根K线下影线长度
TS:=IFELSE(REF(CLOSE,1)>LOW,REF(CLOSE,1)-LOW+HIGH-CLOSE,HIGH-CLOSE);//若前收盘价大于最低价则取当根K线上影线与当根K线幅度的和，否则取当根K线上影线长度
VOL1:=(TB-TS)*VOL/(TB+TS)/10000;//TB与TS差值和成交量求积在与TB和TS的和做商
VOL10:=DMA(VOL1,0.1);//取得VOL1的0.1动态均值
VOL11:=DMA(VOL1,0.05);//取得VOL1的0.05动态均值
SHORT:VOL10-VOL11,COLORSTICK;//取VOL10与VOL11的差值SHORT;	
MA1:MA(SHORT,10);//取SHORT的10周期均值

```

# 量仓分析

## MV 均量线

``` cpp
//该模型仅仅用来示范如何根据指标编写简单的模型
//用户需要根据自己交易经验，进行修改后再实际应用!!!
// //后为文字说明，编写模型时不用写出
TB:=IFELSE(HIGH>REF(CLOSE,1),HIGH-REF(CLOSE,1)+CLOSE-LOW,CLOSE-LOW);//若最高价大于前收盘价则取当根K线下影线与当根K线幅度的和，否则取当根K线下影线长度
TS:=IFELSE(REF(CLOSE,1)>LOW,REF(CLOSE,1)-LOW+HIGH-CLOSE,HIGH-CLOSE);//若前收盘价大于最低价则取当根K线上影线与当根K线幅度的和，否则取当根K线上影线长度
VOL1:=(TB-TS)*VOL/(TB+TS)/10000;//TB与TS差值和成交量求积在与TB和TS的和做商
VOL10:=DMA(VOL1,0.1);//取得VOL1的0.1动态均值
VOL11:=DMA(VOL1,0.05);//取得VOL1的0.05动态均值
SHORT:VOL10-VOL11,COLORSTICK;//取VOL10与VOL11的差值SHORT;	
MA1:MA(SHORT,10);//取SHORT的10周期均值

```

## WAD 威廉多空力度线

``` cpp
//该模型仅仅用来示范如何根据指标编写简单的模型
//用户需要根据自己交易经验，进行修改后再实际应用!!!
// //后为文字说明，编写模型时不用写出
A:ABS(SUM(IFELSE( CLOSE>REF(CLOSE,1),CLOSE-MIN(REF(CLOSE,1),LOW),IFELSE(CLOSE<REF(CLOSE,1),CLOSE-MAX(REF(CLOSE,1),HIGH),0)),0));
//当CLOSE>REF(CLOSE,1)的时候，返回CLOSE-MIN(REF(CLOSE,1),LOW)的值，否则当CLOSE<REF(CLOSE,1)时，返回CLOSE-MAX(REF(CLOSE,1),HIGH)的值，都不满足的话返回0，同时从数据开始的第一根K线开始对每根K线返回值进行加总；
B:SMA(A,N,1);//A的N周期的以1为权重的移动平均；
E:SMA(A,M,1);//A的M周期的以1为权重的移动平均；
```

## AD Accumulation/Distribution

``` cpp
SUM(((CLOSE-LOW)-(HIGH-CLOSE))/(HIGH-LOW)*VOL,0);
```

## CCL 持仓异动

``` cpp
CCL;
```

## CJL 成交量

``` cpp
VOL,VOLUMESTICK;
OPID:OPI;
```

## DUALVOL 多空量比

``` cpp
M:=DUALVOLUME('M');
N:=DUALVOLUME('N');
DRAWCOLUMNCHART(N,SCALE>=0.5,M>=0);
```

## OBV 能量潮

``` cpp
SUM(IFELSE(CLOSE>REF(CLOSE,1),VOL,IFELSE(CLOSE<REF(CLOSE,1),-VOL,0)),0);
```

## OPI 持仓量

``` cpp
OPI,OPISTICK;
```

## PVT 价量趋势指数

``` cpp
SUM((CLOSE-REF(CLOSE,1))/REF(CLOSE,1)*VOL,0);
```

## VOSC Volume Oscillator

``` cpp
(MA(VOL,SHORT)-MA(VOL,LONG))/MA(VOL,SHORT)*100;
```

## VR VR容量比率

``` cpp
LC:=REF(CLOSE,1);
SUM(IFELSE(CLOSE>LC,VOL,0),N)/
SUM(IFELSE(CLOSE<=LC,VOL,0),N)*100;
```

## VROC 量变动速率

``` cpp
(VOL-REF(VOL,N))/REF(VOL,N)*100;
```

## VRSI 量相对强弱

``` cpp
SMA(MAX(VOL-REF(VOL,1),0),N,1)/SMA(ABS(VOL-REF(VOL,1)),N,1)*100;
```

## WVAD 威廉变异离散量

``` cpp
(CLOSE-OPEN)/(HIGH-LOW)*VOL;
```

# 形态选股

## 均线多头排列

``` cpp
//该公式仅仅用来示范如何编写选股公式
//用户需要根据自己交易经验，进行修改后再实际应用!!!
A1:=MA(CLOSE,N);
A2:=MA(CLOSE,N1);
A3:=MA(CLOSE,N2);
A4:=MA(CLOSE,N3);
COUNT(A1>A2 AND A2>A3 AND A3>A4,3)=3 AND ISUP,SELECT;//选出连续3日满足均线多头排列的股票。
```

## 均线空头排列

``` cpp
//该公式仅仅用来示范如何编写选股公式
//用户需要根据自己交易经验，进行修改后再实际应用!!!
A1:=MA(CLOSE,N);
A2:=MA(CLOSE,N1);
A3:=MA(CLOSE,N2);
A4:=MA(CLOSE,N3);
COUNT(A1<A2 AND A2<A3 AND A3<A4,3)=3 AND NOT(ISUP),SELECT;//选出连续3日满足均线空头排列的股票。
```

## 早晨之星

``` cpp
//该公式仅仅用来示范如何编写选股公式
//用户需要根据自己交易经验，进行修改后再实际应用!!!
REF(CLOSE,2)/REF(OPEN,2)<0.95 AND
REF(OPEN,1)<REF(CLOSE,2) AND
ABS(REF(OPEN,1)-REF(CLOSE,1))/REF(CLOSE,1)<0.03 AND
CLOSE/OPEN>1.05 AND CLOSE>REF(CLOSE,2),SELECT;//选出满足“早晨之星”形态的股票。
```

## 黄昏之星

``` cpp
//该公式仅仅用来示范如何编写选股公式
//用户需要根据自己交易经验，进行修改后再实际应用!!!
REF(CLOSE,2)/REF(OPEN,2)>1.03 AND
REF(OPEN,1)>REF(CLOSE,2) AND
ABS(REF(OPEN,1)-REF(CLOSE,1))/REF(CLOSE,1)<0.02 AND
CLOSE/OPEN<0.97 AND CLOSE<REF(CLOSE,2),SELECT;//选出满足“黄昏之星”形态的股票。
```

## 平台整理

``` cpp
//该公式仅仅用来示范如何编写选股公式
//用户需要根据自己交易经验，进行修改后再实际应用!!!
BARPOS>N AND (HHV(CLOSE,N)-LLV(CLOSE,N))/LLV(CLOSE,N)<=(N1/100),SELECT;//选出在过去的N日中K线的最高价和最低价的变动范围在M%以内的股票。

//N、N1是参数，默认值是30、11，即选出在过去的30日中K线的最高价和最低价的变动范围在11%以内的股票。数值可以在参数列表中修改。
```

## 强势整理

``` cpp
//该公式仅仅用来示范如何编写选股公式
//用户需要根据自己交易经验，进行修改后再实际应用!!!
A1:=ABS(CLOSE-OPEN)/OPEN<0.015;
A2:=COUNT(A1,M)=M;
A3:=REF(O,M)<REF(CLOSE,M) AND REF(CLOSE,M)/REF(CLOSE,M+1)>1+N/100;
A2 AND A3,SELECT;//选出前两日收阳，前三日的收盘价上涨N%，且连续2日波幅小于1.5%的股票。

//M和N是参数，默认值是2、5，即选出前两日收阳，前三日的收盘价上涨5%，且连续2日波幅小于1.5%的股票。数值可以在参数列表中修改。
```

## 高开大阴线

``` cpp
//该公式仅仅用来示范如何编写选股公式
//用户需要根据自己交易经验，进行修改后再实际应用!!!
OPEN>CLOSE AND OPEN/REF(C,1)>=1+M/100 AND CLOSE/OPEN<=1-N/100,SELECT;//选出开盘价比昨日收盘价高出M%，且当前K线为跌幅小于N%的阴线的股票。

//M和N是参数，默认值为4、5，即选出开盘价比昨日收盘价高出4%，且当前K线为跌幅小于5%的阴线的股票。数值可以在参数列表中修改。
```

## 低开大阳线

``` cpp
//该公式仅仅用来示范如何编写选股公式
//用户需要根据自己交易经验，进行修改后再实际应用!!!
OPEN<CLOSE AND OPEN/REF(C,1)<=1-M/100 AND CLOSE/OPEN>=1+N/100,SELECT;//选出开盘价比上一周期的收盘价小M%，且当前K线为涨幅大于N%的阳线的股票。

//M和N是参数，默认值为4、7，即选出开盘价比上一周期的收盘价小4%，且当前K线为涨幅大于7%的阳线的股票。数值可以在参数列表中修改。
```

## 四连阴

``` cpp
//该公式仅仅用来示范如何编写选股公式
//用户需要根据自己交易经验，进行修改后再实际应用!!!
EVERY(CLOSE<OPEN,4),SELECT;//选出连续4日收阴的股票。
```

## 四连阳

``` cpp
//该公式仅仅用来示范如何编写选股公式
//用户需要根据自己交易经验，进行修改后再实际应用!!!
EVERY(CLOSE>OPEN,4),SELECT;//选出连续四日收阳的股票。
```

## 低点搜索

``` cpp
//该公式仅仅用来示范如何编写选股公式
//用户需要根据自己交易经验，进行修改后再实际应用!!!
W:=MA((LLV(LOW,45)-CLOSE)/(HHV(HIGH,45)-LLV(LOW,45))*100,N);//定义变量W，表示45日中的最低点和均线的差值，与45日最高最低值之差的比值，在5个周期的均值。
CROSS(-5,W),SELECT;//选出W值下穿-5的股票。

//N是参数，表示均线的周期，可以在参数列表中修改。
```

## 突破

``` cpp
//该公式仅仅用来示范如何编写选股公式
//用户需要根据自己交易经验，进行修改后再实际应用!!!
M1:=MA(C,N1);
M2:=MA(C,N2);
M3:=MA(C,N3);
D1:=BARSLAST(CROSS(M1,M2));
D2:=BARSLAST(CROSS(M1,M3));
D3:=BARSLAST(CROSS(M2,M3));
T1:=CROSS(M2,M3);
T2:=D1>=D2 AND D2>=D3;
T3:=COUNT(CROSS(M2,M1) OR CROSS(M3,M2) OR CROSS(M3,M1),D1)=0;
T4:=REF(M1<M3 AND M2<M3,D1+1);
T1 AND T2 AND T3 AND T4,SELECT;//选出三条均线依次满足向上穿越的股票。

//N1、N2、N3是参数，表示均线的周期，数值可以在参数列表中修改。
```

## 四周法则

``` cpp
//该公式仅仅用来示范如何编写选股公式
//用户需要根据自己交易经验，进行修改后再实际应用!!!
HIGH>HV(HIGH,N),SELECT;//选出最高价创20周期新高的股票。N是参数，表示周期，N值可以在参数列表修改。
```

## 跳空缺口

``` cpp
//该公式仅仅用来示范如何编写选股公式
//用户需要根据自己交易经验，进行修改后再实际应用!!!
HIGH<REF(LOW,1) OR LOW>REF(HIGH,1),SELECT;//选出向上或者向下跳空的股票。
```

## 跳空高开或低开

``` cpp
//该公式仅仅用来示范如何编写选股公式
//用户需要根据自己交易经验，进行修改后再实际应用!!!
A:=(O>REF(H,1) AND (O-REF(C,1))/REF(C,1)*100>N);
B:=(O<REF(L,1) AND (O-REF(C,1))/REF(C,1)*100<N);
IF(N>0,A,B),SELECT;//选出K线实体部分向上或者向下跳空的股票。
```

# 指标选股

## BIAS乖离率买入条件选股

``` cpp
//该公式仅仅用来示范如何编写选股公式
//用户需要根据自己交易经验，进行修改后再实际应用!!!
(CLOSE-MA(CLOSE,N))/MA(CLOSE,N)*100<LL,SELECT;//选出乖离率小于-6的股票；LL为参数，默认值为-6，可以在参数列表修改。
```

## BIAS乖离率卖出条件选股

``` cpp
//该公式仅仅用来示范如何编写选股公式
//用户需要根据自己交易经验，进行修改后再实际应用!!!
100*(C-MA(C,N))/MA(C,N)>M,SELECT;//选出乖离率大于12的股票；M为参数，默认值为12，可以在参数列表修改。
```

## BOLL布林带买入条件选股

``` cpp
//该公式仅仅用来示范如何编写选股公式
//用户需要根据自己交易经验，进行修改后再实际应用!!!
MID:=MA(CLOSE,N);
TMP2:=STD(CLOSE,M);
TOP:=MID+P*TMP2;
BOTTOM:=MID-P*TMP2;
CROSS(CLOSE,BOTTOM),SELECT;//选出价格上穿布林下轨的股票
```

## BOLL布林带卖出条件选股

``` cpp
//该公式仅仅用来示范如何编写选股公式
//用户需要根据自己交易经验，进行修改后再实际应用!!!
MID:=MA(CLOSE,N);
TMP2:=STD(CLOSE,M);
TOP:=MID+P*TMP2;
BOTTOM:=MID-P*TMP2;
CROSS(TOP,C),SELECT;//选出价格下穿布林上轨的股票
```

## KDJ随机指标买入条件选股

``` cpp
//该公式仅仅用来示范如何编写选股公式
//用户需要根据自己交易经验，进行修改后再实际应用!!!
RSV:=(CLOSE-LLV(LOW,N))/(HHV(HIGH,N)-LLV(LOW,N))*100;
K:=SMA(RSV,M1,1);
D:=SMA(K,M2,1);
J:=3*K-2*D;
CROSS(J,0),SELECT;//选出J值上穿0轴的股票
```

## KDJ随机指标卖出条件选股

``` cpp
//该公式仅仅用来示范如何编写选股公式
//用户需要根据自己交易经验，进行修改后再实际应用!!!
RSV:=(CLOSE-LLV(LOW,N))/(HHV(HIGH,N)-LLV(LOW,N))*100;
K:=SMA(RSV,M1,1);
D:=SMA(K,M2,1);
J:=3*K-2*D;
CROSS(0,J),SELECT;//选出J值下穿0轴的股票
```

## KD买入点条件选股

``` cpp
//该公式仅仅用来示范如何编写选股公式
//用户需要根据自己交易经验，进行修改后再实际应用!!!
RSV:= (CLOSE-LLV(LOW,N))/(HHV(HIGH,N)-LLV(LOW,N))*100;
K:=SMA(RSV,M1,1);
D:=SMA(K,M2,1);
CROSS(K,D) && D<N1,SELECT;//选出K上穿D，且D值小于20的股票；N1为参数，默认值为20，可以在参数列表修改。
```

## KD卖出点条件选股

``` cpp
//该公式仅仅用来示范如何编写选股公式
//用户需要根据自己交易经验，进行修改后再实际应用!!!
RSV:= (CLOSE-LLV(LOW,N))/(HHV(HIGH,N)-LLV(LOW,N))*100;
K:=SMA(RSV,N1,1);
D:=SMA(K,N2,1);
CROSS(D,K) && D>N3,SELECT;//选出K下穿D，且D值大于80的股票；N3为参数，默认值为80，可以在参数列表修改。
```

## MACD买入点条件选股

``` cpp
//该公式仅仅用来示范如何编写选股公式
//用户需要根据自己交易经验，进行修改后再实际应用!!!
DIFF:= EMA(CLOSE,SHORT) - EMA(CLOSE,LONG);
DEA:= EMA(DIFF,M);
CROSS(DIFF,DEA),SELECT;//选出DIFF上穿DEA的股票。
```

## MACD卖出点条件选股

``` cpp
//该公式仅仅用来示范如何编写选股公式
//用户需要根据自己交易经验，进行修改后再实际应用!!!
DIFF:= EMA(CLOSE,SHORT) - EMA(CLOSE,LONG);
DEA:= EMA(DIFF,M);
CROSSDOWN(DIFF,DEA),SELECT;//选出DIFF下穿DEA的股票。
```

## MA均线买入条件选股

``` cpp
//该公式仅仅用来示范如何编写选股公式
//用户需要根据自己交易经验，进行修改后再实际应用!!!
CROSS(MA(CLOSE,SHORT),MA(CLOSE,LONG)),SELECT;//选出5周期均线上穿10周期均线的股票；SHORT和LONG为参数，默认值为5和10，可以在参数列表修改。
```

## MA均线卖出条件选股

``` cpp
//该公式仅仅用来示范如何编写选股公式
//用户需要根据自己交易经验，进行修改后再实际应用!!!
CROSS(MA(C,M),MA(C,N)),SELECT;//选出10周期均线下穿30周期均线的股票；M和N为参数，默认值为10和30，可以在参数列表修改。
```

## MTM买入条件选股

``` cpp
//该公式仅仅用来示范如何编写选股公式
//用户需要根据自己交易经验，进行修改后再实际应用!!!
MTM:=CLOSE-REF(CLOSE,N);
MTMMA:=MA(MTM,N1);
CROSS(MTMMA,0),SELECT;//选出MTMMA指标上穿0轴的股票。
```

## MTM卖出条件选股

``` cpp
//该公式仅仅用来示范如何编写选股公式
//用户需要根据自己交易经验，进行修改后再实际应用!!!
MTM:=CLOSE-REF(CLOSE,N);
MTMMA:=MA(MTM,N1);
CROSSDOWN(MTMMA,0),SELECT;//选出MTMMA指标下穿0轴的股票。

```

## RSI买入条件选股

``` cpp
//该公式仅仅用来示范如何编写选股公式
//用户需要根据自己交易经验，进行修改后再实际应用!!!
LC:= REF(CLOSE,1);
RSI1:=SMA(MAX(CLOSE-LC,0),N1,1)/SMA(ABS(CLOSE-LC),N1,1)*100;
RSI2:=SMA(MAX(CLOSE-LC,0),N2,1)/SMA(ABS(CLOSE-LC),N2,1)*100;
CROSS(RSI1,LL),SELECT;//选出RSI上穿20的股票；LL为参数，默认值为20，可以在参数列表修改。
```

## RSI卖出条件选股

``` cpp
//该公式仅仅用来示范如何编写选股公式
//用户需要根据自己交易经验，进行修改后再实际应用!!!
LC:= REF(CLOSE,1);
RSI1:=SMA(MAX(CLOSE-LC,0),N1,1)/SMA(ABS(CLOSE-LC),N1,1)*100;
RSI2:=SMA(MAX(CLOSE-LC,0),N2,1)/SMA(ABS(CLOSE-LC),N2,1)*100;
CROSS(RSI1,HH),SELECT;//选出RSI下穿80的股票；HH为参数，默认值为80，可以在参数列表修改。
```

## SAR买入条件选股

``` cpp
//该公式仅仅用来示范如何编写选股公式
//用户需要根据自己交易经验，进行修改后再实际应用!!!
STEP1:=STEP/100;
MVALUE1:=MVALUE/10;
SARLINE:=SAR(N,STEP1,MVALUE1);
CROSS(SARLINE,0),SELECT;//选出SAR值由负转正的股票。
```

## SAR卖出条件选股

``` cpp
//该公式仅仅用来示范如何编写选股公式
//用户需要根据自己交易经验，进行修改后再实际应用!!!
STEP1:=STEP/100;
MVALUE1:=MVALUE/10;
SARLINE:=SAR(N,STEP1,MVALUE1);
CROSSDOWN(SARLINE,0),SELECT;//选出SAR值由正转负的股票。
```

## W&R威廉指标买入条件选股

``` cpp
//该公式仅仅用来示范如何编写选股公式
//用户需要根据自己交易经验，进行修改后再实际应用!!!
RSV:= (CLOSE-HHV(HIGH,N))/(HHV(HIGH,N)-LLV(LOW,N))*100;
LWR1:=SMA(RSV,M1,1);
LWR2:=SMA(LWR1,M2,1);
CROSS(LWR1,HH),SELECT;//选出威廉指标上穿80的股票；HH为参数，默认值为80，可以在参数列表修改。
```

## W&R威廉指标卖出条件选股

``` cpp
//该公式仅仅用来示范如何编写选股公式
//用户需要根据自己交易经验，进行修改后再实际应用!!!
RSV:= (CLOSE-HHV(HIGH,N))/(HHV(HIGH,N)-LLV(LOW,N))*100;
LWR1:=SMA(RSV,M1,1);
LWR2:=SMA(LWR1,M2,1);
CROSS(LWR1,LL),SELECT;//选出威廉指标下穿20的股票；LL为参数，默认值为20，可以在参数列表修改。

```

# 走势选股

## N日创新高

``` cpp
//该公式仅仅用来示范如何编写选股公式
//用户需要根据自己交易经验，进行修改后再实际应用!!!
HHV(HIGH,N)=HHV(HIGH,0) AND BARSCOUNT(C)>=N,SELECT;//选出最高价创N日新高的股票。

//N为参数，默认值为3，即选出最高价创3日新高的股票。N值可以在参数列表中修改。

```

## N日创新低

``` cpp
//该公式仅仅用来示范如何编写选股公式
//用户需要根据自己交易经验，进行修改后再实际应用!!!
LLV(L,N)=LLV(L,0) AND BARSCOUNT(C)>=N,SELECT;//选出最低价创N日新低的股票。

//N为参数，默认值为3，即选出最低价创3日新低的股票。N值可以在参数列表中修改。

```

## M日阴线多于阳线

``` cpp
//该公式仅仅用来示范如何编写选股公式
//用户需要根据自己交易经验，进行修改后再实际应用!!!
COUNT(ISDOWN,M)>COUNT(ISUP,M),SELECT;//选出M日内阴线数量多于阳线数量的股票。

//M为参数，默认值为30，即选出30日内阴线数量多于阳线数量的股票。M值可以在参数列表中修改。

```

## M日阳线多于阴线

``` cpp
//该公式仅仅用来示范如何编写选股公式
//用户需要根据自己交易经验，进行修改后再实际应用!!!
COUNT(ISDOWN,M)<COUNT(ISUP,M),SELECT;//选出M日内阳线数量多于阴线数量的股票。

//M为参数，默认值为30，即选出30日内阳线数量多于阴线数量的股票。M值可以在参数列表中修改。
```

## N日内上涨多于下跌

``` cpp
//该公式仅仅用来示范如何编写选股公式
//用户需要根据自己交易经验，进行修改后再实际应用!!!
COUNT(C>REF(C,1),N)/N >= M/100,SELECT;//选出N日内上涨K线多于下跌K线的股票。

//N、M为参数，默认值为120、60，即选出120日内上涨K线占比大于60%的股票。N和M的数值可以在参数列表中修改。
```

## N日内下跌多于上涨

``` cpp
//该公式仅仅用来示范如何编写选股公式
//用户需要根据自己交易经验，进行修改后再实际应用!!!
COUNT(C<REF(C,1),N)/N >= M/100,SELECT;//选出N日内下跌K线多于上涨K线的股票。

//N、M为参数，默认值为120、60，即选出120日内下跌K线占比大于60%的股票。N和M的数值可以在参数列表中修改。
```

## 连续N天收阳线

``` cpp
//该公式仅仅用来示范如何编写选股公式
//用户需要根据自己交易经验，进行修改后再实际应用!!!
COUNT(ISUP,N)=N,SELECT;//选出N日内连续收阳的股票。

//N为参数，默认值为7，即选出7日内连续收阳的股票。N值可以在参数列表中修改。
```

## 连续N天收阴线

``` cpp
//该公式仅仅用来示范如何编写选股公式
//用户需要根据自己交易经验，进行修改后再实际应用!!!
COUNT(ISDOWN,N)=N,SELECT;//选出N日内连续收阴的股票。

//N为参数，默认值为7，即选出7日内连续收阴的股票。N值可以在参数列表中修改。
```

## 连续N天上涨

``` cpp
//该公式仅仅用来示范如何编写选股公式
//用户需要根据自己交易经验，进行修改后再实际应用!!!
COUNT(C>REF(C,1),N)=N,SELECT;//选出连续N天上涨的股票。

//N为参数，默认值为5，即选出5日内连续上涨的股票。N值可以在参数列表中修改。
```

## 连续N天下跌

``` cpp
//该公式仅仅用来示范如何编写选股公式
//用户需要根据自己交易经验，进行修改后再实际应用!!!
COUNT(C<REF(C,1),N)=N,SELECT;//选出连续N天下跌的股票。

//N为参数，默认值为5，即选出5日内连续下跌的股票。N值可以在参数列表中修改。
```

## 首次创新高

``` cpp
//该公式仅仅用来示范如何编写选股公式
//用户需要根据自己交易经验，进行修改后再实际应用!!!
BARSSINCE(C>HV(IF(BARSCOUNT(C)=1,HIGH,0),0))+1=1,SELECT;//选出价格首次创新高的股票。

```

## 首次创新低

``` cpp
//该公式仅仅用来示范如何编写选股公式
//用户需要根据自己交易经验，进行修改后再实际应用!!!
BARSSINCE(C<LV(IF(BARSCOUNT(C)=1,LOW,0),0))+1=1,SELECT;//选出价格首次创新低的股票。
```

## 创历史新高

``` cpp
//该公式仅仅用来示范如何编写选股公式
//用户需要根据自己交易经验，进行修改后再实际应用!!!
HHV(CLOSE,0)=CLOSE,SELECT;//选出收盘价创历史新高的股票。
```

## 创历史新低

``` cpp
//该公式仅仅用来示范如何编写选股公式
//用户需要根据自己交易经验，进行修改后再实际应用!!!
LLV(CLOSE,0)=CLOSE,SELECT;//选出收盘价创历史新低的股票。
```

## 持续放量

``` cpp
//该公式仅仅用来示范如何编写选股公式
//用户需要根据自己交易经验，进行修改后再实际应用!!!
B:=VOL>REF(VOL,1);
COUNT(B,M)=M,SELECT;//选出M日内持续放量的股票。

//M为参数，默认值为3，即选出3日内持续放量的股票。M值可以在参数列表中修改。
```

## 持续缩量

``` cpp
//该公式仅仅用来示范如何编写选股公式
//用户需要根据自己交易经验，进行修改后再实际应用!!!
B:=VOL<REF(VOL,1);
COUNT(B,M)=M,SELECT;//选出M日内持续缩量的股票。

//M为参数，默认值为3，即选出3日内持续缩量的股票。M值可以在参数列表中修改。
```

## 间隔放量

``` cpp
//该公式仅仅用来示范如何编写选股公式
//用户需要根据自己交易经验，进行修改后再实际应用!!!
A:=MA(VOL,5);
BARSCOUNT(C)>=N AND HHV(A,N)<N1*LLV(A,N) AND COUNT(VOL>N2*A,N)>N3,SELECT;//选出N日内的成交量均值的最大值小于N1倍的成交量均值最小值，且N日内成交量大于N2倍的成交量均值的K线根数大于N3的股票。

//N、N1、N2、N3为参数，默认值为30、4、2、2，即选出30日内的成交量均值的最大值小于4倍的成交量均值最小值，且30日内成交量大于2倍的成交量均值的K线根数大于2的股票。N、N1、N2、N3的数值可以在参数列表中修改。

```

## 突然放量

``` cpp
//该公式仅仅用来示范如何编写选股公式
//用户需要根据自己交易经验，进行修改后再实际应用!!!
VOL>REF(HHV(VOL,N),1)*M,SELECT;//选成交量大于前N日的成交量最大值的M倍的股票。

//N、M为参数，默认值为10、3，即选出成交量大于前10日中最大成交量3倍的股票。N、M的数值可以在参数列表中修改。
```

## 突破长期盘整

``` cpp
//该公式仅仅用来示范如何编写选股公式
//用户需要根据自己交易经验，进行修改后再实际应用!!!
REF(((HHV(H,N)-LLV(L,N))/LLV(L,N)),1)<=(N1/100) AND C>=REF(HHV(H,N),1) AND BARSCOUNT(C)>N,SELECT;//选出前N天，K线的最高价最低价在上下N1%范围内浮动，当日的价格突破N日最高价的股票。

//N、N1为参数，默认值为30、30，即选出在前30日，K线的最高最低值在30%的范围内浮动，当日价格突破30日最高价的股票。N、N1的数值可以在参数列表修改。
```

## 下跌多日再放量上涨

``` cpp
//该公式仅仅用来示范如何编写选股公式
//用户需要根据自己交易经验，进行修改后再实际应用!!!
A1:=REF(CLOSE,5)>REF(CLOSE,4);
A2:=REF(CLOSE,4)>REF(CLOSE,3);
A3:=REF(CLOSE,3)>REF(CLOSE,2);
A4:=REF(CLOSE,2)>REF(CLOSE,1);
A5:=CLOSE>REF(HIGH,1) AND V>REF(V,1);
A1 AND A2 AND A3 AND A4 AND A5,SELECT;//选出收盘价在前5日内连续下跌，当日价格突破上一日最高价，且成交量放量的股票。

```

## 百日地量

``` cpp
//该公式仅仅用来示范如何编写选股公式
//用户需要根据自己交易经验，进行修改后再实际应用!!!
VOL=LLV(VOL,100),SELECT;//选出成交量在100日内创新低的股票。
```

## 百日天量

``` cpp
//该公式仅仅用来示范如何编写选股公式
//用户需要根据自己交易经验，进行修改后再实际应用!!!
VOL=HHV(VOL,100),SELECT;//选出成交量在100日内创新高的股票。
```

# 其他

## OPEN 开盘价线

``` cpp
OPEN;
```

## HIGH 最高价线

``` cpp
HIGH;
```

## LOW 最低价线

``` cpp
LOW;
```

## MA 简单移动平均线

``` cpp
//该模型仅仅用来示范如何根据指标编写简单的模型
//用户需要根据自己交易经验，进行修改后再实际应用!!!
// //后为文字说明，编写模型时不用写出
MA1:MA(CLOSE,N);//定义10周期均线
```

## EMA 指数加权移动平均线

``` cpp
//该模型仅仅用来示范如何根据指标编写简单的模型
//用户需要根据自己交易经验，进行修改后再实际应用!!!
EMA10:=EMA(CLOSE,10);//定义10周期收盘价的指数平滑移动平均值。
EMA20:=EMA(CLOSE,20);//定义20周期收盘价的指数平滑移动平均值。
```

## EXPMA 指数加权移动平均线组合

``` cpp
MA1:EMA(CLOSE,P1);
MA2:EMA(CLOSE,P2);
MA3:EMA(CLOSE,P3);
MA4:EMA(CLOSE,P4);
```

## SMA 扩展指数加权移动平均线

``` cpp
SMA(CLOSE,N,2);
```

## EMA2 线性加权移动平均线

``` cpp
//该模型仅仅用来示范如何根据指标编写简单的模型
//用户需要根据自己交易经验，进行修改后再实际应用!!!
// //后为文字说明，编写模型时不用写出
EMA210:EMA2(CLOSE,10);//定义10周期收盘价的加权平均值。
EMA220:EMA2(CLOSE,20);//定义20周期收盘价的加权平均值。
```

## TRMA 三角移动平均线

``` cpp
MA1:TRMA(C,N);
```

## TSMA 时间序列三角移动平均线

``` cpp
MA1:TSMA(C,N);
```

## 走势图 Webstock 收盘线

``` cpp
CLOSE;
CALVOLPRICELIST;
POLYPOINT(V - REF(V,1)>BIGVOLLIMIT(V,50,5), C, COLORYELLOW);
POLYPOINT(BIDBIGVOLPRICE> 0 , BIDBIGVOLPRICE , COLORRED);
POLYPOINT(ASKBIGVOLPRICE> 0 , ASKBIGVOLPRICE , COLORGREEN);
```

# 趋势模型编写示范

## WHBXSF

``` cpp
//该公式为“趋势模型编写示范”中“跨周期编写示范”引用使用，请勿删除或者修改，否则将导致“跨周期编写示范”无法正常使用
//该公式内容为4条均线多头和空头排列
MA5:=MA(C,5);
MA10:=MA(C,10);
MA20:=MA(C,20);
MA30:=MA(C,30); //定义四条均线
A:=C>MA5&&MA5>MA10&&MA10>MA20&&MA20>MA30; //4条均线多头排列，且价格在均线之上
B:=C<MA5&&MA5<MA10&&MA10<MA20&&MA20<MA30; //4条均线空头排列，且价格在均线之下
```

## 跨指标编写示范

``` cpp
//该示范用均线和KDJ两个指标结合使用，演示“跨指标模型”的编写方法
//编写示范中，只对示范重点内容语句进行了注释，其他语句请自行翻译，或者咨询文华工作人员
//该模型仅仅用来示范演示使用，依此入市，风险自负。

RSV:=(CLOSE-LLV(LOW,9))/(HHV(HIGH,9)-LLV(LOW,9))*100;
K..SMA(RSV,3,1);
D..SMA(K,3,1);
J..3*K-2*D;//以上为KDJ公式
MA5^^MA(CLOSE,5);
MA10^^MA(CLOSE,10);//以上为定义5周期均线和10周期均线
CROSSUP(MA5,MA10)&&REF(J,1)<70,BK;//5周期均线上穿10周期均线并且前一个周期的J值少于70时买入开仓
CROSSDOWN(K,D)&&REF(J,1)>70,SP;//KD出现死叉并且前一个周期J值大于70时卖出平仓
CROSSDOWN(MA5,MA10)&&REF(J,1)>30,SK;//5周期均线下穿10周期均线并且前一个周期的J值大于30时卖出开仓
CROSSUP(K,D)&&REF(J,1)<30,BP;// KD出现金叉并且前一个周期J值小于30时买入平仓
AUTOFILTER;
```

## 跨合约编写示范

``` cpp
//该示范用均线和KDJ两个指标结合使用，演示“跨指标模型”的编写方法
//编写示范中，只对示范重点内容语句进行了注释，其他语句请自行翻译，或者咨询文华工作人员
//该模型仅仅用来示范演示使用，依此入市，风险自负。

RSV:=(CLOSE-LLV(LOW,9))/(HHV(HIGH,9)-LLV(LOW,9))*100;
K..SMA(RSV,3,1);
D..SMA(K,3,1);
J..3*K-2*D;//以上为KDJ公式
MA5^^MA(CLOSE,5);
MA10^^MA(CLOSE,10);//以上为定义5周期均线和10周期均线
CROSSUP(MA5,MA10)&&REF(J,1)<70,BK;//5周期均线上穿10周期均线并且前一个周期的J值少于70时买入开仓
CROSSDOWN(K,D)&&REF(J,1)>70,SP;//KD出现死叉并且前一个周期J值大于70时卖出平仓
CROSSDOWN(MA5,MA10)&&REF(J,1)>30,SK;//5周期均线下穿10周期均线并且前一个周期的J值大于30时卖出开仓
CROSSUP(K,D)&&REF(J,1)<30,BP;// KD出现金叉并且前一个周期J值小于30时买入平仓
AUTOFILTER;
```

## 跨周期编写示范

``` cpp
//该示范为引用文华商品指标对整体市场方向做判断，在具体品种上交易，演示“跨合约模型”的编写方法
//编写示范中，只对示范重点内容语句进行了注释，其他语句请自行翻译，或者咨询文华工作人员
//该模型仅仅用来示范演示使用，依此入市，风险自负。
#CALL[7186,WHBXSF]AS VAR
WHMA5:=VAR.MA5;//引用文华商品指数的5周期均线
WHMA10:=VAR.MA10;//引用文华商品指数的10周期均线
WHMA20:=VAR.MA20;//引用文华商品指数的20周期均线
N:=BARSLAST(DATE<>REF(DATE,1))+1;
KP:=VALUEWHEN(DATE<>REF(DATE,1),O);
N>5&&C>KP&&WHMA5>WHMA10&&WHMA10>WHMA20,BK;//开盘5个周期后，如果价格大于今开，并且文华商品指数均线多头排列，买入开仓
N>5&&C<KP&&WHMA5<WHMA10&&WHMA10<WHMA20,SK;//开盘5个周期后，如果价格小于今开，并且文华商品指数均线空头排列，卖出开仓
CLOSEMINUTE<=1,CLOSEOUT;
AUTOFILTER;



```

## 分组指令编写示范

``` cpp
//该示范主要用波幅判断不同的行情，使用不同的策略，演示“分组指令”的编写方法
//编写示范中，只对示范重点内容语句进行了注释，其他语句请自行翻译，或者咨询文华工作人员
//该模型仅仅用来示范演示使用，依此入市，风险自负。

TR:=MAX(MAX((HIGH-LOW),ABS(REF(CLOSE,1)-HIGH)),ABS(REF(CLOSE,1)-LOW));
ATR..MA(TR,26);//波幅
RSV:=(CLOSE-LLV(LOW,9))/(HHV(HIGH,9)-LLV(LOW,9))*100;
K:=SMA(RSV,3,1);
D:=SMA(K,3,1);
J:=3*K-2*D;
HH:=HV(H,10);
LL:=LV(L,10);
ATR>HV(ATR,10)&&H>HH&&C>O,BK('A');
ATR>HV(ATR,10)&&L<LL&&C<O,SK('A');//A组开仓指令为当波幅创新高的时候，用价格突破方法开仓
L<LV(L,4),SP('A');
H>HV(H,4),BP('A');//只平A组开仓
ATR<LV(ATR,10)&&CROSS(K,D)&&C>O,BK('B');
ATR<LV(ATR,10)&&CROSS(D,K)&&C<O,SK('B');//B组开仓指令为当波幅创新低的时候，用KDJ金叉死叉开仓
C>BKPRICE+15*MINPRICE||C<BKPRICE-5*MINPRICE||C<REF(L,BARSBK),SP('B');
C<SKPRICE-15*MINPRICE||C>SKPRICE+5*MINPRICE||C>REF(H,BARSSK),BP('B');//只平B组开仓
//不同的开仓条件开仓，用不同的平仓条件，有针对性的平仓。达到不同行情试用不同策略的目的。
AUTOFILTER;
```

## 日内清仓编写示范

``` cpp
//该示范主要演示“日内清仓”的编写方法
//编写示范中，只对示范重点内容语句进行了注释，其他语句请自行翻译，或者咨询文华工作人员
//该模型仅仅用来示范演示使用，依此入市，风险自负。

N:=BARSLAST(DATE<>REF(DATE,1))+1;
H>HV(H,2)&&C>HV(C,2)&&N>=3&&TIME<1445,BK;//开仓的时间要控制在清仓之前，否则清仓后又会开仓
L<LV(L,2)&&C<LV(C,2)&&N>=3&&TIME<1445,SK;
C<REF(L,1),SP;
C>REF(H,1),BP;
CLOSEMINUTE1<=10,CLOSEOUT;//当日收盘前10分钟无论多空都平仓（模型清仓）
MULTSIG(0,0,1,10);//出信号立即下单不复核，一根K线只出一个信号,每隔10秒计算一次信号。
AUTOFILTER;
```

## 加仓减仓编写示范

``` cpp
//该示范主要演示“加仓减仓”的编写方法
//编写示范中，只对示范重点内容语句进行了注释，其他语句请自行翻译，或者咨询文华工作人员
//该模型仅仅用来示范演示使用，依此入市，风险自负。

MA5^^MA(C,5);
MA10^^MA(C,10);
A:=MA5>MA10&&C>=HV(H,5);  //多头开仓条件   
A1:=C>BKPRICE+30*MINPRICE;//多头加仓条件
B:=MA5<MA10&&C<=LV(L,5);//空头开仓条件  
B1:=C<SKPRICE-30*MINPRICE;//空头加仓条件
A2:=BARSBK>=10&&C<BKPRICE+5*MINPRICE;//多头减仓条件;     
B2:=BARSSK>=10&&C>SKPRICE-5*MINPRICE;//空头减仓条件; 
D:=C>=BKPRICE+100*MINPRICE||C<=BKPRICE-10*MINPRICE;//多头全平仓条件; 
E:=C<=SKPRICE-100*MINPRICE||C>=SKPRICE+10*MINPRICE;//空头全平仓条件;
A,BK(2);
B,SK(2);
A1&&BKVOL>=2&&ISLASTBK,BK(1);
B1&&SKVOL>=2&&ISLASTSK,SK(1);//判断持仓和前一个信号，满足条件后加仓
A2&&ISLASTBK&&BKVOL>=2,SP(1);
B2&&ISLASTSK&&SKVOL>=2,BP(1);//判断持仓和前一个信号，满足条件后减仓
D&&BKVOL>0&&(ISLASTBK||ISLASTSP),SP(BKVOL);
E&&SKVOL>0&&(ISLASTSK||ISLASTBP),BP(SKVOL);//判断持仓和前一个信号，满足条件后全平
//加仓减仓模型的编写重点为对持仓和信号的判断，然后才能确定是否进行加仓减仓
TRADE_AGAIN(1);
```

## 海龟交易编写示范

``` cpp
//该示范主要用海龟交易法则，演示“头寸计算，最大仓位控制等资金管理”的编写方法
//编写示范中，只对示范重点内容语句进行了注释，其他语句请自行翻译，或者咨询文华工作人员
//该模型仅仅用来示范演示使用，依此入市，风险自负。

TR:=MAX(MAX((HIGH-LOW),ABS(REF(CLOSE,1)-HIGH)),ABS(REF(CLOSE,1)-LOW));//真实波幅
ATR:=MA(TR,26); //求26个周期内真实波幅的简单移动平均
TC..INTPART((MONEYTOT*0.01/(UNIT*ATR)));//根据权益的1%计算下单手数
MTC..4*TC; //总的持仓头寸
HH:=HV(H,20);
LL:=LV(L,20);
CROSSUP(C,HH)&&ISLASTBK=0&&ISLASTSK=0&&BARPOS>=26,BK(TC);//最新价超过20周期的最高值，首次买入开仓，手数为TC手
CROSSDOWN(C,LL)&&ISLASTBK=0&&ISLASTSK=0,SK(TC); //最新价跌破20周期的最低值，首次卖出开仓，手数为TC手
C>=BKPRICE+0.5*ATR&&BKVOL<MTC&&ISLASTBK,BK(TC);//价格在上次开仓的基础上上涨0.5倍ATR，在手数不超过4倍TC的时候，买入加仓TC手
C<=SKPRICE-0.5*ATR&&SKVOL<MTC&&ISLASTSK,SK(TC);//价格在上次开仓的基础上下跌0.5倍ATR，在手数不超过4倍TC的时候，卖出加仓TC手
C<=(BKPRICE-2*ATR)&&BKVOL>0,SP(BKVOL);//最新价小于开仓价减去2倍的ATR，止损平仓
C>=(SKPRICE+2*ATR)&&SKVOL>0,BP(SKVOL); //最新价大于开仓价加上2倍的ATR，止损平仓
CROSSUP(H,HV(H,10))&&SKVOL>0,BP(SKVOL);//最高价上穿10周期最高价，平仓
CROSSDOWN(L,LV(L,10))&&BKVOL>0,SP(BKVOL); //最低价下穿10周期的最低价，平仓
TRADE_AGAIN(10);

```

## 只算当天数据编写示范

``` cpp
//该示范主要用海龟交易法则，演示“头寸计算，最大仓位控制等资金管理”的编写方法
//编写示范中，只对示范重点内容语句进行了注释，其他语句请自行翻译，或者咨询文华工作人员
//该模型仅仅用来示范演示使用，依此入市，风险自负。

TR:=MAX(MAX((HIGH-LOW),ABS(REF(CLOSE,1)-HIGH)),ABS(REF(CLOSE,1)-LOW));//真实波幅
ATR:=MA(TR,26); //求26个周期内真实波幅的简单移动平均
TC..INTPART((MONEYTOT*0.01/(UNIT*ATR)));//根据权益的1%计算下单手数
MTC..4*TC; //总的持仓头寸
HH:=HV(H,20);
LL:=LV(L,20);
CROSSUP(C,HH)&&ISLASTBK=0&&ISLASTSK=0&&BARPOS>=26,BK(TC);//最新价超过20周期的最高值，首次买入开仓，手数为TC手
CROSSDOWN(C,LL)&&ISLASTBK=0&&ISLASTSK=0,SK(TC); //最新价跌破20周期的最低值，首次卖出开仓，手数为TC手
C>=BKPRICE+0.5*ATR&&BKVOL<MTC&&ISLASTBK,BK(TC);//价格在上次开仓的基础上上涨0.5倍ATR，在手数不超过4倍TC的时候，买入加仓TC手
C<=SKPRICE-0.5*ATR&&SKVOL<MTC&&ISLASTSK,SK(TC);//价格在上次开仓的基础上下跌0.5倍ATR，在手数不超过4倍TC的时候，卖出加仓TC手
C<=(BKPRICE-2*ATR)&&BKVOL>0,SP(BKVOL);//最新价小于开仓价减去2倍的ATR，止损平仓
C>=(SKPRICE+2*ATR)&&SKVOL>0,BP(SKVOL); //最新价大于开仓价加上2倍的ATR，止损平仓
CROSSUP(H,HV(H,10))&&SKVOL>0,BP(SKVOL);//最高价上穿10周期最高价，平仓
CROSSDOWN(L,LV(L,10))&&BKVOL>0,SP(BKVOL); //最低价下穿10周期的最低价，平仓
TRADE_AGAIN(10);

```

## 日内限制交易次数示范

``` cpp
//该示范主要演示用DAYTRADE函数控制模型在分钟周期上只用当天数据进行运行。 
//编写示范中，只对示范重点内容语句进行了注释，其他语句请自行翻译，或者咨询文华工作人员。
//该模型仅仅用来示范演示使用，依此入市，风险自负。

DAYTRADE;//分钟周期，只用当日数据计算 
HH^^HV(H,20);
LL^^LV(L,20);//前20个周期的高低点，当天未满20个周期，则为空值。
CROSSUP(C,HH),BK;
CROSSDOWN(C,LL),SK;
C<BKPRICE-5*MINPRICE,SP;
C>SKPRICE+5*MINPRICE,BP;
CLOSEMINUTE<=1,CLOSEOUT;
AUTOFILTER;
```

## 下单委托价格编写示范

``` cpp
//该示范主要演示“下单委托价格”的编写方法
//编写示范中，只对示范重点内容语句进行了注释，其他语句请自行翻译，或者咨询文华工作人员
//该模型仅仅用来示范演示使用，依此入市，风险自负。

MID^^MA(CLOSE,26);
TMP2:=STD(CLOSE,26);
TOP^^MID+2*TMP2;
BOTTOM^^MID-2*TMP2;
CROSSUP(C,TOP),BK;
CROSSDOWN(C,MID),SP;
CROSSDOWN(C,BOTTOM),SK;
CROSSUP(C,MID),BP;
SETSIGPRICETYPE(BK,NEW_ORDER);//BK信号以信号发出时的最新价进行委托
SETSIGPRICETYPE(SK,NEW_ORDER);//SK信号以信号发出时的最新价进行委托
SETSIGPRICETYPE(BP,TRACING_ORDER);//BP信号根据连续追价的设置进行委托
SETSIGPRICETYPE(SP,TRACING_ORDER);//SP信号根据连续追价的设置进行委托
//其他下单价格委托方式，请参考SETSIGPRICETYPE的函数说明
AUTOFILTER;

```

## 信号执行方式编写示范

``` cpp
//该示范主要演示“信号执行方式”的编写方法
//编写示范中，只对示范重点内容语句进行了注释，其他语句请自行翻译，或者咨询文华工作人员
//该模型仅仅用来示范演示使用，依此入市，风险自负。

MA5^^MA(C,5);
MA10^^MA(C,10);
RSV:=(CLOSE-LLV(LOW,9))/(HHV(HIGH,9)-LLV(LOW,9))*100;
K..SMA(RSV,3,1);
D..SMA(K,3,1);
EVERY(MA5>MA10,3)&&CROSSUP(K,D),BK;
EVERY(MA5<MA10,3)&&CROSSDOWN(K,D),SK;
BARSBK>2&&C<=BKHIGH-20*MINPRICE,SP;
BARSSK>2&&C>=SKLOW+20*MINPRICE,BP;
CHECKSIG(BK,'B',5,'C',0,3);//设置BK信号的信号执行方式为：K线走完前5*3=15秒下单，不进行复核，每隔3秒计算一次信号。
CHECKSIG(SK,'B',5,'C',0,3);//设置SK信号的信号执行方式为：K线走完前5*3=15秒下单，不进行复核，每隔3秒计算一次信号。
CHECKSIG(SP,'A',0,'C',5,3);//设置SP信号的信号执行方式为：出信号立即下单，下单后5*3=15秒进行复核，每隔3秒计算一次信号。
CHECKSIG(BP,'A',0,'C',5,3);//设置BP信号的信号执行方式为：出信号立即下单，下单后5*3=15秒进行复核，每隔3秒计算一次信号。
//更多的信号执行方式，请参考CHECKSIG、CHECKSIG_MIN、MULTSIG、MULTSIG_MIN的函数说明
AUTOFILTER;


```

## 全程追踪止损编写示范

``` cpp
//该示范主要演示“全程追踪止损”的编写方法
//用户需要根据自己交易经验，补充完整开平仓条件，进行修改后再实际应用!!!
//该模型仅仅用来示范演示使用，依此入市，风险自负。

//追踪点差为SL,步长为S
A:=MINPRICE1;//取模组交易合约的最小变动价位
HH:=HHV(H,BARSBK+1);
LL:=LLV(L,BARSSK+1);
//以上取买开仓以来最高价；卖开仓以来最低价；
AA:=BKPRICE-SL*A+S*A*INTPART((HH-BKPRICE)/(S*A));
BB:=SKPRICE+SL*A-S*A*INTPART((SKPRICE-LL)/(S*A));
//以上取开仓后盈利的止损点差应该是多少
((C<=BKPRICE-SL*A)||C<=AA)&&BKPRICE>0,SP;
((C>=SKPRICE+SL*A)||C>=BB)&&SKPRICE>0,BP;
//开仓后亏损达到5个点差，平仓；
//开仓后盈利止损价跟随行情每3个点差向上（或向下）浮动一次，回调时触碰止损点位，平仓；
AUTOFILTER;
```

## 限价止损+追踪止赢编写示范

``` cpp
//该示范主要演示“限价止损+追踪止赢”的编写方法
//用户需要根据自己交易经验，补充完整开平仓条件，进行修改后再实际应用!!!
//该模型仅仅用来示范演示使用，依此入市，风险自负。

//止损点差为SL，止赢点差为TP，追踪点差为DTP
A:=MINPRICE1;//取模组交易合约的最小变动价位
HH:=HHV(H,BARSBK+1);//买开仓位置到现在最高价
LL:=LLV(L,BARSSK+1);//卖开仓位置到现在最低价
A1:=BKPRICE+TP*A;
A2:=A1+DTP*A;
A3:=A1-2*A;
A4:=HH-DTP*A;//以上为根据止赢点差计算多单追踪止赢位置
B1:=SKPRICE-TP*A;
B2:=B1-DTP*A;
B3:=B1+2*A;
B4:=LL+DTP*A;//以上为根据止赢点差计算空单追踪止赢位置
((C<=BKPRICE-SL*A)||(HH>=A1&&HH<=A2&&C<=A3)||(HH>A2&&C<=A4))&&BKPRICE>0,SP;
//最新价跌至开仓价下5个价位，多单止损；
//买开仓后最高价达到止赢点差（20个价位）但未达到追踪点差（23个价位，20+3）就开始回撤，则最新价回撤到止赢点差下2个价位，多单止赢；
//买开仓后最高价超出追踪点差，则最新价从最高价回撤3个价位，多单止赢；
((C>=SKPRICE+SL*A)||(LL<=B1&&LL>=B2&&C>=B3)||(LL<B2&&C>=B4))&&SKPRICE>0,BP;
//空单止赢止损与多单原理相同
AUTOFILTER;
```

## 限价止损+限价止赢编写示范

``` cpp
//该示范主要演示“限价止损+限价止赢”的编写方法
//用户需要根据自己交易经验，补充完整开平仓条件，进行修改后再实际应用!!!
//该模型仅仅用来示范演示使用，依此入市，风险自负。

//止损点差为SL,止赢点差为TP
A:=MINPRICE1;//取模组交易合约的最小变动价位
(C<=BKPRICE-SL*A||C>=BKPRICE+TP*A)&&BKPRICE>0,SP;//低于买开仓价10个点差，多头止损；高于买开仓价20个点差，多头止赢
(C>=SKPRICE+SL*A||C<=SKPRICE-TP*A)&&SKPRICE>0,BP;//高于卖开仓价10个点差，空头止损；低于卖开仓价20个点差，空头止赢
AUTOFILTER;
```

## 股票趋势模型编写示范

``` cpp
//该示范用均线组合演示“股票趋势模型”的编写方法
//编写示范中，对示范内容语句均进行了注释，如有疑问请咨询文华工作人员
//该模型仅仅用来示范演示使用，依此入市，风险自负。

MA5:MA(C,5);//定义5周期均线
MA10:MA(C,10);//定义10周期均线
MA20:MA(C,20);//定义20周期均线
MA120:MA(C,120);//定义120周期均线
C>MA120&&CROSSUP(MA5,MA10),BK;//价格大于120周期均线并且5周期均线上穿10周期均线，买入
CROSSDOWN(MA5,MA20),SP;//5周期均线下穿20周期均线，卖出
AUTOFILTER;//过滤模型
AUTOFINANCING;
//股票模型建议加入AUTOFINANCING函数。加入该函数的模型会根据股票价格自动计算资金，实现收益率准确计算。



```

## 股票T+0模型编写示范

``` cpp
//该示范用于演示“股票T+0模型”的编写方法
//编写示范中，对示范内容语句均进行了注释，如有疑问请咨询文华工作人员
//该模型仅仅用来示范演示使用，依此入市，风险自负。

HH:=HV(H,20);//定义前20周期高点
LL:=LV(L,10);//定义前10周期低点
MA5:=MA(C,5);//定义5周期均线
CROSSDOWN(C,LL),SK(500);//价格下穿前20周期低点，卖出500股
C>=L*1.02,SK(500);//价格大于当日最低价2%，卖出500股
C>=MA5&&L<=REF(C,1)*0.96,BP(SKVOL);//价格在5周期均线上并且最低价小于昨天收盘4%，买入开仓股数
CROSSUP(C,HH),BP(SKVOL);//价格上穿前20周期高点买入开仓股数
STOCKT0;//设置股票T+0交易
AUTOFINANCING;
//股票模型建议加入AUTOFINANCING函数。加入该函数的模型会根据股票价格自动计算资金，实现收益率准确计算。

```

## 股票信号控制方式编写示范

``` cpp
//股票模型“信号执行方式”使用PANZHONG_MIN函数控制，具体请在分类“信号控制函数”中查阅该函数说明
//编写示范中，对示范内容语句均进行了注释，如有疑问请咨询文华工作人员
//该模型仅仅用来示范演示使用，依此入市，风险自负。

MA60:=MA(C,60);
DIFF:EMA(CLOSE,SHORT) - EMA(CLOSE,LONG);//短周期与长周期的收盘价的指数平滑移动平均值做差。
DEA:EMA(DIFF,M);//DIFF的M个周期指数平滑移动平均
DIFF<0&&CROSS(DIFF,DEA),BK;//MACD在0轴下并且DIFF上穿DEA,买入。
CROSS(DEA,DIFF),SP;//DIFF下穿DEA,卖出。
PANZHONG_MIN(0);//买入和卖出指令，出信号立即下单，不复核
AUTOFILTER;
AUTOFINANCING;
//股票模型建议加入AUTOFINANCING函数。加入该函数的模型会根据股票价格自动计算资金，实现收益率准确计算。




```

# 公式条件单编写示范

## 跨指标开仓模型

``` cpp
//公式条件单模型中可以定义多个指标，同时满足条件后开仓（平仓）。
//公式条件单规则，请参考本界面‘帮助’菜单--公式条件单规则
//可点击本界面上方‘主图预览’按钮在主图上查看信号位置。
//该模型仅仅用来示范演示使用，依此入市，风险自负。

MID^^MA(CLOSE,26);//布林通道中轨
TMP2:=STD(CLOSE,26);
TOP^^MID+2*TMP2;//布林通道上轨
BOTTOM^^MID-2*TMP2;//布林通道下轨
RSV:=(CLOSE-LLV(LOW,9))/(HHV(HIGH,9)-LLV(LOW,9))*100;
K:=SMA(RSV,3,1);//KDJ中K值
D:=SMA(K,3,1);//KDJ中D值
J:=3*K-2*D;//KDJ中J值
C>TOP&&EVERY(J>80,2)&&C>O,BK;//布林上轨之上，如果两个周期内J值一直在超买区并收阳，开多仓
CONDITION_ORDER;//公式条件单关键字

```

## 通道突破开仓模型

``` cpp
//公式条件单模型中可以量化出各种平台、通道，突破后开仓（平仓）。
//公式条件单规则，请参考本界面‘帮助’菜单--公式条件单规则
//可点击本界面上方‘主图预览’按钮在主图上查看信号位置。
//该模型仅仅用来示范演示使用，依此入市，风险自负。

HH^^HV(H,20);//20周期高点
CROSSUP(C,HH),BK;//突破20周期高点，开多仓
CONDITION_ORDER;//公式条件单关键字


```

## K线组合开仓模型

``` cpp
//公式条件单模型中可以量化出各种K线形态，如吞没线、黄昏之星等形态开仓（平仓）。
//公式条件单规则，请参考本界面‘帮助’菜单--公式条件单规则
//可点击本界面上方‘主图预览’按钮在主图上查看信号位置。
//该模型仅仅用来示范演示使用，依此入市，风险自负。

REF(C>O,1)&&C<O&&C<REF(O,1)&&O>REF(C,1),SK;//吞没线，阴包阳，开空仓
CONDITION_ORDER;//公式条件单关键字
```

## 多次开仓模型

``` cpp
//公式条件单模型同一指令可以写多行，每个指令行都执行一次后，该公式条件单模型自动停止
//公式条件单规则，请参考本界面‘帮助’菜单--公式条件单规则
//可点击本界面上方‘主图预览’按钮在主图上查看信号位置。
//该模型仅仅用来示范演示使用，依此入市，风险自负。

MA10^^MA(C,10);//定义10周期均线
MA20^^MA(C,20);//定义20周期均线
MA30^^MA(C,30);//定义30周期均线
MA60^^MA(C,60);//定义60周期均线
CROSS(MA10,MA20),BK(2);//10周期均线上穿20周期均线，买开仓2手
CROSS(MA20,MA30),BK(1);//20周期均线上穿30周期均线，买开仓1手
CROSS(MA30,MA60),BK(1);//30周期均线上穿60周期均线，买开仓1手
CONDITION_ORDER;//公式条件单关键字
```

## 日内清仓模型

``` cpp
//该公式条件单模型用于对已有持仓进行日内清仓，规避隔夜持仓风险
//公式条件单规则，请参考本界面‘帮助’菜单--公式条件单规则
//可点击本界面上方‘主图预览’按钮在主图上查看信号位置。
//该模型仅仅用来示范演示使用，依此入市，风险自负。


CLOSEMINUTE<=1,CLOSEOUT;//收盘前1分钟，清仓
SETSIGPRICETYPE(CLOSEOUT,LIMIT_ORDER);//清仓指令用市价进行委托，确保成交
CONDITION_ORDER;//公式条件单关键字
```

## 反向突破止损模型

``` cpp
//行情在延续上涨时，突然出现反向突破，行情骤变时止损。
//固定点位止损止赢可以在下单软件中设置止损止赢单。
//公式条件单规则，请参考本界面‘帮助’菜单--公式条件单规则
//可点击本界面上方‘主图预览’按钮在主图上查看信号位置。
//该模型仅仅用来示范演示使用，依此入市，风险自负。

ST:=ABS(C-O);
ST>MA(ST,10)*2.5&&REF(EXIST(C>HV(H,5),3),1)&&C<O,SP;//价格突然反向突破卖平仓
CONDITION_ORDER;//公式条件单关键字
```

## 停损点止损模型

``` cpp
//指标止损中最实用就是SAR抛物式转向指标，亦称为停损点转向操作系统。
//固定点位止损止赢可以在下单软件中设置止损止赢单。
//公式条件单规则，请参考本界面‘帮助’菜单--公式条件单规则
//可点击本界面上方‘主图预览’按钮在主图上查看信号位置。
//该模型仅仅用来示范演示使用，依此入市，风险自负。

SARLINE:=ABS(SAR(4,0.02,0.2));
CROSSDOWN(SARLINE,C),SP;//SAR跌破价格卖平仓
CONDITION_ORDER;//公式条件单关键字


```

## 吊灯止赢模型

``` cpp
//计算出市场的真实波幅，从高点回撤一定的波幅即平仓。
//固定点位止损止赢可以在下单软件中设置止损止赢单。
//公式条件单规则，请参考本界面‘帮助’菜单--公式条件单规则
//可点击本界面上方‘主图预览’按钮在主图上查看信号位置。
//该模型仅仅用来示范演示使用，依此入市，风险自负。


TR:=MAX(MAX((HIGH-LOW),ABS(REF(CLOSE,1)-HIGH)),ABS(REF(CLOSE,1)-LOW));
ATR:=MA(TR,26),COLORYELLOW;//求真实波幅
CROSSDOWN(C,HV(H,10)-2*ATR),SP;//10个周期内，价格较高点下跌2倍ATR平仓
CONDITION_ORDER;//公式条件单关键字

```

## 时间止赢模型

``` cpp
//上涨一段时间后，在一定的时间内，价格上涨未达到预期，就出场观望
//固定点位止损止赢可以在下单软件中设置止损止赢单。
//公式条件单规则，请参考本界面‘帮助’菜单--公式条件单规则
//可点击本界面上方‘主图预览’按钮在主图上查看信号位置。
//该模型仅仅用来示范演示使用，依此入市，风险自负。


CROSS((C-LV(C,10))/LV(C,10)<0.015,0.5)&&C<MA(C,20),SP;//10周期内价格上涨未达到1.5%卖平仓
CONDITION_ORDER;//公式条件单关键字

```

## 反手模型

``` cpp
//该公式条件单模型演示反手操作的编写方法，反手条件为任意可判断趋势反转的条件。
//公式条件单规则，请参考本界面‘帮助’菜单--公式条件单规则
//可点击本界面上方‘主图预览’按钮在主图上查看信号位置。
//该模型仅仅用来示范演示使用，依此入市，风险自负。

MA5^^MA(C,5);//5周期均线
MA10^^MA(C,10);//10周期均线
MA20^^MA(C,20);//20周期均线
MA30^^MA(C,30);//30周期均线
CROSSDOWN(C,MA5)&&CROSSDOWN(L,MA10)&&REF(MA5>MA10&&MA10>MA20&&MA20>MA30,1),SPK;
//上个周期均线多头排列，当前周期5周期均线接连下穿10周期均线和20周期均线，平掉多头反手做空
CONDITION_ORDER;//公式条件单关键字

```

# 模型开发案例

## 动态突破

``` cpp
//该策略为趋势跟踪交易策略，适用较大周期，如日线。
//该模型仅用作模型开发案例，依此入市，风险自负。
////////////////////////////////////////////////////////
VARIABLE:LOOKBACKDAYS:=0;
TODAYVOLATILITY:=STD(CLOSE,30);//当日市场波动
YESTERDAYVOLATILITY:=REF(TODAYVOLATILITY,1);//昨日市场波动
DELTAVOLATILITY:=(TODAYVOLATILITY-YESTERDAYVOLATILITY)/TODAYVOLATILITY;//市场波动的变动率
LOOKBACKDAYS:=IF(BARPOS<=30,20,REF(LOOKBACKDAYS,1)*(1+DELTAVOLATILITY));//计算自适应参数
LOOKBACKDAYS:=ROUND(LOOKBACKDAYS,0);
LOOKBACKDAYS:=MIN(LOOKBACKDAYS,CEILINGAMT);
LOOKBACKDAYS:=MAX(LOOKBACKDAYS,FLOORAMT);
MIDLINE:=MA(CLOSE,LOOKBACKDAYS);
BAND:=STD(CLOSE,LOOKBACKDAYS); //自适应布林通道中轨
UPBAND:=MIDLINE+BOLBANDTRIG*BAND;//自适应布林通道上轨
DNBAND:=MIDLINE-BOLBANDTRIG*BAND;//自适应布林通道下轨
BUYPOINT:=HV(HIGH,LOOKBACKDAYS);//自适应唐奇安通道上轨
SELLPOINT:=LV(LOW,LOOKBACKDAYS);//自适应唐奇安通道下轨
LIQPOINT:=MIDLINE;//自适应出场均线
C>UPBAND&&C>BUYPOINT,BK;//当日价格大于布林通道上轨，并且当日价格大于唐奇安通道上轨，开多单
C<DNBAND&&C<SELLPOINT,SP;//持有多单时，当日价格小于布林通道下轨，并且当日价格小于唐奇安通道下轨，平多单
EVERY(C<LIQPOINT,3),SP;//持有多单时，价格小于自适应出场均线，平多单
C>UPBAND&&C>BUYPOINT,BP;//持有空单时，当日价格大于布林通道上轨，并且当日价格大于唐奇安通道上轨，平空单
C<DNBAND&&C<SELLPOINT,SK;//当日价格小于布林通道下轨，并且当日价格小于唐奇安通道下轨，开空单
EVERY(C>LIQPOINT,3),BP;//持有空单时，价格大于自适应出场均线，平空单
AUTOFILTER;
```

## 基于平移布林通道的系统

``` cpp
//该策略为趋势跟踪交易策略，适用较大周期，如日线。
//该模型仅用作模型开发案例，依此入市，风险自负。
////////////////////////////////////////////////////////
//平移BOLL通道计算
MID:=MA(C,N);//计算中轨       
TMP:=STD(C,M)*SDEV;//计算标准差
DISPTOP:=REF(MID,P)+TMP;//平移BOLL通道上轨
DISPBOTTOM:=REF(MID,P)-TMP;//平移BOLL通道下轨
//系统入场
H>=DISPTOP,BPK;
L<=DISPBOTTOM,SPK;
AUTOFILTER;
```

## 成交量加权动量交易系统

``` cpp
//该策略为趋势跟踪交易策略，适用较大周期，如日线。
//该模型仅用作模型开发案例，依此入市，风险自负。
////////////////////////////////////////////////////////
MOMVALUE:=C-REF(C,MOMLEN);
VWM:=EMA(VOL*MOMVALUE,AVGLEN);//定义成交量加权为VWM
TRUEHIGH1:=IF(HIGH>REF(C,1),HIGH,REF(C,1));
TRUELOW1:=IF(LOW<=REF(C,1),LOW,REF(C,1));
TRUERANGE1:=IF(ISLASTBAR,H-L,TRUEHIGH1-TRUELOW1);
AATR:=MA(TRUERANGE1,ATRLEN);//定义波动率					   			
BULLSETUP:=CROSSUP(VWM,0);//UWM上穿零轴定义多头势
BEARSETUP:=CROSSDOWN(VWM,0);//UWM下穿零轴定义空头势
LSETUP:=LOOP2(BARPOS=1||BULLSETUP,0,REF(LSETUP,1)+1);//多头势开始计数并记录当前价格
LEPRICE:=VALUEWHEN(BULLSETUP,C);
SSETUP:=LOOP2(BARPOS=1||BEARSETUP,0,REF(SSETUP,1)+1);//空头势开始计数并记录当前价格
SEPRICE:=VALUEWHEN(BEARSETUP,C);
//系统入场
//当多头势满足并且在SETUPLEN的BAR数目内,当价格达到入场价格后,做多
BARPOS>AVGLEN&&H>=REF(LEPRICE,1)+(ATRPCNT*REF(AATR,1))&&REF(LSETUP,1)<=SETUPLEN&&LSETUP>=1,BK;
//系统出场
BEARSETUP,SP;
//系统入场
//当空头势满足并且在SETUPLEN的BAR数目内,当价格达到入场价格后,做空
BARPOS>AVGLEN&&L<=REF(SEPRICE,1)-(ATRPCNT*REF(AATR,1))&&REF(SSETUP,1)<=SETUPLEN&&SSETUP>=1,SK;
//系统出场
BULLSETUP,BP;
AUTOFILTER;
	
```

## 金肯特纳

``` cpp
//该策略为趋势跟踪交易策略，适用较大周期，如日线。
//该模型仅用作模型开发案例，依此入市，风险自负。
////////////////////////////////////////////////////////
MOVAVGVAL:MA((HIGH+LOW+CLOSE)/3,AVGLENGTH);//三价均线
TRUEHIGH1:=IF(HIGH>REF(C,1),HIGH,REF(C,1));
TRUELOW1:=IF(LOW<=REF(C,1),LOW,REF(C,1));
TRUERANGE1:=IF(ISLASTBAR,H-L,TRUEHIGH1-TRUELOW1);
UPBAND:MOVAVGVAL+MA(TRUERANGE1,ATRLENGTH);
DNBAND:MOVAVGVAL-MA(TRUERANGE1,ATRLENGTH);//通道上下轨
LIQUIDPOINT:=MOVAVGVAL;//出场条件
MOVAVGVAL>REF(MOVAVGVAL,1)&&C>UPBAND,BK;//三价均线向上，并且价格上破通道上轨，开多单
C<LIQUIDPOINT,SP;//持有多单时，价格下破三价均线，平多单
MOVAVGVAL<REF(MOVAVGVAL,1)&&C<DNBAND,SK;//三价均线向下，并且价格下破通道下轨，开空单
C>LIQUIDPOINT,BP;//持有空单时，价格上破三价均线，平空单
AUTOFILTER;
```



