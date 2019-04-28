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
ms.openlocfilehash: fe53ea58dc98a4de793fe9dad1c3ceeac71622fc
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61698656"
---
# <a name="using-statement-visual-basic"></a><span data-ttu-id="72402-102">Using ステートメント (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="72402-102">Using Statement (Visual Basic)</span></span>
<span data-ttu-id="72402-103">宣言の先頭を`Using`をブロックし、必要に応じて、ブロックを制御するシステム リソースを取得します。</span><span class="sxs-lookup"><span data-stu-id="72402-103">Declares the beginning of a `Using` block and optionally acquires the system resources that the block controls.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="72402-104">構文</span><span class="sxs-lookup"><span data-stu-id="72402-104">Syntax</span></span>  
  
```  
Using { resourcelist | resourceexpression }  
    [ statements ]  
End Using  
```  
  
## <a name="parts"></a><span data-ttu-id="72402-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="72402-105">Parts</span></span>  
  
|<span data-ttu-id="72402-106">用語</span><span class="sxs-lookup"><span data-stu-id="72402-106">Term</span></span>|<span data-ttu-id="72402-107">定義</span><span class="sxs-lookup"><span data-stu-id="72402-107">Definition</span></span>|  
|---|---|  
|`resourcelist`|<span data-ttu-id="72402-108">指定しないかどうかに必要な`resourceexpression`します。</span><span class="sxs-lookup"><span data-stu-id="72402-108">Required if you do not supply `resourceexpression`.</span></span> <span data-ttu-id="72402-109">この 1 つまたは複数のシステム リソースの一覧表示`Using`コンマで区切られたコントロールをブロックします。</span><span class="sxs-lookup"><span data-stu-id="72402-109">List of one or more system resources that this `Using` block controls, separated by commas.</span></span>|  
|`resourceexpression`|<span data-ttu-id="72402-110">指定しないかどうかに必要な`resourcelist`します。</span><span class="sxs-lookup"><span data-stu-id="72402-110">Required if you do not supply `resourcelist`.</span></span> <span data-ttu-id="72402-111">参照変数または式で制御するシステム リソースを参照する`Using`ブロックします。</span><span class="sxs-lookup"><span data-stu-id="72402-111">Reference variable or expression referring to a system resource to be controlled by this `Using` block.</span></span>|  
|`statements`|<span data-ttu-id="72402-112">省略可能です。</span><span class="sxs-lookup"><span data-stu-id="72402-112">Optional.</span></span> <span data-ttu-id="72402-113">ステートメントのブロックを`Using`ブロックが実行されます。</span><span class="sxs-lookup"><span data-stu-id="72402-113">Block of statements that the `Using` block runs.</span></span>|  
|`End Using`|<span data-ttu-id="72402-114">必須。</span><span class="sxs-lookup"><span data-stu-id="72402-114">Required.</span></span> <span data-ttu-id="72402-115">定義を終了、`Using`ブロックおよびそれによって制御されるすべてのリソースを破棄します。</span><span class="sxs-lookup"><span data-stu-id="72402-115">Terminates the definition of the `Using` block and disposes of all the resources that it controls.</span></span>|  
  
 <span data-ttu-id="72402-116">内の各リソース、`resourcelist`部分が次の構文と部分。</span><span class="sxs-lookup"><span data-stu-id="72402-116">Each resource in the `resourcelist` part has the following syntax and parts:</span></span>  
  
 `resourcename As New resourcetype [ ( [ arglist ] ) ]`  
  
 <span data-ttu-id="72402-117">- または -</span><span class="sxs-lookup"><span data-stu-id="72402-117">-or-</span></span>  
  
 `resourcename As resourcetype = resourceexpression`  
  
## <a name="resourcelist-parts"></a><span data-ttu-id="72402-118">resourcelist パーツ</span><span class="sxs-lookup"><span data-stu-id="72402-118">resourcelist Parts</span></span>  
  
