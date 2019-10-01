---
title: 範囲変数の名前は、引数なしの簡易名または修飾名からのみ推論できます
ms.date: 07/20/2015
f1_keywords:
- vbc36599
- bc36599
helpviewer_keywords:
- BC36599
ms.assetid: 17763dbe-f74f-4ccb-8086-cb7e45ec4d12
ms.openlocfilehash: f448f34dc5909b9128fc700abab5b4f00e911edf
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2019
ms.locfileid: "71701014"
---
# <a name="range-variable-name-can-be-inferred-only-from-a-simple-or-qualified-name-with-no-arguments"></a><span data-ttu-id="fcdc8-102">範囲変数の名前は、引数なしの簡易名または修飾名からのみ推論できます</span><span class="sxs-lookup"><span data-stu-id="fcdc8-102">Range variable name can be inferred only from a simple or qualified name with no arguments</span></span>
<span data-ttu-id="fcdc8-103">1つ以上の引数を受け取るプログラミング要素は、LINQ クエリに含まれています。</span><span class="sxs-lookup"><span data-stu-id="fcdc8-103">A programming element that takes one or more arguments is included in a LINQ query.</span></span> <span data-ttu-id="fcdc8-104">コンパイラは、そのプログラミング要素から範囲変数を推論できません。</span><span class="sxs-lookup"><span data-stu-id="fcdc8-104">The compiler is unable to infer a range variable from that programming element.</span></span>  
  
 <span data-ttu-id="fcdc8-105">**エラー ID:** BC36599</span><span class="sxs-lookup"><span data-stu-id="fcdc8-105">**Error ID:** BC36599</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="fcdc8-106">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="fcdc8-106">To correct this error</span></span>  
  
1. <span data-ttu-id="fcdc8-107">次のコードに示すように、プログラミング要素に明示的な変数名を指定します。</span><span class="sxs-lookup"><span data-stu-id="fcdc8-107">Supply an explicit variable name for the programming element, as shown in the following code:</span></span>  
  
```vb  
Dim query = From var1 In collection1   
            Select VariableAlias= SampleFunction(var1), var1  
```  
  
## <a name="see-also"></a><span data-ttu-id="fcdc8-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="fcdc8-108">See also</span></span>

- [<span data-ttu-id="fcdc8-109">Visual Basic における LINQ の概要</span><span class="sxs-lookup"><span data-stu-id="fcdc8-109">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="fcdc8-110">Select 句</span><span class="sxs-lookup"><span data-stu-id="fcdc8-110">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)
