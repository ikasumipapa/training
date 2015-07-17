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
   - DDBJ(JP): http://www.ddbj.nig.ac.jp/
   - ENA(EU): http://www.ebi.ac.uk/ena/
   - GenBank(USA): http://www.ncbi.nlm.nih.gov/Genbank/

## DDBJ のデータベース ##

   1. Trad  
   1. DDBJ SRA (DRA)  
   1. DDBJ Trace Archive  
   1. BioProject  
   1. BioSample  
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

   1. Trad
   
   1. DDBJ SRA (DRA)
   1. DDBJ Trace Archive
   
     - NGS データアーカイブ: DDBJ SRA (DRA) http://trace.ddbj.nig.ac.jp/dra/  
     
     SRA は NGS の生データアーカイブです。自分でデータ取得できなくても類縁生物との比較による SNP 発見や発現解析などは公開データを使って実施できる場合があります。  
     
     【実習】DRAsearch を使って興味のある材料／方法論のデータを検索してみましょう。SRA 単独を探す場合には NCBI よりも使いやすいという評判もありますよ
     
     - NGS の解析処理を支援するクラウド: DRA pipeline http://p.ddbj.nig.ac.jp/  
     
     【デモ】右上の Login as “guest” から利用イメージをみてみましょう  
     
     See also: 統合TV「今日からはじめるDDBJ Read Annotation Pipeline」http://togotv.dbcls.jp/20100617.html  
     
     - スパコンくらい自分でガシガシつかえるよってひと＞小笠原さんの講習をどうぞ。  
   
   1. BioProject  
     - DDBJ BioProject: http://trace.ddbj.nig.ac.jp/bioproject/  
     
   1. BioSample  
     - DDBJ BioSample: http://trace.ddbj.nig.ac.jp/biosample/  
  
## DDBJ で検索 ##

   1. ARSA  
   1. getentry  

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
  
## DDBJ で解析 ##

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
  　

   - DDBJ BLAST
     - http://blast.ddbj.nig.ac.jp/top-j.html
     

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
  
     BLAST検索のprogram option  

    | program     | Query        | DB           | 概要                                                                        |
    |:-----------:|:------------:|:-------------|:----------------------------------------------------------------------------|
    | BLASTN      | 核酸配列     | 核酸配列     | 問い合わせ配列と類似の核酸配列を検索                                        |
    | BLASTP      | アミノ酸配列 | アミノ酸配列 | 問い合わせ配列と類似のアミノ酸配列を検索                                    |
    | BLASTX      | 核酸配列     | アミノ酸配列 | 問い合わせ核酸配列をアミノ酸に翻訳した配列で、類似のアミノ酸配列を検索      |
    | TBLASTN     | アミノ酸配列 | 核酸配列     | アミノ酸配列を核酸配列のデータベースを翻訳したものと類似の配列を検索        |
    | TBLASTX     | 核酸配列     | 核酸配列     | 問い合わせ核酸配列を翻訳したものを、核酸配列DBを翻訳したものとの類似を検索  |
    | PSI-BLAST   | アミノ酸配列 | アミノ酸配列 | DBとの検索を繰り返すことで、弱い類似しかない配列を検索可能にする方法        |
    | PHI-BLAST   | アミノ酸配列 | アミノ酸配列 | 配列の「パターン」で類似の配列を検索する                                    |
  　
   【実習】BLASTあれこれ  
  
    DDBJ BLASTを体験しよう  
  
   1. http://ddbj.nig.ac.jp/blast/blastn?lang=ja を開く（DDBJ BLAST で検索）
   2. 左のカラムから「BLASTP」を選択
   3. 「Search」窓に以下の配列をコピペする (cmd-C then cmd-V)

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
  
   4. 「Choose Search Set」＞「Database」の「swissprot」を選択
   5. 左下の「BLAST」ボタンをクリック→実行
   6. まず「Conserved domains」が示される（BLASTの結果が帰って来た後でも「Graphic Summary」の「Show Conserved Domains」から閲覧可能）
   7. 「Conserved domains」画像中の「7tm_1」をクリック → Conserved Domain として「7tm_1[pfam00001], 7 transmembrane receptor (rhodopsin family)」が見いだされた（７回膜貫通型receptor）
   8. そろそろ結果が得られているはず。Graphic Summary, Descriptions を眺めてみよう。
   9. 下へスクロールして「Descriptions」へ
   10. 上から順に数本にチェック入れる
       1. Download – 手元にダウンロード
       2. GenPept – GenBank からの翻訳DBへ
       3. Graphics – グラフィクスでの配列比較
       4. AlignmentsDistance tree of results – 簡易的な系統樹が描ける。ざっくり観たいときに便利
       5. Multiple alignment – 選んだ配列でマルチプルアラインメントを実施
   11. 下へスクロールして「Alignments」へ
   12. アラインメントの右横にある Related Information を活用しよう
   13. Gene-associated gene details
   14. Map Viewer-aligned genomic context
   15. 結果上部のリンク「Edit and Resubmit」から生物種やキーワードでの検索結果のしぼりこみができます
       （例）「Choose Search Set」の「Organism」に「Homo sapiens (taxid:9606)」を入れて（Homo あたりまで入れれば補完候補が出る筈）ヒトの opsin を再検索してみましょう。  
   16. 右の Exclude をチェックすることで、特定の生物種（群）を除外することもできます。これ便利な
   17. 結果上部のリンク「Download」から結果の csvでのダウンロードができます＞Excel に読み込んで結果の保存や一致の length や % でのソートが可能
  　
   【応用】: PSI-BLASTを使うと、類似が低いが遠縁であるような配列を捕まえることもできます。上記の配列で実行してみましょう。統合TV本家: http://togotv.dbcls.jp/20071016.html (YouTube版: http://www.youtube.com/watch?v=iIufC3uNlEk ) を参照  
  
    *e-valueとは？*  
   E = Kmn^(e-λS)  
   そのライブラリで偶然に同じスコアでヒットする本数の期待値  
   ライブラリの大きさ／内容が違うと e-value は違うから単純には比較できないぞ。注意  
  　
