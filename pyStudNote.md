define string
```py
price_str = input("輸入價格")
price = float(price_str)
print = (price)
--vvvvvvv--

price = float(input("輸入價格"))
print = (price)
--wwwwwww--

%s   // srting 字串
name = "uke"
print("myNameIs %s, thankYou" % name)
--> myNameIs uke thankYou

%d   // int    整數 %06d 只顯示最少六位數 不足補零
orderNo = 1
ptint("myOrderNoIs %06d" % orderNo)
--> myOrderNoIs 000001

%f   // float  浮點 %.2f 小數位只顯示兩位
price = 4
buy = 5
pay = price * buy
print("price %.2f dollar, buy %.2f sets, pay %.2f dollars" %(price, buy, pay))
--> price 4.00 dollar  buy 5.00 sets pay 20.00 dollars

%%   // print  輸出
scale = 0.25
print("數據佔比 %.2f%%" % (scale * 100))
--> 數據佔比 25.00%
```
ifelse
```py
==   兩邊相等，   ture
!=   兩邊不相等   ture
>    左大於右，   ture
<    左小於右，   ture
>=   左大於等於右  ture
<=   左小於等於右  ture

age = int(input("howOldAreYou"))
if age >= 18:
#if age >= 18 and age <= 30:
    print("plsEntry")
#elif age >= 30 and age <= 40:
#    print("plsPayFrist")
#elif age >= 40 and age <= 70: 
#    print("plsCallYouDoctor")
else:
    print("seeYouNextTime")
*** 滿足其一個就成立 ***  
```

```py
has_ticket = True
knife_length = 30
if has_ticket:
    print("pass,LetUsChk")
    if :
        ....
    else:
        ....
else:
    print("plsBuyTicket")
```
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
