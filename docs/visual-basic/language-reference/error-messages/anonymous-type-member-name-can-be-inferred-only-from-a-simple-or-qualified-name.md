---
title: 匿名型メンバーの名前は、引数なしの簡易名または修飾名からのみ推論できます
ms.date: 07/20/2015
f1_keywords:
- vbc36556
- bc36556
helpviewer_keywords:
- BC36556
ms.assetid: e3ba1f33-3a71-4f03-9b04-ed5ec17de17c
ms.openlocfilehash: f657048a8aa9748104e40503e727a5e6d90a87ad
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64646856"
---
# <a name="anonymous-type-member-name-can-be-inferred-only-from-a-simple-or-qualified-name-with-no-arguments"></a><span data-ttu-id="96354-102">匿名型メンバーの名前は、引数なしの簡易名または修飾名からのみ推論できます</span><span class="sxs-lookup"><span data-stu-id="96354-102">Anonymous type member name can be inferred only from a simple or qualified name with no arguments</span></span>
<span data-ttu-id="96354-103">複雑な式から匿名型メンバーの名前を推論することはできません。</span><span class="sxs-lookup"><span data-stu-id="96354-103">You cannot infer an anonymous type member name from a complex expression.</span></span>  
  
```vb  
Dim numbers() As Integer = {1, 2, 3, 4, 5}  
' Not valid.  
' Dim instanceName1 = New With {numbers(3)}  
```  
  
 <span data-ttu-id="96354-104">ソースから匿名型ができ、メンバーの名前と型を推論することはできませんの詳細については、次を参照してください。[方法。匿名型の宣言におけるプロパティ名と型を推論](../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md)します。</span><span class="sxs-lookup"><span data-stu-id="96354-104">For more information about sources from which anonymous types can and cannot infer member names and types, see [How to: Infer Property Names and Types in Anonymous Type Declarations](../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md).</span></span>  
  
 <span data-ttu-id="96354-105">**エラー ID:** BC36556</span><span class="sxs-lookup"><span data-stu-id="96354-105">**Error ID:** BC36556</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="96354-106">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="96354-106">To correct this error</span></span>  
  
- <span data-ttu-id="96354-107">次のコードに示すように、メンバー名に式を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="96354-107">Assign the expression to a member name, as shown in the following code:</span></span>  
  
    ```  
    Dim instanceName2 = New With {.number = numbers(3)}  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="96354-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="96354-108">See also</span></span>

- [<span data-ttu-id="96354-109">匿名型</span><span class="sxs-lookup"><span data-stu-id="96354-109">Anonymous Types</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
- [<span data-ttu-id="96354-110">方法: 匿名型の宣言におけるプロパティ名と型を推論します。</span><span class="sxs-lookup"><span data-stu-id="96354-110">How to: Infer Property Names and Types in Anonymous Type Declarations</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md)
