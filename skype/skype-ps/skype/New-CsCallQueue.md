---
external help file: Microsoft.Rtc.Management.dll-Help.xml
online version: https://learn.microsoft.com/powershell/module/skype/new-cscallqueue
applicable: Skype for Business Online
title: New-CsCallQueue
author: tomkau
ms.author: tomkau
manager: bulenteg
ms.reviewer:
schema: 2.0.0
---

# New-CsCallQueue

## SYNOPSIS
Creates new Call Queue in your Skype for Business Online organization.

## SYNTAX

```
New-CsCallQueue -Name <String> [-AgentAlertTime <Int16>] [-AllowOptOut <Boolean>] [-DistributionLists <List>] [-Tenant <Guid>] [-UseDefaultMusicOnHold <Boolean>] [-WelcomeMusicAudioFileId <Guid>] [-MusicOnHoldAudioFileId <Guid>] [-OverflowAction <Object>] [-OverflowActionTarget <Guid>] [-OverflowThreshold <Int16>] [-TimeoutAction <Object>] [-TimeoutActionTarget <Guid>] [-TimeoutThreshold <Int16>] [-NoAgentAction <Object>] [-NoAgentActionTarget <Guid>] [-RoutingMethod <Object>] [-PresenceBasedRouting <Boolean>] [-ConferenceMode <Boolean>] [-User <List>] [-LanguageId <String>] [-LineUri <String>] [-OboResourceAccountIds <List>] [-OverflowDisconnectTextToSpeechPrompt <String>][-OverflowDisconnectAudioFilePrompt <Guid>] [-OverflowRedirectPersonTextToSpeechPrompt <String>][-OverflowRedirectPersonAudioFilePrompt <Guid>] [-OverflowRedirectVoiceAppTextToSpeechPrompt <String>] [-OverflowRedirectVoiceAppAudioFilePrompt <Guid>] [-OverflowRedirectPhoneNumberTextToSpeechPrompt <String>] [-OverflowRedirectPhoneNumberAudioFilePrompt <Guid>] [-OverflowRedirectVoicemailTextToSpeechPrompt <String>] [-OverflowRedirectVoicemailAudioFilePrompt <Guid>] [-OverflowSharedVoicemailTextToSpeechPrompt <String>] [-OverflowSharedVoicemailAudioFilePrompt <Guid>] [-EnableOverflowSharedVoicemailTranscription <Boolean>] [-EnableOverflowSharedVoicemailSystemPromptSuppression <Boolean>] [-TimeoutDisconnectTextToSpeechPrompt <String>][-TimeoutDisconnectAudioFilePrompt <Guid>] [-TimeoutRedirectPersonTextToSpeechPrompt <String>] [-TimeoutRedirectPersonAudioFilePrompt <Guid>] [-TimeoutRedirectVoiceAppTextToSpeechPrompt <String>] [-TimeoutRedirectVoiceAppAudioFilePrompt <Guid>] [-TimeoutRedirectPhoneNumberTextToSpeechPrompt <String>] [-TimeoutRedirectPhoneNumberAudioFilePrompt <Guid>] [-TimeoutRedirectVoicemailTextToSpeechPrompt <String>] [-TimeoutRedirectVoicemailAudioFilePrompt <Guid>] [-TimeoutSharedVoicemailTextToSpeechPrompt <String>] [-TimeoutSharedVoicemailAudioFilePrompt <Guid>] [-EnableTimeoutSharedVoicemailTranscription <Boolean>] [-EnableTimeoutSharedVoicemailSystemPromptSuppression <Boolean>] [-NoAgentDisconnectTextToSpeechPrompt <String>][-NoAgentDisconnectAudioFilePrompt <Guid>] [-NoAgentRedirectPersonTextToSpeechPrompt <String>] [-NoAgentRedirectPersonAudioFilePrompt <Guid>] [-NoAgentRedirectVoiceAppTextToSpeechPrompt <String>] [-NoAgentRedirectVoiceAppAudioFilePrompt <Guid>] [-NoAgentRedirectPhoneNumberTextToSpeechPrompt <String>] [-NoAgentRedirectPhoneNumberAudioFilePrompt <Guid>] [-NoAgentRedirectVoicemailTextToSpeechPrompt <String>] [-NoAgentRedirectVoicemailAudioFilePrompt <Guid>] [-NoAgentSharedVoicemailTextToSpeechPrompt <String>] [-NoAgentSharedVoicemailAudioFilePrompt <Guid>] [-EnableNoAgentSharedVoicemailTranscription <Boolean>] [-EnableNoAgentSharedVoicemailSystemPromptSuppression <Boolean>] [-ChannelId <String>] [-ChannelUserObjectId <Guid>] [-AuthorizedUsers <List>] [-HideAuthorizedUsers <List>] [-WelcomeTextToSpeechPrompt <String>] [<CommonParameters>]
```

