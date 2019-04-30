---
title: オーバーフローしました。(Visual Basic ランタイム エラー)
ms.date: 07/20/2015
f1_keywords:
- vbrERRID_Overflow
ms.assetid: c6a23279-3086-412a-bcff-ff8ed2cb8c6f
ms.openlocfilehash: 63223a815e1c4ff8d4e0afbb6c732fff90aad465
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61946550"
---
# <a name="overflow-visual-basic-run-time-error"></a><span data-ttu-id="a1f40-102">オーバーフローしました。(Visual Basic ランタイム エラー)</span><span class="sxs-lookup"><span data-stu-id="a1f40-102">Overflow (Visual Basic Run-Time Error)</span></span>
<span data-ttu-id="a1f40-103">割り当てのターゲットの制限を超える割り当てしようとしたときに、オーバーフローが発生します。</span><span class="sxs-lookup"><span data-stu-id="a1f40-103">An overflow results when you attempt an assignment that exceeds the limits of the assignment's target.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="a1f40-104">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="a1f40-104">To correct this error</span></span>  
  
1. <span data-ttu-id="a1f40-105">値の範囲が広いを割り当て、計算、およびデータ型変換が変数の値、その型の許容範囲内で表現するのには大きすぎないと型の変数に値を代入の結果が保持できることを確認します。、必要な場合。</span><span class="sxs-lookup"><span data-stu-id="a1f40-105">Make sure that results of assignments, calculations, and data type conversions are not too large to be represented within the range of variables allowed for that type of value, and assign the value to a variable of a type that can hold a larger range of values, if necessary.</span></span>  
  
2. <span data-ttu-id="a1f40-106">プロパティへの割り当てが行われるプロパティの範囲を合わせることを確認します。</span><span class="sxs-lookup"><span data-stu-id="a1f40-106">Make sure assignments to properties fit the range of the property to which they are made.</span></span>  
  
3. <span data-ttu-id="a1f40-107">整数に変換する計算で使用される数値の整数より大きい結果がないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="a1f40-107">Make sure that numbers used in calculations that are coerced into integers do not have results larger than integers.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1f40-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="a1f40-108">See also</span></span>

- <xref:System.Int32.MaxValue?displayProperty=nameWithType>
- <xref:System.Double.MaxValue?displayProperty=nameWithType>
- [<span data-ttu-id="a1f40-109">データの種類</span><span class="sxs-lookup"><span data-stu-id="a1f40-109">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="a1f40-110">エラーの種類</span><span class="sxs-lookup"><span data-stu-id="a1f40-110">Error Types</span></span>](../../../visual-basic/programming-guide/language-features/error-types.md)
