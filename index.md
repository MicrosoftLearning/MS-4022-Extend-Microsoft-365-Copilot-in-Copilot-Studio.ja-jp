---
title: 演習の手順
permalink: index.html
layout: home
---

# 演習

このページでは、Microsoft スキル コース「**MS-4022: Copilot Studio で Microsoft 365 Copilot を拡張する**」に関連する演習の一覧を示します。

関連するラーニング パス: [Copilot Studio で Microsoft 365 Copilot を拡張する](https://learn.microsoft.com/training/paths/extend-microsoft-365-copilot-studio/)。

**注**: これらの演習を完了するには、以下が必要です。

- [Copilot Studio にアクセスできる](https://learn.microsoft.com/microsoft-copilot-studio/requirements-licensing-subscriptions)職場または学校アカウント。 Copilot Studio にまだアクセスできない場合、Microsoft 365 組織の構成によっては、[試用版アカウントを作成](https://learn.microsoft.com/microsoft-copilot-studio/sign-up-individual)できる場合があります。
- Microsoft 365 Copilot ライセンス
- 目的のコンテンツ ソース (コネクタ、API など) に接続するために必要な資格情報

{% assign labs = site.pages | where_exp:"page", "page.url contains '/Instructions/Labs'" %} {% assign labs = labs | sort: "lab.title" %} {% for activity in labs  %}
- [{{ activity.lab.title }}]({{ site.github.url }}{{ activity.url }}) {% endfor %}

