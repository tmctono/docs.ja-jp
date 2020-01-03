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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61946602"
---
# <a name="operator-declaration-must-be-one-of----amp-like-mod-and-or-xor-not--"></a><span data-ttu-id="93c9a-102">演算子の宣言は、のいずれかを指定する必要があります: +、-、\*、\,/、^、&amp;などの Mod、Or、Xor、Not、 \< \<、>>.</span><span class="sxs-lookup"><span data-stu-id="93c9a-102">Operator declaration must be one of:  +,-,\*,\,/,^, &amp;, Like, Mod, And, Or, Xor, Not, \<\<, >>...</span></span>
<span data-ttu-id="93c9a-103">オーバー ロードできるは、演算子のみを宣言できます。</span><span class="sxs-lookup"><span data-stu-id="93c9a-103">You can declare only an operator that is eligible for overloading.</span></span> <span data-ttu-id="93c9a-104">次の表は、演算子を宣言することができます。</span><span class="sxs-lookup"><span data-stu-id="93c9a-104">The following table lists the operators you can declare.</span></span>  
  
|<span data-ttu-id="93c9a-105">型</span><span class="sxs-lookup"><span data-stu-id="93c9a-105">Type</span></span>|<span data-ttu-id="93c9a-106">演算子</span><span class="sxs-lookup"><span data-stu-id="93c9a-106">Operators</span></span>|  
|----------|---------------|  
|<span data-ttu-id="93c9a-107">単項</span><span class="sxs-lookup"><span data-stu-id="93c9a-107">Unary</span></span>|<span data-ttu-id="93c9a-108">`+`, `-`, `IsFalse`, `IsTrue`, `Not`</span><span class="sxs-lookup"><span data-stu-id="93c9a-108">`+`, `-`, `IsFalse`, `IsTrue`, `Not`</span></span>|  
|<span data-ttu-id="93c9a-109">2 項</span><span class="sxs-lookup"><span data-stu-id="93c9a-109">Binary</span></span>|<span data-ttu-id="93c9a-110">`+`, `-`, `*`, `/`, `\`, `&`, `^`, `>>`, `<<`, `=`, `<>`, `>`, `>=`, `<`, `<=`, `And`, `Like`, `Mod`, `Or`, `Xor`</span><span class="sxs-lookup"><span data-stu-id="93c9a-110">`+`, `-`, `*`, `/`, `\`, `&`, `^`, `>>`, `<<`, `=`, `<>`, `>`, `>=`, `<`, `<=`, `And`, `Like`, `Mod`, `Or`, `Xor`</span></span>|  
|<span data-ttu-id="93c9a-111">変換 (単項)</span><span class="sxs-lookup"><span data-stu-id="93c9a-111">Conversion (unary)</span></span>|`CType`|  
  
 <span data-ttu-id="93c9a-112">なお、`=`バイナリの一覧で演算子は、比較演算子、代入演算子ではありません。</span><span class="sxs-lookup"><span data-stu-id="93c9a-112">Note that the `=` operator in the binary list is the comparison operator, not the assignment operator.</span></span>  
  
 <span data-ttu-id="93c9a-113">**エラー ID:** BC33000</span><span class="sxs-lookup"><span data-stu-id="93c9a-113">**Error ID:** BC33000</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="93c9a-114">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="93c9a-114">To correct this error</span></span>  
  
1. <span data-ttu-id="93c9a-115">演算子をオーバーロード可能な演算子の中から選択します。</span><span class="sxs-lookup"><span data-stu-id="93c9a-115">Select an operator from the set of overloadable operators.</span></span>  
  
2. <span data-ttu-id="93c9a-116">直接オーバーロードできない演算子をオーバーロードする機能が必要な場合は、適切なパラメーターを受け取り適切な値を返す `Function` プロシージャを作成します。</span><span class="sxs-lookup"><span data-stu-id="93c9a-116">If you need the functionality of overloading an operator that you cannot overload directly, create a `Function` procedure that takes the appropriate parameters and returns the appropriate value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93c9a-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="93c9a-117">See also</span></span>

- [<span data-ttu-id="93c9a-118">Operator ステートメント</span><span class="sxs-lookup"><span data-stu-id="93c9a-118">Operator Statement</span></span>](../../../visual-basic/language-reference/statements/operator-statement.md)
- [<span data-ttu-id="93c9a-119">演算子プロシージャ</span><span class="sxs-lookup"><span data-stu-id="93c9a-119">Operator Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)
- [<span data-ttu-id="93c9a-120">方法: 演算子を定義する</span><span class="sxs-lookup"><span data-stu-id="93c9a-120">How to: Define an Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [<span data-ttu-id="93c9a-121">方法: 変換演算子を定義する</span><span class="sxs-lookup"><span data-stu-id="93c9a-121">How to: Define a Conversion Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)
- [<span data-ttu-id="93c9a-122">Function ステートメント</span><span class="sxs-lookup"><span data-stu-id="93c9a-122">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)
