## 信息


注意：您需要自己的高级VT API才能使用此工具。API密钥继续在第12行！

注意2：如果你有一个免费的VT公共API（你这样做），那么你可以使用功能有限的VirusScan.py（Check Hash / Path / Rescan / DownloadJson / VerboseDetections），每分钟允许四次检查。


## 例子
<pre>
使用方法如下，基本搜索+点击全部的示例
下面的开关：

用法：vs.py [-h] [-s] [-v] [-j] [-d] [-p] [-r] HashorPath

从VirusTotal搜索和下载

位置参数：
 HashorPath输入MD5哈希或文件路径

可选参数：
 -h， -  help显示此帮助消息并退出
 -s， -  search搜索VirusTotal
 -v， -  verbose打开VT报告的详细程度
 -j， -  jsondump将完整的VT报告转储到文件（VTDLXXX.json）
 -d， - 从Virustotal下载文件（VTDLXXX.danger）
 -p， -  apt下载网络流量（VTDLXXX.pcap）
 -r， - 使用当前A / V定义强制重新扫描

基本扫描示例：

root @Ae0lus：〜/ tools $ python vs.py ../../VirtualBox_Share/wsusservice.dll -s

Results for MD5:  92d37a92138659fa75f45ccb87242910

        Results for MD5:  92d37a92138659fa75f45ccb87242910

        Detected by:  53 / 67
        Sophos Detection: Troj/Briba-A
        Kaspersky Detection: Backdoor.Win32.Agent.clfe
        TrendMicro Detection: BKDR_BRIBA.A
        Scanned on: 2018-10-06 17:05:38
        First Seen: 2012-08-15 12:36:02
        Last Seen: 2015-09-30 06:14:28
        Unique Sources 4
        Submission Names:
                file-4567337_
                92d37a92138659fa75f45ccb87242910
                wsusservice.dll_
                wsusservice2.dll_
                wuauclt.exe



示例详细扫描+下载+ Pcap + Json Save + Force Rescan：

root @Ae0lus：〜/ tools $ python vs.py 287f3dda64b830a5ac5a6df3266f7d08 -pdvjr

        Results for MD5:  287f3dda64b830a5ac5a6df3266f7d08

        Detected by:  56 / 72
        Sophos Detection: Troj/Hurgyu-B
        Kaspersky Detection: HEUR:Trojan.Win32.Generic
        TrendMicro Detection: TROJ_GEN.R002C0DKT18
        Scanned on: 2019-05-05 12:24:12
        First Seen: 2012-09-25 09:14:13
        Last Seen: 2018-05-27 14:07:52
        Unique Sources 2
        Submission Names:
                2075717f599d9c7df6fb85d9b191fc26b9f530b371d8689c0a769f2fa0d68598.exe
                7DkduxxH
                wuauclt.exe
                setup.exe

        JSON Written to File -- VTDL287F3DDA64B830A5AC5A6DF3266F7D08.json

        Verbose VirusTotal Information Output:

        Bkav                    False   None
        MicroWorld-eScan        True    Gen:Variant.Barys.5788
        FireEye                 True    Generic.mg.287f3dda64b830a5
        CAT-QuickHeal           True    Backdoor.Poison
        McAfee                  True    Artemis!287F3DDA64B8
        Cylance                 True    Unsafe
        VIPRE                   True    Trojan.Win32.Generic!BT
        TheHacker               True    Trojan/Inject.nfv
        BitDefender             True    Gen:Variant.Barys.5788
        K7GW                    False   None
        K7AntiVirus             False   None
        TrendMicro              True    TROJ_GEN.R002C0DKT18
        Baidu                   False   None
        NANO-Antivirus          True    Trojan.Win32.Dapato.vpmxh
        F-Prot                  False   None
        Symantec                True    ML.Attribute.HighConfidence
        TotalDefense            False   None
        TrendMicro-HouseCall    True    TROJ_GEN.R002C0DKT18
        Paloalto                True    generic.ml
        ClamAV                  False   None
        GData                   True    Gen:Variant.Barys.5788
        Kaspersky               True    HEUR:Trojan.Win32.Generic
        Alibaba                 True    Backdoor:Win32/Poison.6fa44a48
        Babable                 False   None
        ViRobot                 True    Trojan.Win32.A.Agent.29184.AM
        AegisLab                True    Trojan.Win32.Generic.4!c
        Rising                  True    Backdoor.Poison!8.2D7 (CLOUD)
        Ad-Aware                True    Gen:Variant.Barys.5788
        Trustlook               False   None
        Sophos                  True    Troj/Hurgyu-B
        Comodo                  True    Malware@#1ndrscwmvrosl
        F-Secure                True    Trojan:W32/Agent.DUDB
        DrWeb                   True    Trojan.DownLoader6.49674
        Zillya                  True    Dropper.Dapato.Win32.15890
        Invincea                True    heuristic
        McAfee-GW-Edition       True    BehavesLike.Win32.Detnat.mm
        Trapmine                True    malicious.high.ml.score
        CMC                     True    Trojan-Dropper.Win32.Dapato!O
        Emsisoft                True    Gen:Variant.Barys.5788 (B)
        SentinelOne             True    DFI - Suspicious PE
        Cyren                   False   None
        Jiangmin                True    TrojanDropper.Dapato.jlo
        Webroot                 True    W32.Malware.Gen
        Avira                   True    HEUR/AGEN.1010960
        Antiy-AVL               True    Trojan[Dropper]/Win32.Dapato
        Kingsoft                False   None
        Endgame                 True    malicious (high confidence)
        Arcabit                 True    Trojan.Barys.D169C
        SUPERAntiSpyware        False   None
        ZoneAlarm               True    HEUR:Trojan.Win32.Generic
        Avast-Mobile            False   None
        Microsoft               True    Backdoor:Win32/Poison.AU
        TACHYON                 True    Trojan/W32.Small.29184.SN
        AhnLab-V3               True    Trojan/Win32.Inject.R46970
        Acronis                 True    suspicious
        VBA32                   True    BScope.Trojan.Reconyc
        ALYac                   True    Gen:Variant.Barys.5788
        MAX                     True    malware (ai score=85)
        Malwarebytes            False   None
        Panda                   True    Generic Malware
        Zoner                   False   None
        ESET-NOD32              True    a variant of Win32/Inject.NFV
        Tencent                 True    Win32.Trojan.Generic.Hrpn
        Yandex                  True    Trojan.DR.Dapato!qkvVtOGNQlE
        Ikarus                  True    Trojan.Win32.Inject
        eGambit                 False   None
        Fortinet                True    W32/Inject.NFV!tr
        AVG                     True    Win32:Malware-gen
        Cybereason              True    malicious.a64b83
        Avast                   True    Win32:Malware-gen
        CrowdStrike             True    win/malicious_confidence_90% (W)
        Qihoo-360               True    HEUR/Malware.QVM07.Gen
        
       Malware Downloaded to File -- VTDL287F3DDA64B830A5AC5A6DF3266F7D08.danger

       PCAP Downloaded to File -- VTDL287F3DDA64B830A5AC5A6DF3266F7D08.pcap

       Virus Total Rescan Initiated for -- 287F3DDA64B830A5AC5A6DF3266F7D08 (Requery in 10 Mins)
</pre>
