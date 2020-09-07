---
ms.openlocfilehash: 2b4f35fe15f806897e5e4d85ee774b2e4572d974
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497901"
---
### <a name="winrt-stream-adapters-no-long-call-flushasync-automatically-on-close"></a><span data-ttu-id="0bbf3-101">終了時に WinRT ストリーム アダプターで FlushAsync が自動的に呼び出されなくなりました</span><span class="sxs-lookup"><span data-stu-id="0bbf3-101">WinRT stream adapters no long call FlushAsync automatically on close</span></span>

#### <a name="details"></a><span data-ttu-id="0bbf3-102">説明</span><span class="sxs-lookup"><span data-stu-id="0bbf3-102">Details</span></span>

<span data-ttu-id="0bbf3-103">Windows ストア アプリの Windows ランタイム ストリーム アダプターで、Dispose メソッドから FlushAsync メソッドが呼び出されなくなりました。</span><span class="sxs-lookup"><span data-stu-id="0bbf3-103">In Windows Store apps, Windows Runtime stream adapters no longer call the FlushAsync method from the Dispose method.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="0bbf3-104">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="0bbf3-104">Suggestion</span></span>

<span data-ttu-id="0bbf3-105">この変更は透過的である必要があります。</span><span class="sxs-lookup"><span data-stu-id="0bbf3-105">This change should be transparent.</span></span> <span data-ttu-id="0bbf3-106">開発者は次のようなコードを記述して以前の動作を復元できます。</span><span class="sxs-lookup"><span data-stu-id="0bbf3-106">Developers can restore the previous behavior by writing code like this:</span></span><pre><code class="lang-csharp">using (var stream = GetWindowsRuntimeStream() as Stream)&#13;&#10;{&#13;&#10;// do something&#13;&#10;await stream.FlushAsync();&#13;&#10;}&#13;&#10;</code></pre>

| <span data-ttu-id="0bbf3-107">名前</span><span class="sxs-lookup"><span data-stu-id="0bbf3-107">Name</span></span>    | <span data-ttu-id="0bbf3-108">[値]</span><span class="sxs-lookup"><span data-stu-id="0bbf3-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="0bbf3-109">スコープ</span><span class="sxs-lookup"><span data-stu-id="0bbf3-109">Scope</span></span>   |<span data-ttu-id="0bbf3-110">透明</span><span class="sxs-lookup"><span data-stu-id="0bbf3-110">Transparent</span></span>|
|<span data-ttu-id="0bbf3-111">バージョン</span><span class="sxs-lookup"><span data-stu-id="0bbf3-111">Version</span></span>|<span data-ttu-id="0bbf3-112">4.5.1</span><span class="sxs-lookup"><span data-stu-id="0bbf3-112">4.5.1</span></span>|
|<span data-ttu-id="0bbf3-113">種類</span><span class="sxs-lookup"><span data-stu-id="0bbf3-113">Type</span></span>|<span data-ttu-id="0bbf3-114">ランタイム</span><span class="sxs-lookup"><span data-stu-id="0bbf3-114">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="0bbf3-115">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="0bbf3-115">Affected APIs</span></span>

<span data-ttu-id="0bbf3-116">API 分析では検出できません。</span><span class="sxs-lookup"><span data-stu-id="0bbf3-116">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
