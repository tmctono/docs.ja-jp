---
title: コントロールとコンポーネントの作成時のトラブルシューティング
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- troubleshooting components
- troubleshooting controls [Windows Forms]
- controls [Windows Forms], troubleshooting
- components [Windows Forms], troubleshooting
- Windows Forms controls, debugging
ms.assetid: e9c8c099-2271-4737-882f-50f336c7a55e
ms.openlocfilehash: c05e849705f851b51a362d3a1d1d3f81a9eaf0e4
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69923596"
---
# <a name="troubleshooting-control-and-component-authoring"></a><span data-ttu-id="ae24f-102">コントロールとコンポーネントの作成時のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="ae24f-102">Troubleshooting Control and Component Authoring</span></span>
<span data-ttu-id="ae24f-103">このトピックでは、コンポーネントとコントロールの開発時に発生する次の一般的な問題について説明します。</span><span class="sxs-lookup"><span data-stu-id="ae24f-103">This topic lists the following common problems that arise when developing components and controls.</span></span> <span data-ttu-id="ae24f-104">詳細については、「[コンポーネントによるプログラミング](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/0ffkdtkf(v=vs.120))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ae24f-104">For more information, see [Programming with Components](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/0ffkdtkf(v=vs.120)).</span></span>  
  
- <span data-ttu-id="ae24f-105">ツールボックスにコントロールを追加できない</span><span class="sxs-lookup"><span data-stu-id="ae24f-105">Cannot Add Control to Toolbox</span></span>  
  
- <span data-ttu-id="ae24f-106">Windows フォームのユーザー コントロールまたはコンポーネントをデバッグできない</span><span class="sxs-lookup"><span data-stu-id="ae24f-106">Cannot Debug the Windows Forms User Control or Component</span></span>  
  
- <span data-ttu-id="ae24f-107">継承されたコントロールまたはコンポーネントでイベントが 2 回発生する</span><span class="sxs-lookup"><span data-stu-id="ae24f-107">Event Is Raised Twice in Inherited Control or Component</span></span>  
  
- <span data-ttu-id="ae24f-108">デザイン時エラー:"コンポーネント '*コンポーネント名*' を作成できませんでした"</span><span class="sxs-lookup"><span data-stu-id="ae24f-108">Design-Time Error: "Failed to Create Component '*Component Name*'"</span></span>  
  
- <span data-ttu-id="ae24f-109">STAThreadAttribute</span><span class="sxs-lookup"><span data-stu-id="ae24f-109">STAThreadAttribute</span></span>  
  
- <span data-ttu-id="ae24f-110">ツールボックスにコンポーネント アイコンが表示されない</span><span class="sxs-lookup"><span data-stu-id="ae24f-110">Component Icon Does Not Appear in Toolbox</span></span>  
  
## <a name="cannot-add-control-to-toolbox"></a><span data-ttu-id="ae24f-111">ツールボックスにコントロールを追加できない</span><span class="sxs-lookup"><span data-stu-id="ae24f-111">Cannot Add Control to Toolbox</span></span>  
 <span data-ttu-id="ae24f-112">別のプロジェクトで作成したカスタム コントロールまたはサード パーティ製コントロールを**ツールボックス**に追加する場合は、手動で追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ae24f-112">If you want to add a custom control that you created in another project or a third-party control to the **Toolbox**, you must do so manually.</span></span> <span data-ttu-id="ae24f-113">現在のプロジェクトにコントロールまたはコンポーネントが含まれている場合は、**ツールボックス**に自動的に表示されます。</span><span class="sxs-lookup"><span data-stu-id="ae24f-113">If the current project contains your control or component, it should appear in the **Toolbox** automatically.</span></span> <span data-ttu-id="ae24f-114">詳細については、「[チュートリアル:ツールボックスにカスタムコンポーネント](walkthrough-automatically-populating-the-toolbox-with-custom-components.md)を自動的に設定します。</span><span class="sxs-lookup"><span data-stu-id="ae24f-114">For more information, see [Walkthrough: Automatically Populating the Toolbox with Custom Components](walkthrough-automatically-populating-the-toolbox-with-custom-components.md).</span></span>  
  
