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
samp = 'ccsp sampras'
translated = ' '

i = len(samp) - 1  //len()計算有幾個字符
while i >= 0:     // while循環, 檢查結果，當i大於0不斷循環直到等於0
    translated = translated + samp[i]
    i = i - 1    //執行到 false才會到下一行 print

print(translated)






