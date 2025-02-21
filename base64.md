
**Encoding is the process of converting data from one format to another for efficient storage, transmission, or processing.**  

In Base64 encoding, binary data is transformed into a text-friendly format using a specific character set.

**ASCII** is a system that gives numbers to characters so computers can understand text.

Computers don’t understand letters, so they store text as numbers (which are then converted into binary).

Base64 is a way to convert data into text using only letters, numbers, and a few symbols (+ and /).

**Why Use Base64?** <br>
Computers work with binary (0s and 1s), but humans prefer text. Some systems (like emails, URLs, and JSON) don’t allow raw binary data. Base64 encodes binary into a safe text format. <br>

Base64 Uses Only 64 Character<br>
A  6-bit number can represent 64 different values (from 0 to 63).<br>
These values map directly to the 64 Base64 characters (A-Z, a-z, 0-9, +, /)<br>
Base64 has 64 characters → Needs 6-bit encoding (since 2⁶ = 64).<br>
Splitting into 6-bit chunks makes conversion between text & Base64 seamless. <br>
3 bytes (24 bits) → 4 Base64 characters (4 × 6 = 24 bits), keeping everything aligned.<br>


**ENCODING**

Converting string into ASCII then to binary of 8 bits <br>
ord(i) converts each character i in the string s to its ASCII value <br>
format(..., '08b') converts the ASCII value to an 8-bit binary string <br>

In format(ord(char), '08b'), the 08b format specifier means:<br>

0 → Pads with leading zeros (if necessary).<br>
8 → Ensures the output is always 8 bits long.<br>
b → Converts the number to binary representation.<br>


then combine it together as a long string <br>
and then split it into 6 bits <br>
If the long string is not a multiple of 6 then add padding<br>

 base64_encoded = "" → Initializes an empty string to store the final Base64-encoded output.<br>  
 for i in range(0, len(binary_string), 6): → Loops through binary_string in steps of 6 bits at a time.<br>  
 chunk = binary_string [i:i+6] → Extracts a 6-bit segment from binary_string starting at index i. <br> 
 decimal_value = int(chunk, 2)→ Converts the 6-bit binary chunk into a decimal number (Base 10). <br>
 int(string, base) interprets the string in the given base (2 for binary, 16 for hex, etc.).<br>
base64_encoded += BASE64_CHARS[decimal_value] → Finds the corresponding Base64 character using decimal_value as an index in BASE64_CHARS and appends it to base64_encoded. <br>

Add padding if needed (Base64 output must be a multiple of 4 characters) "=" <br>


**DECODING** 

Remove padding 

**How to convert base64 characters into 6 bit binary**

Define the Base64 character set (it contains 64 characters).
 Find the index of each Base64 character in the set.
 Convert the index (decimal) to a 6-bit binary string.
 Join all binary values to get the final binary string

 ''. join(f' {BASE64_ALPHABET. index (c):06b}' for c in encoded_data)

 Join together all 6 bits and split it into 8 bits binary 
 
Then 8 bit binary into decimal

And then decimal to character (using char)





 
<img width="666" alt="Screenshot 2025-02-20 at 10 55 17 PM" src="https://github.com/user-attachments/assets/2670c03f-11b8-414a-bfdb-8b142df44971" />



 




