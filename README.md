# koheitakahashi.github.io

https://blog.koheitakahashi.com/ のソースコード。
https://github.com/cotes2020/chirpy-starter を利用してリポジトリを作成した。

## ローカルでの起動

Ruby のバージョンは `.tool-versions` で指定し、CI でも同じバージョンを使う。Chirpy 7.6 の対応範囲に合わせて Ruby 3.4 系を使っている。

```sh
asdf install
bundle config set --local path vendor/bundle
bundle install
bundle exec jekyll serve
```

## ビルドと検証

```sh
JEKYLL_ENV=production bundle exec jekyll build
bundle exec htmlproofer _site --disable-external
```

`Gemfile.lock` で依存 gem のバージョンを固定する。更新するときは `bundle update` を実行し、ビルドと検証を通してから lockfile も変更に含める。
