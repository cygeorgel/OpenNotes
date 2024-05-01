# Get the Customer with their Pbx3cx Hosts

The customer has a reference within the BlueRockTEL instance and a code within the Pbx3cx Hosts API. You get this code by passing the tenant code and the tenant reference to the "Get customer by origin"  route :

##  Step 1: get customer by origin

```
api/v1.2/customer-from-origin/{tenant_code}/{tenant_reference}
```

Returns the code of the customer within Pbx3cx Hosts API :

```
{
	"code": "abcdef",
	"tenant_code": "0000",
	"tenant_reference": "CLXXXX",
	"name": "HELLO TELECOM",
}
```

## Step 2: get customer (with Pbx3cx hosts)

Then you can use the customer code :

```
api/v1.2/customers/abcdef
```

```
{
	"code": "fedcba",
	"tenant_code": "0000",
	"tenant_reference": "CLXXXX",
	"name": "HELLO TELECOM",
	"pbx3cx_hosts": [
		{
			"id": 1,
			"active": 1,
			"customer_account": null,
			"customer_file_id": null,
			"code": "abcfed",
			"host_name": "host.3cx.com",
			"ip_address": "1.1.1.1",
			...
			}
		}
	]
```



