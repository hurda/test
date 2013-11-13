
;=============================================================================
;
; Copyright (c) Intel Corporation (2009).
;
; INTEL MAKES NO WARRANTY OF ANY KIND REGARDING THE CODE.  THIS CODE IS
; LICENSED ON AN "AS IS" BASIS AND INTEL WILL NOT PROVIDE ANY SUPPORT,
; ASSISTANCE, INSTALLATION, TRAINING OR OTHER SERVICES.  INTEL DOES NOT
; PROVIDE ANY UPDATES, ENHANCEMENTS OR EXTENSIONS.  INTEL SPECIFICALLY
; DISCLAIMS ANY WARRANTY OF MERCHANTABILITY, NONINFRINGEMENT, FITNESS FOR ANY
; PARTICULAR PURPOSE, OR ANY OTHER WARRANTY.  Intel disclaims all liability,
; including liability for infringement of any proprietary rights, relating to
; use of the code. No license, express or implied, by estoppel or otherwise,
; to any intellectual property rights is granted herein.
;
;=============================================================================

; Installation inf for the Intel Corporation graphics adapter.

[Version]
Signature="$WINDOWS NT$"
Provider=%Intel%
ClassGUID={4D36E968-E325-11CE-BFC1-08002BE10318}
Class=Display
CatalogFile=kit51428.cat

DriverVer=01/30/2013,8.15.10.2993

;
; Package Info for Co-Installer
;

[PackageInfo]
Name=Graphics
INFSource=%1%

[DestinationDirs]
DefaultDestDir      = 11  ; system32
igfx.Miniport       = 12  ; drivers
igfx.UserMode       = 11  ; system32
MedKrnG575.Copy     = 11  ; system32
MedKrnG575.Copy32   = 10, SysWow64
MedKrnG600.Copy     = 11  ; system32
MedKrnG600.Copy32   = 10, SysWow64
igfx.UMWow          = 10, SysWow64
Installer_Copy      = 11  ; system32

CUI.Copy            = 11  ; system32
Resource.Copy       = 11  ; copy the resource files
CUISDK.Copy         = 11  ; system32
CUISDK.Copy32   = 10, SysWow64

OpenGL.Copy   	    = 11  ; OpenGL Drivers in System32
OpenGL.Copy32	    = 10, SysWow64

DDE.Copy     = 11  ; system32
DDE.Copy32   = 10, SysWow64

;
; Driver information
;

[Manufacturer]
%Intel%   = IntelGfx, NTamd64.5.1, NTamd64.6.0, NTamd64.6.2 

[IntelGfx.NTamd64.5.1]
; no install on XP

[IntelGfx.NTamd64.6.2]
; no install on Win8

[IntelGfx.NTamd64.6.0]
%iILKGM0% = iILKM0, PCI\VEN_8086&DEV_0046
%iILKG0% = iILKD0, PCI\VEN_8086&DEV_0042

;
; General installation section
;
[iILKM0]
FeatureScore=E6
CopyFiles=igfx.Miniport, igfx.UserMode, MedKrnG575.Copy, MedKrnG575.Copy32, Opm.Copy, igfx.UMWow, Installer_Copy , CUI.Copy , CUISDK.Copy , CUISDK.Copy32 , Resource.Copy , OpenGL.Copy , OpenGL.Copy32
AddReg = igfx_SoftwareDX10Settings
AddReg = igfx_SoftwareCommonSettings
DelReg  = igfx_RemoveDeviceSettings

AddReg = CUI.AddReg
AddReg = CUISDK.AddReg

DelReg  = CUI.DelReg
DelReg  = CUISDK.DelReg

AddReg = OpenGL.AddReg , OpenGL.AddRegSmch.ILK

AddReg = OEMStaticMode_AddSwSettings
DelReg  = OEMStaticMode_DelSwSettings
AddReg = HotPlug_AddSwSettings
DelReg  = HotPlug_DelSwSettings
AddReg = General_AddSwSettings
DelReg  = General_DelSwSettings
AddReg = Underscan_AddSwSettings
DelReg  = Underscan_DelSwSettings
AddReg = PwrCons_ILK_AddSwSettings
DelReg  = PwrCons_ILK_DelSwSettings
AddReg = PwrCons_DPS_AddSwSettings
DelReg  = PwrCons_DPS_DelSwSettings
AddReg = SDVOHDMI_VSI_AddSwSettings
DelReg  = SDVOHDMI_VSI_DelSwSettings
AddReg = NonEDIDMode_AddSwSettings
DelReg  = NonEDIDMode_DelSwSettings
AddReg = DynamicScaling_AddSwSettings
DelReg  = DynamicScaling_DelSwSettings
AddReg = CRTHotPlugDefaultVrefVoltage_AddSwSettings
DelReg  = CRTHotPlugDefaultVrefVoltage_DelSwSettings
AddReg = MediaSrcMode_AddSwSettings
DelReg  = MediaSrcMode_DelSwSettings
AddReg = MediaScaling_AddSwSettings
DelReg  = MediaScaling_DelSwSettings
AddReg = HDMICEATimings_AddSwSettings
DelReg  = HDMICEATimings_DelSwSettings
AddReg = SdvoDdcEdidRead_AddSwSettings
DelReg  = SdvoDdcEdidRead_DelSwSettings
AddReg = AsyncFlips_AddSwSettings
DelReg  = AsyncFlips_DelSwSettings
AddReg = DelayedDetectionForDP_AddSwSettings
DelReg  = DelayedDetectionForDP_DelSwSettings
AddReg = DelayedDetectionForHDMI_AddSwSettings
DelReg  = DelayedDetectionForHDMI_DelSwSettings
AddReg = EnableInterlacedModeRemoval_AddSwSettings
DelReg  = EnableInterlacedModeRemoval_DelSwSettings
AddReg = ForceBorderForMAR_AddSwSettings
DelReg  = ForceBorderForMAR_DelSwSettings
AddReg = Gen6IntLVDSSwing_AddSwSettings
DelReg  = Gen6IntLVDSSwing_DelSwSettings
AddReg = INFHotPlug_AddSwSettings
DelReg  = INFHotPlug_DelSwSettings
AddReg = INFVBTOverride_AddSwSettings
DelReg  = INFVBTOverride_DelSwSettings
AddReg = CRTScaler_AddSwSettings
DelReg  = CRTScaler_DelSwSettings
AddReg = IncFixedSegWA_AddSwSettings
DelReg  = IncFixedSegWA_DelSwSettings
AddReg = igfx_TPV_AddSwSettings
DelReg  = igfx_TPV_DelSwSettings
AddReg = RedBlankingPnl_AddSwSettings
DelReg  = RedBlankingPnl_DelSwSettings
AddReg = PNM_AddSwSettings
DelReg  = PNM_DelSwSettings
AddReg = EnableHDMIUnderScan_AddSwSettings
DelReg  = EnableHDMIUnderScan_DelSwSettings
AddReg = BitBashingSupport_AddSwSettings
DelReg  = BitBashingSupport_DelSwSettings
AddReg = BitBashingForHDCP_AddSwSettings
DelReg  = BitBashingForHDCP_DelSwSettings
AddReg = PanelFitterOnDP_AddSwSettings
DelReg  = PanelFitterOnDP_DelSwSettings
AddReg = XVYCCFeatture_AddSwSettings
DelReg  = XVYCCFeatture_DelSwSettings
AddReg = DeepColorHDMI_AddSwSettings
DelReg  = DeepColorHDMI_DelSwSettings
AddReg = WGFeature_AddSwSettings
DelReg = WGFeature_DelSwSettings
AddReg = MediaRefreshRateMode_AddSwSettings
DelReg  = MediaRefreshRateMode_DelSwSettings
AddReg = ILKM_MBMSettings_AddSwSettings
DelReg  = ILKM_MBMSettings_DelSwSettings
AddReg = eDPNoFLT_AddSwSettings
DelReg = eDPNoFLT_DelSwSettings
AddReg = DynamicClockGating_AddSwSettings
DelReg = DynamicClockGating_DelSwSettings
AddReg = PdTogglingTimer_AddSwSettings
DelReg = PdTogglingTimer_DelSwSettings
AddReg = EnableEccMemoryTileX_WA_ILK_AddSwSettings
DelReg = EnableEccMemoryTileX_WA_ILK_DelSwSettings
RegisterDLLs = igfx_RegisterDLLs

AddPowerSetting = PowerPlanSettings

[iILKM0.HW]
AddReg = igfx_MSI_HardwareDeviceSettings

[iILKD0]
FeatureScore=E6
CopyFiles=igfx.Miniport, igfx.UserMode, MedKrnG575.Copy, MedKrnG575.Copy32, Opm.Copy, igfx.UMWow, Installer_Copy , CUI.Copy , CUISDK.Copy , CUISDK.Copy32 , Resource.Copy , OpenGL.Copy , OpenGL.Copy32
AddReg =  igfx_SoftwareDX10Settings
AddReg =  igfx_SoftwareCommonSettings
DelReg =   igfx_RemoveDeviceSettings

AddReg = CUI.AddReg
AddReg = CUISDK.AddReg

DelReg  = CUI.DelReg
DelReg  = CUISDK.DelReg

AddReg = OpenGL.AddReg , OpenGL.AddRegSmch.ILK

AddReg =  OEMStaticMode_AddSwSettings
DelReg  =  OEMStaticMode_DelSwSettings
AddReg =  HotPlug_AddSwSettings
DelReg  =  HotPlug_DelSwSettings
AddReg =  Underscan_AddSwSettings
DelReg  =  Underscan_DelSwSettings
AddReg = PwrCons_ILK_AddSwSettings
DelReg  = PwrCons_ILK_DelSwSettings
AddReg =  SDVOHDMI_VSI_AddSwSettings
DelReg  =  SDVOHDMI_VSI_DelSwSettings
AddReg =  NonEDIDMode_AddSwSettings
DelReg  =  NonEDIDMode_DelSwSettings
AddReg =  DynamicScaling_AddSwSettings
DelReg  =  DynamicScaling_DelSwSettings
AddReg =  CRTHotPlugDefaultVrefVoltage_AddSwSettings
DelReg  =  CRTHotPlugDefaultVrefVoltage_DelSwSettings
AddReg =  MediaSrcMode_AddSwSettings
DelReg  =  MediaSrcMode_DelSwSettings
AddReg =  MediaScaling_AddSwSettings
DelReg  =  MediaScaling_DelSwSettings
AddReg =  HDMICEATimings_AddSwSettings
DelReg  =  HDMICEATimings_DelSwSettings
AddReg =  SdvoDdcEdidRead_AddSwSettings
DelReg  =  SdvoDdcEdidRead_DelSwSettings
AddReg =  AsyncFlips_AddSwSettings
DelReg  =  AsyncFlips_DelSwSettings
AddReg = DelayedDetectionForDP_AddSwSettings
DelReg  = DelayedDetectionForDP_DelSwSettings
AddReg = DelayedDetectionForHDMI_AddSwSettings
DelReg  = DelayedDetectionForHDMI_DelSwSettings
AddReg =  EnableInterlacedModeRemoval_AddSwSettings
DelReg  =  EnableInterlacedModeRemoval_DelSwSettings
AddReg =  ForceBorderForMAR_AddSwSettings
DelReg  =  ForceBorderForMAR_DelSwSettings
AddReg =  CRTScaler_AddSwSettings
DelReg  =  CRTScaler_DelSwSettings
AddReg = EnableHDMIUnderScan_AddSwSettings
DelReg  = EnableHDMIUnderScan_DelSwSettings
AddReg =  IncFixedSegWA_AddSwSettings
DelReg  =  IncFixedSegWA_DelSwSettings
AddReg =  igfx_TPV_AddSwSettings
DelReg  =  igfx_TPV_DelSwSettings
AddReg =  BitBashingSupport_AddSwSettings
DelReg  =  BitBashingSupport_DelSwSettings
AddReg =  BitBashingForHDCP_AddSwSettings
DelReg  =  BitBashingForHDCP_DelSwSettings
AddReg =  PanelFitterOnDP_AddSwSettings
DelReg  =  PanelFitterOnDP_DelSwSettings
AddReg = XVYCCFeatture_AddSwSettings
DelReg  = XVYCCFeatture_DelSwSettings
AddReg = DeepColorHDMI_AddSwSettings
DelReg  = DeepColorHDMI_DelSwSettings
AddReg = WGFeature_AddSwSettings
DelReg = WGFeature_DelSwSettings
AddReg =  InternalScaler_AddSwSettings
DelReg  =  InternalScaler_DelSwSettings
AddReg =  UseEDIDTimingForCRTClone_AddSwSettings
DelReg  =  UseEDIDTimingForCRTClone_DelSwSettings
AddReg =  MediaRefreshRateMode_AddSwSettings
DelReg  =  MediaRefreshRateMode_DelSwSettings
AddReg = eDPNoFLT_AddSwSettings
DelReg = eDPNoFLT_DelSwSettings
AddReg = DynamicClockGating_AddSwSettings
DelReg = DynamicClockGating_DelSwSettings
AddReg = PdTogglingTimer_AddSwSettings
DelReg = PdTogglingTimer_DelSwSettings
AddReg = EnableEccMemoryTileX_WA_ILK_AddSwSettings
DelReg = EnableEccMemoryTileX_WA_ILK_DelSwSettings
RegisterDLLs = igfx_RegisterDLLs

[iILKD0.HW]
AddReg = igfx_MSI_HardwareDeviceSettings

[iILKM0.CoInstallers]
AddReg = CoInst.AddReg
CopyFiles = CoInst.CopyFiles

[iILKD0.CoInstallers]
AddReg = CoInst.AddReg
CopyFiles = CoInst.CopyFiles

[CoInst.AddReg]
HKR,, CoInstallers32, %REG_MULTI_SZ%, "igfxCoIn_v2993.dll, CoDeviceInstall"

[CoInst.CopyFiles]
igfxCoIn_v2993.dll,igxpco64.dll,,0x00000010

;
; File sections
;
[CUI.DelFiles]
igfxres.dll,,,1

[igfx.Miniport]
igdkmd64.sys

[igfx.UserMode]
igdumd64.dll,,,0x00004000  ; COPYFLG_IN_USE_TRY_RENAME

igd10umd64.dll,,,0x00004000  ; COPYFLG_IN_USE_TRY_RENAME

igfxcmrt64.dll,,,0x00004000  ; COPYFLG_IN_USE_TRY_RENAME
igfxcmjit64.dll,,,0x00004000  ; COPYFLG_IN_USE_TRY_RENAME
IccLibDll_x64.dll,,,0x00004000  ; COPYFLG_IN_USE_TRY_RENAME

[Opm.Copy]
iglhxs64.vp
iglhxo64.vp
iglhxc64.vp
iglhxg64.vp
iglhxa64.vp
iglhxa64.cpa
iglhcp64.dll
iglhsip64.dll

[MedKrnG575.Copy]
igkrng575.bin,,,0x00004000  ; COPYFLG_IN_USE_TRY_RENAME
igcompkrng575.bin,,,0x00004000  ; COPYFLG_IN_USE_TRY_RENAME
igfcg575m.bin,,,0x00004000  ; COPYFLG_IN_USE_TRY_RENAME

[MedKrnG575.Copy32]
igkrng575.bin,,,0x00004000  ; COPYFLG_IN_USE_TRY_RENAME
igcompkrng575.bin,,,0x00004000  ; COPYFLG_IN_USE_TRY_RENAME
igfcg575m.bin,,,0x00004000  ; COPYFLG_IN_USE_TRY_RENAME

