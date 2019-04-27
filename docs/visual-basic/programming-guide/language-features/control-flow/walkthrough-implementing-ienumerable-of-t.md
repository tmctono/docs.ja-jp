---
title: Visual Basic での IEnumerable を実装します。
ms.date: 07/31/2018
helpviewer_keywords:
- control flow [Visual Basic]
- enumerable interfaces
- loop structures [Visual Basic], optimizing performance
- control flow [Visual Basic]
ms.assetid: c60d7589-51f2-4463-a2d5-22506bbc1554
ms.openlocfilehash: b13fd85ae01fd0b6f3c963d87a372add930be99d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61975300"
---
# <a name="walkthrough-implementing-ienumerableof-t-in-visual-basic"></a><span data-ttu-id="6a632-102">チュートリアル: Visual Basic で IEnumerable(Of T) を実装します。</span><span class="sxs-lookup"><span data-stu-id="6a632-102">Walkthrough: Implementing IEnumerable(Of T) in Visual Basic</span></span>
<span data-ttu-id="6a632-103"><xref:System.Collections.Generic.IEnumerable%601>インターフェイスは、一度に 1 つの項目の値のシーケンスを返すことができるクラスによって実装されます。</span><span class="sxs-lookup"><span data-stu-id="6a632-103">The <xref:System.Collections.Generic.IEnumerable%601> interface is implemented by classes that can return a sequence of values one item at a time.</span></span> <span data-ttu-id="6a632-104">一度に 1 つの項目がメモリに読み込むデータの完全なセットを扱うことがないことをデータを返すことの利点です。</span><span class="sxs-lookup"><span data-stu-id="6a632-104">The advantage of returning data one item at a time is that you do not have to load the complete set of data into memory to work with it.</span></span> <span data-ttu-id="6a632-105">のみ、データから 1 つの項目を読み込むに十分なメモリを使用する必要があるとします。</span><span class="sxs-lookup"><span data-stu-id="6a632-105">You only have to use sufficient memory to load a single item from the data.</span></span> <span data-ttu-id="6a632-106">実装するクラス、`IEnumerable(T)`インターフェイスで使用できる`For Each`ループまたは LINQ クエリ。</span><span class="sxs-lookup"><span data-stu-id="6a632-106">Classes that implement the `IEnumerable(T)` interface can be used with `For Each` loops or LINQ queries.</span></span>  
  
 <span data-ttu-id="6a632-107">たとえば、大きなテキスト ファイルを読み取るし、特定の検索条件に一致するファイルからそれぞれの行を返す必要がありますアプリケーションがあるとします。</span><span class="sxs-lookup"><span data-stu-id="6a632-107">For example, consider an application that must read a large text file and return each line from the file that matches particular search criteria.</span></span> <span data-ttu-id="6a632-108">アプリケーションでは、LINQ クエリを使用して、指定した条件に一致するファイルから行を返します。</span><span class="sxs-lookup"><span data-stu-id="6a632-108">The application uses a LINQ query to return lines from the file that match the specified criteria.</span></span> <span data-ttu-id="6a632-109">LINQ クエリを使用して、ファイルの内容を照会するには、アプリケーションは、配列またはコレクションに、ファイルの内容を読み込む可能性があります。</span><span class="sxs-lookup"><span data-stu-id="6a632-109">To query the contents of the file by using a LINQ query, the application could load the contents of the file into an array or a collection.</span></span> <span data-ttu-id="6a632-110">ただし、配列またはコレクションにファイル全体を読み込むには、必要なよりはるかに多くのメモリが消費します。</span><span class="sxs-lookup"><span data-stu-id="6a632-110">However, loading the whole file into an array or collection would consume far more memory than is required.</span></span> <span data-ttu-id="6a632-111">LINQ クエリは、検索条件に一致する値のみを返す、列挙可能なクラスを使用して、ファイルの内容を代わりにクエリでした。</span><span class="sxs-lookup"><span data-stu-id="6a632-111">The LINQ query could instead query the file contents by using an enumerable class, returning only values that match the search criteria.</span></span> <span data-ttu-id="6a632-112">いくつかのみを返すクエリを一致する値ははるかに少ないメモリを消費します。</span><span class="sxs-lookup"><span data-stu-id="6a632-112">Queries that return only a few matching values would consume far less memory.</span></span>  
  
 <span data-ttu-id="6a632-113">実装するクラスを作成することができます、<xref:System.Collections.Generic.IEnumerable%601>として列挙可能なデータ ソースのデータを公開するインターフェイス。</span><span class="sxs-lookup"><span data-stu-id="6a632-113">You can create a class that implements the <xref:System.Collections.Generic.IEnumerable%601> interface to expose source data as enumerable data.</span></span> <span data-ttu-id="6a632-114">実装するクラス、`IEnumerable(T)`インターフェイスを実装する別のクラスが必要になります、<xref:System.Collections.Generic.IEnumerator%601>ソース データを反復処理するインターフェイス。</span><span class="sxs-lookup"><span data-stu-id="6a632-114">Your class that implements the `IEnumerable(T)` interface will require another class that implements the <xref:System.Collections.Generic.IEnumerator%601> interface to iterate through the source data.</span></span> <span data-ttu-id="6a632-115">これら 2 つのクラスを使用すると、順番には、特定の種類のデータ項目を返すことができます。</span><span class="sxs-lookup"><span data-stu-id="6a632-115">These two classes enable you to return items of data sequentially as a specific type.</span></span>  
  
 <span data-ttu-id="6a632-116">このチュートリアルでは、実装するクラスを作成します、`IEnumerable(Of String)`インターフェイスと実装するクラス、`IEnumerator(Of String)`を一度に 1 行ずつテキスト ファイルを読み取るインターフェイス。</span><span class="sxs-lookup"><span data-stu-id="6a632-116">In this walkthrough, you will create a class that implements the `IEnumerable(Of String)` interface and a class that implements the `IEnumerator(Of String)` interface to read a text file one line at a time.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="creating-the-enumerable-class"></a><span data-ttu-id="6a632-117">列挙可能なクラスを作成します。</span><span class="sxs-lookup"><span data-stu-id="6a632-117">Creating the Enumerable Class</span></span>  
  
