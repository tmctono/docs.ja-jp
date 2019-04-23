---
title: '方法: (Visual Basic)、プロシージャ引数の値を変更します。'
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
- arguments [Visual Basic], ByRef
- arguments [Visual Basic], changing value
ms.assetid: 6fad2368-5da7-4c07-8bf8-0f4e65a1be67
ms.openlocfilehash: a56bdf888163c9559b87e857abb33522c547ed45
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59316623"
---
# <a name="how-to-change-the-value-of-a-procedure-argument-visual-basic"></a><span data-ttu-id="801d8-102">方法: (Visual Basic)、プロシージャ引数の値を変更します。</span><span class="sxs-lookup"><span data-stu-id="801d8-102">How to: Change the Value of a Procedure Argument (Visual Basic)</span></span>
<span data-ttu-id="801d8-103">プロシージャを呼び出すときに指定する各引数は、プロシージャで定義されたパラメーターのいずれかに対応します。</span><span class="sxs-lookup"><span data-stu-id="801d8-103">When you call a procedure, each argument you supply corresponds to one of the parameters defined in the procedure.</span></span> <span data-ttu-id="801d8-104">場合によっては、プロシージャのコードは呼び出し元のコードで引数を基になる値を変更できます。</span><span class="sxs-lookup"><span data-stu-id="801d8-104">In some cases, the procedure code can change the value underlying an argument in the calling code.</span></span> <span data-ttu-id="801d8-105">それ以外の場合、プロシージャは、引数のローカル コピーだけを変更できます。</span><span class="sxs-lookup"><span data-stu-id="801d8-105">In other cases, the procedure can change only its local copy of an argument.</span></span>  
  
 <span data-ttu-id="801d8-106">Visual Basic は、渡される引数はすべてのローカル コピーを作成して、プロシージャを呼び出すときに[ByVal](../../../../visual-basic/language-reference/modifiers/byval.md)します。</span><span class="sxs-lookup"><span data-stu-id="801d8-106">When you call the procedure, Visual Basic makes a local copy of every argument that is passed [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md).</span></span> <span data-ttu-id="801d8-107">渡された各引数に対して[ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)、Visual Basic でプロシージャのコードは呼び出し元のコードで引数を基になるプログラミング要素への直接参照します。</span><span class="sxs-lookup"><span data-stu-id="801d8-107">For each argument passed [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), Visual Basic gives the procedure code a direct reference to the programming element underlying the argument in the calling code.</span></span>  
  
 <span data-ttu-id="801d8-108">呼び出し元のコードに基になる要素が変更可能な場合に、引数が渡された`ByRef`プロシージャのコードは、直接の参照を使用して、呼び出し元のコード要素の値を変更します。</span><span class="sxs-lookup"><span data-stu-id="801d8-108">If the underlying element in the calling code is a modifiable element and the argument is passed `ByRef`, the procedure code can use the direct reference to change the element's value in the calling code.</span></span>  
  
## <a name="changing-the-underlying-value"></a><span data-ttu-id="801d8-109">基になる値を変更します。</span><span class="sxs-lookup"><span data-stu-id="801d8-109">Changing the Underlying Value</span></span>  
  
#### <a name="to-change-the-underlying-value-of-a-procedure-argument-in-the-calling-code"></a><span data-ttu-id="801d8-110">呼び出し元のコードでプロシージャ引数の基になる値を変更するには</span><span class="sxs-lookup"><span data-stu-id="801d8-110">To change the underlying value of a procedure argument in the calling code</span></span>  
  
1. <span data-ttu-id="801d8-111">プロシージャの宣言で指定[ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)引数に対応するパラメーター。</span><span class="sxs-lookup"><span data-stu-id="801d8-111">In the procedure declaration, specify [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) for the parameter corresponding to the argument.</span></span>  
  
