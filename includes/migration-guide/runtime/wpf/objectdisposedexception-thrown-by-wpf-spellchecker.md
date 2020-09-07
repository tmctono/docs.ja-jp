---
ms.openlocfilehash: 3244913e06a744dafc4440f824ebe6bed25b8dd1
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496645"
---
### <a name="objectdisposedexception-thrown-by-wpf-spellchecker"></a><span data-ttu-id="71907-101">ObjectDisposedException が WPF スペルチェックでスローされる</span><span class="sxs-lookup"><span data-stu-id="71907-101">ObjectDisposedException thrown by WPF spellchecker</span></span>

#### <a name="details"></a><span data-ttu-id="71907-102">説明</span><span class="sxs-lookup"><span data-stu-id="71907-102">Details</span></span>

<span data-ttu-id="71907-103">スペルチェックで <xref:System.ObjectDisposedException?displayProperty=fullName> がスローされ、WPF アプリケーションがシャットダウン時にクラッシュする場合があります。</span><span class="sxs-lookup"><span data-stu-id="71907-103">WPF applications occasionally crash during application shutdown with an <xref:System.ObjectDisposedException?displayProperty=fullName> thrown by the spellchecker.</span></span> <span data-ttu-id="71907-104">これは .NET Framework 4.7 WPF で修正されます。例外は正しく処理されるため、アプリケーションが悪影響を受けることはなくなります。</span><span class="sxs-lookup"><span data-stu-id="71907-104">This is fixed in .NET Framework 4.7 WPF by handling the exception gracefully, and thus ensuring that applications are no longer adversely affected.</span></span> <span data-ttu-id="71907-105">ただし、デバッグ時に実行中のアプリケーションで初回例外が見られる場合があるので注意してください。</span><span class="sxs-lookup"><span data-stu-id="71907-105">It should be noted that occasional first-chance exceptions would continue to be observed in applications running under a debugger.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="71907-106">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="71907-106">Suggestion</span></span>

<span data-ttu-id="71907-107">.NET Framework 4.7 にアップグレードします</span><span class="sxs-lookup"><span data-stu-id="71907-107">Upgrade to .NET Framework 4.7</span></span>

| <span data-ttu-id="71907-108">名前</span><span class="sxs-lookup"><span data-stu-id="71907-108">Name</span></span>    | <span data-ttu-id="71907-109">[値]</span><span class="sxs-lookup"><span data-stu-id="71907-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="71907-110">スコープ</span><span class="sxs-lookup"><span data-stu-id="71907-110">Scope</span></span>   |<span data-ttu-id="71907-111">エッジ</span><span class="sxs-lookup"><span data-stu-id="71907-111">Edge</span></span>|
|<span data-ttu-id="71907-112">バージョン</span><span class="sxs-lookup"><span data-stu-id="71907-112">Version</span></span>|<span data-ttu-id="71907-113">4.6.1</span><span class="sxs-lookup"><span data-stu-id="71907-113">4.6.1</span></span>|
|<span data-ttu-id="71907-114">種類</span><span class="sxs-lookup"><span data-stu-id="71907-114">Type</span></span>|<span data-ttu-id="71907-115">ランタイム</span><span class="sxs-lookup"><span data-stu-id="71907-115">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="71907-116">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="71907-116">Affected APIs</span></span>

<span data-ttu-id="71907-117">API 分析では検出できません。</span><span class="sxs-lookup"><span data-stu-id="71907-117">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
