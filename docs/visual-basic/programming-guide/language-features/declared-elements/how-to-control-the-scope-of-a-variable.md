---
title: '方法 : 変数のスコープを制御する'
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
ms.openlocfilehash: 0ee6ce183310aa836ecdbbc0bc819e0e83d1872d
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345377"
---
# <a name="how-to-control-the-scope-of-a-variable-visual-basic"></a><span data-ttu-id="9d630-102">方法: 変数のスコープを制御する (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9d630-102">How to: Control the Scope of a Variable (Visual Basic)</span></span>
<span data-ttu-id="9d630-103">通常、変数は、宣言する領域全体で*スコープ*内にあるか、参照用に表示されます。</span><span class="sxs-lookup"><span data-stu-id="9d630-103">Normally, a variable is in *scope*, or visible for reference, throughout the region in which you declare it.</span></span> <span data-ttu-id="9d630-104">場合によっては、変数の*アクセスレベル*がそのスコープに影響を与えることがあります。</span><span class="sxs-lookup"><span data-stu-id="9d630-104">In some cases, the variable's *access level* can influence its scope.</span></span>  
  
 <span data-ttu-id="9d630-105">詳細については、「 [Scope in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9d630-105">For more information, see [Scope in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md).</span></span>  
  
## <a name="scope-at-block-or-procedure-level"></a><span data-ttu-id="9d630-106">ブロックレベルまたはプロシージャレベルのスコープ</span><span class="sxs-lookup"><span data-stu-id="9d630-106">Scope at Block or Procedure Level</span></span>  
  
#### <a name="to-make-a-variable-visible-only-within-a-block"></a><span data-ttu-id="9d630-107">変数がブロック内でのみ表示されるようにするには</span><span class="sxs-lookup"><span data-stu-id="9d630-107">To make a variable visible only within a block</span></span>  
  
- <span data-ttu-id="9d630-108">`For` ループの `For` ステートメントと `Next` ステートメントの間で、そのブロックの開始宣言ステートメントと終了宣言ステートメントの間に変数の[Dim ステートメント](../../../../visual-basic/language-reference/statements/dim-statement.md)を配置します。</span><span class="sxs-lookup"><span data-stu-id="9d630-108">Place the [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md) for the variable between the initiating and terminating declaration statements of that block, for example between the `For` and `Next` statements of a `For` loop.</span></span>  
  
     <span data-ttu-id="9d630-109">変数は、ブロック内からのみ参照できます。</span><span class="sxs-lookup"><span data-stu-id="9d630-109">You can refer to the variable only from within the block.</span></span>  
  
#### <a name="to-make-a-variable-visible-only-within-a-procedure"></a><span data-ttu-id="9d630-110">プロシージャ内でのみ変数を表示するには</span><span class="sxs-lookup"><span data-stu-id="9d630-110">To make a variable visible only within a procedure</span></span>  
  
- <span data-ttu-id="9d630-111">プロシージャ内に変数の `Dim` ステートメントを配置しますが、ブロックの外側 (`With`...`End With` ブロックなど) の内側に配置します。</span><span class="sxs-lookup"><span data-stu-id="9d630-111">Place the `Dim` statement for the variable inside the procedure but outside any block (such as a `With`...`End With` block).</span></span>  
  
     <span data-ttu-id="9d630-112">プロシージャ内の変数を参照できるのは、プロシージャに含まれている任意のブロック内からです。</span><span class="sxs-lookup"><span data-stu-id="9d630-112">You can refer to the variable only from within the procedure, including inside any block contained in the procedure.</span></span>  
  
## <a name="scope-at-module-or-namespace-level"></a><span data-ttu-id="9d630-113">モジュールまたは名前空間レベルのスコープ</span><span class="sxs-lookup"><span data-stu-id="9d630-113">Scope at Module or Namespace Level</span></span>  
 <span data-ttu-id="9d630-114">便宜上、単項*モジュールレベル*はモジュール、クラス、および構造体にも同様に適用されます。</span><span class="sxs-lookup"><span data-stu-id="9d630-114">For convenience, the single term *module level* applies equally to modules, classes, and structures.</span></span> <span data-ttu-id="9d630-115">モジュールレベル変数のアクセスレベルによってそのスコープが決まります。</span><span class="sxs-lookup"><span data-stu-id="9d630-115">The access level of a module level variable determines its scope.</span></span> <span data-ttu-id="9d630-116">モジュール、クラス、または構造体を含む名前空間もスコープに影響します。</span><span class="sxs-lookup"><span data-stu-id="9d630-116">The namespace that contains the module, class, or structure also influences the scope.</span></span>  
  
#### <a name="to-make-a-variable-visible-throughout-a-module-class-or-structure"></a><span data-ttu-id="9d630-117">モジュール、クラス、または構造体全体で変数を表示するには</span><span class="sxs-lookup"><span data-stu-id="9d630-117">To make a variable visible throughout a module, class, or structure</span></span>  
  
1. <span data-ttu-id="9d630-118">変数の `Dim` ステートメントをモジュール、クラス、または構造体の内部に配置しますが、プロシージャの外側に配置します。</span><span class="sxs-lookup"><span data-stu-id="9d630-118">Place the `Dim` statement for the variable inside the module, class, or structure, but outside any procedure.</span></span>  
  
2. <span data-ttu-id="9d630-119">`Dim` ステートメントに[Private](../../../../visual-basic/language-reference/modifiers/private.md)キーワードを含めます。</span><span class="sxs-lookup"><span data-stu-id="9d630-119">Include the [Private](../../../../visual-basic/language-reference/modifiers/private.md) keyword in the `Dim` statement.</span></span>  
  
3. <span data-ttu-id="9d630-120">変数は、モジュール、クラス、または構造体内のどこからでも参照できますが、外部からは参照できません。</span><span class="sxs-lookup"><span data-stu-id="9d630-120">You can refer to the variable from anywhere within the module, class, or structure, but not from outside it.</span></span>  
  
#### <a name="to-make-a-variable-visible-throughout-a-namespace"></a><span data-ttu-id="9d630-121">名前空間全体で変数を表示するには</span><span class="sxs-lookup"><span data-stu-id="9d630-121">To make a variable visible throughout a namespace</span></span>  
  
1. <span data-ttu-id="9d630-122">変数の `Dim` ステートメントをモジュール、クラス、または構造体の内部に配置しますが、プロシージャの外側に配置します。</span><span class="sxs-lookup"><span data-stu-id="9d630-122">Place the `Dim` statement for the variable inside the module, class, or structure, but outside any procedure.</span></span>  
  
2. <span data-ttu-id="9d630-123">`Dim` ステートメントに[Friend](../../../../visual-basic/language-reference/modifiers/friend.md)キーワードまたは[Public](../../../../visual-basic/language-reference/modifiers/public.md)キーワードを含めます。</span><span class="sxs-lookup"><span data-stu-id="9d630-123">Include the [Friend](../../../../visual-basic/language-reference/modifiers/friend.md) or [Public](../../../../visual-basic/language-reference/modifiers/public.md) keyword in the `Dim` statement.</span></span>  
  
3. <span data-ttu-id="9d630-124">変数は、モジュール、クラス、または構造体を含む名前空間内の任意の場所から参照できます。</span><span class="sxs-lookup"><span data-stu-id="9d630-124">You can refer to the variable from anywhere within the namespace containing the module, class, or structure.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9d630-125">例</span><span class="sxs-lookup"><span data-stu-id="9d630-125">Example</span></span>  
 <span data-ttu-id="9d630-126">次の例では、モジュールレベルで変数を宣言し、その可視性をモジュール内のコードに制限しています。</span><span class="sxs-lookup"><span data-stu-id="9d630-126">The following example declares a variable at module level and limits its visibility to code within the module.</span></span>  
  
```vb  
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
  
 <span data-ttu-id="9d630-127">前の例では、モジュール `demonstrateScope` で定義されているすべてのプロシージャが、`String` 変数 `strMsg`を参照できます。</span><span class="sxs-lookup"><span data-stu-id="9d630-127">In the preceding example, all the procedures defined in module `demonstrateScope` can refer to the `String` variable `strMsg`.</span></span> <span data-ttu-id="9d630-128">`usePrivateVariable` プロシージャが呼び出されると、ダイアログボックスに `strMsg` 文字列変数の内容が表示されます。</span><span class="sxs-lookup"><span data-stu-id="9d630-128">When the `usePrivateVariable` procedure is called, it displays the contents of the string variable `strMsg` in a dialog box.</span></span>  
  
 <span data-ttu-id="9d630-129">前の例を次のように変更すると、`strMsg` 文字列変数は、宣言の名前空間内の任意の場所でコードによって参照できます。</span><span class="sxs-lookup"><span data-stu-id="9d630-129">With the following alteration to the preceding example, the string variable `strMsg` can be referred to by code anywhere in the namespace of its declaration.</span></span>  
  
```vb  
Public strMsg As String  
```  
  
## <a name="robust-programming"></a><span data-ttu-id="9d630-130">堅牢性の高いプログラミング</span><span class="sxs-lookup"><span data-stu-id="9d630-130">Robust Programming</span></span>  
 <span data-ttu-id="9d630-131">変数の範囲が狭いほど、同じ名前を持つ別の変数の代わりに、誤って変数を参照してしまう可能性が低くなります。</span><span class="sxs-lookup"><span data-stu-id="9d630-131">The narrower the scope of a variable, the fewer opportunities you have for accidentally referring to it in place of another variable with the same name.</span></span> <span data-ttu-id="9d630-132">参照の一致に関する問題を最小限に抑えることもできます。</span><span class="sxs-lookup"><span data-stu-id="9d630-132">You can also minimize problems of reference matching.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="9d630-133">.NET Framework のセキュリティ</span><span class="sxs-lookup"><span data-stu-id="9d630-133">.NET Framework Security</span></span>  
 <span data-ttu-id="9d630-134">変数の範囲が狭いほど、悪意のあるコードによって不適切に使用される可能性が小さくなります。</span><span class="sxs-lookup"><span data-stu-id="9d630-134">The narrower the scope of a variable, the smaller the chances that malicious code can make improper use of it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d630-135">参照</span><span class="sxs-lookup"><span data-stu-id="9d630-135">See also</span></span>

- [<span data-ttu-id="9d630-136">Visual Basic 内のスコープ</span><span class="sxs-lookup"><span data-stu-id="9d630-136">Scope in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)
- [<span data-ttu-id="9d630-137">Visual Basic の有効期間</span><span class="sxs-lookup"><span data-stu-id="9d630-137">Lifetime in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md)
- [<span data-ttu-id="9d630-138">Visual Basic のアクセスレベル</span><span class="sxs-lookup"><span data-stu-id="9d630-138">Access levels in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
- [<span data-ttu-id="9d630-139">変数</span><span class="sxs-lookup"><span data-stu-id="9d630-139">Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/index.md)
- [<span data-ttu-id="9d630-140">変数宣言</span><span class="sxs-lookup"><span data-stu-id="9d630-140">Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
- [<span data-ttu-id="9d630-141">Dim ステートメント</span><span class="sxs-lookup"><span data-stu-id="9d630-141">Dim Statement</span></span>](../../../../visual-basic/language-reference/statements/dim-statement.md)
