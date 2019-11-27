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
ms.openlocfilehash: 5d00aff07358a0c40159fde9c12c70e0842d848b
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74338616"
---
# <a name="walkthrough-creating-com-objects-with-visual-basic"></a><span data-ttu-id="3e6d7-102">チュートリアル : Visual Basic での COM オブジェクトの作成</span><span class="sxs-lookup"><span data-stu-id="3e6d7-102">Walkthrough: Creating COM Objects with Visual Basic</span></span>
<span data-ttu-id="3e6d7-103">新しいアプリケーションまたはコンポーネントを作成する場合は、.NET Framework アセンブリを作成することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="3e6d7-103">When creating new applications or components, it is best to create .NET Framework assemblies.</span></span> <span data-ttu-id="3e6d7-104">ただし、Visual Basic を使用すると、.NET Framework コンポーネントを COM に簡単に公開できます。</span><span class="sxs-lookup"><span data-stu-id="3e6d7-104">However, Visual Basic also makes it easy to expose a .NET Framework component to COM.</span></span> <span data-ttu-id="3e6d7-105">これにより、COM コンポーネントを必要とする以前のアプリケーションスイートに新しいコンポーネントを提供できるようになります。</span><span class="sxs-lookup"><span data-stu-id="3e6d7-105">This enables you to provide new components for earlier application suites that require COM components.</span></span> <span data-ttu-id="3e6d7-106">このチュートリアルでは、Visual Basic を使用して、COM クラステンプレートを使用するかどうかにかかわらず、.NET Framework オブジェクトを COM オブジェクトとして公開する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="3e6d7-106">This walkthrough demonstrates how to use Visual Basic to expose .NET Framework objects as COM objects, both with and without the COM class template.</span></span>  
  
 <span data-ttu-id="3e6d7-107">Com オブジェクトを公開する最も簡単な方法は、COM クラステンプレートを使用することです。</span><span class="sxs-lookup"><span data-stu-id="3e6d7-107">The easiest way to expose COM objects is by using the COM class template.</span></span> <span data-ttu-id="3e6d7-108">COM クラステンプレートは新しいクラスを作成し、クラスと相互運用性レイヤーを COM オブジェクトとして生成し、オペレーティングシステムに登録するようにプロジェクトを構成します。</span><span class="sxs-lookup"><span data-stu-id="3e6d7-108">The COM class template creates a new class, and then configures your project to generate the class and interoperability layer as a COM object and register it with the operating system.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3e6d7-109">Visual Basic で作成されたクラスをアンマネージコードで使用する COM オブジェクトとして公開することもできますが、これは真の COM オブジェクトではなく、Visual Basic では使用できません。</span><span class="sxs-lookup"><span data-stu-id="3e6d7-109">Although you can also expose a class created in Visual Basic as a COM object for unmanaged code to use, it is not a true COM object and cannot be used by Visual Basic.</span></span> <span data-ttu-id="3e6d7-110">詳細については、「 [.NET Framework アプリケーションでの COM 相互運用性](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3e6d7-110">For more information, see [COM Interoperability in .NET Framework Applications](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md).</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-com-object-by-using-the-com-class-template"></a><span data-ttu-id="3e6d7-111">COM クラステンプレートを使用して COM オブジェクトを作成するには</span><span class="sxs-lookup"><span data-stu-id="3e6d7-111">To create a COM object by using the COM class template</span></span>  
  
1. <span data-ttu-id="3e6d7-112">**[ファイル]** メニューの **[新しいプロジェクト]** をクリックして、新しい Windows アプリケーションプロジェクトを開きます。</span><span class="sxs-lookup"><span data-stu-id="3e6d7-112">Open a new Windows Application project from the **File** menu by clicking **New Project**.</span></span>  
  
2. <span data-ttu-id="3e6d7-113">**新しいプロジェクト** ダイアログボックスの **プロジェクトの種類** フィールドで、Windows が選択されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="3e6d7-113">In the **New Project** dialog box under the **Project Types** field, check that Windows is selected.</span></span> <span data-ttu-id="3e6d7-114">**[テンプレート]** ボックスの一覧から **[クラスライブラリ]** を選択し、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3e6d7-114">Select **Class Library** from the **Templates** list, and then click **OK**.</span></span> <span data-ttu-id="3e6d7-115">新しいプロジェクトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="3e6d7-115">The new project is displayed.</span></span>  
  
