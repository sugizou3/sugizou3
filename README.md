# 杉山 颯 (Sugiyama Sou)

**名古屋工業大学 機械工学専攻 修士1年** 

私は金属を高精度で削る研究をしています。   
この研究は生産技術の関する研究で機械や製品を製作するうえで非常に重要な研究です。 

詳細は **3.研究テーマについて** を参照してください。

---

## 1.スキルセット

### プログラミング言語
- Python
- JavaScript
- C#
- MATLAB

### フレームワーク・ライブラリ
- Scikit-learn
- PyTorch
- Django REST Framework
- React.js
- Next.js

### 開発ツール
- Visual Studio Code
- Anaconda
- Unity
- Docker

### その他のスキル
- Blender
- Fusion360

---

## 2.プロジェクト

### 1. [ビジネス書要約サイト](https://bisiness-hakase-frontend.vercel.app/)
**利用にあたって**  
アカウントにはテスト用にテストユーザーを作成しています。
以下の情報でログインできます。また新規にアカウントを作成していただいてもかまいません。  
メールアドレス : test@test.com  
パスワード : test  


**使用言語**:  
- バックエンド: Python (Django REST Framework)  
- フロントエンド: JavaScript (React.js, Next.js)

**概要**:  
ユーザーがビジネス書の要約を投稿・閲覧できるプラットフォームです。誰でもビジネス書から得たノウハウや具体的なアドバイスを投稿でき、知識やスキル向上のために活用できます。

**開発の動機**:  
YouTube上でビジネス書の要約動画が人気となり、多くのノウハウが提供されている一方で、その情報源が曖昧であったり、内容が散在していることに気づきました。そのため、情報の出典を明確にし、ビジネス書の要約を一元的に管理できるプラットフォームを作成しました。

**機能**:
- ログイン
- 投稿
- 検索ワード自動作成機能（投稿すると投稿内容から検索ワードを自動で生成）
- コメント機能
- いいね機能
- ダウンロード機能（作成中）
- 画面右側に書籍の広告を表示(未実装)

一部バグがあります。  
サイトのレスポンスは遅いです。

