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
ms.openlocfilehash: 9366c7ebe2e5b347f4795b15e6f2c2d0f3835482
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61747522"
---
# <a name="walkthrough-demonstrating-visual-inheritance"></a><span data-ttu-id="bccf6-102">チュートリアル: ビジュアル継承のデモンストレーション</span><span class="sxs-lookup"><span data-stu-id="bccf6-102">Walkthrough: Demonstrating Visual Inheritance</span></span>
<span data-ttu-id="bccf6-103">ビジュアル継承により、基本フォームのコントロールを表示して、新しいコントロールを追加できます。</span><span class="sxs-lookup"><span data-stu-id="bccf6-103">Visual inheritance enables you to see the controls on the base form and to add new controls.</span></span> <span data-ttu-id="bccf6-104">このチュートリアルでは、基本フォームを作成してクラス ライブラリにコンパイルします。</span><span class="sxs-lookup"><span data-stu-id="bccf6-104">In this walkthrough you will create a base form and compile it into a class library.</span></span> <span data-ttu-id="bccf6-105">このクラス ライブラリを別のプロジェクトにインポートして、基本フォームから継承する新しいフォームを作成します。</span><span class="sxs-lookup"><span data-stu-id="bccf6-105">You will import this class library into another project and create a new form that inherits from the base form.</span></span> <span data-ttu-id="bccf6-106">このチュートリアルでは、次の作業を行う方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="bccf6-106">During this walkthrough, you will learn how to:</span></span>  
  
- <span data-ttu-id="bccf6-107">基本フォームを含むクラス ライブラリ プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="bccf6-107">Create a class library project containing a base form.</span></span>  
  
- <span data-ttu-id="bccf6-108">基本フォームの派生クラスが変更できるプロパティを持つボタンを追加します。</span><span class="sxs-lookup"><span data-stu-id="bccf6-108">Add a button with properties that derived classes of the base form can modify.</span></span>  
  
- <span data-ttu-id="bccf6-109">基本フォームの継承元により変更できないボタンを追加します。</span><span class="sxs-lookup"><span data-stu-id="bccf6-109">Add a button that cannot be modified by inheritors of the base form.</span></span>  
  
- <span data-ttu-id="bccf6-110">`BaseForm` から継承したフォームを含むプロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="bccf6-110">Create a project containing a form that inherits from `BaseForm`.</span></span>  
  
 <span data-ttu-id="bccf6-111">最終的には、このチュートリアルでは、継承されたフォーム上のプライベート コントロールとプロテクト コントロールの違いを示します。</span><span class="sxs-lookup"><span data-stu-id="bccf6-111">Ultimately, this walkthrough will demonstrate the difference between private and protected controls on an inherited form.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bccf6-112">実際に画面に表示されるダイアログ ボックスとメニュー コマンドは、アクティブな設定またはエディションによっては、ヘルプの説明と異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="bccf6-112">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="bccf6-113">設定を変更するには、 **[ツール]** メニューの **[設定のインポートとエクスポート]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bccf6-113">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="bccf6-114">詳細については、「[Visual Studio IDE のカスタマイズ](/visualstudio/ide/personalizing-the-visual-studio-ide)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bccf6-114">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="bccf6-115">すべてのコントロールが基本フォームのビジュアル継承をサポートするわけではありません。</span><span class="sxs-lookup"><span data-stu-id="bccf6-115">Not all controls support visual inheritance from a base form.</span></span> <span data-ttu-id="bccf6-116">次のコントロールでは、このチュートリアルで説明するシナリオはサポートされません。</span><span class="sxs-lookup"><span data-stu-id="bccf6-116">The following controls do not support the scenario described in this walkthrough:</span></span>  
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
>  <span data-ttu-id="bccf6-117">継承されたフォームのこれらのコントロールは、使用する修飾子 (`private`、`protected`、または `public`) に関係なく、常に読み取り専用です。</span><span class="sxs-lookup"><span data-stu-id="bccf6-117">These controls in the inherited form are always read-only regardless of the modifiers you use (`private`, `protected`, or `public`).</span></span>  
  
