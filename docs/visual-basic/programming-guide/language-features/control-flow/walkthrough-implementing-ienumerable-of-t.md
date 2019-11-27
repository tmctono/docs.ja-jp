---
title: IEnumerable の実装
ms.date: 07/31/2018
helpviewer_keywords:
- control flow [Visual Basic]
- enumerable interfaces
- loop structures [Visual Basic], optimizing performance
- control flow [Visual Basic]
ms.assetid: c60d7589-51f2-4463-a2d5-22506bbc1554
ms.openlocfilehash: f40fcf7e0724addc478b261dcd36d09e1d8a751a
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74333688"
---
# <a name="walkthrough-implementing-ienumerableof-t-in-visual-basic"></a><span data-ttu-id="17e9d-102">チュートリアル: Visual Basic での IEnumerable(Of T) の実装</span><span class="sxs-lookup"><span data-stu-id="17e9d-102">Walkthrough: Implementing IEnumerable(Of T) in Visual Basic</span></span>
<span data-ttu-id="17e9d-103"><xref:System.Collections.Generic.IEnumerable%601> インターフェイスは、一度に1つの値のシーケンスを返すことができるクラスによって実装されます。</span><span class="sxs-lookup"><span data-stu-id="17e9d-103">The <xref:System.Collections.Generic.IEnumerable%601> interface is implemented by classes that can return a sequence of values one item at a time.</span></span> <span data-ttu-id="17e9d-104">データを一度に1つずつ返す利点は、データの完全なセットをメモリに読み込んで使用する必要がないことです。</span><span class="sxs-lookup"><span data-stu-id="17e9d-104">The advantage of returning data one item at a time is that you do not have to load the complete set of data into memory to work with it.</span></span> <span data-ttu-id="17e9d-105">データから1つの項目を読み込むには、十分なメモリを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="17e9d-105">You only have to use sufficient memory to load a single item from the data.</span></span> <span data-ttu-id="17e9d-106">`IEnumerable(T)` インターフェイスを実装するクラスは、`For Each` ループまたは LINQ クエリで使用できます。</span><span class="sxs-lookup"><span data-stu-id="17e9d-106">Classes that implement the `IEnumerable(T)` interface can be used with `For Each` loops or LINQ queries.</span></span>  
  
 <span data-ttu-id="17e9d-107">たとえば、大きなテキストファイルを読み取って、特定の検索条件に一致するファイルから各行を返すアプリケーションがあるとします。</span><span class="sxs-lookup"><span data-stu-id="17e9d-107">For example, consider an application that must read a large text file and return each line from the file that matches particular search criteria.</span></span> <span data-ttu-id="17e9d-108">アプリケーションでは、LINQ クエリを使用して、指定した条件に一致する行をファイルから取得します。</span><span class="sxs-lookup"><span data-stu-id="17e9d-108">The application uses a LINQ query to return lines from the file that match the specified criteria.</span></span> <span data-ttu-id="17e9d-109">LINQ クエリを使用してファイルの内容を照会するために、アプリケーションでは、ファイルの内容を配列またはコレクションに読み込むことができます。</span><span class="sxs-lookup"><span data-stu-id="17e9d-109">To query the contents of the file by using a LINQ query, the application could load the contents of the file into an array or a collection.</span></span> <span data-ttu-id="17e9d-110">ただし、ファイル全体を配列またはコレクションに読み込むと、必要以上に多くのメモリが消費されます。</span><span class="sxs-lookup"><span data-stu-id="17e9d-110">However, loading the whole file into an array or collection would consume far more memory than is required.</span></span> <span data-ttu-id="17e9d-111">LINQ クエリでは、列挙可能なクラスを使用してファイルの内容に対してクエリを実行し、検索条件に一致する値のみを返すこともできます。</span><span class="sxs-lookup"><span data-stu-id="17e9d-111">The LINQ query could instead query the file contents by using an enumerable class, returning only values that match the search criteria.</span></span> <span data-ttu-id="17e9d-112">一致する値をいくつか返すクエリでは、使用するメモリがはるかに少なくなります。</span><span class="sxs-lookup"><span data-stu-id="17e9d-112">Queries that return only a few matching values would consume far less memory.</span></span>  
  
 <span data-ttu-id="17e9d-113"><xref:System.Collections.Generic.IEnumerable%601> インターフェイスを実装するクラスを作成して、ソースデータを列挙可能なデータとして公開することができます。</span><span class="sxs-lookup"><span data-stu-id="17e9d-113">You can create a class that implements the <xref:System.Collections.Generic.IEnumerable%601> interface to expose source data as enumerable data.</span></span> <span data-ttu-id="17e9d-114">`IEnumerable(T)` インターフェイスを実装するクラスには、ソースデータを反復処理するために <xref:System.Collections.Generic.IEnumerator%601> インターフェイスを実装する別のクラスが必要です。</span><span class="sxs-lookup"><span data-stu-id="17e9d-114">Your class that implements the `IEnumerable(T)` interface will require another class that implements the <xref:System.Collections.Generic.IEnumerator%601> interface to iterate through the source data.</span></span> <span data-ttu-id="17e9d-115">これらの2つのクラスを使用すると、特定の型としてデータの項目を順番に返すことができます。</span><span class="sxs-lookup"><span data-stu-id="17e9d-115">These two classes enable you to return items of data sequentially as a specific type.</span></span>  
  
 <span data-ttu-id="17e9d-116">このチュートリアルでは、`IEnumerable(Of String)` インターフェイスを実装するクラスと、テキストファイルを一度に1行読み取るための `IEnumerator(Of String)` インターフェイスを実装するクラスを作成します。</span><span class="sxs-lookup"><span data-stu-id="17e9d-116">In this walkthrough, you will create a class that implements the `IEnumerable(Of String)` interface and a class that implements the `IEnumerator(Of String)` interface to read a text file one line at a time.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="creating-the-enumerable-class"></a><span data-ttu-id="17e9d-117">列挙可能なクラスの作成</span><span class="sxs-lookup"><span data-stu-id="17e9d-117">Creating the Enumerable Class</span></span>  
  
