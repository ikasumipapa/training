# DDBJ のデータベースと検索・解析 #

国立遺伝学研究所  DDBJセンター  
中村保一
  
## 0. 自己紹介 ##

   49歳。DDBJ 7年目、こんな人です。  
     - http://charles.genes.nig.ac.jp/members/yn/  
     - http://twitter.com/yaskaz  
     - http://spysee.jp/中村保一/1034648/  
  　  
     京大→遺伝研→かずさ→遺伝研と「ゲノム」と「情報」を扱ってきています。  

## 1. DDBJ とはなにか ##

### An INSDC partner ###

   International Nucleotide Sequence Database Collaboration (INSDC): http://www.insdc.org/  
   - DDBJ (JP): http://www.ddbj.nig.ac.jp/
   - ENA (EU): http://www.ebi.ac.uk/ena/
   - GenBank (USA): http://www.ncbi.nlm.nih.gov/Genbank/

## 2. DDBJ のデータベース ##

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
   ⇒どんどんデータベースが増えている。何故？

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

## 3. DDBJ や NCBI などで生物系の情報検索 ##

#### ARSA, getentry, DRAsearch ####
  
   【実習】塩基配列情報へのアクセス  

   1. ARSA  
     - 高速なキーワードによる配列検索・取得
     
   【実習】ヒトのインターロイキン２の全長遺伝子を含む配列を検索しましょう  
   
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
   
   1. getentry
     - 高速な配列取得。配列の ID (accession number) がわかっているときはこちらをどうぞ  
     
     1. DDBJ getentry で検索、getentry を開く  
     2. ID: 窓に **M22005, M26062, D11086** と入力⇒検索  
       ⇒標準では DDBJ フォーマットでまとめて出力されます  
     3. 出力形式: **CDS アミノ酸配列 FASTA** を選んで検索  
       ⇒塩基配列の中から CDS (coding sequence) だけを翻訳した配列が表示される  
       ⇒連番の ID を取りたいときには **M22005-M22010** のように範囲指定できます    
   
   1. DRAsearch
     - DRAsearch を使って興味のある材料／方法論のデータを検索してみましょう。  
     
     SRA は NGS の生データアーカイブです。自分でデータ取得できなくても類縁生物との比較による SNP 発見や発現解析などは公開データを使って実施できる場合があります。  
     
     1. DRAsearch を開く  
     ⇒ http://trace.ddbj.nig.ac.jp/dra/ の上部タブから **Search**  
     1. Organism に生物種名を指定して StudyType を指定するか、キーワードに列挙して絞り込む  
     1. ここでは Keyword に **Arabidopsis Transcriptome alternative splicing** と入れて Search  
     ⇒ Keyword を **Mouse Transcriptome alternative splicing** などご自身の興味のあるもので検索してみてください  
     ⇒ Accession, Study, Run などの関係性は http://trace.ddbj.nig.ac.jp/dra/submission_e.html から Metadata を参照  
     1. FASTQ or SRA format のどちらかでのぞみのデータをダウンロードできます。  

#### GQuery http://www.ncbi.nlm.nih.gov/gquery ####

   - National Center for Biotechnology Information (NCBI)の、配列と論文に関連した情報を何でも引けるNCBIの生物系検索決定版
    
   【課題】NCBI でヒトのインターロイキン２の全長遺伝子を含む配列情報を検索しましょう  
  
   1. GQuery をひらき、眺める（大量のデータベースの複合体）
   2. interleukin-2 から検索スタート
   3. AND human を追加して絞ってみる (interleukin-2 AND human で検索)
   4. AND full length cDNA を追加 (interleukin-2 AND full length cDNA で検索)
   5. 左下あたりの「Nucleotide ? 件」を開いてみると、Mouse などがコンタミしてるので、右ペインの Top Organisms から Homo sapiens を選択  
   6. 検索結果を開き、それぞれのFeatures（特徴）とそこからのリンクを確認しよう。  
  　　  
   【応用】: Pubmed で同様に論文を検索しなさい。  
   【応用】: 右上の Sign in to NCBI からログインすると、どのようなすばらしいサービスが受けられるのかを確認しよう。まだ使ってない人は登録して他のラボメンバーに差をつけよう。  
  
#### GOLD: http://www.genomesonline.org ####

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

#### NCBI Taxonomy: http://www.ncbi.nlm.nih.gov/taxonomy ####

   - 生物分類と配列情報を関連させて調べたい場合にはここ。30万種以上の生物が網羅されています。分類体系は独自な場合もあるので注意   
   【実習】あなたが興味のある生物種のプロジェクトはないかNCBI Taxonomy で調べてみよう （例：Arabidopsis, cat, mouse, … あなたの研究対象／興味のある生物でどうぞ）  

   1. 生物名（common name ＝一般名 も可）で検索できます。  
   2. 右ペインの  Entrez records から、その生物種の NCBI のリソースにおさめられている DB を展開してみましょう（Nucleotide〜Genome, PopSet, GEO, SRA, BioProject, BioSample, BioSystems, …）  
   3. 下部の Lineage から類縁の生物種を展開してみましょう  
   4. 下スクロールして Genome Information, External Information Resources を確認しましょう。GOLD へはここからも行けますね。学名で引かなくて良いのでここから行く方が早そう  
  　　  
   See also: 統合TV「NCBI Taxonomy Browserを使って、生物分類と配列情報を関連させて調べる」 http://togotv.dbcls.jp/20090226.html

  　