[MedKrnG600.Copy]
igkrng600.bin,,,0x00004000  ; COPYFLG_IN_USE_TRY_RENAME
igcompkrng600.bin,,,0x00004000  ; COPYFLG_IN_USE_TRY_RENAME
igfcg600m.bin,,,0x00004000  ; COPYFLG_IN_USE_TRY_RENAME

[MedKrnG600.Copy32]
igkrng600.bin,,,0x00004000  ; COPYFLG_IN_USE_TRY_RENAME
igcompkrng600.bin,,,0x00004000  ; COPYFLG_IN_USE_TRY_RENAME
igfcg600m.bin,,,0x00004000  ; COPYFLG_IN_USE_TRY_RENAME

[Installer_Copy]
difx64.exe

[igfx.UMWow]
igdumd32.dll,,,0x00004000	; COPYFLG_IN_USE_TRY_RENAME

igdumdx32.dll,,,0x00004000      ; COPYFLG_IN_USE_TRY_RENAME

igfxdv32.dll,,,0x00004000	; COPYFLG_IN_USE_TRY_RENAME

igd10umd32.dll,,,0x00004000  ; COPYFLG_IN_USE_TRY_RENAME

iglhcp32.dll,,,0x00004000	; COPYFLG_IN_USE_TRY_RENAME
iglhsip32.dll,,,0x00004000	; COPYFLG_IN_USE_TRY_RENAME
igfxcmrt32.dll,,,0x00004000	; COPYFLG_IN_USE_TRY_RENAME
igfxcmjit32.dll,,,0x00004000	; COPYFLG_IN_USE_TRY_RENAME

[DDE.Copy]
igdde64.dll,,,0x00004000  ; COPYFLG_IN_USE_TRY_RENAME

[DDE.Copy32]
igdde32.dll,,,0x00004000  ; COPYFLG_IN_USE_TRY_RENAME

;
; Start CUI Copy Sections
;
[CUI.Copy]
hccutils.dll,,,0x00004000  ; COPYFLG_IN_USE_TRY_RENAME
igfxsrvc.dll,,,0x00004000  ; COPYFLG_IN_USE_TRY_RENAME
igfxsrvc.exe
igfxpph.dll,,,0x00004000  ; COPYFLG_IN_USE_TRY_RENAME
igfxcpl.cpl
igfxdev.dll,,,0x00004000  ; COPYFLG_IN_USE_TRY_RENAME
igfxdo.dll,,,0x00004000  ; COPYFLG_IN_USE_TRY_RENAME
igfxtray.exe
hkcmd.exe
igfxress.dll,,,0x00004000  ; COPYFLG_IN_USE_TRY_RENAME	     ; Generic language resource file
igfxpers.exe
igfxTMM.dll,,,0x00004000  ; COPYFLG_IN_USE_TRY_RENAME
gfxSrvc.dll,,,0x00004000  ; COPYFLG_IN_USE_TRY_RENAME
GfxUI.exe
GfxUI.exe.config
IGFXDEVLib.dll,,,0x00004000  ; COPYFLG_IN_USE_TRY_RENAME

[CUISDK.Copy]
igfxext.exe	; CUI SDK
igfxexps.dll,,,0x00004000  ; COPYFLG_IN_USE_TRY_RENAME  ; CUI SDK proxy stub

[CUISDK.Copy32]
igfxexps32.dll,,,0x00004000  ; COPYFLG_IN_USE_TRY_RENAME  ; CUI SDK proxy stub for WOW

[Resource.Copy]
; Language Resource files
igfxrara.lrc     ; Arabic 
igfxrchs.lrc    ; Simplified Chinese 
igfxrcht.lrc     ; Traditional Chinese 
igfxrdan.lrc    ; Danish 
igfxrdeu.lrc    ; German 
igfxrenu.lrc    ; American English 
igfxresn.lrc    ; Spanish 
igfxrfin.lrc     ; Finish 
igfxrfra.lrc     ; French 
igfxrheb.lrc    ; Hebrew 
igfxrhrv.lrc    ; Croatian 
igfxrita.lrc     ; Italian 
igfxrjpn.lrc    ; Japanese 
igfxrkor.lrc    ; Korean 
igfxrnld.lrc    ; Netherland 
igfxrnor.lrc    ; Norwegian 
igfxrplk.lrc    ; Polish 
igfxrptb.lrc    ; Brazilian Portuguese 
igfxrptg.lrc    ; Portuguese 
igfxrrom.lrc   ; Romanian 
igfxrrus.lrc    ; Russian 
igfxrsky.lrc    ; Slovakian 
igfxrslv.lrc     ; Slovenian 
igfxrsve.lrc    ; Swedish 
igfxrtha.lrc    ; Thai 
igfxrcsy.lrc    ; Czechoslovakian 
igfxrell.lrc     ; Greek 
igfxrhun.lrc   ; Hungarian 
igfxrtrk.lrc    ; Turkish 
Gfxres.ar-SA.resources 
Gfxres.cs-CZ.resources 
Gfxres.da-DK.resources 
Gfxres.de-DE.resources 
Gfxres.el-GR.resources 
Gfxres.es-ES.resources 
Gfxres.en-US.resources 
Gfxres.fi-FI.resources 
Gfxres.fr-FR.resources 
Gfxres.he-IL.resources
Gfxres.hr-HR.resources
Gfxres.hu-HU.resources 
Gfxres.it-IT.resources 
Gfxres.ja-JP.resources 
Gfxres.ko-KR.resources 
Gfxres.nb-NO.resources 
Gfxres.nl-NL.resources 
Gfxres.pl-PL.resources 
Gfxres.pt-BR.resources 
Gfxres.pt-PT.resources
Gfxres.ro-RO.resources 
Gfxres.ru-RU.resources 
Gfxres.sk-SK.resources 
Gfxres.sl-SI.resources 
Gfxres.sv-SE.resources 
Gfxres.th-TH.resources 
Gfxres.tr-TR.resources 
Gfxres.zh-CN.resources 
Gfxres.zh-TW.resources  
;
; End CUI Copy Sections
; 

[OpenGL.Copy]
ig4icd64.dll,,,0x00004000  ; COPYFLG_IN_USE_TRY_RENAME

[OpenGL.Copy32]
ig4icd32.dll,,,0x00004000  ; COPYFLG_IN_USE_TRY_RENAME

[OpenGL.AddReg]
HKR,, OpenGLDriverName,         %REG_MULTI_SZ%, ig4icd64.dll
HKR,, OpenGLVersion,            %REG_DWORD%,    1
HKR,, OpenGLFlags,              %REG_DWORD%,    3
HKR,, OpenGLDriverNameWow,      %REG_MULTI_SZ%, ig4icd32.dll
HKR,, OpenGLVersionWow,         %REG_DWORD%,    1
HKR,, OpenGLFlagsWow,           %REG_DWORD%,    3

[OpenGL.AddRegSmch.ILK]
HKR,, _oglapp_etqw.exe, %REG_DWORD%, 0x00000001
HKR,, _oglapp_cinebench r10.exe, %REG_DWORD%, 0x00000001
HKR,, _oglapp_cinebench r10 64bit.exe, %REG_DWORD%, 0x00000001
HKR,, _oglapp_Viewperf.exe, %REG_DWORD%, 0x00000008
HKR,, @Minecraft, %REG_DWORD%, 0x00000001
HKR,, _oglapp_CNEXT.exe, %REG_DWORD%, 0x00000080
HKR,, _oglapp_DMU.exe, %REG_DWORD%, 0x00000080

[OpenGL.DelRegSmch]
HKR,, _oglapp_etqw.exe
HKR,, _oglapp_cinebench r10.exe
HKR,, _oglapp_cinebench r10 64bit.exe
HKR,, _oglapp_UT2004.exe
HKR,, _oglapp_CM09OGL.exe
HKR,, _oglapp_Photoshop.exe
HKR,, _oglapp_Viewperf.exe
HKR,, _oglapp_FJVPS.exe
HKR,, @Minecraft
HKR,, _oglapp_CNEXT.exe
HKR,, _oglapp_DMU.exe

[igfx_RegisterDLLs]
11,,igdumd32.dll,1

11,,igdumdx32.dll,1

11,,igdumd64.dll,1

11,,igd10umd32.dll,1
11,,igd10umd64.dll,1

11,,hccutils.dll,1
11,,igfxsrvc.dll,1
11,,gfxSrvc.dll,1
11,,igfxpph.dll,1
11,,igfxdev.dll,1
11,,igfxdo.dll,1
11,,igfxress.dll,1
11,,igfxTMM.dll,1
;11,,igfxexps.dll,1

11,,ig4icd32.dll,1
11,,ig4icd64.dll,1

[CUI.DelReg]
HKLM,%CUIDeviceIndependentKey%
HKLM,%DisplayKey%
; Delete old style cui/driver share key
HKLM,%CUIDriverOldShareKey%
; Delete old style cui keys which are device dependent
HKLM,Software\INTEL\igfxcui
HKR,igfxdiag
HKR,igfxeud
HKR,igfxcfg
HKR,igfxcpl
HKR,igfxpph
HKR,igfxsrvc
HKR,igfxhk
HKR,hkcmd
HKR,igfxtray
HKR,shellex\PropertySheetHandlers
HKR,, Display1_EnableLFPPrimaryInDDC
;
; Delete the CUI registry entry which registers for winlogon events
;
HKLM,"SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon\Notify\igfxcui"

;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;

;CUIService

HKCR,"igfx.CUIService\CLSID"
HKCR,"igfx.CUIService\CurVer"
HKCR,"igfx.CUIService"
HKCR,"igfx.CUIService.1\CLSID"
HKCR,"igfx.CUIService.1"
HKCR,"CLSID\{0F195FA1-CCF0-11D2-8B20-00A0C93CB1F4}\InProcServer32\ThreadingModel"
HKCR,"CLSID\{0F195FA1-CCF0-11D2-8B20-00A0C93CB1F4}\InProcServer32"
HKCR,"CLSID\{0F195FA1-CCF0-11D2-8B20-00A0C93CB1F4}\ProgID"
HKCR,"CLSID\{0F195FA1-CCF0-11D2-8B20-00A0C93CB1F4}\Programmable"
HKCR,"CLSID\{0F195FA1-CCF0-11D2-8B20-00A0C93CB1F4}\VersionIndependentProgID"
HKCR,"CLSID\{0F195FA1-CCF0-11D2-8B20-00A0C93CB1F4}"

;CUITestConfig

HKCR,"igfx.CUITestConfig\CLSID"
HKCR,"igfx.CUITestConfig\CurVer"
HKCR,"igfx.CUITestConfig"
HKCR,"igfx.CUITestConfig.1\CLSID"
HKCR,"igfx.CUITestConfig.1"
HKCR,"CLSID\{97DC3661-693D-11d4-B561-00A0C92E6848}\InProcServer32\ThreadingModel"
HKCR,"CLSID\{97DC3661-693D-11d4-B561-00A0C92E6848}\InProcServer32"
HKCR,"CLSID\{97DC3661-693D-11d4-B561-00A0C92E6848}\ProgID"
HKCR,"CLSID\{97DC3661-693D-11d4-B561-00A0C92E6848}\Programmable"
HKCR,"CLSID\{97DC3661-693D-11d4-B561-00A0C92E6848}\VersionIndependentProgID"
HKCR,"CLSID\{97DC3661-693D-11d4-B561-00A0C92E6848}"

;igfxeud.EndUserShellExt

HKCR,"igfxeud.EndUserShellExt\CLSID"
HKCR,"igfxeud.EndUserShellExt\CurVer"
HKCR,"igfxeud.EndUserShellExt"
HKCR,"igfxeud.EndUserShellExt.1"
HKCR,"igfxeud.EndUserShellExt.1\CLSID"
HKCR,"CLSID\{3AB167A5-CCFF-11D2-8B20-00A0C93CB1F4}\InProcServer32\ThreadingModel"
HKCR,"CLSID\{3AB167A5-CCFF-11D2-8B20-00A0C93CB1F4}\InProcServer32"
HKCR,"CLSID\{3AB167A5-CCFF-11D2-8B20-00A0C93CB1F4}\ProgID"
HKCR,"CLSID\{3AB167A5-CCFF-11D2-8B20-00A0C93CB1F4}\Programmable"
HKCR,"CLSID\{3AB167A5-CCFF-11D2-8B20-00A0C93CB1F4}\VersionIndependentProgID"
HKCR,"CLSID\{3AB167A5-CCFF-11D2-8B20-00A0C93CB1F4}"

;igfxdiag.DiagServices

HKCR,"igfx.DiagServices\CLSID"
HKCR,"igfx.DiagServices\CurVer"
HKCR,"igfx.DiagServices"
HKCR,"igfx.DiagServices.1\CLSID"
HKCR,"igfx.DiagServices.1"
HKCR,"CLSID\{0EF91A8E-03D5-11D3-B995-00A0C9AD54B5}\LocalServer32"
HKCR,"CLSID\{0EF91A8E-03D5-11D3-B995-00A0C9AD54B5}\ProgID"
HKCR,"CLSID\{0EF91A8E-03D5-11D3-B995-00A0C9AD54B5}\VersionIndependentProgID"
HKCR,"CLSID\{0EF91A8E-03D5-11D3-B995-00A0C9AD54B5}"

;igfxdiag.ICUIAGP

HKCR, "Interface\{E0BA4EE2-03D5-11d3-B995-00A0C9AD54B5}\NumMethods"
HKCR, "Interface\{E0BA4EE2-03D5-11d3-B995-00A0C9AD54B5}\ProxyStubClsid32"
HKCR, "Interface\{E0BA4EE2-03D5-11d3-B995-00A0C9AD54B5}"

;igfxdiag.ICUIDiagController

HKCR,"Interface\{48E57D01-53BD-11D3-8EE0-00A0C984F371}\NumMethods"
HKCR,"Interface\{48E57D01-53BD-11D3-8EE0-00A0C984F371}\ProxyStubClsid32"
HKCR,"Interface\{48E57D01-53BD-11D3-8EE0-00A0C984F371}"

;igfxdiag.ICUIDriverInfo

HKCR, "Interface\{C562A581-4989-11D3-8EE0-00A0C984F371}\ProxyStubClsid32"
HKCR, "Interface\{C562A581-4989-11D3-8EE0-00A0C984F371}\NumMethods"
HKCR, "Interface\{C562A581-4989-11D3-8EE0-00A0C984F371}"

;igfxdiag.ICUIMonitor

HKCR,"Interface\{E0BA4EE3-03D5-11D3-B995-00A0C9AD54B5}\NumMethods"
HKCR,"Interface\{E0BA4EE3-03D5-11D3-B995-00A0C9AD54B5}ProxyStubClsid32"
HKCR,"Interface\{E0BA4EE3-03D5-11D3-B995-00A0C9AD54B5}"

;igfxdiag.ICUIMonitor2

HKCR,"Interface\{7D8A8461-25C2-11D4-ACA5-00A0C9AD5629}\ProxyStubClsid32"
HKCR,"Interface\{7D8A8461-25C2-11D4-ACA5-00A0C9AD5629}\NumMethods"
HKCR,"Interface\{7D8A8461-25C2-11D4-ACA5-00A0C9AD5629}"

;igfxdiag.ICUIPCI

