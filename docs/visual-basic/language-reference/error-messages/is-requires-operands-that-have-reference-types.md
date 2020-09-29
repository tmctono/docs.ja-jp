---
title: "'Is' には参照型を持つオペランドが必要ですが、このオペランドの値型は '<typename>' です。"
ms.date: 07/20/2015
f1_keywords:
- bc30020
- vbc30020
helpviewer_keywords:
- BC30020
ms.assetid: 228afebd-1203-4bd3-8d7a-c5c56f3cedc4
ms.openlocfilehash: daf9724fef81b4d7adb4f571ee950723aec09d8d
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "90873915"
---
# <a name="is-requires-operands-that-have-reference-types-but-this-operand-has-the-value-type-typename"></a><span data-ttu-id="c25da-102">'Is' には参照型を持つオペランドが必要ですが、このオペランドの値型は '\<typename>' です。</span><span class="sxs-lookup"><span data-stu-id="c25da-102">'Is' requires operands that have reference types, but this operand has the value type '\<typename>'</span></span>

<span data-ttu-id="c25da-103">`Is` 比較演算子は、2 つのオブジェクト変数が同じインスタンスを参照しているかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="c25da-103">The `Is` comparison operator determines whether two object variables refer to the same instance.</span></span> <span data-ttu-id="c25da-104">この比較は、値型に対して定義されていません。</span><span class="sxs-lookup"><span data-stu-id="c25da-104">This comparison is not defined for value types.</span></span>  
  
 <span data-ttu-id="c25da-105">**エラー ID:** BC30020</span><span class="sxs-lookup"><span data-stu-id="c25da-105">**Error ID:** BC30020</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="c25da-106">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="c25da-106">To correct this error</span></span>  
  
- <span data-ttu-id="c25da-107">適切な算術比較演算子または `Like` 演算子を使用して、2 つの値の型を比較します。</span><span class="sxs-lookup"><span data-stu-id="c25da-107">Use the appropriate arithmetic comparison operator or the `Like` operator to compare two value types.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c25da-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="c25da-108">See also</span></span>

- [<span data-ttu-id="c25da-109">Is 演算子</span><span class="sxs-lookup"><span data-stu-id="c25da-109">Is Operator</span></span>](../operators/is-operator.md)
- [<span data-ttu-id="c25da-110">Like 演算子</span><span class="sxs-lookup"><span data-stu-id="c25da-110">Like Operator</span></span>](../operators/like-operator.md)
- [<span data-ttu-id="c25da-111">比較演算子</span><span class="sxs-lookup"><span data-stu-id="c25da-111">Comparison Operators</span></span>](../operators/comparison-operators.md)
