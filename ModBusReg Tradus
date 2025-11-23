# Registre Modbus RTU - Invertor Hibrid

## Zona Atribute Fixe (Intrinsic Attribute Region)

| Addr | Nume Registru | R/W | Interval | Unitate | Note |
|------|---------------|-----|----------|---------|------|
| 000 | Tip dispozitiv | R | - | - | 0x0200 invertor string, 0x0300 stocare monofazat low voltage, 0x0400 microinvertor, 0x0500 stocare trifazat low voltage, 0x0600 stocare trifazat high voltage |
| 001 | Adresă Modbus | R | [1,247] | - | MI |
| 002 | Versiune protocol comunicație | R | '0'~'9'; 'A'~'Z' | - | Versiune protocol firmware, ex: 0x0102 = versiune 1.2 MI |
| 003 | SN byte 01 | R | '0'~'9'; 'A'~'Z' | - | Număr serial 10 caractere ASCII. Ex: "AH12345678" - Byte 01=0x41(A), Byte 02=0x48(H)...Byte 09=0x37(7), Byte 10=0x38(8). MI |
| | SN byte 02 | | | | |
| 004 | SN byte 03 | R | '0'~'9'; 'A'~'Z' | - | |
| | SN byte 04 | | | | |
| 005 | SN byte 05 | R | '0'~'9'; 'A'~'Z' | - | |
| | SN byte 06 | | | | |
| 006 | SN byte 07 | R | '0'~'9'; 'A'~'Z' | - | |
| | SN byte 08 | | | | |
| 007 | SN byte 09 | R | '0'~'9'; 'A'~'Z' | - | |
| | SN byte 10 | | | | |
| 008 | Putere nominală | R | 0x0000 | - | 2=invertor monofazat, 3=invertor trifazat, 8=invertor stocare monofazat |
| | Flag sistem microinvertor | | | | Bit0: 1=enable registru 18 număr căi mppt, 0=enable, număr căi determinat de putere nominală |
| 009 | Tip chip | R | 0x0000 | - | 4 biți inferiori: AT32F403A_DEVICE=1, SXX32F103_DEVICE=2, GD32F103_DEVICE=3, GD32F303_DEVICE=4 |
| 010 | Versiune firmware placă comunicație câmp 2 | R | - | - | |
| 011 | Versiune program auxiliar placă control | R | - | - | |
| 012 | Versiune firmware placă control câmp 2 | R | - | - | |
| 013 | Versiune firmware placă control | R | - | - | MI |
| 014 | Versiune firmware placă comunicație | R | - | - | |
| 015 | Tip standard siguranță | R | - | - | MI (<3: baterie 48V, =3: baterie 24V) |
| 016 | Putere nominală octet jos | R | - | 0.1W | MI |
| 017 | Putere nominală octet înalt | R | - | 0.1W | MI |
| 018 | Număr căi MPPT și faze | R | [1,8]/[1,3] | - | MI (ex: 0x0503 = 5 mppt-uri trifazat) |
| 019 | Nivel tensiune rețea nominală | R/W | [0-3] | - | 0: 127/220V, 1: 220/380V |

## Zona Atribute Variabile (Variable Attribute Area)

| Addr | Nume Registru | R/W | Interval | Unitate | Note |
|------|---------------|-----|----------|---------|------|
| 020 | Enable blocare de la distanță | R/W | - | - | Închis=0x0002, Deschis=0x0000 |
| 021 | Timp autotest pornire | R/W | [0,1000] | S | MI |
| 022 | Timp sistem byte 01 | R/W | [0,255] | An | MI (baza an 2000) |
| | Timp sistem byte 02 | | [1,12] | Lună | |
| 023 | Timp sistem byte 03 | R/W | [1,31] | Zi | |
| | Timp sistem byte 04 | | [0,23] | Oră | |
| 024 | Timp sistem byte 05 | R/W | [0,59] | Minut | |
| | Timp sistem byte 06 | | [0,59] | Secundă | |
| 025 | Limită inferioară impedanță izolație | R/W | [100,20000] | 0.1KΩ | |
| | Flag CT extern | | | | Bit0: flag calcul putere placă control (software după 2020/10/21 fixat=1, înainte=0), Bit2: flag metodă calcul putere LCD returnată către placă control (1=LCD calculează singur, 0=citește direct registre fără calcul) |
| 026 | Limită superioară tensiune DC | R/W | [2000,10000] | 0.1V | |
| 027 | Limită superioară tensiune rețea | R/W | [1600,5500] | 0.1V | MI |
| 028 | Bit0: ATS Enable, Bit1: ATS status, Bit2: Low power mode<Low Batt, Bit5: MPPT Multi-Point Scanning | R/W | [1600,5500] | 0.1V | 0=disable, 1=enable |
| 029 | Limită superioară frecvență rețea | R/W | [4500,6500] | 0.01Hz | MI |
| 030 | Limită inferioară frecvență rețea | R/W | [4500,6500] | 0.01Hz | MI |
| 031 | Limită superioară curent rețea | R/W | [10,20000] | 0.1A | |
| 032 | Limită superioară tensiune pornire | R/W | [7000,9000] | 0.1V | |
| 033 | Limită inferioară tensiune pornire | R/W | [4500,9000] | 0.1V | |
| 034 | Mod zgomot redus | R/W | [0,1] | - | 1=enable, 0=disable |
| 035 | Procent reducere sarcină suprafrecvență | R/W | [0,100] | - | MI |
| 036 | Limită putere import | R/W | [0,0xFFFF] | 1W | |
| 037 | Adresă comunicație | R | 0x0000 | - | MI |
| 038 | Rată transmisie comunicație (MI: Zigbee sau PLC) | R | 0x0000 | - | MI (0=zigbee, 1=plc) |
| 039 | Reglare factor putere | R/W | [0,2000] | 0.001 | Valoarea reală offset +1000. Ex: -0.852=148, 0=1000, 0.982=1982 |
| 040 | Reglare putere activă | R/W | [0,1200] | 0.1%/1% | Ex: 800=80.0% MI |
| 041 | Reglare putere reactivă | R/W | [0,1200] | 0.1% | Ex: 800=80.0% |
| 042 | Reglare putere aparentă | R/W | [0,1200] | 0.1% | Ex: 800=80.0% |
| 043 | Enable pornire/oprire | R/W | [0,1] | - | 0=oprire, 1=pornire MI, 2=oprire |
| 044 | Enable resetare fabrică | R/W | [0,1] | - | 0=disable, 1=enable |
| 045 | Timp autotest | R/W | [0,1] | - | 0-360 secunde |
| 046 | Timp încărcare Absorption_V | R/W | [0,1] | - | MI (0=disable, 1=enable) |
| 047 | Număr căi MPPT | R/W | [0,1] | - | MI (0=disable, 1=enable) |
| | Enable pornire lentă MI | | | | |
| 048 | Enable autotest Italia CEI | R/W | [0,1] | - | 0=disable, 1=enable |
| 049 | Enable RCD | R/W | [0,1] | - | 0=disable, 1=enable |
| | Enable reducere sarcină suprafrecvență MI | | | | |
| 050 | Enable RISO | R/W | [0,1] | - | 0=disable, 1=enable |
| 051 | Standard rețea | R/W | [0,20] | - | 1=INMETRO, 2=EN50549, 3=EN50438, 4=IEC61727, 5=CUSTOM, 6=VDE_AR_N_4105, 7=UTE_C15_712_1, 8=RD_1699, 9=CEI_0_21, 10=G98_G99, 11=AS4777 |
| 052 | Enable curbă PV | R/W | [0,1] | - | 0=disable, 1=enable |
| | Raport CT | | [1,5000] | | |
| 053 | Putere solară maximă (vechi) | | | | |
| | Potrivire hardware (nou) | R/W | [0,65536] | - | LCD operează acest registru într-o interfață separată. Bit0-1 string monofazat: 0=sistem 500V, 1=sistem 550V, 2-3=rezervat. Bit2-3 string monofazat: 0=PV-10A, 1=PV-12.5A, 2-3=rezervat. Bit4-5 string monofazat: 0=senzor VAC, 1=Tamura, 2=Ximag, 3=rezervat. Bit5-15=rezervat |
| 054 | Precizie putere AC | R | [0,2] | - | 10: registre 167,168,169,170,171,172,176,177,178,179,190,185 au unitate 10W. 1: aceleași registre au unitate 1W |
| 055 | Comandă 1 în test funcțional (doar fabrică) | R/W | [0,3] | - | Bit0: enable test (rest valid după enable), Bit1: pornire toate ventilatoare invertor, Bit2: flash toate LED-uri display, buzzer, backlight, afișare roșu-galben-albastru, Bit3: enable test interfață baterie litiu, Bit4: enable releu semnal Gen, Bit5: restart program LCD |
| 056 | Enable funcție Limiter | R/W | 0x0000 | - | |
| 057 | Coeficient corecție energie generată | R/W | - | -0.01 | 100=1, 111=1.11 |
| 058 | Enable RSD | R/W | 0x0001 | - | 0x0001 |
| | Setări generale | | | | Bit0 Bit1: 01=afișare curent 16 string-uri, 00=nu afișa curent 16 string-uri. Bit2 Bit3: 01=afișare setări 3 niveluri parametri protecție, altfel nu afișa. Bit4-6: rezervat |

## Zona Date Rulare Timp Real (Run Data Area in Real Time)

