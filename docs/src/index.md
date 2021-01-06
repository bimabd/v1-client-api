# BIMABD Clients API V1 for OMC (Overseas medical Certificate)


Sandbox URL: [https://sandbox.bimabd.com](https://sandbox.bimabd.com)

Test Credentials / Secret Key: Will be shared to you in personal email


## Countries       

Getting list of countries with country code before making quotation 

~~~
https://sandbox.bimabd.com/api/client/v1/omc/countries
~~~

#### REQUEST       

URL : `api/client/v1/omc/countries`               
Method: `GET`             
Secret Key: `Not Required`                   

#### RESPONSE

~~~
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
Secret Key: `Not Required`                   

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

~~~
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

