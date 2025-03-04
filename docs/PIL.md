# PIL Memory Region Settings Assignment


## IDP07280 Platform ID Case Study

### Windows Firmware Information

The entire PIL region **allocated** by the UEFI firmware is:

- Start: 0x85C00000
- End: 0x9D600000
- Size: 0x17A00000

(Refer to the section named UEFI Memory Map for more information on how this is defined).

### Subsections of PIL Region:

| FW Name      | CAMERA     | ADSP       | CDSP       | VENUS      | EVA        | IPA        | GFXSUC     | DHMS       | MODEM      | WPSS       |
|--------------|------------|------------|------------|------------|------------|------------|------------|------------|------------|------------|
| Memory Set   | Hardcoded  | PGCM       | PGCM       | PGCM       | PGCM       | PGCM       | PGCM       | PGCM       | PGCM       | PGCM       |
| Memory Start | 0x85C00000 | 0x86100000 | 0x88900000 | 0x8A700000 | 0x8AC00000 | 0x8B100000 | 0x8B110000 | 0x8B200000 | 0x8B800000 | 0x9AE00000 |
| Memory End   | 0x86100000 | 0x88900000 | 0x8A700000 | 0x8AC00000 | 0x8B100000 | 0x8B110000 | 0x8B115000 | 0x8B800000 | 0x9AE00000 | 0x9C700000 |
| Memory Size  | 0x00500000 | 0x02800000 | 0x01E00000 | 0x00500000 | 0x00500000 | 0x00010000 | 0x00005000 | 0x00600000 | 0x0F600000 | 0x01900000 |
| Config       | ACPI, PILE | SUBA, PILE | SUBC, PILE | PILE       | PILE       | PILE       | PILE       | PILE, SUBS | SUBM       | SUBW       |

PGCM area is configured in PILE (qcpilEXT7325) and must match above table allocation plan.

**Below regions are hardcoded in ACPI tables and are therefore not dynamically used by the Operating System**

- CAMERA: Start 0x85C00000, End 0x86100000, Size 0x00500000
   - Defined in ACPI DSDT, Device(VFE0)
   - Defined in \components\QC7325\Extensions\HexagonLoader\PIL\qcpilEXT7325.inf

**Below regions are not hardcoded in ACPI tables / firmware and are therefore dynamically used by the Operating System**

For this kind of region, the PIL driver is instructed the total size of the region in use dynamically below using "PGCM":

- PGCM:	  Start 0x86100000, End 0x9D600000, Size 0x17500000
  - Defined in \components\QC7325\Extensions\HexagonLoader\PIL\qcpilEXT7325.inf

We then define every firmware binary meant to load in such region:

- ADSP:   Start 0x86100000, End 0x88900000, Size 0x02800000
  - Defined in \components\QC7325\Extensions\HexagonLoader\PIL\qcpilEXT7325.inf
  - Defined in \components\QC7325\Extensions\Subsystems\Audio\qcsubsys_ext_adsp7325.inf

- CDSP:   Start 0x88900000, End 0x8A700000, Size 0x01E00000
	- Defined in \components\QC7325\Extensions\HexagonLoader\PIL\qcpilEXT7325.inf
	- Defined in \components\QC7325\Extensions\Subsystems\Compute\qcsubsys_ext_cdsp7325.inf

- VENUS:  Start 0x8A700000, End 0x8AC00000, Size 0x00500000
  - Defined in \components\QC7325\Extensions\HexagonLoader\PIL\qcpilEXT7325.inf

- EVA:    Start 0x8AC00000, End 0x8B100000, Size 0x00500000
  - Defined in \components\QC7325\Extensions\HexagonLoader\PIL\qcpilEXT7325.inf

- IPA:    Start 0x8B100000, End 0x8B110000, Size 0x00010000
  - Defined in \components\QC7325\Extensions\HexagonLoader\PIL\qcpilEXT7325.inf

- GFXSUC: Start 0x8B110000, End 0x8B115000, Size 0x00005000
   - Defined in \components\QC7325\Extensions\HexagonLoader\PIL\qcpilEXT7325.inf

- DHMS:   Start 0x8B200000, End 0x8B800000, Size 0x00600000
	- Defined in \components\QC7325\Extensions\HexagonLoader\PIL\qcpilEXT7325.inf
	- Defined in \components\QC7325\Drivers\Subsystems\CombinedSubsystem\qcsubsys7325.inf

- MODEM:  Start 0x8B800000, End 0x9AE00000, Size 0x0F600000
	- Defined in \components\QC7325\Extensions\Subsystems\Modem\qcsubsys_ext_mpss7325.inf

- WPSS:   Start 0x9AE00000, End 0x9C700000, Size 0x01900000
  - Defined in \components\QC7325\Extensions\WLAN\WPSS\qcwlan_ext_wpss7325.inf

**GAP From 0x9C700000 to 0x9D600000**

