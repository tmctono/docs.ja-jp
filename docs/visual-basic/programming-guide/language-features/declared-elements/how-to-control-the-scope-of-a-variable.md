---
title: '方法: 変数 (Visual Basic) のスコープを制御します。'
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], scope
- declared elements [Visual Basic], scope
- visibility [Visual Basic], declared elements
- variables [Visual Basic], visibility
- scope [Visual Basic], declared elements
- scope [Visual Basic], variables
- scope [Visual Basic], Visual Basic
- declared elements [Visual Basic], visibility
- visibility [Visual Basic], variables
ms.assetid: 44b7f62a-cb5c-4d50-bce9-60ae68f87072
ms.openlocfilehash: 24a7ae3b8f3400beeaedb20ea6352ea44bdb7597
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59324319"
---
# <a name="how-to-control-the-scope-of-a-variable-visual-basic"></a><span data-ttu-id="9f218-102">方法: 変数 (Visual Basic) のスコープを制御します。</span><span class="sxs-lookup"><span data-stu-id="9f218-102">How to: Control the Scope of a Variable (Visual Basic)</span></span>
<span data-ttu-id="9f218-103">変数が、通常、*スコープ*、または宣言をリージョン全体での参照を表示します。</span><span class="sxs-lookup"><span data-stu-id="9f218-103">Normally, a variable is in *scope*, or visible for reference, throughout the region in which you declare it.</span></span> <span data-ttu-id="9f218-104">場合によっては、変数の*アクセス レベル*そのスコープに影響を与えることができます。</span><span class="sxs-lookup"><span data-stu-id="9f218-104">In some cases, the variable's *access level* can influence its scope.</span></span>  
  
 <span data-ttu-id="9f218-105">詳細については、「 [Scope in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9f218-105">For more information, see [Scope in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md).</span></span>  
  
## <a name="scope-at-block-or-procedure-level"></a><span data-ttu-id="9f218-106">ブロックまたはプロシージャ レベルのスコープ</span><span class="sxs-lookup"><span data-stu-id="9f218-106">Scope at Block or Procedure Level</span></span>  
  
#### <a name="to-make-a-variable-visible-only-within-a-block"></a><span data-ttu-id="9f218-107">変数をブロック内でのみ表示されるようにするには</span><span class="sxs-lookup"><span data-stu-id="9f218-107">To make a variable visible only within a block</span></span>  
  
-   <span data-ttu-id="9f218-108">場所、 [Dim ステートメント](../../../../visual-basic/language-reference/statements/dim-statement.md)の開始との間など、そのブロックの宣言ステートメントの終了の間、変数、`For`と`Next`のステートメントを`For`ループします。</span><span class="sxs-lookup"><span data-stu-id="9f218-108">Place the [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md) for the variable between the initiating and terminating declaration statements of that block, for example between the `For` and `Next` statements of a `For` loop.</span></span>  
  
     <span data-ttu-id="9f218-109">ブロック内からのみ、変数を参照することができます。</span><span class="sxs-lookup"><span data-stu-id="9f218-109">You can refer to the variable only from within the block.</span></span>  
  
#### <a name="to-make-a-variable-visible-only-within-a-procedure"></a><span data-ttu-id="9f218-110">変数をプロシージャ内でのみ表示されるようにするには</span><span class="sxs-lookup"><span data-stu-id="9f218-110">To make a variable visible only within a procedure</span></span>  
  
-   <span data-ttu-id="9f218-111">場所、`Dim`変数、プロシージャ内では、ブロックの外側のステートメント (など、 `With`.`End With`ブロック)。</span><span class="sxs-lookup"><span data-stu-id="9f218-111">Place the `Dim` statement for the variable inside the procedure but outside any block (such as a `With`...`End With` block).</span></span>  
  
     <span data-ttu-id="9f218-112">プロシージャに含まれる各ブロックの内部を含むプロシージャ内からのみ、変数を参照することができます。</span><span class="sxs-lookup"><span data-stu-id="9f218-112">You can refer to the variable only from within the procedure, including inside any block contained in the procedure.</span></span>  
  
## <a name="scope-at-module-or-namespace-level"></a><span data-ttu-id="9f218-113">モジュールまたは Namespace レベルのスコープ</span><span class="sxs-lookup"><span data-stu-id="9f218-113">Scope at Module or Namespace Level</span></span>  
 <span data-ttu-id="9f218-114">便宜上、1 つの用語*モジュール レベル*モジュール、クラス、および構造に当てはまります。</span><span class="sxs-lookup"><span data-stu-id="9f218-114">For convenience, the single term *module level* applies equally to modules, classes, and structures.</span></span> <span data-ttu-id="9f218-115">モジュール レベル変数のアクセス レベルは、そのスコープを決定します。</span><span class="sxs-lookup"><span data-stu-id="9f218-115">The access level of a module level variable determines its scope.</span></span> <span data-ttu-id="9f218-116">モジュール、クラスまたは構造体を含む名前空間スコープにも影響します。</span><span class="sxs-lookup"><span data-stu-id="9f218-116">The namespace that contains the module, class, or structure also influences the scope.</span></span>  
  
#### <a name="to-make-a-variable-visible-throughout-a-module-class-or-structure"></a><span data-ttu-id="9f218-117">変数をモジュール、クラスまたは構造体全体にわたって表示されるようにするには</span><span class="sxs-lookup"><span data-stu-id="9f218-117">To make a variable visible throughout a module, class, or structure</span></span>  
  
1. <span data-ttu-id="9f218-118">場所、`Dim`変数ではなく、プロシージャの外部モジュール、クラス、または構造体には、内部のステートメント。</span><span class="sxs-lookup"><span data-stu-id="9f218-118">Place the `Dim` statement for the variable inside the module, class, or structure, but outside any procedure.</span></span>  
  
2. <span data-ttu-id="9f218-119">含める、[プライベート](../../../../visual-basic/language-reference/modifiers/private.md)キーワード、`Dim`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="9f218-119">Include the [Private](../../../../visual-basic/language-reference/modifiers/private.md) keyword in the `Dim` statement.</span></span>  
  
3. <span data-ttu-id="9f218-120">なく、モジュール、クラス、または構造内で任意の場所から変数を参照できる外です。</span><span class="sxs-lookup"><span data-stu-id="9f218-120">You can refer to the variable from anywhere within the module, class, or structure, but not from outside it.</span></span>  
  
#### <a name="to-make-a-variable-visible-throughout-a-namespace"></a><span data-ttu-id="9f218-121">変数を名前空間全体で表示されるようにするには</span><span class="sxs-lookup"><span data-stu-id="9f218-121">To make a variable visible throughout a namespace</span></span>  
  
1. <span data-ttu-id="9f218-122">場所、`Dim`変数ではなく、プロシージャの外部モジュール、クラス、または構造体には、内部のステートメント。</span><span class="sxs-lookup"><span data-stu-id="9f218-122">Place the `Dim` statement for the variable inside the module, class, or structure, but outside any procedure.</span></span>  
  
2. <span data-ttu-id="9f218-123">含める、[フレンド](../../../../visual-basic/language-reference/modifiers/friend.md)または[パブリック](../../../../visual-basic/language-reference/modifiers/public.md)キーワード、`Dim`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="9f218-123">Include the [Friend](../../../../visual-basic/language-reference/modifiers/friend.md) or [Public](../../../../visual-basic/language-reference/modifiers/public.md) keyword in the `Dim` statement.</span></span>  
  
3. <span data-ttu-id="9f218-124">任意の場所から変数を参照できるモジュール、クラスまたは構造体を含む名前空間内で。</span><span class="sxs-lookup"><span data-stu-id="9f218-124">You can refer to the variable from anywhere within the namespace containing the module, class, or structure.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9f218-125">例</span><span class="sxs-lookup"><span data-stu-id="9f218-125">Example</span></span>  
 <span data-ttu-id="9f218-126">次の例では、モジュール レベル変数を宣言し、モジュール内のコードをその可視性を制限します。</span><span class="sxs-lookup"><span data-stu-id="9f218-126">The following example declares a variable at module level and limits its visibility to code within the module.</span></span>  
  
```  
Module demonstrateScope  
    Private strMsg As String  
    Sub initializePrivateVariable()  
        strMsg = "This variable cannot be used outside this module."  
    End Sub  
    Sub usePrivateVariable()  
        MsgBox(strMsg)  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="9f218-127">前の例では、すべてのプロシージャはモジュールで定義されている`demonstrateScope`できますを参照してください、`String`変数`strMsg`します。</span><span class="sxs-lookup"><span data-stu-id="9f218-127">In the preceding example, all the procedures defined in module `demonstrateScope` can refer to the `String` variable `strMsg`.</span></span> <span data-ttu-id="9f218-128">ときに、`usePrivateVariable`プロシージャが呼び出されると、文字列変数の内容を表示`strMsg` ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="9f218-128">When the `usePrivateVariable` procedure is called, it displays the contents of the string variable `strMsg` in a dialog box.</span></span>  
  
 <span data-ttu-id="9f218-129">上記の例では、文字列変数に次の変更と`strMsg`宣言の名前空間内のすべてのコードで参照できます。</span><span class="sxs-lookup"><span data-stu-id="9f218-129">With the following alteration to the preceding example, the string variable `strMsg` can be referred to by code anywhere in the namespace of its declaration.</span></span>  
  
```  
Public strMsg As String  
```  
  
## <a name="robust-programming"></a><span data-ttu-id="9f218-130">信頼性の高いプログラミング</span><span class="sxs-lookup"><span data-stu-id="9f218-130">Robust Programming</span></span>  
 <span data-ttu-id="9f218-131">同じ名前の別の変数の代わりに誤って参照することがある可能性は少なく、変数より狭いスコープ</span><span class="sxs-lookup"><span data-stu-id="9f218-131">The narrower the scope of a variable, the fewer opportunities you have for accidentally referring to it in place of another variable with the same name.</span></span> <span data-ttu-id="9f218-132">参照の対応付けの問題を最小限に抑えることができますも。</span><span class="sxs-lookup"><span data-stu-id="9f218-132">You can also minimize problems of reference matching.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="9f218-133">.NET Framework セキュリティ</span><span class="sxs-lookup"><span data-stu-id="9f218-133">.NET Framework Security</span></span>  
 <span data-ttu-id="9f218-134">変数のスコープが狭い悪意のあるコードが不正に、小さい方の可能性は、その使用します。</span><span class="sxs-lookup"><span data-stu-id="9f218-134">The narrower the scope of a variable, the smaller the chances that malicious code can make improper use of it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f218-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="9f218-135">See also</span></span>

- [<span data-ttu-id="9f218-136">Visual Basic におけるスコープ</span><span class="sxs-lookup"><span data-stu-id="9f218-136">Scope in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)
- [<span data-ttu-id="9f218-137">Visual Basic での有効期間</span><span class="sxs-lookup"><span data-stu-id="9f218-137">Lifetime in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md)
- [<span data-ttu-id="9f218-138">Visual Basic でのアクセス レベル</span><span class="sxs-lookup"><span data-stu-id="9f218-138">Access levels in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
- [<span data-ttu-id="9f218-139">変数</span><span class="sxs-lookup"><span data-stu-id="9f218-139">Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/index.md)
- [<span data-ttu-id="9f218-140">変数宣言</span><span class="sxs-lookup"><span data-stu-id="9f218-140">Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
- [<span data-ttu-id="9f218-141">Dim ステートメント</span><span class="sxs-lookup"><span data-stu-id="9f218-141">Dim Statement</span></span>](../../../../visual-basic/language-reference/statements/dim-statement.md)
