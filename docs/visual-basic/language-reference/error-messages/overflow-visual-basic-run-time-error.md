---
title: オーバーフローしました。(Visual Basic ランタイム エラー)
ms.date: 07/20/2015
f1_keywords:
- vbrERRID_Overflow
ms.assetid: c6a23279-3086-412a-bcff-ff8ed2cb8c6f
ms.openlocfilehash: e287d6c24eca75d8bf20181a201056f467d6fc4e
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "90871217"
---
# <a name="overflow-visual-basic-run-time-error"></a><span data-ttu-id="4e5d1-102">オーバーフローしました。(Visual Basic ランタイム エラー)</span><span class="sxs-lookup"><span data-stu-id="4e5d1-102">Overflow (Visual Basic Run-Time Error)</span></span>

<span data-ttu-id="4e5d1-103">代入の対象の制限を超える代入を試みると、オーバーフローが発生します。</span><span class="sxs-lookup"><span data-stu-id="4e5d1-103">An overflow results when you attempt an assignment that exceeds the limits of the assignment's target.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="4e5d1-104">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="4e5d1-104">To correct this error</span></span>  
  
1. <span data-ttu-id="4e5d1-105">代入、計算、およびデータ型の変換の結果が、その型の値に対して許可されている変数の範囲内で表すには大きすぎないことを確認し、必要に応じて、より大きな値の範囲を保持できる型の変数に値を代入します。</span><span class="sxs-lookup"><span data-stu-id="4e5d1-105">Make sure that results of assignments, calculations, and data type conversions are not too large to be represented within the range of variables allowed for that type of value, and assign the value to a variable of a type that can hold a larger range of values, if necessary.</span></span>  
  
2. <span data-ttu-id="4e5d1-106">プロパティへの代入が、代入先のプロパティの範囲に適合することを確認します。</span><span class="sxs-lookup"><span data-stu-id="4e5d1-106">Make sure assignments to properties fit the range of the property to which they are made.</span></span>  
  
3. <span data-ttu-id="4e5d1-107">整数に強制的に変換される計算で使用される数値に、整数よりも大きな結果がないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="4e5d1-107">Make sure that numbers used in calculations that are coerced into integers do not have results larger than integers.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e5d1-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="4e5d1-108">See also</span></span>

- <xref:System.Int32.MaxValue?displayProperty=nameWithType>
- <xref:System.Double.MaxValue?displayProperty=nameWithType>
- [<span data-ttu-id="4e5d1-109">データの種類</span><span class="sxs-lookup"><span data-stu-id="4e5d1-109">Data Types</span></span>](../data-types/index.md)
- [<span data-ttu-id="4e5d1-110">エラーの種類</span><span class="sxs-lookup"><span data-stu-id="4e5d1-110">Error Types</span></span>](../../programming-guide/language-features/error-types.md)
