#Jul2014 東京工業大学「バイオインフォマティクス」演習

国立遺伝学研究所  
中村保一 (July 16 / 23, 2014)  

この資料のURL→ http://bit.ly/yn15titech  

##イントロダクション

###自己紹介

49歳。木更津市／三島市二重生活中。  
こんな人です。  
http://charles.genes.nig.ac.jp/members/yn/  
http://twitter.com/yaskaz  
http://spysee.jp/中村保一/1034648/  
京大→遺伝研→かずさ→遺伝研と「ゲノム」と「情報」を扱ってきています。  

###情報リテラシー再入門

google

ま、とにかく、まずは「ググれ」www.google.co.jp

google の原理
「ロボット」が収集にやってくる（以下はこのサーバのアクセスログにあったgooglebotの痕跡）
    crawl-66-249-65-51.googlebot.com - - [24/Dec/2006:14:39:41 +0900] "GET /~yn/jp/?plugin=attach&pcmd=open&file=logo_jp.png&refer=LogoMark HTTP/1.1" 200 86078
    crawl-66-249-65-51.googlebot.com - - [24/Dec/2006:15:21:12 +0900] "GET /~yn/jp/?plugin=attach&pcmd=open&file=LogoAndMark_mono.png&refer=LogoMark HTTP/1.1" 200 73543
    crawl-66-249-65-51.googlebot.com - - [24/Dec/2006:15:27:35 +0900] "GET /~yn/jp/?cmd=backup&page=seikawakate2005 HTTP/1.1" 200 6828
    crawl-66-249-65-51.googlebot.com - - [24/Dec/2006:16:02:38 +0900] "GET /~yn/jp/?plugin=attach&pcmd=open&file=sample_namecard.ppt&refer=LogoMark HTTP/1.1" 200 278528
    crawl-66-249-65-51.googlebot.com - - [24/Dec/2006:16:06:19 +0900] "GET /~yn/jp/?Publications HTTP/1.1" 200 53032
    crawl-66-249-65-51.googlebot.com - - [24/Dec/2006:16:44:21 +0900] "GET /~yn/jp/?plugin=attach&pcmd=open&file=arc.jpg&refer=BusTable HTTP/1.1" 200 70808
    ...

「どこからもリンクのないページ」は原理的に探索不可能  
どこかからリンクがあれば、いつかはやってくる  
更新頻度が高いほど、google で上位にやってくる（blog とかが上位に来がちという問題）  

ダブルコーテーションの活用  
課題：ダブルコーテーションありなしに注意しつつ、以下の検索結果の「件数」とその内容を比較しましょう。  
すずかけ台駅 約 856,000 件
"すずかけ台駅" 約 289,000 件
論文の題名の一部または全部でググる
結構pdfがひっかかってきたりする。scholar （後述）へのリンクがトップにでてくる場合がありますね。
検索例：
Arabidopsis kinase
Synechocystis sensory
遺伝子のアクセッション番号や遺伝子名そのものでググる これが意外に使える。論文のサプリメントファイルが拾えたりする場合も。
検索例:
sll1234
英文、とくに前置詞の使い方がただしいかどうか、ググる
検索例:
Study on
Study in
Study of
一歩すすんだ検索

OR検索 googleは「AND検索」つまり、キーワード全てを含む結果を行います。
キーワードの一部を含んでいればいい場合=「OR検索」には文字通り「OR」を使います。
【課題】以下の検索の意味と、検索結果（特に右上の検索結果数) を比較しましょう。どのように違いますか？
Mus musculus domesticus
Mus musculus OR domesticus
【解答】上：３つのキーワードが全部入っているページを検索、下：Musに加え、musculus か domesticus のどちらかが記載されているページ
【課題】以下はそれぞれ、どのような検索をしていることになるのでしょうか。その結果は？
Mus OR musculus OR domesticus
"Mus musculus" OR "Mus domesticus"
【解答】上：Mus, musculus, domesticus のどれかのキーワードがあれば良い、下：「Mus musculus」もしくは「Mus domesticus」のどちらかがあれば良い
* ワイルドカードを使う
なにが挟まっていても良いことを示す記号。トランプで言うと「ジョーカー」みたいなものです。
【課題】以下の検索を実行しましょう
vitamin * is good for *
.. 一定の数値範囲を指定
【課題】以下の検索を実行しましょう
Arabidopsis 2001..2006
− (マイナス) 特定のキーワードを除外
【課題】以下の検索結果数、内容を比較してみる
東工大
東工大 -東京工業大学
filetype の活用【これ有用！】
filetype:ppt, filetype:pdf, filetype.doc, filetype:xls, filetype:txt, filetype:html
ファイルタイプ指定 (PowerPoint, PDF, Word書類, Excel書類, text, html)
【課題】以下の検索を実行しましょう
blast filetype:ppt
mouse filetype:xls
site: 特定のサイトで検索
【課題】それぞれ何を検索しようとしているかを考え、実際に検索してみて、検索数の違いを比較しましょう
東京工業大学
東京工業大学 site:titech.ac.jp
東京工業大学 -site:titech.ac.jp
【課題】癌の研究に関係するPDFとパワポファイルを文部科学省のサイトで探しなさい
【解答】癌 研究 site:mext.go.jp filetype:pdf OR filetype:ppt
link: 特定のサイトへのリンクがあるページ
【課題】東工大のトップページへのリンクがあるページを検索しよう
link:www.titech.ac.jp
電卓・通貨 http://www.google.com/intl/ja/help/features.html#calculator
ちょっと便利だったりする。乗算はアスタリスク、アスタリスクが２つでべき乗
【課題】以下を計算するにはどうしますか？
3×2
3の2乗
【解答】上：3*2　下 3**2 （3^2　でも可)
【課題】「8ルート3」の結果は何が得られると思いますか?
【解答】8 かける ルート３の結果ですね
【課題】「8の3乗根」を求める方法は？
【解答】3rd root of 8　どうやら日本語の表記法は無いようです
【参考】1000円を米ドルに
【参考】10億リットルを東京ドームで
ま、そんなgoogleの便利な利用法についてはこちらを参照 http://support.google.com/websearch/

 

