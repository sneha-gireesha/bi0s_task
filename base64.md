 # BASE64

* Base64 is an encoding scheme that converts binary data (like images, files, or even text) into a text-based representation using a set of  64 printable ASCII characters.
  
*operation of converting data into ascii text format 
  

### Base64 Encoding:

base64 is the operation of  converting  data into ascii text format so that it can be transported 

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

* process: converting each character to its ASCII value, then grouping the bits into 6-bit chunks, looking up the corresponding Base64 character for each chunk, and finally concatenating the results with padding if necessary

```python
def string_to_base64(input_string):
    # Base64 Alphabet
    base64_chars = "ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz0123456789+/"
    
    # Step 1: Convert string to binary
    binary_str = ''.join(format(ord(c), '08b') for c in input_string)
    
    # Step 2: Pad the binary string to be divisible by 6
    padding = len(binary_str) % 6
    if padding != 0:
        binary_str += '0' * (6 - padding)
    
    # Step 3: Break the binary string into 6-bit chunks
    chunks = [binary_str[i:i+6] for i in range(0, len(binary_str), 6)]
    
    # Step 4: Map each 6-bit chunk to a Base64 character
    base64_string = ''.join(base64_chars[int(chunk, 2)] for chunk in chunks)
    
    # Step 5: Add padding (=) to the end if needed
    padding_count = (4 - len(base64_string) % 4) % 4
    base64_string += '=' * padding_count
    
    return base64_string

# Example usage
input_string = "hello"
encoded_string = string_to_base64(input_string)
print(encoded_string)
```

string --->binary--->base64

