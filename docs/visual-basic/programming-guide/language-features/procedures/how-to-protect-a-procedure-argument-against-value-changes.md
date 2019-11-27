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
ms.openlocfilehash: 36092eb597b5b20e1da42cd9d15ab8633636cfb1
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344854"
---
# <a name="how-to-protect-a-procedure-argument-against-value-changes-visual-basic"></a><span data-ttu-id="ab17d-102">方法: プロシージャ引数の値が変化しないようにする (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ab17d-102">How to: Protect a Procedure Argument Against Value Changes (Visual Basic)</span></span>
<span data-ttu-id="ab17d-103">プロシージャがパラメーターを[ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)として宣言している場合、Visual Basic は、呼び出し元のコードの引数の基になるプログラミング要素への直接参照をプロシージャコードに付与します。</span><span class="sxs-lookup"><span data-stu-id="ab17d-103">If a procedure declares a parameter as [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), Visual Basic gives the procedure code a direct reference to the programming element underlying the argument in the calling code.</span></span> <span data-ttu-id="ab17d-104">これにより、プロシージャは、呼び出し元のコードの引数の基になる値を変更できます。</span><span class="sxs-lookup"><span data-stu-id="ab17d-104">This permits the procedure to change the value underlying the argument in the calling code.</span></span> <span data-ttu-id="ab17d-105">場合によっては、呼び出し元のコードでこのような変更から保護することが必要になることがあります。</span><span class="sxs-lookup"><span data-stu-id="ab17d-105">In some cases the calling code might want to protect against such a change.</span></span>  
  
 <span data-ttu-id="ab17d-106">プロシージャ内で対応するパラメーター [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md)を宣言することによって、変更から引数を常に保護することができます。</span><span class="sxs-lookup"><span data-stu-id="ab17d-106">You can always protect an argument from change by declaring the corresponding parameter [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) in the procedure.</span></span> <span data-ttu-id="ab17d-107">特定の引数を他のケース以外でも変更できるようにする場合は、その引数を `ByRef` 宣言し、呼び出し元のコードが各呼び出しで渡される機構を決定できるようにします。</span><span class="sxs-lookup"><span data-stu-id="ab17d-107">If you want to be able to change a given argument in some cases but not others, you can declare it `ByRef` and let the calling code determine the passing mechanism in each call.</span></span> <span data-ttu-id="ab17d-108">これを行うには、対応する引数をかっこで囲み、値で渡します。または、かっこで囲まないようにして、参照渡しで渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="ab17d-108">It does this by enclosing the corresponding argument in parentheses to pass it by value, or not enclosing it in parentheses to pass it by reference.</span></span> <span data-ttu-id="ab17d-109">詳細については、「[方法: 引数を強制的に値で渡す](./how-to-force-an-argument-to-be-passed-by-value.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ab17d-109">For more information, see [How to: Force an Argument to Be Passed by Value](./how-to-force-an-argument-to-be-passed-by-value.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ab17d-110">例</span><span class="sxs-lookup"><span data-stu-id="ab17d-110">Example</span></span>  
 <span data-ttu-id="ab17d-111">次の例は、配列変数を受け取り、その要素を操作する2つのプロシージャを示しています。</span><span class="sxs-lookup"><span data-stu-id="ab17d-111">The following example shows two procedures that take an array variable and operate on its elements.</span></span> <span data-ttu-id="ab17d-112">`increase` の手順では、単に各要素に1つを追加します。</span><span class="sxs-lookup"><span data-stu-id="ab17d-112">The `increase` procedure simply adds one to each element.</span></span> <span data-ttu-id="ab17d-113">`replace` プロシージャは、新しい配列をパラメーター `a()` に割り当て、各要素に1つを追加します。</span><span class="sxs-lookup"><span data-stu-id="ab17d-113">The `replace` procedure assigns a new array to the parameter `a()` and then adds one to each element.</span></span> <span data-ttu-id="ab17d-114">ただし、再割り当ては、呼び出し元のコード内の基になる配列変数には影響しません。</span><span class="sxs-lookup"><span data-stu-id="ab17d-114">However, the reassignment does not affect the underlying array variable in the calling code.</span></span>  
  
 [!code-vb[VbVbcnProcedures#35](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#35)]  
  
 [!code-vb[VbVbcnProcedures#38](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#38)]  
  
 [!code-vb[VbVbcnProcedures#37](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#37)]  
  
 <span data-ttu-id="ab17d-115">最初の `MsgBox` の呼び出しでは、"後に増加する (n):11, 21, 31, 41" と表示されます。</span><span class="sxs-lookup"><span data-stu-id="ab17d-115">The first `MsgBox` call displays "After increase(n): 11, 21, 31, 41".</span></span> <span data-ttu-id="ab17d-116">配列 `n` は参照型であるため、渡される機構が `ByVal`場合でも、`increase` はそのメンバーを変更できます。</span><span class="sxs-lookup"><span data-stu-id="ab17d-116">Because the array `n` is a reference type, `increase` can change its members, even though the passing mechanism is `ByVal`.</span></span>  
  
 <span data-ttu-id="ab17d-117">2番目の `MsgBox` 呼び出しでは、"After replace (n):11, 21, 31, 41" と表示されます。</span><span class="sxs-lookup"><span data-stu-id="ab17d-117">The second `MsgBox` call displays "After replace(n): 11, 21, 31, 41".</span></span> <span data-ttu-id="ab17d-118">`n` は `ByVal`渡されるので、`replace` 新しい配列を割り当てることによって、呼び出し元のコードの変数 `n` を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="ab17d-118">Because `n` is passed `ByVal`, `replace` cannot modify the variable `n` in the calling code by assigning a new array to it.</span></span> <span data-ttu-id="ab17d-119">`replace` によって新しい配列インスタンス `k` 作成され、それがローカル変数 `a`に代入されると、呼び出し元のコードによって渡された `n` への参照が失われます。</span><span class="sxs-lookup"><span data-stu-id="ab17d-119">When `replace` creates the new array instance `k` and assigns it to the local variable `a`, it loses the reference to `n` passed in by the calling code.</span></span> <span data-ttu-id="ab17d-120">`a`のメンバーを変更すると、ローカル配列 `k` のみが影響を受けます。</span><span class="sxs-lookup"><span data-stu-id="ab17d-120">When it changes the members of `a`, only the local array `k` is affected.</span></span> <span data-ttu-id="ab17d-121">したがって、`replace` では、呼び出し元のコードの配列 `n` の値はインクリメントされません。</span><span class="sxs-lookup"><span data-stu-id="ab17d-121">Therefore, `replace` does not increment the values of array `n` in the calling code.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="ab17d-122">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="ab17d-122">Compiling the Code</span></span>  
 <span data-ttu-id="ab17d-123">Visual Basic の既定では、値渡しで引数を渡します。</span><span class="sxs-lookup"><span data-stu-id="ab17d-123">The default in Visual Basic is to pass arguments by value.</span></span> <span data-ttu-id="ab17d-124">ただし、すべての宣言されたパラメーターに[ByVal](../../../../visual-basic/language-reference/modifiers/byval.md)キーワードまたは[ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)キーワードを含めることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="ab17d-124">However, it is good programming practice to include either the [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) or [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) keyword with every declared parameter.</span></span> <span data-ttu-id="ab17d-125">これにより、コードが読みやすくなります。</span><span class="sxs-lookup"><span data-stu-id="ab17d-125">This makes your code easier to read.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab17d-126">参照</span><span class="sxs-lookup"><span data-stu-id="ab17d-126">See also</span></span>

- [<span data-ttu-id="ab17d-127">手順</span><span class="sxs-lookup"><span data-stu-id="ab17d-127">Procedures</span></span>](./index.md)
- [<span data-ttu-id="ab17d-128">プロシージャのパラメーターと引数</span><span class="sxs-lookup"><span data-stu-id="ab17d-128">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="ab17d-129">方法: プロシージャに引数を渡す</span><span class="sxs-lookup"><span data-stu-id="ab17d-129">How to: Pass Arguments to a Procedure</span></span>](./how-to-pass-arguments-to-a-procedure.md)
- [<span data-ttu-id="ab17d-130">引数の値渡しと参照渡し</span><span class="sxs-lookup"><span data-stu-id="ab17d-130">Passing Arguments by Value and by Reference</span></span>](./passing-arguments-by-value-and-by-reference.md)
- [<span data-ttu-id="ab17d-131">変更できる引数と変更できない引数の違い</span><span class="sxs-lookup"><span data-stu-id="ab17d-131">Differences Between Modifiable and Nonmodifiable Arguments</span></span>](./differences-between-modifiable-and-nonmodifiable-arguments.md)
- [<span data-ttu-id="ab17d-132">引数の値渡しと参照渡しの違い</span><span class="sxs-lookup"><span data-stu-id="ab17d-132">Differences Between Passing an Argument By Value and By Reference</span></span>](./differences-between-passing-an-argument-by-value-and-by-reference.md)
- [<span data-ttu-id="ab17d-133">方法: プロシージャ引数の値を変更する</span><span class="sxs-lookup"><span data-stu-id="ab17d-133">How to: Change the Value of a Procedure Argument</span></span>](./how-to-change-the-value-of-a-procedure-argument.md)
- [<span data-ttu-id="ab17d-134">方法: 引数の値渡しを強制する</span><span class="sxs-lookup"><span data-stu-id="ab17d-134">How to: Force an Argument to Be Passed by Value</span></span>](./how-to-force-an-argument-to-be-passed-by-value.md)
- [<span data-ttu-id="ab17d-135">位置と名前による引数渡し</span><span class="sxs-lookup"><span data-stu-id="ab17d-135">Passing Arguments by Position and by Name</span></span>](./passing-arguments-by-position-and-by-name.md)
- [<span data-ttu-id="ab17d-136">値型と参照型</span><span class="sxs-lookup"><span data-stu-id="ab17d-136">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
