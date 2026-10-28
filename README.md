# ティッカーコード for Gemini CLI

Connect [Gemini CLI](https://geminicli.com) to [ティッカーコード](https://ticker-code.com) for Japanese stocks, company financials, disclosures and your own watchlists.

## Install

```sh
gemini extensions install https://github.com/tickercode/gemini-cli-extension
gemini
```

Restart any already-running Gemini CLI session after installation. In the interactive session, authorize the connector:

```text
/mcp auth tickercode
/mcp list
```

Sign in to your own ティッカーコード account in the browser and review the requested permissions. The extension requests stock/disclosure reads, your watchlist reads and writes, and `offline_access` for refresh. No API key or password is included in the extension. Gemini CLI manages the OAuth credentials. Re-run `/mcp auth tickercode` if reconnection is needed.

For a pinned release:

```sh
gemini extensions install https://github.com/tickercode/gemini-cli-extension --ref v0.4.2
```

## Examples

- 「トヨタ7203の会社情報と直近の決算を、出典と対象期間付きで教えて」
- 「トヨタ7203とホンダ7267の主要指標を比較して」
- 「トヨタの直近30日の開示を探して、原文を読んで要点をまとめて」
- 「自分の監視リストを見せて」
- 「指定した監視リストにトヨタを追加して」

18 hosted tools cover company search/get/screen/rank/compare, prices/financials, disclosures and articles, your watchlists/alerts/add/remove, and source search/fetch. Only `watch_add` and `watch_remove` write account data. The connector does not place trades, transfer money, manage subscriptions or delete accounts.

## Privacy and network

The extension uses Streamable HTTP at `https://api.ticker-code.com/mcp`. OAuth discovery identifies `https://ticker-code.com` as the issuer; browser sign-in, consent, client registration and token exchange use that service. Only the account and scopes you authorize can access your private watchlists. MCP results enter your Gemini session and are subject to Google's applicable terms and data policies as well as ティッカーコード's policies.

See [MCP privacy details](https://cdn.ticker-code.com/review/tickercode-mcp-privacy-v1.html), [privacy policy](https://ticker-code.com/legal/privacy), and [service terms](https://ticker-code.com/legal/terms). Contact [support](https://ticker-code.com/contact) or info@tc-kk.com.

This Gemini CLI extension is separate from the consumer Gemini web/mobile custom-app feature and does not change that feature's eligibility requirements.

## Publication

This repository contains only the public connector configuration and guidance. Gallery discovery uses the `gemini-cli-extension` GitHub topic and the root manifest. Google crawls eligible repositories daily; publishing this repository does not guarantee immediate gallery visibility or endorsement.

## License

MIT applies to these extension files. The hosted service and source data retain their applicable terms and rights. Maintained by 株式会社TC.
