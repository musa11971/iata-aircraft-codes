# iata-aircraft-codes
[IATA aircraft codes](https://en.wikipedia.org/wiki/International_Air_Transport_Association_airport_code) in XML format. You can use this XML file containing all IATA aircraft codes. This can be useful when you want to resolve an IATA aircraft code to the aircraft's name without using an API. 
  
Last update: January 3rd 2018

# PHP example

```php
// Function to get the aircraft name from IATA aircraft code
function IATAToAircraft($IATA) {
  $IATAData = simplexml_load_string(file_get_contents('IATA_AIRCRAFTS.xml'));

  foreach($IATAData->iata_aircraft as $code) {
    if($code->code == $IATA) return $code->aircraft;
  }
}
```
