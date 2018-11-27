## ����ָ�깫ʽ

``` pascal

```

## MA  ����(ϵͳ)

``` pascal
MA1:MA(CLOSE,M1);
MA2:MA(CLOSE,M2);
MA3:MA(CLOSE,M3);
MA4:MA(CLOSE,M4);
```

## MA2  ����(ϵͳ)

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

## ABI  ���Թ���ָ��(ϵͳ)

``` pascal
ABI:100*ABS(ADVANCE-DECLINE)/(ADVANCE+DECLINE);
MAABI:EMA(ABI,M);
```

## ADL  ����ָ��(ϵͳ)

``` pascal
ADL:SUM(ADVANCE-DECLINE,0);
MAADL:MA(ADL,M);
```

## ADR  �ǵ�����(ϵͳ)

``` pascal
ADR:SUM(ADVANCE,N)/SUM(DECLINE,N);
MAADR:MA(ADR,M);
```

## ARMS  ��ķ��ָ��(ϵͳ)

``` pascal
ARMS:EMA(ADVANCE/DECLINE,N);
MAARMS:MA(ARMS,M);
```

## BTI  ��������ָ��(ϵͳ)

``` pascal
BTI:EMA(100*ADVANCE/(ADVANCE+DECLINE),N);
MABTI:MA(BTI,M);
```

## MCL  �����ָ��(ϵͳ)

``` pascal
DIF:=ADVANCE-DECLINE;
EMA1:=EMA(DIF,N1);
EMA2:=EMA(DIF,N2);
MCL:EMA1-EMA2;
MAMCL1:EMA1;
MAMCL2:EMA2;
```

## MSI  �����ۺ�ָ��(ϵͳ)

``` pascal

```

## OBOS  ������ָ��(ϵͳ)

``` pascal
OBOS:EMA(ADVANCE-DECLINE,N);
MAOBOS:MA(OBOS,M);
```

## STIX  ָ��ƽ������(ϵͳ)

``` pascal
TBR:100*ADVANCE/(ADVANCE+DECLINE);
MATBR:EMA(TBR,M);
```

## CCI  ��Ʒ·��ָ��(ϵͳ)

``` pascal
TYP:=(HIGH+LOW+CLOSE)/3;
CCI:(TYP-MA(TYP,N))/(0.015*AVEDEV(TYP,N));
```

## KDJ  ���ָ��(ϵͳ)

``` pascal
RSV:=(CLOSE-LLV(LOW,N))/(HHV(HIGH,N)-LLV(LOW,N))*100;
K:SMA(RSV,M1,1);
D:SMA(K,M2,1);
J:3*K-2*D;
```

## KDJ-TDX  ���ָ��-��ͳ��(ϵͳ)

``` pascal

```

## MFI  �ʽ�����ָ��(ϵͳ)

``` pascal
TYP := (HIGH + LOW + CLOSE)/3;
V1:=SUM(IF(TYP>REF(TYP,1),TYP*VOL,0),N)/SUM(IF(TYP<REF(TYP,1),TYP*VOL,0),N);
MFI:100-(100/(1+V1));
```

## MTM  ������(ϵͳ)

``` pascal
MTM:CLOSE-REF(CLOSE,N);
MTMMA:MA(MTM,M);
```

## OSC  �䶯������(ϵͳ)

``` pascal
OSC:100*(CLOSE-MA(CLOSE,N));
MAOSC:EXPMEMA(OSC,M);
```

## ROC  �䶯��ָ��(ϵͳ)

``` pascal
ROC:100*(CLOSE-REF(CLOSE,N))/REF(CLOSE,N);
MAROC:MA(ROC,M);
```

## RSI  ���ǿ��ָ��(ϵͳ)

``` pascal
LC:=REF(CLOSE,1);
RSI1:SMA(MAX(CLOSE-LC,0),N1,1)/SMA(ABS(CLOSE-LC),N1,1)*100;
RSI2:SMA(MAX(CLOSE-LC,0),N2,1)/SMA(ABS(CLOSE-LC),N2,1)*100;
RSI3:SMA(MAX(CLOSE-LC,0),N3,1)/SMA(ABS(CLOSE-LC),N3,1)*100;

```

## KD  ���ָ��KD(ϵͳ)

``` pascal
RSV:=(CLOSE-LLV(LOW,N))/(HHV(HIGH,N)-LLV(LOW,N))*100;
K:SMA(RSV,M1,1);
D:SMA(K,M2,1);
```

## SKDJ  �������ָ��(ϵͳ)

``` pascal
LOWV:=LLV(LOW,N);
HIGHV:=HHV(HIGH,N);
RSV:=EMA((CLOSE-LOWV)/(HIGHV-LOWV)*100,M);
K:EMA(RSV,M);
D:MA(K,M);
```

## UDL  ������(ϵͳ)

``` pascal
UDL:(MA(CLOSE,N1)+MA(CLOSE,N2)+MA(CLOSE,N3)+MA(CLOSE,N4))/4;
MAUDL:MA(UDL,M);
```

## WR  ����ָ��(ϵͳ)

``` pascal
WR1:100*(HHV(HIGH,N)-CLOSE)/(HHV(HIGH,N)-LLV(LOW,N));
WR2:100*(HHV(HIGH,N1)-CLOSE)/(HHV(HIGH,N1)-LLV(LOW,N1));
```

## LWR  LWR����ָ��(ϵͳ)

``` pascal
RSV:= (HHV(HIGH,N)-CLOSE)/(HHV(HIGH,N)-LLV(LOW,N))*100;
LWR1:SMA(RSV,M1,1);
LWR2:SMA(LWR1,M2,1);
```

## MARSI  ���ǿ��ƽ����(ϵͳ)

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

## BIAS-QL  ������-��ͳ��(ϵͳ)

``` pascal
BIAS :(CLOSE-MA(CLOSE,N))/MA(CLOSE,N)*100;
BIASMA :MA(BIAS,M);
```

## BIAS  ������(ϵͳ)

``` pascal
BIAS1 :(CLOSE-MA(CLOSE,N1))/MA(CLOSE,N1)*100;
BIAS2 :(CLOSE-MA(CLOSE,N2))/MA(CLOSE,N2)*100;
BIAS3 :(CLOSE-MA(CLOSE,N3))/MA(CLOSE,N3)*100;
```

## BIAS36  ��������(ϵͳ)

``` pascal
BIAS36:MA(CLOSE,3)-MA(CLOSE,6);
BIAS612:MA(CLOSE,6)-MA(CLOSE,12);
MABIAS:MA(BIAS36,M);
```

## BB  ���ּ���(ϵͳ)

``` pascal

```

## WIDTH  ���޿�(ϵͳ)

``` pascal

```

## ASI  ������ָ��(ϵͳ)

``` pascal

```

## CHO  ����ָ��(ϵͳ)

``` pascal
MID:=SUM(VOL*(2*CLOSE-HIGH-LOW)/(HIGH+LOW),0);
CHO:MA(MID,N1)-MA(MID,N2);
MACHO:MA(CHO,M);
```

## DMA  ƽ����(ϵͳ)

``` pascal
DIF:MA(CLOSE,N1)-MA(CLOSE,N2);
DIFMA:MA(DIF,M);
```

## DMI  ����ָ��(ϵͳ)

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

## DPO  ��������(ϵͳ)

``` pascal
DPO:CLOSE-REF(MA(CLOSE,N),N/2+1);
MADPO:MA(DPO,M);
```

## EMV  ���ײ���ָ��(ϵͳ)

``` pascal
VOLUME:=MA(VOL,N)/VOL;
MID:=100*(HIGH+LOW-REF(HIGH+LOW,1))/(HIGH+LOW);
EMV:MA(MID*VOLUME*(HIGH-LOW)/MA(HIGH-LOW,N),N);
MAEMV:MA(EMV,M);
```

## MACD  ƽ����ͬƽ��(ϵͳ)

``` pascal
DIF:EMA(CLOSE,SHORT)-EMA(CLOSE,LONG);
DEA:EMA(DIF,MID);
MACD:(DIF-DEA)*2,COLORSTICK;
```

## VMACD  ��ƽ����ͬƽ��(ϵͳ)

``` pascal
DIF:EMA(VOL,SHORT)-EMA(VOL,LONG);
DEA:EMA(DIF,MID);
MACD:DIF-DEA,COLORSTICK;
```

## QACD  ������ͬƽ��(ϵͳ)

``` pascal
DIF:EMA(CLOSE,N1)-EMA(CLOSE,N2);
MACD:EMA(DIF,M);
DDIF:DIF-MACD;
```

## TRIX  ����ָ��ƽ����(ϵͳ)

``` pascal
MTR:=EMA(EMA(EMA(CLOSE,N),N),N);
TRIX:(MTR-REF(MTR,1))/REF(MTR,1)*100;
MATRIX:MA(TRIX,M) ;
```

## UOS  �ռ�ָ��(ϵͳ)

``` pascal
TH:=MAX(HIGH,REF(CLOSE,1));
TL:=MIN(LOW,REF(CLOSE,1));
ACC1:=SUM(CLOSE-TL,N1)/SUM(TH-TL,N1);
ACC2:=SUM(CLOSE-TL,N2)/SUM(TH-TL,N2);
ACC3:=SUM(CLOSE-TL,N3)/SUM(TH-TL,N3);
UOS:(ACC1*N2*N3+ACC2*N1*N3+ACC3*N1*N2)*100/(N1*N2+N1*N3+N2*N3);
MAUOS:EXPMEMA(UOS,M);
```

## VPT  ��������(ϵͳ)

``` pascal
VPT:SUM(VOL*(CLOSE-REF(CLOSE,1))/REF(CLOSE,1),N);
MAVPT:MA(VPT,M);
```

## WVAD  ����������ɢ��(ϵͳ)

``` pascal
WVAD:SUM((CLOSE-OPEN)/(HIGH-LOW)*VOL,N)/10000;
MAWVAD:MA(WVAD,M);
```

## BRAR  ����ָ��(ϵͳ)

``` pascal
BR:SUM(MAX(0,HIGH-REF(CLOSE,1)),N)/SUM(MAX(0,REF(CLOSE,1)-LOW),N)*100;
AR:SUM(HIGH-OPEN,N)/SUM(OPEN-LOW,N)*100;
```

## CR  ��״������(ϵͳ)

``` pascal
MID:=REF(HIGH+LOW,1)/2;
CR:SUM(MAX(0,HIGH-MID),N)/SUM(MAX(0,MID-LOW),N)*100;
MA1:REF(MA(CR,M1),M1/2.5+1);
MA2:REF(MA(CR,M2),M2/2.5+1);
MA3:REF(MA(CR,M3),M3/2.5+1);
MA4:REF(MA(CR,M4),M4/2.5+1);
```

## MASS  ÷˹��(ϵͳ)

``` pascal
MASS:SUM(MA(HIGH-LOW,N1)/MA(MA(HIGH-LOW,N1),N1),N2);
MAMASS:MA(MASS,M);
```

## PSY  ������(ϵͳ)

``` pascal
PSY:COUNT(CLOSE>REF(CLOSE,1),N)/N*100;
PSYMA:MA(PSY,M);
```

## VR  �ɽ���������(ϵͳ)

``` pascal
TH:=SUM(IF(CLOSE>REF(CLOSE,1),VOL,0),N);
TL:=SUM(IF(CLOSE<REF(CLOSE,1),VOL,0),N);
TQ:=SUM(IF(CLOSE=REF(CLOSE,1),VOL,0),N);
VR:100*(TH*2+TQ)/(TL*2+TQ);
MAVR:MA(VR,M);
```

## WAD  �������������(ϵͳ)

