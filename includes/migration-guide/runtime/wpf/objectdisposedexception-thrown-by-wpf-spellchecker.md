---
ms.openlocfilehash: a3f5f512fd17ab2b076f868be24e5c73d8698c49
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/15/2020
ms.locfileid: "67802510"
---
### <a name="objectdisposedexception-thrown-by-wpf-spellchecker"></a><span data-ttu-id="8f319-101">ObjectDisposedException が WPF スペルチェックでスローされる</span><span class="sxs-lookup"><span data-stu-id="8f319-101">ObjectDisposedException thrown by WPF spellchecker</span></span>

|   |   |
|---|---|
|<span data-ttu-id="8f319-102">説明</span><span class="sxs-lookup"><span data-stu-id="8f319-102">Details</span></span>|<span data-ttu-id="8f319-103">スペルチェックで <xref:System.ObjectDisposedException?displayProperty=name> がスローされ、WPF アプリケーションがシャットダウン時にクラッシュする場合があります。</span><span class="sxs-lookup"><span data-stu-id="8f319-103">WPF applications occasionally crash during application shutdown with an <xref:System.ObjectDisposedException?displayProperty=name> thrown by the spellchecker.</span></span> <span data-ttu-id="8f319-104">これは .NET Framework 4.7 WPF で修正されます。例外は正しく処理されるため、アプリケーションが悪影響を受けることはなくなります。</span><span class="sxs-lookup"><span data-stu-id="8f319-104">This is fixed in .NET Framework 4.7 WPF by handling the exception gracefully, and thus ensuring that applications are no longer adversely affected.</span></span> <span data-ttu-id="8f319-105">ただし、デバッグ時に実行中のアプリケーションで初回例外が見られる場合があるので注意してください。</span><span class="sxs-lookup"><span data-stu-id="8f319-105">It should be noted that occasional first-chance exceptions would continue to be observed in applications running under a debugger.</span></span>|
|<span data-ttu-id="8f319-106">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="8f319-106">Suggestion</span></span>|<span data-ttu-id="8f319-107">.NET Framework 4.7 にアップグレードします</span><span class="sxs-lookup"><span data-stu-id="8f319-107">Upgrade to .NET Framework 4.7</span></span>|
|<span data-ttu-id="8f319-108">スコープ</span><span class="sxs-lookup"><span data-stu-id="8f319-108">Scope</span></span>|<span data-ttu-id="8f319-109">エッジ</span><span class="sxs-lookup"><span data-stu-id="8f319-109">Edge</span></span>|
|<span data-ttu-id="8f319-110">バージョン</span><span class="sxs-lookup"><span data-stu-id="8f319-110">Version</span></span>|<span data-ttu-id="8f319-111">4.6.1</span><span class="sxs-lookup"><span data-stu-id="8f319-111">4.6.1</span></span>|
|<span data-ttu-id="8f319-112">[種類]</span><span class="sxs-lookup"><span data-stu-id="8f319-112">Type</span></span>|<span data-ttu-id="8f319-113">ランタイム</span><span class="sxs-lookup"><span data-stu-id="8f319-113">Runtime</span></span>|