|<span data-ttu-id="72402-119">用語</span><span class="sxs-lookup"><span data-stu-id="72402-119">Term</span></span>|<span data-ttu-id="72402-120">定義</span><span class="sxs-lookup"><span data-stu-id="72402-120">Definition</span></span>|  
|---|---|  
|`resourcename`|<span data-ttu-id="72402-121">必須。</span><span class="sxs-lookup"><span data-stu-id="72402-121">Required.</span></span> <span data-ttu-id="72402-122">システム リソースを参照する参照変数を`Using`コントロールをブロックします。</span><span class="sxs-lookup"><span data-stu-id="72402-122">Reference variable that refers to a system resource that the `Using` block controls.</span></span>|  
|`New`|<span data-ttu-id="72402-123">必要な場合、`Using`ステートメントがリソースを取得します。</span><span class="sxs-lookup"><span data-stu-id="72402-123">Required if the `Using` statement acquires the resource.</span></span> <span data-ttu-id="72402-124">既にリソースを取得する場合は、2 番目の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="72402-124">If you have already acquired the resource, use the second syntax alternative.</span></span>|  
|`resourcetype`|<span data-ttu-id="72402-125">必須。</span><span class="sxs-lookup"><span data-stu-id="72402-125">Required.</span></span> <span data-ttu-id="72402-126">リソースのクラスです。</span><span class="sxs-lookup"><span data-stu-id="72402-126">The class of the resource.</span></span> <span data-ttu-id="72402-127">クラスを実装する必要があります、<xref:System.IDisposable>インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="72402-127">The class must implement the <xref:System.IDisposable> interface.</span></span>|  
|`arglist`|<span data-ttu-id="72402-128">省略可能です。</span><span class="sxs-lookup"><span data-stu-id="72402-128">Optional.</span></span> <span data-ttu-id="72402-129">インスタンスを作成するコンス トラクターに渡す引数のリスト`resourcetype`します。</span><span class="sxs-lookup"><span data-stu-id="72402-129">List of arguments you are passing to the constructor to create an instance of `resourcetype`.</span></span> <span data-ttu-id="72402-130">参照してください[パラメーター リスト](../../../visual-basic/language-reference/statements/parameter-list.md)します。</span><span class="sxs-lookup"><span data-stu-id="72402-130">See [Parameter List](../../../visual-basic/language-reference/statements/parameter-list.md).</span></span>|  
|`resourceexpression`|<span data-ttu-id="72402-131">必須。</span><span class="sxs-lookup"><span data-stu-id="72402-131">Required.</span></span> <span data-ttu-id="72402-132">変数または式の要件を満たすシステム リソースを参照する`resourcetype`します。</span><span class="sxs-lookup"><span data-stu-id="72402-132">Variable or expression referring to a system resource satisfying the requirements of `resourcetype`.</span></span> <span data-ttu-id="72402-133">2 番目の構文を使用する場合は、制御を渡す前に、リソースを取得する必要があります、`Using`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="72402-133">If you use the second syntax alternative, you must acquire the resource before passing control to the `Using` statement.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="72402-134">Remarks</span><span class="sxs-lookup"><span data-stu-id="72402-134">Remarks</span></span>  
 <span data-ttu-id="72402-135">場合によって、コードでは、ファイル ハンドル、COM ラッパーの場合は、SQL 接続など、アンマネージ リソースが必要です。</span><span class="sxs-lookup"><span data-stu-id="72402-135">Sometimes your code requires an unmanaged resource, such as a file handle, a COM wrapper, or a SQL connection.</span></span> <span data-ttu-id="72402-136">A`Using`られて、コードが完了すると、ブロックがそのような 1 つまたは複数のリソースの破棄を保証します。</span><span class="sxs-lookup"><span data-stu-id="72402-136">A `Using` block guarantees the disposal of one or more such resources when your code is finished with them.</span></span> <span data-ttu-id="72402-137">これにより、使用するには、他のコードで使用可能なことです。</span><span class="sxs-lookup"><span data-stu-id="72402-137">This makes them available for other code to use.</span></span>  
  
 <span data-ttu-id="72402-138">マネージ リソースは、ユーザー側で余分なコーディングなし、.NET Framework ガベージ コレクター (GC) によっての破棄されます。</span><span class="sxs-lookup"><span data-stu-id="72402-138">Managed resources are disposed of by the .NET Framework garbage collector (GC) without any extra coding on your part.</span></span> <span data-ttu-id="72402-139">必要はありません、`Using`マネージ リソースをブロックします。</span><span class="sxs-lookup"><span data-stu-id="72402-139">You do not need a `Using` block for managed resources.</span></span> <span data-ttu-id="72402-140">ただし、引き続き使用できます、`Using`強制的にガベージ コレクターを待つのではなくマネージ リソースの破棄をブロックします。</span><span class="sxs-lookup"><span data-stu-id="72402-140">However, you can still use a `Using` block to force the disposal of a managed resource instead of waiting for the garbage collector.</span></span>  
  
 <span data-ttu-id="72402-141">A`Using`ブロックには 3 つの部分: 取得、使用状況、および破棄します。</span><span class="sxs-lookup"><span data-stu-id="72402-141">A `Using` block has three parts: acquisition, usage, and disposal.</span></span>  
  
