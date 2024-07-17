# PRODIGY_cyber_security1
prodigy 1st task




def caesar_cipher(text, shift, encrypt=True):
    """
    Encrypts or decrypts a given text using the Caesar Cipher algorithm.

    Args:
        text (str): The text to be encrypted or decrypted.
        shift (int): The number of positions to shift the letters.
        encrypt (bool, optional): True to encrypt, False to decrypt. Defaults to True.

    Returns:
        str: The encrypted or decrypted text.
    """
    result = ""
    for char in text:
        if char.isalpha():
            # Shift the character
            shifted = ord(char) + (shift if encrypt else -shift)
            
            # Wrap around if the shifted character is out of range
            if char.isupper():
                result += chr((shifted - 65) % 26 + 65)
            else:
                result += chr((shifted - 97) % 26 + 97)
        else:
            result += char
    return result

# Example usage
plaintext = input("Enter the message: ")
shift = int(input("Enter the shift value: "))

encrypted_text = caesar_cipher(plaintext, shift, encrypt=True)
print("Encrypted message:", encrypted_text)

decrypted_text = caesar_cipher(encrypted_text, shift, encrypt=False)
print("Decrypted message:", decrypted_text)
