---
title: '演算子の宣言は、のいずれかを指定する必要があります: +、-、*、-、-、^、&amp;などの Mod、Or、Xor、Not、<<>>、、<> を =、<、< =、>、> =、CType、IsTrue、または IsFalse'
ms.date: 07/20/2015
f1_keywords:
- bc33000
- vbc33000
helpviewer_keywords:
- BC33000
ms.assetid: 15c5d8eb-3a8c-4141-8f41-33151afabf97
ms.openlocfilehash: 4283547109ec312cc4fe07a054bbb8db3bff660f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59299190"
---
# <a name="operator-declaration-must-be-one-of----amp-like-mod-and-or-xor-not--"></a><span data-ttu-id="f5017-102">演算子の宣言は、のいずれかを指定する必要があります: +、-、\*、\,/、^、&amp;などの Mod、Or、Xor、Not、 \< \<、>>.</span><span class="sxs-lookup"><span data-stu-id="f5017-102">Operator declaration must be one of:  +,-,\*,\,/,^, &amp;, Like, Mod, And, Or, Xor, Not, \<\<, >>...</span></span>
<span data-ttu-id="f5017-103">オーバー ロードできるは、演算子のみを宣言できます。</span><span class="sxs-lookup"><span data-stu-id="f5017-103">You can declare only an operator that is eligible for overloading.</span></span> <span data-ttu-id="f5017-104">次の表は、演算子を宣言することができます。</span><span class="sxs-lookup"><span data-stu-id="f5017-104">The following table lists the operators you can declare.</span></span>  
  
|<span data-ttu-id="f5017-105">型</span><span class="sxs-lookup"><span data-stu-id="f5017-105">Type</span></span>|<span data-ttu-id="f5017-106">演算子</span><span class="sxs-lookup"><span data-stu-id="f5017-106">Operators</span></span>|  
|----------|---------------|  
|<span data-ttu-id="f5017-107">単項</span><span class="sxs-lookup"><span data-stu-id="f5017-107">Unary</span></span>|<span data-ttu-id="f5017-108">`+`, `-`, `IsFalse`, `IsTrue`, `Not`</span><span class="sxs-lookup"><span data-stu-id="f5017-108">`+`, `-`, `IsFalse`, `IsTrue`, `Not`</span></span>|  
|<span data-ttu-id="f5017-109">2 項</span><span class="sxs-lookup"><span data-stu-id="f5017-109">Binary</span></span>|<span data-ttu-id="f5017-110">`+`, `-`, `*`, `/`, `\`, `&`, `^`, `>>`, `<<`, `=`, `<>`, `>`, `>=`, `<`, `<=`, `And`, `Like`, `Mod`, `Or`, `Xor`</span><span class="sxs-lookup"><span data-stu-id="f5017-110">`+`, `-`, `*`, `/`, `\`, `&`, `^`, `>>`, `<<`, `=`, `<>`, `>`, `>=`, `<`, `<=`, `And`, `Like`, `Mod`, `Or`, `Xor`</span></span>|  
|<span data-ttu-id="f5017-111">変換 (単項)</span><span class="sxs-lookup"><span data-stu-id="f5017-111">Conversion (unary)</span></span>|`CType`|  
  
 <span data-ttu-id="f5017-112">なお、`=`バイナリの一覧で演算子は、比較演算子、代入演算子ではありません。</span><span class="sxs-lookup"><span data-stu-id="f5017-112">Note that the `=` operator in the binary list is the comparison operator, not the assignment operator.</span></span>  
  
 <span data-ttu-id="f5017-113">**エラー ID:** BC33000</span><span class="sxs-lookup"><span data-stu-id="f5017-113">**Error ID:** BC33000</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="f5017-114">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="f5017-114">To correct this error</span></span>  
  
1. <span data-ttu-id="f5017-115">演算子をオーバーロード可能な演算子の中から選択します。</span><span class="sxs-lookup"><span data-stu-id="f5017-115">Select an operator from the set of overloadable operators.</span></span>  
  
2. <span data-ttu-id="f5017-116">直接オーバーロードできない演算子をオーバーロードする機能が必要な場合は、適切なパラメーターを受け取り適切な値を返す `Function` プロシージャを作成します。</span><span class="sxs-lookup"><span data-stu-id="f5017-116">If you need the functionality of overloading an operator that you cannot overload directly, create a `Function` procedure that takes the appropriate parameters and returns the appropriate value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5017-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="f5017-117">See also</span></span>

- [<span data-ttu-id="f5017-118">Operator ステートメント</span><span class="sxs-lookup"><span data-stu-id="f5017-118">Operator Statement</span></span>](../../../visual-basic/language-reference/statements/operator-statement.md)
- [<span data-ttu-id="f5017-119">演算子プロシージャ</span><span class="sxs-lookup"><span data-stu-id="f5017-119">Operator Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)
- [<span data-ttu-id="f5017-120">方法: 演算子を定義します。</span><span class="sxs-lookup"><span data-stu-id="f5017-120">How to: Define an Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [<span data-ttu-id="f5017-121">方法: 変換演算子を定義します。</span><span class="sxs-lookup"><span data-stu-id="f5017-121">How to: Define a Conversion Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)
- [<span data-ttu-id="f5017-122">Function ステートメント</span><span class="sxs-lookup"><span data-stu-id="f5017-122">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)
