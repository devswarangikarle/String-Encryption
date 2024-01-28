# String-Encryption
Given a string S, transform it as follows: replace every substring of identical letters with a single instance of that letter followed by the hexadecimal representation of the number of occurrences of that letter. Then, take the resulting string and reverse it. Finally, print the encrypted string.

def string_encryption(s):
    result = ''
    count = 1

    for i in range(1, len(s)):
        if s[i] == s[i - 1]:
            count += 1
        else:
            result += s[i - 1] + hex(count)[2:]
            count = 1

    result += s[-1] + hex(count)[2:]
    encrypted_string = result[::-1].lower()
    return encrypted_string

input_string = "ab"

encrypted_result = string_encryption(input_string)

print(encrypted_result)