| Addr | Nume Registru | R/W | Interval | Unitate | Note |
|------|---------------|-----|----------|---------|------|
| 059 | Stare rulare | R | [0,5] | - | 0x0000=așteptare, 0x0001=autotest, 0x0002=normal, 0x0003=alarmă, 0x0004=eroare |
| 060 | Energie activă generată zilnic | R | [-32768,32767] | 0.1kWh | Integer cu semn MI |
| 061 | Energie reactivă generată zilnic | R | [-32768,32767] | 0.1kVarh | Integer cu semn |
| 062 | Energie generată zilnic generator | R | [0,65535] | 0.1kWh | |
| 063 | Total energie activă generată octet jos | R | [0,0xFFFFFFFF] | 0.1kWh | Integer cu semn MI |
| 064 | Total energie activă generată octet înalt | R | - | 0.1kWh | |
| 065 | **String:** Total energie reactivă generată octet jos | R | [0,0xFFFF] | 0.1kVarh | |
| | **Hybrid:** Energie PV lunară | | | 1kWh | |
| | **Hybrid:** Curent baterie 1 | | | 0.01A | |
| | **MI:** Energie generată zilnic panou 1 | | | 0.1kWh | |
| 066 | **String:** Total energie reactivă generată octet înalt | R | [0,0xFFFF] | 0.1kVarh | |
| | **Hybrid:** Energie consumată lunară | | | 1kWh | |
| | **Hybrid:** Curent baterie 2 | | | 0.01A | |
| | **MI:** Energie generată zilnic panou 2 | | | 0.1kWh | |
| 067 | **String:** Total timp funcționare octet jos | R | [0,0xFFFF] | 0.1h | |
| | **Hybrid:** Energie vândută rețea lunară | | | 1kWh | |
| | **MI:** Energie generată zilnic panou 3 | | | 0.1kWh | |
| 068 | **String:** Total timp funcționare octet înalt | R | [0,0xFFFF] | 0.1h | Statistici LCD, DLN inversare octet înalt/jos |
| | **Hybrid:** Energie PV anuală octet jos | | | 0.1kWh | |
| | **MI:** Energie generată zilnic panou 4 | | | 0.1kWh | |
| 069 | **String:** Eficiență invertor | R | [0,999] | 0.1% | |
| | **Hybrid:** Energie PV anuală octet înalt | | | 0.1kWh | |
| | **MI:** Energie cumulată panou 1 octet jos | | | - | |
| 070 | **String:** Tensiune rețea AB | R | [0,9999] | 0.1V | |
| | **Hybrid:** Energie încărcare baterie zilnică | | | 0.1kWh | |
| | **MI:** Energie cumulată panou 1 octet înalt | | | - | |
| 071 | **String:** Tensiune rețea BC | R | [0,9999] | 0.1V | |
| | **Hybrid:** Energie descărcare baterie zilnică | | | 0.1kWh | |
| | **MI:** Energie cumulată panou 2 octet jos | | | - | |
| 072 | **String:** Tensiune rețea AC | R | [0,9999] | 0.1V | |
| | **Hybrid:** Total energie încărcare baterie octet jos | | | 0.1kWh | |
| | **MI:** Energie cumulată panou 2 octet înalt | | | - | |
| 073 | **String:** Tensiune rețea A | R | [0,9999] | 0.1V | MI |
| | **Hybrid:** Total energie încărcare baterie octet înalt | | | 0.1kWh | |
| 074 | **String:** Tensiune rețea B | R | [0,9999] | 0.1V | |
| | **Hybrid:** Total energie descărcare baterie octet jos | | | 0.1kWh | |
| | **MI:** Energie cumulată panou 3 octet jos | | | - | |
| 075 | **String:** Tensiune rețea C | R | [0,9999] | 0.1V | |
| | **Hybrid:** Total energie descărcare baterie octet înalt | | | 0.1kWh | |
| | **MI:** Energie cumulată panou 3 octet înalt | | | - | |
| 076 | **String:** Curent rețea A | R | [0,65535] | 0.1A | MI |
| | **Hybrid:** Energie cumpărată rețea zilnică | | | 0.1kWh | |
| 077 | **String:** Curent rețea B | R | [0,65535] | 0.1A | |
| | **Hybrid:** Energie vândută rețea zilnică | | | 0.1kWh | |
| | **MI:** Energie cumulată panou 4 octet jos | | | - | |
| 078 | **String:** Curent rețea C | R | [0,65535] | 0.1A | |
| | **Hybrid:** Total energie cumpărată rețea octet jos | | | 0.1kWh | |
| | **MI:** Energie cumulată panou 4 octet înalt | | | - | |
| 079 | Frecvență rețea | R | [0,9999] | 0.01Hz | MI |
| 080 | **String:** Putere afișată octet jos | R | 0x0000 | 0.1W | |
| | **Hybrid:** Total energie cumpărată rețea octet înalt | | | 0.1kWh | |
| 081 | **String:** Putere afișată octet înalt | R | 0x0000 | 0.1W | |
| | **Hybrid:** Total energie vândută rețea octet jos | | | 0.1kWh | |
| 082 | **String:** Putere activă intrare octet jos | R | [0,0xFFFFFFFF] | 0.1W | |
| | **Hybrid:** Total energie vândută rețea octet înalt | | | 0.1kWh | |
| 083 | **String:** Putere activă intrare octet înalt | R | - | 0.1W | |
| | **Hybrid:** Timp funcționare zilnic generator | | | 0.1h | 240=24 ore |
| 084 | **String:** Putere aparentă ieșire octet jos | R | [0,0xFFFF] | 0.1VA | |
| | **Hybrid:** Energie consumată zilnic | | | 0.1kWh | |
| 085 | **String:** Putere aparentă ieșire octet înalt | R | [0,0xFFFF] | 0.1VA | |
| | **Hybrid:** Total energie consumată octet jos | | | 0.1kWh | |
| 086 | **String:** Putere activă ieșire octet jos | R | [0,0xFFFF] | 0.1W | MI |
| | **Hybrid:** Total energie consumată octet înalt | | | 0.1kWh | |
| 087 | **String:** Putere activă ieșire octet înalt | R | [0,0xFFFF] | 0.1W | |
| | **Hybrid:** Energie consumată anuală octet jos | | | 0.1kWh | |
| 088 | **String:** Putere reactivă ieșire octet jos | R | [0,0xFFFF] | 0.1Var | |
| | **Hybrid:** Energie consumată anuală octet înalt | | | 0.1kWh | |
| 089 | Putere reactivă ieșire octet înalt | R | - | - | |
| 090 | Temperatură radiator (temperatură transformator DC) | R | [0,3000] | 0.1℃ | MI |
| 091 | Temperatură modul IGBT (temperatură radiator AC stocare) | R | [0,3000] | 0.1℃ | -56.2℃=438, 0℃=1000, 50.5℃=1505 |
| 092 | Total energie generată generator octet jos | R | [0,65535] | 0.1kWh | |
| 093 | Factor putere | R | [0,1000] | - | |
| | Eroare fază generator, eroare fază rețea, flag amorf | R/W | | | Bit0: 0=EE65, 1=amorf. Bit1: 0=fază rețea corectă, 1=eroare fază. Bit2: 0=fază generator corectă, 1=eroare |
| 094 | Stare card SD | R | [0,3000] | 0.1℃ | 1000=eroare SD, 2000=normal |
| 095 | Total energie generată generator octet înalt | R | [0,65535] | 0.1kWh | |
| 096 | Energie PV istorică octet jos | R | [0,0xFFFFFFFF] | 0.1kWh | |
| 097 | Energie PV istorică octet înalt | R | - | 0.1kWh | |
| 098 | **String:** Curent scurgere RCD | R | [0,65535] | 0.01A | |
| | **Hybrid:** Energie vândută rețea anuală octet jos | | | 0.1kWh | |
| 099 | **String:** Putere Limiter | R | 0x0000 | 1W | |
| | **Hybrid:** Energie vândută rețea anuală octet înalt | | | 0.1kWh | |
| 100 | Alte flag-uri test | R | 0x0000 | - | Bit0: flag comunicație arc, Bit1: comunicație CAN paralelizare (1=normal), Bit8: RS485 interfață baterie litiu, Bit9: CAN interfață baterie litiu, Bit10: butoane 1234, Bit11: stare întrerupere LCD (1=normal) |
| 101 | Mesaj alarmă cuvânt 1 | R | [0,65535] | - | Vezi tabel codificare mesaje alarmă |
| 102 | Mesaj alarmă cuvânt 2 | R | [0,65535] | - | Vezi tabel codificare mesaje alarmă |
| 103 | Mesaj eroare cuvânt 1 | R | [0,65535] | - | Vezi tabel codificare mesaje eroare MI |
| 104 | Mesaj eroare cuvânt 2 | R | [0,65535] | - | Vezi tabel codificare mesaje eroare |
| 105 | Mesaj eroare cuvânt 3 | R | [0,65535] | - | Vezi tabel codificare mesaje eroare |
| 106 | Mesaj eroare cuvânt 4 | R | [0,65535] | - | Vezi tabel codificare mesaje eroare |
| 107 | Capacitate baterie corectată | R | [0,1000] | 1AH | 100=100AH |
| 108 | Energie PV generată zilnic | R | [0,65535] | 0.1kWh | |
| 109 | Tensiune DC 1 | R | [0,65535] | 0.1V | MI |
| 110 | Curent DC 1 | R | [0,65535] | 0.1A | MI |
| 111 | Tensiune DC 2 | R | [0,65535] | 0.1V | MI |
| 112 | Curent DC 2 | R | [0,65535] | 0.1A | MI |
| 113 | Tensiune DC 3 | R | [0,65535] | 0.1V | MI |
| 114 | Curent DC 3 | R | [0,65535] | 0.1A | MI |
| 115 | Tensiune DC 4 | R | [0,65535] | 0.1V | MI |
| 116 | Curent DC 4 | R | [0,65535] | 0.1A | MI |
| 117 | Alarms Status1 | R | 0x0000 | - | Adăugat conform cerințe colector |
| 118 | Alarms Status1 | R | 0x0000 | - | |
| 119 | UPS Power | R | 0x0000 | 1W | |
| 120 | Date debug | R | 0x0000 | - | |
| 121 | Date debug | R | 0x0000 | - | |
| 122 | Date debug | R | 0x0000 | - | |
| 123 | Date debug | R | 0x0000 | - | |
| 124 | Date debug | R | 0x0000 | - | |

---

## Zonă Atribute Timp Real Invertor Hibrid/Stocare (150-192)

