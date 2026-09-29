# VPS購買：料金だけで決めないための選び方とDMITの現行プラン比較

「VPS購買」と検索しているなら、探しているのは単に安いサーバーではないはずです。月額はいくらか、メモリは足りるか、通信量はどのくらい必要か、設置場所はどこにするか。そして何より、**安いプランを選んだのにネットワークが用途に合わない**という失敗を避けたいところです。

今回、2026年9月26日時点でDMITの公式Pricingページと各データセンターの現行ページを確認しました。DMITはCloud InstanceをKVMベースで提供し、Los Angeles、Hong Kong、Tokyoの3拠点を案内しています。ハードウェアはAMD EPYC系とNVMeストレージを使い、ネットワークはPremium、Eyeball、Tier 1に分けられています。

ただし、ここで大事なのは「DMITだから高性能」と一括りにしないことです。同じDMITでも、**拠点、ネットワーク系列、ハードウェア、在庫状態によって条件がかなり違います**。VPS購入では、この順番で見たほうが判断しやすくなります。

## VPS購入で先に決めるべき4つ

最初にCPUやRAMを見ると、プラン一覧の数字に引っ張られます。実際には、用途によって優先順位が変わります。

### 1. VPSを置く場所

WebサイトやAPIを日本中心で使うならTokyo、アジア圏や中国本土との接続を重視するならHong KongやLos Angelesが候補になります。DMITは現在、Los Angeles、Hong Kong、Tokyoをグローバル拠点として掲載しています。

Tokyoは中国本土向けPremium Networkで約28ms、Hong Kongは約15msという公式の参考値を掲げています。もちろん、これは特定地点からの参照値で、実際の遅延は利用回線、経路、時間帯で変わります。

日本国内の利用だけを考えているなら、こうした中国向けルーティング数値だけを見て決める必要はありません。逆に中国本土のユーザーが主要顧客なら、単純なCPU/RAM比較よりネットワーク系列の差のほうが重要になります。

### 2. CPUとRAM

小規模なWebサイト、開発環境、軽いAPIなら1〜2 vCore、1〜2GB RAMから始められるプランが現実的です。一方、複数のサービスを同時に動かすなら4GB以上を見たほうが余裕があります。

DMITのハードウェアは、公式説明ではAN5がAMD EPYC 9005、AN4がEPYC 9004、AS3がEPYC 7003系です。AN5はDDR5とNVMe Gen5、AN4はZen 4、AS3はZen 3という位置づけです。

### 3. 通信量

「10Gbps」と書かれているからといって、毎月の転送量が無制限という意味ではありません。

例えばLos AngelesのTier 1では、V2C2Gが2 vCore、2GB RAM、40GB SSD、最大5000GBのIN/OUT転送、10Gbpsで月額$14.90。V12C24Gでは12 vCore、24GB RAM、320GB SSD、最大160000GBのIN/OUT転送、10Gbpsで月額$199.90です。

帯域幅と転送量は別物です。動画、バックアップ、ミラー、ファイル配信などでは特にここを分けて計算してください。

### 4. ネットワーク系列

DMITは3つの考え方を明確に分けています。

Premium Networkは中国本土向けの低遅延・低損失ルートを重視し、China Telecom CN2 GIAなどを使います。Eyeball NetworkはCMIなどを含む中国向け経路とのバランス型、Tier 1は中国特化ルートを前提にせず、APAC・北米間の一般的な接続や大容量通信を重視する系列です。

つまり、**「高いプランほど正解」ではありません**。中国向け通信が不要なら、Tier 1を選ぶほうが目的に合うケースがあります。

## DMITの全套餐対比表

以下は、2026年9月26日に公式Pricingページおよび各拠点ページで確認できた現行表示を整理したものです。公式ページ自身が「製品と価格は調整により更新が遅れる場合がある」と注意書きを出しているため、最終注文画面では金額と在庫を再確認してください。

購入導線は、提示されたAFFリンクを使用しています。個別PIDを推測したdeeplinkは作成していません。