#### <a name="to-add-a-control-to-the-toolbox"></a><span data-ttu-id="ae24f-115">ツールボックスにコントロールを追加するには</span><span class="sxs-lookup"><span data-stu-id="ae24f-115">To add a control to the Toolbox</span></span>  
  
1. <span data-ttu-id="ae24f-116">**[ツールボックス]** を右クリックし、ショートカット メニューの **[アイテムの選択]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ae24f-116">Right-click the **Toolbox** and from the shortcut menu, select **Choose Items**.</span></span>  
  
2. <span data-ttu-id="ae24f-117">**[ツールボックス アイテムの選択]** ダイアログ ボックスで、コンポーネントを追加します。</span><span class="sxs-lookup"><span data-stu-id="ae24f-117">In the **Choose Toolbox Items** dialog box, add the component:</span></span>  
  
    - <span data-ttu-id="ae24f-118">.NET Framework コンポーネントまたはコントロールを追加する場合は、 **[.NET Framework コンポーネント]** タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="ae24f-118">If you want to add a .NET Framework component or control, click the **.NET Framework Components** tab.</span></span>  
  
         <span data-ttu-id="ae24f-119">または</span><span class="sxs-lookup"><span data-stu-id="ae24f-119">– or –</span></span>  
  
    - <span data-ttu-id="ae24f-120">COM コンポーネントまたは ActiveX コントロールを追加する場合は、 **[COM コンポーネント]** タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="ae24f-120">If you want to add a COM component or ActiveX control, click the **COM Components** tab.</span></span>  
  