HKCR,"Interface\{E0BA4EE1-03D5-11D3-B995-00A0C9AD54B5}\NumMethods"
HKCR,"Interface\{E0BA4EE1-03D5-11D3-B995-00A0C9AD54B5}\ProxyStubClsid32"
HKCR,"Interface\{E0BA4EE1-03D5-11D3-B995-00A0C9AD54B5}"

;igfxdiag.ICUIReport

HKCR,"Interface\{E0BA4EE5-03D5-11D3-B995-00A0C9AD54B5}\NumMethods"
HKCR,"Interface\{E0BA4EE5-03D5-11D3-B995-00A0C9AD54B5}ProxyStubClsid32"
HKCR,"Interface\{E0BA4EE5-03D5-11D3-B995-00A0C9AD54B5}"

;igfxdiag.ICUITests

HKCR,"Interface\{E0BA4EE4-03D5-11D3-B995-00A0C9AD54B5}\NumMethods"
HKCR,"Interface\{E0BA4EE4-03D5-11D3-B995-00A0C9AD54B5}ProxyStubClsid32"
HKCR,"Interface\{E0BA4EE4-03D5-11D3-B995-00A0C9AD54B5}"

;igfxdiag.IDiagServices

HKCR,"Interface\{0EF91A8D-03D5-11D3-B995-00A0C9AD54B5}\NumMethods"
HKCR,"Interface\{0EF91A8D-03D5-11D3-B995-00A0C9AD54B5}\ProxyStubClsid32"
HKCR,"Interface\{0EF91A8D-03D5-11D3-B995-00A0C9AD54B5}"

;igfxdiag.IDiagServices2

HKCR,"Interface\{1D775861-25C6-11D4-ACA5-00A0C9AD5629}\NumMethods"
HKCR,"Interface\{1D775861-25C6-11D4-ACA5-00A0C9AD5629}\ProxyStubClsid32"
HKCR,"Interface\{1D775861-25C6-11D4-ACA5-00A0C9AD5629}"

;igfxhk.Hotkey 

HKCR,"igfxhk.HotKey\CLSID"
HKCR,"igfxhk.HotKey\CurVer"
HKCR,"igfxhk.HotKey"
HKCR,"igfxhk.HotKey.1\CLSID"
HKCR,"igfxhk.HotKey.1"
HKCR,"CLSID\{235CC099-CFB4-44D9-8228-270FEE479D8A}\InProcServer32\ThreadingModel"
HKCR,"CLSID\{235CC099-CFB4-44D9-8228-270FEE479D8A}\InProcServer32"
HKCR,"CLSID\{235CC099-CFB4-44D9-8228-270FEE479D8A}\ProgID"
HKCR,"CLSID\{235CC099-CFB4-44D9-8228-270FEE479D8A}\VersionIndependentProgID"
HKCR,"CLSID\{235CC099-CFB4-44D9-8228-270FEE479D8A}"

;igfxdgps.dll entry

HKCR,"CLSID\{48E57D01-53BD-11D3-8EE0-00A0C984F371}\InProcServer32\ThreadingModel"
HKCR,"CLSID\{48E57D01-53BD-11D3-8EE0-00A0C984F371}\InProcServer32"
HKCR,"CLSID\{48E57D01-53BD-11D3-8EE0-00A0C984F371}"

;Remove HKLM\Software\Microsoft\Windows\Currentversion\Run CUI entries
HKLM,"SOFTWARE\Microsoft\Windows\CurrentVersion\Run","HotKeysCmds"
HKLM,"SOFTWARE\Microsoft\Windows\CurrentVersion\Run","Persistence"
HKLM,"SOFTWARE\Microsoft\Windows\CurrentVersion\Run","igfxtray"
HKLM,"SOFTWARE\Microsoft\Windows\CurrentVersion\Run","igfxhkcmd"
HKLM,"SOFTWARE\Microsoft\Windows\CurrentVersion\Run","igfxpers"

;
; Service Installation
;
[iILKM0.Services]
AddService = igfx, 0x00000002, igfx_Service_Inst

[iILKD0.Services]
AddService = igfx, 0x00000002, igfx_Service_Inst

[igfx_Service_Inst]
ServiceType    = 1               ; SERVICE_KERNEL_DRIVER
StartType      = 3               ; SERVICE_DEMAND_START
ErrorControl   = 0               ; SERVICE_ERROR_IGNORE
LoadOrderGroup = Video
ServiceBinary  = %12%\igdkmd64.sys
;
; DX10 Capable SKUs
;
[igfx_SoftwareDX10Settings]

; DX10

HKR,, InstalledDisplayDrivers,     %REG_MULTI_SZ%, igdumd64, igd10umd64, igdumdx32, igd10umd32
HKR,, UserModeDriverName,        %REG_MULTI_SZ%, igdumd64.dll,  igd10umd64.dll
HKR,, UserModeDriverNameWow,  %REG_MULTI_SZ%, igdumdx32.dll,  igd10umd32.dll

;
; DX11 Capable SKUs
;
[igfx_SoftwareDX11Settings]

; DX10

HKR,, InstalledDisplayDrivers,     %REG_MULTI_SZ%, igdumd64, igd10umd64, igd10umd64, igdumdx32, igd10umd32, igd10umd32
HKR,, UserModeDriverName,        %REG_MULTI_SZ%, igdumd64.dll, igd10umd64.dll, igd10umd64.dll
HKR,, UserModeDriverNameWow,  %REG_MULTI_SZ%, igdumdx32.dll, igd10umd32.dll, igd10umd32.dll

;
;MBM Specific settings
;
[ILKM_MBMSettings_AddSwSettings]
HKR,, Display1_ENABLEMBM,%REG_DWORD%, 0
HKR,, PrefCUIMBM,%REG_DWORD%, 0
HKR,, PanelLUTTableValidSize,%REG_DWORD%, 0 ; 63 -need to put 63 here i.e size has to be 63 
HKR,, PanelLUTTable,%REG_BINARY%, 0 ;default sample- 33,30,38,10,13,3,17,0,0,70,71,64,56,51,48,4,35,24,114,116,103,96,88,81,72,59,44,155,152,145,137,128,117,105,86,61,194,191,188,181,173,160,145,120,83,225,225,223,219,215,207,192,163,119,248,248,248,246,244,240,237,224,170  Default sample

[ILKM_MBMSettings_DelSwSettings]
HKR,, Display1_ENABLEMBM
HKR,, PrefCUIMBM
HKR,, PanelLUTTableValidSize
HKR,, PanelLUTTable

;
; TPV Specific Settings
;
[igfx_TPV_AddSwSettings]
HKR,, TPVSolutionEnabled,       %REG_DWORD%,    1
HKR,, MAXViews,                 %REG_DWORD%,    2
HKR,, MAXDevicesInView,         %REG_DWORD%,    2
HKR,, MAXIntelDevicesActive,    %REG_DWORD%,    2
HKR,, MAXOtherDevicesActive,    %REG_DWORD%,    3
HKR,, IsExtCloneSuppt,          %REG_DWORD%,    0

[igfx_TPV_DelSwSettings]
HKR,, TPVSolutionEnabled
HKR,, MAXViews
HKR,, MAXDevicesInView
HKR,, MAXIntelDevicesActive
HKR,, MAXOtherDevicesActive
HKR,, IsExtCloneSuppt

[igfx_SoftwareCommonSettings]
HKR,, UserModeDriverGUID,  %REG_SZ%, "{6C4BE3D5-831A-42ED-AA62-2AEB34C8CBA4}"
HKR,, MultifunctionSupported,   %REG_DWORD%,    1
HKR,, VgaCompatible,            %REG_DWORD%,    0
HKR,, NativeResolution,         %REG_DWORD%,    1
HKR,, NativeBPP,                %REG_DWORD%,    1
HKR,, ConfigID,                 %REG_DWORD%,    0
HKR,, PC_Release_Major,         %REG_DWORD%,    15        ;Dummy value
HKR,, PC_Release_Minor,         %REG_DWORD%,    0          ; 15.x
HKR,, BIOSHPDSupport,           %REG_DWORD%,    00
HKR,, EnableFakeTV,             %REG_DWORD%,    01
HKR,, EnableFakeCRT,            %REG_DWORD%,    01
HKR,, IntelDefaultPers,         %REG_DWORD%,    00

; OVERLAY SPECIFIC INF SETTINGS START HERE
HKR,, Disable_OverlayDSQualityEnhancement,  %REG_DWORD%,     0
; OVERLAY SPECIFIC INF SETTING END

;ROTATION SPECIFIC INF SETTINGS START HERE

HKR,,   Display1_EnableRotation,    %REG_DWORD%,    0x1
HKR,,   Display1_RotationCaps,      %REG_DWORD%,    0x7     ;Portrait, Inverted Landscape, Inverted Portrait
HKR,,   Display2_RotationCaps,      %REG_DWORD%,    0x7     ;Portrait, Inverted Landscape, Inverted Portrait
HKR,,   Display1_IndependentRotation,    %REG_DWORD%,    0x00
HKR,,   Display1_EnableIndependentRotation,    %REG_DWORD%,    0x00
HKR,,   Display1_EnableIDDC_WA,    	       %REG_DWORD%,    0x00
HKR,,   RotationSPLCase,    %REG_DWORD%,    0x00
HKR,,   SmoothRotationSupport,    %REG_DWORD%,    0x00

;ROTATION SPECIFIC INF SETTINGS END HERE

;EVENT MANAGER SPECIFIC INF SETTINGS START HERE

;HKR,,	DisplayPriority,		0x00000001, 	0x08, 0x80, 0x01, 0x10, 0x04, 0x40, 0x02, 0x20 ;descending
;HKR,, 	EDIDDefaultXX,			%REG_DWORD%,	0x320
;HKR,,	EDIDDefaultYY,			%REG_DWORD%,	0x258
;HKR,,	EDIDDefaultRR,			%REG_DWORD%,	0x3c
;HKR,,	EDIDDefaultBPP,			%REG_DWORD%,	0x20
;HKR,,	LegacyDefaultXX,		%REG_DWORD%,	0x320
;HKR,,	LegacyDefaultYY,		%REG_DWORD%,	0x258
;HKR,,	LegacyDefaultRR,		%REG_DWORD%,	0x3c
;HKR,,	LegacyDefaultBPP,		%REG_DWORD%,	0x20

HKR,,	OpenGLInstalled,		%REG_DWORD%, 	0x01  	; Open GL drivers installed

;EVENT MANAGER SPECIFIC INF SETTINGS END HERE

HKLM,"SYSTEM\CurrentControlSet\Control\GraphicsDrivers",UseXPModel,%REG_DWORD%,0
HKLM,"SYSTEM\CurrentControlSet\Control\GraphicsDrivers\Scheduler",EnablePreemption,%REG_DWORD%,1

[igfx_MSI_HardwareDeviceSettings]
; MSI Support
HKR, "Interrupt Management", 0x00000010
HKR, "Interrupt Management\MessageSignaledInterruptProperties", 0x00000010
HKR, "Interrupt Management\MessageSignaledInterruptProperties", MSISupported, 0x00010001, 1

[igfx_RemoveDeviceSettings]
HKR,, VgaCompatible
HKR,, NativeResolution
HKR,, NativeBPP
HKR,, ConfigID
HKR,, PC_Release_Major
HKR,, PC_Release_Minor

; OVERLAY SPECIFIC INF SETTINGS START HERE
HKR,, Disable_OverlayDSQualityEnhancement
; OVERLAY SPECIFIC INF SETTING END

;ROTATION SPECIFIC INF SETTINGS START HERE

HKR,,   Display1_EnableRotation
HKR,,   Display1_RotationCaps
HKR,,   Display2_RotationCaps
HKR,,   Display1_IndependentRotation
HKR,,   Display1_EnableIndependentRotation
HKR,,   Display1_EnableIDDC_WA
HKR,,   RotationSPLCase
HKR,,   SmoothRotationSupport

;ROTATION SPECIFIC INF SETTINGS END HERE

;EVENT MANAGER SPECIFIC INF SETTINGS START HERE

HKR,,	DisplayPriority
HKR,, 	EDIDDefaultXX
HKR,,	EDIDDefaultYY
HKR,,	EDIDDefaultRR
HKR,,	EDIDDefaultBPP
HKR,,	LegacyDefaultXX
HKR,,	LegacyDefaultYY
HKR,,	LegacyDefaultRR
HKR,,	LegacyDefaultBPP

HKR,,	PerUserPersistence
HKR,,	UseBIOSDataforDock
HKR,,	HpDock
HKR,,	TMM_Active
HKR,,	RequestSig
HKR,,	RequestedXRes
HKR,,	RequestedYRes
HKR,,	RequestedBPP
HKR,,	RequestedRate

HKR,,	HotKeyPersistence
HKR,,	HotKeyPersistMDS
HKR,,	LidPersistence
HKR,,	DockPersistence
HKR,,	HotPlugPersistence
HKR,,	PowerPersistence
HKR,,	EdidPersistence
HKR,,	LFPAlwaysPrimary
HKR,,	OpenGLInstalled

;EVENT MANAGER SPECIFIC INF SETTINGS END HERE

;DEVICE SPECIFIC INF SWITCHES

[EnableEccMemoryTileX_WA_ILK_AddSwSettings]
HKR,, EccMemoryTileXWA, %REG_DWORD%, 0

[EnableEccMemoryTileX_WA_ILK_DelSwSettings]
HKR,, EccMemoryTileXWA

[NonEDIDMode_AddSwSettings]
HKR,, TotalDTDCount, %REG_DWORD%, 0  	; This shows number of DTDs to be used. ;  0-->Disable the feature.
;Following keys have 20 bytes (18 byte DTD + 2 Byte flags).
HKR,, DTD_1,%REG_BINARY%, 01,1D,80,18,71,1C,16,20,58,2C,1A,00,00,00,00,00,00,86,37,01		;1920x1080@60...Interlaced
HKR,, DTD_2, %REG_BINARY%, 01,1D,80,D0,72,1C,16,20,10,2C,1A,80,00,00,00,00,00,86,37, 01		;1920x1080@50...Interlaced
HKR,, DTD_3,%REG_BINARY%, 01,1D,00,BC,52,D0,1E,20,B8,28,25,40,00,00,00,00,00,04,37, 01		;1280x720@50....Non-interlaced
HKR,, DTD_4, %REG_BINARY%, 01,1D,00,72,51,D0,1E,20,6E,28,25,00,00,00,00,00,00,06,37,01		;1280x720@60....Non-interlaced	
HKR,, DTD_5,%REG_BINARY%, 00, 00, 00 ,00, 00, 00,00, 00, 00,00, 00, 00,00, 00, 00,00, 00, 00,00, 00	;Fifth DTD

[NonEDIDMode_DelSwSettings]
HKR,, TotalDTDCount
HKR,, DTD_1
HKR,, DTD_2
HKR,, DTD_3
HKR,, DTD_4
HKR,, DTD_5

[CRTHotPlugDefaultVrefVoltage_AddSwSettings]
HKR,, Display1_EnableCRTHotPlugDefaultVrefVoltage,	%REG_DWORD%, 1  	; 1 - Enable(Default Value) and 0 - Disable(Customized Value)

[CRTHotPlugDefaultVrefVoltage_DelSwSettings]
HKR,, Display1_EnableCRTHotPlugDefaultVrefVoltage

