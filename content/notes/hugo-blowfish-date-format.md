---
title: "Hugo Blowfish Custom Date Format"
date: 2024-11-20
tags: ["hugo", "blowfish", "config"]
type: note
---

Blowfish uses the `dateFormat` parameter in `languages.en.toml` under `[params]`. Hugo's reference time is `Mon Jan 2 15:04:05 MST 2006`, so for YYYY.MMDD format:

```toml
dateFormat = "2006.0102"
```

This renders dates like `2024.1120` instead of the default `2 January 2006`.
