---
title: 内部エラーのため、メモリ情報を取得できませんでした
ms.date: 07/20/2015
f1_keywords:
- vbrDiagnosticInfo_Memory
ms.assetid: 1ba8f774-5858-438e-914e-99fddc9e5e7e
ms.openlocfilehash: 550ac0345d54c8a78e805b224ffaba47a3970ea9
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2020
ms.locfileid: "91076280"
---
# <a name="could-not-obtain-memory-information-due-to-internal-error"></a><span data-ttu-id="91687-102">内部エラーのため、メモリ情報を取得できませんでした</span><span class="sxs-lookup"><span data-stu-id="91687-102">Could not obtain memory information due to internal error</span></span>

<span data-ttu-id="91687-103">`My.Computer.Info` オブジェクトのメモリ情報のプロパティの 1 つに対する呼び出しが失敗しました。</span><span class="sxs-lookup"><span data-stu-id="91687-103">A call to one of the memory-information properties of the `My.Computer.Info` object failed.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="91687-104">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="91687-104">To correct this error</span></span>  
  
- <span data-ttu-id="91687-105">`Try...Catch` オブジェクトのメモリ情報プロパティへの呼び出しの周囲に `My.Computer.Info` を追加します。</span><span class="sxs-lookup"><span data-stu-id="91687-105">Add a `Try...Catch` block around the call to the memory-information property of the `My.Computer.Info` object.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91687-106">こちらもご覧ください</span><span class="sxs-lookup"><span data-stu-id="91687-106">See also</span></span>

- [<span data-ttu-id="91687-107">My.Computer.Info</span><span class="sxs-lookup"><span data-stu-id="91687-107">My.Computer.Info</span></span>](xref:Microsoft.VisualBasic.Devices.ComputerInfo)
- [<span data-ttu-id="91687-108">Try...Catch...Finally ステートメント</span><span class="sxs-lookup"><span data-stu-id="91687-108">Try...Catch...Finally Statement</span></span>](../language-reference/statements/try-catch-finally-statement.md)
