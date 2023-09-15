---
title: RubyMine の Terminal で fish と asdf を使ったときに遭遇したエラー
date: 2023-09-15 12:00:00 +0900
categories: [メモ]
tags: [RubyMine, fish, asdf, terminal, メモ]
---

# はじめに

RubyMine の Terminal で fish と asdf を使おうとしたら、以下のエラーになったので、その対処法を書きます。

```
/Applications/RubyMine.app/Contents/plugins/ruby/rb/terminal/asdf_starter.sh (line 1): Unsupported use of '='. In fish, please use 'set asdf_bin_root $(dirname $RUBY_VERSION_MANAGER_PATH)'.
asdf_bin_root=$(dirname $RUBY_VERSION_MANAGER_PATH)
^~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~^
from sourcing file /Applications/RubyMine.app/Contents/plugins/ruby/rb/terminal/asdf_starter.sh
        called on line 2 of file /Applications/RubyMine.app/Contents/plugins/terminal/shell-integrations/fish/fish-integration.fish
from sourcing file /Applications/RubyMine.app/Contents/plugins/terminal/shell-integrations/fish/fish-integration.fish
source: Error while reading file '/Applications/RubyMine.app/Contents/plugins/ruby/rb/terminal/asdf_starter.sh'
```

# 前提

- [RubyMine](https://www.jetbrains.com/ja-jp/ruby/) 2023.2.1
- [fish](https://fishshell.com/) 3.6.1
- [asdf](https://asdf-vm.com/) 0.12.0

# エラーが発生する条件

- RubyMine の Terminal で、fish を使うように変更
- RubyMine 上で `Ruby SDK and gems` で asdf を使うように指定
- RubyMine の Terminal を開いたときに、上記のエラーが発生

# 解決方法

エラー文に記載されている `/Applications/RubyMine.app/Contents/plugins/ruby/rb/terminal/asdf_starter.sh` を以下のように変更しました。

```diff
-asdf_bin_root=$(dirname $RUBY_VERSION_MANAGER_PATH)
+set asdf_bin_root $(dirname $RUBY_VERSION_MANAGER_PATH)
-source "$asdf_bin_root/../asdf.sh"
+source "$asdf_bin_root/../asdf.fish"
asdf shell ruby $RUBY_VERSION_MANAGER_DISTRIBUTION_ID
```

結局、`asdf_starter.sh` は fish の記法に従っていなかったため、エラーが発生していました。同じ理屈で `asdf.sh` ではなく、 `asdf.fish` を読み込むように変更する必要がありました。