- <span data-ttu-id="72402-142">*買収*変数を作成して、初期化、システムのリソースを参照することを意味します。</span><span class="sxs-lookup"><span data-stu-id="72402-142">*Acquisition* means creating a variable and initializing it to refer to the system resource.</span></span> <span data-ttu-id="72402-143">`Using`ステートメントが 1 つまたは複数のリソースを取得するか、ブロックに入る前に正確に 1 つのリソースを入手してに提供することができます、`Using`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="72402-143">The `Using` statement can acquire one or more resources, or you can acquire exactly one resource before entering the block and supply it to the `Using` statement.</span></span> <span data-ttu-id="72402-144">指定した場合`resourceexpression`、制御を渡す前に、リソースを取得する必要があります、`Using`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="72402-144">If you supply `resourceexpression`, you must acquire the resource before passing control to the `Using` statement.</span></span>  
  
- <span data-ttu-id="72402-145">*使用状況*リソースにアクセスし、それを使ってアクションを実行することを意味します。</span><span class="sxs-lookup"><span data-stu-id="72402-145">*Usage* means accessing the resources and performing actions with them.</span></span> <span data-ttu-id="72402-146">間にあるステートメント`Using`と`End Using`リソースの使用量を表します。</span><span class="sxs-lookup"><span data-stu-id="72402-146">The statements between `Using` and `End Using` represent the usage of the resources.</span></span>  
  
- <span data-ttu-id="72402-147">*廃棄*を呼び出す方法、<xref:System.IDisposable.Dispose%2A>メソッド内のオブジェクトを`resourcename`します。</span><span class="sxs-lookup"><span data-stu-id="72402-147">*Disposal* means calling the <xref:System.IDisposable.Dispose%2A> method on the object in `resourcename`.</span></span> <span data-ttu-id="72402-148">これにより、そのリソースを正常に終了するオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="72402-148">This allows the object to cleanly terminate its resources.</span></span> <span data-ttu-id="72402-149">`End Using`ステートメントを下にあるリソースの破棄、`Using`ブロックのコントロール。</span><span class="sxs-lookup"><span data-stu-id="72402-149">The `End Using` statement disposes of the resources under the `Using` block's control.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="72402-150">動作</span><span class="sxs-lookup"><span data-stu-id="72402-150">Behavior</span></span>  
 <span data-ttu-id="72402-151">A`Using`ブロックのように動作する`Try`.`Finally`を構築、`Try`ブロックはリソースを使用し、`Finally`それらのブロックを破棄します。</span><span class="sxs-lookup"><span data-stu-id="72402-151">A `Using` block behaves like a `Try`...`Finally` construction in which the `Try` block uses the resources and the `Finally` block disposes of them.</span></span> <span data-ttu-id="72402-152">このため、`Using`ブロックがブロックを終了する方法に関係なく、リソースの破棄を保証します。</span><span class="sxs-lookup"><span data-stu-id="72402-152">Because of this, the `Using` block guarantees disposal of the resources, no matter how you exit the block.</span></span> <span data-ttu-id="72402-153">これは、未処理の例外の場合にも当てはまりますを除き、<xref:System.StackOverflowException>します。</span><span class="sxs-lookup"><span data-stu-id="72402-153">This is true even in the case of an unhandled exception, except for a <xref:System.StackOverflowException>.</span></span>  
  
 <span data-ttu-id="72402-154">によって取得されたすべてのリソース変数のスコープ、`Using`ステートメントに制限されていますが、`Using`ブロックします。</span><span class="sxs-lookup"><span data-stu-id="72402-154">The scope of every resource variable acquired by the `Using` statement is limited to the `Using` block.</span></span>  
  
 <span data-ttu-id="72402-155">1 つ以上のシステム リソースを指定する場合、`Using`を入れ子にする場合と同じステートメントでは、効果は`Using`互いをブロックします。</span><span class="sxs-lookup"><span data-stu-id="72402-155">If you specify more than one system resource in the `Using` statement, the effect is the same as if you nested `Using` blocks one within another.</span></span>  
  
 <span data-ttu-id="72402-156">場合`resourcename`は`Nothing`への呼び出しがない<xref:System.IDisposable.Dispose%2A>が行われると例外はスローされません。</span><span class="sxs-lookup"><span data-stu-id="72402-156">If `resourcename` is `Nothing`, no call to <xref:System.IDisposable.Dispose%2A> is made, and no exception is thrown.</span></span>  
  
