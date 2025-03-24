```
graph TD
    %% Internet Service Providers
    ISP1((ISP 1<br>Primary)) --- |WAN1| UDMP(UniFi Dream Machine Pro)
    ISP2((ISP 2<br>Backup)) --- |WAN2| UDMP
    
    %% Core Network
    UDMP --- |10Gbps SFP+| USW_AGG(USW-Aggregation<br>SFP+ Switch)
    
    %% Distribution layer with 4 switches
    USW_AGG --- |SFP+ 1| SW1(Switch 1<br>USW-48-POE-Pro)
    USW_AGG --- |SFP+ 2| SW2(Switch 2<br>USW-48-POE-Pro)
    USW_AGG --- |SFP+ 3| SW3(Switch 3<br>USW-48-POE-Pro)
    USW_AGG --- |SFP+ 4| SW4(Switch 4<br>USW-48-POE-Pro)
    
    %% Switch 1 devices
    SW1 --- |Port 1-2| AP1_1(AP 1.1<br>U6-Pro)
    SW1 --- |Port 3-4| AP1_2(AP 1.2<br>U6-Pro)
    SW1 --- |Port 5-7| CAM1_1(Cam 1.1<br>G4-Pro)
    SW1 --- |Port 8-10| CAM1_2(Cam 1.2<br>G4-Bullet)
    SW1 --- |Port 11-13| CAM1_3(Cam 1.3<br>G4-Dome)
    SW1 --- |Port 14-23| PHONES1[10x PoE Phones<br>Floor 1]
    
    %% Switch 2 devices
    SW2 --- |Port 1-2| AP2_1(AP 2.1<br>U6-Pro)
    SW2 --- |Port 3-4| AP2_2(AP 2.2<br>U6-Pro)
    SW2 --- |Port 5-7| CAM2_1(Cam 2.1<br>G4-Pro)
    SW2 --- |Port 8-10| CAM2_2(Cam 2.2<br>G4-Bullet)
    SW2 --- |Port 11-13| CAM2_3(Cam 2.3<br>G4-Dome)
    SW2 --- |Port 14-23| PHONES2[10x PoE Phones<br>Floor 2]
    
    %% Switch 3 devices
    SW3 --- |Port 1-2| AP3_1(AP 3.1<br>U6-Pro)
    SW3 --- |Port 3-4| AP3_2(AP 3.2<br>U6-Pro)
    SW3 --- |Port 5-7| CAM3_1(Cam 3.1<br>G4-Pro)
    SW3 --- |Port 8-10| CAM3_2(Cam 3.2<br>G4-Bullet)
    SW3 --- |Port 11-13| CAM3_3(Cam 3.3<br>G4-Dome)
    SW3 --- |Port 14-23| PHONES3[10x PoE Phones<br>Floor 3]
    
    %% Switch 4 devices
    SW4 --- |Port 1-2| AP4_1(AP 4.1<br>U6-Pro)
    SW4 --- |Port 3-4| AP4_2(AP 4.2<br>U6-Pro)
    SW4 --- |Port 5-7| CAM4_1(Cam 4.1<br>G4-Pro)
    SW4 --- |Port 8-10| CAM4_2(Cam 4.2<br>G4-Bullet)
    SW4 --- |Port 11-13| CAM4_3(Cam 4.3<br>G4-Dome)
    SW4 --- |Port 14-23| PHONES4[10x PoE Phones<br>Floor 4]
    
    %% Style definitions
    classDef internet fill:#f5f5f5,stroke:#333,stroke-width:2px
    classDef core fill:#e6f7ff,stroke:#0091ff,stroke-width:2px
    classDef distribution fill:#e6ffe6,stroke:#00b300,stroke-width:2px
    classDef accessPoint fill:#fff5e6,stroke:#ff9900,stroke-width:1px
    classDef camera fill:#ffe6e6,stroke:#ff0000,stroke-width:1px
    classDef phone fill:#f2e6ff,stroke:#7700ff,stroke-width:1px
    
    %% Apply styles
    class ISP1,ISP2 internet
    class UDMP,USW_AGG core
    class SW1,SW2,SW3,SW4 distribution
    class AP1_1,AP1_2,AP2_1,AP2_2,AP3_1,AP3_2,AP4_1,AP4_2 accessPoint
    class CAM1_1,CAM1_2,CAM1_3,CAM2_1,CAM2_2,CAM2_3,CAM3_1,CAM3_2,CAM3_3,CAM4_1,CAM4_2,CAM4_3 camera
    class PHONES1,PHONES2,PHONES3,PHONES4 phone

```
