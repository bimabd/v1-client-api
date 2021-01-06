# BIMABD Clients API V1 for OMC (Overseas medical Certificate)


Sandbox URL: [https://sandbox.bimabd.com](https://sandbox.bimabd.com)

Test Credentials / Client Key: Will be shared to you in personal email


## Countries       

Getting list of countries with country code before making quotation 

~~~
https://sandbox.bimabd.com/api/client/v1/omc/countries
~~~

#### REQUEST       

URL : `api/client/v1/omc/countries`               
Method: `GET`             
Client Key: `Not Required`                   

#### RESPONSE

~~~js
{
    "success": true,
    "data": [
        {
            "country_name": "Afghanistan",
            "country_code": "AFG"
        },
        {
            "country_name": "Åland Islands",
            "country_code": "ALA"
        },
        {
            "country_name": "Albania",
            "country_code": "ALB"
        },
        {
            "country_name": "Algeria",
            "country_code": "DZA"
        },
    ]
}
~~~


## OMC price quotation

Fetching OMC price 

~~~
https://sandbox.bimabd.com/api/client/v1/omc/quote
~~~

#### REQUEST       

URL : `api/client/v1/omc/quote`               
Method: `POST`             
Client Key: `Not Required`                   

Form Data     
~~~js
{
  'countries'    : ["USA"],
  'date_of_birth' : '01/01/1999',
  'date_of_travel' : '01/01/2021',
  'days'      : 30,
}
~~~


#### RESPONSE

~~~js
{
    "success": true,
    "data": {
        "countries": [
            "USA"
        ],
        "days": "30",
        "date_of_birth": "01/01/1999",
        "date_of_travel": "01/01/2021",
        "result": {
            "age": 23,
            "country_type": "schengen_us_canada_worldwide",
            "countries": [
                "United States"
            ],
            "net_premium": 3681,
            "vat": 552,
            "total_premium": 4283,
            "delivery_cost": 40,
            "grand_total": 4283,
        }
    },
    "message": ""
}
~~~


## OMC Order Create

Create a OMC order

~~~
https://sandbox.bimabd.com/api/client/v1/omc/order-create
~~~

#### REQUEST       

URL : `api/client/v1/omc/order-create`               
Method: `POST`             
Client Key: `Required`                   

Form Data     
~~~js
{
  'countries'    : ["USA"],
  'date_of_birth' : '01/01/1999',
  'date_of_travel' : '01/01/2021',
  'days'      : 30,

  "name_in_passport" : 'Jon Doe',
  "passport_no" : 'BF3500',
  "permanent_address_in_passport" : 'Vi: Fatepur, Po: Tulpai, Ps: Kachua, Dis: Chandpur',

  "delivery_name" : 'Nizam Alvi',
  "delivery_address" : 'House 15, Road 11, Gudaraghat Badda, Dhaka',
  "contact_number" : '01670978989',
  "client_key" : 'c0f51405c5767e80c579b8f7699e6ac82ca6680420e02191e562ec9c9e0308b1221865655958f435d7f8a6b863844d953fd42cd262839f3d24176525628caa2e'
}
~~~


#### RESPONSE

~~~js
{
  "success": true,
  "data": {
      "order_id": 100783,
      "delivery_name": "Nizam Alvi",
      "delivery_address": "House 15, Road 11, Gudaraghat Badda Dhaka",
      "contact_number": "01670978989",
      "name_in_passport": "Jon Doe",
      "passport_no": "BF3500",
      "permanent_address_in_passport": "Vi: Fatepur, Po: Tulpai, Ps: Kachua, Dis: Chandpur"
  },
  "message": "Your Order has been placed"
}
~~~

## Order Details 

Order Details view

~~~
https://sandbox.bimabd.com/api/client/v1/omc/order-details
~~~

#### REQUEST       

URL : `api/client/v1/omc/order-details`               
Method: `POST`             
Client Key: `Required`                   

Form Data     
~~~js
{
  "client_key" : 'c0f51405c5767e80c579b8f7699e6ac82ca6680420e02191e562ec9c9e0308b1221865655958f435d7f8a6b863844d953fd42cd262839f3d24176525628caa2e',
  "order_id" : '100783'
}
~~~


#### RESPONSE

~~~js
{
    "id": 100783,
    "delivery_name": "Nizam Alvi",
    "delivery_address": "House 15, Road 11, Gudaraghat Badda Dhaka",
    "contact_number": "01670978989",
    "net_premium": "3681.00",
    "total_premium": "4283.00",
    "grand_total": "4283.00",
    "product_type": "omc",
    "status": "pending",
    "breakdown": [],
    "policy_start_date": "2021/01/01",
    "date_of_birth": "1999/01/01",
    "age": "23",
    "countries_code": [
        "USA"
    ],
    "countries": [
        "United States"
    ],
    "name_in_passport": "Jon Doe",
    "remarks": null,
    "permanent_address": "Vi: Fatepur, Po: Tulpai, Ps: Kachua, Dis: Chandpur",
    "passport_no": "BF3500"
}
~~~

