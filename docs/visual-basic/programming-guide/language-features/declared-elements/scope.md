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
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345287"
---
# <a name="scope-in-visual-basic"></a><span data-ttu-id="b412e-102">Visual Basic におけるスコープ</span><span class="sxs-lookup"><span data-stu-id="b412e-102">Scope in Visual Basic</span></span>

<span data-ttu-id="b412e-103">宣言された要素の*スコープ*は、その名前を修飾したり、 [Imports ステートメント (.net 名前空間と型)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)を通じて使用できるようにしたりせずに参照できるすべてのコードのセットです。</span><span class="sxs-lookup"><span data-stu-id="b412e-103">The *scope* of a declared element is the set of all code that can refer to it without qualifying its name or making it available through an [Imports Statement (.NET Namespace and Type)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).</span></span> <span data-ttu-id="b412e-104">要素は、次のいずれかのレベルでスコープを持つことができます。</span><span class="sxs-lookup"><span data-stu-id="b412e-104">An element can have scope at one of the following levels:</span></span>

|<span data-ttu-id="b412e-105">Level</span><span class="sxs-lookup"><span data-stu-id="b412e-105">Level</span></span>|<span data-ttu-id="b412e-106">説明</span><span class="sxs-lookup"><span data-stu-id="b412e-106">Description</span></span>|
|-----------|-----------------|
|<span data-ttu-id="b412e-107">ブロック スコープ</span><span class="sxs-lookup"><span data-stu-id="b412e-107">Block scope</span></span>|<span data-ttu-id="b412e-108">宣言されているコードブロック内でのみ使用可能</span><span class="sxs-lookup"><span data-stu-id="b412e-108">Available only within the code block in which it is declared</span></span>|
|<span data-ttu-id="b412e-109">プロシージャスコープ</span><span class="sxs-lookup"><span data-stu-id="b412e-109">Procedure scope</span></span>|<span data-ttu-id="b412e-110">宣言されているプロシージャ内のすべてのコードで使用できます。</span><span class="sxs-lookup"><span data-stu-id="b412e-110">Available to all code within the procedure in which it is declared</span></span>|
|<span data-ttu-id="b412e-111">モジュールのスコープ</span><span class="sxs-lookup"><span data-stu-id="b412e-111">Module scope</span></span>|<span data-ttu-id="b412e-112">宣言されているモジュール、クラス、または構造体内のすべてのコードで使用できます。</span><span class="sxs-lookup"><span data-stu-id="b412e-112">Available to all code within the module, class, or structure in which it is declared</span></span>|
|<span data-ttu-id="b412e-113">名前空間のスコープ</span><span class="sxs-lookup"><span data-stu-id="b412e-113">Namespace scope</span></span>|<span data-ttu-id="b412e-114">宣言されている名前空間のすべてのコードで使用可能</span><span class="sxs-lookup"><span data-stu-id="b412e-114">Available to all code in the namespace in which it is declared</span></span>|

<span data-ttu-id="b412e-115">最も狭い (ブロック) から最も幅の広い (名前空間) までの範囲の処理レベル。最も*狭いスコープ*は、要素を修飾なしで参照できる最小のコードセットを意味します。</span><span class="sxs-lookup"><span data-stu-id="b412e-115">These levels of scope progress from the narrowest (block) to the widest (namespace), where *narrowest scope* means the smallest set of code that can refer to the element without qualification.</span></span> <span data-ttu-id="b412e-116">詳細については、このページの「範囲のレベル」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b412e-116">For more information, see "Levels of Scope" on this page.</span></span>

## <a name="specifying-scope-and-defining-variables"></a><span data-ttu-id="b412e-117">スコープの指定と変数の定義</span><span class="sxs-lookup"><span data-stu-id="b412e-117">Specifying Scope and Defining Variables</span></span>

<span data-ttu-id="b412e-118">要素のスコープは、宣言するときに指定します。</span><span class="sxs-lookup"><span data-stu-id="b412e-118">You specify the scope of an element when you declare it.</span></span> <span data-ttu-id="b412e-119">スコープは、次の要因に依存する場合があります。</span><span class="sxs-lookup"><span data-stu-id="b412e-119">The scope can depend on the following factors:</span></span>

