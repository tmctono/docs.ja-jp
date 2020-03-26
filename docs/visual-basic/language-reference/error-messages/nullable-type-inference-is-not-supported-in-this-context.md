---
title: Null 許容型の推論はこのコンテキストではサポートされていません
ms.date: 07/20/2015
f1_keywords:
- vbc36629
- bc36629
helpviewer_keywords:
- BC36629
ms.assetid: 0a1e2dbc-d9a4-433d-9306-c5540782b81d
ms.openlocfilehash: 42bde0b1843e52bbc16118bb056ade791591904e
ms.sourcegitcommit: 99b153b93bf94d0fecf7c7bcecb58ac424dfa47c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2020
ms.locfileid: "80249501"
---
# <a name="nullable-type-inference-is-not-supported-in-this-context"></a><span data-ttu-id="d3f85-102">Null 許容型の推論はこのコンテキストではサポートされていません</span><span class="sxs-lookup"><span data-stu-id="d3f85-102">Nullable type inference is not supported in this context</span></span>
<span data-ttu-id="d3f85-103">値型と構造体は null 許容として宣言できます。</span><span class="sxs-lookup"><span data-stu-id="d3f85-103">Value types and structures can be declared nullable.</span></span>  
  
```vb  
Dim a? As Integer  
Dim b As Integer?  
```  
  
 <span data-ttu-id="d3f85-104">ただし、null 許容宣言と型の推論を組み合わせて使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="d3f85-104">However, you cannot use the nullable declaration in combination with type inference.</span></span> <span data-ttu-id="d3f85-105">次の例では、このエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="d3f85-105">The following examples cause this error.</span></span>  
  
```vb  
' Not valid.  
' Dim c? = 10  
' Dim d? = a  
```  
  
 <span data-ttu-id="d3f85-106">**エラー ID:** BC36629</span><span class="sxs-lookup"><span data-stu-id="d3f85-106">**Error ID:** BC36629</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="d3f85-107">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="d3f85-107">To correct this error</span></span>  
  
- <span data-ttu-id="d3f85-108">変数を`As`null 許容値型として宣言するには、句を使用します。</span><span class="sxs-lookup"><span data-stu-id="d3f85-108">Use an `As` clause to declare the variable as a nullable value type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3f85-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="d3f85-109">See also</span></span>

- [<span data-ttu-id="d3f85-110">null 許容値型</span><span class="sxs-lookup"><span data-stu-id="d3f85-110">Nullable Value Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
- [<span data-ttu-id="d3f85-111">ローカル型の推論</span><span class="sxs-lookup"><span data-stu-id="d3f85-111">Local Type Inference</span></span>](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
