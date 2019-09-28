---
title: Using ステートメント (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.using
helpviewer_keywords:
- resource disposal
- Try...Catch...Finally statements, equivalent to Using statement
- resources [Visual Basic], disposing
- Using statement [Visual Basic]
ms.assetid: 665d1580-dd54-4e96-a9a9-6be2a68948f1
ms.openlocfilehash: 819af63acb6a1f038300bcb999dcfb904eb8a457
ms.sourcegitcommit: 35da8fb45b4cca4e59cc99a5c56262c356977159
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/28/2019
ms.locfileid: "71592083"
---
# <a name="using-statement-visual-basic"></a><span data-ttu-id="677ac-102">Using ステートメント (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="677ac-102">Using Statement (Visual Basic)</span></span>

<span data-ttu-id="677ac-103">@No__t 0 ブロックの先頭を宣言し、必要に応じて、ブロックが制御するシステムリソースを取得します。</span><span class="sxs-lookup"><span data-stu-id="677ac-103">Declares the beginning of a `Using` block and optionally acquires the system resources that the block controls.</span></span>

## <a name="syntax"></a><span data-ttu-id="677ac-104">構文</span><span class="sxs-lookup"><span data-stu-id="677ac-104">Syntax</span></span>

```vb
Using { resourcelist | resourceexpression }
    [ statements ]
End Using
```

## <a name="parts"></a><span data-ttu-id="677ac-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="677ac-105">Parts</span></span>

|<span data-ttu-id="677ac-106">項目</span><span class="sxs-lookup"><span data-stu-id="677ac-106">Term</span></span>|<span data-ttu-id="677ac-107">定義</span><span class="sxs-lookup"><span data-stu-id="677ac-107">Definition</span></span>|  
|---|---|  
|`resourcelist`|<span data-ttu-id="677ac-108">@No__t-0 を指定しない場合は必須です。</span><span class="sxs-lookup"><span data-stu-id="677ac-108">Required if you do not supply `resourceexpression`.</span></span> <span data-ttu-id="677ac-109">この @no__t によって制御される1つ以上のシステムリソースのリスト (コンマ区切り)。</span><span class="sxs-lookup"><span data-stu-id="677ac-109">List of one or more system resources that this `Using` block controls, separated by commas.</span></span>|  
|`resourceexpression`|<span data-ttu-id="677ac-110">@No__t-0 を指定しない場合は必須です。</span><span class="sxs-lookup"><span data-stu-id="677ac-110">Required if you do not supply `resourcelist`.</span></span> <span data-ttu-id="677ac-111">この `Using` ブロックによって制御されるシステムリソースを参照する、参照変数または式。</span><span class="sxs-lookup"><span data-stu-id="677ac-111">Reference variable or expression referring to a system resource to be controlled by this `Using` block.</span></span>|  
|`statements`|<span data-ttu-id="677ac-112">任意。</span><span class="sxs-lookup"><span data-stu-id="677ac-112">Optional.</span></span> <span data-ttu-id="677ac-113">@No__t 0 ブロックによって実行されるステートメントのブロック。</span><span class="sxs-lookup"><span data-stu-id="677ac-113">Block of statements that the `Using` block runs.</span></span>|  
|`End Using`|<span data-ttu-id="677ac-114">必須。</span><span class="sxs-lookup"><span data-stu-id="677ac-114">Required.</span></span> <span data-ttu-id="677ac-115">@No__t 0 ブロックの定義を終了し、制御しているすべてのリソースを破棄します。</span><span class="sxs-lookup"><span data-stu-id="677ac-115">Terminates the definition of the `Using` block and disposes of all the resources that it controls.</span></span>|  

 <span data-ttu-id="677ac-116">@No__t-0 部分の各リソースには、次の構文と部分があります。</span><span class="sxs-lookup"><span data-stu-id="677ac-116">Each resource in the `resourcelist` part has the following syntax and parts:</span></span>

 `resourcename As New resourcetype [ ( [ arglist ] ) ]`

 <span data-ttu-id="677ac-117">\- または -</span><span class="sxs-lookup"><span data-stu-id="677ac-117">-or-</span></span>

 `resourcename As resourcetype = resourceexpression`

## <a name="resourcelist-parts"></a><span data-ttu-id="677ac-118">resourcelist パーツ</span><span class="sxs-lookup"><span data-stu-id="677ac-118">resourcelist Parts</span></span>

|<span data-ttu-id="677ac-119">項目</span><span class="sxs-lookup"><span data-stu-id="677ac-119">Term</span></span>|<span data-ttu-id="677ac-120">定義</span><span class="sxs-lookup"><span data-stu-id="677ac-120">Definition</span></span>|  
|---|---|  
|`resourcename`|<span data-ttu-id="677ac-121">必須。</span><span class="sxs-lookup"><span data-stu-id="677ac-121">Required.</span></span> <span data-ttu-id="677ac-122">@No__t 0 ブロックで制御されるシステムリソースを参照する参照変数。</span><span class="sxs-lookup"><span data-stu-id="677ac-122">Reference variable that refers to a system resource that the `Using` block controls.</span></span>|  
|`New`|<span data-ttu-id="677ac-123">@No__t-0 ステートメントでリソースが取得される場合は必須です。</span><span class="sxs-lookup"><span data-stu-id="677ac-123">Required if the `Using` statement acquires the resource.</span></span> <span data-ttu-id="677ac-124">リソースを既に取得している場合は、2番目の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="677ac-124">If you have already acquired the resource, use the second syntax alternative.</span></span>|  
|`resourcetype`|<span data-ttu-id="677ac-125">必須。</span><span class="sxs-lookup"><span data-stu-id="677ac-125">Required.</span></span> <span data-ttu-id="677ac-126">リソースのクラス。</span><span class="sxs-lookup"><span data-stu-id="677ac-126">The class of the resource.</span></span> <span data-ttu-id="677ac-127">クラスは <xref:System.IDisposable> インターフェイスを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="677ac-127">The class must implement the <xref:System.IDisposable> interface.</span></span>|  
|`arglist`|<span data-ttu-id="677ac-128">任意。</span><span class="sxs-lookup"><span data-stu-id="677ac-128">Optional.</span></span> <span data-ttu-id="677ac-129">のインスタンスを作成するためにコンストラクターに渡す引数のリスト `resourcetype`。</span><span class="sxs-lookup"><span data-stu-id="677ac-129">List of arguments you are passing to the constructor to create an instance of `resourcetype`.</span></span> <span data-ttu-id="677ac-130">「[パラメーターリスト](parameter-list.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="677ac-130">See [Parameter List](parameter-list.md).</span></span>|  
|`resourceexpression`|<span data-ttu-id="677ac-131">必須。</span><span class="sxs-lookup"><span data-stu-id="677ac-131">Required.</span></span> <span data-ttu-id="677ac-132">@No__t-0 の要件を満たすシステムリソースを参照する変数または式。</span><span class="sxs-lookup"><span data-stu-id="677ac-132">Variable or expression referring to a system resource satisfying the requirements of `resourcetype`.</span></span> <span data-ttu-id="677ac-133">2番目の構文を使用する場合は、`Using` ステートメントに制御を渡す前にリソースを取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="677ac-133">If you use the second syntax alternative, you must acquire the resource before passing control to the `Using` statement.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="677ac-134">コメント</span><span class="sxs-lookup"><span data-stu-id="677ac-134">Remarks</span></span>

 <span data-ttu-id="677ac-135">コードには、ファイルハンドル、COM ラッパー、SQL 接続などのアンマネージリソースが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="677ac-135">Sometimes your code requires an unmanaged resource, such as a file handle, a COM wrapper, or a SQL connection.</span></span> <span data-ttu-id="677ac-136">@No__t-0 ブロックを使用すると、コードが終了したときに、そのようなリソースが確実に破棄されます。</span><span class="sxs-lookup"><span data-stu-id="677ac-136">A `Using` block guarantees the disposal of one or more such resources when your code is finished with them.</span></span> <span data-ttu-id="677ac-137">これにより、他のコードで使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="677ac-137">This makes them available for other code to use.</span></span>

 <span data-ttu-id="677ac-138">マネージリソースは、.NET Framework ガベージコレクター (GC) によって破棄されます。その際、追加のコーディングは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="677ac-138">Managed resources are disposed of by the .NET Framework garbage collector (GC) without any extra coding on your part.</span></span> <span data-ttu-id="677ac-139">マネージリソースに `Using` ブロックは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="677ac-139">You do not need a `Using` block for managed resources.</span></span> <span data-ttu-id="677ac-140">ただし、`Using` のブロックを使用して、ガベージコレクターを待機するのではなく、マネージリソースを強制的に破棄することもできます。</span><span class="sxs-lookup"><span data-stu-id="677ac-140">However, you can still use a `Using` block to force the disposal of a managed resource instead of waiting for the garbage collector.</span></span>

 <span data-ttu-id="677ac-141">@No__t 0 のブロックには、取得、使用、および破棄という3つの部分があります。</span><span class="sxs-lookup"><span data-stu-id="677ac-141">A `Using` block has three parts: acquisition, usage, and disposal.</span></span>

- <span data-ttu-id="677ac-142">*取得*とは、変数を作成して初期化し、システムリソースを参照することを意味します。</span><span class="sxs-lookup"><span data-stu-id="677ac-142">*Acquisition* means creating a variable and initializing it to refer to the system resource.</span></span> <span data-ttu-id="677ac-143">@No__t 0 のステートメントは1つ以上のリソースを取得できます。また、ブロックを入力する前に1つのリソースだけを取得し、それを `Using` ステートメントに指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="677ac-143">The `Using` statement can acquire one or more resources, or you can acquire exactly one resource before entering the block and supply it to the `Using` statement.</span></span> <span data-ttu-id="677ac-144">@No__t-0 を指定する場合は、`Using` ステートメントに制御を渡す前にリソースを取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="677ac-144">If you supply `resourceexpression`, you must acquire the resource before passing control to the `Using` statement.</span></span>

- <span data-ttu-id="677ac-145">*使用状況*とは、リソースにアクセスし、それらのリソースでアクションを実行することを意味します。</span><span class="sxs-lookup"><span data-stu-id="677ac-145">*Usage* means accessing the resources and performing actions with them.</span></span> <span data-ttu-id="677ac-146">@No__t-0 と `End Using` の間のステートメントは、リソースの使用状況を表します。</span><span class="sxs-lookup"><span data-stu-id="677ac-146">The statements between `Using` and `End Using` represent the usage of the resources.</span></span>

- <span data-ttu-id="677ac-147">*破棄*とは、`resourcename` でオブジェクトの <xref:System.IDisposable.Dispose%2A> メソッドを呼び出すことを意味します。</span><span class="sxs-lookup"><span data-stu-id="677ac-147">*Disposal* means calling the <xref:System.IDisposable.Dispose%2A> method on the object in `resourcename`.</span></span> <span data-ttu-id="677ac-148">これにより、オブジェクトはリソースを完全に終了できます。</span><span class="sxs-lookup"><span data-stu-id="677ac-148">This allows the object to cleanly terminate its resources.</span></span> <span data-ttu-id="677ac-149">@No__t-0 ステートメントは、`Using` ブロックのコントロールの下にあるリソースを破棄します。</span><span class="sxs-lookup"><span data-stu-id="677ac-149">The `End Using` statement disposes of the resources under the `Using` block's control.</span></span>

## <a name="behavior"></a><span data-ttu-id="677ac-150">動作</span><span class="sxs-lookup"><span data-stu-id="677ac-150">Behavior</span></span>

 <span data-ttu-id="677ac-151">@No__t 0 のブロックは、`Try`... `Finally` の構造のように動作します。この構築では、@no__t 3 ブロックがリソースを使用し、@no__t 4 ブロックがそれらを破棄します。</span><span class="sxs-lookup"><span data-stu-id="677ac-151">A `Using` block behaves like a `Try`...`Finally` construction in which the `Try` block uses the resources and the `Finally` block disposes of them.</span></span> <span data-ttu-id="677ac-152">このため、`Using` ブロックは、ブロックを終了する方法に関係なく、リソースの破棄を保証します。</span><span class="sxs-lookup"><span data-stu-id="677ac-152">Because of this, the `Using` block guarantees disposal of the resources, no matter how you exit the block.</span></span> <span data-ttu-id="677ac-153">これは、ハンドルされない例外が発生した場合でも、<xref:System.StackOverflowException> 以外の場合にも当てはまります。</span><span class="sxs-lookup"><span data-stu-id="677ac-153">This is true even in the case of an unhandled exception, except for a <xref:System.StackOverflowException>.</span></span>

 <span data-ttu-id="677ac-154">@No__t-0 ステートメントで取得したすべてのリソース変数のスコープは、`Using` ブロックに制限されます。</span><span class="sxs-lookup"><span data-stu-id="677ac-154">The scope of every resource variable acquired by the `Using` statement is limited to the `Using` block.</span></span>

 <span data-ttu-id="677ac-155">@No__t-0 ステートメントで複数のシステムリソースを指定した場合、その効果は、`Using` ブロックを入れ子にした場合と同じになります。</span><span class="sxs-lookup"><span data-stu-id="677ac-155">If you specify more than one system resource in the `Using` statement, the effect is the same as if you nested `Using` blocks one within another.</span></span>

 <span data-ttu-id="677ac-156">@No__t-0 が `Nothing` の場合、<xref:System.IDisposable.Dispose%2A> の呼び出しは行われず、例外はスローされません。</span><span class="sxs-lookup"><span data-stu-id="677ac-156">If `resourcename` is `Nothing`, no call to <xref:System.IDisposable.Dispose%2A> is made, and no exception is thrown.</span></span>

## <a name="structured-exception-handling-within-a-using-block"></a><span data-ttu-id="677ac-157">Using ブロック内での構造化例外処理</span><span class="sxs-lookup"><span data-stu-id="677ac-157">Structured Exception Handling Within a Using Block</span></span>

 <span data-ttu-id="677ac-158">@No__t-0 ブロック内で発生する可能性のある例外を処理する必要がある場合は、完全な `Try`... `Finally` の構築をそれに追加することができます。</span><span class="sxs-lookup"><span data-stu-id="677ac-158">If you need to handle an exception that might occur within the `Using` block, you can add a complete `Try`...`Finally` construction to it.</span></span> <span data-ttu-id="677ac-159">@No__t-0 ステートメントがリソースの取得に失敗した場合に対処する必要がある場合は、`resourcename` が @no__t かどうかをテストして確認できます。</span><span class="sxs-lookup"><span data-stu-id="677ac-159">If you need to handle the case where the `Using` statement is not successful in acquiring a resource, you can test to see if `resourcename` is `Nothing`.</span></span>

## <a name="structured-exception-handling-instead-of-a-using-block"></a><span data-ttu-id="677ac-160">Using ブロックの代わりに構造化例外処理</span><span class="sxs-lookup"><span data-stu-id="677ac-160">Structured Exception Handling Instead of a Using Block</span></span>

 <span data-ttu-id="677ac-161">リソースの取得をより細かく制御する必要がある場合、または `Finally` ブロックに追加のコードが必要な場合は、`Using` ブロックを `Try`... `Finally` の構築として書き換えることができます。</span><span class="sxs-lookup"><span data-stu-id="677ac-161">If you need finer control over the acquisition of the resources, or you need additional code in the `Finally` block, you can rewrite the `Using` block as a `Try`...`Finally` construction.</span></span> <span data-ttu-id="677ac-162">次の例は、`resource` の取得と破棄に相当するスケルトン `Try` および @no__t の構造を示しています。</span><span class="sxs-lookup"><span data-stu-id="677ac-162">The following example shows skeleton `Try` and `Using` constructions that are equivalent in the acquisition and disposal of `resource`.</span></span>

```vb
Using resource As New resourceType
    ' Insert code to work with resource.
End Using

' For the acquisition and disposal of resource, the following  
' Try construction is equivalent to the Using block.
Dim resource As New resourceType
Try
    ' Insert code to work with resource.
Finally
    If resource IsNot Nothing Then
        resource.Dispose()
    End If
End Try
```

> [!NOTE]
> <span data-ttu-id="677ac-163">@No__t-0 ブロック内のコードでは、`resourcename` のオブジェクトを別の変数に割り当てることはできません。</span><span class="sxs-lookup"><span data-stu-id="677ac-163">The code inside the `Using` block should not assign the object in `resourcename` to another variable.</span></span> <span data-ttu-id="677ac-164">@No__t-0 ブロックを終了すると、リソースが破棄され、他の変数はそのリソースが指しているリソースにアクセスできなくなります。</span><span class="sxs-lookup"><span data-stu-id="677ac-164">When you exit the `Using` block, the resource is disposed, and the other variable cannot access the resource to which it points.</span></span>

## <a name="example"></a><span data-ttu-id="677ac-165">例</span><span class="sxs-lookup"><span data-stu-id="677ac-165">Example</span></span>

 <span data-ttu-id="677ac-166">次の例では、test.txt という名前のファイルを作成し、ファイルに2行のテキストを書き込みます。</span><span class="sxs-lookup"><span data-stu-id="677ac-166">The following example creates a file that is named log.txt and writes two lines of text to the file.</span></span> <span data-ttu-id="677ac-167">この例でも同じファイルが読み取られ、テキスト行が表示されます。</span><span class="sxs-lookup"><span data-stu-id="677ac-167">The example also reads that same file and displays the lines of text:</span></span>

 <span data-ttu-id="677ac-168">@No__t-0 および <xref:System.IO.TextReader> クラスは <xref:System.IDisposable> インターフェイスを実装するため、コードでは `Using` ステートメントを使用して、書き込み操作と読み取り操作の後でファイルが正しく閉じられるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="677ac-168">Because the <xref:System.IO.TextWriter> and <xref:System.IO.TextReader> classes implement the <xref:System.IDisposable> interface, the code can use `Using` statements to ensure that the file is correctly closed after the write and read operations.</span></span>

 [!code-vb[VbVbalrStatements#50](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#50)]

## <a name="see-also"></a><span data-ttu-id="677ac-169">関連項目</span><span class="sxs-lookup"><span data-stu-id="677ac-169">See also</span></span>

- <xref:System.IDisposable>
- [<span data-ttu-id="677ac-170">Try...Catch...Finally ステートメント</span><span class="sxs-lookup"><span data-stu-id="677ac-170">Try...Catch...Finally Statement</span></span>](try-catch-finally-statement.md)
- <span data-ttu-id="677ac-171">[2 つのオブジェクトが等しいかどうかをテストする方法システムリソースの破棄 @ no__t-0</span><span class="sxs-lookup"><span data-stu-id="677ac-171">[How to: Dispose of a System Resource](../../programming-guide/language-features/control-flow/how-to-dispose-of-a-system-resource.md)</span></span>
