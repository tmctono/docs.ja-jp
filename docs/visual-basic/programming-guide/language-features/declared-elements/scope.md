---
title: スコープ
ms.date: 07/20/2015
helpviewer_keywords:
- module scope [Visual Basic]
- scope [Visual Basic], levels
- module level
- procedures [Visual Basic], scope
- declared elements [Visual Basic], scope
- namespaces [Visual Basic], scope
- scope [Visual Basic], declared elements
- scope [Visual Basic], about scope
- levels of scope [Visual Basic]
- block scope [Visual Basic]
- scope [Visual Basic], Visual Basic
- procedure scope [Visual Basic]
ms.assetid: 208106fe-79c9-4eec-93c6-55f08548895f
ms.openlocfilehash: 37fcfa897accb23e9c8c56407ce4ebd956b39c4d
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345287"
---
# <a name="scope-in-visual-basic"></a><span data-ttu-id="cc964-102">Visual Basic におけるスコープ</span><span class="sxs-lookup"><span data-stu-id="cc964-102">Scope in Visual Basic</span></span>

<span data-ttu-id="cc964-103">宣言された要素の*スコープ*は、その名前を修飾したり、[Imports ステートメント (.NET 名前空間および型)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) から使用できるようにしたりしなくても、それを参照できるすべてのコードのセットです。</span><span class="sxs-lookup"><span data-stu-id="cc964-103">The *scope* of a declared element is the set of all code that can refer to it without qualifying its name or making it available through an [Imports Statement (.NET Namespace and Type)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).</span></span> <span data-ttu-id="cc964-104">要素には、次のいずれかのレベルのスコープを設定できます。</span><span class="sxs-lookup"><span data-stu-id="cc964-104">An element can have scope at one of the following levels:</span></span>

|<span data-ttu-id="cc964-105">レベル</span><span class="sxs-lookup"><span data-stu-id="cc964-105">Level</span></span>|<span data-ttu-id="cc964-106">説明</span><span class="sxs-lookup"><span data-stu-id="cc964-106">Description</span></span>|
|-----------|-----------------|
|<span data-ttu-id="cc964-107">ブロック スコープ</span><span class="sxs-lookup"><span data-stu-id="cc964-107">Block scope</span></span>|<span data-ttu-id="cc964-108">それが宣言されているコード ブロック内でのみ使用可能</span><span class="sxs-lookup"><span data-stu-id="cc964-108">Available only within the code block in which it is declared</span></span>|
|<span data-ttu-id="cc964-109">プロシージャ スコープ</span><span class="sxs-lookup"><span data-stu-id="cc964-109">Procedure scope</span></span>|<span data-ttu-id="cc964-110">それが宣言されているプロシージャ内のすべてのコードで使用可能</span><span class="sxs-lookup"><span data-stu-id="cc964-110">Available to all code within the procedure in which it is declared</span></span>|
|<span data-ttu-id="cc964-111">モジュール スコープ</span><span class="sxs-lookup"><span data-stu-id="cc964-111">Module scope</span></span>|<span data-ttu-id="cc964-112">それが宣言されているモジュール、クラス、または構造体内のすべてのコードで使用可能</span><span class="sxs-lookup"><span data-stu-id="cc964-112">Available to all code within the module, class, or structure in which it is declared</span></span>|
|<span data-ttu-id="cc964-113">名前空間スコープ</span><span class="sxs-lookup"><span data-stu-id="cc964-113">Namespace scope</span></span>|<span data-ttu-id="cc964-114">それが宣言されている名前空間内のすべてのコードで使用可能</span><span class="sxs-lookup"><span data-stu-id="cc964-114">Available to all code in the namespace in which it is declared</span></span>|

<span data-ttu-id="cc964-115">これらのスコープのレベルは、最も狭い (ブロック) から最も広い (名前空間) まで進展します。ここで、*最も狭いスコープ*とは、修飾せずに要素を参照できる最小限のコードのセットを意味します。</span><span class="sxs-lookup"><span data-stu-id="cc964-115">These levels of scope progress from the narrowest (block) to the widest (namespace), where *narrowest scope* means the smallest set of code that can refer to the element without qualification.</span></span> <span data-ttu-id="cc964-116">詳細については、このページの「スコープのレベル」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cc964-116">For more information, see "Levels of Scope" on this page.</span></span>

