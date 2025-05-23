# Non exhaustive list of ETW providers for Snapdragon 778G (SM7325)

This list is for debugging purposes. Many drivers use ETW Tracing for logging. This table will help finding out which GUID you want for which driver along with commands for WinDBG and autologger snippets.

## Qualcomm BSP

<table>
<tr>
<td> Offending component </td> <td> ETW Provider Name </td> <td> ETW Provider GUID </td> <td> WMI Trace KD Command ON </td> <td> WMI Trace KD Command OFF </td> <td> Autologger </td>
</tr>
<tr>
<td>ProxyAPO</td>
<td>CTLGUID_AUDIO_APO_DRIVER
QCAPO_ERROR
QCAPO_WARNING</td>
<td>

```
A0F8425A-DAAD-486D-BDC6-4A24CB136B6F
```
</td>
<td>

```
!wmitrace.enable meow A0F8425A-DAAD-486D-BDC6-4A24CB136B6F -level 0xFF
```
</td>
<td>

```
!wmitrace.disable meow A0F8425A-DAAD-486D-BDC6-4A24CB136B6F
```
</td>
<td><details>

```.reg
[HKEY_LOCAL_MACHINE\RTS\ControlSet001\Control\WMI\Autologger\QCOM\{A0F8425A-DAAD-486D-BDC6-4A24CB136B6F}]
"Enabled"=dword:00000001
"EnableFlags"=dword:ffffffff
"EnableLevel"=dword:00000004
"MatchAnyKeyword"=hex(b):00,00,00,00,00,00,00,00
"Status"=dword:00000000

```
</details></td>
</tr>
<tr>
<td>QC_BT_BLEAPI_TEST</td>
<td>QCBLElibTraceGuid
QCBLElibinfo
Core</td>
<td>

```
045AE7B3-B4B5-4483-A1D5-D53D7E8EA008
```
</td>
<td>

```
!wmitrace.enable meow 045AE7B3-B4B5-4483-A1D5-D53D7E8EA008 -level 0xFF
```
</td>
<td>

```
!wmitrace.disable meow 045AE7B3-B4B5-4483-A1D5-D53D7E8EA008
```
</td>
<td><details>

```.reg
[HKEY_LOCAL_MACHINE\RTS\ControlSet001\Control\WMI\Autologger\QCOM\{045AE7B3-B4B5-4483-A1D5-D53D7E8EA008}]
"Enabled"=dword:00000001
"EnableFlags"=dword:ffffffff
"EnableLevel"=dword:00000004
"MatchAnyKeyword"=hex(b):00,00,00,00,00,00,00,00
"Status"=dword:00000000

```
</details></td>
</tr>
<tr>
<td>qc5gnrcoexmgr</td>
<td>NRCOEX_MGR_WPP</td>
<td>

```
de73edd6-b527-46e0-8653-599ddb79b76a
```
</td>
<td>

```
!wmitrace.enable meow de73edd6-b527-46e0-8653-599ddb79b76a -level 0xFF
```
</td>
<td>

```
!wmitrace.disable meow de73edd6-b527-46e0-8653-599ddb79b76a
```
</td>
<td><details>

```.reg
[HKEY_LOCAL_MACHINE\RTS\ControlSet001\Control\WMI\Autologger\QCOM\{de73edd6-b527-46e0-8653-599ddb79b76a}]
"Enabled"=dword:00000001
"EnableFlags"=dword:ffffffff
"EnableLevel"=dword:00000004
"MatchAnyKeyword"=hex(b):00,00,00,00,00,00,00,00
"Status"=dword:00000000

```
</details></td>
</tr>
<tr>
<td>qcabd</td>
<td>AbdTrace
EntryExit
Core</td>
<td>

```
BB4567AF-65A2-4F4A-B791-12D024B65966
```
</td>
<td>

```
!wmitrace.enable meow BB4567AF-65A2-4F4A-B791-12D024B65966 -level 0xFF
```
</td>
<td>

```
!wmitrace.disable meow BB4567AF-65A2-4F4A-B791-12D024B65966
```
</td>
<td><details>

```.reg
[HKEY_LOCAL_MACHINE\RTS\ControlSet001\Control\WMI\Autologger\QCOM\{BB4567AF-65A2-4F4A-B791-12D024B65966}]
"Enabled"=dword:00000001
"EnableFlags"=dword:ffffffff
"EnableLevel"=dword:00000004
"MatchAnyKeyword"=hex(b):00,00,00,00,00,00,00,00
"Status"=dword:00000000

```
</details></td>
</tr>
<tr>
<td>qcadc</td>
<td>AdcTrace
EntryExit
Log</td>
<td>

```
033C84E6-CC87-444E-A911-6F9C1B41548B
```
</td>
<td>

```
!wmitrace.enable meow 033C84E6-CC87-444E-A911-6F9C1B41548B -level 0xFF
```
</td>
<td>

```
!wmitrace.disable meow 033C84E6-CC87-444E-A911-6F9C1B41548B
```
</td>
<td><details>

```.reg
[HKEY_LOCAL_MACHINE\RTS\ControlSet001\Control\WMI\Autologger\QCOM\{033C84E6-CC87-444E-A911-6F9C1B41548B}]
"Enabled"=dword:00000001
"EnableFlags"=dword:ffffffff
"EnableLevel"=dword:00000004
"MatchAnyKeyword"=hex(b):00,00,00,00,00,00,00,00
"Status"=dword:00000000

```
</details></td>
</tr>
<tr>
<td>AudioDspCalMgr</td>
<td>AdcmTrace</td>
<td>

```
1C2B2962-2C8A-4BD0-9E6A-022BE277C9E4
```
</td>
<td>

```
!wmitrace.enable meow 1C2B2962-2C8A-4BD0-9E6A-022BE277C9E4 -level 0xFF
```
</td>
<td>

```
!wmitrace.disable meow 1C2B2962-2C8A-4BD0-9E6A-022BE277C9E4
```
</td>
<td><details>

```.reg
[HKEY_LOCAL_MACHINE\RTS\ControlSet001\Control\WMI\Autologger\QCOM\{1C2B2962-2C8A-4BD0-9E6A-022BE277C9E4}]
"Enabled"=dword:00000001
"EnableFlags"=dword:ffffffff
"EnableLevel"=dword:00000004
"MatchAnyKeyword"=hex(b):00,00,00,00,00,00,00,00
"Status"=dword:00000000

```
</details></td>
</tr>
<tr>
<td>qcadsprpc</td>
<td>FastRPCTrace
DBG_INIT
DBG_POWER</td>
<td>

```
09533D70-822C-4A34-B3AA-970714567089
```
</td>
<td>

```
!wmitrace.enable meow 09533D70-822C-4A34-B3AA-970714567089 -level 0xFF
```
</td>
<td>

```
!wmitrace.disable meow 09533D70-822C-4A34-B3AA-970714567089
```
</td>
<td><details>

```.reg
[HKEY_LOCAL_MACHINE\RTS\ControlSet001\Control\WMI\Autologger\QCOM\{09533D70-822C-4A34-B3AA-970714567089}]
"Enabled"=dword:00000001
"EnableFlags"=dword:ffffffff
"EnableLevel"=dword:00000004
"MatchAnyKeyword"=hex(b):00,00,00,00,00,00,00,00
"Status"=dword:00000000

```
</details></td>
</tr>
<tr>
<td>qcadsprpcd</td>
<td>AdsprpcdTrace
DBG_INIT
DBG_POWER</td>
<td>

```
A94637FC-5099-4134-94E7-BAD9DD9FAF3C
```
</td>
<td>

```
!wmitrace.enable meow A94637FC-5099-4134-94E7-BAD9DD9FAF3C -level 0xFF
```
</td>
<td>

```
!wmitrace.disable meow A94637FC-5099-4134-94E7-BAD9DD9FAF3C
```
</td>
<td><details>

```.reg
[HKEY_LOCAL_MACHINE\RTS\ControlSet001\Control\WMI\Autologger\QCOM\{A94637FC-5099-4134-94E7-BAD9DD9FAF3C}]
"Enabled"=dword:00000001
"EnableFlags"=dword:ffffffff
"EnableLevel"=dword:00000004
"MatchAnyKeyword"=hex(b):00,00,00,00,00,00,00,00
"Status"=dword:00000000

```
</details></td>
</tr>
<tr>
<td>qcauddev</td>
<td>TraceDebug
EntryExit
Core</td>
<td>

```
D3D7C968-4842-4C61-994E-2AAD4DBA2C18
```
</td>
<td>

```
!wmitrace.enable meow D3D7C968-4842-4C61-994E-2AAD4DBA2C18 -level 0xFF
```
</td>
<td>

```
!wmitrace.disable meow D3D7C968-4842-4C61-994E-2AAD4DBA2C18
```
</td>
<td><details>

```.reg
[HKEY_LOCAL_MACHINE\RTS\ControlSet001\Control\WMI\Autologger\QCOM\{D3D7C968-4842-4C61-994E-2AAD4DBA2C18}]
"Enabled"=dword:00000001
"EnableFlags"=dword:ffffffff
"EnableLevel"=dword:00000004
"MatchAnyKeyword"=hex(b):00,00,00,00,00,00,00,00
"Status"=dword:00000000

```
</details></td>
</tr>
<tr>
<td>qcaudminiport</td>
<td>CTLGUID_AUDIO_DRIVER_1
QCAUDRT_ERROR
QCAUDRT_WARNING</td>
<td>

```
B92C2819-2DAA-4804-BC96-720A82209897
```
</td>
<td>

```
!wmitrace.enable meow B92C2819-2DAA-4804-BC96-720A82209897 -level 0xFF
```
</td>
<td>

```
!wmitrace.disable meow B92C2819-2DAA-4804-BC96-720A82209897
```
</td>
<td><details>

```.reg
[HKEY_LOCAL_MACHINE\RTS\ControlSet001\Control\WMI\Autologger\QCOM\{B92C2819-2DAA-4804-BC96-720A82209897}]
"Enabled"=dword:00000001
"EnableFlags"=dword:ffffffff
"EnableLevel"=dword:00000004
"MatchAnyKeyword"=hex(b):00,00,00,00,00,00,00,00
"Status"=dword:00000000

```
</details></td>
</tr>
<tr>
<td>qcbattminiclass</td>
<td>PmicBatteryMiniclassDriverGuid
BattMiniClassWPP_SlefHost
Trace</td>
<td>

```
97413f1d-5298-4884-94eb-6fefbc0ac4a7
```
</td>
<td>

```
!wmitrace.enable meow 97413f1d-5298-4884-94eb-6fefbc0ac4a7 -level 0xFF
```
</td>
<td>

```
!wmitrace.disable meow 97413f1d-5298-4884-94eb-6fefbc0ac4a7
```
</td>
<td><details>

```.reg
[HKEY_LOCAL_MACHINE\RTS\ControlSet001\Control\WMI\Autologger\QCOM\{97413f1d-5298-4884-94eb-6fefbc0ac4a7}]
"Enabled"=dword:00000001
"EnableFlags"=dword:ffffffff
"EnableLevel"=dword:00000004
"MatchAnyKeyword"=hex(b):00,00,00,00,00,00,00,00
"Status"=dword:00000000

```
</details></td>
</tr>
<tr>
<td>qcbtfmuart

qcbtfmuart_hsp</td>
<td>qca_shb_wpp
TFLAG_PNP
TFLAG_POWER</td>
<td>

```
C484A08D-41CE-4CD6-AF73-06F987827ACE
```
</td>
<td>

```
!wmitrace.enable meow C484A08D-41CE-4CD6-AF73-06F987827ACE -level 0xFF
```
</td>
<td>

```
!wmitrace.disable meow C484A08D-41CE-4CD6-AF73-06F987827ACE
```
</td>
<td><details>

```.reg
[HKEY_LOCAL_MACHINE\RTS\ControlSet001\Control\WMI\Autologger\QCOM\{C484A08D-41CE-4CD6-AF73-06F987827ACE}]
"Enabled"=dword:00000001
"EnableFlags"=dword:ffffffff
"EnableLevel"=dword:00000004
"MatchAnyKeyword"=hex(b):00,00,00,00,00,00,00,00
"Status"=dword:00000000

```
</details></td>
</tr>
<tr>
<td>qcccidbridge</td>
<td>CcidbrgTraceGuid
CCIDBRG_TRACE_WPP</td>
<td>

```
D28DAA6A-6063-47EE-BB4D-5CE18F61C754
```
</td>
<td>

```
!wmitrace.enable meow D28DAA6A-6063-47EE-BB4D-5CE18F61C754 -level 0xFF
```
</td>
<td>

```
!wmitrace.disable meow D28DAA6A-6063-47EE-BB4D-5CE18F61C754
```
</td>
<td><details>

