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
ms.openlocfilehash: e562c0f5ec01380c792b4dc064554171cfb007e7
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74339953"
---
# <a name="how-to-change-the-value-of-a-procedure-argument-visual-basic"></a><span data-ttu-id="122dc-102">方法: プロシージャ引数の値を変更する (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="122dc-102">How to: Change the Value of a Procedure Argument (Visual Basic)</span></span>
<span data-ttu-id="122dc-103">プロシージャを呼び出すと、指定した各引数は、プロシージャで定義されたパラメーターのいずれかに対応します。</span><span class="sxs-lookup"><span data-stu-id="122dc-103">When you call a procedure, each argument you supply corresponds to one of the parameters defined in the procedure.</span></span> <span data-ttu-id="122dc-104">場合によっては、プロシージャコードは、呼び出し元のコードの引数の基になる値を変更できます。</span><span class="sxs-lookup"><span data-stu-id="122dc-104">In some cases, the procedure code can change the value underlying an argument in the calling code.</span></span> <span data-ttu-id="122dc-105">それ以外の場合、プロシージャは引数のローカルコピーだけを変更できます。</span><span class="sxs-lookup"><span data-stu-id="122dc-105">In other cases, the procedure can change only its local copy of an argument.</span></span>  
  
 <span data-ttu-id="122dc-106">プロシージャを呼び出すと、Visual Basic によって、 [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md)で渡されるすべての引数のローカルコピーが作成されます。</span><span class="sxs-lookup"><span data-stu-id="122dc-106">When you call the procedure, Visual Basic makes a local copy of every argument that is passed [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md).</span></span> <span data-ttu-id="122dc-107">[ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)で渡された引数ごとに、Visual Basic は、呼び出し元のコードの引数の基になるプログラミング要素への直接参照をプロシージャコードに付与します。</span><span class="sxs-lookup"><span data-stu-id="122dc-107">For each argument passed [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), Visual Basic gives the procedure code a direct reference to the programming element underlying the argument in the calling code.</span></span>  
  
 <span data-ttu-id="122dc-108">呼び出し元のコード内の基になる要素が変更可能な要素であり、引数が `ByRef`渡される場合、プロシージャコードは直接参照を使用して、呼び出し元のコード内の要素の値を変更できます。</span><span class="sxs-lookup"><span data-stu-id="122dc-108">If the underlying element in the calling code is a modifiable element and the argument is passed `ByRef`, the procedure code can use the direct reference to change the element's value in the calling code.</span></span>  
  
## <a name="changing-the-underlying-value"></a><span data-ttu-id="122dc-109">基になる値の変更</span><span class="sxs-lookup"><span data-stu-id="122dc-109">Changing the Underlying Value</span></span>  
  
#### <a name="to-change-the-underlying-value-of-a-procedure-argument-in-the-calling-code"></a><span data-ttu-id="122dc-110">呼び出し元コードのプロシージャ引数の基になる値を変更するには</span><span class="sxs-lookup"><span data-stu-id="122dc-110">To change the underlying value of a procedure argument in the calling code</span></span>  
  
1. <span data-ttu-id="122dc-111">プロシージャの宣言で、引数に対応するパラメーターに[ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)を指定します。</span><span class="sxs-lookup"><span data-stu-id="122dc-111">In the procedure declaration, specify [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) for the parameter corresponding to the argument.</span></span>  
  
2. <span data-ttu-id="122dc-112">呼び出し元のコードで、変更可能なプログラミング要素を引数として渡します。</span><span class="sxs-lookup"><span data-stu-id="122dc-112">In the calling code, pass a modifiable programming element as the argument.</span></span>  
  
3. <span data-ttu-id="122dc-113">呼び出し元のコードでは、引数リストのかっこで引数を囲まないでください。</span><span class="sxs-lookup"><span data-stu-id="122dc-113">In the calling code, do not enclose the argument in parentheses in the argument list.</span></span>  
  
4. <span data-ttu-id="122dc-114">プロシージャコードでは、パラメーター名を使用して、呼び出し元のコードの基になる要素に値を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="122dc-114">In the procedure code, use the parameter name to assign a value to the underlying element in the calling code.</span></span>  
  
 <span data-ttu-id="122dc-115">デモについては、「例」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="122dc-115">See the example further down for a demonstration.</span></span>  
  
## <a name="changing-local-copies"></a><span data-ttu-id="122dc-116">ローカルコピーの変更</span><span class="sxs-lookup"><span data-stu-id="122dc-116">Changing Local Copies</span></span>  
 <span data-ttu-id="122dc-117">呼び出し元のコード内の基になる要素が変更不可能な要素である場合、または引数が `ByVal`渡される場合、プロシージャは呼び出し元のコード内の値を変更できません。</span><span class="sxs-lookup"><span data-stu-id="122dc-117">If the underlying element in the calling code is a nonmodifiable element, or if the argument is passed `ByVal`, the procedure cannot change its value in the calling code.</span></span> <span data-ttu-id="122dc-118">ただし、このプロシージャは、このような引数のローカルコピーを変更できます。</span><span class="sxs-lookup"><span data-stu-id="122dc-118">However, the procedure can change its local copy of such an argument.</span></span>  
  