## 4. DDBJ や NCBI で解析 ##

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
|:-----------:|:------------:|:------------:|:----------------------------------------------------------------------------|
| BLASTN      | 核酸配列     | 核酸配列     | 問い合わせ配列と類似の核酸配列を検索                                        |
| BLASTP      | aa配列       | aa配列       | 問い合わせ配列と類似のアミノ酸配列を検索                                    |
| BLASTX      | 核酸配列     | aa配列       | 問い合わせ核酸配列をアミノ酸に翻訳した配列で、類似のアミノ酸配列を検索      |
| TBLASTN     | aa配列       | 核酸配列     | アミノ酸配列を核酸配列のデータベースを翻訳したものと類似の配列を検索        |
| TBLASTX     | 核酸配列     | 核酸配列     | 問い合わせ核酸配列を翻訳したものを、核酸配列DBを翻訳したものとの類似を検索  |
| MEGABLAST   | 核酸配列     | 核酸配列     | 感度は落ちるが BLASTN より高速。大規模な検索の際に使うと良い                |

   1. DDBJ BLASTを体験しよう  
   
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
     
     1. http://ddbj.nig.ac.jp/blast/blastn?lang=ja を開く（DDBJ BLAST で検索）  
     1. 左のカラムから **blastp** を選択  
     1. **Query** 窓に上記配列をコピペする (cmd-C then cmd-V)  
     1. **Data Sets** には **UniProt (Swiss-Prot)** を選択（小さいが精度の高いDB）
     1. **Send to BLAST** ボタンをクリック ⇒ 暫し待て
     1. チェックを入れた配列で ClustalW によるマルチプルアラインメントを作成することができます  
     >結果が帰ってこない時には **Resurt viewer** に wabi_blast_2015-0717-1754-11-479-233186 を  
     BLAST Help もご一読ください: https://www.ddbj.nig.ac.jp/search/help/blasthelp-j.html  
     
   1. NCBI BLASTを体験しよう  
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
   
   2. NGS の解析処理支援: DDBJ pipeline http://p.ddbj.nig.ac.jp/  
    【デモ】右上の Login as “guest” から利用イメージをみてみましょう  
     
     1. https://p.ddbj.nig.ac.jp/ を開く（DDBJ pipeline で検索）  
     1. 右上の **Login as "guest"** でゲストログイン
     1. DRA000001 の DRX000001 にチェックを入れて **NEXT**
     1. **de novo Assembly** をチェック、**velvet** をチェック **NEXT**
     1. DRR000001 にチェック、**set as pair end** を選び **NEXT**
     1. オプションに変更なければ **NEXT**
     1. e-mail アドレスを入力し、右上の **RUN** (guest の場合は実行不可)  
     >See also: 統合TV「今日からはじめるDDBJ Read Annotation Pipeline」http://togotv.dbcls.jp/20100617.html  
   
   自分でコマンド入力してガシガシつかいたいよってかた＞申請の上、ご利用ください。無料です（今のところ）

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
  
   【課題】 あなたやあなたの知人の出版した論文のなかでこれまでに一番よく引用されているのはどれだろうか。またどんな論文からその論文が引用されているか  
  
   【課題】BLAST (basic local alignment search tool) の初出論文を引用している論文数は膨大なモノだと考えられるが、その数を調べ、また、引用している論文を列挙しなさい  
   【解答】basic local alignment search tool で検索し、引用元を確認  
  
   【応用】文献管理ソフトであるBibTeXやEndNoteに簡単に検索結果を取り込むためのリンクの設置が可能右上のメニューの「設定」からどうぞ。
    
   【応用】h-index ( http://ja.wikipedia.org/wiki/H%E6%8C%87%E6%95%B0 ) は学者の論文数と被引用数とに基づいて、科学者の科学的貢献度を示す指標です。google scholar を利用すると比較的簡単に h-index を出すことができます。引用の多い順に文献の検索結果がならんでいますので、被引用数が、リストの上からのカウントを上回ったらそのひとつ手前のカウントが h-index です。

------------------------------

#### OReFiL: an Online Resource Finder for Lifesciences http://orefil.dbcls.jp/ ####
  
   - ライフサイエンス分野の文献に記載されているウェブリソース(データベースやツールなど)を検索するならこれ
  
   【課題】 primerをアレコレするためのWWWサイトで、報告されているものに、どのようなものがあるだろうか？OReFiLで調べましょう  
   【課題】 codon usage をアレコレするためのWWWサイトで、報告されているものに、どのようなものがあるだろうか？OReFiLで調べましょう
  
    See also: 統合TV「OReFiLを使ってライフサイエンス分野のwebリソースを検索する」 http://togotv.dbcls.jp/20070831.html  

------------------------------

#### Allie: A Search Service for Abbreviation / Long Form http://allie.dbcls.jp/ja ####
  
   - 生命科学分野において利用されている略語とその展開形を検索するサービス
  
   文献中に多く出現する略語は多義語であることが多く、特に専門外の読者には理解するのに困難を伴うことがあります。Allieはこの問題に対する一つの解となるよう開発されています  
  
   【課題】 SPF という略語は生活や生物学研究のさまざまな場面で目にしますが、それらは何の略語で？Allieで調べましょう  
  
   See also: 統合TV「Allieを使って略語の正式名称を検索する」 http://togotv.dbcls.jp/20080522.html  

------------------------------

#### difff: 日本語対応で簡単に差分が確認できるテキスト比較ツール http://difff.jp ####
  
   - 論文や発表要旨を共同研究者が編集したとき、Word の履歴記録がオフになっていると、どこが変わっていたのかわからなくなったりします。difff はテキスト差分を簡単に確認できるツールです。コピペの発見もできちゃうからレポート提出時には要注意ですよ   
  
   【課題】 difff obokata で検索⇒コピペはイカンよ。  
  
   See also: 統合TV「difff《ﾃﾞｭﾌﾌ》を使って文章の変更箇所を調べる」 http://togotv.dbcls.jp/20130828.html  


## おわりに ##

   - JGI GOLD: https://gold.jgi-psf.org/

*end*