``` pascal
MIDA:=CLOSE-MIN(REF(CLOSE,1),LOW);
MIDB:=IF(CLOSE<REF(CLOSE,1),CLOSE-MAX(REF(CLOSE,1),HIGH),0);
WAD:SUM(IF(CLOSE>REF(CLOSE,1),MIDA,MIDB),0);
MAWAD:MA(WAD,M);
```

## AMO  �ɽ����(ϵͳ)

``` pascal
AMOW:AMOUNT/10000.0,VOLSTICK;
AMO1:MA(AMOW,M1);
AMO2:MA(AMOW,M2);
```

## OBV  �ۻ�������(ϵͳ)

``` pascal
VA:=IF(CLOSE>REF(CLOSE,1),VOL,-VOL);
OBV:SUM(IF(CLOSE=REF(CLOSE,1),0,VA),0);
MAOBV:MA(OBV,M);
```

## VOL  �ɽ���(ϵͳ)

``` pascal
VOLUME:VOL,VOLSTICK;
MAVOL1:MA(VOLUME,M1);
MAVOL2:MA(VOLUME,M2);
```

## VOL-TDX  �ɽ���(����)(ϵͳ)

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

## AMO-TDX  �ɽ����(����)(ϵͳ)

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

## SHORTVOL  �׿���(�����ڸ۹�)(ϵͳ)

``` pascal
�׿���:HKSHORTVOL,VOLSTICK;
MACCL:MA(�׿���,M);
```

## CCL  �ֲ���(�������ڻ�)(ϵͳ)

``` pascal
�ֲ���:VOLINSTK;
MACCL:MA(�ֲ���,M);
```

## VRSI  ���ǿ����(ϵͳ)

``` pascal
LC:=REF(VOL,1);
RSI1:SMA(MAX(VOL-LC,0),N1,1)/SMA(ABS(VOL-LC),N1,1)*100;
RSI2:SMA(MAX(VOL-LC,0),N2,1)/SMA(ABS(VOL-LC),N2,1)*100;
RSI3:SMA(MAX(VOL-LC,0),N3,1)/SMA(ABS(VOL-LC),N3,1)*100;

```

## ACD  ������(ϵͳ)

``` pascal
LC:=REF(CLOSE,1);
DIF:=CLOSE-IF(CLOSE>LC,MIN(LOW,LC),MAX(HIGH,LC));
ACD:SUM(IF(CLOSE=LC,0,DIF),0);
MAACD:EXPMEMA(ACD,M);
```

## BBI  ��վ���(ϵͳ)

``` pascal
BBI:(MA(CLOSE,M1)+MA(CLOSE,M2)+MA(CLOSE,M3)+MA(CLOSE,M4))/4;
```

## EXPMA  ָ��ƽ����(ϵͳ)

``` pascal
EXP1:EMA(CLOSE,M1);
EXP2:EMA(CLOSE,M2);
```

## EXPMA_S  ָ��ƽ����-��ͼ(ϵͳ)

``` pascal
EXP1:EMA(CLOSE,M1);
EXP2:EMA(CLOSE,M2);
```

## HMA  �߼�ƽ����(ϵͳ)

``` pascal
HMA1:MA(HIGH,M1);
HMA2:MA(HIGH,M2);
HMA3:MA(HIGH,M3);
HMA4:MA(HIGH,M4);
HMA5:MA(HIGH,M5);
```

## LMA  �ͼ�ƽ����(ϵͳ)

``` pascal
LMA1:MA(LOW,M1);
LMA2:MA(LOW,M2);
LMA3:MA(LOW,M3);
LMA4:MA(LOW,M4);
LMA5:MA(LOW,M5);
```

## VMA  ����ƽ����(ϵͳ)

``` pascal
VV:=(HIGH+OPEN+LOW+CLOSE)/4;
VMA1:MA(VV,M1);
VMA2:MA(VV,M2);
VMA3:MA(VV,M3);
VMA4:MA(VV,M4);
VMA5:MA(VV,M5);
```

## PCNT  ���ȱ�(ϵͳ)

``` pascal
PCNT:(CLOSE-REF(CLOSE,1))/CLOSE*100;
MAPCNT:EXPMEMA(PCNT,M);
```

## BOLL-M  ������-��ͳ��(ϵͳ)

``` pascal

```

## BOLL  ������(ϵͳ)

``` pascal
BOLL:MA(CLOSE,M);
UB:BOLL+2*STD(CLOSE,M);
LB:BOLL-2*STD(CLOSE,M);
```

## XT  ����(ϵͳ)

``` pascal
���䶥��:PEAK(CLOSE,N,1)*0.98;
����ס�:TROUGH(CLOSE,N,1)*1.02;
����ߡ�:100*(���䶥��-����ס�)/����ס�,NODRAW;
```

## JAX  �ð���(ϵͳ)

``` pascal
AA:=ABS((2*CLOSE+HIGH+LOW)/4-MA(CLOSE,N))/MA(CLOSE,N);
�ð���:DMA((2*CLOSE+LOW+HIGH)/4,AA),LINETHICK3,COLORMAGENTA;
CC:=(CLOSE/�ð���);
MA1:=MA(CC*(2*CLOSE+HIGH+LOW)/4,3);
MAAA:=((MA1-�ð���)/�ð���)/3;
TMP:=MA1-MAAA*MA1;
J:IF(TMP<=�ð���,�ð���,DRAWNULL),LINETHICK3,COLORCYAN;
A:TMP,LINETHICK2,COLORYELLOW;
X:IF(TMP<=�ð���,TMP,DRAWNULL),LINETHICK2,COLORGREEN;
```

## PBX  �ٲ���(ϵͳ)

``` pascal
PBX1:(EMA(CLOSE,M1)+MA(CLOSE,M1*2)+MA(CLOSE,M1*4))/3;
PBX2:(EMA(CLOSE,M2)+MA(CLOSE,M2*2)+MA(CLOSE,M2*4))/3;
PBX3:(EMA(CLOSE,M3)+MA(CLOSE,M3*2)+MA(CLOSE,M3*4))/3;
PBX4:(EMA(CLOSE,M4)+MA(CLOSE,M4*2)+MA(CLOSE,M4*4))/3;
PBX5:(EMA(CLOSE,M5)+MA(CLOSE,M5*2)+MA(CLOSE,M5*4))/3;
PBX6:(EMA(CLOSE,M6)+MA(CLOSE,M6*2)+MA(CLOSE,M6*4))/3;
```

## ENE  �����(ϵͳ)

``` pascal
UPPER:(1+M1/100)*MA(CLOSE,N);
LOWER:(1-M2/100)*MA(CLOSE,N);
ENE:(UPPER+LOWER)/2;
```

## MIKE  ���֧��ѹ��(ϵͳ)

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

## SAR  ������ָ��(ϵͳ)

``` pascal

```

## TDXWAVE  ͨ����������(ϵͳ)

``` pascal

```

## VTY  �۸������(ϵͳ)

``` pascal

```

## ZXNH  ֱ�����(ϵͳ)

``` pascal

```

## ZX  ������(ϵͳ)

``` pascal
AV:0.01*AMOUNT/VOL;
```

## AMV  �ɱ��۾���(ϵͳ)

``` pascal
AMOV:=VOL*(OPEN+CLOSE)/2;
AMV1:SUM(AMOV,M1)/SUM(VOL,M1);
AMV2:SUM(AMOV,M2)/SUM(VOL,M2);
AMV3:SUM(AMOV,M3)/SUM(VOL,M3);
AMV4:SUM(AMOV,M4)/SUM(VOL,M4);
```

## PAV  ��������(ϵͳ)

``` pascal

```

## PAVE  ǿ��������(ϵͳ)

``` pascal

```

## MCST  �г��ɱ�(ϵͳ)

``` pascal

```

## NVI  ���ɽ���(ϵͳ)

``` pascal

```

## PVI  ���ɽ���(ϵͳ)

``` pascal

```

## SSRP  �����(ϵͳ)

``` pascal

```

## HSL  ������(ϵͳ)

``` pascal
HSL:IF((SETCODE==0||SETCODE==1),100*VOL,VOL)/(FINANCE(7)/100);
MAHSL:MA(HSL,N);
```

## HSCOL  ������(ϵͳ)

``` pascal
HSCOL:IF((SETCODE==0||SETCODE==1),100*VOL,VOL)/(FINANCE(7)/100),VOLSTICK;
MAHSL:MA(HSCOL,N);
```

## DBQR  �Ա�ǿ��(����������)(ϵͳ)

``` pascal
ZS:(INDEXC-REF(INDEXC,N))/REF(INDEXC,N);
GG:(CLOSE-REF(CLOSE,N))/REF(CLOSE,N);
MADBQR1:MA(GG,M1);
MADBQR2:MA(GG,M2);
MADBQR3:MA(GG,M3);
```

## DBQRV  �Ա�ǿ����(����������)(ϵͳ)

``` pascal
ZS:(INDEXV-REF(INDEXV,N))/REF(INDEXV,N);
GG:(VOL-REF(VOL,N))/REF(VOL,N);
```

## JS  ������(ϵͳ)

``` pascal
JS:100*(CLOSE-REF(CLOSE,N))/(N*REF(CLOSE,N));
MAJS1:MA(JS,M1);
MAJS2:MA(JS,M2);
MAJS3:MA(JS,M3);
```

## DBLB  �Ա�����(����������)(ϵͳ)

``` pascal
GG:=VOL/SUM(REF(VOL,1),N);
ZS:=INDEXV/SUM(REF(INDEXV,1),N);
DBLB:GG/ZS;
MADBLB:MA(DBLB,M);
```

## BBIBOLL  ��ղ�����(ϵͳ)

``` pascal
CV:=CLOSE;
BBIBOLL:(MA(CV,3)+MA(CV,6)+MA(CV,12)+MA(CV,24))/4;
UPR:BBIBOLL+M*STD(BBIBOLL,N);
DWN:BBIBOLL-M*STD(BBIBOLL,N);
```

## ALLIGAT  ������(ϵͳ)

``` pascal
NN:=(H+L)/2;
�ϴ�:REF(MA(NN,5),3),COLOR40FF40;
����:REF(MA(NN,8),5),COLOR0000C0;
���:REF(MA(NN,13),8),COLORFF4040;
```

## ACCER  ��������(ϵͳ)

``` pascal
ACCER:SLOPE(CLOSE,N)/CLOSE;
```

## CYD  �н�����(ϵͳ)

``` pascal
CYDS:WINNER(CLOSE)/(VOL/CAPITAL);
CYDN:WINNER(CLOSE)/MA(VOL/CAPITAL,N);
```

## CYE  �г�����(ϵͳ)

``` pascal
MAL:=MA(CLOSE,5);
MAS:=MA(MA(CLOSE,20),5);
CYEL:(MAL-REF(MAL,1))/REF(MAL,1)*100;
CYES:(MAS-REF(MAS,1))/REF(MAS,1)*100;
```

## CYR  �г�ǿ��(ϵͳ)

``` pascal
DIVE:=0.01*EMA(AMOUNT,N)/EMA(VOL,N);
CYR:(DIVE/REF(DIVE,1)-1)*100;
MACYR:MA(CYR,M);
```

## CYF  �г�����(ϵͳ)

``` pascal
CYF:100-100/(1+EMA(HSL,N));
```

## FSL  ��ˮ��(ϵͳ)

``` pascal
SWL:(EMA(CLOSE,5)*7+EMA(CLOSE,10)*3)/10;
SWS:DMA(EMA(CLOSE,12),MAX(1,100*(SUM(VOL,5)/(3*CAPITAL))));
```

## ADTM  ��̬������ָ��(ϵͳ)