[DynamicScaling_AddSwSettings]
HKR,, Display1_EnableDynamicScaling,%REG_DWORD%, 0  		; 1 - Enable and 0 - Disable

[DynamicScaling_DelSwSettings]
HKR,, Display1_EnableDynamicScaling

[eDPNoFLT_AddSwSettings]
;If this Registry is set to 1 then it will ignore the Fast Link Training and will always do Normal Link Training everytime
HKR,, NoFastLinkTrainingForeDP, %REG_DWORD%, 0

[eDPNoFLT_DelSwSettings]
HKR,, NoFastLinkTrainingForeDP

[DynamicClockGating_AddSwSettings]
HKR,, EnableDynamicClockGating, %REG_DWORD%, 1			;1 - Enable and 0 - Disable

[DynamicClockGating_DelSwSettings]
HKR,, EnableDynamicClockGating

[EnableInterlacedModeRemoval_AddSwSettings]
HKR,, EnableInterlacedModeRemoval,%REG_DWORD%, 1		    ; 1 - Enable and 0 - Disable

[EnableInterlacedModeRemoval_DelSwSettings]
HKR,, EnableInterlacedModeRemoval

[DelayedDetectionForDP_AddSwSettings]
HKR,, DelayedDetectionForDP,%REG_DWORD%, 500  		; Delay in ms Range - 0 - 1000

[DelayedDetectionForDP_DelSwSettings]
HKR,, DelayedDetectionForDP

[DelayedDetectionForHDMI_AddSwSettings]
HKR,, DelayedDetectionForHDMI,%REG_DWORD%, 1000  	; Delay in ms Range - 0 - 1000

[DelayedDetectionForHDMI_DelSwSettings]
HKR,, DelayedDetectionForHDMI

[ForceBorderForMAR_AddSwSettings]
HKR,, ForceBorderForMAR,%REG_DWORD%, 0					    ; 1 - Enable and 0 - Disable

[ForceBorderForMAR_DelSwSettings]
HKR,, ForceBorderForMAR

[Gen6IntLVDSSwing_AddSwSettings]
;0x00 - Medium - Data and Clk Swing set to 298 mV
;0x01 - High - Data and Clk Swing set to 320 mV
;0x02 - Low1 - Data and Clk Swing set to 144 mV
;0x04 - Low2 - Data and Clk Swing set to 170 mV
;0x08 - Low3 - Data and Clk Swing set to 196 mV
;0x10 - Low4 - Data and Clk Swing set to 220 mV
;0x20 - Low5 - Data and Clk Swing set to 247 mV
;0x40 - Low6 - Data and Clk Swing set to 273 mV
HKR,, IntLVDSSwingSetting,%REG_DWORD%, 0x00 

[Gen6IntLVDSSwing_DelSwSettings]
HKR,, IntLVDSSwingSetting

[RedBlankingPnl_AddSwSettings]
HKR,, EnableReducedBlankingPnlWA,%REG_DWORD%, 0x00 ; 0x00- Disable, 0x01 - Enable

[RedBlankingPnl_DelSwSettings]
HKR,, EnableReducedBlankingPnlWA

[AsyncFlips_AddSwSettings]
HKR,, Display1_DisableAsyncFlips,%REG_DWORD%, 0  		; 1 - Disable and 0 - Enable

[AsyncFlips_DelSwSettings]
HKR,, Display1_DisableAsyncFlips

[EnableHDMIUnderScan_AddSwSettings]
HKR,, EnableHDMIUnderScan,%REG_DWORD%, 0  		; 1 - UnderScan and 0 - OverScan

[EnableHDMIUnderScan_DelSwSettings]
HKR,, EnableHDMIUnderScan

[HDMICEATimings_AddSwSettings]
HKR,, Display1_EnableHDMICEATimingsOnly,%REG_DWORD%, 0  		; 1 - Enable and 0 - Disable

[HDMICEATimings_DelSwSettings]
HKR,, Display1_EnableHDMICEATimingsOnly

[SdvoDdcEdidRead_AddSwSettings]
HKR,, Display1_DisableSdvoCrtEdidRead ,%REG_DWORD%, 0  		; 1 - Enable and 0 - Disable

[SdvoDdcEdidRead_DelSwSettings]
HKR,, Display1_DisableSdvoCrtEdidRead

[MediaScaling_AddSwSettings]
HKR,, Display1_EnableMediaScaling,%REG_DWORD%, 0  		; 1 - Enable and 0 - Disable

[MediaScaling_DelSwSettings]
HKR,, Display1_EnableMediaScaling

;To enable VBT override through INF
[INFVBTOverride_AddSwSettings]
HKR,, INF_VBT_Override_EnableFeature,%REG_DWORD%, 0 

[INFVBTOverride_DelSwSettings]
HKR,, INF_VBT_Override_EnableFeature

;    OPTIONS FOR HOTPLUG THROUGH INF 
;2 - Apply logic selected in VBT
;0 - Disable Hot Plug
;1 - Enable Hot Plug
;NOTE: Enable "INF_VBT_Override_EnableFeature" flag to use below given INF entries

[INFHotPlug_AddSwSettings]
HKR,, HotPlug_DVO_SDVO,%REG_DWORD%, 2 
HKR,, HotPlug_CRT,%REG_DWORD%, 2

[INFHotPlug_DelSwSettings]
HKR,,HotPlug_DVO_SDVO
HKR,,HotPlug_CRT

[OEMStaticMode_AddSwSettings]
HKR,, TotalStaticModes, %REG_DWORD%, 0	; This shows number of Static modes to be used. 
;TotalStaticModes = 0-->Disable the feature.
;Following keys have 8 bytes:
; 2B XRes + 2B YRes
; + 2B RRMask (Bit 0 - 60, 1 -70, 2 - 72, 3 - 75, 4 - 85,5 - 100,6 - 120,7-15 reserved)
; + 1B BppMask(Bit 0 - 8bpp,1 - 16bpp,2 - 32bpp, 3-7 reserved)
; + 1B reserved. 
; all values in Hex; l->low byte, h->high byte
;Examples:
;								   xl xh yl yh rl rh bp Rv
;HKR,, STATIC_MODE_1,%REG_BINARY%, 20,03,58,02,03,00,07,0F ;8x6 60,70
;HKR,, STATIC_MODE_2,%REG_BINARY%, 20,03,58,02,20,00,04,0F ;8x6 100 : 32bpp

[OEMStaticMode_DelSwSettings]
;HKR,, STATIC_MODE_1
;HKR,, STATIC_MODE_2

[MediaSrcMode_AddSwSettings]
HKR,, TotalMediaSrcModes, %REG_DWORD%, 0	; This shows number of Media Source to be used. 
;TotalMediaSrcModes = 0-->No Modes Added.
;Modes added must be < 10x7
;Following keys have 8 bytes:
; 2B XRes + 2B YRes
; + 1B reserved. 
; all values in Hex; l->low byte, h->high byte
;Examples:
;								   xl xh yl yh Rv
;HKR,, MEDIA_MODE_1,%REG_BINARY%, D0,02,E0,01,0F ;720x480
;HKR,, MEDIA_MODE_2,%REG_BINARY%, 20,03,58,02,0F ; 800x600

[MediaSrcMode_DelSwSettings]
;HKR,, MEDIA_MODE_1
;HKR,, MEDIA_MODE_2

[MediaRefreshRateMode_AddSwSettings]
HKR,, MediaRefreshRateMask, %REG_DWORD%, 0 ; Mask to enable media refresh rates BIT0 - LFP BIT1-7 :Reserved

[MediaRefreshRateMode_DelSwSettings]
HKR,, MediaRefreshRateMask

[BitBashingSupport_AddSwSettings]
; This is used to enable Bit Bashing instead of GMBUS to read monitor EDID for each
; Display Type.
; CRTType - BIT0, DFPType - BIT1, LFPType - BIT2, BIT[3:7] - Reserved.
HKR,, BitBashingSupport, %REG_BINARY%, 0

[BitBashingSupport_DelSwSettings]
HKR,, BitBashingSupport

[BitBashingForHDCP_AddSwSettings]
;This is to use BitBashing instead of GMBUS for HDCP
HKR,, BitBashingForHDCP, %REG_BINARY%, 0

[BitBashingForHDCP_DelSwSettings]
HKR,, BitBashingForHDCP

[SDVOHDMI_VSI_AddSwSettings]
HKR,, SPDIFVendorName,%REG_SZ%, "Intel" ; max 8 characters
HKR,, SPDIFVendorDesc,%REG_SZ%, "9xxxx" ; max 16 characters
HKR,, SDVOHDMI_OptionalIFPriority,%REG_DWORD%, 0x21 ; default to priority 1 for SPD Infoframe and priority 2 for VS Infoframe
HKR,, SDVOHDMI_SupportCEA861D,%REG_DWORD%, 0 ;To enable support for 861D spec, 1-Support IT Content and RGB Quantization, 0- No 861D support. Default to 0.

[SDVOHDMI_VSI_DelSwSettings]
HKR,, SPDIFVendorName
HKR,, SPDIFVendorDesc
HKR,, SDVOHDMI_OptionalIFPriority
HKR,, SDVOHDMI_SupportCEA861D

[PwrCons_ILK_AddSwSettings]
HKR,, FeatureTestControl,%REG_DWORD%, 0xF800 ; Enable FBC, GSV, RC6, DPS, DPST5, Vista Backlight Control, GPMT, Turbo

[PwrCons_ILK_DelSwSettings]
HKR,, FeatureTestControl

[PwrCons_DPS_AddSwSettings]
HKR,, DPSCheckboxDefault,%REG_DWORD%, 0x1
HKR,, DPSBaseLoRRValue,%REG_DWORD%, 0x0
HKR,, Display1_DPSPanel_Type,%REG_DWORD%, 0xFF ;Normal/Static DRRS = 0, Seamless = 2, or Disable INF option = 0xFF
HKR,, DPSMotionArtifactMitigation,%REG_DWORD%, 0x1
HKR,, SupportForStaticDRRS,%REG_DWORD%, 0x0

[PwrCons_DPS_DelSwSettings]
HKR,, DPSCheckboxDefault
HKR,, DPSControlMode
HKR,, DPSBaseLoRRValue
HKR,, Display1_DPSPanel_Type
HKR,, DPSMotionArtifactMitigation
HKR,, SupportForStaticDRRS

[HotPlug_AddSwSettings]
HKR,, Display1_DVIHotPlugWAFlag,%REG_DWORD%, 0  ; 1 - Enable and 0 - Disable

[HotPlug_DelSwSettings]
HKR,, Display1_DVIHotPlugWAFlag

[CRTScaler_AddSwSettings]
; This is used to enable Scaler on CRT
HKR,, EnableDynamicScalingWithHwScaler, %REG_DWORD%, 1

[CRTScaler_DelSwSettings]
HKR,, EnableDynamicScalingWithHwScaler

[InternalScaler_AddSwSettings]
; This is used to enable Scaler on CRT
HKR,, EnableInternalScalar, %REG_DWORD%, 0

[InternalScaler_DelSwSettings]
HKR,, EnableInternalScalar

[PNM_AddSwSettings]
HKR,, PNMClkDeviation, %REG_DWORD%, 0   ;Clock deviation value which is multiplied by 10.
HKR,, PNMFlags, %REG_DWORD%, 0   ; Bit0:Downward Deviation, Bit1: Upward Deviation. Bit2-31: Reserved.

[PNM_DelSwSettings]
HKR,, PNMClkDeviation
HKR,, PNMFlags

[Underscan_AddSwSettings]
;INTTVOUT
HKR,, Display1_UnderScanPercentageIntTvOut,%REG_DWORD%, 0  ; 0 - default 7.5% under scan and OEM's can give under scan like 8,9 an 10 ..upto 25
;HDMI
HKR,, Display1_AddUnderscanPercentageHDMI,%REG_DWORD%, 0  ; 0 - default 7.5% under scan and OEM's can give under scan like 8,9 an 10 ..

[Underscan_DelSwSettings]
HKR,, Display1_UnderScanPercentageIntTvOut
HKR,, Display1_AddUnderscanPercentageHDMI

[General_AddSwSettings]
HKR,, ModeEnumerationPreference,%REG_DWORD%, 0xFFFFFFFF     ; BitMask for Displays. If Set to 1, it indicates OEM Mode is preferred over EDID.
							    ; Default Value is OEM is preferred over EDID
		     	                                    ; Bit 0- CRT:Bit 2- DFP:Bit 1 and 3 reserved.

[General_DelSwSettings]
HKR,, ModeEnumerationPreference

[IncFixedSegWA_AddSwSettings]
HKR,, IncreaseFixedSegment,%REG_DWORD%, 0   ; 0 - disabled, 1- enabled           

[IncFixedSegWA_DelSwSettings]
HKR,, IncreaseFixedSegment

[PanelFitterOnDP_AddSwSettings]
HKR,, DisablePFonDP,%REG_DWORD%, 0x00 ; 0x00- Enable, 0x01 - Disable... Not applicable for eDP panels.

[PanelFitterOnDP_DelSwSettings]
HKR,, DisablePFonDP

[XVYCCFeatture_AddSwSettings]
HKR,, XVYCCFeatureEnable,%REG_DWORD%, 0x01 ; 0x00- Disable, 0x01 - Enable... 

[XVYCCFeatture_DelSwSettings]
HKR,, XVYCCFeatureEnable

[DeepColorHDMI_AddSwSettings]
HKR,, DeepColorHDMIDisable,%REG_DWORD%, 0 ; 0-Enable Deep Color, 1-Disable Deep Color

[DeepColorHDMI_DelSwSettings]
HKR,, DeepColorHDMIDisable

[WGFeature_AddSwSettings]
HKR,, WideGamutFeatureEnable,%REG_DWORD%, 0x00 ; 0x01- Enable for LFP,0x02 - Enable for DP,0x04 - Enable for HDMI... 
					   ; When Wide Gamut feature is enabled, Hue and Saturation feature is disabled

[WGFeature_DelSwSettings]
HKR,, WideGamutFeatureEnable

[UseEDIDTimingForCRTClone_AddSwSettings]
HKR,, UseEDIDOnlyCRTMode,%REG_DWORD%, 0x00 ; 0x00- Disable, 0x01 - Enable. Use Only EDID Timing for CRT on Clone Mode

[UseEDIDTimingForCRTClone_DelSwSettings]
HKR,, UseEDIDOnlyCRTMode

[PdTogglingTimer_AddSwSettings]
HKR,, PdTogglingTimerValue,%REG_DWORD%, 0xBF ;  Bug 3885162, increasing the delay value.

[PdTogglingTimer_DelSwSettings]
HKR,, PdTogglingTimerValue

; END DEVICE SPECIFIC INF SWITCHES

[iILKM0.GeneralConfigData]
MaximumNumberOfDevices = 2
MaximumDeviceMemoryConfiguration = 512

[iILKD0.GeneralConfigData]
MaximumNumberOfDevices = 2
MaximumDeviceMemoryConfiguration = 512

;
; Source file information
;

[SourceDisksNames]
1 = %DiskId%

