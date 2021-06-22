## 爬山演算法
* 框架化 -----> 通用函數
以後只要帶入from hillClimbing import hillClimbing  引入爬山演算法類別
```
def hillClimbing(s, maxGens, maxFails):   # 爬山演算法的主體函數
    print("start: ", s.str())             # 印出初始解
    fails = 0                             # 失敗次數設為 0
    # 當代數 gen<maxGen，且連續失敗次數 fails < maxFails 時，就持續嘗試尋找更好的解。
    for gens in range(maxGens):
        snew = s.neighbor()               #  取得鄰近的解
        sheight = s.height()              #  sheight=目前解的高度
        nheight = snew.height()           #  nheight=鄰近解的高度
        if (nheight >= sheight):          #  如果鄰近解比目前解更好
            print(gens, ':', snew.str())  #    印出新的解
            s = snew                      #    就移動過去
            fails = 0                     #    移動成功，將連續失敗次數歸零
        else:                             #  否則
            fails = fails + 1             #    將連續失敗次數加一
        if (fails >= maxFails):
            break
    print("solution: ", s.str())          #  印出最後找到的那個解
    return s                              #    然後傳回。

```
* solution物件模組板
    * 定義鄰邊、改變值、能量or高度(將問題框架化)
```
class Solution: # 解答的物件模版 (類別)
    def __init__(self, v, step = 0.01):
        self.v = v       # 參數 v 為解答的資料結構
        self.step = step # 每一小步預設走的距離

    # 以下兩個函數至少需要覆蓋掉一個，否則會無窮遞迴
    def height(self): # 爬山演算法的高度函數
        return -1*self.energy()               # 高度 = -1 * 能量

    def energy(self): # 尋找最低點的能量函數
        return -1*self.height()               # 能量 = -1 * 高度
```
>>energy取最低點
>>height取最高點

* 引入答案值
```
from hillClimbing import hillClimbing # 引入解答類別
from solution import Solution
import random

class SolutionNumber(Solution):
    def neighbor(self): # 單變數解答的鄰居函數。
        x = self.v
        dx= self.step               # x:解答 , dx : 移動步伐大小
        xnew = x+dx if random.random() > 0.5 else x-dx # 用亂數決定向左或向右移動
        return SolutionNumber(xnew) # 建立新解答並傳回。

    def energy(self):               # 能量函數
        x = self.v                  # x:解答
        return abs(x*x-4)           # 能量函數為 |x^2-4|

    def str(self): # 將解答轉為字串，以供印出觀察。
        return "energy({:.3f})={:.3f}".format(self.v, self.energy())

```
* 執行結果
    * 設好能量
    * 鄰邊
    * 字串設定
>>hillClimbingNumber.py
```
$ python hillClimbingNumber.py
start:  energy(0.000)=4.000
0 : energy(0.010)=4.000 
2 : energy(0.020)=4.000 
4 : energy(0.030)=3.999 
5 : energy(0.040)=3.998 
        .
        .
        .
364 : energy(1.950)=0.197
365 : energy(1.960)=0.158
366 : energy(1.970)=0.119
367 : energy(1.980)=0.080
371 : energy(1.990)=0.040
373 : energy(2.000)=0.000
solution:  energy(2.000)=0.000
```
* 圖例
![Pic](https://github.com/brian891005/ai109b/blob/main/Note/%E5%9C%96%E7%89%87/height.jpg)

#### 技術
* 物件導向技巧----->self的應用
* 資料結構化------->串聯各結構