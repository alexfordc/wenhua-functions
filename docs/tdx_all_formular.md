## 技术指标公式

### MA  均线(系统)

``` pascal
M1	0.00	1000.00	5.00
M2	0.00	1000.00	10.00
M3	0.00	1000.00	20.00
M4	0.00	1000.00	60.00
```

``` pascal
MA1:MA(CLOSE,M1);
MA2:MA(CLOSE,M2);
MA3:MA(CLOSE,M3);
MA4:MA(CLOSE,M4);
```

``` pascal
1.股价高于平均线，视为强势；股价低于平均线，视为弱势
2.平均线向上涨升，具有助涨力道；平均线向下跌降，具有助跌力道；
3.二条以上平均线向上交叉时，买进；
4.二条以上平均线向下交叉时，卖出；
5.移动平均线的信号经常落后股价，若以EXPMA 、VMA 辅助，可以改善。

```

### MA2  均线(系统)

``` pascal
M1	0.00	1000.00	5.00
M2	0.00	1000.00	10.00
M3	0.00	1000.00	20.00
M4	0.00	1000.00	60.00
M5	0.00	1000.00	120.00
M6	0.00	1000.00	250.00
M7	0.00	1000.00	0.00
M8	0.00	1000.00	0.00
M9	0.00	1000.00	0.00
M10	0.00	1000.00	0.00
```

``` pascal
MA1:MA(CLOSE,M1);
MA2:MA(CLOSE,M2);
MA3:MA(CLOSE,M3);
MA4:MA(CLOSE,M4);
MA5:MA(CLOSE,M5);
MA6:MA(CLOSE,M6);
MA7:MA(CLOSE,M7);
MA8:MA(CLOSE,M8);
MA9:MA(CLOSE,M9);
MA10:MA(CLOSE,M10);
```

``` pascal
1.股价高于平均线，视为强势；股价低于平均线，视为弱势
2.平均线向上涨升，具有助涨力道；平均线向下跌降，具有助跌力道；
3.二条以上平均线向上交叉时，买进；
4.二条以上平均线向下交叉时，卖出；
5.移动平均线的信号经常落后股价，若以EXPMA 、VMA 辅助，可以改善。

```

### ABI  绝对广量指标(系统)

``` pascal
M	2.00	100.00	10.00
```

``` pascal
ABI:100*ABS(ADVANCE-DECLINE)/(ADVANCE+DECLINE);
MAABI:EMA(ABI,M);
```

``` pascal
1.ABI绝对广量主要用于扫瞄瞬间极端的多头或空头力道；
2.ABI值数据只会在0～100之间波动，数据越高代表市场立即转折的概率越大；ABI值高于95以上时，市场行情将极容易产生短期转折点；
3.越高的数据代表市场转向的机会越大；
4.随著上市公司家数递增，ABI 的极限数据须伴随修正；
5.本指标可设参考线,对ABI作了归一化处理以减少误差。

```

### ADL  腾落指标(系统)

``` pascal
M	2.00	60.00	7.00
```

``` pascal
ADL:SUM(ADVANCE-DECLINE,0);
MAADL:MA(ADL,M);
```

``` pascal
1.ADL与指数顶背离时，指数向下反转机会大；
2.ADL与指数底背离时，指数向上反转机会大；
3.ADL须与ADR 、OBOS等指标配合使用。

```

### ADR  涨跌比率(系统)

``` pascal
N	2.00	100.00	10.00
M	2.00	60.00	6.00
```

``` pascal
ADR:SUM(ADVANCE,N)/SUM(DECLINE,N);
MAADR:MA(ADR,M);
```

``` pascal
1.ADR一般常态分于0.5～1.5的间；
2.ADR>1.5 ，大盘回档机会大；
3.ADR<0.65，大盘反弹机会大；
4.ADR<0.3或0.5，容易形成底部。

```

### ARMS  阿姆氏指标(系统)

``` pascal
N	2.00	120.00	21.00
M	2.00	40.00	6.00
```

``` pascal
ARMS:EMA(ADVANCE/DECLINE,N);
MAARMS:MA(ARMS,M);
```

``` pascal
1.R＝上涨家数/下跌家数
2.ARMS＝R的N日异同移动平均
3.计算ARMS的M日简单移动平均
4.参数N一般设置为21日参数M一般设置为6日

  ARMS指标绝大多数时候是在低位徘徊，这时候对大盘的超买超卖有一定提示作
用，但这种提示只能说明股市在短时间的超买超卖情况，对大势的长期发展方向
的提示作用不大。
  ARMS指标突然升高，意味股市即将构筑底部。这个突然升高的具体数值没有硬
性规定，关键在于ARMS指标能否创出一段时间的新高。
  ARMS指标如果出现急剧增长，往往意味着股市将出现重大转变。这种急剧增长
是指ARMS指标迅速升高到10以上，其在历史中出现的次数不多，但往往能准确预
测股市的顶底。

```

### BTI  广量冲力指标(系统)

``` pascal
N	2.00	90.00	10.00
M	2.00	60.00	5.00
```

``` pascal
BTI:EMA(100*ADVANCE/(ADVANCE+DECLINE),N);
MABTI:MA(BTI,M);
```

``` pascal
1.62～65为超买区；
2.35～38为超卖区；
3.当BTI 产生极大的冲力时，为大多头来临的前兆；
4.本指标可设参考线。

```

### MCL  麦克连指标(系统)

``` pascal
N1	2.00	100.00	19.00
N2	2.00	200.00	39.00
```

``` pascal
DIF:=ADVANCE-DECLINE;
EMA1:=EMA(DIF,N1);
EMA2:=EMA(DIF,N2);
MCL:EMA1-EMA2;
MAMCL1:EMA1;
MAMCL2:EMA2;
```

``` pascal
1.+25～+35的间为超买区，曲线穿越此区后再度反转跌破+25，为卖出信号；
2.-25～-35的间为超卖区，曲线穿越此区后再度反转突破-25，为买进信号；
3.以0轴为中心，正值时，为多头市场；负值时，为空头市场；
4.本指标可设参考线。

```

## MSI  麦氏综合指标(系统)

### OBOS  超买超卖指标(系统)

``` pascal
N	2.00	100.00	10.00
M	2.00	60.00	6.00
```

``` pascal
OBOS:EMA(ADVANCE-DECLINE,N);
MAOBOS:MA(OBOS,M);
```

``` pascal
1.指标上升至+80时为超买，下降至-80时为超卖；
2.指标若超越+100或-100时，应等待其产生背离才可确认；
3.本指标应搭配ADR 、VR、BRAR等指标使用；
4.本指标可设参考线。

```

### STIX  指数平滑广量(系统)

``` pascal
M	2.00	60.00	6.00
```

``` pascal
TBR:100*ADVANCE/(ADVANCE+DECLINE);
MATBR:EMA(TBR,M);
```

``` pascal
1.常态行情时，STIX一般波动于45～56的间，强势行情波动于42～58之间；
2.指标上升至56～58间时，短线应卖出；
3.指标下降至42～45间时，短线应买进；
4.本指标可设参考线。

```

### CCI  商品路径指标(系统)

``` pascal
N	2.00	100.00	14.00
```

``` pascal
TYP:=(HIGH+LOW+CLOSE)/3;
CCI:(TYP-MA(TYP,N))/(0.015*AVEDEV(TYP,N));
```

``` pascal
1.CCI 为正值时，视为多头市场；为负值时，视为空头市场；
2.常态行情时，CCI 波动于±100 的间；强势行情，CCI 会超出±100 ；
3.CCI>100 时，买进，直到CCI<100 时，卖出；
4.CCI<-100 时，放空，直到CCI>-100 时，回补。

```

### KDJ  随机指标(系统)

``` pascal
N	2.00	90.00	9.00
M1	2.00	30.00	3.00
M2	2.00	30.00	3.00
```

``` pascal
RSV:=(CLOSE-LLV(LOW,N))/(HHV(HIGH,N)-LLV(LOW,N))*100;
K:SMA(RSV,M1,1);
D:SMA(K,M2,1);
J:3*K-2*D;
```

``` pascal
1.指标>80 时，回档机率大；指标<20时，反弹机率大；
2.K在20左右向上交叉D时，视为买进信号；
3.K在80左右向下交叉D时，视为卖出信号；
4.J>100 时，股价易反转下跌；J<0 时，股价易反转上涨；
5.KDJ 波动于50左右的任何信号，其作用不大。

```

## KDJ-TDX  随机指标-传统版(系统)

### MFI  资金流量指标(系统)

``` pascal
N	2.00	120.00	14.00
N2	2.00	60.00	6.00
```

``` pascal
TYP := (HIGH + LOW + CLOSE)/3;
V1:=SUM(IF(TYP>REF(TYP,1),TYP*VOL,0),N)/SUM(IF(TYP<REF(TYP,1),TYP*VOL,0),N);
MFI:100-(100/(1+V1));
```

``` pascal
1.MFI>80 为超买，当其回头向下跌破80 时，为短线卖出时机；
2.MFI<20 为超卖，当其回头向上突破20 时，为短线买进时机；
3.MFI>80，而产生背离现象时，视为卖出信号；
4.MFI<20，而产生背离现象时，视为买进信号。

```

### MTM  动量线(系统)

``` pascal
N	2.00	120.00	12.00
M	2.00	60.00	6.00
```

``` pascal
MTM:CLOSE-REF(CLOSE,N);
MTMMA:MA(MTM,M);
```

``` pascal
MTM线　:当日收盘价与N日前的收盘价的差；
MTMMA线:对上面的差值求N日移动平均；
参数：N 间隔天数，也是求移动平均的天数，一般取6
用法：
1.MTM从下向上突破MTMMA，买入信号；
2.MTM从上向下跌破MTMMA，卖出信号；
3.股价续创新高，而MTM未配合上升，意味上涨动力减弱；
4.股价续创新低，而MTM未配合下降，意味下跌动力减弱；
5.股价与MTM在低位同步上升，将有反弹行情；反之，从高位同步下降，将有回落走势。

```

### OSC  变动速率线(系统)

``` pascal
N	2.00	100.00	20.00
M	2.00	60.00	6.00
```

``` pascal
OSC:100*(CLOSE-MA(CLOSE,N));
MAOSC:EXPMEMA(OSC,M);
```

``` pascal
1.OSC 以100 为中轴线，OSC>100 为多头市场；OSC<100 为空头市场；
2.OSC 向上交叉其平均线时，买进；OSC 向下交叉其平均线时卖出；
3.OSC 在高水平或低水平与股价产生背离时，应注意股价随时有反转的可能；
4.OSC 的超买超卖界限值随个股不同而不同，使用者应自行调整

```

### ROC  变动率指标(系统)

``` pascal
N	2.00	120.00	12.00
M	2.00	60.00	6.00
```

``` pascal
ROC:100*(CLOSE-REF(CLOSE,N))/REF(CLOSE,N);
MAROC:MA(ROC,M);
```

``` pascal
1.本指标的超买超卖界限值随个股不同而不同，使用者应自行调整；
2.本指标的超买超卖范围，一般介于±6.5之间；
3.本指标用法请参考MTM 指标用法；
4.本指标可设参考线。

```

### RSI  相对强弱指标(系统)

``` pascal
N1	2.00	120.00	6.00
N2	2.00	250.00	12.00
N3	2.00	500.00	24.00
```

``` pascal
LC:=REF(CLOSE,1);
RSI1:SMA(MAX(CLOSE-LC,0),N1,1)/SMA(ABS(CLOSE-LC),N1,1)*100;
RSI2:SMA(MAX(CLOSE-LC,0),N2,1)/SMA(ABS(CLOSE-LC),N2,1)*100;
RSI3:SMA(MAX(CLOSE-LC,0),N3,1)/SMA(ABS(CLOSE-LC),N3,1)*100;

```

``` pascal
1.RSI>80 为超买，RSI<20 为超卖；
2.RSI 以50为中界线，大于50视为多头行情，小于50视为空头行情；
3.RSI 在80以上形成Ｍ头或头肩顶形态时，视为向下反转信号；
4.RSI 在20以下形成Ｗ底或头肩底形态时，视为向上反转信号；
5.RSI 向上突破其高点连线时，买进；RSI 向下跌破其低点连线时，卖出。

```

### KD  随机指标KD(系统)

``` pascal
N	2.00	100.00	9.00
M1	2.00	100.00	3.00
M2	2.00	100.00	3.00
```

``` pascal
RSV:=(CLOSE-LLV(LOW,N))/(HHV(HIGH,N)-LLV(LOW,N))*100;
K:SMA(RSV,M1,1);
D:SMA(K,M2,1);
```

### SKDJ  慢速随机指标(系统)

``` pascal
N	2.00	90.00	9.00
M	2.00	30.00	3.00
```

``` pascal
LOWV:=LLV(LOW,N);
HIGHV:=HHV(HIGH,N);
RSV:=EMA((CLOSE-LOWV)/(HIGHV-LOWV)*100,M);
K:EMA(RSV,M);
D:MA(K,M);
```

``` pascal
1.指标>80 时，回档机率大；指标<20 时，反弹机率大；
2.K在20左右向上交叉D时，视为买进信号； 
3.K在80左右向下交叉D时，视为卖出信号；
4.SKDJ波动于50左右的任何讯号，其作用不大。

```

### UDL  引力线(系统)

``` pascal
N1	2.00	20.00	3.00
N2	2.00	30.00	5.00
N3	2.00	60.00	10.00
N4	2.00	120.00	20.00
M	2.00	10.00	6.00
```

``` pascal
UDL:(MA(CLOSE,N1)+MA(CLOSE,N2)+MA(CLOSE,N3)+MA(CLOSE,N4))/4;
MAUDL:MA(UDL,M);
```

``` pascal
1.本指标的超买超卖界限值随个股不同而不同，使用者应自行调整；
2.使用时，可列出一年以上走势图，观察其常态性分布范围，然
  后用参考线设定其超买超卖范围。通常UDL 高于某个极限时，
  短期股价会下跌；UDL 低于某个极限时，短期股价会上涨；
3.本指标可设参考线。

```

### WR  威廉指标(系统)

``` pascal
N	2.00	100.00	10.00
N1	2.00	100.00	6.00
```

``` pascal
WR1:100*(HHV(HIGH,N)-CLOSE)/(HHV(HIGH,N)-LLV(LOW,N));
WR2:100*(HHV(HIGH,N1)-CLOSE)/(HHV(HIGH,N1)-LLV(LOW,N1));
```

``` pascal
1.WR波动于0 - 100，100置于顶部，0置于底部。
2.本指标以50为中轴线，高于50视为股价转强；低于50视为股价转弱
3.本指标高于20后再度向下跌破20，卖出；低于80后再度向上突破80，买进。
4.WR连续触底3 - 4次，股价向下反转机率大；连续触顶3 - 4次，股价向上反转机率大。

```

### LWR  LWR威廉指标(系统)

``` pascal
N	1.00	100.00	9.00
M1	2.00	40.00	3.00
M2	2.00	40.00	3.00
```

``` pascal
RSV:= (HHV(HIGH,N)-CLOSE)/(HHV(HIGH,N)-LLV(LOW,N))*100;
LWR1:SMA(RSV,M1,1);
LWR2:SMA(LWR1,M2,1);
```

### MARSI  相对强弱平均线(系统)

``` pascal
M1	2.00	100.00	10.00
M2	2.00	60.00	6.00
```

``` pascal
DIF:=CLOSE-REF(CLOSE,1);
VU:=IF(DIF>=0,DIF,0);
VD:=IF(DIF<0,-DIF,0);
MAU1:=MEMA(VU,M1);
MAD1:=MEMA(VD,M1);
MAU2:=MEMA(VU,M2);
MAD2:=MEMA(VD,M2);
RSI10:MA(100*MAU1/(MAU1+MAD1),M1);
RSI6:MA(100*MAU2/(MAU2+MAD2),M2);
```

``` pascal
1.RSI>20 为超买；RSI<20 为超卖；
2.RSI 以50为中界线，大于50视为多头行情，小于50视为空头行情；
3.RSI 在80以上形成Ｍ头或头肩顶形态时，视为向下反转信号；
4.RSI 在20以下形成Ｗ底或头肩底形态时，视为向上反转信号；
5.RSI 向上突破其高点连线时，买进；RSI 向下跌破其低点连线时，卖出。

```

### BIAS-QL  乖离率-传统版(系统)

``` pascal
N	2.00	250.00	6.00
M	2.00	250.00	6.00
```

``` pascal
BIAS :(CLOSE-MA(CLOSE,N))/MA(CLOSE,N)*100;
BIASMA :MA(BIAS,M);
```

### BIAS  乖离率(系统)

``` pascal
N1	2.00	250.00	6.00
N2	2.00	250.00	12.00
N3	2.00	250.00	24.00
```

``` pascal
BIAS1 :(CLOSE-MA(CLOSE,N1))/MA(CLOSE,N1)*100;
BIAS2 :(CLOSE-MA(CLOSE,N2))/MA(CLOSE,N2)*100;
BIAS3 :(CLOSE-MA(CLOSE,N3))/MA(CLOSE,N3)*100;
```

``` pascal
1.本指标的乖离极限值随个股不同而不同，使用者可利用参考线设定，固定其乖离范围；
2.当股价的正乖离扩大到一定极限时，股价会产生向下拉回的作用力；
3.当股价的负乖离扩大到一定极限时，股价会产生向上拉升的作用力；
4.本指标可设参考线。

```

### BIAS36  三六乖离(系统)

``` pascal
M	2.00	60.00	6.00
```

``` pascal
BIAS36:MA(CLOSE,3)-MA(CLOSE,6);
BIAS612:MA(CLOSE,6)-MA(CLOSE,12);
MABIAS:MA(BIAS36,M);
```

``` pascal
1.本指标的乖离极限值随个股不同而不同，使用者可利用参考线设定，固定其乖离范围。※一般6-12BIAS信号的可靠度比3-6BIAS佳；
2.当股价的正乖离扩大到一定极限时，股价会产生向下拉回的作用力；
3.当股价的负乖离扩大到一定极限时，股价会产生向上拉升的作用力；
4.本指标可设参考线。

```

## BB  布林极限(系统)

## WIDTH  极限宽(系统)

## ASI  振动升降指标(系统)

### CHO  佳庆指标(系统)

``` pascal
N1	2.00	60.00	10.00
N2	2.00	100.00	20.00
M	2.00	60.00	6.00
```

``` pascal
MID:=SUM(VOL*(2*CLOSE-HIGH-LOW)/(HIGH+LOW),0);
CHO:MA(MID,N1)-MA(MID,N2);
MACHO:MA(CHO,M);
```

``` pascal
1.CHO 曲线产生急促的「凸起」时，代表行情即将向上或向下反转；
2.股价>90 天平均线，CHO由负转正时，买进；
3.股价<90 天平均线，CHO由正转负时，卖出；
4.本指标也可设参考线，自定超买超卖的界限值；
5.本指标须配合OBOS、ENVELOPE同时使用。

```

### DMA  平均差(系统)

``` pascal
N1	2.00	60.00	10.00
N2	2.00	250.00	50.00
M	2.00	100.00	10.00
```

``` pascal
DIF:MA(CLOSE,N1)-MA(CLOSE,N2);
DIFMA:MA(DIF,M);
```

``` pascal
1.DMA 向上交叉其平均线时，买进；
2.DMA 向下交叉其平均线时，卖出；
3.DMA 的交叉信号比MACD、TRIX 略快；
4.DMA 与股价产生背离时的交叉信号，可信度较高；
5.DMA、MACD、TRIX 三者构成一组指标群，互相验证。

```

### DMI  趋向指标(系统)

``` pascal
N	2.00	90.00	14.00
M	2.00	60.00	6.00
```

``` pascal
MTR:=SUM(MAX(MAX(HIGH-LOW,ABS(HIGH-REF(CLOSE,1))),ABS(REF(CLOSE,1)-LOW)),N);
HD :=HIGH-REF(HIGH,1);
LD :=REF(LOW,1)-LOW;
DMP:=SUM(IF(HD>0&&HD>LD,HD,0),N);
DMM:=SUM(IF(LD>0&&LD>HD,LD,0),N);
PDI: DMP*100/MTR;
MDI: DMM*100/MTR;
ADX: MA(ABS(MDI-PDI)/(MDI+PDI)*100,M);
ADXR:(ADX+REF(ADX,M))/2;
```

``` pascal
用法：市场行情趋向明显时，指标效果理想。
PDI(上升方向线)    MDI(下降方向线)  ADX(趋向平均值)
1.PDI线从下向上突破MDI线，显示有新多头进场，为买进信号；
2.PDI线从上向下跌破MDI线，显示有新空头进场，为卖出信号；
3.ADX值持续高于前一日时，市场行情将维持原趋势；
4.ADX值递减，降到20以下，且横向行进时，市场气氛为盘整；
5.ADX值从上升倾向转为下降时，表明行情即将反转。
参数：N　统计天数； M  间隔天数，一般为14、6

```

### DPO  区间震荡线(系统)

``` pascal
N	2.00	90.00	20.00
M	2.00	60.00	6.00
```

``` pascal
DPO:CLOSE-REF(MA(CLOSE,N),N/2+1);
MADPO:MA(DPO,M);
```

``` pascal
1.DOP>0 ，表示目前处于多头市场；DOP<0 ，表示目前处于空头市场；
2.在0 轴上方设定一条超买线，当股价波动至超买线时，会形成短期高点；
3.在0 轴下方设定一条超卖线，当股价波动至超卖线时，会形成短期低点；
4.超买超卖的范围随个股不同而不同，使用者应自行调整；
5.本指标可设参考线。

```

### EMV  简易波动指标(系统)

``` pascal
N	2.00	90.00	14.00
M	2.00	60.00	9.00
```

``` pascal
VOLUME:=MA(VOL,N)/VOL;
MID:=100*(HIGH+LOW-REF(HIGH+LOW,1))/(HIGH+LOW);
EMV:MA(MID*VOLUME*(HIGH-LOW)/MA(HIGH-LOW,N),N);
MAEMV:MA(EMV,M);
```

