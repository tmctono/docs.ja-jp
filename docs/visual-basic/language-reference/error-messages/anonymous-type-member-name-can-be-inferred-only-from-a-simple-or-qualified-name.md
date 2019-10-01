---
title: 匿名型メンバーの名前は、引数なしの簡易名または修飾名からのみ推論できます
ms.date: 07/20/2015
f1_keywords:
- vbc36556
- bc36556
helpviewer_keywords:
- BC36556
ms.assetid: e3ba1f33-3a71-4f03-9b04-ed5ec17de17c
ms.openlocfilehash: 38f669fe183ac79ebed6e5a122bc70aedc9bb753
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2019
ms.locfileid: "71701226"
---
# <a name="anonymous-type-member-name-can-be-inferred-only-from-a-simple-or-qualified-name-with-no-arguments"></a><span data-ttu-id="e5217-102">匿名型メンバーの名前は、引数なしの簡易名または修飾名からのみ推論できます</span><span class="sxs-lookup"><span data-stu-id="e5217-102">Anonymous type member name can be inferred only from a simple or qualified name with no arguments</span></span>
<span data-ttu-id="e5217-103">複合式から匿名型のメンバー名を推論することはできません。</span><span class="sxs-lookup"><span data-stu-id="e5217-103">You cannot infer an anonymous type member name from a complex expression.</span></span>  
  
```vb  
Dim numbers() As Integer = {1, 2, 3, 4, 5}  
' Not valid.  
' Dim instanceName1 = New With {numbers(3)}  
```  
  
 <span data-ttu-id="e5217-104">匿名型がメンバーの名前および型を推定できるソースと、メンバーの名前および型を推論できないソースの詳細については、「[How to:匿名型の宣言でプロパティ名と型を推論する @ no__t-0。</span><span class="sxs-lookup"><span data-stu-id="e5217-104">For more information about sources from which anonymous types can and cannot infer member names and types, see [How to: Infer Property Names and Types in Anonymous Type Declarations](../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md).</span></span>  
  
 <span data-ttu-id="e5217-105">**エラー ID:** BC36556</span><span class="sxs-lookup"><span data-stu-id="e5217-105">**Error ID:** BC36556</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="e5217-106">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="e5217-106">To correct this error</span></span>  
  
- <span data-ttu-id="e5217-107">次のコードに示すように、式をメンバー名に割り当てます。</span><span class="sxs-lookup"><span data-stu-id="e5217-107">Assign the expression to a member name, as shown in the following code:</span></span>  
  
    ```vb  
    Dim instanceName2 = New With {.number = numbers(3)}  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="e5217-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="e5217-108">See also</span></span>

- [<span data-ttu-id="e5217-109">匿名型</span><span class="sxs-lookup"><span data-stu-id="e5217-109">Anonymous Types</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
- <span data-ttu-id="e5217-110">[2 つのオブジェクトが等しいかどうかをテストする方法匿名型の宣言でプロパティ名と型を推論する @ no__t-0</span><span class="sxs-lookup"><span data-stu-id="e5217-110">[How to: Infer Property Names and Types in Anonymous Type Declarations](../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md)</span></span>
