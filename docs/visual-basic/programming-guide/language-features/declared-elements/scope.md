---
title: Visual Basic におけるスコープ
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
ms.openlocfilehash: 6139af65958cefe43578f436204fa6836a71de0b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61917840"
---
# <a name="scope-in-visual-basic"></a><span data-ttu-id="3724e-102">Visual Basic におけるスコープ</span><span class="sxs-lookup"><span data-stu-id="3724e-102">Scope in Visual Basic</span></span>
<span data-ttu-id="3724e-103">*スコープ*一連の名前を修飾したり、を通じて利用できるようにせずに参照できるすべてのコードは、宣言された要素の[Imports ステートメント (.NET Namespace よぶ型)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)します。</span><span class="sxs-lookup"><span data-stu-id="3724e-103">The *scope* of a declared element is the set of all code that can refer to it without qualifying its name or making it available through an [Imports Statement (.NET Namespace and Type)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).</span></span> <span data-ttu-id="3724e-104">要素は、次のレベルのいずれかのスコープを設定できます。</span><span class="sxs-lookup"><span data-stu-id="3724e-104">An element can have scope at one of the following levels:</span></span>  
  
|<span data-ttu-id="3724e-105">レベル</span><span class="sxs-lookup"><span data-stu-id="3724e-105">Level</span></span>|<span data-ttu-id="3724e-106">説明</span><span class="sxs-lookup"><span data-stu-id="3724e-106">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="3724e-107">ブロック スコープ</span><span class="sxs-lookup"><span data-stu-id="3724e-107">Block scope</span></span>|<span data-ttu-id="3724e-108">それが宣言されているブロック、コード内でのみ使用可能</span><span class="sxs-lookup"><span data-stu-id="3724e-108">Available only within the code block in which it is declared</span></span>|  
|<span data-ttu-id="3724e-109">プロシージャ スコープ</span><span class="sxs-lookup"><span data-stu-id="3724e-109">Procedure scope</span></span>|<span data-ttu-id="3724e-110">宣言されているプロシージャ内のすべてのコードで使用可能</span><span class="sxs-lookup"><span data-stu-id="3724e-110">Available to all code within the procedure in which it is declared</span></span>|  
|<span data-ttu-id="3724e-111">モジュール スコープ</span><span class="sxs-lookup"><span data-stu-id="3724e-111">Module scope</span></span>|<span data-ttu-id="3724e-112">モジュール、クラス、または構造体が宣言されているすべてのコードで使用可能</span><span class="sxs-lookup"><span data-stu-id="3724e-112">Available to all code within the module, class, or structure in which it is declared</span></span>|  
|<span data-ttu-id="3724e-113">Namespace スコープ</span><span class="sxs-lookup"><span data-stu-id="3724e-113">Namespace scope</span></span>|<span data-ttu-id="3724e-114">名前空間が宣言されているすべてのコードで使用可能</span><span class="sxs-lookup"><span data-stu-id="3724e-114">Available to all code in the namespace in which it is declared</span></span>|  
  
 <span data-ttu-id="3724e-115">これらのレベルを最も幅の広い (名前空間)、最も狭い (ブロック) からスコープの進行状況の場所*最も狭いスコープ*修飾なしの要素を参照するコードの最小セットのことを意味します。</span><span class="sxs-lookup"><span data-stu-id="3724e-115">These levels of scope progress from the narrowest (block) to the widest (namespace), where *narrowest scope* means the smallest set of code that can refer to the element without qualification.</span></span> <span data-ttu-id="3724e-116">詳細については、このページで「レベルのスコープ」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3724e-116">For more information, see "Levels of Scope" on this page.</span></span>  
  
## <a name="specifying-scope-and-defining-variables"></a><span data-ttu-id="3724e-117">スコープを指定して、変数を定義します。</span><span class="sxs-lookup"><span data-stu-id="3724e-117">Specifying Scope and Defining Variables</span></span>  
 <span data-ttu-id="3724e-118">宣言するときに、要素のスコープを指定します。</span><span class="sxs-lookup"><span data-stu-id="3724e-118">You specify the scope of an element when you declare it.</span></span> <span data-ttu-id="3724e-119">スコープは、次の要因によって異なります。</span><span class="sxs-lookup"><span data-stu-id="3724e-119">The scope can depend on the following factors:</span></span>  
  
