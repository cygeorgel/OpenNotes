# Get Pbx3CX Call

Getting a single call (with detail of segments and information about its recording).

## Route

```
GET api/v1.2/{pbx3cx_host}/call
```

## Exemple of  response

```
{
	"call_id": "433195",
	"start_time": "2024-07-11 12:09:28+00",
	"end_time": "2024-07-11 12:22:09+00",
	"is_answered": "1",
	"segments": {
		"1": {
			"call_id": "433195",
			"seg_id": "1130408",
			"seg_type": "1",
			"seg_order": "1",
			"start_time": "2024-07-11 12:09:28",
			"end_time": "2024-07-11 12:09:28",
			"src_dn_type": "1",
			"src_dn": "10001",
			"src_display_name": "014*******",
			"src_firstlastname": "",
			"dst_start_time": "2024-07-11 12:09:28",
			"dst_answer_time": null,
			"dst_end_time": "2024-07-11 12:09:28",
			"dst_billing_rate": "",
			"dst_dn_type": "14",
			"dst_dn": "supportv2.Main",
			"dst_display_name": "",
			"dst_firstlastname": "",
			"dst_caller_number": "Ext.supportv2.Main",
			"dst_dn_class": "0",
			"act": "1",
			"act_dn_type": "",
			"act_dn": "",
			"act_display_name": "",
			"act_firstlastname": ""
		},
		"2": {
			"call_id": "433195",
			"seg_id": "1130409",
			"seg_type": "2",
			"seg_order": "2",
			"start_time": "2024-07-11 12:09:28",
			"end_time": "2024-07-11 12:09:47",
			"src_dn_type": "1",
			"src_dn": "10001",
			"src_display_name": "014*******",
			"src_firstlastname": "",
			"dst_start_time": "2024-07-11 12:09:28",
			"dst_answer_time": "2024-07-11 12:09:28",
			"dst_end_time": "2024-07-11 12:09:47",
			"dst_billing_rate": "",
			"dst_dn_type": "14",
			"dst_dn": "supportv2.Main",
			"dst_display_name": "",
			"dst_firstlastname": "",
			"dst_caller_number": "Ext.supportv2.Main",
			"dst_dn_class": "0",
			"act": "10",
			"act_dn_type": "4",
			"act_dn": "809",
			"act_display_name": "SupportFR",
			"act_firstlastname": ""
		},
		"3": {
			"call_id": "433195",
			"seg_id": "1130410",
			"seg_type": "1",
			"seg_order": "3",
			"start_time": "2024-07-11 12:09:47",
			"end_time": "2024-07-11 12:09:47",
			"src_dn_type": "1",
			"src_dn": "10001",
			"src_display_name": "014*******",
			"src_firstlastname": "",
			"dst_start_time": "2024-07-11 12:09:47",
			"dst_answer_time": null,
			"dst_end_time": "2024-07-11 12:09:47",
			"dst_billing_rate": "",
			"dst_dn_type": "4",
			"dst_dn": "809",
			"dst_display_name": "SupportFR",
			"dst_firstlastname": "",
			"dst_caller_number": "Ext.809",
			"dst_dn_class": "0",
			"act": "1",
			"act_dn_type": "",
			"act_dn": "",
			"act_display_name": "",
			"act_firstlastname": ""
		},
		"4": {
			"call_id": "433195",
			"seg_id": "1130411",
			"seg_type": "2",
			"seg_order": "4",
			"start_time": "2024-07-11 12:09:47",
			"end_time": "2024-07-11 12:10:10",
			"src_dn_type": "1",
			"src_dn": "10001",
			"src_display_name": "014*******",
			"src_firstlastname": "",
			"dst_start_time": "2024-07-11 12:09:47",
			"dst_answer_time": "2024-07-11 12:09:47",
			"dst_end_time": "2024-07-11 12:10:10",
			"dst_billing_rate": "",
			"dst_dn_type": "4",
			"dst_dn": "809",
			"dst_display_name": "SupportFR",
			"dst_firstlastname": "",
			"dst_caller_number": "Ext.809",
			"dst_dn_class": "0",
			"act": "10",
			"act_dn_type": "0",
			"act_dn": "101",
			"act_display_name": "Yann",
			"act_firstlastname": "Yann"
		},
		"5": {
			"call_id": "433195",
			"seg_id": "1130412",
			"seg_type": "1",
			"seg_order": "5",
			"start_time": "2024-07-11 12:09:59",
			"end_time": "2024-07-11 12:10:10",
			"src_dn_type": "1",
			"src_dn": "10001",
			"src_display_name": "014*******",
			"src_firstlastname": "",
			"dst_start_time": "2024-07-11 12:09:59",
			"dst_answer_time": null,
			"dst_end_time": "2024-07-11 12:10:10",
			"dst_billing_rate": "",
			"dst_dn_type": "0",
			"dst_dn": "101",
			"dst_display_name": "Yann",
			"dst_firstlastname": "",
			"dst_caller_number": "Ext.101",
			"dst_dn_class": "0",
			"act": "2",
			"act_dn_type": "0",
			"act_dn": "101",
			"act_display_name": "Yann",
			"act_firstlastname": "Yann"
		},
		"6": {
			"call_id": "433195",
			"seg_id": "1130413",
			"seg_type": "1",
			"seg_order": "6",
			"start_time": "2024-07-11 12:10:10",
			"end_time": "2024-07-11 12:10:10",
			"src_dn_type": "1",
			"src_dn": "10001",
			"src_display_name": "014*******",
			"src_firstlastname": "",
			"dst_start_time": "2024-07-11 12:10:10",
			"dst_answer_time": "2024-07-11 12:10:10",
			"dst_end_time": "2024-07-11 12:22:09",
			"dst_billing_rate": "",
			"dst_dn_type": "0",
			"dst_dn": "101",
			"dst_display_name": "Yann",
			"dst_firstlastname": "Yann",
			"dst_caller_number": "Ext.101",
			"dst_dn_class": "0",
			"act": "1",
			"act_dn_type": "",
			"act_dn": "",
			"act_display_name": "",
			"act_firstlastname": ""
		},
		"7": {
			"call_id": "433195",
			"seg_id": "1130414",
			"seg_type": "2",
			"seg_order": "7",
			"start_time": "2024-07-11 12:10:10",
			"end_time": "2024-07-11 12:22:09",
			"src_dn_type": "1",
			"src_dn": "10001",
			"src_display_name": "014*******",
			"src_firstlastname": "",
			"dst_start_time": "2024-07-11 12:10:10",
			"dst_answer_time": "2024-07-11 12:10:10",
			"dst_end_time": "2024-07-11 12:22:09",
			"dst_billing_rate": "",
			"dst_dn_type": "0",
			"dst_dn": "101",
			"dst_display_name": "Yann",
			"dst_firstlastname": "Yann",
			"dst_caller_number": "Ext.101",
			"dst_dn_class": "0",
			"act": "6",
			"act_dn_type": "",
			"act_dn": "",
			"act_display_name": "",
			"act_firstlastname": ""
		}
	},
	"participants": [],
	"recordings": [
		"101\/[]_101-014*******_20240711121010(56492).wav"
	],
	"display_name": "014*******",
	"firstlastname": "",
	"did_number": "017*******",
	"caller_number": "014*******"
}
```