## DESCRIPTION
The New-CsCallQueue cmdlet creates a new Call Queue.

> [!CAUTION]
> The following configuration parameters are currently only available in PowerShell and do not appear in Teams admin center. Saving a call queue configuration through Teams admin center will _remove_ any of these configured items:
> 
> - -OverflowDisconnectTextToSpeechPrompt
> - -OverflowDisconnectAudioFilePrompt
> - -OverflowRedirectPersonTextToSpeechPrompt
> - -OverflowRedirectPersonAudioFilePrompt
> - -OverflowRedirectVoiceAppTextToSpeechPrompt
> - -OverflowRedirectVoiceAppAudioFilePrompt
> - -OverflowRedirectPhoneNumberTextToSpeechPrompt
> - -OverflowRedirectPhoneNumberAudioFilePrompt
> - -OverflowRedirectVoicemailTextToSpeechPrompt
> - -OverflowRedirectVoicemailAudioFilePrompt
> - -TimeoutDisconnectTextToSpeechPrompt
> - -TimeoutDisconnectAudioFilePrompt
> - -TimeoutRedirectPersonTextToSpeechPrompt
> - -TimeoutRedirectPersonAudioFilePrompt
> - -TimeoutRedirectVoiceAppTextToSpeechPrompt
> - -TimeoutRedirectVoiceAppAudioFilePrompt
> - -TimeoutRedirectPhoneNumberTextToSpeechPrompt
> - -TimeoutRedirectPhoneNumberAudioFilePrompt
> - -TimeoutRedirectVoicemailTextToSpeechPrompt
> - -TimeoutRedirectVoicemailAudioFilePrompt
> - -NoAgentDisconnectTextToSpeechPrompt
> - -NoAgentDisconnectAudioFilePrompt
> - -NoAgentRedirectPersonTextToSpeechPrompt
> - -NoAgentRedirectPersonAudioFilePrompt
> - -NoAgentRedirectVoiceAppTextToSpeechPrompt
> - -NoAgentRedirectVoiceAppAudioFilePrompt
> - -NoAgentRedirectPhoneNumberTextToSpeechPrompt
> - -NoAgentRedirectPhoneNumberAudioFilePrompt
> - -NoAgentRedirectVoicemailTextToSpeechPrompt
> - -NoAgentRedirectVoicemailAudioFilePrompt

## EXAMPLES

### Example 1
```
New-CsCallQueue -Name "Help Desk" -UseDefaultMusicOnHold $true
```

This example creates a Call Queue for the organization named "Help Desk" using default music on hold.

### Example 2
```
New-CsCallQueue -Name "Help desk" -RoutingMethod Attendant -DistributionLists @("8521b0e3-51bd-4a4b-a8d6-b219a77a0a6a", "868dccd8-d723-4b4f-8d74-ab59e207c357") -AllowOptOut $false -AgentAlertTime 30 -OverflowThreshold 15 -OverflowAction Forward -OverflowActionTarget 7fd04db1-1c8e-4fdf-9af5-031514ba1358 -TimeoutThreshold 30 -TimeoutAction Disconnect -MusicOnHoldAudioFileId 1e81adaf-7c3e-4db1-9d61-5d135abb1bcc -WelcomeMusicAudioFileId 0b31bbe5-e2a0-4117-9b6f-956bca6023f8

```

This example creates a Call Queue for the organization named "Help Desk" with music on hold and welcome music audio files.


## PARAMETERS

### -Name
The Name parameter specifies a unique name for the Call Queue.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 
Applicable: Skype for Business Online

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AgentAlertTime
The AgentAlertTime parameter represents the time (in seconds) that a call can remain unanswered before it is automatically routed to the next agent. The AgentAlertTime can be set to any integer value between 15 and 180 seconds (3 minutes), inclusive. The default value is 30 seconds.

