---
title: '方法: プロシージャ引数の値を変更する'
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
ms.openlocfilehash: 9960dacc053c5dc8d8cfdfd6eaa0ea3258ed0fea
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2020
ms.locfileid: "91077073"
---
# <a name="how-to-change-the-value-of-a-procedure-argument-visual-basic"></a><span data-ttu-id="ffc8e-102">方法: プロシージャ引数の値を変更する (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ffc8e-102">How to: Change the Value of a Procedure Argument (Visual Basic)</span></span>

<span data-ttu-id="ffc8e-103">プロシージャを呼び出すときに、指定する引数は、プロシージャで定義されているパラメーターにそれぞれ対応しています。</span><span class="sxs-lookup"><span data-stu-id="ffc8e-103">When you call a procedure, each argument you supply corresponds to one of the parameters defined in the procedure.</span></span> <span data-ttu-id="ffc8e-104">プロシージャ コードが、呼び出し元のコードの引数の基になる値を変更できる場合があります。</span><span class="sxs-lookup"><span data-stu-id="ffc8e-104">In some cases, the procedure code can change the value underlying an argument in the calling code.</span></span> <span data-ttu-id="ffc8e-105">また、プロシージャが引数のローカル コピーのみを変更できる場合もあります。</span><span class="sxs-lookup"><span data-stu-id="ffc8e-105">In other cases, the procedure can change only its local copy of an argument.</span></span>  
  
 <span data-ttu-id="ffc8e-106">Visual Basic では、プロシージャを呼び出すときに、[ByVal](../../../language-reference/modifiers/byval.md) で渡されるすべての引数のローカル コピーが作成されます。</span><span class="sxs-lookup"><span data-stu-id="ffc8e-106">When you call the procedure, Visual Basic makes a local copy of every argument that is passed [ByVal](../../../language-reference/modifiers/byval.md).</span></span> <span data-ttu-id="ffc8e-107">[ByRef](../../../language-reference/modifiers/byref.md) で渡される各引数では、引数の基になる呼び出し元のコードのプログラミング要素への直接参照がプロシージャ コードに渡されます。</span><span class="sxs-lookup"><span data-stu-id="ffc8e-107">For each argument passed [ByRef](../../../language-reference/modifiers/byref.md), Visual Basic gives the procedure code a direct reference to the programming element underlying the argument in the calling code.</span></span>  
  
 <span data-ttu-id="ffc8e-108">呼び出し元のコードの基になる要素が変更可能な要素であり、引数が `ByRef` で渡される場合、プロシージャ コードは直接参照を使用して呼び出し元のコードの要素の値を変更できます。</span><span class="sxs-lookup"><span data-stu-id="ffc8e-108">If the underlying element in the calling code is a modifiable element and the argument is passed `ByRef`, the procedure code can use the direct reference to change the element's value in the calling code.</span></span>  
  
## <a name="changing-the-underlying-value"></a><span data-ttu-id="ffc8e-109">基になる値を変更する</span><span class="sxs-lookup"><span data-stu-id="ffc8e-109">Changing the Underlying Value</span></span>  
  
#### <a name="to-change-the-underlying-value-of-a-procedure-argument-in-the-calling-code"></a><span data-ttu-id="ffc8e-110">呼び出し元のコードのプロシージャ引数の基になる値を変更するには</span><span class="sxs-lookup"><span data-stu-id="ffc8e-110">To change the underlying value of a procedure argument in the calling code</span></span>  
  
1. <span data-ttu-id="ffc8e-111">プロシージャの宣言で、引数に対応するパラメーターに [ByRef](../../../language-reference/modifiers/byref.md) を指定します。</span><span class="sxs-lookup"><span data-stu-id="ffc8e-111">In the procedure declaration, specify [ByRef](../../../language-reference/modifiers/byref.md) for the parameter corresponding to the argument.</span></span>  
  
