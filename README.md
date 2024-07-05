# def encrypt(text, shift):
    encrypted_text = ""
    for char in text:
        if char.isalpha():
            shift_amount = shift % 26
            if char.islower():
                new_char = chr((ord(char) - ord('a') + shift_amount) % 26 + ord('a'))
            else:
                new_char = chr((ord(char) - ord('A') + shift_amount) % 26 + ord('A'))
            encrypted_text += new_char
        else:
            encrypted_text += char
    return encrypted_text

def decrypt(text, shift):
    return encrypt(text, -shift)

def main():
    while True:
        choice = input("Would you like to encrypt or decrypt a message? (e/d): ").lower()
        if choice not in ['e', 'd']:
            print("Invalid choice. Please enter 'e' to encrypt or 'd' to decrypt.")
            continue
        
        message = input("Enter your message: ")
        shift = int(input("Enter the shift value: "))

        if choice == 'e':
            result = encrypt(message, shift)
            print("Encrypted message:", result)
        else:
            result = decrypt(message, shift)
            print("Decrypted message:", result)
        
        another = input("Would you like to encrypt/decrypt another message? (y/n): ").lower()
        if another != 'y':
            break

if __name__ == "__main__":
    main()-decept
Prodigy infotech 
