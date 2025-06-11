
## 出典
This directory was created with reference to [arxiv-style](https://github.com/kourgeorge/arxiv-style) (MIT License).

このディレクトリは [arxiv-style](https://github.com/kourgeorge/arxiv-style)（MITライセンス）を参考に作成されました。

## 説明

このプロジェクトは、arXiv、techrXhiv、biorXiv などの「プレプリント」公開に適した、美しくシンプルな LaTeX スタイルを提供します。  
[**nips_2018.sty**](https://media.nips.cc/Conferences/NIPS2018/Styles/nips_2018.sty) スタイルをベースにしています。

NeurIPS の美学を維持しつつ、プレプリントにより適した機能追加や変更を行っています。  
その結果、NeurIPS スタイルとはかなり異なる見た目となり、読者がプレプリントを NeurIPS 掲載論文と誤解することはありません。

### なぜ NeurIPS なのか？
NeurIPS のスタイルは、読みやすく美しいシングルカラム形式で、とても快適だからです。

## 使い方
1. ドキュメントクラスは **article** を使用してください。
2. **arxiv.sty** を TeX ファイルと同じフォルダにコピーします。
3. `\documentclass{article}` の後に `\usepackage{arxiv}` を追加します。
4. スタイルファイルで使用しているパッケージは **geometry** と **fancyheader** のみです。これらを再度インポートしないでください。

**template.tex** を参照してください。

## プロジェクトファイル
1. **arxiv.sty** - スタイルファイル
2. **template.tex** - **arxiv スタイル**を利用したサンプルテンプレート
3. **references.bib** - template.tex 用の参考文献ファイル
4. **template.pdf** - arxiv スタイルのデザインを示すテンプレートのサンプル出力

## arXiv.org への投稿時の参考文献の扱い
参考文献は外部の BibTeX ファイルを使って管理するのが便利です。  
ただし、これは [bibtex](http://www.bibtex.org/) ツールを使って `.bib` ファイルを「コンパイル」し、`.bbl` ファイル（bibitem 群）を生成し、これをメインの TeX ファイルに直接挿入する必要があります。  
しかし arXiv の TeX 環境（[Tex Live](https://www.tug.org/texlive/)）では自動的にこれが行われません。  
そのため、arXiv へ投稿する際は、参考文献を含む単一の自己完結型 .tex ファイルを作成するのが最も簡単です。  
自分のマシンで BibTeX コマンドを実行し、生成された `.bbl` ファイルの内容を `.tex` ファイルの `\begin{thebibliography}` の部分に挿入し、外部参照ファイルを指定する `\bibliography{references}` をコメントアウトしてください。

プロジェクトフォルダで以下のコマンドを実行します:
1. `$ latex template` を実行
2. `$ bibtex template` を実行
3. `template.bbl` ファイルが生成されていることを確認
4. `template.bbl` の内容を `template.tex` の `\begin{thebibliography}` の部分にコピー
5. `template.tex` の `\bibliography{references}` コマンドをコメントアウト
6. これで arXiv.org への投稿準備が完了です


