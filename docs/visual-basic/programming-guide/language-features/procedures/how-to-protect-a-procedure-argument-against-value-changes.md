---
title: '方法: プロシージャ引数の値が変化しないようにする'
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
ms.openlocfilehash: b0504d9f7a8862274d5d71dc6a9c1570551629a5
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2020
ms.locfileid: "84414364"
---
# <a name="how-to-protect-a-procedure-argument-against-value-changes-visual-basic"></a><span data-ttu-id="64816-102">方法: プロシージャ引数の値が変更されないように保護する (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="64816-102">How to: Protect a Procedure Argument Against Value Changes (Visual Basic)</span></span>
<span data-ttu-id="64816-103">Visual Basic では、プロシージャでパラメーターが [ByRef](../../../language-reference/modifiers/byref.md) として宣言されている場合、引数の基になる呼び出し元のコードのプログラミング要素への直接参照がプロシージャ コードに渡されます。</span><span class="sxs-lookup"><span data-stu-id="64816-103">If a procedure declares a parameter as [ByRef](../../../language-reference/modifiers/byref.md), Visual Basic gives the procedure code a direct reference to the programming element underlying the argument in the calling code.</span></span> <span data-ttu-id="64816-104">これにより、プロシージャは引数の基になる呼び出し元のコードの値を変更できます。</span><span class="sxs-lookup"><span data-stu-id="64816-104">This permits the procedure to change the value underlying the argument in the calling code.</span></span> <span data-ttu-id="64816-105">呼び出し元のコードで、そのような変更から保護することが必要な場合もあります。</span><span class="sxs-lookup"><span data-stu-id="64816-105">In some cases the calling code might want to protect against such a change.</span></span>  
  
 <span data-ttu-id="64816-106">プロシージャで対応するパラメーターを [ByVal](../../../language-reference/modifiers/byval.md) として宣言することで、引数を変更から常に保護できます。</span><span class="sxs-lookup"><span data-stu-id="64816-106">You can always protect an argument from change by declaring the corresponding parameter [ByVal](../../../language-reference/modifiers/byval.md) in the procedure.</span></span> <span data-ttu-id="64816-107">特定の引数を一部のケースでは変更できるようにし、他のケースでは変更できないようにする場合は、その引数を `ByRef` として宣言し、呼び出し元のコードが呼び出しごとに引渡し方法を決定できるようにします。</span><span class="sxs-lookup"><span data-stu-id="64816-107">If you want to be able to change a given argument in some cases but not others, you can declare it `ByRef` and let the calling code determine the passing mechanism in each call.</span></span> <span data-ttu-id="64816-108">これを行うには、対応する引数をかっこで囲んで値渡しにするか、かっこで囲まずに参照渡しにします。</span><span class="sxs-lookup"><span data-stu-id="64816-108">It does this by enclosing the corresponding argument in parentheses to pass it by value, or not enclosing it in parentheses to pass it by reference.</span></span> <span data-ttu-id="64816-109">詳細については、[方法: 引数の値渡しを強制する](./how-to-force-an-argument-to-be-passed-by-value.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="64816-109">For more information, see [How to: Force an Argument to Be Passed by Value](./how-to-force-an-argument-to-be-passed-by-value.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="64816-110">例</span><span class="sxs-lookup"><span data-stu-id="64816-110">Example</span></span>  
 <span data-ttu-id="64816-111">次の例は、配列変数を受け取り、その要素を操作する 2 つのプロシージャを示しています。</span><span class="sxs-lookup"><span data-stu-id="64816-111">The following example shows two procedures that take an array variable and operate on its elements.</span></span> <span data-ttu-id="64816-112">`increase` プロシージャは、各要素に 1 を加算するだけです。</span><span class="sxs-lookup"><span data-stu-id="64816-112">The `increase` procedure simply adds one to each element.</span></span> <span data-ttu-id="64816-113">`replace` プロシージャは、`a()` パラメーターに新しい配列を割り当ててから、各要素に 1 を加算します。</span><span class="sxs-lookup"><span data-stu-id="64816-113">The `replace` procedure assigns a new array to the parameter `a()` and then adds one to each element.</span></span> <span data-ttu-id="64816-114">ただし、再割り当ては、呼び出し元のコードの基になる配列変数には影響しません。</span><span class="sxs-lookup"><span data-stu-id="64816-114">However, the reassignment does not affect the underlying array variable in the calling code.</span></span>  
  
 [!code-vb[VbVbcnProcedures#35](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#35)]  
  
 [!code-vb[VbVbcnProcedures#38](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#38)]  
  
 [!code-vb[VbVbcnProcedures#37](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#37)]  
  
 <span data-ttu-id="64816-115">最初の `MsgBox` 呼び出しでは、"After increase(n): 11, 21, 31, 41" と表示されます。</span><span class="sxs-lookup"><span data-stu-id="64816-115">The first `MsgBox` call displays "After increase(n): 11, 21, 31, 41".</span></span> <span data-ttu-id="64816-116">配列 `n` は参照型であるため、引渡し方法が `ByVal` であっても、`increase` はそのメンバーを変更できます。</span><span class="sxs-lookup"><span data-stu-id="64816-116">Because the array `n` is a reference type, `increase` can change its members, even though the passing mechanism is `ByVal`.</span></span>  
  
 <span data-ttu-id="64816-117">2 番目の `MsgBox` 呼び出しでは、"After replace(n): 11, 21, 31, 41" と表示されます。</span><span class="sxs-lookup"><span data-stu-id="64816-117">The second `MsgBox` call displays "After replace(n): 11, 21, 31, 41".</span></span> <span data-ttu-id="64816-118">`n` は `ByVal` で渡されるため、`replace` は呼び出し元のコードの変数 `n` に新しい配列を割り当てて変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="64816-118">Because `n` is passed `ByVal`, `replace` cannot modify the variable `n` in the calling code by assigning a new array to it.</span></span> <span data-ttu-id="64816-119">`replace` が新しい配列インスタンス `k` を作成し、ローカル変数 `a` に割り当てると、呼び出し元のコードによって渡された `n` への参照は失われます。</span><span class="sxs-lookup"><span data-stu-id="64816-119">When `replace` creates the new array instance `k` and assigns it to the local variable `a`, it loses the reference to `n` passed in by the calling code.</span></span> <span data-ttu-id="64816-120">`a` のメンバーを変更すると、ローカル配列 `k` だけが影響を受けます。</span><span class="sxs-lookup"><span data-stu-id="64816-120">When it changes the members of `a`, only the local array `k` is affected.</span></span> <span data-ttu-id="64816-121">したがって、`replace` は呼び出し元のコードの配列 `n` の値をインクリメントしません。</span><span class="sxs-lookup"><span data-stu-id="64816-121">Therefore, `replace` does not increment the values of array `n` in the calling code.</span></span>  
  
## <a name="compile-the-code"></a><span data-ttu-id="64816-122">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="64816-122">Compile the code</span></span>  
 <span data-ttu-id="64816-123">Visual Basic の既定では、引数は値渡しになります。</span><span class="sxs-lookup"><span data-stu-id="64816-123">The default in Visual Basic is to pass arguments by value.</span></span> <span data-ttu-id="64816-124">ただし、宣言されるすべてのパラメーターに、[ByVal](../../../language-reference/modifiers/byval.md) または [ByRef](../../../language-reference/modifiers/byref.md) キーワードを含めることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="64816-124">However, it is good programming practice to include either the [ByVal](../../../language-reference/modifiers/byval.md) or [ByRef](../../../language-reference/modifiers/byref.md) keyword with every declared parameter.</span></span> <span data-ttu-id="64816-125">これにより、コードが読みやすくなります。</span><span class="sxs-lookup"><span data-stu-id="64816-125">This makes your code easier to read.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64816-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="64816-126">See also</span></span>

- [<span data-ttu-id="64816-127">手順</span><span class="sxs-lookup"><span data-stu-id="64816-127">Procedures</span></span>](./index.md)
- [<span data-ttu-id="64816-128">プロシージャのパラメーターと引数</span><span class="sxs-lookup"><span data-stu-id="64816-128">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="64816-129">方法: プロシージャに引数を渡す</span><span class="sxs-lookup"><span data-stu-id="64816-129">How to: Pass Arguments to a Procedure</span></span>](./how-to-pass-arguments-to-a-procedure.md)
- [<span data-ttu-id="64816-130">引数の値渡しと参照渡し</span><span class="sxs-lookup"><span data-stu-id="64816-130">Passing Arguments by Value and by Reference</span></span>](./passing-arguments-by-value-and-by-reference.md)
- [<span data-ttu-id="64816-131">変更できる引数と変更できない引数の違い</span><span class="sxs-lookup"><span data-stu-id="64816-131">Differences Between Modifiable and Nonmodifiable Arguments</span></span>](./differences-between-modifiable-and-nonmodifiable-arguments.md)
- [<span data-ttu-id="64816-132">引数の値渡しと参照渡しの違い</span><span class="sxs-lookup"><span data-stu-id="64816-132">Differences Between Passing an Argument By Value and By Reference</span></span>](./differences-between-passing-an-argument-by-value-and-by-reference.md)
- [<span data-ttu-id="64816-133">方法: プロシージャ引数の値を変更する</span><span class="sxs-lookup"><span data-stu-id="64816-133">How to: Change the Value of a Procedure Argument</span></span>](./how-to-change-the-value-of-a-procedure-argument.md)
- [<span data-ttu-id="64816-134">方法: 引数の値渡しを強制する</span><span class="sxs-lookup"><span data-stu-id="64816-134">How to: Force an Argument to Be Passed by Value</span></span>](./how-to-force-an-argument-to-be-passed-by-value.md)
- [<span data-ttu-id="64816-135">位置と名前による引数渡し</span><span class="sxs-lookup"><span data-stu-id="64816-135">Passing Arguments by Position and by Name</span></span>](./passing-arguments-by-position-and-by-name.md)
- [<span data-ttu-id="64816-136">Value Types and Reference Types</span><span class="sxs-lookup"><span data-stu-id="64816-136">Value Types and Reference Types</span></span>](../data-types/value-types-and-reference-types.md)
