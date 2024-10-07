# Inbound rules
## Without specific hours:

![image](https://storage.gra.cloud.ovh.net/v1/AUTH_9c30d35f284f44b2bda08609e7c19f33/cyrille_public/20241006151126.png)


```

= App\Models\Pbx3cxHostCalendar {#5408
    id: 602,
    pbx3cx_host_code: "df7jol",
    idcalendar: 5817,
    dummy: 1,
    fkdirulehours: 2,
    pv_ignore_holidays: "0",
    created_at: "2024-10-06 14:32:13",
    updated_at: "2024-10-06 14:32:13",
}

```
  
=> idcalendar = 5817

=> fkdirulehours : 2

*(shoud be fkidrulehours, of course it is a typo)*

### API response:

```

[0184799461] => Array
	(
		[rule_name] => 7. regle de reference
		[dst_dn] => 007
		[out_of_office_iddn] => 3100
		[out_of_office_destination_type] => extension
		[out_of_office_destination] => 103
		[rules] => Array
			(
				[0] => Array
					(
						[day_of_week] => 1
						[start] => 08:00:00
						[end] => 17:00:00
					)

				[1] => Array
					(
						[day_of_week] => 2
						[start] => 09:00:00
						[end] => 18:00:00
					)

				[2] => Array
					(
						[day_of_week] => 3
						[start] => 09:00:00
						[end] => 18:00:00
					)

				[3] => Array
					(
						[day_of_week] => 4
						[start] => 09:00:00
						[end] => 18:00:00
					)

				[4] => Array
					(
						[day_of_week] => 5
						[start] => 09:00:00
						[end] => 18:00:00
					)

				[5] => Array
					(
						[day_of_week] => 5
						[start] => 20:00:00
						[end] => 23:00:00
					)
			)
	)

```

## With specific hours:

![image](https://storage.gra.cloud.ovh.net/v1/AUTH_9c30d35f284f44b2bda08609e7c19f33/cyrille_public/20241006151424.png)

```

= App\Models\Pbx3cxHostCalendar {#6135
    id: 903,
    pbx3cx_host_code: "df7jol",
    idcalendar: 5817,
    dummy: 1,
    fkdirulehours: 5,
    pv_ignore_holidays: "0",
    created_at: "2024-10-06 14:35:42",
    updated_at: "2024-10-06 14:35:42",
  }


```

=>  idcalendar = 5817

=> fkdirulehours =>5
### API response:

```
[0184799461] => Array
	(
		[rule_name] => 7. regle de reference
		[dst_dn] => 007
		[out_of_office_iddn] => 3110
		[out_of_office_destination_type] => extension
		[out_of_office_destination] => 104
		[rules] => Array
			(
				[0] => Array
					(
						[day_of_week] => 1
						[start] => 05:00:00
						[end] => 23:00:00
					)
				[1] => Array
					(
						[day_of_week] => 2
						[start] => 06:00:00
						[end] => 22:00:00
					)
			)
	)

```


------
## More

### Test 1

![image](https://storage.gra.cloud.ovh.net/v1/AUTH_9c30d35f284f44b2bda08609e7c19f33/cyrille_public/20241006151445.png)


```
= App\Models\Pbx3cxHostCalendar {#6135
    id: 7525,
    pbx3cx_host_code: "df7jol",
    idcalendar: 5817,
    dummy: 1,
    fkdirulehours: 2,
    pv_ignore_holidays: "0",
    created_at: "2024-10-07 04:47:49",
    updated_at: "2024-10-07 04:47:49",
  }

```

### Test 2

![image](https://storage.gra.cloud.ovh.net/v1/AUTH_9c30d35f284f44b2bda08609e7c19f33/cyrille_public/20241007054611.png)

```
= App\Models\Pbx3cxHostCalendar {#6135
    id: 7826,
    pbx3cx_host_code: "df7jol",
    idcalendar: 5817,
    dummy: 1,
    fkdirulehours: 2,
    pv_ignore_holidays: "0",
    created_at: "2024-10-07 04:50:23",
    updated_at: "2024-10-07 04:50:23",
  }

```

### Test 3

![Image](https://storage.gra.cloud.ovh.net/v1/AUTH_9c30d35f284f44b2bda08609e7c19f33/cyrille_public/20241007055157.png)

```
= App\Models\Pbx3cxHostCalendar {#6135
    id: 8428,
    pbx3cx_host_code: "df7jol",
    idcalendar: 5817,
    dummy: 1,
    fkdirulehours: 4,
    pv_ignore_holidays: "0",
    created_at: "2024-10-07 04:52:43",
    updated_at: "2024-10-07 04:52:43",
  }

```

### Test 4


![Image](https://storage.gra.cloud.ovh.net/v1/AUTH_9c30d35f284f44b2bda08609e7c19f33/cyrille_public/20241007055843.png)

```
= App\Models\Pbx3cxHostCalendar {#6135
    id: 9030,
    pbx3cx_host_code: "df7jol",
    idcalendar: 5817,
    dummy: 1,
    fkdirulehours: 2,
    pv_ignore_holidays: "0",
    created_at: "2024-10-07 05:29:04",
    updated_at: "2024-10-07 05:29:04",
  }

```

