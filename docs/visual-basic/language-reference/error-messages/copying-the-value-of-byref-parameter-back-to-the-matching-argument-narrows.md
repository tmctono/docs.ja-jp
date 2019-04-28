---
title: "'ByRef' パラメーター '<parametername>' の値を一致する引数へ戻してコピーすると、型 '<typename1>' から型 '<typename2>' に下位変換します"
ms.date: 07/20/2015
f1_keywords:
- bc32053
- vbc32053
helpviewer_keywords:
- BC32053
ms.assetid: 281564b7-99f7-451f-b10d-f985e831bb25
ms.openlocfilehash: fa8607bf72dfb344048ec82514182dcb6810274d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61803858"
---
# <a name="copying-the-value-of-byref-parameter-parametername-back-to-the-matching-argument-narrows-from-type-typename1-to-type-typename2"></a><span data-ttu-id="fa002-102">'ByRef' パラメーターの値をコピー '\<parametername >' 型から縮小変換、一致する引数に戻して'\<typename1 >' 型に '\<typename2 >'</span><span class="sxs-lookup"><span data-stu-id="fa002-102">Copying the value of 'ByRef' parameter '\<parametername>' back to the matching argument narrows from type '\<typename1>' to type '\<typename2>'</span></span>
<span data-ttu-id="fa002-103">プロシージャは、対応するパラメーターの型を拡張する引数を指定して呼び出され、パラメーターから、引数への変換は縮小します。</span><span class="sxs-lookup"><span data-stu-id="fa002-103">A procedure is called with an argument that widens to the corresponding parameter type, and the conversion from the parameter to the argument is narrowing.</span></span>  
  
 <span data-ttu-id="fa002-104">クラスまたは構造体を定義するときは、そのクラスまたは構造体の型を他の型に変換する 1 つまたは複数の変換演算子を定義できます。</span><span class="sxs-lookup"><span data-stu-id="fa002-104">When you define a class or structure, you can define one or more conversion operators to convert that class or structure type to other types.</span></span> <span data-ttu-id="fa002-105">その他の型をクラスまたは構造体の型に変換する逆の変換演算子を定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="fa002-105">You can also define reverse conversion operators to convert those other types back to your class or structure type.</span></span> <span data-ttu-id="fa002-106">プロシージャ呼び出しでクラスまたは構造体の型を使用すると、Visual Basic は、対応するパラメーターの型の引数の型に変換するのにこれらの変換演算子を使用できます。</span><span class="sxs-lookup"><span data-stu-id="fa002-106">When you use your class or structure type in a procedure call, Visual Basic can use these conversion operators to convert the type of an argument to the type of its corresponding parameter.</span></span>  
  
 <span data-ttu-id="fa002-107">引数を渡す場合[ByRef](../../../visual-basic/language-reference/modifiers/byref.md)、Visual Basic は、ローカル変数の参照を渡す代わりにプロシージャに引数の値をコピーすることがあります。</span><span class="sxs-lookup"><span data-stu-id="fa002-107">If you pass the argument [ByRef](../../../visual-basic/language-reference/modifiers/byref.md), Visual Basic sometimes copies the argument value into a local variable in the procedure instead of passing a reference.</span></span> <span data-ttu-id="fa002-108">このような場合は、プロシージャが返されるときに Visual Basic する必要がありますにコピーしてローカル変数の値戻す呼び出し元のコードの引数。</span><span class="sxs-lookup"><span data-stu-id="fa002-108">In such a case, when the procedure returns, Visual Basic must then copy the local variable value back into the argument in the calling code.</span></span>  
  
 <span data-ttu-id="fa002-109">`ByRef` 引数の値がプロシージャにコピーされ、引数とパラメーターが同じ型である場合、変換は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="fa002-109">If a `ByRef` argument value is copied into the procedure and the argument and parameter are of the same type, no conversion is necessary.</span></span> <span data-ttu-id="fa002-110">種類が異なる場合は、Visual Basic が双方向で変換する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fa002-110">But if the types are different, Visual Basic must convert in both directions.</span></span> <span data-ttu-id="fa002-111">型のいずれかがクラスまたは構造体の型の場合は、Visual Basic は両方と、他の型の間を変換する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fa002-111">If one of the types is your class or structure type, Visual Basic must convert it both to and from the other type.</span></span> <span data-ttu-id="fa002-112">これらの変換のいずれかを拡大すると場合、逆の変換は縮小可能性があります。</span><span class="sxs-lookup"><span data-stu-id="fa002-112">If one of these conversions is widening, the reverse conversion might be narrowing.</span></span>  
  
 <span data-ttu-id="fa002-113">**エラー ID:** BC32053</span><span class="sxs-lookup"><span data-stu-id="fa002-113">**Error ID:** BC32053</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="fa002-114">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="fa002-114">To correct this error</span></span>  
  
