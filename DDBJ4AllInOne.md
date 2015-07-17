# DDBJ のデータベースと検索・解析 #

国立遺伝学研究所  DDBJセンター
中村保一
  
### 自己紹介 ###

   49歳。こんな人です。  
     - http://charles.genes.nig.ac.jp/members/yn/  
     - http://twitter.com/yaskaz  
     - http://spysee.jp/中村保一/1034648/  
  　  
     京大→遺伝研→かずさ→遺伝研と「ゲノム」と「情報」を扱ってきています。  

------------------------------

## DDBJ とはなにか ##

### INSDC: International Nucleotide Sequence Database Collaboration ###

http://www.insdc.org/  
   - DDBJ (JP): http://www.ddbj.nig.ac.jp/
   - ENA (EU): http://www.ebi.ac.uk/ena/
   - GenBank (USA): http://www.ncbi.nlm.nih.gov/Genbank/

## DDBJ のデータベース ##

   1. Trad  
   1. DDBJ SRA (DRA)  
   1. DDBJ Trace Archive  
   1. BioProject  
     - DDBJ BioProject: http://trace.ddbj.nig.ac.jp/bioproject/  
   1. BioSample  
     - DDBJ BioSample: http://trace.ddbj.nig.ac.jp/biosample/  
   1. JGA  
   どんどんデータベースが増えている。何故か？

### シークエンシングテクノロジの進歩 ###

#### 蛍光によるdideoxy法（サンガー法） ####

   - Polymerase Chain Reaction (PCP)
     - http://www.youtube.com/watch?v=QaWLJVGEFi8 (youtube)
   - Sanger Sequencing (dideoxy method)
     - http://www.youtube.com/watch?v=oYpllbI0qF8 (youtube)
     - http://www.youtube.com/watch?v=6ldtdWjDwes (youtube)
  
#### New Generation Sequencer (NGS) ####

   - illumina Genome Analyser
     - http://www.youtube.com/watch?v=77r5p8IBwJk (youtube)
  
     1. フラットな固層上に適当な間隔でDNAを1分子ずつ固定、基盤上で「ブリッジPCR」を行い、スポットとしてDNAを増幅  
     2. 相補鎖合成を行いながら、4つの塩基に別々の蛍光標識をつけておいて、結合した塩基の場所をスポットの光として特定し、塩基配列を解読していく。  

------------------------------

## DDBJ で検索 ##

   ARSA と getentry  
  
   【実習】塩基配列情報へのアクセス  

   1. ARSA  
   
     - きわめて高速。キーワードによる配列検索
     
     1. DDBJ ARSA で検索、ARSA を開く
     2. interleukin-2 から検索スタート
     3. AND human を追加して絞ってみる (interleukin-2 AND human で検索)
     4. AND full length cDNA を追加 (interleukin-2 AND full length cDNA で検索)
       検索結果を開き、それぞれのFeatures（特徴）を確認しよう。  

   1. getentry
   
   - きわめて高速な配列取得
     
     1. DDBJ ARSA で検索、ARSA を開く
     2. interleukin-2 から検索スタート
     3. AND human を追加して絞ってみる (interleukin-2 AND human で検索)
     4. AND full length cDNA を追加 (interleukin-2 AND full length cDNA で検索)

   1. DRAsearch
   
     - NGS データアーカイブ: DDBJ SRA (DRA) http://trace.ddbj.nig.ac.jp/dra/  
     
     SRA は NGS の生データアーカイブです。自分でデータ取得できなくても類縁生物との比較による SNP 発見や発現解析などは公開データを使って実施できる場合があります。  
     
     【実習】DRAsearch を使って興味のある材料／方法論のデータを検索してみましょう。SRA 単独を探す場合には NCBI よりも使いやすいという評判もありますよ

## DDBJ で解析 ##

DDBJ BLAST と DDBJ pipeline の紹介

### 配列の類似検索 (BLAST) ###

