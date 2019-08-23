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
ms.openlocfilehash: 346a26ad5751599831d8b0d3e0497e4d488eb76c
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69957545"
---
# <a name="using-statement-visual-basic"></a><span data-ttu-id="2b741-102">Using ステートメント (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2b741-102">Using Statement (Visual Basic)</span></span>
<span data-ttu-id="2b741-103">`Using`ブロックの先頭を宣言し、必要に応じて、ブロックが制御するシステムリソースを取得します。</span><span class="sxs-lookup"><span data-stu-id="2b741-103">Declares the beginning of a `Using` block and optionally acquires the system resources that the block controls.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2b741-104">構文</span><span class="sxs-lookup"><span data-stu-id="2b741-104">Syntax</span></span>  
  
```  
Using { resourcelist | resourceexpression }  
    [ statements ]  
End Using  
```  
  
## <a name="parts"></a><span data-ttu-id="2b741-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="2b741-105">Parts</span></span>  
  
|<span data-ttu-id="2b741-106">用語</span><span class="sxs-lookup"><span data-stu-id="2b741-106">Term</span></span>|<span data-ttu-id="2b741-107">定義</span><span class="sxs-lookup"><span data-stu-id="2b741-107">Definition</span></span>|  
|---|---|  
|`resourcelist`|<span data-ttu-id="2b741-108">を指定`resourceexpression`しない場合は必須です。</span><span class="sxs-lookup"><span data-stu-id="2b741-108">Required if you do not supply `resourceexpression`.</span></span> <span data-ttu-id="2b741-109">この`Using`ブロックで制御される1つ以上のシステムリソースのリストをコンマで区切ります。</span><span class="sxs-lookup"><span data-stu-id="2b741-109">List of one or more system resources that this `Using` block controls, separated by commas.</span></span>|  
|`resourceexpression`|<span data-ttu-id="2b741-110">を指定`resourcelist`しない場合は必須です。</span><span class="sxs-lookup"><span data-stu-id="2b741-110">Required if you do not supply `resourcelist`.</span></span> <span data-ttu-id="2b741-111">この`Using`ブロックによって制御されるシステムリソースを参照する、参照変数または式。</span><span class="sxs-lookup"><span data-stu-id="2b741-111">Reference variable or expression referring to a system resource to be controlled by this `Using` block.</span></span>|  
|`statements`|<span data-ttu-id="2b741-112">省略可能です。</span><span class="sxs-lookup"><span data-stu-id="2b741-112">Optional.</span></span> <span data-ttu-id="2b741-113">`Using`ブロックによって実行されるステートメントのブロック。</span><span class="sxs-lookup"><span data-stu-id="2b741-113">Block of statements that the `Using` block runs.</span></span>|  
|`End Using`|<span data-ttu-id="2b741-114">必須。</span><span class="sxs-lookup"><span data-stu-id="2b741-114">Required.</span></span> <span data-ttu-id="2b741-115">`Using`ブロックの定義を終了し、制御しているすべてのリソースを破棄します。</span><span class="sxs-lookup"><span data-stu-id="2b741-115">Terminates the definition of the `Using` block and disposes of all the resources that it controls.</span></span>|  
  
 <span data-ttu-id="2b741-116">`resourcelist`パートの各リソースには、次の構文と部分があります。</span><span class="sxs-lookup"><span data-stu-id="2b741-116">Each resource in the `resourcelist` part has the following syntax and parts:</span></span>  
  
 `resourcename As New resourcetype [ ( [ arglist ] ) ]`  
  
 <span data-ttu-id="2b741-117">\- または -</span><span class="sxs-lookup"><span data-stu-id="2b741-117">-or-</span></span>  
  
 `resourcename As resourcetype = resourceexpression`  
  
## <a name="resourcelist-parts"></a><span data-ttu-id="2b741-118">resourcelist パーツ</span><span class="sxs-lookup"><span data-stu-id="2b741-118">resourcelist Parts</span></span>  
  
