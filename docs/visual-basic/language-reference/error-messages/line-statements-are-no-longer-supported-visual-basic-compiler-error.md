---
title: "'Line' ステートメントはサポートされていません (Visual Basic コンパイラ エラー)"
ms.date: 07/20/2015
f1_keywords:
- bc30830
- vbc30830
helpviewer_keywords:
- BC30830
ms.assetid: 4734bc1d-882e-4555-b498-1f1ec0399d16
ms.openlocfilehash: a3d243f39f3fc45ca6b1ba0d26892d4c3db56f59
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2020
ms.locfileid: "84397299"
---
# <a name="line-statements-are-no-longer-supported-visual-basic-compiler-error"></a><span data-ttu-id="76d89-102">'Line' ステートメントはサポートされていません (Visual Basic コンパイラ エラー)</span><span class="sxs-lookup"><span data-stu-id="76d89-102">'Line' statements are no longer supported (Visual Basic Compiler Error)</span></span>
<span data-ttu-id="76d89-103">Line ステートメントは現在サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="76d89-103">Line statements are no longer supported.</span></span> <span data-ttu-id="76d89-104">ファイル I/O 機能は `Microsoft.VisualBasic.FileSystem.LineInput` として使用でき、グラフィックス機能は `System.Drawing.Graphics.DrawLine` として使用できます。</span><span class="sxs-lookup"><span data-stu-id="76d89-104">File I/O functionality is available as `Microsoft.VisualBasic.FileSystem.LineInput` and graphics functionality is available as `System.Drawing.Graphics.DrawLine`.</span></span>  
  
 <span data-ttu-id="76d89-105">**エラー ID:** BC30830</span><span class="sxs-lookup"><span data-stu-id="76d89-105">**Error ID:** BC30830</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="76d89-106">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="76d89-106">To correct this error</span></span>  
  
1. <span data-ttu-id="76d89-107">ファイル アクセスを実行する場合は、`Microsoft.VisualBasic.FileSystem.LineInput` を使用します。</span><span class="sxs-lookup"><span data-stu-id="76d89-107">If performing file access, use `Microsoft.VisualBasic.FileSystem.LineInput`.</span></span>  
  
2. <span data-ttu-id="76d89-108">グラフィックス処理を行っている場合は、 `System.Drawing.Graphics.Drawline`を使用します。</span><span class="sxs-lookup"><span data-stu-id="76d89-108">If performing graphics, use `System.Drawing.Graphics.Drawline`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76d89-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="76d89-109">See also</span></span>

- <xref:System.IO>
- <xref:System.Drawing>
- [<span data-ttu-id="76d89-110">Visual Basic におけるファイル アクセス</span><span class="sxs-lookup"><span data-stu-id="76d89-110">File Access with Visual Basic</span></span>](../../developing-apps/programming/drives-directories-files/file-access.md)
