---
title: 'チュートリアル: COM オブジェクトの作成'
ms.date: 07/20/2015
helpviewer_keywords:
- COM interop [Visual Basic], creating COM objects
- COM objects, creating
- COM interop [Visual Basic], walkthroughs
- object creation [Visual Basic], COM objects
- COM objects, walkthroughs
ms.assetid: 7b07a463-bc72-4392-9ba0-9dfcb697a44f
ms.openlocfilehash: 6ff23f73af384a1440bcebd4b6bac21714e01756
ms.sourcegitcommit: 0edbeb66d71b8df10fcb374cfca4d731b58ccdb2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "86051481"
---
# <a name="walkthrough-creating-com-objects-with-visual-basic"></a><span data-ttu-id="9984d-102">チュートリアル: Visual Basic での COM オブジェクトの作成</span><span class="sxs-lookup"><span data-stu-id="9984d-102">Walkthrough: Creating COM Objects with Visual Basic</span></span>
<span data-ttu-id="9984d-103">新しいアプリケーションまたはコンポーネントを作成する場合は、.NET Framework アセンブリを作成することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="9984d-103">When creating new applications or components, it is best to create .NET Framework assemblies.</span></span> <span data-ttu-id="9984d-104">ただし、Visual Basic を使用すると、COM への .NET Framework コンポーネントの公開も簡単になります。</span><span class="sxs-lookup"><span data-stu-id="9984d-104">However, Visual Basic also makes it easy to expose a .NET Framework component to COM.</span></span> <span data-ttu-id="9984d-105">これにより、COM コンポーネントを必要とする以前のアプリケーション スイートに対して新しいコンポーネントが提供できるようになります。</span><span class="sxs-lookup"><span data-stu-id="9984d-105">This enables you to provide new components for earlier application suites that require COM components.</span></span> <span data-ttu-id="9984d-106">このチュートリアルでは、Visual Basic を使用して、COM クラス テンプレートを使用するかどうかにかかわらず、.NET Framework オブジェクトを COM オブジェクトとして公開する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="9984d-106">This walkthrough demonstrates how to use Visual Basic to expose .NET Framework objects as COM objects, both with and without the COM class template.</span></span>  
  
 <span data-ttu-id="9984d-107">COM オブジェクトを公開する最も簡単な方法は、COM クラス テンプレートを使用することです。</span><span class="sxs-lookup"><span data-stu-id="9984d-107">The easiest way to expose COM objects is by using the COM class template.</span></span> <span data-ttu-id="9984d-108">このテンプレートでは、新しいクラスが作成され、クラスと相互運用性レイヤーを COM オブジェクトとして生成してオペレーティング システムに登録するようにプロジェクトが構成されます。</span><span class="sxs-lookup"><span data-stu-id="9984d-108">This template creates a new class, then configures your project to generate the class with an interoperability layer as a COM object, and register it with the operating system.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9984d-109">Visual Basic で作成されたクラスをアンマネージド コードで使用できるように COM オブジェクトとして公開することもできますが、これは実際の COM オブジェクトではなく、Visual Basic では使用できません。</span><span class="sxs-lookup"><span data-stu-id="9984d-109">Although you can also expose a class created in Visual Basic as a COM object for unmanaged code to use, it is not a true COM object and cannot be used by Visual Basic.</span></span> <span data-ttu-id="9984d-110">詳細については、「[.NET Framework アプリケーションにおける COM 相互運用性](com-interoperability-in-net-framework-applications.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9984d-110">For more information, see [COM Interoperability in .NET Framework Applications](com-interoperability-in-net-framework-applications.md).</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-com-object-by-using-the-com-class-template"></a><span data-ttu-id="9984d-111">COM クラス テンプレートを使用して COM オブジェクトを作成するには</span><span class="sxs-lookup"><span data-stu-id="9984d-111">To create a COM object by using the COM class template</span></span>  
  
1. <span data-ttu-id="9984d-112">**[新しいプロジェクト]** をクリックして、 **[ファイル]** メニューから新しい Windows アプリケーション プロジェクトを開きます。</span><span class="sxs-lookup"><span data-stu-id="9984d-112">Open a new Windows Application project from the **File** menu by clicking **New Project**.</span></span>  
  
