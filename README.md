# CMake-docs-ja
CMakeドキュメントの日本語翻訳
## POファイル生成
```
$ git clone git@github.com:Kitware/CMake.git
$ cmake -B build-pot/conf -S CMake/Utilities/Sphinx -DSPHINX_HTML=ON
$ sphinx-build -b gettext -c build-pot/conf -D gettext_compact=0 Cmake/Help build-pot/gettext
$ sphinx-intl update -p build-pot/gettext -l ja
```
## HTMLファイル生成
```
$ git clone git@github.com:Kitware/CMake.git
$ mkdir -p locales/ja/LC_MESSAGES
$ git clone git@github.com:k-mana/CMake-docs-ja.git locales/ja/LC_MESSAES
$ cmake -B build-docs-ja -S CMake/Utilities/Sphinx -DSPHINX_HTML=ON -DSPHINX_FLAGS="-D locale_dirs=locales -D language=ja -D gettext_compact=0"
$ cmake --build build-docs-ja
```