[SourceDisksFiles]
igdkmd64.sys  = 1
igdumd64.dll = 1
igdumd32.dll = 1
igkrng575.bin = 1
igkrng600.bin = 1
igcompkrng575.bin = 1
igcompkrng600.bin = 1
igfcg575m.bin = 1
igfcg600m.bin = 1
iglhxs64.vp = 1
iglhxo64.vp = 1
iglhxc64.vp = 1
iglhxg64.vp = 1
iglhxa64.vp = 1
iglhxa64.cpa = 1
iglhcp64.dll = 1
iglhcp32.dll = 1
iglhsip64.dll = 1
iglhsip32.dll = 1
difx64.exe = 1
igxpco64.dll = 1
IccLibDll_x64.dll = 1
igfxcmrt32.dll = 1
igfxcmjit32.dll = 1
igfxcmrt64.dll = 1
igfxcmjit64.dll = 1
igdde64.dll = 1
igdde32.dll = 1

hccutils.dll = 1
igfxsrvc.dll = 1
igfxsrvc.exe = 1
igfxpph.dll = 1
igfxcpl.cpl = 1
igfxcfg.exe = 1
igfxdev.dll = 1
igfxdv32.dll = 1
igfxdo.dll = 1
igfxtray.exe = 1
hkcmd.exe = 1
igfxpers.exe = 1
igfxext.exe = 1	; CUI SDK
igfxexps.dll = 1	; CUI SDK proxy stub
igfxexps32.dll = 1
igfxTMM.dll = 1	

igfxress.dll = 1 ; Generic language resource file
igfxrara.lrc=1   ; Arabic 
igfxrchs.lrc=1  ; Simplified Chinese 
igfxrcht.lrc=1  ; Traditional Chinese 
igfxrdan.lrc=1  ; Danish 
igfxrdeu.lrc=1  ; German
igfxrenu.lrc=1  ; American English 
igfxresn.lrc=1  ; Spanish 
igfxrfin.lrc=1   ; Finish 
igfxrfra.lrc=1   ; French 
igfxrheb.lrc=1  ; Hebrew 
igfxrhrv.lrc=1  ; Croatian
igfxrita.lrc=1   ; Italian 
igfxrjpn.lrc=1  ; Japanese 
igfxrkor.lrc=1  ; Korean 
igfxrnld.lrc=1  ; Netherlands 
igfxrnor.lrc=1  ; Norwegian 
igfxrplk.lrc=1  ; Polish 
igfxrptb.lrc=1  ; Brazilian Portuguese 
igfxrptg.lrc=1  ; Portuguese 
igfxrrom.lrc=1 ; Romanian
igfxrrus.lrc=1  ; Russian 
igfxrsky.lrc=1  ; Slovakian 
igfxrslv.lrc=1   ; Slovenian 
igfxrsve.lrc=1  ; Swedish 
igfxrtha.lrc=1  ; Thai 
igfxrcsy.lrc=1  ; Czechoslovakian 
igfxrell.lrc=1   ; Greek 
igfxrhun.lrc=1  ; Hungarian 
igfxrtrk.lrc=1  ; Turkish 

Gfxres.ar-SA.resources = 1 
Gfxres.cs-CZ.resources = 1 
Gfxres.da-DK.resources = 1 
Gfxres.de-DE.resources = 1 
Gfxres.el-GR.resources = 1 
Gfxres.es-ES.resources = 1 
Gfxres.en-US.resources = 1 
Gfxres.fi-FI.resources = 1 
Gfxres.fr-FR.resources = 1 
Gfxres.he-IL.resources = 1
Gfxres.hr-HR.resources = 1 
Gfxres.hu-HU.resources = 1 
Gfxres.it-IT.resources = 1 
Gfxres.ja-JP.resources = 1 
Gfxres.ko-KR.resources = 1 
Gfxres.nb-NO.resources = 1 
Gfxres.nl-NL.resources = 1 
Gfxres.pl-PL.resources = 1 
Gfxres.pt-BR.resources = 1 
Gfxres.pt-PT.resources = 1 
Gfxres.ro-RO.resources = 1
Gfxres.ru-RU.resources = 1 
Gfxres.sk-SK.resources = 1 
Gfxres.sl-SI.resources = 1 
Gfxres.sv-SE.resources = 1 
Gfxres.th-TH.resources = 1 
Gfxres.tr-TR.resources = 1 
Gfxres.zh-CN.resources = 1 
Gfxres.zh-TW.resources = 1

gfxSrvc.dll = 1    ; 3.0 UI
GfxUI.exe = 1
GfxUI.exe.config = 1    
IGFXDEVLib.dll = 1    

ig4icd64.dll = 1
ig4icd32.dll = 1

igd10umd32.dll = 1
igd10umd64.dll = 1

igdumdx32.dll = 1

;
; Start CUI Registry Sections
;
[CUI.AddReg]
;Add INTEL/CUI keys
HKLM,"Software\INTEL"
HKLM,%DisplayKey%
HKLM,%CUIDeviceIndependentKey%

;HKLM,"%CUIDeviceIndependentKey%\igfxdev","MaxSuppXX",%REG_DWORD%,800

;HKLM,"%CUIDeviceIndependentKey%\igfxdev","MaxSuppYY",%REG_DWORD%,480

; Device Independent registry location
HKCR,"CLSID\{280A8F40-E382-11D2-B561-00A0C92E6848}",,,%CUIDeviceIndependentKey%

; Add Diagnostic Pages with the rest of the pages
HKLM,"SOFTWARE\Microsoft\Windows\CurrentVersion\Controls Folder\Display\shellex\PropertySheetHandlers\igfxcui",,,"{3AB1675A-CCFF-11D2-8B20-00A0C93CB1F4}"
HKCR,"CLSID\{280A8F40-E382-11D2-B561-00A0C92E6848}\shellex\PropertyPageHandlers\igfxcfg\diagHandler",,,"{3AB167A5-CCFF-11D2-8B20-00A0C93CB1F4}"

;Hide Graphics Property String for SG
;HKLM,"%CUIDeviceIndependentKey%\igfxpph\resources","3060",%REG_SZ%,""

;Intel Application Name
HKLM,"%CUIDeviceIndependentKey%\igfxcfg\resources","Application",%REG_SZ%,"GfxUI.exe"

; Store resource information under %CUIDeviceIndependentKey%
; as for 830M these all will come under device independent keys
; Control panel resource
HKLM,"%CUIDeviceIndependentKey%\igfxcpl\resources","468",,%11%"\igfxcfg.exe"
; static pages resource
HKLM,"%CUIDeviceIndependentKey%\igfxpph\resources","468",,%11%"\igfxcfg.exe"
; Diagnostics resource
HKLM,"%CUIDeviceIndependentKey%\igfxcfg\resources","2945",,%11%"\igfxdiag.exe"
; cfg resource
HKLM,"%CUIDeviceIndependentKey%\igfxcfg\resources","468",,%11%"\igfxcfg.exe"
HKLM,"%CUIDeviceIndependentKey%\igfxcfg\resources","829",,""
; service resource
HKLM,"%CUIDeviceIndependentKey%\igfxsrvc\resources","468",,%11%"\igfxcfg.exe"
HKLM,"%CUIDeviceIndependentKey%\igfxtray\TrayIcon","ShowTrayIcon",%REG_DWORD%,1
; tray resource
HKLM,"%CUIDeviceIndependentKey%\igfxtray","ShowOptimalBalloon",%REG_DWORD%,1
HKLM,"%CUIDeviceIndependentKey%\igfxtray\resources","468",,%11%"\igfxcfg.exe"
HKLM,"%CUIDeviceIndependentKey%\igfxtray\resources","467",,%11%"\igfxtray.exe"
; hotkey resource
HKLM,"%CUIDeviceIndependentKey%\hkcmd\resources","468",,%11%"\igfxcfg.exe"
;CUI Aspect Scaling hotkey expansion RCR 942979
HKLM,"%CUIDeviceIndependentKey%\hkcmd","ExpansionAllDisplay",%REG_DWORD%,0x1
;static pages resource
HKLM,"%CUIDeviceIndependentKey%\igfxpph\resources","467",,%11%"\igfxtray.exe"
;This flag is used to enable WA for setting LFP as Primary in DDC
HKR,,   Display1_EnableLFPPrimaryInDDC,    %REG_DWORD%,    0x00
;CUI AC/DC Rotation uncomment the below line to enable this feature
;HKLM,"%CUIDeviceIndependentKey%\igfxcfg","DCRotationCaps",%REG_DWORD%,0x1
;CUI default mode selection policy
HKLM,"%CUIDeviceIndependentKey%\igfxsrvc","ModeSelectionPolicy",%REG_DWORD%,0x01
;preset profiles
HKLM,"%CUIDeviceIndependentKey%\profiles\Media\Default Profile","ProcAmpHue",%REG_SZ%,0.00
HKLM,"%CUIDeviceIndependentKey%\profiles\Media\Default Profile","ProcAmpSaturation",%REG_SZ%,1.00
HKLM,"%CUIDeviceIndependentKey%\profiles\Media\Default Profile","ProcAmpBrightness",%REG_SZ%,0.00
HKLM,"%CUIDeviceIndependentKey%\profiles\Media\Default Profile","ProcAmpContrast",%REG_SZ%,1.00

HKLM,"%CUIDeviceIndependentKey%\profiles\Media\Darken Movie","ProcAmpHue",%REG_SZ%,0.00
HKLM,"%CUIDeviceIndependentKey%\profiles\Media\Darken Movie","ProcAmpSaturation",%REG_SZ%,1.00
HKLM,"%CUIDeviceIndependentKey%\profiles\Media\Darken Movie","ProcAmpBrightness",%REG_SZ%,-30.00
HKLM,"%CUIDeviceIndependentKey%\profiles\Media\Darken Movie","ProcAmpContrast",%REG_SZ%,1.00

HKLM,"%CUIDeviceIndependentKey%\profiles\Media\Brighten Movie","ProcAmpHue",%REG_SZ%,0.00
HKLM,"%CUIDeviceIndependentKey%\profiles\Media\Brighten Movie","ProcAmpSaturation",%REG_SZ%,1.00
HKLM,"%CUIDeviceIndependentKey%\profiles\Media\Brighten Movie","ProcAmpBrightness",%REG_SZ%,30.00
HKLM,"%CUIDeviceIndependentKey%\profiles\Media\Brighten Movie","ProcAmpContrast",%REG_SZ%,1.00

HKLM,"%CUIDeviceIndependentKey%\profiles\Media\Vivid Colors","ProcAmpHue",%REG_SZ%,0.00
HKLM,"%CUIDeviceIndependentKey%\profiles\Media\Vivid Colors","ProcAmpSaturation",%REG_SZ%,1.70
HKLM,"%CUIDeviceIndependentKey%\profiles\Media\Vivid Colors","ProcAmpBrightness",%REG_SZ%,0.00
HKLM,"%CUIDeviceIndependentKey%\profiles\Media\Vivid Colors","ProcAmpContrast",%REG_SZ%,1.50
;=============================================================================
HKLM,"SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon\Notify\igfxcui"
HKLM,"SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon\Notify\igfxcui","DLLName",%REG_SZ%,"igfxdev.dll"
HKLM,"SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon\Notify\igfxcui","Asynchronous",%REG_DWORD%,1
HKLM,"SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon\Notify\igfxcui","Impersonate",%REG_DWORD%,1
HKLM,"SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon\Notify\igfxcui","Unlock",%REG_SZ%,"WinlogonUnlockEvent"
;=============================================================================

; Class ID of the CUIDriver component.
HKR,"DEFAULT","CUIDriver",,"{9CEE304E-DC6C-11D2-B561-00A0C92E6848}"