- <span data-ttu-id="fa002-115">可能であれば、Visual Basic は、変換を行う必要はありませんので、プロシージャのパラメーターとして、同じ種類の呼び出し元の引数を使用します。</span><span class="sxs-lookup"><span data-stu-id="fa002-115">If possible, use a calling argument of the same type as the procedure parameter, so Visual Basic does not need to do any conversion.</span></span>  
  
- <span data-ttu-id="fa002-116">パラメーター型とは異なる引数型を使用してプロシージャを呼び出す必要があり、呼び出し元の引数に値を返す必要がない場合は、 [ByRef](../../../visual-basic/language-reference/modifiers/byval.md) ではなく `ByRef`になるようにパラメーターを定義します。</span><span class="sxs-lookup"><span data-stu-id="fa002-116">If you need to call the procedure with an argument type different from the parameter type but do not need to return a value into the calling argument, define the parameter to be [ByVal](../../../visual-basic/language-reference/modifiers/byval.md) instead of `ByRef`.</span></span>  
  
- <span data-ttu-id="fa002-117">呼び出し元の引数に値を返す場合は、定義として逆の変換演算子[Widening](../../../visual-basic/language-reference/modifiers/widening.md)、可能な場合。</span><span class="sxs-lookup"><span data-stu-id="fa002-117">If you need to return a value into the calling argument, define the reverse conversion operator as [Widening](../../../visual-basic/language-reference/modifiers/widening.md), if possible.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa002-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="fa002-118">See also</span></span>

- [<span data-ttu-id="fa002-119">プロシージャ</span><span class="sxs-lookup"><span data-stu-id="fa002-119">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)
- [<span data-ttu-id="fa002-120">プロシージャのパラメーターと引数</span><span class="sxs-lookup"><span data-stu-id="fa002-120">Procedure Parameters and Arguments</span></span>](../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)
- [<span data-ttu-id="fa002-121">引数の値渡しと参照渡し</span><span class="sxs-lookup"><span data-stu-id="fa002-121">Passing Arguments by Value and by Reference</span></span>](../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)
- [<span data-ttu-id="fa002-122">演算子プロシージャ</span><span class="sxs-lookup"><span data-stu-id="fa002-122">Operator Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)
- [<span data-ttu-id="fa002-123">Operator ステートメント</span><span class="sxs-lookup"><span data-stu-id="fa002-123">Operator Statement</span></span>](../../../visual-basic/language-reference/statements/operator-statement.md)
- [<span data-ttu-id="fa002-124">方法: 演算子を定義します。</span><span class="sxs-lookup"><span data-stu-id="fa002-124">How to: Define an Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [<span data-ttu-id="fa002-125">方法: 変換演算子を定義します。</span><span class="sxs-lookup"><span data-stu-id="fa002-125">How to: Define a Conversion Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)
- [<span data-ttu-id="fa002-126">Visual Basic における型変換</span><span class="sxs-lookup"><span data-stu-id="fa002-126">Type Conversions in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
- [<span data-ttu-id="fa002-127">拡大変換と縮小変換</span><span class="sxs-lookup"><span data-stu-id="fa002-127">Widening and Narrowing Conversions</span></span>](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