We reached the end of the whole reserved region in our UEFI firmware.

---

### INF Packages

\components\QC7325\Extensions\HexagonLoader\PIL\qcpilEXT7325.inf

```ini
; CAMERA registry values
HKR, SubsystemLoad\CAMERA, MemoryAddress,     %REG_DWORD%, 0x85C00000
HKR, SubsystemLoad\CAMERA, MemoryReservation, %REG_DWORD%, 0x00500000
; ADSP registry values
HKR, SubsystemLoad\ADSP, MemoryAddress, %REG_DWORD%, 0x86100000
; Venus registry values
HKR, SubsystemLoad\VENUS, MemoryAddress,     %REG_DWORD%, 0x8A700000
HKR, SubsystemLoad\VENUS, MemoryReservation, %REG_DWORD%, 0x00500000
HKR, SubsystemLoad\VENUS, MemoryAlignment,   %REG_DWORD%, 0
; EVA registry values
HKR, SubsystemLoad\EVA, MemoryAddress,     %REG_DWORD%, 0x8AC00000
HKR, SubsystemLoad\EVA, MemoryReservation, %REG_DWORD%, 0x00500000
; IPA registry values
HKR, SubsystemLoad\IPA, MemoryAddress,     %REG_DWORD%, 0x8B100000
HKR, SubsystemLoad\IPA, MemoryReservation, %REG_DWORD%, 0x00010000
; GFX registry values
HKR, SubsystemLoad\GFXSUC, MemoryAddress,     %REG_DWORD%, 0x8B110000
HKR, SubsystemLoad\GFXSUC, MemoryReservation, %REG_DWORD%, 0x00005000
HKR, SubsystemLoad\GFXSUC, MemoryAlignment,   %REG_DWORD%, 0x00001000
; CDSP registry values
HKR, SubsystemLoad\CDSP, MemoryAddress, %REG_DWORD%, 0x88900000

;DHMS region need to be added as a region under SubsystemLoad like below as we do not want 
;PIL to use or operate on this region which is not managed by PIL by any means.
;DHMS is managed by QSM device of subsys
HKR,SubsystemLoad\DHMS,MemoryAddress,%REG_DWORD%,0x8B200000	
HKR,SubsystemLoad\DHMS,MemoryReservation,%REG_DWORD%,0x00600000
HKR,SubsystemLoad\DHMS,MemoryAlignment,%REG_DWORD%,0x00100000
;0x0 - PIL-Region to be included in PGCM and usable by PIL driver.
;0x1 - PIL-Region to be excluded from PGCM and not-usable by PIL driver.
;0x2 - PIL-Region to be excluded from PGCM and to be returned to HLOS.
HKR,SubsystemLoad\DHMS,MemoryAttribute,%REG_DWORD%,0x1

;Misc
HKR,PilConfig,HypProtectionEnabled,%REG_DWORD%,1
HKR,PilConfig,DoNotReturnMemoryToHLOS,%REG_DWORD%,0

;PGCM
HKR,PGCM,BaseAddress,%REG_DWORD%,0x86100000
HKR,PGCM,Size,%REG_DWORD%,0x17500000

;IMEM - this refers to PIL/reloc.Img.load.Info in ipcat - https://ipcatalog.qualcomm.com/memmap/chip/379/map/1217/version/7307/block/7971925
HKR, IMEM, BaseAddress, %REG_DWORD%, 0x146AA000
HKR, IMEM, Offset,      %REG_DWORD%, 0x94C

```

\components\QC7325\Drivers\Subsystems\CombinedSubsystem\qcsubsys7325.inf

```ini
; Format of MemClientInfo in parser. MemClientInfo can have array of below sequence of data.
; typedef struct _QSM_MEMORYREGION_DESCRIPTOR
; {
;     WCHAR       memoryRegionName[QSM_MAX_LEN_MEMORYREGION_NAME]; // Client name eg: "Diag", "GPS"
;     GUID        memoryRegionId; // NULL GUID indicate no crash-dump for this client
;     ULONG       maxCmaSize; // Max CMA size (not supported), 0 = Use_carveout
;     ULONG       bufferAddr; // Address of the region if Use_carveout = 0, else ignored.
;     ULONG       bufferSize; // Size of the region if Use_carveout = 0, else ignored.
; } QSM_MEMORYREGION_DESCRIPTOR, *PQSM_MEMORYREGION_DESCRIPTOR;
HKR,QSM\DHMSS,"MemClientInfo",%REG_MULTI_SZ%,"Diag","{00000000-0000-0000-0000-000000000000}","0","0x8B200000","0x00600000"
```

\components\QC7325\Extensions\Subsystems\Audio\qcsubsys_ext_adsp7325.inf