- <span data-ttu-id="b412e-120">要素を宣言する領域 (ブロック、プロシージャ、モジュール、クラス、または構造体)</span><span class="sxs-lookup"><span data-stu-id="b412e-120">The region (block, procedure, module, class, or structure) in which you declare the element</span></span>

- <span data-ttu-id="b412e-121">要素の宣言を含む名前空間</span><span class="sxs-lookup"><span data-stu-id="b412e-121">The namespace containing the element's declaration</span></span>

- <span data-ttu-id="b412e-122">要素に対して宣言するアクセスレベル</span><span class="sxs-lookup"><span data-stu-id="b412e-122">The access level you declare for the element</span></span>

<span data-ttu-id="b412e-123">同じ名前でスコープが異なる変数を定義する場合は、慎重に行う必要があります。これは、予期しない結果につながる可能性があるためです。</span><span class="sxs-lookup"><span data-stu-id="b412e-123">Use care when you define variables with the same name but different scope, because doing so can lead to unexpected results.</span></span> <span data-ttu-id="b412e-124">詳細については、「[宣言された要素の参照](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b412e-124">For more information, see [References to Declared Elements](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span></span>

## <a name="levels-of-scope"></a><span data-ttu-id="b412e-125">スコープのレベル</span><span class="sxs-lookup"><span data-stu-id="b412e-125">Levels of Scope</span></span>

<span data-ttu-id="b412e-126">プログラミング要素は、宣言する領域全体で使用できます。</span><span class="sxs-lookup"><span data-stu-id="b412e-126">A programming element is available throughout the region in which you declare it.</span></span> <span data-ttu-id="b412e-127">同じリージョン内のすべてのコードは、その名前を修飾せずに要素を参照できます。</span><span class="sxs-lookup"><span data-stu-id="b412e-127">All code in the same region can refer to the element without qualifying its name.</span></span>

### <a name="block-scope"></a><span data-ttu-id="b412e-128">ブロックスコープ</span><span class="sxs-lookup"><span data-stu-id="b412e-128">Block Scope</span></span>

<span data-ttu-id="b412e-129">ブロックは、次のように、宣言ステートメントの開始と終了に囲まれた一連のステートメントです。</span><span class="sxs-lookup"><span data-stu-id="b412e-129">A block is a set of statements enclosed within initiating and terminating declaration statements, such as the following:</span></span>

- <span data-ttu-id="b412e-130">`Do` および `Loop`</span><span class="sxs-lookup"><span data-stu-id="b412e-130">`Do` and `Loop`</span></span>

- <span data-ttu-id="b412e-131">`For` [`Each`] と `Next`</span><span class="sxs-lookup"><span data-stu-id="b412e-131">`For` [`Each`] and `Next`</span></span>

- <span data-ttu-id="b412e-132">`If` および `End If`</span><span class="sxs-lookup"><span data-stu-id="b412e-132">`If` and `End If`</span></span>

- <span data-ttu-id="b412e-133">`Select` および `End Select`</span><span class="sxs-lookup"><span data-stu-id="b412e-133">`Select` and `End Select`</span></span>

- <span data-ttu-id="b412e-134">`SyncLock` および `End SyncLock`</span><span class="sxs-lookup"><span data-stu-id="b412e-134">`SyncLock` and `End SyncLock`</span></span>

- <span data-ttu-id="b412e-135">`Try` および `End Try`</span><span class="sxs-lookup"><span data-stu-id="b412e-135">`Try` and `End Try`</span></span>

- <span data-ttu-id="b412e-136">`While` および `End While`</span><span class="sxs-lookup"><span data-stu-id="b412e-136">`While` and `End While`</span></span>

- <span data-ttu-id="b412e-137">`With` および `End With`</span><span class="sxs-lookup"><span data-stu-id="b412e-137">`With` and `End With`</span></span>

<span data-ttu-id="b412e-138">ブロック内で変数を宣言すると、そのブロック内でのみ変数を使用できます。</span><span class="sxs-lookup"><span data-stu-id="b412e-138">If you declare a variable within a block, you can use it only within that block.</span></span> <span data-ttu-id="b412e-139">次の例では、整数変数 `cube` のスコープが `If` と `End If`間のブロックであり、ブロックから実行が渡されたときに `cube` を参照することはできません。</span><span class="sxs-lookup"><span data-stu-id="b412e-139">In the following example, the scope of the integer variable `cube` is the block between `If` and `End If`, and you can no longer refer to `cube` when execution passes out of the block.</span></span>

```vb
If n < 1291 Then
    Dim cube As Integer
    cube = n ^ 3
End If
```

> [!NOTE]
> <span data-ttu-id="b412e-140">変数のスコープがブロックに限定されている場合でも、その有効期間はプロシージャ全体の有効期間になります。</span><span class="sxs-lookup"><span data-stu-id="b412e-140">Even if the scope of a variable is limited to a block, its lifetime is still that of the entire procedure.</span></span> <span data-ttu-id="b412e-141">プロシージャの実行中にブロックを複数回入力した場合、各ブロック変数の前の値が保持されます。</span><span class="sxs-lookup"><span data-stu-id="b412e-141">If you enter the block more than once during the procedure, each block variable retains its previous value.</span></span> <span data-ttu-id="b412e-142">このような場合に予期しない結果が生じないようにするには、ブロックの先頭でブロック変数を初期化することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="b412e-142">To avoid unexpected results in such a case, it is wise to initialize block variables at the beginning of the block.</span></span>

### <a name="procedure-scope"></a><span data-ttu-id="b412e-143">プロシージャスコープ</span><span class="sxs-lookup"><span data-stu-id="b412e-143">Procedure Scope</span></span>

<span data-ttu-id="b412e-144">プロシージャ内で宣言された要素は、そのプロシージャの外部では使用できません。</span><span class="sxs-lookup"><span data-stu-id="b412e-144">An element declared within a procedure is not available outside that procedure.</span></span> <span data-ttu-id="b412e-145">宣言を含むプロシージャだけが使用できます。</span><span class="sxs-lookup"><span data-stu-id="b412e-145">Only the procedure that contains the declaration can use it.</span></span> <span data-ttu-id="b412e-146">このレベルの変数は、*ローカル変数*とも呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="b412e-146">Variables at this level are also known as *local variables*.</span></span> <span data-ttu-id="b412e-147">これらの宣言は、 [Static](../../../../visual-basic/language-reference/modifiers/static.md)キーワードの有無にかかわらず、 [Dim ステートメント](../../../../visual-basic/language-reference/statements/dim-statement.md)を使用して宣言します。</span><span class="sxs-lookup"><span data-stu-id="b412e-147">You declare them with the [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md), with or without the [Static](../../../../visual-basic/language-reference/modifiers/static.md) keyword.</span></span>

<span data-ttu-id="b412e-148">プロシージャとブロックのスコープは密接に関連しています。</span><span class="sxs-lookup"><span data-stu-id="b412e-148">Procedure and block scope are closely related.</span></span> <span data-ttu-id="b412e-149">プロシージャ内で変数を宣言し、そのプロシージャ内のブロックの外側で変数を宣言した場合、その変数はブロックスコープを持つと考えることができます。ブロックはプロシージャ全体です。</span><span class="sxs-lookup"><span data-stu-id="b412e-149">If you declare a variable inside a procedure but outside any block within that procedure, you can think of the variable as having block scope, where the block is the entire procedure.</span></span>

> [!NOTE]
> <span data-ttu-id="b412e-150">すべてのローカル要素は `Static` 変数であっても、それらが表示されるプロシージャに対してプライベートです。</span><span class="sxs-lookup"><span data-stu-id="b412e-150">All local elements, even if they are `Static` variables, are private to the procedure in which they appear.</span></span> <span data-ttu-id="b412e-151">プロシージャ内で[Public](../../../../visual-basic/language-reference/modifiers/public.md)キーワードを使用して要素を宣言することはできません。</span><span class="sxs-lookup"><span data-stu-id="b412e-151">You cannot declare any element using the [Public](../../../../visual-basic/language-reference/modifiers/public.md) keyword within a procedure.</span></span>

### <a name="module-scope"></a><span data-ttu-id="b412e-152">モジュールのスコープ</span><span class="sxs-lookup"><span data-stu-id="b412e-152">Module Scope</span></span>

<span data-ttu-id="b412e-153">便宜上、単項*モジュールレベル*はモジュール、クラス、および構造体にも同様に適用されます。</span><span class="sxs-lookup"><span data-stu-id="b412e-153">For convenience, the single term *module level* applies equally to modules, classes, and structures.</span></span> <span data-ttu-id="b412e-154">このレベルで要素を宣言するには、宣言ステートメントをプロシージャまたはブロックの外側に配置し、モジュール、クラス、または構造体の内部に配置します。</span><span class="sxs-lookup"><span data-stu-id="b412e-154">You can declare elements at this level by placing the declaration statement outside of any procedure or block but within the module, class, or structure.</span></span>

<span data-ttu-id="b412e-155">モジュールレベルで宣言を行うと、選択したアクセスレベルによってスコープが決まります。</span><span class="sxs-lookup"><span data-stu-id="b412e-155">When you make a declaration at the module level, the access level you choose determines the scope.</span></span> <span data-ttu-id="b412e-156">モジュール、クラス、または構造体を含む名前空間は、スコープにも影響します。</span><span class="sxs-lookup"><span data-stu-id="b412e-156">The namespace that contains the module, class, or structure also affects the scope.</span></span>

<span data-ttu-id="b412e-157">[Private](../../../../visual-basic/language-reference/modifiers/private.md) アクセスレベルを宣言する要素は、そのモジュール内のすべてのプロシージャで使用できますが、別のモジュール内のコードには使用できません。</span><span class="sxs-lookup"><span data-stu-id="b412e-157">Elements for which you declare [Private](../../../../visual-basic/language-reference/modifiers/private.md) access level are available to every procedure in that module, but not to any code in a different module.</span></span> <span data-ttu-id="b412e-158">アクセスレベルのキーワードを使用しない場合、モジュールレベルの `Dim` ステートメントは既定で `Private` になります。</span><span class="sxs-lookup"><span data-stu-id="b412e-158">The `Dim` statement at module level defaults to `Private` if you do not use any access level keywords.</span></span> <span data-ttu-id="b412e-159">ただし、`Dim` ステートメントで `Private` キーワードを使用すると、スコープとアクセスレベルをより明確にすることができます。</span><span class="sxs-lookup"><span data-stu-id="b412e-159">However, you can make the scope and access level more obvious by using the `Private` keyword in the `Dim` statement.</span></span>

<span data-ttu-id="b412e-160">次の例では、モジュールで定義されているすべてのプロシージャが文字列変数 `strMsg`を参照できます。</span><span class="sxs-lookup"><span data-stu-id="b412e-160">In the following example, all procedures defined in the module can refer to the string variable `strMsg`.</span></span> <span data-ttu-id="b412e-161">2番目のプロシージャを呼び出すと、`strMsg` 文字列変数の内容がダイアログボックスに表示されます。</span><span class="sxs-lookup"><span data-stu-id="b412e-161">When the second procedure is called, it displays the contents of the string variable `strMsg` in a dialog box.</span></span>

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

### <a name="namespace-scope"></a><span data-ttu-id="b412e-162">名前空間のスコープ</span><span class="sxs-lookup"><span data-stu-id="b412e-162">Namespace Scope</span></span>

<span data-ttu-id="b412e-163">[Friend](../../../../visual-basic/language-reference/modifiers/friend.md)または[Public](../../../../visual-basic/language-reference/modifiers/public.md)キーワードを使用してモジュールレベルで要素を宣言すると、その要素が宣言されている名前空間全体のすべてのプロシージャで使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="b412e-163">If you declare an element at module level using the [Friend](../../../../visual-basic/language-reference/modifiers/friend.md) or [Public](../../../../visual-basic/language-reference/modifiers/public.md) keyword, it becomes available to all procedures throughout the namespace in which the element is declared.</span></span> <span data-ttu-id="b412e-164">前の例を次のように変更すると、`strMsg` 文字列変数は、宣言の名前空間内の任意の場所でコードによって参照できます。</span><span class="sxs-lookup"><span data-stu-id="b412e-164">With the following alteration to the preceding example, the string variable `strMsg` can be referred to by code anywhere in the namespace of its declaration.</span></span>

```vb
' Include this declaration at module level (not inside any procedure).
Public strMsg As String
```

<span data-ttu-id="b412e-165">名前空間スコープには入れ子になった名前空間が含まれます。</span><span class="sxs-lookup"><span data-stu-id="b412e-165">Namespace scope includes nested namespaces.</span></span> <span data-ttu-id="b412e-166">名前空間内から使用できる要素は、その名前空間内で入れ子になっている名前空間内からも使用できます。</span><span class="sxs-lookup"><span data-stu-id="b412e-166">An element available from within a namespace is also available from within any namespace nested inside that namespace.</span></span>

<span data-ttu-id="b412e-167">プロジェクトに[名前空間ステートメント](../../../../visual-basic/language-reference/statements/namespace-statement.md)が含まれていない場合、プロジェクト内のすべてのものが同じ名前空間にあります。</span><span class="sxs-lookup"><span data-stu-id="b412e-167">If your project does not contain any [Namespace Statement](../../../../visual-basic/language-reference/statements/namespace-statement.md)s, everything in the project is in the same namespace.</span></span> <span data-ttu-id="b412e-168">この場合、名前空間のスコープはプロジェクトスコープと考えることができます。</span><span class="sxs-lookup"><span data-stu-id="b412e-168">In this case, namespace scope can be thought of as project scope.</span></span> <span data-ttu-id="b412e-169">モジュール、クラス、または構造体内の `Public` 要素は、そのプロジェクトを参照するすべてのプロジェクトでも使用できます。</span><span class="sxs-lookup"><span data-stu-id="b412e-169">`Public` elements in a module, class, or structure are also available to any project that references their project.</span></span>

## <a name="choice-of-scope"></a><span data-ttu-id="b412e-170">スコープの選択</span><span class="sxs-lookup"><span data-stu-id="b412e-170">Choice of Scope</span></span>

<span data-ttu-id="b412e-171">変数を宣言するときは、そのスコープを選択するときに、次の点に注意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b412e-171">When you declare a variable, you should keep in mind the following points when choosing its scope.</span></span>

### <a name="advantages-of-local-variables"></a><span data-ttu-id="b412e-172">ローカル変数の利点</span><span class="sxs-lookup"><span data-stu-id="b412e-172">Advantages of Local Variables</span></span>

<span data-ttu-id="b412e-173">ローカル変数は、次の理由により、任意の種類の一時的な計算に適しています。</span><span class="sxs-lookup"><span data-stu-id="b412e-173">Local variables are a good choice for any kind of temporary calculation, for the following reasons:</span></span>

- <span data-ttu-id="b412e-174">**名前の競合の回避。**</span><span class="sxs-lookup"><span data-stu-id="b412e-174">**Name Conflict Avoidance.**</span></span> <span data-ttu-id="b412e-175">ローカル変数名が競合する可能性はありません。</span><span class="sxs-lookup"><span data-stu-id="b412e-175">Local variable names are not susceptible to conflict.</span></span> <span data-ttu-id="b412e-176">たとえば、`intTemp`という変数を含むいくつかの異なるプロシージャを作成できます。</span><span class="sxs-lookup"><span data-stu-id="b412e-176">For example, you can create several different procedures containing a variable called `intTemp`.</span></span> <span data-ttu-id="b412e-177">各 `intTemp` がローカル変数として宣言されている限り、各プロシージャは独自のバージョンの `intTemp`のみを認識します。</span><span class="sxs-lookup"><span data-stu-id="b412e-177">As long as each `intTemp` is declared as a local variable, each procedure recognizes only its own version of `intTemp`.</span></span> <span data-ttu-id="b412e-178">1つのプロシージャでは、他のプロシージャの `intTemp` 変数に影響を与えることなく、ローカル `intTemp` の値を変更できます。</span><span class="sxs-lookup"><span data-stu-id="b412e-178">Any one procedure can alter the value in its local `intTemp` without affecting `intTemp` variables in other procedures.</span></span>

- <span data-ttu-id="b412e-179">**メモリ使用量。**</span><span class="sxs-lookup"><span data-stu-id="b412e-179">**Memory Consumption.**</span></span> <span data-ttu-id="b412e-180">ローカル変数は、プロシージャの実行中にのみメモリを消費します。</span><span class="sxs-lookup"><span data-stu-id="b412e-180">Local variables consume memory only while their procedure is running.</span></span> <span data-ttu-id="b412e-181">メモリは、プロシージャが呼び出し元のコードに戻ったときに解放されます。</span><span class="sxs-lookup"><span data-stu-id="b412e-181">Their memory is released when the procedure returns to the calling code.</span></span> <span data-ttu-id="b412e-182">これに対し、[Shared](../../../../visual-basic/language-reference/modifiers/shared.md)変数と[Static](../../../../visual-basic/language-reference/modifiers/static.md)変数は、アプリケーションが実行を停止するまでメモリリソースを消費するため、必要な場合にのみ使用します。</span><span class="sxs-lookup"><span data-stu-id="b412e-182">By contrast, [Shared](../../../../visual-basic/language-reference/modifiers/shared.md) and [Static](../../../../visual-basic/language-reference/modifiers/static.md) variables consume memory resources until your application stops running, so use them only when necessary.</span></span> <span data-ttu-id="b412e-183">インスタンス*変数*は、インスタンスが存在している間はメモリを消費するため、ローカル変数よりも効率的ではありませんが、`Shared` または `Static` 変数よりも効率的です。</span><span class="sxs-lookup"><span data-stu-id="b412e-183">*Instance variables* consume memory while their instance continues to exist, which makes them less efficient than local variables, but potentially more efficient than `Shared` or `Static` variables.</span></span>

### <a name="minimizing-scope"></a><span data-ttu-id="b412e-184">スコープの最小化</span><span class="sxs-lookup"><span data-stu-id="b412e-184">Minimizing Scope</span></span>

<span data-ttu-id="b412e-185">一般に、変数または定数を宣言するときは、可能な限り範囲を絞り込むことをお勧めします (ブロックスコープが最も狭い)。</span><span class="sxs-lookup"><span data-stu-id="b412e-185">In general, when declaring any variable or constant, it is good programming practice to make the scope as narrow as possible (block scope is the narrowest).</span></span> <span data-ttu-id="b412e-186">これにより、メモリを節約し、コードが間違った変数を誤って参照する可能性を最小限に抑えることができます。</span><span class="sxs-lookup"><span data-stu-id="b412e-186">This helps conserve memory and minimizes the chances of your code erroneously referring to the wrong variable.</span></span> <span data-ttu-id="b412e-187">同様に、プロシージャ呼び出し間で値を保持する必要がある場合にのみ、変数を[Static](../../../../visual-basic/language-reference/modifiers/static.md)に宣言する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b412e-187">Similarly, you should declare a variable to be [Static](../../../../visual-basic/language-reference/modifiers/static.md) only when it is necessary to preserve its value between procedure calls.</span></span>

## <a name="see-also"></a><span data-ttu-id="b412e-188">参照</span><span class="sxs-lookup"><span data-stu-id="b412e-188">See also</span></span>

- [<span data-ttu-id="b412e-189">宣言された要素の特性</span><span class="sxs-lookup"><span data-stu-id="b412e-189">Declared Element Characteristics</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md)
- [<span data-ttu-id="b412e-190">方法: 変数のスコープを制御する</span><span class="sxs-lookup"><span data-stu-id="b412e-190">How to: Control the Scope of a Variable</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-control-the-scope-of-a-variable.md)
- [<span data-ttu-id="b412e-191">Visual Basic の有効期間</span><span class="sxs-lookup"><span data-stu-id="b412e-191">Lifetime in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md)
- [<span data-ttu-id="b412e-192">Visual Basic でのアクセス レベル</span><span class="sxs-lookup"><span data-stu-id="b412e-192">Access levels in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
- [<span data-ttu-id="b412e-193">宣言された要素の参照</span><span class="sxs-lookup"><span data-stu-id="b412e-193">References to Declared Elements</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
- [<span data-ttu-id="b412e-194">変数宣言</span><span class="sxs-lookup"><span data-stu-id="b412e-194">Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
