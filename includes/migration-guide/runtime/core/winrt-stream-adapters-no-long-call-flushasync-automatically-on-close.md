---
ms.openlocfilehash: 60937459b6f18e9abae87ad2dc97c3942325eedc
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620275"
---
### <a name="winrt-stream-adapters-no-long-call-flushasync-automatically-on-close"></a><span data-ttu-id="c035a-101">終了時に WinRT ストリーム アダプターで FlushAsync が自動的に呼び出されなくなりました</span><span class="sxs-lookup"><span data-stu-id="c035a-101">WinRT stream adapters no long call FlushAsync automatically on close</span></span>

#### <a name="details"></a><span data-ttu-id="c035a-102">説明</span><span class="sxs-lookup"><span data-stu-id="c035a-102">Details</span></span>

<span data-ttu-id="c035a-103">Windows ストア アプリの Windows ランタイム ストリーム アダプターで、Dispose メソッドから FlushAsync メソッドが呼び出されなくなりました。</span><span class="sxs-lookup"><span data-stu-id="c035a-103">In Windows Store apps, Windows Runtime stream adapters no longer call the FlushAsync method from the Dispose method.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="c035a-104">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="c035a-104">Suggestion</span></span>

<span data-ttu-id="c035a-105">この変更は透過的である必要があります。</span><span class="sxs-lookup"><span data-stu-id="c035a-105">This change should be transparent.</span></span> <span data-ttu-id="c035a-106">開発者は次のようなコードを記述して以前の動作を復元できます。</span><span class="sxs-lookup"><span data-stu-id="c035a-106">Developers can restore the previous behavior by writing code like this:</span></span><pre><code class="lang-csharp">using (var stream = GetWindowsRuntimeStream() as Stream)&#13;&#10;{&#13;&#10;// do something&#13;&#10;await stream.FlushAsync();&#13;&#10;}&#13;&#10;</code></pre>

| <span data-ttu-id="c035a-107">名前</span><span class="sxs-lookup"><span data-stu-id="c035a-107">Name</span></span>    | <span data-ttu-id="c035a-108">[値]</span><span class="sxs-lookup"><span data-stu-id="c035a-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="c035a-109">スコープ</span><span class="sxs-lookup"><span data-stu-id="c035a-109">Scope</span></span>   |<span data-ttu-id="c035a-110">透明</span><span class="sxs-lookup"><span data-stu-id="c035a-110">Transparent</span></span>|
|<span data-ttu-id="c035a-111">バージョン</span><span class="sxs-lookup"><span data-stu-id="c035a-111">Version</span></span>|<span data-ttu-id="c035a-112">4.5.1</span><span class="sxs-lookup"><span data-stu-id="c035a-112">4.5.1</span></span>|
|<span data-ttu-id="c035a-113">種類</span><span class="sxs-lookup"><span data-stu-id="c035a-113">Type</span></span>|<span data-ttu-id="c035a-114">ランタイム</span><span class="sxs-lookup"><span data-stu-id="c035a-114">Runtime</span></span>|
