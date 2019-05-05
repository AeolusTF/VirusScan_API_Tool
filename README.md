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

        Detected by:  53 / 67
        Sophos Detection: Troj/Briba-A
        Kaspersky Detection: Backdoor.Win32.Agent.clfe
        ESET Detection: a variant of Win32/Briba.AA
        Scanned on: 2018-10-06 17:05:38
        Unique Sources 3
        Submission Names:
            92d37a92138659fa75f45ccb87242910
            wsusservice.dll_
            wsusservice2.dll_
            file-4567337_



示例详细扫描+下载+ Pcap + Json Save + Force Rescan：

root @Ae0lus：〜/ tools $ python vs.py 287f3dda64b830a5ac5a6df3266f7d08 -pdvjr

       Results for MD5:  287f3dda64b830a5ac5a6df3266f7d08

        Detected by:  50 / 66
        Sophos Detection: Troj/Hurgyu-B
        Kaspersky Detection: HEUR:Trojan.Win32.Generic
        ESET Detection: a variant of Win32/Inject.NFV
        Scanned on: 2019-03-20 20:03:39
        Unique Sources 1
        Submission Names:
            7DkduxxH

       JSON Written to File -- VTDL287F3DDA64B830A5AC5A6DF3266F7D08.json

       详细的VirusTotal信息输出：

       MicroWorld-eScan         True     Trojan.Generic.7705996
       nProtect                 True     Trojan/W32.Small.29184.SN
       CAT-QuickHeal            True     TrojanDropper.Dapato.bnnu
       McAfee                   True     Generic Dropper!ff3
       Malwarebytes             True     Trojan.Inject
       K7AntiVirus              True     Riskware
       TheHacker                False    None
       NANO-Antivirus           True     Trojan.Win32.Dapato.vpmxh
       F-Prot                   False    None
       Symantec                 True     Trojan.Gen.2
       Norman                   True     Suspicious_Gen4.AWDSR
       TotalDefense             False    None
       TrendMicro-HouseCall     True     TROJ_GEN.RCBC8HQ
       Avast                    True     MX97:ShellCode-I [Expl]
       eSafe                    False    None
       ClamAV                   False    None
       Kaspersky                True     Trojan-Dropper.Win32.Dapato.bnnu
       BitDefender              True     Trojan.Generic.7705996
       Agnitum                  True     Trojan.DR.Dapato!qkvVtOGNQlE
       SUPERAntiSpyware         False    None
       Emsisoft                 True     Trojan.Generic.7705996 (B)
       Comodo                   True     UnclassifiedMalware
       F-Secure                 True     Trojan:W32/Agent.DUDB
       DrWeb                    True     Trojan.DownLoader6.49674
       VIPRE                    True     Trojan.Win32.Generic!BT
       AntiVir                  True     TR/Agent.29184.170
       TrendMicro               True     TROJ_GEN.RCBC8HQ
       McAfee-GW-Edition        True     Generic Dropper!ff3
       Sophos                   True     Troj/Hurgyu-A
       Jiangmin                 True     TrojanDropper.Dapato.mfq
       Antiy-AVL                True     Trojan/Win32.Dapato.gen
       Kingsoft                 True     Win32.Troj.Dapato.(kcloud)
       Microsoft                True     VirTool:Win32/Obfuscator.ABD
       ViRobot                  True     Dropper.A.Dapato.29184.J
       AhnLab-V3                True     Trojan/Win32.Inject
       GData                    True     Trojan.Generic.7705996
       Commtouch                False    None
       ByteHero                 False    None
       VBA32                    True     Trojan-Dropper.Dapato.bnnu
       PCTools                  True     Trojan.Gen
       ESET-NOD32               True     a variant of Win32/Inject.NFV
       Rising                   True     Suspicious
       Ikarus                   True     Win32.SuspectCrc
       Fortinet                 True     W32/Inject.NFV!tr
       AVG                      True     Dropper.Generic6.APFX
       Panda                    True     Generic Trojan

       Malware Downloaded to File -- VTDL287F3DDA64B830A5AC5A6DF3266F7D08.danger

       PCAP Downloaded to File -- VTDL287F3DDA64B830A5AC5A6DF3266F7D08.pcap

       Virus Total Rescan Initiated for -- 287F3DDA64B830A5AC5A6DF3266F7D08 (Requery in 10 Mins)
</pre>
