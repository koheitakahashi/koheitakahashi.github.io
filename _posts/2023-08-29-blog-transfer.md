---
title: ブログを移転しました
date: 2023-08-30 09:00:00 +0900
categories: [よもやま話]
tags: [よもやま話, ポエム]
image:
  path: /assets/img/2023-08-29-blog-transfer/preview.png
  alt: ブログ移転のイメージ
---

# ブログを移転しました

元々、[このはてなブログ](https://nmp300.hatenablog.com)で個人ブログを運用していました。そして、自分が書いた文章をバージョン管理したいという動機から、ローカルファイルで記事を書き、その内容をはてなブログにコピペするという作業を続けていました。しかし、この方法が徐々に手間だと感じるようになり、GitHubにpushしたと同時に記事が公開される形にしたいと思い、今回ブログを移転しました。

新しいブログの構成は GitHub Pages + 静的サイトジェネレーター([Jekyll](https://jekyllrb.com/)) です。使用しているブログのテーマは、[chirpy](https://github.com/cotes2020/jekyll-theme-chirpy)です。これは GitHub の Repository Template として公開されていたので、ブログの公開まで非常にスムーズに進めることができました。

静的サイトジェネレーターには [Hugo(Golang)](https://github.com/gohugoio/hugo) や [Gatsby(JavaScript)](https://www.gatsbyjs.com/) などの選択肢がありましたが、私が仕事でRubyを使用しているため、トラブルシューティングがしやすいと考え、Ruby 製の Jekyll を選択しました。

最近は筆不精がちでしたが、今後は技術的、非技術的な内容を問わず、もっとアウトプットを増やしていきたいと思っています。この新しいブログで様々なことを気軽に書いていけたらと考えています。