| Addr | Nume Registru | R/W | Interval | Unitate | Note |
|------|---------------|-----|----------|---------|------|
| 150 | Tensiune rețea L1-N | R | - | 0.1V | |
| 151 | Tensiune rețea L2-N | R | - | 0.1V | |
| 152 | Tensiune rețea L1-L2 | R | - | 0.1V | |
| 153 | Tensiune partea centrală releu L1-L2 | R | - | 0.1V | |
| 154 | Tensiune ieșire invertor L1-N | R | - | 0.1V | |
| 155 | Tensiune ieșire invertor L2-N | R | - | 0.1V | |
| 156 | Tensiune ieșire invertor L1-L2 | R | - | 0.1V | |
| 157 | Tensiune sarcină L1 | R | - | 0.1V | |
| 158 | Tensiune sarcină L2 | R | - | 0.1V | |
| 159 | Rezervat | R | - | - | |
| 160 | Curent rețea L1 | R | - | 0.01A | Integer cu semn |
| 161 | Curent rețea L2 | R | - | 0.01A | Integer cu semn |
| 162 | Curent Limiter extern rețea L1 | R | - | 0.01A | Integer cu semn |
| 163 | Curent Limiter extern rețea L2 | R | - | 0.01A | Integer cu semn |
| 164 | Curent ieșire invertor L1 | R | - | 0.01A | Integer cu semn |
| 165 | Curent ieșire invertor L2 | R | - | 0.01A | Integer cu semn |
| 166 | Putere intrare Gen ca microinvertor | R | - | 1W | Ca ieșire sarcină: putere ieșire=pozitiv. Ca intrare microinvertor: putere ieșire microinvertor către invertor stocare=negativ |
| 167 | Putere rețea L1 | R | - | 1W 10W:54 register=10 | Integer cu semn |
| 168 | Putere rețea L2 | R | - | 1W 10W:54 register=10 | Integer cu semn |
| 169 | Putere rețea total | R | - | 1W 10W:54 register=10 | Integer cu semn. >0=cumpărare, <0=vânzare |
| 170 | Putere Limiter1 extern rețea | R | - | 1W 10W:54 register=10 | Integer cu semn |
| 171 | Putere Limiter2 extern rețea | R | - | 1W 10W:54 register=10 | Integer cu semn |
| 172 | Putere totală extern rețea | R | - | 1W 10W:54 register=10 | Integer cu semn |
| 173 | Putere ieșire invertor L1 | R | - | 1W | Integer cu semn |
| 174 | Putere ieșire invertor L2 | R | - | 1W | Integer cu semn |
| 175 | Putere totală ieșire invertor | R | - | 1W | Integer cu semn |
| 176 | Putere sarcină L1 | R | - | 1W 10W:54 register=10 | Integer cu semn |
| 177 | Putere sarcină L2 | R | - | 1W 10W:54 register=10 | Integer cu semn |
| 178 | Putere totală sarcină | R | - | 1W 10W:54 register=10 | Integer cu semn |
| 179 | Curent sarcină L1 | R | - | 0.01A | Integer cu semn |
| 180 | Curent sarcină L2 | R | - | 0.01A | Integer cu semn |
| 181 | Tensiune port Gen | R | - | - | |
| 182 | Temperatură baterie | R | [0,3000] | 0.1℃ | Valoare reală offset +1000. 1200=20.0℃ |
| 183 | Tensiune baterie | R | - | 0.01V | 4100=41.0V |
| 184 | Capacitate baterie | R | [0,100] | 1% | |
| 185 | Stare încărcare baterie | R | - | - | |
| 186 | Putere intrare PV1 | R | - | 1W | |
| 187 | Putere intrare PV2 | R | - | 1W | |
| 188 | Putere intrare PV3 | R | - | 1W | |
| 189 | Putere intrare PV4 | R | - | 1W | |
| 190 | Putere ieșire baterie | R | - | 1W | Integer cu semn |
| 191 | Curent ieșire baterie | R | - | 0.01A | Integer cu semn |
| 192 | Frecvență sarcină | R | - | 0.01Hz | |
| 193 | Frecvență ieșire invertor | R | - | 0.01Hz | |
| 194 | Stare releu lateral rețea | R | - | - | 0=deconectat, 1=închis |
| 195 | Stare releu lateral generator | R | - | - | Bit0-3 (4 biți inferiori): stare releu generator. 0=neatașat, 1=activare, 2=vacant, 3=generator în funcțiune cu activare. Bit4-7 (4 biți superiori): semnal comutator. 0=oprire, 1=pornire. Bit8-11: semnal generare energie |
| 196 | Frecvență port generator | R | - | 0.01Hz | |
| 197 | Rezervat | R | - | - | |

---

## Zonă Atribute Variabile Adăugate Invertor Stocare (200-439)