- <span data-ttu-id="3724e-120">要素を宣言するリージョン (ブロック、プロシージャ、モジュール、クラスまたは構造体)</span><span class="sxs-lookup"><span data-stu-id="3724e-120">The region (block, procedure, module, class, or structure) in which you declare the element</span></span>  
  
- <span data-ttu-id="3724e-121">要素の宣言を含む名前空間</span><span class="sxs-lookup"><span data-stu-id="3724e-121">The namespace containing the element's declaration</span></span>  
  
- <span data-ttu-id="3724e-122">要素の宣言するアクセス レベル</span><span class="sxs-lookup"><span data-stu-id="3724e-122">The access level you declare for the element</span></span>  
  
 <span data-ttu-id="3724e-123">これを行うため、名前が同じで、異なるスコープを持つ変数を定義するときに、注意してについては、予期しない結果につながります。</span><span class="sxs-lookup"><span data-stu-id="3724e-123">Use care when you define variables with the same name but different scope, because doing so can lead to unexpected results.</span></span> <span data-ttu-id="3724e-124">詳細については、「 [References to Declared Elements](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3724e-124">For more information, see [References to Declared Elements](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span></span>  
  
## <a name="levels-of-scope"></a><span data-ttu-id="3724e-125">スコープのレベル</span><span class="sxs-lookup"><span data-stu-id="3724e-125">Levels of Scope</span></span>  
 <span data-ttu-id="3724e-126">プログラミング要素は、その宣言領域全体で使用できます。</span><span class="sxs-lookup"><span data-stu-id="3724e-126">A programming element is available throughout the region in which you declare it.</span></span> <span data-ttu-id="3724e-127">同じリージョン内のすべてのコードは、その名前を修飾しなくても、要素を参照できます。</span><span class="sxs-lookup"><span data-stu-id="3724e-127">All code in the same region can refer to the element without qualifying its name.</span></span>  
  
### <a name="block-scope"></a><span data-ttu-id="3724e-128">ブロック スコープ</span><span class="sxs-lookup"><span data-stu-id="3724e-128">Block Scope</span></span>  
 <span data-ttu-id="3724e-129">ブロックを開始して、次の宣言ステートメントの終了で囲まれたステートメントのセットを示します。</span><span class="sxs-lookup"><span data-stu-id="3724e-129">A block is a set of statements enclosed within initiating and terminating declaration statements, such as the following:</span></span>  
  
- <span data-ttu-id="3724e-130">`Do` および `Loop`</span><span class="sxs-lookup"><span data-stu-id="3724e-130">`Do` and `Loop`</span></span>  
  
- <span data-ttu-id="3724e-131">`For` [`Each`] と `Next`</span><span class="sxs-lookup"><span data-stu-id="3724e-131">`For` [`Each`] and `Next`</span></span>  
  
- <span data-ttu-id="3724e-132">`If` および `End If`</span><span class="sxs-lookup"><span data-stu-id="3724e-132">`If` and `End If`</span></span>  
  
- <span data-ttu-id="3724e-133">`Select` および `End Select`</span><span class="sxs-lookup"><span data-stu-id="3724e-133">`Select` and `End Select`</span></span>  
  
- <span data-ttu-id="3724e-134">`SyncLock` および `End SyncLock`</span><span class="sxs-lookup"><span data-stu-id="3724e-134">`SyncLock` and `End SyncLock`</span></span>  
  
- <span data-ttu-id="3724e-135">`Try` および `End Try`</span><span class="sxs-lookup"><span data-stu-id="3724e-135">`Try` and `End Try`</span></span>  
  
- <span data-ttu-id="3724e-136">`While` および `End While`</span><span class="sxs-lookup"><span data-stu-id="3724e-136">`While` and `End While`</span></span>  
  
- <span data-ttu-id="3724e-137">`With` および `End With`</span><span class="sxs-lookup"><span data-stu-id="3724e-137">`With` and `End With`</span></span>  
  
 <span data-ttu-id="3724e-138">ブロック内で変数を宣言する場合は、そのブロック内でのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="3724e-138">If you declare a variable within a block, you can use it only within that block.</span></span> <span data-ttu-id="3724e-139">次の例では、整数変数のスコープで`cube`間ブロック`If`と`End If`を参照することが不要になったと`cube`ブロックからの実行のパスとします。</span><span class="sxs-lookup"><span data-stu-id="3724e-139">In the following example, the scope of the integer variable `cube` is the block between `If` and `End If`, and you can no longer refer to `cube` when execution passes out of the block.</span></span>  
  
```  
If n < 1291 Then  
    Dim cube As Integer  
    cube = n ^ 3  
End If  
```  
  
> [!NOTE]
>  <span data-ttu-id="3724e-140">変数のスコープは、ブロックに制限されている場合でもその有効期間は引き続き手順全体の。</span><span class="sxs-lookup"><span data-stu-id="3724e-140">Even if the scope of a variable is limited to a block, its lifetime is still that of the entire procedure.</span></span> <span data-ttu-id="3724e-141">処理中に、ブロックを複数回入力した場合、各ブロック変数は、前の値を保持します。</span><span class="sxs-lookup"><span data-stu-id="3724e-141">If you enter the block more than once during the procedure, each block variable retains its previous value.</span></span> <span data-ttu-id="3724e-142">このような場合に予期しない結果を回避するためには、ブロックの先頭ブロックの変数を初期化することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="3724e-142">To avoid unexpected results in such a case, it is wise to initialize block variables at the beginning of the block.</span></span>  
  
### <a name="procedure-scope"></a><span data-ttu-id="3724e-143">プロシージャ スコープ</span><span class="sxs-lookup"><span data-stu-id="3724e-143">Procedure Scope</span></span>  
 <span data-ttu-id="3724e-144">プロシージャ内で宣言された要素は、そのプロシージャの外にご利用いただけません。</span><span class="sxs-lookup"><span data-stu-id="3724e-144">An element declared within a procedure is not available outside that procedure.</span></span> <span data-ttu-id="3724e-145">宣言を含むプロシージャのみを使用できます。</span><span class="sxs-lookup"><span data-stu-id="3724e-145">Only the procedure that contains the declaration can use it.</span></span> <span data-ttu-id="3724e-146">このレベルの変数とも呼ばれます*ローカル変数*します。</span><span class="sxs-lookup"><span data-stu-id="3724e-146">Variables at this level are also known as *local variables*.</span></span> <span data-ttu-id="3724e-147">宣言することで、 [Dim ステートメント](../../../../visual-basic/language-reference/statements/dim-statement.md)、またはなし、[静的](../../../../visual-basic/language-reference/modifiers/static.md)キーワード。</span><span class="sxs-lookup"><span data-stu-id="3724e-147">You declare them with the [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md), with or without the [Static](../../../../visual-basic/language-reference/modifiers/static.md) keyword.</span></span>  
  
 <span data-ttu-id="3724e-148">プロシージャとブロックのスコープは密接に関連します。</span><span class="sxs-lookup"><span data-stu-id="3724e-148">Procedure and block scope are closely related.</span></span> <span data-ttu-id="3724e-149">プロシージャ内にあるが、そのプロシージャ内で任意のブロックの外部変数を宣言する場合、プロシージャ全体は、ブロック スコープを持つものとして変数を考えることができます。</span><span class="sxs-lookup"><span data-stu-id="3724e-149">If you declare a variable inside a procedure but outside any block within that procedure, you can think of the variable as having block scope, where the block is the entire procedure.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3724e-150">いる場合でも、すべてのローカル要素`Static`変数は、出現するプロシージャ。</span><span class="sxs-lookup"><span data-stu-id="3724e-150">All local elements, even if they are `Static` variables, are private to the procedure in which they appear.</span></span> <span data-ttu-id="3724e-151">使用して、要素を宣言することはできません、[パブリック](../../../../visual-basic/language-reference/modifiers/public.md)プロシージャ内でキーワード。</span><span class="sxs-lookup"><span data-stu-id="3724e-151">You cannot declare any element using the [Public](../../../../visual-basic/language-reference/modifiers/public.md) keyword within a procedure.</span></span>  
  
### <a name="module-scope"></a><span data-ttu-id="3724e-152">モジュール スコープ</span><span class="sxs-lookup"><span data-stu-id="3724e-152">Module Scope</span></span>  
 <span data-ttu-id="3724e-153">便宜上、1 つの用語*モジュール レベル*モジュール、クラス、および構造に当てはまります。</span><span class="sxs-lookup"><span data-stu-id="3724e-153">For convenience, the single term *module level* applies equally to modules, classes, and structures.</span></span> <span data-ttu-id="3724e-154">このレベルで要素を宣言するには、任意のプロシージャまたはブロックの外部では、モジュール、クラスまたは構造体の宣言ステートメントを配置します。</span><span class="sxs-lookup"><span data-stu-id="3724e-154">You can declare elements at this level by placing the declaration statement outside of any procedure or block but within the module, class, or structure.</span></span>  
  
 <span data-ttu-id="3724e-155">モジュール レベルで宣言すると、選択したアクセス レベルは、スコープを決定します。</span><span class="sxs-lookup"><span data-stu-id="3724e-155">When you make a declaration at the module level, the access level you choose determines the scope.</span></span> <span data-ttu-id="3724e-156">モジュール、クラスまたは構造体を含む名前空間には、スコープも影響します。</span><span class="sxs-lookup"><span data-stu-id="3724e-156">The namespace that contains the module, class, or structure also affects the scope.</span></span>  
  
 <span data-ttu-id="3724e-157">要素を宣言する[プライベート](../../../../visual-basic/language-reference/modifiers/private.md)アクセス レベルは別のモジュール内のコードではなく、そのモジュールでは、すべてのプロシージャに使用できます。</span><span class="sxs-lookup"><span data-stu-id="3724e-157">Elements for which you declare [Private](../../../../visual-basic/language-reference/modifiers/private.md) access level are available to every procedure in that module, but not to any code in a different module.</span></span> <span data-ttu-id="3724e-158">`Dim`モジュール レベルでのステートメントは既定に`Private`アクセス レベル キーワードを使用しない場合。</span><span class="sxs-lookup"><span data-stu-id="3724e-158">The `Dim` statement at module level defaults to `Private` if you do not use any access level keywords.</span></span> <span data-ttu-id="3724e-159">ただし、行うことができます、スコープとアクセス レベルより明白なを使用して、`Private`キーワード、`Dim`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="3724e-159">However, you can make the scope and access level more obvious by using the `Private` keyword in the `Dim` statement.</span></span>  
  
 <span data-ttu-id="3724e-160">次の例では、モジュールで定義されているすべてのプロシージャが文字列変数を指すこと`strMsg`します。</span><span class="sxs-lookup"><span data-stu-id="3724e-160">In the following example, all procedures defined in the module can refer to the string variable `strMsg`.</span></span> <span data-ttu-id="3724e-161">2 番目のプロシージャが呼び出されたときに、文字列変数の内容を表示します。 `strMsg`  ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="3724e-161">When the second procedure is called, it displays the contents of the string variable `strMsg` in a dialog box.</span></span>  
  
```  
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
  
### <a name="namespace-scope"></a><span data-ttu-id="3724e-162">Namespace スコープ</span><span class="sxs-lookup"><span data-stu-id="3724e-162">Namespace Scope</span></span>  
 <span data-ttu-id="3724e-163">モジュールを使用してレベルにある要素を宣言する場合、[フレンド](../../../../visual-basic/language-reference/modifiers/friend.md)または[パブリック](../../../../visual-basic/language-reference/modifiers/public.md)要素が宣言されている名前空間全体ですべてのプロシージャを使用可能になったキーワード。</span><span class="sxs-lookup"><span data-stu-id="3724e-163">If you declare an element at module level using the [Friend](../../../../visual-basic/language-reference/modifiers/friend.md) or [Public](../../../../visual-basic/language-reference/modifiers/public.md) keyword, it becomes available to all procedures throughout the namespace in which the element is declared.</span></span> <span data-ttu-id="3724e-164">上記の例では、文字列変数に次の変更と`strMsg`宣言の名前空間内のすべてのコードで参照できます。</span><span class="sxs-lookup"><span data-stu-id="3724e-164">With the following alteration to the preceding example, the string variable `strMsg` can be referred to by code anywhere in the namespace of its declaration.</span></span>  
  
```  
' Include this declaration at module level (not inside any procedure).  
Public strMsg As String  
```  
  
 <span data-ttu-id="3724e-165">Namespace スコープには、入れ子になった名前空間が含まれています。</span><span class="sxs-lookup"><span data-stu-id="3724e-165">Namespace scope includes nested namespaces.</span></span> <span data-ttu-id="3724e-166">名前空間内で使用可能な要素もその名前空間内で入れ子になった名前空間の中から使用できます。</span><span class="sxs-lookup"><span data-stu-id="3724e-166">An element available from within a namespace is also available from within any namespace nested inside that namespace.</span></span>  
  
 <span data-ttu-id="3724e-167">プロジェクトが含まれない場合[Namespace ステートメント](../../../../visual-basic/language-reference/statements/namespace-statement.md)s、同じ名前空間は、プロジェクト内のすべて。</span><span class="sxs-lookup"><span data-stu-id="3724e-167">If your project does not contain any [Namespace Statement](../../../../visual-basic/language-reference/statements/namespace-statement.md)s, everything in the project is in the same namespace.</span></span> <span data-ttu-id="3724e-168">この場合、名前空間のスコープは、プロジェクトのスコープとして考えることができます。</span><span class="sxs-lookup"><span data-stu-id="3724e-168">In this case, namespace scope can be thought of as project scope.</span></span> <span data-ttu-id="3724e-169">`Public` モジュール、クラスまたは構造内の要素は、プロジェクトを参照する任意のプロジェクトにも利用します。</span><span class="sxs-lookup"><span data-stu-id="3724e-169">`Public` elements in a module, class, or structure are also available to any project that references their project.</span></span>  
  
## <a name="choice-of-scope"></a><span data-ttu-id="3724e-170">スコープの選択</span><span class="sxs-lookup"><span data-stu-id="3724e-170">Choice of Scope</span></span>  
 <span data-ttu-id="3724e-171">変数を宣言するときにおく必要がありますに注意してください、次の点スコープを選択します。</span><span class="sxs-lookup"><span data-stu-id="3724e-171">When you declare a variable, you should keep in mind the following points when choosing its scope.</span></span>  
  
### <a name="advantages-of-local-variables"></a><span data-ttu-id="3724e-172">ローカル変数の利点</span><span class="sxs-lookup"><span data-stu-id="3724e-172">Advantages of Local Variables</span></span>  
 <span data-ttu-id="3724e-173">ローカル変数では、任意の種類の一時的な計算は、適切な選択が、次の理由です。</span><span class="sxs-lookup"><span data-stu-id="3724e-173">Local variables are a good choice for any kind of temporary calculation, for the following reasons:</span></span>  
  
- <span data-ttu-id="3724e-174">**名前の競合を回避することです。**</span><span class="sxs-lookup"><span data-stu-id="3724e-174">**Name Conflict Avoidance.**</span></span> <span data-ttu-id="3724e-175">ローカルの変数名が競合を受けやすくなります。</span><span class="sxs-lookup"><span data-stu-id="3724e-175">Local variable names are not susceptible to conflict.</span></span> <span data-ttu-id="3724e-176">たとえば、という名前の変数を含むいくつかの異なる手順を作成できます`intTemp`します。</span><span class="sxs-lookup"><span data-stu-id="3724e-176">For example, you can create several different procedures containing a variable called `intTemp`.</span></span> <span data-ttu-id="3724e-177">それぞれ`intTemp`各プロシージャに独自のバージョンのみが認識されるローカル変数として宣言されての`intTemp`します。</span><span class="sxs-lookup"><span data-stu-id="3724e-177">As long as each `intTemp` is declared as a local variable, each procedure recognizes only its own version of `intTemp`.</span></span> <span data-ttu-id="3724e-178">任意の 1 つのプロシージャは、ローカルの値を変更できます`intTemp`影響を与えずに`intTemp`他のプロシージャでの変数。</span><span class="sxs-lookup"><span data-stu-id="3724e-178">Any one procedure can alter the value in its local `intTemp` without affecting `intTemp` variables in other procedures.</span></span>  
  
- <span data-ttu-id="3724e-179">**メモリ使用量。**</span><span class="sxs-lookup"><span data-stu-id="3724e-179">**Memory Consumption.**</span></span> <span data-ttu-id="3724e-180">ローカル変数は、そのプロシージャが実行中にのみ、メモリを消費します。</span><span class="sxs-lookup"><span data-stu-id="3724e-180">Local variables consume memory only while their procedure is running.</span></span> <span data-ttu-id="3724e-181">プロシージャが呼び出し元のコードに返されるときに、メモリは解放されます。</span><span class="sxs-lookup"><span data-stu-id="3724e-181">Their memory is released when the procedure returns to the calling code.</span></span> <span data-ttu-id="3724e-182">これに対し、 [Shared](../../../../visual-basic/language-reference/modifiers/shared.md)と[静的](../../../../visual-basic/language-reference/modifiers/static.md)変数がメモリ リソースを消費するアプリケーションの実行が停止されるまで、そのために必要な場合にのみ使用します。</span><span class="sxs-lookup"><span data-stu-id="3724e-182">By contrast, [Shared](../../../../visual-basic/language-reference/modifiers/shared.md) and [Static](../../../../visual-basic/language-reference/modifiers/static.md) variables consume memory resources until your application stops running, so use them only when necessary.</span></span> <span data-ttu-id="3724e-183">*インスタンス変数*間メモリを消費、インスタンスが存在しているローカル変数よりも効率的ですよりも非効率`Shared`または`Static`変数。</span><span class="sxs-lookup"><span data-stu-id="3724e-183">*Instance variables* consume memory while their instance continues to exist, which makes them less efficient than local variables, but potentially more efficient than `Shared` or `Static` variables.</span></span>  
  
### <a name="minimizing-scope"></a><span data-ttu-id="3724e-184">スコープを最小限に抑える</span><span class="sxs-lookup"><span data-stu-id="3724e-184">Minimizing Scope</span></span>  
 <span data-ttu-id="3724e-185">一般に、任意の変数または定数を宣言するときをお勧めできるだけスコープを作成するプログラミング手法 (ブロック スコープでは、最も狭い)。</span><span class="sxs-lookup"><span data-stu-id="3724e-185">In general, when declaring any variable or constant, it is good programming practice to make the scope as narrow as possible (block scope is the narrowest).</span></span> <span data-ttu-id="3724e-186">これにより、メモリを節約でき、不正な変数を誤って参照するコードの可能性を最小限に抑えられます。</span><span class="sxs-lookup"><span data-stu-id="3724e-186">This helps conserve memory and minimizes the chances of your code erroneously referring to the wrong variable.</span></span> <span data-ttu-id="3724e-187">同様に、ある変数を宣言する必要があります[静的](../../../../visual-basic/language-reference/modifiers/static.md)プロシージャ呼び出しの間には、その値を保持するために必要な場合のみです。</span><span class="sxs-lookup"><span data-stu-id="3724e-187">Similarly, you should declare a variable to be [Static](../../../../visual-basic/language-reference/modifiers/static.md) only when it is necessary to preserve its value between procedure calls.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3724e-188">関連項目</span><span class="sxs-lookup"><span data-stu-id="3724e-188">See also</span></span>

- [<span data-ttu-id="3724e-189">宣言された要素の特性</span><span class="sxs-lookup"><span data-stu-id="3724e-189">Declared Element Characteristics</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md)
- [<span data-ttu-id="3724e-190">方法: コントロール変数のスコープ</span><span class="sxs-lookup"><span data-stu-id="3724e-190">How to: Control the Scope of a Variable</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-control-the-scope-of-a-variable.md)
- [<span data-ttu-id="3724e-191">Visual Basic での有効期間</span><span class="sxs-lookup"><span data-stu-id="3724e-191">Lifetime in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md)
- [<span data-ttu-id="3724e-192">Visual Basic でのアクセス レベル</span><span class="sxs-lookup"><span data-stu-id="3724e-192">Access levels in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
- [<span data-ttu-id="3724e-193">宣言された要素の参照</span><span class="sxs-lookup"><span data-stu-id="3724e-193">References to Declared Elements</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
- [<span data-ttu-id="3724e-194">変数宣言</span><span class="sxs-lookup"><span data-stu-id="3724e-194">Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
