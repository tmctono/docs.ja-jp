---
title: 'チュートリアル: Visual Basic による Windows フォーム コントロールからの継承'
ms.date: 03/30/2017
dev_langs:
- vb
helpviewer_keywords:
- inheritance [Windows Forms], custom controls
- inheritance [Windows Forms], control
- Windows Forms controls, inheritance
- inheritance [Windows Forms], walkthroughs
- custom controls [Windows Forms], inheritance
ms.assetid: fb58d7c8-b702-4478-ad31-b00cae118882
ms.openlocfilehash: 378d7b0c67791e6c48e9859e0546594df3ccc85e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69931014"
---
# <a name="walkthrough-inheriting-from-a-windows-forms-control-with-visual-basic"></a><span data-ttu-id="f26a5-102">チュートリアル: Visual Basic による Windows フォーム コントロールからの継承</span><span class="sxs-lookup"><span data-stu-id="f26a5-102">Walkthrough: Inheriting from a Windows Forms Control with Visual Basic</span></span>
<span data-ttu-id="f26a5-103">Visual Basic を使用すると、*継承*によって強力なカスタムコントロールを作成できます。</span><span class="sxs-lookup"><span data-stu-id="f26a5-103">With Visual Basic, you can create powerful custom controls through *inheritance*.</span></span> <span data-ttu-id="f26a5-104">継承を使用すると、標準の Windows フォーム コントロールの固有の機能をすべて保持しながら、カスタム機能も組み込んだコントロールを作成できます。</span><span class="sxs-lookup"><span data-stu-id="f26a5-104">Through inheritance you are able to create controls that retain all of the inherent functionality of standard Windows Forms controls but also incorporate custom functionality.</span></span> <span data-ttu-id="f26a5-105">このチュートリアルでは、`ValueButton` という単純な継承されたコントロールを作成します。</span><span class="sxs-lookup"><span data-stu-id="f26a5-105">In this walkthrough, you will create a simple inherited control called `ValueButton`.</span></span> <span data-ttu-id="f26a5-106">このボタンは、標準の Windows フォーム<xref:System.Windows.Forms.Button>コントロールから機能を継承し、と呼ば`ButtonValue`れるカスタムプロパティを公開します。</span><span class="sxs-lookup"><span data-stu-id="f26a5-106">This button will inherit functionality from the standard Windows Forms <xref:System.Windows.Forms.Button> control, and will expose a custom property called `ButtonValue`.</span></span>

## <a name="creating-the-project"></a><span data-ttu-id="f26a5-107">プロジェクトの作成</span><span class="sxs-lookup"><span data-stu-id="f26a5-107">Creating the Project</span></span>
 <span data-ttu-id="f26a5-108">新しいプロジェクトを作成するときは、ルート名前空間、アセンブリ名、プロジェクト名を設定し、既定のコンポーネントが適切な名前空間に含まれるようにするために、プロジェクトの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="f26a5-108">When you create a new project, you specify its name in order to set the root namespace, assembly name, and project name, and to ensure that the default component will be in the correct namespace.</span></span>

### <a name="to-create-the-valuebuttonlib-control-library-and-the-valuebutton-control"></a><span data-ttu-id="f26a5-109">ValueButtonLib コントロール ライブラリと ValueButton コントロールを作成するには</span><span class="sxs-lookup"><span data-stu-id="f26a5-109">To create the ValueButtonLib control library and the ValueButton control</span></span>

1. <span data-ttu-id="f26a5-110">**[ファイル]** メニューの **[新規作成]** をポイントし、 **[プロジェクト]** をクリックして **[新しいプロジェクト]** ダイアログ ボックスを開きます。</span><span class="sxs-lookup"><span data-stu-id="f26a5-110">On the **File** menu, point to **New** and then click **Project** to open the **New Project** dialog box.</span></span>