``` pascal
DTM:=IF(OPEN<=REF(OPEN,1),0,MAX((HIGH-OPEN),(OPEN-REF(OPEN,1))));
DBM:=IF(OPEN>=REF(OPEN,1),0,MAX((OPEN-LOW),(OPEN-REF(OPEN,1))));
STM:=SUM(DTM,N);
SBM:=SUM(DBM,N);
ADTM:IF(STM>SBM,(STM-SBM)/STM,IF(STM=SBM,0,(STM-SBM)/SBM));
MAADTM:MA(ADTM,M);
```

## ATR  ��ʵ����(ϵͳ)

``` pascal
MTR:MAX(MAX((HIGH-LOW),ABS(REF(CLOSE,1)-HIGH)),ABS(REF(CLOSE,1)-LOW));
ATR:MA(MTR,N);
```

## DKX  �����(ϵͳ)

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

## TAPI  ��Ȩָ���ɽ�ֵ(����������)(ϵͳ)

``` pascal
TAPI:AMOUNT/INDEXC;
MATAIP:MA(TAPI,M);
```

## PUCU  ��ʱ������(ϵͳ)

``` pascal
PU:MA(CLOSE,N);
CU:MA(VOL,N);
```

## XS  Ѧ˹ͨ��(ϵͳ)

``` pascal
VAR2:=CLOSE*VOL;
VAR3:=EMA((EMA(VAR2,3)/EMA(VOL,3)+EMA(VAR2,6)/EMA(VOL,6)+EMA(VAR2,12)/EMA(VOL,12)+EMA(VAR2,24)/EMA(VOL,24))/4,N);
SUP:1.06*VAR3;
SDN:VAR3*0.94;
VAR4:=EMA(CLOSE,9);
LUP:EMA(VAR4*1.14,5);
LDN:EMA(VAR4*0.86,5);
```

## XS2  Ѧ˹ͨ��II(ϵͳ)

``` pascal
AA:=MA((2*CLOSE+HIGH+LOW)/4,5); 
ͨ��1:AA*N/100; 
ͨ��2:AA*(200-N)/100; 
CC:=ABS((2*CLOSE+HIGH+LOW)/4-MA(CLOSE,20))/MA(CLOSE,20); 
DD:=DMA(CLOSE,CC); 
ͨ��3:(1+M/100)*DD; 
ͨ��4:(1-M/100)*DD;
```

## QR  ǿ��ָ��(����������)(ϵͳ)

``` pascal
����: (CLOSE-REF(CLOSE,N))/REF(CLOSE,N)*100; 
����: (INDEXC-REF(INDEXC,N))/REF(INDEXC,N)*100; 
ǿ��ֵ:EMA(����-����,2),COLORSTICK;
```

## GDX  �����(ϵͳ)

``` pascal
AA:=ABS((2*CLOSE+HIGH+LOW)/4-MA(CLOSE,N))/MA(CLOSE,N); 
���:DMA(CLOSE,AA);
ѹ����:(1+M/100)*���; 
֧����:(1-M/100)*���;  
```

## JLHB  ��·����(ϵͳ)

``` pascal
VAR1:=(CLOSE-LLV(LOW,60))/(HHV(HIGH,60)-LLV(LOW,60))*80; 
B:SMA(VAR1,N,1); 
VAR2:SMA(B,M,1); 
��·����:IF(CROSS(B,VAR2) AND B<40,50,0);
```

## MA����  MA����(ϵͳ)(�ɽ���)

``` pascal
{��ģ��Ϊʾ��ģ��,������˵���㷨�﷨,�û�������Լ����׾����޸ĺ���ʵ��Ӧ��}
{������ֵ}
MA1:=MA(CLOSE,SHORT);
MA2:=MA(CLOSE,LONG);
{��������}
ƽ�տ���:=CROSS(MA1,MA2);
ƽ�࿪��:=CROSS(MA2,MA1);
{����ϵͳ}
BUYSHORT_BUY(ƽ�տ���,LOW);
SELL_SELLSHORT(ƽ�࿪��,HIGH);
{�����źŹ���}
AUTOFILTER;
```

## MACD����  MACD����(ϵͳ)(�ɽ���)

``` pascal
{��ģ��Ϊʾ��ģ��,������˵���㷨�﷨,�û�������Լ����׾����޸ĺ���ʵ��Ӧ��}
DIFF:=EMA(CLOSE,SHORT)-EMA(CLOSE,LONG);
DEA:=EMA(DIFF,MID);
MACD:=2*(DIFF-DEA);
ƽ�տ���:=CROSS(MACD,0);
ƽ�࿪��:=CROSS(0,MACD);
BUYSHORT_BUY(ƽ�տ���,LOW);
SELL_SELLSHORT(ƽ�࿪��,HIGH);
AUTOFILTER;
```

## KDJ����  KDJ����(ϵͳ)(�ɽ���)

``` pascal
{��ģ��Ϊʾ��ģ��,������˵���㷨�﷨,�û�������Լ����׾����޸ĺ���ʵ��Ӧ��}
RSV:=(CLOSE-LLV(LOW,N))/(HHV(HIGH,N)-LLV(LOW,N))*100;
K:=SMA(RSV,M1,1);
D:=SMA(K,M1,1);
J:=3*K-2*D;
ƽ�տ���:=CROSS(J,0);
ƽ�࿪��:=CROSS(100,J);
BUYSHORT_BUY(ƽ�տ���,LOW);
SELL_SELLSHORT(ƽ�࿪��,HIGH);
AUTOFILTER;
```

## ������  ������ͨ������(ϵͳ)(�ɽ���)

``` pascal
{��ģ��Ϊʾ��ģ��,������˵���㷨�﷨,�û�������Լ����׾����޸ĺ���ʵ��Ӧ��}
MA1:=REF(MA((HIGH+LOW+CLOSE)/3,AVGLENGTH),1);
UPPERBAND:=MA1+REF(MA(TR,ATRLENGTH),1);
LOWERBAND:=MA1-REF(MA(TR,ATRLENGTH),1);
��������:=MA1>REF(MA1,1) AND HIGH>=UPPERBAND;
ƽ������:=LOW<=MA1;
��������:=MA1<REF(MA1,1) AND LOW<=LOWERBAND;
ƽ������:=HIGH>=MA1;
GL1:=NOT(��������=1 AND ƽ������=1);
GL2:=NOT(��������=1 AND ƽ������=1);
SELL(ƽ������,HIGH);
BUYSHORT(ƽ������,LOW);
BUY(�������� AND GL1,LOW);
SELLSHORT(�������� AND GL2,HIGH);
AUTOFILTER;
```

## ���氲  ���氲ͨ������(ϵͳ)(�ɽ���)

``` pascal
{��ģ��Ϊʾ��ģ��,������˵���㷨�﷨,�û�������Լ����׾����޸ĺ���ʵ��Ӧ��}
���ڸߵ�:=REF(HHV(H,X1),1);
���ڵ͵�:=REF(LLV(L,X2),1);
ƽ�տ���:=HIGH>=���ڸߵ�;
ƽ�࿪��:=LOW<=���ڵ͵�;
BUYSHORT_BUY(ƽ�տ���,LOW);
SELL_SELLSHORT(ƽ�࿪��,HIGH);
AUTOFILTER;
```

## ����ͻ��  ����ͻ�ƽ���(ϵͳ)(�ɽ���)

``` pascal
{��ģ��Ϊʾ��ģ��,������˵���㷨�﷨,�û�������Լ����׾����޸ĺ���ʵ��Ӧ��}
{������ֵ}
NBAR:=BARSLAST(DATE<>REF(DATE,1))+1;
HHN:REF(HHV(H,N),1);
LLN:REF(LLV(L,N),1);
MID:(HHN+LLN)/2;
T1:=TIME>900 AND TIME <1455;{����Ʒ�ֵĽ���ʱ���ѡ�����������Ӧ����}
T2:=TIME>=1455;{����Ʒ�ֵĽ���ʱ���ѡ�����������Ӧ����}
{��������}
��������:=H>HHN AND (HHN-MID)/MID<M/1000 AND NBAR>=30 AND T1;
��������:=L<LLN AND (MID-LLN)/MID<M/1000 AND NBAR>=30 AND T1;
{����ϵͳ}
BUY(��������,LOW);
SELLSHORT(��������,HIGH);
SELL(T2,HIGH);
BUYSHORT(T2,LOW);
AUTOFILTER;
```

## HANS123  ����HANS����(ϵͳ)(�ɽ���)

``` pascal
{��ģ��Ϊʾ��ģ��,������˵���㷨�﷨,�û�������Լ����׾����޸ĺ���ʵ��Ӧ��}
{������ֵ}
N:=BARSLAST(DATE<>REF(DATE,1))+1;
HHH:=VALUEWHEN(TIME<=900+NMIN1,HHV(H,N));
LLL:=VALUEWHEN(TIME<=900+NMIN1,LLV(L,N));
�Ϲ�:HHH+M*MINDIFF;
�¹�:LLL-M*MINDIFF;
{��������}
��������:=C>�Ϲ�;
��������:=C<�¹�;
����ʱ��:=TIME>900+NMIN1 AND TIME<1450;
ƽ��ʱ��:=TIME>=1500-NMIN2;
{����ϵͳ}
BUY(�������� AND ����ʱ��,LOW);
SELLSHORT(�������� AND ����ʱ��,HIGH);
SELL(ƽ��ʱ��,HIGH);
BUYSHORT(ƽ��ʱ��,LOW);
AUTOFILTER;
```

## SG-XDT  �ĵ�ͼ(����������)(ϵͳ)

``` pascal
QR:CLOSE/INDEXC*1000;
MQR1:MA(QR,5);
MQR2:MA(QR,10);
```

## SG-NDB  �Ե粨(��ϵ)(ϵͳ)

``` pascal
HH:=IF(C/REF(C,1)>1.093 AND L>REF(H,1),2*C-REF(C,1)-H,2*C-H-L);
V1:=BARSCOUNT(C);
V2:=2*REF(C,V1)-REF(H,V1)-REF(L,V1);
DK:SUM(HH,0)+V2;
MDK5:MA(DK,P1);
MDK10:MA(DK,P2);
```

## SG-SMX  ������(����������)(ϵͳ)

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

## SG-LB  ����(����������)(ϵͳ)

``` pascal
ZY2:=VOL/INDEXV*1000;
����:ZY2;
MA5:MA(ZY2,5);
MA10:MA(ZY2,10);
```

## SG-PF  ǿ�ƹ�����(����������)(ϵͳ)

``` pascal
ZY1:=CLOSE/INDEXC*1000;
A1:=IF(ZY1>HHV(ZY1,3),10,0);
A2:=IF(ZY1>HHV(ZY1,5),15,0);
A3:=IF(ZY1>HHV(ZY1,10),20,0);
A4:=IF(ZY1>HHV(ZY1,2),10,0);
A5:=COUNT(ZY1>REF(ZY1,1) ,9)*5;
ǿ�ƹ�����:A1+A2+A3+A4+A5;
```

## CYC  �ɱ�����(ϵͳ)

``` pascal
JJJ:=IF(DYNAINFO(8)>0.01,0.01*DYNAINFO(10)/DYNAINFO(8),DYNAINFO(3));
DDD:=(DYNAINFO(5)<0.01 || DYNAINFO(6)<0.01);
JJJT:=IF(DDD,1,(JJJ<(DYNAINFO(5)+0.01) && JJJ>(DYNAINFO(6)-0.01)));
CYC1:IF(JJJT,0.01*EMA(AMOUNT,P1)/EMA(VOL,P1),EMA((HIGH+LOW+CLOSE)/3,P1));
CYC2:IF(JJJT,0.01*EMA(AMOUNT,P2)/EMA(VOL,P2),EMA((HIGH+LOW+CLOSE)/3,P2));
CYC3:IF(JJJT,0.01*EMA(AMOUNT,P3)/EMA(VOL,P3),EMA((HIGH+LOW+CLOSE)/3,P3));
CYC��:IF(JJJT,DMA(AMOUNT/(100*VOL),100*VOL/FINANCE(7)),EMA((HIGH+LOW+CLOSE)/3,120));
```

