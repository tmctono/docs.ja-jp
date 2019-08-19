---
title: 'チュートリアル: ビジュアル継承のデモンストレーション'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- form inheritance [Windows Forms], walkthroughs
- visual inheritance
- inheritance [Windows Forms], walkthroughs
- walkthroughs [Windows Forms], visual inheritance
- Windows Forms, inheritance
ms.assetid: 01966086-3142-450e-8210-3fd4cb33f591
ms.openlocfilehash: 6fd504269ae9afbfd02b58276582a644674e1e0f
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/15/2019
ms.locfileid: "69040319"
---
# <a name="walkthrough-demonstrating-visual-inheritance"></a><span data-ttu-id="81c8c-102">チュートリアル: ビジュアル継承のデモンストレーション</span><span class="sxs-lookup"><span data-stu-id="81c8c-102">Walkthrough: Demonstrating Visual Inheritance</span></span>

<span data-ttu-id="81c8c-103">ビジュアル継承により、基本フォームのコントロールを表示して、新しいコントロールを追加できます。</span><span class="sxs-lookup"><span data-stu-id="81c8c-103">Visual inheritance enables you to see the controls on the base form and to add new controls.</span></span> <span data-ttu-id="81c8c-104">このチュートリアルでは、基本フォームを作成してクラス ライブラリにコンパイルします。</span><span class="sxs-lookup"><span data-stu-id="81c8c-104">In this walkthrough you will create a base form and compile it into a class library.</span></span> <span data-ttu-id="81c8c-105">このクラス ライブラリを別のプロジェクトにインポートして、基本フォームから継承する新しいフォームを作成します。</span><span class="sxs-lookup"><span data-stu-id="81c8c-105">You will import this class library into another project and create a new form that inherits from the base form.</span></span> <span data-ttu-id="81c8c-106">このチュートリアルでは、次の作業を行う方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="81c8c-106">During this walkthrough, you will learn how to:</span></span>

- <span data-ttu-id="81c8c-107">基本フォームを含むクラス ライブラリ プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="81c8c-107">Create a class library project containing a base form.</span></span>

- <span data-ttu-id="81c8c-108">基本フォームの派生クラスが変更できるプロパティを持つボタンを追加します。</span><span class="sxs-lookup"><span data-stu-id="81c8c-108">Add a button with properties that derived classes of the base form can modify.</span></span>

- <span data-ttu-id="81c8c-109">基本フォームの継承元により変更できないボタンを追加します。</span><span class="sxs-lookup"><span data-stu-id="81c8c-109">Add a button that cannot be modified by inheritors of the base form.</span></span>

- <span data-ttu-id="81c8c-110">`BaseForm` から継承したフォームを含むプロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="81c8c-110">Create a project containing a form that inherits from `BaseForm`.</span></span>

<span data-ttu-id="81c8c-111">最終的には、このチュートリアルでは、継承されたフォーム上のプライベート コントロールとプロテクト コントロールの違いを示します。</span><span class="sxs-lookup"><span data-stu-id="81c8c-111">Ultimately, this walkthrough will demonstrate the difference between private and protected controls on an inherited form.</span></span>

> [!CAUTION]
> <span data-ttu-id="81c8c-112">すべてのコントロールが基本フォームのビジュアル継承をサポートするわけではありません。</span><span class="sxs-lookup"><span data-stu-id="81c8c-112">Not all controls support visual inheritance from a base form.</span></span> <span data-ttu-id="81c8c-113">次のコントロールでは、このチュートリアルで説明するシナリオはサポートされません。</span><span class="sxs-lookup"><span data-stu-id="81c8c-113">The following controls do not support the scenario described in this walkthrough:</span></span>
>
>  <xref:System.Windows.Forms.WebBrowser>
>
>  <xref:System.Windows.Forms.ToolStrip>
>
>  <xref:System.Windows.Forms.ToolStripPanel>
>
>  <xref:System.Windows.Forms.TableLayoutPanel>
>
>  <xref:System.Windows.Forms.FlowLayoutPanel>
>
>  <xref:System.Windows.Forms.DataGridView>
>
>  <span data-ttu-id="81c8c-114">継承されたフォームのこれらのコントロールは、使用する修飾子 (`private`、`protected`、または `public`) に関係なく、常に読み取り専用です。</span><span class="sxs-lookup"><span data-stu-id="81c8c-114">These controls in the inherited form are always read-only regardless of the modifiers you use (`private`, `protected`, or `public`).</span></span>