2. <span data-ttu-id="ffc8e-112">呼び出し元のコードで、変更可能なプログラミング要素を引数として渡します。</span><span class="sxs-lookup"><span data-stu-id="ffc8e-112">In the calling code, pass a modifiable programming element as the argument.</span></span>  
  
3. <span data-ttu-id="ffc8e-113">呼び出し元のコードでは、引数リストの引数をかっこで囲まないでください。</span><span class="sxs-lookup"><span data-stu-id="ffc8e-113">In the calling code, do not enclose the argument in parentheses in the argument list.</span></span>  
  
4. <span data-ttu-id="ffc8e-114">プロシージャ コードで、パラメーター名を使用して、呼び出し元のコードの基になる要素に値を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="ffc8e-114">In the procedure code, use the parameter name to assign a value to the underlying element in the calling code.</span></span>  
  
 <span data-ttu-id="ffc8e-115">デモについては、後述の例を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ffc8e-115">See the example further down for a demonstration.</span></span>  
  
## <a name="changing-local-copies"></a><span data-ttu-id="ffc8e-116">ローカル コピーを変更する</span><span class="sxs-lookup"><span data-stu-id="ffc8e-116">Changing Local Copies</span></span>  

 <span data-ttu-id="ffc8e-117">呼び出し元のコードの基になる要素が変更不可能な要素である場合や、引数が `ByVal` で渡される場合、プロシージャは呼び出し元のコードの値を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="ffc8e-117">If the underlying element in the calling code is a nonmodifiable element, or if the argument is passed `ByVal`, the procedure cannot change its value in the calling code.</span></span> <span data-ttu-id="ffc8e-118">ただし、プロシージャはそのような引数のローカル コピーを変更できます。</span><span class="sxs-lookup"><span data-stu-id="ffc8e-118">However, the procedure can change its local copy of such an argument.</span></span>  
  
#### <a name="to-change-the-copy-of-a-procedure-argument-in-the-procedure-code"></a><span data-ttu-id="ffc8e-119">プロシージャ コードのプロシージャ引数のコピーを変更するには</span><span class="sxs-lookup"><span data-stu-id="ffc8e-119">To change the copy of a procedure argument in the procedure code</span></span>  
  
1. <span data-ttu-id="ffc8e-120">プロシージャの宣言で、引数に対応するパラメーターに [ByVal](../../../language-reference/modifiers/byval.md) を指定します。</span><span class="sxs-lookup"><span data-stu-id="ffc8e-120">In the procedure declaration, specify [ByVal](../../../language-reference/modifiers/byval.md) for the parameter corresponding to the argument.</span></span>  
  
     <span data-ttu-id="ffc8e-121">\- または -</span><span class="sxs-lookup"><span data-stu-id="ffc8e-121">-or-</span></span>  
  
     <span data-ttu-id="ffc8e-122">呼び出し元のコードで、引数リストの引数をかっこで囲みます。</span><span class="sxs-lookup"><span data-stu-id="ffc8e-122">In the calling code, enclose the argument in parentheses in the argument list.</span></span> <span data-ttu-id="ffc8e-123">これにより、対応するパラメーターに `ByRef` が指定されている場合でも、引数の値渡しが強制されます。</span><span class="sxs-lookup"><span data-stu-id="ffc8e-123">This forces Visual Basic to pass the argument by value, even if the corresponding parameter specifies `ByRef`.</span></span>  
  