## CYS  �г�ӯ��(ϵͳ)

``` pascal
CYC13:=0.01*EMA(AMOUNT,13)/EMA(VOL,13);
CYS:(CLOSE-CYC13)/CYC13*100;
```

## CYQKL  ����K�߳���(ϵͳ)

``` pascal
KL:100*(WINNER(CLOSE)-WINNER(OPEN));
```

## CYW  ��������(ϵͳ)

``` pascal
VAR1:=CLOSE-LOW;
VAR2:=HIGH-LOW;
VAR3:=CLOSE-HIGH;
VAR4:=IF(HIGH>LOW,(VAR1/VAR2+VAR3/VAR2)*VOL,0);
CYW: SUM(VAR4,10)/10000, COLORSTICK;
```

## RAD  �����״�(����������)(ϵͳ)

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

## LON  ��ϵ����(ϵͳ)

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

## SHT  ��ϵ����(ϵͳ)

``` pascal
VAR1:=MA((VOL-REF(VOL,1))/REF(VOL,1),5);
VAR2:=(CLOSE-MA(CLOSE,24))/MA(CLOSE,24)*100;
MY: VAR2*(1+VAR1);
SHT: MY, COLORSTICK;
SHTMA: MA(SHT,N);
```

## ZLJC  ��������(ϵͳ)

``` pascal
VAR1:=(CLOSE+LOW+HIGH)/3; 
VAR2:=SUM(((VAR1-REF(LOW,1))-(HIGH-VAR1))*VOL/100000/(HIGH-LOW),0); 
VAR3:=EMA(VAR2,1); 
JCS:VAR3; 
JCM:MA(VAR3,12); 
JCL:MA(VAR3,26);
```

## ZLMM  ��������(ϵͳ)

``` pascal
LC :=REF(CLOSE,1);
RSI2:=SMA(MAX(CLOSE-LC,0),12,1)/SMA(ABS(CLOSE-LC),12,1)*100;
RSI3:=SMA(MAX(CLOSE-LC,0),18,1)/SMA(ABS(CLOSE-LC),18,1)*100;
MMS:MA(3*RSI2-2*SMA(MAX(CLOSE-LC,0),16,1)/SMA(ABS(CLOSE-LC),16,1)*100,3);
MMM:EMA(MMS,8);
MML:MA(3*RSI3-2*SMA(MAX(CLOSE-LC,0),12,1)/SMA(ABS(CLOSE-LC),12,1)*100,5);
```

## SLZT  ��������(ϵͳ)

``` pascal
����: MA(CLOSE,125);
����: ����+2*STD(CLOSE,170);
����: ����-2*STD(CLOSE,145);
����: SAR(125,1,7), LINESTICK;
VAR2:=HHV(HIGH,70);
VAR3:=HHV(HIGH,20);
����: VAR2*0.83;
����: VAR3*0.91;
```

## ADVOL  ��ϵ��ɢ��(ϵͳ)

``` pascal
A:=SUM(((CLOSE-LOW)-(HIGH-CLOSE))*VOL/10000/(HIGH-LOW),0);
ADVOL:A;
MA1:MA(A,30);
MA2:MA(MA1,100);
```

## CJDX  ��������(ϵͳ)

``` pascal
VAR1:=(2*CLOSE+HIGH+LOW)/4;
VAR2:=EMA(EMA(EMA(VAR1,4),4),4);
J: (VAR2-REF(VAR2,1))/REF(VAR2,1)*100, COLORSTICK;
D: MA(J,3);
K: MA(J,1);
```

## ZJTJ  ׯ��̧��(ϵͳ)

``` pascal
VAR1:=EMA(EMA(CLOSE,9),9);
����:=(VAR1-REF(VAR1,1))/REF(VAR1,1)*1000;
STICKLINE(����<0,����,0,1,0),COLORWHITE;
A10:=CROSS(����,0);
��ׯ����:IF(����<0,����,0),COLORWHITE,NODRAW;
��ʼ����:IF(A10,5,0),LINETHICK1,COLORYELLOW;
STICKLINE(����>REF(����,1) AND ����>0,����,0,1,0),COLORRED;
��ׯ����:IF(����>REF(����,1) AND ����>0,����,0),COLORRED,NODRAW;
VAR2:=100*WINNER(CLOSE*0.95);
STICKLINE(VAR2>50 AND COST(85)<CLOSE AND ����>0,����,0,1,0),COLORFF00FF;
�߶ȿ���:IF(VAR2>50 AND COST(85)<CLOSE AND ����>0,����,0),COLORFF00FF,NODRAW;
STICKLINE(����<REF(����,1) AND ����>0,����,0,1,0),COLOR00FF00;
��������:IF(����<REF(����,1) AND ����>0,����,0),COLOR00FF00,NODRAW;
```

## ZBCD  ׼������(ϵͳ)

``` pascal
VAR1:=AMOUNT/VOL/7;
VAR2:=(3*HIGH+LOW+OPEN+2*CLOSE)/7;
VAR3:=SUM(AMOUNT,N)/VAR1/7;
VAR4:=DMA(VAR2,VOL/VAR3);
����:(CLOSE-VAR4)/VAR4*100,COLORLIMAGENTA;
DRAWICON(CROSS(-7.0,����),����,1);
```

## BDZX  ����֮��(ϵͳ)

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
���: IF(CROSS(AK,AD1),58,20);
����: IF(CROSS(AD1,AK),58,20);
```

## LHXJ  �Ժ��Ⱦ�(ϵͳ)

``` pascal
VAR1:=(CLOSE*2+HIGH+LOW)/4;
VAR2:=EMA(VAR1,13)-EMA(VAR1,34);
VAR3:=EMA(VAR2,5);
��������: (-2)*(VAR2-VAR3)*3.8;
��������: 2*(VAR2-VAR3)*3.8;
```

## LYJH  ��ӥ�ߺ�(ϵͳ)

``` pascal
VAR1:=(HHV(HIGH,36)-CLOSE)/(HHV(HIGH,36)-LLV(LOW,36))*100;
��������������: SMA(VAR1,2,1);
VAR2:=(CLOSE-LLV(LOW,9))/(HHV(HIGH,9)-LLV(LOW,9))*100;
��������������: SMA(VAR2,5,1)-8;
LH: M;
LH1: M1;
```

## JFZX  쫷���������(ϵͳ)

``` pascal
VAR2:=SUM(IF(CLOSE>OPEN,VOL,0),N)/SUM(VOL,N)*100;
VAR3:=100-SUM(IF(CLOSE>OPEN,VOL,0),N)/SUM(VOL,N)*100;
��ͷ����: VAR2;
��ͷ����: VAR3;
���ƽ��: 50;
```

## CYHT  ���˺�ͨ(ϵͳ)

``` pascal
VAR1:=(2*CLOSE+HIGH+LOW+OPEN)/5;
����: 80;
VAR2:=LLV(LOW,34);
VAR3:=HHV(HIGH,34);
SK: EMA((VAR1-VAR2)/(VAR3-VAR2)*100,13);
SD: EMA(SK,3);
����: 20;
ǿ���ֽ�: 50;
VAR4:=IF(CROSS(SK,SD),40,22);
VAR5:=IF(CROSS(SD,SK),60,78);
����: VAR5;
���: VAR4;
```

## SCR  ���뼯�ж�(ϵͳ)

``` pascal
A:=P1+(100-P1)/2;
B:=(100-P1)/2;
CC:=COST(A);
DD:=COST(B);
SCR:(CC-DD)/(CC+DD)*100/2;
```

## ASR  �������(ϵͳ)

``` pascal
ASR:(WINNER(C*1.1)-WINNER(C*0.9))/WINNER(HHV(H,0))*100;
```

## BSQJ  ��������(ϵͳ)

``` pascal
����:=EMA(C,2);
����:=EMA(SLOPE(C,21)*20+C,42);
STICKLINE(����>=����,REFDATE(HHV(H,0),DATE),REFDATE(LLV(L,0),DATE),6,0),COLOR001050;
STICKLINE(����<����,REFDATE(HHV(H,0),DATE),REFDATE(LLV(L,0),DATE),6,0),COLOR404050;
DRAWKLINE(H,O,L,C);
ָ��:=EMA((EMA(CLOSE,4)+EMA(CLOSE,6)+EMA(CLOSE,12)+EMA(CLOSE,24))/4,2);
��:=MA(CLOSE,27);
B��:IF(CROSS(ָ��,��) OR CROSS(����,����),C,DRAWNULL),COLORMAGENTA,NODRAW;
�ֲ�:IF(����>=����,C,DRAWNULL),COLORRED,NODRAW;
S��:IF(CROSS(��,ָ��) OR CROSS(����,����),C,DRAWNULL),COLORLIGRAY,NODRAW;
�ղ�:IF(����<����,C,DRAWNULL),COLORGREEN,NODRAW;
DRAWICON(CROSS(����,����),L,1);
DRAWICON(CROSS(����,����),H,2);
```

## ZJL  �ۼ���,��������(ϵͳ)

``` pascal
�ۼ���:IF(FINANCE(34)>0.001,(FINANCE(34)-CLOSE)*100.0/FINANCE(34),0);
```

## CDP-STD  ���Ʋ���(ϵͳ)

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

## TBP-STD  ����ƽ���(ϵͳ)

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
��ͷ����:REF(IF(DIRECT0>50,APX*2-L,DRAWNULL),1),NODRAW;
��ͷͣ��:REF(IF(DIRECT0>50,APX-TR0,DRAWNULL),1),NODRAW;
��ͷ�ز�:REF(IF(DIRECT0<-50,APX*2-H,DRAWNULL),1),NODRAW;
��ͷͣ��:REF(IF(DIRECT0<-50,APX+TR0,DRAWNULL),1),NODRAW;
```

## SC  ����(ϵͳ)

``` pascal

```

## NDB  �Ե粨(ϵͳ)

``` pascal

```

## JYJL  ���ײο�����(ϵͳ)

``` pascal
��λʱ������: SUM(VOL,N)*100,NODRAW;
��λʱ���ھ���: ��λʱ������/(N/M);
```

## JSJG  �ο������(�����ڽ����ڻ�)(ϵͳ)

``` pascal
FIRST:=IF(PERIOD=0,HOUR=14 AND MINUTE=16,DRAWNULL);
TOTAL:=IF(PERIOD=0,60,0);
MAMIN:=BARSLAST(FIRST)+1;
COUNTFLAG:=(PERIOD=0 AND ( (HOUR=14 AND MINUTE>=16) OR HOUR=15 ));
�ƽ�����۸�:IF(COUNTFLAG,SUM(C*V,MAMIN)/SUM(V,MAMIN),DRAWNULL);
LASTP:=C;
LASTM:=MAMIN;
LASTV:=MA(V,MAMIN);
�ο�����۸�:IF(COUNTFLAG,(SUM(C*V,MAMIN)+LASTP*LASTV*(TOTAL-LASTM))/(LASTV*TOTAL),DRAWNULL);
```

## PRICEV  �۸񲨶���(ϵͳ)

``` pascal
VR:STDDEV(CLOSE,N)*100;
VRMA:MA(VR,M);
```

## HISV  ��ʷ������(ϵͳ)

``` pascal
������:STDDEV(CLOSE,N)*SQRT(250)*100.0;
```

## VOLATILITY  ��Ȩ������(ϵͳ)

``` pascal
HV:IVOLAT(N,0)*100.0;
����������:IVOLAT(N,1)*100.0;
������:(����������-HV),COLORSTICK;
```

## CPBS  ����BS��(ϵͳ)

