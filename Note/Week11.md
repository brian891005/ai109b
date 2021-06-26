## 傅立葉轉換
* 定義
傅立葉轉換（法語：Transformation de Fourier、英語：Fourier transform）是一種線性積分轉換，用於信號在時域（或空域）和頻域之間的轉換，在物理學和工程學中有許多應用。

因其基本思想首先由法國學者約瑟夫·傅立葉系統地提出，所以以其名字來命名以示紀念。實際上傅立葉轉換就像化學分析，確定物質的基本成分；信號來自自然界，也可對其進行分析，確定其基本成分。

## 科學計算常用函式庫
* matplotlib -----> 畫圖、視覺化工具
    * subplot(x,y,z) row_x乘column_y張圖中的第z張。
* numpy -------> 數學矩陣運算
    * import numpy as np
    * np.arange(x,y) 從起始值到上限值。
    * np.add(x,y) 兩矩陣相加。
    * .shape() 回傳矩陣為幾乘幾陣列 .shape=(x,y) 重設矩陣維度。
    * np.linspace(x,y,z) 從x~y分成z個。
    * 可直接使用 a+b a*b a>b 等。
    * a[x:y:z] a變數中大於等於x，小於y,一次取z單位。
    * np.linalg.det(x)求出x矩陣之行列式
    * np.random.randint(0,10,6) 0~10取6個。
* scipy -----> 擴充numpy
    * from scipy import linalg 計算矩陣特徵向量
    * linalg.eig()
* sympy -----> 符號運算
    * x,y = symbols('x y') 建立變數x y。
    * diff(x,y) 對x做y微分。
    * integrate(x,y,z) 對x做積分，範圍是y~z。
    * factor(x) 將x做因數分解。
    * expand(x) 將x乘開。
    * simplify(x) 將x進行同類項合併。
    * solve(x) 將x求解。
    * sympy.sqrt(x) 若x=8則可求出「2根號2」而非無窮小數解。

