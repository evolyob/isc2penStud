```py
##  Reverse Cipher
samp = 'ccsp sampras'
# samp = input('Enter message: ')
translated = ' '

i = len(samp) - 1  
# len()計算有幾個字符
while i >= 0:
# while循環, 檢查結果true,false，當i大於0不斷循環直到等於0
    translated = translated + samp[i]
    i = i - 1
# 執行到 false才會到下一行 print()

print(translated)
```
```py
##  Caesar Cipher
import pyperclip

# the string to encryption decryption
message = 'this is my secret.'
# the en/decryption key
key = 13

# tells the program to encrypt or decrypt
mode = 'encrypt' # set to 'encrypt' or 'decrypt'

# every possible symbol that can be encrypted
#  加密程序的符號集，變量名是全大寫的約定
LETTERS = 'ABCDEFGHIJKLMNOPQRSTUVWXYZ'

# stores the encrypted/decrypted form of the message
translated =''

# capitalize the string in message
message = message.upper()
## 把message都轉成大寫

for symbol in message:
# for是循環歷遍字符或列表， for 歷遍字符在 message裡面。
     if symbol in LETTERS:
#如果symbol裡有在LETTERS裡面就為true
         # get the encrypted (or decrypted) number for this symbol
        num = LETTERS.find(symbol) # get the number of the symbol
        if mode == 'encrypt':
            num = num + key
        elif mode == 'decrypt': ## 並檢查此條件是否為 true
            num = num - key
        # handle the wrap-around if num is larger than the length of
        # LETTERS or less than 0
        if num >= len(LETTERS):
            num = num - len(LETTERS)
         elif num < 0:
            num = num + len(LETTERS)

        # add encrypted/decrypted number's symbol at the end of translated
        translated = translated + LETTERS[num]

    else:
        # just add the symbol without encrypting/decrypting
        translated = translated + symbol

# print the encrypted/decrypted string to the screen
print(translated)

# copy the encrypted/decrypted string to the clipboard
pyperclip.copy(translated)

```
```py

 # Caesar Cipher Hacker
message = 'GUVF VF ZL FRPERG ZRFFNTR.'
LETTERS = 'ABCDEFGHIJKLMNOPQRSTUVWXYZ'

# loop through every possible key
for key in range(len(LETTERS)):

    # It is important to set translated to the blank string so that the
    # previous iteration 1s value for translated is cleared.
    translated =''

    #The rest of the program is the same as the original Caesar program:

    # run the encryption/decryption code on each symbol in the message
    for symbol in message:
        if symbol in LETTERS:
            num = LETTERS.find(symbol) # get the number of the symbol
            num = num - key

        # handle the wrap-around if num is 26 or larger or less than 0
        if num < 0:
            num = num + len(LETTERS)

        # add number's symbol at the end of translated
        translated = translated + LETTERS[num]

    else:
        # just add the symbol without encrypting/decrypting
        translated = translated + symbol

# display the current key being tested, along with its decryption
print('Key #%s: %s' % (key, translated))
```