2. <span data-ttu-id="f26a5-111">Visual Basic プロジェクトの一覧から **[Windows フォームコントロールライブラリ]** プロジェクトテンプレートを選択し、 `ValueButtonLib` **[名前]** ボックスに「」と入力します。</span><span class="sxs-lookup"><span data-stu-id="f26a5-111">Select the **Windows Forms Control Library** project template from the list of Visual Basic projects, and type `ValueButtonLib` in the **Name** box.</span></span>

     <span data-ttu-id="f26a5-112">プロジェクト名 `ValueButtonLib` は、既定でルート名前空間にも割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="f26a5-112">The project name, `ValueButtonLib`, is also assigned to the root namespace by default.</span></span> <span data-ttu-id="f26a5-113">ルート名前空間は、アセンブリ内のコンポーネント名の修飾に使用されます。</span><span class="sxs-lookup"><span data-stu-id="f26a5-113">The root namespace is used to qualify the names of components in the assembly.</span></span> <span data-ttu-id="f26a5-114">たとえば、`ValueButton` という名前のコンポーネントが 2 つのアセンブリに含まれている場合、`ValueButtonLib.ValueButton` を使用して目的の `ValueButton` コンポーネントを指定できます。</span><span class="sxs-lookup"><span data-stu-id="f26a5-114">For example, if two assemblies provide components named `ValueButton`, you can specify your `ValueButton` component using `ValueButtonLib.ValueButton`.</span></span> <span data-ttu-id="f26a5-115">詳細については、「[Visual Basic における名前空間](../../../visual-basic/programming-guide/program-structure/namespaces.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f26a5-115">For more information, see [Namespaces in Visual Basic](../../../visual-basic/programming-guide/program-structure/namespaces.md).</span></span>

3. <span data-ttu-id="f26a5-116">**ソリューション エクスプローラー**で、 **[UserControl1.vb]** を右クリックし、ショートカット メニューの **[名前の変更]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f26a5-116">In **Solution Explorer**, right-click **UserControl1.vb**, then choose **Rename** from the shortcut menu.</span></span> <span data-ttu-id="f26a5-117">ファイル名を `ValueButton.vb` に変更します。</span><span class="sxs-lookup"><span data-stu-id="f26a5-117">Change the file name to `ValueButton.vb`.</span></span> <span data-ttu-id="f26a5-118">コード要素 "UserControl1" へのすべての参照の名前を変更するかどうかをたずねられたら、 **[はい]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f26a5-118">Click the **Yes** button when you are asked if you want to rename all references to the code element 'UserControl1'.</span></span>

4. <span data-ttu-id="f26a5-119">**ソリューション エクスプローラー**で、 **[すべてのファイルを表示]** ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="f26a5-119">In **Solution Explorer**, click the **Show All Files** button.</span></span>

5. <span data-ttu-id="f26a5-120">**[ValueButton.vb]** ノードを開いて、デザイナーによって生成されたコード ファイル (**ValueButton.Designer.vb**) を表示します。</span><span class="sxs-lookup"><span data-stu-id="f26a5-120">Open the **ValueButton.vb** node to display the designer-generated code file, **ValueButton.Designer.vb**.</span></span> <span data-ttu-id="f26a5-121">このファイルを**コード エディター**で開きます。</span><span class="sxs-lookup"><span data-stu-id="f26a5-121">Open this file in the **Code Editor**.</span></span>

6. <span data-ttu-id="f26a5-122">ステートメントを`Partial Public Class ValueButton`見つけて、このコントロールの継承<xref:System.Windows.Forms.UserControl>元の型をに<xref:System.Windows.Forms.Button>変更します。 `Class`</span><span class="sxs-lookup"><span data-stu-id="f26a5-122">Locate the `Class` statement, `Partial Public Class ValueButton`, and change the type from which this control inherits from <xref:System.Windows.Forms.UserControl> to <xref:System.Windows.Forms.Button>.</span></span> <span data-ttu-id="f26a5-123">これにより、継承されたコントロールが<xref:System.Windows.Forms.Button>コントロールのすべての機能を継承できるようになります。</span><span class="sxs-lookup"><span data-stu-id="f26a5-123">This allows your inherited control to inherit all the functionality of the <xref:System.Windows.Forms.Button> control.</span></span>

7. <span data-ttu-id="f26a5-124">メソッドを見つけて、プロパティを<xref:System.Windows.Forms.ContainerControl.AutoScaleMode%2A>割り当てる行を削除します。 `InitializeComponent`</span><span class="sxs-lookup"><span data-stu-id="f26a5-124">Locate the `InitializeComponent` method and remove the line that assigns the <xref:System.Windows.Forms.ContainerControl.AutoScaleMode%2A> property.</span></span> <span data-ttu-id="f26a5-125">このプロパティは<xref:System.Windows.Forms.Button>コントロールに存在しません。</span><span class="sxs-lookup"><span data-stu-id="f26a5-125">This property does not exist in the <xref:System.Windows.Forms.Button> control.</span></span>

8. <span data-ttu-id="f26a5-126">**[ファイル]** メニューの **[すべて保存]** をクリックして、プロジェクトを保存します。</span><span class="sxs-lookup"><span data-stu-id="f26a5-126">From the **File** menu, choose **Save All** to save the project.</span></span>

     <span data-ttu-id="f26a5-127">ビジュアル デザイナーは使用できなくなっていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="f26a5-127">Note that a visual designer is no longer available.</span></span> <span data-ttu-id="f26a5-128">コントロールは<xref:System.Windows.Forms.Button>独自の描画を行うため、デザイナーで外観を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="f26a5-128">Because the <xref:System.Windows.Forms.Button> control does its own painting, you are unable to modify its appearance in the designer.</span></span> <span data-ttu-id="f26a5-129">ビジュアル表現は、コード内で変更されない限り、から継承したクラス (つまり<xref:System.Windows.Forms.Button>、) とまったく同じになります。</span><span class="sxs-lookup"><span data-stu-id="f26a5-129">Its visual representation will be exactly the same as that of the class it inherits from (that is, <xref:System.Windows.Forms.Button>) unless modified in the code.</span></span>

> [!NOTE]
> <span data-ttu-id="f26a5-130">UI 要素のないコンポーネントをデザイン サーフェイスに追加することは可能です。</span><span class="sxs-lookup"><span data-stu-id="f26a5-130">You can still add components, which have no UI elements, to the design surface.</span></span>

## <a name="adding-a-property-to-your-inherited-control"></a><span data-ttu-id="f26a5-131">継承されたコントロールへのプロパティの追加</span><span class="sxs-lookup"><span data-stu-id="f26a5-131">Adding a Property to Your Inherited Control</span></span>
 <span data-ttu-id="f26a5-132">継承された Windows フォーム コントロールの考えられる用途の 1 つとして、外観と動作 (ルック アンド フィール) は標準の Windows フォーム コントロールと同じでありながら、カスタム プロパティを公開するコントロールの作成があります。</span><span class="sxs-lookup"><span data-stu-id="f26a5-132">One possible use of inherited Windows Forms controls is the creation of controls that are identical in appearance and behavior (look and feel) to standard Windows Forms controls, but expose custom properties.</span></span> <span data-ttu-id="f26a5-133">このセクションでは、`ButtonValue` というプロパティをコントロールに追加します。</span><span class="sxs-lookup"><span data-stu-id="f26a5-133">In this section, you will add a property called `ButtonValue` to your control.</span></span>

### <a name="to-add-the-value-property"></a><span data-ttu-id="f26a5-134">Value プロパティを追加するには</span><span class="sxs-lookup"><span data-stu-id="f26a5-134">To add the Value property</span></span>

1. <span data-ttu-id="f26a5-135">**ソリューション エクスプローラー**で、 **[ValueButton.vb]** を右クリックし、ショートカット メニューの **[コードの表示]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f26a5-135">In **Solution Explorer**, right-click **ValueButton.vb**, and then click **View Code** from the shortcut menu.</span></span>

2. <span data-ttu-id="f26a5-136">`Public Class ValueButton` ステートメントを探します。</span><span class="sxs-lookup"><span data-stu-id="f26a5-136">Locate the `Public Class ValueButton` statement.</span></span> <span data-ttu-id="f26a5-137">このステートメントの直後に、次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="f26a5-137">Immediately beneath this statement, type the following code:</span></span>

    ```vb
    ' Creates the private variable that will store the value of your
    ' property.
    Private varValue as integer
    ' Declares the property.
    Property ButtonValue() as Integer
    ' Sets the method for retrieving the value of your property.
       Get
          Return varValue
       End Get
    ' Sets the method for setting the value of your property.
       Set(ByVal Value as Integer)
          varValue = Value
       End Set
    End Property
    ```

     <span data-ttu-id="f26a5-138">このコードでは、`ButtonValue` プロパティを格納し、取得するメソッドを設定しています。</span><span class="sxs-lookup"><span data-stu-id="f26a5-138">This code sets the methods by which the `ButtonValue` property is stored and retrieved.</span></span> <span data-ttu-id="f26a5-139">`Get` ステートメントは、返された値を `varValue` プライベート変数に格納されている値に設定します。`Set` ステートメントは、`Value` キーワードを使用してプライベート変数の値を設定します。</span><span class="sxs-lookup"><span data-stu-id="f26a5-139">The `Get` statement sets the value returned to the value that is stored in the private variable `varValue`, and the `Set` statement sets the value of the private variable by use of the `Value` keyword.</span></span>

3. <span data-ttu-id="f26a5-140">**[ファイル]** メニューの **[すべて保存]** をクリックして、プロジェクトを保存します。</span><span class="sxs-lookup"><span data-stu-id="f26a5-140">From the **File** menu, choose **Save All** to save the project.</span></span>

## <a name="testing-your-control"></a><span data-ttu-id="f26a5-141">コントロールのテスト</span><span class="sxs-lookup"><span data-stu-id="f26a5-141">Testing Your Control</span></span>
 <span data-ttu-id="f26a5-142">コントロールはスタンドアロン プロジェクトではないため、コンテナー内でホストする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f26a5-142">Controls are not stand-alone projects; they must be hosted in a container.</span></span> <span data-ttu-id="f26a5-143">コントロールをテストするには、コントロールを実行するテスト プロジェクトを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f26a5-143">In order to test your control, you must provide a test project for it to run in.</span></span> <span data-ttu-id="f26a5-144">また、コントロールをビルド (コンパイル) して、テスト プロジェクトからアクセスできるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f26a5-144">You must also make your control accessible to the test project by building (compiling) it.</span></span> <span data-ttu-id="f26a5-145">このセクションでは、コントロールをビルドし、Windows フォームでテストします。</span><span class="sxs-lookup"><span data-stu-id="f26a5-145">In this section, you will build your control and test it in a Windows Form.</span></span>

### <a name="to-build-your-control"></a><span data-ttu-id="f26a5-146">コントロールをビルドするには</span><span class="sxs-lookup"><span data-stu-id="f26a5-146">To build your control</span></span>

1. <span data-ttu-id="f26a5-147">**[ビルド]** メニューの **[ソリューションのビルド]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f26a5-147">On the **Build** menu, click **Build Solution**.</span></span>

     <span data-ttu-id="f26a5-148">コンパイル エラーも警告も発生せずに、ビルドが正常に完了します。</span><span class="sxs-lookup"><span data-stu-id="f26a5-148">The build should be successful with no compiler errors or warnings.</span></span>

### <a name="to-create-a-test-project"></a><span data-ttu-id="f26a5-149">テスト プロジェクトを作成するには</span><span class="sxs-lookup"><span data-stu-id="f26a5-149">To create a test project</span></span>

1. <span data-ttu-id="f26a5-150">**[ファイル]** メニューの **[追加]** をポイントし、 **[新しいプロジェクト]** をクリックして **[新しいプロジェクトの追加]** ダイアログ ボックスを開きます。</span><span class="sxs-lookup"><span data-stu-id="f26a5-150">On the **File** menu, point to **Add** and then click **New Project** to open the **Add New Project** dialog box.</span></span>

2. <span data-ttu-id="f26a5-151">Visual Basic プロジェクト ノードを選択し、 **Windows フォームアプリケーション** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f26a5-151">Select the Visual Basic projects node, and click **Windows Forms Application**.</span></span>

3. <span data-ttu-id="f26a5-152">**[名前]** ボックスに「 `Test`」と入力します。</span><span class="sxs-lookup"><span data-stu-id="f26a5-152">In the **Name** box, type `Test`.</span></span>

4. <span data-ttu-id="f26a5-153">**ソリューション エクスプローラー**で、 **[すべてのファイルを表示]** ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="f26a5-153">In **Solution Explorer**, click the **Show All Files** button.</span></span>

5. <span data-ttu-id="f26a5-154">**ソリューション エクスプローラー**で、テスト プロジェクトの **[参照設定]** ノードを右クリックし、ショートカット メニューの **[参照の追加]** をクリックして **[参照の追加]** ダイアログ ボックスを表示します。</span><span class="sxs-lookup"><span data-stu-id="f26a5-154">In **Solution Explorer**, right-click the **References** node for your test project, then select **Add Reference** from the shortcut menu to display the **Add Reference** dialog box.</span></span>

6. <span data-ttu-id="f26a5-155">**[プロジェクト]** タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="f26a5-155">Click the **Projects** tab.</span></span>

7. <span data-ttu-id="f26a5-156">**[プロジェクト]** というラベルのタブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="f26a5-156">Click the tab labeled **Projects**.</span></span> <span data-ttu-id="f26a5-157">**[プロジェクト名]** に `ValueButtonLib` プロジェクトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f26a5-157">Your `ValueButtonLib` project will be listed under **Project Name**.</span></span> <span data-ttu-id="f26a5-158">プロジェクトをダブルクリックして、テスト プロジェクトへの参照を追加します。</span><span class="sxs-lookup"><span data-stu-id="f26a5-158">Double-click the project to add the reference to the test project.</span></span>

8. <span data-ttu-id="f26a5-159">**ソリューション エクスプローラー**で、 **[Test]** を右クリックし、 **[ビルド]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f26a5-159">In **Solution Explorer,** right-click **Test** and select **Build**.</span></span>

### <a name="to-add-your-control-to-the-form"></a><span data-ttu-id="f26a5-160">コントロールをフォームに追加するには</span><span class="sxs-lookup"><span data-stu-id="f26a5-160">To add your control to the form</span></span>

1. <span data-ttu-id="f26a5-161">**ソリューション エクスプローラー**で、 **[Form1.vb]** を右クリックし、ショートカット メニューの **[デザイナーの表示]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f26a5-161">In **Solution Explorer**, right-click **Form1.vb** and choose **View Designer** from the shortcut menu.</span></span>

2. <span data-ttu-id="f26a5-162">**ツールボックス**の **[ValueButtonLib コンポーネント]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f26a5-162">In the **Toolbox**, click **ValueButtonLib Components**.</span></span> <span data-ttu-id="f26a5-163">**[ValueButton]** をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="f26a5-163">Double-click **ValueButton**.</span></span>

     <span data-ttu-id="f26a5-164">**ValueButton** がフォームに表示されます。</span><span class="sxs-lookup"><span data-stu-id="f26a5-164">A **ValueButton** appears on the form.</span></span>

3. <span data-ttu-id="f26a5-165">**[ValueButton]** を右クリックし、ショートカット メニューの **[プロパティ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f26a5-165">Right-click the **ValueButton** and select **Properties** from the shortcut menu.</span></span>

4. <span data-ttu-id="f26a5-166">**[プロパティ]** ウィンドウで、このコントロールのプロパティを調べます。</span><span class="sxs-lookup"><span data-stu-id="f26a5-166">In the **Properties** window, examine the properties of this control.</span></span> <span data-ttu-id="f26a5-167">プロパティは、追加のプロパティである `ButtonValue` がある点を除き、標準ボタンで公開されるプロパティと同じです。</span><span class="sxs-lookup"><span data-stu-id="f26a5-167">Note that they are identical to the properties exposed by a standard button, except that there is an additional property, `ButtonValue`.</span></span>

5. <span data-ttu-id="f26a5-168">`ButtonValue` プロパティを `5`に設定します。</span><span class="sxs-lookup"><span data-stu-id="f26a5-168">Set the `ButtonValue` property to `5`.</span></span>

6. <span data-ttu-id="f26a5-169">**ツールボックス**の **[すべての Windows フォーム]** タブで、[ <xref:System.Windows.Forms.Label>ラベル] をダブルクリックしてフォームにコントロールを追加します。</span><span class="sxs-lookup"><span data-stu-id="f26a5-169">On the **All Windows Forms** tab of the **Toolbox**, double-click **Label** to add a <xref:System.Windows.Forms.Label> control to your form.</span></span>

7. <span data-ttu-id="f26a5-170">ラベルをフォームの中央に配置し直します。</span><span class="sxs-lookup"><span data-stu-id="f26a5-170">Relocate the label to the center of the form.</span></span>

8. <span data-ttu-id="f26a5-171">`ValueButton1` をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="f26a5-171">Double-click `ValueButton1`.</span></span>

     <span data-ttu-id="f26a5-172">**コード エディター**が開き、`ValueButton1_Click` イベントが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f26a5-172">The **Code Editor** opens to the `ValueButton1_Click` event.</span></span>

9. <span data-ttu-id="f26a5-173">次のコード行を入力します。</span><span class="sxs-lookup"><span data-stu-id="f26a5-173">Type the following line of code.</span></span>

    ```vb
    Label1.Text = CStr(ValueButton1.ButtonValue)
    ```

10. <span data-ttu-id="f26a5-174">**ソリューション エクスプローラー**で、 **[Test]** を右クリックし、ショートカット メニューの **[スタートアップ プロジェクトに設定]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f26a5-174">In **Solution Explorer**, right-click **Test**, and choose **Set as Startup Project** from the shortcut menu.</span></span>

11. <span data-ttu-id="f26a5-175">**[デバッグ]** メニューの **[デバッグの開始]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f26a5-175">From the **Debug** menu, select **Start Debugging**.</span></span>

     <span data-ttu-id="f26a5-176">`Form1` が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f26a5-176">`Form1` appears.</span></span>

12. <span data-ttu-id="f26a5-177">[`Valuebutton1`] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f26a5-177">Click `Valuebutton1`.</span></span>

     <span data-ttu-id="f26a5-178">`Label1` に数字の "5" が表示されます。これは、継承されたコントロールの `ButtonValue` プロパティが、`ValueButton1_Click` メソッドによって `Label1` に渡されたことを示しています。</span><span class="sxs-lookup"><span data-stu-id="f26a5-178">The numeral '5' is displayed in `Label1`, demonstrating that the `ButtonValue` property of your inherited control has been passed to `Label1` through the `ValueButton1_Click` method.</span></span> <span data-ttu-id="f26a5-179">このようにして、`ValueButton` コントロールは標準の Windows フォーム ボタンの機能をすべて継承しながら、追加のカスタム プロパティを公開します。</span><span class="sxs-lookup"><span data-stu-id="f26a5-179">Thus your `ValueButton` control inherits all the functionality of the standard Windows Forms button, but exposes an additional, custom property.</span></span>

## <a name="see-also"></a><span data-ttu-id="f26a5-180">関連項目</span><span class="sxs-lookup"><span data-stu-id="f26a5-180">See also</span></span>

- [<span data-ttu-id="f26a5-181">チュートリアル: Visual Basic による複合コントロールの作成</span><span class="sxs-lookup"><span data-stu-id="f26a5-181">Walkthrough: Authoring a Composite Control with Visual Basic</span></span>](walkthrough-authoring-a-composite-control-with-visual-basic.md)
- <span data-ttu-id="f26a5-182">[方法: [ツールボックスアイテムの選択] ダイアログボックスにコントロールを表示する](how-to-display-a-control-in-the-choose-toolbox-items-dialog-box.md)</span><span class="sxs-lookup"><span data-stu-id="f26a5-182">[How to: Display a Control in the Choose Toolbox Items Dialog Box](how-to-display-a-control-in-the-choose-toolbox-items-dialog-box.md)</span></span>
- [<span data-ttu-id="f26a5-183">.NET Framework を使用したカスタム Windows フォーム コントロールの開発</span><span class="sxs-lookup"><span data-stu-id="f26a5-183">Developing Custom Windows Forms Controls with the .NET Framework</span></span>](developing-custom-windows-forms-controls.md)
- [<span data-ttu-id="f26a5-184">継承の基本 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f26a5-184">Inheritance basics (Visual Basic)</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