#### <a name="to-change-the-copy-of-a-procedure-argument-in-the-procedure-code"></a><span data-ttu-id="122dc-119">プロシージャコードのプロシージャ引数のコピーを変更するには</span><span class="sxs-lookup"><span data-stu-id="122dc-119">To change the copy of a procedure argument in the procedure code</span></span>  
  
1. <span data-ttu-id="122dc-120">プロシージャの宣言で、引数に対応するパラメーターに[ByVal](../../../../visual-basic/language-reference/modifiers/byval.md)を指定します。</span><span class="sxs-lookup"><span data-stu-id="122dc-120">In the procedure declaration, specify [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) for the parameter corresponding to the argument.</span></span>  
  
     <span data-ttu-id="122dc-121">または</span><span class="sxs-lookup"><span data-stu-id="122dc-121">-or-</span></span>  
  
     <span data-ttu-id="122dc-122">呼び出し元のコードの引数リストで、引数をかっこで囲みます。</span><span class="sxs-lookup"><span data-stu-id="122dc-122">In the calling code, enclose the argument in parentheses in the argument list.</span></span> <span data-ttu-id="122dc-123">これにより、対応するパラメーターで `ByRef`が指定されている場合でも、値渡しで引数を渡すことが Visual Basic されます。</span><span class="sxs-lookup"><span data-stu-id="122dc-123">This forces Visual Basic to pass the argument by value, even if the corresponding parameter specifies `ByRef`.</span></span>  
  
2. <span data-ttu-id="122dc-124">プロシージャコードでは、パラメーター名を使用して、引数のローカルコピーに値を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="122dc-124">In the procedure code, use the parameter name to assign a value to the local copy of the argument.</span></span> <span data-ttu-id="122dc-125">呼び出し元のコードの基になる値は変更されません。</span><span class="sxs-lookup"><span data-stu-id="122dc-125">The underlying value in the calling code is not changed.</span></span>  
  
