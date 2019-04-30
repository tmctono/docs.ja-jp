---
title: ParamArray (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.ParamArray
- ParamArray
helpviewer_keywords:
- ParamArray keyword [Visual Basic]
- ParamArray keyword [Visual Basic], syntax
ms.assetid: a5f18789-92bd-488f-9c7e-cf3719963635
ms.openlocfilehash: b9dee0fc876c6e7a02d085db7db4bf1c5dd2c68d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62053913"
---
# <a name="paramarray-visual-basic"></a><span data-ttu-id="ec6b9-102">ParamArray (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ec6b9-102">ParamArray (Visual Basic)</span></span>
<span data-ttu-id="ec6b9-103">プロシージャのパラメーターが指定した型の要素の省略可能な配列を受け取ることを指定します。</span><span class="sxs-lookup"><span data-stu-id="ec6b9-103">Specifies that a procedure parameter takes an optional array of elements of the specified type.</span></span> <span data-ttu-id="ec6b9-104">`ParamArray` パラメーター リストの最後のパラメーターでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="ec6b9-104">`ParamArray` can be used only on the last parameter of a parameter list.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ec6b9-105">Remarks</span><span class="sxs-lookup"><span data-stu-id="ec6b9-105">Remarks</span></span>  
 <span data-ttu-id="ec6b9-106">`ParamArray` プロシージャに任意の数の引数を渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="ec6b9-106">`ParamArray` allows you to pass an arbitrary number of arguments to the procedure.</span></span> <span data-ttu-id="ec6b9-107">A`ParamArray`を使用してパラメーターが常に宣言[ByVal](../../../visual-basic/language-reference/modifiers/byval.md)します。</span><span class="sxs-lookup"><span data-stu-id="ec6b9-107">A `ParamArray` parameter is always declared using [ByVal](../../../visual-basic/language-reference/modifiers/byval.md).</span></span>  
  
 <span data-ttu-id="ec6b9-108">1 つまたは複数の引数を指定できます、`ParamArray`適切なデータの配列を渡すことによってパラメーターの型、値、または何ものコンマ区切りの一覧にします。</span><span class="sxs-lookup"><span data-stu-id="ec6b9-108">You can supply one or more arguments to a `ParamArray` parameter by passing an array of the appropriate data type, a comma-separated list of values, or nothing at all.</span></span> <span data-ttu-id="ec6b9-109">詳細については、"呼び出しを ParamArray"を参照してください[パラメーター配列](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md)します。</span><span class="sxs-lookup"><span data-stu-id="ec6b9-109">For details, see "Calling a ParamArray" in [Parameter Arrays](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="ec6b9-110">無限に増大することができる配列を処理するたびに、アプリケーションの内部の容量を超過してしまう可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ec6b9-110">Whenever you deal with an array which can be indefinitely large, there is a risk of overrunning some internal capacity of your application.</span></span> <span data-ttu-id="ec6b9-111">呼び出し元のコードからパラメーターの配列を受け取る場合その長さをテスト、アプリケーションが大きすぎる場合は、適切な手順を実行してください。</span><span class="sxs-lookup"><span data-stu-id="ec6b9-111">If you accept a parameter array from the calling code, you should test its length and take appropriate steps if it is too large for your application.</span></span>  
  
 <span data-ttu-id="ec6b9-112">`ParamArray` 修飾子は、次のコンテキストで使用できます。</span><span class="sxs-lookup"><span data-stu-id="ec6b9-112">The `ParamArray` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="ec6b9-113">Declare ステートメント</span><span class="sxs-lookup"><span data-stu-id="ec6b9-113">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [<span data-ttu-id="ec6b9-114">Function ステートメント</span><span class="sxs-lookup"><span data-stu-id="ec6b9-114">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="ec6b9-115">Property ステートメント</span><span class="sxs-lookup"><span data-stu-id="ec6b9-115">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="ec6b9-116">Sub ステートメント</span><span class="sxs-lookup"><span data-stu-id="ec6b9-116">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="ec6b9-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="ec6b9-117">See also</span></span>

- [<span data-ttu-id="ec6b9-118">キーワード</span><span class="sxs-lookup"><span data-stu-id="ec6b9-118">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
- [<span data-ttu-id="ec6b9-119">パラメーター配列</span><span class="sxs-lookup"><span data-stu-id="ec6b9-119">Parameter Arrays</span></span>](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md)
