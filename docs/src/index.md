# BIMABD Clients API V1 for OMC (Overseas medical Certificate)


Sandbox URL: [https://sandbox.bimabd.com](https://sandbox.bimabd.com)

Test Credentials: Will be shared to you in personal email


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