```ini
[PIL_Reg_common]
HKR, SubsystemLoad\ADSP, MemoryAlignment, %REG_DWORD%, 0x00100000

[PIL_Reg_MSM]
; ADSP registry values
HKR, SubsystemLoad\ADSP, MemoryReservation, %REG_DWORD%, 0x02800000
```

\components\QC7325\Extensions\Subsystems\Compute\qcsubsys_ext_cdsp7325.inf

```ini
[PIL_Reg_common]
HKR, SubsystemLoad\CDSP, MemoryAlignment, %REG_DWORD%, 0x00100000

[PIL_Reg_MSM]
; CDSP registry values
HKR, SubsystemLoad\CDSP, MemoryReservation, %REG_DWORD%, 0x01e00000

```

\components\QC7325\Extensions\Subsystems\Modem\qcsubsys_ext_mpss7325.inf

```ini
[PIL_Reg_common]
; AMSS registry values
HKR, SubsystemLoad\MODEM, MemoryAlignment, %REG_DWORD%, 0x00400000
HKR, SubsystemLoad\MODEM, MemoryAddress,   %REG_DWORD%, 0x8B800000

[PIL_Reg_MSM]
; AMSS registry values
HKR, SubsystemLoad\MODEM, MemoryReservation, %REG_DWORD%, 0x0f600000
```

\components\QC7325\Extensions\WLAN\WPSS\qcwlan_ext_wpss7325.inf

```ini
[PIL_Reg_common]
HKR, SubsystemLoad\WPSS, MemoryAlignment,   %REG_DWORD%, 0x00100000
HKR, SubsystemLoad\WPSS, MemoryAddress,     %REG_DWORD%, 0x9AE00000
HKR, SubsystemLoad\WPSS, MemoryReservation, %REG_DWORD%, 0x1900000
```

### UEFI Memory Map

```c
/* ... */
{ "GPU PRR",           0x80894000, 0x00001000, AddMem, MEM_RES, WRITE_COMBINEABLE, Reserv, UNCACHED_UNBUFFERED_XN },
/* ... */
{ "MPSS_EFS",          0xA0800000, 0x00300000, AddMem, SYS_MEM, SYS_MEM_CAP, Reserv, UNCACHED_UNBUFFERED_XN },
/* ... */
{ "PIL Reserved",      0x85C00000, 0x17A00000, AddMem, MEM_RES, UNCACHEABLE, Reserv, UNCACHED_UNBUFFERED_XN },
/* ... */
```

### ACPI DSDT

```asl
        Device(VFE0)
        {
            /* ... */
            Method(_CRS, 0x0, NotSerialized)
            {
                Name (RBUF, ResourceTemplate ()
                {
                    /* ... */
                    // CAMERA FW
                    Memory32Fixed (ReadWrite,
                        0x85C00000,         // Address Base
                        0x00500000,         // Address Length
                        )
                    /* ... */
```


### Android Firmware Information

#### Device Tree

```dts
		camera@86200000 {
			no-map;
			reg = <0x00 0x86200000 0x00 0x500000>;
			phandle = <0x293>;
		};

		adsp@86700000 {
			no-map;
			reg = <0x00 0x86700000 0x00 0x2800000>;
			phandle = <0xb4>;
		};

		cdsp@88f00000 {
			no-map;
			reg = <0x00 0x88f00000 0x00 0x1e00000>;
			phandle = <0xb7>;
		};

		adsp_region {
			compatible = "shared-dma-pool";
			alloc-ranges = <0x00 0x00 0x00 0xffffffff>;
			reusable;
			alignment = <0x00 0x400000>;
			size = <0x00 0xc00000>;
			phandle = <0xbe>;
		};

		video@8ad00000 {
			no-map;
			reg = <0x00 0x8ad00000 0x00 0x500000>;
			phandle = <0x26f>;
		};

		cvp@8b200000 {
			no-map;
			reg = <0x00 0x8b200000 0x00 0x500000>;
			phandle = <0x32>;
		};

		ipa_fw@8b700000 {
			no-map;
			reg = <0x00 0x8b700000 0x00 0x10000>;
			phandle = <0x294>;
		};

		ipa_gsi@8b710000 {
			no-map;
			reg = <0x00 0x8b710000 0x00 0xa000>;
			phandle = <0xbf>;
		};

		gpu_micro_code@8b71a000 {
			no-map;
			reg = <0x00 0x8b71a000 0x00 0x2000>;
			phandle = <0x288>;
		};

		mpss@8b800000 {
			no-map;
			reg = <0x00 0x8b800000 0x00 0xf600000>;
			phandle = <0xaf>;
		};

		wlan@9ae00000 {
			no-map;
			reg = <0x00 0x9ae00000 0x00 0x1900000>;
			phandle = <0xa7>;
		};
```

#### XBL

```ini
0x85800000, 0x16F00000, "PIL Reserved",      AddMem, MEM_RES, UNCACHEABLE, Reserv, UNCACHED_UNBUFFERED_XN
```