---
ms.openlocfilehash: 6d7f998cda6326e1f584713576a0aa27b3a68655
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497573"
---
### <a name="wpf-spell-checking-in-text-enabled-controls-will-not-work-in-windows-10-for-languages-not-in-the-oss-input-language-list"></a><span data-ttu-id="828ee-101">OS の入力言語リストにない言語の場合、Windows 10 でテキスト対応コントロールの WPF スペル チェックが動作しなくなる</span><span class="sxs-lookup"><span data-stu-id="828ee-101">WPF spell checking in text-enabled controls will not work in Windows 10 for languages not in the OS's input language list</span></span>

#### <a name="details"></a><span data-ttu-id="828ee-102">説明</span><span class="sxs-lookup"><span data-stu-id="828ee-102">Details</span></span>

<span data-ttu-id="828ee-103">プラットフォームのスペル チェック機能は入力言語リストに存在する言語でしか使用できないため、 Windows 10 での実行時には、WPF テキスト対応コントロール向けのスペル チェック機能が動作しないことがあります。Windows 10 では、使用可能なキーボードのリストに言語を追加すると、対応するオンデマンド機能 (FOD) パッケージが自動的にダウンロードおよびインストールされ、スペル チェック機能が提供されます。</span><span class="sxs-lookup"><span data-stu-id="828ee-103">When running on Windows 10, the spell checker may not work for WPF text-enabled controls because platform spell-checking capabilities are available only for languages present in the input languages list.In Windows 10, when a language is added to the list of available keyboards, Windows automatically downloads and installs a corresponding Feature on Demand (FOD) package that provides spell-checking capabilities.</span></span> <span data-ttu-id="828ee-104">入力言語リストに言語を追加することで、スペル チェック機能がサポートされます。</span><span class="sxs-lookup"><span data-stu-id="828ee-104">By adding the language to the input languages list, the spell checker will be supported.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="828ee-105">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="828ee-105">Suggestion</span></span>

<span data-ttu-id="828ee-106">Windows 10 でスペルチェックを動作させるには、スペルチェック対象の言語またはテキストを入力言語として追加する必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="828ee-106">Be aware that the language or text to be spell-checked must be added as an input language for spell-checking to work in Windows 10.</span></span>

| <span data-ttu-id="828ee-107">名前</span><span class="sxs-lookup"><span data-stu-id="828ee-107">Name</span></span>    | <span data-ttu-id="828ee-108">値</span><span class="sxs-lookup"><span data-stu-id="828ee-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="828ee-109">スコープ</span><span class="sxs-lookup"><span data-stu-id="828ee-109">Scope</span></span>   |<span data-ttu-id="828ee-110">エッジ</span><span class="sxs-lookup"><span data-stu-id="828ee-110">Edge</span></span>|
|<span data-ttu-id="828ee-111">バージョン</span><span class="sxs-lookup"><span data-stu-id="828ee-111">Version</span></span>|<span data-ttu-id="828ee-112">4.6</span><span class="sxs-lookup"><span data-stu-id="828ee-112">4.6</span></span>|
|<span data-ttu-id="828ee-113">種類</span><span class="sxs-lookup"><span data-stu-id="828ee-113">Type</span></span>|<span data-ttu-id="828ee-114">ランタイム</span><span class="sxs-lookup"><span data-stu-id="828ee-114">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="828ee-115">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="828ee-115">Affected APIs</span></span>

<span data-ttu-id="828ee-116">API 分析では検出できません。</span><span class="sxs-lookup"><span data-stu-id="828ee-116">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
