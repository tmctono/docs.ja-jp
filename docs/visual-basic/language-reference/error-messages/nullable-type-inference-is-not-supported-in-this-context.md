---
title: Null 許容型の推論はこのコンテキストではサポートされていません
ms.date: 07/20/2015
f1_keywords:
- vbc36629
- bc36629
helpviewer_keywords:
- BC36629
ms.assetid: 0a1e2dbc-d9a4-433d-9306-c5540782b81d
ms.openlocfilehash: 52e5391fbcf30a4dada4d64a0e810c900ea85806
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409388"
---
# <a name="nullable-type-inference-is-not-supported-in-this-context"></a><span data-ttu-id="c6eba-102">Null 許容型の推論はこのコンテキストではサポートされていません</span><span class="sxs-lookup"><span data-stu-id="c6eba-102">Nullable type inference is not supported in this context</span></span>
<span data-ttu-id="c6eba-103">値の型と構造体は、Null 許容と宣言できます。</span><span class="sxs-lookup"><span data-stu-id="c6eba-103">Value types and structures can be declared nullable.</span></span>  
  
```vb  
Dim a? As Integer  
Dim b As Integer?  
```  
  
 <span data-ttu-id="c6eba-104">ただし、Null 許容の宣言を型の推定と組み合わせて使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="c6eba-104">However, you cannot use the nullable declaration in combination with type inference.</span></span> <span data-ttu-id="c6eba-105">次の例では、このエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="c6eba-105">The following examples cause this error.</span></span>  
  
```vb  
' Not valid.  
' Dim c? = 10  
' Dim d? = a  
```  
  
 <span data-ttu-id="c6eba-106">**エラー ID:** BC36629</span><span class="sxs-lookup"><span data-stu-id="c6eba-106">**Error ID:** BC36629</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="c6eba-107">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="c6eba-107">To correct this error</span></span>  
  
- <span data-ttu-id="c6eba-108">`As` 句を使用して、変数を null 許容値型として宣言します。</span><span class="sxs-lookup"><span data-stu-id="c6eba-108">Use an `As` clause to declare the variable as a nullable value type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6eba-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="c6eba-109">See also</span></span>

- [<span data-ttu-id="c6eba-110">null 許容値型</span><span class="sxs-lookup"><span data-stu-id="c6eba-110">Nullable Value Types</span></span>](../../programming-guide/language-features/data-types/nullable-value-types.md)
- [<span data-ttu-id="c6eba-111">ローカル型の推論</span><span class="sxs-lookup"><span data-stu-id="c6eba-111">Local Type Inference</span></span>](../../programming-guide/language-features/variables/local-type-inference.md)
