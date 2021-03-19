# PDP Parser

Developed by Mrbeastmode of BlazeAIO

## Why?
Well, most PDP parsing functions take about 50-100 lines of chunky, gross code.
Why bother looking through terrible naming conventions, stressing over properly parsing,
insuring that you found the right sizes, when you could leave that to me to solve? : D

In any case, enjoy!

## How to use
First install PDPParser using
```
pip install PDPParser
````

Then, import in PDPParser using
```
from PDPParser import Parse
```
To use the package,
PASS IN YOUR TEXT TO EITHER OF THESE 3 METHODS:

  1. Sizes: Use this to return a list/array of product sizes and pids

  2. Info: Use this to return a list/array of product info
    This will return:
        - Title
        - Image
        - Price

  3. Launch: Check if the product has launched, or is yet to launch
        - If this returns 0, the product has been launched
        - Otherwise, it is the time left to launch in seconds

  4. Random_Size: Will return a random size and pid, great for quick atc


  5. Specific_size: When you pass in a list/array of user inputed sizes, it will match them with the available sizes, and return matching PIDS
 

AT ANY POINT, IF IT RETURNS ERROR, CHECK YOUR INPUTS!


EX:
```python
import requests
from PDPParser import Parse

r = requests.get(f'https://footlocker.com/api/pdp/products/{sku}')

sizes = Parse.sizes(r.text,sku)

info = Parse.info(r.text,sku)

random_size = Parse.random_size(r.text, sku)

launch_time = Parse.launch(r.text)

user_entries = ["10","10.5","11"]
specific_sizes = Parse.specific_size(r.text,sku,user_entries)
```



## TODO: Add more functions
