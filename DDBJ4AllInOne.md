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


## 3. DDBJ で検索 ##

   ARSA, getentry, DRAsearch
  
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

## 4. DDBJ で解析 ##

DDBJ BLAST と DDBJ pipeline の紹介

### 配列の類似検索 (BLAST) ###

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
   
   自分でコマンド入力してガシガシつかいたいよって方＞小笠原さんの講習をどうぞ！  

## おわりに ##

   - JGI GOLD: https://gold.jgi-psf.org/

*end*
