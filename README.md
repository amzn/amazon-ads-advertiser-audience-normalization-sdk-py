
## Address Hashing

Description:
This library can be used to prepare files for data upload with Amazon Marketing Cloud and Amazon DSP. Before files are uploaded to an AMC/Amazon DSP, certain columns must be normalized and hashed (SHA-256). This library performs the normalization and hashing process for the address field in the input file to ensure values confomr to Amazon's hashed address input format to generate high match rates.

### How to use the package:
1. The package has an AddressHash module which can be imported using the command > from AddressHashing import AddressHash
2. AddressHash module has an AddressNormalizer class 
3. An instance of AddressNormalizer should be created by passing the Country code. Following are the supported country codes 
   US,CA,UK,FR,DE,ES,IT,JP,IN
4. AddressNormalizer has the attrubutes normalizedAddress and sha256normalizedAddress which will be updated on calling the 
   .normalize method. 
5. If using this library for AMC/DSP data matching, the final address string that needs to be hashed should only include the street address and not the State Country and ZipCode

### Sample code useage:

from AddressHashing import AddressHash
import csv

address = '03646 Nicholas Stravenue Mooretown'
addressNormalizer = AddressHash.AddressNormalizer('US')
result = addressNormalizer.normalize(address)
print(result.normalizedAddress)
print(result.sha256normalizedAddress)

or

print(addressNormalizer.normalizedAddress)
print(addressNormalizer.sha256normalizedAddress)


