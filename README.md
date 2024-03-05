# Cryptography---19CS412-classical-techqniques


# Caeser Cipher
Caeser Cipher using with different key values

# AIM:

To develop a simple C program to implement Caeser Cipher.

## DESIGN STEPS:

### Step 1:

Design of Caeser Cipher algorithnm 

### Step 2:

Implementation using C or pyhton code

### Step 3:

Testing algorithm with different key values. 

## PROGRAM:
## Encryption:

def caesar_cipher(text, shift):
    encrypted_text = ""
    for char in text:
        if char.isalpha():  # Check if the character is alphabet
            shifted = ord(char) + shift
            if char.islower():
                if shifted > ord('z'):
                    shifted -= 26
                elif shifted < ord('a'):
                    shifted += 26
            elif char.isupper():
                if shifted > ord('Z'):
                    shifted -= 26
                elif shifted < ord('A'):
                    shifted += 26
            encrypted_text += chr(shifted)
        else:
            encrypted_text += char
    return encrypted_text
text = "kaushik"
shift = 3


encrypted_text = caesar_cipher(text, shift)
print("Original Text:", text)
print("Encrypted Text:", encrypted_text)

## Decryption:

def caesar_decrypt(encrypted_text, shift):
    decrypted_text = ""
    for char in encrypted_text:
        if char.isalpha():  # Check if the character is alphabet
            shifted = ord(char) - shift
            if char.islower():
                if shifted > ord('z'):
                    shifted -= 26
                elif shifted < ord('a'):
                    shifted += 26
            elif char.isupper():
                if shifted > ord('Z'):
                    shifted -= 26
                elif shifted < ord('A'):
                    shifted += 26
            decrypted_text += chr(shifted)
        else:
            decrypted_text += char
    return decrypted_text


text = "kaushik"
shift = 3

decrypted_text = caesar_decrypt(encrypted_text, shift)
print("Decrypted Text:", decrypted_text)
## OUTPUT:
![Screenshot 2024-03-05 132930](https://github.com/kaushik2022/Cryptography---19CS412-classical-techqniques/assets/129837020/abd0b2ff-127e-449d-bc39-3b64bf56645c)

## RESULT:
The program is executed successfully

---------------------------------

# PlayFair Cipher
Playfair Cipher using with different key values

# AIM:

To develop a simple C program to implement PlayFair Cipher.

## DESIGN STEPS:

### Step 1:

Design of PlayFair Cipher algorithnm 

### Step 2:

Implementation using C or pyhton code

### Step 3:

Testing algorithm with different key values. 

## PROGRAM:
def generate_key_square(key):
    key = key.upper().replace(" ", "")
    key_square = ""
    for char in key:
        if char not in key_square:
            key_square += char
    alphabet = "ABCDEFGHIKLMNOPQRSTUVWXYZ"
    for char in alphabet:
        if char not in key_square:
            key_square += char
    return key_square

def prepare_text(text):
    text = text.upper().replace(" ", "")
    text = "".join(char for char in text if char.isalpha())
    if len(text) % 2 != 0:
        text += 'X'
    return text

def encrypt_pair(pair, key_square):
    row1, col1 = divmod(key_square.index(pair[0]), 5)
    row2, col2 = divmod(key_square.index(pair[1]), 5)
    if row1 == row2:
        return key_square[row1 * 5 + (col1 + 1) % 5] + key_square[row2 * 5 + (col2 + 1) % 5]
    elif col1 == col2:
        return key_square[((row1 + 1) % 5) * 5 + col1] + key_square[((row2 + 1) % 5) * 5 + col2]
    else:
        return key_square[row1 * 5 + col2] + key_square[row2 * 5 + col1]

def decrypt_pair(pair, key_square):
    row1, col1 = divmod(key_square.index(pair[0]), 5)
    row2, col2 = divmod(key_square.index(pair[1]), 5)
    if row1 == row2:
        return key_square[row1 * 5 + (col1 - 1) % 5] + key_square[row2 * 5 + (col2 - 1) % 5]
    elif col1 == col2:
        return key_square[((row1 - 1) % 5) * 5 + col1] + key_square[((row2 - 1) % 5) * 5 + col2]
    else:
        return key_square[row1 * 5 + col2] + key_square[row2 * 5 + col1]

def playfair_encrypt(plain_text, key):
    key_square = generate_key_square(key)
    plain_text = prepare_text(plain_text)
    encrypted_text = ""
    for i in range(0, len(plain_text), 2):
        encrypted_text += encrypt_pair(plain_text[i:i+2], key_square)
    return encrypted_text

def playfair_decrypt(encrypted_text, key):
    key_square = generate_key_square(key)
    decrypted_text = ""
    for i in range(0, len(encrypted_text), 2):
        decrypted_text += decrypt_pair(encrypted_text[i:i+2], key_square)
    return decrypted_text

# Example usage:
plain_text = "kaushik"
key = "PLAYFAIR EXAMPLE"

encrypted_text = playfair_encrypt(plain_text, key)
print("Encrypted Text:", encrypted_text)

decrypted_text = playfair_decrypt(encrypted_text, key)
print("Decrypted Text:", decrypted_text)


## OUTPUT:
![Screenshot 2024-03-05 134556](https://github.com/kaushik2022/Cryptography---19CS412-classical-techqniques/assets/129837020/6c6808b4-e9d3-4e9c-b695-ef6abd373ffd)

## RESULT:
The program is executed successfully


---------------------------

# Hill Cipher
Hill Cipher using with different key values

# AIM:

To develop a simple C program to implement Hill Cipher.

## DESIGN STEPS:

### Step 1:

Design of Hill Cipher algorithnm 

### Step 2:

Implementation using C or pyhton code

### Step 3:

Testing algorithm with different key values. 

## PROGRAM:

## OUTPUT:

## RESULT:
The program is executed successfully

-------------------------------------------------

# Vigenere Cipher
Vigenere Cipher using with different key values

# AIM:

To develop a simple C program to implement Vigenere Cipher.

## DESIGN STEPS:

### Step 1:

Design of Vigenere Cipher algorithnm 

### Step 2:

Implementation using C or pyhton code

### Step 3:

Testing algorithm with different key values. 

## PROGRAM:

## OUTPUT:

## RESULT:
The program is executed successfully

-----------------------------------------------------------------------

# Rail Fence Cipher
Rail Fence Cipher using with different key values

# AIM:

To develop a simple C program to implement Rail Fence Cipher.

## DESIGN STEPS:

### Step 1:

Design of Rail Fence Cipher algorithnm 

### Step 2:

Implementation using C or pyhton code

### Step 3:

Testing algorithm with different key values. 

## PROGRAM:

## OUTPUT:

## RESULT:
The program is executed successfully