``` pascal
1.EMV 由下往上穿越0 轴时，视为中期买进信号；
2.EMV 由上往下穿越0 轴时，视为中期卖出信号；
3.EMV 的平均线穿越0 轴，产生假信号的机会较少；
4.当ADX 低于±DI时，本指标失去效用；
5.须长期使用EMV 指标才能获得最佳利润。

```

### MACD  平滑异同平均(系统)

``` pascal
SHORT	2.00	200.00	12.00
LONG	2.00	200.00	26.00
MID	2.00	200.00	9.00
```

``` pascal
DIF:EMA(CLOSE,SHORT)-EMA(CLOSE,LONG);
DEA:EMA(DIF,MID);
MACD:(DIF-DEA)*2,COLORSTICK;
```

``` pascal
DIFF线　收盘价短期、长期指数平滑移动平均线间的差
DEA线　 DIFF线的M日指数平滑移动平均线
MACD线　DIFF线与DEA线的差，彩色柱状线
参数：SHORT(短期)、LONG(长期)、M 天数，一般为12、26、9
用法：
1.DIFF、DEA均为正，DIFF向上突破DEA，买入信号。
2.DIFF、DEA均为负，DIFF向下跌破DEA，卖出信号。
3.DEA线与K线发生背离，行情反转信号。
4.分析MACD柱状线，由红变绿(正变负)，卖出信号；由绿变红，买入信号

```

### VMACD  量平滑异同平均(系统)

``` pascal
SHORT	2.00	200.00	12.00
LONG	2.00	200.00	26.00
MID	2.00	200.00	9.00
```

``` pascal
DIF:EMA(VOL,SHORT)-EMA(VOL,LONG);
DEA:EMA(DIF,MID);
MACD:DIF-DEA,COLORSTICK;
```

### QACD  快速异同平均(系统)

``` pascal
N1	2.00	200.00	12.00
N2	2.00	200.00	26.00
M	2.00	200.00	9.00
```

``` pascal
DIF:EMA(CLOSE,N1)-EMA(CLOSE,N2);
MACD:EMA(DIF,M);
DDIF:DIF-MACD;
```

``` pascal
1.DIF 向上交叉MACD，买进；DIF 向下交叉MACD，卖出；
2.DIF 连续两次向下交叉MACD，将造成较大的跌幅；
3.DIF 连续两次向上交叉MACD，将造成较大的涨幅；
4.DIF 与股价形成背离时所产生的信号，可信度较高；
5.DMA、MACD、TRIX 三者构成一组指标群，互相验证。

```

### TRIX  三重指数平均线(系统)

``` pascal
N	2.00	100.00	12.00
M	2.00	100.00	9.00
```

``` pascal
MTR:=EMA(EMA(EMA(CLOSE,N),N),N);
TRIX:(MTR-REF(MTR,1))/REF(MTR,1)*100;
MATRIX:MA(TRIX,M) ;
```

``` pascal
1.TRIX由下往上交叉其平均线时，为长期买进信号；
2.TRIX由上往下交叉其平均线时，为长期卖出信号；
3.DMA、MACD、TRIX 三者构成一组指标群，互相验证。

```

### UOS  终极指标(系统)

``` pascal
N1	2.00	30.00	7.00
N2	2.00	60.00	14.00
N3	2.00	120.00	28.00
M	2.00	30.00	6.00
```

``` pascal
TH:=MAX(HIGH,REF(CLOSE,1));
TL:=MIN(LOW,REF(CLOSE,1));
ACC1:=SUM(CLOSE-TL,N1)/SUM(TH-TL,N1);
ACC2:=SUM(CLOSE-TL,N2)/SUM(TH-TL,N2);
ACC3:=SUM(CLOSE-TL,N3)/SUM(TH-TL,N3);
UOS:(ACC1*N2*N3+ACC2*N1*N3+ACC3*N1*N2)*100/(N1*N2+N1*N3+N2*N3);
MAUOS:EXPMEMA(UOS,M);
```

``` pascal
1.UOS 上升至50～70的间，而后向下跌破其Ｎ字曲线低点时，为短线卖点；
2.UOS 上升超过70以上，而后向下跌破70时，为中线卖点；
3.UOS 下跌至45以下，而后向上突破其Ｎ字曲线高点时，为短线买点；
4.UOS 下跌至35以下，产生一底比一底高的背离现象时，为底部特征；
5.以上各项数据会因个股不同而略有不同，请利用参考线自行修正。

```

### VPT  量价曲线(系统)

``` pascal
N	2.00	120.00	51.00
M	2.00	60.00	6.00
```

``` pascal
VPT:SUM(VOL*(CLOSE-REF(CLOSE,1))/REF(CLOSE,1),N);
MAVPT:MA(VPT,M);
```

``` pascal
1.VPT 由下往上穿越0 轴时，为买进信号；
2.VPT 由上往下穿越0 轴时，为卖出信号；
3.股价一顶比一顶高，VPT 一顶比一顶低时，暗示股价将反转下跌；
4.股价一底比一底低，VPT 一底比一底高时，暗示股价将反转上涨；
5.VPT 可搭配EMV 和WVAD指标使用效果更佳。

```

### WVAD  威廉变异离散量(系统)

``` pascal
N	2.00	120.00	24.00
M	2.00	60.00	6.00
```

``` pascal
WVAD:SUM((CLOSE-OPEN)/(HIGH-LOW)*VOL,N)/10000;
MAWVAD:MA(WVAD,M);
```

``` pascal
1.WVAD由下往上穿越0 轴时，视为长期买进信号；
2.WVAD由上往下穿越0 轴时，视为长期卖出信号； 
3.当ADX 低于±DI时，本指标失去效用；
4.长期使用WVAD指标才能获得最佳利润；
5.本指标可与EMV 指标搭配使用。

```

### BRAR  情绪指标(系统)

``` pascal
N	2.00	120.00	26.00
```

``` pascal
BR:SUM(MAX(0,HIGH-REF(CLOSE,1)),N)/SUM(MAX(0,REF(CLOSE,1)-LOW),N)*100;
AR:SUM(HIGH-OPEN,N)/SUM(OPEN-LOW,N)*100;
```

``` pascal
1.BR>400，暗示行情过热，应反向卖出；BR<40 ，行情将起死回生，应买进；
2.AR>180，能量耗尽，应卖出；AR<40 ，能量已累积爆发力，应买进；
3.BR 由300 以上的高点下跌至50以下的水平,低于AR 时,为绝佳买点；
4.BR、AR、CR、VR 四者合为一组指标群，须综合搭配使用。

```

### CR  带状能量线(系统)

``` pascal
N	2.00	100.00	26.00
M1	0.00	100.00	10.00
M2	0.00	100.00	20.00
M3	0.00	100.00	40.00
M4	0.00	100.00	62.00
```

``` pascal
MID:=REF(HIGH+LOW,1)/2;
CR:SUM(MAX(0,HIGH-MID),N)/SUM(MAX(0,MID-LOW),N)*100;
MA1:REF(MA(CR,M1),M1/2.5+1);
MA2:REF(MA(CR,M2),M2/2.5+1);
MA3:REF(MA(CR,M3),M3/2.5+1);
MA4:REF(MA(CR,M4),M4/2.5+1);
```

``` pascal
1.CR>400时，其10日平均线向下滑落，视为卖出信号；CR<40买进；
2.CR 由高点下滑至其四条平均线下方时，股价容易形成短期底部；
3.CR 由下往上连续突破其四条平均线时，为强势买进点；
4.CR 除了预测价格的外，最大的作用在于预测时间；
5.BR、AR、CR、VR 四者合为一组指标群，须综合搭配使用。

```

### MASS  梅斯线(系统)

``` pascal
N1	2.00	120.00	9.00
N2	2.00	120.00	25.00
M	2.00	120.00	6.00
```

``` pascal
MASS:SUM(MA(HIGH-LOW,N1)/MA(MA(HIGH-LOW,N1),N1),N2);
MAMASS:MA(MASS,M);
```

``` pascal
1.MASS>27 后，随后又跌破26.5，此时股价若呈上涨状态，则卖出；
2.MASS<27 后，随后又跌破26.5，此时股价若呈下跌状态，则买进；
3.MASS<20 的行情，不宜进行投资。

```

### PSY  心理线(系统)

``` pascal
N	2.00	100.00	12.00
M	2.00	100.00	6.00
```

``` pascal
PSY:COUNT(CLOSE>REF(CLOSE,1),N)/N*100;
PSYMA:MA(PSY,M);
```

``` pascal
1.PSY>75，形成Ｍ头时，股价容易遭遇压力；
2.PSY<25，形成Ｗ底时，股价容易获得支撑；
3.PSY 与VR 指标属一组指标群，须互相搭配使用。

```

### VR  成交量变异率(系统)

``` pascal
N	2.00	100.00	26.00
M	2.00	100.00	6.00
```

``` pascal
TH:=SUM(IF(CLOSE>REF(CLOSE,1),VOL,0),N);
TL:=SUM(IF(CLOSE<REF(CLOSE,1),VOL,0),N);
TQ:=SUM(IF(CLOSE=REF(CLOSE,1),VOL,0),N);
VR:100*(TH*2+TQ)/(TL*2+TQ);
MAVR:MA(VR,M);
```

``` pascal
1.VR>450，市场成交过热，应反向卖出；
2.VR<40 ，市场成交低迷，人心看淡的际，应反向买进；
3.VR 由低档直接上升至250，股价仍为遭受阻力，此为大行情的前兆；
4.VR 除了与PSY为同指标群外，尚须与BR、AR、CR同时搭配研判

```

### WAD  威廉多空力度线(系统)

``` pascal
M	2.00	120.00	30.00
```

``` pascal
MIDA:=CLOSE-MIN(REF(CLOSE,1),LOW);
MIDB:=IF(CLOSE<REF(CLOSE,1),CLOSE-MAX(REF(CLOSE,1),HIGH),0);
WAD:SUM(IF(CLOSE>REF(CLOSE,1),MIDA,MIDB),0);
MAWAD:MA(WAD,M);
```

``` pascal
1.股价一顶比一顶高，而WAD 一顶比一顶低，暗示头部即将形成；
2.股价一底比一底低，而WAD 一底比一底高，暗示底部即将形成；
3.WAD 与OBV、PVT、ADVOL、ADL同属一组指标群，使用时应综合研判。

```

### AMO  成交金额(系统)

``` pascal
M1	2.00	500.00	5.00
M2	2.00	500.00	10.00
```

``` pascal
AMOW:AMOUNT/10000.0,VOLSTICK;
AMO1:MA(AMOW,M1);
AMO2:MA(AMOW,M2);
```

``` pascal
1.成交金额大，代表交投热络，可界定为热门股；
2.底部起涨点出现大成交金额，代表攻击量；
3.头部地区出现大成交金额，代表出货量；
4.观察成交金额的变化，比观察成交手数更具意义，因为成交手数并未反应股价的涨跌的后所应支出的实际金额。 

```

### OBV  累积能量线(系统)

``` pascal
M	2.00	100.00	30.00
```

``` pascal
VA:=IF(CLOSE>REF(CLOSE,1),VOL,-VOL);
OBV:SUM(IF(CLOSE=REF(CLOSE,1),0,VA),0);
MAOBV:MA(OBV,M);
```

``` pascal
1.股价一顶比一顶高，而OBV 一顶比一顶低，暗示头部即将形成；
2.股价一底比一底低，而OBV 一底比一底高，暗示底部即将形成；
3.OBV 突破其Ｎ字形波动的高点次数达5 次时，为短线卖点；
4.OBV 跌破其Ｎ字形波动的低点次数达5 次时，为短线买点；
5.OBV 与ADVOL、PVT、WAD、ADL同属一组指标群，使用时应综合研判。

```

### VOL  成交量(系统)

``` pascal
M1	2.00	500.00	5.00
M2	2.00	500.00	10.00
```

``` pascal
VOLUME:VOL,VOLSTICK;
MAVOL1:MA(VOLUME,M1);
MAVOL2:MA(VOLUME,M2);
```

``` pascal
1.成交量大，代表交投热络，可界定为热门股；
2.底部起涨点出现大成交量(成交手数)，代表攻击量；
3.头部地区出现大成交量(成交手数)，代表出货量；
4.观察成交金额的变化，比观察成交手数更具意义，因为成交手数并未反应股价的涨跌的后所应支出的实际金额。 

```

### VOL-TDX  成交量(虚拟)(系统)

``` pascal
M1	2.00	500.00	5.00
M2	2.00	500.00	10.00
```

``` pascal
TOTAL:=IF(PERIOD=1,5,IF(PERIOD=2,15,IF(PERIOD=3,30,IF(PERIOD=4,60,IF(PERIOD=5,TOTALFZNUM,1)))));
MTIME:=MOD(FROMOPEN,TOTAL);
CTIME:=IF(MTIME<0.5,TOTAL,MTIME);
VVOL:IF((CURRBARSCOUNT=1 AND DYNAINFO(8)>1),VOL*(TOTAL+3)/(CTIME+3),DRAWNULL),NODRAW;
STICKLINE((CURRBARSCOUNT=1 AND DYNAINFO(8)>1),VVOL,0,-1,-1),COLOR00C0C0;
VOLUME:VOL,VOLSTICK;
MAVOL1:MA(VOLUME,M1);
MAVOL2:MA(VOLUME,M2);
```

``` pascal
对当天的最后一根日K线进行全天成交量预测,方便与以前的成交量进行对比

```

### AMO-TDX  成交金额(虚拟)(系统)

``` pascal
M1	2.00	500.00	5.00
M2	2.00	500.00	10.00
```

``` pascal
TOTAL:=IF(PERIOD=1,5,IF(PERIOD=2,15,IF(PERIOD=3,30,IF(PERIOD=4,60,IF(PERIOD=5,TOTALFZNUM,1)))));
MTIME:=MOD(FROMOPEN,TOTAL);
CTIME:=IF(MTIME<0.5,TOTAL,MTIME);
VAMO:IF((CURRBARSCOUNT=1 AND DYNAINFO(8)>1),AMOUNT/10000.0*TOTAL/CTIME,DRAWNULL),NODRAW;
STICKLINE((CURRBARSCOUNT=1 AND DYNAINFO(8)>1),VAMO,0,-1,-1),COLOR00C0C0;
AMOW:AMOUNT/10000.0,VOLSTICK;
AMO1:MA(AMOW,M1);
AMO2:MA(AMOW,M2);
```

### SHORTVOL  抛空量(适用于港股)(系统)

``` pascal
M	2.00	500.00	5.00
```

``` pascal
抛空量:HKSHORTVOL,VOLSTICK;
MACCL:MA(抛空量,M);
```

### CCL  持仓量(适用于期货)(系统)

``` pascal
M	2.00	500.00	5.00
```

``` pascal
持仓量:VOLINSTK;
MACCL:MA(持仓量,M);
```

### VRSI  相对强弱量(系统)

``` pascal
N1	2.00	100.00	6.00
N2	2.00	100.00	12.00
N3	2.00	100.00	24.00
```

``` pascal
LC:=REF(VOL,1);
RSI1:SMA(MAX(VOL-LC,0),N1,1)/SMA(ABS(VOL-LC),N1,1)*100;
RSI2:SMA(MAX(VOL-LC,0),N2,1)/SMA(ABS(VOL-LC),N2,1)*100;
RSI3:SMA(MAX(VOL-LC,0),N3,1)/SMA(ABS(VOL-LC),N3,1)*100;

```

``` pascal
1.VRSI>20 为超买；VRSI<20 为超卖；
2.VRSI 以50为中界线，大于50视为多头行情，小于50视为空头行情；
3.VRSI 在80以上形成Ｍ头或头肩顶形态时，视为向下反转信号；
4.VRSI 在20以下形成Ｗ底或头肩底形态时，视为向上反转信号；
5.VRSI 向上突破其高点连线时，买进；VRSI 向下跌破其低点连线时，卖出。

```

### ACD  升降线(系统)

``` pascal
M	2.00	100.00	20.00
```

``` pascal
LC:=REF(CLOSE,1);
DIF:=CLOSE-IF(CLOSE>LC,MIN(LOW,LC),MAX(HIGH,LC));
ACD:SUM(IF(CLOSE=LC,0,DIF),0);
MAACD:EXPMEMA(ACD,M);
```

``` pascal
升降线（Accumulation Distribution），是分析收盘价与最高、最低及涨跌的关系的指标。
1. ACD 线下降，而股价会上升时，为卖出信号；
2. ACD 线上升，而股价下降时，为买进信号。

```

### BBI  多空均线(系统)

``` pascal
M1	2.00	100.00	3.00
M2	2.00	100.00	6.00
M3	2.00	100.00	12.00
M4	2.00	100.00	24.00
```

``` pascal
BBI:(MA(CLOSE,M1)+MA(CLOSE,M2)+MA(CLOSE,M3)+MA(CLOSE,M4))/4;
```

``` pascal
1.股价位于BBI 上方，视为多头市场；
2.股价位于BBI 下方，视为空头市场。

```

### EXPMA  指数平均线(系统)

``` pascal
M1	2.00	500.00	12.00
M2	2.00	500.00	50.00
```

``` pascal
EXP1:EMA(CLOSE,M1);
EXP2:EMA(CLOSE,M2);
```

``` pascal
1.EXPMA 一般以观察12日和50日二条均线为主；
2.12日指数平均线向上交叉50日指数平均线时，买进；
3.12日指数平均线向下交叉50日指数平均线时，卖出；
4.EXPMA 是多种平均线计算方法的一；
5.EXPMA 配合MTM 指标使用，效果更佳。

```

### EXPMA_S  指数平均线-副图(系统)

``` pascal
M1	2.00	500.00	12.00
M2	2.00	500.00	50.00
```

``` pascal
EXP1:EMA(CLOSE,M1);
EXP2:EMA(CLOSE,M2);
```

### HMA  高价平均线(系统)

``` pascal
M1	2.00	500.00	6.00
M2	2.00	500.00	12.00
M3	2.00	500.00	30.00
M4	2.00	500.00	72.00
M5	2.00	500.00	144.00
```

``` pascal
HMA1:MA(HIGH,M1);
HMA2:MA(HIGH,M2);
HMA3:MA(HIGH,M3);
HMA4:MA(HIGH,M4);
HMA5:MA(HIGH,M5);
```

``` pascal
  一般移动平均线以收盘价为计算基础，高价平均线是以每日最高价为计算基础。目前市场上许多投资人将其运用在空头市场，认为它的压力效应比传统平均线更具参考价值。

```

### LMA  低价平均线(系统)

``` pascal
M1	2.00	500.00	6.00
M2	2.00	500.00	12.00
M3	2.00	500.00	30.00
M4	2.00	500.00	72.00
M5	2.00	500.00	144.00
```

``` pascal
LMA1:MA(LOW,M1);
LMA2:MA(LOW,M2);
LMA3:MA(LOW,M3);
LMA4:MA(LOW,M4);
LMA5:MA(LOW,M5);
```

``` pascal
  一般移动平均线以收盘价为计算基础，低价平均线是以每日最低价为计算基础。目前市场上许多投资人将其运用在多头市场，认为它的支撑效应比传统平均线更具参考价值。

```

### VMA  变异平均线(系统)

``` pascal
M1	2.00	500.00	6.00
M2	2.00	500.00	12.00
M3	2.00	500.00	30.00
M4	2.00	500.00	72.00
M5	2.00	500.00	144.00
```

``` pascal
VV:=(HIGH+OPEN+LOW+CLOSE)/4;
VMA1:MA(VV,M1);
VMA2:MA(VV,M2);
VMA3:MA(VV,M3);
VMA4:MA(VV,M4);
VMA5:MA(VV,M5);
```

``` pascal
1.股价高于平均线，视为强势；股价低于平均线，视为弱势；
2.平均线向上涨升，具有助涨力道；平均线向下跌降，具有助跌力道；
3.二条以上平均线向上交叉时，买进；
4.二条以上平均线向下交叉时，卖出；
5.VMA 比一般平均线的敏感度更高，消除了部份平均线落后的缺陷。

```

### PCNT  幅度比(系统)

``` pascal
M	2.00	250.00	5.00
```

``` pascal
PCNT:(CLOSE-REF(CLOSE,1))/CLOSE*100;
MAPCNT:EXPMEMA(PCNT,M);
```

``` pascal
1.PCNT 重视价格的涨跌幅度，排除观察涨跌跳动值；
2.较高的PCNT 值，表示该股波动幅度大；
3.较低的PCNT 值，表示该股波动幅度小。

```

## BOLL-M  布林线-传统版(系统)

### BOLL  布林线(系统)

``` pascal
M	2.00	999.00	20.00
```

``` pascal
BOLL:MA(CLOSE,M);
UB:BOLL+2*STD(CLOSE,M);
LB:BOLL-2*STD(CLOSE,M);
```

``` pascal
1.股价上升穿越布林线上限时，回档机率大；
2.股价下跌穿越布林线下限时，反弹机率大；
3.布林线震动波带变窄时，表示变盘在即；
4.BOLL须配合BB 、WIDTH 使用；

```

### XT  箱体(系统)

``` pascal
N	3.00	30.00	10.00
```

``` pascal
【箱顶】:PEAK(CLOSE,N,1)*0.98;
【箱底】:TROUGH(CLOSE,N,1)*1.02;
【箱高】:100*(【箱顶】-【箱底】)/【箱底】,NODRAW;
```

``` pascal
股票箱体买卖法的具体操作是：投资者将股价每波动
的高点连成直线，将这条线添为压力线,将股价每次
波动的低点连成直线，称这条线为支撑线。压力线相
当于股票箱体的顶。支撑线也就相当于股票箱体的底
，当股价上升到压力线时，投资者就卖出股票，而当
股价下跌到支撑线时，投资者就进行相应的补进。股
票箱体买卖法是根据过去的经验和判断所进行的投资
操作。在特定的情况下，股价也会突破压力线或支撑
线，即股价上升或下跌到另一个股票箱体中，在这种
情况下，投资者就要寻找新的箱体,在新的箱体尚未
被确认之前，投资者最好不要轻易操作。以免被套
牢而受损。

```