3. <span data-ttu-id="ae24f-121">ダイアログ ボックスにコントロールが表示されている場合は、コントロールが選択されていることを確認し、 **[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ae24f-121">If your control is listed in the dialog box, confirm it is selected, and then click **OK**.</span></span>  
  
     <span data-ttu-id="ae24f-122">コントロールが**ツールボックス**に追加されます。</span><span class="sxs-lookup"><span data-stu-id="ae24f-122">The control is added to the **Toolbox**.</span></span>  
  
4. <span data-ttu-id="ae24f-123">ダイアログ ボックスにコントロールが表示されていない場合は、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="ae24f-123">If your control is not listed in the dialog box, do the following:</span></span>  
  
    1. <span data-ttu-id="ae24f-124">**[参照]** ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="ae24f-124">Click the **Browse** button.</span></span>  
  
    2. <span data-ttu-id="ae24f-125">コントロールが含まれた .dll ファイルがあるフォルダーを参照します。</span><span class="sxs-lookup"><span data-stu-id="ae24f-125">Browse to the folder that contains the .dll file that contains your control.</span></span>  
  
    3. <span data-ttu-id="ae24f-126">.dll ファイルを選択し、 **[開く]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ae24f-126">Select the .dll file and click **Open**.</span></span>  
  
         <span data-ttu-id="ae24f-127">ダイアログ ボックスにコントロールが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ae24f-127">Your control appears in the dialog box.</span></span>  
  
    4. <span data-ttu-id="ae24f-128">コントロールが選択されていることを確認し、 **[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ae24f-128">Confirm that your control is selected, and then click **OK**.</span></span>  
  
         <span data-ttu-id="ae24f-129">コントロールが**ツールボックス**に追加されます。</span><span class="sxs-lookup"><span data-stu-id="ae24f-129">Your control is added to the **Toolbox**.</span></span>  
  
## <a name="cannot-debug-the-windows-forms-user-control-or-component"></a><span data-ttu-id="ae24f-130">Windows フォームのユーザー コントロールまたはコンポーネントをデバッグできない</span><span class="sxs-lookup"><span data-stu-id="ae24f-130">Cannot Debug the Windows Forms User Control or Component</span></span>  
 <span data-ttu-id="ae24f-131">コントロールが<xref:System.Windows.Forms.UserControl>クラスから派生している場合は、テストコンテナーで実行時の動作をデバッグできます。</span><span class="sxs-lookup"><span data-stu-id="ae24f-131">If your control derives from the <xref:System.Windows.Forms.UserControl> class, you can debug its run-time behavior with the test container.</span></span> <span data-ttu-id="ae24f-132">詳細については、「[方法 :UserControl](how-to-test-the-run-time-behavior-of-a-usercontrol.md)の実行時の動作をテストします。</span><span class="sxs-lookup"><span data-stu-id="ae24f-132">For more information, see [How to: Test the Run-Time Behavior of a UserControl](how-to-test-the-run-time-behavior-of-a-usercontrol.md).</span></span>  
  
 <span data-ttu-id="ae24f-133">他のカスタム コントロールやカスタム コンポーネントはスタンドアロン プロジェクトではありません。</span><span class="sxs-lookup"><span data-stu-id="ae24f-133">Other custom controls and components are not stand-alone projects.</span></span> <span data-ttu-id="ae24f-134">そのため、Windows フォーム プロジェクトなどのアプリケーションでホストする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ae24f-134">They must be hosted by an application such as a Windows Forms project.</span></span> <span data-ttu-id="ae24f-135">コントロールまたはコンポーネントをデバッグするには、Windows フォーム プロジェクトに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ae24f-135">To debug a control or component, you must add it to a Windows Forms project.</span></span>  
  
#### <a name="to-debug-a-control-or-component"></a><span data-ttu-id="ae24f-136">コントロールまたはコンポーネントをデバッグするには</span><span class="sxs-lookup"><span data-stu-id="ae24f-136">To debug a control or component</span></span>  
  
1. <span data-ttu-id="ae24f-137">**[ビルド]** メニューの **[ソリューションのビルド]** をクリックして、ソリューションをビルドします。</span><span class="sxs-lookup"><span data-stu-id="ae24f-137">From the **Build** menu, click **Build Solution** to build your solution.</span></span>  
  
2. <span data-ttu-id="ae24f-138">**[ファイル]** メニューの **[追加]** をクリックし、 **[新しいプロジェクト]** をクリックして、アプリケーションにテスト プロジェクトを追加します。</span><span class="sxs-lookup"><span data-stu-id="ae24f-138">From the **File** menu, choose **Add**, and then **New Project** to add a test project to your application.</span></span>  
  
3. <span data-ttu-id="ae24f-139">**[新しいプロジェクトの追加]** ダイアログ ボックスで、プロジェクトの種類として **[Windows アプリケーション]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="ae24f-139">In the **Add New Project** dialog box choose **Windows Application** for the type of project.</span></span>  
  
4. <span data-ttu-id="ae24f-140">**ソリューション エクスプローラー**で、新しいプロジェクトの **[参照設定]** ノードを右クリックします。</span><span class="sxs-lookup"><span data-stu-id="ae24f-140">In **Solution Explorer**, right-click the **References** node for the new project.</span></span> <span data-ttu-id="ae24f-141">ショートカット メニューの **[参照の追加]** をクリックして、コントロールまたはコンポーネントを含むプロジェクトへの参照を追加します。</span><span class="sxs-lookup"><span data-stu-id="ae24f-141">On the shortcut menu, click **Add Reference** to add a reference to the project containing the control or component.</span></span>  
  
5. <span data-ttu-id="ae24f-142">テスト プロジェクトにコントロールまたはコンポーネントのインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="ae24f-142">Create an instance of your control or component in the test project.</span></span> <span data-ttu-id="ae24f-143">コンポーネントが**ツールボックス**に表示されている場合は、デザイナー画面にドラッグできます。または、次のコード例に示すように、インスタンスをプログラムで作成できます。</span><span class="sxs-lookup"><span data-stu-id="ae24f-143">If your component is in the **Toolbox**, you can drag it to your designer surface, or you can create the instance programmatically, as shown in the following code example.</span></span>  
  
    ```vb  
    Dim Component1 As New MyNeatComponent()  
    ```  
  
    ```csharp  
    MyNeatComponent Component1 = new MyNeatComponent();  
    ```  
  
     <span data-ttu-id="ae24f-144">これで、コントロールまたはコンポーネントを通常どおりデバッグできるようになります。</span><span class="sxs-lookup"><span data-stu-id="ae24f-144">You can now debug your control or component as usual.</span></span>  
  
 <span data-ttu-id="ae24f-145">デバッグの詳細については、「 [Visual Studio でのデバッグ](/visualstudio/debugger/debugging-in-visual-studio)」および[「チュートリアル:デザイン時](walkthrough-debugging-custom-windows-forms-controls-at-design-time.md)にカスタム Windows フォームコントロールをデバッグする。</span><span class="sxs-lookup"><span data-stu-id="ae24f-145">For more information about debugging, see [Debugging in Visual Studio](/visualstudio/debugger/debugging-in-visual-studio) and [Walkthrough: Debugging Custom Windows Forms Controls at Design Time](walkthrough-debugging-custom-windows-forms-controls-at-design-time.md).</span></span>  
  
## <a name="event-is-raised-twice-in-inherited-control-or-component"></a><span data-ttu-id="ae24f-146">継承されたコントロールまたはコンポーネントでイベントが 2 回発生する</span><span class="sxs-lookup"><span data-stu-id="ae24f-146">Event Is Raised Twice in Inherited Control or Component</span></span>  
 <span data-ttu-id="ae24f-147">`Handles` 句が重複していることが原因と考えられます。</span><span class="sxs-lookup"><span data-stu-id="ae24f-147">This is likely due to a duplicated `Handles` clause.</span></span> <span data-ttu-id="ae24f-148">詳細については、「[Visual Basic での継承されたイベント ハンドラーのトラブルシューティング](../../../visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ae24f-148">For more information, see [Troubleshooting Inherited Event Handlers in Visual Basic](../../../visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md).</span></span>  
  
## <a name="design-time-error-failed-to-create-component-component-name"></a><span data-ttu-id="ae24f-149">デザイン時エラー:"コンポーネント ' コンポーネント名 ' を作成できませんでした"</span><span class="sxs-lookup"><span data-stu-id="ae24f-149">Design-Time Error: "Failed to Create Component 'Component Name'"</span></span>  
 <span data-ttu-id="ae24f-150">コンポーネントまたはコントロールは、パラメーターなしのパラメーターなしのコンストラクターを提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ae24f-150">Your component or control must provide a parameterless constructor with no parameters.</span></span> <span data-ttu-id="ae24f-151">デザイン環境では、コンポーネントまたはコントロールのインスタンスを作成するときに、パラメーターを受け取るコンストラクター オーバーロードにパラメーターを提供しません。</span><span class="sxs-lookup"><span data-stu-id="ae24f-151">When the design environment creates an instance of your component or control, it does not attempt to provide any parameters to constructor overloads that take parameters.</span></span>  
  
## <a name="stathreadattribute"></a><span data-ttu-id="ae24f-152">STAThreadAttribute</span><span class="sxs-lookup"><span data-stu-id="ae24f-152">STAThreadAttribute</span></span>  
 <span data-ttu-id="ae24f-153">は<xref:System.STAThreadAttribute> 、シングルスレッドアパートメントモデルを使用 Windows フォームことを共通言語ランタイム (CLR) に通知します。</span><span class="sxs-lookup"><span data-stu-id="ae24f-153">The <xref:System.STAThreadAttribute> informs the common language runtime (CLR) that Windows Forms uses the single-threaded apartment model.</span></span> <span data-ttu-id="ae24f-154">この属性を Windows フォーム アプリケーションの `Main` メソッドに適用していない場合、意図しない動作が発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="ae24f-154">You may notice unintended behavior if you do not apply this attribute to your Windows Forms application's `Main` method.</span></span> <span data-ttu-id="ae24f-155">たとえば、のような<xref:System.Windows.Forms.ListView>コントロールでは、背景イメージが表示されない場合があります。</span><span class="sxs-lookup"><span data-stu-id="ae24f-155">For example, background images may not appear for controls like <xref:System.Windows.Forms.ListView>.</span></span> <span data-ttu-id="ae24f-156">また、一部のコントロールでは、オートコンプリートやドラッグ アンド ドロップの動作を正常に行うためにこの属性が必要になる場合もあります。</span><span class="sxs-lookup"><span data-stu-id="ae24f-156">Some controls may also require this attribute for correct AutoComplete and drag-and-drop behavior.</span></span>  
  
## <a name="component-icon-does-not-appear-in-toolbox"></a><span data-ttu-id="ae24f-157">ツールボックスにコンポーネント アイコンが表示されない</span><span class="sxs-lookup"><span data-stu-id="ae24f-157">Component Icon Does Not Appear in Toolbox</span></span>  
 <span data-ttu-id="ae24f-158">を使用<xref:System.Drawing.ToolboxBitmapAttribute>してアイコンをカスタムコンポーネントに関連付けた場合、ツールボックスには自動生成されたコンポーネントのビットマップが表示されません。</span><span class="sxs-lookup"><span data-stu-id="ae24f-158">When you use <xref:System.Drawing.ToolboxBitmapAttribute> to associate an icon with your custom component, the bitmap does not appear in the Toolbox for autogenerated components.</span></span> <span data-ttu-id="ae24f-159">ビットマップを表示するには、 **[ツールボックス アイテムの選択]** ダイアログ ボックスを使用してコントロールを再読み込みします。</span><span class="sxs-lookup"><span data-stu-id="ae24f-159">To see the bitmap, reload the control by using the **Choose Toolbox Items** dialog box.</span></span> <span data-ttu-id="ae24f-160">詳細については、「[方法 :コントロール](how-to-provide-a-toolbox-bitmap-for-a-control.md)のツールボックスビットマップを提供します。</span><span class="sxs-lookup"><span data-stu-id="ae24f-160">For more information, see [How to: Provide a Toolbox Bitmap for a Control](how-to-provide-a-toolbox-bitmap-for-a-control.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae24f-161">関連項目</span><span class="sxs-lookup"><span data-stu-id="ae24f-161">See also</span></span>

- [<span data-ttu-id="ae24f-162">デザイン時の Windows フォーム コントロールの開発</span><span class="sxs-lookup"><span data-stu-id="ae24f-162">Developing Windows Forms Controls at Design Time</span></span>](developing-windows-forms-controls-at-design-time.md)
- [<span data-ttu-id="ae24f-163">チュートリアル: ツールボックスへのカスタムコンポーネントの自動設定</span><span class="sxs-lookup"><span data-stu-id="ae24f-163">Walkthrough: Automatically Populating the Toolbox with Custom Components</span></span>](walkthrough-automatically-populating-the-toolbox-with-custom-components.md)
- [<span data-ttu-id="ae24f-164">方法: UserControl の実行時の動作をテストする</span><span class="sxs-lookup"><span data-stu-id="ae24f-164">How to: Test the Run-Time Behavior of a UserControl</span></span>](how-to-test-the-run-time-behavior-of-a-usercontrol.md)
- [<span data-ttu-id="ae24f-165">チュートリアル: カスタム Windows フォーム コントロールのデザイン時のデバッグ</span><span class="sxs-lookup"><span data-stu-id="ae24f-165">Walkthrough: Debugging Custom Windows Forms Controls at Design Time</span></span>](walkthrough-debugging-custom-windows-forms-controls-at-design-time.md)
- <span data-ttu-id="ae24f-166">[コンポーネントの作成](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/5dya64wy(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="ae24f-166">[Component Authoring](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/5dya64wy(v=vs.120))</span></span>
- <span data-ttu-id="ae24f-167">[デザイン時開発のトラブルシューティング](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171843(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="ae24f-167">[Troubleshooting Design-Time Development](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171843(v=vs.120))</span></span>
