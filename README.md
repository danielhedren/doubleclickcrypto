# DoubleClickCrypto
 Python module for decrypting doubleclick price confirmations.
 
 See https://developers.google.com/authorized-buyers/rtb/response-guide/decrypt-price.

## Installation
```
pip install doubleclickcrypto
```

## Features
The module handles decryption of price confirmations with signature checking and stale response handling.

## Example usage
Look at the test cases in the source for more examples.

### Simple decryption
 ```python
from doubleclickcrypto import DoubleClickCrypto

e_key = "skU7Ax_NL5pPAFyKdkfZjZz2-VhIN8bjj1rVFOaJ_5o="
i_key = "arO23ykdNqUQ5LEoQ0FVmPkBd7xB5CO89PDZlSjpFxo="
enc = "YWJjMTIzZGVmNDU2Z2hpN7fhCuPemCce_6msaw"

DoubleClickCrypto.decrypt(enc, e_key, i_key)
#  -> 100
 ```
### Check for stale response
```python
DoubleClickCrypto.decrypt(enc, e_key, i_key, max_timedelta_seconds=0)
#  -> throws StaleResponseException
```