```.reg
[HKEY_LOCAL_MACHINE\RTS\ControlSet001\Control\WMI\Autologger\QCOM\{D28DAA6A-6063-47EE-BB4D-5CE18F61C754}]
"Enabled"=dword:00000001
"EnableFlags"=dword:ffffffff
"EnableLevel"=dword:00000004
"MatchAnyKeyword"=hex(b):00,00,00,00,00,00,00,00
"Status"=dword:00000000

```
</details></td>
</tr>
<tr>
<td>qcbtfmuart

qcbtfmuart_hst

QCDiagBridge

qcdxkm

qcglink

qcipa

qcpep

qcqdss

qcsubsys

qcwlan</td>
<td>RpelibTraceGuid
RPEinfo
Core

RpelibTraceGuid
RPEinfo</td>
<td>

```
A77E292C-44CF-4821-907A-93AC09231A2D
```
</td>
<td>

```
!wmitrace.enable meow A77E292C-44CF-4821-907A-93AC09231A2D -level 0xFF
```
</td>
<td>

```
!wmitrace.disable meow A77E292C-44CF-4821-907A-93AC09231A2D
```
</td>
<td><details>

```.reg
[HKEY_LOCAL_MACHINE\RTS\ControlSet001\Control\WMI\Autologger\QCOM\{A77E292C-44CF-4821-907A-93AC09231A2D}]
"Enabled"=dword:00000001
"EnableFlags"=dword:ffffffff
"EnableLevel"=dword:00000004
"MatchAnyKeyword"=hex(b):00,00,00,00,00,00,00,00
"Status"=dword:00000000

```
</details></td>
</tr>
<tr>
<td>qcbtfmuart

qcbtfmuart_hsp</td>
<td>qca_shb_wpp
TFLAG_PNP
TFLAG_POWER</td>
<td>

```
C484A08D-41CE-4CD6-AF73-06F987827ACE
```
</td>
<td>

```
!wmitrace.enable meow C484A08D-41CE-4CD6-AF73-06F987827ACE -level 0xFF
```
</td>
<td>

```
!wmitrace.disable meow C484A08D-41CE-4CD6-AF73-06F987827ACE
```
</td>
<td><details>

```.reg
[HKEY_LOCAL_MACHINE\RTS\ControlSet001\Control\WMI\Autologger\QCOM\{C484A08D-41CE-4CD6-AF73-06F987827ACE}]
"Enabled"=dword:00000001
"EnableFlags"=dword:ffffffff
"EnableLevel"=dword:00000004
"MatchAnyKeyword"=hex(b):00,00,00,00,00,00,00,00
"Status"=dword:00000000

```
</details></td>
</tr>
<tr>
<td>qccdi</td>
<td>CDITrace</td>
<td>

```
4b02d255-8053-4fa7-8f5b-66139f7ebe73
```
</td>
<td>

```
!wmitrace.enable meow 4b02d255-8053-4fa7-8f5b-66139f7ebe73 -level 0xFF
```
</td>
<td>

```
!wmitrace.disable meow 4b02d255-8053-4fa7-8f5b-66139f7ebe73
```
</td>
<td><details>

```.reg
[HKEY_LOCAL_MACHINE\RTS\ControlSet001\Control\WMI\Autologger\QCOM\{4b02d255-8053-4fa7-8f5b-66139f7ebe73}]
"Enabled"=dword:00000001
"EnableFlags"=dword:ffffffff
"EnableLevel"=dword:00000004
"MatchAnyKeyword"=hex(b):00,00,00,00,00,00,00,00
"Status"=dword:00000000

```
</details></td>
</tr>
<tr>
<td>qcdeepstandbymdm</td>
<td>DSBYMDM_WPP</td>
<td>

```
E3EC95BD-414D-43BF-87F2-417A41F21FF0
```
</td>
<td>

```
!wmitrace.enable meow E3EC95BD-414D-43BF-87F2-417A41F21FF0 -level 0xFF
```
</td>
<td>

```
!wmitrace.disable meow E3EC95BD-414D-43BF-87F2-417A41F21FF0
```
</td>
<td><details>

```.reg
[HKEY_LOCAL_MACHINE\RTS\ControlSet001\Control\WMI\Autologger\QCOM\{E3EC95BD-414D-43BF-87F2-417A41F21FF0}]
"Enabled"=dword:00000001
"EnableFlags"=dword:ffffffff
"EnableLevel"=dword:00000004
"MatchAnyKeyword"=hex(b):00,00,00,00,00,00,00,00
"Status"=dword:00000000

```
</details></td>
</tr>
<tr>
<td>QCDiagBridge</td>
<td>QcdbTrace
DBG_ALL
DBG_DRIVER</td>
<td>

```
06F6B256-D87F-4F3B-BC94-07B471EBB957
```
</td>
<td>

```
!wmitrace.enable meow 06F6B256-D87F-4F3B-BC94-07B471EBB957 -level 0xFF
```
</td>
<td>

```
!wmitrace.disable meow 06F6B256-D87F-4F3B-BC94-07B471EBB957
```
</td>
<td><details>

```.reg
[HKEY_LOCAL_MACHINE\RTS\ControlSet001\Control\WMI\Autologger\QCOM\{06F6B256-D87F-4F3B-BC94-07B471EBB957}]
"Enabled"=dword:00000001
"EnableFlags"=dword:ffffffff
"EnableLevel"=dword:00000004
"MatchAnyKeyword"=hex(b):00,00,00,00,00,00,00,00
"Status"=dword:00000000

```
</details></td>
</tr>
<tr>
<td>qcdiagcsi</td>
<td>DiagCSITrace
Core
Utils</td>
<td>

```
5AB48ED9-AAFE-40A2-84CF-DBD60690E80D
```
</td>
<td>

```
!wmitrace.enable meow 5AB48ED9-AAFE-40A2-84CF-DBD60690E80D -level 0xFF
```
</td>
<td>

```
!wmitrace.disable meow 5AB48ED9-AAFE-40A2-84CF-DBD60690E80D
```
</td>
<td><details>

```.reg
[HKEY_LOCAL_MACHINE\RTS\ControlSet001\Control\WMI\Autologger\QCOM\{5AB48ED9-AAFE-40A2-84CF-DBD60690E80D}]
"Enabled"=dword:00000001
"EnableFlags"=dword:ffffffff
"EnableLevel"=dword:00000004
"MatchAnyKeyword"=hex(b):00,00,00,00,00,00,00,00
"Status"=dword:00000000

```
</details></td>
</tr>
<tr>
<td>qcdiagrouter</td>
<td>DiagRouterTrace
Core
Protocol</td>
<td>

```
9CBA380D-42BA-45DB-94F0-AC310885CE4E
```
</td>
<td>

```
!wmitrace.enable meow 9CBA380D-42BA-45DB-94F0-AC310885CE4E -level 0xFF
```
</td>
<td>

```
!wmitrace.disable meow 9CBA380D-42BA-45DB-94F0-AC310885CE4E
```
</td>
<td><details>

```.reg
[HKEY_LOCAL_MACHINE\RTS\ControlSet001\Control\WMI\Autologger\QCOM\{9CBA380D-42BA-45DB-94F0-AC310885CE4E}]
"Enabled"=dword:00000001
"EnableFlags"=dword:ffffffff
"EnableLevel"=dword:00000004
"MatchAnyKeyword"=hex(b):00,00,00,00,00,00,00,00
"Status"=dword:00000000

```
</details></td>
</tr>
<tr>
<td>qcdplbridge</td>
<td>DplbrgTrace
DPLBRG_WPP_TRACE</td>
<td>

```
749F79BE-BF41-431F-8366-E06B309BA1B1
```
</td>
<td>

```
!wmitrace.enable meow 749F79BE-BF41-431F-8366-E06B309BA1B1 -level 0xFF
```
</td>
<td>

```
!wmitrace.disable meow 749F79BE-BF41-431F-8366-E06B309BA1B1
```
</td>
<td><details>

```.reg
[HKEY_LOCAL_MACHINE\RTS\ControlSet001\Control\WMI\Autologger\QCOM\{749F79BE-BF41-431F-8366-E06B309BA1B1}]
"Enabled"=dword:00000001
"EnableFlags"=dword:ffffffff
"EnableLevel"=dword:00000004
"MatchAnyKeyword"=hex(b):00,00,00,00,00,00,00,00
"Status"=dword:00000000

```
</details></td>
</tr>
<tr>
<td>qcdx11arm32um

qcdx11arm64um

qcdx11arm64xum

qcdx11chpeum

qcdx11x86um</td>
<td>dx11Trace
bin
vs</td>
<td>

```
B770C40B-693B-452B-92E1-207B14C403DA
```
</td>
<td>

```
!wmitrace.enable meow B770C40B-693B-452B-92E1-207B14C403DA -level 0xFF
```
</td>
<td>

```
!wmitrace.disable meow B770C40B-693B-452B-92E1-207B14C403DA
```
</td>
<td><details>

```.reg
[HKEY_LOCAL_MACHINE\RTS\ControlSet001\Control\WMI\Autologger\QCOM\{B770C40B-693B-452B-92E1-207B14C403DA}]
"Enabled"=dword:00000001
"EnableFlags"=dword:ffffffff
"EnableLevel"=dword:00000004
"MatchAnyKeyword"=hex(b):00,00,00,00,00,00,00,00
"Status"=dword:00000000

```
</details></td>
</tr>
<tr>
<td>qcdx12arm32um

qcdx12arm64um

qcdx12arm64xum

qcdx12chpeum

qcdx12x86um</td>
<td>dx12Trace
entryExit
assert</td>
<td>

```
0CC81B61-D1B4-4A2F-9253-9FE25448B470
```
</td>
<td>

```
!wmitrace.enable meow 0CC81B61-D1B4-4A2F-9253-9FE25448B470 -level 0xFF
```
</td>
<td>

```
!wmitrace.disable meow 0CC81B61-D1B4-4A2F-9253-9FE25448B470
```
</td>
<td><details>

```.reg
[HKEY_LOCAL_MACHINE\RTS\ControlSet001\Control\WMI\Autologger\QCOM\{0CC81B61-D1B4-4A2F-9253-9FE25448B470}]
"Enabled"=dword:00000001
"EnableFlags"=dword:ffffffff
"EnableLevel"=dword:00000004
"MatchAnyKeyword"=hex(b):00,00,00,00,00,00,00,00
"Status"=dword:00000000

```
</details></td>
</tr>
<tr>
<td>qcdxkm</td>
<td>QdiKmdTrace
QdiTraceMDP
QdiTraceDSI</td>
<td>

```
E55D560E-55FA-47C3-A3EC-2AA0C319C2EF
```
</td>
<td>

```
!wmitrace.enable meow E55D560E-55FA-47C3-A3EC-2AA0C319C2EF -level 0xFF
```
</td>
<td>

```
!wmitrace.disable meow E55D560E-55FA-47C3-A3EC-2AA0C319C2EF
```
</td>
<td><details>

```.reg
[HKEY_LOCAL_MACHINE\RTS\ControlSet001\Control\WMI\Autologger\QCOM\{E55D560E-55FA-47C3-A3EC-2AA0C319C2EF}]
"Enabled"=dword:00000001
"EnableFlags"=dword:ffffffff
"EnableLevel"=dword:00000004
"MatchAnyKeyword"=hex(b):00,00,00,00,00,00,00,00
"Status"=dword:00000000

```
</details></td>
</tr>
<tr>
<td>qcdxkm</td>
<td>GpuKmdTrace
GpuDcvsAlgorithmOutput
GpuDcvsRawData</td>
<td>

```
AF531841-DA56-4E11-87EE-1D4F673BC873
```
</td>
<td>

```
!wmitrace.enable meow AF531841-DA56-4E11-87EE-1D4F673BC873 -level 0xFF
```
</td>
<td>

```
!wmitrace.disable meow AF531841-DA56-4E11-87EE-1D4F673BC873
```
</td>
<td><details>

```.reg
[HKEY_LOCAL_MACHINE\RTS\ControlSet001\Control\WMI\Autologger\QCOM\{AF531841-DA56-4E11-87EE-1D4F673BC873}]
"Enabled"=dword:00000001
"EnableFlags"=dword:ffffffff
"EnableLevel"=dword:00000004
"MatchAnyKeyword"=hex(b):00,00,00,00,00,00,00,00
"Status"=dword:00000000

```
</details></td>
</tr>
<tr>
<td>QcEUD</td>
<td>QcEUDTraceGuid
FuncTrace
DBG_INIT</td>
<td>

```
D15F23FF-6EE1-406B-ADD6-4AC396DEE296
```
</td>
<td>

```
!wmitrace.enable meow D15F23FF-6EE1-406B-ADD6-4AC396DEE296 -level 0xFF
```
</td>
<td>

```
!wmitrace.disable meow D15F23FF-6EE1-406B-ADD6-4AC396DEE296
```
</td>
<td><details>