| Addr | Nume Registru | R/W | Interval | Unitate | Note |
|------|---------------|-----|----------|---------|------|
| 200 | Tip încărcare baterie (Mod Control) | R/W | - | - | 0x0000=baterie plumb, metodă încărcare 4 etape. 0x0001=baterie litiu |
| 201 | Tensiune echilibrare | R/W | [3800,6100] | 0.01V | 1480=14.8V |
| 202 | Tensiune absorbție | R/W | [3800,6100] | 0.01V | 1440=14.4V |
| 203 | Tensiune flotare | R/W | [3800,6100] | 0.01V | 1440=14.4V |
| 204 | Capacitate baterie | R/W | [0,2000] | 1Ah | 200=200AH |
| 205 | Tensiune goală | R/W | - | 0.01V | |
| 206 | Putere minimă activare ZeroExport | R/W | - | - | |
| 207 | Ciclu zile execuție încărcare echilibrare | R/W | [0,90] | Zi | |
| 208 | Timp execuție încărcare echilibrare | R/W | [0,20] | 0.5h | Rezoluție 0.5h, [0-20]=0-10 ore, dar MCU primește [0-100] |
| 209 | Valoare compensare temperatură | R/W | [0,50] | 1mV/℃ | Integer cu semn |
| 210 | Curent maxim încărcare baterie | R/W | [0,185] | 1A | 0-185A |
| 211 | Curent maxim descărcare baterie | R/W | [0,185] | 1A | 0-185A |
| 212 | Rezervat | R/W | - | - | |
| 213 | Baterie funcționează după tensiune sau capacitate | R/W | - | - | 0=după tensiune, 1=după capacitate, 2=fără baterie |
| 214 | Flag trezire baterie litiu | R/W | - | - | 0=activat, 1=dezactivat |
| 215 | Valoare rezistență internă baterie | R/W | [0,6000] | mΩ | |
| 216 | Eficiență încărcare baterie | R/W | [0,100] | 0.1% | 983=98.3% |
| 217 | Capacitate baterie oprire | R/W | [0,100] | 1% | Punct limită capacitate joasă |
| 218 | Capacitate baterie repornire | R/W | [0,100] | 1% | Punct recuperare protecție |
| 219 | Capacitate baterie nivel jos | R/W | [0,100] | 1% | |
| 220 | Tensiune baterie oprire | R/W | [3800,6100] | 0.01V | Punct protecție jos, ex: 41V |
| 221 | Tensiune baterie repornire | R/W | [3800,6100] | 0.01V | Repornire/recuperare, ex: 52V |
| 222 | Tensiune baterie nivel jos | R/W | [3800,6100] | 0.01V | Adâncime descărcare, ex: 46V |
| 223 | Timp maxim funcționare generator | R/W | - | 0.1h | 120=12 ore |
| 224 | Timp răcire generator | R/W | - | 0.1h | 120=12 ore |
| 225 | Punct tensiune pornire încărcare generator | R/W | [0,6300] | 0.01V | Generator pornește încărcare când tensiune baterie <valoare |
| 226 | Punct capacitate pornire încărcare generator | R/W | [0,6300] | 1% | Generator pornește încărcare când capacitate baterie <valoare |
| 227 | Curent încărcare baterie de la generator | R/W | [0,185] | 1A | |
| 228 | Punct tensiune pornire încărcare rețea | R/W | [0,6300] | 0.01V | |
| 229 | Punct capacitate pornire încărcare rețea | R/W | [0,6300] | 1% | |
| 230 | Curent încărcare baterie de la rețea | R/W | [0,185] | 1A | |
| 231 | Enable încărcare generator | R/W | - | - | |
| 232 | Enable încărcare rețea | R/W | - | - | |
| 233 | Intrare solar ca PSU | R/W | [0,1] | - | 0=solar, 1=PSU |
| 234 | Funcție forțare pornire generator ca sarcină | R/W | - | - | Premisă: registrul 235 activat=1. 0=nu forța, 1=forțează |
| 235 | Enable intrare generator ca ieșire sarcină | R/W | - | - | 0=doar intrare generator (dezactivat), 1=ieșire sarcină inteligentă, 2=activat ca intrare invertor |
| 236 | Tensiune baterie oprire sarcină generator | R/W | [3800,6300] | 0.01V | |
| 237 | Capacitate baterie oprire sarcină generator | R/W | [0,100] | 1% | |
| 238 | Tensiune baterie pornire sarcină generator | R/W | [3800,6300] | 0.01V | |
| 239 | Capacitate baterie pornire sarcină generator | R/W | [0,100] | 1% | |
| 240 | Enable test PWM | R/W | - | - | 0=implicit, 1=intrare funcție test PWM |
| 241 | Putere solară minimă pornire generator | R/W | [0,8000] | 1W | |
| 242 | Gen_Grid_Signal On | R/W | - | - | |
| 243 | Model management energie | R/W | - | - | 0=mod prioritate baterie, 1=mod prioritate sarcină |
| 244 | Funcție control limit | R/W | - | 0/1 | 0x00=activat vânzare energie, 0x01=activat încorporat, 0x02=activat extern |
| 245 | Limită putere maximă ieșire rețea | R/W | [0,8000] | 1W | Reprezintă putere totală |
| 246 | Fază clema senzor curent extern | R/W | [xx,00] | 1W | [11][12] |
| 247 | Vânzare solar | R/W | - | - | 0x00=solar nu vinde, 0x01=solar vinde |
| 248 | Enable funcție avansată Time of Use Selling | R/W | - | - | Bit0: 0=dezactivat, 1=activat. Bit1: Luni (0=dezactivat, 1=activat). Bit2: Marți...Bit7: Duminică. Bit8: mod lucru 3 (cerință client Spania) |
| 249 | Rezervat | R/W | - | - | |
| 250 | Punct timp 1 mod vânzare | R/W | [0,2359] | - | 2359=23:59. MCU calcul intern 0-287, trimite către MCU și colector 2355 |
| 251 | Punct timp 2 mod vânzare | R/W | [0,2359] | - | |
| 252 | Punct timp 3 mod vânzare | R/W | [0,2359] | - | |
| 253 | Punct timp 4 mod vânzare | R/W | [0,2359] | - | |
| 254 | Punct timp 5 mod vânzare | R/W | [0,2359] | - | |
| 255 | Punct timp 6 mod vânzare | R/W | [0,2359] | - | |
| 256 | Putere punct timp 1 mod vânzare | R/W | [0,8000] | 1W | Afectat de puterea maximă descărcare baterie |
| 257 | Putere punct timp 2 mod vânzare | R/W | [0,8000] | 1W | |
| 258 | Putere punct timp 3 mod vânzare | R/W | [0,8000] | 1W | |
| 259 | Putere punct timp 4 mod vânzare | R/W | [0,8000] | 1W | |
| 260 | Putere punct timp 5 mod vânzare | R/W | [0,8000] | 1W | |
| 261 | Putere punct timp 6 mod vânzare | R/W | [0,8000] | 1W | |
| 262 | Tensiune punct timp 1 mod vânzare | R/W | [0,6300] | 0.01V | Afectat de tensiunea bateriei |
| 263 | Tensiune punct timp 2 mod vânzare | R/W | [0,6300] | 0.01V | |
| 264 | Tensiune punct timp 3 mod vânzare | R/W | [0,6300] | 0.01V | |
| 265 | Tensiune punct timp 4 mod vânzare | R/W | [0,6300] | 0.01V | |
| 266 | Tensiune punct timp 5 mod vânzare | R/W | [0,6300] | 0.01V | |
| 267 | Tensiune punct timp 6 mod vânzare | R/W | [0,6300] | 0.01V | |
| 268 | Capacitate 1 | R/W | [0,100] | 1% | SOC |
| 269 | Capacitate 2 | R/W | [0,100] | 1% | |
| 270 | Capacitate 3 | R/W | [0,100] | 1% | |
| 271 | Capacitate 4 | R/W | [0,100] | 1% | |
| 272 | Capacitate 5 | R/W | [0,100] | 1% | |
| 273 | Capacitate 6 | R/W | [0,100] | 1% | |
| 274 | Enable încărcare punct timp 1 | R/W | [0,1] | - | Bit0: enable încărcare rețea. Bit1: enable încărcare generator. 0=dezactivat, 1=activat. Bit2: mod GM. Bit3: mod BU. Bit4: mod CH |
| 275 | Enable încărcare punct timp 2 | R/W | [0,1] | - | Idem |
| 276 | Enable încărcare punct timp 3 | R/W | [0,1] | - | Idem |
| 277 | Enable încărcare punct timp 4 | R/W | [0,1] | - | Idem |
| 278 | Enable încărcare punct timp 5 | R/W | [0,1] | - | Idem |
| 279 | Enable încărcare punct timp 6 | R/W | [0,1] | - | Idem |
| 280 | Microinvertor export la rețea cutoff | R/W | [0,1] | - | Bit0-3: tensiune ieșire invertor. Dacă 286==0: 0=230V, 1=220V, 2=240V, 3=200V. Dacă 286==1: 0=120/240V, 1=110/220V, 2=120/240V, 3=110/200V. Dacă 286==2: 0=120/208V, 1=127/220V. Bit4-7: 0=Gen peak-shaving dezactivat, 1=activat. Bit8-11: 0=Grid peak-shaving dezactivat, 1=activat. Bit12: On Grid always on. Bit13: releu extern. Bit14: enable raportare eroare pierdere baterie litiu. Bit15: enable DRM |
| 281 | Enable detecție automată direcție senzor extern | R/W | [0,1] | - | |
| 282 | Timp restabilire conectare rețea | R/W | [10,300] | - | |
| 283 | Enable mod Solar Arc Fault | R/W | [0,1] | - | 0x00=închis, 0x01=deschis, 0x02=resetare eroare arc (invertor primește 02=LCD trimite flag resetare, apoi revine automat la 01) |
| 284 | Mod rețea (standard rețea) | R/W | [0,1] | - | 0=standard general, 1=UL1741&IEEE1547, 2=CPUC RULE21, 3=SRD-UL1741, 4=CEI 0-21... |
| 285 | Setare frecvență rețea | R/W | [0,1] | - | 0x00=50Hz, 0x01=60Hz |
| 286 | Setare tip rețea | R/W | [0,3] | - | 0x00=monofazat, 0x01=bifazat 120V/240V, 0x02=trifazat 208V 120°, 0x03=120V monofazat |
| 287 | Punct protecție tensiune înaltă rețea | R/W | [1800,2700] | 0.1V | |
| 288 | Punct protecție tensiune joasă rețea | R/W | [1800,2700] | 0.1V | |
| 289 | Punct protecție frecvență înaltă rețea | R/W | [4500,6500] | 0.01Hz | |
| 290 | Punct protecție frecvență joasă rețea | R/W | [4500,6500] | 0.01Hz | |
| 291 | Generator conectat la intrare rețea | R/W | [0,1] | - | 0=dezactivat, 1=activat |
| 292 | Putere GEN peak shaving | R/W | [0,16000] | 1W | |
| 293 | Putere GRID peak shaving | R/W | [0,16000] | 1W | |
| 294 | Întârziere deschidere SmartLoad | R/W | [1,120] | 1min | |
| 295 | Setare valoare PF ieșire (reglare activă) | R/W | [800,1200] | - | 800=80%, 1200=120% |
| 296 | Bit releu extern | R/W | [0,0xFFFF] | - | Bit0-8: corespund 8 biți releu |
| 297 | ARC_factory_B octet înalt | R/W | [0,65535] | - | Combinație octet înalt + jos, afișare numerică |
| 298 | ARC_factory_B octet jos | R/W | [0,65535] | - | |
| 299 | ARC_factory_I octet înalt | R/W | [0,65535] | - | |
| 300 | ARC_factory_I octet jos | R/W | [0,65535] | - | |
| 301 | ARC_factory_F octet înalt | R/W | [0,65535] | - | |
| 302 | ARC_factory_F octet jos | R/W | [0,65535] | - | |
| 303 | ARC_factory_D octet înalt | R/W | [0,65535] | - | |
| 304 | ARC_factory_D octet jos | R/W | [0,65535] | - | |
| 305 | ARC_factory_T octet înalt | R/W | [0,65535] | - | |
| 306 | ARC_factory_T octet jos | R/W | [0,65535] | - | |
| 307 | ARC_factory_C octet înalt | R/W | [0,65535] | - | |
| 308 | ARC_factory_C octet jos | R/W | [0,65535] | - | |
| 309 | ARC_factory_Frz octet înalt | R/W | [0,65535] | - | |
| 310 | ARC_factory_Frz octet jos | R/W | [0,65535] | - | |
| 311 | Ups_time | R/W | - | 1S | 0=implicit, 1=1S |
| 312 | Tensiune încărcare | R/W | - | 0.01V | |
| 313 | Tensiune descărcare | R/W | - | 0.01V | |
| 314 | Limitare curent încărcare | R/W | - | 1A | |
| 315 | Limitare curent descărcare | R/W | - | 1A | |
| 316 | Capacitate timp real | R/W | - | 1% | |
| 317 | Tensiune timp real | R/W | - | 0.01V | |
| 318 | Curent timp real | R/W | - | 1A | |
| 319 | Temperatură timp real | R/W | - | 0.1℃ | 1000=0°, 1200=20.0°, 800=-20.0℃ |
| 320 | Limită curent încărcare maximă | R/W | - | 1A | |
| 321 | Limită curent descărcare maximă | R/W | - | - | |
| 322 | Bit alarmă baterie litiu | R/W | - | - | 0x0001 |
| 323 | Bit eroare baterie litiu | R/W | [0,65535] | - | |
| 324 | Simbol 2 baterie litiu | R/W | [0,65535] | - | Bit0: vacant, Bit1: flag încărcare forțată |
| 325 | Tip baterie litiu | R/W | - | - | 0x0000=PYLON/SOLAX/protocol CAN general, 0x0001=Tianbangda RS485 Modbus, 0x0002=KOK, 0x0003=Keith, 0x0004=Tuopai, 0x0005=Pylon 485, 0x0006=Jelis 485, 0x0007=Sunwoda 485, 0x0008=Xinruineng 485, 0x0009=Tianbangda 485, 0x000A=Shenggao CAN |
| 326 | Ex_MeterCT | R/W | - | - | Bit0: 1=enable, 0=enable Meter1 CT. Bit1: enable fază A. Bit2: enable fază B. Bit3: enable fază C. Bit6: 1=enable, 0=enable ActoGrid. Bit7: 1=enable, 0=enable ActoLoad. Bit8-11: tip contor 1/2 (4=Chint DDSU666 monofazat, 3=Donghong SDM230 monofazat, 2=Chint DTSU666 trifazat, 1=Donghong SDM630 trifazat). Bit12: 1=enable, 0=enable Meter2 CT. Bit13: 1=enable, 0=enable forțare pornire generator. Bit14-15: rezervat |
| 327 | Raport CT | R/W | [200,8000] | - | Multiplu CT extern |
| 328 | Bit funcție specială | R/W | - | - | Bit0: eroare împământare versiune US (0=oprire, 1=fără oprire) |
| 329 | Limită superioară frecvență AC couple | R/W | [5000,6500] | - | |
| 330 | Funcție setare placă comunicație | R/W | - | - | Bit0-1: sincronizare timp. Bit2-3: beep. Bit4-5: AM/PM. Bit6-7: Auto dim. Bit8-9: Solarm Discern. Bit10-11: nu afișa subpachet baterie litiu pe web (11=nu afișa, 10=afișa). -00/-01=fără acțiune, -10=dezactivat, -11=activat |
| 331 | Enable CA_LHVRT California | R/W | [0,1] | - | 0=dezactivat, 1=activat |
| 332 | CA_HV2 | R/W | [1000,3000] | 0.1V | |
| 333 | CA_HV1 | R/W | - | - | |
| 334 | CA_LV1 | R/W | - | - | |
| 335 | CA_LV2 | R/W | - | - | |
| 336 | CA_LV3 | R/W | - | - | |
| 337 | CA_HV2_Time | R/W | [0,300] | - | 0=0.16S |
| 338 | CA_HV1_Time | R/W | - | - | |
| 339 | CA_LV1_Time | R/W | - | - | |
| 340 | CA_LV2_Time | R/W | - | - | |
| 341 | CA_LV3_Time | R/W | - | - | |
| 342 | Enable CA_LHFRT California | R/W | - | - | |
| 343 | CA_HF2 | R/W | [4500,6500] | 0.01Hz | |
| 344 | CA_HF1 | R/W | - | - | |
| 345 | CA_LF1 | R/W | - | - | |
| 346 | CA_LF2 | R/W | - | - | |
| 347 | CA_HF2_Time | R/W | [0,300] | - | |
| 348 | CA_HF1_Time | R/W | - | - | |
| 349 | CA_LF1_Time | R/W | - | - | |
| 350 | CA_LF2_Time | R/W | - | - | |
| 351 | Enable CA_QV California | R/W | - | - | |
| 352 | CA_QV_V1 | R/W | [1000,3000] | - | |
| 353 | CA_QV_V2 | R/W | - | - | |
| 354 | CA_QV_V3 | R/W | - | - | |
| 355 | CA_QV_V4 | R/W | [-44,+44] | 0.01 | |
| 356 | CA_QV_Q1 | R/W | - | - | |
| 357 | CA_QV_Q2 | R/W | - | - | |
| 358 | CA_QV_Q3 | R/W | - | - | |
| 359 | CA_QV_Q4 | R/W | - | - | |
| 360 | Enable CA_FW California | R/W | - | - | |
| 361 | CA_Fstart | R/W | - | - | |
| 362 | CA_Fstop | R/W | - | - | |
| 363 | Enable CA_VW California | R/W | - | - | |
| 364 | CA_Vstart | R/W | - | - | |
| 365 | CA_Vstop | R/W | - | - | |
| 366 | Pantă normală ascendentă | R/W | [1,100] | 1% | |
| 367 | Rată creștere soft start | R/W | [1,100] | 1% | Implicit 100% |
| 368 | Timp răspuns QV | R/W | [0,90] | S | |
| 369 | Timp răspuns VW | R/W | [0,60] | S | |
| 370 | Timp răspuns FW | R/W | - | - | |
| 371 | Rezervat | R/W | - | - | |
| 372 | Rezervat | R/W | - | - | |
| 373 | Rezervat | R/W | - | - | |
| 374 | Rezervat | R/W | - | - | |
| 375 | Rezervat | R/W | - | - | |
| 376 | Grid1_I | R/W | - | - | |
| 377 | Grid2_I | R/W | - | - | |
| 378 | Grid_V_L1 | R/W | - | - | |
| 379 | Grid_V_L2 | R/W | - | - | |
| 380 | Limit1_I | R/W | - | - | |
| 381 | Limit2_I | R/W | - | - | |
| 382 | PV1_V | R/W | - | - | |
| 383 | PV1_I | R/W | - | - | |
| 384 | PV2_V | R/W | - | - | |
| 385 | PV2_I | R/W | - | - | |
| 386 | INV_I | R/W | - | - | |
| 387 | INV_V | R/W | - | - | |
| 388 | BAT_I | R/W | - | - | |
| 389 | BAT_V | R/W | - | - | |
| 390 | Enable Solar1 ca intrare Wind | R/W | [0,1] | - | 0=dezactivat, 1=activat |
| 391 | Enable Solar2 ca intrare Wind | R/W | [0,1] | - | 0=dezactivat, 1=activat |
| 392 | Voltage 1 | R/W | [500,5000] | 0.1V | |
| 393 | Voltage 2 | R/W | - | 0.1V | |
| 394 | Voltage 3 | R/W | - | 0.1V | |
| 395 | Voltage 4 | R/W | - | 0.1V | |
| 396 | Voltage 5 | R/W | - | 0.1V | |
| 397 | Voltage 6 | R/W | - | 0.1V | |
| 398 | Voltage 7 | R/W | - | 0.1V | |
| 399 | Voltage 8 | R/W | - | 0.1V | |
| 400 | Voltage 9 | R/W | - | 0.1V | |
| 401 | Voltage 10 | R/W | - | 0.1V | |
| 402 | Voltage 11 | R/W | - | 0.1V | |
| 403 | Voltage 12 | R/W | - | 0.1V | |
| 404 | Current 1 | R/W | [0,200] | 0.1A | |
| 405 | Current 2 | R/W | - | 0.1A | |
| 406 | Current 3 | R/W | - | 0.1A | |
| 407 | Current 4 | R/W | - | 0.1A | |
| 408 | Current 5 | R/W | - | 0.1A | |
| 409 | Current 6 | R/W | - | 0.1A | |
| 410 | Current 7 | R/W | - | 0.1A | |
| 411 | Current 8 | R/W | - | 0.1A | |
| 412 | Current 9 | R/W | - | 0.1A | |
| 413 | Current 10 | R/W | - | 0.1A | |
| 414 | Current 11 | R/W | - | 0.1A | |
| 415 | Current 12 | R/W | - | 0.1A | |
| 416 | Bit forțare funcționare off-grid | R/W | - | - | |
| 417 | Registru paralelizare 1 | R/W | - | - | Bit0: 1=Parallel Enable, 0=Parallel Disable. Bit1: 1=Master, 0=Slave. Bit2-7: gol. Bit8-9: Fază (00=A, 01=B, 10=C, 11=gol). Bit10-15: Modbus SN (0-63) |
| 418 | Registru paralelizare 2 | R/W | - | - | Bit0-4: număr invertor fază A. Bit5-9: număr invertor fază B. Bit10-14: număr invertor fază C. Bit15: gol |
| 419 | Versiune baterie litiu octet jos | R/W | - | - | Paralelizare multi-noduri: citește doar ultimul nod |
| 420 | Versiune baterie litiu octet înalt | R/W | - | - | |
| 421 | Timp sistem byte 01 | R/W | - | An | Dacă LCD setat ca slave și detectează timp aici, va sincroniza timpul |
| | Timp sistem byte 02 | | | Lună | |
| 422 | Timp sistem byte 03 | R/W | - | Zi | |
| | Timp sistem byte 04 | | | Oră | |
| 423 | Timp sistem byte 05 | R/W | - | Minut | |
| | Timp sistem byte 06 | | | Secundă | |
| 424 | Rezervat | R/W | - | - | |
| 425 | Rezervat | R/W | - | - | |
| 426 | Rezervat | R/W | - | - | |
| 427 | Rezervat | R/W | - | - | |
| 428 | Rezervat | R/W | - | - | |
| 429 | Rezervat | R/W | - | - | |
| 430 | Rezervat | R/W | - | - | |
| 431 | Rezervat | R/W | - | - | |
| 432 | Rezervat | R/W | - | - | |
| 433 | Punct reconectare tensiune înaltă rețea | R/W | [1800,2700] | 0.1V | Grid V High Reconnect |
| 434 | Punct reconectare tensiune joasă rețea | R/W | [1800,2700] | 0.1V | Grid V Low Reconnect |
| 435 | Punct reconectare frecvență înaltă rețea | R/W | [4500,6500] | 0.01Hz | Grid Hz High Reconnect |
| 436 | Punct reconectare frecvență joasă rețea | R/W | [4500,6500] | 0.01Hz | Grid Hz Low Reconnect |
| 437 | Rezervat | R/W | - | - | |
| 438 | Rezervat | R/W | - | - | |
| 439 | Rezervat | R/W | - | - | |

