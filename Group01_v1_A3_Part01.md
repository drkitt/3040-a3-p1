### ***API description***

ManitobaFloods.org is a simple API that provides users with flood data and statistics from their area. Providing a Manitoban flood region and year range will return you data regarding; previous floods, rainfall and snowmelt. 

### *List of endpoints with parameters* 

https://api.ManitobaFloods/json?MBfr&StartYear&EndYear
* MBfr(String): The Manitoba flood region information is wanted for. Required.
* StartYear(int): The start year for the range of years flood information is requested for. Required.
* EndYear(int): The end year for the range of years flood information is requested for. Required.

### **Description of resources - formatted as JSON**

**Floods:** An array of floods from start year to end year. Each flood has the following properties:
**PropertyDamage**: The total Dollar amount of property damage. 
“PropertyDmg”: 364000
**Deaths** : the total number of deaths.
“Deaths”: 12
**StartDate**: the starting date of floods
“StartDate”: 04-15-1950

