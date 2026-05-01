# yasutake_repo01

### `-u` とは？

**`-u` は「このブランチの push／pull 先を覚えさせる」オプション**です。

```bash
git push -u origin develop
```

これで起きることは **2つだけ**👇

1.  **今この場で**  
    → `develop` を `origin/develop` に push する
2.  **これから先の設定として**  
    → 「`develop` の行き先は `origin/develop`」と記憶する（upstream を設定）

***

### `-u` を付けた後にできること

```bash
git push
git pull
```

✅ どちらも **`origin/develop`** が自動で使われる  
（毎回 `origin develop` を書かなくてよくなる）

***

### 一言まとめ

> **`-u` =「次から省略できるように、行き先を覚えさせる」**


## お試し
```
git branch -vv
  develop          d1776cf [origin/develop: ahead 1] push test from develop
* feature/add-note d1776cf push test from develop
  main             a2e44f0 [origin/main: ahead 1] NG test

git push -u origin feature/add-note

git branch -vv
  develop          d1776cf [origin/develop: ahead 1] push test from develop
* feature/add-note 1f4f25f [origin/feature/add-note] Explanation of upstream
  main             a2e44f0 [origin/main: ahead 1] NG test
```

まとめ（覚えておくと便利）
| 目的 | コマンド |
|---|---|
| upstream 確認（おすすめ） | `git branch -vv` |
| upstream だけ確認 | `git rev-parse --abbrev-ref @{u}` |
| upstream 再設定 | `git branch --set-upstream-to=origin/develop` |