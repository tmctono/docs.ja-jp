---
ms.openlocfilehash: a3f5f512fd17ab2b076f868be24e5c73d8698c49
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59234206"
---
### <a name="objectdisposedexception-thrown-by-wpf-spellchecker"></a><span data-ttu-id="b1e3b-101">ObjectDisposedException が WPF スペルチェックでスローされる</span><span class="sxs-lookup"><span data-stu-id="b1e3b-101">ObjectDisposedException thrown by WPF spellchecker</span></span>

|   |   |
|---|---|
|<span data-ttu-id="b1e3b-102">説明</span><span class="sxs-lookup"><span data-stu-id="b1e3b-102">Details</span></span>|<span data-ttu-id="b1e3b-103">スペルチェックで <xref:System.ObjectDisposedException?displayProperty=name> がスローされ、WPF アプリケーションがシャットダウン時にクラッシュする場合があります。</span><span class="sxs-lookup"><span data-stu-id="b1e3b-103">WPF applications occasionally crash during application shutdown with an <xref:System.ObjectDisposedException?displayProperty=name> thrown by the spellchecker.</span></span> <span data-ttu-id="b1e3b-104">これは .NET Framework 4.7 WPF で修正されます。例外は正しく処理されるため、アプリケーションが悪影響を受けることはなくなります。</span><span class="sxs-lookup"><span data-stu-id="b1e3b-104">This is fixed in .NET Framework 4.7 WPF by handling the exception gracefully, and thus ensuring that applications are no longer adversely affected.</span></span> <span data-ttu-id="b1e3b-105">ただし、デバッグ時に実行中のアプリケーションで初回例外が見られる場合があるので注意してください。</span><span class="sxs-lookup"><span data-stu-id="b1e3b-105">It should be noted that occasional first-chance exceptions would continue to be observed in applications running under a debugger.</span></span>|
|<span data-ttu-id="b1e3b-106">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="b1e3b-106">Suggestion</span></span>|<span data-ttu-id="b1e3b-107">.NET Framework 4.7 にアップグレードします</span><span class="sxs-lookup"><span data-stu-id="b1e3b-107">Upgrade to .NET Framework 4.7</span></span>|
|<span data-ttu-id="b1e3b-108">スコープ</span><span class="sxs-lookup"><span data-stu-id="b1e3b-108">Scope</span></span>|<span data-ttu-id="b1e3b-109">エッジ</span><span class="sxs-lookup"><span data-stu-id="b1e3b-109">Edge</span></span>|
|<span data-ttu-id="b1e3b-110">Version</span><span class="sxs-lookup"><span data-stu-id="b1e3b-110">Version</span></span>|<span data-ttu-id="b1e3b-111">4.6.1</span><span class="sxs-lookup"><span data-stu-id="b1e3b-111">4.6.1</span></span>|
|<span data-ttu-id="b1e3b-112">型</span><span class="sxs-lookup"><span data-stu-id="b1e3b-112">Type</span></span>|<span data-ttu-id="b1e3b-113">ランタイム</span><span class="sxs-lookup"><span data-stu-id="b1e3b-113">Runtime</span></span>|