; Context menu handler entry.
HKCR, "Directory\Background\shellex\ContextMenuHandlers\igfxcui",,,"{3AB1675A-CCFF-11D2-8B20-00A0C93CB1F4}"
;
; Registration of CUI dll's:            These will not self-register through the have-disk install.
;                                       Does not register TypeLibs or Interfaces.
;
; igfxcfg.exe self registration entries
;
HKCR,"AppID\{3D62E9A1-D243-11D2-B561-00A0C92E6848}",,,"igfxcfg"
HKCR,"AppID\igfxcfg.EXE","AppID",,"{3D62E9A1-D243-11D2-B561-00A0C92E6848}"
HKCR,"CLSID\{A354BD60-4C0A-11d3-B561-00A0C92E6848}",,,"DataObject Class"
HKCR,"CLSID\{A354BD60-4C0A-11d3-B561-00A0C92E6848}","AppID",,"{3D62E9A1-D243-11D2-B561-00A0C92E6848}"
HKCR,"CLSID\{A354BD60-4C0A-11d3-B561-00A0C92E6848}\ProgID",,,"igfxcfg.DataObject.1"
HKCR,"CLSID\{A354BD60-4C0A-11d3-B561-00A0C92E6848}\VersionIndependentProgID",,,"igfxcfg.DataObject"
HKCR,"CLSID\{A354BD60-4C0A-11d3-B561-00A0C92E6848}\LocalServer32",,,%11%"\igfxcfg.exe"
HKCR,"CLSID\{EE2D6561-D63C-11D2-B561-00A0C92E6848}",,,"ShellExt Class"
HKCR,"CLSID\{EE2D6561-D63C-11D2-B561-00A0C92E6848}","AppID",,"{3D62E9A1-D243-11D2-B561-00A0C92E6848}"
HKCR,"CLSID\{EE2D6561-D63C-11D2-B561-00A0C92E6848}\ProgID",,,"igfxcfg.ShellExt.1"
HKCR,"CLSID\{EE2D6561-D63C-11D2-B561-00A0C92E6848}\VersionIndependentProgID",,,"igfxcfg.ShellExt"
HKCR,"CLSID\{EE2D6561-D63C-11D2-B561-00A0C92E6848}\Programmable",,,
HKCR,"CLSID\{EE2D6561-D63C-11D2-B561-00A0C92E6848}\LocalServer32",,,%11%"\igfxcfg.exe"
HKCR,"igfxcfg.DataObject.1",,,"DataObject Class"
HKCR,"igfxcfg.DataObject.1\CLSID",,,"{A354BD60-4C0A-11d3-B561-00A0C92E6848}"
HKCR,"igfxcfg.DataObject",,,"DataObject Class"
HKCR,"igfxcfg.DataObject\CurVer",,,"igfxcfg.DataObject.1"
HKCR,"igfxcfg.DataObject\CLSID",,,"{A354BD60-4C0A-11d3-B561-00A0C92E6848}"
HKCR,"igfxcfg.ShellExt.1",,,"ShellExt Class"
HKCR,"igfxcfg.ShellExt.1\CLSID",,,"{EE2D6561-D63C-11D2-B561-00A0C92E6848}"
HKCR,"igfxcfg.ShellExt",,,"ShellExt Class"
HKCR,"igfxcfg.ShellExt\CurVer",,,"igfxcfg.ShellExt.1"
HKCR,"igfxcfg.ShellExt\CLSID",,,"{EE2D6561-D63C-11D2-B561-00A0C92E6848}"
;
; igfxdev.dll self registration entries
;
HKCR,"igfxdev.CUIDriver",,,"CUIDriver Class"
HKCR,"igfxdev.CUIDriver\CLSID",,,"{9CEE304E-DC6C-11D2-B561-00A0C92E6848}"
HKCR,"igfxdev.CUIDriver\CurVer",,,"igfxdev.CUIDriver.1"
HKCR,"igfxdev.CUIDriver.1",,,"CUIDriver Class"
HKCR,"igfxdev.CUIDriver.1\CLSID",,,"{9CEE304E-DC6C-11D2-B561-00A0C92E6848}"
HKCR,"CLSID\{9CEE304E-DC6C-11D2-B561-00A0C92E6848}",,,"CUIDriver Class"
HKCR,"CLSID\{9CEE304E-DC6C-11D2-B561-00A0C92E6848}\InProcServer32",,,%11%"\igfxdev.dll"
HKCR,"CLSID\{9CEE304E-DC6C-11D2-B561-00A0C92E6848}\InProcServer32","ThreadingModel",,"Apartment"
HKCR,"CLSID\{9CEE304E-DC6C-11D2-B561-00A0C92E6848}\ProgID",,,"igfxdev.CUIDriver.1"
HKCR,"CLSID\{9CEE304E-DC6C-11D2-B561-00A0C92E6848}\VersionIndependentProgID",,,"igfxdev.CUIDriver"
; 
; igfxdv32.dll self registration entries
;
HKLM,"Software\Wow6432Node\Classes\igfxdv32.CUIDriver",,,"CUIDriver Class"
HKLM,"Software\Wow6432Node\Classes\igfxdv32.CUIDriver\CLSID",,,"{9CEE304E-DC6C-11D2-B561-00A0C92E6848}"
HKLM,"Software\Wow6432Node\Classes\igfxdv32.CUIDriver\CurVer",,,"igfxdv32.CUIDriver.1"
HKLM,"Software\Wow6432Node\Classes\igfxdv32.CUIDriver.1",,,"CUIDriver Class"
HKLM,"Software\Wow6432Node\Classes\igfxdv32.CUIDriver.1\CLSID",,,"{9CEE304E-DC6C-11D2-B561-00A0C92E6848}"
HKLM,"Software\Wow6432Node\Classes\CLSID\{9CEE304E-DC6C-11D2-B561-00A0C92E6848}",,,"CUIDriver Class"
HKLM,"Software\Wow6432Node\Classes\CLSID\{9CEE304E-DC6C-11D2-B561-00A0C92E6848}\InProcServer32",,,%10%\SysWOW64"\igfxdv32.dll"
HKLM,"Software\Wow6432Node\Classes\CLSID\{9CEE304E-DC6C-11D2-B561-00A0C92E6848}\InProcServer32","ThreadingModel",,"Apartment"
HKLM,"Software\Wow6432Node\Classes\CLSID\{9CEE304E-DC6C-11D2-B561-00A0C92E6848}\ProgID",,,"igfxdv32.CUIDriver.1"
HKLM,"Software\Wow6432Node\Classes\CLSID\{9CEE304E-DC6C-11D2-B561-00A0C92E6848}\VersionIndependentProgID",,,"igfxdv32.CUIDriver"
;
;igfxTMM.dll self registration entries
;
HKCR,"igfxTMM.CloneViewHelper",,,"CloneViewHelper Class"
HKCR,"igfxTMM.CloneViewHelper\CLSID",,,"{6C4BE3D5-831A-42ED-AA62-2AEB34C8CBA4}"
HKCR,"igfxTMM.CloneViewHelper\CurVer",,,"igfxTMM.CloneViewHelper.1"
HKCR,"igfxTMM.CloneViewHelper.1",,,"CloneViewHelper Class"
HKCR,"igfxTMM.CloneViewHelper.1\CLSID",,,"{6C4BE3D5-831A-42ED-AA62-2AEB34C8CBA4}"
HKCR,"CLSID\{6C4BE3D5-831A-42ED-AA62-2AEB34C8CBA4}",,,"CloneViewHelper Class"
HKCR,"CLSID\{6C4BE3D5-831A-42ED-AA62-2AEB34C8CBA4}\InProcServer32",,,%11%"\igfxTMM.dll"
HKCR,"CLSID\{6C4BE3D5-831A-42ED-AA62-2AEB34C8CBA4}\InProcServer32","ThreadingModel",,"Both"
HKCR,"CLSID\{6C4BE3D5-831A-42ED-AA62-2AEB34C8CBA4}\ProgID",,,"igfxTMM.CloneViewHelper.1"
HKCR,"CLSID\{6C4BE3D5-831A-42ED-AA62-2AEB34C8CBA4}\TypeLib",,,"{9F7668BC-E163-414C-92C6-01228863FF5A}"
HKCR,"CLSID\{6C4BE3D5-831A-42ED-AA62-2AEB34C8CBA4}\VersionIndependentProgID",,,"igfxTMM.CloneViewHelper"

;igfxTMM entry for enabling ViewHelper Interface
HKLM,"Software\Microsoft\TMM","UseIViewHelper",%REG_DWORD%,1

;
; igfxsrvc.exe self registration entries
;
HKCR,"igfxsrvc.Settings\CLSID",,,"{078AEF33-C48A-49F7-AFF3-A0EE810BFE7C}"
HKCR,"igfxsrvc.Settings\CurVer",,,"igfxsrvc.Settings.1"
HKCR,"igfxsrvc.Settings.1\CLSID",,,"{078AEF33-C48A-49F7-AFF3-A0EE810BFE7C}"
HKCR,"CLSID\{078AEF33-C48A-49F7-AFF3-A0EE810BFE7C}",,,"Settings Class"
HKCR,"CLSID\{078AEF33-C48A-49F7-AFF3-A0EE810BFE7C}\LocalServer32",,,%11%"\igfxsrvc.exe"
HKCR,"CLSID\{078AEF33-C48A-49F7-AFF3-A0EE810BFE7C}\ProgID",,,"igfxsrvc.Settings.1"
HKCR,"CLSID\{078AEF33-C48A-49F7-AFF3-A0EE810BFE7C}\VersionIndependentProgID",,,"igfxsrvc.Settings"
HKCR,"Interface\{916FEC45-8FAB-460F-9BD1-325055E3DEC9}",,,"ISettings"

HKCR,"igfxsrvc.DisplayConfig\CLSID",,,"{C2BFE331-6739-4270-86C9-493D9A04CD38}"
HKCR,"igfxsrvc.DisplayConfig\CurVer",,,"igfxsrvc.DisplayConfig.1"
HKCR,"igfxsrvc.DispayConfig.1\CLSID",,,"{C2BFE331-6739-4270-86C9-493D9A04CD38}"
HKCR,"CLSID\{C2BFE331-6739-4270-86C9-493D9A04CD38}",,,"DisplayConfig Class"
HKCR,"CLSID\{C2BFE331-6739-4270-86C9-493D9A04CD38}\LocalServer32",,,%11%"\igfxsrvc.exe"
HKCR,"CLSID\{C2BFE331-6739-4270-86C9-493D9A04CD38}\ProgID",,,"igfxsrvc.DisplayConfig.1"
HKCR,"CLSID\{C2BFE331-6739-4270-86C9-493D9A04CD38}\VersionIndependentProgID",,,"igfxsrvc.DisplayConfig"
HKCR,"Interface\{DC61FD6D-FB60-4ABC-BF2E-4DF75C90C601}",,,"IDisplayConfig" 

HKCR,"igfxsrvc.EDID\CLSID",,,"{40CB6EA0-AB2A-45F8-BA45-2DC7756A7B49}"
HKCR,"igfxsrvc.EDID\CurVer",,,"igfxsrvc.EDID.1"
HKCR,"igfx.EDID.1\CLSID",,,"{40CB6EA0-AB2A-45F8-BA45-2DC7756A7B49}"
HKCR,"CLSID\{40CB6EA0-AB2A-45F8-BA45-2DC7756A7B49}",,,"EDID Class"
HKCR,"CLSID\{40CB6EA0-AB2A-45F8-BA45-2DC7756A7B49}\LocalServer32",,,%11%"\igfxsrvc.exe"
HKCR,"CLSID\{40CB6EA0-AB2A-45F8-BA45-2DC7756A7B49}\ProgID",,,"igfxsrvc.EDID.1"
HKCR,"CLSID\{40CB6EA0-AB2A-45F8-BA45-2DC7756A7B49}\VersionIndependentProgID",,,"igfxsrvc.EDID"
HKCR,"Interface\{B7C4F4C9-EE21-4042-9C11-BEA5E039B1F9}",,,"IEDID"

HKCR,"igfxsrvc.Color\CLSID",,,"{FE9617F6-E606-42AA-BECC-0E9CDA246D63}"
HKCR,"igfxsrvc.Color\CurVer",,,"igfxsrvc.Color.1"
HKCR,"igfx.Color.1\CLSID",,,"{FE9617F6-E606-42AA-BECC-0E9CDA246D63}"
HKCR,"CLSID\{FE9617F6-E606-42AA-BECC-0E9CDA246D63}",,,"Color Class"
HKCR,"CLSID\{FE9617F6-E606-42AA-BECC-0E9CDA246D63}\LocalServer32",,,%11%"\igfxsrvc.exe"
HKCR,"CLSID\{FE9617F6-E606-42AA-BECC-0E9CDA246D63}\ProgID",,,"igfxsrvc.Color.1"
HKCR,"CLSID\{FE9617F6-E606-42AA-BECC-0E9CDA246D63}\VersionIndependentProgID",,,"igfxsrvc.Color"
HKCR,"Interface\{63CDDDB9-A85B-411E-AA78-101B3BC17261}",,,"IColor"

HKCR,"igfxsrvc.CUIService",,,"CUIService Class"
HKCR,"igfxsrvc.CUIService\CLSID",,,"{0F195FA1-CCF0-11D2-8B20-00A0C93CB1F4}"
HKCR,"igfxsrvc.CUIService\CurVer",,,"igfxsrvc.CUIService.1"
HKCR,"igfxsrvc.CUIService.1",,,"CUIService Class"
HKCR,"igfx.CUIService.1\CLSID",,,"{0F195FA1-CCF0-11D2-8B20-00A0C93CB1F4}"
HKCR,"CLSID\{0F195FA1-CCF0-11D2-8B20-00A0C93CB1F4}",,,"CUIService Class"
HKCR,"CLSID\{0F195FA1-CCF0-11D2-8B20-00A0C93CB1F4}\InProcServer32",,,%11%"\igfxsrvc.exe"
HKCR,"CLSID\{0F195FA1-CCF0-11D2-8B20-00A0C93CB1F4}\InProcServer32","ThreadingModel",,"Apartment"
HKCR,"CLSID\{0F195FA1-CCF0-11D2-8B20-00A0C93CB1F4}\ProgID",,,"igfxsrvc.CUIService.1"
HKCR,"CLSID\{0F195FA1-CCF0-11D2-8B20-00A0C93CB1F4}\VersionIndependentProgID",,,"igfxsrvc.CUIService"

HKCR,"igfxsrvc.CUIPower\CLSID",,,"{C332C124-340D-4430-AA0D-C75602876FCC}"
HKCR,"igfxsrvc.CUIPower\CurVer",,,"igfxsrvc.CUIPower.1"
HKCR,"igfx.CUIPower.1\CLSID",,,"{C332C124-340D-4430-AA0D-C75602876FCC}"
HKCR,"CLSID\{C332C124-340D-4430-AA0D-C75602876FCC}",,,"CUIPower Class"
HKCR,"CLSID\{C332C124-340D-4430-AA0D-C75602876FCC}\LocalServer32",,,%11%"\igfxsrvc.exe"
HKCR,"CLSID\{C332C124-340D-4430-AA0D-C75602876FCC}\ProgID",,,"igfxsrvc.CUIPower.1"
HKCR,"CLSID\{C332C124-340D-4430-AA0D-C75602876FCC}\VersionIndependentProgID",,,"igfxsrvc.CUIPower"
HKCR,"Interface\{299D88F9-2CBD-4225-BF19-FCD164C54C3F}",,,"ICUIPower"

HKCR,"igfxsrvc.MCCS\CLSID",,,"{999276E0-DA71-4743-8F02-0AB0A2D65558}"
HKCR,"igfxsrvc.MCCS\CurVer",,,"igfxsrvc.MCCS.1"
HKCR,"igfx.MCCS.1\CLSID",,,"{999276E0-DA71-4743-8F02-0AB0A2D65558}"
HKCR,"CLSID\{999276E0-DA71-4743-8F02-0AB0A2D65558}",,,"MCCS Class"
HKCR,"CLSID\{999276E0-DA71-4743-8F02-0AB0A2D65558}\LocalServer32",,,%11%"\igfxsrvc.exe"
HKCR,"CLSID\{999276E0-DA71-4743-8F02-0AB0A2D65558}\ProgID",,,"igfxsrvc.MCCS.1"
HKCR,"CLSID\{999276E0-DA71-4743-8F02-0AB0A2D65558}\VersionIndependentProgID",,,"igfxsrvc.MCCS"
HKCR,"Interface\{D80D344A-0CCD-4B2F-B379-56DE3EC2C4D1}",,,"IMCCS"

HKCR,"igfxsrvc.OpenGL\CLSID",,,"{DCB2D492-5F4F-4378-8FF4-DA87062D42E3}"
HKCR,"igfxsrvc.OpenGL\CurVer",,,"igfxsrvc.OpenGL.1"
HKCR,"igfx.OpenGL.1\CLSID",,,"{DCB2D492-5F4F-4378-8FF4-DA87062D42E3}"
HKCR,"CLSID\{DCB2D492-5F4F-4378-8FF4-DA87062D42E3}",,,"OpenGL Class"
HKCR,"CLSID\{DCB2D492-5F4F-4378-8FF4-DA87062D42E3}\LocalServer32",,,%11%"\igfxsrvc.exe"
HKCR,"CLSID\{DCB2D492-5F4F-4378-8FF4-DA87062D42E3}\ProgID",,,"igfxsrvc.OpenGL.1"
HKCR,"CLSID\{DCB2D492-5F4F-4378-8FF4-DA87062D42E3}\VersionIndependentProgID",,,"igfxsrvc.OpenGL"
HKCR,"Interface\{965FD393-C149-45F1-863C-402C4E2E38C5}",,,"IOpenGL"

HKCR,"igfxsrvc.Overlay\CLSID",,,"{016B931D-8430-4988-8510-C69C214CFF32}"
HKCR,"igfxsrvc.Overlay\CurVer",,,"igfxsrvc.Overlay.1"
HKCR,"igfx.Overlay.1\CLSID",,,"{016B931D-8430-4988-8510-C69C214CFF32}"
HKCR,"CLSID\{016B931D-8430-4988-8510-C69C214CFF32}",,,"Overlay Class"
HKCR,"CLSID\{016B931D-8430-4988-8510-C69C214CFF32}\LocalServer32",,,%11%"\igfxsrvc.exe"
HKCR,"CLSID\{016B931D-8430-4988-8510-C69C214CFF32}\ProgID",,,"igfxsrvc.Overlay.1"
HKCR,"CLSID\{016B931D-8430-4988-8510-C69C214CFF32}\VersionIndependentProgID",,,"igfxsrvc.Overlay"
HKCR,"Interface\{25824158-68E7-4A6F-A2FD-F6AD1D6845D4}",,,"IOverlay"

HKCR,"igfxsrvc.Rotation\CLSID",,,"{9B908879-E03F-4D0C-ACB3-9065B1155460}"
HKCR,"igfxsrvc.Rotation\CurVer",,,"igfxsrvc.Rotation.1"
HKCR,"igfx.Rotation.1\CLSID",,,"{9B908879-E03F-4D0C-ACB3-9065B1155460}"
HKCR,"CLSID\{9B908879-E03F-4D0C-ACB3-9065B1155460}",,,"Rotation Class"
HKCR,"CLSID\{9B908879-E03F-4D0C-ACB3-9065B1155460}\LocalServer32",,,%11%"\igfxsrvc.exe"
HKCR,"CLSID\{9B908879-E03F-4D0C-ACB3-9065B1155460}\ProgID",,,"igfxsrvc.Rotation.1"
HKCR,"CLSID\{9B908879-E03F-4D0C-ACB3-9065B1155460}\VersionIndependentProgID",,,"igfxsrvc.Rotation"
HKCR,"Interface\{72DC5954-069D-43C4-9B8B-19B59269DC74}",,,"IRotation"

