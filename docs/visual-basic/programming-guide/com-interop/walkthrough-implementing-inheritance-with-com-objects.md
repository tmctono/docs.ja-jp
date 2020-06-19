---
title: 'チュートリアル: COM オブジェクトによる継承の実装'
ms.date: 07/20/2015
helpviewer_keywords:
- inheritance [Visual Basic], COM reusability
- base classes [Visual Basic], COM reusability
- inheritance [Visual Basic], walkthroughs
- derived classes [Visual Basic], COM reusability
ms.assetid: f8e7263a-de13-48d1-b67c-ca1adf3544d9
ms.openlocfilehash: bdb891e1a150f0d7b79aefcc3db1f18dc8e84be4
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2020
ms.locfileid: "84396728"
---
# <a name="walkthrough-implementing-inheritance-with-com-objects-visual-basic"></a><span data-ttu-id="c99ae-102">チュートリアル: COM オブジェクトによる継承の実装 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c99ae-102">Walkthrough: Implementing Inheritance with COM Objects (Visual Basic)</span></span>

<span data-ttu-id="c99ae-103">以前のバージョンの Visual Basic で作成されたものでも、COM オブジェクトの `Public` クラスから Visual Basic クラスを派生させることができます。</span><span class="sxs-lookup"><span data-stu-id="c99ae-103">You can derive Visual Basic classes from `Public` classes in COM objects, even those created in earlier versions of Visual Basic.</span></span> <span data-ttu-id="c99ae-104">COM オブジェクトから継承されたクラスのプロパティとメソッドは、他の基底クラスのプロパティとメソッドがオーバーライドまたはオーバーロードできるのと同様に、オーバーライドまたはオーバーロードできます。</span><span class="sxs-lookup"><span data-stu-id="c99ae-104">The properties and methods of classes inherited from COM objects can be overridden or overloaded just as properties and methods of any other base class can be overridden or overloaded.</span></span> <span data-ttu-id="c99ae-105">COM オブジェクトからの継承は、再コンパイルしたくない既存のクラス ライブラリがある場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="c99ae-105">Inheritance from COM objects is useful when you have an existing class library that you do not want to recompile.</span></span>

<span data-ttu-id="c99ae-106">次の手順では、Visual Basic 6.0 を使用してクラスを含む COM オブジェクトを作成してから、それを基底クラスとして使用する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="c99ae-106">The following procedure shows how to use Visual Basic 6.0 to create a COM object that contains a class, and then use it as a base class.</span></span>

[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]

## <a name="to-build-the-com-object-that-is-used-in-this-walkthrough"></a><span data-ttu-id="c99ae-107">このチュートリアルで使用する COM オブジェクトをビルドするには</span><span class="sxs-lookup"><span data-stu-id="c99ae-107">To build the COM object that is used in this walkthrough</span></span>

1. <span data-ttu-id="c99ae-108">Visual Basic 6.0 で、新しい ActiveX DLL プロジェクトを開きます。</span><span class="sxs-lookup"><span data-stu-id="c99ae-108">In Visual Basic 6.0, open a new ActiveX DLL project.</span></span> <span data-ttu-id="c99ae-109">`Project1` という名前のプロジェクトが作成されます。</span><span class="sxs-lookup"><span data-stu-id="c99ae-109">A project named `Project1` is created.</span></span> <span data-ttu-id="c99ae-110">これには `Class1` という名前のクラスが含まれています。</span><span class="sxs-lookup"><span data-stu-id="c99ae-110">It has a class named `Class1`.</span></span>

2. <span data-ttu-id="c99ae-111">**プロジェクト エクスプローラー**で **[Project1]** を右クリックし、 **[Project1 Properties] (Project1 のプロパティ)** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c99ae-111">In the **Project Explorer**, right-click **Project1**, and then click **Project1 Properties**.</span></span> <span data-ttu-id="c99ae-112">**[プロジェクトのプロパティ]** ダイアログ ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c99ae-112">The **Project Properties** dialog box is displayed.</span></span>