… だいぶお遊びが過ぎたので学術系にもどろう

 

学術系論文等情報検索

1. PubMed: http://pubmed.gov

泣く子も黙るNational Center for Biotechnology Information (NCBI) 提供の学術論文検索の総本山

E. coli O111のゲノム関連論文を探してみよう
検索窓に E. coli と入れてGoをクリック ⇒ Results: 1 to 20 of “331745” こんなに大腸菌論文がある
O111 を追加して「E. coli O111」で絞り込み検索する ⇒ 941 報まで絞り込まれる
さらにgenome を追加して「E. coli O111 genome」で検索  ⇒ 109 報まで絞り込まれる
実際にどのようなタームに展開されて検索されているかは右カラムの「Datails」に表示されている (… MeSHってなんだ？＞ただちにぐぐろう）
より一層の絞り込みは上部のAdvancedから指定できる。たとえば「Title/Abstract」や「Author」「Publication Date」を指定するなどして絞りこめる
【課題】 猫アレルギーの人が猫を飼うための猫洗いのテクニックを記述した学術論文を検索しなさい。(ヒント: wash allergy)
【解答】 cat wash allergy で検索し「Evaluation of different techniques for washing cats: quantitation of allergen removed from the cat and the effect on airborne Fel d 1.」に至る。１週間に１度、３分間お湯につけるのを２回繰り返すとよい
【応用】: RSS feedを使って、定点観測するには
本家統合TV: http://togotv.dbcls.jp/20070920.html (YouTube版: http://www.youtube.com/watch?v=5K8-xnkcClo ) を参照
【応用】: PubMedに収録されているすべての論文数を知りたい場合には？
本家: http://togotv.dbcls.jp/20071213.html (YouTube版: http://www.youtube.com/watch?v=Or5QeVMlzMQ ) を参照 (All[filter] で検索)
2. Google Scholar

学術系のgoogle検索: http://scholar.google.com

学術専門誌、論文、書籍、要約など、さまざまな分野の学術資料を検索。ISIと契約するお金がなくても、論文引用数の概数を知ることは可能。たとえば、NAKAMURA Yasukazu. さんの発表論文や講演要旨をさがしてみよう。
author:yasukazu-nakamura
【課題】 あなたの論文、あるいはあなたの指導教員の出版した論文のなかでこれまでに一番よく引用されているのはどれだろうか。またどんな論文からその論文が引用されているか
【課題】 BLAST ( basic local alignment search tool ) の初出論文を引用している論文数は膨大なモノだと考えられるが、その数を調べ、また、引用している論文を列挙しなさい
【解答】basic local alignment search tool で検索し、引用元を確認
【応用】文献管理ソフトであるBibTeXやEndNoteに簡単に検索結果を取り込むためのリンクの設置が可能「Scholar設定」からどうぞ
h-index (http://ja.wikipedia.org/wiki/H%E6%8C%87%E6%95%B0) は学者の論文数と被引用数とに基づいて、科学者の科学的貢献度を示す指標です。google scholar を利用すると比較的簡単に h-index を出すことができます。引用の多い順に文献の検索結果がならんでいますので、被引用数が、リストの上からのカウントを上回ったらそのひとつ手前のカウントが h-index です。あなたのまわりのセンセイ方の戦闘能力を数値で定量比較してみよう。いっひっひ。
3. OReFiL: an Online Resource Finder for Lifesciences

ライフサイエンス分野の文献に記載されているウェブリソース(データベースやツールなど)を検索するならこれ: http://orefil.dbcls.jp/

【課題】 primerをアレコレするためのWWWサイトで、報告されているものに、どのようなものがあるだろうか？OReFiLで調べなさい
【課題】 codon usage をアレコレするためのWWWサイトで、報告されているものに、どのようなものがあるだろうか？OReFiLで調べなさい
See also: 統合TV「OReFiLを使ってライフサイエンス分野のwebリソースを検索する」 http://togotv.dbcls.jp/20070831.html

4. Allie: A Search Service for Abbreviation / Long Form

生命科学分野において利用されている略語とその展開形を検索するサービスです。 文献中に多く出現する略語は多義語であることが多く、特に専門外の読者には理解するのに困難を伴うことがあります。Allieはこの問題に対する一つの解となるよう開発されています http://allie.dbcls.jp/ja

【課題】 SPF という略語は生活や生物学研究のさまざまな場面で目にしますが、それらは何の略語で？Allieで調べなさい
See also: 統合TV「Allieを使って略語の正式名称を検索する」 http://togotv.dbcls.jp/20080522.html

5. difff: 日本語対応で簡単に差分が確認できるテキスト比較ツール

論文や発表要旨を先生になおしてもらったときに、Word の履歴記録がオフになっていると、どこが変わっていたのかわからなくなったりします。difff はテキスト差分を簡単に確認できるツールです。コピペの発見もできちゃうからレポート提出時には要注意ですよ http://difff.jp

【課題】 difff obokata で検索⇒コピペはイカンよ。
See also: 統合TV「difff《ﾃﾞｭﾌﾌ》を使って文章の変更箇所を調べる」 http://togotv.dbcls.jp/20130828.html

