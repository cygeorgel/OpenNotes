---
title: DIDs Reports
author: Cyrille Georgel < cyrille@bluerocktel.com >
tags:
  - bluerocktel
  - cx-engine
  - 3CX
  - statistics
  - expert-statistics
  - expert-stats
status: Working
---

# DIDs Report 

## Sample

### Json representation

```
{
    "0331xxxxxxxx": {
        "did": "00331xxxxxxxx",
        "c_solicited_calls": 426,
        "c_answered_calls": 131,
        "c_abandoned_calls": 0,
        "c_diverted_calls": 258,
        "c_diverted_calls_internally": 187,
        "c_diverted_calls_externally": 71,
        "i_solicited_calls": 426,
        "i_forwarded_calls": 228,
        "i_diverted_calls": 198,
        "i_diverted_calls_internally": 127,
        "i_diverted_calls_externally": 71,
        "q_solicited_calls": 191,
        "q_answered_calls": 131,
        "q_abandoned_calls": 0,
        "q_diverted_calls": 60,
        "q_diverted_calls_internally": 0,
        "q_diverted_calls_externally": 60,
        "e_solicited_calls": 226,
        "e_solicited_segments": 554,
        "e_diverted_segments": 853,
        "e_answered_calls": 131,
        "e_answered_segments": 135,
        "e_diverted_calls": 0,
        "e_diverted_calls_externally": 0,
        "e_transferred_segments": 4,
        "e_transferred_calls": 4,
        "e_transferred_calls_externally": 0
    }
}
```

### CSV report

[Report CSV format](sample.csv)

## Definitions

### did

The DID (Direct Inward Dialing) we get the data for.

### "c_" prefixed keys

"c" stands for "calls": those keys contain the data of all the calls incoming via this specific DID.

#### c_solicited_calls

The number of calls reaching the DID within the observed period.

#### c_answered_calls

The number of calls answered within the observed period.

In our statistics, a call is answered only if answered by an extension.

#### c_abandoned_calls

The number of calls left by the caller.

#### c_diverted_calls

The number of calls diverted, either internally (i.e. voicemail) or externally (number).

This include all kinds of diversions, for example diversions by the Pbx and diversions by the queue.

#### c_diverted_externally

The number of calls diverted to an external destination.

This include all kinds of diversions, for example diversions by the Pbx and diversions by the queue.

### "i_" prefixed keys

"i" stands for "in": those keys contain the data for what happens of the first level of the call, i.e. a IVR (Interactive Voice Response), before any queue or extension.

#### i_solicited_calls

i_solicited_calls should always match c_solicited_calls.

#### i_forwarded_calls

The number of calls forwarded by the first level to a queue or an extension.

#### i_diverted_calls

The number of calls diverted at i level.

#### i_diverted_calls_internally

The number of calls diverted a i level to an internal destination (i.e. voicemail).

#### i_diverted_calls_externally

The number of calls diverted at "in" level to a external destination (the trunk is solicited by this diversion).

### "q_" prefixed keys

"q" stands for "Queue" (Call Queue): those key contain the data for what happened a queue level.

#### q_solicited_calls

The number of calls reaching the queue level.

#### q_answered_calls

The number of calls answered.

#### q_diverted_calls

The number of calls diverted by the queue.

#### q_diverted_calls_internally

The number of calls diverted by the call queue to a internal destination (i.e. voicemail)

#### q_diverted_calls_externally

The number of calls diverted by the call queue to an external destination (the trunk is solicited by this diversion).

### "e_" prefixed keys

"e" stands for "Extension" : those keyes contain the data for everything happening at extension level.

#### e_solicited_calls

The number of times the calls reach an extension. If a single call reaches two different extension, e_solicited_calls will be increased by two (therefore e_solicited_calls can be higher than q_solicited_calls).

#### e_solicited_segments

The number of call segments that have reached a extension (answered or not). If the same call reached several extensions, it will generate as many 'e_solicited_segments'. If the same call reached the same extension several times, it will also generate as many 'e_solicited_segments'.

#### e_diverted_segments

The number of call segments that have reached an extension without being answered.

### e_answered_calls

The number of unique calls that have been answered by at least one extension.

### e_answered_segments

The number of segments of calls that have been answered by an extension.

Example: if Jack answers a call, it will increase both the 'e_answered_calls' and the 'e_answered_segments' keys. If Jack transfers the calls to Jane, it will increase the 'e_answered_segments' key by one, but it will not change the 'e_answered_calls' value.

#### e_diverted_calls

The number of calls having at least one diverted segment.

#### e_diverted_calls_externally

Not used.

#### e_transferred_segments

The number of segments transferred internally or externally, at extension level.

#### e_transferred_calls

The number of calls transferred internally or externally, at extension level.

#### e_transferred_calls_externally

The number of calls transferred externally, at extension level.
