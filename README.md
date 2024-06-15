# PRODIGY_Taskcode_01
first task that name is caesar cipher program in python language 
letters = 'abcdefghijklmnopqrstuvwxyz'
num_letters = len(letters)

def encrypt(plaintext, key):
    ciphertext = ''
    for letter in plaintext:
        letter = letter.lower()
        if letter != ' ':
            index = letters.find(letter)
            if index == -1:
                ciphertext += letter
            else:
                new_index = (index + key) % num_letters
                ciphertext += letters[new_index]
    return ciphertext

def decrypt(ciphertext, key):
    plaintext = ''
    for letter in ciphertext:
        letter = letter.lower()
        if letter != ' ':
            index = letters.find(letter)
            if index == -1:
                plaintext += letter
            else:
                new_index = (index - key) % num_letters
                plaintext += letters[new_index]
    return plaintext

print('\n*** CAESAR CIPHER PROGRAM ***\n')

print('Do you want to encrypt or decrypt?')
user_input = input('e/d: ').lower()

if user_input == 'e':
    print('\nENCRYPTION MODE SELECTED\n')
    key = int(input('Enter the key (1 through 26): '))
    text = input('Enter the text to encrypt: ')
    ciphertext = encrypt(text, key)
    print(f'CIPHERTEXT: {ciphertext}')

elif user_input == 'd':
    print('\nDECRYPTION MODE SELECTED\n')
    key = int(input('Enter the key (1 through 26): '))
    text = input('Enter the text to decrypt: ')
    plaintext = decrypt(text, key)
    print(f'PLAINTEXT: {plaintext}')