### JAX  济安线(系统)

``` pascal
N	2.00	100.00	30.00
```

``` pascal
AA:=ABS((2*CLOSE+HIGH+LOW)/4-MA(CLOSE,N))/MA(CLOSE,N);
济安线:DMA((2*CLOSE+LOW+HIGH)/4,AA),LINETHICK3,COLORMAGENTA;
CC:=(CLOSE/济安线);
MA1:=MA(CC*(2*CLOSE+HIGH+LOW)/4,3);
MAAA:=((MA1-济安线)/济安线)/3;
TMP:=MA1-MAAA*MA1;
J:IF(TMP<=济安线,济安线,DRAWNULL),LINETHICK3,COLORCYAN;
A:TMP,LINETHICK2,COLORYELLOW;
X:IF(TMP<=济安线,TMP,DRAWNULL),LINETHICK2,COLORGREEN;
```

``` pascal
随行情自动调整参数，在济安线上面做多，重心价低于济安线做空。


```

### PBX  瀑布线(系统)

``` pascal
M1	3.00	10.00	4.00
M2	3.00	20.00	6.00
M3	3.00	30.00	9.00
M4	3.00	40.00	13.00
M5	3.00	50.00	18.00
M6	3.00	60.00	24.00
```

``` pascal
PBX1:(EMA(CLOSE,M1)+MA(CLOSE,M1*2)+MA(CLOSE,M1*4))/3;
PBX2:(EMA(CLOSE,M2)+MA(CLOSE,M2*2)+MA(CLOSE,M2*4))/3;
PBX3:(EMA(CLOSE,M3)+MA(CLOSE,M3*2)+MA(CLOSE,M3*4))/3;
PBX4:(EMA(CLOSE,M4)+MA(CLOSE,M4*2)+MA(CLOSE,M4*4))/3;
PBX5:(EMA(CLOSE,M5)+MA(CLOSE,M5*2)+MA(CLOSE,M5*4))/3;
PBX6:(EMA(CLOSE,M6)+MA(CLOSE,M6*2)+MA(CLOSE,M6*4))/3;
```

``` pascal
1.股价上升穿越轨道线上限时，回档机率大；
2.股价下跌穿越轨道线下限时，反弹机率大；
3.股价波动于轨道线内时，代表常态行情，此时，超买超卖指标可发挥效用；
4.股价波动于轨道线外时，代表脱轨行情，此时，应使用趋势型指标。

```

### ENE  轨道线(系统)

``` pascal
N	2.00	120.00	25.00
M1	2.00	120.00	6.00
M2	2.00	120.00	6.00
```

``` pascal
UPPER:(1+M1/100)*MA(CLOSE,N);
LOWER:(1-M2/100)*MA(CLOSE,N);
ENE:(UPPER+LOWER)/2;
```

``` pascal
1.股价上升穿越轨道线上限时，回档机率大；
2.股价下跌穿越轨道线下限时，反弹机率大；
3.股价波动于轨道线内时，代表常态行情，此时，超买超卖指标可发挥效用；
4.股价波动于轨道线外时，代表脱轨行情，此时，应使用趋势型指标。

```

### MIKE  麦克支撑压力(系统)

``` pascal
N	2.00	120.00	10.00
```

``` pascal
HLC:=REF(MA((HIGH+LOW+CLOSE)/3,N),1);
HV:=EMA(HHV(HIGH,N),3);
LV:=EMA(LLV(LOW,N),3);
STOR:EMA(2*HV-LV,3);
MIDR:EMA(HLC+HV-LV,3);
WEKR:EMA(HLC*2-LV,3);
WEKS:EMA(HLC*2-HV,3);
MIDS:EMA(HLC-HV+LV,3);
STOS:EMA(2*LV-HV,3);
```

``` pascal
1.MIKE指标共有六条曲线，上方三条压力线，下方三条支撑线；
2.当股价往压力线方向涨升时，其下方支撑线不具参考价值；
3.当股价往支撑线方向下跌时，其上方压力线不具参考价值；

```

## SAR  抛物线指标(系统)

## TDXWAVE  通达信趋势浪(系统)

## VTY  价格变异率(系统)

## ZXNH  直线拟合(系统)

### ZX  重心线(系统)

``` pascal
AV:0.01*AMOUNT/VOL;
```

``` pascal
重心线指标，重心线是由重心价连接而成的曲线，反映历史平均价位，
对于指数计算公式为:
  ZX = 成交金额/成交量。
对个股而言:
         最高指数＋最低指数＋收盘指数
  ZX ＝ ━━━━━━━━━━━━━━━
                      3
类似于不加权平均指数。

```

### AMV  成本价均线(系统)

``` pascal
M1	2.00	120.00	5.00
M2	2.00	120.00	13.00
M3	2.00	120.00	34.00
M4	2.00	250.00	60.00
```

``` pascal
AMOV:=VOL*(OPEN+CLOSE)/2;
AMV1:SUM(AMOV,M1)/SUM(VOL,M1);
AMV2:SUM(AMOV,M2)/SUM(VOL,M2);
AMV3:SUM(AMOV,M3)/SUM(VOL,M3);
AMV4:SUM(AMOV,M4)/SUM(VOL,M4);
```

``` pascal
成本价均线不同于一般移动平均线系统，成本价均线系
统首次将成交量引入均线系统，充分提高均线系统的可
靠性。同样对于成本价均线可以使用月均线系统(5,10,
20,250)和季均线系统(20,40,60,250),另外成本价均线
还可以使用自身特有的均线系统(5,13,34,250),称为市
场平均建仓成本均线，简称成本价均线。在四个均线中
参数为250的均线为年度均线,为行情支撑均线。成本均
线不容易造成虚假信号或骗线，比如某日股价无量暴涨，
移动均线会大幅拉升，但成本均线却不会大幅上升，因
为在无量的情况下市场持仓成本不会有太大的变化。依
据均线理论，当短期均线站在长期均线之上时叫多头排
列，反之就叫空头排列。短期均线上穿长期均线叫金叉，
短期均线下穿长期均线叫死叉。均线的多头排列是牛市
的标志，空头排列是熊市的标志。均线系统一直是市场
广泛认可的简单而可靠的分析指标，其使用要点是尽量
做多头排列的股票，回避空头排列的股票。34日成本线
是市场牛熊的重要的分水岭。一旦股价跌破34日成本线，
则常常是最后的出逃机会。

```

## PAV  筹码引力(系统)

## PAVE  强筹码引力(系统)

## MCST  市场成本(系统)

## NVI  负成交量(系统)

## PVI  正成交量(系统)

## SSRP  筹码峰(系统)

### HSL  换手线(系统)

``` pascal
N	2.00	120.00	5.00
```

``` pascal
HSL:IF((SETCODE==0||SETCODE==1),100*VOL,VOL)/(FINANCE(7)/100);
MAHSL:MA(HSL,N);
```

``` pascal
换手线是根据换手率绘制的曲线，使对于成交量的研判
不受股本变动的影响，更增加了成交量具有可比性。

```

### HSCOL  换手柱(系统)

``` pascal
N	2.00	120.00	5.00
```

``` pascal
HSCOL:IF((SETCODE==0||SETCODE==1),100*VOL,VOL)/(FINANCE(7)/100),VOLSTICK;
MAHSL:MA(HSCOL,N);
```

### DBQR  对比强弱(需下载日线)(系统)

``` pascal
N	2.00	120.00	5.00
M1	2.00	120.00	10.00
M2	2.00	120.00	20.00
M3	2.00	250.00	60.00
```

``` pascal
ZS:(INDEXC-REF(INDEXC,N))/REF(INDEXC,N);
GG:(CLOSE-REF(CLOSE,N))/REF(CLOSE,N);
MADBQR1:MA(GG,M1);
MADBQR2:MA(GG,M2);
MADBQR3:MA(GG,M3);
```

``` pascal
对比强弱指标包含有两条指标线,一条是对应指数的强弱
线。另外一条是个股的强弱线。当个股强弱线与指数强弱
线发生金叉时，表明个股开始强过大盘，是买入时机。
当个股强弱线与指数强弱线发生死叉时，表明个股开始弱
于大盘，是卖出时机。对比强弱指标是一个短线指标。

注意：此指标使用到了大盘的数据，所以需要下载完整的
日线数据,否则显示可能不正确

```

### DBQRV  对比强弱量(需下载日线)(系统)

``` pascal
N	2.00	120.00	5.00
```

``` pascal
ZS:(INDEXV-REF(INDEXV,N))/REF(INDEXV,N);
GG:(VOL-REF(VOL,N))/REF(VOL,N);
```

``` pascal
对比强弱量指标包含有两条指标线,一条是对应指数量的
强弱线。另外一条是个股成交量的强弱线。当个股强弱线
与指数强弱线发生金叉时，表明个股成交活跃过大盘。当
个股强弱线与指数强弱线发生死叉时，表明个股活跃度开
始弱于大盘。对比强弱量指标也是一个短线指标。

注意：此指标使用到了大盘的数据，所以需要下载完整的
日线数据,否则显示可能不正确

```

### JS  加速线(系统)

``` pascal
N	2.00	100.00	5.00
M1	2.00	100.00	5.00
M2	2.00	100.00	10.00
M3	2.00	100.00	20.00
```

``` pascal
JS:100*(CLOSE-REF(CLOSE,N))/(N*REF(CLOSE,N));
MAJS1:MA(JS,M1);
MAJS2:MA(JS,M2);
MAJS3:MA(JS,M3);
```

``` pascal
加速线指标是衡量股价涨速的工具,加速线指标上升表明
股价上升动力增加,加速线指标下降表明股价下降压力增加。
加速线适用于DMI表明趋势明显时(DMI.ADX大于20)使用:
1.如果加速线在0值附近形成平台，则表明既不是最好的
  买入时机也不是最好的卖入时机；
2.在加速线发生金叉后,均线形成底部是买入时机。
3.在加速线发生死叉后,均线形成顶部是卖出时机。

```

### DBLB  对比量比(需下载日线)(系统)

``` pascal
N	2.00	100.00	5.00
M	2.00	100.00	5.00
```

``` pascal
GG:=VOL/SUM(REF(VOL,1),N);
ZS:=INDEXV/SUM(REF(INDEXV,1),N);
DBLB:GG/ZS;
MADBLB:MA(DBLB,M);
```

``` pascal
对比量比指标用于用于测度成交量放大程度或萎缩程度
的指标。对比量比值越大，说明成交量较前期成交量放
大程度越大，对比量比值越小，说明成交量较前期成交
量萎缩程度越大，一般认为:
1.对比量比大于20可以认为成交量极度放大；
2.对比量比大于3,可以认为成交量显著放大；
3.对比量比小于0.2,可以认为成交量极度萎缩；
4.对比量比小于0.4,可以认为成交量显著萎缩。

```

### BBIBOLL  多空布林线(系统)

``` pascal
N	2.00	100.00	11.00
M	2.00	100.00	6.00
```

``` pascal
CV:=CLOSE;
BBIBOLL:(MA(CV,3)+MA(CV,6)+MA(CV,12)+MA(CV,24))/4;
UPR:BBIBOLL+M*STD(BBIBOLL,N);
DWN:BBIBOLL-M*STD(BBIBOLL,N);
```

``` pascal
BBI算法：
3日平均价加6日平均价加12日平均价加24日平均价，其和除以四。
用法：
1.为BBI与BOLL的迭加；
2.高价区收盘价跌破BBI线，卖出信号；
3.低价区收盘价突破BBI线，买入信号；
4.BBI线向上，股价在BBI线之上，多头势强；
5.BBI线向下，股价在BBI线之下，空头势强。

```

### ALLIGAT  鳄鱼线(系统)

``` pascal
NN:=(H+L)/2;
上唇:REF(MA(NN,5),3),COLOR40FF40;
牙齿:REF(MA(NN,8),5),COLOR0000C0;
下颚:REF(MA(NN,13),8),COLORFF4040;
```

``` pascal
鳄鱼线是运用分形几何学和非线性动力学的一组平均线（实际上就是一种比较特别的均线）。它分为蓝、红、绿三条。
蓝线被称为鳄鱼的颚部，红线被称为鳄鱼的牙齿，绿色被称为鳄鱼的唇吻。
它们的构造方法如下：
    颚部——13根价格线的平滑移动均线，并将数值向未来方向移动8根价格线；
    牙齿——8根价格线的平滑移动平均线，并将数值向未来方向移动5根价格线；
    唇吻——5根价格线的平滑移动均线，并将数值向未来方向移动3根价格线。
鳄鱼线的基本使用方法是：
    当颚部、牙齿、唇吻纠缠在一起时，我们便进入了观望期（鳄鱼休息了）
    当唇吻(绿）在牙齿（红）以上，牙齿在颚部（蓝）以上时，我们便进入了多头市场（颚鱼要开始吃牛肉了）
    当唇吻在牙齿以下，牙齿在颚部以下时，我便进入了空头市场（鳄鱼要开始吃熊肉了）

```

### ACCER  幅度涨速(系统)

``` pascal
N	2.00	100.00	8.00
```

``` pascal
ACCER:SLOPE(CLOSE,N)/CLOSE;
```

``` pascal
幅度涨速
算法：
先求出斜率，再对其价格进行归一

```

### CYD  承接因子(系统)

``` pascal
N	2.00	100.00	21.00
```

``` pascal
CYDS:WINNER(CLOSE)/(VOL/CAPITAL);
CYDN:WINNER(CLOSE)/MA(VOL/CAPITAL,N);
```

``` pascal
1.CYD称为承接因子指标，其市场含义是以今天的成交量承接所有获利盘需要的天数;
2.CYD可以反映市场上持股者的信心。 CYD大，说明以较小的成交量就可以维持较多的获利盘，说明市场上持股者的信心较强；反之CYD小，或者由于成交量大或者由于获利盘小，都反映了持股者信心不足;
3.可以用CYD来寻找市场大盘信心崩溃的点，当CYD极低时，说明市场投资人信心极低，市场信心崩溃，根据相反原理，此时就是大盘的底了，是中线炒底的机会。
4.可以用CYD寻找市场中个股信心最强的股票。如果在某一天CYD很大，显示这只股票的持股者信心特强，则这只股票很可能有强庄在其中，下面就有迅猛拉抬的可能。
5.股价在筹码密集区下方和密集区内,CYD越低越好,说明市场承接市场抛盘能力加大。
6.股价在筹码密集区的上方，尤其是已经进入拉升阶段，CYD越高越好，说明主力的获利盘没有散户承接，主力不能出货。如CYD突然走低，小心主力派发。
7.零号指数CYD如果低于5是绝对中线底部信号，大盘将在5天内见底反转。

```

### CYE  市场趋势(系统)

``` pascal
MAL:=MA(CLOSE,5);
MAS:=MA(MA(CLOSE,20),5);
CYEL:(MAL-REF(MAL,1))/REF(MAL,1)*100;
CYES:(MAS-REF(MAS,1))/REF(MAS,1)*100;
```

``` pascal
1. CYE指标又叫趋势指标,是计算机模拟人的感觉用数值分析的方法对即日的K线进行一次拟合和趋势的判断;
2.CYE以 0轴为界，其上为上升趋势,否则为下降趋势.

```

### CYR  市场强弱(系统)

``` pascal
N	2.00	100.00	13.00
M	2.00	100.00	5.00
```

``` pascal
DIVE:=0.01*EMA(AMOUNT,N)/EMA(VOL,N);
CYR:(DIVE/REF(DIVE,1)-1)*100;
MACYR:MA(CYR,M);
```

``` pascal
1.CYR是成本均线派生出的指标,是13日成本均线的升降幅度;
2.使用CYR可以对股票的强弱进行排序,找出其中的强势和弱势股票。

```

### CYF  市场能量(系统)

``` pascal
N	2.00	100.00	21.00
```

``` pascal
CYF:100-100/(1+EMA(HSL,N));
```

``` pascal
1.CYF反映了市场公众的状态和追涨热情,又称市场能量指标;
2.使用CYF判断股票的活跃程度, CYF小于10的股票是冷门股，CYF在20到40之间是活跃股，CYF大于50是热门股;
3.CYF与股价顶背离时,易形成反转.

```

### FSL  分水岭(系统)

``` pascal
SWL:(EMA(CLOSE,5)*7+EMA(CLOSE,10)*3)/10;
SWS:DMA(EMA(CLOSE,12),MAX(1,100*(SUM(VOL,5)/(3*CAPITAL))));
```

``` pascal
股价在分水岭之上为强势,反之为弱势.

```

### ADTM  动态买卖气指标(系统)

``` pascal
N	2.00	100.00	23.00
M	2.00	100.00	8.00
```

``` pascal
DTM:=IF(OPEN<=REF(OPEN,1),0,MAX((HIGH-OPEN),(OPEN-REF(OPEN,1))));
DBM:=IF(OPEN>=REF(OPEN,1),0,MAX((OPEN-LOW),(OPEN-REF(OPEN,1))));
STM:=SUM(DTM,N);
SBM:=SUM(DBM,N);
ADTM:IF(STM>SBM,(STM-SBM)/STM,IF(STM=SBM,0,(STM-SBM)/SBM));
MAADTM:MA(ADTM,M);
```

``` pascal
1.该指标在+1到-1之间波动;
2.低于-0.5时为很好的买入点,高于+0.5时需注意风险.

```

### ATR  真实波幅(系统)

``` pascal
N	2.00	300.00	14.00
```

``` pascal
MTR:MAX(MAX((HIGH-LOW),ABS(REF(CLOSE,1)-HIGH)),ABS(REF(CLOSE,1)-LOW));
ATR:MA(MTR,N);
```

``` pascal
算法：今日振幅、今日最高与昨收差价、今日最低与昨收差价中的最大值，为真实波幅，求真实波幅的N日移动平均
参数：N　天数，一般取14

```

### DKX  多空线(系统)

``` pascal
M	2.00	250.00	10.00
```

``` pascal
MID:=(3*CLOSE+LOW+OPEN+HIGH)/6;
DKX:(20*MID+19*REF(MID,1)+18*REF(MID,2)+17*REF(MID,3)+
16*REF(MID,4)+15*REF(MID,5)+14*REF(MID,6)+
13*REF(MID,7)+12*REF(MID,8)+11*REF(MID,9)+
10*REF(MID,10)+9*REF(MID,11)+8*REF(MID,12)+
7*REF(MID,13)+6*REF(MID,14)+5*REF(MID,15)+
4*REF(MID,16)+3*REF(MID,17)+2*REF(MID,18)+REF(MID,20))/210;
MADKX:MA(DKX,M);
```

``` pascal
1、当多空线上穿其均线时为买入信号;
2、当多空线下穿其均线时为卖出信号。

```

### TAPI  加权指数成交值(需下载日线)(系统)

``` pascal
M	2.00	200.00	6.00
```

``` pascal
TAPI:AMOUNT/INDEXC;
MATAIP:MA(TAPI,M);
```

``` pascal
1.先界定TAPI长期以来经常性的高低极限值，当TAPI触及顶端极
  限时，股价可能形成头部；当TAPI触及底端极限时，股价可能
  形成底部；
2.行情上涨，TAPI应伴随上涨；若不升反跌，则近期内将面临回档；
3.先前大盘量缩下跌，当其回升时，TAPI值却持续下跌，可视为买入信号。

注意：此指标使用到了大盘的数据，所以需要下载完整的
日线数据,否则显示可能不正确

```

### PUCU  逆时钟曲线(系统)

``` pascal
N	2.00	200.00	24.00
```

``` pascal
PU:MA(CLOSE,N);
CU:MA(VOL,N);
```

``` pascal
1.图表的曲线上有一个箭头，该处代表目前价量的位置；
2.曲线由绿变成红色时，视为买进信号；
3.曲线由红变成绿色时，视为卖出信号。

```

### XS  薛斯通道(系统)

``` pascal
N	2.00	120.00	13.00
```

``` pascal
VAR2:=CLOSE*VOL;
VAR3:=EMA((EMA(VAR2,3)/EMA(VOL,3)+EMA(VAR2,6)/EMA(VOL,6)+EMA(VAR2,12)/EMA(VOL,12)+EMA(VAR2,24)/EMA(VOL,24))/4,N);
SUP:1.06*VAR3;
SDN:VAR3*0.94;
VAR4:=EMA(CLOSE,9);
LUP:EMA(VAR4*1.14,5);
LDN:EMA(VAR4*0.86,5);
```

``` pascal
薛斯建立于薛斯的循环理论的基础上，属于短线指标。
在薛斯通道中，股价实际上是被短期小通道包容着在
长期大通道中上下运行，基本买卖策略是当短期小通道
接近长期大通道时，预示着趋势的近期反转。在上沿接
近时趋势向下反转，可扑捉短期卖点。在下沿接近时趋
势向上反转，可捕捉短期买点。研究这个方法可以在每
一波行情中成功地逃顶捉底，寻求最大限度的赢利。
薛斯通道的研判法则:
 1.长期大通道是反映该股票的长期趋势状态，趋势有一
   定惯性，延伸时间较长，反映股票大周期，可以反握
   股票整体趋势，适于中长线投资；
 2.短期小通道反映该股票的短期走势状态，包容股票的
   涨跌起伏，有效地滤除股票走势中的频繁振动，但保
   留了股票价格在大通道内的上下波动，反映股票小周
   期，适于中短线炒作；
 3.长期大通道向上，即大趋势总体向上 ，此时短期小通
   道触及（或接近长期大通道底部时，即买压增大，有反
   弹的可能。而短期小通道触及长期大通道顶部，既卖压
   增大，形态出现回调或盘整，有向长期大通道靠近的趋
   势。如果K线走势与短期小通道走势亦吻合得很好，那
   么更为有效；
 4.长期大通道向上，而短期小通道触及长期大通道顶部，
   此时该股为强力拉长阶段，可适当观望，待短期转平或
   转头向下时，为较好出货点，但穿透区为风险区应密切
   注意反转信号，随时出货；
 5.长期大通道向下，即大趋势向下，此时短期小通道或股
   价触顶卖压增加，有再次下跌趋势。而触底形态即买压
   增大，有缓跌调整或止跌要求，同时价格运动将趋向靠
   近长期大通道上沿。回调宜慎重对待，待确认反转信号
   后方可买入；
 6.长期大通道向下，而短期小通道向下穿透长期大通道底
   线，此时多为暴跌过程，有反弹要求，但下跌过程会持
   续，不宜立即建仓，应慎重，待长期大通道走平且有向
   上趋势，短期小通道回头向上穿回时，是较好的低位建
   仓机会；
 7.当长期大通道长期横向走平时，为盘整行情，价格沿通
   道上下震荡，此时为调整、建仓、洗盘阶段，预示着下
   一轮行情的出现，短线炒家可逢高抛出，逢低买入。若
   以短期小通道强力上穿长期大通道，且长期大通道向上
   转向，表明强劲上涨行情开始。若以短期小通道向下穿
   透长期大通道，且长期大通道向下转向，表明下跌将继
   续。 

```

