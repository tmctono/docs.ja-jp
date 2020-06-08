---
title: ParamArray
ms.date: 07/20/2015
f1_keywords:
- vb.ParamArray
- ParamArray
helpviewer_keywords:
- ParamArray keyword [Visual Basic]
- ParamArray keyword [Visual Basic], syntax
ms.assetid: a5f18789-92bd-488f-9c7e-cf3719963635
ms.openlocfilehash: e3c24818ea87884a0dd9b42c604e13e16ca6d3d7
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2020
ms.locfileid: "84391821"
---
# <a name="paramarray-visual-basic"></a><span data-ttu-id="4d93f-102">ParamArray (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4d93f-102">ParamArray (Visual Basic)</span></span>
<span data-ttu-id="4d93f-103">プロシージャのパラメーターが、指定された型の、省略可能な要素の配列を受け取ることを示します。</span><span class="sxs-lookup"><span data-stu-id="4d93f-103">Specifies that a procedure parameter takes an optional array of elements of the specified type.</span></span> <span data-ttu-id="4d93f-104">`ParamArray` は、パラメーター リストの最後のパラメーターでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="4d93f-104">`ParamArray` can be used only on the last parameter of a parameter list.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4d93f-105">Remarks</span><span class="sxs-lookup"><span data-stu-id="4d93f-105">Remarks</span></span>  
 <span data-ttu-id="4d93f-106">`ParamArray` により、プロシージャに任意の数の引数を渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="4d93f-106">`ParamArray` allows you to pass an arbitrary number of arguments to the procedure.</span></span> <span data-ttu-id="4d93f-107">`ParamArray` パラメーターは常に、[ByVal](byval.md) を使用して宣言します。</span><span class="sxs-lookup"><span data-stu-id="4d93f-107">A `ParamArray` parameter is always declared using [ByVal](byval.md).</span></span>  
  
 <span data-ttu-id="4d93f-108">適切なデータ型の配列やコンマ区切りの値のリストを渡すか、または何も渡さないで、`ParamArray` パラメーターに 1 つ以上の引数を指定することができます。</span><span class="sxs-lookup"><span data-stu-id="4d93f-108">You can supply one or more arguments to a `ParamArray` parameter by passing an array of the appropriate data type, a comma-separated list of values, or nothing at all.</span></span> <span data-ttu-id="4d93f-109">詳細については、「[パラメーター配列](../../programming-guide/language-features/procedures/parameter-arrays.md)」の「ParamArray の呼び出し」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4d93f-109">For details, see "Calling a ParamArray" in [Parameter Arrays](../../programming-guide/language-features/procedures/parameter-arrays.md).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="4d93f-110">無限に大きくなる可能性がある配列を処理する場合は常に、アプリケーションの何らかの内部容量が超過するリスクがあります。</span><span class="sxs-lookup"><span data-stu-id="4d93f-110">Whenever you deal with an array which can be indefinitely large, there is a risk of overrunning some internal capacity of your application.</span></span> <span data-ttu-id="4d93f-111">呼び出し元のコードからパラメーター配列を受け取る場合は、その長さをテストし、それがアプリケーションに大きすぎる場合は、適切なステップを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4d93f-111">If you accept a parameter array from the calling code, you should test its length and take appropriate steps if it is too large for your application.</span></span>  
  
 <span data-ttu-id="4d93f-112">`ParamArray` 修飾子は、次のコンテキストで使用できます。</span><span class="sxs-lookup"><span data-stu-id="4d93f-112">The `ParamArray` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="4d93f-113">Declare ステートメント</span><span class="sxs-lookup"><span data-stu-id="4d93f-113">Declare Statement</span></span>](../statements/declare-statement.md)  
  
 [<span data-ttu-id="4d93f-114">Function ステートメント</span><span class="sxs-lookup"><span data-stu-id="4d93f-114">Function Statement</span></span>](../statements/function-statement.md)  
  
 [<span data-ttu-id="4d93f-115">Property ステートメント</span><span class="sxs-lookup"><span data-stu-id="4d93f-115">Property Statement</span></span>](../statements/property-statement.md)  
  
 [<span data-ttu-id="4d93f-116">Sub ステートメント</span><span class="sxs-lookup"><span data-stu-id="4d93f-116">Sub Statement</span></span>](../statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="4d93f-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="4d93f-117">See also</span></span>

- [<span data-ttu-id="4d93f-118">キーワード</span><span class="sxs-lookup"><span data-stu-id="4d93f-118">Keywords</span></span>](../keywords/index.md)
- [<span data-ttu-id="4d93f-119">パラメーター配列</span><span class="sxs-lookup"><span data-stu-id="4d93f-119">Parameter Arrays</span></span>](../../programming-guide/language-features/procedures/parameter-arrays.md)