```.reg
[HKEY_LOCAL_MACHINE\RTS\ControlSet001\Control\WMI\Autologger\QCOM\{D15F23FF-6EE1-406B-ADD6-4AC396DEE296}]
"Enabled"=dword:00000001
"EnableFlags"=dword:ffffffff
"EnableLevel"=dword:00000004
"MatchAnyKeyword"=hex(b):00,00,00,00,00,00,00,00
"Status"=dword:00000000

```
</details></td>
</tr>
<tr>
<td>Qcfgbcl</td>
<td>fgbclTrace
FGBCLWPP_SelfHost
FGBCLWPP_Trace</td>
<td>

```
E528B6D3-4B45-44D2-AA9E-589BF570B994
```
</td>
<td>

```
!wmitrace.enable meow E528B6D3-4B45-44D2-AA9E-589BF570B994 -level 0xFF
```
</td>
<td>

```
!wmitrace.disable meow E528B6D3-4B45-44D2-AA9E-589BF570B994
```
</td>
<td><details>

```.reg
[HKEY_LOCAL_MACHINE\RTS\ControlSet001\Control\WMI\Autologger\QCOM\{E528B6D3-4B45-44D2-AA9E-589BF570B994}]
"Enabled"=dword:00000001
"EnableFlags"=dword:ffffffff
"EnableLevel"=dword:00000004
"MatchAnyKeyword"=hex(b):00,00,00,00,00,00,00,00
"Status"=dword:00000000

```
</details></td>
</tr>
<tr>
<td>qcglink</td>
<td>GlinkTraceErrGuid
Error</td>
<td>

```
e98045ad-4058-444c-a751-97157605bbf8
```
</td>
<td>

```
!wmitrace.enable meow e98045ad-4058-444c-a751-97157605bbf8 -level 0xFF
```
</td>
<td>

```
!wmitrace.disable meow e98045ad-4058-444c-a751-97157605bbf8
```
</td>
<td><details>

```.reg
[HKEY_LOCAL_MACHINE\RTS\ControlSet001\Control\WMI\Autologger\QCOM\{e98045ad-4058-444c-a751-97157605bbf8}]
"Enabled"=dword:00000001
"EnableFlags"=dword:ffffffff
"EnableLevel"=dword:00000004
"MatchAnyKeyword"=hex(b):00,00,00,00,00,00,00,00
"Status"=dword:00000000

```
</details></td>
</tr>
<tr>
<td>qcglink</td>
<td>GlinkTraceGuid
EntryExit
Wdf</td>
<td>

```
c37a7356-c3d3-45a7-b991-01c0403e5918
```
</td>
<td>

```
!wmitrace.enable meow c37a7356-c3d3-45a7-b991-01c0403e5918 -level 0xFF
```
</td>
<td>

```
!wmitrace.disable meow c37a7356-c3d3-45a7-b991-01c0403e5918
```
</td>
<td><details>

```.reg
[HKEY_LOCAL_MACHINE\RTS\ControlSet001\Control\WMI\Autologger\QCOM\{c37a7356-c3d3-45a7-b991-01c0403e5918}]
"Enabled"=dword:00000001
"EnableFlags"=dword:ffffffff
"EnableLevel"=dword:00000004
"MatchAnyKeyword"=hex(b):00,00,00,00,00,00,00,00
"Status"=dword:00000000

```
</details></td>
</tr>
<tr>
<td>qcgnss</td>
<td>GpsTraceGuid
DBG_INFO_HIGH
DBG_INFO_MEDIUM</td>
<td>

```
8AC657C6-6FCE-4904-93BC-E631ED8134BB
```
</td>
<td>

```
!wmitrace.enable meow 8AC657C6-6FCE-4904-93BC-E631ED8134BB -level 0xFF
```
</td>
<td>

```
!wmitrace.disable meow 8AC657C6-6FCE-4904-93BC-E631ED8134BB
```
</td>
<td><details>

```.reg
[HKEY_LOCAL_MACHINE\RTS\ControlSet001\Control\WMI\Autologger\QCOM\{8AC657C6-6FCE-4904-93BC-E631ED8134BB}]
"Enabled"=dword:00000001
"EnableFlags"=dword:ffffffff
"EnableLevel"=dword:00000004
"MatchAnyKeyword"=hex(b):00,00,00,00,00,00,00,00
"Status"=dword:00000000

```
</details></td>
</tr>
<tr>
<td></td>
<td>NI</td>
<td>

```
7A0A5522-F1D4-450F-903B-F945F1FB67F1
```
</td>
<td>

```
!wmitrace.enable meow 7A0A5522-F1D4-450F-903B-F945F1FB67F1 -level 0xFF
```
</td>
<td>

```
!wmitrace.disable meow 7A0A5522-F1D4-450F-903B-F945F1FB67F1
```
</td>
<td><details>

```.reg
[HKEY_LOCAL_MACHINE\RTS\ControlSet001\Control\WMI\Autologger\QCOM\{7A0A5522-F1D4-450F-903B-F945F1FB67F1}]
"Enabled"=dword:00000001
"EnableFlags"=dword:ffffffff
"EnableLevel"=dword:00000004
"MatchAnyKeyword"=hex(b):00,00,00,00,00,00,00,00
"Status"=dword:00000000

```
</details></td>
</tr>
<tr>
<td></td>
<td>Geofence</td>
<td>

```
DF6D05B1-3295-4364-9D88-304106352274
```
</td>
<td>

```
!wmitrace.enable meow DF6D05B1-3295-4364-9D88-304106352274 -level 0xFF
```
</td>
<td>

```
!wmitrace.disable meow DF6D05B1-3295-4364-9D88-304106352274
```
</td>
<td><details>

```.reg
[HKEY_LOCAL_MACHINE\RTS\ControlSet001\Control\WMI\Autologger\QCOM\{DF6D05B1-3295-4364-9D88-304106352274}]
"Enabled"=dword:00000001
"EnableFlags"=dword:ffffffff
"EnableLevel"=dword:00000004
"MatchAnyKeyword"=hex(b):00,00,00,00,00,00,00,00
"Status"=dword:00000000

```
</details></td>
</tr>
<tr>
<td></td>
<td>Qmiloc</td>
<td>

```
6F28F4BA-37F0-4BB4-B6CE-BB273B88CA54
```
</td>
<td>

```
!wmitrace.enable meow 6F28F4BA-37F0-4BB4-B6CE-BB273B88CA54 -level 0xFF
```
</td>
<td>

```
!wmitrace.disable meow 6F28F4BA-37F0-4BB4-B6CE-BB273B88CA54
```
</td>
<td><details>

```.reg
[HKEY_LOCAL_MACHINE\RTS\ControlSet001\Control\WMI\Autologger\QCOM\{6F28F4BA-37F0-4BB4-B6CE-BB273B88CA54}]
"Enabled"=dword:00000001
"EnableFlags"=dword:ffffffff
"EnableLevel"=dword:00000004
"MatchAnyKeyword"=hex(b):00,00,00,00,00,00,00,00
"Status"=dword:00000000

```
</details></td>
</tr>
<tr>
<td></td>
<td>QmuxTrace</td>
<td>

```
40D8BF0F-70D8-4AF2-8A20-B866AB10F380
```
</td>
<td>

```
!wmitrace.enable meow 40D8BF0F-70D8-4AF2-8A20-B866AB10F380 -level 0xFF
```
</td>
<td>

```
!wmitrace.disable meow 40D8BF0F-70D8-4AF2-8A20-B866AB10F380
```
</td>
<td><details>

```.reg
[HKEY_LOCAL_MACHINE\RTS\ControlSet001\Control\WMI\Autologger\QCOM\{40D8BF0F-70D8-4AF2-8A20-B866AB10F380}]
"Enabled"=dword:00000001
"EnableFlags"=dword:ffffffff
"EnableLevel"=dword:00000004
"MatchAnyKeyword"=hex(b):00,00,00,00,00,00,00,00
"Status"=dword:00000000

```
</details></td>
</tr>
<tr>
<td>qcgpi</td>
<td>GpiTracer
TRACE_FLAG_GPI
TRACE_FLAG_INTERNAL</td>
<td>

```
F0EEE77F-2B57-43A3-82E9-20F0F02331E1
```
</td>
<td>

```
!wmitrace.enable meow F0EEE77F-2B57-43A3-82E9-20F0F02331E1 -level 0xFF
```
</td>
<td>

```
!wmitrace.disable meow F0EEE77F-2B57-43A3-82E9-20F0F02331E1
```
</td>
<td><details>

```.reg
[HKEY_LOCAL_MACHINE\RTS\ControlSet001\Control\WMI\Autologger\QCOM\{F0EEE77F-2B57-43A3-82E9-20F0F02331E1}]
"Enabled"=dword:00000001
"EnableFlags"=dword:ffffffff
"EnableLevel"=dword:00000004
"MatchAnyKeyword"=hex(b):00,00,00,00,00,00,00,00
"Status"=dword:00000000

```
</details></td>
</tr>
<tr>
<td>qcgpio</td>
<td>QcGpioTraceGuid
TRACE_DRIVERLOAD
TRACE_DEVICEINIT</td>
<td>

```
302c57a4-26d4-4ec3-B754-29025DCD164B
```
</td>
<td>

```
!wmitrace.enable meow 302c57a4-26d4-4ec3-B754-29025DCD164B -level 0xFF
```
</td>
<td>

```
!wmitrace.disable meow 302c57a4-26d4-4ec3-B754-29025DCD164B
```
</td>
<td><details>

```.reg
[HKEY_LOCAL_MACHINE\RTS\ControlSet001\Control\WMI\Autologger\QCOM\{302c57a4-26d4-4ec3-B754-29025DCD164B}]
"Enabled"=dword:00000001
"EnableFlags"=dword:ffffffff
"EnableLevel"=dword:00000004
"MatchAnyKeyword"=hex(b):00,00,00,00,00,00,00,00
"Status"=dword:00000000

```
</details></td>
</tr>
<tr>
<td>qchdcpumd</td>
<td>CtlGuid
UMD_HDCP_INFO
UMD_HDCP_DEBUG</td>
<td>

```
28EE579B-CF67-43b6-9D19-8930E7AAA131
```
</td>
<td>

```
!wmitrace.enable meow 28EE579B-CF67-43b6-9D19-8930E7AAA131 -level 0xFF
```
</td>
<td>

```
!wmitrace.disable meow 28EE579B-CF67-43b6-9D19-8930E7AAA131
```
</td>
<td><details>

```.reg
[HKEY_LOCAL_MACHINE\RTS\ControlSet001\Control\WMI\Autologger\QCOM\{28EE579B-CF67-43b6-9D19-8930E7AAA131}]
"Enabled"=dword:00000001
"EnableFlags"=dword:ffffffff
"EnableLevel"=dword:00000004
"MatchAnyKeyword"=hex(b):00,00,00,00,00,00,00,00
"Status"=dword:00000000

```
</details></td>
</tr>
<tr>
<td>qchwnled</td>
<td>hwnledTraceGuid
MYDRIVER_ALL_INFO
TRACE_DRIVER</td>
<td>

```
1B23D121-227A-4CA9-A143-BAF9205EF142
```
</td>
<td>

```
!wmitrace.enable meow 1B23D121-227A-4CA9-A143-BAF9205EF142 -level 0xFF
```
</td>
<td>

```
!wmitrace.disable meow 1B23D121-227A-4CA9-A143-BAF9205EF142
```
</td>
<td><details>

```.reg
[HKEY_LOCAL_MACHINE\RTS\ControlSet001\Control\WMI\Autologger\QCOM\{1B23D121-227A-4CA9-A143-BAF9205EF142}]
"Enabled"=dword:00000001
"EnableFlags"=dword:ffffffff
"EnableLevel"=dword:00000004
"MatchAnyKeyword"=hex(b):00,00,00,00,00,00,00,00
"Status"=dword:00000000

```
</details></td>
</tr>
<tr>
<td>qci2c</td>
<td>PbcTraceGuid
TRACE_FLAG_WDFLOADING
TRACE_FLAG_SPBDDI</td>
<td>

```
EF49A24A-40CD-46D0-8A8A-3623B7A18969
```
</td>
<td>

```
!wmitrace.enable meow EF49A24A-40CD-46D0-8A8A-3623B7A18969 -level 0xFF
```
</td>
<td>

```
!wmitrace.disable meow EF49A24A-40CD-46D0-8A8A-3623B7A18969
```
</td>
<td><details>

```.reg
[HKEY_LOCAL_MACHINE\RTS\ControlSet001\Control\WMI\Autologger\QCOM\{EF49A24A-40CD-46D0-8A8A-3623B7A18969}]
"Enabled"=dword:00000001
"EnableFlags"=dword:ffffffff
"EnableLevel"=dword:00000004
"MatchAnyKeyword"=hex(b):00,00,00,00,00,00,00,00
"Status"=dword:00000000

```
</details></td>
</tr>
<tr>
<td>qciommu</td>
<td>SmmuTrace
EntryExit
Core</td>
<td>