| 拠点・系列 | プランと構成 | 価格・周期 | 購入 |
| --- | --- | ---: | --- |
| Los Angeles 現行表示ブロックA | TINY 1vCore/2GB/20GB/1000GB/1Gbps、Pocket 2vCore/2GB/40GB/1500GB/4Gbps、STARTER 2vCore/2GB/80GB/3000GB/10Gbps、MINI 4vCore/4GB/80GB/5000GB/10Gbps、MICRO 4vCore/4GB/160GB/7000GB/10Gbps、MEDIUM 6vCore/8GB/160GB/15000GB/10Gbps | $10.90〜$199.90/月 | [ 現行LAXプランを確認する](https://bit.ly/DmiT) |
| Los Angeles 現行表示ブロックB | MINI 4vCore/4GB/80GB/5000GB/10Gbps、MICRO 4vCore/4GB/160GB/7000GB/10Gbps、MEDIUM 6vCore/8GB/160GB/15000GB/10Gbps、LARGE 8vCore/16GB/320GB/25000GB/10Gbps、GIANT 12vCore/24GB/640GB/50000GB/10Gbps | $72.90〜$929.90/月、**在庫なし表示** | [ 在庫状況を確認する](https://bit.ly/DmiT) |
| Los Angeles 現行表示ブロックC | MINI 4vCore/4GB/80GB/10000GB/10Gbps、MICRO 4vCore/4GB/160GB/14000GB/10Gbps、MEDIUM 6vCore/8GB/160GB/30000GB/10Gbps、LARGE 8vCore/16GB/320GB/50000GB/10Gbps、GIANT 12vCore/24GB/640GB/100000GB/10Gbps | $79.90〜$1009.90/月 | [ LAXの別構成を確認する](https://bit.ly/DmiT) |
| Los Angeles AS3系別表示 | TINY〜MEDIUM、1〜6 vCore、2〜8GB、20〜160GB SSD、1500〜30000GB、2〜10Gbps | $10.90〜$199.90/月 | [ LAX AS3系を確認する](https://bit.ly/DmiT) |
| Los Angeles AS3系在庫なし表示 | MINI〜GIANT、4〜12 vCore、4〜24GB、80〜640GB SSD、10000〜100000GB、10Gbps | $72.90〜$929.90/月、**在庫なし表示** | [ LAX在庫を確認する](https://bit.ly/DmiT) |
| Los Angeles AS3系現行表示 | MINI〜GIANT、4〜12 vCore、4〜24GB、80〜640GB SSD、10000〜100000GB、10Gbps | $79.90〜$1009.90/月 | [ LAX AS3プランを確認する](https://bit.ly/DmiT) |
| Los Angeles Tier 1 / LAX.AS3.T1 | WEE 1vCore/1GB/20GB/1000GB、TINY 1vCore/1GB/20GB/2000GB、STARTER 2vCore/2GB/40GB/4000GB、MINI 2vCore/4GB/80GB/8000GB、MICRO 4vCore/4GB/120GB/16000GB、いずれもIN/OUT最大 | WEE $36.90/年、TINY $6.90/月〜MICRO $32.90/月 | [ 低価格のLAX Tier 1を確認する](https://bit.ly/DmiT) |
| Los Angeles AN5 Tier 1 VOLUME | V2C2G 2vCore/2GB/40GB/5000GB、V2C4G 2vCore/4GB/80GB/10000GB、V4C4G 4vCore/4GB/120GB/20000GB、V4C8G 4vCore/8GB/160GB/40000GB、V8C16G 8vCore/16GB/240GB/80000GB、V12C24G 12vCore/24GB/320GB/160000GB。10Gbps | $14.90〜$199.90/月 | [ 大容量転送向けLAX VOLUMEを確認する](https://bit.ly/DmiT) |
| Los Angeles AN5 Tier 1 GENERAL | G2C4G 2vCore/4GB/80GB/4000GB、G4C8G 4vCore/8GB/160GB/8000GB、G8C16G 8vCore/16GB/320GB/12000GB、G12C24G 12vCore/24GB/480GB/最大240000GB、G16C32G 16vCore/32GB/640GB/最大320000GB。10Gbps | $16.90〜$199.90/月 | [ LAX GENERALを確認する](https://bit.ly/DmiT) |
| Hong Kong Premium | MINI 4vCore/4GB/80GB/1500GB、MICRO 4vCore/4GB/160GB/2000GB、MEDIUM 6vCore/8GB/160GB/2500GB、LARGE 8vCore/16GB/320GB/3000GB、GIANT 12vCore/24GB/640GB/6000GB。1Gbps | $149.90〜$759.90/月 | [ Hong Kong Premiumを確認する](https://bit.ly/DmiT) |
| Hong Kong Eyeball | TINY 1vCore/1GB/20GB/500GB、STARTER 1vCore/2GB/40GB/1000GB、MINI 2vCore/4GB/60GB/1500GB、MICRO 4vCore/4GB/80GB/2000GB、MEDIUM 4vCore/8GB/160GB/2500GB。1Gbps | $39.90〜$239.90/月 | [ Hong Kong Eyeballを確認する](https://bit.ly/DmiT) |
| Hong Kong 別表示ブロック | MINI〜GIANT、4〜12 vCore、4〜24GB、80〜640GB SSD、1500〜9000GB、1Gbps | $149.90〜$759.90/月 | [ Hong Kongの別構成を確認する](https://bit.ly/DmiT) |
| Hong Kong 別表示ブロック | TINY〜MEDIUM、1〜4 vCore、1〜8GB、20〜160GB SSD、800〜4000GB、1Gbps | $39.90〜$239.90/月 | [ Hong Kongの現行在庫を確認する](https://bit.ly/DmiT) |
| Hong Kong Tier 1 | WEE 1vCore/1GB/20GB/1000GB、TINY 1vCore/1GB/20GB/2000GB、STARTER 1vCore/2GB/40GB/4000GB、MINI 2vCore/2GB/60GB/8000GB、MICRO 4vCore/4GB/80GB/16000GB、MEDIUM 4vCore/8GB/160GB/32000GB、LARGE 8vCore/16GB/320GB/64000GB、GIANT 8vCore/24GB/640GB/128000GB。IN/OUT最大 | WEE $36.90/年、TINY $6.90/月〜GIANT $199.90/月 | [ 大容量転送向けHKG Tier 1を確認する](https://bit.ly/DmiT) |
| Tokyo Premium | TINY 1vCore/1GB/20GB/500GB、STARTER 1vCore/2GB/40GB/1000GB、MINI 2vCore/4GB/60GB/2000GB、MICRO 4vCore/4GB/80GB/4000GB、MEDIUM 4vCore/8GB/160GB/6000GB、LARGE 8vCore/16GB/320GB/8000GB、GIANT 8vCore/24GB/640GB/15000GB。1Gbps | $21.90〜$829.90/月 | [ Tokyo Premiumを確認する](https://bit.ly/DmiT) |
| Tokyo Tier 1 | WEE 1vCore/1GB/20GB/1000GB、TINY 1vCore/1GB/20GB/2000GB、STARTER 1vCore/2GB/40GB/4000GB、MINI 2vCore/2GB/60GB/8000GB、MICRO 4vCore/4GB/80GB/16000GB、MEDIUM 4vCore/8GB/160GB/32000GB、LARGE 8vCore/16GB/320GB/64000GB、GIANT 8vCore/24GB/640GB/128000GB。IN/OUT最大 | WEE $36.90/年、TINY $6.90/月〜GIANT $199.90/月 | [ Tokyo Tier 1を確認する](https://bit.ly/DmiT) |

公式ページでは、Los AngelesでAN5 Tier 1に「VOLUME」と「GENERAL」の2系統が明示されています。またHong KongではAN5がPremiumのみ、AS3がEyeballとTier 1に提供されると説明されています。

## どのプランからVPS購入を始めるか

価格だけを見るなら、Los Angeles Tier 1のTINYが月額$6.90、Tokyo Tier 1のTINYが月額$6.90、Hong Kong Tier 1のTINYも月額$6.90です。ただし、Tier 1は中国本土向けの特別なルーティングを目的にした系列ではありません。

この価格帯は、開発用、監視、CI/CD、軽い個人サービスなど「まずVPSを持ちたい」用途の検討対象になります。DMIT自身もTier 1をバックアップ、アーカイブ、CI/CD、DevOps、VPN・リレー、一般的なコンピュート用途として案内しています。

一方、メモリを増やしたいならLAX Tier 1のSTARTERは2 vCore、2GB RAM、40GB SSD、4000GBのIN/OUT最大で$12.90/月。MINIでは2 vCore、4GB RAM、60GB SSD、8000GBで$21.90/月です。

4GB RAMが欲しいからといって、いきなりPremiumへ行く必要はありません。日本や北米中心の通常用途なら、まずTier 1で必要性能を満たせるか考えたほうが比較しやすいでしょう。

## 中国本土向けなら「料金差」よりネットワークを見る

DMITを調べる人の中には、中国本土向けの接続品質を重視しているケースがあります。ここではPremium Networkの意味が出てきます。

Hong Kong Premiumは公式説明でCN2 GIAを使い、中国本土向け平均約15ms、パケットロス0.1%未満という参考値を掲載しています。Tokyo Premiumは約28ms、パケットロス0.1%未満という参考値です。いずれも特定地点からの計測値で、ユーザー環境の実測を保証する数字ではありません。

Los AngelesでもPremium NetworkはChina Telecom CN2 GIAなどを使う構成と説明され、Tier 1は中国向け最適化を持たない系列として区別されています。

ここはかなり重要です。たとえば同じ4GB RAMでも、Tier 1とPremiumをCPUやSSD容量だけで比較すると差を見誤ります。料金差は、単純な計算資源だけでなく**ネットワーク経路そのもの**に対して支払う部分があります。

## Los Angeles、Hong Kong、Tokyoの違い

### Los Angeles

Los AngelesはDMITの主要北米拠点で、公式にはCoreSiteとDigital Realtyをまたぐ構成、最大3.8TbpsのTier 1接続、China Telecom、China Unicom、China Mobile Internationalへの接続を案内しています。

米国側ユーザーとアジア側ユーザーをまたぐ構成、グローバルAPI、バックアップなどを考えるなら比較しやすい拠点です。Tier 1には月額$6.90のTINYから大型プランまであり、価格レンジも広めです。

ただし、公式ページには**LAX AS3シリーズはまだ構築・最適化中で、ディスク性能低下や成熟プラットフォームより低いSLAが発生する可能性がある**という明記があります。AS3を購入候補に入れるなら、この注意書きは見落とさないほうがいいでしょう。

### Hong Kong

Hong KongはEquinix HK2に置かれ、Premium Networkでは中国本土向けの低遅延を前面に出しています。一方、Eyeball NetworkはCMIなどを使った中間的な構成、Tier 1は中国特化を前提にしない国際接続向けです。

注意したいのは、**HKG Eyeballは現在Beta**と公式に明記されている点です。製品とルーティングは調整中で、パフォーマンスや経路が変わる可能性があり、高い安定性が必要な本番用途にはまだ推奨しないという説明があります。

安さだけでEyeballを選ぶ前に、これが用途に合うか確認してください。

### Tokyo

TokyoはEquinix TY8、品川のキャリアハブに設置されています。Premium NetworkとTier 1 Networkの2系列が現行ページで掲載され、Premiumは中国本土向け低遅延、Tier 1はAPAC・北米・欧州間の一般的な高帯域通信向けです。

日本国内の利用者から見ると、Tokyoは地理的な近さという意味で自然な候補です。ただし、最終的な応答速度はサーバー所在地だけで決まらず、アクセス回線と相手側ネットワークにも左右されます。

## DMITの評判はどう見るべきか

第三者評価は、公式の仕様表とは分けて見る必要があります。

TrustpilotのDMITプロフィールは現在4件のレビューで、表示されているTrustScoreは2.6/5です。そのうち3件が過去12か月のレビューで、掲載されている評価はすべて1つ星です。ただし、Trustpilot自身もこのプロフィールは未請求で、レビュー数が少なく、代表性を保証するものではないと説明しています。

2026年のレビューには、サポート対応、接続安定性、返金への不満を訴える投稿があります。これは「DMIT利用者全体がそう感じている」とまでは言えませんが、購入前に確認しておくべき具体的な不満事例ではあります。

逆に、公開されている技術情報では、DMITはAMD EPYC、NVMe、独自ネットワーク、複数Tier 1事業者との接続、そして中国向け専用ルートをかなり具体的に説明しています。

つまり、評判を一言でまとめるより、**「ネットワークやインフラ面で必要な条件」と「サポートに対するリスク」を別々に評価する**ほうが実用的です。

## 「安いVPSを買ったのに失敗した」を避けるチェック方法

購入ボタンを押す前に、最低限この順番で確認すると失敗しにくくなります。

1. **ユーザー所在地を決める**
   日本中心、北米中心、アジア中心、中国本土向けなど、実際のアクセス元を先に決めます。

2. **ネットワーク系列を決める**
   中国向け最適化が不要ならTier 1を候補にし、必要ならPremiumやEyeballを比較します。

3. **RAMを先に決める**
   CPUコア数だけではなく、常駐サービス数を考えて2GB、4GB、8GBのどこが必要かを決めます。

4. **月間転送量を見る**
   動画、バックアップ、大量ダウンロードではここがボトルネックになります。

5. **在庫を確認する**
   DMITのPricingページにはOut of Stock表示のプランも実際にあります。ページに表示されていても、注文できるとは限りません。

6. **購入前に最終価格をもう一度確認する**
   公式ページには、価格や製品表示が調整により最新状態でない場合があるとの注意書きがあります。

この順番なら「4GB RAMだからこれ」と決め打ちせず、必要な条件を削らずに予算を調整できます。

## 割引コードやキャンペーンはある？

ここは注意が必要です。

今回確認した現行の公式Pricingページと2026年の現行公開情報では、**誰でも今すぐ利用できる常設のVPS割引コードを確実に確認できませんでした**。一方、DMITの利用規約には、割引コードを随時発行すると明記されています。新規顧客向けのコードと、既存顧客向けの補償目的のコードを分けて扱う旨も記載されています。

そのため、「30%OFFコードがある」といった古いブログ記事の情報を、そのまま現在の価格として扱わないほうが安全です。実際、検索すると2023年、2024年、2025年のキャンペーンページが現在もインデックスされていますが、これらは過去イベントです。

現在の料金を確認したうえで、注文画面に有効なプロモーションが出ているかを見るのが確実です。

## 返金や利用制限も購入前に確認したい

DMITの現行規約では、前払いしたサービスを有効期限前にキャンセルしても、残りの前払い料金などについて返金しないという条項があります。つまり、年払いを安さだけで選ぶなら、途中解約時の扱いまで読んでから決めたほうがいいでしょう。

また、Acceptable Use Policyでは、無許可のポートスキャン、第三者の規約に反する自動購入ボット、商用目的の二次仮想化、最終製品の再販などが制限されています。用途が一般的なWebサイト、アプリ、開発環境なら問題になりにくい一方、特殊なネットワーク用途や再販用途では事前確認が必要です。

## 結局、どんな基準で選ぶ？

VPS購入でDMITを候補にするなら、考え方はかなりシンプルです。

**価格を優先する一般用途**なら、Los Angeles、Hong Kong、TokyoのTier 1から必要なRAMと転送量で選ぶ。

**アジアや中国本土への通信品質を重視する用途**なら、Premium Networkを中心に比較する。

**コストと中国向け通信の中間を狙う**なら、Hong KongのEyeballを確認する。ただし現状はBetaなので、安定性要件の高い本番環境では注意する。

そして、**CPU・RAM・SSDだけを横並びにしない**こと。DMITの場合、ネットワーク系列の違いが料金と用途の差につながるからです。

特に初めて買うなら、いきなり大型プランへ行くより、必要なRAMと転送量を見積もって小さい構成から始める考え方が分かりやすいです。逆に、業務系で中国本土との接続が収益やユーザー体験に直結するなら、安価なTier 1との価格差だけでPremiumを切り捨てるのも合理的ではありません。

最終的には「一番安いVPS」ではなく、**自分のアクセス元、必要RAM、月間転送量、ネットワーク経路、許容できる契約条件に合うプラン**を選ぶのがVPS購買の基本です。

まず現在の在庫と料金を確認するなら、提示されたAFF導線から一覧を見て、注文画面で最終条件を確認してください。

[👉 DMITの現行VPSプランと在庫を確認する](https://bit.ly/DmiT)
