---
ms.assetid: 3457cfb6-3891-4e15-a4e0-53ad43adcc2d
title: Functions with Unicode (W) Versions
ms.technology: desktop
ms.prod: windows
ms.author: windowssdkdev
ms.topic: article
ms.date: 05/31/2018
---

# Functions with Unicode (W) Versions

The following TAPI functions are implemented in Unicode (W) and ANSI (A) versions. In general, the implementation of the ANSI version calls the Unicode version and performs necessary conversions of ANSI parameters and structure fields to and from Unicode; the following table indicates the parameters that are converted.

Applications that explicitly call the generic (neither "W" or "A" suffix) version of a function will execute the ANSI version, for compatibility with previous versions of TAPI.

> [!Note]  
> The entire Telephony Service Provider Interface (TSPI) is Unicode for version 2.0.

 

Listed in the following table are references to string fields in TAPI structures that consist of a portion of the field names. For example, the "Caller Address" in the [**LINEFORWARD**](/windows/desktop/api/Tapi/ns-tapi-lineforward_tag) structure is pointed to by the **dwCallerAddressOffset** field and delimited by the **dwCallerAddressSize** field; in the table, this string is identified simply as **CallerAddress**.



<table><colgroup><col style="width: 50%" /><col style="width: 50%" /></colgroup><thead><tr class="header"><th>TAPI function</th><th>Parameters and structure fields converted in ANSI version of function</th></tr></thead><tbody><tr class="odd"><td>[<strong>lineAddProvider</strong>](/windows/desktop/api/Tapi/nf-tapi-lineaddprovider)</td><td><em>lpszProviderName</em></td></tr><tr class="even"><td>[<strong>lineBlindTransfer</strong>](/windows/desktop/api/Tapi/nf-tapi-lineblindtransfer)</td><td><em>lpszDestAddress</em></td></tr><tr class="odd"><td>[<strong>lineConfigDialog</strong>](/windows/desktop/api/Tapi/nf-tapi-lineconfigdialog)</td><td><em>lpszDeviceClass</em></td></tr><tr class="even"><td>[<strong>lineConfigDialogEdit</strong>](/windows/desktop/api/Tapi/nf-tapi-lineconfigdialogedit)</td><td><em>lpszDeviceClass</em><blockquote>[!Note]<br />
Application must handle conversion of strings in <em>lpDeviceConfigIn</em> and <em>lpDeviceConfigOut</em>, if directly manipulated.</blockquote><br/></td></tr><tr class="odd"><td>[<strong>lineDial</strong>](/windows/desktop/api/Tapi/nf-tapi-linedial)</td><td><em>lpszDestAddress</em></td></tr><tr class="even"><td>[<strong>lineForward</strong>](/windows/desktop/api/Tapi/nf-tapi-lineforward)</td><td><em>lpForwardList</em> ( [<strong>LINEFORWARDLIST</strong>](/windows/desktop/api/Tapi/ns-tapi-lineforwardlist_tag))<ul><li><em>ForwardList</em> ( [<strong>LINEFORWARD</strong>](/windows/desktop/api/Tapi/ns-tapi-lineforward_tag))<ul><li><em>CallerAddress</em></li><li><em>DestAddress</em></li></ul></li></ul><em>lpCallParams</em> ( [<strong>LINECALLPARAMS</strong>](/windows/desktop/api/Tapi/ns-tapi-linecallparams_tag))<br/><ul><li><em>OrigAddress</em></li><li><em>DisplayableAddress</em></li><li><em>CalledParty</em></li><li><em>Comment</em></li><li><em>TargetAddress</em></li><li><em>DeviceClass</em></li><li><em>CallingPartyID</em></li></ul></td></tr><tr class="odd"><td>[<strong>lineGatherDigits</strong>](/windows/desktop/api/Tapi/nf-tapi-linegatherdigits)</td><td><em>lpsDigitslpszTerminationDigits</em> <br/></td></tr><tr class="even"><td>[<strong>lineGenerateDigits</strong>](/windows/desktop/api/Tapi/nf-tapi-linegeneratedigits)</td><td><em>lpszDigits</em></td></tr><tr class="odd"><td>[<strong>lineGetAddressCaps</strong>](/windows/desktop/api/Tapi/nf-tapi-linegetaddresscaps)</td><td><em>lpAddressCaps</em> ( [<strong>LINEADDRESSCAPS</strong>](/windows/desktop/api/Tapi/ns-tapi-lineaddresscaps_tag))<ul><li><em>Address</em></li><li><em>CompletionMsgText</em></li><li><em>DeviceClasses</em></li><li><em>CallTreatmentList</em> ( [<strong>LINECALLTREATMENTENTRY</strong>](/windows/desktop/api/Tapi/ns-tapi-linecalltreatmententry_tag))</li><li><em>CallTreatmentName</em></li></ul></td></tr><tr class="even"><td>[<strong>lineGetAddressID</strong>](/windows/desktop/api/Tapi/nf-tapi-linegetaddressid)</td><td><em>lpsAddress</em></td></tr><tr class="odd"><td>[<strong>lineGetAddressStatus</strong>](/windows/desktop/api/Tapi/nf-tapi-linegetaddressstatus)</td><td><em>lpAddressStatus</em> ( [<strong>LINEADDRESSSTATUS</strong>](/windows/desktop/api/Tapi/ns-tapi-lineaddressstatus_tag))<ul><li><em>Forward</em> ( [<strong>LINEFORWARD</strong>](/windows/desktop/api/Tapi/ns-tapi-lineforward_tag))</li><li><em>CallerAddress</em></li><li><em>DestAddress</em></li></ul></td></tr><tr class="even"><td>[<strong>lineGetAgentActivityList</strong>](/windows/desktop/api/Tapi/nf-tapi-linegetagentactivitylista)</td><td><em>lpAgentActivityList</em> ( [<strong>LINEAGENTACTIVITYLIST</strong>](/windows/desktop/api/Tapi/ns-tapi-lineagentactivitylist_tag))<ul><li><em>List</em> ( [<strong>LINEAGENTACTIVITYENTRY</strong>](/windows/desktop/api/Tapi/ns-tapi-lineagentactivityentry_tag))</li><li><em>Name</em></li></ul></td></tr><tr class="odd"><td>[<strong>lineGetAgentCaps</strong>](/windows/desktop/api/Tapi/nf-tapi-linegetagentcapsa)</td><td><em>lpAgentCaps</em> ( [<strong>LINEAGENTCAPS</strong>](/windows/desktop/api/Tapi/ns-tapi-lineagentcaps_tag))<ul><li><em>AgentHandlerInfo</em></li></ul></td></tr><tr class="even"><td>[<strong>lineGetAgentGroupList</strong>](/windows/desktop/api/Tapi/nf-tapi-linegetagentgrouplista)</td><td><em>lpAgentGroupListI</em>( [<strong>LINEAGENTGROUPLIST</strong>](/windows/desktop/api/Tapi/ns-tapi-lineagentgrouplist_tag))<ul><li><em>List</em> ( [<strong>LINEAGENTGROUPENTRY</strong>](/windows/desktop/api/Tapi/ns-tapi-lineagentgroupentry_tag))</li><li><em>Name</em></li></ul></td></tr><tr class="odd"><td>[<strong>lineGetAgentStatus</strong>](/windows/desktop/api/Tapi/nf-tapi-linegetagentstatusa)</td><td><em>lpAgentStatus</em> ( [<strong>LINEAGENTSTATUS</strong>](/windows/desktop/api/Tapi/ns-tapi-lineagentstatus_tag))<ul><li><em>Activity</em></li><li><em>GroupList</em> ( [<strong>LINEAGENTGROUPENTRY</strong>](/windows/desktop/api/Tapi/ns-tapi-lineagentgroupentry_tag))</li><li><em>Name</em></li></ul></td></tr><tr class="even"><td>[<strong>lineGetAppPriority</strong>](/windows/desktop/api/Tapi/nf-tapi-linegetapppriority)</td><td><em>lpszAppFilenamelpExtensionName</em> <br/></td></tr><tr class="odd"><td>[<strong>lineGetCallInfo</strong>](/windows/desktop/api/Tapi/nf-tapi-linegetcallinfo)</td><td><em>lpCallInfo</em> ( [<strong>LINECALLINFO</strong>](/windows/desktop/api/Tapi/ns-tapi-linecallinfo_tag))<ul><li><em>CallerID</em></li><li><em>CallerIDName</em></li><li><em>CalledID</em></li><li><em>CalledIDName</em></li><li><em>ConnectID</em></li><li><em>ConnectedIDName</em></li><li><em>RedirectionID</em></li><li><em>RedirectionIDName</em></li><li><em>RedirectingID</em></li><li><em>RedirectingIDName</em></li><li><em>AppName</em></li><li><em>DisplayableAddress</em></li><li><em>CalledParty</em></li><li><em>Comment</em></li></ul></td></tr><tr class="even"><td>[<strong>lineGetCountry</strong>](/windows/desktop/api/Tapi/nf-tapi-linegetcountry)</td><td><em>lpLineCountryList</em> ( [<strong>LINECOUNTRYLIST</strong>](/windows/desktop/api/Tapi/ns-tapi-linecountrylist_tag))<ul><li><em>CountryList</em> ( [<strong>LINECOUNTRYENTRY</strong>](/windows/desktop/api/Tapi/ns-tapi-linecountryentry_tag))</li><li><em>CountryName</em></li><li><em>SameAreaRule</em></li><li><em>LongDistanceRule</em></li><li><em>InternationalRule</em></li></ul></td></tr><tr class="odd"><td>[<strong>lineGetDevCaps</strong>](/windows/desktop/api/Tapi/nf-tapi-linegetdevcaps)</td><td><em>lpLineDevCaps</em> ( [<strong>LINEDEVCAPS</strong>](/windows/desktop/api/Tapi/ns-tapi-linedevcaps_tag))<ul><li><em>ProviderInfo</em></li><li><em>SwitchInfo</em></li><li><em>LineName</em></li><li><em>TerminalText</em></li><li><em>DeviceClasses</em></li></ul><blockquote>[!Note]<br />
<em>dwStringFormat</em> is obsolete.</blockquote><br/></td></tr><tr class="even"><td>[<strong>LineGetDevConfig</strong>](/windows/desktop/api/Tapi/nf-tapi-linegetdevconfig)</td><td><em>lpszDeviceClass</em><blockquote>[!Note]<br />
Application must handle conversion of strings in <em>lpDeviceConfig</em>, if these are directly manipulated.</blockquote><br/></td></tr><tr class="odd"><td>[<strong>LineGetIcon</strong>](/windows/desktop/api/Tapi/nf-tapi-linegeticon)</td><td><em>lpszDeviceClass</em></td></tr><tr class="even"><td>[<strong>lineGetID</strong>](/windows/desktop/api/Tapi/nf-tapi-linegetid)</td><td><em>lpszDeviceClass</em><blockquote>[!Note]<br />
Application must handle conversion of strings in <em>lpDeviceID</em>, if these are directly manipulated.</blockquote><br/></td></tr><tr class="odd"><td>[<strong>LineGetLineDevStatus</strong>](/windows/desktop/api/Tapi/nf-tapi-linegetlinedevstatus)</td><td><em>lpLineDevStatus</em> ( [<strong>LINEDEVSTATUS</strong>](/windows/desktop/api/Tapi/ns-tapi-linedevstatus_tag))<ul><li><em>AppInfo</em> (LINEAPPINFO)</li><li><em>MachineName</em></li><li><em>UserName</em></li><li><em>ModuleFilename</em></li><li><em>FriendlyName</em></li></ul></td></tr><tr class="even"><td>[<strong>lineGetProviderList</strong>](/windows/desktop/api/Tapi/nf-tapi-linegetproviderlist)</td><td><em>lpProviderList</em> ( [<strong>LINEPROVIDERLIST</strong>](/windows/desktop/api/Tapi/ns-tapi-lineproviderlist_tag))<ul><li><em>ProviderList</em> ( [<strong>LINEPROVIDERENTRY</strong>](/windows/desktop/api/Tapi/ns-tapi-lineproviderentry_tag))</li><li><em>ProviderFilename</em></li></ul></td></tr><tr class="odd"><td>[<strong>lineGetRequest</strong>](/windows/desktop/api/Tapi/nf-tapi-linegetrequest)</td><td><em>lpRequestBuffer</em> ( [<strong>LINEREQMAKECALL</strong>](/windows/desktop/api/Tapi/ns-tapi-linereqmakecall_tag)<ul><li><em>szDestAddress</em></li><li><em>szAppName</em></li><li><em>szCalledParty</em></li><li><em>szComment</em></li></ul></td></tr><tr class="even"><td>[<strong>lineGetTranslateCaps</strong>](/windows/desktop/api/Tapi/nf-tapi-linegettranslatecaps)</td><td><em>lpTranslateCaps</em> ( [<strong>LINETRANSLATECAPS</strong>](/windows/desktop/api/Tapi/ns-tapi-linetranslatecaps_tag))<ul><li><em>CardList</em> ( [<strong>LINECARDENTRY</strong>](/windows/desktop/api/Tapi/ns-tapi-linecardentry_tag))</li><li><em>CardName</em></li><li><em>SameAreaRule</em></li><li><em>LongDistanceRule</em></li><li><em>InternationalRule</em></li><li><em>LocationList</em> ( [<strong>LINELOCATIONENTRY</strong>](/windows/desktop/api/Tapi/ns-tapi-linelocationentry_tag)</li><li><em>LocationName</em></li><li><em>CityCode</em></li><li><em>LocalAccessCode</em></li><li><em>LongDistanceAccessCode</em></li><li><em>TollPrefixList</em></li><li><em>celCallWaiting</em></li></ul></td></tr><tr class="odd"><td>[<strong>lineHandoff</strong>](/windows/desktop/api/Tapi/nf-tapi-linehandoff)</td><td><em>lpszFileName</em></td></tr><tr class="even"><td>[<strong>lineInitializeEx</strong>](/windows/desktop/api/Tapi/nf-tapi-lineinitializeexa)</td><td><em>lpszFriendlyAppName</em></td></tr><tr class="odd"><td>[<strong>lineMakeCall</strong>](/windows/desktop/api/Tapi/nf-tapi-linemakecall)</td><td><em>lpszDestAddresslpCallParams</em> ( [<strong>LINECALLPARAMS</strong>](/windows/desktop/api/Tapi/ns-tapi-linecallparams_tag))<br/><ul><li><em>OrigAddress</em></li><li><em>DisplayableAddress</em></li><li><em>CalledParty</em></li><li><em>Comment</em></li><li><em>TargetAddress</em></li><li><em>DeviceClass</em></li><li><em>CallingPartyID</em></li></ul></td></tr><tr class="even"><td>[<strong>lineOpen</strong>](/windows/desktop/api/Tapi/nf-tapi-lineopen)</td><td><em>lpCallParams</em> ( [<strong>LINECALLPARAMS</strong>](/windows/desktop/api/Tapi/ns-tapi-linecallparams_tag))<ul><li><em>OrigAddress</em></li><li><em>DisplayableAddress</em></li><li><em>CalledParty</em></li><li><em>Comment</em></li><li><em>TargetAddress</em></li><li><em>DeviceClass</em></li><li><em>CallingPartyID</em></li></ul></td></tr><tr class="odd"><td>[<strong>linePark</strong>](/windows/desktop/api/Tapi/nf-tapi-linepark)</td><td><em>lpszDirAddresslpNonDirAddress</em> ( [<strong>VARSTRING</strong>](/windows/desktop/api/Tapi/ns-tapi-varstring_tag))<br/><ul><li><em>String</em></li></ul></td></tr><tr class="even"><td>[<strong>linePickup</strong>](/windows/desktop/api/Tapi/nf-tapi-linepickup)</td><td><em>lpszDestAddresslpszGroupID</em> <br/></td></tr><tr class="odd"><td>[<strong>linePrepareAddToConference</strong>](/windows/desktop/api/Tapi/nf-tapi-lineprepareaddtoconference)</td><td><em>lpCallParams</em> ( [<strong>LINECALLPARAMS</strong>](/windows/desktop/api/Tapi/ns-tapi-linecallparams_tag))<ul><li><em>OrigAddress</em></li><li><em>DisplayableAddress</em></li><li><em>CalledParty</em></li><li><em>Comment</em></li><li><em>TargetAddress</em></li><li><em>DeviceClass</em></li><li><em>CallingPartyID</em></li></ul></td></tr><tr class="even"><td>[<strong>lineRedirect</strong>](/windows/desktop/api/Tapi/nf-tapi-lineredirect)</td><td><em>lpszDestAddress</em></td></tr><tr class="odd"><td>[<strong>lineSetAppPriority</strong>](/windows/desktop/api/Tapi/nf-tapi-linesetapppriority)</td><td><em>lpszAppFilenamelpszExtensionName</em> <br/></td></tr><tr class="even"><td>[<strong>lineSetDevConfig</strong>](/windows/desktop/api/Tapi/nf-tapi-linesetdevconfig)</td><td><em>lpszDeviceClass</em><blockquote>[!Note]<br />
Application must handle conversion of strings in <em>lpDeviceConfig</em>, if these are directly manipulated.</blockquote><br/></td></tr><tr class="odd"><td>[<strong>lineSetTollList</strong>](/windows/desktop/api/Tapi/nf-tapi-linesettolllist)</td><td><em>lpszAddressIn</em></td></tr><tr class="even"><td>[<strong>lineSetupConference</strong>](/windows/desktop/api/Tapi/nf-tapi-linesetupconference)</td><td><em>lpCallParams</em> ( [<strong>LINECALLPARAMS</strong>](/windows/desktop/api/Tapi/ns-tapi-linecallparams_tag))<ul><li><em>OrigAddress</em></li><li><em>DisplayableAddress</em></li><li><em>CalledParty</em></li><li><em>Comment</em></li><li><em>TargetAddress</em></li><li><em>DeviceClass</em></li><li><em>CallingPartyID</em></li></ul></td></tr><tr class="odd"><td>[<strong>lineSetupTransfer</strong>](/windows/desktop/api/Tapi/nf-tapi-linesetuptransfer)</td><td><em>lpCallParams</em> ( [<strong>LINECALLPARAMS</strong>](/windows/desktop/api/Tapi/ns-tapi-linecallparams_tag))<ul><li><em>OrigAddress</em></li><li><em>DisplayableAddress</em></li><li><em>CalledParty</em></li><li><em>Comment</em></li><li><em>TargetAddress</em></li><li><em>DeviceClass</em></li><li><em>CallingPartyID</em></li></ul></td></tr><tr class="even"><td>[<strong>lineTranslateAddress</strong>](/windows/desktop/api/Tapi/nf-tapi-linetranslateaddress)</td><td><em>lpszAddressInlpTranslateOutput</em> ( [<strong>LINETRANSLATEOUTPUT</strong>](/windows/desktop/api/Tapi/ns-tapi-linetranslateoutput_tag))<br/><ul><li><em>DialableString</em></li><li><em>DisplayableString</em></li></ul></td></tr><tr class="odd"><td>[<strong>lineTranslateDialog</strong>](/windows/desktop/api/Tapi/nf-tapi-linetranslatedialog)</td><td><em>lpszAddressIn</em></td></tr><tr class="even"><td>[<strong>lineUnpark</strong>](/windows/desktop/api/Tapi/nf-tapi-lineunpark)</td><td><em>lpszDestAddress</em></td></tr><tr class="odd"><td>[<strong>phoneConfigDialog</strong>](/windows/desktop/api/Tapi/nf-tapi-phoneconfigdialog)</td><td><em>lpszDeviceClass</em></td></tr><tr class="even"><td>[<strong>phoneGetButtonInfo</strong>](/windows/desktop/api/Tapi/nf-tapi-phonegetbuttoninfo)</td><td><em>lpButtonInfo</em> ( [<strong>PHONEBUTTONINFO</strong>](/windows/desktop/api/Tapi/ns-tapi-phonebuttoninfo_tag))<ul><li><em>ButtonText</em></li></ul></td></tr><tr class="odd"><td>[<strong>phoneGetDevCaps</strong>](/windows/desktop/api/Tapi/nf-tapi-phonegetdevcaps)</td><td><em>lpPhoneCaps</em> ( [<strong>PHONECAPS</strong>](/windows/desktop/api/Tapi/ns-tapi-phonecaps_tag))<ul><li><em>ProviderInfo</em></li><li><em>PhoneInfo</em></li><li><em>PhoneName</em></li><li><em>Device Classes</em></li></ul><blockquote>[!Note]<br />
<em>dwStringFormat</em> is obsolete.</blockquote><br/></td></tr><tr class="even"><td>[<strong>phoneGetIcon</strong>](/windows/desktop/api/Tapi/nf-tapi-phonegeticon)</td><td><em>lpszDeviceClass</em></td></tr><tr class="odd"><td>[<strong>phoneGetID</strong>](/windows/desktop/api/Tapi/nf-tapi-phonegetid)</td><td><em>lpszDeviceClass</em><blockquote>[!Note]<br />
Application must handle conversion of strings in <em>lpDeviceID</em>, if these are directly manipulated.</blockquote><br/></td></tr><tr class="even"><td>[<strong>phoneGetStatus</strong>](/windows/desktop/api/Tapi/nf-tapi-phonegetstatus)</td><td><em>lpPhoneStatus</em> ( [<strong>PHONESTATUS</strong>](/windows/desktop/api/Tapi/ns-tapi-phonestatus_tag))<ul><li><em>OwnerName</em></li></ul></td></tr><tr class="odd"><td>[<strong>phoneInitializeEx</strong>](/windows/desktop/api/Tapi/nf-tapi-phoneinitializeexa)</td><td><em>lpszFriendlyAppName</em></td></tr><tr class="even"><td>[<strong>phoneSetButtonInfo</strong>](/windows/desktop/api/Tapi/nf-tapi-phonesetbuttoninfo)</td><td><em>lpButtonInfo</em> ( [<strong>PHONEBUTTONINFO</strong>](/windows/desktop/api/Tapi/ns-tapi-phonebuttoninfo_tag))<ul><li><em>ButtonTest</em></li></ul></td></tr><tr class="odd"><td>[<strong>tapiGetLocationInfo</strong>](/windows/desktop/api/Tapi/nf-tapi-tapigetlocationinfo)</td><td><em>lpszCountryCodelpszCityCode</em> <br/></td></tr><tr class="even"><td>[<strong>tapiRequestMakeCall</strong>](/windows/desktop/api/Tapi/nf-tapi-tapirequestmakecall)</td><td><em>lpszDestAddresslpszAppName</em> <br/> <em>lpszCalledParty</em> <br/> <em>lpszComment</em><br/></td></tr></tbody></table>



 

 

 



