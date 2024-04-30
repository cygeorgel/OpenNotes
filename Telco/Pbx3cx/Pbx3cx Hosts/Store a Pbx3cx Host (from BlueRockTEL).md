##  Step 1: get customer by origin (if exists)

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

## Step 1b: store the customer (if not exists)

```
POST /api/v1.2/customers
```

## Step 2: store the Pbx3cx Host

```
POST /api/v1.2/pbx3cx-hosts
```

### Parameters

- host_name
- ip_address
- web_username
- web_password
- licence_key
- sbc_aliases
## Step 3: attach the Pbx3cx Host to the customer

```
POST /api/v1.2/customer-pbx3cx-host
```

### Parameters
- customer_code
- host_code
- action: attach, detach, syncWithoutDetaching