``` pascal
BU:=CROSS(HIGH,SAR(3,1,20));
SEL:=CROSS(SAR(3,1,20),LOW);
DRAWTEXT(BU,LOW,'B'),COLORYELLOW,LINETHICK2;
DRAWTEXT(SEL,1.01*HIGH,'S'),COLORGREEN,LINETHICK2;
```

## CYX  ��ѹ��(ϵͳ)

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

## WAVE  ���˷���(ϵͳ)

``` pascal
ZIG(3,����);
```

## SKSD  ʱ�����(ϵͳ)

``` pascal
STICKLINE(CURRBARSCOUNT<=N,H,L,-1,0),COLORBLACK;
DRAWTEXT_FIX(ISLASTBAR,0,0,0,STRCAT(CON2STR(N,0),'����ǰK��  ѡ����ͼ��ALT+T�����ڻ��˵�����')),COLORLIMAGENTA;
NOTEXT1:IF(CURRBARSCOUNT>=N+1,MA(C,M),DRAWNULL),COLORWHITE;
NOTEXT2:IF(CURRBARSCOUNT<=N,MA(C,M),DRAWNULL),COLORBLACK; 
```

## ���߾���  ���ֹ߳ɳֱ���(ϵͳ)

``` pascal

```

## ���߾���  ���ֹ߳ɳֱ���(ϵͳ)

``` pascal

```

## XLPL  ��������(ϵͳ)

``` pascal

```

## GSTQ  ��������(ϵͳ)

``` pascal

```

## AROON  ��¡ָ��(ϵͳ)

``` pascal
�Ϲ�:(N-HHVBARS(H,N))/N*100,COLORRED;
�¹�:(N-LLVBARS(H,N))/N*100,COLORGREEN;
```

## CFJT  �Ƹ�����(ϵͳ)

``` pascal
ͻ��:=REF(EMA(C,14),1);
A1X:=(EMA(C,10)-ͻ��)/ͻ��*100;
�෽:=IF(A1X>=0,REF(EMA(C,10),BARSLAST(CROSS(A1X,0))+1),DRAWNULL);
�շ�:=IF(A1X<0,REF(EMA(C,10),BARSLAST(CROSS(0,A1X))+1),DRAWNULL);
STICKLINE(A1X>=0,�෽,ͻ��,10,0),COLOR000099;
STICKLINE(A1X<0,�շ�,ͻ��,10,0),COLOR00CC66;
```

## TJCJL  ̫���ɽ���(ϵͳ)

``` pascal
����:VOL,NODRAW;
DRAWTEXT_FIX(ISLASTBAR,0,0,0,'˵��: ��ɫ��Ϊ������,��ɫΪ������,��ɫΪ����,��ɫΪ����'),COLORGRAY;
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

## ZJFZ  ׷����ת(ϵͳ)

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

## ZSDB  ָ���Ա�(��ͼ,����������)(ϵͳ)

``` pascal
A:=REF(INDEXC,1);
ָ���Ƿ�:IF(A>0,(INDEXC-A)*100/A,0),NODRAW;
HYDB:DRAWKLINE(INDEXH,INDEXO,INDEXL,INDEXC);
```

## HYDB  ��ҵ�Ա�(��ͼ,����������)(ϵͳ)

``` pascal
A:=REF(HY_INDEXC,1);
��ҵ�Ƿ�:IF(A>0,(HY_INDEXC-A)*100/A,0),NODRAW;
DRAWTEXT_FIX(ISLASTBAR,0,0,0,HYBLOCK),COLOR00C0C0;
HYDB:DRAWKLINE(HY_INDEXH,HY_INDEXO,HY_INDEXL,HY_INDEXC);
```

## DKCOL  ���������(�����ڷ�ʱ��ͼ)(ϵͳ)

``` pascal
FF:=(C-REF(C,N))/REF(C,N);
STICKLINE(FF>0,DYNAINFO(3),DYNAINFO(3)*(1+FF),0.5,0),COLORRED;
STICKLINE(FF<0,DYNAINFO(3),DYNAINFO(3)*(1+FF),0.5,0),COLORGREEN;
```

## FKX  ��K��(ϵͳ)

``` pascal
DRAWKLINE(-LOW, -OPEN, -HIGH, -CLOSE);
```

## ZJLX  �ʽ�����(ϵͳ)

``` pascal
��B:=L2_AMO(0,2)/10000.0;
��B:=L2_AMO(1,2)/10000.0;
��B:=L2_AMO(2,2)/10000.0;
СB:=L2_AMO(3,2)/10000.0;
��S:=L2_AMO(0,3)/10000.0;
��S:=L2_AMO(1,3)/10000.0;
��S:=L2_AMO(2,3)/10000.0;
СS:=L2_AMO(3,3)/10000.0;
�ʽ�����:(��B+��B+��B+СB)-(��S+��S+��S+СS),NODRAW;
STICKLINE(�ʽ�����>0,0,�ʽ�����,2,0),COLORRED;
STICKLINE(�ʽ�����<0,0,�ʽ�����,2,0),COLORCYAN;
��5������:SUM(�ʽ�����,5),NODRAW;
��10������:SUM(�ʽ�����,10),NODRAW;
```

## ZJQDL  �ʽ�������(ϵͳ)

``` pascal
��B:=L2_AMO(0,2)/10000.0;
��B:=L2_AMO(1,2)/10000.0;
��B:=L2_AMO(2,2)/10000.0;
СB:=L2_AMO(3,2)/10000.0;
��S:=L2_AMO(0,3)/10000.0;
��S:=L2_AMO(1,3)/10000.0;
��S:=L2_AMO(2,3)/10000.0;
СS:=L2_AMO(3,3)/10000.0;
������:(��B+��B+��B+СB)-(��S+��S+��S+СS);
���ھ�����:(��B+��B)-(��S+��S);
```

## ZJBY  �ʽ���(ϵͳ)

``` pascal
��B:=L2_AMO(0,2)/10000.0;
��B:=L2_AMO(1,2)/10000.0;
��B:=L2_AMO(2,2)/10000.0;
СB:=L2_AMO(3,2)/10000.0;
��S:=-L2_AMO(0,3)/10000.0;
��S:=-L2_AMO(1,3)/10000.0;
��S:=-L2_AMO(2,3)/10000.0;
СS:=-L2_AMO(3,3)/10000.0;
������:(��B+��B+��B+СB)+(��S+��S+��S+СS),NODRAW;
����:(��B)+(��S);
��:(��B)+(��S);
�е�:(��B)+(��S);
С��:(СB)+(СS);
```

## DDX  �󵥶���(ϵͳ)

``` pascal
�󵥶���:(LARGEINTRDVOL-LARGEOUTTRDVOL)*10000/FINANCE(7),NODRAW;
NOTEXT1:MA(�󵥶���,N)*3;
STICKLINE(�󵥶���>0,0,�󵥶���,2,0),COLORRED;
STICKLINE(�󵥶���<0,0,�󵥶���,2,0),COLORCYAN;
```

## DDY  �ǵ�����(ϵͳ)

``` pascal
�ǵ�����:IF(TRADENUM>0,(TRADEOUTNUM-TRADEINNUM)*100/TRADENUM,0),NODRAW;
NOTEXT1:MA(�ǵ�����,N)*3;
STICKLINE(�ǵ�����>0,0,�ǵ�����,2,0),COLORRED;
STICKLINE(�ǵ�����<0,0,�ǵ�����,2,0),COLORCYAN;
```

## DDZ  �󵥲��(ϵͳ)

``` pascal
�󵥲��:IF(TRADENUM>0,(LARGETRDINNUM-LARGETRDOUTNUM)/TRADENUM*100,0),NODRAW;
DDZ1:=�󵥲��*7;
DDZ2:=�󵥲��*3;
DRAWBAND(DDZ1,RGB(255,32,32),DDZ2,RGB(0,224,224));
```

## DDF  ��Ƶ��(ϵͳ)

``` pascal
��Ƶ��:IF(TRADENUM>0,LARGETRDINNUM*100/TRADENUM,0),NODRAW;
NOTEXT1:MA(��Ƶ��,N)*2;
STICKLINE(1,0,��Ƶ��,2,0);
```

## SUPL  ������ɢ��(ϵͳ)

``` pascal
������ɢ��:SUM((LARGEINTRDVOL-LARGEOUTTRDVOL)*10000/FINANCE(7),0),LINETHICK2;
MA1:MA(������ɢ��,N),COLORBROWN;
```

## SUPV  ����������(ϵͳ)

``` pascal
����������:(LARGEINTRDVOL-LARGEOUTTRDVOL);
��������:LARGEINTRDVOL,COLORRED,NODRAW;
��������:LARGEOUTTRDVOL,COLORGREEN,NODRAW;
STICKLINE(1,0,IF(��������>0,VOL,0),2,0),COLORBROWN;
STICKLINE(1,0,IF(��������>0,-VOL,0),2,0),COLORBROWN;
STICKLINE(1,0,��������,2,0),COLORRED;
STICKLINE(1,0,(-1*��������),2,0),COLORGREEN;
```

## SUPH  ������Ծ��(ϵͳ)

``` pascal
TMP:=LARGEINTRDVOL-LARGEOUTTRDVOL;
������Ծ��:(LARGEINTRDVOL+LARGEOUTTRDVOL)*10000/(2*FINANCE(7)),NODRAW;
STICKLINE(TMP>0,0,������Ծ��,2,0),COLORLIRED;
STICKLINE(TMP=0,0,������Ծ��,2,0),COLORYELLOW;
STICKLINE(TMP<0,0,������Ծ��,2,0),COLORLIGREEN;
```

## SUPAMO  �����ʽ���(ϵͳ)

``` pascal
�����ʽ���:(L2_AMO(0,0)+L2_AMO(1,0)-L2_AMO(0,1)-L2_AMO(1,1))/10000.0,LINETHICK2;
```

## DDE����  DDE,��������(ϵͳ)

``` pascal
DDX:(LARGEINTRDVOL-LARGEOUTTRDVOL)*10000/FINANCE(7);
DDY:IF(TRADENUM>0,(TRADEOUTNUM-TRADEINNUM)*100/TRADENUM,0);
DDZ:IF(TRADENUM>0,(LARGETRDINNUM-LARGETRDOUTNUM)/TRADENUM*100,0);
```

## SUP����  SUP,��������(ϵͳ)

``` pascal
SUPL:SUM((LARGEINTRDVOL-LARGEOUTTRDVOL)*10000/FINANCE(7),0);
SUPV:(LARGEINTRDVOL-LARGEOUTTRDVOL);
SUPH:(LARGEINTRDVOL+LARGEOUTTRDVOL)*10000/(2*FINANCE(7));
SUPAMO:(L2_AMO(0,0)+L2_AMO(1,0)-L2_AMO(0,1)-L2_AMO(1,1))/10000.0;
```

## DDE����  DDE����,��������(ϵͳ)

``` pascal
����������:LARGEINTRDVOL*100/VOL;
����������:LARGEOUTTRDVOL*100/VOL;
```

## ����ѡ�ɹ�ʽ

``` pascal