## <a name="specifying-scope-and-defining-variables"></a><span data-ttu-id="cc964-117">スコープの指定と変数の定義</span><span class="sxs-lookup"><span data-stu-id="cc964-117">Specifying Scope and Defining Variables</span></span>

<span data-ttu-id="cc964-118">要素のスコープは、それを宣言するときに指定します。</span><span class="sxs-lookup"><span data-stu-id="cc964-118">You specify the scope of an element when you declare it.</span></span> <span data-ttu-id="cc964-119">スコープは、次の要因によって異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="cc964-119">The scope can depend on the following factors:</span></span>

- <span data-ttu-id="cc964-120">要素を宣言する領域 (ブロック、プロシージャ、モジュール、クラス、または構造体)</span><span class="sxs-lookup"><span data-stu-id="cc964-120">The region (block, procedure, module, class, or structure) in which you declare the element</span></span>

- <span data-ttu-id="cc964-121">要素の宣言を含む名前空間</span><span class="sxs-lookup"><span data-stu-id="cc964-121">The namespace containing the element's declaration</span></span>

- <span data-ttu-id="cc964-122">要素に対して宣言するアクセス レベル</span><span class="sxs-lookup"><span data-stu-id="cc964-122">The access level you declare for the element</span></span>

<span data-ttu-id="cc964-123">同じ名前だがスコープが異なる変数を定義する場合は、それによって予期しない結果につながる可能性があるため、注意してください。</span><span class="sxs-lookup"><span data-stu-id="cc964-123">Use care when you define variables with the same name but different scope, because doing so can lead to unexpected results.</span></span> <span data-ttu-id="cc964-124">詳細については、「 [References to Declared Elements](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cc964-124">For more information, see [References to Declared Elements](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span></span>

## <a name="levels-of-scope"></a><span data-ttu-id="cc964-125">スコープのレベル</span><span class="sxs-lookup"><span data-stu-id="cc964-125">Levels of Scope</span></span>

<span data-ttu-id="cc964-126">プログラミング要素は、それを宣言する領域全体で使用できます。</span><span class="sxs-lookup"><span data-stu-id="cc964-126">A programming element is available throughout the region in which you declare it.</span></span> <span data-ttu-id="cc964-127">同じリージョン内のすべてのコードでは、その名前を修飾せずに要素を参照できます。</span><span class="sxs-lookup"><span data-stu-id="cc964-127">All code in the same region can refer to the element without qualifying its name.</span></span>

### <a name="block-scope"></a><span data-ttu-id="cc964-128">ブロック スコープ</span><span class="sxs-lookup"><span data-stu-id="cc964-128">Block Scope</span></span>

<span data-ttu-id="cc964-129">ブロックは、次のように、開始と終了の宣言ステートメントに囲まれた一連のステートメントです。</span><span class="sxs-lookup"><span data-stu-id="cc964-129">A block is a set of statements enclosed within initiating and terminating declaration statements, such as the following:</span></span>

- <span data-ttu-id="cc964-130">`Do` および `Loop`</span><span class="sxs-lookup"><span data-stu-id="cc964-130">`Do` and `Loop`</span></span>

- <span data-ttu-id="cc964-131">`For` [`Each`] および `Next`</span><span class="sxs-lookup"><span data-stu-id="cc964-131">`For` [`Each`] and `Next`</span></span>

- <span data-ttu-id="cc964-132">`If` および `End If`</span><span class="sxs-lookup"><span data-stu-id="cc964-132">`If` and `End If`</span></span>

- <span data-ttu-id="cc964-133">`Select` および `End Select`</span><span class="sxs-lookup"><span data-stu-id="cc964-133">`Select` and `End Select`</span></span>

- <span data-ttu-id="cc964-134">`SyncLock` および `End SyncLock`</span><span class="sxs-lookup"><span data-stu-id="cc964-134">`SyncLock` and `End SyncLock`</span></span>

- <span data-ttu-id="cc964-135">`Try` および `End Try`</span><span class="sxs-lookup"><span data-stu-id="cc964-135">`Try` and `End Try`</span></span>

- <span data-ttu-id="cc964-136">`While` および `End While`</span><span class="sxs-lookup"><span data-stu-id="cc964-136">`While` and `End While`</span></span>

- <span data-ttu-id="cc964-137">`With` および `End With`</span><span class="sxs-lookup"><span data-stu-id="cc964-137">`With` and `End With`</span></span>

<span data-ttu-id="cc964-138">ブロック内で変数を宣言すると、そのブロック内でのみそれを使用できます。</span><span class="sxs-lookup"><span data-stu-id="cc964-138">If you declare a variable within a block, you can use it only within that block.</span></span> <span data-ttu-id="cc964-139">次の例で、整数変数 `cube` のスコープは `If` と `End If` の間のブロックであるため、実行がブロックから出ると、`cube` を参照できなくなります。</span><span class="sxs-lookup"><span data-stu-id="cc964-139">In the following example, the scope of the integer variable `cube` is the block between `If` and `End If`, and you can no longer refer to `cube` when execution passes out of the block.</span></span>

```vb
If n < 1291 Then
    Dim cube As Integer
    cube = n ^ 3
End If
```

> [!NOTE]
> <span data-ttu-id="cc964-140">変数のスコープがブロックに制限されている場合でも、その有効期間はプロシージャ全体の有効期間になります。</span><span class="sxs-lookup"><span data-stu-id="cc964-140">Even if the scope of a variable is limited to a block, its lifetime is still that of the entire procedure.</span></span> <span data-ttu-id="cc964-141">プロシージャの実行中にブロックに複数回入る場合、各ブロック変数で前の値が保持されます。</span><span class="sxs-lookup"><span data-stu-id="cc964-141">If you enter the block more than once during the procedure, each block variable retains its previous value.</span></span> <span data-ttu-id="cc964-142">そのような場合に予期しない結果を避けるには、ブロックの先頭でブロック変数を初期化することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="cc964-142">To avoid unexpected results in such a case, it is wise to initialize block variables at the beginning of the block.</span></span>

### <a name="procedure-scope"></a><span data-ttu-id="cc964-143">プロシージャ スコープ</span><span class="sxs-lookup"><span data-stu-id="cc964-143">Procedure Scope</span></span>

<span data-ttu-id="cc964-144">プロシージャ内で宣言された要素は、そのプロシージャの外部で使用できません。</span><span class="sxs-lookup"><span data-stu-id="cc964-144">An element declared within a procedure is not available outside that procedure.</span></span> <span data-ttu-id="cc964-145">宣言を含むプロシージャだけがそれを使用できます。</span><span class="sxs-lookup"><span data-stu-id="cc964-145">Only the procedure that contains the declaration can use it.</span></span> <span data-ttu-id="cc964-146">このレベルの変数は、*ローカル変数*とも呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="cc964-146">Variables at this level are also known as *local variables*.</span></span> <span data-ttu-id="cc964-147">それらは、[Dim ステートメント](../../../../visual-basic/language-reference/statements/dim-statement.md)で、[Static](../../../../visual-basic/language-reference/modifiers/static.md) キーワードを付けるか、または付けないで、宣言します。</span><span class="sxs-lookup"><span data-stu-id="cc964-147">You declare them with the [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md), with or without the [Static](../../../../visual-basic/language-reference/modifiers/static.md) keyword.</span></span>

<span data-ttu-id="cc964-148">プロシージャとブロックのスコープは密接に関連しています。</span><span class="sxs-lookup"><span data-stu-id="cc964-148">Procedure and block scope are closely related.</span></span> <span data-ttu-id="cc964-149">プロシージャ内の、ただしそのプロシージャ内のいずれかのブロックの外部で変数を宣言した場合、その変数はブロック スコープを持つと考えることができます。その場合ブロックはプロシージャ全体になります。</span><span class="sxs-lookup"><span data-stu-id="cc964-149">If you declare a variable inside a procedure but outside any block within that procedure, you can think of the variable as having block scope, where the block is the entire procedure.</span></span>

> [!NOTE]
> <span data-ttu-id="cc964-150">すべてのローカル要素は、`Static` 変数であっても、それらが存在するプロシージャに対してプライベートです。</span><span class="sxs-lookup"><span data-stu-id="cc964-150">All local elements, even if they are `Static` variables, are private to the procedure in which they appear.</span></span> <span data-ttu-id="cc964-151">プロシージャ内で [Public](../../../../visual-basic/language-reference/modifiers/public.md) キーワードを使用して要素を宣言することはできません。</span><span class="sxs-lookup"><span data-stu-id="cc964-151">You cannot declare any element using the [Public](../../../../visual-basic/language-reference/modifiers/public.md) keyword within a procedure.</span></span>

### <a name="module-scope"></a><span data-ttu-id="cc964-152">モジュール スコープ</span><span class="sxs-lookup"><span data-stu-id="cc964-152">Module Scope</span></span>

<span data-ttu-id="cc964-153">便宜上、*モジュール レベル*という 1 つの用語は、モジュール、クラス、および構造体に等しく適用されます。</span><span class="sxs-lookup"><span data-stu-id="cc964-153">For convenience, the single term *module level* applies equally to modules, classes, and structures.</span></span> <span data-ttu-id="cc964-154">このレベルで要素を宣言するには、宣言ステートメントをプロシージャまたはブロックの外部で、ただしモジュール、クラス、または構造体内に配置します。</span><span class="sxs-lookup"><span data-stu-id="cc964-154">You can declare elements at this level by placing the declaration statement outside of any procedure or block but within the module, class, or structure.</span></span>

<span data-ttu-id="cc964-155">モジュール レベルで宣言を行うと、選択したアクセス レベルによってスコープが決まります。</span><span class="sxs-lookup"><span data-stu-id="cc964-155">When you make a declaration at the module level, the access level you choose determines the scope.</span></span> <span data-ttu-id="cc964-156">モジュール、クラス、または構造体を含む名前空間もスコープに影響します。</span><span class="sxs-lookup"><span data-stu-id="cc964-156">The namespace that contains the module, class, or structure also affects the scope.</span></span>

<span data-ttu-id="cc964-157">[Private](../../../../visual-basic/language-reference/modifiers/private.md) アクセス レベルを宣言した要素は、そのモジュール内のすべてのプロシージャで使用できますが、別のモジュール内のコードでは使用できません。</span><span class="sxs-lookup"><span data-stu-id="cc964-157">Elements for which you declare [Private](../../../../visual-basic/language-reference/modifiers/private.md) access level are available to every procedure in that module, but not to any code in a different module.</span></span> <span data-ttu-id="cc964-158">アクセス レベル キーワードを使用しない場合、モジュール レベルの `Dim` ステートメントは既定で `Private` になります。</span><span class="sxs-lookup"><span data-stu-id="cc964-158">The `Dim` statement at module level defaults to `Private` if you do not use any access level keywords.</span></span> <span data-ttu-id="cc964-159">ただし、`Dim` ステートメントで `Private` キーワードを使用することで、スコープとアクセス レベルをより明確にすることができます。</span><span class="sxs-lookup"><span data-stu-id="cc964-159">However, you can make the scope and access level more obvious by using the `Private` keyword in the `Dim` statement.</span></span>

<span data-ttu-id="cc964-160">次の例では、モジュールに定義されているすべてのプロシージャで、文字列変数 `strMsg` を参照できます。</span><span class="sxs-lookup"><span data-stu-id="cc964-160">In the following example, all procedures defined in the module can refer to the string variable `strMsg`.</span></span> <span data-ttu-id="cc964-161">2 番目のプロシージャを呼び出すと、ダイアログ ボックスに `strMsg` 文字列変数の内容が表示されます。</span><span class="sxs-lookup"><span data-stu-id="cc964-161">When the second procedure is called, it displays the contents of the string variable `strMsg` in a dialog box.</span></span>

```vb
' Put the following declaration at module level (not in any procedure).
Private strMsg As String
' Put the following Sub procedure in the same module.
Sub initializePrivateVariable()
    strMsg = "This variable cannot be used outside this module."
End Sub
' Put the following Sub procedure in the same module.
Sub usePrivateVariable()
    MsgBox(strMsg)
End Sub
```

### <a name="namespace-scope"></a><span data-ttu-id="cc964-162">名前空間スコープ</span><span class="sxs-lookup"><span data-stu-id="cc964-162">Namespace Scope</span></span>

<span data-ttu-id="cc964-163">[Friend](../../../../visual-basic/language-reference/modifiers/friend.md) または [Public](../../../../visual-basic/language-reference/modifiers/public.md) キーワードを使用して、要素をモジュール レベルで宣言すると、その要素が宣言されている名前空間全体のすべてのプロシージャで使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="cc964-163">If you declare an element at module level using the [Friend](../../../../visual-basic/language-reference/modifiers/friend.md) or [Public](../../../../visual-basic/language-reference/modifiers/public.md) keyword, it becomes available to all procedures throughout the namespace in which the element is declared.</span></span> <span data-ttu-id="cc964-164">前の例を次のように変更すると、文字列変数 `strMsg` は、宣言の名前空間内の任意の場所でコードによって参照できます。</span><span class="sxs-lookup"><span data-stu-id="cc964-164">With the following alteration to the preceding example, the string variable `strMsg` can be referred to by code anywhere in the namespace of its declaration.</span></span>

```vb
' Include this declaration at module level (not inside any procedure).
Public strMsg As String
```

<span data-ttu-id="cc964-165">名前空間スコープには、入れ子になった名前空間が含まれます。</span><span class="sxs-lookup"><span data-stu-id="cc964-165">Namespace scope includes nested namespaces.</span></span> <span data-ttu-id="cc964-166">名前空間内から使用できる要素は、その名前空間内に入れ子になっているすべての名前空間内からも使用できます。</span><span class="sxs-lookup"><span data-stu-id="cc964-166">An element available from within a namespace is also available from within any namespace nested inside that namespace.</span></span>

<span data-ttu-id="cc964-167">プロジェクトに [Namespace ステートメント](../../../../visual-basic/language-reference/statements/namespace-statement.md) が含まれていない場合、プロジェクトのすべてのものが同じ名前空間内にあります。</span><span class="sxs-lookup"><span data-stu-id="cc964-167">If your project does not contain any [Namespace Statement](../../../../visual-basic/language-reference/statements/namespace-statement.md)s, everything in the project is in the same namespace.</span></span> <span data-ttu-id="cc964-168">この場合、名前空間スコープはプロジェクト スコープと考えることができます。</span><span class="sxs-lookup"><span data-stu-id="cc964-168">In this case, namespace scope can be thought of as project scope.</span></span> <span data-ttu-id="cc964-169">モジュール、クラス、または構造体内の `Public` 要素は、そのプロジェクトを参照するすべてのプロジェクトでも使用できます。</span><span class="sxs-lookup"><span data-stu-id="cc964-169">`Public` elements in a module, class, or structure are also available to any project that references their project.</span></span>

## <a name="choice-of-scope"></a><span data-ttu-id="cc964-170">スコープの選択</span><span class="sxs-lookup"><span data-stu-id="cc964-170">Choice of Scope</span></span>

<span data-ttu-id="cc964-171">変数を宣言する場合、そのスコープを選択するときに、次の点に注意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cc964-171">When you declare a variable, you should keep in mind the following points when choosing its scope.</span></span>

### <a name="advantages-of-local-variables"></a><span data-ttu-id="cc964-172">ローカル変数の利点</span><span class="sxs-lookup"><span data-stu-id="cc964-172">Advantages of Local Variables</span></span>

<span data-ttu-id="cc964-173">ローカル変数は、次の理由で、あらゆる種類の一時的な計算に適しています。</span><span class="sxs-lookup"><span data-stu-id="cc964-173">Local variables are a good choice for any kind of temporary calculation, for the following reasons:</span></span>

- <span data-ttu-id="cc964-174">**名前の競合の回避。**</span><span class="sxs-lookup"><span data-stu-id="cc964-174">**Name Conflict Avoidance.**</span></span> <span data-ttu-id="cc964-175">ローカル変数名は競合する可能性がありません。</span><span class="sxs-lookup"><span data-stu-id="cc964-175">Local variable names are not susceptible to conflict.</span></span> <span data-ttu-id="cc964-176">たとえば、`intTemp` という変数を含む複数の異なるプロシージャを作成できます。</span><span class="sxs-lookup"><span data-stu-id="cc964-176">For example, you can create several different procedures containing a variable called `intTemp`.</span></span> <span data-ttu-id="cc964-177">各 `intTemp` がローカル変数として宣言されている限り、各プロシージャではその独自のバージョンの `intTemp` のみが認識されます。</span><span class="sxs-lookup"><span data-stu-id="cc964-177">As long as each `intTemp` is declared as a local variable, each procedure recognizes only its own version of `intTemp`.</span></span> <span data-ttu-id="cc964-178">他のプロシージャの `intTemp` 変数に影響を与えることなく、あるプロシージャで、そのローカル `intTemp` の値を変更できます。</span><span class="sxs-lookup"><span data-stu-id="cc964-178">Any one procedure can alter the value in its local `intTemp` without affecting `intTemp` variables in other procedures.</span></span>

- <span data-ttu-id="cc964-179">**メモリの使用量。**</span><span class="sxs-lookup"><span data-stu-id="cc964-179">**Memory Consumption.**</span></span> <span data-ttu-id="cc964-180">ローカル変数は、プロシージャの実行中にのみメモリを消費します。</span><span class="sxs-lookup"><span data-stu-id="cc964-180">Local variables consume memory only while their procedure is running.</span></span> <span data-ttu-id="cc964-181">それらのメモリは、プロシージャが呼び出し元のコードに戻ったときに解放されます。</span><span class="sxs-lookup"><span data-stu-id="cc964-181">Their memory is released when the procedure returns to the calling code.</span></span> <span data-ttu-id="cc964-182">これに対し、[Shared](../../../../visual-basic/language-reference/modifiers/shared.md) 変数と [Static](../../../../visual-basic/language-reference/modifiers/static.md) 変数では、アプリケーションが実行を停止するまでメモリ リソースが消費されるため、必要な場合にのみそれらを使用してください。</span><span class="sxs-lookup"><span data-stu-id="cc964-182">By contrast, [Shared](../../../../visual-basic/language-reference/modifiers/shared.md) and [Static](../../../../visual-basic/language-reference/modifiers/static.md) variables consume memory resources until your application stops running, so use them only when necessary.</span></span> <span data-ttu-id="cc964-183">*インスタンス変数*では、それらのインスタンスが存在し続ける間メモリが消費されるので、ローカル変数よりも非効率的ですが、`Shared` または `Static` 変数よりも効率的である可能性があります。</span><span class="sxs-lookup"><span data-stu-id="cc964-183">*Instance variables* consume memory while their instance continues to exist, which makes them less efficient than local variables, but potentially more efficient than `Shared` or `Static` variables.</span></span>

### <a name="minimizing-scope"></a><span data-ttu-id="cc964-184">スコープの最小化</span><span class="sxs-lookup"><span data-stu-id="cc964-184">Minimizing Scope</span></span>

<span data-ttu-id="cc964-185">一般に、変数または定数を宣言するときは、スコープを可能な限り狭くすることをお勧めします (ブロック スコープが最も狭い)。</span><span class="sxs-lookup"><span data-stu-id="cc964-185">In general, when declaring any variable or constant, it is good programming practice to make the scope as narrow as possible (block scope is the narrowest).</span></span> <span data-ttu-id="cc964-186">これにより、メモリを節約し、コードで間違った変数を誤って参照する可能性が最小限に抑えられます。</span><span class="sxs-lookup"><span data-stu-id="cc964-186">This helps conserve memory and minimizes the chances of your code erroneously referring to the wrong variable.</span></span> <span data-ttu-id="cc964-187">同様に、プロシージャ呼び出しの間でその値を保持する必要がある場合にのみ、変数を [Static](../../../../visual-basic/language-reference/modifiers/static.md) として宣言する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cc964-187">Similarly, you should declare a variable to be [Static](../../../../visual-basic/language-reference/modifiers/static.md) only when it is necessary to preserve its value between procedure calls.</span></span>

## <a name="see-also"></a><span data-ttu-id="cc964-188">関連項目</span><span class="sxs-lookup"><span data-stu-id="cc964-188">See also</span></span>

- [<span data-ttu-id="cc964-189">宣言された要素の特性</span><span class="sxs-lookup"><span data-stu-id="cc964-189">Declared Element Characteristics</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md)
- [<span data-ttu-id="cc964-190">方法: 変数のスコープを制御する</span><span class="sxs-lookup"><span data-stu-id="cc964-190">How to: Control the Scope of a Variable</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-control-the-scope-of-a-variable.md)
- [<span data-ttu-id="cc964-191">Visual Basic における有効期間</span><span class="sxs-lookup"><span data-stu-id="cc964-191">Lifetime in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md)
- [<span data-ttu-id="cc964-192">Visual Basic でのアクセス レベル</span><span class="sxs-lookup"><span data-stu-id="cc964-192">Access levels in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
- [<span data-ttu-id="cc964-193">宣言された要素の参照</span><span class="sxs-lookup"><span data-stu-id="cc964-193">References to Declared Elements</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
- [<span data-ttu-id="cc964-194">変数宣言</span><span class="sxs-lookup"><span data-stu-id="cc964-194">Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