```yaml
Type: Int16
Parameter Sets: (All)
Aliases: 
Applicable: Skype for Business Online

Required: False
Position: Named
Default value: 30
Accept pipeline input: False
Accept wildcard characters: False
```

### -AllowOptOut
The AllowOptOut parameter indicates whether or not agents can opt in or opt out from taking calls from a Call Queue.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 
Applicable: Skype for Business Online

Required: False
Position: Named
Default value: True
Accept pipeline input: False
Accept wildcard characters: False
```

### -DistributionLists
The DistributionLists parameter lets you add all the members of the distribution lists to the Call Queue. This is a list of distribution list GUIDs. A service wide configurable maximum number of DLs per Call Queue are allowed. Only the first N (service wide configurable) agents from all distribution lists combined are considered for accepting the call. Nested DLs are supported. O365 Groups can also be used to add members to the Call Queue.

```yaml
Type: List
Parameter Sets: (All)
Aliases: 
Applicable: Skype for Business Online

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Tenant
This parameter is reserved for Microsoft internal use only.

```yaml
Type: Guid
Parameter Sets: (All)
Aliases: 
Applicable: Skype for Business Online

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UseDefaultMusicOnHold
The UseDefaultMusicOnHold parameter indicates that this Call Queue uses the default music on hold. This parameter cannot be specified together with MusicOnHoldAudioFileId.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 
Applicable: Skype for Business Online

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WelcomeMusicAudioFileId
The WelcomeMusicAudioFileId parameter represents the audio file to play when callers are connected with the Call Queue. This is the unique identifier of the audio file.

```yaml
Type: Guid
Parameter Sets: (All)
Aliases: 
Applicable: Skype for Business Online

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MusicOnHoldAudioFileId
The MusicOnHoldAudioFileId parameter represents music to play when callers are placed on hold. This is the unique identifier of the audio file. This parameter is required if the UseDefaultMusicOnHold parameter is not specified.

```yaml
Type: Guid
Parameter Sets: (All)
Aliases: 
Applicable: Skype for Business Online

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OverflowAction
The OverflowAction parameter designates the action to take if the overflow threshold is reached. The OverflowAction property must be set to one of the following values: DisconnectWithBusy, Forward, Voicemail, and SharedVoicemail. The default value is DisconnectWithBusy.

PARAMVALUE: DisconnectWithBusy | Forward | Voicemail | SharedVoicemail

```yaml
Type: Object
Parameter Sets: (All)
Aliases: 
Applicable: Skype for Business Online

Required: False
Position: Named
Default value: DisconnectWithBusy
Accept pipeline input: False
Accept wildcard characters: False
```

### -OverflowActionTarget
The OverflowActionTarget parameter represents the target of the overflow action. If the OverFlowAction is set to Forward, this parameter must be set to a Guid or a telephone number with a mandatory 'tel:' prefix. If the OverflowAction is set to SharedVoicemail, this parameter must be set to a group ID (Microsoft 365, Distribution list, or Mail-enabled security). Otherwise, this parameter is optional.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 
Applicable: Skype for Business Online

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OverflowThreshold
The OverflowThreshold parameter defines the number of calls that can be in the queue at any one time before the overflow action is triggered. The OverflowThreshold can be any integer value between 0 and 200, inclusive. A value of 0 causes calls not to reach agents and the overflow action to be taken immediately

```yaml
Type: Int16
Parameter Sets: (All)
Aliases: 
Applicable: Skype for Business Online

Required: False
Position: Named
Default value: 50
Accept pipeline input: False
Accept wildcard characters: False
```

### -TimeoutAction
The TimeoutAction parameter defines the action to take if the timeout threshold is reached. The TimeoutAction property must be set to one of the following values: Disconnect, Forward, Voicemail, and SharedVoicemail. The default value is Disconnect.

PARAMVALUE: Disconnect | Forward | Voicemail | SharedVoicemail

```yaml
Type: Object
Parameter Sets: (All)
Aliases: 
Applicable: Skype for Business Online

