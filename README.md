# KURL

is a curl wrapper to simplify some of the most common usage of curl for API requests


# Usage examples

> Example, whether it be good or bad, has a powerful influence. *George Washington*


## --data-json
```bash
kurl \
--include \
--headers "Accept: application/json" \
--headers "Content-Type: application/json" \
--request POST \
--data-json number1:123 \
--data-json "number2:123" \
--data-json "string1:'123'" \
--data-json string2:\"123\" \
--data-json "boolean1:true" \
--data-json string3:\"true\" \
--data-json "string4:qwe" \
--data-json string5:\"qwe\" \
--data-json "string6:'qwe'" \
--url https://com.com/test
```

is equivalent to

```apiary
POST https://com.com/test
> Accept: application/json
> Content-Type: application/json
{
  "number1": 123,
  "number2": 123,
  "string1": "123",
  "string2": "123",
  "boolean1": true,
  "string3": "true",
  "string4": "qwe",
  "string5": "qwe",
  "string6": "qwe"
}
```


## --query

```bash
kurl \
--include \
--headers "Accept: application/json" \
--request GET \
--query "name=Andrei" \
--query "likes=['apples', 'pie']" \
--url https://com.com/test
```

is equivalent to

```apiary
GET https://com.com/test?name=Andrei&likes=%5b'apples',%2520'pies'%5d
> Accept: application/json
```