2. <span data-ttu-id="801d8-112">呼び出し元のコードでは、変更可能なプログラミング要素を引数として渡します。</span><span class="sxs-lookup"><span data-stu-id="801d8-112">In the calling code, pass a modifiable programming element as the argument.</span></span>  
  
3. <span data-ttu-id="801d8-113">呼び出し元のコードでは囲まないで引数リストのかっこで囲まれた引数。</span><span class="sxs-lookup"><span data-stu-id="801d8-113">In the calling code, do not enclose the argument in parentheses in the argument list.</span></span>  
  
4. <span data-ttu-id="801d8-114">プロシージャのコードで、パラメーター名を使用して、呼び出し元のコード内の基になる要素に値を代入します。</span><span class="sxs-lookup"><span data-stu-id="801d8-114">In the procedure code, use the parameter name to assign a value to the underlying element in the calling code.</span></span>  
  
 <span data-ttu-id="801d8-115">例を参照してください。 デモについてはさらにダウンします。</span><span class="sxs-lookup"><span data-stu-id="801d8-115">See the example further down for a demonstration.</span></span>  
  
## <a name="changing-local-copies"></a><span data-ttu-id="801d8-116">ローカル コピーを変更します。</span><span class="sxs-lookup"><span data-stu-id="801d8-116">Changing Local Copies</span></span>  
 <span data-ttu-id="801d8-117">呼び出し元のコードで基になる要素が、変更不可能な要素である場合、または引数が渡された場合`ByVal`プロシージャが呼び出し元のコードでは、その値を変更できません。</span><span class="sxs-lookup"><span data-stu-id="801d8-117">If the underlying element in the calling code is a nonmodifiable element, or if the argument is passed `ByVal`, the procedure cannot change its value in the calling code.</span></span> <span data-ttu-id="801d8-118">ただし、プロシージャは、このような引数のローカル コピーを変更できます。</span><span class="sxs-lookup"><span data-stu-id="801d8-118">However, the procedure can change its local copy of such an argument.</span></span>  
  
#### <a name="to-change-the-copy-of-a-procedure-argument-in-the-procedure-code"></a><span data-ttu-id="801d8-119">プロシージャのコードでプロシージャ引数のコピーを変更するには</span><span class="sxs-lookup"><span data-stu-id="801d8-119">To change the copy of a procedure argument in the procedure code</span></span>  
  
1. <span data-ttu-id="801d8-120">プロシージャの宣言で指定[ByVal](../../../../visual-basic/language-reference/modifiers/byval.md)引数に対応するパラメーター。</span><span class="sxs-lookup"><span data-stu-id="801d8-120">In the procedure declaration, specify [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) for the parameter corresponding to the argument.</span></span>  
  
     <span data-ttu-id="801d8-121">- または -</span><span class="sxs-lookup"><span data-stu-id="801d8-121">-or-</span></span>  
  
     <span data-ttu-id="801d8-122">呼び出し元のコードで、引数、引数リストのかっこで囲みます。</span><span class="sxs-lookup"><span data-stu-id="801d8-122">In the calling code, enclose the argument in parentheses in the argument list.</span></span> <span data-ttu-id="801d8-123">これにより、対応するパラメーターが指定されている場合でも、Visual Basic での値で、引数を渡す`ByRef`します。</span><span class="sxs-lookup"><span data-stu-id="801d8-123">This forces Visual Basic to pass the argument by value, even if the corresponding parameter specifies `ByRef`.</span></span>  
  
2. <span data-ttu-id="801d8-124">プロシージャのコードで、パラメーター名を使用して、引数のローカル コピーに値を代入します。</span><span class="sxs-lookup"><span data-stu-id="801d8-124">In the procedure code, use the parameter name to assign a value to the local copy of the argument.</span></span> <span data-ttu-id="801d8-125">呼び出し元のコードで基になる値は変更されません。</span><span class="sxs-lookup"><span data-stu-id="801d8-125">The underlying value in the calling code is not changed.</span></span>  
  
