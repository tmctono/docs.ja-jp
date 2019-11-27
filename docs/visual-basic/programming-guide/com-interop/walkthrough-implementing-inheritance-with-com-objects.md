---
title: 'チュートリアル : COM オブジェクトによる継承の実装'
ms.date: 07/20/2015
helpviewer_keywords:
- inheritance [Visual Basic], COM reusability
- base classes [Visual Basic], COM reusability
- inheritance [Visual Basic], walkthroughs
- derived classes [Visual Basic], COM reusability
ms.assetid: f8e7263a-de13-48d1-b67c-ca1adf3544d9
ms.openlocfilehash: 209e1005b9f944bf4883e8406031fb17d4d60df1
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347992"
---
# <a name="walkthrough-implementing-inheritance-with-com-objects-visual-basic"></a><span data-ttu-id="41b8a-102">チュートリアル: COM オブジェクトによる継承の実装 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="41b8a-102">Walkthrough: Implementing Inheritance with COM Objects (Visual Basic)</span></span>

<span data-ttu-id="41b8a-103">以前のバージョンの Visual Basic で作成されたクラスも含めて、COM オブジェクトの `Public` クラスから Visual Basic クラスを派生させることができます。</span><span class="sxs-lookup"><span data-stu-id="41b8a-103">You can derive Visual Basic classes from `Public` classes in COM objects, even those created in earlier versions of Visual Basic.</span></span> <span data-ttu-id="41b8a-104">COM オブジェクトから継承されたクラスのプロパティとメソッドは、他の基底クラスのプロパティおよびメソッドがオーバーライドまたはオーバーロードできるのと同様にオーバーライドまたはオーバーロードできます。</span><span class="sxs-lookup"><span data-stu-id="41b8a-104">The properties and methods of classes inherited from COM objects can be overridden or overloaded just as properties and methods of any other base class can be overridden or overloaded.</span></span> <span data-ttu-id="41b8a-105">COM オブジェクトからの継承は、再コンパイルしたくない既存のクラスライブラリがある場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="41b8a-105">Inheritance from COM objects is useful when you have an existing class library that you do not want to recompile.</span></span>

<span data-ttu-id="41b8a-106">次の手順では、Visual Basic 6.0 を使用して、クラスを含む COM オブジェクトを作成し、それを基底クラスとして使用する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="41b8a-106">The following procedure shows how to use Visual Basic 6.0 to create a COM object that contains a class, and then use it as a base class.</span></span>

[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]

## <a name="to-build-the-com-object-that-is-used-in-this-walkthrough"></a><span data-ttu-id="41b8a-107">このチュートリアルで使用する COM オブジェクトをビルドするには</span><span class="sxs-lookup"><span data-stu-id="41b8a-107">To build the COM object that is used in this walkthrough</span></span>

1. <span data-ttu-id="41b8a-108">Visual Basic 6.0 で、新しい ActiveX DLL プロジェクトを開きます。</span><span class="sxs-lookup"><span data-stu-id="41b8a-108">In Visual Basic 6.0, open a new ActiveX DLL project.</span></span> <span data-ttu-id="41b8a-109">`Project1` という名前のプロジェクトが作成されます。</span><span class="sxs-lookup"><span data-stu-id="41b8a-109">A project named `Project1` is created.</span></span> <span data-ttu-id="41b8a-110">このクラスには、`Class1`という名前のクラスがあります。</span><span class="sxs-lookup"><span data-stu-id="41b8a-110">It has a class named `Class1`.</span></span>