#### DNA→RNA→タンパク質の情報の流れ ####

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
  
   |code1 | code3 | アミノ酸(E)   | アミノ酸(J)      |
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
  　
     1. 配列の比較・検索＝アラインメント
     2. アミノ酸配列のアラインメント
     「マトリクス」＝類似の程度を示す
       - PAM250
       - BLOSUM62
     3. ダイナミックプログラミング = DP
  
     「最適経路中の部分経路もまた最適経路になっている」  
     動的計画法は、この原理を利用して最適化問題を解く。  
     ある問題を、多段階に「バラす」ことができる場合、動的計画法によって各段階の最適解(経路)を求め、それをたどることで、全体の問題を解くことが可能になる。  
     まじめにDPやるとタイヘンなんで、はしょる  
  
   - FASTA
     - よく似た領域の周囲だけをDPで探索
   - BLAST
     - 「ワード」の一致を発見・そこからアラインメントを横へ延ばす・きわめて高速・巨大配列も探索可能
  
     BLAST検索のprogram options  
   
    | program     | Query        | DB           | 概要                                                                        |
    |:-----------:|:------------:|:-------------|:----------------------------------------------------------------------------|
    | BLASTN      | 核酸配列     | 核酸配列     | 問い合わせ配列と類似の核酸配列を検索                                        |
    | BLASTP      | アミノ酸配列 | アミノ酸配列 | 問い合わせ配列と類似のアミノ酸配列を検索                                    |
    | BLASTX      | 核酸配列     | アミノ酸配列 | 問い合わせ核酸配列をアミノ酸に翻訳した配列で、類似のアミノ酸配列を検索      |
    | TBLASTN     | アミノ酸配列 | 核酸配列     | アミノ酸配列を核酸配列のデータベースを翻訳したものと類似の配列を検索        |
    | TBLASTX     | 核酸配列     | 核酸配列     | 問い合わせ核酸配列を翻訳したものを、核酸配列DBを翻訳したものとの類似を検索  |
    | PSI-BLAST   | アミノ酸配列 | アミノ酸配列 | DBとの検索を繰り返すことで、弱い類似しかない配列を検索可能にする方法        |
    | PHI-BLAST   | アミノ酸配列 | アミノ酸配列 | 配列の「パターン」で類似の配列を検索する                                    |
   　


   1. DDBJ BLASTを体験しよう  

     1. http://ddbj.nig.ac.jp/blast/blastn?lang=ja を開く（DDBJ BLAST で検索）
     1. 左のカラムから「BLASTP」を選択
     1. 「Search」窓に以下の配列をコピペする (cmd-C then cmd-V)

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
  
     1. 「Choose Search Set」＞「Database」の「swissprot」を選択
     1. 左下の「BLAST」ボタンをクリック→実行
     1. そろそろ結果が得られているはず。Graphic Summary, Descriptions を眺めてみよう。
     1. 下へスクロールして「Alignments」へ
  　
   【応用】: PSI-BLASTを使うと、類似が低いが遠縁であるような配列を捕まえることもできます。上記の配列で実行してみましょう。統合TV本家: http://togotv.dbcls.jp/20071016.html (YouTube版: http://www.youtube.com/watch?v=iIufC3uNlEk ) を参照  
  
   *e-valueとは？*  
     E = Kmn^(e-λS)  
     そのライブラリで偶然に同じスコアでヒットする本数の期待値  
     ライブラリの大きさ／内容が違うと e-value は違うから単純には比較できないぞ。注意  

   2. NGS の解析処理支援: DDBJ pipeline http://p.ddbj.nig.ac.jp/  
     
     【デモ】右上の Login as “guest” から利用イメージをみてみましょう  
     
     See also: 統合TV「今日からはじめるDDBJ Read Annotation Pipeline」http://togotv.dbcls.jp/20100617.html  
     
     - 自分でコマンド入れてガシガシつかえるよってひと＞小笠原さんの講習をどうぞ。  

[end]
