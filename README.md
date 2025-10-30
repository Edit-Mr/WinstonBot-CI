# WinstonBot CI

WinstonBot 是一個中文檢查工具，可以檢查拼寫錯誤、專有名詞大小寫、中國政治色彩用語等問題。它提供了 [Discord Bot](https://discord.com/oauth2/authorize?client_id=1342364253486846032)、[網頁](https://winston.emtech.cc/)、與 [CI](https://github.com/Edit-Mr/WinstonBot-CI) 三種使用方式。

此為 GitHub Actions 版本，同時整合 [AutoCorrect](https://github.com/huacnlee/autocorrect)。詳情請見 WinstonBot 的 [GitHub 頁面](https://github.com/Edit-Mr/WinstonBot)。

AutoCorrect 盤古之白皆會檢查。WinstonBot 預設只會檢查 Markdown (`.md`) 檔案，你可以指定檔案副檔名。

```yaml
uses: emtech-labs/winston-check-action@v1
with:
  exts: markdown,md,txt
```

## 使用方式

建立一個 GitHub Actions workflow（`.github/workflows/ci.yml`），內容範例如下：

```yml
name: 中文格式檢查

on:
  push:
  pull_request:

jobs:
  winston-bot:
    name: 📰 Winston Bot 中文檢查
    runs-on: ubuntu-latest
    steps:
      - name: Winston Bot 中文檢查
        uses: Edit-Mr/WinstonBot-CI@main
```
