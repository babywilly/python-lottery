# python-樂透對獎

第一次用python做樂透對獎<br>
我分別做了兩種<br>
一種是電腦出號碼－電腦隨機輸入對獎號碼<br>
另一種是電腦出號碼－手動輸入對獎號碼<br>
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