|<span data-ttu-id="2b741-119">用語</span><span class="sxs-lookup"><span data-stu-id="2b741-119">Term</span></span>|<span data-ttu-id="2b741-120">定義</span><span class="sxs-lookup"><span data-stu-id="2b741-120">Definition</span></span>|  
|---|---|  
|`resourcename`|<span data-ttu-id="2b741-121">必須。</span><span class="sxs-lookup"><span data-stu-id="2b741-121">Required.</span></span> <span data-ttu-id="2b741-122">`Using`ブロックが制御するシステムリソースを参照する参照変数。</span><span class="sxs-lookup"><span data-stu-id="2b741-122">Reference variable that refers to a system resource that the `Using` block controls.</span></span>|  
|`New`|<span data-ttu-id="2b741-123">ステートメントがリソース`Using`を取得する場合は必須です。</span><span class="sxs-lookup"><span data-stu-id="2b741-123">Required if the `Using` statement acquires the resource.</span></span> <span data-ttu-id="2b741-124">リソースを既に取得している場合は、2番目の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="2b741-124">If you have already acquired the resource, use the second syntax alternative.</span></span>|  
|`resourcetype`|<span data-ttu-id="2b741-125">必須。</span><span class="sxs-lookup"><span data-stu-id="2b741-125">Required.</span></span> <span data-ttu-id="2b741-126">リソースのクラス。</span><span class="sxs-lookup"><span data-stu-id="2b741-126">The class of the resource.</span></span> <span data-ttu-id="2b741-127">クラスは、インターフェイスを<xref:System.IDisposable>実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2b741-127">The class must implement the <xref:System.IDisposable> interface.</span></span>|  
|`arglist`|<span data-ttu-id="2b741-128">省略可能です。</span><span class="sxs-lookup"><span data-stu-id="2b741-128">Optional.</span></span> <span data-ttu-id="2b741-129">インスタンスを作成するコンストラクターに渡す引数のリスト`resourcetype`。</span><span class="sxs-lookup"><span data-stu-id="2b741-129">List of arguments you are passing to the constructor to create an instance of `resourcetype`.</span></span> <span data-ttu-id="2b741-130">「[パラメーターリスト](../../../visual-basic/language-reference/statements/parameter-list.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2b741-130">See [Parameter List](../../../visual-basic/language-reference/statements/parameter-list.md).</span></span>|  
|`resourceexpression`|<span data-ttu-id="2b741-131">必須。</span><span class="sxs-lookup"><span data-stu-id="2b741-131">Required.</span></span> <span data-ttu-id="2b741-132">の`resourcetype`要件を満たすシステムリソースを参照する変数または式。</span><span class="sxs-lookup"><span data-stu-id="2b741-132">Variable or expression referring to a system resource satisfying the requirements of `resourcetype`.</span></span> <span data-ttu-id="2b741-133">2番目の構文を使用する場合は、 `Using`ステートメントに制御を渡す前にリソースを取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2b741-133">If you use the second syntax alternative, you must acquire the resource before passing control to the `Using` statement.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2b741-134">Remarks</span><span class="sxs-lookup"><span data-stu-id="2b741-134">Remarks</span></span>  
 <span data-ttu-id="2b741-135">コードには、ファイルハンドル、COM ラッパー、SQL 接続などのアンマネージリソースが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="2b741-135">Sometimes your code requires an unmanaged resource, such as a file handle, a COM wrapper, or a SQL connection.</span></span> <span data-ttu-id="2b741-136">ブロック`Using`は、コードが終了したときに、そのようなリソースの破棄を保証します。</span><span class="sxs-lookup"><span data-stu-id="2b741-136">A `Using` block guarantees the disposal of one or more such resources when your code is finished with them.</span></span> <span data-ttu-id="2b741-137">これにより、他のコードで使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="2b741-137">This makes them available for other code to use.</span></span>  
  
 <span data-ttu-id="2b741-138">マネージリソースは、.NET Framework ガベージコレクター (GC) によって破棄されます。その際、追加のコーディングは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="2b741-138">Managed resources are disposed of by the .NET Framework garbage collector (GC) without any extra coding on your part.</span></span> <span data-ttu-id="2b741-139">マネージリソースのための`Using`ブロックは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="2b741-139">You do not need a `Using` block for managed resources.</span></span> <span data-ttu-id="2b741-140">ただし、ブロックを`Using`使用して、ガベージコレクターを待機するのではなく、マネージリソースを強制的に破棄することもできます。</span><span class="sxs-lookup"><span data-stu-id="2b741-140">However, you can still use a `Using` block to force the disposal of a managed resource instead of waiting for the garbage collector.</span></span>  
  
 <span data-ttu-id="2b741-141">ブロック`Using`には、取得、使用、および破棄という3つの部分があります。</span><span class="sxs-lookup"><span data-stu-id="2b741-141">A `Using` block has three parts: acquisition, usage, and disposal.</span></span>  
  
- <span data-ttu-id="2b741-142">*取得*とは、変数を作成して初期化し、システムリソースを参照することを意味します。</span><span class="sxs-lookup"><span data-stu-id="2b741-142">*Acquisition* means creating a variable and initializing it to refer to the system resource.</span></span> <span data-ttu-id="2b741-143">ステートメント`Using`では、1つまたは複数のリソースを取得できます。また、ブロックに入る前に1つ`Using`のリソースだけを取得して、ステートメントに指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="2b741-143">The `Using` statement can acquire one or more resources, or you can acquire exactly one resource before entering the block and supply it to the `Using` statement.</span></span> <span data-ttu-id="2b741-144">を指定`resourceexpression`する場合は、 `Using`ステートメントに制御を渡す前にリソースを取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2b741-144">If you supply `resourceexpression`, you must acquire the resource before passing control to the `Using` statement.</span></span>  
  
- <span data-ttu-id="2b741-145">*使用状況*とは、リソースにアクセスし、それらのリソースでアクションを実行することを意味します。</span><span class="sxs-lookup"><span data-stu-id="2b741-145">*Usage* means accessing the resources and performing actions with them.</span></span> <span data-ttu-id="2b741-146">`Using` と`End Using`の間のステートメントは、リソースの使用状況を表します。</span><span class="sxs-lookup"><span data-stu-id="2b741-146">The statements between `Using` and `End Using` represent the usage of the resources.</span></span>  
  
- <span data-ttu-id="2b741-147">*破棄*とは、 <xref:System.IDisposable.Dispose%2A>で`resourcename`オブジェクトに対してメソッドを呼び出すことを意味します。</span><span class="sxs-lookup"><span data-stu-id="2b741-147">*Disposal* means calling the <xref:System.IDisposable.Dispose%2A> method on the object in `resourcename`.</span></span> <span data-ttu-id="2b741-148">これにより、オブジェクトはリソースを完全に終了できます。</span><span class="sxs-lookup"><span data-stu-id="2b741-148">This allows the object to cleanly terminate its resources.</span></span> <span data-ttu-id="2b741-149">ステートメント`End Using`は、 `Using`ブロックのコントロールの下にあるリソースを破棄します。</span><span class="sxs-lookup"><span data-stu-id="2b741-149">The `End Using` statement disposes of the resources under the `Using` block's control.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="2b741-150">動作</span><span class="sxs-lookup"><span data-stu-id="2b741-150">Behavior</span></span>  
 <span data-ttu-id="2b741-151">ブロック`Using`は次のよう`Try`に動作します...ブロックがリソースを使用し、ブロックが`Finally`それらを破棄する構築。 `Finally` `Try`</span><span class="sxs-lookup"><span data-stu-id="2b741-151">A `Using` block behaves like a `Try`...`Finally` construction in which the `Try` block uses the resources and the `Finally` block disposes of them.</span></span> <span data-ttu-id="2b741-152">このため、ブロックを`Using`終了する方法に関係なく、ブロックはリソースの破棄を保証します。</span><span class="sxs-lookup"><span data-stu-id="2b741-152">Because of this, the `Using` block guarantees disposal of the resources, no matter how you exit the block.</span></span> <span data-ttu-id="2b741-153">これは、を除き<xref:System.StackOverflowException>、ハンドルされない例外が発生した場合にも当てはまります。</span><span class="sxs-lookup"><span data-stu-id="2b741-153">This is true even in the case of an unhandled exception, except for a <xref:System.StackOverflowException>.</span></span>  
  
 <span data-ttu-id="2b741-154">`Using`ステートメントによって取得されるすべてのリソース変数のスコープは`Using` 、ブロックに制限されます。</span><span class="sxs-lookup"><span data-stu-id="2b741-154">The scope of every resource variable acquired by the `Using` statement is limited to the `Using` block.</span></span>  
  
 <span data-ttu-id="2b741-155">`Using`ステートメントで複数のシステムリソースを指定した場合、その効果は、入れ子になったブロックを別のブロック内に入れ子`Using`にした場合と同じになります。</span><span class="sxs-lookup"><span data-stu-id="2b741-155">If you specify more than one system resource in the `Using` statement, the effect is the same as if you nested `Using` blocks one within another.</span></span>  
  
 <span data-ttu-id="2b741-156">が`resourcename` <xref:System.IDisposable.Dispose%2A>の場合、への呼び出しは行われず、例外はスローされません。 `Nothing`</span><span class="sxs-lookup"><span data-stu-id="2b741-156">If `resourcename` is `Nothing`, no call to <xref:System.IDisposable.Dispose%2A> is made, and no exception is thrown.</span></span>  
  
## <a name="structured-exception-handling-within-a-using-block"></a><span data-ttu-id="2b741-157">Using ブロック内での構造化例外処理</span><span class="sxs-lookup"><span data-stu-id="2b741-157">Structured Exception Handling Within a Using Block</span></span>  
 <span data-ttu-id="2b741-158">`Using`ブロック内で発生する可能性のある例外を処理する必要がある場合は、完全`Try`な...`Finally`構築します。</span><span class="sxs-lookup"><span data-stu-id="2b741-158">If you need to handle an exception that might occur within the `Using` block, you can add a complete `Try`...`Finally` construction to it.</span></span> <span data-ttu-id="2b741-159">`Using`ステートメントがリソースの取得に失敗した場合に対処する必要がある場合は、が`Nothing`かどうか`resourcename`をテストして確認できます。</span><span class="sxs-lookup"><span data-stu-id="2b741-159">If you need to handle the case where the `Using` statement is not successful in acquiring a resource, you can test to see if `resourcename` is `Nothing`.</span></span>  
  
## <a name="structured-exception-handling-instead-of-a-using-block"></a><span data-ttu-id="2b741-160">Using ブロックの代わりに構造化例外処理</span><span class="sxs-lookup"><span data-stu-id="2b741-160">Structured Exception Handling Instead of a Using Block</span></span>  
 <span data-ttu-id="2b741-161">リソースの取得をより細かく制御する必要がある場合、または`Finally`ブロック`Using`に追加のコードが必要な場合は、ブロック`Try`を...`Finally`構築。</span><span class="sxs-lookup"><span data-stu-id="2b741-161">If you need finer control over the acquisition of the resources, or you need additional code in the `Finally` block, you can rewrite the `Using` block as a `Try`...`Finally` construction.</span></span> <span data-ttu-id="2b741-162">次の例は、 `Try`の`Using` `resource`取得および破棄に相当するスケルトンと構造を示しています。</span><span class="sxs-lookup"><span data-stu-id="2b741-162">The following example shows skeleton `Try` and `Using` constructions that are equivalent in the acquisition and disposal of `resource`.</span></span>  
  
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
> <span data-ttu-id="2b741-163">`Using`ブロック内のコードで`resourcename`は、オブジェクトを別の変数に割り当てることはできません。</span><span class="sxs-lookup"><span data-stu-id="2b741-163">The code inside the `Using` block should not assign the object in `resourcename` to another variable.</span></span> <span data-ttu-id="2b741-164">`Using`ブロックを終了すると、リソースが破棄され、もう一方の変数は、それが指しているリソースにアクセスできなくなります。</span><span class="sxs-lookup"><span data-stu-id="2b741-164">When you exit the `Using` block, the resource is disposed, and the other variable cannot access the resource to which it points.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2b741-165">例</span><span class="sxs-lookup"><span data-stu-id="2b741-165">Example</span></span>  
 <span data-ttu-id="2b741-166">次の例では、test.txt という名前のファイルを作成し、ファイルに2行のテキストを書き込みます。</span><span class="sxs-lookup"><span data-stu-id="2b741-166">The following example creates a file that is named log.txt and writes two lines of text to the file.</span></span> <span data-ttu-id="2b741-167">また、同じファイルを読み取り、テキストの行を表示します。</span><span class="sxs-lookup"><span data-stu-id="2b741-167">The example also reads that same file and displays the lines of text.</span></span>  
  
 <span data-ttu-id="2b741-168">クラスと<xref:System.IO.TextWriter> <xref:System.IO.TextReader>クラスは<xref:System.IDisposable>インターフェイスを実装するため、コードで`Using`ステートメントを使用して、書き込み操作と読み取り操作の後でファイルが正しく閉じられるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="2b741-168">Because the <xref:System.IO.TextWriter> and <xref:System.IO.TextReader> classes implement the <xref:System.IDisposable> interface, the code can use `Using` statements to ensure that the file is correctly closed after the write and read operations.</span></span>  
  
 [!code-vb[VbVbalrStatements#50](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#50)]  
  
## <a name="see-also"></a><span data-ttu-id="2b741-169">関連項目</span><span class="sxs-lookup"><span data-stu-id="2b741-169">See also</span></span>

- <xref:System.IDisposable>
- [<span data-ttu-id="2b741-170">Try...Catch...Finally ステートメント</span><span class="sxs-lookup"><span data-stu-id="2b741-170">Try...Catch...Finally Statement</span></span>](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
- [<span data-ttu-id="2b741-171">方法: システムリソースの破棄</span><span class="sxs-lookup"><span data-stu-id="2b741-171">How to: Dispose of a System Resource</span></span>](../../../visual-basic/programming-guide/language-features/control-flow/how-to-dispose-of-a-system-resource.md)
