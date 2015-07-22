# Jul2015 東京工業大学「バイオインフォマティクス」演習 #

国立遺伝学研究所  
中村保一 (July 16 / 23, 2014)  
  
# この資料のURL→ http://bit.ly/yn15titech #
## [July 23 ここから](https://github.com/ikasumipapa/training/blob/master/titech2015.md#ddbj--国立遺伝学研究所-httpwwwddbjnigacjp) ##
  
## 0. イントロダクション ##

### 自己紹介 ###

   49歳。木更津市／三島市二重生活中。  
   こんな人です。  
   http://charles.genes.nig.ac.jp/members/yn/  
   http://twitter.com/yaskaz  
   http://spysee.jp/中村保一/1034648/  
  　
  
   京大→遺伝研→かずさ→遺伝研と「ゲノム」と「情報」を扱ってきています。  

------------------------------

### 情報リテラシー再入門：検索 ###

#### google ####

*ま、とにかく、まずは「ググれ」 http://www.google.co.jp*  
  
- google の原理
  
   「ロボット」が収集にやってくる（以下はとあるサーバのアクセスログにあったgooglebotの痕跡）  
  
   ```
   crawl-66-249-65-51.googlebot.com - - [24/Dec/2006:14:39:41 +0900] "GET /~yn/jp/?plugin=attach&pcmd=open&file=logo_jp.png&refer=LogoMark HTTP/1.1" 200 86078
   crawl-66-249-65-51.googlebot.com - - [24/Dec/2006:15:21:12 +0900] "GET /~yn/jp/?plugin=attach&pcmd=open&file=LogoAndMark_mono.png&refer=LogoMark HTTP/1.1" 200 73543
   crawl-66-249-65-51.googlebot.com - - [24/Dec/2006:15:27:35 +0900] "GET /~yn/jp/?cmd=backup&page=seikawakate2005 HTTP/1.1" 200 6828
   crawl-66-249-65-51.googlebot.com - - [24/Dec/2006:16:02:38 +0900] "GET /~yn/jp/?plugin=attach&pcmd=open&file=sample_namecard.ppt&refer=LogoMark HTTP/1.1" 200 278528
   crawl-66-249-65-51.googlebot.com - - [24/Dec/2006:16:06:19 +0900] "GET /~yn/jp/?Publications HTTP/1.1" 200 53032
   crawl-66-249-65-51.googlebot.com - - [24/Dec/2006:16:44:21 +0900] "GET /~yn/jp/?plugin=attach&pcmd=open&file=arc.jpg&refer=BusTable HTTP/1.1" 200 70808
   ```
  
   - 「どこからもリンクのないページ」は原理的に探索不可能  
   - どこかからリンクがあれば、いつかはやってくる  
   - 更新頻度が高いほど、google で上位にやってくる（blog とかが上位に来がちという問題）  
  
  　

#####基本的活用法#####

- ダブルコーテーションの活用（勝手に解釈させない）  
   課題：ダブルコーテーションありなしに注意しつつ、以下の検索結果の「件数」とその内容を比較しましょう。  
   ```
   すずけか台
   "すずけか台"
   ```
  　

- 論文の題名の一部または全部でググる
   結構pdfがひっかかってきたりする。scholar （後述）へのリンクがトップにでてくる場合がありますね。  
   検索例：
   ```
   Arabidopsis kinase
   Synechocystis sensory
   ```
   遺伝子のアクセッション番号や遺伝子名そのものでググる これが意外に使える。論文のサプリメントファイルが拾えたりする場合も。  

   検索例:
   ```
   sll1234
   ```
  　
  
- 英文、とくに前置詞の使い方がただしいかどうか、ググる  
   検索例:
   ```
   Study on
   Study in
   Study of
   ```
  　
  