<span data-ttu-id="17e9d-118">**列挙可能なクラスプロジェクトを作成する**</span><span class="sxs-lookup"><span data-stu-id="17e9d-118">**Create the enumerable class project**</span></span>

1. <span data-ttu-id="17e9d-119">Visual Basic で、 **[ファイル]** メニューの **[新規作成]** をポイントし、 **[プロジェクト]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="17e9d-119">In Visual Basic, on the **File** menu, point to **New** and then click **Project**.</span></span>

1. <span data-ttu-id="17e9d-120">**[新しいプロジェクト]** ダイアログ ボックスの **[プロジェクトの種類]** ペインで、 **[Windows]** が選択されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="17e9d-120">In the **New Project** dialog box, in the **Project Types** pane, make sure that **Windows** is selected.</span></span> <span data-ttu-id="17e9d-121">**[テンプレート]** ペインで **[クラス ライブラリ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="17e9d-121">Select **Class Library** in the **Templates** pane.</span></span> <span data-ttu-id="17e9d-122">**[名前]** ボックスに `StreamReaderEnumerable` と入力して、 **[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="17e9d-122">In the **Name** box, type `StreamReaderEnumerable`, and then click **OK**.</span></span> <span data-ttu-id="17e9d-123">新しいプロジェクトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="17e9d-123">The new project is displayed.</span></span>

1. <span data-ttu-id="17e9d-124">**ソリューションエクスプローラー**で、Class1 ファイルを右クリックし、[名前の**変更**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="17e9d-124">In **Solution Explorer**, right-click the Class1.vb file and click **Rename**.</span></span> <span data-ttu-id="17e9d-125">ファイルの名前を `StreamReaderEnumerable.vb` に変更し、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="17e9d-125">Rename the file to `StreamReaderEnumerable.vb` and press ENTER.</span></span> <span data-ttu-id="17e9d-126">ファイルの名前を変更すると、クラスの名前も `StreamReaderEnumerable` に変更されます。</span><span class="sxs-lookup"><span data-stu-id="17e9d-126">Renaming the file will also rename the class to `StreamReaderEnumerable`.</span></span> <span data-ttu-id="17e9d-127">このクラスが `IEnumerable(Of String)` インターフェイスを実装します。</span><span class="sxs-lookup"><span data-stu-id="17e9d-127">This class will implement the `IEnumerable(Of String)` interface.</span></span>

1. <span data-ttu-id="17e9d-128">StreamReaderEnumerable プロジェクトを右クリックし、 **[追加]** をポイントして、 **[新しい項目]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="17e9d-128">Right-click the StreamReaderEnumerable project, point to **Add**, and then click **New Item**.</span></span> <span data-ttu-id="17e9d-129">**クラス**テンプレートを選択します。</span><span class="sxs-lookup"><span data-stu-id="17e9d-129">Select the **Class** template.</span></span> <span data-ttu-id="17e9d-130">**[名前]** ボックスに「`StreamReaderEnumerator.vb`」と入力し、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="17e9d-130">In the **Name** box, type `StreamReaderEnumerator.vb` and click **OK**.</span></span>

 <span data-ttu-id="17e9d-131">このプロジェクトの最初のクラスは列挙可能なクラスであり、`IEnumerable(Of String)` インターフェイスを実装します。</span><span class="sxs-lookup"><span data-stu-id="17e9d-131">The first class in this project is the enumerable class and will implement the `IEnumerable(Of String)` interface.</span></span> <span data-ttu-id="17e9d-132">このジェネリックインターフェイスは <xref:System.Collections.IEnumerable> インターフェイスを実装し、このクラスのコンシューマーが `String`として型指定された値にアクセスできることを保証します。</span><span class="sxs-lookup"><span data-stu-id="17e9d-132">This generic interface implements the <xref:System.Collections.IEnumerable> interface and guarantees that consumers of this class can access values typed as `String`.</span></span>  
  
<span data-ttu-id="17e9d-133">**IEnumerable を実装するコードを追加します。**</span><span class="sxs-lookup"><span data-stu-id="17e9d-133">**Add the code to implement IEnumerable**</span></span>

1. <span data-ttu-id="17e9d-134">StreamReaderEnumerable ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="17e9d-134">Open the StreamReaderEnumerable.vb file.</span></span>

2. <span data-ttu-id="17e9d-135">`Public Class StreamReaderEnumerable`の後の行で、次のように入力し、enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="17e9d-135">On the line after `Public Class StreamReaderEnumerable`, type the following and press ENTER.</span></span>

     [!code-vb[VbVbalrIteratorWalkthrough#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/StreamReaderIterator.vb#1)]

   <span data-ttu-id="17e9d-136">Visual Basic は、`IEnumerable(Of String)` インターフェイスに必要なメンバーをクラスに自動的に設定します。</span><span class="sxs-lookup"><span data-stu-id="17e9d-136">Visual Basic automatically populates the class with the members that are required by the `IEnumerable(Of String)` interface.</span></span>
  
3. <span data-ttu-id="17e9d-137">この列挙可能なクラスは、一度に1行ずつテキストファイルから行を読み取ります。</span><span class="sxs-lookup"><span data-stu-id="17e9d-137">This enumerable class will read lines from a text file one line at a time.</span></span> <span data-ttu-id="17e9d-138">次のコードをクラスに追加して、入力パラメーターとしてファイルパスを受け取るパブリックコンストラクターを公開します。</span><span class="sxs-lookup"><span data-stu-id="17e9d-138">Add the following code to the class to expose a public constructor that takes a file path as an input parameter.</span></span>

     [!code-vb[VbVbalrIteratorWalkthrough#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/StreamReaderIterator.vb#2)]

4. <span data-ttu-id="17e9d-139">`IEnumerable(Of String)` インターフェイスの <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A> メソッドを実装すると、`StreamReaderEnumerator` クラスの新しいインスタンスが返されます。</span><span class="sxs-lookup"><span data-stu-id="17e9d-139">Your implementation of the <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A> method of the `IEnumerable(Of String)` interface will return a new instance of the `StreamReaderEnumerator` class.</span></span> <span data-ttu-id="17e9d-140">`IEnumerable(Of String)` インターフェイスのメンバーのみを公開する必要があるため、`IEnumerable` インターフェイスの `GetEnumerator` メソッドの実装は `Private`できます。</span><span class="sxs-lookup"><span data-stu-id="17e9d-140">The implementation of the `GetEnumerator` method of the `IEnumerable` interface can be made `Private`, because you have to expose only members of the `IEnumerable(Of String)` interface.</span></span> <span data-ttu-id="17e9d-141">`GetEnumerator` メソッドに対して生成された Visual Basic コードを次のコードに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="17e9d-141">Replace the code that Visual Basic generated for the `GetEnumerator` methods with the following code.</span></span>

     [!code-vb[VbVbalrIteratorWalkthrough#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/StreamReaderIterator.vb#3)]  
  
<span data-ttu-id="17e9d-142">**IEnumerator を実装するコードを追加する**</span><span class="sxs-lookup"><span data-stu-id="17e9d-142">**Add the code to implement IEnumerator**</span></span>

1. <span data-ttu-id="17e9d-143">StreamReaderEnumerator .vb ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="17e9d-143">Open the StreamReaderEnumerator.vb file.</span></span>

2. <span data-ttu-id="17e9d-144">`Public Class StreamReaderEnumerator`の後の行で、次のように入力し、enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="17e9d-144">On the line after `Public Class StreamReaderEnumerator`, type the following and press ENTER.</span></span>

     [!code-vb[VbVbalrIteratorWalkthrough#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/StreamReaderIterator.vb#4)]

   <span data-ttu-id="17e9d-145">Visual Basic は、`IEnumerator(Of String)` インターフェイスに必要なメンバーをクラスに自動的に設定します。</span><span class="sxs-lookup"><span data-stu-id="17e9d-145">Visual Basic automatically populates the class with the members that are required by the `IEnumerator(Of String)` interface.</span></span>

3. <span data-ttu-id="17e9d-146">列挙子クラスはテキストファイルを開き、ファイルの行を読み取るためにファイル i/o を実行します。</span><span class="sxs-lookup"><span data-stu-id="17e9d-146">The enumerator class opens the text file and performs the file I/O to read the lines from the file.</span></span> <span data-ttu-id="17e9d-147">次のコードをクラスに追加して、ファイルパスを入力パラメーターとして受け取り、テキストファイルを読み取り用に開くパブリックコンストラクターを公開します。</span><span class="sxs-lookup"><span data-stu-id="17e9d-147">Add the following code to the class to expose a public constructor that takes a file path as an input parameter and open the text file for reading.</span></span>

     [!code-vb[VbVbalrIteratorWalkthrough#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/StreamReaderIterator.vb#5)]

4. <span data-ttu-id="17e9d-148">`IEnumerator(Of String)` インターフェイスと `IEnumerator` インターフェイスの両方の `Current` プロパティは、テキストファイルから現在の項目を `String`として返します。</span><span class="sxs-lookup"><span data-stu-id="17e9d-148">The `Current` properties for both the `IEnumerator(Of String)` and `IEnumerator` interfaces return the current item from the text file as a `String`.</span></span> <span data-ttu-id="17e9d-149">`IEnumerator(Of String)` インターフェイスのメンバーのみを公開する必要があるため、`IEnumerator` インターフェイスの `Current` プロパティの実装は `Private`できます。</span><span class="sxs-lookup"><span data-stu-id="17e9d-149">The implementation of the `Current` property of the `IEnumerator` interface can be made `Private`, because you have to expose only members of the `IEnumerator(Of String)` interface.</span></span> <span data-ttu-id="17e9d-150">`Current` のプロパティに対して生成 Visual Basic コードを次のコードに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="17e9d-150">Replace the code that Visual Basic generated for the `Current` properties with the following code.</span></span>

     [!code-vb[VbVbalrIteratorWalkthrough#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/StreamReaderIterator.vb#6)]

5. <span data-ttu-id="17e9d-151">`IEnumerator` インターフェイスの `MoveNext` メソッドは、テキストファイル内の次の項目に移動し、`Current` プロパティによって返される値を更新します。</span><span class="sxs-lookup"><span data-stu-id="17e9d-151">The `MoveNext` method of the `IEnumerator` interface navigates to the next item in the text file and updates the value that is returned by the `Current` property.</span></span> <span data-ttu-id="17e9d-152">読み取る項目がそれ以上ない場合、`MoveNext` メソッドは `False`を返します。それ以外の場合、`MoveNext` メソッドは `True`を返します。</span><span class="sxs-lookup"><span data-stu-id="17e9d-152">If there are no more items to read, the `MoveNext` method returns `False`; otherwise the `MoveNext` method returns `True`.</span></span> <span data-ttu-id="17e9d-153">`MoveNext` メソッドに次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="17e9d-153">Add the following code to the `MoveNext` method.</span></span>

     [!code-vb[VbVbalrIteratorWalkthrough#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/StreamReaderIterator.vb#7)]

6. <span data-ttu-id="17e9d-154">`IEnumerator` インターフェイスの `Reset` メソッドは、テキストファイルの先頭を指すように反復子に指示し、現在の項目の値をクリアします。</span><span class="sxs-lookup"><span data-stu-id="17e9d-154">The `Reset` method of the `IEnumerator` interface directs the iterator to point to the start of the text file and clears the current item value.</span></span> <span data-ttu-id="17e9d-155">`Reset` メソッドに次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="17e9d-155">Add the following code to the `Reset` method.</span></span>

     [!code-vb[VbVbalrIteratorWalkthrough#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/StreamReaderIterator.vb#8)]

7. <span data-ttu-id="17e9d-156">`IEnumerator` インターフェイスの `Dispose` メソッドは、反復子が破棄される前にすべてのアンマネージリソースが解放されることを保証します。</span><span class="sxs-lookup"><span data-stu-id="17e9d-156">The `Dispose` method of the `IEnumerator` interface guarantees that all unmanaged resources are released before the iterator is destroyed.</span></span> <span data-ttu-id="17e9d-157">`StreamReader` オブジェクトによって使用されるファイルハンドルはアンマネージリソースであり、反復子インスタンスが破棄される前に閉じる必要があります。</span><span class="sxs-lookup"><span data-stu-id="17e9d-157">The file handle that is used by the `StreamReader` object is an unmanaged resource and must be closed before the iterator instance is destroyed.</span></span> <span data-ttu-id="17e9d-158">`Dispose` メソッドに対して生成 Visual Basic コードを次のコードに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="17e9d-158">Replace the code that Visual Basic generated for the `Dispose` method with the following code.</span></span>

     [!code-vb[VbVbalrIteratorWalkthrough#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/StreamReaderIterator.vb#9)] 
  
## <a name="using-the-sample-iterator"></a><span data-ttu-id="17e9d-159">サンプル反復子の使用</span><span class="sxs-lookup"><span data-stu-id="17e9d-159">Using the Sample Iterator</span></span>

 <span data-ttu-id="17e9d-160">コード内で列挙可能なクラスを、`For Next` ループや LINQ クエリなどの `IEnumerable`を実装するオブジェクトを必要とする制御構造と共に使用できます。</span><span class="sxs-lookup"><span data-stu-id="17e9d-160">You can use an enumerable class in your code together with control structures that require an object that implements `IEnumerable`, such as a `For Next` loop or a LINQ query.</span></span> <span data-ttu-id="17e9d-161">次の例は、LINQ クエリの `StreamReaderEnumerable` を示しています。</span><span class="sxs-lookup"><span data-stu-id="17e9d-161">The following example shows the `StreamReaderEnumerable` in a LINQ query.</span></span>  
  
 [!code-vb[VbVbalrIteratorWalkthrough#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/Module1.vb#10)]  
  
## <a name="see-also"></a><span data-ttu-id="17e9d-162">参照</span><span class="sxs-lookup"><span data-stu-id="17e9d-162">See also</span></span>

- [<span data-ttu-id="17e9d-163">Visual Basic における LINQ の概要</span><span class="sxs-lookup"><span data-stu-id="17e9d-163">Introduction to LINQ in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="17e9d-164">制御フロー</span><span class="sxs-lookup"><span data-stu-id="17e9d-164">Control Flow</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)
- [<span data-ttu-id="17e9d-165">ループ構造</span><span class="sxs-lookup"><span data-stu-id="17e9d-165">Loop Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [<span data-ttu-id="17e9d-166">For Each...Next ステートメント</span><span class="sxs-lookup"><span data-stu-id="17e9d-166">For Each...Next Statement</span></span>](../../../../visual-basic/language-reference/statements/for-each-next-statement.md)