### XS2  薛斯通道II(系统)

``` pascal
N	80.00	120.00	102.00
M	2.00	20.00	7.00
```

``` pascal
AA:=MA((2*CLOSE+HIGH+LOW)/4,5); 
通道1:AA*N/100; 
通道2:AA*(200-N)/100; 
CC:=ABS((2*CLOSE+HIGH+LOW)/4-MA(CLOSE,20))/MA(CLOSE,20); 
DD:=DMA(CLOSE,CC); 
通道3:(1+M/100)*DD; 
通道4:(1-M/100)*DD;
```

``` pascal
特点: 
1、根据通道形态找出波动的短周期,长周期是多少。
2、根据周期预测股票的后期走势。
3、股价的波动周期的各底是买入时机,股价的波动各顶是卖出时机。
用法:  
1、当股价运行到短周期通道的下轨时是短线买入机会,当股价运行到短周期通道的上轨时是短线的卖出时机。
2、当股价运行到长周期的下轨时是中长线买入时机,而当股价运行到长周期的上轨时是中长线的卖出时机。
3、当短周期运行到长周期的下轨时，从下向上突破长周期的下轨时是买入时机，而当短周期运行到长周期的上轨时，从上向下突破长周期的上轨时为卖出时机。

```

### QR  强弱指标(需下载日线)(系统)

``` pascal
N	2.00	200.00	21.00
```

``` pascal
个股: (CLOSE-REF(CLOSE,N))/REF(CLOSE,N)*100; 
大盘: (INDEXC-REF(INDEXC,N))/REF(INDEXC,N)*100; 
强弱值:EMA(个股-大盘,2),COLORSTICK;
```

``` pascal
指标攀升表明个股走势渐强于大盘，后市看好；指标滑落
表明个股走势弱于大盘，可择机换股。同时要结合大盘走
势研判，应选择大盘转暖或走牛时出击。

注意：此指标使用到了大盘的数据，所以需要下载完整的
日线数据,否则显示可能不正确

```

### GDX  轨道线(系统)

``` pascal
N	2.00	120.00	30.00
M	3.00	50.00	9.00
```

``` pascal
AA:=ABS((2*CLOSE+HIGH+LOW)/4-MA(CLOSE,N))/MA(CLOSE,N); 
轨道:DMA(CLOSE,AA);
压力线:(1+M/100)*轨道; 
支撑线:(1-M/100)*轨道;
```

``` pascal
通道理论公式，是一种用技术手段和经验判断来决定买
卖股票的方法。该公式对趋势线做了平滑和修正处理，
更精确的反应了股价运行规律。当股价上升到压力线时，
投资者就卖出股票，而当股价下跌到支撑线时，投资者
就进行相应的补进。

```

### JLHB  绝路航标(系统)

``` pascal
N	2.00	100.00	7.00
M	2.00	100.00	5.00
```

``` pascal
VAR1:=(CLOSE-LLV(LOW,60))/(HHV(HIGH,60)-LLV(LOW,60))*80; 
B:SMA(VAR1,N,1); 
VAR2:SMA(B,M,1); 
绝路航标:IF(CROSS(B,VAR2) AND B<40,50,0);
```

``` pascal
反趋势类选股指标。综合了动量观念、强弱指标与移动
平均线的优点，在计算过程中主要研究高低价位与收市
价的关系，反映价格走势的强弱和超买超卖现象。在市
场短期超买超卖的预测方面又较敏感。

```

### MA交易  MA交易(系统)(可交易)

``` pascal
SHORT	1.00	30.00	5.00
LONG	1.00	30.00	20.00
```

``` pascal
{该模型为示范模型,仅用于说明算法语法,用户需根据自己交易经验修改后再实际应用}
{变量赋值}
MA1:=MA(CLOSE,SHORT);
MA2:=MA(CLOSE,LONG);
{交易条件}
平空开多:=CROSS(MA1,MA2);
平多开空:=CROSS(MA2,MA1);
{交易系统}
BUYSHORT_BUY(平空开多,LOW);
SELL_SELLSHORT(平多开空,HIGH);
{交易信号过滤}
AUTOFILTER;
```

### MACD交易  MACD交易(系统)(可交易)

``` pascal
SHORT	2.00	200.00	12.00
LONG	2.00	200.00	26.00
MID	2.00	200.00	9.00
```

``` pascal
{该模型为示范模型,仅用于说明算法语法,用户需根据自己交易经验修改后再实际应用}
DIFF:=EMA(CLOSE,SHORT)-EMA(CLOSE,LONG);
DEA:=EMA(DIFF,MID);
MACD:=2*(DIFF-DEA);
平空开多:=CROSS(MACD,0);
平多开空:=CROSS(0,MACD);
BUYSHORT_BUY(平空开多,LOW);
SELL_SELLSHORT(平多开空,HIGH);
AUTOFILTER;
```

### KDJ交易  KDJ交易(系统)(可交易)

``` pascal
N	1.00	40.00	9.00
M1	2.00	10.00	3.00
```

``` pascal
{该模型为示范模型,仅用于说明算法语法,用户需根据自己交易经验修改后再实际应用}
RSV:=(CLOSE-LLV(LOW,N))/(HHV(HIGH,N)-LLV(LOW,N))*100;
K:=SMA(RSV,M1,1);
D:=SMA(K,M1,1);
J:=3*K-2*D;
平空开多:=CROSS(J,0);
平多开空:=CROSS(100,J);
BUYSHORT_BUY(平空开多,LOW);
SELL_SELLSHORT(平多开空,HIGH);
AUTOFILTER;
```

### 肯特纳  肯特纳通道交易(系统)(可交易)

``` pascal
AVGLENGTH	1.00	100.00	40.00
ATRLENGTH	1.00	100.00	40.00
```

``` pascal
{该模型为示范模型,仅用于说明算法语法,用户需根据自己交易经验修改后再实际应用}
MA1:=REF(MA((HIGH+LOW+CLOSE)/3,AVGLENGTH),1);
UPPERBAND:=MA1+REF(MA(TR,ATRLENGTH),1);
LOWERBAND:=MA1-REF(MA(TR,ATRLENGTH),1);
开多条件:=MA1>REF(MA1,1) AND HIGH>=UPPERBAND;
平多条件:=LOW<=MA1;
开空条件:=MA1<REF(MA1,1) AND LOW<=LOWERBAND;
平空条件:=HIGH>=MA1;
GL1:=NOT(开多条件=1 AND 平多条件=1);
GL2:=NOT(开空条件=1 AND 平空条件=1);
SELL(平多条件,HIGH);
BUYSHORT(平空条件,LOW);
BUY(开多条件 AND GL1,LOW);
SELLSHORT(开空条件 AND GL2,HIGH);
AUTOFILTER;
```

### 唐奇安  唐奇安通道交易(系统)(可交易)

``` pascal
X1	1.00	100.00	20.00
X2	1.00	100.00	10.00
NMIN	1.00	100.00	10.00
```

``` pascal
{该模型为示范模型,仅用于说明算法语法,用户需根据自己交易经验修改后再实际应用}
周期高点:=REF(HHV(H,X1),1);
周期低点:=REF(LLV(L,X2),1);
平空开多:=HIGH>=周期高点;
平多开空:=LOW<=周期低点;
BUYSHORT_BUY(平空开多,LOW);
SELL_SELLSHORT(平多开空,HIGH);
AUTOFILTER;
```

### 日内突破  日内突破交易(系统)(可交易)

``` pascal
N	1.00	100.00	30.00
M	1.00	20.00	5.00
```

``` pascal
{该模型为示范模型,仅用于说明算法语法,用户需根据自己交易经验修改后再实际应用}
{变量赋值}
NBAR:=BARSLAST(DATE<>REF(DATE,1))+1;
HHN:REF(HHV(H,N),1);
LLN:REF(LLV(L,N),1);
MID:(HHN+LLN)/2;
T1:=TIME>900 AND TIME <1455;{根据品种的交易时间和选择的周期做相应调整}
T2:=TIME>=1455;{根据品种的交易时间和选择的周期做相应调整}
{交易条件}
开多条件:=H>HHN AND (HHN-MID)/MID<M/1000 AND NBAR>=30 AND T1;
开空条件:=L<LLN AND (MID-LLN)/MID<M/1000 AND NBAR>=30 AND T1;
{交易系统}
BUY(开多条件,LOW);
SELLSHORT(开空条件,HIGH);
SELL(T2,HIGH);
BUYSHORT(T2,LOW);
AUTOFILTER;
```

### HANS123  日内HANS交易(系统)(可交易)

``` pascal
M	1.00	100.00	1.00
NMIN1	1.00	100.00	30.00
NMIN2	1.00	100.00	10.00
```

``` pascal
{该模型为示范模型,仅用于说明算法语法,用户需根据自己交易经验修改后再实际应用}
{变量赋值}
N:=BARSLAST(DATE<>REF(DATE,1))+1;
HHH:=VALUEWHEN(TIME<=900+NMIN1,HHV(H,N));
LLL:=VALUEWHEN(TIME<=900+NMIN1,LLV(L,N));
上轨:HHH+M*MINDIFF;
下轨:LLL-M*MINDIFF;
{交易条件}
开多条件:=C>上轨;
开空条件:=C<下轨;
交易时间:=TIME>900+NMIN1 AND TIME<1450;
平仓时间:=TIME>=1500-NMIN2;
{交易系统}
BUY(开多条件 AND 交易时间,LOW);
SELLSHORT(开空条件 AND 交易时间,HIGH);
SELL(平仓时间,HIGH);
BUYSHORT(平仓时间,LOW);
AUTOFILTER;
```

### SG-XDT  心电图(需下载日线)(系统)

``` pascal
P1	1.00	100.00	5.00
P2	1.00	100.00	10.00
```

``` pascal
QR:CLOSE/INDEXC*1000;
MQR1:MA(QR,5);
MQR2:MA(QR,10);
```

``` pascal
注意：此指标使用到了大盘的数据，所以需要下载完整的
日线数据,否则显示可能不正确

```

### SG-NDB  脑电波(神系)(系统)

``` pascal
P1	1.00	100.00	5.00
P2	1.00	100.00	10.00
```

``` pascal
HH:=IF(C/REF(C,1)>1.093 AND L>REF(H,1),2*C-REF(C,1)-H,2*C-H-L);
V1:=BARSCOUNT(C);
V2:=2*REF(C,V1)-REF(H,V1)-REF(L,V1);
DK:SUM(HH,0)+V2;
MDK5:MA(DK,P1);
MDK10:MA(DK,P2);
```

### SG-SMX  生命线(需下载日线)(系统)

``` pascal
N	1.00	100.00	50.00
```

``` pascal
H1:=HHV(HIGH,N);
L1:=LLV(LOW,N);
H2:=HHV(INDEXH,N);
L2:=LLV(INDEXL,N);
ZY:=CLOSE/INDEXC*2000;
ZY1:EMA(ZY,3);
ZY2:EMA(ZY,17);
ZY3:EMA(ZY,34);
```

``` pascal
注意：此指标使用到了大盘的数据，所以需要下载完整的
日线数据,否则显示可能不正确

```

### SG-LB  量比(需下载日线)(系统)

``` pascal
ZY2:=VOL/INDEXV*1000;
量比:ZY2;
MA5:MA(ZY2,5);
MA10:MA(ZY2,10);
```

``` pascal
注意：此指标使用到了大盘的数据，所以需要下载完整的
日线数据,否则显示可能不正确

```

### SG-PF  强势股评分(需下载日线)(系统)

``` pascal
ZY1:=CLOSE/INDEXC*1000;
A1:=IF(ZY1>HHV(ZY1,3),10,0);
A2:=IF(ZY1>HHV(ZY1,5),15,0);
A3:=IF(ZY1>HHV(ZY1,10),20,0);
A4:=IF(ZY1>HHV(ZY1,2),10,0);
A5:=COUNT(ZY1>REF(ZY1,1) ,9)*5;
强势股评分:A1+A2+A3+A4+A5;
```

``` pascal
注意：此指标使用到了大盘的数据，所以需要下载完整的
日线数据,否则显示可能不正确

```

### CYC  成本均线(系统)

``` pascal
P1	2.00	30.00	5.00
P2	2.00	60.00	13.00
P3	2.00	120.00	34.00
```

``` pascal
JJJ:=IF(DYNAINFO(8)>0.01,0.01*DYNAINFO(10)/DYNAINFO(8),DYNAINFO(3));
DDD:=(DYNAINFO(5)<0.01 || DYNAINFO(6)<0.01);
JJJT:=IF(DDD,1,(JJJ<(DYNAINFO(5)+0.01) && JJJ>(DYNAINFO(6)-0.01)));
CYC1:IF(JJJT,0.01*EMA(AMOUNT,P1)/EMA(VOL,P1),EMA((HIGH+LOW+CLOSE)/3,P1));
CYC2:IF(JJJT,0.01*EMA(AMOUNT,P2)/EMA(VOL,P2),EMA((HIGH+LOW+CLOSE)/3,P2));
CYC3:IF(JJJT,0.01*EMA(AMOUNT,P3)/EMA(VOL,P3),EMA((HIGH+LOW+CLOSE)/3,P3));
CYC∞:IF(JJJT,DMA(AMOUNT/(100*VOL),100*VOL/FINANCE(7)),EMA((HIGH+LOW+CLOSE)/3,120));
```

### CYS  市场盈亏(系统)

``` pascal
CYC13:=0.01*EMA(AMOUNT,13)/EMA(VOL,13);
CYS:(CLOSE-CYC13)/CYC13*100;
```

### CYQKL  博弈K线长度(系统)

``` pascal
KL:100*(WINNER(CLOSE)-WINNER(OPEN));
```

### CYW  主力控盘(系统)

``` pascal
VAR1:=CLOSE-LOW;
VAR2:=HIGH-LOW;
VAR3:=CLOSE-HIGH;
VAR4:=IF(HIGH>LOW,(VAR1/VAR2+VAR3/VAR2)*VOL,0);
CYW: SUM(VAR4,10)/10000, COLORSTICK;
```

### RAD  威力雷达(需下载日线)(系统)

``` pascal
D	1.00	100.00	3.00
S	1.00	250.00	30.00
M	1.00	100.00	30.00
```

``` pascal
SM:=(OPEN+HIGH+CLOSE+LOW)/4;
SMID:=MA(SM,D);
IM:=(INDEXO+INDEXH+INDEXL+INDEXC)/4;
IMID:=MA(IM,D);
SI1:=(SMID-REF(SMID,1))/SMID;
II:=(IMID-REF(IMID,1))/IMID;
RADER1:SUM((SI1-II)*2,S)*1000;
RADERMA:SMA(RADER1,M,1);
```

``` pascal
1.RAD 曲线往上跷升越陡者，代表该股为强势股。
2.RAD 指标选择强势股的效果相当良好，请多多利用。

注意：此指标使用到了大盘的数据，所以需要下载完整的
日线数据,否则显示可能不正确

```

### LON  龙系长线(系统)

``` pascal
N	2.00	300.00	10.00
```

``` pascal
LC := REF(CLOSE,1);
VID := SUM(VOL,2)/(((HHV(HIGH,2)-LLV(LOW,2)))*100);
RC := (CLOSE-LC)*VID;
LONG := SUM(RC,0);
DIFF := SMA(LONG,10,1);
DEA := SMA(LONG,20,1);
LON : DIFF-DEA;
LONMA : MA(LON,N);
LONT : LON, COLORSTICK;
```

``` pascal
1.当指标曲线向上交叉其平均线时，视为长线买进信号。
2.当指标曲线向下交叉其平均线时，视为长线卖出信号。
3.本指标可搭配MACD、TRIX指标使用。

```

### SHT  龙系短线(系统)

``` pascal
N	2.00	250.00	5.00
```

``` pascal
VAR1:=MA((VOL-REF(VOL,1))/REF(VOL,1),5);
VAR2:=(CLOSE-MA(CLOSE,24))/MA(CLOSE,24)*100;
MY: VAR2*(1+VAR1);
SHT: MY, COLORSTICK;
SHTMA: MA(SHT,N);
```

``` pascal
1.当指标曲线向上交叉其平均线时，视为短线买进信号。
2.当指标曲线向下交叉其平均线时，视为短线卖出信号。
3.本指标可搭配KDJ、DMA指标使用。

```

### ZLJC  主力进出(系统)

``` pascal
VAR1:=(CLOSE+LOW+HIGH)/3; 
VAR2:=SUM(((VAR1-REF(LOW,1))-(HIGH-VAR1))*VOL/100000/(HIGH-LOW),0); 
VAR3:=EMA(VAR2,1); 
JCS:VAR3; 
JCM:MA(VAR3,12); 
JCL:MA(VAR3,26);
```

``` pascal
白线为短期主力运作轨迹，黄线为中期主力运作轨迹，紫线为长期主力运作轨迹。
1、主力进出指标的白线向上突破黄线、紫线且三线向上发散，表示主力有效控盘，可逢底介入，持股待涨。
2、主力进出指标的白线上涨过快远离黄、紫线，出现较大乖离，表示短线获利筹码较多，宜注意控制风险，可适当卖出。
3、当白线回落至黄、紫线处受支撑时，而黄紫线发散向上，表示上升趋势未改，前期股价回落仅是途中的回调，可适量跟进。
4、主力进出三线“死亡交叉”，盘口呈空头排列，投资者宜尽快出局。
5、主力进出三线相近并平行向下时，表明主力尚未进场或正在出货，此时不宜介入。
6、主力进出是一种趋势指标，但趋势改变信号有时会出现滞后现象，此时就要用主力买卖指标加以配合使用。

```

### ZLMM  主力买卖(系统)

``` pascal
LC :=REF(CLOSE,1);
RSI2:=SMA(MAX(CLOSE-LC,0),12,1)/SMA(ABS(CLOSE-LC),12,1)*100;
RSI3:=SMA(MAX(CLOSE-LC,0),18,1)/SMA(ABS(CLOSE-LC),18,1)*100;
MMS:MA(3*RSI2-2*SMA(MAX(CLOSE-LC,0),16,1)/SMA(ABS(CLOSE-LC),16,1)*100,3);
MMM:EMA(MMS,8);
MML:MA(3*RSI3-2*SMA(MAX(CLOSE-LC,0),12,1)/SMA(ABS(CLOSE-LC),12,1)*100,5);
```

``` pascal
白线为短期趋势线，黄线为中期趋势线，紫线为长期趋势线。
1、主力买卖与主力进出配合使用时准确率极高。 
2、当底部构成发出信号，且主力进出线向上时判断买点，准确率极高。 
3、当短线上穿中线及长线时，形成最佳短线买点交叉形态（如底部构成已发出信号或主力进出线也向上且短线乖离率不大时）。
4、当短线、中线均上穿长线，形成中线最佳买点形态（如底部构成已发出信号或主力进出线也向上且三线均向上时）。 
5、当短线下穿中线，且短线与长线正乖离率太大时，形成短线最佳卖点交叉形态。 
6、当短线、中线下穿长线，且是主力进出已走平或下降时，形成中线最佳卖点交叉形态。
7、在上升途中，短、中线回落受长线支撑再度上行之时，为较佳的买入时机。
8、指标在0以上表明个股处于强势，指标跌穿0线表明该股步入弱势。

```

### SLZT  神龙在天(系统)

``` pascal
白龙: MA(CLOSE,125);
黄龙: 白龙+2*STD(CLOSE,170);
紫龙: 白龙-2*STD(CLOSE,145);
青龙: SAR(125,1,7), LINESTICK;
VAR2:=HHV(HIGH,70);
VAR3:=HHV(HIGH,20);
红龙: VAR2*0.83;
蓝龙: VAR3*0.91;
```

### ADVOL  龙系离散量(系统)

``` pascal
A:=SUM(((CLOSE-LOW)-(HIGH-CLOSE))*VOL/10000/(HIGH-LOW),0);
ADVOL:A;
MA1:MA(A,30);
MA2:MA(MA1,100);
```

### CJDX  超级短线(系统)

``` pascal
VAR1:=(2*CLOSE+HIGH+LOW)/4;
VAR2:=EMA(EMA(EMA(VAR1,4),4),4);
J: (VAR2-REF(VAR2,1))/REF(VAR2,1)*100, COLORSTICK;
D: MA(J,3);
K: MA(J,1);
```

### ZJTJ  庄家抬轿(系统)

``` pascal
VAR1:=EMA(EMA(CLOSE,9),9);
控盘:=(VAR1-REF(VAR1,1))/REF(VAR1,1)*1000;
STICKLINE(控盘<0,控盘,0,1,0),COLORWHITE;
A10:=CROSS(控盘,0);
无庄控盘:IF(控盘<0,控盘,0),COLORWHITE,NODRAW;
开始控盘:IF(A10,5,0),LINETHICK1,COLORYELLOW;
STICKLINE(控盘>REF(控盘,1) AND 控盘>0,控盘,0,1,0),COLORRED;
有庄控盘:IF(控盘>REF(控盘,1) AND 控盘>0,控盘,0),COLORRED,NODRAW;
VAR2:=100*WINNER(CLOSE*0.95);
STICKLINE(VAR2>50 AND COST(85)<CLOSE AND 控盘>0,控盘,0,1,0),COLORFF00FF;
高度控盘:IF(VAR2>50 AND COST(85)<CLOSE AND 控盘>0,控盘,0),COLORFF00FF,NODRAW;
STICKLINE(控盘<REF(控盘,1) AND 控盘>0,控盘,0,1,0),COLOR00FF00;
主力出货:IF(控盘<REF(控盘,1) AND 控盘>0,控盘,0),COLOR00FF00,NODRAW;
```