```

## UPN  ��������(ϵͳ)

``` pascal
UP3:UPNDAY(CLOSE,N);
```

## DOWNN  ��������(ϵͳ)

``` pascal
DOWN3:DOWNNDAY(CLOSE,N);
```

## BIAS����  ��������������ѡ��(ϵͳ)

``` pascal
(CLOSE-MA(CLOSE,N))/MA(CLOSE,N)*100+LL<0;
```

## KD����  KD��������ѡ��(ϵͳ)

``` pascal
RSV:=(CLOSE-LLV(LOW,N))/(HHV(HIGH,N)-LLV(LOW,N))*100;
K:=SMA(RSV,M1,1);
D:=SMA(K,M2,1);
KD:CROSS(K,D)&&K<20;
```

## MSTAR  �糿֮��(ϵͳ)

``` pascal
STAR:REF(CLOSE,2)/REF(OPEN,2)<0.95&&
REF(OPEN,1)<REF(CLOSE,2)&&
ABS(REF(OPEN,1)-REF(CLOSE,1))/REF(CLOSE,1)<0.03&&
CLOSE/OPEN>1.05&&CLOSE>REF(CLOSE,2);
```

## W&R����  ����ָ����������ѡ��(ϵͳ)

``` pascal
CROSS(LL,WR(N,N));
```

## MTM����  MTM��������ѡ��(ϵͳ)

``` pascal
IMTM:CROSS(MTM(N,N),0);
```

## KDJ����  KDJ��������ѡ��(ϵͳ)

``` pascal
RSV:=(CLOSE-LLV(LOW,N1))/(HHV(HIGH,N1)-LLV(LOW,N1))*100;
K:=SMA(RSV,N2,1);
D:=SMA(K,N3,1);
J:=3*K-2*D;
CROSS(J,0);
```

## SWORD  ��(ϵͳ)

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

## TLFZ  ��������(ϵͳ)

``` pascal
STAR:CLOSE>OPEN&&HHV(CLOSE,50)=CLOSE&&DYNAINFO(37)>0.1&&
DYNAINFO(13)<0.14;
```

## GREEN4  �Ĵ���(ϵͳ)

``` pascal
STAR:EVERY(CLOSE<OPEN,4);
```

## RED4  �Ĵ���(ϵͳ)

``` pascal
A:EVERY(CLOSE>OPEN,4);
```

## CSFR  ��ˮܽ��(ϵͳ)

``` pascal
AAA:=CLOSE>OPEN;
BBB:=AAA&&CLOSE>MA(CLOSE,S)&&CLOSE>MA(CLOSE,M)&&CLOSE>MA(CLOSE,N);
CCC:=BBB&&OPEN<MA(CLOSE,M)&&OPEN<MA(CLOSE,N);
CSFR:CCC&&(CLOSE-OPEN)>0.0618*CLOSE;
```

## NHIGH  ���մ���ʷ�¸�(ϵͳ)

``` pascal
HHV(HIGH,N)=HHV(HIGH,0);
```

## NLOW  ���մ���ʷ�µ�(ϵͳ)

``` pascal
LLV(LOW,N)=LLV(LOW,0);
```

## XRDS  ���ճ���(ϵͳ)

``` pascal
BUY1:=LAST(CLOSE<MA(CLOSE,N),0,5);
BUYIT:CLOSE>MA(CLOSE,N)&&VOL>MA(VOL,5)*2&&BUY1;
```

## QTDS  ���ѵ�ˮ(ϵͳ)

``` pascal
BUY1:=LAST(CLOSE>MA(CLOSE,N),0,5);
BUY2:=EXIST(CLOSE<MA(CLOSE,N),5);
BUYIT:USEDDATANUM>N+50 && CLOSE>MA(CLOSE,N) && BUY1 && BUY2;
```

## A001  �Ͷ�̬��ӯ��ѡ��(ϵͳ)

``` pascal
DYNAINFO(39)>0 AND DYNAINFO(39)<=N;
```

## A003  Ӫҵ������ѡ��(ϵͳ)

``` pascal
FINANCE(20)>0 && FINANCE(23)/FINANCE(20)>N/100;
```

## A004  �о���ѡ��(ϵͳ)

``` pascal
FINANCE(34)>0 AND CLOSE/FINANCE(34)<N;
```

## A005  ���¹�ѡ��(ϵͳ)

``` pascal
FINANCE(42)<N;
```

## A006  PEGѡ��(ϵͳ)

``` pascal
PE:=DYNAINFO(39);
EPSRATE:=FINANCE(43);
PE>0 && PE<50 && EPSRATE>0 && PE/EPSRATE<1;
```

## A008  �ͷ���ѡ��(ϵͳ)

``` pascal
A1:=(FINANCE(20)-FINANCE(21) )/FINANCE(20)*100>N1;{����ë����}
A2:=FINANCE(30)/FINANCE(20)*100>N2;{������}
A3:=FINANCE(30)/FINANCE(19)*100>N3;{���ʲ�������}
A1 AND A2 AND A3;
```

## A011  ���ܵ�ָ��ɻ��Ĺ�(ϵͳ)

``` pascal
AAA:=BARSLASTCOUNT(FINANCE(7)*CLOSE>��ֵ*10000*10000)>=����;
BBB:=(10000*(SUM(VOL,����2))/FINANCE(7))>����;
CCC:=(FINANCE(7)>�ɱ�*10000*10000);
AAA&&BBB&&CCC;
```

## B003  ������ѡ��(����)(ϵͳ)

``` pascal
(DYNAINFO(23)>DYNAINFO(22)) AND (DYNAINFO(7)>DYNAINFO(3));
```

## B004  ������ѡ��(�µ�)(ϵͳ)

``` pascal
(DYNAINFO(22)>DYNAINFO(23)) AND (DYNAINFO(7)<DYNAINFO(3));
```

## B005  ���л�Ծ�ͼ۹�(ϵͳ)

``` pascal
DYNAINFO(7)<�۸� AND DYNAINFO(14)>(����Ƿ�/100) AND DYNAINFO(14)<0.2 AND DYNAINFO(17)>���� AND (SELLVOL/BUYVOL)<�����;
```

## B006  ���з�ʱ���ֽ��(ϵͳ)

``` pascal
DYNAINFO(7)>MAX(DYNAINFO(11)+0.01,DYNAINFO(11)*1.001) AND DYNAINFO(25)<DYNAINFO(11);
```

## B007  ��ǰ�����ǵ�ͣѡ��(ϵͳ)

``` pascal
ISST��:=NAMEINCLUDE('ST');
��ͣ10:=NOT(ISST��) AND DYNAINFO(5)=ZTPRICE(DYNAINFO(3),0.1) AND DYNAINFO(5)>0;
��ͣ5:=ISST�� AND DYNAINFO(5)=ZTPRICE(DYNAINFO(3),0.05) AND DYNAINFO(5)>0;
������ͣ:=(��ͣ10 OR ��ͣ5) AND (����һ�ְ� OR (NOT(����һ�ְ�) AND DYNAINFO(5)!=DYNAINFO(6)));
��ǰ��ͣ:=������ͣ AND MAX(DYNAINFO(20),DYNAINFO(7))=DYNAINFO(5) AND DYNAINFO(59)<1;
��������ͣ:=������ͣ AND NOT(��ǰ��ͣ);
��ͣ10:=NOT(ISST��) AND DYNAINFO(6)=DTPRICE(DYNAINFO(3),0.1) AND DYNAINFO(6)>0;
��ͣ5:=ISST�� AND DYNAINFO(6)=DTPRICE(DYNAINFO(3),0.05) AND DYNAINFO(6)>0;
���е�ͣ:=(��ͣ10 OR ��ͣ5) AND (����һ�ְ� OR (NOT(����һ�ְ�) AND DYNAINFO(5)!=DYNAINFO(6)));
��ǰ��ͣ:=���е�ͣ AND MIN(DYNAINFO(21),DYNAINFO(7))=DYNAINFO(6) AND DYNAINFO(58)<1;
�����е�ͣ:=���е�ͣ AND NOT(��ǰ��ͣ);
��ͣRET:=IF(�ǵ�ͣ����=0,������ͣ,IF(�ǵ�ͣ����=1,��ǰ��ͣ,��������ͣ));
��ͣRET:=IF(�ǵ�ͣ����=3,���е�ͣ,IF(�ǵ�ͣ����=4,��ǰ��ͣ,�����е�ͣ));
IF(�ǵ�ͣ����<3,��ͣRET,��ͣRET);
```

## DTPL  ���߶�ͷ����(ϵͳ)

``` pascal
A1:=MA(CLOSE,N);
A2:=MA(CLOSE,N1);
A3:=MA(CLOSE,N2);
A4:=MA(CLOSE,N3);
CLOSE>A1 AND A1>A2 AND A2>A3 AND A3>A4 AND CLOSE>OPEN;
```

## KTPL  ���߿�ͷ����(ϵͳ)

``` pascal
A1:=MA(CLOSE,N);
A2:=MA(CLOSE,N1);
A3:=MA(CLOSE,N2);
A4:=MA(CLOSE,N3);
CLOSE<A1 AND A1<A2 AND A2<A3 AND A3<A4 AND CLOSE<OPEN;
```

## QSZL  ǿ������(ϵͳ)

``` pascal
A1:=ABS(CLOSE-OPEN)/OPEN<0.015;
A2:=COUNT(A1,N)=N;
A3:=REF(OPEN,N)<REF(CLOSE,N) AND 
REF(CLOSE,N)/REF(CLOSE,N+1)>1+M/100;
A2 AND A3;
```

## W-103  �߿�������(ϵͳ)

``` pascal
OPEN/REF(CLOSE,1)>=1+M/100 && CLOSE/OPEN<=1-N/100;
```

## W-104  �Ϳ�������(ϵͳ)

``` pascal
OPEN/REF(CLOSE,1)<=1-M/100 && CLOSE/OPEN>=1+N/100;
```

## W-105  ����ȱ��ѡ��(ϵͳ)

``` pascal
HIGH<(REF(LOW,1)-0.001) || LOW>(REF(HIGH,1)+0.001);
```

## BIAS����  ��������������ѡ��(ϵͳ)

``` pascal
100*(CLOSE-MA(CLOSE,N))/MA(CLOSE,N)>M;
```

## BOLL����  ���ִ���������ѡ��(ϵͳ)

``` pascal
MID :=  MA(CLOSE,N);
UPPER:= MID+S*STD(CLOSE,N);
LOWER:= MID-S*STD(CLOSE,N);
CROSS(CLOSE,LOWER);
```

## BOLL����  ���ִ���������ѡ��(ϵͳ)

``` pascal
MID :=  MA(CLOSE,N);
UPPER:= MID+PP*STD(CLOSE,N);
LOWER:= MID-PP*STD(CLOSE,N);
CROSS(UPPER,CLOSE);
```

## KD����  KD��������ѡ��(ϵͳ)

``` pascal
RSV:= (CLOSE-LLV(LOW,N))/(HHV(HIGH,N)-LLV(LOW,N))*100;
K:=SMA(RSV,N1,1);
D:=SMA(K,N2,1);
CROSS(D,K) AND D>N3;
```

## KDJ����  KDJ��������ѡ��(ϵͳ)

``` pascal
RSV:=(CLOSE-LLV(LOW,N1))/(HHV(HIGH,N1)-LLV(LOW,N1))*100;
K:=SMA(RSV,N2,1);
D:=SMA(K,N3,1);
J:=3*K-2*D;
CROSS(100,J);
```

## MA����  ������������ѡ��(ϵͳ)

``` pascal
CROSS(MA(CLOSE,SHORT),MA(CLOSE,LONG));
```

## MA����  ������������ѡ��(ϵͳ)

``` pascal
CROSS(MA(CLOSE,M),MA(CLOSE,N));
```

## MACD����  MACD���������ѡ��(ϵͳ)

``` pascal
DIFF := EMA(CLOSE,SHORT) - EMA(CLOSE,LONG);
DEA  := EMA(DIFF,M);
CROSS(DIFF,DEA);
```

## MACD����  MACD��������ѡ��(ϵͳ)

``` pascal
DIFF := EMA(CLOSE,SHORT) - EMA(CLOSE,LONG);
DEA  := EMA(DIFF,M);
CROSS(DEA ,DIFF);
```

## MTM����  MTM��������ѡ��(ϵͳ)

``` pascal
CROSS(0,MA(CLOSE-REF(CLOSE,N),N1));
```

## RSI����  RSI��������ѡ��(ϵͳ)

``` pascal
LC:= REF(CLOSE,1);
RSI1:=SMA(MAX(CLOSE-LC,0),N,1)/SMA(ABS(CLOSE-LC),N,1)*100;
CROSS(RSI1,LL);
```

## RSI����  RSI��������ѡ��(ϵͳ)

``` pascal
LC := REF(CLOSE,1);
RSI1:=SMA(MAX(CLOSE-LC,0),N,1)/SMA(ABS(CLOSE-LC),N,1)*100;
CROSS(LL,RSI1);
```

## SAR����  ����ת����������ѡ��(ϵͳ)

``` pascal
SARTURN(N,STEP,MAXP)=1;
```

## SAR����  ����ת����������(ϵͳ)

``` pascal
SARTURN(N,STEP,MAXP)=-1;
```

## W&R����  ����ָ����������ѡ��(ϵͳ)

``` pascal
WR:=100*(HHV(HIGH,N)-CLOSE)/(HHV(HIGH,N)-LLV(LOW,N));
CROSS(M,WR);
```

## RUBLINE  �����(ϵͳ)

``` pascal
A1:=(REF(H,1)-MAX(REF(C,1),REF(O,1)))/(REF(H,1)-REF(L,1))*100>N;{��Ӱ��ռK�ߵ�N%����}
A2:=(MIN(O,C)-L)/(H-L)*100>N;{��Ӱ��ռK�ߵ�N%����}
A3:=ABS(C-REF(C,1))/MIN(C,REF(C,1))*100<2;{��ӰK�ĵ������ܳ���2%}
A4:=REF(C,2)>REF(C,3);{�����̬ǰ����}
A5:=V<REF(V,1);{����}
A7:A1 AND A2 AND A3 AND A4 AND A5;
```

## SP  �͵���Ѱ(ϵͳ)

``` pascal
W:=MA((LLV(LOW,45)-CLOSE)/(HHV(HIGH,45)-LLV(LOW,45))*100,N);
CROSS(-5,W);
```

## TP  ͻ��(ϵͳ)

``` pascal
M1:=MA(C,N1);{���ڲ�����5}
M2:=MA(C,N2);{���ڲ�����10}
M3:=MA(C,N3);{���ڲ�����30}
{���¼��㽻����������}
D1:=BARSLAST(CROSS(M1,M2));{���ϴ���}
D2:=BARSLAST(CROSS(M1,M3));{���ϴ���}
D3:=BARSLAST(CROSS(M2,M3));{���ϴ���}
T1:=CROSS(M2,M3);{���������ϴ�����}
T2:=D1>=D2 AND D2>=D3;{���水ָ�����Ⱥ����}
T3:=COUNT(CROSS(M2,M1) OR CROSS(M3,M2) OR CROSS(M3,M1),D1)=0;{�м��޼�����������}
T4:=REF(M1<M3 AND M2<M3,D1+1);{���ϴ���ǰһ��̡������ڳ���֮��}
JT:T1 AND T2 AND T3 AND T4;{����ȷ��};
```

## PRD  ��͸��(����)(ϵͳ)

``` pascal
PR:(WINNER(CLOSE)-REF(WINNER(CLOSE),1))>P1*VOL/CAPITAL;
```

## PRX  ��͸��(С��)(ϵͳ)

``` pascal
PR:(WINNER(CLOSE)-REF(WINNER(CLOSE),1))<P1*VOL/CAPITAL;
```

## ASRD  �������(����)(ϵͳ)

``` pascal
ASR:100*(WINNER(CLOSE*1.1)-WINNER(CLOSE*0.9))>P1*WINNER(HHV(HIGH,0));
```

## ASRX  �������(С��)(ϵͳ)

``` pascal
ASR:100*(WINNER(CLOSE*1.1)-WINNER(CLOSE*0.9))<P1*WINNER(HHV(HIGH,0));
```

## C101  N���ڴ��¸�(ϵͳ)

``` pascal
HHV(HIGH,N)=HHV(HIGH,0) AND BARSCOUNT(CLOSE)>=N;
```

## C102  N���ڴ��µ�(ϵͳ)

``` pascal
LLV(LOW,N)=LLV(LOW,0) AND BARSCOUNT(CLOSE)>=N;
```

## C103  M�������߶�������(ϵͳ)

``` pascal
COUNT(OPEN>CLOSE,M)/M >= N/100;
```

## C104  M�������߶�������(ϵͳ)

``` pascal
COUNT(OPEN<CLOSE,M)/M >= N/100;
```

## C105  N�������Ƕ����µ�(ϵͳ)

``` pascal
COUNT(CLOSE>REF(CLOSE,1),M)/M >= N/100;
```

## C106  N�����µ���������(ϵͳ)

``` pascal
COUNT(CLOSE<REF(CLOSE,1),M)/M >= N/100;
```

## C107  ����N��������(ϵͳ)

``` pascal
EVERY(CLOSE>OPEN,N);
```

## C108  ����N��������(ϵͳ)

``` pascal
EVERY(OPEN>CLOSE,N);
```

## C128  N���ڳ�������ͣ����(ϵͳ)

``` pascal
ZT:=(CLOSE>=ZTPRICE(REF(CLOSE,1),0.1)); { ����ͣ���� }
ZTO:FINANCE(42)>200 AND EXIST(ZT,N); { ������200��,N���������ͣ���� };
```

## C129  N���ڳ�����ͣ(ϵͳ)

``` pascal
EZT:=(HIGH>=ZTPRICE(REF(CLOSE,1),0.1)); { ���ֹ���ͣ }
EZTO:FINANCE(42)>200 AND EXIST(EZT,N); { ������200��,N���ڴ��ڹ���ͣ };
```

## C130  N���ھ�����ͣ(ϵͳ)

``` pascal
ZTTJ:=(CLOSE>=ZTPRICE(REF(CLOSE,1),0.1));
FINANCE(42)>200 AND COUNT(ZTTJ,N)>=��ͣ����;
```

## C110  ���շ���(ϵͳ)

``` pascal
A1:=MA(VOL,5);
A2:=REF(A1,1);
VOL/A2>N AND (IF((SETCODE==0||SETCODE==1),100*VOL,VOL))/CAPITAL>M;
```

## C111  �׶�����(ϵͳ)

``` pascal
100*SUM(VOL,N)/CAPITAL<=M;
```

## C112  �׶η���(ϵͳ)

``` pascal
100*SUM(VOL,N)/CAPITAL>=M;
```

## C113  ��������(ϵͳ)

``` pascal
EVERY(VOL>=REF(VOL,1),M);
```

## C114  ��������(ϵͳ)

``` pascal
COUNT(VOL<=REF(VOL,1),M)=M;
```

## C115  �������(ϵͳ)

``` pascal
A:=MA(VOL,5);
BARSCOUNT(CLOSE)>=N AND HHV(A,N)<N1*LLV(A,N) 
AND COUNT(VOL>N2*A,N)>N3;
```

## C116  �����Ϲ�(ϵͳ)

``` pascal
A:= (CLOSE-REF(CLOSE,1))/REF(CLOSE,1)>=(N/100);
100*SUM(VOL,N1)/CAPITAL>=N2 
AND COUNT(VOL>REF(VOL,1),N3)=N3 AND  COUNT(A,N3)=N3;
```

## C117  �ºͷ����Ϲ�(ϵͳ)

``` pascal
A1:=CLOSE/REF(CLOSE,1);
A2:=A1>1 AND A1<1.03;
{�ɼ�С������}
B1:=VOL/REF(VOL,1);
B2:=B1>1 AND B1<2;
C1:=100*MA(VOL,N)/CAPITAL<5;
{�ɽ���С������}
COUNT(A2 AND B2,N)/N>0.6 AND C1;
```

## C118  ͻȻ����(ϵͳ)

``` pascal
VOL>REF(HHV(VOL,N),1)*M;
```

## C119  ƽ̨����(ϵͳ)

``` pascal
COUNT(CLOSE>0,0)>N && 
(HHV(CLOSE,N)-LLV(CLOSE,N))/LLV(CLOSE,N)<=(N1/100);
```

## C123  ͻ�Ƴ�������(ϵͳ)

``` pascal
REF(((HHV(HIGH,N)-LLV(LOW,N))/LLV(LOW,N)),1)<=(N1/100) 
 && CLOSE>=REF(HHV(HIGH,N),1) && BARSCOUNT(CLOSE)>N;