3. <span data-ttu-id="3e6d7-116">**[プロジェクト]** メニューの **[新しい項目の追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3e6d7-116">Select **Add New Item** from the **Project** menu.</span></span> <span data-ttu-id="3e6d7-117">**[新しい項目の追加]** ダイアログ ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="3e6d7-117">The **Add New Item** dialog box is displayed.</span></span>  
  
4. <span data-ttu-id="3e6d7-118">**[テンプレート]** ボックスの一覧から **[COM クラス]** を選択し、 **[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3e6d7-118">Select **COM Class** from the **Templates** list, and then click **Add**.</span></span> <span data-ttu-id="3e6d7-119">Visual Basic は、新しいクラスを追加し、COM 相互運用のために新しいプロジェクトを構成します。</span><span class="sxs-lookup"><span data-stu-id="3e6d7-119">Visual Basic adds a new class and configures the new project for COM interop.</span></span>  
  
5. <span data-ttu-id="3e6d7-120">プロパティ、メソッド、イベントなどのコードを COM クラスに追加します。</span><span class="sxs-lookup"><span data-stu-id="3e6d7-120">Add code such as properties, methods, and events to the COM class.</span></span>  
  
6. <span data-ttu-id="3e6d7-121">**[ビルド]** メニューの **[ビルドと]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="3e6d7-121">Select **Build ClassLibrary1** from the **Build** menu.</span></span> <span data-ttu-id="3e6d7-122">Visual Basic は、アセンブリをビルドし、オペレーティングシステムに COM オブジェクトを登録します。</span><span class="sxs-lookup"><span data-stu-id="3e6d7-122">Visual Basic builds the assembly and registers the COM object with the operating system.</span></span>  
  
## <a name="creating-com-objects-without-the-com-class-template"></a><span data-ttu-id="3e6d7-123">Com クラステンプレートを使用しない COM オブジェクトの作成</span><span class="sxs-lookup"><span data-stu-id="3e6d7-123">Creating COM Objects without the COM Class Template</span></span>  
 <span data-ttu-id="3e6d7-124">Com クラステンプレートを使用する代わりに、手動で COM クラスを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="3e6d7-124">You can also create a COM class manually instead of using the COM class template.</span></span> <span data-ttu-id="3e6d7-125">この手順は、コマンドラインから作業する場合や、COM オブジェクトの定義方法をより細かく制御する必要がある場合に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="3e6d7-125">This procedure is helpful when you are working from the command line or when you want more control over how COM objects are defined.</span></span>  
  
#### <a name="to-set-up-your-project-to-generate-a-com-object"></a><span data-ttu-id="3e6d7-126">COM オブジェクトを生成するようにプロジェクトを設定するには</span><span class="sxs-lookup"><span data-stu-id="3e6d7-126">To set up your project to generate a COM object</span></span>  
  
1. <span data-ttu-id="3e6d7-127">**[ファイル]** メニューの **[NewProject]** をクリックして、新しい Windows アプリケーションプロジェクトを開きます。</span><span class="sxs-lookup"><span data-stu-id="3e6d7-127">Open a new Windows Application project from the **File** menu by clicking **NewProject**.</span></span>  
  
2. <span data-ttu-id="3e6d7-128">**新しいプロジェクト** ダイアログボックスの **プロジェクトの種類** フィールドで、Windows が選択されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="3e6d7-128">In the **New Project** dialog box under the **Project Types** field, check that Windows is selected.</span></span> <span data-ttu-id="3e6d7-129">**[テンプレート]** ボックスの一覧から **[クラスライブラリ]** を選択し、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3e6d7-129">Select **Class Library** from the **Templates** list, and then click **OK**.</span></span> <span data-ttu-id="3e6d7-130">新しいプロジェクトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="3e6d7-130">The new project is displayed.</span></span>  
  
3. <span data-ttu-id="3e6d7-131">**ソリューション エクスプローラー**で、プロジェクトを右クリックして、 **[プロパティ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3e6d7-131">In **Solution Explorer**, right-click your project, and then click **Properties**.</span></span> <span data-ttu-id="3e6d7-132">**プロジェクトデザイナー**が表示されます。</span><span class="sxs-lookup"><span data-stu-id="3e6d7-132">The **Project Designer** is displayed.</span></span>  
  
4. <span data-ttu-id="3e6d7-133">**[コンパイル]** タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="3e6d7-133">Click the **Compile** tab.</span></span>  
  
5. <span data-ttu-id="3e6d7-134">[ **COM 相互運用機能に登録**する] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="3e6d7-134">Select the **Register for COM Interop** check box.</span></span>  
  
#### <a name="to-set-up-the-code-in-your-class-to-create-a-com-object"></a><span data-ttu-id="3e6d7-135">COM オブジェクトを作成するためにクラス内のコードを設定するには</span><span class="sxs-lookup"><span data-stu-id="3e6d7-135">To set up the code in your class to create a COM object</span></span>  
  
1. <span data-ttu-id="3e6d7-136">**ソリューションエクスプローラー**で、 **[Class1]** をダブルクリックしてコードを表示します。</span><span class="sxs-lookup"><span data-stu-id="3e6d7-136">In **Solution Explorer**, double-click **Class1.vb** to display its code.</span></span>  
  
2. <span data-ttu-id="3e6d7-137">クラスの名前を `ComClass1` に変更します。</span><span class="sxs-lookup"><span data-stu-id="3e6d7-137">Rename the class to `ComClass1`.</span></span>  
  
3. <span data-ttu-id="3e6d7-138">`ComClass1`に次の定数を追加します。</span><span class="sxs-lookup"><span data-stu-id="3e6d7-138">Add the following constants to `ComClass1`.</span></span> <span data-ttu-id="3e6d7-139">これらは、COM オブジェクトに必要なグローバル一意識別子 (GUID) 定数を格納します。</span><span class="sxs-lookup"><span data-stu-id="3e6d7-139">They will store the Globally Unique Identifier (GUID) constants that the COM objects are required to have.</span></span>  
  
     [!code-vb[VbVbalrInterop#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#2)]  
  
4. <span data-ttu-id="3e6d7-140">**[ツール]** メニューの **[GUID の作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3e6d7-140">On the **Tools** menu, click **Create Guid**.</span></span> <span data-ttu-id="3e6d7-141">**[GUID の作成]** ダイアログ ボックスで、 **[レジストリ形式]** をクリックし、 **[コピー]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3e6d7-141">In the **Create GUID** dialog box, click **Registry Format** and then click **Copy**.</span></span> <span data-ttu-id="3e6d7-142">**[終了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3e6d7-142">Click **Exit**.</span></span>  
  
5. <span data-ttu-id="3e6d7-143">`ClassId` の空の文字列を GUID に置き換え、先頭と末尾の中かっこを削除します。</span><span class="sxs-lookup"><span data-stu-id="3e6d7-143">Replace the empty string for the `ClassId` with the GUID, removing the leading and trailing braces.</span></span> <span data-ttu-id="3e6d7-144">たとえば、Guidgen.exe によって提供された GUID が `"{2C8B0AEE-02C9-486e-B809-C780A11530FE}"` 場合、コードは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="3e6d7-144">For example, if the GUID provided by Guidgen is `"{2C8B0AEE-02C9-486e-B809-C780A11530FE}"` then your code should appear as follows.</span></span>  
  
     [!code-vb[VbVbalrInterop#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#3)]  
  
6. <span data-ttu-id="3e6d7-145">次の例に示すように、`InterfaceId` と `EventsId` の定数に対して前の手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="3e6d7-145">Repeat the previous steps for the `InterfaceId` and `EventsId` constants, as in the following example.</span></span>  
  
     [!code-vb[VbVbalrInterop#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#4)]  
  
    > [!NOTE]
    > <span data-ttu-id="3e6d7-146">Guid が新規で一意であることを確認します。それ以外の場合、COM コンポーネントは他の COM コンポーネントと競合する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="3e6d7-146">Make sure that the GUIDs are new and unique; otherwise, your COM component could conflict with other COM components.</span></span>  
  
7. <span data-ttu-id="3e6d7-147">次の例に示すように、`ComClass` 属性を `ComClass1`に追加して、クラス ID、インターフェイス ID、およびイベント ID の Guid を指定します。</span><span class="sxs-lookup"><span data-stu-id="3e6d7-147">Add the `ComClass` attribute to `ComClass1`, specifying the GUIDs for the Class ID, Interface ID, and Events ID as in the following example:</span></span>  
  
     [!code-vb[VbVbalrInterop#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#5)]  
  
8. <span data-ttu-id="3e6d7-148">COM クラスにはパラメーターなしの `Public Sub New()` コンストラクターが必要です。または、クラスが正しく登録されません。</span><span class="sxs-lookup"><span data-stu-id="3e6d7-148">COM classes must have a parameterless `Public Sub New()` constructor, or the class will not register correctly.</span></span> <span data-ttu-id="3e6d7-149">パラメーターなしのコンストラクターをクラスに追加します。</span><span class="sxs-lookup"><span data-stu-id="3e6d7-149">Add a parameterless constructor to the class:</span></span>  
  
     [!code-vb[VbVbalrInterop#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#6)]  
  
9. <span data-ttu-id="3e6d7-150">プロパティ、メソッド、およびイベントをクラスに追加し、`End Class` ステートメントで終了します。</span><span class="sxs-lookup"><span data-stu-id="3e6d7-150">Add properties, methods, and events to the class, ending it with an `End Class` statement.</span></span> <span data-ttu-id="3e6d7-151">**[ビルド]** メニューの **[ソリューションのビルド]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="3e6d7-151">Select **Build Solution** from the **Build** menu.</span></span> <span data-ttu-id="3e6d7-152">Visual Basic は、アセンブリをビルドし、オペレーティングシステムに COM オブジェクトを登録します。</span><span class="sxs-lookup"><span data-stu-id="3e6d7-152">Visual Basic builds the assembly and registers the COM object with the operating system.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="3e6d7-153">Visual Basic で生成した COM オブジェクトは、実際の COM オブジェクトではないため、他の Visual Basic アプリケーションでは使用できません。</span><span class="sxs-lookup"><span data-stu-id="3e6d7-153">The COM objects you generate with Visual Basic cannot be used by other Visual Basic applications because they are not true COM objects.</span></span> <span data-ttu-id="3e6d7-154">そのような COM オブジェクトへの参照を追加しようとすると、エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="3e6d7-154">Attempts to add references to such COM objects will raise an error.</span></span> <span data-ttu-id="3e6d7-155">詳細については、「 [.NET Framework アプリケーションでの COM 相互運用性](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3e6d7-155">For details, see [COM Interoperability in .NET Framework Applications](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e6d7-156">参照</span><span class="sxs-lookup"><span data-stu-id="3e6d7-156">See also</span></span>

- <xref:Microsoft.VisualBasic.ComClassAttribute>
- [<span data-ttu-id="3e6d7-157">COM 相互運用</span><span class="sxs-lookup"><span data-stu-id="3e6d7-157">COM Interop</span></span>](../../../visual-basic/programming-guide/com-interop/index.md)
- [<span data-ttu-id="3e6d7-158">チュートリアル : COM オブジェクトによる継承の実装</span><span class="sxs-lookup"><span data-stu-id="3e6d7-158">Walkthrough: Implementing Inheritance with COM Objects</span></span>](../../../visual-basic/programming-guide/com-interop/walkthrough-implementing-inheritance-with-com-objects.md)
- [<span data-ttu-id="3e6d7-159">#Region ディレクティブ</span><span class="sxs-lookup"><span data-stu-id="3e6d7-159">#Region Directive</span></span>](../../../visual-basic/language-reference/directives/region-directive.md)
- [<span data-ttu-id="3e6d7-160">.NET Framework アプリケーションにおける COM 相互運用性</span><span class="sxs-lookup"><span data-stu-id="3e6d7-160">COM Interoperability in .NET Framework Applications</span></span>](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md)
- [<span data-ttu-id="3e6d7-161">相互運用性のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="3e6d7-161">Troubleshooting Interoperability</span></span>](../../../visual-basic/programming-guide/com-interop/troubleshooting-interoperability.md)