Required: False
Position: Named
Default value: Disconnect
Accept pipeline input: False
Accept wildcard characters: False
```

### -TimeoutActionTarget
The TimeoutActionTarget represents the target of the timeout action. If the TimeoutAction is set to Forward, this parameter must be set to a Guid or a telephone number with a mandatory 'tel:' prefix. If the TimeoutAction is set to SharedVoicemail, this parameter must be set to an Office 365 Group ID. Otherwise, this field is optional.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 
Applicable: Skype for Business Online

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TimeoutThreshold
The TimeoutThreshold parameter defines the time (in seconds) that a call can be in the queue before that call times out. At that point, the system will take the action specified by the TimeoutAction parameter. 
The TimeoutThreshold can be any integer value between 0 and 2700 seconds (inclusive), and is rounded to the nearest 15th interval. For example, if set to 47 seconds, then it is rounded down to 45. If set to 0, welcome music is played, and then the timeout action will be taken.

```yaml
Type: Int16
Parameter Sets: (All)
Aliases: 
Applicable: Skype for Business Online

Required: False
Position: Named
Default value: 1200
Accept pipeline input: False
Accept wildcard characters: False
```

### -NoAgentAction
The NoAgentAction parameter defines the action to take if the no agents condition is reached. The NoAgentAction property must be set to one of the following values: Queue, Disconnect, Forward, Voicemail, and SharedVoicemail. The default value is Queue.

PARAMVALUE: Queue | Disconnect | Forward | Voicemail | SharedVoicemail

```yaml
Type: Object
Parameter Sets: (All)
Aliases: 
Applicable: Skype for Business Online

Required: False
Position: Named
Default value: Disconnect
Accept pipeline input: False
Accept wildcard characters: False
```

### -NoAgentActionTarget
The NoAgentActionTarget represents the target of the no agent action. If the NoAgentAction is set to Forward, this parameter must be set to a GUID or a telephone number with a mandatory 'tel:' prefix. If the NoAgentAction is set to SharedVoicemail, this parameter must be set to a Microsoft 365 Group ID. Otherwise, this field is optional.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 
Applicable: Skype for Business Online

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RoutingMethod
The RoutingMethod parameter defines how agents will be called in a Call Queue. If the routing method is set to Serial, then agents will be called one at a time. If the routing method is set to Attendant, then agents will be called in parallel. If the routing method is set to RoundRobin, the agents will be called using the Round Robin strategy so that all agents share the call load equally. If the routing method is set to LongestIdle, the agents will be called based on their idle time, that is, the agent that has been idle for the longest period will be called.

PARAMVALUE: Attendant | Serial | RoundRobin | LongestIdle

```yaml
Type: Object
Parameter Sets: (All)
Aliases: 
Applicable: Skype for Business Online

Required: False
Position: Named
Default value: Attendant
Accept pipeline input: False
Accept wildcard characters: False
```

### -PresenceBasedRouting
The PresenceBasedRouting parameter indicates whether or not presence based routing will be applied while call being routed to Call Queue agents. When set to False, calls will be routed to agents who have opted in to receive calls, regardless of their presence state. When set to True, opted-in agents will receive calls only when their presence state is Available.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 
Applicable: Skype for Business Online

Required: False
Position: Named
Default value: True
Accept pipeline input: False
Accept wildcard characters: False
```

### -ConferenceMode
The ConferenceMode parameter indicates whether or not Conference mode will be applied on calls for this Call queue. Conference mode significantly reduces the amount of time it takes for a caller to be connected to an agent, after the agent accepts the call. The following bullet points detail the difference between both modes:

- Conference Mode Disabled: CQ call is presented to agent. Agent answers and media streams are setup. Based on geographic location of the CQ call and agent, there may be a slight delay in setting up the media streams which may result in some dead air and the first part of the conversation being cut off.

- Conference Mode Enabled: CQ call is put into conference. Agent answers and is brought into conference. Media streams are already setup when agent is brought into conference thus no dead air, and first bit of conversation will not be cut off.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 
Applicable: Skype for Business Online

Required: False
Position: Named
Default value: True
Accept pipeline input: False
Accept wildcard characters: False
```

### -Users
The Users parameter lets you add agents to the Call Queue. This parameter expects a list of user unique identifiers (GUID).

```yaml
Type: List
Parameter Sets: (All)
Aliases: 
Applicable: Skype for Business Online

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LanguageId
The LanguageId parameter indicates the language that is used to play shared voicemail prompts. This parameter becomes a required parameter if either OverflowAction or TimeoutAction is set to SharedVoicemail.