```

## C124  �׶�ǿ�ڴ���(ϵͳ)

``` pascal
A:=SUM(IF(CURRBARSCOUNT=N,INDEXC,0),0);
B:=SUM(IF(CURRBARSCOUNT=N1,INDEXC,0),0);
E:=SUM(IF(CURRBARSCOUNT=N,CLOSE,0),0);
F:=SUM(IF(CURRBARSCOUNT=N1,CLOSE,0),0);
((F-E)/E)>(((B-A)/A)+0.01);
```

## C125  �׶����ڴ���(ϵͳ)

``` pascal
A:=SUM(IF(CURRBARSCOUNT=N,INDEXC,0),0);
B:=SUM(IF(CURRBARSCOUNT=N1,INDEXC,0),0);
E:=SUM(IF(CURRBARSCOUNT=N,CLOSE,0),0);
F:=SUM(IF(CURRBARSCOUNT=N1,CLOSE,0),0);
((F-E)/E)<(((B-A)/A)-0.01);
```

## C126  ����ͬ��ѡ��(ϵͳ)

``` pascal
COUNT((CLOSE>OPEN && INDEXC>INDEXO) || (CLOSE<OPEN && INDEXC<INDEXO),N)/N>M/100;
```

## C127  N����ǿ�ƹ�(ϵͳ)

``` pascal
GG:=(CLOSE-REF(OPEN,N))/REF(OPEN,N);
GGG:=IF(GG>0,GG,0);
DP:=(INDEXC-REF(INDEXO,N))/REF(INDEXO,N);
QSG:GGG/DP>=M;
```

## C131  �µ������ٷ�������(ϵͳ)

``` pascal
A1:=REF(CLOSE,5)>REF(CLOSE,4);
A2:=REF(CLOSE,4)>REF(CLOSE,3);
A3:=REF(CLOSE,3)>REF(CLOSE,2);
A4:=REF(CLOSE,2)>REF(CLOSE,1);
A5:=CLOSE>REF(HIGH,1) AND V>REF(V,1);
RET:A1 AND A2 AND A3 AND A4 AND A5;
```

## C132  ���ո߿���Ϳ�(ϵͳ)

``` pascal
A:= (O>REF(H,1) AND (O-REF(C,1))/REF(C,1)*100>N);
B:= (O<REF(L,1) AND (O-REF(C,1))/REF(C,1)*100<N);
IF(N>0,A,B);
```

## ר��ϵͳ��ʽ

``` pascal

