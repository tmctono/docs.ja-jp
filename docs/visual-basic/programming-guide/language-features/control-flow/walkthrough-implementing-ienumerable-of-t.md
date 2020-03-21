---
title: IEnumerable の実装
ms.date: 07/31/2018
helpviewer_keywords:
- control flow [Visual Basic]
- enumerable interfaces
- loop structures [Visual Basic], optimizing performance
- control flow [Visual Basic]
ms.assetid: c60d7589-51f2-4463-a2d5-22506bbc1554
ms.openlocfilehash: 4151a680050f234d450d8de5e67a767c54e8df68
ms.sourcegitcommit: 43d10ef65f0f1fd6c3b515e363bde11a3fcd8d6d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2020
ms.locfileid: "78266912"
---
# <a name="walkthrough-implementing-ienumerableof-t-in-visual-basic"></a><span data-ttu-id="2ba09-102">チュートリアル: Visual Basic での IEnumerable(Of T) の実装</span><span class="sxs-lookup"><span data-stu-id="2ba09-102">Walkthrough: Implementing IEnumerable(Of T) in Visual Basic</span></span>
<span data-ttu-id="2ba09-103">インターフェイス<xref:System.Collections.Generic.IEnumerable%601>は、一度に 1 項目ずつ値のシーケンスを返すことができるクラスによって実装されます。</span><span class="sxs-lookup"><span data-stu-id="2ba09-103">The <xref:System.Collections.Generic.IEnumerable%601> interface is implemented by classes that can return a sequence of values one item at a time.</span></span> <span data-ttu-id="2ba09-104">一度に 1 つの項目でデータを返す利点は、データの完全なセットをメモリに読み込んで作業する必要がなさ、ということです。</span><span class="sxs-lookup"><span data-stu-id="2ba09-104">The advantage of returning data one item at a time is that you do not have to load the complete set of data into memory to work with it.</span></span> <span data-ttu-id="2ba09-105">データから 1 つの項目を読み込むために十分なメモリを使用するだけで済みます。</span><span class="sxs-lookup"><span data-stu-id="2ba09-105">You only have to use sufficient memory to load a single item from the data.</span></span> <span data-ttu-id="2ba09-106">インターフェイスを実装する`IEnumerable(T)`クラスは、ループまたは`For Each`LINQ クエリで使用できます。</span><span class="sxs-lookup"><span data-stu-id="2ba09-106">Classes that implement the `IEnumerable(T)` interface can be used with `For Each` loops or LINQ queries.</span></span>  
  
 <span data-ttu-id="2ba09-107">たとえば、大きなテキスト ファイルを読み取り、特定の検索条件に一致するファイルから各行を返す必要があるアプリケーションを考えてみます。</span><span class="sxs-lookup"><span data-stu-id="2ba09-107">For example, consider an application that must read a large text file and return each line from the file that matches particular search criteria.</span></span> <span data-ttu-id="2ba09-108">アプリケーションは、指定された条件に一致するファイルから行を返すために LINQ クエリを使用します。</span><span class="sxs-lookup"><span data-stu-id="2ba09-108">The application uses a LINQ query to return lines from the file that match the specified criteria.</span></span> <span data-ttu-id="2ba09-109">LINQ クエリを使用してファイルの内容を照会するために、アプリケーションはファイルの内容を配列またはコレクションに読み込むことができます。</span><span class="sxs-lookup"><span data-stu-id="2ba09-109">To query the contents of the file by using a LINQ query, the application could load the contents of the file into an array or a collection.</span></span> <span data-ttu-id="2ba09-110">ただし、ファイル全体を配列またはコレクションに読み込むと、必要なメモリよりもはるかに多くのメモリが消費されます。</span><span class="sxs-lookup"><span data-stu-id="2ba09-110">However, loading the whole file into an array or collection would consume far more memory than is required.</span></span> <span data-ttu-id="2ba09-111">LINQ クエリは、列挙可能なクラスを使用してファイルの内容をクエリし、検索条件に一致する値のみを返すことができます。</span><span class="sxs-lookup"><span data-stu-id="2ba09-111">The LINQ query could instead query the file contents by using an enumerable class, returning only values that match the search criteria.</span></span> <span data-ttu-id="2ba09-112">一致する値を少数しか返さなクエリでは、消費するメモリの量が非常に少なくなります。</span><span class="sxs-lookup"><span data-stu-id="2ba09-112">Queries that return only a few matching values would consume far less memory.</span></span>  
  
 <span data-ttu-id="2ba09-113">インターフェイスを実装するクラスを作成して、<xref:System.Collections.Generic.IEnumerable%601>ソース データを列挙可能なデータとして公開できます。</span><span class="sxs-lookup"><span data-stu-id="2ba09-113">You can create a class that implements the <xref:System.Collections.Generic.IEnumerable%601> interface to expose source data as enumerable data.</span></span> <span data-ttu-id="2ba09-114">`IEnumerable(T)`インターフェイスを実装するクラスには、ソース データを反復処理するインターフェイス<xref:System.Collections.Generic.IEnumerator%601>を実装する別のクラスが必要です。</span><span class="sxs-lookup"><span data-stu-id="2ba09-114">Your class that implements the `IEnumerable(T)` interface will require another class that implements the <xref:System.Collections.Generic.IEnumerator%601> interface to iterate through the source data.</span></span> <span data-ttu-id="2ba09-115">これら 2 つのクラスを使用すると、データの項目を特定の型として順番に返します。</span><span class="sxs-lookup"><span data-stu-id="2ba09-115">These two classes enable you to return items of data sequentially as a specific type.</span></span>  
  
 <span data-ttu-id="2ba09-116">このチュートリアルでは、`IEnumerable(Of String)`インターフェイスを実装するクラスと、テキスト ファイルを一度に 1`IEnumerator(Of String)`行ずつ読み取るインターフェイスを実装するクラスを作成します。</span><span class="sxs-lookup"><span data-stu-id="2ba09-116">In this walkthrough, you will create a class that implements the `IEnumerable(Of String)` interface and a class that implements the `IEnumerator(Of String)` interface to read a text file one line at a time.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="creating-the-enumerable-class"></a><span data-ttu-id="2ba09-117">列挙可能なクラスの作成</span><span class="sxs-lookup"><span data-stu-id="2ba09-117">Creating the Enumerable Class</span></span>  
  
