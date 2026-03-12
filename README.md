# EX-8-ADVANCED-ENCRYPTION-STANDARD ALGORITHM
# Aim:
To use Advanced Encryption Standard (AES) Algorithm for a practical application like URL Encryption.

# ALGORITHM:
AES is based on a design principle known as a substitution–permutation.
AES does not use a Feistel network like DES, it uses variant of Rijndael.
It has a fixed block size of 128 bits, and a key size of 128, 192, or 256 bits.
AES operates on a 4 × 4 column-major order array of bytes, termed the state
# PROGRAM:
```
from Crypto.Cipher import AES
from Crypto.Random import get_random_bytes
import base64

# Function to pad text
def pad(text):
    while len(text) % 16 != 0:
        text += ' '
    return text

# Encryption
def encrypt(message, key):
    cipher = AES.new(key, AES.MODE_ECB)
    message = pad(message)
    encrypted = cipher.encrypt(message.encode())
    return base64.b64encode(encrypted).decode()

# Decryption
def decrypt(ciphertext, key):
    cipher = AES.new(key, AES.MODE_ECB)
    decoded = base64.b64decode(ciphertext)
    decrypted = cipher.decrypt(decoded).decode()
    return decrypted.strip()

# Main program
key = get_random_bytes(16)

message = input("Enter message: ")

encrypted_text = encrypt(message, key)
print("Encrypted:", encrypted_text)

decrypted_text = decrypt(encrypted_text, key)
print("Decrypted:", decrypted_text)
```
# OUTPUT:
<img width="1906" height="1104" alt="image" src="https://github.com/user-attachments/assets/2a4332ea-77a7-44f5-a018-ecc59f1d7bab" />


# RESULT:
Thus the program to implement AES encryption and decryption is done successfully



