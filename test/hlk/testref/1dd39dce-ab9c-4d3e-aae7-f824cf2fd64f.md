---
title: WGF11 Precision
description: WGF11 Precision
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 7eb0e3d0-39b8-4fd3-b0a7-9e3cdf4a6295
author: sapaetsc
ms.author: sapaetsc
ms.date: 10/15/17
ms.topic: article
ms.prod: windows-hardware
ms.technology: windows-oem
---

# <span id="p_hlk_test.1dd39dce-ab9c-4d3e-aae7-f824cf2fd64f"></span>WGF11 Precision


This automated test ensures that when shaders specify the minimum partial precision flag (8, 10, or 16-bit) that IHVs do not use a lower precision for calculations. For example, the shader specifies 16-bit but the IHV uses 10-bit.

This topic is applicable to the following test cases:

-   WGF11 Precision

-   WGF11 Precision (WoW64)

-   WGF11 Precision FL9.3

-   WGF11 Precision FL9.3 (WoW64)

>[!NOTE]
>  
Using higher precision than the minimum specified value is valid.

 

## Test details
|||
|---|---|
| **Specifications**  | <ul><li>Device.Graphics.AdapterRender.D3D11PartialPrecision.D3D11CoreE</li></ul> |  
| **Platforms**   | <ul><li>Windows 10, client editions (x86)</li><li>Windows 10, client editions (x64)</li><li>Windows Server 2016 (x64)</li><li>Windows 10, client editions (ARM64)</li></ul> |
| **Supported Releases** | <ul><li>Windows 10</li><li>Windows 10, version 1511</li><li>Windows 10, version 1607</li><li>Windows 10, version 1703</li><li>Windows 10, version 1709</li></ul> |
|**Expected run time (in minutes)**| 2 |
|**Category**| Compatibility |
|**Timeout (in minutes)**| 120 |
|**Requires reboot**| false |
|**Requires special configuration**| false |
|**Type**| automatic |

 

## <span id="Additional_documentation"></span><span id="additional_documentation"></span><span id="ADDITIONAL_DOCUMENTATION"></span>Additional documentation


Tests in this feature area might have additional documentation, including prerequisites, setup, and troubleshooting information, that can be found in the following topic(s):

-   [Device.Graphics additional documentation](device-graphics-additional-documentation.md)

## <span id="Running_the_test"></span><span id="running_the_test"></span><span id="RUNNING_THE_TEST"></span>Running the test


Before you run the test, complete the test setup as described in the test requirements: [Graphic Adapter or Chipset Testing Prerequisites](graphic-adapter-or-chipset-testing-prerequisites.md).

## <span id="Troubleshooting"></span><span id="troubleshooting"></span><span id="TROUBLESHOOTING"></span>Troubleshooting


For generic troubleshooting of HLK test failures, see [Troubleshooting Windows HLK Test Failures](..\user\troubleshooting-windows-hlk-test-failures.md).

For troubleshooting information, see [Troubleshooting Device.Graphics Testing](troubleshooting-devicegraphics-testing.md).

This test will always return Pass if precision is handled correctly, or return Fail if not. To review test details, review the test log from the Windows HLK Manager.

If the partial precision test fails, try setting your driver to ignore the partial precision flags. If that passes, then it means that when you are attempting to follow the partial precision flags, you are using a lower precision than what the shader specified. E.g. The shader asked for 16-bit minimum, but you are using 8-bit or 10-bit. If you ignore the partial precision flags, and it still fails, ensure other conformance tests pass because the test relies on things like “sample” working correctly.

## <span id="More_information"></span><span id="more_information"></span><span id="MORE_INFORMATION"></span>More information


The partial precision group in WGF11Precision.exe ensures that when shaders specify the minimum partial precision flag (8, 10, or 16-bit) that IHVs do not use a lower precision for calculations. For example, the shader specifies 16-bit but the IHV uses 10-bit. Using higher precision than the minimum specified value is valid.

### <span id="Command_syntax"></span><span id="command_syntax"></span><span id="COMMAND_SYNTAX"></span>Command syntax

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Command option</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>WGF11Precision.exe</strong></p></td>
<td><p>Runs the test jobs.</p></td>
</tr>
</tbody>
</table>

>[!NOTE]
>  
For command line help for this test binary, type **/?**.

 

### <span id="File_list"></span><span id="file_list"></span><span id="FILE_LIST"></span>File list

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>File</th>
<th>Location</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Configdisplay.exe</p></td>
<td><p><em>&lt;[testbinroot]&gt;</em>\nttest\windowstest\tools\</p></td>
</tr>
<tr class="even">
<td><p>D3d11_1sdklayers.dll</p></td>
<td><p><em>&lt;[testbinroot]&gt;</em>\nttest\windowstest\graphics\d3d\support\</p></td>
</tr>
<tr class="odd">
<td><p>D3d11ref.dll</p></td>
<td><p><em>&lt;[testbinroot]&gt;</em>\nttest\windowstest\graphics\d3d\support\</p></td>
</tr>
<tr class="even">
<td><p>D3d11sdklayers.dll</p></td>
<td><p><em>&lt;[testbinroot]&gt;</em>\nttest\windowstest\graphics\d3d\support\</p></td>
</tr>
<tr class="odd">
<td><p>D3dcompiler_test.dll</p></td>
<td><p><em>&lt;[testbinroot]&gt;</em>\nttest\windowstest\graphics\d3d\support</p></td>
</tr>
<tr class="even">
<td><p>D3dx10_test.dll</p></td>
<td><p><em>&lt;[testbinroot]&gt;</em>\nttest\windowstest\graphics\d3d\support\</p></td>
</tr>
<tr class="odd">
<td><p>d3dx11_test.dll</p></td>
<td><p><em>&lt;[testbinroot]&gt;</em>\nttest\windowstest\graphics\d3d\support\</p></td>
</tr>
<tr class="even">
<td><p>TDRWatch.exe</p></td>
<td><p><em>&lt;[testbinroot]&gt;</em>\nttest\windowstest\graphics\</p></td>
</tr>
<tr class="odd">
<td><p>WGF11Precision.exe</p></td>
<td><p><em>&lt;[testbinroot]&gt;</em>\nttest\windowstest\graphics\d3d\conf</p></td>
</tr>
</tbody>
</table>

 

### <span id="Parameters"></span><span id="parameters"></span><span id="PARAMETERS"></span>Parameters

| Parameter name               | Parameter description                                 |
|------------------------------|-------------------------------------------------------|
| **MODIFIEDCMDLINE**          | Additional command line arguments for test executable |
| **LLU\_NetAccessOnly**       | LLU Name of net user                                  |
| **ConfigDisplayCommandLine** | Custom Command Line for ConfigDisplay. Default: logo  |
| **TDRArgs**                  | /get or /set                                          |

 

 

 