### ZBCD  准备抄底(系统)

``` pascal
N	1.00	300.00	10.00
```

``` pascal
VAR1:=AMOUNT/VOL/7;
VAR2:=(3*HIGH+LOW+OPEN+2*CLOSE)/7;
VAR3:=SUM(AMOUNT,N)/VAR1/7;
VAR4:=DMA(VAR2,VOL/VAR3);
抄底:(CLOSE-VAR4)/VAR4*100,COLORLIMAGENTA;
DRAWICON(CROSS(-7.0,抄底),抄底,1);
```

### BDZX  波段之星(系统)

``` pascal
VAR2:=(HIGH+LOW+CLOSE*2)/4;
VAR3:=EMA(VAR2,21);
VAR4:=STD(VAR2,21);
VAR5:=((VAR2-VAR3)/VAR4*100+200)/4;
VAR6:=(EMA(VAR5,5)-25)*1.56;
AK: EMA(VAR6,2)*1.22;
AD1: EMA(AK,2);
AJ: 3*AK-2*AD1;
AA:100;
BB:0;
CC:80;
买进: IF(CROSS(AK,AD1),58,20);
卖出: IF(CROSS(AD1,AK),58,20);
```

### LHXJ  猎狐先觉(系统)

``` pascal
VAR1:=(CLOSE*2+HIGH+LOW)/4;
VAR2:=EMA(VAR1,13)-EMA(VAR1,34);
VAR3:=EMA(VAR2,5);
主力弃盘: (-2)*(VAR2-VAR3)*3.8;
主力控盘: 2*(VAR2-VAR3)*3.8;
```

### LYJH  猎鹰歼狐(系统)

``` pascal
M	1.00	200.00	80.00
M1	1.00	200.00	50.00
```

``` pascal
VAR1:=(HHV(HIGH,36)-CLOSE)/(HHV(HIGH,36)-LLV(LOW,36))*100;
机构做空能量线: SMA(VAR1,2,1);
VAR2:=(CLOSE-LLV(LOW,9))/(HHV(HIGH,9)-LLV(LOW,9))*100;
机构做多能量线: SMA(VAR2,5,1)-8;
LH: M;
LH1: M1;
```

### JFZX  飓风智能中线(系统)

``` pascal
N	5.00	200.00	30.00
```

``` pascal
VAR2:=SUM(IF(CLOSE>OPEN,VOL,0),N)/SUM(VOL,N)*100;
VAR3:=100-SUM(IF(CLOSE>OPEN,VOL,0),N)/SUM(VOL,N)*100;
多头力量: VAR2;
空头力量: VAR3;
多空平衡: 50;
```

### CYHT  财运亨通(系统)

``` pascal
VAR1:=(2*CLOSE+HIGH+LOW+OPEN)/5;
高抛: 80;
VAR2:=LLV(LOW,34);
VAR3:=HHV(HIGH,34);
SK: EMA((VAR1-VAR2)/(VAR3-VAR2)*100,13);
SD: EMA(SK,3);
低吸: 20;
强弱分界: 50;
VAR4:=IF(CROSS(SK,SD),40,22);
VAR5:=IF(CROSS(SD,SK),60,78);
卖出: VAR5;
买进: VAR4;
```

### SCR  筹码集中度(系统)

``` pascal
P1	1.00	100.00	90.00
```

``` pascal
A:=P1+(100-P1)/2;
B:=(100-P1)/2;
CC:=COST(A);
DD:=COST(B);
SCR:(CC-DD)/(CC+DD)*100/2;
```

### ASR  浮筹比例(系统)

``` pascal
ASR:(WINNER(C*1.1)-WINNER(C*0.9))/WINNER(HHV(H,0))*100;
```

### BSQJ  买卖区间(系统)

``` pascal
买线:=EMA(C,2);
卖线:=EMA(SLOPE(C,21)*20+C,42);
STICKLINE(买线>=卖线,REFDATE(HHV(H,0),DATE),REFDATE(LLV(L,0),DATE),6,0),COLOR001050;
STICKLINE(买线<卖线,REFDATE(HHV(H,0),DATE),REFDATE(LLV(L,0),DATE),6,0),COLOR404050;
DRAWKLINE(H,O,L,C);
指导:=EMA((EMA(CLOSE,4)+EMA(CLOSE,6)+EMA(CLOSE,12)+EMA(CLOSE,24))/4,2);
界:=MA(CLOSE,27);
B买:IF(CROSS(指导,界) OR CROSS(买线,卖线),C,DRAWNULL),COLORMAGENTA,NODRAW;
持仓:IF(买线>=卖线,C,DRAWNULL),COLORRED,NODRAW;
S卖:IF(CROSS(界,指导) OR CROSS(卖线,买线),C,DRAWNULL),COLORLIGRAY,NODRAW;
空仓:IF(买线<卖线,C,DRAWNULL),COLORGREEN,NODRAW;
DRAWICON(CROSS(买线,卖线),L,1);
DRAWICON(CROSS(卖线,买线),H,2);
```

### ZJL  折价率,用于排序(系统)

``` pascal
折价率:IF(FINANCE(34)>0.001,(FINANCE(34)-CLOSE)*100.0/FINANCE(34),0);
```

### CDP-STD  逆势操作(系统)

``` pascal
CH:=REF(H,1);
CL:=REF(L,1);
CC:=REF(C,1);
CDP:(CH+CL+CC)/3;
AH:2*CDP+CH-2*CL;
NH:CDP+CDP-CL;
NL:CDP+CDP-CH;
AL:2*CDP-2*CH+CL;
```

``` pascal
1.在股价波动不是很大的情况下，即开盘价位在近高值与近低
  值之间时，通常交易者可以在近低值价位买进，而在近高值
  价位卖出，或在近高值价位卖出，近低值价位买进；
2.当开盘价开在最高值或最低值附近时，则意味着跳空开高或
  跳空开低，是一个大行情发动的开始；
3.投资者可以在最高值的价位去追买，在最低值的价位去追卖
  。通常，一个跳空意味着强烈的涨跌，一般有相当利润。

```

### TBP-STD  趋势平衡点(系统)

``` pascal
APX:=(H+L+C)/3;
TR0:=MAX(H-L,MAX(ABS(H-REF(C,1)),ABS(L-REF(C,1))));
MF0:=C-REF(C,2);
MF1:=REF(MF0,1);
MF2:=REF(MF0,2);
DIRECT1:=BARSLAST(MF0>MF1 AND MF0>MF2);
DIRECT2:=BARSLAST(MF0<MF1 AND MF0<MF2);
DIRECT0:=IF(DIRECT1<DIRECT2,100,-100);
TBP:REF(REF(C,1)+IF(DIRECT0>50,MIN(MF0,MF1),MAX(MF0,MF1)),1);
多头获利:REF(IF(DIRECT0>50,APX*2-L,DRAWNULL),1),NODRAW;
多头停损:REF(IF(DIRECT0>50,APX-TR0,DRAWNULL),1),NODRAW;
空头回补:REF(IF(DIRECT0<-50,APX*2-H,DRAWNULL),1),NODRAW;
空头停损:REF(IF(DIRECT0<-50,APX+TR0,DRAWNULL),1),NODRAW;
```

``` pascal
一.开始进场
1.当收盘价高于TBP时，在收盘的那一刻，应该进场买入股票；
2.当收盘价低于TBP时，在收盘的那一刻，应该卖出股票出场或融券放空；
二.市况反转（股价未触及了结点或停损点时）
1.当收盘价高于TBP时，在收盘的那一刻，应该把空头交易改为多头交易；
2.当收盘价低于TBP时，在收盘的那一刻，应该把多头交易改为空头交易；
三.出场
1.当股价抵达了结点时，应获利了结出场，但不能反转；
2.当股价碰触停损点时，应停损出场，但不能反转；
四.重新进场
1.出场后，须依据收盘时的TBP来决定是否重新进场；
五.决定明天的TBP
1.如果市况是多头，则先挑出前两天速量因子中较小者，然后，再与昨天的收盘价相加，即可求出明天的TBP；
2.如果市况是空头，则先挑出前两天速量加子中较大者，然后，再与昨天的收盘 价相加，即可求出明天的TBP。

```

## SC  三叉(系统)

## NDB  脑电波(系统)

### JYJL  交易参考均量(系统)

``` pascal
N	1.00	1000.00	120.00
M	1.00	1000.00	5.00
```

``` pascal
单位时间总量: SUM(VOL,N)*100,NODRAW;
单位时间内均量: 单位时间总量/(N/M);
```

### JSJG  参考结算价(适用于金融期货)(系统)

``` pascal
FIRST:=IF(PERIOD=0,HOUR=14 AND MINUTE=16,DRAWNULL);
TOTAL:=IF(PERIOD=0,60,0);
MAMIN:=BARSLAST(FIRST)+1;
COUNTFLAG:=(PERIOD=0 AND ( (HOUR=14 AND MINUTE>=16) OR HOUR=15 ));
逼近结算价格:IF(COUNTFLAG,SUM(C*V,MAMIN)/SUM(V,MAMIN),DRAWNULL);
LASTP:=C;
LASTM:=MAMIN;
LASTV:=MA(V,MAMIN);
参考结算价格:IF(COUNTFLAG,(SUM(C*V,MAMIN)+LASTP*LASTV*(TOTAL-LASTM))/(LASTV*TOTAL),DRAWNULL);
```

``` pascal
1.因为非交割日结算价格依赖于期货合约自身,因此公式应使用于期货合约交易时段的最后60分钟,建议用于单日分时图.
2.若是在多日分时使用,非交割日结果有效,交割日结果无效,相邻两日之间会被连接,该连接线无效.
3.逼近交割价格为,统计时间范围内已经确认的价格的算术平均价,随时间变动逼近最终交割价格.
4.参考交割价格为,按照最新价格将未确认价格补全后,统计时间范围内所有计算价格的算术平均价.


```

### PRICEV  价格波动率(系统)

``` pascal
N	2.00	10000.00	60.00
M	2.00	10000.00	120.00
```

``` pascal
VR:STDDEV(CLOSE,N)*100;
VRMA:MA(VR,M);
```

### HISV  历史波动率(系统)

``` pascal
N	2.00	10000.00	60.00
```

``` pascal
波动率:STDDEV(CLOSE,N)*SQRT(250)*100.0;
```

### VOLATILITY  期权波动率(系统)

``` pascal
N	2.00	10000.00	60.00
```

``` pascal
HV:IVOLAT(N,0)*100.0;
隐含波动率:IVOLAT(N,1)*100.0;
波动差:(隐含波动率-HV),COLORSTICK;
```

### CPBS  操盘BS点(系统)

``` pascal
BU:=CROSS(HIGH,SAR(3,1,20));
SEL:=CROSS(SAR(3,1,20),LOW);
DRAWTEXT(BU,LOW,'B'),COLORYELLOW,LINETHICK2;
DRAWTEXT(SEL,1.01*HIGH,'S'),COLORGREEN,LINETHICK2;
```

### CYX  撑压线(系统)

``` pascal
N	1.00	100.00	7.00
```

``` pascal
Z1:=STRCAT(HYBLOCK,' ');
Z2:=STRCAT(Z1,DYBLOCK);
Z3:=STRCAT(Z2,' ');
DRAWTEXT_FIX(ISLASTBAR,0,0,0,STRCAT(Z3,GNBLOCK)),COLOR00C0C0;
A1:=REF(H,N)=HHV(H,2*N+1);
B1:=FILTER(A1,N);
C1:=BACKSET(B1,N+1);
D1:=FILTER(C1,N);
A2:=REF(L,N)=LLV(L,2*N+1);
B2:=FILTER(A2,N);
C2:=BACKSET(B2,N+1);
D2:=FILTER(C2,N);
E1:=(REF(LLV(L,2*N),1)+REF(HHV(H,2*N),1))/2;
E2:=(H+L)/2;
H1:=(D1 AND NOT(D2 AND E1>=E2)) OR ISLASTBAR OR BARSCOUNT(C)=1;
L1:=(D2 AND NOT(D1 AND E1<E2));
H2:=D1 AND NOT(D2 AND E1>=E2);
X1:=REF(BARSLAST(H1),1)+1;
F1:=BACKSET(H1 AND COUNT(L1,X1)>0,LLVBARS(IF(L1,L,10000),X1));
G1:=F1>REF(F1,1);
I1:=BACKSET(G1,2);
LD:=I1>REF(I1,1);
L2:=LD OR ISLASTBAR OR BARSCOUNT(C)=1;
X2:=REF(BARSLAST(L2),1)+1;
F2:=BACKSET(L2 AND COUNT(H2,X2)>0,HHVBARS(IF(H2,H,0),X2));
G2:=F2>REF(F2,1);
I2:=BACKSET(G2,2);
HD:=I2>REF(I2,1);
R1:=BACKSET(ISLASTBAR,BARSLAST(HD)+1);
S1:=R1>REF(R1,1);
T1:=BACKSET(ISLASTBAR,BARSLAST(LD)+1);
U1:=T1>REF(T1,1);
R2:=BACKSET(S1,REF(BARSLAST(HD),1)+2);
S2:=R2>REF(R2,1);
T2:=BACKSET(U1,REF(BARSLAST(LD),1)+2);
U2:=T2>REF(T2,1);
NOTEXT1:DRAWLINE(S2,H,S1,H,1),LINETHICK2,COLORRED;
NOTEXT2:DRAWLINE(U2,L,U1,L,1),LINETHICK2,COLORGREEN;
```

### WAVE  波浪分析(系统)

``` pascal
因子	0.20	100.00	5.00
```

``` pascal
ZIG(3,因子);
```

### SKSD  时空隧道(系统)

``` pascal
N	1.00	200.00	5.00
M	1.00	200.00	10.00
```

``` pascal
STICKLINE(CURRBARSCOUNT<=N,H,L,-1,0),COLORBLACK;
DRAWTEXT_FIX(ISLASTBAR,0,0,0,STRCAT(CON2STR(N,0),'周期前K线  选中主图后按ALT+T键调节回退的周期')),COLORLIMAGENTA;
NOTEXT1:IF(CURRBARSCOUNT>=N+1,MA(C,M),DRAWNULL),COLORWHITE;
NOTEXT2:IF(CURRBARSCOUNT<=N,MA(C,M),DRAWNULL),COLORBLACK;
```

## 短线决策  短线持股持币区(系统)

## 中线决策  中线持股持币区(系统)

## XLPL  吸拉派落(系统)

## GSTQ  股市天气(系统)

### AROON  阿隆指标(系统)

``` pascal
N	1.00	300.00	25.00
```

``` pascal
上轨:(N-HHVBARS(H,N))/N*100,COLORRED;
下轨:(N-LLVBARS(H,N))/N*100,COLORGREEN;
```

``` pascal
在分析Aroon指标时,主要观察三种状态:

1、极值0和100，当UP线达到100时，市场处于强势；如果维持在70~100之间，表示一个上升趋势。同样，如果Down线达到0，表示处于弱势，如果维持在0~30之间，表示处于下跌趋势。如果两条线同处于极值水平，则表明一个更强的趋势。 

2、平行运动，如果两条线平行运动时，表明市场趋势被打破。可以预期该状况将持续下去，只到由极值水平或交叉穿行时为止。 　　

3、交叉穿行，当下行线上穿上行线时，表明潜在弱势，预期价格开始趋于下跌。反之，表明潜在强势，预期价格趋于走高。


```

### CFJT  财富阶梯(系统)

``` pascal
突破:=REF(EMA(C,14),1);
A1X:=(EMA(C,10)-突破)/突破*100;
多方:=IF(A1X>=0,REF(EMA(C,10),BARSLAST(CROSS(A1X,0))+1),DRAWNULL);
空方:=IF(A1X<0,REF(EMA(C,10),BARSLAST(CROSS(0,A1X))+1),DRAWNULL);
STICKLINE(A1X>=0,多方,突破,10,0),COLOR000099;
STICKLINE(A1X<0,空方,突破,10,0),COLOR00CC66;
```

### TJCJL  太极成交量(系统)

``` pascal
总量:VOL,NODRAW;
DRAWTEXT_FIX(ISLASTBAR,0,0,0,'说明: 红色柱为吸货量,绿色为出货量,黄色为天量,蓝色为地量'),COLORGRAY;
ZZ:=IF(REF(C,1)>REF(O,1) AND O>REF(C,1)*1.014 AND C<O*1.02,1,3);
V5:=MA(V,5);
V12:=MA(V,12);
V34:=MA(V,34);
C6:=MA(C,6);
STICKLINE(VOL,0,VOL,1,0),COLORLIGRAY;
STICKLINE(CROSS(C,C6) AND V>V5*1.2 AND V>V12*1.2 AND ZZ>2 AND C>H*0.975,0,VOL,1,0),COLORRED;
STICKLINE(CROSS(C6,C) AND V>V5*1.2 AND V>V12*1.2,0,VOL,1,0),COLORGREEN;
STICKLINE(VOL>MA(VOL,5)*2 AND V>V34*3 AND C<REF(C,1)*1.05,0,VOL,1,0),COLORYELLOW;
STICKLINE(VOL<MA(VOL,5)/2 AND V<V12/2,0,VOL,1,0),COLORBLUE;
STICKLINE(VOL>MA(VOL,5)*2 AND V>V34*3 AND C<REF(C,1)*1.05 AND CROSS(C,C6) AND V>V5*1.2 AND V>V12*1.2 AND ZZ>2 AND C>H*0.975,VOL*0.5,0,1,0),COLORRED;
STICKLINE(VOL>MA(VOL,5)*2 AND V>V34*3 AND C<REF(C,1)*1.05 AND CROSS(C6,C) AND V>V5*1.2 AND V>V12*1.2,VOL*0.5,0,1,0),COLORRED;
```

### ZJFZ  追击反转(系统)

``` pascal
VAR2:=REF(LOW,1);
VAR3:=SMA(ABS(LOW-VAR2),3,1)/SMA(MAX(LOW-VAR2,0),3,1)*100;
VAR4:=EMA(VAR3*10,3);
VAR5:=LLV(LOW,13);
VAR6:=HHV(VAR4,13);
VAR7:=EMA(IF(LOW<=VAR5,(VAR4+VAR6*2)/2,0),3)/618;
VAR8:=IF(VAR7>500,500,VAR7);
STICKLINE(VAR8>-120,0,VAR8,3,1),COLORGRAY;
STICKLINE(VAR8>1 AND "KDJ.J">REF("KDJ.J",1) AND REF("KDJ.J",1)<REF("KDJ.J",2),0,VAR8,3,0),COLORRED;
STICKLINE(VAR8>0.1 AND VAR8<1 AND "KDJ.J">REF("KDJ.J",1) AND REF("KDJ.J",1)<REF("KDJ.J",2),0,VAR8,3,0),COLOR00FFFF;
```

### ZSDB  指数对比(副图,需下载日线)(系统)

``` pascal
A:=REF(INDEXC,1);
指数涨幅:IF(A>0,(INDEXC-A)*100/A,0),NODRAW;
HYDB:DRAWKLINE(INDEXH,INDEXO,INDEXL,INDEXC);
```

### HYDB  行业对比(副图,需下载日线)(系统)

``` pascal
A:=REF(HY_INDEXC,1);
行业涨幅:IF(A>0,(HY_INDEXC-A)*100/A,0),NODRAW;
DRAWTEXT_FIX(ISLASTBAR,0,0,0,HYBLOCK),COLOR00C0C0;
HYDB:DRAWKLINE(HY_INDEXH,HY_INDEXO,HY_INDEXL,HY_INDEXC);
```

### DKCOL  多空能量柱(适用于分时主图)(系统)

``` pascal
N	1.00	200.00	5.00
```

``` pascal
FF:=(C-REF(C,N))/REF(C,N);
STICKLINE(FF>0,DYNAINFO(3),DYNAINFO(3)*(1+FF),0.5,0),COLORRED;
STICKLINE(FF<0,DYNAINFO(3),DYNAINFO(3)*(1+FF),0.5,0),COLORGREEN;
```

### FKX  反K线(系统)

``` pascal
DRAWKLINE(-LOW, -OPEN, -HIGH, -CLOSE);
```

### ZJLX  资金流向(系统)

``` pascal
超B:=L2_AMO(0,2)/10000.0;
大B:=L2_AMO(1,2)/10000.0;
中B:=L2_AMO(2,2)/10000.0;
小B:=L2_AMO(3,2)/10000.0;
超S:=L2_AMO(0,3)/10000.0;
大S:=L2_AMO(1,3)/10000.0;
中S:=L2_AMO(2,3)/10000.0;
小S:=L2_AMO(3,3)/10000.0;
资金流向:(超B+大B+中B+小B)-(超S+大S+中S+小S),NODRAW;
STICKLINE(资金流向>0,0,资金流向,2,0),COLORRED;
STICKLINE(资金流向<0,0,资金流向,2,0),COLORCYAN;
近5日流向:SUM(资金流向,5),NODRAW;
近10日流向:SUM(资金流向,10),NODRAW;
```

### ZJQDL  资金驱动力(系统)

``` pascal
超B:=L2_AMO(0,2)/10000.0;
大B:=L2_AMO(1,2)/10000.0;
中B:=L2_AMO(2,2)/10000.0;
小B:=L2_AMO(3,2)/10000.0;
超S:=L2_AMO(0,3)/10000.0;
大S:=L2_AMO(1,3)/10000.0;
中S:=L2_AMO(2,3)/10000.0;
小S:=L2_AMO(3,3)/10000.0;
净流入:(超B+大B+中B+小B)-(超S+大S+中S+小S);
大宗净流入:(超B+大B)-(超S+大S);
```