2. <span data-ttu-id="41b8a-111">**Project Explorer**で、 **[project1]** を右クリックし、 **[project1 のプロパティ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="41b8a-111">In the **Project Explorer**, right-click **Project1**, and then click **Project1 Properties**.</span></span> <span data-ttu-id="41b8a-112">**[プロジェクトのプロパティ]** ダイアログボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="41b8a-112">The **Project Properties** dialog box is displayed.</span></span>

3. <span data-ttu-id="41b8a-113">**[プロジェクトのプロパティ]** ダイアログボックスの **[全般**] タブで、 **[プロジェクト名]** フィールドに「`ComObject1`」と入力して、プロジェクト名を変更します。</span><span class="sxs-lookup"><span data-stu-id="41b8a-113">On the **General** tab of the **Project Properties** dialog box, change the project name by typing `ComObject1` in the **Project Name** field.</span></span>

4. <span data-ttu-id="41b8a-114">**Project Explorer**で、[`Class1`] を右クリックし、 **[プロパティ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="41b8a-114">In the **Project Explorer**, right-click `Class1`, and then click **Properties**.</span></span> <span data-ttu-id="41b8a-115">クラスの **[プロパティ]** ウィンドウが表示されます。</span><span class="sxs-lookup"><span data-stu-id="41b8a-115">The **Properties** window for the class is displayed.</span></span>

5. <span data-ttu-id="41b8a-116">`Name` プロパティを `MathFunctions`に変更します。</span><span class="sxs-lookup"><span data-stu-id="41b8a-116">Change the `Name` property to `MathFunctions`.</span></span>

6. <span data-ttu-id="41b8a-117">**Project Explorer**で、[`MathFunctions`] を右クリックし、 **[コードの表示]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="41b8a-117">In the **Project Explorer**, right-click `MathFunctions`, and then click **View Code**.</span></span> <span data-ttu-id="41b8a-118">**コードエディター**が表示されます。</span><span class="sxs-lookup"><span data-stu-id="41b8a-118">The **Code Editor** is displayed.</span></span>

7. <span data-ttu-id="41b8a-119">プロパティ値を保持するローカル変数を追加します。</span><span class="sxs-lookup"><span data-stu-id="41b8a-119">Add a local variable to hold the property value:</span></span>

    ```vb
    ' Local variable to hold property value
    Private mvarProp1 As Integer
    ```

8. <span data-ttu-id="41b8a-120">プロパティ `Let` プロパティとプロパティ `Get` プロパティプロシージャを追加します。</span><span class="sxs-lookup"><span data-stu-id="41b8a-120">Add Property `Let` and Property `Get` property procedures:</span></span>

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

9. <span data-ttu-id="41b8a-121">関数を追加します。</span><span class="sxs-lookup"><span data-stu-id="41b8a-121">Add a function:</span></span>

    ```vb
    Function AddNumbers(
       ByVal SomeNumber As Integer,
       ByVal AnotherNumber As Integer) As Integer

       AddNumbers = SomeNumber + AnotherNumber
    End Function
    ```

10. <span data-ttu-id="41b8a-122">**[ファイル]** メニューの **[ComObject1]** の作成 をクリックして、COM オブジェクトを作成し、登録します。</span><span class="sxs-lookup"><span data-stu-id="41b8a-122">Create and register the COM object by clicking **Make ComObject1.dll** on the **File** menu.</span></span>

    > [!NOTE]
    > <span data-ttu-id="41b8a-123">Visual Basic で作成されたクラスを COM オブジェクトとして公開することもできますが、これは真の COM オブジェクトではなく、このチュートリアルでは使用できません。</span><span class="sxs-lookup"><span data-stu-id="41b8a-123">Although you can also expose a class created with Visual Basic as a COM object, it is not a true COM object and cannot be used in this walkthrough.</span></span> <span data-ttu-id="41b8a-124">詳細については、「 [.NET Framework アプリケーションでの COM 相互運用性](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="41b8a-124">For details, see [COM Interoperability in .NET Framework Applications](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md).</span></span>

## <a name="interop-assemblies"></a><span data-ttu-id="41b8a-125">相互運用機能アセンブリ</span><span class="sxs-lookup"><span data-stu-id="41b8a-125">Interop Assemblies</span></span>

<span data-ttu-id="41b8a-126">次の手順では、アンマネージコード (COM オブジェクトなど) と Visual Studio で使用されるマネージコードの間のブリッジとして機能する相互運用機能アセンブリを作成します。</span><span class="sxs-lookup"><span data-stu-id="41b8a-126">In the following procedure, you will create an interop assembly, which acts as a bridge between unmanaged code (such as a COM object) and the managed code Visual Studio uses.</span></span> <span data-ttu-id="41b8a-127">Visual Basic に*よって作成*された相互運用機能アセンブリは、com オブジェクトとの間で移動するときに、パラメーターと戻り値を同等のデータ型にパッケージ化するプロセスなど、com オブジェクトの操作の詳細の多くを処理します。</span><span class="sxs-lookup"><span data-stu-id="41b8a-127">The interop assembly that Visual Basic creates handles many of the details of working with COM objects, such as *interop marshaling*, the process of packaging parameters and return values into equivalent data types as they move to and from COM objects.</span></span> <span data-ttu-id="41b8a-128">Visual Basic アプリケーション内の参照は、実際の COM オブジェクトではなく、相互運用機能アセンブリを指します。</span><span class="sxs-lookup"><span data-stu-id="41b8a-128">The reference in the Visual Basic application points to the interop assembly, not the actual COM object.</span></span>

### <a name="to-use-a-com-object-with-visual-basic-2005-and-later-versions"></a><span data-ttu-id="41b8a-129">Visual Basic 2005 以降のバージョンで COM オブジェクトを使用するには</span><span class="sxs-lookup"><span data-stu-id="41b8a-129">To use a COM object with Visual Basic 2005 and later versions</span></span>

1. <span data-ttu-id="41b8a-130">新しい Visual Basic Windows アプリケーション プロジェクトを開きます。</span><span class="sxs-lookup"><span data-stu-id="41b8a-130">Open a new Visual Basic Windows Application project.</span></span>

2. <span data-ttu-id="41b8a-131">**[プロジェクト]** メニューの **[参照の追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="41b8a-131">On the **Project** menu, click **Add Reference**.</span></span>

     <span data-ttu-id="41b8a-132">**[参照の追加]** ダイアログ ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="41b8a-132">The **Add Reference** dialog box is displayed.</span></span>

3. <span data-ttu-id="41b8a-133">**[COM]** タブで、 **[コンポーネント名]** ボックスの一覧の `ComObject1` をダブルクリックし、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="41b8a-133">On the **COM** tab, double-click `ComObject1` in the **Component Name** list and click **OK**.</span></span>

4. <span data-ttu-id="41b8a-134">**[プロジェクト]** メニューの **[新しい項目の追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="41b8a-134">On the **Project** menu, click **Add New Item**.</span></span>

     <span data-ttu-id="41b8a-135">**[新しい項目の追加]** ダイアログ ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="41b8a-135">The **Add New Item** dialog box is displayed.</span></span>

5. <span data-ttu-id="41b8a-136">**[テンプレート]** ペインで、 **[クラス]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="41b8a-136">In the **Templates** pane, click **Class**.</span></span>

     <span data-ttu-id="41b8a-137">既定のファイル名 `Class1.vb`が **[名前]** フィールドに表示されます。</span><span class="sxs-lookup"><span data-stu-id="41b8a-137">The default file name, `Class1.vb`, appears in the **Name** field.</span></span> <span data-ttu-id="41b8a-138">このフィールドを MathClass に変更し、 **[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="41b8a-138">Change this field to MathClass.vb and click **Add**.</span></span> <span data-ttu-id="41b8a-139">これにより `MathClass`という名前のクラスが作成され、そのコードが表示されます。</span><span class="sxs-lookup"><span data-stu-id="41b8a-139">This creates a class named `MathClass`, and displays its code.</span></span>

6. <span data-ttu-id="41b8a-140">COM クラスを継承するために、`MathClass` の先頭に次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="41b8a-140">Add the following code to the top of `MathClass` to inherit from the COM class.</span></span>

     [!code-vb[VbVbalrInterop#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#31)]

7. <span data-ttu-id="41b8a-141">`MathClass`に次のコードを追加して、基底クラスのパブリックメソッドをオーバーロードします。</span><span class="sxs-lookup"><span data-stu-id="41b8a-141">Overload the public method of the base class by adding the following code to `MathClass`:</span></span>

     [!code-vb[VbVbalrInterop#32](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#32)]

8. <span data-ttu-id="41b8a-142">`MathClass`に次のコードを追加して、継承されたクラスを拡張します。</span><span class="sxs-lookup"><span data-stu-id="41b8a-142">Extend the inherited class by adding the following code to `MathClass`:</span></span>

     [!code-vb[VbVbalrInterop#33](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#33)]

<span data-ttu-id="41b8a-143">新しいクラスは、COM オブジェクトの基底クラスのプロパティを継承し、メソッドをオーバーロードして、クラスを拡張する新しいメソッドを定義します。</span><span class="sxs-lookup"><span data-stu-id="41b8a-143">The new class inherits the properties of the base class in the COM object, overloads a method, and defines a new method to extend the class.</span></span>

### <a name="to-test-the-inherited-class"></a><span data-ttu-id="41b8a-144">継承されたクラスをテストするには</span><span class="sxs-lookup"><span data-stu-id="41b8a-144">To test the inherited class</span></span>

1. <span data-ttu-id="41b8a-145">スタートアップフォームにボタンを追加し、それをダブルクリックしてコードを表示します。</span><span class="sxs-lookup"><span data-stu-id="41b8a-145">Add a button to your startup form, and then double-click it to view its code.</span></span>

2. <span data-ttu-id="41b8a-146">ボタンの `Click` イベントハンドラープロシージャに次のコードを追加して、`MathClass` のインスタンスを作成し、オーバーロードされたメソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="41b8a-146">In the button's `Click` event handler procedure, add the following code to create an instance of `MathClass` and call the overloaded methods:</span></span>

     [!code-vb[VbVbalrInterop#34](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#34)]

3. <span data-ttu-id="41b8a-147">F5 キーを押してプロジェクトを実行します。</span><span class="sxs-lookup"><span data-stu-id="41b8a-147">Run the project by pressing F5.</span></span>

<span data-ttu-id="41b8a-148">フォームのボタンをクリックすると、`AddNumbers` メソッドが最初に `Short` データ型の数値で呼び出され、Visual Basic 基本クラスから適切なメソッドが選択されます。</span><span class="sxs-lookup"><span data-stu-id="41b8a-148">When you click the button on the form, the `AddNumbers` method is first called with `Short` data type numbers, and Visual Basic chooses the appropriate method from the base class.</span></span> <span data-ttu-id="41b8a-149">`AddNumbers` の2回目の呼び出しは `MathClass`からのオーバーロードメソッドに送られます。</span><span class="sxs-lookup"><span data-stu-id="41b8a-149">The second call to `AddNumbers` is directed to the overload method from `MathClass`.</span></span> <span data-ttu-id="41b8a-150">3番目の呼び出しは、クラスを拡張する `SubtractNumbers` メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="41b8a-150">The third call calls the `SubtractNumbers` method, which extends the class.</span></span> <span data-ttu-id="41b8a-151">基本クラスのプロパティが設定され、値が表示されます。</span><span class="sxs-lookup"><span data-stu-id="41b8a-151">The property in the base class is set, and the value is displayed.</span></span>

## <a name="next-steps"></a><span data-ttu-id="41b8a-152">次の手順</span><span class="sxs-lookup"><span data-stu-id="41b8a-152">Next Steps</span></span>

<span data-ttu-id="41b8a-153">オーバーロードされた `AddNumbers` 関数は、COM オブジェクトの基底クラスから継承されたメソッドと同じデータ型を持つように見えます。</span><span class="sxs-lookup"><span data-stu-id="41b8a-153">You may have noticed that the overloaded `AddNumbers` function appears to have the same data type as the method inherited from the base class of the COM object.</span></span> <span data-ttu-id="41b8a-154">これは、基底クラスのメソッドの引数とパラメーターが Visual Basic 6.0 で16ビット整数として定義されているのに対し、Visual Basic の以降のバージョンでは `Short` 型の16ビット整数として公開されているためです。</span><span class="sxs-lookup"><span data-stu-id="41b8a-154">This is because the arguments and parameters of the base class method are defined as 16-bit integers in Visual Basic 6.0, but they are exposed as 16-bit integers of type `Short` in later versions of Visual Basic.</span></span> <span data-ttu-id="41b8a-155">新しい関数は、32ビットの整数を受け取り、基底クラスの関数をオーバーロードします。</span><span class="sxs-lookup"><span data-stu-id="41b8a-155">The new function accepts 32-bit integers, and overloads the base class function.</span></span>

<span data-ttu-id="41b8a-156">COM オブジェクトを使用する場合は、パラメーターのサイズとデータ型を必ず確認してください。</span><span class="sxs-lookup"><span data-stu-id="41b8a-156">When working with COM objects, make sure that you verify the size and data types of parameters.</span></span> <span data-ttu-id="41b8a-157">たとえば、引数として Visual Basic 6.0 collection オブジェクトを受け取る COM オブジェクトを使用している場合、Visual Basic の新しいバージョンのコレクションを指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="41b8a-157">For example, when you are using a COM object that accepts a Visual Basic 6.0 collection object as an argument, you cannot provide a collection from a later version of Visual Basic.</span></span>

<span data-ttu-id="41b8a-158">COM クラスから継承されたプロパティとメソッドはオーバーライドできます。つまり、基本 COM クラスから継承されたプロパティまたはメソッドを置き換えるローカルプロパティまたはメソッドを宣言できます。</span><span class="sxs-lookup"><span data-stu-id="41b8a-158">Properties and methods inherited from COM classes can be overridden, meaning that you can declare a local property or method that replaces a property or method inherited from a base COM class.</span></span> <span data-ttu-id="41b8a-159">継承された COM プロパティをオーバーライドするための規則は、次の例外を除き、他のプロパティおよびメソッドをオーバーライドするための規則に似ています。</span><span class="sxs-lookup"><span data-stu-id="41b8a-159">The rules for overriding inherited COM properties are similar to the rules for overriding other properties and methods with the following exceptions:</span></span>

- <span data-ttu-id="41b8a-160">COM クラスから継承されたプロパティまたはメソッドをオーバーライドする場合は、継承された他のすべてのプロパティとメソッドをオーバーライドする必要があります。</span><span class="sxs-lookup"><span data-stu-id="41b8a-160">If you override any property or method inherited from a COM class, you must override all the other inherited properties and methods.</span></span>

- <span data-ttu-id="41b8a-161">`ByRef` パラメーターを使用するプロパティをオーバーライドすることはできません。</span><span class="sxs-lookup"><span data-stu-id="41b8a-161">Properties that use `ByRef` parameters cannot be overridden.</span></span>

## <a name="see-also"></a><span data-ttu-id="41b8a-162">参照</span><span class="sxs-lookup"><span data-stu-id="41b8a-162">See also</span></span>

- [<span data-ttu-id="41b8a-163">.NET Framework アプリケーションにおける COM 相互運用性</span><span class="sxs-lookup"><span data-stu-id="41b8a-163">COM Interoperability in .NET Framework Applications</span></span>](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md)
- [<span data-ttu-id="41b8a-164">Inherits ステートメント</span><span class="sxs-lookup"><span data-stu-id="41b8a-164">Inherits Statement</span></span>](../../../visual-basic/language-reference/statements/inherits-statement.md)
- [<span data-ttu-id="41b8a-165">Short データ型</span><span class="sxs-lookup"><span data-stu-id="41b8a-165">Short Data Type</span></span>](../../../visual-basic/language-reference/data-types/short-data-type.md)
