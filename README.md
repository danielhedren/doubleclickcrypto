# DoubleClickCrypto
 Python module for decrypting doubleclick price confirmations.

## Installation
```
pip install doubleclickcrypto
```

## Features
The module handles decryption of price confirmations and advertising identifiers with signature checking and, for price confirmations, stale response handling.

## Example usage
Look at the test cases in the source for more examples.

### Price decryption
 ```python
from doubleclickcrypto import DoubleClickCrypto

e_key = "skU7Ax_NL5pPAFyKdkfZjZz2-VhIN8bjj1rVFOaJ_5o="
i_key = "arO23ykdNqUQ5LEoQ0FVmPkBd7xB5CO89PDZlSjpFxo="
cipher = "YWJjMTIzZGVmNDU2Z2hpN7fhCuPemCce_6msaw"

DoubleClickCrypto.decrypt_price(cipher, e_key, i_key)
#  -> 100

# Check for stale responses
DoubleClickCrypto.decrypt_price(cipher, e_key, i_key, max_timedelta_seconds=0)
#  -> throws StaleResponseException
 ```
### Advertising id decryption
```python
from doubleclickcrypto import DoubleClickCrypto

e_key = "sIxwz7yw62yrfoLGt12lIHKuYrK_S5kLuApI2BQe7Ac="
i_key = "v3fsVcMBMMHYzRhi7SpM0sdqwzvAxM6KPTu9OtVod5I="
cipher = "5nmwvgAM0UABI0VniavN72_tyXf-QJOmQdL0tmh_fduB2go_"

DoubleClickCrypto.decrypt_ad_id(cipher, e_key, i_key)
# -> bytes([0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15])
```

## Repository

https://github.com/danielhedren/doubleclickcrypto
