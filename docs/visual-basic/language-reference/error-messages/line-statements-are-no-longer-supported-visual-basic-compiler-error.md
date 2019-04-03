---
title: "'Line' ステートメントはサポートされていません (Visual Basic コンパイラ エラー)"
ms.date: 07/20/2015
f1_keywords:
- bc30830
- vbc30830
helpviewer_keywords:
- BC30830
ms.assetid: 4734bc1d-882e-4555-b498-1f1ec0399d16
ms.openlocfilehash: 7616bcdc39ab479049586534fac22f1e2d96a700
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/02/2019
ms.locfileid: "58831840"
---
# <a name="line-statements-are-no-longer-supported-visual-basic-compiler-error"></a><span data-ttu-id="85ec0-102">'Line' ステートメントはサポートされていません (Visual Basic コンパイラ エラー)</span><span class="sxs-lookup"><span data-stu-id="85ec0-102">'Line' statements are no longer supported (Visual Basic Compiler Error)</span></span>
<span data-ttu-id="85ec0-103">行のステートメントがサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="85ec0-103">Line statements are no longer supported.</span></span> <span data-ttu-id="85ec0-104">ファイル I/O 機能は`Microsoft.VisualBasic.FileSystem.LineInput`グラフィックス機能は、`System.Drawing.Graphics.DrawLine`します。</span><span class="sxs-lookup"><span data-stu-id="85ec0-104">File I/O functionality is available as `Microsoft.VisualBasic.FileSystem.LineInput` and graphics functionality is available as `System.Drawing.Graphics.DrawLine`.</span></span>  
  
 <span data-ttu-id="85ec0-105">**エラー ID:** BC30830</span><span class="sxs-lookup"><span data-stu-id="85ec0-105">**Error ID:** BC30830</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="85ec0-106">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="85ec0-106">To correct this error</span></span>  
  
1.  <span data-ttu-id="85ec0-107">ファイル アクセスを実行する場合は、使用`Microsoft.VisualBasic.FileSystem.LineInput`します。</span><span class="sxs-lookup"><span data-stu-id="85ec0-107">If performing file access, use `Microsoft.VisualBasic.FileSystem.LineInput`.</span></span>  
  
2.  <span data-ttu-id="85ec0-108">グラフィックス処理を行っている場合は、 `System.Drawing.Graphics.Drawline`を使用します。</span><span class="sxs-lookup"><span data-stu-id="85ec0-108">If performing graphics, use `System.Drawing.Graphics.Drawline`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85ec0-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="85ec0-109">See also</span></span>

- <xref:System.IO>
- <xref:System.Drawing>
- [<span data-ttu-id="85ec0-110">Visual Basic におけるファイル アクセス</span><span class="sxs-lookup"><span data-stu-id="85ec0-110">File Access with Visual Basic</span></span>](../../../visual-basic/developing-apps/programming/drives-directories-files/file-access.md)