## <a name="example"></a><span data-ttu-id="122dc-126">例</span><span class="sxs-lookup"><span data-stu-id="122dc-126">Example</span></span>  
 <span data-ttu-id="122dc-127">次の例は、配列変数を受け取り、その要素を操作する2つのプロシージャを示しています。</span><span class="sxs-lookup"><span data-stu-id="122dc-127">The following example shows two procedures that take an array variable and operate on its elements.</span></span> <span data-ttu-id="122dc-128">`increase` の手順では、単に各要素に1つを追加します。</span><span class="sxs-lookup"><span data-stu-id="122dc-128">The `increase` procedure simply adds one to each element.</span></span> <span data-ttu-id="122dc-129">`replace` プロシージャは、新しい配列をパラメーター `a()` に割り当て、各要素に1つを追加します。</span><span class="sxs-lookup"><span data-stu-id="122dc-129">The `replace` procedure assigns a new array to the parameter `a()` and then adds one to each element.</span></span>  
  
 [!code-vb[VbVbcnProcedures#35](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#35)]  
  
 [!code-vb[VbVbcnProcedures#36](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#36)]  
  
 [!code-vb[VbVbcnProcedures#37](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#37)]  
  
 <span data-ttu-id="122dc-130">最初の `MsgBox` の呼び出しでは、"後に増加する (n):11, 21, 31, 41" と表示されます。</span><span class="sxs-lookup"><span data-stu-id="122dc-130">The first `MsgBox` call displays "After increase(n): 11, 21, 31, 41".</span></span> <span data-ttu-id="122dc-131">配列 `n` は参照型であるため、渡される機構が `ByVal`場合でも、`replace` はそのメンバーを変更できます。</span><span class="sxs-lookup"><span data-stu-id="122dc-131">Because the array `n` is a reference type, `replace` can change its members, even though the passing mechanism is `ByVal`.</span></span>  
  
 <span data-ttu-id="122dc-132">2番目の `MsgBox` 呼び出しでは、"置換後 (n): 101, 201, 301" と表示されます。</span><span class="sxs-lookup"><span data-stu-id="122dc-132">The second `MsgBox` call displays "After replace(n): 101, 201, 301".</span></span> <span data-ttu-id="122dc-133">`n` は `ByRef`渡されるので、`replace` は呼び出し元のコードの変数 `n` を変更し、その変数に新しい配列を割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="122dc-133">Because `n` is passed `ByRef`, `replace` can modify the variable `n` in the calling code and assign a new array to it.</span></span> <span data-ttu-id="122dc-134">`n` は参照型であるため、`replace` はそのメンバーを変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="122dc-134">Because `n` is a reference type, `replace` can also change its members.</span></span>  
  
 <span data-ttu-id="122dc-135">プロシージャが呼び出し元のコードで変数自体を変更しないようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="122dc-135">You can prevent the procedure from modifying the variable itself in the calling code.</span></span> <span data-ttu-id="122dc-136">「[方法: プロシージャ引数を値の変更に対して保護](./how-to-protect-a-procedure-argument-against-value-changes.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="122dc-136">See [How to: Protect a Procedure Argument Against Value Changes](./how-to-protect-a-procedure-argument-against-value-changes.md).</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="122dc-137">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="122dc-137">Compiling the Code</span></span>  
 <span data-ttu-id="122dc-138">変数を参照渡しで渡す場合は、`ByRef` キーワードを使用してこのメカニズムを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="122dc-138">When you pass a variable by reference, you must use the `ByRef` keyword to specify this mechanism.</span></span>  
  
 <span data-ttu-id="122dc-139">Visual Basic の既定では、値渡しで引数を渡します。</span><span class="sxs-lookup"><span data-stu-id="122dc-139">The default in Visual Basic is to pass arguments by value.</span></span> <span data-ttu-id="122dc-140">ただし、すべての宣言されたパラメーターに[ByVal](../../../../visual-basic/language-reference/modifiers/byval.md)キーワードまたは[ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)キーワードを含めることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="122dc-140">However, it is good programming practice to include either the [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) or [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) keyword with every declared parameter.</span></span> <span data-ttu-id="122dc-141">これにより、コードが読みやすくなります。</span><span class="sxs-lookup"><span data-stu-id="122dc-141">This makes your code easier to read.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="122dc-142">.NET Framework のセキュリティ</span><span class="sxs-lookup"><span data-stu-id="122dc-142">.NET Framework Security</span></span>  
 <span data-ttu-id="122dc-143">プロシージャが呼び出し元のコードの引数の基になる値を変更できるようにすると、常にリスクが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="122dc-143">There is always a potential risk in allowing a procedure to change the value underlying an argument in the calling code.</span></span> <span data-ttu-id="122dc-144">この値が変更されることが予想されることを確認し、使用前に有効かどうかを確認できるように準備してください。</span><span class="sxs-lookup"><span data-stu-id="122dc-144">Make sure you expect this value to be changed, and be prepared to check it for validity before using it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="122dc-145">参照</span><span class="sxs-lookup"><span data-stu-id="122dc-145">See also</span></span>

- [<span data-ttu-id="122dc-146">手順</span><span class="sxs-lookup"><span data-stu-id="122dc-146">Procedures</span></span>](./index.md)
- [<span data-ttu-id="122dc-147">プロシージャのパラメーターと引数</span><span class="sxs-lookup"><span data-stu-id="122dc-147">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="122dc-148">方法: プロシージャに引数を渡す</span><span class="sxs-lookup"><span data-stu-id="122dc-148">How to: Pass Arguments to a Procedure</span></span>](./how-to-pass-arguments-to-a-procedure.md)
- [<span data-ttu-id="122dc-149">引数の値渡しと参照渡し</span><span class="sxs-lookup"><span data-stu-id="122dc-149">Passing Arguments by Value and by Reference</span></span>](./passing-arguments-by-value-and-by-reference.md)
- [<span data-ttu-id="122dc-150">変更できる引数と変更できない引数の違い</span><span class="sxs-lookup"><span data-stu-id="122dc-150">Differences Between Modifiable and Nonmodifiable Arguments</span></span>](./differences-between-modifiable-and-nonmodifiable-arguments.md)
- [<span data-ttu-id="122dc-151">引数の値渡しと参照渡しの違い</span><span class="sxs-lookup"><span data-stu-id="122dc-151">Differences Between Passing an Argument By Value and By Reference</span></span>](./differences-between-passing-an-argument-by-value-and-by-reference.md)
- [<span data-ttu-id="122dc-152">方法: プロシージャ引数の値が変化しないようにする</span><span class="sxs-lookup"><span data-stu-id="122dc-152">How to: Protect a Procedure Argument Against Value Changes</span></span>](./how-to-protect-a-procedure-argument-against-value-changes.md)
- [<span data-ttu-id="122dc-153">方法: 引数の値渡しを強制する</span><span class="sxs-lookup"><span data-stu-id="122dc-153">How to: Force an Argument to Be Passed by Value</span></span>](./how-to-force-an-argument-to-be-passed-by-value.md)
- [<span data-ttu-id="122dc-154">位置と名前による引数渡し</span><span class="sxs-lookup"><span data-stu-id="122dc-154">Passing Arguments by Position and by Name</span></span>](./passing-arguments-by-position-and-by-name.md)
- [<span data-ttu-id="122dc-155">値型と参照型</span><span class="sxs-lookup"><span data-stu-id="122dc-155">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
