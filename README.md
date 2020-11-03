# python-樂透對獎

第一次用python做樂透對獎<br>
我分別做了兩種<br>
一種是電腦出號碼－電腦隨機輸入對獎號碼<br>
```
import  random
luckynumber1 =set()                                       #3-5電腦自動出現幸運號碼並加入集合
while(len(luckynumber1)<5):
    luckynumber1.add(random.randint(1,39))
print("本次幸運號碼:" , luckynumber1)
luckynumber2 =set()                                       #7-9電腦自動出現自己號碼並加入集合
while(len(luckynumber2)<5):
    luckynumber2.add(random.randint(1,39))
print("本次自己號碼:" , luckynumber2)
number = luckynumber1.symmetric_difference(luckynumber2)
if len(number)==10 :                                       #判斷中獎個數
    print("可惜一個都沒中")
elif len(number)==8 :
    print("還好還有中一個")
elif len(number)==6 :
    print("恭喜中肆獎")
elif len(number)==4 :
    print("恭喜中參獎")
elif len(number)==2 :
    print("恭喜中貳獎")
elif len(number)==0 :
    print("恭喜中頭獎")
else :
    print("輸入錯誤，請重新輸入")
```
![](https://github.com/babywilly/python-lottery/raw/main/lottery1.jpg)
<br>另一種是電腦出號碼－手動輸入對獎號碼<br>
```
#      今彩539
import  random
luckynumber1 =set()                                       #3-5電腦自動出現幸運號碼
while(len(luckynumber1)<5):
    luckynumber1.add(random.randint(1,39))
luckynumber2= set()
number2 = input("請輸入自己的樂透號碼，以空格鍵隔開共5個:").split()
nums = []   # 儲存得到的五個數。
while True:
    for n in number2:
        if n.isdigit():                            # 檢查是不是整數。
            nums += [int(n)]
        if len(nums) == 5:                         # 如果已經得到五個數字，就離開迴圈。
            break
    if len(nums) < 5:                              # 如果數字少於五個，提示使用者繼續輸入。
        number2 = input("請繼續輸入：").split()
    else:
        break
luckynumber2.update(nums)
number = luckynumber1.symmetric_difference(luckynumber2)
print("本次幸運號碼:" , luckynumber1)
print("本次自己號碼:" , luckynumber2)
if len(number)==10 :
    print("可惜一個都沒中")
elif len(number)==8 :
    print("還好還有中一個")
elif len(number)==6 :
    print("恭喜中肆獎")
elif len(number)==4 :
    print("恭喜中參獎")
elif len(number)==2 :
    print("恭喜中貳獎")
elif len(number)==0 :
    print("恭喜中頭獎")
else :
    print("輸入錯誤，請重新輸入")
```
![](https://github.com/babywilly/python-lottery/raw/main/lottery2.jpg)
11111111111111112222222222222222222222222222