---

## Date Timp Real 3 Invertor Hibrid - ID Pack-uri Baterie (500-589)

**Notă:** 15 pack-uri baterie ID (doar pentru TIAN-POWER / baterie Shengyang)

| Addr | Nume Registru | R/W | Interval | Unitate | Note |
|------|---------------|-----|----------|---------|------|
| 500 | Pack 1 byte 01 | R | '0'-'9' 'A'-'Z' | - | Caractere ASCII |
| | Pack 1 byte 02 | | | | |
| 501 | Pack 1 byte 03 | R | | | |
| | Pack 1 byte 04 | | | | |
| 502 | Pack 1 byte 05 | R | | | |
| | Pack 1 byte 06 | | | | |
| 503 | Pack 1 byte 07 | R | | | |
| | Pack 1 byte 08 | | | | |
| 504 | Pack 1 byte 09 | R | | | |
| | Pack 1 byte 10 | | | | |
| 505 | Pack 1 byte 11 | R | | | |
| | Pack 1 byte 12 | | | | |
| 506 | Pack 2 byte 01 | R | '0'-'9' 'A'-'Z' | - | Caractere ASCII |
| | Pack 2 byte 02 | | | | |
| 507 | Pack 2 byte 03 | R | | | |
| | Pack 2 byte 04 | | | | |
| 508 | Pack 2 byte 05 | R | | | |
| | Pack 2 byte 06 | | | | |
| 509 | Pack 2 byte 07 | R | | | |
| | Pack 2 byte 08 | | | | |
| 510 | Pack 2 byte 09 | R | | | |
| | Pack 2 byte 10 | | | | |
| 511 | Pack 2 byte 11 | R | | | |
| | Pack 2 byte 12 | | | | |
| 512 | Pack 3 byte 01 | R | '0'-'9' 'A'-'Z' | - | Caractere ASCII |
| | Pack 3 byte 02 | | | | |
| 513 | Pack 3 byte 03 | R | | | |
| | Pack 3 byte 04 | | | | |
| 514 | Pack 3 byte 05 | R | | | |
| | Pack 3 byte 06 | | | | |
| 515 | Pack 3 byte 07 | R | | | |
| | Pack 3 byte 08 | | | | |
| 516 | Pack 3 byte 09 | R | | | |
| | Pack 3 byte 10 | | | | |
| 517 | Pack 3 byte 11 | R | | | |
| | Pack 3 byte 12 | | | | |
| 518 | Pack 4 byte 01 | R | '0'-'9' 'A'-'Z' | - | Caractere ASCII |
| | Pack 4 byte 02 | | | | |
| 519 | Pack 4 byte 03 | R | | | |
| | Pack 4 byte 04 | | | | |
| 520 | Pack 4 byte 05 | R | | | |
| | Pack 4 byte 06 | | | | |
| 521 | Pack 4 byte 07 | R | | | |
| | Pack 4 byte 08 | | | | |
| 522 | Pack 4 byte 09 | R | | | |
| | Pack 4 byte 10 | | | | |
| 523 | Pack 4 byte 11 | R | | | |
| | Pack 4 byte 12 | | | | |
| 524 | Pack 5 byte 01 | R | '0'-'9' 'A'-'Z' | - | Caractere ASCII |
| | Pack 5 byte 02 | | | | |
| 525 | Pack 5 byte 03 | R | | | |
| | Pack 5 byte 04 | | | | |
| 526 | Pack 5 byte 05 | R | | | |
| | Pack 5 byte 06 | | | | |
| 527 | Pack 5 byte 07 | R | | | |
| | Pack 5 byte 08 | | | | |
| 528 | Pack 5 byte 09 | R | | | |
| | Pack 5 byte 10 | | | | |
| 529 | Pack 5 byte 11 | R | | | |
| | Pack 5 byte 12 | | | | |
| 530 | Pack 6 byte 01 | R | '0'-'9' 'A'-'Z' | - | Caractere ASCII |
| | Pack 6 byte 02 | | | | |
| 531 | Pack 6 byte 03 | R | | | |
| | Pack 6 byte 04 | | | | |
| 532 | Pack 6 byte 05 | R | | | |
| | Pack 6 byte 06 | | | | |
| 533 | Pack 6 byte 07 | R | | | |
| | Pack 6 byte 08 | | | | |
| 534 | Pack 6 byte 09 | R | | | |
| | Pack 6 byte 10 | | | | |
| 535 | Pack 6 byte 11 | R | | | |
| | Pack 6 byte 12 | | | | |
| 536 | Pack 7 byte 01 | R | '0'-'9' 'A'-'Z' | - | Caractere ASCII |
| | Pack 7 byte 02 | | | | |
| 537 | Pack 7 byte 03 | R | | | |
| | Pack 7 byte 04 | | | | |
| 538 | Pack 7 byte 05 | R | | | |
| | Pack 7 byte 06 | | | | |
| 539 | Pack 7 byte 07 | R | | | |
| | Pack 7 byte 08 | | | | |
| 540 | Pack 7 byte 09 | R | | | |
| | Pack 7 byte 10 | | | | |
| 541 | Pack 7 byte 11 | R | | | |
| | Pack 7 byte 12 | | | | |
| 542 | Pack 8 byte 01 | R | '0'-'9' 'A'-'Z' | - | Caractere ASCII |
| | Pack 8 byte 02 | | | | |
| 543 | Pack 8 byte 03 | R | | | |
| | Pack 8 byte 04 | | | | |
| 544 | Pack 8 byte 05 | R | | | |
| | Pack 8 byte 06 | | | | |
| 545 | Pack 8 byte 07 | R | | | |
| | Pack 8 byte 08 | | | | |
| 546 | Pack 8 byte 09 | R | | | |
| | Pack 8 byte 10 | | | | |
| 547 | Pack 8 byte 11 | R | | | |
| | Pack 8 byte 12 | | | | |
| 548 | Pack 9 byte 01 | R | '0'-'9' 'A'-'Z' | - | Caractere ASCII |
| | Pack 9 byte 02 | | | | |
| 549 | Pack 9 byte 03 | R | | | |
| | Pack 9 byte 04 | | | | |
| 550 | Pack 9 byte 05 | R | | | |
| | Pack 9 byte 06 | | | | |
| 551 | Pack 9 byte 07 | R | | | |
| | Pack 9 byte 08 | | | | |
| 552 | Pack 9 byte 09 | R | | | |
| | Pack 9 byte 10 | | | | |
| 553 | Pack 9 byte 11 | R | | | |
| | Pack 9 byte 12 | | | | |
| 554 | Pack 10 byte 01 | R | '0'-'9' 'A'-'Z' | - | Caractere ASCII |
| | Pack 10 byte 02 | | | | |
| 555 | Pack 10 byte 03 | R | | | |
| | Pack 10 byte 04 | | | | |
| 556 | Pack 10 byte 05 | R | | | |
| | Pack 10 byte 06 | | | | |
| 557 | Pack 10 byte 07 | R | | | |
| | Pack 10 byte 08 | | | | |
| 558 | Pack 10 byte 09 | R | | | |
| | Pack 10 byte 10 | | | | |
| 559 | Pack 10 byte 11 | R | | | |
| | Pack 10 byte 12 | | | | |
| 560 | Pack 11 byte 01 | R | '0'-'9' 'A'-'Z' | - | Caractere ASCII |
| | Pack 11 byte 02 | | | | |
| 561 | Pack 11 byte 03 | R | | | |
| | Pack 11 byte 04 | | | | |
| 562 | Pack 11 byte 05 | R | | | |
| | Pack 11 byte 06 | | | | |
| 563 | Pack 11 byte 07 | R | | | |
| | Pack 11 byte 08 | | | | |
| 564 | Pack 11 byte 09 | R | | | |
| | Pack 11 byte 10 | | | | |
| 565 | Pack 11 byte 11 | R | | | |
| | Pack 11 byte 12 | | | | |
| 566 | Pack 12 byte 01 | R | '0'-'9' 'A'-'Z' | - | Caractere ASCII |
| | Pack 12 byte 02 | | | | |
| 567 | Pack 12 byte 03 | R | | | |
| | Pack 12 byte 04 | | | | |
| 568 | Pack 12 byte 05 | R | | | |
| | Pack 12 byte 06 | | | | |
| 569 | Pack 12 byte 07 | R | | | |
| | Pack 12 byte 08 | | | | |
| 570 | Pack 12 byte 09 | R | | | |
| | Pack 12 byte 10 | | | | |
| 571 | Pack 12 byte 11 | R | | | |
| | Pack 12 byte 12 | | | | |
| 572 | Pack 13 byte 01 | R | '0'-'9' 'A'-'Z' | - | Caractere ASCII |
| | Pack 13 byte 02 | | | | |
| 573 | Pack 13 byte 03 | R | | | |
| | Pack 13 byte 04 | | | | |
| 574 | Pack 13 byte 05 | R | | | |
| | Pack 13 byte 06 | | | | |
| 575 | Pack 13 byte 07 | R | | | |
| | Pack 13 byte 08 | | | | |
| 576 | Pack 13 byte 09 | R | | | |
| | Pack 13 byte 10 | | | | |
| 577 | Pack 13 byte 11 | R | | | |
| | Pack 13 byte 12 | | | | |
| 578 | Pack 14 byte 01 | R | '0'-'9' 'A'-'Z' | - | Caractere ASCII |
| | Pack 14 byte 02 | | | | |
| 579 | Pack 14 byte 03 | R | | | |
| | Pack 14 byte 04 | | | | |
| 580 | Pack 14 byte 05 | R | | | |
| | Pack 14 byte 06 | | | | |
| 581 | Pack 14 byte 07 | R | | | |
| | Pack 14 byte 08 | | | | |
| 582 | Pack 14 byte 09 | R | | | |
| | Pack 14 byte 10 | | | | |
| 583 | Pack 14 byte 11 | R | | | |
| | Pack 14 byte 12 | | | | |
| 584 | Pack 15 byte 01 | R | '0'-'9' 'A'-'Z' | - | Caractere ASCII |
| | Pack 15 byte 02 | | | | |
| 585 | Pack 15 byte 03 | R | | | |
| | Pack 15 byte 04 | | | | |
| 586 | Pack 15 byte 05 | R | | | |
| | Pack 15 byte 06 | | | | |
| 587 | Pack 15 byte 07 | R | | | |
| | Pack 15 byte 08 | | | | |
| 588 | Pack 15 byte 09 | R | | | |
| | Pack 15 byte 10 | | | | |
| 589 | Pack 15 byte 11 | R | | | |
| | Pack 15 byte 12 | | | | |

