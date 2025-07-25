# genome_Cpa

## Cladonema pacificumのhap1に対するgene model生成の結果

### JBrowseへのリンク↓
[https://junichiro-ui.github.io/genome_Cpa/](https://junichiro-ui.github.io/genome_Cpa/)

### トラックの説明
#### gene modelのトラック
gene modelはbraker3で生成した。
| track name | RNAseq | Isoseq | Nematostella+Hydra proteome | Clytia proteome | Metazoa proteome |
|---------|---------|---------|---------|---------|---------|
| braker_rnaseq | + | - | - | - | - |
| braker_rnaseq_isoseq | + | + | - | - | - |
| braker_rnaseq_protein | + | - | + | - | - |
| braker_rnaseq_isoseq_protein | + | + | + | - | - |
| braker_rnaseq_protein-clytia | + | - | + | + | - |
| braker_rnaseq_isoseq_protein-clytia | + | + | + | + | - |
| braker_rnaseq_protein-metazoa | + | - | - | - | + |
| braker_rnaseq_isoseq_protein-metazoa | + | + | - | - | + |

- RNAseqデータは谷本先生、竹田先生、中嶋Gのデータをまとめたものを使用
- 中嶋Gが持つisoseqデータは3'末端付近の短い断片が多くフルレングスが少なかった。信頼性には疑問もあるため、信頼性スコアは100（中程度？）で使用。
- Nematostella vectensisのproteomeは[こちら](https://simrbase.stowers.org/starletseaanemone)からダウンロードした。
- Hydra vulgaris (AEP strain)のproteomeは[こちら](https://research.nhgri.nih.gov/HydraAEP/download/index.cgi?dl=pm)からダウンロードした。
- Clytia hemisphaericaのproteomeは[こちら](http://marimba.obs-vlfr.fr/downloads/)からダウンロードした。
- Metazoaのproteomeは[OrthoDB12](https://bioinf.uni-greifswald.de/bioinf/partitioned_odb12/)からダウンロードした。

高品質なゲノムアセンブリがありCladonema pacificumに近縁であるNematostellaとHydraのみを使用することでgene modelが向上するのか、それともこれら2種よりさらにCladonema pacificumに近縁であるClytiaを追加することでgene modelが向上するのか、それともBraker3の推奨通りmetazoaのレファレンスを用いた方がgene modelが向上するのか、を調べたいというモチベーションで、これら複数のproteomeの組み合わせを使用した。

#### miniprotのトラック
以下のproteomeをhap1に対してminiprotでアラインメントした。
- Hydra miniprot
- Nematostella miniprot
- Clytia miniprot
- Hydractinia miniprot

Nematostellaのminiprotに関してのみ、uniprotへのblast best hitが利用できたので、そちらを紐付けてある。
検索フォルダに例えばCASP3などと入力すると、このnematostellaのblast best hitの名前がヒットすることで対応するであろうCladonemaの遺伝子がわかるようになっている。


### 注意点
Repeatmaskerトラックは、githubには容量の関係上アップロードできなかったので、チェックを入れても表示できない（自分が持っているローカルのJBrowseには存在する）。
RNAseq coverageトラックも同様。