```
C1C2BFB3-0542-4352-9D2B-C8515A674A97
```
</td>
<td>

```
!wmitrace.enable meow C1C2BFB3-0542-4352-9D2B-C8515A674A97 -level 0xFF
```
</td>
<td>

```
!wmitrace.disable meow C1C2BFB3-0542-4352-9D2B-C8515A674A97
```
</td>
<td><details>

```.reg
[HKEY_LOCAL_MACHINE\RTS\ControlSet001\Control\WMI\Autologger\QCOM\{C1C2BFB3-0542-4352-9D2B-C8515A674A97}]
"Enabled"=dword:00000001
"EnableFlags"=dword:ffffffff
"EnableLevel"=dword:00000004
"MatchAnyKeyword"=hex(b):00,00,00,00,00,00,00,00
"Status"=dword:00000000

```
</details></td>
</tr>
<tr>
<td>qciommu

qcsmmu</td>
<td>SmmuTrace
EntryExit
Core</td>
<td>

```
cf6bfd48-e161-4949-96d5-8647cfc488c8
```
</td>
<td>

```
!wmitrace.enable meow cf6bfd48-e161-4949-96d5-8647cfc488c8 -level 0xFF
```
</td>
<td>

```
!wmitrace.disable meow cf6bfd48-e161-4949-96d5-8647cfc488c8
```
</td>
<td><details>

```.reg
[HKEY_LOCAL_MACHINE\RTS\ControlSet001\Control\WMI\Autologger\QCOM\{cf6bfd48-e161-4949-96d5-8647cfc488c8}]
"Enabled"=dword:00000001
"EnableFlags"=dword:ffffffff
"EnableLevel"=dword:00000004
"MatchAnyKeyword"=hex(b):00,00,00,00,00,00,00,00
"Status"=dword:00000000

```
</details></td>
</tr>
<tr>
<td>qcipa</td>
<td>IPATRACE
EntryExit
IPA</td>
<td>

```
367DC0A5-4DE5-4142-C7D4-E29C47275A6C
```
</td>
<td>

```
!wmitrace.enable meow 367DC0A5-4DE5-4142-C7D4-E29C47275A6C -level 0xFF
```
</td>
<td>

```
!wmitrace.disable meow 367DC0A5-4DE5-4142-C7D4-E29C47275A6C
```
</td>
<td><details>

```.reg
[HKEY_LOCAL_MACHINE\RTS\ControlSet001\Control\WMI\Autologger\QCOM\{367DC0A5-4DE5-4142-C7D4-E29C47275A6C}]
"Enabled"=dword:00000001
"EnableFlags"=dword:ffffffff
"EnableLevel"=dword:00000004
"MatchAnyKeyword"=hex(b):00,00,00,00,00,00,00,00
"Status"=dword:00000000

```
</details></td>
</tr>
<tr>
<td>qcipcc</td>
<td>QcIpccTrace</td>
<td>

```
9c9b9be9-56c0-4012-a2e6-e702ee6b7e61
```
</td>
<td>

```
!wmitrace.enable meow 9c9b9be9-56c0-4012-a2e6-e702ee6b7e61 -level 0xFF
```
</td>
<td>

```
!wmitrace.disable meow 9c9b9be9-56c0-4012-a2e6-e702ee6b7e61
```
</td>
<td><details>

```.reg
[HKEY_LOCAL_MACHINE\RTS\ControlSet001\Control\WMI\Autologger\QCOM\{9c9b9be9-56c0-4012-a2e6-e702ee6b7e61}]
"Enabled"=dword:00000001
"EnableFlags"=dword:ffffffff
"EnableLevel"=dword:00000004
"MatchAnyKeyword"=hex(b):00,00,00,00,00,00,00,00
"Status"=dword:00000000

```
</details></td>
</tr>
<tr>
<td>qcipcrouter</td>
<td>IPCRouterTraceCtrlGuid
EntryExit
Wdf</td>
<td>

```
0076be32-0be5-4df7-a923-a19945d66ab0
```
</td>
<td>

```
!wmitrace.enable meow 0076be32-0be5-4df7-a923-a19945d66ab0 -level 0xFF
```
</td>
<td>

```
!wmitrace.disable meow 0076be32-0be5-4df7-a923-a19945d66ab0
```
</td>
<td><details>

```.reg
[HKEY_LOCAL_MACHINE\RTS\ControlSet001\Control\WMI\Autologger\QCOM\{0076be32-0be5-4df7-a923-a19945d66ab0}]
"Enabled"=dword:00000001
"EnableFlags"=dword:ffffffff
"EnableLevel"=dword:00000004
"MatchAnyKeyword"=hex(b):00,00,00,00,00,00,00,00
"Status"=dword:00000000

```
</details></td>
</tr>
<tr>
<td>qcipcrouter</td>
<td>IPCRouterTraceErrGuid
Error</td>
<td>

```
500cfd06-5db8-49e3-9e1c-1613cf51d308
```
</td>
<td>

```
!wmitrace.enable meow 500cfd06-5db8-49e3-9e1c-1613cf51d308 -level 0xFF
```
</td>
<td>

```
!wmitrace.disable meow 500cfd06-5db8-49e3-9e1c-1613cf51d308
```
</td>
<td><details>

```.reg
[HKEY_LOCAL_MACHINE\RTS\ControlSet001\Control\WMI\Autologger\QCOM\{500cfd06-5db8-49e3-9e1c-1613cf51d308}]
"Enabled"=dword:00000001
"EnableFlags"=dword:ffffffff
"EnableLevel"=dword:00000004
"MatchAnyKeyword"=hex(b):00,00,00,00,00,00,00,00
"Status"=dword:00000000

```
</details></td>
</tr>
<tr>
<td>qcipcrouter</td>
<td>IPCRouterTracePktGuid
TracePkt</td>
<td>

```
5767b83a-4578-4020-8db1-c26cb6e88a49
```
</td>
<td>

```
!wmitrace.enable meow 5767b83a-4578-4020-8db1-c26cb6e88a49 -level 0xFF
```
</td>
<td>

```
!wmitrace.disable meow 5767b83a-4578-4020-8db1-c26cb6e88a49
```
</td>
<td><details>

```.reg
[HKEY_LOCAL_MACHINE\RTS\ControlSet001\Control\WMI\Autologger\QCOM\{5767b83a-4578-4020-8db1-c26cb6e88a49}]
"Enabled"=dword:00000001
"EnableFlags"=dword:ffffffff
"EnableLevel"=dword:00000004
"MatchAnyKeyword"=hex(b):00,00,00,00,00,00,00,00
"Status"=dword:00000000

```
</details></td>
</tr>
<tr>
<td>qckmbam</td>
<td>BamTraceGuid
CORE
TRACE_DRIVER</td>
<td>

```
5C443E1C-6949-4E39-A898-2020331C8F90
```
</td>
<td>

```
!wmitrace.enable meow 5C443E1C-6949-4E39-A898-2020331C8F90 -level 0xFF
```
</td>
<td>

```
!wmitrace.disable meow 5C443E1C-6949-4E39-A898-2020331C8F90
```
</td>
<td><details>

```.reg
[HKEY_LOCAL_MACHINE\RTS\ControlSet001\Control\WMI\Autologger\QCOM\{5C443E1C-6949-4E39-A898-2020331C8F90}]
"Enabled"=dword:00000001
"EnableFlags"=dword:ffffffff
"EnableLevel"=dword:00000004
"MatchAnyKeyword"=hex(b):00,00,00,00,00,00,00,00
"Status"=dword:00000000

```
</details></td>
</tr>
<tr>
<td>QCListenSoundModel</td>
<td>CntrlQCSounModelDll
SMDBH_INFO
SMDBH_ERROR</td>
<td>

```
435B6D64-B9CE-4DB5-BAF6-11060BC7656F
```
</td>
<td>

```
!wmitrace.enable meow 435B6D64-B9CE-4DB5-BAF6-11060BC7656F -level 0xFF
```
</td>
<td>

```
!wmitrace.disable meow 435B6D64-B9CE-4DB5-BAF6-11060BC7656F
```
</td>
<td><details>

```.reg
[HKEY_LOCAL_MACHINE\RTS\ControlSet001\Control\WMI\Autologger\QCOM\{435B6D64-B9CE-4DB5-BAF6-11060BC7656F}]
"Enabled"=dword:00000001
"EnableFlags"=dword:ffffffff
"EnableLevel"=dword:00000004
"MatchAnyKeyword"=hex(b):00,00,00,00,00,00,00,00
"Status"=dword:00000000

```
</details></td>
</tr>
<tr>
<td>qcmbbnetadapter</td>
<td>QCOM_DATAIO_WPP</td>
<td>

```
5D16139A-7BFA-49BF-A6AF-7DBADCE37773
```
</td>
<td>

```
!wmitrace.enable meow 5D16139A-7BFA-49BF-A6AF-7DBADCE37773 -level 0xFF
```
</td>
<td>

```
!wmitrace.disable meow 5D16139A-7BFA-49BF-A6AF-7DBADCE37773
```
</td>
<td><details>

```.reg
[HKEY_LOCAL_MACHINE\RTS\ControlSet001\Control\WMI\Autologger\QCOM\{5D16139A-7BFA-49BF-A6AF-7DBADCE37773}]
"Enabled"=dword:00000001
"EnableFlags"=dword:ffffffff
"EnableLevel"=dword:00000004
"MatchAnyKeyword"=hex(b):00,00,00,00,00,00,00,00
"Status"=dword:00000000

```
</details></td>
</tr>
<tr>
<td></td>
<td>QCOM_PCIEIO_WPP
QCOM_NETADAPTER_WPP</td>
<td>

```
356297b5-5d26-4f97-bc0b-20dd5dbeabcd
```
</td>
<td>

```
!wmitrace.enable meow 356297b5-5d26-4f97-bc0b-20dd5dbeabcd -level 0xFF
```
</td>
<td>

```
!wmitrace.disable meow 356297b5-5d26-4f97-bc0b-20dd5dbeabcd
```
</td>
<td><details>

```.reg
[HKEY_LOCAL_MACHINE\RTS\ControlSet001\Control\WMI\Autologger\QCOM\{356297b5-5d26-4f97-bc0b-20dd5dbeabcd}]
"Enabled"=dword:00000001
"EnableFlags"=dword:ffffffff
"EnableLevel"=dword:00000004
"MatchAnyKeyword"=hex(b):00,00,00,00,00,00,00,00
"Status"=dword:00000000

```
</details></td>
</tr>
<tr>
<td>qcmbbnetadapterfilter</td>
<td>QNET_FLTR_TRACE</td>
<td>

```
3f6186be-d390-4981-a62b-b9214cdc93b4
```
</td>
<td>

```
!wmitrace.enable meow 3f6186be-d390-4981-a62b-b9214cdc93b4 -level 0xFF
```
</td>
<td>

```
!wmitrace.disable meow 3f6186be-d390-4981-a62b-b9214cdc93b4
```
</td>
<td><details>

```.reg
[HKEY_LOCAL_MACHINE\RTS\ControlSet001\Control\WMI\Autologger\QCOM\{3f6186be-d390-4981-a62b-b9214cdc93b4}]
"Enabled"=dword:00000001
"EnableFlags"=dword:ffffffff
"EnableLevel"=dword:00000004
"MatchAnyKeyword"=hex(b):00,00,00,00,00,00,00,00
"Status"=dword:00000000

```
</details></td>
</tr>
<tr>
<td>qcmbrg</td>
<td>MbrgTracer
MBRG_WPP_LOGS</td>
<td>

```
cdef430e-1881-4bc4-b281-c477253e4b17
```
</td>
<td>

```
!wmitrace.enable meow cdef430e-1881-4bc4-b281-c477253e4b17 -level 0xFF
```
</td>
<td>

```
!wmitrace.disable meow cdef430e-1881-4bc4-b281-c477253e4b17
```
</td>
<td><details>

```.reg
[HKEY_LOCAL_MACHINE\RTS\ControlSet001\Control\WMI\Autologger\QCOM\{cdef430e-1881-4bc4-b281-c477253e4b17}]
"Enabled"=dword:00000001
"EnableFlags"=dword:ffffffff
"EnableLevel"=dword:00000004
"MatchAnyKeyword"=hex(b):00,00,00,00,00,00,00,00
"Status"=dword:00000000

```
</details></td>
</tr>
<tr>
<td>qcpdsr</td>
<td>PDSRTrace
EntryExit
PDSR</td>
<td>

```
8626d8e5-081f-48d7-a01a-040ef269652b
```
</td>
<td>

```
!wmitrace.enable meow 8626d8e5-081f-48d7-a01a-040ef269652b -level 0xFF
```
</td>
<td>

```
!wmitrace.disable meow 8626d8e5-081f-48d7-a01a-040ef269652b
```
</td>
<td><details>

