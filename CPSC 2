def positional_shift_cipher(text):
    # Define the custom order for non-alphabetic characters
    custom_order = r' !"$%&\'()*+,-./0123456789:;<=>?@[]^_{|}~§abcdefghijklmnopqrstuvwxyzæøå'
    custom_length = len(custom_order)

    result = []
    cumulative_shift = 0

    for index, char in enumerate(text):
        shift = index + 1 + cumulative_shift  # The shift includes the cumulative shift from previous characters

        if char.isalpha():  # Check if the character is a letter
            if char.islower():
                shifted_char = chr((ord(char) - ord('a') + shift) % 26 + ord('a'))
            elif char.isupper():
                shifted_char = chr((ord(char) - ord('A') + shift) % 26 + ord('A'))
            cumulative_shift += ord(shifted_char) - ord(char)  # Update cumulative shift
            result.append(shifted_char)
        elif char in custom_order:  # Check if the character is in the custom order
            original_index = custom_order.index(char)
            shifted_index = (original_index + shift) % custom_length
            shifted_char = custom_order[shifted_index]
            cumulative_shift += shifted_index - original_index  # Update cumulative shift
            result.append(shifted_char)
        else:
            result.append(char)  # Characters not in custom order are added unchanged

    return ''.join(result)


# Example usage:
input_text = "Hello I am cool! 1234"
ciphered_text = positional_shift_cipher(input_text)
print(f"Original text: {input_text}")
print(f"Ciphered text: {ciphered_text}")
