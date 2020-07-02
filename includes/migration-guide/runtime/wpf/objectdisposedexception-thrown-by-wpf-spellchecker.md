---
ms.openlocfilehash: b836b26f3f52e9d0cc78feb764629bd2fa306657
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621809"
---
### <a name="objectdisposedexception-thrown-by-wpf-spellchecker"></a><span data-ttu-id="151c4-101">ObjectDisposedException が WPF スペルチェックでスローされる</span><span class="sxs-lookup"><span data-stu-id="151c4-101">ObjectDisposedException thrown by WPF spellchecker</span></span>

#### <a name="details"></a><span data-ttu-id="151c4-102">説明</span><span class="sxs-lookup"><span data-stu-id="151c4-102">Details</span></span>

<span data-ttu-id="151c4-103">スペルチェックで <xref:System.ObjectDisposedException?displayProperty=fullName> がスローされ、WPF アプリケーションがシャットダウン時にクラッシュする場合があります。</span><span class="sxs-lookup"><span data-stu-id="151c4-103">WPF applications occasionally crash during application shutdown with an <xref:System.ObjectDisposedException?displayProperty=fullName> thrown by the spellchecker.</span></span> <span data-ttu-id="151c4-104">これは .NET Framework 4.7 WPF で修正されます。例外は正しく処理されるため、アプリケーションが悪影響を受けることはなくなります。</span><span class="sxs-lookup"><span data-stu-id="151c4-104">This is fixed in .NET Framework 4.7 WPF by handling the exception gracefully, and thus ensuring that applications are no longer adversely affected.</span></span> <span data-ttu-id="151c4-105">ただし、デバッグ時に実行中のアプリケーションで初回例外が見られる場合があるので注意してください。</span><span class="sxs-lookup"><span data-stu-id="151c4-105">It should be noted that occasional first-chance exceptions would continue to be observed in applications running under a debugger.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="151c4-106">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="151c4-106">Suggestion</span></span>

<span data-ttu-id="151c4-107">.NET Framework 4.7 にアップグレードします</span><span class="sxs-lookup"><span data-stu-id="151c4-107">Upgrade to .NET Framework 4.7</span></span>

| <span data-ttu-id="151c4-108">名前</span><span class="sxs-lookup"><span data-stu-id="151c4-108">Name</span></span>    | <span data-ttu-id="151c4-109">[値]</span><span class="sxs-lookup"><span data-stu-id="151c4-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="151c4-110">スコープ</span><span class="sxs-lookup"><span data-stu-id="151c4-110">Scope</span></span>   |<span data-ttu-id="151c4-111">エッジ</span><span class="sxs-lookup"><span data-stu-id="151c4-111">Edge</span></span>|
|<span data-ttu-id="151c4-112">バージョン</span><span class="sxs-lookup"><span data-stu-id="151c4-112">Version</span></span>|<span data-ttu-id="151c4-113">4.6.1</span><span class="sxs-lookup"><span data-stu-id="151c4-113">4.6.1</span></span>|
|<span data-ttu-id="151c4-114">種類</span><span class="sxs-lookup"><span data-stu-id="151c4-114">Type</span></span>|<span data-ttu-id="151c4-115">ランタイム</span><span class="sxs-lookup"><span data-stu-id="151c4-115">Runtime</span></span>|