---

## Date Detaliate Pack-uri Baterie (600-802)

| Addr | Nume Registru | R/W | Interval | Unitate | Note |
|------|---------------|-----|----------|---------|------|
| 600 | PACK1 - Tensiune modul | R | - | 0.01V | |
| 601 | PACK1 - Curent modul | R | - | 0.1A | |
| 602 | PACK1 - Temperatură medie | R | - | - | 1250=25.0℃ |
| 603 | PACK1 - SOC | R | - | 0.1 | |
| 604 | PACK1 - Capacitate rămasă | R | - | 0.1Ah | |
| 605 | PACK1 - Capacitate totală | R | - | 0.1Ah | |
| 606 | PACK1 - Tensiune încărcare | R | - | 0.01V | |
| 607 | PACK1 - Curent încărcare | R | - | 0.1A | |
| 608 | PACK1 - Curent descărcare | R | - | 0.1A | |
| 609 | PACK1 - Tensiune celulă maximă | R | - | 0.01V | |
| 610 | PACK1 - Tensiune celulă minimă | R | - | 0.01V | |
| 611 | PACK1 - Număr cicluri | R | - | 1 | |
| 612 | PACK1 - Avertizare | R | - | - | |
| 613 | PACK1 - Eroare | R | - | - | |
| 614 | PACK2 - Tensiune modul | R | - | 0.01V | |
| 615 | PACK2 - Curent modul | R | - | 0.1A | |
| 616 | PACK2 - Temperatură medie | R | - | - | 1250=25.0℃ |
| 617 | PACK2 - SOC | R | - | 0.1 | |
| 618 | PACK2 - Capacitate rămasă | R | - | 0.1Ah | |
| 619 | PACK2 - Capacitate totală | R | - | 0.1Ah | |
| 620 | PACK2 - Tensiune încărcare | R | - | 0.01V | |
| 621 | PACK2 - Curent încărcare | R | - | 0.1A | |
| 622 | PACK2 - Curent descărcare | R | - | 0.1A | |
| 623 | PACK2 - Tensiune celulă maximă | R | - | 0.01V | |
| 624 | PACK2 - Tensiune celulă minimă | R | - | 0.01V | |
| 625 | PACK2 - Număr cicluri | R | - | 1 | |
| 626 | PACK2 - Avertizare | R | - | - | |
| 627 | PACK2 - Eroare | R | - | - | |
| 628 | PACK3 - Tensiune modul | R | - | 0.01V | |
| 629 | PACK3 - Curent modul | R | - | 0.1A | |
| 630 | PACK3 - Temperatură medie | R | - | - | 1250=25.0℃ |
| 631 | PACK3 - SOC | R | - | 0.1 | |
| 632 | PACK3 - Capacitate rămasă | R | - | 0.1Ah | |
| 633 | PACK3 - Capacitate totală | R | - | 0.1Ah | |
| 634 | PACK3 - Tensiune încărcare | R | - | 0.01V | |
| 635 | PACK3 - Curent încărcare | R | - | 0.1A | |
| 636 | PACK3 - Curent descărcare | R | - | 0.1A | |
| 637 | PACK3 - Tensiune celulă maximă | R | - | 0.01V | |
| 638 | PACK3 - Tensiune celulă minimă | R | - | 0.01V | |
| 639 | PACK3 - Număr cicluri | R | - | 1 | |
| 640 | PACK3 - Avertizare | R | - | - | |
| 641 | PACK3 - Eroare | R | - | - | |
| 642 | PACK4 - Tensiune modul | R | - | 0.01V | |
| 643 | PACK4 - Curent modul | R | - | 0.1A | |
| 644 | PACK4 - Temperatură medie | R | - | - | 1250=25.0℃ |
| 645 | PACK4 - SOC | R | - | 0.1 | |
| 646 | PACK4 - Capacitate rămasă | R | - | 0.1Ah | |
| 647 | PACK4 - Capacitate totală | R | - | 0.1Ah | |
| 648 | PACK4 - Tensiune încărcare | R | - | 0.01V | |
| 649 | PACK4 - Curent încărcare | R | - | 0.1A | |
| 650 | PACK4 - Curent descărcare | R | - | 0.1A | |
| 651 | PACK4 - Tensiune celulă maximă | R | - | 0.01V | |
| 652 | PACK4 - Tensiune celulă minimă | R | - | 0.01V | |
| 653 | PACK4 - Număr cicluri | R | - | 1 | |
| 654 | PACK4 - Avertizare | R | - | - | |
| 655 | PACK4 - Eroare | R | - | - | |
| 656 | PACK5 - Tensiune modul | R | - | 0.01V | |
| 657 | PACK5 - Curent modul | R | - | 0.1A | |
| 658 | PACK5 - Temperatură medie | R | - | - | 1250=25.0℃ |
| 659 | PACK5 - SOC | R | - | 0.1 | |
| 660 | PACK5 - Capacitate rămasă | R | - | 0.1Ah | |
| 661 | PACK5 - Capacitate totală | R | - | 0.1Ah | |
| 662 | PACK5 - Tensiune încărcare | R | - | 0.01V | |
| 663 | PACK5 - Curent încărcare | R | - | 0.1A | |
| 664 | PACK5 - Curent descărcare | R | - | 0.1A | |
| 665 | PACK5 - Tensiune celulă maximă | R | - | 0.01V | |
| 666 | PACK5 - Tensiune celulă minimă | R | - | 0.01V | |
| 667 | PACK5 - Număr cicluri | R | - | 1 | |
| 668 | PACK5 - Avertizare | R | - | - | |
| 669 | PACK5 - Eroare | R | - | - | |
| 670 | PACK6 - Tensiune modul | R | - | 0.01V | |
| 671 | PACK6 - Curent modul | R | - | 0.1A | |
| 672 | PACK6 - Temperatură medie | R | - | - | 1250=25.0℃ |
| 673 | PACK6 - SOC | R | - | 0.1 | |
| 674 | PACK6 - Capacitate rămasă | R | - | 0.1Ah | |
| 675 | PACK6 - Capacitate totală | R | - | 0.1Ah | |
| 676 | PACK6 - Tensiune încărcare | R | - | 0.01V | |
| 677 | PACK6 - Curent încărcare | R | - | 0.1A | |
| 678 | PACK6 - Curent descărcare | R | - | 0.1A | |
| 679 | PACK6 - Tensiune celulă maximă | R | - | 0.01V | |
| 680 | PACK6 - Tensiune celulă minimă | R | - | 0.01V | |
| 681 | PACK6 - Număr cicluri | R | - | 1 | |
| 682 | PACK6 - Avertizare | R | - | - | |
| 683 | PACK6 - Eroare | R | - | - | |
| 684 | PACK7 - Tensiune modul | R | - | 0.01V | |
| 685 | PACK7 - Curent modul | R | - | 0.1A | |
| 686 | PACK7 - Temperatură medie | R | - | - | 1250=25.0℃ |
| 687 | PACK7 - SOC | R | - | 0.1 | |
| 688 | PACK7 - Capacitate rămasă | R | - | 0.1Ah | |
| 689 | PACK7 - Capacitate totală | R | - | 0.1Ah | |
| 690 | PACK7 - Tensiune încărcare | R | - | 0.01V | |
| 691 | PACK7 - Curent încărcare | R | - | 0.1A | |
| 692 | PACK7 - Curent descărcare | R | - | 0.1A | |
| 693 | PACK7 - Tensiune celulă maximă | R | - | 0.01V | |
| 694 | PACK7 - Tensiune celulă minimă | R | - | 0.01V | |
| 695 | PACK7 - Număr cicluri | R | - | 1 | |
| 696 | PACK7 - Avertizare | R | - | - | |
| 697 | PACK7 - Eroare | R | - | - | |
| 698 | PACK8 - Tensiune modul | R | - | 0.01V | |
| 699 | PACK8 - Curent modul | R | - | 0.1A | |
| 700 | PACK8 - Temperatură medie | R | - | - | 1250=25.0℃ |
| 701 | PACK8 - SOC | R | - | 0.1 | |
| 702 | PACK8 - Capacitate rămasă | R | - | 0.1Ah | |
| 703 | PACK8 - Capacitate totală | R | - | 0.1Ah | |
| 704 | PACK8 - Tensiune încărcare | R | - | 0.01V | |
| 705 | PACK8 - Curent încărcare | R | - | 0.1A | |
| 706 | PACK8 - Curent descărcare | R | - | 0.1A | |
| 707 | PACK8 - Tensiune celulă maximă | R | - | 0.01V | |
| 708 | PACK8 - Tensiune celulă minimă | R | - | 0.01V | |
| 709 | PACK8 - Număr cicluri | R | - | 1 | |
| 710 | PACK8 - Avertizare | R | - | - | |
| 711 | PACK8 - Eroare | R | - | - | |
| 712 | PACK9 - Tensiune modul | R | - | 0.01V | |
| 713 | PACK9 - Curent modul | R | - | 0.1A | |
| 714 | PACK9 - Temperatură medie | R | - | - | 1250=25.0℃ |
| 715 | PACK9 - SOC | R | - | 0.1 | |
| 716 | PACK9 - Capacitate rămasă | R | - | 0.1Ah | |
| 717 | PACK9 - Capacitate totală | R | - | 0.1Ah | |
| 718 | PACK9 - Tensiune încărcare | R | - | 0.01V | |
| 719 | PACK9 - Curent încărcare | R | - | 0.1A | |
| 720 | PACK9 - Curent descărcare | R | - | 0.1A | |
| 721 | PACK9 - Tensiune celulă maximă | R | - | 0.01V | |
| 722 | PACK9 - Tensiune celulă minimă | R | - | 0.01V | |
| 723 | PACK9 - Număr cicluri | R | - | 1 | |
| 724 | PACK9 - Avertizare | R | - | - | |
| 725 | PACK9 - Eroare | R | - | - | |
| 726 | PACK10 - Tensiune modul | R | - | 0.01V | |
| 727 | PACK10 - Curent modul | R | - | 0.1A | |
| 728 | PACK10 - Temperatură medie | R | - | - | 1250=25.0℃ |
| 729 | PACK10 - SOC | R | - | 0.1 | |
| 730 | PACK10 - Capacitate rămasă | R | - | 0.1Ah | |
| 731 | PACK10 - Capacitate totală | R | - | 0.1Ah | |
| 732 | PACK10 - Tensiune încărcare | R | - | 0.01V | |
| 733 | PACK10 - Curent încărcare | R | - | 0.1A | |
| 734 | PACK10 - Curent descărcare | R | - | 0.1A | |
| 735 | PACK10 - Tensiune celulă maximă | R | - | 0.01V | |
| 736 | PACK10 - Tensiune celulă minimă | R | - | 0.01V | |
| 737 | PACK10 - Număr cicluri | R | - | 1 | |
| 738 | PACK10 - Avertizare | R | - | - | |
| 739 | PACK10 - Eroare | R | - | - | |
| 740 | PACK11 - Tensiune modul | R | - | 0.01V | |
| 741 | PACK11 - Curent modul | R | - | 0.1A | |
| 742 | PACK11 - Temperatură medie | R | - | - | 1250=25.0℃ |
| 743 | PACK11 - SOC | R | - | 0.1 | |
| 744 | PACK11 - Capacitate rămasă | R | - | 0.1Ah | |
| 745 | PACK11 - Capacitate totală | R | - | 0.1Ah | |
| 746 | PACK11 - Tensiune încărcare | R | - | 0.01V | |
| 747 | PACK11 - Curent încărcare | R | - | 0.1A | |
| 748 | PACK11 - Curent descărcare | R | - | 0.1A | |
| 749 | PACK11 - Tensiune celulă maximă | R | - | 0.01V | |
| 750 | PACK11 - Tensiune celulă minimă | R | - | 0.01V | |
| 751 | PACK11 - Număr cicluri | R | - | 1 | |
| 752 | PACK11 - Avertizare | R | - | - | |
| 753 | PACK11 - Eroare | R | - | - | |
| 754 | PACK12 - Tensiune modul | R | - | 0.01V | |
| 755 | PACK12 - Curent modul | R | - | 0.1A | |
| 756 | PACK12 - Temperatură medie | R | - | - | 1250=25.0℃ |
| 757 | PACK12 - SOC | R | - | 0.1 | |
| 758 | PACK12 - Capacitate rămasă | R | - | 0.1Ah | |
| 759 | PACK12 - Capacitate totală | R | - | 0.1Ah | |
| 760 | PACK12 - Tensiune încărcare | R | - | 0.01V | |
| 761 | PACK12 - Curent încărcare | R | - | 0.1A | |
| 762 | PACK12 - Curent descărcare | R | - | 0.1A | |
| 763 | PACK12 - Tensiune celulă maximă | R | - | 0.01V | |
| 764 | PACK12 - Tensiune celulă minimă | R | - | 0.01V | |
| 765 | PACK12 - Număr cicluri | R | - | 1 | |
| 766 | PACK12 - Avertizare | R | - | - | |
| 767 | PACK12 - Eroare | R | - | - | |
| 768 | PACK13 - Tensiune modul | R | - | 0.01V | |
| 769 | PACK13 - Curent modul | R | - | 0.1A | |
| 770 | PACK13 - Temperatură medie | R | - | - | 1250=25.0℃ |
| 771 | PACK13 - SOC | R | - | 0.1 | |
| 772 | PACK13 - Capacitate rămasă | R | - | 0.1Ah | |
| 773 | PACK13 - Capacitate totală | R | - | 0.1Ah | |
| 774 | PACK13 - Tensiune încărcare | R | - | 0.01V | |
| 775 | PACK13 - Curent încărcare | R | - | 0.1A | |
| 776 | PACK13 - Curent descărcare | R | - | 0.1A | |
| 777 | PACK13 - Tensiune celulă maximă | R | - | 0.01V | |
| 778 | PACK13 - Tensiune celulă minimă | R | - | 0.01V | |
| 779 | PACK13 - Număr cicluri | R | - | 1 | |
| 780 | PACK13 - Avertizare | R | - | - | |
| 781 | PACK13 - Eroare | R | - | - | |
| 782 | PACK14 - Tensiune modul | R | - | 0.01V | |
| 783 | PACK14 - Curent modul | R | - | 0.1A | |
| 784 | PACK14 - Temperatură medie | R | - | - | 1250=25.0℃ |
| 785 | PACK14 - SOC | R | - | 0.1 | |
| 786 | PACK14 - Capacitate rămasă | R | - | 0.1Ah | |
| 787 | PACK14 - Capacitate totală | R | - | 0.1Ah | |
| 788 | PACK14 - Tensiune încărcare | R | - | 0.01V | |
| 789 | PACK14 - Curent încărcare | R | - | 0.1A | |
| 790 | PACK14 - Curent descărcare | R | - | 0.1A | |
| 791 | PACK14 - Tensiune celulă maximă | R | - | 0.01V | |
| 792 | PACK14 - Tensiune celulă minimă | R | - | 0.01V | |
| 793 | PACK14 - Număr cicluri | R | - | 1 | |
| 794 | PACK14 - Avertizare | R | - | - | |
| 795 | PACK14 - Eroare | R | - | - | |
| 796 | PACK15 - Tensiune modul | R | - | 0.01V | |
| 797 | PACK15 - Curent modul | R | - | 0.1A | |
| 798 | PACK15 - Temperatură medie | R | - | - | 1250=25.0℃ |
| 799 | PACK15 - SOC | R | - | 0.1 | |
| 800 | PACK15 - Capacitate rămasă | R | - | 0.1Ah | |
| 801 | PACK15 - Capacitate totală | R | - | 0.1Ah | |
| 802 | PACK15 - Tensiune încărcare | R | - | 0.01V | |
| 803 | PACK15 - Curent încărcare | R | - | 0.1A | |
| 804 | PACK15 - Curent descărcare | R | - | 0.1A | |
| 805 | PACK15 - Tensiune celulă maximă | R | - | 0.01V | |
| 806 | PACK15 - Tensiune celulă minimă | R | - | 0.01V | |
| 807 | PACK15 - Număr cicluri | R | - | 1 | |
| 808 | PACK15 - Avertizare | R | - | - | |
| 809 | PACK15 - Eroare | R | - | - | |


