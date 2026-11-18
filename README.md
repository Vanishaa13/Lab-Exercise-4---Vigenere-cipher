# Lab-Exercise-4---Vigenere-cipher
# AIM

To develop a simple C program to implement Vigenere Cipher.

# ALGORITHM


1.Start the program.



2.Get the plaintext and keyword from the user.



3.Convert the plaintext and key into uppercase.



4.Repeat the keyword according to the length of the plaintext.



5.Convert each plaintext letter and key letter into numerical values.



6.Add the corresponding plaintext and key values.



7.Apply modulo 26 to get the encrypted value.



8.Convert the encrypted value into the corresponding alphabet.



9.For decryption, subtract the key value from the ciphertext value and apply modulo 26.



10.Display the encrypted and decrypted text.



11.Stop the program.

# PROGRAM
```

def vigenere_encrypt(plaintext, key):
    plaintext = plaintext.upper()
    key = key.upper()
    ciphertext = ""
    j = 0

    for char in plaintext:
        if char.isalpha():
            row = ord(key[j % len(key)]) - ord('A')
            col = ord(char) - ord('A')

            encrypted = chr((row + col) % 26 + ord('A'))
            ciphertext += encrypted
            j += 1
        else:
            ciphertext += char

    return ciphertext


def vigenere_decrypt(ciphertext, key):
    ciphertext = ciphertext.upper()
    key = key.upper()
    plaintext = ""
    j = 0

    for char in ciphertext:
        if char.isalpha():
            row = ord(key[j % len(key)]) - ord('A')
            col = ord(char) - ord('A')

            decrypted = chr((col - row) % 26 + ord('A'))
            plaintext += decrypted
            j += 1
        else:
            plaintext += char

    return plaintext


message = input("Enter plaintext: ")
key = input("Enter key: ")

if key.isalpha():
    encrypted = vigenere_encrypt(message, key)
    print("Encrypted text:", encrypted)

    decrypted = vigenere_decrypt(encrypted, key)
    print("Decrypted text:", decrypted)
else:
    print("Key must contain only alphabets.")



```


# OUTPUT


<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/69930105-0e27-4dc0-a403-cf0aaac5b31f" />



# RESULT

The Vigenère Cipher program is executed successfully.