### ZJBY  资金搏弈(系统)

``` pascal
超B:=L2_AMO(0,2)/10000.0;
大B:=L2_AMO(1,2)/10000.0;
中B:=L2_AMO(2,2)/10000.0;
小B:=L2_AMO(3,2)/10000.0;
超S:=-L2_AMO(0,3)/10000.0;
大S:=-L2_AMO(1,3)/10000.0;
中S:=-L2_AMO(2,3)/10000.0;
小S:=-L2_AMO(3,3)/10000.0;
净流入:(超B+大B+中B+小B)+(超S+大S+中S+小S),NODRAW;
超大单:(超B)+(超S);
大单:(大B)+(大S);
中单:(中B)+(中S);
小单:(小B)+(小S);
```

### DDX  大单动向(系统)

``` pascal
N	2.00	500.00	10.00
```

``` pascal
大单动向:(LARGEINTRDVOL-LARGEOUTTRDVOL)*10000/FINANCE(7),NODRAW;
NOTEXT1:MA(大单动向,N)*3;
STICKLINE(大单动向>0,0,大单动向,2,0),COLORRED;
STICKLINE(大单动向<0,0,大单动向,2,0),COLORCYAN;
```

``` pascal
DDX指标称为大单动向指标,基于LEVEL2数据的逐单分析,用大单买入净量除以流通盘,这是一个短中线兼顾的技术指标。
DDX红绿柱线表示当日大单买入净量占流通盘的百分比(估计值)，红柱表示大单买入量较大，绿柱表示大单卖出量较大，MA1是DDX的N日均值(参数N可调,默认参数为10)。

指标用法:
(1)如果当日红绿柱线为红色表示当日大单买入较多，反之如果当日红绿柱线为绿色表示大单卖出较多。
(2)可以在趋势导航条中的DDE决策中对DDX由大到小排序。
(3)研判时可结合DDE系列指标组中的其它指标及SUP系列指标 (DDE深度数据决策系列指标包含DDX、DDY、DDZ；SUP主力资金系列指标包含SUPL、SUPV、SUPH) 


```

### DDY  涨跌动因(系统)

``` pascal
N	2.00	500.00	10.00
```

``` pascal
涨跌动因:IF(TRADENUM>0,(TRADEOUTNUM-TRADEINNUM)*100/TRADENUM,0),NODRAW;
NOTEXT1:MA(涨跌动因,N)*3;
STICKLINE(涨跌动因>0,0,涨跌动因,2,0),COLORRED;
STICKLINE(涨跌动因<0,0,涨跌动因,2,0),COLORCYAN;
```

``` pascal
DDY指标称为涨跌动因指标, 基于LEVEL2数据的逐单分析,用卖出买入单数差除以总的成交单数。
DDY红绿柱线是卖出成交单数和买入成交单数的差占总成交比数的比例(估算值)，MA1是DDY的N日均值(参数N可调,默认参数为10)。
原理说明:对一笔成交来说,有对应的买单卖单,如果买单数量少,对应的卖单数量多,表示买单的平均每笔成交量要大；通过对股票总的买单数与卖单数进行统计来确定股票的涨跌动因。

指标用法:
(1)如果当日红绿柱线为红色表示当日单数差为正，大单买入较多，反之如果当日红绿柱线为绿色表示当日单数差为负，大单卖出较多。
(2)可以在趋势导航条中的DDE决策中对DDY由大到小排序。
(3)研判时可结合DDE系列指标组中的其它指标及SUP系列指标 (DDE深度数据决策系列指标包含DDX、DDY、DDZ；SUP主力资金系列指标包含SUPL、SUPV、SUPH) 。


```

### DDZ  大单差分(系统)

``` pascal
大单差分:IF(TRADENUM>0,(LARGETRDINNUM-LARGETRDOUTNUM)/TRADENUM*100,0),NODRAW;
DDZ1:=大单差分*7;
DDZ2:=大单差分*3;
DRAWBAND(DDZ1,RGB(255,32,32),DDZ2,RGB(0,224,224));
```

``` pascal
DDZ指标称为大单差分指标, 基于LEVEL2数据的逐单分析, 用卖出买入单数差除以卖出买入单数之和求得大单差分值,取大单差分值乘以7为DDZ1, 取大单差分值乘以3为DDZ2,依DDZ1与DDZ2的值画出彩带。

指标用法:
(1)红色彩带表示了大资金买入强度，对应色带越宽、越高表示买入强度越大;当红色彩带突然升高放宽时往往预示短线将快速上涨。绿色彩带表示了大资金买出强度，对应色带越宽、越低表示买出强度越大;当彩带突然回落放宽时往往预示短线将快速下跌。
(2)可以在趋势导航条中的DDE决策中对DDZ由大到小排序。
(3)研判时可结合DDE系列指标组中的其它指标及SUP系列指标 (DDE深度数据决策系列指标包含DDX、DDY、DDZ；SUP主力资金系列指标包含SUPL、SUPV、SUPH) 。


```

### DDF  大单频率(系统)

``` pascal
N	2.00	500.00	10.00
```

``` pascal
大单频率:IF(TRADENUM>0,LARGETRDINNUM*100/TRADENUM,0),NODRAW;
NOTEXT1:MA(大单频率,N)*2;
STICKLINE(1,0,大单频率,2,0);
```

``` pascal
DDF指标称为大单频率指标, 基于LEVEL2数据的逐单分析, 用买入大单数差除以总的成交单数。


```

### SUPL  主力集散线(系统)

``` pascal
N	2.00	500.00	10.00
```

``` pascal
主力集散线:SUM((LARGEINTRDVOL-LARGEOUTTRDVOL)*10000/FINANCE(7),0),LINETHICK2;
MA1:MA(主力集散线,N),COLORBROWN;
```

``` pascal
SUPL指标称为主力资金线指标, 基于LEVEL2数据的逐单分析, 用大单买入净量的历史累计和计算主力资金线值, 这是一个中长线的技术指标；MA1是主力资金线值的N日均值(参数N可调,默认参数为10)。

指标用法:
(1)当主力资金线持续向上走时,主力资金流入;反之,主力资金流出。
(2)研判时可结合SUP系列指标组中的其它指标及DDE系列指标 (SUP主力资金系列指标包含SUPL、SUPV、SUPH；DDE深度数据决策系列指标组包含DDX、DDY、DDZ) 


```

### SUPV  主力净买量(系统)

``` pascal
主力净买量:(LARGEINTRDVOL-LARGEOUTTRDVOL);
主力买量:LARGEINTRDVOL,COLORRED,NODRAW;
主力卖量:LARGEOUTTRDVOL,COLORGREEN,NODRAW;
STICKLINE(1,0,IF(主力买量>0,VOL,0),2,0),COLORBROWN;
STICKLINE(1,0,IF(主力卖量>0,-VOL,0),2,0),COLORBROWN;
STICKLINE(1,0,主力买量,2,0),COLORRED;
STICKLINE(1,0,(-1*主力卖量),2,0),COLORGREEN;
```

``` pascal
SUPV指标称为主力净买量, 基于LEVEL2数据的逐单分析,分别计算出买量,主力买量,卖量,主力卖量,主力净买量。

指标用法:
(1)柱状图上面红色为主力买量,上面棕色为总买量,下面绿色为主力卖量,下面棕色为总卖量;通过红色柱状与绿色柱状的长度的比较确定主力买量与主力卖量的强弱,通过红色柱状占上面棕色柱状的比值,确定主力买量占总买量的比值, 通过绿色柱状占下面棕色柱状的比值,确定主力卖量占?
卖量的比值。
(2)研判时可结合SUP系列指标组中的其它指标及DDE系列指标 (SUP主力资金系列指标包含SUPL、SUPV、SUPH；DDE深度数据决策系列指标包含DDX、DDY、DDZ) 。


```

### SUPH  主力活跃度(系统)

``` pascal
TMP:=LARGEINTRDVOL-LARGEOUTTRDVOL;
主力活跃度:(LARGEINTRDVOL+LARGEOUTTRDVOL)*10000/(2*FINANCE(7)),NODRAW;
STICKLINE(TMP>0,0,主力活跃度,2,0),COLORLIRED;
STICKLINE(TMP=0,0,主力活跃度,2,0),COLORYELLOW;
STICKLINE(TMP<0,0,主力活跃度,2,0),COLORLIGREEN;
```

``` pascal
SUPH指标称为主力活跃度, 基于LEVEL2数据的逐单分析,用逐笔成交大单之和除以2倍流通盘。

指标用法:
(1)柱状图为红色表示当逐笔成交买入大单大于逐笔成交卖出大单, 柱状图为绿色表示当逐笔成交买入大单小于逐笔成交卖出大单,通过观察柱状图的颜色及长度来确定主力活跃度。
(2)研判时可结合SUP系列指标组中的其它指标及DDE系列指标 (SUP主力资金系列指标包含SUPL、SUPV、SUPH；DDE深度数据决策系列指标包含DDX、DDY、DDZ) 


```

### SUPAMO  主力资金线(系统)

``` pascal
主力资金线:(L2_AMO(0,0)+L2_AMO(1,0)-L2_AMO(0,1)-L2_AMO(1,1))/10000.0,LINETHICK2;
```

``` pascal
SUPAMO指标称为主力净流入, 基于LEVEL2数据的逐单分析,表示每天的主力资金的流入流出量的净额(元)


```

### DDE排序  DDE,用于排序(系统)

``` pascal
DDX:(LARGEINTRDVOL-LARGEOUTTRDVOL)*10000/FINANCE(7);
DDY:IF(TRADENUM>0,(TRADEOUTNUM-TRADEINNUM)*100/TRADENUM,0);
DDZ:IF(TRADENUM>0,(LARGETRDINNUM-LARGETRDOUTNUM)/TRADENUM*100,0);
```

### SUP排序  SUP,用于排序(系统)

``` pascal
SUPL:SUM((LARGEINTRDVOL-LARGEOUTTRDVOL)*10000/FINANCE(7),0);
SUPV:(LARGEINTRDVOL-LARGEOUTTRDVOL);
SUPH:(LARGEINTRDVOL+LARGEOUTTRDVOL)*10000/(2*FINANCE(7));
SUPAMO:(L2_AMO(0,0)+L2_AMO(1,0)-L2_AMO(0,1)-L2_AMO(1,1))/10000.0;
```

### DDE力度  DDE力度,用于排序(系统)

``` pascal
主力买力度:LARGEINTRDVOL*100/VOL;
主力卖力度:LARGEOUTTRDVOL*100/VOL;
```

## 条件选股公式

### UPN  连涨数天(系统)

``` pascal
N	1.00	50.00	3.00
```

``` pascal
UP3:UPNDAY(CLOSE,N);
```

``` pascal
连续数天的涨势显示了多方上攻的痕迹。

```

### DOWNN  连跌数天(系统)

``` pascal
N	1.00	50.00	3.00
```

``` pascal
DOWN3:DOWNNDAY(CLOSE,N);
```

``` pascal
连续数天的跌势显示了空方下挫的痕迹。

```

### BIAS买入  乖离率买入条件选股(系统)

``` pascal
N	1.00	250.00	12.00
LL	0.00	40.00	6.00
```

``` pascal
(CLOSE-MA(CLOSE,N))/MA(CLOSE,N)*100+LL<0;
```

### KD买入  KD买入条件选股(系统)

``` pascal
N	1.00	40.00	9.00
M1	2.00	10.00	3.00
M2	2.00	10.00	3.00
```

``` pascal
RSV:=(CLOSE-LLV(LOW,N))/(HHV(HIGH,N)-LLV(LOW,N))*100;
K:=SMA(RSV,M1,1);
D:=SMA(K,M2,1);
KD:CROSS(K,D)&&K<20;
```

### MSTAR  早晨之星(系统)

``` pascal
STAR:REF(CLOSE,2)/REF(OPEN,2)<0.95&&
REF(OPEN,1)<REF(CLOSE,2)&&
ABS(REF(OPEN,1)-REF(CLOSE,1))/REF(CLOSE,1)<0.03&&
CLOSE/OPEN>1.05&&CLOSE>REF(CLOSE,2);
```

``` pascal
K线模式早晨之星，指示见底反弹。

```

### W&R买入  威廉指标买入条件选股(系统)

``` pascal
N	2.00	100.00	14.00
LL	60.00	100.00	80.00
```

``` pascal
CROSS(LL,WR(N,N));
```

### MTM买入  MTM买入条件选股(系统)

``` pascal
N	1.00	50.00	6.00
```

``` pascal
IMTM:CROSS(MTM(N,N),0);
```

### KDJ买入  KDJ买入条件选股(系统)

``` pascal
N1	2.00	100.00	9.00
N2	2.00	40.00	3.00
N3	2.00	40.00	3.00
```

``` pascal
RSV:=(CLOSE-LLV(LOW,N1))/(HHV(HIGH,N1)-LLV(LOW,N1))*100;
K:=SMA(RSV,N2,1);
D:=SMA(K,N3,1);
J:=3*K-2*D;
CROSS(J,0);
```

### SWORD  剑(系统)

``` pascal
AA:=VOL>REF(VOL,1)||VOL>CAPITAL;
BB:=OPEN>=(REF(HIGH,1))&&REF(HIGH,1)>(REF(HIGH,2)*1.06);
CC:=CLOSE>(REF(CLOSE,1))-(REF(CLOSE,1)*0.01);
DD:=CLOSE<(HIGH*0.965) && HIGH>(OPEN*1.05);
EE:=LOW<OPEN && LOW<CLOSE &&  HIGH>(REF(CLOSE,1)*1.06);
FF:=(HIGH-(MAX(OPEN,CLOSE)))/2>(MIN(OPEN,CLOSE))-LOW;
GG:=(ABS(OPEN-CLOSE))/2<(MIN(OPEN,CLOSE)-LOW);
STAR:AA&&BB&&CC&&DD&&EE&&FF&&GG;
```

``` pascal
出鞘利剑，冲破了空头束缚的阴影

```

### TLFZ  天量法则(系统)

``` pascal
STAR:CLOSE>OPEN&&HHV(CLOSE,50)=CLOSE&&DYNAINFO(37)>0.1&&
DYNAINFO(13)<0.14;
```

``` pascal
量于价先行，冲天大量，预示了行情的好转

```

### GREEN4  四串阴(系统)

``` pascal
STAR:EVERY(CLOSE<OPEN,4);
```

``` pascal
连续数天的跌势显示了空方下挫的痕迹。

```

### RED4  四串阳(系统)

``` pascal
A:EVERY(CLOSE>OPEN,4);
```

``` pascal
连续数天的涨势显示了多方上攻的痕迹。

```

### CSFR  出水芙蓉(系统)

``` pascal
S	1.00	60.00	20.00
M	1.00	60.00	40.00
N	1.00	60.00	60.00
```

``` pascal
AAA:=CLOSE>OPEN;
BBB:=AAA&&CLOSE>MA(CLOSE,S)&&CLOSE>MA(CLOSE,M)&&CLOSE>MA(CLOSE,N);
CCC:=BBB&&OPEN<MA(CLOSE,M)&&OPEN<MA(CLOSE,N);
CSFR:CCC&&(CLOSE-OPEN)>0.0618*CLOSE;
```

``` pascal
阳线穿过20、40、60日季均线，展示了多方上功的实力和决心

```

### NHIGH  近日创历史新高(系统)

``` pascal
N	1.00	60.00	3.00
```

``` pascal
HHV(HIGH,N)=HHV(HIGH,0);
```

``` pascal
历史的新高，既反映了行情的火爆，也提醒投资者小心见顶回落的必要

```

### NLOW  近日创历史新低(系统)

``` pascal
N	1.00	60.00	3.00
```

``` pascal
LLV(LOW,N)=LLV(LOW,0);
```

``` pascal
历史新低，既反映了行情的冷淡，也提醒投资者关注市场底部的到来

```

### XRDS  旭日初升(系统)

``` pascal
N	20.00	250.00	120.00
```

``` pascal
BUY1:=LAST(CLOSE<MA(CLOSE,N),0,5);
BUYIT:CLOSE>MA(CLOSE,N)&&VOL>MA(VOL,5)*2&&BUY1;
```

``` pascal
长期潜伏于年线之下的股票，终于露出了行动的痕迹

```

### QTDS  蜻蜓点水(系统)

``` pascal
N	20.00	250.00	120.00
```

``` pascal
BUY1:=LAST(CLOSE>MA(CLOSE,N),0,5);
BUY2:=EXIST(CLOSE<MA(CLOSE,N),5);
BUYIT:USEDDATANUM>N+50 && CLOSE>MA(CLOSE,N) && BUY1 && BUY2;
```

``` pascal
个股跌破半年线后并未大幅下滑，仅仅在半年线处短暂停留便如弹簧般迅速弹起，犹如蜻蜓般掠过湖面

```

### A001  低动态市盈率选股(系统)

``` pascal
N	5.00	30.00	20.00
```

``` pascal
DYNAINFO(39)>0 AND DYNAINFO(39)<=N;
```

``` pascal
选择市盈率较小的股票

```

### A003  营业利润率选股(系统)

``` pascal
N	1.00	100.00	50.00
```

``` pascal
FINANCE(20)>0 && FINANCE(23)/FINANCE(20)>N/100;
```

### A004  市净率选股(系统)

``` pascal
N	1.00	50.00	5.00
```

``` pascal
FINANCE(34)>0 AND CLOSE/FINANCE(34)<N;
```

### A005  次新股选股(系统)

``` pascal
N	1.00	200.00	60.00
```

``` pascal
FINANCE(42)<N;
```

### A006  PEG选股(系统)

``` pascal
PE:=DYNAINFO(39);
EPSRATE:=FINANCE(43);
PE>0 && PE<50 && EPSRATE>0 && PE/EPSRATE<1;
```

### A008  巴菲特选股(系统)

``` pascal
N1	1.00	100.00	40.00
N2	1.00	100.00	5.00
N3	1.00	100.00	15.00
```

``` pascal
A1:=(FINANCE(20)-FINANCE(21) )/FINANCE(20)*100>N1;{销售毛利率}
A2:=FINANCE(30)/FINANCE(20)*100>N2;{净利率}
A3:=FINANCE(30)/FINANCE(19)*100>N3;{净资产收益率}
A1 AND A2 AND A3;
```

### A011  可能的指标股或标的股(系统)

``` pascal
天数	1.00	1000.00	20.00
市值	1.00	1000.00	30.00
天数2	1.00	1000.00	60.00
换手	1.00	1000.00	25.00
股本	1.00	1000.00	3.00
```

``` pascal
AAA:=BARSLASTCOUNT(FINANCE(7)*CLOSE>市值*10000*10000)>=天数;
BBB:=(10000*(SUM(VOL,天数2))/FINANCE(7))>换手;
CCC:=(FINANCE(7)>股本*10000*10000);
AAA&&BBB&&CCC;
```

### B003  内外盘选股(上涨)(系统)

``` pascal
(DYNAINFO(23)>DYNAINFO(22)) AND (DYNAINFO(7)>DYNAINFO(3));
```

### B004  内外盘选股(下跌)(系统)

``` pascal
(DYNAINFO(22)>DYNAINFO(23)) AND (DYNAINFO(7)<DYNAINFO(3));
```

### B005  盘中活跃低价股(系统)

``` pascal
价格	0.00	100.00	3.00
最低涨幅	-2.00	30.00	-1.00
量比	1.50	300.00	2.00
内外比	0.00	100.00	0.50
```

``` pascal
DYNAINFO(7)<价格 AND DYNAINFO(14)>(最低涨幅/100) AND DYNAINFO(14)<0.2 AND DYNAINFO(17)>量比 AND (SELLVOL/BUYVOL)<内外比;
```

### B006  盘中分时出现金叉(系统)

``` pascal
DYNAINFO(7)>MAX(DYNAINFO(11)+0.01,DYNAINFO(11)*1.001) AND DYNAINFO(25)<DYNAINFO(11);
```

### B007  当前沪深涨跌停选股(系统)

``` pascal
涨跌停类型	0.00	5.00	0.00
包括一字板	0.00	1.00	1.00
```

``` pascal
ISST股:=NAMEINCLUDE('ST');
涨停10:=NOT(ISST股) AND DYNAINFO(5)=ZTPRICE(DYNAINFO(3),0.1) AND DYNAINFO(5)>0;
涨停5:=ISST股 AND DYNAINFO(5)=ZTPRICE(DYNAINFO(3),0.05) AND DYNAINFO(5)>0;
所有涨停:=(涨停10 OR 涨停5) AND (包括一字板 OR (NOT(包括一字板) AND DYNAINFO(5)!=DYNAINFO(6)));
当前涨停:=所有涨停 AND MAX(DYNAINFO(20),DYNAINFO(7))=DYNAINFO(5) AND DYNAINFO(59)<1;
仅盘中涨停:=所有涨停 AND NOT(当前涨停);
跌停10:=NOT(ISST股) AND DYNAINFO(6)=DTPRICE(DYNAINFO(3),0.1) AND DYNAINFO(6)>0;
跌停5:=ISST股 AND DYNAINFO(6)=DTPRICE(DYNAINFO(3),0.05) AND DYNAINFO(6)>0;
所有跌停:=(跌停10 OR 跌停5) AND (包括一字板 OR (NOT(包括一字板) AND DYNAINFO(5)!=DYNAINFO(6)));
当前跌停:=所有跌停 AND MIN(DYNAINFO(21),DYNAINFO(7))=DYNAINFO(6) AND DYNAINFO(58)<1;
仅盘中跌停:=所有跌停 AND NOT(当前跌停);
涨停RET:=IF(涨跌停类型=0,所有涨停,IF(涨跌停类型=1,当前涨停,仅盘中涨停));
跌停RET:=IF(涨跌停类型=3,所有跌停,IF(涨跌停类型=4,当前跌停,仅盘中跌停));
IF(涨跌停类型<3,涨停RET,跌停RET);
```

