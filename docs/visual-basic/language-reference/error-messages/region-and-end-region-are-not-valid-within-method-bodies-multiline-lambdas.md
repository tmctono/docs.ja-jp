---
title: "'#Region' および ' #End Region' ステートメントはメソッド本体や複数行ラムダ内では有効ではありません。"
ms.date: 07/20/2015
f1_keywords:
- bc32025
- vbc32025
helpviewer_keywords:
- BC32025
ms.assetid: 43707bf1-1c6b-4d82-b081-e5a17dca51c1
ms.openlocfilehash: deef3de645040d7c3d95b1a6c8a25fcf10de881b
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/02/2019
ms.locfileid: "58842708"
---
# <a name="region-and-end-region-statements-are-not-valid-within-method-bodiesmultiline-lambdas"></a><span data-ttu-id="3a4ae-102">'#Region' および '#End Region' ステートメントは、メソッド本体や複数行ラムダの内部では有効ではありません。</span><span class="sxs-lookup"><span data-stu-id="3a4ae-102">'#Region' and '#End Region' statements are not valid within method bodies/multiline lambdas</span></span>
<span data-ttu-id="3a4ae-103">`#Region`ブロックは、クラス、モジュール、または名前空間レベルで宣言する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3a4ae-103">The `#Region` block must be declared at a class, module, or namespace level.</span></span> <span data-ttu-id="3a4ae-104">折りたたみ可能な領域は、1 つ以上のプロシージャを含めることができますが、開始またはプロシージャの内部で終了することはできません。</span><span class="sxs-lookup"><span data-stu-id="3a4ae-104">A collapsible region can include one or more procedures, but it cannot begin or end inside of a procedure.</span></span>  
  
 <span data-ttu-id="3a4ae-105">**エラー ID:** BC32025</span><span class="sxs-lookup"><span data-stu-id="3a4ae-105">**Error ID:** BC32025</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="3a4ae-106">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="3a4ae-106">To correct this error</span></span>  
  
1.  <span data-ttu-id="3a4ae-107">直前のプロシージャが、`End Function`ステートメントまたは`End Sub`ステートメントによって正しく終了していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="3a4ae-107">Ensure that the preceding procedure is properly terminated with an `End Function` or `End Sub` statement.</span></span>  
  
2.  <span data-ttu-id="3a4ae-108">`#Region`ディレクティブおよび`#End Region`ディレクティブが同じコード ブロック内にあることを確認します。</span><span class="sxs-lookup"><span data-stu-id="3a4ae-108">Ensure that the `#Region` and `#End Region` directives are in the same code block.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a4ae-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="3a4ae-109">See also</span></span>

- [<span data-ttu-id="3a4ae-110">#Region ディレクティブ</span><span class="sxs-lookup"><span data-stu-id="3a4ae-110">#Region Directive</span></span>](../../../visual-basic/language-reference/directives/region-directive.md)
