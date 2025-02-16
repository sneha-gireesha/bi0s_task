# BASE64

* Base64 is an encoding scheme that converts binary data (like images, files, or even text) into a text-based representation using a set of  64 printable ASCII characters.

* can be easily shared, especially in places like emails or URLs where binary data doesn’t work well.


### Base64 Encoding:

Base64 encoding takes a bunch of data ( string or file) and turns it into a text format, using  readable characters.

readable character :
* Letters (A-Z, a-z)
* Digits (0-9)
* Punctuation marks (e.g., ., ,, !, ?)


non readable character:
Whitespace characters like 
* space (' ')  
* tab (\t)
* newline (\n)

## Base64 encoding working :

### Input Data:
* The binary data (could be an image, file, etc.) is split  into groups of 3 bytes (each representing 8 bits)
(bit is the smallest unit of digital information )

* these 3-bytes (24 bits) is then split into 4 groups of 6  bits each.
This makes a total of 4 characters in the output for each 3 bytes of input.

* Each 6-bit block is mapped to a corresponding character from a Base64 alphabet (A-Z, a-z, 0-9, +, and /).

* If the number of input bytes isn’t a multiple of 3 bytyes ,we add = sign to the end of the output to make it a multiple of 4 characters. (padding)

This gives the resulting encoded string

#### Decoding is the reverse of encoding

#### To encode data into Base64:
eg: wap to encode a message to Base64 in Python
```python 
import base64

# Original string
original_string = "Hello, World!"

# Step 1: Convert the string to bytes
encoded_string = base64.b64encode(original_string.encode('utf-8'))

# Step 2: Convert the byte result  to string for easy viewing
encoded_string_str = encoded_string.decode('utf-8')

print(f"Encoded: {encoded_string_str}")

```
decoding :
```python
import base64

# Base64 encoded string
base64_string = "SGVsbG8gd29ybGQh" 

# Decode the Base64 string
decoded_bytes = base64.b64decode(base64_string)

# Convert the decoded bytes to a string
decoded_string = decoded_bytes.decode('utf-8')

print(decoded_string)
```
### UTF-8 
* Unicode Transformation Format - 8-bit

* UTF-8 is a way of converting text (such as characters, symbols, etc.) into binary data

* UTF-8 is a common way to turn text into binary, so if you want to Base64-encode text, it first needs to be turned into binary using UTF-8. This helps make sure that all characters (including special ones like emojis) are correctly converted.

string --->binary--->base64

