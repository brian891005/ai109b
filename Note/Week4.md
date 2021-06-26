## 線性規劃

在數學中，線性規劃（Linear Programming，簡稱LP）特指目標函數和約束條件皆為線性的最佳化問題。

* 種類
    * 標準型
    * 增廣矩陣 - [單純形法](https://zh.wikipedia.org/wiki/%E5%8D%95%E7%BA%AF%E5%BD%A2%E6%B3%95)
    * 對偶
* 特性
    * 可加性 : L(x+t) = L(x) + L (t)
    * 一次齊次性 : L(mx) = mL(x)

## 整數規劃
要求所有的未知量都為整數的線性規劃問題。

相對於即使在最壞情況下也能有效率地解出的線性規劃問題，整數規劃問題的最壞情況是不確定的，在某些實際情況中（有約束變量的那些）為NP困難問題。

## NP完全或NP完備(縮寫為NP-C或NPC）
NP完備是NP與NP困難的交集，是NP中最難的決定性問題，所有NP問題都可以被快速歸化為NP完備問題。

* bigO
    * 泡沫排序法:時間複雜度 = n的2次方
    * 循序搜尋法:時間複雜度 = n

* 深度優先搜尋法
![Pic](https://github.com/brian891005/ai109b/blob/main/Note/%E5%9C%96%E7%89%87/深度優先搜尋法.jpg)

* 廣度優先搜尋法
![Pic](https://github.com/brian891005/ai109b/blob/main/Note/%E5%9C%96%E7%89%87/廣度優先.jpg)

