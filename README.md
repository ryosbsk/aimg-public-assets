# aimg-public-assets

aimg専用の公開画像asset配信repo。承認された画像の公開copyと、配信に必要な最小限の管理fileだけを置く。

## 配信

GitHub Pagesのsourceは `main` branchの `/(root)`。rootの `.nojekyll` により静的fileを配信する。
専用build toolchain、独自Actions workflow、package、独自domainは使用しない。

蓋画像の固定URL:

https://ryosbsk.github.io/aimg-public-assets/aimg-catalog-card/catalog-cover/63aa4922ec0ccc8459a4128aafbfc689a0cc89e8e1da578f18f74dc3386c099f.png

PNG: 1213 × 1296 pixel / 762,276 bytes
SHA-256: `63aa4922ec0ccc8459a4128aafbfc689a0cc89e8e1da578f18f74dc3386c099f`

## asset管理契約

- 制作正本からbyte一致する公開copyを配置する。このrepoのPNGを独立した編集正本にしない。
- file名はPNG全bytesのSHA-256。asset版はuserscriptのSemVerと独立させる。
- 同じ画像は同じURLを再利用する。変更時は新hashのPNGを追加し、既存hashのfileを上書き・削除しない。
- 可変alias、時刻query、branch名だけによる版識別は使用しない。
- private repoのsource、spec、保存値、調査証拠、認証情報は配置しない。
- copy・push・Pages設定はuserscriptのstandard buildへ組み込まない。

## 更新手順

1. 承認された制作正本のPNG形式・寸法・bytes・SHA-256を確認する。
2. 新hashのpathへ無加工でcopyし、制作正本とのbyte一致を確認する。
3. 配置対象だけをcommitして `main` へpushする。
4. Pages配信後、匿名HTTPS取得が成功し、制作正本とbytes・SHA-256・寸法が一致することを確認する。

userscriptの実装・配布・releaseはこのrepoの対象外。
