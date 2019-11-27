---
title: Using ステートメント
ms.date: 07/20/2015
f1_keywords:
- vb.using
helpviewer_keywords:
- resource disposal
- Try...Catch...Finally statements, equivalent to Using statement
- resources [Visual Basic], disposing
- Using statement [Visual Basic]
ms.assetid: 665d1580-dd54-4e96-a9a9-6be2a68948f1
ms.openlocfilehash: 6ec0e228b3898f66f27e322b5db2dd7f3bf3d7d6
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352756"
---
# <a name="using-statement-visual-basic"></a><span data-ttu-id="37364-102">Using ステートメント (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="37364-102">Using Statement (Visual Basic)</span></span>

<span data-ttu-id="37364-103">`Using` ブロックの先頭を宣言し、必要に応じて、ブロックが制御するシステムリソースを取得します。</span><span class="sxs-lookup"><span data-stu-id="37364-103">Declares the beginning of a `Using` block and optionally acquires the system resources that the block controls.</span></span>

## <a name="syntax"></a><span data-ttu-id="37364-104">構文</span><span class="sxs-lookup"><span data-stu-id="37364-104">Syntax</span></span>

```vb
Using { resourcelist | resourceexpression }
    [ statements ]
End Using
```

## <a name="parts"></a><span data-ttu-id="37364-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="37364-105">Parts</span></span>

|<span data-ttu-id="37364-106">用語</span><span class="sxs-lookup"><span data-stu-id="37364-106">Term</span></span>|<span data-ttu-id="37364-107">Definition</span><span class="sxs-lookup"><span data-stu-id="37364-107">Definition</span></span>|  
|---|---|  
|`resourcelist`|<span data-ttu-id="37364-108">`resourceexpression`を指定しない場合は必須です。</span><span class="sxs-lookup"><span data-stu-id="37364-108">Required if you do not supply `resourceexpression`.</span></span> <span data-ttu-id="37364-109">この `Using` ブロックをコンマで区切った1つまたは複数のシステムリソースの一覧。</span><span class="sxs-lookup"><span data-stu-id="37364-109">List of one or more system resources that this `Using` block controls, separated by commas.</span></span>|  
|`resourceexpression`|<span data-ttu-id="37364-110">`resourcelist`を指定しない場合は必須です。</span><span class="sxs-lookup"><span data-stu-id="37364-110">Required if you do not supply `resourcelist`.</span></span> <span data-ttu-id="37364-111">この `Using` ブロックによって制御されるシステムリソースを参照する、参照変数または式。</span><span class="sxs-lookup"><span data-stu-id="37364-111">Reference variable or expression referring to a system resource to be controlled by this `Using` block.</span></span>|  
|`statements`|<span data-ttu-id="37364-112">省略可。</span><span class="sxs-lookup"><span data-stu-id="37364-112">Optional.</span></span> <span data-ttu-id="37364-113">`Using` ブロックによって実行されるステートメントのブロック。</span><span class="sxs-lookup"><span data-stu-id="37364-113">Block of statements that the `Using` block runs.</span></span>|  
|`End Using`|<span data-ttu-id="37364-114">必須。</span><span class="sxs-lookup"><span data-stu-id="37364-114">Required.</span></span> <span data-ttu-id="37364-115">`Using` ブロックの定義を終了し、制御しているすべてのリソースを破棄します。</span><span class="sxs-lookup"><span data-stu-id="37364-115">Terminates the definition of the `Using` block and disposes of all the resources that it controls.</span></span>|  

 <span data-ttu-id="37364-116">`resourcelist` パートの各リソースには、次の構文と部分があります。</span><span class="sxs-lookup"><span data-stu-id="37364-116">Each resource in the `resourcelist` part has the following syntax and parts:</span></span>

 `resourcename As New resourcetype [ ( [ arglist ] ) ]`

 <span data-ttu-id="37364-117">または</span><span class="sxs-lookup"><span data-stu-id="37364-117">-or-</span></span>

 `resourcename As resourcetype = resourceexpression`

## <a name="resourcelist-parts"></a><span data-ttu-id="37364-118">resourcelist パーツ</span><span class="sxs-lookup"><span data-stu-id="37364-118">resourcelist Parts</span></span>