3. <span data-ttu-id="c99ae-113">**[プロジェクトのプロパティ]** ダイアログ ボックスの **[全般]** タブで、 **[プロジェクト名]** フィールドに「`ComObject1`」と入力してプロジェクト名を変更します。</span><span class="sxs-lookup"><span data-stu-id="c99ae-113">On the **General** tab of the **Project Properties** dialog box, change the project name by typing `ComObject1` in the **Project Name** field.</span></span>

4. <span data-ttu-id="c99ae-114">**プロジェクト エクスプローラー**で `Class1` を右クリックし、 **[プロパティ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c99ae-114">In the **Project Explorer**, right-click `Class1`, and then click **Properties**.</span></span> <span data-ttu-id="c99ae-115">クラスの **[プロパティ]** ウィンドウが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c99ae-115">The **Properties** window for the class is displayed.</span></span>

5. <span data-ttu-id="c99ae-116">`Name` プロパティを `MathFunctions` に変更します。</span><span class="sxs-lookup"><span data-stu-id="c99ae-116">Change the `Name` property to `MathFunctions`.</span></span>

6. <span data-ttu-id="c99ae-117">**プロジェクト エクスプローラー**で `MathFunctions` を右クリックし、 **[コードの表示]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c99ae-117">In the **Project Explorer**, right-click `MathFunctions`, and then click **View Code**.</span></span> <span data-ttu-id="c99ae-118">**[コード エディター]** が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c99ae-118">The **Code Editor** is displayed.</span></span>

7. <span data-ttu-id="c99ae-119">プロパティ値を保持するためにローカル変数を追加します。</span><span class="sxs-lookup"><span data-stu-id="c99ae-119">Add a local variable to hold the property value:</span></span>

    ```vb
    ' Local variable to hold property value
    Private mvarProp1 As Integer
    ```

8. <span data-ttu-id="c99ae-120">Property `Let` と Property `Get` のプロパティ プロシージャを追加します。</span><span class="sxs-lookup"><span data-stu-id="c99ae-120">Add Property `Let` and Property `Get` property procedures:</span></span>

    ```vb
    Public Property Let Prop1(ByVal vData As Integer)
       'Used when assigning a value to the property.
       mvarProp1 = vData
    End Property
    Public Property Get Prop1() As Integer
       'Used when retrieving a property's value.
       Prop1 = mvarProp1
    End Property
    ```

9. <span data-ttu-id="c99ae-121">関数を追加します。</span><span class="sxs-lookup"><span data-stu-id="c99ae-121">Add a function:</span></span>

    ```vb
    Function AddNumbers(
       ByVal SomeNumber As Integer,
       ByVal AnotherNumber As Integer) As Integer

       AddNumbers = SomeNumber + AnotherNumber
    End Function
    ```

10. <span data-ttu-id="c99ae-122">**[ファイル]** メニューの **[Make ComObject1.dll] (ComObject1 の作成)** をクリックして、COM オブジェクトを作成して登録します。</span><span class="sxs-lookup"><span data-stu-id="c99ae-122">Create and register the COM object by clicking **Make ComObject1.dll** on the **File** menu.</span></span>

    > [!NOTE]
    > <span data-ttu-id="c99ae-123">Visual Basic で作成されたクラスを COM オブジェクトとして公開することもできますが、これは真の COM オブジェクトではなく、このチュートリアルでは使用できません。</span><span class="sxs-lookup"><span data-stu-id="c99ae-123">Although you can also expose a class created with Visual Basic as a COM object, it is not a true COM object and cannot be used in this walkthrough.</span></span> <span data-ttu-id="c99ae-124">詳細については、「[.NET Framework アプリケーションにおける COM 相互運用性](com-interoperability-in-net-framework-applications.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c99ae-124">For details, see [COM Interoperability in .NET Framework Applications](com-interoperability-in-net-framework-applications.md).</span></span>

## <a name="interop-assemblies"></a><span data-ttu-id="c99ae-125">相互運用機能アセンブリ</span><span class="sxs-lookup"><span data-stu-id="c99ae-125">Interop Assemblies</span></span>

<span data-ttu-id="c99ae-126">次の手順では、アンマネージ コード (COM オブジェクトなど) と Visual Studio で使用されるマネージド コードの間のブリッジとして機能する相互運用機能アセンブリを作成します。</span><span class="sxs-lookup"><span data-stu-id="c99ae-126">In the following procedure, you will create an interop assembly, which acts as a bridge between unmanaged code (such as a COM object) and the managed code Visual Studio uses.</span></span> <span data-ttu-id="c99ae-127">Visual Basic で作成される相互運用機能アセンブリは、COM オブジェクトの操作の多くの詳細情報を処理します。たとえば、*相互運用マーシャリング*、COM オブジェクトとの間で移動するときに、パラメーターと戻り値を同等のデータ型にパッケージ化するプロセスなどです。</span><span class="sxs-lookup"><span data-stu-id="c99ae-127">The interop assembly that Visual Basic creates handles many of the details of working with COM objects, such as *interop marshaling*, the process of packaging parameters and return values into equivalent data types as they move to and from COM objects.</span></span> <span data-ttu-id="c99ae-128">Visual Basic アプリケーション内の参照は、実際の COM オブジェクトではなく、相互運用機能アセンブリを指します。</span><span class="sxs-lookup"><span data-stu-id="c99ae-128">The reference in the Visual Basic application points to the interop assembly, not the actual COM object.</span></span>

### <a name="to-use-a-com-object-with-visual-basic-2005-and-later-versions"></a><span data-ttu-id="c99ae-129">Visual Basic 2005 以降のバージョンで COM オブジェクトを使用するには</span><span class="sxs-lookup"><span data-stu-id="c99ae-129">To use a COM object with Visual Basic 2005 and later versions</span></span>

1. <span data-ttu-id="c99ae-130">新しい Visual Basic Windows アプリケーション プロジェクトを開きます。</span><span class="sxs-lookup"><span data-stu-id="c99ae-130">Open a new Visual Basic Windows Application project.</span></span>

2. <span data-ttu-id="c99ae-131">**[プロジェクト]** メニューの **[参照の追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c99ae-131">On the **Project** menu, click **Add Reference**.</span></span>

     <span data-ttu-id="c99ae-132">**[参照の追加]** ダイアログ ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c99ae-132">The **Add Reference** dialog box is displayed.</span></span>

3. <span data-ttu-id="c99ae-133">**[COM]** タブで、 **[コンポーネント名]** の一覧で `ComObject1` をダブルクリックし、 **[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c99ae-133">On the **COM** tab, double-click `ComObject1` in the **Component Name** list and click **OK**.</span></span>

4. <span data-ttu-id="c99ae-134">**[プロジェクト]** メニューの **[新しい項目の追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c99ae-134">On the **Project** menu, click **Add New Item**.</span></span>

     <span data-ttu-id="c99ae-135">**[新しい項目の追加]** ダイアログ ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c99ae-135">The **Add New Item** dialog box is displayed.</span></span>

5. <span data-ttu-id="c99ae-136">**[テンプレート]** ウィンドウで **[クラス]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c99ae-136">In the **Templates** pane, click **Class**.</span></span>

     <span data-ttu-id="c99ae-137">`Class1.vb`[名前]**フィールドに既定のファイル名** が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c99ae-137">The default file name, `Class1.vb`, appears in the **Name** field.</span></span> <span data-ttu-id="c99ae-138">このフィールドを MathClass.vb に変更し、 **[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c99ae-138">Change this field to MathClass.vb and click **Add**.</span></span> <span data-ttu-id="c99ae-139">これにより `MathClass` という名前のクラスが作成され、そのコードが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c99ae-139">This creates a class named `MathClass`, and displays its code.</span></span>

6. <span data-ttu-id="c99ae-140">COM クラスを継承するために、`MathClass` の先頭に次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="c99ae-140">Add the following code to the top of `MathClass` to inherit from the COM class.</span></span>

     [!code-vb[VbVbalrInterop#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#31)]

7. <span data-ttu-id="c99ae-141">`MathClass` に次のコードを追加して、基底クラスのパブリック メソッドをオーバーロードします。</span><span class="sxs-lookup"><span data-stu-id="c99ae-141">Overload the public method of the base class by adding the following code to `MathClass`:</span></span>

     [!code-vb[VbVbalrInterop#32](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#32)]

8. <span data-ttu-id="c99ae-142">次のコードを `MathClass` に追加して、継承されたクラスを拡張します。</span><span class="sxs-lookup"><span data-stu-id="c99ae-142">Extend the inherited class by adding the following code to `MathClass`:</span></span>

     [!code-vb[VbVbalrInterop#33](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#33)]

<span data-ttu-id="c99ae-143">新しいクラスは、COM オブジェクトの基底クラスのプロパティを継承し、メソッドをオーバーロードして、クラスを拡張する新しいメソッドを定義します。</span><span class="sxs-lookup"><span data-stu-id="c99ae-143">The new class inherits the properties of the base class in the COM object, overloads a method, and defines a new method to extend the class.</span></span>

### <a name="to-test-the-inherited-class"></a><span data-ttu-id="c99ae-144">継承されたクラスをテストするには</span><span class="sxs-lookup"><span data-stu-id="c99ae-144">To test the inherited class</span></span>

1. <span data-ttu-id="c99ae-145">スタートアップ フォームにボタンを追加し、それをダブルクリックしてコードを表示します。</span><span class="sxs-lookup"><span data-stu-id="c99ae-145">Add a button to your startup form, and then double-click it to view its code.</span></span>

2. <span data-ttu-id="c99ae-146">ボタンの `Click` イベント ハンドラー プロシージャに次のコードを追加して、`MathClass` のインスタンスを作成し、オーバーロードされたメソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="c99ae-146">In the button's `Click` event handler procedure, add the following code to create an instance of `MathClass` and call the overloaded methods:</span></span>

     [!code-vb[VbVbalrInterop#34](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#34)]

3. <span data-ttu-id="c99ae-147">F5 キーを押して、プロジェクトを実行します。</span><span class="sxs-lookup"><span data-stu-id="c99ae-147">Run the project by pressing F5.</span></span>

<span data-ttu-id="c99ae-148">フォームのボタンをクリックすると、`AddNumbers` メソッドが最初に `Short` データ型の数値で呼び出され、Visual Basic で基底クラスから適切なメソッドが選択されます。</span><span class="sxs-lookup"><span data-stu-id="c99ae-148">When you click the button on the form, the `AddNumbers` method is first called with `Short` data type numbers, and Visual Basic chooses the appropriate method from the base class.</span></span> <span data-ttu-id="c99ae-149">`AddNumbers` の 2 回目の呼び出しは `MathClass` からのオーバーロード メソッドに送られます。</span><span class="sxs-lookup"><span data-stu-id="c99ae-149">The second call to `AddNumbers` is directed to the overload method from `MathClass`.</span></span> <span data-ttu-id="c99ae-150">3 回目の呼び出しは、クラスを拡張する `SubtractNumbers` メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="c99ae-150">The third call calls the `SubtractNumbers` method, which extends the class.</span></span> <span data-ttu-id="c99ae-151">基底クラスのプロパティが設定され、値が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c99ae-151">The property in the base class is set, and the value is displayed.</span></span>

## <a name="next-steps"></a><span data-ttu-id="c99ae-152">次の手順</span><span class="sxs-lookup"><span data-stu-id="c99ae-152">Next Steps</span></span>

<span data-ttu-id="c99ae-153">オーバーロードされた `AddNumbers` 関数が、COM オブジェクトの基底クラスから継承されたメソッドと同じデータ型を持つように見えることに気付いたかもしれません。</span><span class="sxs-lookup"><span data-stu-id="c99ae-153">You may have noticed that the overloaded `AddNumbers` function appears to have the same data type as the method inherited from the base class of the COM object.</span></span> <span data-ttu-id="c99ae-154">これは、基底クラスのメソッドの引数とパラメーターが Visual Basic 6.0 では 16 ビット整数として定義されているのに対し、以降のバージョンの Visual Basic では型 `Short` の 16 ビット整数として公開されているためです。</span><span class="sxs-lookup"><span data-stu-id="c99ae-154">This is because the arguments and parameters of the base class method are defined as 16-bit integers in Visual Basic 6.0, but they are exposed as 16-bit integers of type `Short` in later versions of Visual Basic.</span></span> <span data-ttu-id="c99ae-155">新しい関数は、32 ビットの整数を受け入れ、基底クラスの関数をオーバーロードします。</span><span class="sxs-lookup"><span data-stu-id="c99ae-155">The new function accepts 32-bit integers, and overloads the base class function.</span></span>

<span data-ttu-id="c99ae-156">COM オブジェクトを使用する場合は、パラメーターのサイズとデータ型を必ず確認してください。</span><span class="sxs-lookup"><span data-stu-id="c99ae-156">When working with COM objects, make sure that you verify the size and data types of parameters.</span></span> <span data-ttu-id="c99ae-157">たとえば、引数として Visual Basic 6.0 コレクション オブジェクトを受け入れる COM オブジェクトを使用している場合、以降のバージョンの Visual Basic のコレクションを指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="c99ae-157">For example, when you are using a COM object that accepts a Visual Basic 6.0 collection object as an argument, you cannot provide a collection from a later version of Visual Basic.</span></span>

<span data-ttu-id="c99ae-158">COM クラスから継承されたプロパティとメソッドは、オーバーライドすることができます。つまり、基底の COM クラスから継承されたプロパティまたはメソッドを置き換えるローカル プロパティまたはメソッドを宣言できます。</span><span class="sxs-lookup"><span data-stu-id="c99ae-158">Properties and methods inherited from COM classes can be overridden, meaning that you can declare a local property or method that replaces a property or method inherited from a base COM class.</span></span> <span data-ttu-id="c99ae-159">継承された COM プロパティをオーバーライドするためのルールは、次の例外を除き、他のプロパティおよびメソッドをオーバーライドするためのルールに似ています。</span><span class="sxs-lookup"><span data-stu-id="c99ae-159">The rules for overriding inherited COM properties are similar to the rules for overriding other properties and methods with the following exceptions:</span></span>

- <span data-ttu-id="c99ae-160">COM クラスから継承されたプロパティまたはメソッドをオーバーライドする場合は、継承された他のすべてのプロパティとメソッドをオーバーライドする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c99ae-160">If you override any property or method inherited from a COM class, you must override all the other inherited properties and methods.</span></span>

- <span data-ttu-id="c99ae-161">`ByRef` パラメーターを使用するプロパティをオーバーライドすることはできません。</span><span class="sxs-lookup"><span data-stu-id="c99ae-161">Properties that use `ByRef` parameters cannot be overridden.</span></span>

## <a name="see-also"></a><span data-ttu-id="c99ae-162">関連項目</span><span class="sxs-lookup"><span data-stu-id="c99ae-162">See also</span></span>

- [<span data-ttu-id="c99ae-163">.NET Framework アプリケーションにおける COM 相互運用性</span><span class="sxs-lookup"><span data-stu-id="c99ae-163">COM Interoperability in .NET Framework Applications</span></span>](com-interoperability-in-net-framework-applications.md)
- [<span data-ttu-id="c99ae-164">Inherits ステートメント</span><span class="sxs-lookup"><span data-stu-id="c99ae-164">Inherits Statement</span></span>](../../language-reference/statements/inherits-statement.md)
- [<span data-ttu-id="c99ae-165">Short データ型</span><span class="sxs-lookup"><span data-stu-id="c99ae-165">Short Data Type</span></span>](../../language-reference/data-types/short-data-type.md)