```.reg
[HKEY_LOCAL_MACHINE\RTS\ControlSet001\Control\WMI\Autologger\QCOM\{8626d8e5-081f-48d7-a01a-040ef269652b}]
"Enabled"=dword:00000001
"EnableFlags"=dword:ffffffff
"EnableLevel"=dword:00000004
"MatchAnyKeyword"=hex(b):00,00,00,00,00,00,00,00
"Status"=dword:00000000

```
</details></td>
</tr>
<tr>
<td>qcpep</td>
<td>PepAopTraceGuid0
PEP_AOP_FLAG_COMMON</td>
<td>

```
77776ABB-0FA4-426d-B95B-2E02A583BD19
```
</td>
<td>

```
!wmitrace.enable meow 77776ABB-0FA4-426d-B95B-2E02A583BD19 -level 0xFF
```
</td>
<td>

```
!wmitrace.disable meow 77776ABB-0FA4-426d-B95B-2E02A583BD19
```
</td>
<td><details>

```.reg
[HKEY_LOCAL_MACHINE\RTS\ControlSet001\Control\WMI\Autologger\QCOM\{77776ABB-0FA4-426d-B95B-2E02A583BD19}]
"Enabled"=dword:00000001
"EnableFlags"=dword:ffffffff
"EnableLevel"=dword:00000004
"MatchAnyKeyword"=hex(b):00,00,00,00,00,00,00,00
"Status"=dword:00000000

```
</details></td>
</tr>
<tr>
<td>qcpep</td>
<td>RpmhTraceGuid0
RPMH_LOG_LEVEL_ERROR
RPMH_LOG_LEVEL_CRITICAL</td>
<td>

```
2C89C855-6301-41F9-BF56-63416DFE9CA9
```
</td>
<td>

```
!wmitrace.enable meow 2C89C855-6301-41F9-BF56-63416DFE9CA9 -level 0xFF
```
</td>
<td>

```
!wmitrace.disable meow 2C89C855-6301-41F9-BF56-63416DFE9CA9
```
</td>
<td><details>

```.reg
[HKEY_LOCAL_MACHINE\RTS\ControlSet001\Control\WMI\Autologger\QCOM\{2C89C855-6301-41F9-BF56-63416DFE9CA9}]
"Enabled"=dword:00000001
"EnableFlags"=dword:ffffffff
"EnableLevel"=dword:00000004
"MatchAnyKeyword"=hex(b):00,00,00,00,00,00,00,00
"Status"=dword:00000000

```
</details></td>
</tr>
<tr>
<td>qcpep</td>
<td>UlogTraceGuid0
ULOG_FLAG_CPR
ULOG_FLAG_CLK</td>
<td>

```
F4F985AD-8617-4D42-B21B-28E3105C0CAA
```
</td>
<td>

```
!wmitrace.enable meow F4F985AD-8617-4D42-B21B-28E3105C0CAA -level 0xFF
```
</td>
<td>

```
!wmitrace.disable meow F4F985AD-8617-4D42-B21B-28E3105C0CAA
```
</td>
<td><details>

```.reg
[HKEY_LOCAL_MACHINE\RTS\ControlSet001\Control\WMI\Autologger\QCOM\{F4F985AD-8617-4D42-B21B-28E3105C0CAA}]
"Enabled"=dword:00000001
"EnableFlags"=dword:ffffffff
"EnableLevel"=dword:00000004
"MatchAnyKeyword"=hex(b):00,00,00,00,00,00,00,00
"Status"=dword:00000000

```
</details></td>
</tr>
<tr>
<td>qcpep</td>
<td>PEPBCLTraceGUID
PEP_BCL_LOG_LEVEL_DEBUG
PEP_BCL_LOG_LEVEL_ERROR</td>
<td>

```
2A2D4F18-5DCB-4277-AF1B-7416408DCA55
```
</td>
<td>

```
!wmitrace.enable meow 2A2D4F18-5DCB-4277-AF1B-7416408DCA55 -level 0xFF
```
</td>
<td>

```
!wmitrace.disable meow 2A2D4F18-5DCB-4277-AF1B-7416408DCA55
```
</td>
<td><details>

```.reg
[HKEY_LOCAL_MACHINE\RTS\ControlSet001\Control\WMI\Autologger\QCOM\{2A2D4F18-5DCB-4277-AF1B-7416408DCA55}]
"Enabled"=dword:00000001
"EnableFlags"=dword:ffffffff
"EnableLevel"=dword:00000004
"MatchAnyKeyword"=hex(b):00,00,00,00,00,00,00,00
"Status"=dword:00000000

```
</details></td>
</tr>
<tr>
<td>qcpep</td>
<td>PEPCOREBSPTraceGUID
PEP_COREBSP_FLAG_GENERIC</td>
<td>

```
CA218504-C8B7-421D-A5F3-F932CB62BC30
```
</td>
<td>

```
!wmitrace.enable meow CA218504-C8B7-421D-A5F3-F932CB62BC30 -level 0xFF
```
</td>
<td>

```
!wmitrace.disable meow CA218504-C8B7-421D-A5F3-F932CB62BC30
```
</td>
<td><details>

```.reg
[HKEY_LOCAL_MACHINE\RTS\ControlSet001\Control\WMI\Autologger\QCOM\{CA218504-C8B7-421D-A5F3-F932CB62BC30}]
"Enabled"=dword:00000001
"EnableFlags"=dword:ffffffff
"EnableLevel"=dword:00000004
"MatchAnyKeyword"=hex(b):00,00,00,00,00,00,00,00
"Status"=dword:00000000

```
</details></td>
</tr>
<tr>
<td>qcpep</td>
<td>PEPDCVSTraceGUID
PEP_DCVS_FLAG_GENERIC</td>
<td>

```
D179D27F-322A-4EBF-B209-FBC860D05812
```
</td>
<td>

```
!wmitrace.enable meow D179D27F-322A-4EBF-B209-FBC860D05812 -level 0xFF
```
</td>
<td>

```
!wmitrace.disable meow D179D27F-322A-4EBF-B209-FBC860D05812
```
</td>
<td><details>

```.reg
[HKEY_LOCAL_MACHINE\RTS\ControlSet001\Control\WMI\Autologger\QCOM\{D179D27F-322A-4EBF-B209-FBC860D05812}]
"Enabled"=dword:00000001
"EnableFlags"=dword:ffffffff
"EnableLevel"=dword:00000004
"MatchAnyKeyword"=hex(b):00,00,00,00,00,00,00,00
"Status"=dword:00000000

```
</details></td>
</tr>
<tr>
<td>qcpep</td>
<td>PEPThermalTraceGUID
PEP_THERMAL_FLAG_GENERIC
PEP_THERMAL_FLAG_ADC</td>
<td>

```
155F8C3F-FD86-40A4-B059-4160B29A4223
```
</td>
<td>

```
!wmitrace.enable meow 155F8C3F-FD86-40A4-B059-4160B29A4223 -level 0xFF
```
</td>
<td>

```
!wmitrace.disable meow 155F8C3F-FD86-40A4-B059-4160B29A4223
```
</td>
<td><details>

```.reg
[HKEY_LOCAL_MACHINE\RTS\ControlSet001\Control\WMI\Autologger\QCOM\{155F8C3F-FD86-40A4-B059-4160B29A4223}]
"Enabled"=dword:00000001
"EnableFlags"=dword:ffffffff
"EnableLevel"=dword:00000004
"MatchAnyKeyword"=hex(b):00,00,00,00,00,00,00,00
"Status"=dword:00000000

```
</details></td>
</tr>
<tr>
<td>qcpep</td>
<td>PEPIdleTraceGUID
PEP_IDLE_FLAG_COMMON
PEP_IDLE_FLAG_CHIPSPECIFIC</td>
<td>

```
8789CFBB-E215-463F-A4A2-906DD6F0250C
```
</td>
<td>

```
!wmitrace.enable meow 8789CFBB-E215-463F-A4A2-906DD6F0250C -level 0xFF
```
</td>
<td>

```
!wmitrace.disable meow 8789CFBB-E215-463F-A4A2-906DD6F0250C
```
</td>
<td><details>

```.reg
[HKEY_LOCAL_MACHINE\RTS\ControlSet001\Control\WMI\Autologger\QCOM\{8789CFBB-E215-463F-A4A2-906DD6F0250C}]
"Enabled"=dword:00000001
"EnableFlags"=dword:ffffffff
"EnableLevel"=dword:00000004
"MatchAnyKeyword"=hex(b):00,00,00,00,00,00,00,00
"Status"=dword:00000000

```
</details></td>
</tr>
<tr>
<td>qcpep</td>
<td>PEPDevicePowerMgmtFrameworkTraceGuid
PEP_FLAG_GENERAL_FRAMEWORK
PEP_FLAG_STATE_TRANSITIONS</td>
<td>

```
39D7D81E-7C75-493F-B7A0-3171AF1AB3E2
```
</td>
<td>

```
!wmitrace.enable meow 39D7D81E-7C75-493F-B7A0-3171AF1AB3E2 -level 0xFF
```
</td>
<td>

```
!wmitrace.disable meow 39D7D81E-7C75-493F-B7A0-3171AF1AB3E2
```
</td>
<td><details>

```.reg
[HKEY_LOCAL_MACHINE\RTS\ControlSet001\Control\WMI\Autologger\QCOM\{39D7D81E-7C75-493F-B7A0-3171AF1AB3E2}]
"Enabled"=dword:00000001
"EnableFlags"=dword:ffffffff
"EnableLevel"=dword:00000004
"MatchAnyKeyword"=hex(b):00,00,00,00,00,00,00,00
"Status"=dword:00000000

```
</details></td>
</tr>
<tr>
<td>qcpep</td>
<td>CprTraceGuid0
CPR_LOG_LEVEL_ERROR
CPR_LOG_LEVEL_CRITICAL</td>
<td>

```
EA4AC5EE-4FBC-48FC-BCC1-E58D6F5429AF
```
</td>
<td>

```
!wmitrace.enable meow EA4AC5EE-4FBC-48FC-BCC1-E58D6F5429AF -level 0xFF
```
</td>
<td>

```
!wmitrace.disable meow EA4AC5EE-4FBC-48FC-BCC1-E58D6F5429AF
```
</td>
<td><details>

```.reg
[HKEY_LOCAL_MACHINE\RTS\ControlSet001\Control\WMI\Autologger\QCOM\{EA4AC5EE-4FBC-48FC-BCC1-E58D6F5429AF}]
"Enabled"=dword:00000001
"EnableFlags"=dword:ffffffff
"EnableLevel"=dword:00000004
"MatchAnyKeyword"=hex(b):00,00,00,00,00,00,00,00
"Status"=dword:00000000

```
</details></td>
</tr>
<tr>
<td>qcpep</td>
<td>PppTraceGuid
PPP_TRACE_FRAMEWORK
PPP_TRACE_FUNCTION_ENTRY_EXIT</td>
<td>

```
4747672D-8C2C-4B4C-A8B0-9A23F41549FF
```
</td>
<td>

```
!wmitrace.enable meow 4747672D-8C2C-4B4C-A8B0-9A23F41549FF -level 0xFF
```
</td>
<td>

```
!wmitrace.disable meow 4747672D-8C2C-4B4C-A8B0-9A23F41549FF
```
</td>
<td><details>

```.reg
[HKEY_LOCAL_MACHINE\RTS\ControlSet001\Control\WMI\Autologger\QCOM\{4747672D-8C2C-4B4C-A8B0-9A23F41549FF}]
"Enabled"=dword:00000001
"EnableFlags"=dword:ffffffff
"EnableLevel"=dword:00000004
"MatchAnyKeyword"=hex(b):00,00,00,00,00,00,00,00
"Status"=dword:00000000

```
</details></td>
</tr>
<tr>
<td>qcpep</td>
<td>PepTraceGuid0
SLEEP_LOG_LEVEL_ERROR
SLEEP_LOG_LEVEL_WARNING</td>
<td>

```
a577097e-09a7-43ca-a409-685f78c4efb7
```
</td>
<td>

```
!wmitrace.enable meow a577097e-09a7-43ca-a409-685f78c4efb7 -level 0xFF
```
</td>
<td>

```
!wmitrace.disable meow a577097e-09a7-43ca-a409-685f78c4efb7
```
</td>
<td><details>

```.reg
[HKEY_LOCAL_MACHINE\RTS\ControlSet001\Control\WMI\Autologger\QCOM\{a577097e-09a7-43ca-a409-685f78c4efb7}]
"Enabled"=dword:00000001
"EnableFlags"=dword:ffffffff
"EnableLevel"=dword:00000004
"MatchAnyKeyword"=hex(b):00,00,00,00,00,00,00,00
"Status"=dword:00000000

```
</details></td>
</tr>
<tr>
<td>qcpil</td>
<td>ElfParserTraceGuid
ElfParserInfo</td>
<td>

```
C1FE9AE2-F88D-443F-B40C-1BB32AE012A2
```
</td>
<td>

