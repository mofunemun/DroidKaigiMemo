# Unleash the power of AndroidStudio

## AndroidStudio のバージョンによって動作が異なる

### UI ツール

- Flamingo
  - Flamingo 以降では使用している JDK がバージョンアップする
  - Flamingo 以前のプロジェクトが動かなくなる可能性がある
  - Mac に限り起動が速くなっている
- Electric Eel は AGP が 7.x 系なので 8 系は使えない
- Live Edit
  - G 以降では Live Edit が Composable に対応している
  - 再 compile の必要がない
  - 設定から弄れるので作ってみてね
- デバイスミラーリング
  - Hedgehog から
  - 実機に触らなくても OK!
- Compose MultiPreview templates
- Dynamic color Preview
  - Material3 の色合いをその場で確認できる！
- Compose Animation Preview
  - アニメーションのプレビューがサクサク！
  - 見積もりも楽になるよ
- Gradle Managed Devices
  - 自動 test を安定化することが出来るよ
  - Hedgehog から

### ビルドツール

- ElectricEel で高速化がなされた
- Build Analyzer がビルド速度に文句を言い始めるようになった
- 各バージョンで警告の内容/範囲が変わる
  - E ではダウンロードがビルド速度に影響しているかを知らせてくれる(何をキャッシュすべきか)
  - F では、ビルドにかかる時間を各カテゴリごとに図示してくれる(重いプロセス・プラグインは？)
  - G では依存関係のダウンロード時間を把握できる
- ビルドスクリプト
  - Groovy vs KTS
    - google の主張では Kotlin にしてほしいらしい
      - Kotlin の方が Lint などの恩恵を受けられる
  - Gradle Version Catalog 対応
    - マルチモジュールやプロジェクト関係を共有できる。
    - 読み込んでいるライブラリやプラグインのバージョンが予期せず上がることを防げる
    - H から安定版になった

### Inspect(品質)

- E 以降、LogCat が大幅に見やすくなっている
- F 以降では NetworkInspector がすべてのトラフィックを表示できる
  - 予め指定したリクエストを拾うことで、通信処理が行えていることを簡易的に確認できる
- App Quality Insights
  - E までは FireBase のクラッシュを見れるだけだった
  - F からは直接ノートが書ける
  - H からは Android Vitals に対応！クラッシュの期間・デバイスの絞り込みで検索できる
  - I からは git と連携し、クラッシュが発生するバージョンと現行バージョンの差分を表示してくれるように！
    - かなり利用要件はしんどいので、今後の開発方針を考える時に参考にしてね
- Compose のトレース対応
  - System Trace が Compose に対応。
    - recompose されている関数を探せる
    - H からはデバッガでブレークポイントで停めて引数を見れるので、不安定な関数を目視で確認できる
- 画面の構成変更に伴う test
  - Espresso の仮想デバイス上で検証可能
  - UI のアクション(コード 1 行 1 行)ごとに検査できるので test の正確性を向上できる

### まとめ

- Android Studio は 3 か月ごとにリリースサイクル
- 高速化や Studio Bot などの新機能が続々出てきている
- ツール導入による生産性向上と、学習コスト・複雑性を天秤にかけよう
- 新機能を見据えながら現在の開発環境を見直し、負債になるようなものがないか確認しよう。
- うまくエコシステムの中を泳ごう
