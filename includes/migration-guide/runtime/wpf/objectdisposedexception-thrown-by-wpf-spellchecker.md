---
ms.openlocfilehash: 9d09f598538b9d5ee3f995d6281b8eb4b2668050
ms.sourcegitcommit: 0aca6c5d166d7961a1e354c248495645b97a1dc5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/01/2019
ms.locfileid: "58761378"
---
### <a name="objectdisposedexception-thrown-by-wpf-spellchecker"></a><span data-ttu-id="613d1-101">ObjectDisposedException が WPF スペルチェックでスローされる</span><span class="sxs-lookup"><span data-stu-id="613d1-101">ObjectDisposedException thrown by WPF spellchecker</span></span>

|   |   |
|---|---|
|<span data-ttu-id="613d1-102">説明</span><span class="sxs-lookup"><span data-stu-id="613d1-102">Details</span></span>|<span data-ttu-id="613d1-103">スペルチェックで <xref:System.ObjectDisposedException?displayProperty=name> がスローされ、WPF アプリケーションがシャットダウン時にクラッシュする場合があります。</span><span class="sxs-lookup"><span data-stu-id="613d1-103">WPF applications occasionally crash during application shutdown with an <xref:System.ObjectDisposedException?displayProperty=name> thrown by the spellchecker.</span></span> <span data-ttu-id="613d1-104">これは .NET Framework 4.7 WPF で修正されます。例外は正しく処理されるため、アプリケーションが悪影響を受けることはなくなります。</span><span class="sxs-lookup"><span data-stu-id="613d1-104">This is fixed in .NET Framework 4.7 WPF by handling the exception gracefully, and thus ensuring that applications are no longer adversely affected.</span></span> <span data-ttu-id="613d1-105">ただし、デバッグ時に実行中のアプリケーションで初回例外が見られる場合があるので注意してください。</span><span class="sxs-lookup"><span data-stu-id="613d1-105">It should be noted that occasional first-chance exceptions would continue to be observed in applications running under a debugger.</span></span>|
|<span data-ttu-id="613d1-106">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="613d1-106">Suggestion</span></span>|<span data-ttu-id="613d1-107">.NET Framework 4.7 にアップグレードします</span><span class="sxs-lookup"><span data-stu-id="613d1-107">Upgrade to .NET Framework 4.7</span></span>|
|<span data-ttu-id="613d1-108">スコープ</span><span class="sxs-lookup"><span data-stu-id="613d1-108">Scope</span></span>|<span data-ttu-id="613d1-109">エッジ</span><span class="sxs-lookup"><span data-stu-id="613d1-109">Edge</span></span>|
|<span data-ttu-id="613d1-110">Version</span><span class="sxs-lookup"><span data-stu-id="613d1-110">Version</span></span>|<span data-ttu-id="613d1-111">4.6.1</span><span class="sxs-lookup"><span data-stu-id="613d1-111">4.6.1</span></span>|
|<span data-ttu-id="613d1-112">型</span><span class="sxs-lookup"><span data-stu-id="613d1-112">Type</span></span>|<span data-ttu-id="613d1-113">ランタイム</span><span class="sxs-lookup"><span data-stu-id="613d1-113">Runtime</span></span>|

