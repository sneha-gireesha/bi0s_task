### Task2

# CRYPTOHACK

### ENCODING 
## ASCII
* American Standard code for Information Interchange
* ascii is a character encoding system
* ```ord()``` function works to obtainthe ASCII value of a character

```python
character =("enter the character")
print("ASCII value =", ord(character))
```
to convert ASCII  back to character  we use the function ```chr() ```
```python
num=int(input("enter the number"))
print("ASCII value ="chr(num))
```
* i converted each number one-by-one to get the flag
![ascii](<cryptohack encode ASCII.png>)


## Hex 
* ```bytes.fromhex()``` is used for directly converting hex string to bytes
* hexadecimal is a number system  used to represent bytes.
* bytes are units of data
![hex](<cryptohack encoding hex.png>)

## Base 64
* the base64 library is functions for encoding and decoding    binary data 

* use ```bytes.fromhex``` to convert hex string to bytes string
* ```base64.b64encode ``` is used to encode bytes object into a base-64 
* base-64 represent binary data as ASCII string using 64 characters

![base64](<cryptohack encode base64.png>)

## Bytes and Big integers
* PyCryptodome is a library for Python that helps you protect data by using cryptography—which is basically turning your information into a secret code so that only authorized people or systems can read it.

* ```long_to_bytes``` convert integer into bytes
* ```bytes_to_long ```convert bytes into integer

![bytes and big integer](<cryptohack encode bytes and big integer.png>)

## Encoding challenges
* pass all the 100 level ``` for i in range (100)```
* each level has string encoded in several format like base64 , rot13 , hex , bignit , uft-8 
* have to decode each of it 

```python 
def decode(encoded_string , encoded_type):
 
    if encoded_type == "base64":
        return  base64.b64decode(encoded_string).decode("utf-8")
    elif encoded_type == "hex":
        return bytes.fromhex(encoded_string).decode("utf-8") 
    elif encoded_type == "rot13":
        return codecs.decode(encoded_string , "rot13")
    elif encoded_type == "utf-8":
        return ''.join(chr(i) for i in encoded_string)  
    else:
        return bytes(long_to_bytes(int(encoded_string,16))).decode("utf-8") 
 
```

* Connect at socket.cryptohack.org 13377  ```r = remote('socket.cryptohack.org', 13377, level = 'debug')```


* resources used: [pwntools](https://docs.pwntools.com/en/stable/)


### XOR
## XOR starter

resoruce used :

[xor](https://www.geeksforgeeks.org/bitwise-xor-operator-in-programming/)

![xor](<xor .png>)

XOR a string:
* convert each character(of that string) to integer representing unicode character ``` ord(characters)```
* XOR each character with integer 13 ``` ord(char)^13```
* convert these integer back to string ``` chr (ord(charac)^13)```

## XOR properties
* got to know about some properties of XOR operator
* here the hex is decoded into bytes ,which is then XOR into flag

![xor properties](<xor properties.png>)
* to undo Xor encryption we can reapply the XOR function with same key that was used to encrypt data

resources used : 

[pwntools xor](https://docs.pwntools.com/en/stable/util/fiddling.html#pwnlib.util.fiddling.xor)

## Favourite bytes

* after decoding the data from hex to bytes it is xor with numbers from 0 to 100

![xor favourite](<xor favourite .png>)

## You either know ,XOR you dont
* decoded to bytes from hex
* flag format ```crypto{}```
* xor and encoded with ```crypto{```
* again xor and encoded with ```myXORkey```

![fav xor](<xor if you know xor you know.png>)

## Lemur XOR

* "stego" image (the image containing the hidden data)

resources used :

 [stackovertheflow](https://stackoverflow.com/questions/8504882/searching-for-a-way-to-do-bitwise-xor-on-images)

 [binascii](https://docs.python.org/es/3.6/library/binascii.html)

 website used to correct errors:

 [stackovertheflow](https://stackoverflow.com/questions/37261495/fp-builtins-openfilename-rb-error)

 [stackovertheflow](https://stackoverflow.com/questions/63607971/django-tuple-object-has-no-attribute-save)


* convert both the host image and hidden image to binary data
* perform bitwise operation b/w corresponding bits of the host image and hidden data with the ```secret key```
* if you XOR 2 encrypted images together the key will cancel out ,becasue (X^X=0)and you'll be left with the XOR of the original image 

![lemur is cute ](<xor lemur  hahahah i completed it .png>)
* have to install PLI (python image library) used the commad ```pip install pillow```
* ```ImageChops``` for comparing 2 images and find their difference 

### Mathematics

## Greatest Common Divisor
* it is to find the largest number which divide two positiv integers(a,b)

![gcd](<mathematics modular arithmetic 1-1.png>)

```python 
if a>b : 
    a//b=c
    a%b=d
elif b>a:
    b//a=c
    b%a=d

a=b(c)+d
a=b
b=d

```



## EXtended GCD
resource used : 
[extended gcd ](https://www.youtube.com/watch?v=hB34-GSDT3k)

![extended](<mathematics extended gcd .png>)

```pythos
888=54(16)+24
54=24(2)+6
24=6(4)+0
**6**
gcd(888,54)=6

6=54-24(2)
6=54+24(-2)
 =54+(-2)(888-54(16))
6=54+(-2)(888)-(54(16)(-2))
6=54+(-2)(888)+(54)(32)
6=54(33)-888(-2)

x=33
y=-2
linear combination of 888 and 54
gcd(888,54)=888(x)+54(y)
gcd(a,b)=a(x)+b(y)
```

resource used : [Extended Euclidean Algorithm](https://www.youtube.com/watch?v=YZfPcvbwwvI&t=4s)

## Modular Arithmetic 1
![modular](<mathematics modular arithmetic 1.png>)
* a ≡ b mod m

    here b is the remainder of a /m      
      ``` a % m = b ``` 

## Modular Arithmetic 2
 ![modular 2](<mathematics modular arithmatics 2.png>)
  
  resources used :

   [GeeksofGeeks](https://www.geeksforgeeks.org/fermats-little-theorem/)

   [Fermats little theorem](https://www.youtube.com/watch?v=pl0eOHWU3Gg)



* if 
  p is a prime number 
  
  a is a integer 

  ```V=a^p-p```

 if a = interger 
 
  p = prime 

  ```a^(p-1) = 1(mod p)```

 if  a - integer co-prime to p 
 
 p - prime

   ```a^p ≡ a(mod p )```





## Modular Inverting 
![modular inverting](<mathematics modular inverting .png>)

modular multilicative inverse of an integer a is an integer x 
such that  ```a.x ≡ 1 mod m 

modular inverse exist  
            if and only if a and m are relatively prime 
            ie , gcd((a,m)=1)


            g.d = 1 mod p
            gcd( g ,p ) = 1


            if gcd not equal to 1 
            then no inverse


resources used : 

[cp algorithm](https://cp-algorithms.com/algebra/module-inverse.html)
[stackovertheflow](https://stackoverflow.com/questions/4798654/modular-multiplicative-inverse-function-in-python)



