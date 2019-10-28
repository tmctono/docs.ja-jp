---
ms.openlocfilehash: 6bb8c87af66e744514fb43e628c6423487342ac2
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2019
ms.locfileid: "72887798"
---
### <a name="calls-to-systemwindowsinputpencontextdisable-on-touch-enabled-systems-may-throw-an-argumentexception"></a><span data-ttu-id="65f43-101">タッチ対応システムで System.Windows.Input.PenContext.Disable を呼び出すと ArgumentException がスローされることがある</span><span class="sxs-lookup"><span data-stu-id="65f43-101">Calls to System.Windows.Input.PenContext.Disable on touch-enabled systems may throw an ArgumentException</span></span>

|   |   |
|---|---|
|<span data-ttu-id="65f43-102">説明</span><span class="sxs-lookup"><span data-stu-id="65f43-102">Details</span></span>|<span data-ttu-id="65f43-103">一部の状況では、タッチ対応システムで内部 **System.Windows.Intput.PenContext.Disable** メソッドを呼び出すと、再入に起因して未処理の <code>T:System.ArgumentException</code> がスローされることがあります。</span><span class="sxs-lookup"><span data-stu-id="65f43-103">Under some circumstances, calls to the internal **System.Windows.Intput.PenContext.Disable** method on touch-enabled systems may throw an unhandled <code>T:System.ArgumentException</code> because of reentrancy.</span></span>|
|<span data-ttu-id="65f43-104">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="65f43-104">Suggestion</span></span>|<span data-ttu-id="65f43-105">この問題は、.NET Framework 4.7 では対処済みです。</span><span class="sxs-lookup"><span data-stu-id="65f43-105">This issue has been addressed in the .NET Framework 4.7.</span></span> <span data-ttu-id="65f43-106">例外を防ぐには、.NET Framework 4.7 以降のバージョンの .NET Framework にアップグレードします。</span><span class="sxs-lookup"><span data-stu-id="65f43-106">To prevent the exception, upgrade to a version of the .NET Framework starting with the .NET Framework 4.7.</span></span>|
|<span data-ttu-id="65f43-107">スコープ</span><span class="sxs-lookup"><span data-stu-id="65f43-107">Scope</span></span>|<span data-ttu-id="65f43-108">エッジ</span><span class="sxs-lookup"><span data-stu-id="65f43-108">Edge</span></span>|
|<span data-ttu-id="65f43-109">Version</span><span class="sxs-lookup"><span data-stu-id="65f43-109">Version</span></span>|<span data-ttu-id="65f43-110">4.6.1</span><span class="sxs-lookup"><span data-stu-id="65f43-110">4.6.1</span></span>|
|<span data-ttu-id="65f43-111">型</span><span class="sxs-lookup"><span data-stu-id="65f43-111">Type</span></span>|<span data-ttu-id="65f43-112">再ターゲット中</span><span class="sxs-lookup"><span data-stu-id="65f43-112">Retargeting</span></span>|