## <a name="scenario-steps"></a><span data-ttu-id="bccf6-118">シナリオの手順</span><span class="sxs-lookup"><span data-stu-id="bccf6-118">Scenario Steps</span></span>  
 <span data-ttu-id="bccf6-119">最初の手順では、基本フォームを作成します。</span><span class="sxs-lookup"><span data-stu-id="bccf6-119">The first step is to create the base form.</span></span>  
  
#### <a name="to-create-a-class-library-project-containing-a-base-form"></a><span data-ttu-id="bccf6-120">基本フォームを含むクラス ライブラリ プロジェクトを作成するには</span><span class="sxs-lookup"><span data-stu-id="bccf6-120">To create a class library project containing a base form</span></span>  
  
1. <span data-ttu-id="bccf6-121">**ファイル** メニューの 選択**新規**、し**プロジェクト**を開く、**新しいプロジェクト** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="bccf6-121">From the **File** menu, choose **New**, and then **Project** to open the **New Project** dialog box.</span></span>  
  
2. <span data-ttu-id="bccf6-122">という名前の Windows フォーム アプリケーションを作成する`BaseFormLibrary`します。</span><span class="sxs-lookup"><span data-stu-id="bccf6-122">Create a Windows Forms application named `BaseFormLibrary`.</span></span>  
  
3. <span data-ttu-id="bccf6-123">標準の Windows フォーム アプリケーションではなくクラス ライブラリを作成する**ソリューション エクスプ ローラー**を右クリックし、 **BaseFormLibrary**プロジェクト ノードを選び**プロパティ**.</span><span class="sxs-lookup"><span data-stu-id="bccf6-123">To create a class library instead of a standard Windows Forms application, in **Solution Explorer**, right-click the **BaseFormLibrary** project node and then select **Properties**.</span></span>  
  
4. <span data-ttu-id="bccf6-124">プロジェクトのプロパティで、変更、**出力の種類**から**Windows アプリケーション**に**クラス ライブラリ**します。</span><span class="sxs-lookup"><span data-stu-id="bccf6-124">In the properties for the project, change the **Output type** from **Windows Application** to **Class Library**.</span></span>  
  
