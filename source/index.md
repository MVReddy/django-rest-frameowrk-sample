---
title: CLIPS API Reference

includes:
  - errors

search: true
---

# Introduction

Welcome to the CLIPS API! You can use our API to access CLIPS API endpoints, which can get information on various actual and projected cashflow data in our database.

Feel free to edit it and use it as a base for editing or updating API's documentation.

# CLIPS API Documentation

## Get Actual cash flow data

```bash
curl "http://127.0.0.1:8000/clips/clips_api/actual_cash_liquidity/?value_type=cashflow&format=api&fund_name=SSALT%20FUND%20LIMITED&value_date_from=2016-05-20&value_date_to=2016-05-31&label_key=inv_subs&publish_date=2016-05-12"
  -H "Authorization: <user_name>"
```

> The above command returns JSON structured like this:

```json
{
    "Venkat": [
        "2016-05-31T00:00:00",
        "2016-05-31T00:00:00"
    ],
    "FORECAST_DATE": [
        "2016-05-12T00:00:00",
        "2016-05-12T00:00:00"
    ],
    "LABEL_KEY": [
        "inv_subs",
        "inv_subs"
    ],
    "FUND_NAME": [
        "SSALT FUND LIMITED",
        "SSALT FUND LIMITED"
    ],
    "LABEL_VALUE": [
        "Investor subscription",
        "Investor subscription"
    ],
    "CF_AMOUNT": [
        2184167.0,
        2184167.0
    ],
    "TYPE": [
        "cashflow",
        "cashflow"
    ]
}
```

This endpoint retrieves the actual cashflow for a given time period amd a given value type.


### HTTP Request

GET http://127.0.0.1:8000/clips/clips_api/projected_cash_liquidity/

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
value_type | cashflow | If set to cashflow, the result will also include cashflow data.
format | json | If set to csv, the result will be downloaded as csv file.
fund_name | SSALT FUND LIMITED | You can pass any fund name.
value_date_from | 2016-05-20 | You can pass any start date.
value_date_to | 2016-05-20 | You can pass any end date.

<aside class="success">
Remember — a happy clips is an authenticated clips!
</aside>

## Get Projected cash flow data

```bash
curl "http://127.0.0.1:8000/clips/clips_api/projected_cash_liquidity/?value_type=cashflow&format=api&fund_name=SSALT%20FUND%20LIMITED&value_date_from=2016-05-20&value_date_to=2016-05-31&label_key=inv_subs&publish_date=2016-05-12"
  -H "Authorization: meowmeowmeow"
```

> The above command returns JSON structured like this:

```json
{
    "VALUE_DATE": [
        "2016-05-31T00:00:00",
        "2016-05-31T00:00:00"
    ],
    "FORECAST_DATE": [
        "2016-05-12T00:00:00",
        "2016-05-12T00:00:00"
    ],
    "LABEL_KEY": [
        "inv_subs",
        "inv_subs"
    ],
    "FUND_NAME": [
        "SSALT FUND LIMITED",
        "SSALT FUND LIMITED"
    ],
    "LABEL_VALUE": [
        "Investor subscription",
        "Investor subscription"
    ],
    "CF_AMOUNT": [
        2184167.0,
        2184167.0
    ],
    "TYPE": [
        "cashflow",
        "cashflow"
    ]
}
```

This endpoint retrieves the projected cashflow for a given time period amd a given value type.

<aside class="warning">If you're not using an administrator API key, note that some clipss will return 403 Forbidden if they are hidden for admins only.</aside>

### HTTP Request

`GET http://127.0.0.1:8000/clips/clips/clips_api/projected_cash_liquidity/?value_type=cashflow&format=api&fund_name=SSALT%20FUND%20LIMITED&value_date_from=2016-05-20&value_date_to=2016-05-31&label_key=inv_subs&publish_date=2016-05-12`

### URL Parameters

Parameter | Description
--------- | -----------
value_type | cashflow | If set to cashflow, the result will also include cashflow data.
format | json | If set to csv, the result will be downloaded as csv file.
fund_name | SSALT FUND LIMITED | You can pass any fund name.
value_date_from | 2016-05-20 | You can pass any start date.
value_date_to | 2016-05-20 | You can pass any end date.
publish_date_to | 2016-05-12 | You can pass any end date.
label_key | SSALT inv_subs | You can pass any fund name.

<aside class="success">
Remember — a happy clips is an authenticated clips!
</aside>