#####一歩すすんだ検索#####
  
   - OR検索 googleは「AND検索」つまり、キーワード全てを含む結果を行います。  
   キーワードの一部を含んでいればいい場合=「OR検索」には文字通り「OR」を使います。  

   【課題】以下の検索の意味と、検索結果（特に右上の検索結果数) を比較しましょう。どのように違いますか？  
   ```
   Mus musculus domesticus
   Mus musculus OR domesticus
   ```
   【解答】上：３つのキーワードが全部入っているページを検索、下：Musに加え、musculus か domesticus のどちらかが記載されているページ
  
   【課題】以下はそれぞれ、どのような検索をしていることになるのでしょうか。その結果は？  
   ```
   Mus OR musculus OR domesticus
   "Mus musculus" OR "Mus domesticus"
   ```
   【解答】上：Mus, musculus, domesticus のどれかのキーワードがあれば良い、下：「Mus musculus」もしくは「Mus domesticus」のどちらかがあれば良い
  　　
  　
  
   　  
   - ワイルドカードを使う  
   
   なにが挟まっていても良いことを示す記号。トランプで言うと「ジョーカー」みたいなものです。  
  
   【課題】以下の検索を実行しましょう
   ```
   vitamin * is good for *
   ```
  　　
  　
  
   - .. 一定の数値範囲を指定  
  
   【課題】以下の検索を実行しましょう
   ```
   Arabidopsis 2001..2006
   ```
  　
  
   - − (マイナス) 特定のキーワードを除外  
  
   【課題】以下の検索結果数、内容を比較してみる
   ```
   東工大
   東工大 -東京工業大学
   ```
  　
  
   - ファイルタイプ指定 (PowerPoint, PDF, Word書類, Excel書類, text, html) 【これ有用！】
   ```
   filetype:ppt, filetype:pdf, filetype.doc, filetype:xls, filetype:txt, filetype:html
   ```
   
   【課題】以下の検索を実行しましょう
   ```
   blast filetype:ppt
   mouse filetype:xls
   ```
  　
  
   - site: 特定のサイトで検索  
  
   【課題】それぞれ何を検索しようとしているかを考え、実際に検索してみて、検索数の違いを比較しましょう
   ```
   東京工業大学
   東京工業大学 site:titech.ac.jp
   東京工業大学 -site:titech.ac.jp
   ```
  　
  
   【課題】癌の研究に関係するPDFとパワポファイルを文部科学省のサイトで探しなさい  
   【解答】癌 研究 site:mext.go.jp filetype:pdf OR filetype:ppt
  　
  　
  
  　　
   - link: 特定のサイトへのリンクがあるページ  
  
   【課題】東工大のトップページへのリンクがあるページを検索しよう
   ```
   link:www.titech.ac.jp
   ```
  　
  
   - 電卓・通貨 http://www.google.com/intl/ja/help/features.html#calculator  
  
   ちょっと便利だったりする。乗算はアスタリスク、アスタリスクが２つでべき乗  
  
   【課題】以下を計算するにはどうしますか？
   ```
   3×2
   3の2乗
   ```
   【解答】上：3\*2　下 3\*\*2 （3\^2　でも可)  
    
   【課題】「8ルート3」の結果は何が得られると思いますか?  
   【解答】8 かける ルート３の結果ですね  
  
   【課題】「8の3乗根」を求める方法は？  
   【解答】3rd root of 8　どうやら日本語の表記法は無いようです  
    
   【参考】1000円を米ドルに  
   【参考】10億リットルを東京ドームで  
  　
  
   そんなgoogleの便利な利用法についてはこちらを参照 http://support.google.com/websearch/  
  　
  
------------------------------

### 学術系論文等情報検索  