5. <span data-ttu-id="bccf6-125">**ファイル**] メニューの [選択**すべて保存**を既定の場所に、プロジェクトおよびファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="bccf6-125">From the **File** menu, choose **Save All** to save the project and files to the default location.</span></span>  
  
 <span data-ttu-id="bccf6-126">次の 2 つの手順では、基本フォームにボタンを追加します。</span><span class="sxs-lookup"><span data-stu-id="bccf6-126">The next two procedures add buttons to the base form.</span></span> <span data-ttu-id="bccf6-127">ビジュアル継承を示すには、`Modifiers` プロパティを設定して、ボタンに異なるアクセス レベルを付与します。</span><span class="sxs-lookup"><span data-stu-id="bccf6-127">To demonstrate visual inheritance, you will give the buttons different access levels by setting their `Modifiers` properties.</span></span>  
  
#### <a name="to-add-a-button-that-inheritors-of-the-base-form-can-modify"></a><span data-ttu-id="bccf6-128">基本フォームの継承クラスから変更が可能なボタンを追加するには</span><span class="sxs-lookup"><span data-stu-id="bccf6-128">To add a button that inheritors of the base form can modify</span></span>  
  
1. <span data-ttu-id="bccf6-129">デザイナーで **Form1** を開きます。</span><span class="sxs-lookup"><span data-stu-id="bccf6-129">Open **Form1** in the designer.</span></span>  
  
2. <span data-ttu-id="bccf6-130">**すべての Windows フォーム**のタブ、**ツールボックス**、ダブルクリック**ボタン**をフォームにボタンを追加します。</span><span class="sxs-lookup"><span data-stu-id="bccf6-130">On the **All Windows Forms** tab of the **Toolbox**, double-click **Button** to add a button to the form.</span></span> <span data-ttu-id="bccf6-131">マウスを使用し、ボタンを配置してサイズを変更します。</span><span class="sxs-lookup"><span data-stu-id="bccf6-131">Use the mouse to position and resize the button.</span></span>  
  
3. <span data-ttu-id="bccf6-132">[プロパティ] ウィンドウで、ボタンの次のプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="bccf6-132">In the Properties window, set the following properties of the button:</span></span>  
  
    - <span data-ttu-id="bccf6-133">設定、**テキスト**プロパティを**Say こんにちは**します。</span><span class="sxs-lookup"><span data-stu-id="bccf6-133">Set the **Text** property to **Say Hello**.</span></span>  
  
    - <span data-ttu-id="bccf6-134">設定、 **(名)** プロパティを**btnProtected**します。</span><span class="sxs-lookup"><span data-stu-id="bccf6-134">Set the **(Name)** property to **btnProtected**.</span></span>  
  
    - <span data-ttu-id="bccf6-135">設定、**修飾子**プロパティを**Protected**します。</span><span class="sxs-lookup"><span data-stu-id="bccf6-135">Set the **Modifiers** property to **Protected**.</span></span> <span data-ttu-id="bccf6-136">継承するフォームが可能になります。 **Form1**のプロパティを変更する**btnProtected**します。</span><span class="sxs-lookup"><span data-stu-id="bccf6-136">This makes it possible for forms that inherit from **Form1** to modify the properties of **btnProtected**.</span></span>  
  
4. <span data-ttu-id="bccf6-137">ダブルクリックして、 **Say こんにちは**のイベント ハンドラーを追加するボタン、 **をクリックして**イベント。</span><span class="sxs-lookup"><span data-stu-id="bccf6-137">Double-click the **Say Hello** button to add an event handler for the **Click** event.</span></span>  
  
5. <span data-ttu-id="bccf6-138">イベント ハンドラーに次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="bccf6-138">Add the following line of code to the event handler:</span></span>  
  
    ```vb  
    MessageBox.Show("Hello, World!")  
    ```  
  
    ```csharp  
    MessageBox.Show("Hello, World!");  
    ```  
  
#### <a name="to-add-a-button-that-cannot-be-modified-by-inheritors-of-the-base-form"></a><span data-ttu-id="bccf6-139">基本フォームの継承元により変更できないボタンを追加するには</span><span class="sxs-lookup"><span data-stu-id="bccf6-139">To add a button that cannot be modified by inheritors of the base form</span></span>  
  
1. <span data-ttu-id="bccf6-140">クリックしてデザイン ビューに切り替え、 **Form1.vb [デザイン]、Form1.cs [デザイン]、または Form1.jsl の [デザイン]** コード エディターの上または F7 キーを押してタブです。</span><span class="sxs-lookup"><span data-stu-id="bccf6-140">Switch to design view by clicking the **Form1.vb [Design], Form1.cs [Design], or Form1.jsl [Design]** tab above the code editor, or by pressing F7.</span></span>  
  
2. <span data-ttu-id="bccf6-141">2 番目のボタンを追加し、そのプロパティを次のように設定します。</span><span class="sxs-lookup"><span data-stu-id="bccf6-141">Add a second button and set its properties as follows:</span></span>  
  
    - <span data-ttu-id="bccf6-142">設定、**テキスト**プロパティを**Say Goodbye**します。</span><span class="sxs-lookup"><span data-stu-id="bccf6-142">Set the **Text** property to **Say Goodbye**.</span></span>  
  
    - <span data-ttu-id="bccf6-143">設定、 **(名)** プロパティを**btnPrivate**します。</span><span class="sxs-lookup"><span data-stu-id="bccf6-143">Set the **(Name)** property to **btnPrivate**.</span></span>  
  
    - <span data-ttu-id="bccf6-144">設定、**修飾子**プロパティを**プライベート**します。</span><span class="sxs-lookup"><span data-stu-id="bccf6-144">Set the **Modifiers** property to **Private**.</span></span> <span data-ttu-id="bccf6-145">継承するフォームが不可能になります。 **Form1**のプロパティを変更する**btnPrivate**します。</span><span class="sxs-lookup"><span data-stu-id="bccf6-145">This makes it impossible for forms that inherit from **Form1** to modify the properties of **btnPrivate**.</span></span>  
  
3. <span data-ttu-id="bccf6-146">ダブルクリックして、 **Say Goodbye**のイベント ハンドラーを追加するボタン、 **をクリックして**イベント。</span><span class="sxs-lookup"><span data-stu-id="bccf6-146">Double-click the **Say Goodbye** button to add an event handler for the **Click** event.</span></span> <span data-ttu-id="bccf6-147">イベントの手順で、次のコード行を配置します。</span><span class="sxs-lookup"><span data-stu-id="bccf6-147">Place the following line of code in the event procedure:</span></span>  
  
    ```vb  
    MessageBox.Show("Goodbye!")  
    ```  
  
    ```csharp  
    MessageBox.Show("Goodbye!");  
    ```  
  
4. <span data-ttu-id="bccf6-148">**ビルド**] メニューの [選択**BaseForm ライブラリのビルド**クラス ライブラリをビルドします。</span><span class="sxs-lookup"><span data-stu-id="bccf6-148">From the **Build** menu, choose **Build BaseForm Library** to build the class library.</span></span>  
  
     <span data-ttu-id="bccf6-149">ライブラリがビルドされたら、作成したフォームから継承する新しいプロジェクトを作成できます。</span><span class="sxs-lookup"><span data-stu-id="bccf6-149">Once the library is built, you can create a new project that inherits from the form you just created.</span></span>  
  
#### <a name="to-create-a-project-containing-a-form-that-inherits-from-the-base-form"></a><span data-ttu-id="bccf6-150">基本フォームから継承したフォームを含むプロジェクトを作成するには</span><span class="sxs-lookup"><span data-stu-id="bccf6-150">To create a project containing a form that inherits from the base form</span></span>  
  
1. <span data-ttu-id="bccf6-151">**ファイル** メニューの 選択**追加**し**新しいプロジェクト**を開く、**新しいプロジェクトの追加** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="bccf6-151">From the **File** menu, choose **Add** and then **New Project** to open the **Add New Project** dialog box.</span></span>  
  
2. <span data-ttu-id="bccf6-152">という名前の Windows フォーム アプリケーションを作成する`InheritanceTest`します。</span><span class="sxs-lookup"><span data-stu-id="bccf6-152">Create a Windows Forms application named `InheritanceTest`.</span></span>  
  
#### <a name="to-add-an-inherited-form"></a><span data-ttu-id="bccf6-153">継承されたフォームを追加するには</span><span class="sxs-lookup"><span data-stu-id="bccf6-153">To add an inherited form</span></span>  
  
1. <span data-ttu-id="bccf6-154">**ソリューション エクスプ ローラー**を右クリックし、 **InheritanceTest**プロジェクトで、**追加**、し、**新しい項目の**します。</span><span class="sxs-lookup"><span data-stu-id="bccf6-154">In **Solution Explorer**, right-click the **InheritanceTest** project, select **Add**, and then select **New Item**.</span></span>  
  
2. <span data-ttu-id="bccf6-155">**新しい項目の追加**ダイアログ ボックスで、 **Windows フォーム**カテゴリ (カテゴリの一覧の場合) と選択し、**継承されたフォーム**テンプレート。</span><span class="sxs-lookup"><span data-stu-id="bccf6-155">In the **Add New Item** dialog box, select the **Windows Forms** category (if you have a list of categories) and then select the **Inherited Form** template.</span></span>  
  
3. <span data-ttu-id="bccf6-156">既定の名前をそのまま`Form2`し**追加**します。</span><span class="sxs-lookup"><span data-stu-id="bccf6-156">Leave the default name of `Form2` and then click **Add**.</span></span>  
  
4. <span data-ttu-id="bccf6-157">**継承ピッカー**ダイアログ ボックスで、 **Form1**から、 **BaseFormLibrary**フォームから継承し、をクリックするとプロジェクト**OK**.</span><span class="sxs-lookup"><span data-stu-id="bccf6-157">In the **Inheritance Picker** dialog box, select **Form1** from the **BaseFormLibrary** project as the form to inherit from and click **OK**.</span></span>  
  
     <span data-ttu-id="bccf6-158">これでフォームを作成、 **InheritanceTest**プロジェクト内のフォームから派生した**BaseFormLibrary**します。</span><span class="sxs-lookup"><span data-stu-id="bccf6-158">This creates a form in the **InheritanceTest** project that derives from the form in **BaseFormLibrary**.</span></span>  
  
5. <span data-ttu-id="bccf6-159">継承されたフォームを開きます (**Form2**) がまだ開いていない場合をダブルクリックしてデザイナーでします。</span><span class="sxs-lookup"><span data-stu-id="bccf6-159">Open the inherited form (**Form2**) in the designer by double-clicking it, if it is not already open.</span></span>  
  
     <span data-ttu-id="bccf6-160">デザイナーで、継承されたボタンがあるシンボル (</span><span class="sxs-lookup"><span data-stu-id="bccf6-160">In the designer, the inherited buttons have a symbol (</span></span>![Visual Basic の継承の記号のスクリーン ショット。](./media/walkthrough-demonstrating-visual-inheritance/visual-basic-inheritance-glyph.gif)<span data-ttu-id="bccf6-162">) で継承されることを示す、隅。</span><span class="sxs-lookup"><span data-stu-id="bccf6-162">) in their upper corner, indicating they are inherited.</span></span>  
  
6. <span data-ttu-id="bccf6-163">選択、 **Say こんにちは**ボタンをクリックし、サイズ変更ハンドルを観察します。</span><span class="sxs-lookup"><span data-stu-id="bccf6-163">Select the **Say Hello** button and observe the resize handles.</span></span> <span data-ttu-id="bccf6-164">このボタンは保護されているため、継承元が、移動、サイズ変更、キャプションの変更、およびその他の変更を実行できます。</span><span class="sxs-lookup"><span data-stu-id="bccf6-164">Because this button is protected, the inheritors can move it, resize it, change its caption, and make other modifications.</span></span>  
  
7. <span data-ttu-id="bccf6-165">プライベート**Say Goodbye**ボタン、およびサイズ変更ハンドルがないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="bccf6-165">Select the private **Say Goodbye** button, and notice that it does not have resize handles.</span></span> <span data-ttu-id="bccf6-166">さらに、**プロパティ**を変更できないことを示すために、このボタンのプロパティ ウィンドウが淡色表示されています。</span><span class="sxs-lookup"><span data-stu-id="bccf6-166">Additionally, in the **Properties** window, the properties of this button are grayed to indicate they cannot be modified.</span></span>  
  
8. <span data-ttu-id="bccf6-167">Visual c#: 使用している場合</span><span class="sxs-lookup"><span data-stu-id="bccf6-167">If you are using Visual C#:</span></span>  
  
    1. <span data-ttu-id="bccf6-168">**ソリューション エクスプ ローラー**、右クリックして**Form1**で、 **InheritanceTest**プロジェクト**削除**します。</span><span class="sxs-lookup"><span data-stu-id="bccf6-168">In **Solution Explorer**, right-click **Form1** in the **InheritanceTest** project and then choose **Delete**.</span></span> <span data-ttu-id="bccf6-169">メッセージ ボックスが表示されますが、次のようにクリックします。 **OK** 、削除を確定します。</span><span class="sxs-lookup"><span data-stu-id="bccf6-169">In the message box that appears, click **OK** to confirm the deletion.</span></span>  
  
    2. <span data-ttu-id="bccf6-170">Program.cs ファイルを開き、行 `Application.Run(new Form1());` を `Application.Run(new Form2());` に変更します。</span><span class="sxs-lookup"><span data-stu-id="bccf6-170">Open the Program.cs file and change the line `Application.Run(new Form1());` to `Application.Run(new Form2());`.</span></span>  
  
9. <span data-ttu-id="bccf6-171">**ソリューション エクスプ ローラー**を右クリックし、 **InheritanceTest**順に選択して**スタートアップ プロジェクトとして設定**します。</span><span class="sxs-lookup"><span data-stu-id="bccf6-171">In **Solution Explorer**, right-click the **InheritanceTest** project and select **Set As Startup Project**.</span></span>  
  
10. <span data-ttu-id="bccf6-172">**ソリューション エクスプ ローラー**を右クリックし、 **InheritanceTest**順に選択して**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="bccf6-172">In **Solution Explorer**, right-click the **InheritanceTest** project and select **Properties**.</span></span>  
  
11. <span data-ttu-id="bccf6-173">**InheritanceTest**プロパティ ページ、設定、**スタートアップ オブジェクト**継承されたフォーム (**Form2**)。</span><span class="sxs-lookup"><span data-stu-id="bccf6-173">In the **InheritanceTest** property pages, set the **Startup object** to be the inherited form (**Form2**).</span></span>  
  
12. <span data-ttu-id="bccf6-174">F5 を押してアプリケーションを実行し、継承されたフォームの動作を確認します。</span><span class="sxs-lookup"><span data-stu-id="bccf6-174">Press F5 to run the application, and observe the behavior of the inherited form.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="bccf6-175">次の手順</span><span class="sxs-lookup"><span data-stu-id="bccf6-175">Next Steps</span></span>  
 <span data-ttu-id="bccf6-176">ユーザー コントロールの継承はほぼ同じ方法で機能します。</span><span class="sxs-lookup"><span data-stu-id="bccf6-176">Inheritance for user controls works in much the same way.</span></span> <span data-ttu-id="bccf6-177">新しいクラス ライブラリ プロジェクトを開き、ユーザー コントロールを追加します。</span><span class="sxs-lookup"><span data-stu-id="bccf6-177">Open a new class library project and add a user control.</span></span> <span data-ttu-id="bccf6-178">内在コントロールを配置し、プロジェクトをコンパイルします。</span><span class="sxs-lookup"><span data-stu-id="bccf6-178">Place constituent controls on it and compile the project.</span></span> <span data-ttu-id="bccf6-179">別の新しいクラス ライブラリ プロジェクトを開き、コンパイル済みのクラス ライブラリへの参照を追加します。</span><span class="sxs-lookup"><span data-stu-id="bccf6-179">Open another new class library project and add a reference to the compiled class library.</span></span> <span data-ttu-id="bccf6-180">また、[継承コントロールを追加してみてください (を通じて、**新しい項目の追加**] ダイアログ ボックス) をプロジェクトを使用して、**継承ピッカー**します。</span><span class="sxs-lookup"><span data-stu-id="bccf6-180">Also, try adding an inherited control (through the **Add New Items** dialog box) to the project and using the **Inheritance Picker**.</span></span> <span data-ttu-id="bccf6-181">ユーザー コントロールを追加し、変更、 `Inherits` (`:` Visual c#) ステートメント。</span><span class="sxs-lookup"><span data-stu-id="bccf6-181">Add a user control, and change the `Inherits` (`:` in Visual C#) statement.</span></span> <span data-ttu-id="bccf6-182">詳細については、「[方法 :Windows フォームを継承する](how-to-inherit-windows-forms.md)します。</span><span class="sxs-lookup"><span data-stu-id="bccf6-182">For more information, see [How to: Inherit Windows Forms](how-to-inherit-windows-forms.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bccf6-183">関連項目</span><span class="sxs-lookup"><span data-stu-id="bccf6-183">See also</span></span>

- [<span data-ttu-id="bccf6-184">方法: Windows フォームを継承します。</span><span class="sxs-lookup"><span data-stu-id="bccf6-184">How to: Inherit Windows Forms</span></span>](how-to-inherit-windows-forms.md)
- [<span data-ttu-id="bccf6-185">Windows フォームのビジュアルの継承</span><span class="sxs-lookup"><span data-stu-id="bccf6-185">Windows Forms Visual Inheritance</span></span>](windows-forms-visual-inheritance.md)
- [<span data-ttu-id="bccf6-186">Windows フォーム</span><span class="sxs-lookup"><span data-stu-id="bccf6-186">Windows Forms</span></span>](../index.md)