|<span data-ttu-id="37364-119">用語</span><span class="sxs-lookup"><span data-stu-id="37364-119">Term</span></span>|<span data-ttu-id="37364-120">Definition</span><span class="sxs-lookup"><span data-stu-id="37364-120">Definition</span></span>|  
|---|---|  
|`resourcename`|<span data-ttu-id="37364-121">必須。</span><span class="sxs-lookup"><span data-stu-id="37364-121">Required.</span></span> <span data-ttu-id="37364-122">`Using` ブロックで制御されるシステムリソースを参照する参照変数。</span><span class="sxs-lookup"><span data-stu-id="37364-122">Reference variable that refers to a system resource that the `Using` block controls.</span></span>|  
|`New`|<span data-ttu-id="37364-123">`Using` ステートメントがリソースを取得する場合は必須です。</span><span class="sxs-lookup"><span data-stu-id="37364-123">Required if the `Using` statement acquires the resource.</span></span> <span data-ttu-id="37364-124">リソースを既に取得している場合は、2番目の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="37364-124">If you have already acquired the resource, use the second syntax alternative.</span></span>|  
|`resourcetype`|<span data-ttu-id="37364-125">必須。</span><span class="sxs-lookup"><span data-stu-id="37364-125">Required.</span></span> <span data-ttu-id="37364-126">リソースのクラス。</span><span class="sxs-lookup"><span data-stu-id="37364-126">The class of the resource.</span></span> <span data-ttu-id="37364-127">クラスは、<xref:System.IDisposable> インターフェイスを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="37364-127">The class must implement the <xref:System.IDisposable> interface.</span></span>|  
|`arglist`|<span data-ttu-id="37364-128">省略可。</span><span class="sxs-lookup"><span data-stu-id="37364-128">Optional.</span></span> <span data-ttu-id="37364-129">`resourcetype`のインスタンスを作成するためにコンストラクターに渡す引数のリスト。</span><span class="sxs-lookup"><span data-stu-id="37364-129">List of arguments you are passing to the constructor to create an instance of `resourcetype`.</span></span> <span data-ttu-id="37364-130">「[パラメーターリスト](parameter-list.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="37364-130">See [Parameter List](parameter-list.md).</span></span>|  
|`resourceexpression`|<span data-ttu-id="37364-131">必須。</span><span class="sxs-lookup"><span data-stu-id="37364-131">Required.</span></span> <span data-ttu-id="37364-132">`resourcetype`の要件を満たすシステムリソースを参照する変数または式。</span><span class="sxs-lookup"><span data-stu-id="37364-132">Variable or expression referring to a system resource satisfying the requirements of `resourcetype`.</span></span> <span data-ttu-id="37364-133">2番目の構文を使用する場合は、`Using` ステートメントに制御を渡す前にリソースを取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="37364-133">If you use the second syntax alternative, you must acquire the resource before passing control to the `Using` statement.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="37364-134">コメント</span><span class="sxs-lookup"><span data-stu-id="37364-134">Remarks</span></span>

 <span data-ttu-id="37364-135">コードには、ファイルハンドル、COM ラッパー、SQL 接続などのアンマネージリソースが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="37364-135">Sometimes your code requires an unmanaged resource, such as a file handle, a COM wrapper, or a SQL connection.</span></span> <span data-ttu-id="37364-136">`Using` ブロックは、コードが終了したときに、そのようなリソースが確実に破棄されるようにします。</span><span class="sxs-lookup"><span data-stu-id="37364-136">A `Using` block guarantees the disposal of one or more such resources when your code is finished with them.</span></span> <span data-ttu-id="37364-137">これにより、他のコードで使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="37364-137">This makes them available for other code to use.</span></span>

 <span data-ttu-id="37364-138">マネージリソースは、.NET Framework ガベージコレクター (GC) によって破棄されます。その際、追加のコーディングは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="37364-138">Managed resources are disposed of by the .NET Framework garbage collector (GC) without any extra coding on your part.</span></span> <span data-ttu-id="37364-139">マネージリソースに `Using` ブロックは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="37364-139">You do not need a `Using` block for managed resources.</span></span> <span data-ttu-id="37364-140">ただし、`Using` ブロックを使用して、ガベージコレクターを待機するのではなく、マネージリソースを強制的に破棄することもできます。</span><span class="sxs-lookup"><span data-stu-id="37364-140">However, you can still use a `Using` block to force the disposal of a managed resource instead of waiting for the garbage collector.</span></span>

 <span data-ttu-id="37364-141">`Using` ブロックには、取得、使用、および破棄という3つの部分があります。</span><span class="sxs-lookup"><span data-stu-id="37364-141">A `Using` block has three parts: acquisition, usage, and disposal.</span></span>

- <span data-ttu-id="37364-142">*取得*とは、変数を作成して初期化し、システムリソースを参照することを意味します。</span><span class="sxs-lookup"><span data-stu-id="37364-142">*Acquisition* means creating a variable and initializing it to refer to the system resource.</span></span> <span data-ttu-id="37364-143">`Using` ステートメントは1つ以上のリソースを取得できます。また、ブロックを入力する前に1つのリソースだけを取得し、それを `Using` ステートメントに指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="37364-143">The `Using` statement can acquire one or more resources, or you can acquire exactly one resource before entering the block and supply it to the `Using` statement.</span></span> <span data-ttu-id="37364-144">`resourceexpression`を指定する場合は、`Using` ステートメントに制御を渡す前にリソースを取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="37364-144">If you supply `resourceexpression`, you must acquire the resource before passing control to the `Using` statement.</span></span>

- <span data-ttu-id="37364-145">*使用状況*とは、リソースにアクセスし、それらのリソースでアクションを実行することを意味します。</span><span class="sxs-lookup"><span data-stu-id="37364-145">*Usage* means accessing the resources and performing actions with them.</span></span> <span data-ttu-id="37364-146">`Using` と `End Using` 間のステートメントは、リソースの使用状況を表します。</span><span class="sxs-lookup"><span data-stu-id="37364-146">The statements between `Using` and `End Using` represent the usage of the resources.</span></span>

- <span data-ttu-id="37364-147">*破棄*とは、`resourcename`内のオブジェクトに対して <xref:System.IDisposable.Dispose%2A> メソッドを呼び出すことを意味します。</span><span class="sxs-lookup"><span data-stu-id="37364-147">*Disposal* means calling the <xref:System.IDisposable.Dispose%2A> method on the object in `resourcename`.</span></span> <span data-ttu-id="37364-148">これにより、オブジェクトはリソースを完全に終了できます。</span><span class="sxs-lookup"><span data-stu-id="37364-148">This allows the object to cleanly terminate its resources.</span></span> <span data-ttu-id="37364-149">`End Using` ステートメントは、`Using` ブロックのコントロールの下にあるリソースを破棄します。</span><span class="sxs-lookup"><span data-stu-id="37364-149">The `End Using` statement disposes of the resources under the `Using` block's control.</span></span>

## <a name="behavior"></a><span data-ttu-id="37364-150">動作</span><span class="sxs-lookup"><span data-stu-id="37364-150">Behavior</span></span>

 <span data-ttu-id="37364-151">`Using` ブロックは `Try`...`Finally` 構築のように動作し、`Try` ブロックはリソースを使用し、`Finally` ブロックはそれらを破棄します。</span><span class="sxs-lookup"><span data-stu-id="37364-151">A `Using` block behaves like a `Try`...`Finally` construction in which the `Try` block uses the resources and the `Finally` block disposes of them.</span></span> <span data-ttu-id="37364-152">このため、ブロックの終了方法に関係なく、`Using` ブロックによってリソースが確実に破棄されます。</span><span class="sxs-lookup"><span data-stu-id="37364-152">Because of this, the `Using` block guarantees disposal of the resources, no matter how you exit the block.</span></span> <span data-ttu-id="37364-153">これは、ハンドルされない例外が発生した場合でも、<xref:System.StackOverflowException>を除き、true になります。</span><span class="sxs-lookup"><span data-stu-id="37364-153">This is true even in the case of an unhandled exception, except for a <xref:System.StackOverflowException>.</span></span>

 <span data-ttu-id="37364-154">`Using` ステートメントによって取得されるすべてのリソース変数のスコープは、`Using` ブロックに制限されます。</span><span class="sxs-lookup"><span data-stu-id="37364-154">The scope of every resource variable acquired by the `Using` statement is limited to the `Using` block.</span></span>

 <span data-ttu-id="37364-155">`Using` ステートメントで複数のシステムリソースを指定した場合、その効果は、入れ子になった `Using` ブロックを別のでブロックした場合と同じになります。</span><span class="sxs-lookup"><span data-stu-id="37364-155">If you specify more than one system resource in the `Using` statement, the effect is the same as if you nested `Using` blocks one within another.</span></span>

 <span data-ttu-id="37364-156">`resourcename` が `Nothing`場合、<xref:System.IDisposable.Dispose%2A> の呼び出しは行われず、例外はスローされません。</span><span class="sxs-lookup"><span data-stu-id="37364-156">If `resourcename` is `Nothing`, no call to <xref:System.IDisposable.Dispose%2A> is made, and no exception is thrown.</span></span>

## <a name="structured-exception-handling-within-a-using-block"></a><span data-ttu-id="37364-157">Using ブロック内での構造化例外処理</span><span class="sxs-lookup"><span data-stu-id="37364-157">Structured Exception Handling Within a Using Block</span></span>

 <span data-ttu-id="37364-158">`Using` ブロック内で発生する可能性のある例外を処理する必要がある場合は、完全な `Try`...`Finally` 構築を追加できます。</span><span class="sxs-lookup"><span data-stu-id="37364-158">If you need to handle an exception that might occur within the `Using` block, you can add a complete `Try`...`Finally` construction to it.</span></span> <span data-ttu-id="37364-159">`Using` ステートメントがリソースの取得に失敗した場合に対処する必要がある場合は、`resourcename` が `Nothing`かどうかをテストして確認できます。</span><span class="sxs-lookup"><span data-stu-id="37364-159">If you need to handle the case where the `Using` statement is not successful in acquiring a resource, you can test to see if `resourcename` is `Nothing`.</span></span>

## <a name="structured-exception-handling-instead-of-a-using-block"></a><span data-ttu-id="37364-160">Using ブロックの代わりに構造化例外処理</span><span class="sxs-lookup"><span data-stu-id="37364-160">Structured Exception Handling Instead of a Using Block</span></span>

 <span data-ttu-id="37364-161">リソースの取得をより細かく制御する必要がある場合、または `Finally` ブロックに追加のコードが必要な場合は、`Using` ブロックを `Try`...`Finally` の構築として書き換えることができます。</span><span class="sxs-lookup"><span data-stu-id="37364-161">If you need finer control over the acquisition of the resources, or you need additional code in the `Finally` block, you can rewrite the `Using` block as a `Try`...`Finally` construction.</span></span> <span data-ttu-id="37364-162">次の例は、`resource`の取得と破棄に相当するスケルトン `Try` と `Using` の構造を示しています。</span><span class="sxs-lookup"><span data-stu-id="37364-162">The following example shows skeleton `Try` and `Using` constructions that are equivalent in the acquisition and disposal of `resource`.</span></span>

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
> <span data-ttu-id="37364-163">`Using` ブロック内のコードでは、`resourcename` 内のオブジェクトを別の変数に割り当てることはできません。</span><span class="sxs-lookup"><span data-stu-id="37364-163">The code inside the `Using` block should not assign the object in `resourcename` to another variable.</span></span> <span data-ttu-id="37364-164">`Using` ブロックを終了すると、リソースが破棄され、他の変数はそのリソースが指すリソースにアクセスできなくなります。</span><span class="sxs-lookup"><span data-stu-id="37364-164">When you exit the `Using` block, the resource is disposed, and the other variable cannot access the resource to which it points.</span></span>

## <a name="example"></a><span data-ttu-id="37364-165">例</span><span class="sxs-lookup"><span data-stu-id="37364-165">Example</span></span>

 <span data-ttu-id="37364-166">次の例では、test.txt という名前のファイルを作成し、ファイルに2行のテキストを書き込みます。</span><span class="sxs-lookup"><span data-stu-id="37364-166">The following example creates a file that is named log.txt and writes two lines of text to the file.</span></span> <span data-ttu-id="37364-167">この例でも同じファイルが読み取られ、テキスト行が表示されます。</span><span class="sxs-lookup"><span data-stu-id="37364-167">The example also reads that same file and displays the lines of text:</span></span>

 <span data-ttu-id="37364-168"><xref:System.IO.TextWriter> クラスと <xref:System.IO.TextReader> クラスには <xref:System.IDisposable> インターフェイスが実装されているため、コードでは `Using` ステートメントを使用して、書き込み操作と読み取り操作の後でファイルが正しく閉じられるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="37364-168">Because the <xref:System.IO.TextWriter> and <xref:System.IO.TextReader> classes implement the <xref:System.IDisposable> interface, the code can use `Using` statements to ensure that the file is correctly closed after the write and read operations.</span></span>

 [!code-vb[VbVbalrStatements#50](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#50)]

## <a name="see-also"></a><span data-ttu-id="37364-169">参照</span><span class="sxs-lookup"><span data-stu-id="37364-169">See also</span></span>

- <xref:System.IDisposable>
- [<span data-ttu-id="37364-170">Try...Catch...Finally ステートメント</span><span class="sxs-lookup"><span data-stu-id="37364-170">Try...Catch...Finally Statement</span></span>](try-catch-finally-statement.md)
- [<span data-ttu-id="37364-171">方法 : システム リソースを破棄する</span><span class="sxs-lookup"><span data-stu-id="37364-171">How to: Dispose of a System Resource</span></span>](../../programming-guide/language-features/control-flow/how-to-dispose-of-a-system-resource.md)
