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
ms.openlocfilehash: 8fc5d1afd9e9723e6b3c58e100b0519ef8fdfab4
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69968364"
---
# <a name="paramarray-visual-basic"></a><span data-ttu-id="5f78a-102">ParamArray (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5f78a-102">ParamArray (Visual Basic)</span></span>
<span data-ttu-id="5f78a-103">プロシージャパラメーターが、指定された型の要素のオプションの配列を受け取ることを指定します。</span><span class="sxs-lookup"><span data-stu-id="5f78a-103">Specifies that a procedure parameter takes an optional array of elements of the specified type.</span></span> <span data-ttu-id="5f78a-104">`ParamArray`は、パラメーターリストの最後のパラメーターでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="5f78a-104">`ParamArray` can be used only on the last parameter of a parameter list.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5f78a-105">Remarks</span><span class="sxs-lookup"><span data-stu-id="5f78a-105">Remarks</span></span>  
 <span data-ttu-id="5f78a-106">`ParamArray`プロシージャに任意の数の引数を渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="5f78a-106">`ParamArray` allows you to pass an arbitrary number of arguments to the procedure.</span></span> <span data-ttu-id="5f78a-107">パラメーターは常に [ByVal](../../../visual-basic/language-reference/modifiers/byval.md) を使用して宣言されます。`ParamArray`</span><span class="sxs-lookup"><span data-stu-id="5f78a-107">A `ParamArray` parameter is always declared using [ByVal](../../../visual-basic/language-reference/modifiers/byval.md).</span></span>  
  
 <span data-ttu-id="5f78a-108">適切なデータ型の配列、コンマ区切り`ParamArray`の値のリスト、または何も指定しないで、パラメーターに1つ以上の引数を渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="5f78a-108">You can supply one or more arguments to a `ParamArray` parameter by passing an array of the appropriate data type, a comma-separated list of values, or nothing at all.</span></span> <span data-ttu-id="5f78a-109">詳細については、「[パラメーター配列](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md)」の「ParamArray の呼び出し」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5f78a-109">For details, see "Calling a ParamArray" in [Parameter Arrays](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="5f78a-110">無限に大きくなる可能性がある配列を処理する場合、アプリケーションの内部容量がオーバーランするリスクがあります。</span><span class="sxs-lookup"><span data-stu-id="5f78a-110">Whenever you deal with an array which can be indefinitely large, there is a risk of overrunning some internal capacity of your application.</span></span> <span data-ttu-id="5f78a-111">呼び出し元のコードからパラメーター配列を受け取る場合は、その長さをテストし、アプリケーションにとって大きすぎる場合は適切な手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5f78a-111">If you accept a parameter array from the calling code, you should test its length and take appropriate steps if it is too large for your application.</span></span>  
  
 <span data-ttu-id="5f78a-112">`ParamArray` 修飾子は、次のコンテキストで使用できます。</span><span class="sxs-lookup"><span data-stu-id="5f78a-112">The `ParamArray` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="5f78a-113">Declare ステートメント</span><span class="sxs-lookup"><span data-stu-id="5f78a-113">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [<span data-ttu-id="5f78a-114">Function ステートメント</span><span class="sxs-lookup"><span data-stu-id="5f78a-114">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="5f78a-115">Property ステートメント</span><span class="sxs-lookup"><span data-stu-id="5f78a-115">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="5f78a-116">Sub ステートメント</span><span class="sxs-lookup"><span data-stu-id="5f78a-116">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="5f78a-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="5f78a-117">See also</span></span>

- [<span data-ttu-id="5f78a-118">キーワード</span><span class="sxs-lookup"><span data-stu-id="5f78a-118">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
- [<span data-ttu-id="5f78a-119">パラメーター配列</span><span class="sxs-lookup"><span data-stu-id="5f78a-119">Parameter Arrays</span></span>](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md)
