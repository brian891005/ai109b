## Colab

* python notebook
* 優點
    * 使用雲端空間，不用自己的電腦空間。
    * 可免費用 Colab 的 GPU 算力，執行深度學習速度有感。
    * 可以跳過 Mac 、 Win 的各種坑，設定省心。
    * 手機平板也可以執行，但建議只用來看成果，因為容易斷線且優化待加強。

* 缺點
    * 佔用 Google 雲端硬碟容量，有些學校有提供學生/校友免費申請 Gmail 教育帳號，使用空間無限大(更新:Google 2022年7月取消該政策改有限額度)。
    * Colab 設定其實也有不少坑。
    * 雲端服務一定要有網路。

![Pic](https://github.com/brian891005/ai109b/blob/main/Note/%E5%9C%96%E7%89%87/RNN.jpg)

## 機器學習 (Machine Learning)
* 指導式學習 (Supervised Learning):
    * 目標是要讓 learning algorithm (model) 能夠根據 training set 學習到 hypothesis function h,使得 h(x)能夠盡可能準確地預測 y
    * Training set 包含了期望的 output y, 因此稱為 supervised learning.

    ![Pic](https://github.com/brian891005/ai109b/blob/main/Note/%E5%9C%96%E7%89%87/指導式學習.jpg)

## One-hot
One-hot在數位電路中被用來表示一種特殊的位元組合，該位元組裏，僅容許單一位元爲1，其他位元都必須爲0

![Pic](https://github.com/brian891005/ai109b/blob/main/Note/%E5%9C%96%E7%89%87/真值表.jpg)

* 優點
    * 決定狀態機目前狀態的時間成本低，因爲讀取一個正反器的時間成本固定。
    * 改變機器的狀態所需時間成本也是固定，因爲每次只需要改變兩個正反器的值。
    * 設計及設計變更容易。
    * 容易偵測出非法狀態。
    * 可以有效率地使用FPGA的大量正反器。 相較於其他編碼，使用one-hot來實現狀態機通常可以達到更高的時脈頻率。

* 缺點
比起其他編碼，需要更多的正反器，使得其在PAL裝置上不切實際。 會有很多非法狀態存在。這是由於N個正反器構成的計數器總共有2^N個狀態（每個正反器可以是0或1，所以總共2^N種可能狀態），但是合法狀態卻只有N個（即同一時間只允許一個正反器是1,其他必須爲0），所以總共會有2^N-N個可能的非法狀態。