## <a name="structured-exception-handling-within-a-using-block"></a><span data-ttu-id="72402-157">構造化例外処理を使用してブロック内で</span><span class="sxs-lookup"><span data-stu-id="72402-157">Structured Exception Handling Within a Using Block</span></span>  
 <span data-ttu-id="72402-158">内で発生する例外を処理する必要があるかどうか、`Using`ブロック、完全なを追加する`Try`.`Finally`を構築します。</span><span class="sxs-lookup"><span data-stu-id="72402-158">If you need to handle an exception that might occur within the `Using` block, you can add a complete `Try`...`Finally` construction to it.</span></span> <span data-ttu-id="72402-159">ケースを処理する必要がある場合で、`Using`ステートメントがリソースの取得中に失敗した、かどうかをテストできます`resourcename`は`Nothing`します。</span><span class="sxs-lookup"><span data-stu-id="72402-159">If you need to handle the case where the `Using` statement is not successful in acquiring a resource, you can test to see if `resourcename` is `Nothing`.</span></span>  
  
## <a name="structured-exception-handling-instead-of-a-using-block"></a><span data-ttu-id="72402-160">構造化例外処理を使用してブロックではなく</span><span class="sxs-lookup"><span data-stu-id="72402-160">Structured Exception Handling Instead of a Using Block</span></span>  
 <span data-ttu-id="72402-161">場合は、リソースの取得をより細かく制御する必要がありますまたはでコードを追加する必要があります、`Finally`ブロック、書き直すことができます、`Using`としてブロック、 `Try`.`Finally`構築します。</span><span class="sxs-lookup"><span data-stu-id="72402-161">If you need finer control over the acquisition of the resources, or you need additional code in the `Finally` block, you can rewrite the `Using` block as a `Try`...`Finally` construction.</span></span> <span data-ttu-id="72402-162">次の例では、スケルトン`Try`と`Using`の取得と破棄に相当する構造`resource`します。</span><span class="sxs-lookup"><span data-stu-id="72402-162">The following example shows skeleton `Try` and `Using` constructions that are equivalent in the acquisition and disposal of `resource`.</span></span>  
  
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
>  <span data-ttu-id="72402-163">内のコード、`Using`ブロック内のオブジェクトを割り当てないでください`resourcename`別の変数にします。</span><span class="sxs-lookup"><span data-stu-id="72402-163">The code inside the `Using` block should not assign the object in `resourcename` to another variable.</span></span> <span data-ttu-id="72402-164">終了すると、`Using`ブロック、リソースが破棄され、その他の変数が指すリソースにアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="72402-164">When you exit the `Using` block, the resource is disposed, and the other variable cannot access the resource to which it points.</span></span>  
  
## <a name="example"></a><span data-ttu-id="72402-165">例</span><span class="sxs-lookup"><span data-stu-id="72402-165">Example</span></span>  
 <span data-ttu-id="72402-166">次の例では、log.txt という名前をファイルに 2 つの行のテキストを書き込むファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="72402-166">The following example creates a file that is named log.txt and writes two lines of text to the file.</span></span> <span data-ttu-id="72402-167">例では、同じファイルを読み取るし、行のテキストが表示されます。</span><span class="sxs-lookup"><span data-stu-id="72402-167">The example also reads that same file and displays the lines of text.</span></span>  
  
 <span data-ttu-id="72402-168"><xref:System.IO.TextWriter>と<xref:System.IO.TextReader>クラスの実装、<xref:System.IDisposable>インターフェイス、コードで使用できる`Using`ステートメントをファイルが正しく、書き込み後に終了し、読み取り操作ことを確認します。</span><span class="sxs-lookup"><span data-stu-id="72402-168">Because the <xref:System.IO.TextWriter> and <xref:System.IO.TextReader> classes implement the <xref:System.IDisposable> interface, the code can use `Using` statements to ensure that the file is correctly closed after the write and read operations.</span></span>  
  
 [!code-vb[VbVbalrStatements#50](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#50)]  
  
## <a name="see-also"></a><span data-ttu-id="72402-169">関連項目</span><span class="sxs-lookup"><span data-stu-id="72402-169">See also</span></span>

- <xref:System.IDisposable>
- [<span data-ttu-id="72402-170">Try...Catch...Finally ステートメント</span><span class="sxs-lookup"><span data-stu-id="72402-170">Try...Catch...Finally Statement</span></span>](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
- [<span data-ttu-id="72402-171">方法: システム リソースを破棄します。</span><span class="sxs-lookup"><span data-stu-id="72402-171">How to: Dispose of a System Resource</span></span>](../../../visual-basic/programming-guide/language-features/control-flow/how-to-dispose-of-a-system-resource.md)