HKCR,"igfxsrvc.Scheme\CLSID",,,"{C071C982-2EB2-4D3A-9821-E4B31B0142C8}"
HKCR,"igfxsrvc.Scheme\CurVer",,,"igfxsrvc.Scheme.1"
HKCR,"igfx.Scheme.1\CLSID",,,"{C071C982-2EB2-4D3A-9821-E4B31B0142C8}"
HKCR,"CLSID\{C071C982-2EB2-4D3A-9821-E4B31B0142C8}",,,"Scheme Class"
HKCR,"CLSID\{C071C982-2EB2-4D3A-9821-E4B31B0142C8}\LocalServer32",,,%11%"\igfxsrvc.exe"
HKCR,"CLSID\{C071C982-2EB2-4D3A-9821-E4B31B0142C8}\ProgID",,,"igfxsrvc.Scheme.1"
HKCR,"CLSID\{C071C982-2EB2-4D3A-9821-E4B31B0142C8}\VersionIndependentProgID",,,"igfxsrvc.Scheme"
HKCR,"Interface\{D5393CA5-EF8F-49E0-B180-212C903C652C}",,,"IScheme"

HKCR,"igfxsrvc.TVParam\CLSID",,,"{12E3793C-7C3C-4C00-BC4E-C79849B3F430}"
HKCR,"igfxsrvc.TVParam\CurVer",,,"igfxsrvc.TVParam.1"
HKCR,"igfx.TVParam.1\CLSID",,,"{12E3793C-7C3C-4C00-BC4E-C79849B3F430}"
HKCR,"CLSID\{12E3793C-7C3C-4C00-BC4E-C79849B3F430}",,,"TVParam Class"
HKCR,"CLSID\{12E3793C-7C3C-4C00-BC4E-C79849B3F430}\LocalServer32",,,%11%"\igfxsrvc.exe"
HKCR,"CLSID\{12E3793C-7C3C-4C00-BC4E-C79849B3F430}\ProgID",,,"igfxsrvc.TVParam.1"
HKCR,"CLSID\{12E3793C-7C3C-4C00-BC4E-C79849B3F430}\VersionIndependentProgID",,,"igfxsrvc.TVParam"
HKCR,"Interface\{DDA11344-AB20-4AEC-94C4-6AA091574CD0}",,,"ITVParam"
;
;proxy stub for igfxsrvc.exe
;
HKCR,"CLSID\{DDA11344-AB20-4AEC-94C4-6AA091574CD0}",,,"PSFactoryBuffer"
HKCR,"CLSID\{DDA11344-AB20-4AEC-94C4-6AA091574CD0}\InProcServer32",,,%11%"\igfxsrvc.dll"
HKCR,"CLSID\{DDA11344-AB20-4AEC-94C4-6AA091574CD0}\InProcServer32","ThreadingModel",,"Both"

HKCR,"Interface\{DDA11344-AB20-4AEC-94C4-6AA091574CD0}",,,"ITVParam"
HKCR,"Interface\{DDA11344-AB20-4AEC-94C4-6AA091574CD0}\ProxyStubClsid32",,,"{DDA11344-AB20-4AEC-94C4-6AA091574CD0}"
HKCR,"Interface\{DDA11344-AB20-4AEC-94C4-6AA091574CD0}\NumMethods",,,"9"

HKCR,"Interface\{916FEC45-8FAB-460F-9BD1-325055E3DEC9}",,,"ISettings"
HKCR,"Interface\{916FEC45-8FAB-460F-9BD1-325055E3DEC9}\ProxyStubClsid32",,,"{DDA11344-AB20-4AEC-94C4-6AA091574CD0}"
HKCR,"Interface\{916FEC45-8FAB-460F-9BD1-325055E3DEC9}\NumMethods",,,"13"

HKCR,"Interface\{D5393CA5-EF8F-49E0-B180-212C903C652C}",,,"IScheme"
HKCR,"Interface\{D5393CA5-EF8F-49E0-B180-212C903C652C}\ProxyStubClsid32",,,"{DDA11344-AB20-4AEC-94C4-6AA091574CD0}"
HKCR,"Interface\{D5393CA5-EF8F-49E0-B180-212C903C652C}\NumMethods",,,"7"

HKCR,"Interface\{72DC5954-069D-43C4-9B8B-19B59269DC74}",,,"IRotation"
HKCR,"Interface\{72DC5954-069D-43C4-9B8B-19B59269DC74}\ProxyStubClsid32",,,"{DDA11344-AB20-4AEC-94C4-6AA091574CD0}"
HKCR,"Interface\{72DC5954-069D-43C4-9B8B-19B59269DC74}\NumMethods",,,"9"

HKCR,"Interface\{25824158-68E7-4A6F-A2FD-F6AD1D6845D4}",,,"IOverlay"
HKCR,"Interface\{25824158-68E7-4A6F-A2FD-F6AD1D6845D4}\ProxyStubClsid32",,,"{DDA11344-AB20-4AEC-94C4-6AA091574CD0}"
HKCR,"Interface\{25824158-68E7-4A6F-A2FD-F6AD1D6845D4}\NumMethods",,,"13"

HKCR,"Interface\{965FD393-C149-45F1-863C-402C4E2E38C5}",,,"IOpenGL"
HKCR,"Interface\{965FD393-C149-45F1-863C-402C4E2E38C5}\ProxyStubClsid32",,,"{DDA11344-AB20-4AEC-94C4-6AA091574CD0}"
HKCR,"Interface\{965FD393-C149-45F1-863C-402C4E2E38C5}\NumMethods",,,"7"

HKCR,"Interface\{D80D344A-0CCD-4B2F-B379-56DE3EC2C4D1}",,,"IMCCS"
HKCR,"Interface\{D80D344A-0CCD-4B2F-B379-56DE3EC2C4D1}\ProxyStubClsid32",,,"{DDA11344-AB20-4AEC-94C4-6AA091574CD0}"
HKCR,"Interface\{D80D344A-0CCD-4B2F-B379-56DE3EC2C4D1}\NumMethods",,,"9"

HKCR,"Interface\{B7C4F4C9-EE21-4042-9C11-BEA5E039B1F9}",,,"IEDID"
HKCR,"Interface\{B7C4F4C9-EE21-4042-9C11-BEA5E039B1F9}\ProxyStubClsid32",,,"{DDA11344-AB20-4AEC-94C4-6AA091574CD0}"
HKCR,"Interface\{B7C4F4C9-EE21-4042-9C11-BEA5E039B1F9}\NumMethods",,,"12"

HKCR,"Interface\{DC61FD6D-FB60-4ABC-BF2E-4DF75C90C601}",,,"IDisplayConfig"
HKCR,"Interface\{DC61FD6D-FB60-4ABC-BF2E-4DF75C90C601}\ProxyStubClsid32",,,"{DDA11344-AB20-4AEC-94C4-6AA091574CD0}"
HKCR,"Interface\{DC61FD6D-FB60-4ABC-BF2E-4DF75C90C601}\NumMethods",,,"15"

HKCR,"Interface\{299D88F9-2CBD-4225-BF19-FCD164C54C3F}",,,"ICUIPower"
HKCR,"Interface\{299D88F9-2CBD-4225-BF19-FCD164C54C3F}\ProxyStubClsid32",,,"{DDA11344-AB20-4AEC-94C4-6AA091574CD0}"
HKCR,"Interface\{299D88F9-2CBD-4225-BF19-FCD164C54C3F}\NumMethods",,,"7"

HKCR,"Interface\{63CDDDB9-A85B-411E-AA78-101B3BC17261}",,,"IColor"
HKCR,"Interface\{63CDDDB9-A85B-411E-AA78-101B3BC17261}\ProxyStubClsid32",,,"{DDA11344-AB20-4AEC-94C4-6AA091574CD0}"
HKCR,"Interface\{63CDDDB9-A85B-411E-AA78-101B3BC17261}\NumMethods",,,"14"
;
; igfxpph.dll self registration entries
;
HKCR,"igfxpph.GraphicsShellExt",,,"GraphicsShellExt Class"
HKCR,"igfxpph.GraphicsShellExt\CLSID",,,"{3AB1675A-CCFF-11D2-8B20-00A0C93CB1F4}"
HKCR,"igfxpph.GraphicsShellExt\CurVer",,,"igfxpph.GraphicsShellExt.1"
HKCR,"igfxpph.GraphicsShellExt.1",,,"GraphicsShellExt Class"
HKCR,"igfxpph.GraphicsShellExt.1\CLSID",,,"{3AB1675A-CCFF-11D2-8B20-00A0C93CB1F4}"
HKCR,"CLSID\{3AB1675A-CCFF-11D2-8B20-00A0C93CB1F4}",,,"GraphicsShellExt Class"
HKCR,"CLSID\{3AB1675A-CCFF-11D2-8B20-00A0C93CB1F4}\InProcServer32",,,%11%"\igfxpph.dll"
HKCR,"CLSID\{3AB1675A-CCFF-11D2-8B20-00A0C93CB1F4}\InProcServer32","ThreadingModel",,"Apartment"
HKCR,"CLSID\{3AB1675A-CCFF-11D2-8B20-00A0C93CB1F4}\ProgID",,,"igfxpph.GraphicsShellExt.1"
HKCR,"CLSID\{3AB1675A-CCFF-11D2-8B20-00A0C93CB1F4}\VersionIndependentProgID",,,"igfxpph.GraphicsShellExt"
HKCR,"CLSID\{3AB1675A-CCFF-11D2-8B20-00A0C93CB1F4}\Programmable",,,
;
; igfxeud.dll self registration entries
;
;HKCR,"igfxeud.EndUserShellExt",,,"EndUserShellExt Class"
;HKCR,"igfxeud.EndUserShellExt\CLSID",,,"{3AB167A5-CCFF-11D2-8B20-00A0C93CB1F4}"
;HKCR,"igfxeud.EndUserShellExt\CurVer",,,"igfxeud.EndUserShellExt.1"
;HKCR,"igfxeud.EndUserShellExt.1",,,"EndUserShellExt Class"
;HKCR,"igfxeud.EndUserShellExt.1\CLSID",,,"{3AB167A5-CCFF-11D2-8B20-00A0C93CB1F4}"
;HKCR,"CLSID\{3AB167A5-CCFF-11D2-8B20-00A0C93CB1F4}",,,"EndUserShellExt Class"
;HKCR,"CLSID\{3AB167A5-CCFF-11D2-8B20-00A0C93CB1F4}\InProcServer32",,,%11%"\igfxeud.dll"
;HKCR,"CLSID\{3AB167A5-CCFF-11D2-8B20-00A0C93CB1F4}\InProcServer32","ThreadingModel",,"Apartment"
;HKCR,"CLSID\{3AB167A5-CCFF-11D2-8B20-00A0C93CB1F4}\ProgID",,,"igfxeud.EndUserShellExt.1"
;HKCR,"CLSID\{3AB167A5-CCFF-11D2-8B20-00A0C93CB1F4}\VersionIndependentProgID",,,"igfxeud.EndUserShellExt"
;HKCR,"CLSID\{3AB167A5-CCFF-11D2-8B20-00A0C93CB1F4}\Programmable",,,

; Igfxdo.dll self registration entries
;
HKCR,"Igfxdo.DataObject",,,"DataObject Class"
HKCR,"Igfxdo.DataObject\CLSID",,,"{D4FA3D4E-BE69-11D4-AA30-00902704C6BF}"
HKCR,"Igfxdo.DataObject\CurVer",,,"Igfxdo.DataObject.1"
HKCR,"Igfxdo.DataObject.1",,,"DataObject Class"
HKCR,"Igfxdo.DataObject.1\CLSID",,,"{D4FA3D4E-BE69-11D4-AA30-00902704C6BF}"
HKCR,"CLSID\{D4FA3D4E-BE69-11D4-AA30-00902704C6BF}",,,"DataObject Class"
HKCR,"CLSID\{D4FA3D4E-BE69-11D4-AA30-00902704C6BF}\InProcServer32",,,%11%"\igfxdo.dll"
HKCR,"CLSID\{D4FA3D4E-BE69-11D4-AA30-00902704C6BF}\InProcServer32","ThreadingModel",,"Apartment"
HKCR,"CLSID\{D4FA3D4E-BE69-11D4-AA30-00902704C6BF}\ProgID",,,"Igfxdo.DataObject.1"
HKCR,"CLSID\{D4FA3D4E-BE69-11D4-AA30-00902704C6BF}\VersionIndependentProgID",,,"Igfxdo.DataObject"
HKCR,"CLSID\{D4FA3D4E-BE69-11D4-AA30-00902704C6BF}\Programmable",,,

HKCR,"Igfxdo.DataObjectInit",,,"DataObjectInit Class"
HKCR,"Igfxdo.DataObjectInit\CLSID",,,"{4501A903-BF07-11D4-AA30-00902704C6BF}"
HKCR,"Igfxdo.DataObjectInit\CurVer",,,"Igfxdo.DataObjectInit.1"
HKCR,"Igfxdo.DataObjectInit.1",,,"DataObjectInit Class"
HKCR,"Igfxdo.DataObjectInit.1\CLSID",,,"{4501A903-BF07-11D4-AA30-00902704C6BF}"
HKCR,"CLSID\{4501A903-BF07-11D4-AA30-00902704C6BF}",,,"DataObjectInit Class"
HKCR,"CLSID\{4501A903-BF07-11D4-AA30-00902704C6BF}\InProcServer32",,,%11%"\igfxdo.dll"
HKCR,"CLSID\{4501A903-BF07-11D4-AA30-00902704C6BF}\InProcServer32","ThreadingModel",,"Apartment"
HKCR,"CLSID\{4501A903-BF07-11D4-AA30-00902704C6BF}\ProgID",,,"Igfxdo.DataObjectInit.1"
HKCR,"CLSID\{4501A903-BF07-11D4-AA30-00902704C6BF}\VersionIndependentProgID",,,"Igfxdo.DataObjectInit"
HKCR,"CLSID\{4501A903-BF07-11D4-AA30-00902704C6BF}\Programmable",,,
;
; igfxtray.exe execution on startup
;
HKLM,Software\Microsoft\Windows\CurrentVersion\Run,IgfxTray,,%11%"\igfxtray.exe"
HKLM,Software\Microsoft\Windows\CurrentVersion\Run,HotKeysCmds,,%11%"\hkcmd.exe"
HKLM,Software\Microsoft\Windows\CurrentVersion\Run,Persistence,,%11%"\igfxpers.exe"
;
;
; Entries for receiving winlogon unlock event
;
HKLM,"SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon\Notify\igfxcui","DLLName",%REG_SZ%,"igfxdev.dll"
HKLM,"SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon\Notify\igfxcui","Asynchronous",%REG_DWORD%,1
HKLM,"SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon\Notify\igfxcui","Impersonate",%REG_DWORD%,1
HKLM,"SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon\Notify\igfxcui","Unlock",%REG_SZ%,"WinlogonUnlockEvent"