2. <span data-ttu-id="ffc8e-124">プロシージャ コードで、パラメーター名を使用して、引数のローカル コピーに値を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="ffc8e-124">In the procedure code, use the parameter name to assign a value to the local copy of the argument.</span></span> <span data-ttu-id="ffc8e-125">呼び出し元のコードの基になる値は変更されません。</span><span class="sxs-lookup"><span data-stu-id="ffc8e-125">The underlying value in the calling code is not changed.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ffc8e-126">例</span><span class="sxs-lookup"><span data-stu-id="ffc8e-126">Example</span></span>  

 <span data-ttu-id="ffc8e-127">次の例は、配列変数を受け取り、その要素を操作する 2 つのプロシージャを示しています。</span><span class="sxs-lookup"><span data-stu-id="ffc8e-127">The following example shows two procedures that take an array variable and operate on its elements.</span></span> <span data-ttu-id="ffc8e-128">`increase` プロシージャは、各要素に 1 を加算するだけです。</span><span class="sxs-lookup"><span data-stu-id="ffc8e-128">The `increase` procedure simply adds one to each element.</span></span> <span data-ttu-id="ffc8e-129">`replace` プロシージャは、`a()` パラメーターに新しい配列を割り当ててから、各要素に 1 を加算します。</span><span class="sxs-lookup"><span data-stu-id="ffc8e-129">The `replace` procedure assigns a new array to the parameter `a()` and then adds one to each element.</span></span>  
  
 [!code-vb[VbVbcnProcedures#35](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#35)]  
  
 [!code-vb[VbVbcnProcedures#36](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#36)]  
  
 [!code-vb[VbVbcnProcedures#37](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#37)]  
  
 <span data-ttu-id="ffc8e-130">最初の `MsgBox` 呼び出しでは、"After increase(n): 11, 21, 31, 41" と表示されます。</span><span class="sxs-lookup"><span data-stu-id="ffc8e-130">The first `MsgBox` call displays "After increase(n): 11, 21, 31, 41".</span></span> <span data-ttu-id="ffc8e-131">配列 `n` は参照型であるため、引渡し方法が `ByVal` であっても、`replace` はそのメンバーを変更できます。</span><span class="sxs-lookup"><span data-stu-id="ffc8e-131">Because the array `n` is a reference type, `replace` can change its members, even though the passing mechanism is `ByVal`.</span></span>  
  
 <span data-ttu-id="ffc8e-132">2 番目の `MsgBox` 呼び出しでは、"After replace(n): 101, 201, 301" と表示されます。</span><span class="sxs-lookup"><span data-stu-id="ffc8e-132">The second `MsgBox` call displays "After replace(n): 101, 201, 301".</span></span> <span data-ttu-id="ffc8e-133">`n` は `ByRef` で渡されるため、`replace` は呼び出し元のコードの変数 `n` を変更して新しい配列を割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="ffc8e-133">Because `n` is passed `ByRef`, `replace` can modify the variable `n` in the calling code and assign a new array to it.</span></span> <span data-ttu-id="ffc8e-134">`n` は参照型であるため、`replace` はそのメンバーを変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="ffc8e-134">Because `n` is a reference type, `replace` can also change its members.</span></span>  
  
 <span data-ttu-id="ffc8e-135">プロシージャが、呼び出し元のコードの変数自体を変更できないようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="ffc8e-135">You can prevent the procedure from modifying the variable itself in the calling code.</span></span> <span data-ttu-id="ffc8e-136">「[方法:プロシージャ引数の値が変更されないように保護する](./how-to-protect-a-procedure-argument-against-value-changes.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="ffc8e-136">See [How to: Protect a Procedure Argument Against Value Changes](./how-to-protect-a-procedure-argument-against-value-changes.md).</span></span>  
  
## <a name="compile-the-code"></a><span data-ttu-id="ffc8e-137">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="ffc8e-137">Compile the code</span></span>  

 <span data-ttu-id="ffc8e-138">変数を参照渡しにするときは、`ByRef` キーワードを使用してこの方法を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ffc8e-138">When you pass a variable by reference, you must use the `ByRef` keyword to specify this mechanism.</span></span>  
  
 <span data-ttu-id="ffc8e-139">Visual Basic の既定では、引数は値渡しになります。</span><span class="sxs-lookup"><span data-stu-id="ffc8e-139">The default in Visual Basic is to pass arguments by value.</span></span> <span data-ttu-id="ffc8e-140">ただし、宣言されるすべてのパラメーターに、[ByVal](../../../language-reference/modifiers/byval.md) または [ByRef](../../../language-reference/modifiers/byref.md) キーワードを含めることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="ffc8e-140">However, it is good programming practice to include either the [ByVal](../../../language-reference/modifiers/byval.md) or [ByRef](../../../language-reference/modifiers/byref.md) keyword with every declared parameter.</span></span> <span data-ttu-id="ffc8e-141">これにより、コードが読みやすくなります。</span><span class="sxs-lookup"><span data-stu-id="ffc8e-141">This makes your code easier to read.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="ffc8e-142">.NET Framework セキュリティ</span><span class="sxs-lookup"><span data-stu-id="ffc8e-142">.NET Framework Security</span></span>  

 <span data-ttu-id="ffc8e-143">プロシージャが呼び出し元のコードの引数の基になる値を変更できるようにする場合、常に潜在的なリスクがあります。</span><span class="sxs-lookup"><span data-stu-id="ffc8e-143">There is always a potential risk in allowing a procedure to change the value underlying an argument in the calling code.</span></span> <span data-ttu-id="ffc8e-144">この値が変更されることを想定し、使用前に有効性をチェックする準備をしておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="ffc8e-144">Make sure you expect this value to be changed, and be prepared to check it for validity before using it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ffc8e-145">関連項目</span><span class="sxs-lookup"><span data-stu-id="ffc8e-145">See also</span></span>

- [<span data-ttu-id="ffc8e-146">手順</span><span class="sxs-lookup"><span data-stu-id="ffc8e-146">Procedures</span></span>](./index.md)
- [<span data-ttu-id="ffc8e-147">プロシージャのパラメーターと引数</span><span class="sxs-lookup"><span data-stu-id="ffc8e-147">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="ffc8e-148">方法: プロシージャに引数を渡す</span><span class="sxs-lookup"><span data-stu-id="ffc8e-148">How to: Pass Arguments to a Procedure</span></span>](./how-to-pass-arguments-to-a-procedure.md)
- [<span data-ttu-id="ffc8e-149">引数の値渡しと参照渡し</span><span class="sxs-lookup"><span data-stu-id="ffc8e-149">Passing Arguments by Value and by Reference</span></span>](./passing-arguments-by-value-and-by-reference.md)
- [<span data-ttu-id="ffc8e-150">変更できる引数と変更できない引数の違い</span><span class="sxs-lookup"><span data-stu-id="ffc8e-150">Differences Between Modifiable and Nonmodifiable Arguments</span></span>](./differences-between-modifiable-and-nonmodifiable-arguments.md)
- [<span data-ttu-id="ffc8e-151">引数の値渡しと参照渡しの違い</span><span class="sxs-lookup"><span data-stu-id="ffc8e-151">Differences Between Passing an Argument By Value and By Reference</span></span>](./differences-between-passing-an-argument-by-value-and-by-reference.md)
- [<span data-ttu-id="ffc8e-152">方法: プロシージャ引数の値が変更されないように保護する</span><span class="sxs-lookup"><span data-stu-id="ffc8e-152">How to: Protect a Procedure Argument Against Value Changes</span></span>](./how-to-protect-a-procedure-argument-against-value-changes.md)
- [<span data-ttu-id="ffc8e-153">方法: 引数の値渡しを強制する</span><span class="sxs-lookup"><span data-stu-id="ffc8e-153">How to: Force an Argument to Be Passed by Value</span></span>](./how-to-force-an-argument-to-be-passed-by-value.md)
- [<span data-ttu-id="ffc8e-154">位置と名前による引数渡し</span><span class="sxs-lookup"><span data-stu-id="ffc8e-154">Passing Arguments by Position and by Name</span></span>](./passing-arguments-by-position-and-by-name.md)
- [<span data-ttu-id="ffc8e-155">Value Types and Reference Types</span><span class="sxs-lookup"><span data-stu-id="ffc8e-155">Value Types and Reference Types</span></span>](../data-types/value-types-and-reference-types.md)