```
!wmitrace.enable meow C1FE9AE2-F88D-443F-B40C-1BB32AE012A2 -level 0xFF
```
</td>
<td>

```
!wmitrace.disable meow C1FE9AE2-F88D-443F-B40C-1BB32AE012A2
```
</td>
<td><details>

```.reg
[HKEY_LOCAL_MACHINE\RTS\ControlSet001\Control\WMI\Autologger\QCOM\{C1FE9AE2-F88D-443F-B40C-1BB32AE012A2}]
"Enabled"=dword:00000001
"EnableFlags"=dword:ffffffff
"EnableLevel"=dword:00000004
"MatchAnyKeyword"=hex(b):00,00,00,00,00,00,00,00
"Status"=dword:00000000

```
</details></td>
</tr>
<tr>
<td>qcpil</td>
<td>PilTrace
DBG_ALL
DBG_DRIVER</td>
<td>

```
4B2AE6CB-2AFC-4251-8DF6-55939744250F
```
</td>
<td>

```
!wmitrace.enable meow 4B2AE6CB-2AFC-4251-8DF6-55939744250F -level 0xFF
```
</td>
<td>

```
!wmitrace.disable meow 4B2AE6CB-2AFC-4251-8DF6-55939744250F
```
</td>
<td><details>

```.reg
[HKEY_LOCAL_MACHINE\RTS\ControlSet001\Control\WMI\Autologger\QCOM\{4B2AE6CB-2AFC-4251-8DF6-55939744250F}]
"Enabled"=dword:00000001
"EnableFlags"=dword:ffffffff
"EnableLevel"=dword:00000004
"MatchAnyKeyword"=hex(b):00,00,00,00,00,00,00,00
"Status"=dword:00000000

```
</details></td>
</tr>
<tr>
<td>QCPILFilter</td>
<td>PilFilterTrace</td>
<td>

```
5690ee19-f758-444a-92fc-80967b86a3ee
```
</td>
<td>

```
!wmitrace.enable meow 5690ee19-f758-444a-92fc-80967b86a3ee -level 0xFF
```
</td>
<td>

```
!wmitrace.disable meow 5690ee19-f758-444a-92fc-80967b86a3ee
```
</td>
<td><details>

```.reg
[HKEY_LOCAL_MACHINE\RTS\ControlSet001\Control\WMI\Autologger\QCOM\{5690ee19-f758-444a-92fc-80967b86a3ee}]
"Enabled"=dword:00000001
"EnableFlags"=dword:ffffffff
"EnableLevel"=dword:00000004
"MatchAnyKeyword"=hex(b):00,00,00,00,00,00,00,00
"Status"=dword:00000000

```
</details></td>
</tr>
<tr>
<td>qcpmic</td>
<td>PmicKmdfTrace
Trace
EntryExit</td>
<td>

```
23A49036-9AE1-4D2F-B167-16849DD6040D
```
</td>
<td>

```
!wmitrace.enable meow 23A49036-9AE1-4D2F-B167-16849DD6040D -level 0xFF
```
</td>
<td>

```
!wmitrace.disable meow 23A49036-9AE1-4D2F-B167-16849DD6040D
```
</td>
<td><details>

```.reg
[HKEY_LOCAL_MACHINE\RTS\ControlSet001\Control\WMI\Autologger\QCOM\{23A49036-9AE1-4D2F-B167-16849DD6040D}]
"Enabled"=dword:00000001
"EnableFlags"=dword:ffffffff
"EnableLevel"=dword:00000004
"MatchAnyKeyword"=hex(b):00,00,00,00,00,00,00,00
"Status"=dword:00000000

```
</details></td>
</tr>
<tr>
<td>QcPmicApps</td>
<td>PmicAppsTrace
Trace
EntryExit</td>
<td>

```
D46834A3-5940-43A3-B007-44E86420AC21
```
</td>
<td>

```
!wmitrace.enable meow D46834A3-5940-43A3-B007-44E86420AC21 -level 0xFF
```
</td>
<td>

```
!wmitrace.disable meow D46834A3-5940-43A3-B007-44E86420AC21
```
</td>
<td><details>

```.reg
[HKEY_LOCAL_MACHINE\RTS\ControlSet001\Control\WMI\Autologger\QCOM\{D46834A3-5940-43A3-B007-44E86420AC21}]
"Enabled"=dword:00000001
"EnableFlags"=dword:ffffffff
"EnableLevel"=dword:00000004
"MatchAnyKeyword"=hex(b):00,00,00,00,00,00,00,00
"Status"=dword:00000000

```
</details></td>
</tr>
<tr>
<td>qcpmicglink</td>
<td>PmicGlinkTrace
PmicGlinkWPP_SelfHost
PmicGlinkWPP_device</td>
<td>

```
3804DC7C-C7BC-457D-8386-DB0BCB690358
```
</td>
<td>

```
!wmitrace.enable meow 3804DC7C-C7BC-457D-8386-DB0BCB690358 -level 0xFF
```
</td>
<td>

```
!wmitrace.disable meow 3804DC7C-C7BC-457D-8386-DB0BCB690358
```
</td>
<td><details>

```.reg
[HKEY_LOCAL_MACHINE\RTS\ControlSet001\Control\WMI\Autologger\QCOM\{3804DC7C-C7BC-457D-8386-DB0BCB690358}]
"Enabled"=dword:00000001
"EnableFlags"=dword:ffffffff
"EnableLevel"=dword:00000004
"MatchAnyKeyword"=hex(b):00,00,00,00,00,00,00,00
"Status"=dword:00000000

```
</details></td>
</tr>
<tr>
<td>qcpmicgpio</td>
<td>PmicGpioTrace
EntryExit
Trace</td>
<td>

```
5BBED14F-3671-4598-AD2F-A9B6BCD3824D
```
</td>
<td>

```
!wmitrace.enable meow 5BBED14F-3671-4598-AD2F-A9B6BCD3824D -level 0xFF
```
</td>
<td>

```
!wmitrace.disable meow 5BBED14F-3671-4598-AD2F-A9B6BCD3824D
```
</td>
<td><details>

```.reg
[HKEY_LOCAL_MACHINE\RTS\ControlSet001\Control\WMI\Autologger\QCOM\{5BBED14F-3671-4598-AD2F-A9B6BCD3824D}]
"Enabled"=dword:00000001
"EnableFlags"=dword:ffffffff
"EnableLevel"=dword:00000004
"MatchAnyKeyword"=hex(b):00,00,00,00,00,00,00,00
"Status"=dword:00000000

```
</details></td>
</tr>
<tr>
<td>qcppx</td>
<td>PpxTrace</td>
<td>

```
11BB6DA3-32F8-443D-886F-2811CD201BB7
```
</td>
<td>

```
!wmitrace.enable meow 11BB6DA3-32F8-443D-886F-2811CD201BB7 -level 0xFF
```
</td>
<td>

```
!wmitrace.disable meow 11BB6DA3-32F8-443D-886F-2811CD201BB7
```
</td>
<td><details>

```.reg
[HKEY_LOCAL_MACHINE\RTS\ControlSet001\Control\WMI\Autologger\QCOM\{11BB6DA3-32F8-443D-886F-2811CD201BB7}]
"Enabled"=dword:00000001
"EnableFlags"=dword:ffffffff
"EnableLevel"=dword:00000004
"MatchAnyKeyword"=hex(b):00,00,00,00,00,00,00,00
"Status"=dword:00000000

```
</details></td>
</tr>
<tr>
<td>qcpsautoreg</td>
<td>WNWPP</td>
<td>

```
AFCB9E8B-375B-457C-919C-89BAAAE2D2F0
```
</td>
<td>

```
!wmitrace.enable meow AFCB9E8B-375B-457C-919C-89BAAAE2D2F0 -level 0xFF
```
</td>
<td>

```
!wmitrace.disable meow AFCB9E8B-375B-457C-919C-89BAAAE2D2F0
```
</td>
<td><details>

```.reg
[HKEY_LOCAL_MACHINE\RTS\ControlSet001\Control\WMI\Autologger\QCOM\{AFCB9E8B-375B-457C-919C-89BAAAE2D2F0}]
"Enabled"=dword:00000001
"EnableFlags"=dword:ffffffff
"EnableLevel"=dword:00000004
"MatchAnyKeyword"=hex(b):00,00,00,00,00,00,00,00
"Status"=dword:00000000

```
</details></td>
</tr>
<tr>
<td>qcqdss</td>
<td>qdssTraceGuid
MYDRIVER_ALL_INFO
TRACE_DRIVER</td>
<td>

```
fc0a1d4b-d5db-44cc-9ee5-07fd56ee5787
```
</td>
<td>

```
!wmitrace.enable meow fc0a1d4b-d5db-44cc-9ee5-07fd56ee5787 -level 0xFF
```
</td>
<td>

```
!wmitrace.disable meow fc0a1d4b-d5db-44cc-9ee5-07fd56ee5787
```
</td>
<td><details>

```.reg
[HKEY_LOCAL_MACHINE\RTS\ControlSet001\Control\WMI\Autologger\QCOM\{fc0a1d4b-d5db-44cc-9ee5-07fd56ee5787}]
"Enabled"=dword:00000001
"EnableFlags"=dword:ffffffff
"EnableLevel"=dword:00000004
"MatchAnyKeyword"=hex(b):00,00,00,00,00,00,00,00
"Status"=dword:00000000

```
</details></td>
</tr>
<tr>
<td>qcquadspi</td>
<td>QualcommSpiTraceGuid
ERROR
WARNING</td>
<td>

```
19C72EFC-FE22-47F6-B6A0-F25577B6205B
```
</td>
<td>

```
!wmitrace.enable meow 19C72EFC-FE22-47F6-B6A0-F25577B6205B -level 0xFF
```
</td>
<td>

```
!wmitrace.disable meow 19C72EFC-FE22-47F6-B6A0-F25577B6205B
```
</td>
<td><details>

```.reg
[HKEY_LOCAL_MACHINE\RTS\ControlSet001\Control\WMI\Autologger\QCOM\{19C72EFC-FE22-47F6-B6A0-F25577B6205B}]
"Enabled"=dword:00000001
"EnableFlags"=dword:ffffffff
"EnableLevel"=dword:00000004
"MatchAnyKeyword"=hex(b):00,00,00,00,00,00,00,00
"Status"=dword:00000000

```
</details></td>
</tr>
<tr>
<td>qcremoteat</td>
<td>FdoTrace
REMOTEAT_WPP_TRACE</td>
<td>

```
0E1402ED-3DCA-487D-8E64-91E1A5663F54
```
</td>
<td>

```
!wmitrace.enable meow 0E1402ED-3DCA-487D-8E64-91E1A5663F54 -level 0xFF
```
</td>
<td>

```
!wmitrace.disable meow 0E1402ED-3DCA-487D-8E64-91E1A5663F54
```
</td>
<td><details>

```.reg
[HKEY_LOCAL_MACHINE\RTS\ControlSet001\Control\WMI\Autologger\QCOM\{0E1402ED-3DCA-487D-8E64-91E1A5663F54}]
"Enabled"=dword:00000001
"EnableFlags"=dword:ffffffff
"EnableLevel"=dword:00000004
"MatchAnyKeyword"=hex(b):00,00,00,00,00,00,00,00
"Status"=dword:00000000

```
</details></td>
</tr>
<tr>
<td>qcremoteatsrvc</td>
<td>FdoTrace
REMOTEATSRVC_WPP_TRACE</td>
<td>

```
1EECC841-9F7C-44E2-8E9B-986ACF2173A2
```
</td>
<td>

```
!wmitrace.enable meow 1EECC841-9F7C-44E2-8E9B-986ACF2173A2 -level 0xFF
```
</td>
<td>

```
!wmitrace.disable meow 1EECC841-9F7C-44E2-8E9B-986ACF2173A2
```
</td>
<td><details>

```.reg
[HKEY_LOCAL_MACHINE\RTS\ControlSet001\Control\WMI\Autologger\QCOM\{1EECC841-9F7C-44E2-8E9B-986ACF2173A2}]
"Enabled"=dword:00000001
"EnableFlags"=dword:ffffffff
"EnableLevel"=dword:00000004
"MatchAnyKeyword"=hex(b):00,00,00,00,00,00,00,00
"Status"=dword:00000000

```
</details></td>
</tr>
<tr>
<td>qcremotefs</td>
<td>RFSTrace
EntryExit
Core</td>
<td>

```
583DA23E-3DA2-4DB2-8295-F8212C8C2511
```
</td>
<td>

```
!wmitrace.enable meow 583DA23E-3DA2-4DB2-8295-F8212C8C2511 -level 0xFF
```
</td>
<td>

```
!wmitrace.disable meow 583DA23E-3DA2-4DB2-8295-F8212C8C2511
```
</td>
<td><details>

