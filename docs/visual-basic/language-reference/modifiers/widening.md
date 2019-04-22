---
title: Widening (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.widening
helpviewer_keywords:
- conversions [Visual Basic], type
- type conversion [Visual Basic]
- conversions [Visual Basic], data type
- Widening keyword [Visual Basic]
- data type conversion [Visual Basic]
ms.assetid: 646ae263-94d3-40a2-b0cc-64f619292f56
ms.openlocfilehash: d7d43d4f5f931881d5c8b663c719fe7f92559799
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "58825314"
---
# <a name="widening-visual-basic"></a><span data-ttu-id="6affd-102">Widening (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6affd-102">Widening (Visual Basic)</span></span>
<span data-ttu-id="6affd-103">示します変換演算子 (`CType`) クラスまたは構造体を元のクラスまたは構造体のすべての値を保持できる型に変換します。</span><span class="sxs-lookup"><span data-stu-id="6affd-103">Indicates that a conversion operator (`CType`) converts a class or structure to a type that can hold all possible values of the original class or structure.</span></span>  
  
## <a name="converting-with-the-widening-keyword"></a><span data-ttu-id="6affd-104">拡大のキーワードを使用して変換します。</span><span class="sxs-lookup"><span data-stu-id="6affd-104">Converting with the Widening Keyword</span></span>  
 <span data-ttu-id="6affd-105">変換の手順を指定する必要があります`Public Shared`に加えて`Widening`します。</span><span class="sxs-lookup"><span data-stu-id="6affd-105">The conversion procedure must specify `Public Shared` in addition to `Widening`.</span></span>  
  
 <span data-ttu-id="6affd-106">拡大変換では、実行時に常に成功して、データの損失が発生することはありません。</span><span class="sxs-lookup"><span data-stu-id="6affd-106">Widening conversions always succeed at run time and never incur data loss.</span></span> <span data-ttu-id="6affd-107">例としては、`Single`に`Double`、`Char`に`String`、およびその基本型に派生型。</span><span class="sxs-lookup"><span data-stu-id="6affd-107">Examples are `Single` to `Double`, `Char` to `String`, and a derived type to its base type.</span></span> <span data-ttu-id="6affd-108">派生型が基本型のすべてのメンバーを含まれており、基本データ型のインスタンスであるため、この最後の変換が拡大します。</span><span class="sxs-lookup"><span data-stu-id="6affd-108">This last conversion is widening because the derived type contains all the members of the base type and thus is an instance of the base type.</span></span>  
  
 <span data-ttu-id="6affd-109">使用側コードが使用する必要はありません`CType`拡大変換では、たとえ`Option Strict`は`On`。</span><span class="sxs-lookup"><span data-stu-id="6affd-109">The consuming code does not have to use `CType` for widening conversions, even if `Option Strict` is `On`.</span></span>  
  
 <span data-ttu-id="6affd-110">`Widening`キーワードは、このコンテキストで使用できます。</span><span class="sxs-lookup"><span data-stu-id="6affd-110">The `Widening` keyword can be used in this context:</span></span>  
  
 [<span data-ttu-id="6affd-111">Operator ステートメント</span><span class="sxs-lookup"><span data-stu-id="6affd-111">Operator Statement</span></span>](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
 <span data-ttu-id="6affd-112">たとえばの拡大と縮小変換の演算子の定義を参照してください[方法。変換演算子を定義](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)します。</span><span class="sxs-lookup"><span data-stu-id="6affd-112">For example definitions of widening and narrowing conversion operators, see [How to: Define a Conversion Operator](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6affd-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="6affd-113">See also</span></span>

- [<span data-ttu-id="6affd-114">Operator ステートメント</span><span class="sxs-lookup"><span data-stu-id="6affd-114">Operator Statement</span></span>](../../../visual-basic/language-reference/statements/operator-statement.md)
- [<span data-ttu-id="6affd-115">Narrowing</span><span class="sxs-lookup"><span data-stu-id="6affd-115">Narrowing</span></span>](../../../visual-basic/language-reference/modifiers/narrowing.md)
- [<span data-ttu-id="6affd-116">拡大変換と縮小変換</span><span class="sxs-lookup"><span data-stu-id="6affd-116">Widening and Narrowing Conversions</span></span>](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [<span data-ttu-id="6affd-117">方法: 演算子を定義します。</span><span class="sxs-lookup"><span data-stu-id="6affd-117">How to: Define an Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [<span data-ttu-id="6affd-118">CType 関数</span><span class="sxs-lookup"><span data-stu-id="6affd-118">CType Function</span></span>](../../../visual-basic/language-reference/functions/ctype-function.md)
- [<span data-ttu-id="6affd-119">Option Strict ステートメント</span><span class="sxs-lookup"><span data-stu-id="6affd-119">Option Strict Statement</span></span>](../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [<span data-ttu-id="6affd-120">方法: 変換演算子を定義します。</span><span class="sxs-lookup"><span data-stu-id="6affd-120">How to: Define a Conversion Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)