# Registre Modbus Baterie Deye - Zonă Doar Citire

## Registre Principale Baterie (10000-10031)

| Addr | Nume Registru | R/W | Interval | Unitate | Note |
|------|---------------|-----|----------|---------|------|
| 10000 | Tip dispozitiv | R | - | - | 0x700: Protocol Pack baterie litiu |
| 10001 | Versiune protocol | R | - | - | |
| 10002 | Număr Pack-uri baterie | R | - | 1 | |
| 10003 | Tensiune baterie | R | - | 0.1V | |
| 10004 | Curent baterie | R | - | 0.1A | |
| 10005 | Capacitate baterie SOC | R | - | 1% | |
| 10006 | Sănătate baterie SOH | R | - | 1% | |
| 10007 | Capacitate rămasă baterie | R | - | 1Ah | |
| 10008 | Temperatură baterie | R | - | 0.1℃ | |
| 10009 | Tensiune încărcare baterie | R | - | 0.1V | |
| 10010 | Tensiune descărcare baterie | R | - | 0.1V | |
| 10011 | Tensiune oprire încărcare baterie | R | - | 1V | |
| 10012 | Tensiune oprire descărcare baterie | R | - | 1V | |
| 10013 | Limitare curent încărcare baterie | R | - | 1A | |
| 10014 | Limitare curent descărcare baterie | R | - | 1A | |
| 10015 | Limitare curent încărcare off-grid baterie | R | - | 1A | |
| 10016 | Limitare curent descărcare off-grid baterie | R | - | 1A | |
| 10017 | Flag încărcare forțată | R | - | - | |
| 10018 | Flag calibrare SOC | R | - | - | |
| 10019 | Eroare baterie 1 | R | - | - | |
| 10020 | Eroare baterie 2 | R | - | - | |
| 10021 | Alarmă baterie 1 | R | - | - | |
| 10022 | Alarmă baterie 2 | R | - | - | |
| 10023 | Rezervat 1 | R | - | - | |
| 10024 | Rezervat 2 | R | - | - | |
| 10025 | Rezervat 3 | R | - | - | |
| 10026 | Rezervat 4 | R | - | - | |
| 10027 | Rezervat 5 | R | - | - | |
| 10028 | Rezervat 6 | R | - | - | |
| 10029 | Rezervat 7 | R | - | - | |
| 10030 | Rezervat 8 | R | - | - | |
| 10031 | Rezervat 9 | R | - | - | |