```.reg
[HKEY_LOCAL_MACHINE\RTS\ControlSet001\Control\WMI\Autologger\QCOM\{583DA23E-3DA2-4DB2-8295-F8212C8C2511}]
"Enabled"=dword:00000001
"EnableFlags"=dword:ffffffff
"EnableLevel"=dword:00000004
"MatchAnyKeyword"=hex(b):00,00,00,00,00,00,00,00
"Status"=dword:00000000

```
</details></td>
</tr>
<tr>
<td>qcrmnetbridge</td>
<td>RmnbrgTrace
RMNBRG_WPP_TRACE</td>
<td>

```
7980CAA5-0DAA-4954-A39C-93B2B4707DD4
```
</td>
<td>

```
!wmitrace.enable meow 7980CAA5-0DAA-4954-A39C-93B2B4707DD4 -level 0xFF
```
</td>
<td>

```
!wmitrace.disable meow 7980CAA5-0DAA-4954-A39C-93B2B4707DD4
```
</td>
<td><details>

```.reg
[HKEY_LOCAL_MACHINE\RTS\ControlSet001\Control\WMI\Autologger\QCOM\{7980CAA5-0DAA-4954-A39C-93B2B4707DD4}]
"Enabled"=dword:00000001
"EnableFlags"=dword:ffffffff
"EnableLevel"=dword:00000004
"MatchAnyKeyword"=hex(b):00,00,00,00,00,00,00,00
"Status"=dword:00000000

```
</details></td>
</tr>
<tr>
<td>qcrpen</td>
<td>RpenTraceGuid
EntryExit
Core</td>
<td>

```
7311d40c-ce4f-496f-a563-f72d7bc9d92f
```
</td>
<td>

```
!wmitrace.enable meow 7311d40c-ce4f-496f-a563-f72d7bc9d92f -level 0xFF
```
</td>
<td>

```
!wmitrace.disable meow 7311d40c-ce4f-496f-a563-f72d7bc9d92f
```
</td>
<td><details>

```.reg
[HKEY_LOCAL_MACHINE\RTS\ControlSet001\Control\WMI\Autologger\QCOM\{7311d40c-ce4f-496f-a563-f72d7bc9d92f}]
"Enabled"=dword:00000001
"EnableFlags"=dword:ffffffff
"EnableLevel"=dword:00000004
"MatchAnyKeyword"=hex(b):00,00,00,00,00,00,00,00
"Status"=dword:00000000

```
</details></td>
</tr>
<tr>
<td>qcscm</td>
<td>SCMTraceGuid
SCM_ALL_INFO
TRACE_DRIVER</td>
<td>

```
BC491612-4CA5-4489-A3EA-8DDE1F3B268E
```
</td>
<td>

```
!wmitrace.enable meow BC491612-4CA5-4489-A3EA-8DDE1F3B268E -level 0xFF
```
</td>
<td>

```
!wmitrace.disable meow BC491612-4CA5-4489-A3EA-8DDE1F3B268E
```
</td>
<td><details>

```.reg
[HKEY_LOCAL_MACHINE\RTS\ControlSet001\Control\WMI\Autologger\QCOM\{BC491612-4CA5-4489-A3EA-8DDE1F3B268E}]
"Enabled"=dword:00000001
"EnableFlags"=dword:ffffffff
"EnableLevel"=dword:00000004
"MatchAnyKeyword"=hex(b):00,00,00,00,00,00,00,00
"Status"=dword:00000000

```
</details></td>
</tr>
<tr>
<td>qcsecapp</td>
<td>TzLogTrace</td>
<td>

```
AE845C3A-F5E0-47F5-AC22-C016E748DE3E
```
</td>
<td>

```
!wmitrace.enable meow AE845C3A-F5E0-47F5-AC22-C016E748DE3E -level 0xFF
```
</td>
<td>

```
!wmitrace.disable meow AE845C3A-F5E0-47F5-AC22-C016E748DE3E
```
</td>
<td><details>

```.reg
[HKEY_LOCAL_MACHINE\RTS\ControlSet001\Control\WMI\Autologger\QCOM\{AE845C3A-F5E0-47F5-AC22-C016E748DE3E}]
"Enabled"=dword:00000001
"EnableFlags"=dword:ffffffff
"EnableLevel"=dword:00000004
"MatchAnyKeyword"=hex(b):00,00,00,00,00,00,00,00
"Status"=dword:00000000

```
</details></td>
</tr>
<tr>
<td></td>
<td>QseeLogTrace</td>
<td>

```
BA5ED9BB-7FDF-4E48-8E29-B833734926D3
```
</td>
<td>

```
!wmitrace.enable meow BA5ED9BB-7FDF-4E48-8E29-B833734926D3 -level 0xFF
```
</td>
<td>

```
!wmitrace.disable meow BA5ED9BB-7FDF-4E48-8E29-B833734926D3
```
</td>
<td><details>

```.reg
[HKEY_LOCAL_MACHINE\RTS\ControlSet001\Control\WMI\Autologger\QCOM\{BA5ED9BB-7FDF-4E48-8E29-B833734926D3}]
"Enabled"=dword:00000001
"EnableFlags"=dword:ffffffff
"EnableLevel"=dword:00000004
"MatchAnyKeyword"=hex(b):00,00,00,00,00,00,00,00
"Status"=dword:00000000

```
</details></td>
</tr>
<tr>
<td></td>
<td>SecappTrace</td>
<td>

```
28AC3DC8-8BEF-44F4-9CCA-E7672225989A
```
</td>
<td>

```
!wmitrace.enable meow 28AC3DC8-8BEF-44F4-9CCA-E7672225989A -level 0xFF
```
</td>
<td>

```
!wmitrace.disable meow 28AC3DC8-8BEF-44F4-9CCA-E7672225989A
```
</td>
<td><details>

```.reg
[HKEY_LOCAL_MACHINE\RTS\ControlSet001\Control\WMI\Autologger\QCOM\{28AC3DC8-8BEF-44F4-9CCA-E7672225989A}]
"Enabled"=dword:00000001
"EnableFlags"=dword:ffffffff
"EnableLevel"=dword:00000004
"MatchAnyKeyword"=hex(b):00,00,00,00,00,00,00,00
"Status"=dword:00000000

```
</details></td>
</tr>
<tr>
<td>qcSensors</td>
<td>SensorsClxTraceGuid
DEBUG_SPEW
EntryExit</td>
<td>

```
44D2526D-EF8B-4336-B5E0-FBDB88CA10C0
```
</td>
<td>

```
!wmitrace.enable meow 44D2526D-EF8B-4336-B5E0-FBDB88CA10C0 -level 0xFF
```
</td>
<td>

```
!wmitrace.disable meow 44D2526D-EF8B-4336-B5E0-FBDB88CA10C0
```
</td>
<td><details>

```.reg
[HKEY_LOCAL_MACHINE\RTS\ControlSet001\Control\WMI\Autologger\QCOM\{44D2526D-EF8B-4336-B5E0-FBDB88CA10C0}]
"Enabled"=dword:00000001
"EnableFlags"=dword:ffffffff
"EnableLevel"=dword:00000004
"MatchAnyKeyword"=hex(b):00,00,00,00,00,00,00,00
"Status"=dword:00000000

```
</details></td>
</tr>
<tr>
<td>qcshutdownsvc</td>
<td>MyDriver1TraceGuid
Core</td>
<td>

```
de6c1d2d-861a-4248-a8f3-e236c4f16a19
```
</td>
<td>

```
!wmitrace.enable meow de6c1d2d-861a-4248-a8f3-e236c4f16a19 -level 0xFF
```
</td>
<td>

```
!wmitrace.disable meow de6c1d2d-861a-4248-a8f3-e236c4f16a19
```
</td>
<td><details>

```.reg
[HKEY_LOCAL_MACHINE\RTS\ControlSet001\Control\WMI\Autologger\QCOM\{de6c1d2d-861a-4248-a8f3-e236c4f16a19}]
"Enabled"=dword:00000001
"EnableFlags"=dword:ffffffff
"EnableLevel"=dword:00000004
"MatchAnyKeyword"=hex(b):00,00,00,00,00,00,00,00
"Status"=dword:00000000

```
</details></td>
</tr>
<tr>
<td>qcslimbus</td>
<td>SlimBusTraceGuid
CORE
TRACE_DRIVER</td>
<td>

```
C951B320-B923-4F26-A9BA-DA30550F2136
```
</td>
<td>

```
!wmitrace.enable meow C951B320-B923-4F26-A9BA-DA30550F2136 -level 0xFF
```
</td>
<td>

```
!wmitrace.disable meow C951B320-B923-4F26-A9BA-DA30550F2136
```
</td>
<td><details>

```.reg
[HKEY_LOCAL_MACHINE\RTS\ControlSet001\Control\WMI\Autologger\QCOM\{C951B320-B923-4F26-A9BA-DA30550F2136}]
"Enabled"=dword:00000001
"EnableFlags"=dword:ffffffff
"EnableLevel"=dword:00000004
"MatchAnyKeyword"=hex(b):00,00,00,00,00,00,00,00
"Status"=dword:00000000

```
</details></td>
</tr>
<tr>
<td>QcSOCPartition</td>
<td>QcSOCPartitionTraceGUID
QCSOCPARTITION_KMDF</td>
<td>

```
7637b3ab-0bb6-42d9-aa7a-ac32c0327991
```
</td>
<td>

```
!wmitrace.enable meow 7637b3ab-0bb6-42d9-aa7a-ac32c0327991 -level 0xFF
```
</td>
<td>

```
!wmitrace.disable meow 7637b3ab-0bb6-42d9-aa7a-ac32c0327991
```
</td>
<td><details>

```.reg
[HKEY_LOCAL_MACHINE\RTS\ControlSet001\Control\WMI\Autologger\QCOM\{7637b3ab-0bb6-42d9-aa7a-ac32c0327991}]
"Enabled"=dword:00000001
"EnableFlags"=dword:ffffffff
"EnableLevel"=dword:00000004
"MatchAnyKeyword"=hex(b):00,00,00,00,00,00,00,00
"Status"=dword:00000000

```
</details></td>
</tr>
<tr>
<td>qcspi</td>
<td>QualcommSpiTraceGuid
ERROR
WARNING</td>
<td>

```
CE0458F5-EE40-403A-AF35-A3E7FACC2BD0
```
</td>
<td>

```
!wmitrace.enable meow CE0458F5-EE40-403A-AF35-A3E7FACC2BD0 -level 0xFF
```
</td>
<td>

```
!wmitrace.disable meow CE0458F5-EE40-403A-AF35-A3E7FACC2BD0
```
</td>
<td><details>

```.reg
[HKEY_LOCAL_MACHINE\RTS\ControlSet001\Control\WMI\Autologger\QCOM\{CE0458F5-EE40-403A-AF35-A3E7FACC2BD0}]
"Enabled"=dword:00000001
"EnableFlags"=dword:ffffffff
"EnableLevel"=dword:00000004
"MatchAnyKeyword"=hex(b):00,00,00,00,00,00,00,00
"Status"=dword:00000000

```
</details></td>
</tr>
<tr>
<td>qcspmi</td>
<td>qcspmiTraceGuid
TRACE_CORE
TRACE_DRIVER</td>
<td>

```
c1de55d4-9831-472f-a17d-3500da9c7fa8
```
</td>
<td>

```
!wmitrace.enable meow c1de55d4-9831-472f-a17d-3500da9c7fa8 -level 0xFF
```
</td>
<td>

```
!wmitrace.disable meow c1de55d4-9831-472f-a17d-3500da9c7fa8
```
</td>
<td><details>

```.reg
[HKEY_LOCAL_MACHINE\RTS\ControlSet001\Control\WMI\Autologger\QCOM\{c1de55d4-9831-472f-a17d-3500da9c7fa8}]
"Enabled"=dword:00000001
"EnableFlags"=dword:ffffffff
"EnableLevel"=dword:00000004
"MatchAnyKeyword"=hex(b):00,00,00,00,00,00,00,00
"Status"=dword:00000000

```
</details></td>
</tr>
<tr>
<td>qcsubsys</td>
<td>SubSysTrace
EntryExit
SUBSYS</td>
<td>

```
8601DCB7-CA1A-48B7-91B4-E113B7D2A655
```
</td>
<td>

```
!wmitrace.enable meow 8601DCB7-CA1A-48B7-91B4-E113B7D2A655 -level 0xFF
```
</td>
<td>

```
!wmitrace.disable meow 8601DCB7-CA1A-48B7-91B4-E113B7D2A655
```
</td>
<td><details>

```.reg
[HKEY_LOCAL_MACHINE\RTS\ControlSet001\Control\WMI\Autologger\QCOM\{8601DCB7-CA1A-48B7-91B4-E113B7D2A655}]
"Enabled"=dword:00000001
"EnableFlags"=dword:ffffffff
"EnableLevel"=dword:00000004
"MatchAnyKeyword"=hex(b):00,00,00,00,00,00,00,00
"Status"=dword:00000000

```
</details></td>
</tr>
<tr>
<td>qcSubsysThermalMgr</td>
<td>SubsysThermalTrace</td>
<td>

