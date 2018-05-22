﻿---
Description: 'The DXGI\_PRESENT constants specify options for presenting frames to the output.'
ms.assetid: '1ddf8643-ea3e-4c9f-8439-c245942f7333'
title: 'DXGI\_PRESENT'
---

# DXGI\_PRESENT

The **DXGI\_PRESENT** constants specify options for presenting frames to the output.



<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th style="text-align: left;">Constant/value</th>
<th style="text-align: left;">Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="text-align: left;"><span></span><dl> <dt><strong></strong></dt> <dt>0</dt> </dl></td>
<td style="text-align: left;">Present a frame from each buffer (starting with the current buffer) to the output.<br/></td>
</tr>
<tr class="even">
<td style="text-align: left;"><span id="DXGI_PRESENT_DO_NOT_SEQUENCE"></span><span id="dxgi_present_do_not_sequence"></span><dl> <dt><strong>DXGI_PRESENT_DO_NOT_SEQUENCE</strong></dt> <dt>0x00000002UL</dt> </dl></td>
<td style="text-align: left;">Present a frame from the current buffer to the output. Use this flag so that the presentation can use vertical-blank synchronization instead of sequencing buffers in the chain in the usual manner.<br/>
<blockquote>
[!Note]<br />
If the calling application sets the DXGI_PRESENT_DO_NOT_SEQUENCE constant on the first present operation (that is, when there is no current buffer), the runtime ignores that present operation and does not call the driver.
</blockquote>
<br/></td>
</tr>
<tr class="odd">
<td style="text-align: left;"><span id="DXGI_PRESENT_TEST"></span><span id="dxgi_present_test"></span><dl> <dt><strong>DXGI_PRESENT_TEST</strong></dt> <dt>0x00000001UL</dt> </dl></td>
<td style="text-align: left;">Do not present the frame to the output. The status of the swap chain will be tested and appropriate errors returned. DXGI_PRESENT_TEST is intended for use only when switching from the idle state; do not use it to determine when to switch to the idle state because doing so can leave the swap chain unable to exit full-screen mode.<br/></td>
</tr>
<tr class="even">
<td style="text-align: left;"><span id="DXGI_PRESENT_RESTART"></span><span id="dxgi_present_restart"></span><dl> <dt><strong>DXGI_PRESENT_RESTART</strong></dt> <dt>0x00000004UL</dt> </dl></td>
<td style="text-align: left;">Specifies that the runtime will discard outstanding queued presents.<br/></td>
</tr>
<tr class="odd">
<td style="text-align: left;"><span id="DXGI_PRESENT_DO_NOT_WAIT"></span><span id="dxgi_present_do_not_wait"></span><dl> <dt><strong>DXGI_PRESENT_DO_NOT_WAIT</strong></dt> <dt>0x00000008UL</dt> </dl></td>
<td style="text-align: left;">Specifies that the runtime will fail the presentation (that is, fail a call to [<strong>IDXGISwapChain1::Present1</strong>](idxgiswapchain1-present1.md)) with the [DXGI_ERROR_WAS_STILL_DRAWING](dxgi-error.md#dxgi-error-was-still-drawing) error code if the calling thread is blocked; the runtime returns DXGI_ERROR_WAS_STILL_DRAWING instead of sleeping until the dependency is resolved.<br/> <strong>Direct3D 11:</strong> This enumeration value is supported starting with Windows 8.<br/></td>
</tr>
<tr class="even">
<td style="text-align: left;"><span id="DXGI_PRESENT_RESTRICT_TO_OUTPUT"></span><span id="dxgi_present_restrict_to_output"></span><dl> <dt><strong>DXGI_PRESENT_RESTRICT_TO_OUTPUT</strong></dt> <dt>0x00000010UL</dt> </dl></td>
<td style="text-align: left;">Indicates that presentation content will be shown only on the particular output. The content will not be visible on other outputs. For example, if the user tries to relocate video content on another output, the video content will not be visible. <br/> <strong>Direct3D 11:</strong> This enumeration value is supported starting with Windows 8. <br/>
<blockquote>
[!Note]<br />
This flag should only be used with swap effect [DXGI_SWAP_EFFECT_FLIP_SEQUENTIAL](dxgi-swap-effect.md) or DXGI_SWAP_EFFECT_FLIP_DISCARD. The use of this flag with <em>other</em> swap effects is being deprecated, and may not work in future versions of Windows.
</blockquote>
<br/></td>
</tr>
<tr class="odd">
<td style="text-align: left;"><span id="DXGI_PRESENT_STEREO_PREFER_RIGHT"></span><span id="dxgi_present_stereo_prefer_right"></span><dl> <dt><strong>DXGI_PRESENT_STEREO_PREFER_RIGHT</strong></dt> <dt>0x00000020UL</dt> </dl></td>
<td style="text-align: left;">Indicates that if the stereo present must be reduced to mono, right-eye viewing is used rather than left-eye viewing.<br/> <strong>Direct3D 11:</strong> This enumeration value is supported starting with Windows 8.<br/></td>
</tr>
<tr class="even">
<td style="text-align: left;"><span id="DXGI_PRESENT_STEREO_TEMPORARY_MONO"></span><span id="dxgi_present_stereo_temporary_mono"></span><dl> <dt><strong>DXGI_PRESENT_STEREO_TEMPORARY_MONO</strong></dt> <dt>0x00000040UL</dt> </dl></td>
<td style="text-align: left;">Indicates that the presentation should use the left buffer as a mono buffer. An application calls the [<strong>IDXGISwapChain1::IsTemporaryMonoSupported</strong>](idxgiswapchain1-istemporarymonosupported.md) method to determine whether a swap chain supports &quot;temporary mono&quot;.<br/> <strong>Direct3D 11:</strong> This enumeration value is supported starting with Windows 8.<br/></td>
</tr>
<tr class="odd">
<td style="text-align: left;"><span id="DXGI_PRESENT_USE_DURATION"></span><span id="dxgi_present_use_duration"></span><dl> <dt><strong>DXGI_PRESENT_USE_DURATION</strong></dt> <dt>0x00000100UL</dt> </dl></td>
<td style="text-align: left;">This flag must be set by media apps that are currently using a custom present duration (custom refresh rate). See [<strong>IDXGISwapChainMedia</strong>](idxgiswapchainmedia.md).<br/>
<blockquote>
[!Note]<br />
This value is supported starting in Windows 8.1.
</blockquote>
<br/></td>
</tr>
<tr class="even">
<td style="text-align: left;"><span id="DXGI_PRESENT_ALLOW_TEARING"></span><span id="dxgi_present_allow_tearing"></span><dl> <dt><strong>DXGI_PRESENT_ALLOW_TEARING</strong></dt> <dt>0x00000200UL</dt> </dl></td>
<td style="text-align: left;">Allowing tearing is a requirement of variable refresh rate displays.<br/> The conditions for using DXGI_PRESENT_ALLOW_TEARING during Present are as follows:<br/>
<ul>
<li>The swap chain must be created with the [<strong>DXGI_SWAP_CHAIN_FLAG_ALLOW_TEARING</strong>](direct3ddxgi.dxgi_swap_chain_flag) flag.</li>
<li>The sync interval passed in to [<strong>Present</strong>](idxgiswapchain-present.md) (or [<strong>Present1</strong>](idxgiswapchain1-present1.md)) must be 0.</li>
<li>The DXGI_PRESENT_ALLOW_TEARING flag cannot be used in an application that is currently in full screen exclusive mode (set by calling [<strong>SetFullscreenState(TRUE)</strong>](idxgiswapchain-setfullscreenstate.md)). It can only be used in windowed mode. To use this flag in full screen Win32 apps, the application should present to a fullscreen borderless window and disable automatic ALT+ENTER fullscreen switching using [<strong>IDXGIFactory::MakeWindowAssociation</strong>](idxgifactory-makewindowassociation.md). UWP apps that enter fullscreen mode by calling <code>Windows::UI::ViewManagement::ApplicationView::TryEnterFullscreen()</code> are fullscreen borderless windows and may use the flag.</li>
</ul>
Calling [<strong>Present</strong>](idxgiswapchain-present.md) (or [<strong>Present1</strong>](idxgiswapchain1-present1.md)) with this flag and not meeting the conditions above will result in a DXGI_ERROR_INVALID_CALL error being returned to the calling application.<br/></td>
</tr>
</tbody>
</table>



## Remarks

Presentation options are supplied during the [**IDXGISwapChain::Present**](idxgiswapchain-present.md) or [**IDXGISwapChain1::Present1**](idxgiswapchain1-present1.md) call. The buffers are specified in the swap chain description (see [**DXGI\_SWAP\_CHAIN\_DESC**](dxgi-swap-chain-desc.md) or [**DXGI\_SWAP\_CHAIN\_DESC1**](dxgi-swap-chain-desc1.md)).

DXGI\_PRESENT\_RESTART is valid only for flip-model swap chains and full screen. Applications can use DXGI\_PRESENT\_RESTART to recover from glitches in playback, as well as to discard previously queued presentations. Discarding previously queued presentations is useful if those queued presentations are windowed scenarios. In particular, the previously queued presentation might have assumed that the window is an old size (that is, a resize operation occurred after submission).

DXGI\_PRESENT\_RESTRICT\_TO\_OUTPUT is valid only for swap chains that specified a particular output to restrict content to when those swap chains were created ([**IDXGIFactory2::CreateSwapChainForHwnd**](idxgifactory2-createswapchain1.md)). If there is no output to restrict to, the flag is invalid.

DXGI\_PRESENT\_STEREO\_PREFER\_RIGHT indicates that if the stereo present must be reduced to mono the right eye should be used rather than the left (default) eye. You can use this flag if one side is higher quality (for example, if the stereo pair is synthesized from a standard image.)

DXGI\_PRESENT\_STEREO\_TEMPORARY\_MONO indicates that the present should use the left buffer as a mono buffer. You can use this flag to avoid updating the right buffer when an application temporarily has no stereo content. You should use this flag whenever possible because it enables significant optimization by the operating system and under some circumstances it can avoid visible mode change artifacts.

You should use the DXGI\_PRESENT\_STEREO\_TEMPORARY\_MONO flag in preference to switching to a mono swap chain for most applications that you anticipate will use stereo again. You need to balance the use of this flag in applications that are extremely long running or that rarely display stereo against the disadvantage of unused memory.

> [!Note]  
> Full-screen applications that switch to a mono swap chain cause a mode change that generally has visible artifacts (for example, "flashing”). However, temporary mono might not be supported for full-screen swap chains.

 

The DXGI\_PRESENT\_STEREO\_PREFER\_RIGHT and DXGI\_PRESENT\_STEREO\_TEMPORARY\_MONO flags apply only to stereo swap chains. If you use them when you present mono swap chains, an invalid operation occurs.

If you use the DXGI\_PRESENT\_STEREO\_TEMPORARY\_MONO flag when you present a stereo swap chain that does not support temporary mono, an error occurs, the swap chain does not display, and the presentation returns [DXGI\_ERROR\_INVALID\_CALL](dxgi-error.md#dxgi-error-invalid-call).

## Requirements



|                   |                                                                                   |
|-------------------|-----------------------------------------------------------------------------------|
| Header<br/> | <dl> <dt>DXGI.h</dt> </dl> |



## See also

<dl> <dt>

[DXGI Constants](d3d10-graphics-reference-dxgi-constants.md)
</dt> </dl>

 

 