## Număr Serial Pack 1 (10032-10039)

| Addr | Nume Registru | R/W | Interval | Unitate | Note |
|------|---------------|-----|----------|---------|------|
| 10032 | Pack 1 byte 01 | R | '0'-'9' 'A'-'Z' | - | Caractere ASCII |
| | Pack 1 byte 02 | | | | |
| 10033 | Pack 1 byte 03 | R | '0'-'9' 'A'-'Z' | - | Caractere ASCII |
| | Pack 1 byte 04 | | | | |
| 10034 | Pack 1 byte 05 | R | '0'-'9' 'A'-'Z' | - | Caractere ASCII |
| | Pack 1 byte 06 | | | | |
| 10035 | Pack 1 byte 07 | R | '0'-'9' 'A'-'Z' | - | Caractere ASCII |
| | Pack 1 byte 08 | | | | |
| 10036 | Pack 1 byte 09 | R | '0'-'9' 'A'-'Z' | - | Caractere ASCII |
| | Pack 1 byte 10 | | | | |
| 10037 | Pack 1 byte 11 | R | '0'-'9' 'A'-'Z' | - | Caractere ASCII |
| | Pack 1 byte 12 | | | | |
| 10038 | Pack 1 byte 13 | R | '0'-'9' 'A'-'Z' | - | Caractere ASCII |
| | Pack 1 byte 14 | | | | |
| 10039 | Pack 1 byte 15 | R | '0'-'9' 'A'-'Z' | - | Caractere ASCII |

## Date Detaliate PACK1 (10040-10069)

| Addr | Nume Registru | R/W | Interval | Unitate | Note |
|------|---------------|-----|----------|---------|------|
| 10040 | PACK1 - Tensiune modul | R | - | 0.1V | |
| 10041 | PACK1 - Curent modul | R | - | 0.1A | |
| 10042 | PACK1 - Temperatură medie | R | - | - | 1250=25.0℃ |
| 10043 | PACK1 - Temperatură celulă maximă | R | - | - | 1250=25.0℃ |
| 10044 | PACK1 - Temperatură celulă minimă | R | - | - | 1250=25.0℃ |
| 10045 | PACK1 - Temperatură MOS maximă | R | - | - | 1250=25.0℃ |
| 10046 | PACK1 - Temperatură membrană încălzire | R | - | - | 1250=25.0℃ |
| 10047 | PACK1 - SOC | R | - | 0.1 | |
| 10048 | PACK1 - SOH | R | - | 0.1 | |
| 10049 | PACK1 - Capacitate rămasă | R | - | 0.1Ah | |
| 10050 | PACK1 - Capacitate totală | R | - | 0.1Ah | |
| 10051 | PACK1 - Tensiune încărcare | R | - | 0.01V | |
| 10052 | PACK1 - Tensiune descărcare | R | - | 0.01V | |
| 10053 | PACK1 - Curent încărcare | R | - | 0.1A | |
| 10054 | PACK1 - Curent descărcare | R | - | 0.1A | |
| 10055 | PACK1 - Tensiune celulă maximă | R | - | 0.01V | |
| 10056 | PACK1 - Tensiune celulă minimă | R | - | 0.01V | |
| 10057 | PACK1 - Număr cicluri | R | - | 1 | |
| 10058 | PACK1 - Stare MOS | R | - | 1 | |
| 10059 | PACK1 - Avertizare 1 | R | - | - | |
| 10060 | PACK1 - Avertizare 2 | R | - | - | |
| 10061 | PACK1 - Eroare 1 | R | - | - | |
| 10062 | PACK1 - Eroare 2 | R | - | - | |
| 10063 | PACK1 - Versiune software | R | - | - | |
| 10064 | PACK1 - Versiune hardware | R | - | - | |
| 10065 | PACK1 - Rezervat 1 | R | - | - | |
| 10066 | PACK1 - Rezervat 2 | R | - | - | |
| 10067 | PACK1 - Rezervat 3 | R | - | - | |
| 10068 | PACK1 - Rezervat 4 | R | - | - | |
| 10069 | PACK1 - Rezervat 5 | R | - | - | |

---

**Notă:** Structura se repetă pentru fiecare Pack baterie:
- **8 registre SN** (număr serial ASCII)
- **30 registre date** (informații detaliate Pack)
- **Total: 38 registre per Pack**

Pack 2 începe la adresa: **10070** (8 registre SN) + **10078** (30 registre date)  
Pack 3 începe la adresa: **10108** (8 registre SN) + **10116** (30 registre date)  
Și așa mai departe...


# Protocol Modbus RTU - Informații Tehnice

## 2.6 Coduri Funcție Protocol Modbus_RTU

Tabelul listează doar codurile funcție aplicate în acest protocol:

| Cod Funcție | Tip Cod Funcție | Explicație | Observații |
|-------------|-----------------|------------|------------|
| 0x03 | Cod funcție public | Citire registru | Include citire registru singular și multiple |
| 0x10 | Cod funcție public | Scriere registru | Include scriere registru singular și multiple |

### 2.6.1 Citire Registru (Cod Funcție: 0x03)

#### (1) Cerere PDU

| Structură Date | Lungime Date | Interval Valori |
|----------------|--------------|-----------------|
| Cod funcție | 1 byte | 0x03 |
| Adresă registru start | 2 bytes | 0x0000~0xFFFF |
| Număr registre | 2 bytes | 0x0001~0x007D |

#### (2) Răspuns Normal PDU

| Structură Date | Lungime Date | Interval Valori |
|----------------|--------------|-----------------|
| Cod funcție | 1 byte | 0x03 |
| Număr bytes | 1 byte | N×2 |
| Valori registre | N×2 bytes | - |

**Notă:** N = număr registre

#### (3) Răspuns Excepție PDU

| Structură Date | Lungime Date | Interval Valori |
|----------------|--------------|-----------------|
| Cod eroare | 1 byte | 0x83 |
| Cod excepție | 1 byte | Vezi "cod excepție" |

#### (4) Exemplu

Cerere citire 3 registre consecutive pornind de la adresa 107 (doar PDU):

**Cerere:**
- Cod funcție: 0x03
- Adresă start Hi: 0x00
- Adresă start Lo: 0x6B
- Număr registre Hi: 0x00
- Număr registre Lo: 0x03

**Răspuns Normal:**
- Cod funcție: 0x03
- Număr bytes: 0x06
- Registru[107] Hi: 0x02
- Registru[107] Lo: 0x2B
- Registru[108] Hi: 0x00
- Registru[108] Lo: 0x00
- Registru[109] Hi: 0x00
- Registru[109] Lo: 0x64

**Răspuns Excepție:**
- Cod eroare: 0x83
- Cod excepție: 0x04

### 2.6.2 Scriere Registru (Cod Funcție: 0x10)

#### (1) Cerere PDU

| Structură Date | Lungime Date | Interval Valori |
|----------------|--------------|-----------------|
| Cod funcție | 1 byte | 0x10 |
| Adresă registru start | 2 bytes | 0x0000~0xFFFF |
| Număr registre | 2 bytes | 0x0001~0x007B |
| Număr bytes | 1 byte | N×2 |
| Valori registre | N×2 bytes | - |

**Notă:** N = număr registre

#### (2) Răspuns Normal PDU

| Structură Date | Lungime Date | Interval Valori |
|----------------|--------------|-----------------|
| Cod funcție | 1 byte | 0x10 |
| Adresă registru start | 2 bytes | 0x0000~0xFFFF |
| Număr registre | 2 bytes | 0x0001~0x007B |

#### (3) Răspuns Excepție PDU

| Structură Date | Lungime Date | Interval Valori |
|----------------|--------------|-----------------|
| Cod eroare | 1 byte | 0x90 |
| Cod excepție | 1 byte | Vezi "cod excepție" |

#### (4) Exemplu

Cerere scriere 0x000A și 0x0102 în două registre pornind de la adresa 1 (doar PDU):

**Cerere:**
- Cod funcție: 0x10
- Adresă start Hi: 0x00
- Adresă start Lo: 0x01
- Număr registre Hi: 0x00
- Număr registre Lo: 0x02
- Număr bytes: 0x04
- Valoare registru Hi: 0x00
- Valoare registru Lo: 0x0A
- Valoare registru Hi: 0x01
- Valoare registru Lo: 0x02

**Răspuns Normal:**
- Cod funcție: 0x10
- Adresă start Hi: 0x00
- Adresă start Lo: 0x01
- Număr registre Hi: 0x00
- Număr registre Lo: 0x02

**Răspuns Excepție:**
- Cod eroare: 0x90
- Cod excepție: 0x04

---

## Observații Generale

- **Rată transmisie:** 9600bps RS232 sau RS485
- **Cuvinte rezervate, bytes rezervați, biți rezervați și registre nesuportate** se completează cu 0x00
- Acest protocol este pentru microinvertor, invertor string și invertor stocare