```

## BIAS  ������ר��ϵͳ(ϵͳ)

``` pascal
BIAS:=(CLOSE-MA(CLOSE,N))/MA(CLOSE,N)*100;
ENTERLONG:CROSS(-LL,BIAS);
EXITLONG:CROSS(BIAS,LH);
```

## CCI  CCIר��ϵͳ(ϵͳ)

``` pascal
INDEX:=CCI(N);
ENTERLONG:CROSS(INDEX,-100);
EXITLONG:CROSS(100,INDEX);
```

## DMI  ����ר��ϵͳ(ϵͳ)

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

## KD  KDָ��ר��ϵͳ(ϵͳ)

``` pascal
WRSV:=(CLOSE-LLV(LOW,N))/(HHV(HIGH,N)-LLV(LOW,N))*100;
WK:=SMA(WRSV,M1,1);
D:=SMA(WK,M2,1);
ENTERLONG:CROSS(WK,D)&&WK<20;
EXITLONG:CROSS(D,WK)&&WK>80;
```

## BOLL  ���ִ�ר��ϵͳ(ϵͳ)

``` pascal
MID :=MA(CLOSE,N);
UPPER:=MID+2*STD(CLOSE,N);
LOWER:=MID-2*STD(CLOSE,N);
ENTERLONG:CROSS(CLOSE,LOWER);
EXITLONG:CROSS(CLOSE,UPPER);
```

## KDJ  KDJר��ϵͳ(ϵͳ)

``` pascal
RSV:=(CLOSE-LLV(LOW,N))/(HHV(HIGH,N)-LLV(LOW,N))*100;
K:=SMA(RSV,M1,1);
D:=SMA(K,M1,1);
J:=3*K-2*D;
ENTERLONG:CROSS(J,0);
EXITLONG:CROSS(100,J);
```

## MA  ����ר��ϵͳ(ϵͳ)

``` pascal
ENTERLONG:CROSS(MA(CLOSE,SHORT),MA(CLOSE,LONG));
EXITLONG:CROSS(MA(CLOSE,LONG),MA(CLOSE,SHORT));
```

## MACD  MACDר��ϵͳ(ϵͳ)

``` pascal
DIFF:=EMA(CLOSE,SHORT) - EMA(CLOSE,LONG);
DEA  := EMA(DIFF,M);
MACD := 2*(DIFF-DEA);
ENTERLONG:CROSS(MACD,0);
EXITLONG:CROSS(0,MACD);
```

## MTM  ����ָ��ר��ϵͳ(ϵͳ)

``` pascal
WMTM:=MTM;
ENTERLONG:CROSS(WMTM,0);
EXITLONG:CROSS(0,WMTM);
```

## PSY  PSY������ר��ϵͳ(ϵͳ)

``` pascal
MYPSY:=PSY(N,1);
ENTERLONG:CROSS(LL,MYPSY);
EXITLONG:CROSS(MYPSY,LH);
```

## ROC  �䶯����ר��ϵͳ(ϵͳ)

``` pascal
WROC:=ROC(N,M);
ENTERLONG:CROSS(WROC,0);
EXITLONG:CROSS(0,WROC);
```

## RSI  ���ǿ��ר��ϵͳ(ϵͳ)

``` pascal
LC:=REF(CLOSE,1);
WRSI:=SMA(MAX(CLOSE-LC,0),N,1)/SMA(ABS(CLOSE-LC),N,1)*100;
ENTERLONG:CROSS(WRSI,LL);
EXITLONG:CROSS(LH,WRSI);
```

## VR  VR��������ר��ϵͳ(ϵͳ)

``` pascal
WVR := SUM((IF(CLOSE>OPEN,VOL,0)+IF(CLOSE=OPEN,VOL/2,0)),N)/
SUM((IF(CLOSE<OPEN,VOL,0)+IF(CLOSE=OPEN,VOL/2,0)),N)*100;
ENTERLONG:CROSS(LL,WVR);
EXITLONG:CROSS(WVR,LH);
```

## DPSJ  �������ר��ϵͳ(ϵͳ)

``` pascal
RSV:=(INDEXC-LLV(INDEXL,N1))/(HHV(INDEXH,N1)-LLV(INDEXL,N1))*100;
K:=SMA(RSV,N2,1);
ENTERLONG: CROSS(K,20);
EXITLONG: (CROSS(HSL,5) OR CROSS(K,80));
```

## ���K�߹�ʽ

``` pascal

```

## KSTAR1  ʮ����(ϵͳ)

``` pascal
KSTAR:CLOSE=OPEN&&HIGH>LOW;
```

## KSTAR2  �糿֮��(ϵͳ)

``` pascal
KSTAR:(REF(CLOSE,2)/REF(OPEN,2)<0.95)&&
(REF(OPEN,1) < REF(CLOSE,2))&&
(ABS(REF(OPEN,1)-REF(CLOSE,1))/REF(CLOSE,1)<0.03) && 
CLOSE/OPEN>1.05 && CLOSE>REF(CLOSE,2);
```

## KSTAR3  �ƻ�֮��(ϵͳ)

``` pascal
KSTAR:REF(CLOSE,2)/REF(OPEN,2)>1.05&&
REF(OPEN,1)>REF(CLOSE,2)&&
ABS(REF(OPEN,1)-REF(CLOSE,1))/REF(CLOSE,1)<0.03&&
CLOSE/OPEN<0.95&&CLOSE<REF(CLOSE,2);
```

## SHI1  ��ʮ��(ϵͳ)

``` pascal
KSTAR:CLOSE=OPEN&&HIGH/LOW>1.03;
```

## K220  ������(ϵͳ)

``` pascal
KSTAR:ABS(REF(CLOSE,1)-REF(OPEN,1))/REF(CLOSE,1)>0.04&&
ABS(CLOSE-OPEN)/CLOSE<0.005&&
MAX(CLOSE,OPEN)<MAX(REF(CLOSE,1),REF(OPEN,1))&&
MIN(CLOSE,OPEN)>MIN(REF(CLOSE,1),REF(OPEN,1));
```

## K300  ��������ʿ(ϵͳ)

``` pascal
KSTAR:UPNDAY(CLOSE,3)&&NDAY(CLOSE,OPEN,3);
```

## K310  ��ֻ��ѻ(ϵͳ)

``` pascal
KSTAR:DOWNNDAY(CLOSE,3)&&NDAY(OPEN,CLOSE,3);
```

## K380  ��ͷ����(ϵͳ)

``` pascal
KSTAR:HIGH=CLOSE&&HIGH>LOW;
```

## K390  �������(ϵͳ)

``` pascal
KSTAR:LOW=CLOSE&&HIGH>LOW;
```

## K134  ����ʮ��(ϵͳ)

``` pascal
KSTAR:CLOSE=OPEN&&CLOSE=LOW&&CLOSE<HIGH;
```

## K140  �糿ʮ����(ϵͳ)

``` pascal
KSTAR:REF(CLOSE,2)/REF(OPEN,2)<0.95&&
REF(OPEN,1)<REF(CLOSE,2)&&
REF(OPEN,1)=REF(CLOSE,1)&&
CLOSE/OPEN>1.05&&CLOSE>REF(CLOSE,2);
```

## K150  �ƻ�ʮ����(ϵͳ)

``` pascal
KSTAR:REF(CLOSE,2)/REF(OPEN,2)>1.05&&
REF(OPEN,1)>REF(CLOSE,2)&&
REF(OPEN,1)=REF(CLOSE,1)&&
CLOSE/OPEN<0.95&&CLOSE<REF(CLOSE,2);
```

## K160  ���֮��(ϵͳ)

``` pascal
KSTAR:MIN(OPEN,CLOSE)=LOW&&
HIGH-LOW>3*(MAX(OPEN,CLOSE)-LOW)&&
CLOSE>MA(CLOSE,5);
```

## K165  ��ת��ͷ(ϵͳ)

``` pascal
KSTAR:MIN(OPEN,CLOSE)=LOW&&
HIGH-LOW>3*(MAX(OPEN,CLOSE)-LOW)&&
CLOSE<MA(CLOSE,5);
```

## K170  ��ͷ(ϵͳ)

``` pascal
OUT:HIGH=MAX(OPEN,CLOSE)&&
HIGH-LOW>3*(HIGH-MIN(OPEN,CLOSE))&&
CLOSE<MA(CLOSE,5);
```

## K180  ����(ϵͳ)

``` pascal
OUT:HIGH=MAX(OPEN,CLOSE)&&
HIGH-LOW>3*(HIGH-MIN(OPEN,CLOSE))&&
CLOSE>MA(CLOSE,5);
```

## K190  ��ͷ�ƽ�(ϵͳ)

``` pascal
OUT:(REF(CLOSE,1)/REF(OPEN,1)>1.03&&
CLOSE/OPEN<0.96&&
CLOSE<REF(OPEN,1)&&OPEN>REF(CLOSE,1))||
(REF(CLOSE,1)/REF(OPEN,1)<0.97&&
CLOSE/OPEN>1.04&&
CLOSE>REF(OPEN,1)&&OPEN<REF(CLOSE,1));
```

## SWORD  ��(ϵͳ)

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

## CSFR  ��ˮܽ��(ϵͳ)

``` pascal
A:=CLOSE>OPEN;
B:=A&&CLOSE>MA(CLOSE,S)&&CLOSE>MA(CLOSE,M)&&CLOSE>MA(CLOSE,LL);
CC:=B&&OPEN<MA(CLOSE,M)&&OPEN<MA(CLOSE,LL);
CSFRO:CC&&(CLOSE-OPEN)>0.0618*CLOSE;
```

## WYGD  ���ƸǶ� (ϵͳ)

``` pascal
BACKSET( 
REF(CLOSE,1)/REF(OPEN,1)>1.03 AND 
CLOSE/OPEN<0.97 AND 
OPEN>REF(CLOSE,1) AND CLOSE<REF(CLOSE,1), 3);
```

## SGCJ  ������ (ϵͳ)

``` pascal
BACKSET( 
REF(CLOSE,1)/REF(OPEN,1)<0.97 AND 
CLOSE/OPEN>1.03 AND 
OPEN<REF(CLOSE,1) AND CLOSE>REF(CLOSE,1), 3);
```

## SZTAI  ʮ��̥ (ϵͳ)

``` pascal
BACKSET( ABS(REF(CLOSE,1)-REF(OPEN,1))/REF(CLOSE,1) > 0.04 AND 
CLOSE=OPEN AND CLOSE < MAX(REF(CLOSE,1),REF(OPEN,1)) AND 
CLOSE > MIN(REF(CLOSE,1),REF(OPEN,1)), 2);
```

## PINGDING  ƽ�� (ϵͳ)

``` pascal
BACKSET(ABS(HIGH-REF(HIGH,1))/HIGH<0.001,2);
```

## PINGDI  ƽ�� (ϵͳ)

``` pascal
BACKSET((ABS(LOW-REF(LOW,1))/LOW<0.001 AND 
ABS(REF(LOW,1)-REF(LOW,2))/REF(LOW,1)<=0.001),2);
```

## DAYANZHU  ������ (ϵͳ)

``` pascal
CLOSE/OPEN>1.05 AND 
HIGH/LOW < CLOSE/OPEN+0.018;
```

## DAYINGZHU  ������ (ϵͳ)

``` pascal
OPEN/CLOSE > 1.05 AND 
HIGH/LOW < OPEN/CLOSE+0.018;
```

## HYFG  ���ѷ��� (ϵͳ)

``` pascal
BACKSET( (REF(CLOSE,1)<REF(OPEN,1) AND 
CLOSE>OPEN AND ABS(CLOSE-REF(CLOSE,1))/CLOSE<0.002),2);
```

## TKQK  ����ȱ�� (ϵͳ)

``` pascal
BACKSET( HIGH<REF(LOW,1) OR LOW>REF(HIGH,1),2);
```

## SFWY  ˫����ѻ (ϵͳ)

``` pascal
BACKSET( REF(CLOSE,1)<REF(OPEN,1) AND CLOSE<OPEN AND CLOSE/OPEN<0.98,1);
```

## SSSBQ  ����������(ϵͳ)

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

## XDSBQ  �µ�������(ϵͳ)

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

## CHXY  ����Ӱ(ϵͳ)

``` pascal
(MIN(CLOSE,OPEN)-LOW)/(HIGH-LOW)>0.667;
```

## CHSY  ����Ӱ(ϵͳ)

``` pascal
(HIGH-MAX(CLOSE,OPEN))/(HIGH-LOW)>0.667,COLORBLUE;
```

## FENLI  ����(ϵͳ)

``` pascal
BACKSET( OPEN=REF(OPEN,1) AND 
(CLOSE-OPEN)*(REF(CLOSE,1)-REF(OPEN,1))<0,2);
```

## NXSD  ţ��ʱ��(ϵͳ)

``` pascal

```