### DTPL  均线多头排列(系统)

``` pascal
N	1.00	500.00	5.00
N1	1.00	500.00	10.00
N2	1.00	500.00	20.00
N3	1.00	500.00	30.00
```

``` pascal
A1:=MA(CLOSE,N);
A2:=MA(CLOSE,N1);
A3:=MA(CLOSE,N2);
A4:=MA(CLOSE,N3);
CLOSE>A1 AND A1>A2 AND A2>A3 AND A3>A4 AND CLOSE>OPEN;
```

``` pascal
均线系统呈多头排列,多方占据一定优势.

```

### KTPL  均线空头排列(系统)

``` pascal
N	1.00	500.00	5.00
N1	1.00	500.00	10.00
N2	1.00	500.00	20.00
N3	1.00	500.00	30.00
```

``` pascal
A1:=MA(CLOSE,N);
A2:=MA(CLOSE,N1);
A3:=MA(CLOSE,N2);
A4:=MA(CLOSE,N3);
CLOSE<A1 AND A1<A2 AND A2<A3 AND A3<A4 AND CLOSE<OPEN;
```

``` pascal
均线系统呈空头排列,这时的形势不利与多方迅速组织起强有力的反攻.

```

### QSZL  强势整理(系统)

``` pascal
M	1.00	20.00	5.00
N	1.00	20.00	2.00
```

``` pascal
A1:=ABS(CLOSE-OPEN)/OPEN<0.015;
A2:=COUNT(A1,N)=N;
A3:=REF(OPEN,N)<REF(CLOSE,N) AND 
REF(CLOSE,N)/REF(CLOSE,N+1)>1+M/100;
A2 AND A3;
```

``` pascal
强势整理:一根实体超过5%的长阳,后面跟2个振幅不超过1.5%的K线

```

### W-103  高开大阴线(系统)

``` pascal
N	1.00	20.00	6.00
M	1.00	10.00	4.00
```

``` pascal
OPEN/REF(CLOSE,1)>=1+M/100 && CLOSE/OPEN<=1-N/100;
```

``` pascal
收盘为高开大阴线：跳空高开m%,当日股价较开盘价跌幅大于n%

```

### W-104  低开大阳线(系统)

``` pascal
N	1.00	20.00	6.00
M	1.00	10.00	4.00
```

``` pascal
OPEN/REF(CLOSE,1)<=1-M/100 && CLOSE/OPEN>=1+N/100;
```

``` pascal
收盘为低开大阳线：今日低开m% 且收盘价相对开盘价上涨大于n%,

```

### W-105  跳空缺口选股(系统)

``` pascal
HIGH<(REF(LOW,1)-0.001) || LOW>(REF(HIGH,1)+0.001);
```

### BIAS卖出  乖离率卖出条件选股(系统)

``` pascal
N	1.00	250.00	12.00
M	1.00	250.00	12.00
```

``` pascal
100*(CLOSE-MA(CLOSE,N))/MA(CLOSE,N)>M;
```

### BOLL买入  布林带买入条件选股(系统)

``` pascal
N	5.00	100.00	20.00
S	0.00	10.00	2.00
```

``` pascal
MID :=  MA(CLOSE,N);
UPPER:= MID+S*STD(CLOSE,N);
LOWER:= MID-S*STD(CLOSE,N);
CROSS(CLOSE,LOWER);
```

``` pascal
收盘价由下向上穿越BOLL下轨(买入)

```

### BOLL卖出  布林带卖出条件选股(系统)

``` pascal
N	5.00	100.00	20.00
PP	0.00	10.00	2.00
```

``` pascal
MID :=  MA(CLOSE,N);
UPPER:= MID+PP*STD(CLOSE,N);
LOWER:= MID-PP*STD(CLOSE,N);
CROSS(UPPER,CLOSE);
```

``` pascal
收盘价向下突破上限upper，为卖出时机

```

### KD卖出  KD卖出条件选股(系统)

``` pascal
N	1.00	100.00	9.00
N1	1.00	100.00	3.00
N2	1.00	100.00	3.00
N3	1.00	100.00	80.00
```

``` pascal
RSV:= (CLOSE-LLV(LOW,N))/(HHV(HIGH,N)-LLV(LOW,N))*100;
K:=SMA(RSV,N1,1);
D:=SMA(K,N2,1);
CROSS(D,K) AND D>N3;
```

``` pascal
K线向下突破线D，且K值在80以上，卖出信号

```

### KDJ卖出  KDJ卖出条件选股(系统)

``` pascal
N1	1.00	100.00	9.00
N2	1.00	100.00	3.00
N3	1.00	100.00	3.00
```

``` pascal
RSV:=(CLOSE-LLV(LOW,N1))/(HHV(HIGH,N1)-LLV(LOW,N1))*100;
K:=SMA(RSV,N2,1);
D:=SMA(K,N3,1);
J:=3*K-2*D;
CROSS(100,J);
```

``` pascal
KDJ指标共绘制三条线，其中：
J线向下突破零线，卖出信号

```

### MA买入  均线买入条件选股(系统)

``` pascal
SHORT	1.00	100.00	5.00
LONG	2.00	300.00	20.00
```

``` pascal
CROSS(MA(CLOSE,SHORT),MA(CLOSE,LONG));
```

``` pascal
短期均线从下向上穿越长期均线.
短期均线参数为SHORT,长期均线参数为LONG

```

### MA卖出  均线卖出条件选股(系统)

``` pascal
N	1.00	100.00	10.00
M	2.00	300.00	20.00
```

``` pascal
CROSS(MA(CLOSE,M),MA(CLOSE,N));
```

``` pascal
长期均线从上往下交叉短期均线为卖出信号.

```

### MACD买入  MACD买入点条件选股(系统)

``` pascal
SHORT	5.00	200.00	12.00
LONG	20.00	200.00	26.00
M	2.00	200.00	9.00
```

``` pascal
DIFF := EMA(CLOSE,SHORT) - EMA(CLOSE,LONG);
DEA  := EMA(DIFF,M);
CROSS(DIFF,DEA);
```

``` pascal
分析MACD柱状线，由绿变红(负变正)，买入信号。DIFF与DEA形成金叉时为买入信号.

```

### MACD卖出  MACD卖出条件选股(系统)

``` pascal
SHORT	5.00	200.00	12.00
LONG	20.00	200.00	26.00
M	2.00	200.00	9.00
```

``` pascal
DIFF := EMA(CLOSE,SHORT) - EMA(CLOSE,LONG);
DEA  := EMA(DIFF,M);
CROSS(DEA ,DIFF);
```

``` pascal
分析MACD柱状线，由红变绿(正变负)，卖出信号。DEA与DIFF形成死叉时为卖出信号.

```

### MTM卖出  MTM卖出条件选股(系统)

``` pascal
N	1.00	100.00	6.00
N1	1.00	100.00	6.00
```

``` pascal
CROSS(0,MA(CLOSE-REF(CLOSE,N),N1));
```

``` pascal
MTMMA向下突破零，卖出信号

```

### RSI买入  RSI买入条件选股(系统)

``` pascal
N	2.00	100.00	6.00
LL	0.00	100.00	20.00
```

``` pascal
LC:= REF(CLOSE,1);
RSI1:=SMA(MAX(CLOSE-LC,0),N,1)/SMA(ABS(CLOSE-LC),N,1)*100;
CROSS(RSI1,LL);
```

### RSI卖出  RSI卖出条件选股(系统)

``` pascal
N	2.00	100.00	6.00
LL	0.00	100.00	80.00
```

``` pascal
LC := REF(CLOSE,1);
RSI1:=SMA(MAX(CLOSE-LC,0),N,1)/SMA(ABS(CLOSE-LC),N,1)*100;
CROSS(LL,RSI1);
```

``` pascal
RSI从高位区域下跌,预示股价高,有回调要求.

```

### SAR买入  抛物转向买入条件选股(系统)

``` pascal
N	1.00	50.00	10.00
STEP	1.00	5.00	2.00
MAXP	5.00	80.00	20.00
```

``` pascal
SARTURN(N,STEP,MAXP)=1;
```

### SAR卖出  抛物转向卖出条件(系统)

``` pascal
N	1.00	50.00	10.00
STEP	1.00	5.00	2.00
MAXP	5.00	80.00	20.00
```

``` pascal
SARTURN(N,STEP,MAXP)=-1;
```

### W&R卖出  威廉指标卖出条件选股(系统)

``` pascal
N	1.00	100.00	14.00
M	1.00	100.00	20.00
```

``` pascal
WR:=100*(HHV(HIGH,N)-CLOSE)/(HHV(HIGH,N)-LLV(LOW,N));
CROSS(M,WR);
```

``` pascal
威廉指标向下突破某一区域(20)为卖出信号

```

### RUBLINE  揉搓线(系统)

``` pascal
N	50.00	100.00	50.00
```

``` pascal
A1:=(REF(H,1)-MAX(REF(C,1),REF(O,1)))/(REF(H,1)-REF(L,1))*100>N;{上影线占K线的N%以上}
A2:=(MIN(O,C)-L)/(H-L)*100>N;{下影线占K线的N%以上}
A3:=ABS(C-REF(C,1))/MIN(C,REF(C,1))*100<2;{下影K的跌幅不能超过2%}
A4:=REF(C,2)>REF(C,3);{揉搓形态前收涨}
A5:=V<REF(V,1);{缩量}
A7:A1 AND A2 AND A3 AND A4 AND A5;
```

### SP  低点搜寻(系统)

``` pascal
N	1.00	20.00	5.00
```

``` pascal
W:=MA((LLV(LOW,45)-CLOSE)/(HHV(HIGH,45)-LLV(LOW,45))*100,N);
CROSS(-5,W);
```

### TP  突破(系统)

``` pascal
N1	1.00	100.00	5.00
N2	1.00	100.00	10.00
N3	1.00	100.00	30.00
```

``` pascal
M1:=MA(C,N1);{短期参数：5}
M2:=MA(C,N2);{中期参数：10}
M3:=MA(C,N3);{长期参数：30}
{以下计算交叉点距今的天数}
D1:=BARSLAST(CROSS(M1,M2));{短上穿中}
D2:=BARSLAST(CROSS(M1,M3));{短上穿长}
D3:=BARSLAST(CROSS(M2,M3));{中上穿长}
T1:=CROSS(M2,M3);{今天中线上穿长线}
T2:=D1>=D2 AND D2>=D3;{交叉按指定的先后出现}
T3:=COUNT(CROSS(M2,M1) OR CROSS(M3,M2) OR CROSS(M3,M1),D1)=0;{中间无夹杂其它交叉}
T4:=REF(M1<M3 AND M2<M3,D1+1);{短上穿中前一天短、中线在长线之下}
JT:T1 AND T2 AND T3 AND T4;{价托确定};
```

### PRD  穿透率(大于)(系统)

``` pascal
P1	0.00	100.00	40.00
```

``` pascal
PR:(WINNER(CLOSE)-REF(WINNER(CLOSE),1))>P1*VOL/CAPITAL;
```

### PRX  穿透率(小于)(系统)

``` pascal
P1	-100.00	0.00	-40.00
```

``` pascal
PR:(WINNER(CLOSE)-REF(WINNER(CLOSE),1))<P1*VOL/CAPITAL;
```

### ASRD  浮筹比例(大于)(系统)

``` pascal
P1	0.00	100.00	90.00
```

``` pascal
ASR:100*(WINNER(CLOSE*1.1)-WINNER(CLOSE*0.9))>P1*WINNER(HHV(HIGH,0));
```

### ASRX  浮筹比例(小于)(系统)

``` pascal
P1	0.00	100.00	20.00
```

``` pascal
ASR:100*(WINNER(CLOSE*1.1)-WINNER(CLOSE*0.9))<P1*WINNER(HHV(HIGH,0));
```

### C101  N日内创新高(系统)

``` pascal
N	1.00	250.00	10.00
```

``` pascal
HHV(HIGH,N)=HHV(HIGH,0) AND BARSCOUNT(CLOSE)>=N;
```

### C102  N日内创新低(系统)

``` pascal
N	1.00	60.00	10.00
```

``` pascal
LLV(LOW,N)=LLV(LOW,0) AND BARSCOUNT(CLOSE)>=N;
```

### C103  M日内阴线多于阳线(系统)

``` pascal
N	50.00	100.00	60.00
M	3.00	300.00	30.00
```

``` pascal
COUNT(OPEN>CLOSE,M)/M >= N/100;
```

### C104  M日内阳线多于阴线(系统)

``` pascal
N	50.00	100.00	60.00
M	3.00	300.00	30.00
```

``` pascal
COUNT(OPEN<CLOSE,M)/M >= N/100;
```

### C105  N日内上涨多于下跌(系统)

``` pascal
N	50.00	100.00	60.00
M	1.00	300.00	120.00
```

``` pascal
COUNT(CLOSE>REF(CLOSE,1),M)/M >= N/100;
```

### C106  N日内下跌多于上涨(系统)

``` pascal
N	50.00	100.00	60.00
M	1.00	300.00	120.00
```

``` pascal
COUNT(CLOSE<REF(CLOSE,1),M)/M >= N/100;
```

### C107  连续N天收阳线(系统)

``` pascal
N	1.00	100.00	7.00
```

``` pascal
EVERY(CLOSE>OPEN,N);
```

### C108  连续N天收阴线(系统)

``` pascal
N	1.00	100.00	7.00
```

``` pascal
EVERY(OPEN>CLOSE,N);
```

### C128  N天内出现以涨停收盘(系统)

``` pascal
N	1.00	100.00	10.00
```

``` pascal
ZT:=(CLOSE>=ZTPRICE(REF(CLOSE,1),0.1)); { 以涨停收盘 }
ZTO:FINANCE(42)>200 AND EXIST(ZT,N); { 上市满200天,N天存在以涨停收盘 };
```

### C129  N天内出现涨停(系统)

``` pascal
N	1.00	100.00	20.00
```

``` pascal
EZT:=(HIGH>=ZTPRICE(REF(CLOSE,1),0.1)); { 出现过涨停 }
EZTO:FINANCE(42)>200 AND EXIST(EZT,N); { 上市满200天,N天内存在过涨停 };
```

### C130  N天内经常涨停(系统)

``` pascal
N	1.00	250.00	100.00
涨停天数	1.00	250.00	8.00
```

``` pascal
ZTTJ:=(CLOSE>=ZTPRICE(REF(CLOSE,1),0.1));
FINANCE(42)>200 AND COUNT(ZTTJ,N)>=涨停天数;
```

### C110  单日放量(系统)

``` pascal
N	1.00	10.00	2.00
M	1.00	100.00	15.00
```

``` pascal
A1:=MA(VOL,5);
A2:=REF(A1,1);
VOL/A2>N AND (IF((SETCODE==0||SETCODE==1),100*VOL,VOL))/CAPITAL>M;
```

### C111  阶段缩量(系统)

``` pascal
N	1.00	100.00	10.00
M	1.00	100.00	5.00
```

``` pascal
100*SUM(VOL,N)/CAPITAL<=M;
```

### C112  阶段放量(系统)

``` pascal
N	1.00	100.00	10.00
M	1.00	100.00	15.00
```

``` pascal
100*SUM(VOL,N)/CAPITAL>=M;
```

### C113  持续放量(系统)

``` pascal
M	1.00	100.00	3.00
```

``` pascal
EVERY(VOL>=REF(VOL,1),M);
```

### C114  持续缩量(系统)

``` pascal
M	1.00	100.00	3.00
```

``` pascal
COUNT(VOL<=REF(VOL,1),M)=M;
```

### C115  间隔放量(系统)

``` pascal
N	20.00	60.00	30.00
N1	0.00	100.00	4.00
N2	1.00	100.00	2.00
N3	1.00	100.00	3.00
```

``` pascal
A:=MA(VOL,5);
BARSCOUNT(CLOSE)>=N AND HHV(A,N)<N1*LLV(A,N) 
AND COUNT(VOL>N2*A,N)>N3;
```

### C116  放量上攻(系统)

``` pascal
N	0.00	10.00	1.00
N1	1.00	10.00	3.00
N2	1.00	1000.00	20.00
N3	1.00	100.00	4.00
```

``` pascal
A:= (CLOSE-REF(CLOSE,1))/REF(CLOSE,1)>=(N/100);
100*SUM(VOL,N1)/CAPITAL>=N2 
AND COUNT(VOL>REF(VOL,1),N3)=N3 AND  COUNT(A,N3)=N3;
```

### C117  温和放量上攻(系统)

``` pascal
N	2.00	10.00	5.00
```

``` pascal
A1:=CLOSE/REF(CLOSE,1);
A2:=A1>1 AND A1<1.03;
{股价小幅上扬}
B1:=VOL/REF(VOL,1);
B2:=B1>1 AND B1<2;
C1:=100*MA(VOL,N)/CAPITAL<5;
{成交量小幅上扬}
COUNT(A2 AND B2,N)/N>0.6 AND C1;
```

### C118  突然放量(系统)

``` pascal
N	1.00	300.00	10.00
M	1.00	40.00	3.00
```

``` pascal
VOL>REF(HHV(VOL,N),1)*M;
```

### C119  平台整理(系统)

``` pascal
N	1.00	100.00	30.00
N1	1.00	100.00	5.00
```

``` pascal
COUNT(CLOSE>0,0)>N && 
(HHV(CLOSE,N)-LLV(CLOSE,N))/LLV(CLOSE,N)<=(N1/100);
```

``` pascal
成交量分布比较均匀,偶尔有所放大,但马上又缩小.如果发生在底部区域,且盘整时间较长,则很有可能是庄家的吸货行为.

```

### C123  突破长期盘整(系统)

``` pascal
N	10.00	60.00	30.00
N1	5.00	50.00	5.00
```

``` pascal
REF(((HHV(HIGH,N)-LLV(LOW,N))/LLV(LOW,N)),1)<=(N1/100) 
 && CLOSE>=REF(HHV(HIGH,N),1) && BARSCOUNT(CLOSE)>N;
```

### C124  阶段强于大盘(系统)

``` pascal
N	2.00	999.00	50.00
N1	1.00	998.00	1.00
```

``` pascal
A:=SUM(IF(CURRBARSCOUNT=N,INDEXC,0),0);
B:=SUM(IF(CURRBARSCOUNT=N1,INDEXC,0),0);
E:=SUM(IF(CURRBARSCOUNT=N,CLOSE,0),0);
F:=SUM(IF(CURRBARSCOUNT=N1,CLOSE,0),0);
((F-E)/E)>(((B-A)/A)+0.01);
```

### C125  阶段弱于大盘(系统)

``` pascal
N	2.00	999.00	50.00
N1	1.00	998.00	1.00
```

``` pascal
A:=SUM(IF(CURRBARSCOUNT=N,INDEXC,0),0);
B:=SUM(IF(CURRBARSCOUNT=N1,INDEXC,0),0);
E:=SUM(IF(CURRBARSCOUNT=N,CLOSE,0),0);
F:=SUM(IF(CURRBARSCOUNT=N1,CLOSE,0),0);
((F-E)/E)<(((B-A)/A)-0.01);
```

### C126  大盘同步选股(系统)

``` pascal
N	1.00	100.00	10.00
M	5.00	100.00	50.00
```

``` pascal
COUNT((CLOSE>OPEN && INDEXC>INDEXO) || (CLOSE<OPEN && INDEXC<INDEXO),N)/N>M/100;
```

### C127  N日内强势股(系统)

``` pascal
N	1.00	100.00	20.00
M	1.00	100.00	3.00
```

``` pascal
GG:=(CLOSE-REF(OPEN,N))/REF(OPEN,N);
GGG:=IF(GG>0,GG,0);
DP:=(INDEXC-REF(INDEXO,N))/REF(INDEXO,N);
QSG:GGG/DP>=M;
```

### C131  下跌多日再放量上涨(系统)

``` pascal
A1:=REF(CLOSE,5)>REF(CLOSE,4);
A2:=REF(CLOSE,4)>REF(CLOSE,3);
A3:=REF(CLOSE,3)>REF(CLOSE,2);
A4:=REF(CLOSE,2)>REF(CLOSE,1);
A5:=CLOSE>REF(HIGH,1) AND V>REF(V,1);
RET:A1 AND A2 AND A3 AND A4 AND A5;
```

### C132  跳空高开或低开(系统)

``` pascal
N	-100.00	100.00	3.00
```

``` pascal
A:= (O>REF(H,1) AND (O-REF(C,1))/REF(C,1)*100>N);
B:= (O<REF(L,1) AND (O-REF(C,1))/REF(C,1)*100<N);
IF(N>0,A,B);
```

## 专家系统公式

### BIAS  乖离率专家系统(系统)

``` pascal
N	2.00	250.00	12.00
LL	0.00	40.00	6.00
LH	0.00	40.00	6.00
```

``` pascal
BIAS:=(CLOSE-MA(CLOSE,N))/MA(CLOSE,N)*100;
ENTERLONG:CROSS(-LL,BIAS);
EXITLONG:CROSS(BIAS,LH);
```

``` pascal
乖离率的值围绕零上下波动
1.负的乖离率越小，空头回补的可能性越大，因此，负的乖离率向下跌破买入线，为买入时机；
2.正的乖离率越大，表示短期获利越大，获利回吐的可能性越高，因此正的乖离率向上突破卖出线，为卖出时机．
参数：
N 天数，计算乖离率时用　一般12天
LL  买入线，一般-6；LH　卖出线，一般6

```

### CCI  CCI专家系统(系统)

``` pascal
N	1.00	100.00	14.00
```

``` pascal
INDEX:=CCI(N);
ENTERLONG:CROSS(INDEX,-100);
EXITLONG:CROSS(100,INDEX);
```

