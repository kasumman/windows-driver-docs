---
title: PKEY\_APO\_SWFallback\_ProcessingModes
description: In Windows 10 version 1709 and later, the PKEY\_APO\_SWFallback\_ProcessingModes property key identifies the HW modes that can fallback to software processing modes supported by the driver.

ms.author: windowsdriverdev
ms.date: 12/06/2017
ms.topic: article
ms.prod: windows-hardware
ms.technology: windows-devices
---

# PKEY\_APO\_SWFallback\_ProcessingModes

In Windows 10 version 1709 and later, the *PKEY\_APO\_SWFallback\_ProcessingModes* property key identifies the modes that can fallback to software processing. The driver developer should list all of the mode effect processing modes that support software fallback that their driver supports. This list needs to encompass all the modes that the driver supports in DSP.

If a stream is requested for one of these modes and there are insufficient HW resources available to open a pin in that processing mode, a pin will be opened in the RAW mode and the SW APO initialized with the requested processing mode will be used instead.

 If a stream is requested for one of these modes and there are insufficient HW resources available, a Raw mode stream will be created and the SW APO will be used instead.  

 Drivers that would like to support software fallback of HW processing modes, must support RAW mode, as RAW mode is used to host the SW fallback APOs. 

 All of the modes on the device must support software processing, so all modes that the device supports must be listed.

Any connector modes in this list are assumed to have a corresponding SW APO that supports the same mode or set of modes.  

For more information about audio modes, see [Audio Signal Processing Modes](audio-signal-processing-modes.md).


###  PKEY\_APO\_SWFallback\_ProcessingModes Definition

*PKEY\_APO\_SWFallback\_ProcessingModes* is defined as shown here.

```
PKEY_APO_SWFallback_ProcessingModes (REG_MULTI_SZ) = {D3993A3F-99C2-4402-B5EC-A92A0367664B},13 
```


### <span id="INF_File_Sample"></span><span id="inf_file_sample"></span><span id="INF_FILE_SAMPLE"></span>INF File Sample

The INF file property key lists the signal processing modes supported by the host connector that are available for fallback to SW APO if sufficient HW resources aren't available. 

An INF file specifies settings for in the add-registry section for that device. The following INF example shows the strings and add-registry sections that loads the APO SW fallback processing modes into the registry. In this example four modes are implemented, raw, default, movie and communications. 

```
[Strings]
PKEY_APO_SWFallback_ProcessingModes  = "{D3993A3F-99C2-4402-B5EC-A92A0367664B},13"
...
AUDIO_SIGNALPROCESSINGMODE_DEFAULT = "{C18E2F7E-933D-4965-B7D1-1EEF228D2AF3}"
AUDIO_SIGNALPROCESSINGMODE_MOVIE   = "{B26FEB0D-EC94-477C-9494-D1AB8E753F6E}"
AUDIO_SIGNALPROCESSINGMODE_COMMUNICATIONS = "{98951333-B9CD-48B1-A0A3-FF40682D73F7}"
...
[PKEY.APO.SWFallback.AddReg]
;Include all supported modes:
HKR,"FX\\0",%PKEY_APO_SWFallback_ProcessingModes%,%REG_MULTI_SZ%,%AUDIO_SIGNALPROCESSINGMODE_DEFAULT%,%AUDIO_SIGNALPROCESSINGMODE_MOVIE%,%AUDIO_SIGNALPROCESSINGMODE_COMMUNICATIONS%
```

## <span id="related_topics"></span>Related topics


[Media-Class INF Extensions](media-class-inf-extensions.md)

 

 

[Send comments about this topic to Microsoft](mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback%20[audio\audio]:%20PKEY_MFX_ProcessingModes_Supported_For_Streaming%20%20RELEASE:%20%2811/22/2017%29&body=%0A%0APRIVACY%20STATEMENT%0A%0AWe%20use%20your%20feedback%20to%20improve%20the%20documentation.%20We%20don't%20use%20your%20email%20address%20for%20any%20other%20purpose,%20and%20we'll%20remove%20your%20email%20address%20from%20our%20system%20after%20the%20issue%20that%20you're%20reporting%20is%20fixed.%20While%20we're%20working%20to%20fix%20this%20issue,%20we%20might%20send%20you%20an%20email%20message%20to%20ask%20for%20more%20info.%20Later,%20we%20might%20also%20send%20you%20an%20email%20message%20to%20let%20you%20know%20that%20we've%20addressed%20your%20feedback.%0A%0AFor%20more%20info%20about%20Microsoft's%20privacy%20policy,%20see%20http://privacy.microsoft.com/default.aspx. "Send comments about this topic to Microsoft")




