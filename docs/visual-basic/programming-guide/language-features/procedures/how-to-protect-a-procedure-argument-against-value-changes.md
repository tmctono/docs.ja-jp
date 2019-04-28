---
title: '方法: プロシージャ引数の値の変更 (Visual Basic) を保護します。'
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], arguments
- procedures [Visual Basic], parameters
- procedure arguments
- arguments [Visual Basic], passing by reference
- Visual Basic code, procedures
- arguments [Visual Basic], ByVal
- arguments [Visual Basic], passing by value
- procedure parameters
- procedures [Visual Basic], calling
- arguments [Visual Basic], ByRef
- arguments [Visual Basic], changing value
ms.assetid: d2b7c766-ce16-4d2c-8d79-3fc0e7ba2227
ms.openlocfilehash: 70378b57c6d3af5a98e0ba9c6e3aebc319561b1b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61665742"
---
# <a name="how-to-protect-a-procedure-argument-against-value-changes-visual-basic"></a><span data-ttu-id="4747c-102">方法: プロシージャ引数の値の変更 (Visual Basic) を保護します。</span><span class="sxs-lookup"><span data-stu-id="4747c-102">How to: Protect a Procedure Argument Against Value Changes (Visual Basic)</span></span>
<span data-ttu-id="4747c-103">プロシージャ宣言のパラメーターとして場合[ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)、Visual Basic でプロシージャのコードは呼び出し元のコードで引数を基になるプログラミング要素への直接参照します。</span><span class="sxs-lookup"><span data-stu-id="4747c-103">If a procedure declares a parameter as [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), Visual Basic gives the procedure code a direct reference to the programming element underlying the argument in the calling code.</span></span> <span data-ttu-id="4747c-104">これにより、プロシージャが呼び出し元のコードで引数を基になる値を変更します。</span><span class="sxs-lookup"><span data-stu-id="4747c-104">This permits the procedure to change the value underlying the argument in the calling code.</span></span> <span data-ttu-id="4747c-105">場合によってはの呼び出し元のコードは、このような変更から保護します。</span><span class="sxs-lookup"><span data-stu-id="4747c-105">In some cases the calling code might want to protect against such a change.</span></span>  
  
 <span data-ttu-id="4747c-106">対応するパラメーターを宣言することで、変更から引数を保護できます常に[ByVal](../../../../visual-basic/language-reference/modifiers/byval.md)の手順でします。</span><span class="sxs-lookup"><span data-stu-id="4747c-106">You can always protect an argument from change by declaring the corresponding parameter [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) in the procedure.</span></span> <span data-ttu-id="4747c-107">によって自動的に指定した引数を変更できる場合は、宣言できる`ByRef`呼び出し元のコードが各呼び出しで引き渡し方法を決定できるようにします。</span><span class="sxs-lookup"><span data-stu-id="4747c-107">If you want to be able to change a given argument in some cases but not others, you can declare it `ByRef` and let the calling code determine the passing mechanism in each call.</span></span> <span data-ttu-id="4747c-108">これは、対応する引数を値で渡す括弧で囲むか、参照渡しするためにかっこで囲まないとで実行します。</span><span class="sxs-lookup"><span data-stu-id="4747c-108">It does this by enclosing the corresponding argument in parentheses to pass it by value, or not enclosing it in parentheses to pass it by reference.</span></span> <span data-ttu-id="4747c-109">詳細については、「[方法 :引数の値渡しを強制](./how-to-force-an-argument-to-be-passed-by-value.md)します。</span><span class="sxs-lookup"><span data-stu-id="4747c-109">For more information, see [How to: Force an Argument to Be Passed by Value](./how-to-force-an-argument-to-be-passed-by-value.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="4747c-110">例</span><span class="sxs-lookup"><span data-stu-id="4747c-110">Example</span></span>  
 <span data-ttu-id="4747c-111">次の例では、その要素の配列変数を受け取り、操作を 2 つの手順を示します。</span><span class="sxs-lookup"><span data-stu-id="4747c-111">The following example shows two procedures that take an array variable and operate on its elements.</span></span> <span data-ttu-id="4747c-112">`increase`プロシージャが単純に各要素に 1 つを追加します。</span><span class="sxs-lookup"><span data-stu-id="4747c-112">The `increase` procedure simply adds one to each element.</span></span> <span data-ttu-id="4747c-113">`replace`プロシージャ パラメーターに新しい配列を割り当てます`a()`し、各要素に 1 つを追加します。</span><span class="sxs-lookup"><span data-stu-id="4747c-113">The `replace` procedure assigns a new array to the parameter `a()` and then adds one to each element.</span></span> <span data-ttu-id="4747c-114">ただし、再割り当てでは、呼び出し元のコードで、基になる配列変数には影響しません。</span><span class="sxs-lookup"><span data-stu-id="4747c-114">However, the reassignment does not affect the underlying array variable in the calling code.</span></span>  
  
 [!code-vb[VbVbcnProcedures#35](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#35)]  
  
 [!code-vb[VbVbcnProcedures#38](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#38)]  
  
 [!code-vb[VbVbcnProcedures#37](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#37)]  
  
 <span data-ttu-id="4747c-115">最初の`MsgBox`呼び出しが表示されます"increase(n) 後。11, 21, 31, 41".</span><span class="sxs-lookup"><span data-stu-id="4747c-115">The first `MsgBox` call displays "After increase(n): 11, 21, 31, 41".</span></span> <span data-ttu-id="4747c-116">配列`n`、参照型では、`increase`引き渡し方法は、そのメンバーを変更することができます`ByVal`します。</span><span class="sxs-lookup"><span data-stu-id="4747c-116">Because the array `n` is a reference type, `increase` can change its members, even though the passing mechanism is `ByVal`.</span></span>  
  
 <span data-ttu-id="4747c-117">2 番目の`MsgBox`呼び出しが表示されます"目後。11, 21, 31, 41".</span><span class="sxs-lookup"><span data-stu-id="4747c-117">The second `MsgBox` call displays "After replace(n): 11, 21, 31, 41".</span></span> <span data-ttu-id="4747c-118">`n`が渡される`ByVal`、`replace`変数を変更することはできません`n`を新しい配列を割り当てることで、呼び出しコード。</span><span class="sxs-lookup"><span data-stu-id="4747c-118">Because `n` is passed `ByVal`, `replace` cannot modify the variable `n` in the calling code by assigning a new array to it.</span></span> <span data-ttu-id="4747c-119">ときに`replace`新しい配列インスタンスを作成します`k`し、ローカル変数に代入`a`への参照が失われた`n`呼び出し元のコードで渡されます。</span><span class="sxs-lookup"><span data-stu-id="4747c-119">When `replace` creates the new array instance `k` and assigns it to the local variable `a`, it loses the reference to `n` passed in by the calling code.</span></span> <span data-ttu-id="4747c-120">メンバーが変更されたとき`a`、ローカルの配列のみ`k`が影響を受けます。</span><span class="sxs-lookup"><span data-stu-id="4747c-120">When it changes the members of `a`, only the local array `k` is affected.</span></span> <span data-ttu-id="4747c-121">そのため、`replace`配列の値は増分されません`n`呼び出し元のコード。</span><span class="sxs-lookup"><span data-stu-id="4747c-121">Therefore, `replace` does not increment the values of array `n` in the calling code.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="4747c-122">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="4747c-122">Compiling the Code</span></span>  
 <span data-ttu-id="4747c-123">Visual Basic では既定では、引数を値渡しです。</span><span class="sxs-lookup"><span data-stu-id="4747c-123">The default in Visual Basic is to pass arguments by value.</span></span> <span data-ttu-id="4747c-124">いずれかを指定することをお勧め、 [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md)または[ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)キーワード パラメーターを宣言します。</span><span class="sxs-lookup"><span data-stu-id="4747c-124">However, it is good programming practice to include either the [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) or [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) keyword with every declared parameter.</span></span> <span data-ttu-id="4747c-125">これにより、コードが読みやすくなります。</span><span class="sxs-lookup"><span data-stu-id="4747c-125">This makes your code easier to read.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4747c-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="4747c-126">See also</span></span>

- [<span data-ttu-id="4747c-127">プロシージャ</span><span class="sxs-lookup"><span data-stu-id="4747c-127">Procedures</span></span>](./index.md)
- [<span data-ttu-id="4747c-128">プロシージャのパラメーターと引数</span><span class="sxs-lookup"><span data-stu-id="4747c-128">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="4747c-129">方法: プロシージャに引数を渡す</span><span class="sxs-lookup"><span data-stu-id="4747c-129">How to: Pass Arguments to a Procedure</span></span>](./how-to-pass-arguments-to-a-procedure.md)
- [<span data-ttu-id="4747c-130">引数の値渡しと参照渡し</span><span class="sxs-lookup"><span data-stu-id="4747c-130">Passing Arguments by Value and by Reference</span></span>](./passing-arguments-by-value-and-by-reference.md)
- [<span data-ttu-id="4747c-131">変更できる引数と変更できない引数の違い</span><span class="sxs-lookup"><span data-stu-id="4747c-131">Differences Between Modifiable and Nonmodifiable Arguments</span></span>](./differences-between-modifiable-and-nonmodifiable-arguments.md)
- [<span data-ttu-id="4747c-132">引数の値渡しと参照渡しの違い</span><span class="sxs-lookup"><span data-stu-id="4747c-132">Differences Between Passing an Argument By Value and By Reference</span></span>](./differences-between-passing-an-argument-by-value-and-by-reference.md)
- [<span data-ttu-id="4747c-133">方法: プロシージャ引数の値を変更します。</span><span class="sxs-lookup"><span data-stu-id="4747c-133">How to: Change the Value of a Procedure Argument</span></span>](./how-to-change-the-value-of-a-procedure-argument.md)
- [<span data-ttu-id="4747c-134">方法: 引数の値渡しを強制します。</span><span class="sxs-lookup"><span data-stu-id="4747c-134">How to: Force an Argument to Be Passed by Value</span></span>](./how-to-force-an-argument-to-be-passed-by-value.md)
- [<span data-ttu-id="4747c-135">位置と名前による引数渡し</span><span class="sxs-lookup"><span data-stu-id="4747c-135">Passing Arguments by Position and by Name</span></span>](./passing-arguments-by-position-and-by-name.md)
- [<span data-ttu-id="4747c-136">値型と参照型</span><span class="sxs-lookup"><span data-stu-id="4747c-136">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