``` pascal
1.当CCI指标从下向上突破+100线而进入非常态区间时，表明股价脱离常态而进入异常波动阶段，中短线应及时买入，如果有较大的成交量配合，买入信号则更为可靠； 
2.当CCI指标从上向下突破－100线而进入另一个非常态区间时，表明股价的盘整阶段已经结束，将进入一个比较长的寻底过程，投资者应以持币观望为主； 
3.当CCI指标从上向下突破+100线而重新进入常态区间时，表明股价的上涨阶段可能结束，将进入一个比较长时间的盘整阶段，投资者应及时逢高卖出股票； 
4.当CCI指标从下向上突破－100线而重新进入常态区间时，表明股价的探底阶段可能结束，有将进入一个盘整阶段，投资者可以逢低少量买入股票； 
5.当CCI指标在+100线～－100线的常态区间里运行时,投资者则可以用KDJ、WR等其它超买超卖指标进行研判。
参数：N　计算CCI时用，一般14天

```

### DMI  趋向专家系统(系统)

``` pascal
N	2.00	80.00	14.00
```

``` pascal
MTR:=SUM(MAX(MAX(HIGH-LOW,ABS(HIGH-REF(CLOSE,1))),ABS(LOW-REF(CLOSE,1))),N);
HD :=HIGH-REF(HIGH,1);
LD :=REF(LOW,1)-LOW;
PDM:=SUM(IF(HD>0&&HD>LD,HD,0),N);
MDM:=SUM(IF(LD>0&&LD>HD,LD,0),N);
PDI:=PDM*100/MTR;
MDI:=MDM*100/MTR;
ENTERLONG:CROSS(PDI,MDI);
EXITLONG:CROSS(MDI,PDI);
```

``` pascal
市场行情趋向明显时，效果理想。
PDI(上升方向线)　MDI(下降方向线)
1.PDI线从下向上突破MDI线，显示有新多头进场，为买进信号
2.MDI线从下向上突破PDI线，显示有新空头进场，为卖出信号
参数：N　天数　计算趋向值用

```

### KD  KD指标专家系统(系统)

``` pascal
N	1.00	40.00	9.00
M1	2.00	10.00	3.00
M2	2.00	10.00	3.00
```

``` pascal
WRSV:=(CLOSE-LLV(LOW,N))/(HHV(HIGH,N)-LLV(LOW,N))*100;
WK:=SMA(WRSV,M1,1);
D:=SMA(WK,M2,1);
ENTERLONG:CROSS(WK,D)&&WK<20;
EXITLONG:CROSS(D,WK)&&WK>80;
```

``` pascal
1.线K向上突破线D，且K值在20以下，买进信号；
2.线K向下跌破线D，且K值在80以上，卖出信号；
参数：N、M1、M2　天数，计算KD时用，一般为9、3、3

```

### BOLL  布林带专家系统(系统)

``` pascal
N	5.00	100.00	20.00
```

``` pascal
MID :=MA(CLOSE,N);
UPPER:=MID+2*STD(CLOSE,N);
LOWER:=MID-2*STD(CLOSE,N);
ENTERLONG:CROSS(CLOSE,LOWER);
EXITLONG:CROSS(CLOSE,UPPER);
```

``` pascal
一、收盘价向上突破下限，为买入信号；
二、收盘价向上突破上限，为卖出信号；
三、参数： N  天数，在计算布林带时用，一般26天
       P　一般为20，用于调整上限和下限的值

```

### KDJ  KDJ专家系统(系统)

``` pascal
N	1.00	40.00	9.00
M1	2.00	10.00	3.00
```

``` pascal
RSV:=(CLOSE-LLV(LOW,N))/(HHV(HIGH,N)-LLV(LOW,N))*100;
K:=SMA(RSV,M1,1);
D:=SMA(K,M1,1);
J:=3*K-2*D;
ENTERLONG:CROSS(J,0);
EXITLONG:CROSS(100,J);
```

``` pascal
J线向上突破零线，买入信号
J线向下跌破100，卖出信号

```

### MA  均线专家系统(系统)

``` pascal
SHORT	1.00	30.00	5.00
LONG	5.00	100.00	20.00
```

``` pascal
ENTERLONG:CROSS(MA(CLOSE,SHORT),MA(CLOSE,LONG));
EXITLONG:CROSS(MA(CLOSE,LONG),MA(CLOSE,SHORT));
```

``` pascal
一、收盘价短期均线向上突破长期均线，买入信号；
二、收盘价短期均线向下跌破长期均线，卖出信号；
三、参数：SHORT　短期天数　　LONG　长期天数。

```

### MACD  MACD专家系统(系统)

``` pascal
LONG	10.00	200.00	26.00
SHORT	2.00	200.00	12.00
M	2.00	200.00	9.00
```

``` pascal
DIFF:=EMA(CLOSE,SHORT) - EMA(CLOSE,LONG);
DEA  := EMA(DIFF,M);
MACD := 2*(DIFF-DEA);
ENTERLONG:CROSS(MACD,0);
EXITLONG:CROSS(0,MACD);
```

``` pascal
一、分析MACD柱状线，由红变绿(正变负)，卖出信号；由绿变红，买入信号；
二、参数：LONG、SHORT、M 　天数，计算MACD时用，一般26、12、9

```

### MTM  动力指标专家系统(系统)

``` pascal
WMTM:=MTM;
ENTERLONG:CROSS(WMTM,0);
EXITLONG:CROSS(0,WMTM);
```

``` pascal
参数：N 　间隔天数，也是求移动平均的天数，一般为6
1.MTMMA线向上突破零，买入信号；
2.MTMMA线向下跌破零，卖出信号；

```

### PSY  PSY心理线专家系统(系统)

``` pascal
N	2.00	50.00	12.00
LL	0.00	25.00	10.00
LH	75.00	100.00	85.00
```

``` pascal
MYPSY:=PSY(N,1);
ENTERLONG:CROSS(LL,MYPSY);
EXITLONG:CROSS(MYPSY,LH);
```

``` pascal
1.心理线向下跌破下限，买入时机；
2.心理线向上突破上限，卖出时机；
3.参数：LL 下限，一般取10 ； LH　上限，一般取85

```

### ROC  变动速率专家系统(系统)

``` pascal
N	1.00	100.00	12.00
M	1.00	20.00	6.00
```

``` pascal
WROC:=ROC(N,M);
ENTERLONG:CROSS(WROC,0);
EXITLONG:CROSS(0,WROC);
```

``` pascal
1.ROC向下跌破零，卖出信号；
2.ROC向上突破零，买入信号；
3.参数：N 间隔天数；M　计算移动平均的天数

```

### RSI  相对强弱专家系统(系统)

``` pascal
N	2.00	50.00	6.00
LL	0.00	35.00	20.00
LH	65.00	100.00	80.00
```

``` pascal
LC:=REF(CLOSE,1);
WRSI:=SMA(MAX(CLOSE-LC,0),N,1)/SMA(ABS(CLOSE-LC),N,1)*100;
ENTERLONG:CROSS(WRSI,LL);
EXITLONG:CROSS(LH,WRSI);
```

``` pascal
1.RSI向上突破下限，买入信号；
2.RSI向下跌破上限，卖出信号；
3.参数：N　统计天数，一般取6
LL 下限，一般取20
LH 上限，一般取80

```

### VR  VR容量比率专家系统(系统)

``` pascal
N	5.00	100.00	26.00
LL	0.00	80.00	70.00
LH	160.00	400.00	250.00
```

``` pascal
WVR := SUM((IF(CLOSE>OPEN,VOL,0)+IF(CLOSE=OPEN,VOL/2,0)),N)/
SUM((IF(CLOSE<OPEN,VOL,0)+IF(CLOSE=OPEN,VOL/2,0)),N)*100;
ENTERLONG:CROSS(LL,WVR);
EXITLONG:CROSS(WVR,LH);
```

``` pascal
1.一般 40至70，低位区，卖进；80至150，盘整区，持有；160至350，获利区，获利了结；
2.VR向下跌破下限，买入信号；
3.VR向上突破上限，卖出信号；
4.参数：LH 上限，一般取70；LL 下限，一般取250

```

### DPSJ  大盘随机专家系统(系统)

``` pascal
N1	2.00	60.00	18.00
N2	3.00	12.00	12.00
```

``` pascal
RSV:=(INDEXC-LLV(INDEXL,N1))/(HHV(INDEXH,N1)-LLV(INDEXL,N1))*100;
K:=SMA(RSV,N2,1);
ENTERLONG: CROSS(K,20);
EXITLONG: (CROSS(HSL,5) OR CROSS(K,80));
```

## 五彩K线公式

### KSTAR1  十字星(系统)

``` pascal
KSTAR:CLOSE=OPEN&&HIGH>LOW;
```

``` pascal
十字星由一支K线组成，有转向的意味。
顾名思义，十字星呈十字形状，开市价与收市价相同。

```

### KSTAR2  早晨之星(系统)

``` pascal
KSTAR:(REF(CLOSE,2)/REF(OPEN,2)<0.95)&&
(REF(OPEN,1) < REF(CLOSE,2))&&
(ABS(REF(OPEN,1)-REF(CLOSE,1))/REF(CLOSE,1)<0.03) && 
CLOSE/OPEN>1.05 && CLOSE>REF(CLOSE,2);
```

``` pascal
早晨之星由三支K线组成，代表可能见底回升。
第一日：在跌势中出现一支长阴烛；
第二日：裂口下跌，烛身短，可以是阴烛或阳烛。
第三日：阳烛，回升到第一支蜡烛上。

```

### KSTAR3  黄昏之星(系统)

``` pascal
KSTAR:REF(CLOSE,2)/REF(OPEN,2)>1.05&&
REF(OPEN,1)>REF(CLOSE,2)&&
ABS(REF(OPEN,1)-REF(CLOSE,1))/REF(CLOSE,1)<0.03&&
CLOSE/OPEN<0.95&&CLOSE<REF(CLOSE,2);
```

``` pascal
黄昏之星由三支K线组成，形态刚好与早晨之星相反，代表可能见顶回落。
第一日：在升势中出现一支长阳烛；
第二日：裂口上涨，烛身短，可以是阴烛或阳烛。
第三日：阴烛，回落到第一支蜡烛下。

```

### SHI1  长十字(系统)

``` pascal
KSTAR:CLOSE=OPEN&&HIGH/LOW>1.03;
```

``` pascal
长十字由一支K线组成，是十字星的一种，有较强的转向意味。
长十字呈十字形状，开市价与收市价相同，同时有较长的手部和脚部。

```

### K220  身怀六甲(系统)

``` pascal
KSTAR:ABS(REF(CLOSE,1)-REF(OPEN,1))/REF(CLOSE,1)>0.04&&
ABS(CLOSE-OPEN)/CLOSE<0.005&&
MAX(CLOSE,OPEN)<MAX(REF(CLOSE,1),REF(OPEN,1))&&
MIN(CLOSE,OPEN)>MIN(REF(CLOSE,1),REF(OPEN,1));
```

``` pascal
身怀六甲由两支K线组成，表示行情将要转向。
第一日：在上升行情中出现一支较长的阳烛，或在下跌行情中出现一支较长的阴烛；
第二日：蜡烛部分很短。

```

### K300  三个白武士(系统)

``` pascal
KSTAR:UPNDAY(CLOSE,3)&&NDAY(CLOSE,OPEN,3);
```

``` pascal
三个白武士由三支K线组成，表示可能见底回升。
三个白武士由三支阳烛组成，且每日收市价都上移。

```

### K310  三只乌鸦(系统)

``` pascal
KSTAR:DOWNNDAY(CLOSE,3)&&NDAY(OPEN,CLOSE,3);
```

``` pascal
三只乌鸦由三支K线组成，表示可能见顶回落。
三只乌鸦由三支阴烛组成，且每日收市价都下移。

```

### K380  光头阳线(系统)

``` pascal
KSTAR:HIGH=CLOSE&&HIGH>LOW;
```

``` pascal
光头阳线
最高价等于开盘价的阳线.

```

### K390  光脚阴线(系统)

``` pascal
KSTAR:LOW=CLOSE&&HIGH>LOW;
```

``` pascal
光脚阴线
最底价等于收盘价的阴线.

```

### K134  垂死十字(系统)

``` pascal
KSTAR:CLOSE=OPEN&&CLOSE=LOW&&CLOSE<HIGH;
```

``` pascal
垂死十字是十字星的一种特例，由一支K线组成，若出现在顶部就是一种可靠性较高的见顶回落形态。
垂死十字的开市价、收市价相同，并且出现在最低价范围内。

```

### K140  早晨十字星(系统)

``` pascal
KSTAR:REF(CLOSE,2)/REF(OPEN,2)<0.95&&
REF(OPEN,1)<REF(CLOSE,2)&&
REF(OPEN,1)=REF(CLOSE,1)&&
CLOSE/OPEN>1.05&&CLOSE>REF(CLOSE,2);
```

``` pascal
早晨十字是早晨之星的一种特例，有更强的见底回升趋势。
第一日：在跌势中出现一支长阴烛；
第二日：裂口下跌，烛身短，呈十字星。
第三日：阳烛，回升到第一支蜡烛上。

```

### K150  黄昏十字星(系统)

``` pascal
KSTAR:REF(CLOSE,2)/REF(OPEN,2)>1.05&&
REF(OPEN,1)>REF(CLOSE,2)&&
REF(OPEN,1)=REF(CLOSE,1)&&
CLOSE/OPEN<0.95&&CLOSE<REF(CLOSE,2);
```

``` pascal
黄昏十字是黄昏之星的一种特例，有更强的见顶回落趋势。
第一日：在升势中出现一支长阳烛；
第二日：裂口上涨，烛身短，呈十字星。
第三日：阴烛，回落到第一支蜡烛下。

```

### K160  射击之星(系统)

``` pascal
KSTAR:MIN(OPEN,CLOSE)=LOW&&
HIGH-LOW>3*(MAX(OPEN,CLOSE)-LOW)&&
CLOSE>MA(CLOSE,5);
```

``` pascal
射击之星由一支K线组成，表示可能见顶回落，其可靠性较低。
射击之星蜡烛部分较短，并且出现在底部，蜡烛上面出现一支较长的“箭”。

```

### K165  倒转锤头(系统)

``` pascal
KSTAR:MIN(OPEN,CLOSE)=LOW&&
HIGH-LOW>3*(MAX(OPEN,CLOSE)-LOW)&&
CLOSE<MA(CLOSE,5);
```

``` pascal
倒转锤头由一支K线组成，属于见底回升的转向形态。
倒转锤头有较长的手部，蜡烛部分很少，且在底部出现。

```

### K170  锤头(系统)

``` pascal
OUT:HIGH=MAX(OPEN,CLOSE)&&
HIGH-LOW>3*(HIGH-MIN(OPEN,CLOSE))&&
CLOSE<MA(CLOSE,5);
```

``` pascal
锤头由一支K线组成，属于见底回升的转向形态，其脚部越长威力越大。
锤头出现在下跌行情中，有较长的脚部，蜡烛部分很少，且在顶部出现。

```

### K180  吊颈(系统)

``` pascal
OUT:HIGH=MAX(OPEN,CLOSE)&&
HIGH-LOW>3*(HIGH-MIN(OPEN,CLOSE))&&
CLOSE>MA(CLOSE,5);
```

``` pascal
吊颈与锤头形态相同，只是吊颈出现在上升行情中，表示将见顶回落。
吊颈出现在上升行情中，有较长的脚部，蜡烛部分很少，且在顶部出现。

```

### K190  穿头破脚(系统)

``` pascal
OUT:(REF(CLOSE,1)/REF(OPEN,1)>1.03&&
CLOSE/OPEN<0.96&&
CLOSE<REF(OPEN,1)&&OPEN>REF(CLOSE,1))||
(REF(CLOSE,1)/REF(OPEN,1)<0.97&&
CLOSE/OPEN>1.04&&
CLOSE>REF(OPEN,1)&&OPEN<REF(CLOSE,1));
```

``` pascal
穿头破脚由两支K线组成，表示行情将要转向。
穿头破脚第二支蜡烛烛身部分长于第一支蜡烛且蜡烛颜色相反；若是上升行情第一支蜡烛为阳线，若是下跌行情第一支蜡烛为阴线。

```

### SWORD  剑(系统)

``` pascal
AA:=VOL>REF(VOL,1)||VOL>(CAPITAL*0.1);
BB:=OPEN>=(REF(HIGH,1))&&REF(HIGH,1)>(REF(HIGH,2)*1.06);
CC:=CLOSE>(REF(CLOSE,1))-(REF(CLOSE,1)*0.01);
DD:=CLOSE<(HIGH*0.965) && HIGH>(OPEN*1.05);
EE:=LOW<OPEN && LOW<CLOSE&&HIGH>(REF(CLOSE,1)*1.06);
FF:=(HIGH-(MAX(OPEN,CLOSE)))/2>(MIN(OPEN,CLOSE))-LOW;
GG:=(ABS(OPEN-CLOSE))/2<(MIN(OPEN,CLOSE)-LOW);
SWORDO:AA&&BB&&CC&&DD&&EE&&FF&&GG;
```

``` pascal
出鞘利剑，冲破了空头束缚的阴影

```

### CSFR  出水芙蓉(系统)

``` pascal
S	1.00	60.00	20.00
M	1.00	60.00	40.00
LL	1.00	60.00	60.00
```

``` pascal
A:=CLOSE>OPEN;
B:=A&&CLOSE>MA(CLOSE,S)&&CLOSE>MA(CLOSE,M)&&CLOSE>MA(CLOSE,LL);
CC:=B&&OPEN<MA(CLOSE,M)&&OPEN<MA(CLOSE,LL);
CSFRO:CC&&(CLOSE-OPEN)>0.0618*CLOSE;
```

``` pascal
阳线穿过20、40、60日季均线，展示了多方上功的实力和决心

```

### WYGD  乌云盖顶 (系统)

``` pascal
BACKSET( 
REF(CLOSE,1)/REF(OPEN,1)>1.03 AND 
CLOSE/OPEN<0.97 AND 
OPEN>REF(CLOSE,1) AND CLOSE<REF(CLOSE,1), 3);
```

### SGCJ  曙光初现 (系统)

``` pascal
BACKSET( 
REF(CLOSE,1)/REF(OPEN,1)<0.97 AND 
CLOSE/OPEN>1.03 AND 
OPEN<REF(CLOSE,1) AND CLOSE>REF(CLOSE,1), 3);
```

### SZTAI  十字胎 (系统)

``` pascal
BACKSET( ABS(REF(CLOSE,1)-REF(OPEN,1))/REF(CLOSE,1) > 0.04 AND 
CLOSE=OPEN AND CLOSE < MAX(REF(CLOSE,1),REF(OPEN,1)) AND 
CLOSE > MIN(REF(CLOSE,1),REF(OPEN,1)), 2);
```

### PINGDING  平顶 (系统)

``` pascal
BACKSET(ABS(HIGH-REF(HIGH,1))/HIGH<0.001,2);
```

### PINGDI  平底 (系统)

``` pascal
BACKSET((ABS(LOW-REF(LOW,1))/LOW<0.001 AND 
ABS(REF(LOW,1)-REF(LOW,2))/REF(LOW,1)<=0.001),2);
```

### DAYANZHU  大阳烛 (系统)

``` pascal
CLOSE/OPEN>1.05 AND 
HIGH/LOW < CLOSE/OPEN+0.018;
```

### DAYINGZHU  大阴烛 (系统)

``` pascal
OPEN/CLOSE > 1.05 AND 
HIGH/LOW < OPEN/CLOSE+0.018;
```

### HYFG  好友反攻 (系统)

``` pascal
BACKSET( (REF(CLOSE,1)<REF(OPEN,1) AND 
CLOSE>OPEN AND ABS(CLOSE-REF(CLOSE,1))/CLOSE<0.002),2);
```

### TKQK  跳空缺口 (系统)

``` pascal
BACKSET( HIGH<REF(LOW,1) OR LOW>REF(HIGH,1),2);
```

### SFWY  双飞乌鸦 (系统)

``` pascal
BACKSET( REF(CLOSE,1)<REF(OPEN,1) AND CLOSE<OPEN AND CLOSE/OPEN<0.98,1);
```

### SSSBQ  上升三部曲(系统)

``` pascal
BACKSET( 
REF(CLOSE,4)/REF(OPEN,4)>1.03 AND 
REF(CLOSE,3)<REF(OPEN,3) AND 
REF(CLOSE,2)<REF(OPEN,2) AND 
REF(CLOSE,1)<REF(OPEN,1) AND 
REF(LOW,4)<REF(LOW,3) AND 
REF(LOW,4)<REF(LOW,2) AND 
REF(LOW,4)<REF(LOW,1) AND 
REF(HIGH,4)>REF(HIGH,3) AND 
REF(HIGH,4)>REF(HIGH,2) AND 
REF(HIGH,4)>REF(HIGH,1) AND 
CLOSE/OPEN>1.03 AND 
CLOSE>REF(CLOSE,4), 5);
```

### XDSBQ  下跌三部曲(系统)

``` pascal
BACKSET( 
REF(CLOSE,4)/REF(OPEN,4)<0.97 AND 
REF(CLOSE,3)>REF(OPEN,3) AND 
REF(CLOSE,2)>REF(OPEN,2) AND 
REF(CLOSE,1)>REF(OPEN,1) AND 
REF(LOW,4)<REF(LOW,3) AND 
REF(LOW,4)<REF(LOW,2) AND 
REF(LOW,4)<REF(LOW,1) AND 
REF(HIGH,4)>REF(HIGH,3) AND 
REF(HIGH,4)>REF(HIGH,2) AND 
REF(HIGH,4)>REF(HIGH,1) AND 
CLOSE/OPEN<0.97 AND 
CLOSE<REF(CLOSE,4), 5);
```

### CHXY  长下影(系统)

``` pascal
(MIN(CLOSE,OPEN)-LOW)/(HIGH-LOW)>0.667;
```

### CHSY  长上影(系统)

``` pascal
(HIGH-MAX(CLOSE,OPEN))/(HIGH-LOW)>0.667,COLORBLUE;
```

### FENLI  分离(系统)

``` pascal
BACKSET( OPEN=REF(OPEN,1) AND 
(CLOSE-OPEN)*(REF(CLOSE,1)-REF(OPEN,1))<0,2);
```

## NXSD  牛熊时段(系统)