<span data-ttu-id="2ba09-118">**列挙可能なクラス プロジェクトを作成します。**</span><span class="sxs-lookup"><span data-stu-id="2ba09-118">**Create the enumerable class project**</span></span>

1. <span data-ttu-id="2ba09-119">Visual Basic の [**ファイル**] メニューの [**新規作成**] をポイントし、[**プロジェクト**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2ba09-119">In Visual Basic, on the **File** menu, point to **New** and then click **Project**.</span></span>

1. <span data-ttu-id="2ba09-120">**[新しいプロジェクト]** ダイアログ ボックスの **[プロジェクトの種類]** ペインで、**[Windows]** が選択されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="2ba09-120">In the **New Project** dialog box, in the **Project Types** pane, make sure that **Windows** is selected.</span></span> <span data-ttu-id="2ba09-121">**[テンプレート]** ペインで **[クラス ライブラリ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="2ba09-121">Select **Class Library** in the **Templates** pane.</span></span> <span data-ttu-id="2ba09-122">**[名前]** ボックスに `StreamReaderEnumerable` と入力して、**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2ba09-122">In the **Name** box, type `StreamReaderEnumerable`, and then click **OK**.</span></span> <span data-ttu-id="2ba09-123">新しいプロジェクトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="2ba09-123">The new project is displayed.</span></span>

1. <span data-ttu-id="2ba09-124">**ソリューション エクスプローラ**で、Class1.vb ファイルを右クリックし、[**名前の変更**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2ba09-124">In **Solution Explorer**, right-click the Class1.vb file and click **Rename**.</span></span> <span data-ttu-id="2ba09-125">ファイルの名前を `StreamReaderEnumerable.vb` に変更し、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="2ba09-125">Rename the file to `StreamReaderEnumerable.vb` and press ENTER.</span></span> <span data-ttu-id="2ba09-126">ファイルの名前を変更すると、クラスの名前も `StreamReaderEnumerable` に変更されます。</span><span class="sxs-lookup"><span data-stu-id="2ba09-126">Renaming the file will also rename the class to `StreamReaderEnumerable`.</span></span> <span data-ttu-id="2ba09-127">このクラスが `IEnumerable(Of String)` インターフェイスを実装します。</span><span class="sxs-lookup"><span data-stu-id="2ba09-127">This class will implement the `IEnumerable(Of String)` interface.</span></span>

1. <span data-ttu-id="2ba09-128">プロジェクトを右クリックし、[**追加**] をポイントして、[**新しい項目**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2ba09-128">Right-click the StreamReaderEnumerable project, point to **Add**, and then click **New Item**.</span></span> <span data-ttu-id="2ba09-129">**[クラス**] テンプレートを選択します。</span><span class="sxs-lookup"><span data-stu-id="2ba09-129">Select the **Class** template.</span></span> <span data-ttu-id="2ba09-130">**[名前]** ボックスに「`StreamReaderEnumerator.vb`」と入力し、**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2ba09-130">In the **Name** box, type `StreamReaderEnumerator.vb` and click **OK**.</span></span>

 <span data-ttu-id="2ba09-131">このプロジェクトの最初のクラスは列挙可能なクラスであり、インターフェイスを実装`IEnumerable(Of String)`します。</span><span class="sxs-lookup"><span data-stu-id="2ba09-131">The first class in this project is the enumerable class and will implement the `IEnumerable(Of String)` interface.</span></span> <span data-ttu-id="2ba09-132">このジェネリック インターフェイスはインターフェイス<xref:System.Collections.IEnumerable>を実装し、このクラスのコンシューマーが 型指定された値に`String`アクセスできることを保証します。</span><span class="sxs-lookup"><span data-stu-id="2ba09-132">This generic interface implements the <xref:System.Collections.IEnumerable> interface and guarantees that consumers of this class can access values typed as `String`.</span></span>  
  
<span data-ttu-id="2ba09-133">**IEnumerable を実装するコードを追加します。**</span><span class="sxs-lookup"><span data-stu-id="2ba09-133">**Add the code to implement IEnumerable**</span></span>

1. <span data-ttu-id="2ba09-134">ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="2ba09-134">Open the StreamReaderEnumerable.vb file.</span></span>

2. <span data-ttu-id="2ba09-135">の後`Public Class StreamReaderEnumerable`の行に、次のコマンドを入力し、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="2ba09-135">On the line after `Public Class StreamReaderEnumerable`, type the following and press ENTER.</span></span>

     [!code-vb[VbVbalrIteratorWalkthrough#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/StreamReaderIterator.vb#1)]

   <span data-ttu-id="2ba09-136">Visual Basic では、インターフェイスに必要なメンバーが自動的にクラス`IEnumerable(Of String)`に設定されます。</span><span class="sxs-lookup"><span data-stu-id="2ba09-136">Visual Basic automatically populates the class with the members that are required by the `IEnumerable(Of String)` interface.</span></span>
  
3. <span data-ttu-id="2ba09-137">この列挙可能なクラスは、テキスト ファイルから一度に 1 行ずつ行を読み取ります。</span><span class="sxs-lookup"><span data-stu-id="2ba09-137">This enumerable class will read lines from a text file one line at a time.</span></span> <span data-ttu-id="2ba09-138">次のコードをクラスに追加して、ファイル パスを入力パラメーターとして受け取るパブリック コンストラクターを公開します。</span><span class="sxs-lookup"><span data-stu-id="2ba09-138">Add the following code to the class to expose a public constructor that takes a file path as an input parameter.</span></span>

     [!code-vb[VbVbalrIteratorWalkthrough#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/StreamReaderIterator.vb#2)]

4. <span data-ttu-id="2ba09-139">インターフェイスのメソッドの<xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A>実装は`IEnumerable(Of String)`、クラスの新しいインスタンスを`StreamReaderEnumerator`返します。</span><span class="sxs-lookup"><span data-stu-id="2ba09-139">Your implementation of the <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A> method of the `IEnumerable(Of String)` interface will return a new instance of the `StreamReaderEnumerator` class.</span></span> <span data-ttu-id="2ba09-140">インターフェイスの`GetEnumerator`メンバーのみを公開する必要があるため、インターフェイスの`Private`メソッドの`IEnumerable(Of String)`実装を行うことができます。 `IEnumerable`</span><span class="sxs-lookup"><span data-stu-id="2ba09-140">The implementation of the `GetEnumerator` method of the `IEnumerable` interface can be made `Private`, because you have to expose only members of the `IEnumerable(Of String)` interface.</span></span> <span data-ttu-id="2ba09-141">メソッドに対して生成されたコードを次`GetEnumerator`のコードに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="2ba09-141">Replace the code that Visual Basic generated for the `GetEnumerator` methods with the following code.</span></span>

     [!code-vb[VbVbalrIteratorWalkthrough#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/StreamReaderIterator.vb#3)]  
  
<span data-ttu-id="2ba09-142">**IEnumerator を実装するコードを追加します。**</span><span class="sxs-lookup"><span data-stu-id="2ba09-142">**Add the code to implement IEnumerator**</span></span>

1. <span data-ttu-id="2ba09-143">ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="2ba09-143">Open the StreamReaderEnumerator.vb file.</span></span>

2. <span data-ttu-id="2ba09-144">の後`Public Class StreamReaderEnumerator`の行に、次のコマンドを入力し、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="2ba09-144">On the line after `Public Class StreamReaderEnumerator`, type the following and press ENTER.</span></span>

     [!code-vb[VbVbalrIteratorWalkthrough#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/StreamReaderIterator.vb#4)]

   <span data-ttu-id="2ba09-145">Visual Basic では、インターフェイスに必要なメンバーが自動的にクラス`IEnumerator(Of String)`に設定されます。</span><span class="sxs-lookup"><span data-stu-id="2ba09-145">Visual Basic automatically populates the class with the members that are required by the `IEnumerator(Of String)` interface.</span></span>

3. <span data-ttu-id="2ba09-146">列挙子クラスは、テキスト ファイルを開き、ファイル I/O を実行してファイルから行を読み取ります。</span><span class="sxs-lookup"><span data-stu-id="2ba09-146">The enumerator class opens the text file and performs the file I/O to read the lines from the file.</span></span> <span data-ttu-id="2ba09-147">次のコードをクラスに追加して、ファイル パスを入力パラメーターとして受け取るパブリック コンストラクターを公開し、読み取り用にテキスト ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="2ba09-147">Add the following code to the class to expose a public constructor that takes a file path as an input parameter and open the text file for reading.</span></span>

     [!code-vb[VbVbalrIteratorWalkthrough#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/StreamReaderIterator.vb#5)]

4. <span data-ttu-id="2ba09-148">インターフェイス`Current`と インターフェイス`IEnumerator(Of String)``IEnumerator`の両方のプロパティは、テキスト ファイルから現在のアイテム`String`を .</span><span class="sxs-lookup"><span data-stu-id="2ba09-148">The `Current` properties for both the `IEnumerator(Of String)` and `IEnumerator` interfaces return the current item from the text file as a `String`.</span></span> <span data-ttu-id="2ba09-149">インターフェイスの`Current`メンバーのみを公開する必要があるため、インターフェイスの`Private`プロパティの`IEnumerator(Of String)`実装を行うことができます。 `IEnumerator`</span><span class="sxs-lookup"><span data-stu-id="2ba09-149">The implementation of the `Current` property of the `IEnumerator` interface can be made `Private`, because you have to expose only members of the `IEnumerator(Of String)` interface.</span></span> <span data-ttu-id="2ba09-150">プロパティに対して生成されたコードを次`Current`のコードに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="2ba09-150">Replace the code that Visual Basic generated for the `Current` properties with the following code.</span></span>

     [!code-vb[VbVbalrIteratorWalkthrough#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/StreamReaderIterator.vb#6)]

5. <span data-ttu-id="2ba09-151">インターフェイス`MoveNext`の`IEnumerator`メソッドは、テキスト ファイル内の次の項目に移動し、プロパティによって返される値を`Current`更新します。</span><span class="sxs-lookup"><span data-stu-id="2ba09-151">The `MoveNext` method of the `IEnumerator` interface navigates to the next item in the text file and updates the value that is returned by the `Current` property.</span></span> <span data-ttu-id="2ba09-152">読み取る項目がなくなった場合、メソッド`MoveNext`は返`False`します。それ以外`MoveNext`の場合`True`、メソッドは を返します。</span><span class="sxs-lookup"><span data-stu-id="2ba09-152">If there are no more items to read, the `MoveNext` method returns `False`; otherwise the `MoveNext` method returns `True`.</span></span> <span data-ttu-id="2ba09-153">`MoveNext` メソッドに次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="2ba09-153">Add the following code to the `MoveNext` method.</span></span>

     [!code-vb[VbVbalrIteratorWalkthrough#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/StreamReaderIterator.vb#7)]

6. <span data-ttu-id="2ba09-154">インターフェイス`Reset`の`IEnumerator`メソッドは、テキスト ファイルの先頭を指し示す反復器を指示し、現在の項目の値をクリアします。</span><span class="sxs-lookup"><span data-stu-id="2ba09-154">The `Reset` method of the `IEnumerator` interface directs the iterator to point to the start of the text file and clears the current item value.</span></span> <span data-ttu-id="2ba09-155">`Reset` メソッドに次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="2ba09-155">Add the following code to the `Reset` method.</span></span>

     [!code-vb[VbVbalrIteratorWalkthrough#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/StreamReaderIterator.vb#8)]

7. <span data-ttu-id="2ba09-156">インターフェイス`Dispose`の`IEnumerator`メソッドは、反復器が破棄される前にすべてのアンマネージ リソースが解放されることを保証します。</span><span class="sxs-lookup"><span data-stu-id="2ba09-156">The `Dispose` method of the `IEnumerator` interface guarantees that all unmanaged resources are released before the iterator is destroyed.</span></span> <span data-ttu-id="2ba09-157">`StreamReader`オブジェクトによって使用されるファイル ハンドルはアンマネージ リソースであり、反復処理インスタンスが破棄される前に閉じる必要があります。</span><span class="sxs-lookup"><span data-stu-id="2ba09-157">The file handle that is used by the `StreamReader` object is an unmanaged resource and must be closed before the iterator instance is destroyed.</span></span> <span data-ttu-id="2ba09-158">メソッドに対して生成されたコードを`Dispose`次のコードに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="2ba09-158">Replace the code that Visual Basic generated for the `Dispose` method with the following code.</span></span>

     [!code-vb[VbVbalrIteratorWalkthrough#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/StreamReaderIterator.vb#9)]
  
## <a name="using-the-sample-iterator"></a><span data-ttu-id="2ba09-159">サンプル反復器の使用</span><span class="sxs-lookup"><span data-stu-id="2ba09-159">Using the Sample Iterator</span></span>

 <span data-ttu-id="2ba09-160">コード内で列挙可能なクラスを使用し、ループや LINQ クエリなどの`IEnumerable`を実装するオブジェクトを必要とするコントロール構造を使用できます。 `For Next`</span><span class="sxs-lookup"><span data-stu-id="2ba09-160">You can use an enumerable class in your code together with control structures that require an object that implements `IEnumerable`, such as a `For Next` loop or a LINQ query.</span></span> <span data-ttu-id="2ba09-161">次の例は、LINQ`StreamReaderEnumerable`クエリの例です。</span><span class="sxs-lookup"><span data-stu-id="2ba09-161">The following example shows the `StreamReaderEnumerable` in a LINQ query.</span></span>  
  
 [!code-vb[VbVbalrIteratorWalkthrough#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/Module1.vb#10)]  
  
## <a name="see-also"></a><span data-ttu-id="2ba09-162">関連項目</span><span class="sxs-lookup"><span data-stu-id="2ba09-162">See also</span></span>

- [<span data-ttu-id="2ba09-163">Visual Basic における LINQ の概要</span><span class="sxs-lookup"><span data-stu-id="2ba09-163">Introduction to LINQ in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="2ba09-164">制御フロー</span><span class="sxs-lookup"><span data-stu-id="2ba09-164">Control Flow</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)
- [<span data-ttu-id="2ba09-165">ループ構造</span><span class="sxs-lookup"><span data-stu-id="2ba09-165">Loop Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [<span data-ttu-id="2ba09-166">For Each...Next ステートメント</span><span class="sxs-lookup"><span data-stu-id="2ba09-166">For Each...Next Statement</span></span>](../../../../visual-basic/language-reference/statements/for-each-next-statement.md)