## <a name="example"></a><span data-ttu-id="801d8-126">例</span><span class="sxs-lookup"><span data-stu-id="801d8-126">Example</span></span>  
 <span data-ttu-id="801d8-127">次の例では、その要素の配列変数を受け取り、操作を 2 つの手順を示します。</span><span class="sxs-lookup"><span data-stu-id="801d8-127">The following example shows two procedures that take an array variable and operate on its elements.</span></span> <span data-ttu-id="801d8-128">`increase`プロシージャが単純に各要素に 1 つを追加します。</span><span class="sxs-lookup"><span data-stu-id="801d8-128">The `increase` procedure simply adds one to each element.</span></span> <span data-ttu-id="801d8-129">`replace`プロシージャ パラメーターに新しい配列を割り当てます`a()`し、各要素に 1 つを追加します。</span><span class="sxs-lookup"><span data-stu-id="801d8-129">The `replace` procedure assigns a new array to the parameter `a()` and then adds one to each element.</span></span>  
  
 [!code-vb[VbVbcnProcedures#35](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#35)]  
  
 [!code-vb[VbVbcnProcedures#36](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#36)]  
  
 [!code-vb[VbVbcnProcedures#37](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#37)]  
  
 <span data-ttu-id="801d8-130">最初の`MsgBox`呼び出しが表示されます"increase(n) 後。11, 21, 31, 41".</span><span class="sxs-lookup"><span data-stu-id="801d8-130">The first `MsgBox` call displays "After increase(n): 11, 21, 31, 41".</span></span> <span data-ttu-id="801d8-131">配列`n`、参照型では、`replace`引き渡し方法は、そのメンバーを変更することができます`ByVal`します。</span><span class="sxs-lookup"><span data-stu-id="801d8-131">Because the array `n` is a reference type, `replace` can change its members, even though the passing mechanism is `ByVal`.</span></span>  
  
 <span data-ttu-id="801d8-132">2 番目の`MsgBox`呼び出しが表示されます"目後。101, 201, 301".</span><span class="sxs-lookup"><span data-stu-id="801d8-132">The second `MsgBox` call displays "After replace(n): 101, 201, 301".</span></span> <span data-ttu-id="801d8-133">`n`が渡される`ByRef`、`replace`変数を変更できます`n`呼び出し元のコードに割り当てる新しい配列。</span><span class="sxs-lookup"><span data-stu-id="801d8-133">Because `n` is passed `ByRef`, `replace` can modify the variable `n` in the calling code and assign a new array to it.</span></span> <span data-ttu-id="801d8-134">`n` 、参照型では、`replace`そのメンバーを変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="801d8-134">Because `n` is a reference type, `replace` can also change its members.</span></span>  
  
 <span data-ttu-id="801d8-135">プロシージャ呼び出し元のコードでは、変数自体を変更することを防止できます。</span><span class="sxs-lookup"><span data-stu-id="801d8-135">You can prevent the procedure from modifying the variable itself in the calling code.</span></span> <span data-ttu-id="801d8-136">「[方法:プロシージャ引数の値が変化しない](./how-to-protect-a-procedure-argument-against-value-changes.md)します。</span><span class="sxs-lookup"><span data-stu-id="801d8-136">See [How to: Protect a Procedure Argument Against Value Changes](./how-to-protect-a-procedure-argument-against-value-changes.md).</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="801d8-137">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="801d8-137">Compiling the Code</span></span>  
 <span data-ttu-id="801d8-138">参照渡しで変数を渡す場合は、使用、`ByRef`このメカニズムを指定するキーワード。</span><span class="sxs-lookup"><span data-stu-id="801d8-138">When you pass a variable by reference, you must use the `ByRef` keyword to specify this mechanism.</span></span>  
  
 <span data-ttu-id="801d8-139">Visual Basic では既定では、引数を値渡しです。</span><span class="sxs-lookup"><span data-stu-id="801d8-139">The default in Visual Basic is to pass arguments by value.</span></span> <span data-ttu-id="801d8-140">いずれかを指定することをお勧め、 [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md)または[ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)キーワード パラメーターを宣言します。</span><span class="sxs-lookup"><span data-stu-id="801d8-140">However, it is good programming practice to include either the [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) or [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) keyword with every declared parameter.</span></span> <span data-ttu-id="801d8-141">これにより、コードが読みやすくなります。</span><span class="sxs-lookup"><span data-stu-id="801d8-141">This makes your code easier to read.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="801d8-142">.NET Framework セキュリティ</span><span class="sxs-lookup"><span data-stu-id="801d8-142">.NET Framework Security</span></span>  
 <span data-ttu-id="801d8-143">呼び出し元のコードで引数を基になる値を変更するプロシージャを許可するのには、潜在的なリスクがあります。</span><span class="sxs-lookup"><span data-stu-id="801d8-143">There is always a potential risk in allowing a procedure to change the value underlying an argument in the calling code.</span></span> <span data-ttu-id="801d8-144">変更して、使用する前に有効性を確認するよう準備するのには、この値を期待することを確認します。</span><span class="sxs-lookup"><span data-stu-id="801d8-144">Make sure you expect this value to be changed, and be prepared to check it for validity before using it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="801d8-145">関連項目</span><span class="sxs-lookup"><span data-stu-id="801d8-145">See also</span></span>

- [<span data-ttu-id="801d8-146">プロシージャ</span><span class="sxs-lookup"><span data-stu-id="801d8-146">Procedures</span></span>](./index.md)
- [<span data-ttu-id="801d8-147">プロシージャのパラメーターと引数</span><span class="sxs-lookup"><span data-stu-id="801d8-147">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="801d8-148">方法: プロシージャに引数を渡す</span><span class="sxs-lookup"><span data-stu-id="801d8-148">How to: Pass Arguments to a Procedure</span></span>](./how-to-pass-arguments-to-a-procedure.md)
- [<span data-ttu-id="801d8-149">引数の値渡しと参照渡し</span><span class="sxs-lookup"><span data-stu-id="801d8-149">Passing Arguments by Value and by Reference</span></span>](./passing-arguments-by-value-and-by-reference.md)
- [<span data-ttu-id="801d8-150">変更できる引数と変更できない引数の違い</span><span class="sxs-lookup"><span data-stu-id="801d8-150">Differences Between Modifiable and Nonmodifiable Arguments</span></span>](./differences-between-modifiable-and-nonmodifiable-arguments.md)
- [<span data-ttu-id="801d8-151">引数の値渡しと参照渡しの違い</span><span class="sxs-lookup"><span data-stu-id="801d8-151">Differences Between Passing an Argument By Value and By Reference</span></span>](./differences-between-passing-an-argument-by-value-and-by-reference.md)
- [<span data-ttu-id="801d8-152">方法: プロシージャ引数の値が変化しません。</span><span class="sxs-lookup"><span data-stu-id="801d8-152">How to: Protect a Procedure Argument Against Value Changes</span></span>](./how-to-protect-a-procedure-argument-against-value-changes.md)
- [<span data-ttu-id="801d8-153">方法: 引数の値渡しを強制します。</span><span class="sxs-lookup"><span data-stu-id="801d8-153">How to: Force an Argument to Be Passed by Value</span></span>](./how-to-force-an-argument-to-be-passed-by-value.md)
- [<span data-ttu-id="801d8-154">位置と名前による引数渡し</span><span class="sxs-lookup"><span data-stu-id="801d8-154">Passing Arguments by Position and by Name</span></span>](./passing-arguments-by-position-and-by-name.md)
- [<span data-ttu-id="801d8-155">値型と参照型</span><span class="sxs-lookup"><span data-stu-id="801d8-155">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
