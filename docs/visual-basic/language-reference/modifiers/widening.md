---
title: Widening
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
ms.openlocfilehash: 1c9aa78549ca6e41c9fe54c12e0aaec8e7cc30cb
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347831"
---
# <a name="widening-visual-basic"></a><span data-ttu-id="357fd-102">Widening (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="357fd-102">Widening (Visual Basic)</span></span>
<span data-ttu-id="357fd-103">変換演算子 (`CType`) が、クラスまたは構造体を、元のクラスまたは構造体のすべての可能な値を保持できる型に変換することを示します。</span><span class="sxs-lookup"><span data-stu-id="357fd-103">Indicates that a conversion operator (`CType`) converts a class or structure to a type that can hold all possible values of the original class or structure.</span></span>  
  
## <a name="converting-with-the-widening-keyword"></a><span data-ttu-id="357fd-104">拡大キーワードを使用した変換</span><span class="sxs-lookup"><span data-stu-id="357fd-104">Converting with the Widening Keyword</span></span>  
 <span data-ttu-id="357fd-105">変換プロシージャでは、`Widening`に加えて `Public Shared` を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="357fd-105">The conversion procedure must specify `Public Shared` in addition to `Widening`.</span></span>  
  
 <span data-ttu-id="357fd-106">拡大変換は実行時に常に成功し、データ損失は発生しません。</span><span class="sxs-lookup"><span data-stu-id="357fd-106">Widening conversions always succeed at run time and never incur data loss.</span></span> <span data-ttu-id="357fd-107">例として、`Double`、`Char` `String`、および派生型から基本型への `Single` があります。</span><span class="sxs-lookup"><span data-stu-id="357fd-107">Examples are `Single` to `Double`, `Char` to `String`, and a derived type to its base type.</span></span> <span data-ttu-id="357fd-108">この最後の変換は、派生型に基本型のすべてのメンバーが含まれているため、拡張されます。したがって、は基本型のインスタンスです。</span><span class="sxs-lookup"><span data-stu-id="357fd-108">This last conversion is widening because the derived type contains all the members of the base type and thus is an instance of the base type.</span></span>  
  
 <span data-ttu-id="357fd-109">`Option Strict` が `On`場合でも、使用しているコードでは、拡大変換に `CType` を使用する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="357fd-109">The consuming code does not have to use `CType` for widening conversions, even if `Option Strict` is `On`.</span></span>  
  
 <span data-ttu-id="357fd-110">このコンテキストでは、`Widening` キーワードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="357fd-110">The `Widening` keyword can be used in this context:</span></span>  
  
 [<span data-ttu-id="357fd-111">Operator ステートメント</span><span class="sxs-lookup"><span data-stu-id="357fd-111">Operator Statement</span></span>](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
 <span data-ttu-id="357fd-112">拡大変換と縮小変換演算子の定義の例については、「[方法: 変換演算子を定義](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="357fd-112">For example definitions of widening and narrowing conversion operators, see [How to: Define a Conversion Operator](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="357fd-113">参照</span><span class="sxs-lookup"><span data-stu-id="357fd-113">See also</span></span>

- [<span data-ttu-id="357fd-114">Operator ステートメント</span><span class="sxs-lookup"><span data-stu-id="357fd-114">Operator Statement</span></span>](../../../visual-basic/language-reference/statements/operator-statement.md)
- [<span data-ttu-id="357fd-115">Narrowing</span><span class="sxs-lookup"><span data-stu-id="357fd-115">Narrowing</span></span>](../../../visual-basic/language-reference/modifiers/narrowing.md)
- [<span data-ttu-id="357fd-116">拡大変換と縮小変換</span><span class="sxs-lookup"><span data-stu-id="357fd-116">Widening and Narrowing Conversions</span></span>](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [<span data-ttu-id="357fd-117">方法 : 演算子を定義する</span><span class="sxs-lookup"><span data-stu-id="357fd-117">How to: Define an Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [<span data-ttu-id="357fd-118">CType Function</span><span class="sxs-lookup"><span data-stu-id="357fd-118">CType Function</span></span>](../../../visual-basic/language-reference/functions/ctype-function.md)
- [<span data-ttu-id="357fd-119">Option Strict ステートメント</span><span class="sxs-lookup"><span data-stu-id="357fd-119">Option Strict Statement</span></span>](../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [<span data-ttu-id="357fd-120">方法 : 変換演算子を定義する</span><span class="sxs-lookup"><span data-stu-id="357fd-120">How to: Define a Conversion Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)