2. <span data-ttu-id="9984d-113">**[新しいプロジェクト]** ダイアログ ボックスの **[プロジェクトの種類]** フィールドで、[Windows] が選択されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="9984d-113">In the **New Project** dialog box under the **Project Types** field, check that Windows is selected.</span></span> <span data-ttu-id="9984d-114">**[テンプレート]** の一覧から **[クラス ライブラリ]** を選択し、 **[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9984d-114">Select **Class Library** from the **Templates** list, and then click **OK**.</span></span> <span data-ttu-id="9984d-115">新しいプロジェクトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="9984d-115">The new project is displayed.</span></span>  
  
3. <span data-ttu-id="9984d-116">**[プロジェクト]** メニューの **[新しい項目の追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="9984d-116">Select **Add New Item** from the **Project** menu.</span></span> <span data-ttu-id="9984d-117">**[新しい項目の追加]** ダイアログ ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="9984d-117">The **Add New Item** dialog box is displayed.</span></span>  
  
4. <span data-ttu-id="9984d-118">**[テンプレート]** の一覧から **[COM クラス]** を選択し、 **[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9984d-118">Select **COM Class** from the **Templates** list, and then click **Add**.</span></span> <span data-ttu-id="9984d-119">Visual Basic は、新しいクラスを追加し、COM 相互運用のための新しいプロジェクトを構成します。</span><span class="sxs-lookup"><span data-stu-id="9984d-119">Visual Basic adds a new class and configures the new project for COM interop.</span></span>  
  
5. <span data-ttu-id="9984d-120">プロパティ、メソッド、イベントなどのコードを COM クラスに追加します。</span><span class="sxs-lookup"><span data-stu-id="9984d-120">Add code such as properties, methods, and events to the COM class.</span></span>  
  
6. <span data-ttu-id="9984d-121">**[ビルド]** メニューから **[ClassLibrary1 のビルド]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="9984d-121">Select **Build ClassLibrary1** from the **Build** menu.</span></span> <span data-ttu-id="9984d-122">Visual Basic は、アセンブリをビルドし、オペレーティング システムに COM オブジェクトを登録します。</span><span class="sxs-lookup"><span data-stu-id="9984d-122">Visual Basic builds the assembly and registers the COM object with the operating system.</span></span>  
  
## <a name="creating-com-objects-without-the-com-class-template"></a><span data-ttu-id="9984d-123">COM クラス テンプレートを使用しない COM オブジェクトの作成</span><span class="sxs-lookup"><span data-stu-id="9984d-123">Creating COM Objects without the COM Class Template</span></span>  
 <span data-ttu-id="9984d-124">COM クラス テンプレートを使用する代わりに、手動で COM クラスを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="9984d-124">You can also create a COM class manually instead of using the COM class template.</span></span> <span data-ttu-id="9984d-125">この手順は、コマンド ラインから作業する場合や、COM オブジェクトの定義方法をより細かく制御する必要がある場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="9984d-125">This procedure is helpful when you are working from the command line or when you want more control over how COM objects are defined.</span></span>  
  
#### <a name="to-set-up-your-project-to-generate-a-com-object"></a><span data-ttu-id="9984d-126">COM オブジェクトを生成するようにプロジェクトを設定するには</span><span class="sxs-lookup"><span data-stu-id="9984d-126">To set up your project to generate a COM object</span></span>  
  
1. <span data-ttu-id="9984d-127">**[新しいプロジェクト]** をクリックして、 **[ファイル]** メニューから新しい Windows アプリケーション プロジェクトを開きます。</span><span class="sxs-lookup"><span data-stu-id="9984d-127">Open a new Windows Application project from the **File** menu by clicking **NewProject**.</span></span>  
  
2. <span data-ttu-id="9984d-128">**[新しいプロジェクト]** ダイアログ ボックスの **[プロジェクトの種類]** フィールドで、[Windows] が選択されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="9984d-128">In the **New Project** dialog box under the **Project Types** field, check that Windows is selected.</span></span> <span data-ttu-id="9984d-129">**[テンプレート]** の一覧から **[クラス ライブラリ]** を選択し、 **[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9984d-129">Select **Class Library** from the **Templates** list, and then click **OK**.</span></span> <span data-ttu-id="9984d-130">新しいプロジェクトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="9984d-130">The new project is displayed.</span></span>  
  
3. <span data-ttu-id="9984d-131">**ソリューション エクスプローラー**で、プロジェクトを右クリックして、 **[プロパティ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9984d-131">In **Solution Explorer**, right-click your project, and then click **Properties**.</span></span> <span data-ttu-id="9984d-132">**プロジェクト デザイナー**が表示されます。</span><span class="sxs-lookup"><span data-stu-id="9984d-132">The **Project Designer** is displayed.</span></span>  
  
4. <span data-ttu-id="9984d-133">**[コンパイル]** タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="9984d-133">Click the **Compile** tab.</span></span>  
  
5. <span data-ttu-id="9984d-134">**[COM の相互運用機能に登録]** チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="9984d-134">Select the **Register for COM Interop** check box.</span></span>  
  
#### <a name="to-set-up-the-code-in-your-class-to-create-a-com-object"></a><span data-ttu-id="9984d-135">COM オブジェクトを作成するためにクラス内のコードを設定するには</span><span class="sxs-lookup"><span data-stu-id="9984d-135">To set up the code in your class to create a COM object</span></span>  
  
1. <span data-ttu-id="9984d-136">**ソリューション エクスプローラー**で、 **[Class1.vb]** をダブルクリックしてコードを表示します。</span><span class="sxs-lookup"><span data-stu-id="9984d-136">In **Solution Explorer**, double-click **Class1.vb** to display its code.</span></span>  
  
2. <span data-ttu-id="9984d-137">クラスの名前を `ComClass1` に変更します。</span><span class="sxs-lookup"><span data-stu-id="9984d-137">Rename the class to `ComClass1`.</span></span>  
  
3. <span data-ttu-id="9984d-138">次の定数を `ComClass1` に追加します。</span><span class="sxs-lookup"><span data-stu-id="9984d-138">Add the following constants to `ComClass1`.</span></span> <span data-ttu-id="9984d-139">これにより、COM オブジェクトに必要なグローバル一意識別子 (GUID) 定数が格納されます。</span><span class="sxs-lookup"><span data-stu-id="9984d-139">They will store the Globally Unique Identifier (GUID) constants that the COM objects are required to have.</span></span>  
  
     [!code-vb[VbVbalrInterop#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#2)]  
  
4. <span data-ttu-id="9984d-140">**[ツール]** メニューの **[GUID の作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9984d-140">On the **Tools** menu, click **Create Guid**.</span></span> <span data-ttu-id="9984d-141">**[GUID の作成]** ダイアログ ボックスで、 **[レジストリ形式]** をクリックし、 **[コピー]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9984d-141">In the **Create GUID** dialog box, click **Registry Format** and then click **Copy**.</span></span> <span data-ttu-id="9984d-142">**[終了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9984d-142">Click **Exit**.</span></span>  
  
5. <span data-ttu-id="9984d-143">`ClassId` の空の文字列を GUID に置き換え、先頭と末尾の中かっこを削除します。</span><span class="sxs-lookup"><span data-stu-id="9984d-143">Replace the empty string for the `ClassId` with the GUID, removing the leading and trailing braces.</span></span> <span data-ttu-id="9984d-144">たとえば、Guidgen によって提供された GUID が `"{2C8B0AEE-02C9-486e-B809-C780A11530FE}"` の場合、コードは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="9984d-144">For example, if the GUID provided by Guidgen is `"{2C8B0AEE-02C9-486e-B809-C780A11530FE}"` then your code should appear as follows.</span></span>  
  
     [!code-vb[VbVbalrInterop#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#3)]  
  
6. <span data-ttu-id="9984d-145">次の例に示すように、`InterfaceId` と `EventsId` の定数に対して前のステップを繰り返します。</span><span class="sxs-lookup"><span data-stu-id="9984d-145">Repeat the previous steps for the `InterfaceId` and `EventsId` constants, as in the following example.</span></span>  
  
     [!code-vb[VbVbalrInterop#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#4)]  
  
    > [!NOTE]
    > <span data-ttu-id="9984d-146">GUID が新しく、一意であることを確認します。そうでない場合、COM コンポーネントは他の COM コンポーネントと競合する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="9984d-146">Make sure that the GUIDs are new and unique; otherwise, your COM component could conflict with other COM components.</span></span>  
  
7. <span data-ttu-id="9984d-147">次の例に示すように、`ComClass` 属性を `ComClass1` に追加して、クラス ID、インターフェイス ID、およびイベント ID の GUID を指定します。</span><span class="sxs-lookup"><span data-stu-id="9984d-147">Add the `ComClass` attribute to `ComClass1`, specifying the GUIDs for the Class ID, Interface ID, and Events ID as in the following example:</span></span>  
  
     [!code-vb[VbVbalrInterop#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#5)]  
  
8. <span data-ttu-id="9984d-148">COM クラスにはパラメーターなしの `Public Sub New()` コンストラクターが必要です。そうでない場合、クラスが正しく登録されません。</span><span class="sxs-lookup"><span data-stu-id="9984d-148">COM classes must have a parameterless `Public Sub New()` constructor, or the class will not register correctly.</span></span> <span data-ttu-id="9984d-149">クラスにパラメーターなしのコンストラクターを追加します。</span><span class="sxs-lookup"><span data-stu-id="9984d-149">Add a parameterless constructor to the class:</span></span>  
  
     [!code-vb[VbVbalrInterop#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#6)]  
  
9. <span data-ttu-id="9984d-150">プロパティ、メソッド、およびイベントをクラスに追加し、`End Class` ステートメントで終了します。</span><span class="sxs-lookup"><span data-stu-id="9984d-150">Add properties, methods, and events to the class, ending it with an `End Class` statement.</span></span> <span data-ttu-id="9984d-151">**[ビルド]** メニューの **[ソリューションのビルド]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9984d-151">Select **Build Solution** from the **Build** menu.</span></span> <span data-ttu-id="9984d-152">Visual Basic は、アセンブリをビルドし、オペレーティング システムに COM オブジェクトを登録します。</span><span class="sxs-lookup"><span data-stu-id="9984d-152">Visual Basic builds the assembly and registers the COM object with the operating system.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="9984d-153">Visual Basic で生成した COM オブジェクトは、実際の COM オブジェクトではないため、他の Visual Basic アプリケーションでは使用できません。</span><span class="sxs-lookup"><span data-stu-id="9984d-153">The COM objects you generate with Visual Basic cannot be used by other Visual Basic applications because they are not true COM objects.</span></span> <span data-ttu-id="9984d-154">そのような COM オブジェクトに参照を追加しようとすると、エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="9984d-154">Attempts to add references to such COM objects will raise an error.</span></span> <span data-ttu-id="9984d-155">詳細については、「[.NET Framework アプリケーションにおける COM 相互運用性](com-interoperability-in-net-framework-applications.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9984d-155">For details, see [COM Interoperability in .NET Framework Applications](com-interoperability-in-net-framework-applications.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9984d-156">関連項目</span><span class="sxs-lookup"><span data-stu-id="9984d-156">See also</span></span>

- <xref:Microsoft.VisualBasic.ComClassAttribute>
- [<span data-ttu-id="9984d-157">COM 相互運用</span><span class="sxs-lookup"><span data-stu-id="9984d-157">COM Interop</span></span>](index.md)
- [<span data-ttu-id="9984d-158">チュートリアル: COM オブジェクトによる継承の実装</span><span class="sxs-lookup"><span data-stu-id="9984d-158">Walkthrough: Implementing Inheritance with COM Objects</span></span>](walkthrough-implementing-inheritance-with-com-objects.md)
- [<span data-ttu-id="9984d-159">#Region ディレクティブ</span><span class="sxs-lookup"><span data-stu-id="9984d-159">#Region Directive</span></span>](../../language-reference/directives/region-directive.md)
- [<span data-ttu-id="9984d-160">.NET Framework アプリケーションにおける COM 相互運用性</span><span class="sxs-lookup"><span data-stu-id="9984d-160">COM Interoperability in .NET Framework Applications</span></span>](com-interoperability-in-net-framework-applications.md)
- [<span data-ttu-id="9984d-161">相互運用性のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="9984d-161">Troubleshooting Interoperability</span></span>](troubleshooting-interoperability.md)