#### PubMed: http://pubmed.gov ####
  
   - 泣く子も黙るNational Center for Biotechnology Information (NCBI) 提供の学術論文検索の総本山

   *E. coli*（大腸菌）O111のゲノム関連論文を探してみよう  

   1. 検索窓に E. coli と入れてGoをクリック ⇒ Results: の論文数をチェック＝こんなに大腸菌に関する論文がある  
   2. O111 を追加して「E. coli O111」で絞り込み検索する  
   3. さらにgenome を追加して「E. coli O111 genome」で絞り込み
   4. 実際にどのようなタームに展開されて検索されているかは右カラムの「Datails」に表示されている (… MeSHってなんだ？＞ただちにぐぐろう）  
   5. より一層の絞り込みは上部のAdvancedから指定できる。たとえば「Title/Abstract」や「Author」「Publication Date」を指定するなどして絞りこめる  

   ※complete genome sequence などの語句を指定しても一発でゲノム論文を出すのは結構難しいことがわかります
  
    【課題】 猫アレルギーの人が猫を飼うための猫洗いのテクニックを記述した学術論文を検索しなさい。(ヒント: wash allergy)  
    【解答】 cat wash allergy で検索し「Evaluation of different techniques for washing cats: quantitation of allergen removed from the cat and the effect on airborne Fel d 1.」に至る。１週間に１度、３分間お湯につけるのを２回
繰り返すとよい  
  
    【応用】: RSS feedを使って、定点観測するには  
    本家統合TV: http://togotv.dbcls.jp/20070920.html (YouTube版: http://www.youtube.com/watch?v=5K8-xnkcClo ) を参照  
  
    【応用】: PubMedに収録されているすべての論文数を知りたい場合には？  
    本家: http://togotv.dbcls.jp/20071213.html (YouTube版: http://www.youtube.com/watch?v=Or5QeVMlzMQ ) を参照 (All[filter] で検索)

------------------------------

#### Google Scholar http://scholar.google.com ####
  
   - 学術系のgoogle検索
  
   学術専門誌、論文、書籍、要約など、さまざまな分野の学術資料を検索。ISIと契約するお金がなくても、論文引用数の概数を知ることは可能。たとえば、NAKAMURA Yasukazu. さんの発表論文や講演要旨をさがしてみよう。  
  
   ```
   author:yasukazu-nakamura
   ```
  
   【課題】 あなたの論文、あるいはあなたの指導教員の出版した論文のなかでこれまでに一番よく引用されているのはどれだろうか。またどんな論文からその論文が引用されているか  
  
   【課題】 BLAST ( basic local alignment search tool )   の初出論文を引用している論文数は膨大なモノだと考えられるが、その数を調べ、また、引用している論文を列挙しなさい  
   【解答】basic local alignment search tool で検索し、引用元を確認  
  
   【応用】文献管理ソフトであるBibTeXやEndNoteに簡単に検索結果を取り込むためのリンクの設置が可能右上のメニューの「設定」からどうぞ。＞修論書く際に、引用文献一覧つくるのが楽になるぞ
    
   【応用】h-index ( http://ja.wikipedia.org/wiki/H%E6%8C%87%E6%95%B0 ) は学者の論文数と被引用数とに基づいて、科学者の科学的貢献度を示す指標です。google scholar を利用すると比較的簡単に h-index を出すことができます。引用の多い順に文献の検索結果がならんでいますので、被引用数が、リストの上からのカウントを上回ったらそのひとつ手前のカウントが h-index です。あなたのまわりのセンセイ方の戦闘能力を数値で定量比較してみよう。いっひっひ。  

------------------------------

#### OReFiL: an Online Resource Finder for Lifesciences http://orefil.dbcls.jp/ ####
  
   - ライフサイエンス分野の文献に記載されているウェブリソース(データベースやツールなど)を検索するならこれ
  
   【課題】 primerをアレコレするためのWWWサイトで、報告されているものに、どのようなものがあるだろうか？OReFiLで調べなさい  
   【課題】 codon usage をアレコレするためのWWWサイトで、報告されているものに、どのようなものがあるだろうか？OReFiLで調べなさい
  
    See also: 統合TV「OReFiLを使ってライフサイエンス分野のwebリソースを検索する」 http://togotv.dbcls.jp/20070831.html  

------------------------------

#### Allie: A Search Service for Abbreviation / Long Form http://allie.dbcls.jp/ja ####
  
   - 生命科学分野において利用されている略語とその展開形を検索するサービス
  
   文献中に多く出現する略語は多義語であることが多く、特に専門外の読者には理解するのに困難を伴うことがあります。Allieはこの問題に対する一つの解となるよう開発されています  
  
   【課題】 SPF という略語は生活や生物学研究のさまざまな場面で目にしますが、それらは何の略語で？Allieで調べなさい  
  
   See also: 統合TV「Allieを使って略語の正式名称を検索する」 http://togotv.dbcls.jp/20080522.html  

------------------------------

#### difff: 日本語対応で簡単に差分が確認できるテキスト比較ツール http://difff.jp ####
  
   - 論文や発表要旨を先生になおしてもらったときに、Word の履歴記録がオフになっていると、どこが変わっていたのかわからなくなったりします。difff はテキスト差分を簡単に確認できるツールです。コピペの発見もできちゃうからレポート提出時には要注意ですよ   
  
   【課題】 difff obokata で検索⇒コピペはイカンよ。  
  
   See also: 統合TV「difff《ﾃﾞｭﾌﾌ》を使って文章の変更箇所を調べる」 http://togotv.dbcls.jp/20130828.html  



## 2. 配列決定法とゲノムプロジェクト ##

### ゲノムプロジェクト ###

#### シークエンシングテクノロジの進歩 ####

##### 蛍光によるdideoxy法（サンガー法） #####

   - Polymerase Chain Reaction (PCP)
     - http://www.youtube.com/watch?v=QaWLJVGEFi8 (youtube)
   - Sanger Sequencing (dideoxy method)
     - http://www.youtube.com/watch?v=oYpllbI0qF8 (youtube)
     - http://www.youtube.com/watch?v=6ldtdWjDwes (youtube)
  
##### New Generation Sequencer (NGS) #####

   - illumina Genome Analyser
     - http://www.youtube.com/watch?v=77r5p8IBwJk (youtube)
  
     1. フラットな固層上に適当な間隔でDNAを1分子ずつ固定、基盤上で「ブリッジPCR」を行い、スポットとしてDNAを増幅  
     2. 相補鎖合成を行いながら、4つの塩基に別々の蛍光標識をつけておいて、結合した塩基の場所をスポットの光として特定し、塩基配列を解読していく。  
  　
  
#### どのような目的でシーケンスを行うのか ####

##### NGSの出現によって可能になった塩基配列決定プロジェクト #####

   - 1000ゲノムプロジェクト
   - 環境ゲノミクス
  
### DDBJ @ 国立遺伝学研究所 http://www.ddbj.nig.ac.jp ###

   An INSDC partner

   International Nucleotide Sequence Database Collaboration (INSDC): http://www.insdc.org/  
   - DDBJ (JP): http://www.ddbj.nig.ac.jp/
   - ENA (EU): http://www.ebi.ac.uk/ena/
   - GenBank (USA): http://www.ncbi.nlm.nih.gov/Genbank/

### INSDC / DDBJ のデータベース ###

   1. Trad  
     - DDBJ の紹介: http://www.ddbj.nig.ac.jp/intro-j.html  
     - Release: http://www.ddbj.nig.ac.jp/breakdown_stats/dbgrowth-e.html#graph  
   1. DDBJ SRA (DRA)  
     - http://trace.ddbj.nig.ac.jp/dra/  
   1. DDBJ Trace Archive  
     - http://trace.ddbj.nig.ac.jp/dta/  
   1. BioProject  
     - http://trace.ddbj.nig.ac.jp/bioproject/  
   1. BioSample  
     - http://trace.ddbj.nig.ac.jp/biosample/  
   1. Japanese Genotype-phenotype Archive (JGA)  
     - http://trace.ddbj.nig.ac.jp/jga/  
   ⇒どんどんデータベースが増えている。何故？ ⇒ NGS で配列決定研究が多彩・多数に

------------------------------

###【実習】塩基配列情報へのアクセス ###

#### 1. DDBJ ARSA で検索: http://ddbj.nig.ac.jp/arsa/ ####

   - 高速なキーワードによる配列検索・取得
   
   【課題】DDBJ でヒトのインターロイキン２の全長遺伝子を含む配列を検索しましょう  
   
   1. DDBJ ARSA で検索、ARSA を開く  
   1. Quick Search 窓に **Homo sapiens interleukin 2** と入力する  
      ⇒大量のヒットが得られる。どうもヒト以外もたくさんはいっているようだ  
   1. Facet の Organism_facet から **Homo sapiens** を選ぶと、ヒトの配列に限定される。だがまだ多いな
     ⇒interleukin 1 なんかが混入している。"interleukin 2" をセットで検索しましょう  
   1. Search Condition をひらいて、**Homo sapiens "interleukin 2"** として検索  
     ⇒だいぶ減ったが、partial な配列が多数あるようだ  
   1. Search Condition をひらいて、**Homo sapiens "interleukin 2" complete** として検索  
     ⇒検索結果を開き、Features（特徴）を確認しよう。  
     ⇒得たい配列にチェックをいれ、フォーマットを選んでダウンロードできます  
   【応用】Advanced Search もお試しください。日付や論文等で絞り込みできます  

#### 2. Entrez 改め GQuery http://www.ncbi.nlm.nih.gov/gquery ####

   - National Center for Biotechnology Information (NCBI)の、配列と論文に関連した情報を何でも引けるNCBIの生物系検索決定版
    
   【課題】NCBI でヒトのインターロイキン２の全長遺伝子を含む配列を検索しましょう  
  
   1. GQuery をひらき、眺める（大量のデータベースの複合体）
   2. interleukin-2 から検索スタート
   3. AND human を追加して絞ってみる (interleukin-2 AND human で検索)
   4. AND full length cDNA を追加 (interleukin-2 AND full length cDNA で検索)
   5. 左下あたりの「Nucleotide ? 件」を開いてみると、Mouse などがコンタミしてるので、右ペインの Top Organisms から Homo sapiens を選択  
   6. 検索結果を開き、それぞれのFeatures（特徴）とそこからのリンクを確認しよう。  
  　　  
   【応用】: Pubmed で同様に論文を検索しなさい。  
   【応用】: 右上の Sign in to NCBI からログインすると、どのようなすばらしいサービスが受けられるのかを確認しよう。まだ使ってない人は登録して他のラボメンバーに差をつけよう。  
  
#### 3. GOLD: http://www.genomesonline.org ####

   *世界中のゲノムプロジェクトとESTプロジェクトを網羅したすごいデータベース*

   1. メタゲノムプロジェクト（複数の生物をまとめて読んでしまうやりかた） metagenomes
   2. 終了したプロジェクト: Complete Projects
   3. 進行中のプロジェクト: Incomplete Projects
   4. アナウンスされているプロジェクト: Targeted Projects
  　　  
   - 生物の種名の調べ方
   　　いきなりgoogleとかでもいいんですよ http://www.google.co.jp/  
  　　  
   【実習】大腸菌O111ゲノムは決められている？  
   【実習】大腸菌のゲノムプロジェクトはいくつ存在？そのうち、完成して発表 (Complete and Published) されたプロジェクトはいくつか？  
   【実習】ネコゲノムプロジェクトって存在する？そのフェイズは？  
  　　  
   See also: 統合TV「GOLD -Genomes Online Databaseを使い倒す 2013」http://togotv.dbcls.jp/20131029.html

#### 4. NCBI Taxonomy: http://www.ncbi.nlm.nih.gov/taxonomy ####

   - 生物分類と配列情報を関連させて調べたい場合にはここ。30万種以上の生物が網羅されています。分類体系は独自な場合もあるので注意   
   【実習】あなたが興味のある生物種のプロジェクトはないかNCBI Taxonomy で調べてみよう （例：Arabidopsis, cat, mouse, … あなたの研究対象／興味のある生物でどうぞ）  

   1. 生物名（common name ＝一般名 も可）で検索できます。  
   2. 右ペインの  Entrez records から、その生物種の NCBI のリソースにおさめられている DB を展開してみましょう（Nucleotide〜Genome, PopSet, GEO, SRA, BioProject, BioSample, BioSystems, …）  
   3. 下部の Lineage から類縁の生物種を展開してみましょう  
   4. 下スクロールして Genome Information, External Information Resources を確認しましょう。GOLD へはここからも行けますね。学名で引かなくて良いのでここから行く方が早そう  
  　　  
   > See also: 統合TV「NCBI Taxonomy Browserを使って、生物分類と配列情報を関連させて調べる」 http://togotv.dbcls.jp/20090226.html


## 3. 配列類似検索 ##

### 塩基配列の注釈の基礎 (annotation) ###

#### DNA→RNA→タンパク質の情報の流れ（一応おさらい） ####

   - DNA→(転写:transcription)→RNA→(翻訳:translation)
     - DNA: ATGGGAGTTCTG...
     - RNA: AUGGGAGUUCUG...

     DNAのT(チミン)＝RNAのU(ウリジン)　他の塩基は同じ

   - RNA→(翻訳:translation)→タンパク質 protein

      RNA: AUGGGAGUUCUG...  
      PRO:  M  G  V  L  ...  
  
      塩基３文字（＝コドン）がアミノ酸１文字に対応  
      アミノ酸配列＝タンパク質  

   - タンパク質は生体を構成する主要な物質。

   タンパク質の多くは「酵素」であり、細胞内で物質を変換する触媒となる  
   「代謝」をつかさどっているのがタンパク質でできた酵素。その設計図がDNA上の「遺伝子」  
   タンパク質の配列は、アミノ酸の性質によって、一定の形に折り畳まれる  
  
   生体内で用いられるアミノ酸は20種類ある。
  
   |一文字コード|三文字コード| アミノ酸(英)   | アミノ酸(和)      |
   |:----:|:-----:|:--------------|:-----------------|
   |A     | Ala   | Alanine       | アラニン         |
   |C     | Cys   | Cystein       | システイン       |
   |D     | Asp   | Aspartate     | アスパラギン酸   |
   |E     | Glu   | Glutamate     | グルタミン酸     |
   |F     | Phe   | Phenylalanine | フェニルアラニン |
   |G     | Gly   | Glycine       | グリシン         |
   |H     | His   | Histidine     | ヒスチジン       |
   |I     | Ile   | Isoleucine    | イソロイシン     |
   |K     | Lys   | Lysine        | リジン           |
   |L     | Leu   | Leucine       | ロイシン         |
   |M     | Met   | Methyonine    | メチオニン       |
   |N     | Asn   | Asparagine    | アスパラギン     |
   |P     | Pro   | Proline       | プロリン         |
   |Q     | Gln   | Glutamine     | グルタミン       |
   |R     | Arg   | Arginine      | アルギニン       |
   |S     | Ser   | Serine        | セリン           |
   |T     | Thr   | Threonine     | スレオニン       |
   |V     | Val   | Valine        | バリン           |
   |W     | Typ   | Tryptophan    | トリプトファン   |
   |Y     | Tyr   | Tyrosine      | チロシン         |
  
   アミノ酸は20種類しかないのに、コドンは３文字だから、4x4x4=64種類ある  
   一つのアミノ酸を指定するコドンが複数存在する場合がおおい  
  
   例: F (Phe) フェニルアラニン UUU, UUC  
   例: L (Leu) ロイシン UUA, UUG, CUU, CUC, CUA, CUG (後ろの４つは実質 CU の二文字で判別可)  
  　
  
#### ゲノムの注釈 genome annotation ####

   注釈には二種類ある
   
   - 構造注釈 structural annotation  
     - 遺伝子の構造を記載したアノテーション  
   - 機能注釈 functional annotation  
     - 遺伝子の機能を記載したアノテーション  
   INSDC の例: http://www.ncbi.nlm.nih.gov/nuccore/4732164 (Arabidopsis BAC F10A2)  
   featuresなどの注釈がどのようについているのか、眺めてみましょう。
   - 遺伝子の「構造 structure」を予測すること  
     DNAは読めるが、それだけでは遺伝子はわからない  
     ゲノムを読んだら遺伝子の構造を把握することがまず第一  
  
#### 遺伝子構造アノテーションの基礎 ####

1. 類似配列検索

   既知の遺伝子に類似な配列は遺伝子（たぶん）  
     - オーソログ ortholog （種分化と同時に遺伝子が分離）  
     - パラログ paralog （種のなかで遺伝子が重複）  
   
   - NCBI BLAST  
     - http://www.ncbi.nlm.nih.gov/BLAST/  
   - DDBJ BLAST  
     - http://blast.ddbj.nig.ac.jp/top-j.html  
     - 日本語・clustalwへの連続技が可能  
   - BLAT  
     - http://genome.ucsc.edu/cgi-bin/hgBlat  
     - 高度な一致を検索する。やたらと高速  

   遺伝子のレパートリーは数え尽くされたか？→No。誰とも似ていない遺伝子がたくさんある
   
     1. 配列の比較・検索＝アラインメント  
     2. アミノ酸配列のアラインメント  
     「マトリクス」＝類似の程度を示す  
       - PAM250・BLOSUM62  
     3. ダイナミックプログラミング = DP  
       「最適経路中の部分経路もまた最適経路になっている」動的計画法は、この原理を利用して最適化問題を解く。  
       ある問題を、多段階に「バラす」ことができる場合、動的計画法によって各段階の最適解(経路)を求め、それをたどることで、全体の問題を解くことが可能になる。  
       ただし、まじめにDPやるとタイヘンなんで、はしょる  

   - FASTA  
     - よく似た領域の周囲だけをDPで探索  
   - BLAST  
     - 「ワード」の一致を発見・そこからアラインメントを横へ延ばす・きわめて高速・巨大配列も探索可能  

BLAST検索のprogram option  

| program     | Query        | DB           | 概要                                                                        |
|:-----------:|:------------:|:-------------|:----------------------------------------------------------------------------|
| BLASTN      | 核酸配列     | 核酸配列     | 問い合わせ配列と類似の核酸配列を検索                                        |
| BLASTP      | アミノ酸配列 | アミノ酸配列 | 問い合わせ配列と類似のアミノ酸配列を検索                                    |
| BLASTX      | 核酸配列     | アミノ酸配列 | 問い合わせ核酸配列をアミノ酸に翻訳した配列で、類似のアミノ酸配列を検索      |
| TBLASTN     | アミノ酸配列 | 核酸配列     | アミノ酸配列を核酸配列のデータベースを翻訳したものと類似の配列を検索        |
| TBLASTX     | 核酸配列     | 核酸配列     | 問い合わせ核酸配列を翻訳したものを、核酸配列DBを翻訳したものとの類似を検索  |
| MEGABLAST   | 核酸配列     | 核酸配列     | 感度は落ちるが BLASTN より高速。大規模な検索の際に使うと良い                |
| PSI-BLAST   | アミノ酸配列 | アミノ酸配列 | DBとの検索を繰り返すことで、弱い類似しかない配列を検索可能にする方法        |
| PHI-BLAST   | アミノ酸配列 | アミノ酸配列 | 配列の「パターン」で類似の配列を検索する                                    |

   【実習】BLASTあれこれ  
  
   - NCBI BLASTを体験しよう  
   
     ```
     >opsin Rh2(Drosophila melanogaster)  
     MERSHLPETPFDLAHSGPRFQAQSSGNGSVLDNVLPDMAHLVNPYWSRFAPMDPMMSKIL  
     GLFTLAIMIISCCGNGVVVYIFGGTKSLRTPANLLVLNLAFSDFCMMASQSPVMIINFYY  
     ETWVLGPLWCDIYAGCGSLFGCVSIWSMCMIAFDRYNVIVKGINGTPMTIKTSIMKILFI  
     WMMAVFWTVMPLIGWSAYVPEGNLTACSIDYMTRMWNPRSYLITYSLFVYYTPLFLICYS  
     YWFIIAAVAAHEKAMREQAKKMNVKSLRSSEDCDKSAEGKLAKVALTTISLWFMAWTPYL  
     VICYFGLFKIDGLTPLTTIWGATFAKTSAVYNPIVYGISHPKYRIVLKEKCPMCVFGNTD  
     EPKPDAPASDTETTSEADSKA  
     ```
   
     1. http://blast.ncbi.nlm.nih.gov/Blast.cgi を開く
     2. 「protein BLAST」を選択
     3. 「Enter accession number(s), gi(s), or FASTA sequence(s) 」窓に上記の配列をコピペする (cmd-C then cmd-V)
     4. 「Choose Search Set」＞「Database」の「UniProtKB/Swiss-Prot(swissprot)」を選択
     5. 左下の「BLAST」ボタンをクリック→実行
     6. まず「Conserved domains」が示される（BLASTの結果が帰って来た後でも「Graphic Summary」の「Show Conserved Domains」から閲覧可能）
     7. 「Conserved domains」画像中の「7tm_1 superfamily」をクリック → Conserved Domain として「7tm_1[pfam00001], 7 transmembrane receptor (rhodopsin family)」が見いだされた（７回膜貫通型receptor）
     8. そろそろ結果が得られているはず。Graphic Summary, Descriptions を眺めてみよう。
     9. 下へスクロールして「Descriptions」へ
     10. 上から順に数本にチェック入れる
       1. Download – 手元にダウンロード
       2. GenPept – GenBank からの翻訳DBへ
       3. Graphics – グラフィクスでの配列比較
       4. Distance tree of results – 簡易的な系統樹が描ける。ざっくり観たいときに便利
       5. Multiple alignment – 選んだ配列で COBALT によるマルチプルアラインメントを実施
     11. 下へスクロールして「Alignments」へ
     12. アラインメントの右横にある Related Information を活用しよう
     15. 結果上部のリンク「Edit and Resubmit」から生物種やキーワードでの検索結果のしぼりこみができます
       （例）「Choose Search Set」の「Organism」に「Homo sapiens (taxid:9606)」を入れて（Homo あたりまで入れれば補完候補が出る筈）ヒトの opsin を再検索してみましょう。  
     16. 右の Exclude をチェックすることで、特定の生物種（群）を除外することもできます。これ便利な
     17. 結果上部のリンク「Download」から結果の csvでのダウンロードができます＞Excel に読み込んで結果の保存や一致の length や % でのソートが可能
  　
  
   【参考】: cDNAやESTのゲノムへのマッピング（貼り付け）は、BLATのほうがよい。ただしWWWで検索できる生物種はほとんどが animal。上記リンクで確認しよう。  
   【応用】: 検索結果で得られた類似な配列をまとめどりしよう統合TV本家: http://togotv.dbcls.jp/20070926.html (YouTube版: http://www.youtube.com/watch?v=RhTmgpOIUIw ) を参照  
   【応用】: PSI-BLASTを使うと、類似が低いが遠縁であるような配列を捕まえることもできます。上記の配列で実行してみましょう。統合TV本家: http://togotv.dbcls.jp/20071016.html (YouTube版: http://www.youtube.com/watch?v=iIufC3uNlEk ) を参照  
   【応用】「マトリクス」をかえて検索してみましょう。  
   【応用】table format は大量にサーチする際に便利です。結果をダウンロードして、エクセルで開いてみよう  
  
    *e-valueとは？*  
   E = Kmn^(e-λS)
   そのライブラリで偶然に同じスコアでヒットする本数の期待値  
   ライブラリの大きさ／内容が違うと e-value は違うから単純には比較できないぞ。注意  
  　

#### 遺伝子機能予測 ####

   遺伝子の機能を知るためには

   まず、機能が「本当の意味で」判明している遺伝子は驚くほど少ないことを認識しましょう。

   - 実験で知る・推し量る  
     酵素活性をはかる  
     遺伝子(DNA)→転写→RNA→翻訳→タンパク質  
     タンパク質をとり、どんな酵素活性をもつのか調べる  
     - 古典的遺伝学　形態や現象から遺伝子へ
     - 逆遺伝学　遺伝子から形態や現象へ＝遺伝子を「潰す」
   
   - 実験を使わずに類推する  
     配列の類似 ⇒ 配列が似ていれば機能も似ている（多分）  
     しかし！類似の類似の類似の類似は類似ではないかもしれない  
       - 「相同 (homology) 人の手＝猫の足＝鳥の羽  
       - 「相似」(similarity) コウモリと鳥の羽、パンダの親指  
     部分一致している部分は機能と関わらないかもしれない  
     機能とかかわらない領域の部分的な一致が非常に危険  

「嘘類似」の問題回避法は？  
   
   1. 配列類似検索の対象は、信頼できるライブラリから順に使う
     
     - UniProt/SwissProt, UniProt/TrEMBL: http://www.uniprot.org/
     - nr: (see. 2. BLAST Database Content)
     
   2. 配列類似検索以外の機能予測方法を用いる
   
     機能に関わるタンパク質の部分配列（モチーフやドメイン）  
     
     - InterPro: さまざまなタンパク質機能探索のための統合データベース  
       - http://www.ebi.ac.uk/interpro
    
   3. 注釈の「根拠 (evidence)」が明示できる方法で注釈する
   
   see: http://www.geneontology.org/ -> Documentation -> Annotation -> Guide to Evidence Codes  
  
     - IDA (Inferred from Direct Assay)
     - TAS (traceable author statement)
     - IEA (Inferred from Electronic Annotation)
     - ISS (Inferred from Sequence or Structural similarity) etc.
  　
  
###【実習】InterPro・GOで遺伝子機能のエビデンスを確認しよう ###

#### 1. InterProScan: http://www.ebi.ac.uk/interpro ####
  
   - モチーフ、プロファイル検索のまとめがけ、Gene Ontrogyにまで到達可能な優れたアミノ酸配列解析総合サイト  
```
>opsin Rh2(Drosophila melanogaster)
MERSHLPETPFDLAHSGPRFQAQSSGNGSVLDNVLPDMAHLVNPYWSRFAPMDPMMSKIL
GLFTLAIMIISCCGNGVVVYIFGGTKSLRTPANLLVLNLAFSDFCMMASQSPVMIINFYY
ETWVLGPLWCDIYAGCGSLFGCVSIWSMCMIAFDRYNVIVKGINGTPMTIKTSIMKILFI
WMMAVFWTVMPLIGWSAYVPEGNLTACSIDYMTRMWNPRSYLITYSLFVYYTPLFLICYS
YWFIIAAVAAHEKAMREQAKKMNVKSLRSSEDCDKSAEGKLAKVALTTISLWFMAWTPYL
VICYFGLFKIDGLTPLTTIWGATFAKTSAVYNPIVYGISHPKYRIVLKEKCPMCVFGNTD
EPKPDAPASDTETTSEADSKA
```
   1. googleの検索窓に「InterProScan」と入れて、googleで探し出す  
   2. Enter or paste a PROTEIN sequence in any supported format: の枠に上記の配列をコピペする (ctl-C then ctl-V)  
   3. 「Submit」をクリックしてジョブをスタート  
   4. この配列がもつモチーフ・プロファイルを確認しましょう（G_PROTEIN, 7tm, OPSIN, Visual pigments (opsins) retinal binding site, etc.）  
  　
   【発展】どのようなプログラムが使われているのか？それぞれの詳細について知っておきましょう  
  　
  
#### 2. GO: http://www.geneontology.org ####
  
   - 遺伝子機能注釈のための生物共通語彙を提供。evidence のレベルで絞り込むことができます
   
   【実習】生物の体内時計 (circadian clock) に関する遺伝子について検索してみましょう  
   1. circadian rhythm (GO:0007623) で検索  
   2. Search Directory から Genes and gene products を選択⇒circadian rhythm関係の遺伝子がリストされる
   3. 任意の遺伝子を選択  
   3. 左ペインの Evidence type を展開してそれぞれのアノテーションの根拠を確認してみよう  


## appendix: 時間があれば紹介 ##

#### DDBJ の NGS アーカイブと、解析パイプライン ####

   - NGS データアーカイブ: DDBJ SRA (DRA) http://trace.ddbj.nig.ac.jp/dra/

   SRA は NGS の生データアーカイブです。自分でデータ取得できなくても類縁生物との比較による SNP 発見や発現解析などは公開データを使って実施できる場合があります。  

   1. DRAsearch
     - DRAsearch を使って興味のある材料／方法論のデータを検索してみましょう。  
   【実習】DRAsearch を使って興味のある材料／方法論のデータを検索してみましょう
   
   SRA は NGS の生データアーカイブです。自分でデータ取得できなくても類縁生物との比較による SNP 発見や発現解析などは公開データを使って実施できる場合があります。  
   
     1. DRAsearch を開く  
     ⇒ http://trace.ddbj.nig.ac.jp/dra/ の上部タブから **Search**  
     1. Organism に生物種名を指定して StudyType を指定するか、キーワードに列挙して絞り込む  
     1. ここでは Keyword に **Arabidopsis Transcriptome alternative splicing** と入れて Search  
     ⇒ Keyword を **Mouse Transcriptome alternative splicing** などご自身の興味のあるもので検索してみてください  
     ⇒ Accession, Study, Run などの関係性は http://trace.ddbj.nig.ac.jp/dra/submission_e.html から Metadata を参照  
     1. FASTQ or SRA format のどちらかでのぞみのデータをダウンロードできます。  
   
   2. NGS の解析処理支援: DDBJ pipeline http://p.ddbj.nig.ac.jp/  
     - NGS の解析処理を支援するクラウド: DRA pipeline http://p.ddbj.nig.ac.jp/
   
     【デモ】右上の Login as “guest” から利用イメージをみてみましょう  
     
     1. https://p.ddbj.nig.ac.jp/ を開く（DDBJ pipeline で検索）  
     1. 右上の **Login as "guest"** でゲストログイン
     1. DRA000001 の DRX000001 にチェックを入れて **NEXT**
     1. **de novo Assembly** をチェック、**velvet** をチェック **NEXT**
     1. DRR000001 にチェック、**set as pair end** を選び **NEXT**
     1. オプションに変更なければ **NEXT**
     1. e-mail アドレスを入力し、右上の **RUN** (guest の場合は実行不可)  
     >See also: 統合TV「今日からはじめるDDBJ Read Annotation Pipeline」http://togotv.dbcls.jp/20100617.html  

   - スパコンくらい自分でガシガシつかえるよってひと＞「遺伝研」「スーパーコンピュータ」で検索。無料です！

#### 2. TogoAnnotation (旧 KazusaAnnotation) の活用 ####

   - ソーシャルブックマークによるゲノムアノテーション蓄積／改善／統合サイト。  
   5,830 報文から 66,787 遺伝子に関する 388,914 アノテーション (2015年7月23日現在) を収集  

   なぜこんなものをつくったのか?  
   - ゲノムの「アノテーション」が怪しい  
      アノテーションとは、遺伝子の場所や機能を推測した情報  
      アノテーションの改善が必要。しかしあまりに膨大  
   - 大勢の力を結集することが必要  
      そのための仕組みとして、ソーシャルブックマークを利用する  
      普通のブックマークはあなたのパソコンのなか、ソーシャルブックマークはネット上で共有するブックマーク  
   詳細は、googleで検索してみてください

   - どんな情報が入っているのか  
      - シアノバクテリア（酸素発生型光合成細菌）  
      - 根粒菌（細胞内共生型窒素固定最近）  
      - 高等植物（マメ科植物のミヤコグサ）  
   とくにかずさDNA研究所が世界で初めて全ゲノムを決定した独立栄養生物である *Synechocystis* PCC 6803 の論文はほぼ全部、入力されています。これはすごい！   

   【実習】TogoAnnotationの利用例  
   
     1. http://togo.annotation.jp/ を開いてみましょう  
     2. 酸素発生型光合成細菌の *Synechocystis* の光合成系IIの遺伝子psbA3のアノテーションを検索しましょう。右上の検索窓に「Synechocystis psbA3」と入れて「検索」を押します  
     3. sll1867 の赤い字でしめされた「? annotations」をクリックすると sll1867  遺伝子についたアノテーション（＝ブックマーク）が一覧されます。遺伝子シンボルの表記の揺れが人力で解消されていることに注目してください（psbA3, psbA, psbAIII, psba-3)  
     4. Pubmed ID (例えば 12228353） をクリックすると、その遺伝子に言及した論文の情報が表示されます。そこからPubmedに行くこともできます。  
     5. Section Table や Gene Index のなかの sll1867 をクリックすると、当該遺伝子のデータベース中の遺伝子特徴のサマリページが表示されます。そのページ中の Reference 欄に、この遺伝子に言及している全ての論文がマニュアルキュレーションされています。  

#### 3: ExPASy http://www.expasy.org/ ####
  
   - proteomics に関係したオリジナルツール＆他サイトへのリンクが豊富  
  　
   The ExPASy (Expert Protein Analysis System) proteomics server of the Swiss Institute of Bioinformatics (SIB) is dedicated to the analysis of protein sequences and structures as well as 2-D PAGE  
   - タンパク質の同定 (peptide mass fingerprint, pI, MW etc.): Aldente, TagIdent, MultiIdent, AACompIdent  
   - 翻訳後修飾や切断部位の推定: Findmod, FindPept, GlycoMod などなど、多数のツールを提供。

