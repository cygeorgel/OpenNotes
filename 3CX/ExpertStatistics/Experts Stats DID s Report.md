# Expert Stats DIDs Report

This is the **Design Document** for a new Expert Stats DIDs  Report.

See also https://github.com/cygeorgel/OpenNotes/blob/master/Telco/Pbx3cx/ExpertStatistics/CsvReports/DIDs%20Report.md, especially for definitions.
## Default view

The default view shows the data for the PBX.

This matches the columns A to G of the CSV / Excel version.

| DID    | Solicited calls | Answered calls | Abandoned calls | Diverted calls | Diverted internally | Diverted externally |
| ------ | --------------- | -------------- | --------------- | -------------- | ------------------- | ------------------- |
| +33... | nb              | nb \| %        | nb \| %<br>     | nb \| %        | nb \| %             | nb \| %             |

Then I imagine a "accordion" system that would make the user able to switch to the different detailed views : 

- first level of the call
- queue level
- extension level
## First level of the call

Everything that happens at the first level of the call (PBX entry point), i.e. before any queue or extension.

| DID    | Time (waiting)                         | Solicited calls | Forwarded calls | Diverted calls | Diverted internally | Diverted externally |
| ------ | -------------------------------------- | --------------- | --------------- | -------------- | ------------------- | ------------------- |
| +33... | 00:00:00 (total)<br>00:00:00 (average) | nb              | nb \| %         | nb \| %        | nb \| %             | nb \| %             |

Forwarded calls i.e. forwarded to a queue or an extension (forwarded to a voicemail is a diversion).
## Queue Level

| DID    | Time (waiting)                         | Solicited calls | Answered calls | Abandoned calls | Diverted calls | Diverted internally | Diverted externally |
| ------ | -------------------------------------- | --------------- | -------------- | --------------- | -------------- | ------------------- | ------------------- |
| +33... | 00:00:00 (total)<br>00:00:00 (average) | nb              | nb  \| %       | nb \| %         | nb \| %        | nb \| %             | nb \| %<br>         |
## Extension level

| DID    | Time (talking)                         | Solicited calls | Solicited segments | Diverted segments | Answered calls | Answered segments | Diverted calls | Diverted calls externally | Transferred calls | Trans ferred segments | Transferred calls externally |
| ------ | -------------------------------------- | --------------- | ------------------ | ----------------- | -------------- | ----------------- | -------------- | ------------------------- | ----------------- | --------------------- | ---------------------------- |
| +33... | 00:00:00 (total)<br>00:00:00 (average) | nb              | nb                 | nb \| %           | nb \| %        | nb \| %           | nb \| %<br>    | nb \| %                   | nb \| %           | nb \| %               | nb \| %                      |