![website](https://github.com/user-attachments/assets/376a08f3-215f-4199-874e-19da9c537485)


---

### 2. 競馬AI

**使用言語**:  
- Python (PyTorch)

**概要**:  
このプロジェクトでは、Webサイトからスクレイピングした競馬データを用いて、競馬のレース結果や着順の予測を行っています。過去のレースデータを基にAIを訓練し、着順を予測するモデルを開発しています。

**開発の動機**:  
AIに対する興味から、競馬の着順予測を行うことにしました。競馬では毎週レースが開催され、多くのデータが豊富に存在します。実際に賭けが行われるため、AIの予測精度を上げることで賭けに勝つ可能性があるという点が非常に面白く、現在最も力を入れている内容です。

**技術的内容**:  
最初は**Random Forest**アルゴリズムを使用していましたが、現在は自作のディープラーニングモデルを使用しています。  

競馬のDeeplearningにおける学習で難しい点は可変長、時系列の入力を扱う点です。  
競馬は5～18頭の馬が競い合って順位を決めますが何頭レースに参加するかは毎レース異なります。そのため体重や性別などの馬の情報は馬の出走数だけあるので可変長になります。出走する馬の情報を複製したり、マスクすることで対策しました。  
また順位の予測で重要な情報はその馬が以前のレースでどのような成績を収めたかです。どのような条件（天候など）でどの馬と競い、何位になったかという情報が重要です。このような過去のデータが影響を与えるので競馬は時系列データとなります。時系列データに関してはRNN（再帰的ニューラルネットワーク）が非常に有効です。本競馬AIも隠れ層を作り、過去の情報を引き継ぐようにしました。  

現在のモデルの予測精度はおよそ27%です。参考までに、1番人気の馬が1位になる確率が約33%、ランダムな予測では約8%です。  
現在は、**深層強化学習**を導入し、最も収益が得られる馬券の購入方法を学習させています。

（[詳細はこちら](https://github.com/sugizou3/keiba))

![keiba_model](https://github.com/user-attachments/assets/6c638a97-862e-46e7-a1c1-3b1e2b8459c9)



---

### 3. 画像一致プログラム（研究用途）

**使用言語**:  
- Python (OpenCV)

**概要**:  
金属表面の実験前後の形状を比較するため、2つの画像を一致させるプログラムを開発しました。これにより、実験による表面の変化を正確に観測することが可能になりました。

**開発の動機**:  
実験結果の観測が難しかったため、表面形状を画像として扱い比較できる方法を考案しました。このプログラムは、他の研究室メンバーにも利用されています。

**技術的内容**:  
1. **画像の平行移動補正**: 部分一致を利用して、2枚の画像の相互相関を計算し、最も一致する箇所を特定して補正します。  
2. **表面傾斜の補正**: 最小二乗法を用いて表面の傾斜を補正し、より正確に画像を一致させます。

（[詳細はこちら](https://github.com/sugizou3/Image_match))
![画像一致プログラム画像](https://github.com/user-attachments/assets/e4792a6d-82c4-45ff-a5a3-75765a697d18)




---

### 4. 英単語学習レーシングゲーム

**使用言語**:  
- C# (Unity)

**概要**:  
英単語を学びながら楽しめるレーシングゲームを開発しました。ゲーム内で表示される英単語に正しく答えるとカートが加速し、レースでの優位性が得られるという仕組みです。

**開発の動機**:  
楽しく英単語を学べる方法を模索していたところ、レーシングゲームとの組み合わせを思いつきました。ゲームを楽しむことで、自然に英単語を覚えることができる設計となっています。

**技術的内容**:  
- **UnityのMLAgents**を使用し、強化学習によるレーシングAIを作成。  
- Webスクレイピング技術を活用し、単語の自動発音機能を実装しました。

![RacingGame](https://github.com/user-attachments/assets/1e2748fb-3abb-4faf-8bee-45715f09efea)


---

### 5. その他
#### 1.ビー玉転がし自動生成プログラム  　
概要：Blenderを用い、pythonでビー玉が転がるレール（ジェットコースターのレールのようなもの）を3Dモデルとして自動生成するプログラムを作成しました。  
技術的内容：ランダムに生成した点をベジェ曲線という関数を用いて滑らかに点をつなぎコースを作成、各位置における速度、加速度を微分で求め、加速度の値から急カーブなどは落ちずに転がるように最適な傾斜つけるアルゴリズムを作成

#### 2.機械言語のコンパイルプログラム　
概要：現在研究で使用しているプログラムです。加工機を動かすときにはGコードと呼ばれる言語を使用しますが、可読性や保守性が非常に悪いです。そこでpythonで書いたプログラムをGコードにコンパイルするプログラムや、実際の動作をテストするプログラムを作成しました。

#### 3.追従ミサイルプログラム　
概要：ターゲットに物理的に自然な挙動で追従するミサイルのプログラムを作成しました。  
技術的内容：慣性や粘性とよばれる力学的な作用を学び、またシミュレーション上で物体を回転させるときに使用されるクォータニオンについて理解し実装しました。

---
## 3.研究テーマについて
私の研究では、金属を削る際に発生する「切り屑」がどのように生成されるかを詳しく調べています。金属の加工方法の一つに、不要な部分を削り取って形状を整える方法があります。通常、金属を削ると削り取られた部分が切り屑となって排出されます。しかし、ナノメートル単位の非常に薄い層を削ろうとすると、切り屑がうまく排出されず、表面をただ擦るだけで実質的な削り加工ができない場合があります。  

この切り屑の生成プロセスを深く理解することで、より精密に金属を削り、表面を滑らかに仕上げる技術を向上させることができます。こうした技術は、電子機器や光学部品の製造に不可欠です。  

私の研究では、工具の形状、削る速度、素材の特性が切り屑の生成に与える影響を実験的に調査しました。また、削る過程で素材の表面がどのように変化するかを観察する新しい方法を考案し、これまで困難だった詳細な観察を可能にしました。  
この研究により、より高精度な金属加工技術の開発に寄与することを目指しています。

## 4.趣味
- サッカー
- 筋トレ
- レザークラフト
- 将棋



---
## 5.学歴

- 名古屋工業大学 工学部 機械工学科 卒業 (2023年3月)
- 名古屋工業大学大学院 機械工学専攻 在学中 (修士課程)

---
