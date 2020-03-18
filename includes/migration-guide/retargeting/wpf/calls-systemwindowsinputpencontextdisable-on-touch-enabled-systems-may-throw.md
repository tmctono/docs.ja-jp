---
ms.openlocfilehash: 6bb8c87af66e744514fb43e628c6423487342ac2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/15/2020
ms.locfileid: "72887798"
---
### <a name="calls-to-systemwindowsinputpencontextdisable-on-touch-enabled-systems-may-throw-an-argumentexception"></a><span data-ttu-id="776ef-101">タッチ対応システムで System.Windows.Input.PenContext.Disable を呼び出すと ArgumentException がスローされることがある</span><span class="sxs-lookup"><span data-stu-id="776ef-101">Calls to System.Windows.Input.PenContext.Disable on touch-enabled systems may throw an ArgumentException</span></span>

|   |   |
|---|---|
|<span data-ttu-id="776ef-102">説明</span><span class="sxs-lookup"><span data-stu-id="776ef-102">Details</span></span>|<span data-ttu-id="776ef-103">一部の状況では、タッチ対応システムで内部 **System.Windows.Intput.PenContext.Disable** メソッドを呼び出すと、再入に起因して未処理の <code>T:System.ArgumentException</code> がスローされることがあります。</span><span class="sxs-lookup"><span data-stu-id="776ef-103">Under some circumstances, calls to the internal **System.Windows.Intput.PenContext.Disable** method on touch-enabled systems may throw an unhandled <code>T:System.ArgumentException</code> because of reentrancy.</span></span>|
|<span data-ttu-id="776ef-104">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="776ef-104">Suggestion</span></span>|<span data-ttu-id="776ef-105">この問題は、.NET Framework 4.7 では対処済みです。</span><span class="sxs-lookup"><span data-stu-id="776ef-105">This issue has been addressed in the .NET Framework 4.7.</span></span> <span data-ttu-id="776ef-106">例外を防ぐには、.NET Framework 4.7 以降のバージョンの .NET Framework にアップグレードします。</span><span class="sxs-lookup"><span data-stu-id="776ef-106">To prevent the exception, upgrade to a version of the .NET Framework starting with the .NET Framework 4.7.</span></span>|
|<span data-ttu-id="776ef-107">スコープ</span><span class="sxs-lookup"><span data-stu-id="776ef-107">Scope</span></span>|<span data-ttu-id="776ef-108">エッジ</span><span class="sxs-lookup"><span data-stu-id="776ef-108">Edge</span></span>|
|<span data-ttu-id="776ef-109">バージョン</span><span class="sxs-lookup"><span data-stu-id="776ef-109">Version</span></span>|<span data-ttu-id="776ef-110">4.6.1</span><span class="sxs-lookup"><span data-stu-id="776ef-110">4.6.1</span></span>|
|<span data-ttu-id="776ef-111">[種類]</span><span class="sxs-lookup"><span data-stu-id="776ef-111">Type</span></span>|<span data-ttu-id="776ef-112">再ターゲット中</span><span class="sxs-lookup"><span data-stu-id="776ef-112">Retargeting</span></span>|