; Disable Hot Key action 
;HKLM,"%CUIDeviceIndependentKey%\igfxsrvc\resources","2658",,"Disable"

;Hide Custom Mode Blade
;HKLM,"%CUIDeviceIndependentKey%\igfxcfg\resources","MainWindowDisplayCustomModes",,""

[CUISDK.AddReg]
;
; igfxext.exe self registration entries
;
HKCR,"IgfxExt.CUIExternal\CLSID",,,"{7160A13D-73DA-4CEA-95B9-37356478588A}"
HKCR,"IgfxExt.CUIExternal\CurVer",,,"IgfxExt.CUIExternal.1"
HKCR,"IgfxExt.CUIExternal.1\CLSID",,,"{7160A13D-73DA-4CEA-95B9-37356478588A}"
HKCR,"CLSID\{7160A13D-73DA-4CEA-95B9-37356478588A}",,,"CUIExternal Class"
HKCR,"CLSID\{7160A13D-73DA-4CEA-95B9-37356478588A}\LocalServer32",,,%11%"\igfxext.exe"
HKCR,"CLSID\{7160A13D-73DA-4CEA-95B9-37356478588A}\ProgID",,,"IgfxExt.CUIExternal.1"
HKCR,"CLSID\{7160A13D-73DA-4CEA-95B9-37356478588A}\VersionIndependentProgID",,,"IgfxExt.CUIExternal"
;

;
;proxy stub for igfxext.exe (igfxexps.dll)
;
HKCR,"CLSID\{27E7234F-429F-4787-AC8F-8AADDED01355}",,,"PSFactoryBuffer"
HKCR,"CLSID\{27E7234F-429F-4787-AC8F-8AADDED01355}\InProcServer32",,,%11%"\IGFXEXPS.DLL"
HKCR,"CLSID\{27E7234F-429F-4787-AC8F-8AADDED01355}\InProcServer32","ThreadingModel",,"Both"

HKCR,"Interface\{F4C4B98D-F59E-4a0c-AEE9-801E0CDB671E}",,,"ICUIExtClientNotify"
HKCR,"Interface\{F4C4B98D-F59E-4a0c-AEE9-801E0CDB671E}\ProxyStubClsid32",,,"{27E7234F-429F-4787-AC8F-8AADDED01355}"
HKCR,"Interface\{F4C4B98D-F59E-4a0c-AEE9-801E0CDB671E}\NumMethods",,,"1"

HKCR,"Interface\{27E7234F-429F-4787-AC8F-8AADDED01355}",,,"ICUIExternal2"
HKCR,"Interface\{27E7234F-429F-4787-AC8F-8AADDED01355}\ProxyStubClsid32",,,"{27E7234F-429F-4787-AC8F-8AADDED01355}"
HKCR,"Interface\{27E7234F-429F-4787-AC8F-8AADDED01355}\NumMethods",,,"8"

HKCR,"Interface\{70F8C65F-06AA-443b-9E6B-7C73808F07E5}",,,"ICUIExternal3"
HKCR,"Interface\{70F8C65F-06AA-443b-9E6B-7C73808F07E5}\ProxyStubClsid32",,,"{27E7234F-429F-4787-AC8F-8AADDED01355}"
HKCR,"Interface\{70F8C65F-06AA-443b-9E6B-7C73808F07E5}\NumMethods",,,"2"

HKCR,"Interface\{3473E05A-3317-4df5-9098-E5387C94D1B0}",,,"ICUIExternalDual"
HKCR,"Interface\{3473E05A-3317-4df5-9098-E5387C94D1B0}\ProxyStubClsid32",,,"{27E7234F-429F-4787-AC8F-8AADDED01355}"
HKCR,"Interface\{3473E05A-3317-4df5-9098-E5387C94D1B0}\NumMethods",,,"0"

HKCR,"Interface\{5DC5B31E-0C28-4679-B8D8-32CF2F9BACED}",,,"ICUIExternal4"
HKCR,"Interface\{5DC5B31E-0C28-4679-B8D8-32CF2F9BACED}\ProxyStubClsid32",,,"{27E7234F-429F-4787-AC8F-8AADDED01355}"
HKCR,"Interface\{5DC5B31E-0C28-4679-B8D8-32CF2F9BACED}\NumMethods",,,"7"

HKCR,"Interface\{A05C525D-B4CB-4108-BFF7-1ACF1A14F00A}",,,"ICUIExternal5"
HKCR,"Interface\{A05C525D-B4CB-4108-BFF7-1ACF1A14F00A}\ProxyStubClsid32",,,"{27E7234F-429F-4787-AC8F-8AADDED01355}"
HKCR,"Interface\{A05C525D-B4CB-4108-BFF7-1ACF1A14F00A}\NumMethods",,,"5"

HKCR,"Interface\{AFB6489F-4515-44AA-8DF7-ED28EA46283C}",,,"ICUIExternal6"
HKCR,"Interface\{AFB6489F-4515-44AA-8DF7-ED28EA46283C}\ProxyStubClsid32",,,"{27E7234F-429F-4787-AC8F-8AADDED01355}"
HKCR,"Interface\{AFB6489F-4515-44AA-8DF7-ED28EA46283C}\NumMethods",,,"12"

HKCR,"Interface\{2CED2F89-627B-4E5D-840F-B126EE858CD8}",,,"ICUIExternal7"
HKCR,"Interface\{2CED2F89-627B-4E5D-840F-B126EE858CD8}\ProxyStubClsid32",,,"{27E7234F-429F-4787-AC8F-8AADDED01355}"
HKCR,"Interface\{2CED2F89-627B-4E5D-840F-B126EE858CD8}\NumMethods",,,"2"

HKCR,"Interface\{F932C038-6484-45ca-8FA1-7C8C279F7AEE}",,,"ICUIExternal8"
HKCR,"Interface\{F932C038-6484-45ca-8FA1-7C8C279F7AEE}\ProxyStubClsid32",,,"{27E7234F-429F-4787-AC8F-8AADDED01355}"
HKCR,"Interface\{F932C038-6484-45ca-8FA1-7C8C279F7AEE}\NumMethods",,,"2"

HKLM,"Software\Classes\Interface\{86709F66-89C5-4b19-A83F-E4995E21599A}",,,"ICUIDownScale"
HKLM,"Software\Classes\Interface\{86709F66-89C5-4b19-A83F-E4995E21599A}\ProxyStubClsid32",,,"{27E7234F-429F-4787-AC8F-8AADDED01355}"
HKLM,"Software\Classes\Interface\{86709F66-89C5-4b19-A83F-E4995E21599A}\NumMethods",,,"4"
;
;proxy stub for igfxext32.exe (igfxexps32.dll)
;
HKLM,"Software\Wow6432Node\Classes\CLSID\{27E7234F-429F-4787-AC8F-8AADDED01355}",,,"PSFactoryBuffer"
HKLM,"Software\Wow6432Node\Classes\CLSID\{27E7234F-429F-4787-AC8F-8AADDED01355}\InProcServer32",,,%10%\SysWOW64"\igfxexps32.DLL"
HKLM,"Software\Wow6432Node\Classes\CLSID\{27E7234F-429F-4787-AC8F-8AADDED01355}\InProcServer32","ThreadingModel",,"Both"

HKLM,"Software\Wow6432Node\Classes\Interface\{F4C4B98D-F59E-4a0c-AEE9-801E0CDB671E}",,,"ICUIExtClientNotify"
HKLM,"Software\Wow6432Node\Classes\Interface\{F4C4B98D-F59E-4a0c-AEE9-801E0CDB671E}\ProxyStubClsid32",,,"{27E7234F-429F-4787-AC8F-8AADDED01355}"
HKLM,"Software\Wow6432Node\Classes\Interface\{F4C4B98D-F59E-4a0c-AEE9-801E0CDB671E}\NumMethods",,,"1"

HKLM,"Software\Wow6432Node\Classes\Interface\{27E7234F-429F-4787-AC8F-8AADDED01355}",,,"ICUIExternal2"
HKLM,"Software\Wow6432Node\Classes\Interface\{27E7234F-429F-4787-AC8F-8AADDED01355}\ProxyStubClsid32",,,"{27E7234F-429F-4787-AC8F-8AADDED01355}"
HKLM,"Software\Wow6432Node\Classes\Interface\{27E7234F-429F-4787-AC8F-8AADDED01355}\NumMethods",,,"8"

HKLM,"Software\Wow6432Node\Classes\Interface\{70F8C65F-06AA-443b-9E6B-7C73808F07E5}",,,"ICUIExternal3"
HKLM,"Software\Wow6432Node\Classes\Interface\{70F8C65F-06AA-443b-9E6B-7C73808F07E5}\ProxyStubClsid32",,,"{27E7234F-429F-4787-AC8F-8AADDED01355}"
HKLM,"Software\Wow6432Node\Classes\Interface\{70F8C65F-06AA-443b-9E6B-7C73808F07E5}\NumMethods",,,"2"

HKLM,"Software\Wow6432Node\Classes\Interface\{3473E05A-3317-4df5-9098-E5387C94D1B0}",,,"ICUIExternalDual"
HKLM,"Software\Wow6432Node\Classes\Interface\{3473E05A-3317-4df5-9098-E5387C94D1B0}\ProxyStubClsid32",,,"{27E7234F-429F-4787-AC8F-8AADDED01355}"
HKLM,"Software\Wow6432Node\Classes\Interface\{3473E05A-3317-4df5-9098-E5387C94D1B0}\NumMethods",,,"0"

HKLM,"Software\Wow6432Node\Classes\Interface\{5DC5B31E-0C28-4679-B8D8-32CF2F9BACED}",,,"ICUIExternal4"
HKLM,"Software\Wow6432Node\Classes\Interface\{5DC5B31E-0C28-4679-B8D8-32CF2F9BACED}\ProxyStubClsid32",,,"{27E7234F-429F-4787-AC8F-8AADDED01355}"
HKLM,"Software\Wow6432Node\Classes\Interface\{5DC5B31E-0C28-4679-B8D8-32CF2F9BACED}\NumMethods",,,"7"

HKLM,"Software\Wow6432Node\Classes\Interface\{A05C525D-B4CB-4108-BFF7-1ACF1A14F00A}",,,"ICUIExternal5"
HKLM,"Software\Wow6432Node\Classes\Interface\{A05C525D-B4CB-4108-BFF7-1ACF1A14F00A}\ProxyStubClsid32",,,"{27E7234F-429F-4787-AC8F-8AADDED01355}"
HKLM,"Software\Wow6432Node\Classes\Interface\{A05C525D-B4CB-4108-BFF7-1ACF1A14F00A}\NumMethods",,,"5"

HKLM,"Software\Wow6432Node\Classes\Interface\{AFB6489F-4515-44AA-8DF7-ED28EA46283C}",,,"ICUIExternal6"
HKLM,"Software\Wow6432Node\Classes\Interface\{AFB6489F-4515-44AA-8DF7-ED28EA46283C}\ProxyStubClsid32",,,"{27E7234F-429F-4787-AC8F-8AADDED01355}"
HKLM,"Software\Wow6432Node\Classes\Interface\{AFB6489F-4515-44AA-8DF7-ED28EA46283C}\NumMethods",,,"12"

HKLM,"Software\Wow6432Node\Classes\Interface\{2CED2F89-627B-4E5D-840F-B126EE858CD8}",,,"ICUIExternal7"
HKLM,"Software\Wow6432Node\Classes\Interface\{2CED2F89-627B-4E5D-840F-B126EE858CD8}\ProxyStubClsid32",,,"{27E7234F-429F-4787-AC8F-8AADDED01355}"
HKLM,"Software\Wow6432Node\Classes\Interface\{2CED2F89-627B-4E5D-840F-B126EE858CD8}\NumMethods",,,"2"

HKLM,"Software\Wow6432Node\Classes\Interface\{F932C038-6484-45ca-8FA1-7C8C279F7AEE}",,,"ICUIExternal8"
HKLM,"Software\Wow6432Node\Classes\Interface\{F932C038-6484-45ca-8FA1-7C8C279F7AEE}\ProxyStubClsid32",,,"{27E7234F-429F-4787-AC8F-8AADDED01355}"
HKLM,"Software\Wow6432Node\Classes\Interface\{F932C038-6484-45ca-8FA1-7C8C279F7AEE}\NumMethods",,,"2"

HKLM,"Software\Wow6432Node\Classes\Interface\{86709F66-89C5-4b19-A83F-E4995E21599A}",,,"ICUIDownScale"
HKLM,"Software\Wow6432Node\Classes\Interface\{86709F66-89C5-4b19-A83F-E4995E21599A}\ProxyStubClsid32",,,"{27E7234F-429F-4787-AC8F-8AADDED01355}"
HKLM,"Software\Wow6432Node\Classes\Interface\{86709F66-89C5-4b19-A83F-E4995E21599A}\NumMethods",,,"4"

[CUISDK.DelReg]
HKR,Igfxext

;  
; End CUI Registry Sections
;
[PowerPlanSettings]
;Intel Graphics Power Plan
Subgroup = {44F3BECA-A7C0-460e-9DF2-BB8B99E0CBA6}, "Intel(R) Graphics Settings", "Configure Intel(R) Graphics Settings"
Setting = {3619C3F2-AFB2-4afc-B0E9-E7FEF372DE36},"Intel(R) Graphics Power Plan", "Configure Intel(R) Graphics Power Plan"

Value = 0, "Maximum Battery Life", "Maximum Battery", %REG_DWORD%, 0
Value = 1, "Balanced", "Balanced", %REG_DWORD%, 1
Value = 2, "Maximum Performance", "Maximum Performance", %REG_DWORD%, 2

Default = %GUID_MAX_POWER_SAVINGS%, %AC%, 0
Default = %GUID_MAX_POWER_SAVINGS%, %DC%, 0
Default = %GUID_TYPICAL_POWER_SAVINGS%, %AC%, 1
Default = %GUID_TYPICAL_POWER_SAVINGS%, %DC%, 1 
Default = %GUID_MIN_POWER_SAVINGS%, %AC%, 2
Default = %GUID_MIN_POWER_SAVINGS%, %DC%, 2

[Strings]

;DPPE
GUID_MAX_POWER_SAVINGS = "{a1841308-3541-4fab-bc81-f71556f20b4a}"
GUID_TYPICAL_POWER_SAVINGS = "{381b4222-f694-41f0-9685-ff5bb260df2e}"
GUID_MIN_POWER_SAVINGS = "{8c5e7fda-e8bf-4a96-9a85-a6e23a8c635c}"
AC = 0
DC = 1

;
; Customizable Strings
;
CUIDeviceIndependentKey="Software\Intel\Display\igfxcui"
DisplayKey="Software\Intel\Display"
CUIDriverOldShareKey="Software\Intel\CUI"

;
; Non-Localizable Strings
;

REG_SZ         = 0x00000000
REG_MULTI_SZ   = 0x00010000
REG_DWORD      = 0x00010001
REG_BINARY     = 0x00000001
SERVICEROOT    = "System\CurrentControlSet\Services"

;
; Localizable Strings
;
DiskId      = "Intel(R) Graphics Media Accelerator Driver for Windows"
Intel       = "Intel Corporation"
iILKGM0     = "Intel(R) HD Graphics"
iILKG0      = "Intel(R) HD Graphics"

;
; Do not modify or copy the following line
; set SIGNING_KEY_VERSION=2
;