You can query the supported languages using the Get-CsAutoAttendantSupportedLanguage cmdlet.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 
Applicable: Skype for Business Online

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LineUri
This parameter is reserved for Microsoft internal use only.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 
Applicable: Skype for Business Online

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OboResourceAccountIds
The OboResourceAccountIds parameter lets you add resource account with phone number to the Call Queue. The agents in the Call Queue will be able to make outbound calls using the phone number on the resource accounts.  This is a list of resource account GUIDs.

Only Call Queue managed by a Teams Channel will be able to use this feature. For more information, refer to [Manage your support Call Queue in Teams](https://support.microsoft.com/office/manage-your-support-call-queue-in-teams-9f07dabe-91c6-4a9b-a545-8ffdddd2504e).

```yaml
Type: List
Parameter Sets: (All)
Aliases: 
Applicable: Skype for Business Online

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OverflowDisconnectTextToSpeechPrompt
The OverflowDisconnectTextToSpeechPrompt parameter indicates the Text-to-Speech (TTS) prompt which is played to the caller when being disconnected due to overflow. 

```yaml
Type: String
Parameter Sets: (All)
Aliases: 
Applicable: Skype for Business Online

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OverflowDisconnectAudioFilePrompt
The OverflowDisconnectAudioFilePrompt parameter indicates the unique identifier for the Audio file prompt which is played to the caller when being disconnected due to overflow.

```yaml
Type: Guid
Parameter Sets: (All)
Aliases: 
Applicable: Skype for Business Online

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OverflowRedirectPersonTextToSpeechPrompt
The OverflowRedirectPersonTextToSpeechPrompt parameter indicates the Text-to-Speech (TTS) prompt which is played to the caller when being redirected to a person in the organization due to overflow. 

```yaml
Type: String
Parameter Sets: (All)
Aliases: 
Applicable: Skype for Business Online

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OverflowRedirectPersonAudioFilePrompt
The OverflowRedirectPersonAudioFilePrompt parameter indicates the unique identifier for the Audio file prompt which is played to the caller when being redirected to a person in the organization due to overflow. 

```yaml
Type: Guid
Parameter Sets: (All)
Aliases: 
Applicable: Skype for Business Online

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OverflowRedirectVoiceAppTextToSpeechPrompt
The OverflowRedirectVoiceAppsTextToSpeechPrompt parameter indicates the Text-to-Speech (TTS) prompt which is played to the caller when being redirected to a voice application due to overflow. 

```yaml
Type: String
Parameter Sets: (All)
Aliases: 
Applicable: Skype for Business Online

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OverflowRedirectVoiceAppAudioFilePrompt
The OverflowRedirectVoiceAppAudioFilePrompt parameter indicates the unique identifier for the Audio file prompt which is played to the caller when being redirected to a voice application due to overflow. 

```yaml
Type: Guid
Parameter Sets: (All)
Aliases: 
Applicable: Skype for Business Online

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OverflowRedirectPhoneNumberTextToSpeechPrompt
The OverflowRedirectPhoneNumberTextToSpeechPrompt parameter indicates the Text-to-Speech (TTS) prompt which is played to the caller when being redirected to an external PSTN phone number due to overflow. 

```yaml
Type: String
Parameter Sets: (All)
Aliases: 
Applicable: Skype for Business Online

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OverflowRedirectPhoneNumberAudioFilePrompt
The OverflowRedirectPhoneNumberAudioFilePrompt parameter indicates the unique identifier for the Audio file prompt which is played to the caller when being redirected to an external PSTN phone number due to overflow. 

```yaml
Type: Guid
Parameter Sets: (All)
Aliases: 
Applicable: Skype for Business Online

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OverflowRedirectVoicemailTextToSpeechPrompt
The OverflowRedirectVoicemailTextToSpeechPrompt parameter indicates the Text-to-Speech (TTS) prompt which is played to the caller when being redirected to a person's voicemail due to overflow. 

```yaml
Type: String
Parameter Sets: (All)
Aliases: 
Applicable: Skype for Business Online

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OverflowRedirectVoicemailAudioFilePrompt
The OverflowRedirectVoiceMailAudioFilePrompt parameter indicates the unique identifier for the Audio file prompt which is played to the caller when being redirected to a person's voicemail due to overflow. 

```yaml
Type: Guid
Parameter Sets: (All)
Aliases: 
Applicable: Skype for Business Online

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OverflowSharedVoicemailTextToSpeechPrompt
The OverflowSharedVoicemailTextToSpeechPrompt parameter indicates the Text-to-Speech (TTS) prompt which is to be played as a greeting to the caller when transferred to shared voicemail on overflow. This parameter becomes a required parameter when OverflowAction is SharedVoicemail and OverflowSharedVoicemailAudioFilePrompt is null.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 
Applicable: Skype for Business Online

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OverflowSharedVoicemailAudioFilePrompt
The OverflowSharedVoicemailAudioFilePrompt parameter indicates the unique identifier for the Audio file prompt which is to be played as a greeting to the caller when transferred to shared voicemail on overflow. This parameter becomes a required parameter when OverflowAction is SharedVoicemail and OverflowSharedVoicemailTextToSpeechPrompt is null.

```yaml
Type: Guid
Parameter Sets: (All)
Aliases: 
Applicable: Skype for Business Online

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EnableOverflowSharedVoicemailTranscription
The EnableOverflowSharedVoicemailTranscription parameter is used to turn on transcription for voicemails left by a caller on overflow. This parameter is only applicable when OverflowAction is set to SharedVoicemail.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 
Applicable: Skype for Business Online

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -EnableOverflowSharedVoicemailSystemPromptSuppression
The EnableOverflowSharedVoicemailSystemPromptSuppress parameter is used to turn off the default voicemail system prompts.  This parameter is only applicable when OverflowAction is set to SharedVoicemail.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 
Applicable: Skype for Business Online

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -TimeoutDisconnectTextToSpeechPrompt
The TimeoutDisconnectTextToSpeechPrompt parameter indicates the Text-to-Speech (TTS) prompt which is played to the caller when being disconnected due to timeout. 

```yaml
Type: String
Parameter Sets: (All)
Aliases: 
Applicable: Skype for Business Online

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TimeoutDisconnectAudioFilePrompt
The TimeoutDisconnectAudioFilePrompt parameter indicates the unique identifier for the Audio file prompt which is played to the caller when being disconnected due to timeout.

```yaml
Type: Guid
Parameter Sets: (All)
Aliases: 
Applicable: Skype for Business Online

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TimeoutRedirectPersonTextToSpeechPrompt
The TimeoutRedirectPersonTextToSpeechPrompt parameter indicates the Text-to-Speech (TTS) prompt which is played to the caller when being redirected to a person in the organization due to timeout. 

```yaml
Type: String
Parameter Sets: (All)
Aliases: 
Applicable: Skype for Business Online

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TimeoutRedirectPersonAudioFilePrompt
The TimeoutRedirectPersonAudioFilePrompt parameter indicates the unique identifier for the Audio file prompt which is played to the caller when being redirected to a person in the organization due to timeout. 

```yaml
Type: Guid
Parameter Sets: (All)
Aliases: 
Applicable: Skype for Business Online

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TimeoutRedirectVoiceAppTextToSpeechPrompt
The TimeoutRedirectVoiceAppsTextToSpeechPrompt parameter indicates the Text-to-Speech (TTS) prompt which is played to the caller when being redirected to a voice application due to timeout. 

```yaml
Type: String
Parameter Sets: (All)
Aliases: 
Applicable: Skype for Business Online

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TimeoutRedirectVoiceAppAudioFilePrompt
The TimeoutRedirectVoiceAppAudioFilePrompt parameter indicates the unique identifier for the Audio file prompt which is played to the caller when being redirected to a voice application due to timeout. 

```yaml
Type: Guid
Parameter Sets: (All)
Aliases: 
Applicable: Skype for Business Online

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TimeoutRedirectPhoneNumberTextToSpeechPrompt
The TimeoutRedirectPhoneNumberTextToSpeechPrompt parameter indicates the Text-to-Speech (TTS) prompt which is played to the caller when being redirected to an external PSTN phone number due to timeout. 

```yaml
Type: String
Parameter Sets: (All)
Aliases: 
Applicable: Skype for Business Online

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TimeoutRedirectPhoneNumberAudioFilePrompt
The TimeoutRedirectPhoneNumberAudioFilePrompt parameter indicates the unique identifier for the Audio file prompt which is played to the caller when being redirected to an external PSTN phone number due to timeout. 

```yaml
Type: Guid
Parameter Sets: (All)
Aliases: 
Applicable: Skype for Business Online

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TimeoutRedirectVoicemailTextToSpeechPrompt
The TimeoutRedirectVoicemailTextToSpeechPrompt parameter indicates the Text-to-Speech (TTS) prompt which is played to the caller when being redirected to a person's voicemail due to timeout. 

```yaml
Type: String
Parameter Sets: (All)
Aliases: 
Applicable: Skype for Business Online

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TimeoutRedirectVoicemailAudioFilePrompt
The TimeoutRedirectVoiceMailAudioFilePrompt parameter indicates the unique identifier for the Audio file prompt which is played to the caller when being redirected to a person's voicemail due to timeout. 

```yaml
Type: Guid
Parameter Sets: (All)
Aliases: 
Applicable: Skype for Business Online

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TimeoutSharedVoicemailTextToSpeechPrompt
The TimeoutSharedVoicemailTextToSpeechPrompt parameter indicates the Text-to-Speech (TTS) prompt which is to be played as a greeting to the caller when transferred to shared voicemail on timeout. This parameter becomes a required parameter when TimeoutAction is SharedVoicemail and TimeoutSharedVoicemailAudioFilePrompt is null.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 
Applicable: Skype for Business Online

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TimeoutSharedVoicemailAudioFilePrompt
The TimeoutSharedVoicemailAudioFilePrompt parameter indicates the unique identifier for the Audio file prompt which is to be played as a greeting to the caller when transferred to shared voicemail on timeout. This parameter becomes a required parameter when TimeoutAction is SharedVoicemail and TimeoutSharedVoicemailTextToSpeechPrompt is null.

```yaml
Type: Guid
Parameter Sets: (All)
Aliases: 
Applicable: Skype for Business Online

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EnableTimeoutSharedVoicemailTranscription
The EnableTimeoutSharedVoicemailTranscription parameter is used to turn on transcription for voicemails left by a caller on timeout. This parameter is only applicable when TimeoutAction is set to SharedVoicemail.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 
Applicable: Skype for Business Online

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -EnableTimeoutSharedVoicemailSystemPromptSuppression
The EnableTimeoutSharedVoicemailSystemPromptSuppress parameter is used to turn off the default voicemail system prompts. This parameter is only applicable when OverflowAction is set to SharedVoicemail.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 
Applicable: Skype for Business Online

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -NoAgentDisconnectTextToSpeechPrompt
The NoAgentDisconnectTextToSpeechPrompt parameter indicates the Text-to-Speech (TTS) prompt which is played to the caller when being disconnected due to no agents. 

```yaml
Type: String
Parameter Sets: (All)
Aliases: 
Applicable: Skype for Business Online

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NoAgentDisconnectAudioFilePrompt
The NoAgentDisconnectAudioFilePrompt parameter indicates the unique identifier for the Audio file prompt which is played to the caller when being disconnected due to no agents.

```yaml
Type: Guid
Parameter Sets: (All)
Aliases: 
Applicable: Skype for Business Online

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NoAgentRedirectPersonTextToSpeechPrompt
The NoAgentRedirectPersonTextToSpeechPrompt parameter indicates the Text-to-Speech (TTS) prompt which is played to the caller when being redirected to a person in the organization due to no agents. 

```yaml
Type: String
Parameter Sets: (All)
Aliases: 
Applicable: Skype for Business Online

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NoAgentRedirectPersonAudioFilePrompt
The NoAgentRedirectPersonAudioFilePrompt parameter indicates the unique identifier for the Audio file prompt which is played to the caller when being redirected to a person in the organization due to no agents. 

```yaml
Type: Guid
Parameter Sets: (All)
Aliases: 
Applicable: Skype for Business Online

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NoAgentRedirectVoiceAppTextToSpeechPrompt
The NoAgentRedirectVoiceAppsTextToSpeechPrompt parameter indicates the Text-to-Speech (TTS) prompt which is played to the caller when being redirected to a voice application due to no agents. 

```yaml
Type: String
Parameter Sets: (All)
Aliases: 
Applicable: Skype for Business Online

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NoAgentRedirectVoiceAppAudioFilePrompt
The NoAgentRedirectVoiceAppAudioFilePrompt parameter indicates the unique identifier for the Audio file prompt which is played to the caller when being redirected to a voice application due to no agents. 

```yaml
Type: Guid
Parameter Sets: (All)
Aliases: 
Applicable: Skype for Business Online

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NoAgentRedirectPhoneNumberTextToSpeechPrompt
The NoAgentRedirectPhoneNumberTextToSpeechPrompt parameter indicates the Text-to-Speech (TTS) prompt which is played to the caller when being redirected to an external PSTN phone number due to no agents. 

```yaml
Type: String
Parameter Sets: (All)
Aliases: 
Applicable: Skype for Business Online

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NoAgentsRedirectPhoneNumberAudioFilePrompt
The NoAgentRedirectPhoneNumberAudioFilePrompt parameter indicates the unique identifier for the Audio file prompt which is played to the caller when being redirected to an external PSTN phone number due to no agents. 

```yaml
Type: Guid
Parameter Sets: (All)
Aliases: 
Applicable: Skype for Business Online

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NoAgentRedirectVoicemailTextToSpeechPrompt
The NoAgentRedirectVoicemailTextToSpeechPrompt parameter indicates the Text-to-Speech (TTS) prompt which is played to the caller when being redirected to a person's voicemail due to no agent. 

```yaml
Type: String
Parameter Sets: (All)
Aliases: 
Applicable: Skype for Business Online

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NoAgentRedirectVoicemailAudioFilePrompt
The NoAgentRedirectVoiceMailAudioFilePrompt parameter indicates the unique identifier for the Audio file prompt which is played to the caller when being redirected to a person's voicemail due to no agent. 

```yaml
Type: Guid
Parameter Sets: (All)
Aliases: 
Applicable: Skype for Business Online

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NoAgentSharedVoicemailTextToSpeechPrompt
The NoAgentSharedVoicemailTextToSpeechPrompt parameter indicates the Text-to-Speech (TTS) prompt which is to be played as a greeting to the caller when transferred to shared voicemail on no agents. This parameter becomes a required parameter when NoAgentAction is SharedVoicemail and NoAgentSharedVoicemailAudioFilePrompt is null.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 
Applicable: Skype for Business Online

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NoAgentSharedVoicemailAudioFilePrompt
The NoAgentSharedVoicemailAudioFilePrompt parameter indicates the unique identifier for the Audio file prompt which is to be played as a greeting to the caller when transferred to shared voicemail on no agents. This parameter becomes a required parameter when NoAgentAction is SharedVoicemail and NoAgentSharedVoicemailTextToSpeechPrompt is null.

```yaml
Type: Guid
Parameter Sets: (All)
Aliases: 
Applicable: Skype for Business Online

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EnableNoAgentSharedVoicemailTranscription
The EnableNoAgentSharedVoicemailTranscription parameter is used to turn on transcription for voicemails left by a caller on no agents. This parameter is only applicable when NoAgentAction is set to SharedVoicemail.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 
Applicable: Skype for Business Online

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -EnableNoAgentSharedVoicemailSystemPromptSuppression
The EnableNoAgentSharedVoicemailSystemPromptSuppress parameter is used to turn off the default voicemail system prompts. This parameter is only applicable when NoAgentAction is set to SharedVoicemail.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 
Applicable: Skype for Business Online

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -ChannelId
Id of the channel to connect a call queue to.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 
Applicable: Skype for Business Online

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ChannelUserObjectId
Guid should contain 32 digits with 4 dashes (xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx). This is the GUID of one of the owners of the team the channels belongs to.

```yaml
Type: Guid
Parameter Sets: (All)
Aliases: 
Applicable: Skype for Business Online

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AuthorizedUsers
This is a list of GUIDs for users who are authorized to make changes to this call queue. The users must also have a TeamsVoiceApplications policy assigned. The GUID should contain 32 digits with 4 dashes (xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx). 

```yaml
Type: List
Parameter Sets: (All)
Aliases: 
Applicable: Skype for Business Online

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -HideAuthorizedUsers
This is a list of GUIDs of authorized users who should not appear on the list of supervisors for the agents who are members of this queue.  The GUID should contain 32 digits with 4 dashes (xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx). 

```yaml
Type: List
Parameter Sets: (All)
Aliases: 
Applicable: Skype for Business Online

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WelcomeTextToSpeechPrompt
This parameter indicates which Text-to-Speech (TTS) prompt is played when callers are connected to the Call Queue.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Rtc.Management.Hosted.CallQueue.Models.CallQueue

## NOTES

## RELATED LINKS
[Create a Phone System Call Queue](https://support.office.com/article/Create-a-Phone-System-call-queue-67ccda94-1210-43fb-a25b-7b9785f8a061)