## <a name="create-a-class-library-project-containing-a-base-form"></a><span data-ttu-id="81c8c-115">基本フォームを含むクラスライブラリプロジェクトを作成する</span><span class="sxs-lookup"><span data-stu-id="81c8c-115">Create a class library project containing a base form</span></span>

1. <span data-ttu-id="81c8c-116">Visual Studio で、[**ファイル**] メニューの [**新しい** > **プロジェクト**] をクリックし、[**新しいプロジェクト**] ダイアログボックスを開きます。</span><span class="sxs-lookup"><span data-stu-id="81c8c-116">In Visual Studio, from the **File** menu, choose **New** > **Project** to open the **New Project** dialog box.</span></span>

2. <span data-ttu-id="81c8c-117">という名前`BaseFormLibrary`の Windows フォームアプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="81c8c-117">Create a Windows Forms application named `BaseFormLibrary`.</span></span>

3. <span data-ttu-id="81c8c-118">標準 Windows フォームアプリケーションではなくクラスライブラリを作成するには、**ソリューションエクスプローラー**で [ **baseformlibrary** ] プロジェクトノードを右クリックし、[**プロパティ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="81c8c-118">To create a class library instead of a standard Windows Forms application, in **Solution Explorer**, right-click the **BaseFormLibrary** project node and then select **Properties**.</span></span>

4. <span data-ttu-id="81c8c-119">プロジェクトのプロパティで、[**出力の種類**] を [ **Windows アプリケーション**] から [**クラスライブラリ**] に変更します。</span><span class="sxs-lookup"><span data-stu-id="81c8c-119">In the properties for the project, change the **Output type** from **Windows Application** to **Class Library**.</span></span>

5. <span data-ttu-id="81c8c-120">[**ファイル**] メニューの [**すべてを保存**] をクリックして、プロジェクトとファイルを既定の場所に保存します。</span><span class="sxs-lookup"><span data-stu-id="81c8c-120">From the **File** menu, choose **Save All** to save the project and files to the default location.</span></span>

 <span data-ttu-id="81c8c-121">次の 2 つの手順では、基本フォームにボタンを追加します。</span><span class="sxs-lookup"><span data-stu-id="81c8c-121">The next two procedures add buttons to the base form.</span></span> <span data-ttu-id="81c8c-122">ビジュアル継承を示すには、`Modifiers` プロパティを設定して、ボタンに異なるアクセス レベルを付与します。</span><span class="sxs-lookup"><span data-stu-id="81c8c-122">To demonstrate visual inheritance, you will give the buttons different access levels by setting their `Modifiers` properties.</span></span>

## <a name="add-a-button-that-inheritors-of-the-base-form-can-modify"></a><span data-ttu-id="81c8c-123">基本フォームの継承元が変更できるボタンを追加します。</span><span class="sxs-lookup"><span data-stu-id="81c8c-123">Add a button that inheritors of the base form can modify</span></span>

1. <span data-ttu-id="81c8c-124">デザイナーで **Form1** を開きます。</span><span class="sxs-lookup"><span data-stu-id="81c8c-124">Open **Form1** in the designer.</span></span>

2. <span data-ttu-id="81c8c-125">**ツールボックス**の [**すべての Windows フォーム**] タブで、[ **] ボタン**をダブルクリックして、フォームにボタンを追加します。</span><span class="sxs-lookup"><span data-stu-id="81c8c-125">On the **All Windows Forms** tab of the **Toolbox**, double-click **Button** to add a button to the form.</span></span> <span data-ttu-id="81c8c-126">マウスを使用し、ボタンを配置してサイズを変更します。</span><span class="sxs-lookup"><span data-stu-id="81c8c-126">Use the mouse to position and resize the button.</span></span>

3. <span data-ttu-id="81c8c-127">[プロパティ] ウィンドウで、ボタンの次のプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="81c8c-127">In the Properties window, set the following properties of the button:</span></span>

    - <span data-ttu-id="81c8c-128">[ **Text** ] プロパティを「 **Hello**」に設定します。</span><span class="sxs-lookup"><span data-stu-id="81c8c-128">Set the **Text** property to **Say Hello**.</span></span>

    - <span data-ttu-id="81c8c-129">**(Name)** プロパティを**btnprotected**に設定します。</span><span class="sxs-lookup"><span data-stu-id="81c8c-129">Set the **(Name)** property to **btnProtected**.</span></span>

    - <span data-ttu-id="81c8c-130">**Modifiers**プロパティを**Protected**に設定します。</span><span class="sxs-lookup"><span data-stu-id="81c8c-130">Set the **Modifiers** property to **Protected**.</span></span> <span data-ttu-id="81c8c-131">これにより、 **Form1**から継承するフォームが、 **btnprotected**のプロパティを変更できるようになります。</span><span class="sxs-lookup"><span data-stu-id="81c8c-131">This makes it possible for forms that inherit from **Form1** to modify the properties of **btnProtected**.</span></span>

4. <span data-ttu-id="81c8c-132">ダブルクリックして、 **Say こんにちは**のイベント ハンドラーを追加するボタン、 **をクリックして**イベント。</span><span class="sxs-lookup"><span data-stu-id="81c8c-132">Double-click the **Say Hello** button to add an event handler for the **Click** event.</span></span>

5. <span data-ttu-id="81c8c-133">イベント ハンドラーに次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="81c8c-133">Add the following line of code to the event handler:</span></span>

    ```vb
    MessageBox.Show("Hello, World!")
    ```

    ```csharp
    MessageBox.Show("Hello, World!");
    ```

## <a name="add-a-button-that-cannot-be-modified-by-inheritors-of-the-base-form"></a><span data-ttu-id="81c8c-134">基本フォームの継承元によって変更できないボタンを追加する</span><span class="sxs-lookup"><span data-stu-id="81c8c-134">Add a button that cannot be modified by inheritors of the base form</span></span>

1. <span data-ttu-id="81c8c-135">クリックしてデザイン ビューに切り替え、 **Form1.vb [デザイン]、Form1.cs [デザイン]、または Form1.jsl の [デザイン]** コード エディターの上または F7 キーを押してタブです。</span><span class="sxs-lookup"><span data-stu-id="81c8c-135">Switch to design view by clicking the **Form1.vb [Design], Form1.cs [Design], or Form1.jsl [Design]** tab above the code editor, or by pressing F7.</span></span>

2. <span data-ttu-id="81c8c-136">2 番目のボタンを追加し、そのプロパティを次のように設定します。</span><span class="sxs-lookup"><span data-stu-id="81c8c-136">Add a second button and set its properties as follows:</span></span>

    - <span data-ttu-id="81c8c-137">Text プロパティを「」**と** **入力**します。</span><span class="sxs-lookup"><span data-stu-id="81c8c-137">Set the **Text** property to **Say Goodbye**.</span></span>

    - <span data-ttu-id="81c8c-138">**(Name)** プロパティを**btnprivate**に設定します。</span><span class="sxs-lookup"><span data-stu-id="81c8c-138">Set the **(Name)** property to **btnPrivate**.</span></span>

    - <span data-ttu-id="81c8c-139">**Modifiers**プロパティを**Private**に設定します。</span><span class="sxs-lookup"><span data-stu-id="81c8c-139">Set the **Modifiers** property to **Private**.</span></span> <span data-ttu-id="81c8c-140">これにより、 **Form1**から継承したフォームでは、 **btnprivate**のプロパティを変更できなくなります。</span><span class="sxs-lookup"><span data-stu-id="81c8c-140">This makes it impossible for forms that inherit from **Form1** to modify the properties of **btnPrivate**.</span></span>

3. <span data-ttu-id="81c8c-141">ダブルクリックして、 **Say Goodbye**のイベント ハンドラーを追加するボタン、 **をクリックして**イベント。</span><span class="sxs-lookup"><span data-stu-id="81c8c-141">Double-click the **Say Goodbye** button to add an event handler for the **Click** event.</span></span> <span data-ttu-id="81c8c-142">イベントの手順で、次のコード行を配置します。</span><span class="sxs-lookup"><span data-stu-id="81c8c-142">Place the following line of code in the event procedure:</span></span>

    ```vb
    MessageBox.Show("Goodbye!")
    ```

    ```csharp
    MessageBox.Show("Goodbye!");
    ```

4. <span data-ttu-id="81c8c-143">[**ビルド**] メニューの [ **Baseform library のビルド**] をクリックして、クラスライブラリをビルドします。</span><span class="sxs-lookup"><span data-stu-id="81c8c-143">From the **Build** menu, choose **Build BaseForm Library** to build the class library.</span></span>

     <span data-ttu-id="81c8c-144">ライブラリがビルドされたら、作成したフォームから継承する新しいプロジェクトを作成できます。</span><span class="sxs-lookup"><span data-stu-id="81c8c-144">Once the library is built, you can create a new project that inherits from the form you just created.</span></span>

## <a name="create-a-project-containing-a-form-that-inherits-from-the-base-form"></a><span data-ttu-id="81c8c-145">基本フォームから継承するフォームを含むプロジェクトを作成する</span><span class="sxs-lookup"><span data-stu-id="81c8c-145">Create a project containing a form that inherits from the base form</span></span>

1. <span data-ttu-id="81c8c-146">[**ファイル**] メニューの [**追加**] をポイントし、[**新しいプロジェクト**] をクリックして、[**新しいプロジェクトの追加**] ダイアログボックスを開きます。</span><span class="sxs-lookup"><span data-stu-id="81c8c-146">From the **File** menu, choose **Add** and then **New Project** to open the **Add New Project** dialog box.</span></span>

2. <span data-ttu-id="81c8c-147">という名前`InheritanceTest`の Windows フォームアプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="81c8c-147">Create a Windows Forms application named `InheritanceTest`.</span></span>

## <a name="add-an-inherited-form"></a><span data-ttu-id="81c8c-148">継承されたフォームを追加する</span><span class="sxs-lookup"><span data-stu-id="81c8c-148">Add an inherited form</span></span>

1. <span data-ttu-id="81c8c-149">**ソリューションエクスプローラー**で、 **InheritanceTest**プロジェクトを右クリックし、[**追加**]、[**新しい項目**] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="81c8c-149">In **Solution Explorer**, right-click the **InheritanceTest** project, select **Add**, and then select **New Item**.</span></span>

2. <span data-ttu-id="81c8c-150">[**新しい項目の追加**] ダイアログボックスで、[ **Windows フォーム**] カテゴリ (カテゴリの一覧がある場合) を選択し、[継承された**フォーム**] テンプレートを選択します。</span><span class="sxs-lookup"><span data-stu-id="81c8c-150">In the **Add New Item** dialog box, select the **Windows Forms** category (if you have a list of categories) and then select the **Inherited Form** template.</span></span>

3. <span data-ttu-id="81c8c-151">既定の`Form2`名前のままにして、[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="81c8c-151">Leave the default name of `Form2` and then click **Add**.</span></span>

4. <span data-ttu-id="81c8c-152">[**継承ピッカー** ] ダイアログボックスで、継承元のフォームとして**baseformlibrary**プロジェクトから**Form1**を選択し、[ **OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="81c8c-152">In the **Inheritance Picker** dialog box, select **Form1** from the **BaseFormLibrary** project as the form to inherit from and click **OK**.</span></span>

     <span data-ttu-id="81c8c-153">これにより、 **Baseformlibrary**のフォームから派生するフォームが**InheritanceTest**プロジェクトに作成されます。</span><span class="sxs-lookup"><span data-stu-id="81c8c-153">This creates a form in the **InheritanceTest** project that derives from the form in **BaseFormLibrary**.</span></span>

5. <span data-ttu-id="81c8c-154">デザイナーで、継承されたフォーム (**Form2**) をダブルクリックして開きます (まだ開いていない場合)。</span><span class="sxs-lookup"><span data-stu-id="81c8c-154">Open the inherited form (**Form2**) in the designer by double-clicking it, if it is not already open.</span></span>

     <span data-ttu-id="81c8c-155">デザイナーでは、継承されたボタンにシンボル (</span><span class="sxs-lookup"><span data-stu-id="81c8c-155">In the designer, the inherited buttons have a symbol (</span></span>![Visual Basic 継承シンボルのスクリーンショット。](./media/walkthrough-demonstrating-visual-inheritance/visual-basic-inheritance-glyph.gif)<span data-ttu-id="81c8c-157">) を上隅に置いて、それらが継承されていることを示します。</span><span class="sxs-lookup"><span data-stu-id="81c8c-157">) in their upper corner, indicating they are inherited.</span></span>

6. <span data-ttu-id="81c8c-158">[ **Hello Hello** ] ボタンを選択し、サイズ変更ハンドルを観察します。</span><span class="sxs-lookup"><span data-stu-id="81c8c-158">Select the **Say Hello** button and observe the resize handles.</span></span> <span data-ttu-id="81c8c-159">このボタンは保護されているため、継承元が、移動、サイズ変更、キャプションの変更、およびその他の変更を実行できます。</span><span class="sxs-lookup"><span data-stu-id="81c8c-159">Because this button is protected, the inheritors can move it, resize it, change its caption, and make other modifications.</span></span>

7. <span data-ttu-id="81c8c-160">[プライベート]ボタンをクリックし、サイズ変更ハンドルがないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="81c8c-160">Select the private **Say Goodbye** button, and notice that it does not have resize handles.</span></span> <span data-ttu-id="81c8c-161">また、[**プロパティ**] ウィンドウでは、このボタンのプロパティがグレーで表示され、変更できないことが示されています。</span><span class="sxs-lookup"><span data-stu-id="81c8c-161">Additionally, in the **Properties** window, the properties of this button are grayed to indicate they cannot be modified.</span></span>

8. <span data-ttu-id="81c8c-162">ビジュアルC#を使用している場合:</span><span class="sxs-lookup"><span data-stu-id="81c8c-162">If you are using Visual C#:</span></span>

    1. <span data-ttu-id="81c8c-163">**ソリューションエクスプローラー**で、 **InheritanceTest**プロジェクトの**Form1**を右クリックし、[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="81c8c-163">In **Solution Explorer**, right-click **Form1** in the **InheritanceTest** project and then choose **Delete**.</span></span> <span data-ttu-id="81c8c-164">表示されるメッセージボックスで、[ **OK** ] をクリックして削除を確定します。</span><span class="sxs-lookup"><span data-stu-id="81c8c-164">In the message box that appears, click **OK** to confirm the deletion.</span></span>

    2. <span data-ttu-id="81c8c-165">Program.cs ファイルを開き、行 `Application.Run(new Form1());` を `Application.Run(new Form2());` に変更します。</span><span class="sxs-lookup"><span data-stu-id="81c8c-165">Open the Program.cs file and change the line `Application.Run(new Form1());` to `Application.Run(new Form2());`.</span></span>

9. <span data-ttu-id="81c8c-166">**ソリューションエクスプローラー**で、 **InheritanceTest**プロジェクトを右クリックし、[**スタートアッププロジェクトに設定**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="81c8c-166">In **Solution Explorer**, right-click the **InheritanceTest** project and select **Set As Startup Project**.</span></span>

10. <span data-ttu-id="81c8c-167">**ソリューションエクスプローラー**で、 **InheritanceTest**プロジェクトを右クリックし、[**プロパティ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="81c8c-167">In **Solution Explorer**, right-click the **InheritanceTest** project and select **Properties**.</span></span>

11. <span data-ttu-id="81c8c-168">**InheritanceTest**プロパティページで、 **Startup オブジェクト**を継承されたフォーム (**Form2**) に設定します。</span><span class="sxs-lookup"><span data-stu-id="81c8c-168">In the **InheritanceTest** property pages, set the **Startup object** to be the inherited form (**Form2**).</span></span>

12. <span data-ttu-id="81c8c-169">**F5**キーを押してアプリケーションを実行し、継承されたフォームの動作を確認します。</span><span class="sxs-lookup"><span data-stu-id="81c8c-169">Press **F5** to run the application, and observe the behavior of the inherited form.</span></span>

## <a name="next-steps"></a><span data-ttu-id="81c8c-170">次の手順</span><span class="sxs-lookup"><span data-stu-id="81c8c-170">Next steps</span></span>

<span data-ttu-id="81c8c-171">ユーザー コントロールの継承はほぼ同じ方法で機能します。</span><span class="sxs-lookup"><span data-stu-id="81c8c-171">Inheritance for user controls works in much the same way.</span></span> <span data-ttu-id="81c8c-172">新しいクラス ライブラリ プロジェクトを開き、ユーザー コントロールを追加します。</span><span class="sxs-lookup"><span data-stu-id="81c8c-172">Open a new class library project and add a user control.</span></span> <span data-ttu-id="81c8c-173">内在コントロールを配置し、プロジェクトをコンパイルします。</span><span class="sxs-lookup"><span data-stu-id="81c8c-173">Place constituent controls on it and compile the project.</span></span> <span data-ttu-id="81c8c-174">別の新しいクラス ライブラリ プロジェクトを開き、コンパイル済みのクラス ライブラリへの参照を追加します。</span><span class="sxs-lookup"><span data-stu-id="81c8c-174">Open another new class library project and add a reference to the compiled class library.</span></span> <span data-ttu-id="81c8c-175">また、継承されたコントロールを ([**新しい項目の追加**] ダイアログボックスを使用して) プロジェクトに追加し、**継承ピッカー**を使用してみてください。</span><span class="sxs-lookup"><span data-stu-id="81c8c-175">Also, try adding an inherited control (through the **Add New Items** dialog box) to the project and using the **Inheritance Picker**.</span></span> <span data-ttu-id="81c8c-176">ユーザーコントロールを追加し、 `Inherits` (`:` Visual C#) ステートメントを変更します。</span><span class="sxs-lookup"><span data-stu-id="81c8c-176">Add a user control, and change the `Inherits` (`:` in Visual C#) statement.</span></span> <span data-ttu-id="81c8c-177">詳細については、「[方法 :Windows フォーム](how-to-inherit-windows-forms.md)を継承します。</span><span class="sxs-lookup"><span data-stu-id="81c8c-177">For more information, see [How to: Inherit Windows Forms](how-to-inherit-windows-forms.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="81c8c-178">関連項目</span><span class="sxs-lookup"><span data-stu-id="81c8c-178">See also</span></span>

- [<span data-ttu-id="81c8c-179">方法: Windows フォームを継承する</span><span class="sxs-lookup"><span data-stu-id="81c8c-179">How to: Inherit Windows Forms</span></span>](how-to-inherit-windows-forms.md)
- [<span data-ttu-id="81c8c-180">Windows フォームのビジュアルの継承</span><span class="sxs-lookup"><span data-stu-id="81c8c-180">Windows Forms Visual Inheritance</span></span>](windows-forms-visual-inheritance.md)
- [<span data-ttu-id="81c8c-181">Windows フォーム</span><span class="sxs-lookup"><span data-stu-id="81c8c-181">Windows Forms</span></span>](../index.md)