```
32C8FBB2-B9E6-4403-9D5A-000A6652273F
```
</td>
<td>

```
!wmitrace.enable meow 32C8FBB2-B9E6-4403-9D5A-000A6652273F -level 0xFF
```
</td>
<td>

```
!wmitrace.disable meow 32C8FBB2-B9E6-4403-9D5A-000A6652273F
```
</td>
<td><details>

```.reg
[HKEY_LOCAL_MACHINE\RTS\ControlSet001\Control\WMI\Autologger\QCOM\{32C8FBB2-B9E6-4403-9D5A-000A6652273F}]
"Enabled"=dword:00000001
"EnableFlags"=dword:ffffffff
"EnableLevel"=dword:00000004
"MatchAnyKeyword"=hex(b):00,00,00,00,00,00,00,00
"Status"=dword:00000000

```
</details></td>
</tr>
<tr>
<td>qcsyscache</td>
<td>SmmuTrace
EntryExit
Core</td>
<td>

```
055E96F6-823F-4F94-8954-A12ABD1B339D
```
</td>
<td>

```
!wmitrace.enable meow 055E96F6-823F-4F94-8954-A12ABD1B339D -level 0xFF
```
</td>
<td>

```
!wmitrace.disable meow 055E96F6-823F-4F94-8954-A12ABD1B339D
```
</td>
<td><details>

```.reg
[HKEY_LOCAL_MACHINE\RTS\ControlSet001\Control\WMI\Autologger\QCOM\{055E96F6-823F-4F94-8954-A12ABD1B339D}]
"Enabled"=dword:00000001
"EnableFlags"=dword:ffffffff
"EnableLevel"=dword:00000004
"MatchAnyKeyword"=hex(b):00,00,00,00,00,00,00,00
"Status"=dword:00000000

```
</details></td>
</tr>
<tr>
<td>QcTftpKmdf</td>
<td>QCTFTPTraceGUID
QCTFTP_KMDF</td>
<td>

```
8cb2c430-3aa3-455e-a4c4-328719e67055
```
</td>
<td>

```
!wmitrace.enable meow 8cb2c430-3aa3-455e-a4c4-328719e67055 -level 0xFF
```
</td>
<td>

```
!wmitrace.disable meow 8cb2c430-3aa3-455e-a4c4-328719e67055
```
</td>
<td><details>

```.reg
[HKEY_LOCAL_MACHINE\RTS\ControlSet001\Control\WMI\Autologger\QCOM\{8cb2c430-3aa3-455e-a4c4-328719e67055}]
"Enabled"=dword:00000001
"EnableFlags"=dword:ffffffff
"EnableLevel"=dword:00000004
"MatchAnyKeyword"=hex(b):00,00,00,00,00,00,00,00
"Status"=dword:00000000

```
</details></td>
</tr>
<tr>
<td>QcTrEE</td>
<td>TrEETrace
DBG_TREE
DBG_LISTENER</td>
<td>

```
DE3B1201-A1DF-478A-9062-E443CDABF070
```
</td>
<td>

```
!wmitrace.enable meow DE3B1201-A1DF-478A-9062-E443CDABF070 -level 0xFF
```
</td>
<td>

```
!wmitrace.disable meow DE3B1201-A1DF-478A-9062-E443CDABF070
```
</td>
<td><details>

```.reg
[HKEY_LOCAL_MACHINE\RTS\ControlSet001\Control\WMI\Autologger\QCOM\{DE3B1201-A1DF-478A-9062-E443CDABF070}]
"Enabled"=dword:00000001
"EnableFlags"=dword:ffffffff
"EnableLevel"=dword:00000004
"MatchAnyKeyword"=hex(b):00,00,00,00,00,00,00,00
"Status"=dword:00000000

```
</details></td>
</tr>
<tr>
<td>qcuart</td>
<td>QualcommUartTraceGuid
ERROR
WARNING</td>
<td>

```
CE22E47E-2675-49C8-9D20-790BDACA429B
```
</td>
<td>

```
!wmitrace.enable meow CE22E47E-2675-49C8-9D20-790BDACA429B -level 0xFF
```
</td>
<td>

```
!wmitrace.disable meow CE22E47E-2675-49C8-9D20-790BDACA429B
```
</td>
<td><details>

```.reg
[HKEY_LOCAL_MACHINE\RTS\ControlSet001\Control\WMI\Autologger\QCOM\{CE22E47E-2675-49C8-9D20-790BDACA429B}]
"Enabled"=dword:00000001
"EnableFlags"=dword:ffffffff
"EnableLevel"=dword:00000004
"MatchAnyKeyword"=hex(b):00,00,00,00,00,00,00,00
"Status"=dword:00000000

```
</details></td>
</tr>
<tr>
<td>qcusbcucsi</td>
<td>QcUsbCTraceGuid
FuncTrace
DBG_INIT</td>
<td>

```
3168776E-0E5B-4B63-8F92-9D6C1B395166
```
</td>
<td>

```
!wmitrace.enable meow 3168776E-0E5B-4B63-8F92-9D6C1B395166 -level 0xFF
```
</td>
<td>

```
!wmitrace.disable meow 3168776E-0E5B-4B63-8F92-9D6C1B395166
```
</td>
<td><details>

```.reg
[HKEY_LOCAL_MACHINE\RTS\ControlSet001\Control\WMI\Autologger\QCOM\{3168776E-0E5B-4B63-8F92-9D6C1B395166}]
"Enabled"=dword:00000001
"EnableFlags"=dword:ffffffff
"EnableLevel"=dword:00000004
"MatchAnyKeyword"=hex(b):00,00,00,00,00,00,00,00
"Status"=dword:00000000

```
</details></td>
</tr>
<tr>
<td>QcUsbFnSsFilter</td>
<td>UsbFnSsTrace
FuncTrace
Core</td>
<td>

```
6FD2F1A8-C3D9-4A72-B122-30C6AD3E0A5F
```
</td>
<td>

```
!wmitrace.enable meow 6FD2F1A8-C3D9-4A72-B122-30C6AD3E0A5F -level 0xFF
```
</td>
<td>

```
!wmitrace.disable meow 6FD2F1A8-C3D9-4A72-B122-30C6AD3E0A5F
```
</td>
<td><details>

```.reg
[HKEY_LOCAL_MACHINE\RTS\ControlSet001\Control\WMI\Autologger\QCOM\{6FD2F1A8-C3D9-4A72-B122-30C6AD3E0A5F}]
"Enabled"=dword:00000001
"EnableFlags"=dword:ffffffff
"EnableLevel"=dword:00000004
"MatchAnyKeyword"=hex(b):00,00,00,00,00,00,00,00
"Status"=dword:00000000

```
</details></td>
</tr>
<tr>
<td>qcvidencarm64mfth264

qcvidencarm64mfthevc

qcvidencarm64xmfth264

qcvidencarm64xmfthevc

qcvidencmfth264

qcvidencmfthevc

qcvidencx86mfth264

qcvidencx86mfthevc</td>
<td>qveTrace
Low
Medium</td>
<td>

```
CEA35F95-03DB-4f70-A5C2-25E3ACA61E2A
```
</td>
<td>

```
!wmitrace.enable meow CEA35F95-03DB-4f70-A5C2-25E3ACA61E2A -level 0xFF
```
</td>
<td>

```
!wmitrace.disable meow CEA35F95-03DB-4f70-A5C2-25E3ACA61E2A
```
</td>
<td><details>

```.reg
[HKEY_LOCAL_MACHINE\RTS\ControlSet001\Control\WMI\Autologger\QCOM\{CEA35F95-03DB-4f70-A5C2-25E3ACA61E2A}]
"Enabled"=dword:00000001
"EnableFlags"=dword:ffffffff
"EnableLevel"=dword:00000004
"MatchAnyKeyword"=hex(b):00,00,00,00,00,00,00,00
"Status"=dword:00000000

```
</details></td>
</tr>
<tr>
<td>qcvidencarm64um

qcvidencarm64xum

qcvidencum

qcvidencx86um</td>
<td>qcvidencumTrace
Low
Medium</td>
<td>

```
F805AFCE-F65F-4F5E-9B6D-6AC067876850
```
</td>
<td>

```
!wmitrace.enable meow F805AFCE-F65F-4F5E-9B6D-6AC067876850 -level 0xFF
```
</td>
<td>

```
!wmitrace.disable meow F805AFCE-F65F-4F5E-9B6D-6AC067876850
```
</td>
<td><details>

```.reg
[HKEY_LOCAL_MACHINE\RTS\ControlSet001\Control\WMI\Autologger\QCOM\{F805AFCE-F65F-4F5E-9B6D-6AC067876850}]
"Enabled"=dword:00000001
"EnableFlags"=dword:ffffffff
"EnableLevel"=dword:00000004
"MatchAnyKeyword"=hex(b):00,00,00,00,00,00,00,00
"Status"=dword:00000000

```
</details></td>
</tr>
<tr>
<td>qcWlanSleepMgr</td>
<td>Ctl</td>
<td>

```
435bb1ca-51ea-407f-9899-85da4c2d7f0e
```
</td>
<td>

```
!wmitrace.enable meow 435bb1ca-51ea-407f-9899-85da4c2d7f0e -level 0xFF
```
</td>
<td>

```
!wmitrace.disable meow 435bb1ca-51ea-407f-9899-85da4c2d7f0e
```
</td>
<td><details>

```.reg
[HKEY_LOCAL_MACHINE\RTS\ControlSet001\Control\WMI\Autologger\QCOM\{435bb1ca-51ea-407f-9899-85da4c2d7f0e}]
"Enabled"=dword:00000001
"EnableFlags"=dword:ffffffff
"EnableLevel"=dword:00000004
"MatchAnyKeyword"=hex(b):00,00,00,00,00,00,00,00
"Status"=dword:00000000

```
</details></td>
</tr>
<tr>
<td>QcXhciFilter</td>
<td>XhciTrace
FuncTrace
Core</td>
<td>

```
11ED5F0A-0200-42AF-B5DF-B8BEC02C9624
```
</td>
<td>

```
!wmitrace.enable meow 11ED5F0A-0200-42AF-B5DF-B8BEC02C9624 -level 0xFF
```
</td>
<td>

```
!wmitrace.disable meow 11ED5F0A-0200-42AF-B5DF-B8BEC02C9624
```
</td>
<td><details>

```.reg
[HKEY_LOCAL_MACHINE\RTS\ControlSet001\Control\WMI\Autologger\QCOM\{11ED5F0A-0200-42AF-B5DF-B8BEC02C9624}]
"Enabled"=dword:00000001
"EnableFlags"=dword:ffffffff
"EnableLevel"=dword:00000004
"MatchAnyKeyword"=hex(b):00,00,00,00,00,00,00,00
"Status"=dword:00000000

```
</details></td>
</tr>
<tr>
<td>qSarMgr</td>
<td>qsarMgrTraceGuid
TRACE_SARMGR
→</td>
<td>

```
ba8b8ca7-ad28-4983-967c-6fd34c36acf8
```
</td>
<td>

```
!wmitrace.enable meow ba8b8ca7-ad28-4983-967c-6fd34c36acf8 -level 0xFF
```
</td>
<td>

```
!wmitrace.disable meow ba8b8ca7-ad28-4983-967c-6fd34c36acf8
```
</td>
<td><details>

```.reg
[HKEY_LOCAL_MACHINE\RTS\ControlSet001\Control\WMI\Autologger\QCOM\{ba8b8ca7-ad28-4983-967c-6fd34c36acf8}]
"Enabled"=dword:00000001
"EnableFlags"=dword:ffffffff
"EnableLevel"=dword:00000004
"MatchAnyKeyword"=hex(b):00,00,00,00,00,00,00,00
"Status"=dword:00000000

```
</details></td>
</tr>
<tr>
<td>ufnserialclass</td>
<td>UfnSerialClassTraceGuid
DBG_INIT
DBG_PNP</td>
<td>

```
D5393B53-8AAE-40B1-938B-C207E999605F
```
</td>
<td>

```
!wmitrace.enable meow D5393B53-8AAE-40B1-938B-C207E999605F -level 0xFF
```
</td>
<td>

```
!wmitrace.disable meow D5393B53-8AAE-40B1-938B-C207E999605F
```
</td>
<td><details>

```.reg
[HKEY_LOCAL_MACHINE\RTS\ControlSet001\Control\WMI\Autologger\QCOM\{D5393B53-8AAE-40B1-938B-C207E999605F}]
"Enabled"=dword:00000001
"EnableFlags"=dword:ffffffff
"EnableLevel"=dword:00000004
"MatchAnyKeyword"=hex(b):00,00,00,00,00,00,00,00
"Status"=dword:00000000

```
</details></td>
</tr>

</table>

---