<span data-ttu-id="6a632-118">**クラスの列挙可能なプロジェクトを作成します。**</span><span class="sxs-lookup"><span data-stu-id="6a632-118">**Create the enumerable class project**</span></span>

1. <span data-ttu-id="6a632-119">Visual basic での**ファイル**メニューで、**新規**順にクリックします**プロジェクト**します。</span><span class="sxs-lookup"><span data-stu-id="6a632-119">In Visual Basic, on the **File** menu, point to **New** and then click **Project**.</span></span>

1. <span data-ttu-id="6a632-120">**[新しいプロジェクト]** ダイアログ ボックスの **[プロジェクトの種類]** ペインで、**[Windows]** が選択されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="6a632-120">In the **New Project** dialog box, in the **Project Types** pane, make sure that **Windows** is selected.</span></span> <span data-ttu-id="6a632-121">**[テンプレート]** ペインで **[クラス ライブラリ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="6a632-121">Select **Class Library** in the **Templates** pane.</span></span> <span data-ttu-id="6a632-122">**[名前]** ボックスに `StreamReaderEnumerable` と入力して、**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6a632-122">In the **Name** box, type `StreamReaderEnumerable`, and then click **OK**.</span></span> <span data-ttu-id="6a632-123">新しいプロジェクトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6a632-123">The new project is displayed.</span></span>

1. <span data-ttu-id="6a632-124">**ソリューション エクスプ ローラー**Class1.vb ファイルを右クリックし、クリックして、**の名前を変更**します。</span><span class="sxs-lookup"><span data-stu-id="6a632-124">In **Solution Explorer**, right-click the Class1.vb file and click **Rename**.</span></span> <span data-ttu-id="6a632-125">ファイルの名前を `StreamReaderEnumerable.vb` に変更し、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="6a632-125">Rename the file to `StreamReaderEnumerable.vb` and press ENTER.</span></span> <span data-ttu-id="6a632-126">ファイルの名前を変更すると、クラスの名前も `StreamReaderEnumerable` に変更されます。</span><span class="sxs-lookup"><span data-stu-id="6a632-126">Renaming the file will also rename the class to `StreamReaderEnumerable`.</span></span> <span data-ttu-id="6a632-127">このクラスが `IEnumerable(Of String)` インターフェイスを実装します。</span><span class="sxs-lookup"><span data-stu-id="6a632-127">This class will implement the `IEnumerable(Of String)` interface.</span></span>

1. <span data-ttu-id="6a632-128">StreamReaderEnumerable プロジェクトを右クリックし、[**追加**、] をクリックし、**新しい項目の**します。</span><span class="sxs-lookup"><span data-stu-id="6a632-128">Right-click the StreamReaderEnumerable project, point to **Add**, and then click **New Item**.</span></span> <span data-ttu-id="6a632-129">選択、**クラス**テンプレート。</span><span class="sxs-lookup"><span data-stu-id="6a632-129">Select the **Class** template.</span></span> <span data-ttu-id="6a632-130">**名前**ボックスに「 `StreamReaderEnumerator.vb`  をクリック**OK**します。</span><span class="sxs-lookup"><span data-stu-id="6a632-130">In the **Name** box, type `StreamReaderEnumerator.vb` and click **OK**.</span></span>

 <span data-ttu-id="6a632-131">このプロジェクトの最初のクラスは列挙可能なクラスであり、実装、`IEnumerable(Of String)`インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="6a632-131">The first class in this project is the enumerable class and will implement the `IEnumerable(Of String)` interface.</span></span> <span data-ttu-id="6a632-132">このジェネリック インターフェイスを実装して、<xref:System.Collections.IEnumerable>インターフェイスと、このクラスのコンシューマーとして型指定された値にアクセスできることの保証`String`します。</span><span class="sxs-lookup"><span data-stu-id="6a632-132">This generic interface implements the <xref:System.Collections.IEnumerable> interface and guarantees that consumers of this class can access values typed as `String`.</span></span>  
  
<span data-ttu-id="6a632-133">**IEnumerable を実装するコードを追加します。**</span><span class="sxs-lookup"><span data-stu-id="6a632-133">**Add the code to implement IEnumerable**</span></span>

1. <span data-ttu-id="6a632-134">StreamReaderEnumerable.vb ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="6a632-134">Open the StreamReaderEnumerable.vb file.</span></span>

2. <span data-ttu-id="6a632-135">後の行に`Public Class StreamReaderEnumerable`次を入力し、ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="6a632-135">On the line after `Public Class StreamReaderEnumerable`, type the following and press ENTER.</span></span>

     [!code-vb[VbVbalrIteratorWalkthrough#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/StreamReaderIterator.vb#1)]

   <span data-ttu-id="6a632-136">Visual Basic では必要なメンバーを持つクラスを自動的に設定する、`IEnumerable(Of String)`インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="6a632-136">Visual Basic automatically populates the class with the members that are required by the `IEnumerable(Of String)` interface.</span></span>
  
3. <span data-ttu-id="6a632-137">この列挙可能なクラスに、一度に 1 行ずつテキスト ファイルから行を読み取ります。</span><span class="sxs-lookup"><span data-stu-id="6a632-137">This enumerable class will read lines from a text file one line at a time.</span></span> <span data-ttu-id="6a632-138">入力パラメーターとしてファイル パスを受け取るパブリック コンス トラクターを公開するクラスには、次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="6a632-138">Add the following code to the class to expose a public constructor that takes a file path as an input parameter.</span></span>

     [!code-vb[VbVbalrIteratorWalkthrough#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/StreamReaderIterator.vb#2)]

4. <span data-ttu-id="6a632-139">実装、<xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A>のメソッド、`IEnumerable(Of String)`インターフェイスはの新しいインスタンスを返します、`StreamReaderEnumerator`クラス。</span><span class="sxs-lookup"><span data-stu-id="6a632-139">Your implementation of the <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A> method of the `IEnumerable(Of String)` interface will return a new instance of the `StreamReaderEnumerator` class.</span></span> <span data-ttu-id="6a632-140">実装、`GetEnumerator`のメソッド、`IEnumerable`インターフェイスにできる`Private`のメンバーのみを公開する必要があるため、`IEnumerable(Of String)`インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="6a632-140">The implementation of the `GetEnumerator` method of the `IEnumerable` interface can be made `Private`, because you have to expose only members of the `IEnumerable(Of String)` interface.</span></span> <span data-ttu-id="6a632-141">Visual Basic 用に生成するコードに置き換えます、`GetEnumerator`メソッドを次のコード。</span><span class="sxs-lookup"><span data-stu-id="6a632-141">Replace the code that Visual Basic generated for the `GetEnumerator` methods with the following code.</span></span>

     [!code-vb[VbVbalrIteratorWalkthrough#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/StreamReaderIterator.vb#3)]  
  
<span data-ttu-id="6a632-142">**IEnumerator を実装するコードを追加します。**</span><span class="sxs-lookup"><span data-stu-id="6a632-142">**Add the code to implement IEnumerator**</span></span>

1. <span data-ttu-id="6a632-143">StreamReaderEnumerator.vb ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="6a632-143">Open the StreamReaderEnumerator.vb file.</span></span>

2. <span data-ttu-id="6a632-144">後の行に`Public Class StreamReaderEnumerator`次を入力し、ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="6a632-144">On the line after `Public Class StreamReaderEnumerator`, type the following and press ENTER.</span></span>

     [!code-vb[VbVbalrIteratorWalkthrough#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/StreamReaderIterator.vb#4)]

   <span data-ttu-id="6a632-145">Visual Basic では必要なメンバーを持つクラスを自動的に設定する、`IEnumerator(Of String)`インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="6a632-145">Visual Basic automatically populates the class with the members that are required by the `IEnumerator(Of String)` interface.</span></span>

3. <span data-ttu-id="6a632-146">列挙子クラスは、テキスト ファイルを開き、ファイルをファイルから行を読み取る I/O を実行します。</span><span class="sxs-lookup"><span data-stu-id="6a632-146">The enumerator class opens the text file and performs the file I/O to read the lines from the file.</span></span> <span data-ttu-id="6a632-147">クラス ファイルのパスを入力パラメーターとして受け取るパブリック コンス トラクターを公開し、テキスト ファイルを読み取り用に次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="6a632-147">Add the following code to the class to expose a public constructor that takes a file path as an input parameter and open the text file for reading.</span></span>

     [!code-vb[VbVbalrIteratorWalkthrough#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/StreamReaderIterator.vb#5)]

4. <span data-ttu-id="6a632-148">`Current`両方のプロパティ、`IEnumerator(Of String)`と`IEnumerator`インターフェイスとしてテキスト ファイルから現在の項目を返す、`String`します。</span><span class="sxs-lookup"><span data-stu-id="6a632-148">The `Current` properties for both the `IEnumerator(Of String)` and `IEnumerator` interfaces return the current item from the text file as a `String`.</span></span> <span data-ttu-id="6a632-149">実装、`Current`のプロパティ、`IEnumerator`インターフェイスにできる`Private`のメンバーのみを公開する必要があるため、`IEnumerator(Of String)`インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="6a632-149">The implementation of the `Current` property of the `IEnumerator` interface can be made `Private`, because you have to expose only members of the `IEnumerator(Of String)` interface.</span></span> <span data-ttu-id="6a632-150">Visual Basic 用に生成するコードに置き換えます、`Current`プロパティを次のコード。</span><span class="sxs-lookup"><span data-stu-id="6a632-150">Replace the code that Visual Basic generated for the `Current` properties with the following code.</span></span>

     [!code-vb[VbVbalrIteratorWalkthrough#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/StreamReaderIterator.vb#6)]

5. <span data-ttu-id="6a632-151">`MoveNext`のメソッド、`IEnumerator`インターフェイスが、テキスト ファイルに次の項目に移動し、によって返される値を更新して、`Current`プロパティ。</span><span class="sxs-lookup"><span data-stu-id="6a632-151">The `MoveNext` method of the `IEnumerator` interface navigates to the next item in the text file and updates the value that is returned by the `Current` property.</span></span> <span data-ttu-id="6a632-152">読み取るには、これ以上項目がある場合、`MoveNext`メソッドを返します。 `False`。 そうしないと、`MoveNext`メソッドを返します。`True`します。</span><span class="sxs-lookup"><span data-stu-id="6a632-152">If there are no more items to read, the `MoveNext` method returns `False`; otherwise the `MoveNext` method returns `True`.</span></span> <span data-ttu-id="6a632-153">`MoveNext` メソッドに次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="6a632-153">Add the following code to the `MoveNext` method.</span></span>

     [!code-vb[VbVbalrIteratorWalkthrough#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/StreamReaderIterator.vb#7)]

6. <span data-ttu-id="6a632-154">`Reset`のメソッド、`IEnumerator`インターフェイスは、テキスト ファイルの先頭を指す反復子に指示し、現在の項目の値を消去します。</span><span class="sxs-lookup"><span data-stu-id="6a632-154">The `Reset` method of the `IEnumerator` interface directs the iterator to point to the start of the text file and clears the current item value.</span></span> <span data-ttu-id="6a632-155">`Reset` メソッドに次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="6a632-155">Add the following code to the `Reset` method.</span></span>

     [!code-vb[VbVbalrIteratorWalkthrough#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/StreamReaderIterator.vb#8)]

7. <span data-ttu-id="6a632-156">`Dispose`のメソッド、`IEnumerator`インターフェイス、反復子が破棄される前にすべてのアンマネージ リソースが解放されることを保証します。</span><span class="sxs-lookup"><span data-stu-id="6a632-156">The `Dispose` method of the `IEnumerator` interface guarantees that all unmanaged resources are released before the iterator is destroyed.</span></span> <span data-ttu-id="6a632-157">によって使用されるファイル ハンドル、`StreamReader`オブジェクトは、アンマネージ リソースし、反復子インスタンスが破棄される前に閉じる必要があります。</span><span class="sxs-lookup"><span data-stu-id="6a632-157">The file handle that is used by the `StreamReader` object is an unmanaged resource and must be closed before the iterator instance is destroyed.</span></span> <span data-ttu-id="6a632-158">Visual Basic 用に生成するコードに置き換えます、`Dispose`メソッドを次のコード。</span><span class="sxs-lookup"><span data-stu-id="6a632-158">Replace the code that Visual Basic generated for the `Dispose` method with the following code.</span></span>

     [!code-vb[VbVbalrIteratorWalkthrough#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/StreamReaderIterator.vb#9)] 
  
## <a name="using-the-sample-iterator"></a><span data-ttu-id="6a632-159">サンプルの反復子を使用</span><span class="sxs-lookup"><span data-stu-id="6a632-159">Using the Sample Iterator</span></span>

 <span data-ttu-id="6a632-160">制御構造を実装するオブジェクトを必要とすると、コード内の列挙可能なクラスを使用できます`IEnumerable`などを`For Next`ループまたは LINQ クエリ。</span><span class="sxs-lookup"><span data-stu-id="6a632-160">You can use an enumerable class in your code together with control structures that require an object that implements `IEnumerable`, such as a `For Next` loop or a LINQ query.</span></span> <span data-ttu-id="6a632-161">次の例は、 `StreamReaderEnumerable` LINQ クエリでします。</span><span class="sxs-lookup"><span data-stu-id="6a632-161">The following example shows the `StreamReaderEnumerable` in a LINQ query.</span></span>  
  
 [!code-vb[VbVbalrIteratorWalkthrough#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/Module1.vb#10)]  
  
## <a name="see-also"></a><span data-ttu-id="6a632-162">関連項目</span><span class="sxs-lookup"><span data-stu-id="6a632-162">See also</span></span>

- [<span data-ttu-id="6a632-163">Visual Basic における LINQ の概要</span><span class="sxs-lookup"><span data-stu-id="6a632-163">Introduction to LINQ in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="6a632-164">制御フロー</span><span class="sxs-lookup"><span data-stu-id="6a632-164">Control Flow</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)
- [<span data-ttu-id="6a632-165">ループ構造</span><span class="sxs-lookup"><span data-stu-id="6a632-165">Loop Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [<span data-ttu-id="6a632-166">For Each...Next ステートメント</span><span class="sxs-lookup"><span data-stu-id="6a632-166">For Each...Next Statement</span></span>](../../../../visual-basic/language-reference/statements/for-each-next-statement.md)
