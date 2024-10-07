# Inbound rules

## Without specific hours:

![[Pasted image 20241006151454.png]]


=> idcalendar = 5817


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

=> fkdirulehours : 2


## With specific hours:



![[Pasted image 20241006151427.png]]

=>  fkidcalendar = 5817

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



##  Test

![[Pasted image 20241007054613.png]]


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


## Test 2
![[Pasted image 20241007055000.png]]

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




## Test 3

![[Pasted image 20241007055213.png]]


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



## Test

![[Pasted image 20241007055900.png]]
















