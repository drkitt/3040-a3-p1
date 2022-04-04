### ***API description***

ManitobaFloods.org is a simple API that provides users with flood data and statistics from their area. Providing a Manitoban flood region and year range will return you data regarding; previous floods, rainfall and snowmelt. 

### *List of endpoints with parameters* 

https://api.ManitobaFloods/json?MBfr&StartYear&EndYear
* MBfr(String): The Manitoba flood region information is wanted for. Required.
* StartYear(int): The start year for the range of years flood information is requested for. Required.
* EndYear(int): The end year for the range of years flood information is requested for. Required.

### **Description of resources - formatted as JSON**

* **Floods:** An array of floods from start year to end year. Each flood has the following properties:
  * **PropertyDamage**: The total Dollar amount of property damage. 
  * “PropertyDmg”: 364000
  * **Deaths** : the total number of deaths.
  * “Deaths”: 12
  * **StartDate**: the starting date of floods
  * “StartDate”: 04-15-1950
  * **EndDate**: the last date of flood
  * "EndDate": 06-12-1950
  
 * **Status:** Contains “OK” if the request succeeded, or one of the following error codes if it failed:
   * **INVALID_REGION**: The MBfr string is not the name of a valid region.
   * **INVALID_START**: StartYear is less than 1870, greater than 2022, greater than EndYear, or not a number.
   * **INVALID_END**: EndYear is less than 1870, greater than 2022, less than StartYear, or not a number.
   * **UNKNOWN_ERROR**: An unexpected server error occurred. Making the request again may solve the problem.

### *Sample request with sample response*

`https://api.ManitobaFloods.org/json?MBfr=red_river&startyear=1950&endyear=1997`

```
{
  “results”: {
    “Floods”: [
    {
      “PropertyDamage”: 950000000,
      “Deaths”: 8,
      “StartDate”: “04-15-1950”,
      “EndDate”: “06-12-1950”
    },
    {
      “PropertyDamage”: 3500000000,
      “Deaths”: 0,
      “StartDate”: “04-10-1997”,
      “EndDate”: “05-13-1997”
    },
    ],
  },
  “Status”: “OK”
}
```
