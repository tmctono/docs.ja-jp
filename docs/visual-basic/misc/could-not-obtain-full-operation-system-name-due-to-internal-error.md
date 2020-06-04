---
title: 内部エラーのために完全な運用システム名を取得できませんでした
ms.date: 07/20/2015
f1_keywords:
- vbrDiagnosticInfo_FullOSName
ms.assetid: f69da02b-eb9a-4284-bb9e-3025517ae6c1
ms.openlocfilehash: 67e8fb5e906800d28bf15714463b7ff6ae585693
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2020
ms.locfileid: "84402279"
---
# <a name="could-not-obtain-full-operation-system-name-due-to-internal-error"></a><span data-ttu-id="9550e-102">内部エラーのために完全な運用システム名を取得できませんでした</span><span class="sxs-lookup"><span data-stu-id="9550e-102">Could not obtain full operation system name due to internal error</span></span>
<span data-ttu-id="9550e-103">内部エラーのために完全な運用システム名を取得できませんでした。</span><span class="sxs-lookup"><span data-stu-id="9550e-103">Could not obtain full operation system name due to internal error.</span></span> <span data-ttu-id="9550e-104">これは、現在のコンピューターに WMI が存在しないことが原因である場合があります。</span><span class="sxs-lookup"><span data-stu-id="9550e-104">This might be caused by WMI not existing on the current machine.</span></span>  
  
 <span data-ttu-id="9550e-105">`My.Computer.Info.OSFullName` プロパティの呼び出しに失敗しました。</span><span class="sxs-lookup"><span data-stu-id="9550e-105">A call to the `My.Computer.Info.OSFullName` property failed.</span></span> <span data-ttu-id="9550e-106">このエラーの考えられる原因は、Windows Management Instrumentation (WMI) が、現在のコンピューターにインストールされていないことです。</span><span class="sxs-lookup"><span data-stu-id="9550e-106">A possible cause for this failure is if Windows Management Instrumentation (WMI) is not installed on the current computer.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="9550e-107">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="9550e-107">To correct this error</span></span>  
  
1. <span data-ttu-id="9550e-108">`Try...Catch` プロパティの呼び出しの周囲に `My.Computer.Info.OSFullName` ブロックを追加します。</span><span class="sxs-lookup"><span data-stu-id="9550e-108">Add a `Try...Catch` block around the call to the `My.Computer.Info.OSFullName` property.</span></span>  
  
2. <span data-ttu-id="9550e-109">WMI とそのインストール方法の詳細については、「」にアクセスし、「Windows Management Instrumentation Core」を検索してください。</span><span class="sxs-lookup"><span data-stu-id="9550e-109">For more information about WMI and how to install it, go to  and search for "Windows Management Instrumentation Core".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9550e-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="9550e-110">See also</span></span>

- [<span data-ttu-id="9550e-111">マイ. Computer. Info. OSFullName</span><span class="sxs-lookup"><span data-stu-id="9550e-111">My.Computer.Info.OSFullName</span></span>](xref:Microsoft.VisualBasic.Devices.ComputerInfo.OSFullName)
- [<span data-ttu-id="9550e-112">.NET での例外の処理とスロー</span><span class="sxs-lookup"><span data-stu-id="9550e-112">Handling and throwing exceptions in .NET</span></span>](../../standard/exceptions/index.md)
- [<span data-ttu-id="9550e-113">Try...Catch...Finally ステートメント</span><span class="sxs-lookup"><span data-stu-id="9550e-113">Try...Catch...Finally Statement</span></span>](../language-reference/statements/try-catch-finally-statement.md)
