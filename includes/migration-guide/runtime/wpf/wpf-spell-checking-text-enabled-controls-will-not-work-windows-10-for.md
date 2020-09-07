---
ms.openlocfilehash: 6d7f998cda6326e1f584713576a0aa27b3a68655
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497573"
---
### <a name="wpf-spell-checking-in-text-enabled-controls-will-not-work-in-windows-10-for-languages-not-in-the-oss-input-language-list"></a>OS の入力言語リストにない言語の場合、Windows 10 でテキスト対応コントロールの WPF スペル チェックが動作しなくなる

#### <a name="details"></a>説明

プラットフォームのスペル チェック機能は入力言語リストに存在する言語でしか使用できないため、 Windows 10 での実行時には、WPF テキスト対応コントロール向けのスペル チェック機能が動作しないことがあります。Windows 10 では、使用可能なキーボードのリストに言語を追加すると、対応するオンデマンド機能 (FOD) パッケージが自動的にダウンロードおよびインストールされ、スペル チェック機能が提供されます。 入力言語リストに言語を追加することで、スペル チェック機能がサポートされます。

#### <a name="suggestion"></a>提案される解決策

Windows 10 でスペルチェックを動作させるには、スペルチェック対象の言語またはテキストを入力言語として追加する必要があることに注意してください。

| 名前    | 値       |
|:--------|:------------|
| スコープ   |エッジ|
|バージョン|4.6|
|種類|ランタイム|

#### <a name="affected-apis"></a>影響を受ける API

API 分析では検出できません。

<!--

#### Affected APIs

Not detectable via API analysis.

-->
