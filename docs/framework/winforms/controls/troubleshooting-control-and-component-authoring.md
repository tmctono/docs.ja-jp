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
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 5d3aa715590a10391bafa08a85265842ee8cedfb
ms.sourcegitcommit: 5a28f8eb071fcc09b045b0c4ae4b96898673192e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2019
ms.locfileid: "73197115"
---
# <a name="troubleshoot-control-and-component-authoring"></a><span data-ttu-id="84aa0-102">コントロールとコンポーネントの作成に関するトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="84aa0-102">Troubleshoot Control and Component Authoring</span></span>

<span data-ttu-id="84aa0-103">このトピックでは、コンポーネントとコントロールの開発時に発生する一般的な問題について説明します。</span><span class="sxs-lookup"><span data-stu-id="84aa0-103">This topic lists the following common problems that arise when developing components and controls:</span></span>

- <span data-ttu-id="84aa0-104">ツールボックスにコントロールを追加できない</span><span class="sxs-lookup"><span data-stu-id="84aa0-104">Cannot Add Control to Toolbox</span></span>

- <span data-ttu-id="84aa0-105">Windows フォームのユーザー コントロールまたはコンポーネントをデバッグできない</span><span class="sxs-lookup"><span data-stu-id="84aa0-105">Cannot Debug the Windows Forms User Control or Component</span></span>

- <span data-ttu-id="84aa0-106">継承されたコントロールまたはコンポーネントでイベントが 2 回発生する</span><span class="sxs-lookup"><span data-stu-id="84aa0-106">Event Is Raised Twice in Inherited Control or Component</span></span>

- <span data-ttu-id="84aa0-107">デザイン時エラー: "コンポーネント '*コンポーネント名*' を生成できませんでした"</span><span class="sxs-lookup"><span data-stu-id="84aa0-107">Design-Time Error: "Failed to Create Component '*Component Name*'"</span></span>

- <span data-ttu-id="84aa0-108">STAThreadAttribute</span><span class="sxs-lookup"><span data-stu-id="84aa0-108">STAThreadAttribute</span></span>

- <span data-ttu-id="84aa0-109">ツールボックスにコンポーネント アイコンが表示されない</span><span class="sxs-lookup"><span data-stu-id="84aa0-109">Component Icon Does Not Appear in Toolbox</span></span>

## <a name="cannot-add-control-to-toolbox"></a><span data-ttu-id="84aa0-110">ツールボックスにコントロールを追加できない</span><span class="sxs-lookup"><span data-stu-id="84aa0-110">Cannot Add Control to Toolbox</span></span>

<span data-ttu-id="84aa0-111">別のプロジェクトで作成したカスタム コントロールまたはサード パーティ製コントロールを**ツールボックス**に追加する場合は、手動で追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="84aa0-111">If you want to add a custom control that you created in another project or a third-party control to the **Toolbox**, you must do so manually.</span></span> <span data-ttu-id="84aa0-112">現在のプロジェクトにコントロールまたはコンポーネントが含まれている場合は、**ツールボックス**に自動的に表示されます。</span><span class="sxs-lookup"><span data-stu-id="84aa0-112">If the current project contains your control or component, it should appear in the **Toolbox** automatically.</span></span> <span data-ttu-id="84aa0-113">詳細については、「[チュートリアル: ツールボックスへのカスタム コンポーネントの自動設定](walkthrough-automatically-populating-the-toolbox-with-custom-components.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="84aa0-113">For more information, see [Walkthrough: Automatically Populating the Toolbox with Custom Components](walkthrough-automatically-populating-the-toolbox-with-custom-components.md).</span></span>

### <a name="to-add-a-control-to-the-toolbox"></a><span data-ttu-id="84aa0-114">ツールボックスにコントロールを追加するには</span><span class="sxs-lookup"><span data-stu-id="84aa0-114">To add a control to the Toolbox</span></span>

1. <span data-ttu-id="84aa0-115">**[ツールボックス]** を右クリックし、ショートカット メニューの **[アイテムの選択]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="84aa0-115">Right-click the **Toolbox** and from the shortcut menu, select **Choose Items**.</span></span>

2. <span data-ttu-id="84aa0-116">**[ツールボックス アイテムの選択]** ダイアログ ボックスで、コンポーネントを追加します。</span><span class="sxs-lookup"><span data-stu-id="84aa0-116">In the **Choose Toolbox Items** dialog box, add the component:</span></span>

    - <span data-ttu-id="84aa0-117">.NET Framework コンポーネントまたはコントロールを追加する場合は、 **[.NET Framework コンポーネント]** タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="84aa0-117">If you want to add a .NET Framework component or control, click the **.NET Framework Components** tab.</span></span>

         <span data-ttu-id="84aa0-118">または</span><span class="sxs-lookup"><span data-stu-id="84aa0-118">– or –</span></span>

    - <span data-ttu-id="84aa0-119">COM コンポーネントまたは ActiveX コントロールを追加する場合は、 **[COM コンポーネント]** タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="84aa0-119">If you want to add a COM component or ActiveX control, click the **COM Components** tab.</span></span>

3. <span data-ttu-id="84aa0-120">ダイアログ ボックスにコントロールが表示されている場合は、コントロールが選択されていることを確認し、 **[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="84aa0-120">If your control is listed in the dialog box, confirm it is selected, and then click **OK**.</span></span>

     <span data-ttu-id="84aa0-121">コントロールが**ツールボックス**に追加されます。</span><span class="sxs-lookup"><span data-stu-id="84aa0-121">The control is added to the **Toolbox**.</span></span>

4. <span data-ttu-id="84aa0-122">ダイアログ ボックスにコントロールが表示されていない場合は、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="84aa0-122">If your control is not listed in the dialog box, do the following:</span></span>

    1. <span data-ttu-id="84aa0-123">**[参照]** ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="84aa0-123">Click the **Browse** button.</span></span>

    2. <span data-ttu-id="84aa0-124">コントロールが含まれた .dll ファイルがあるフォルダーを参照します。</span><span class="sxs-lookup"><span data-stu-id="84aa0-124">Browse to the folder that contains the .dll file that contains your control.</span></span>

    3. <span data-ttu-id="84aa0-125">.dll ファイルを選択し、 **[開く]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="84aa0-125">Select the .dll file and click **Open**.</span></span>

         <span data-ttu-id="84aa0-126">ダイアログ ボックスにコントロールが表示されます。</span><span class="sxs-lookup"><span data-stu-id="84aa0-126">Your control appears in the dialog box.</span></span>

    4. <span data-ttu-id="84aa0-127">コントロールが選択されていることを確認し、 **[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="84aa0-127">Confirm that your control is selected, and then click **OK**.</span></span>

         <span data-ttu-id="84aa0-128">コントロールが**ツールボックス**に追加されます。</span><span class="sxs-lookup"><span data-stu-id="84aa0-128">Your control is added to the **Toolbox**.</span></span>

## <a name="cannot-debug-the-windows-forms-user-control-or-component"></a><span data-ttu-id="84aa0-129">Windows フォームのユーザー コントロールまたはコンポーネントをデバッグできない</span><span class="sxs-lookup"><span data-stu-id="84aa0-129">Cannot Debug the Windows Forms User Control or Component</span></span>

<span data-ttu-id="84aa0-130">コントロールが <xref:System.Windows.Forms.UserControl> クラスから派生している場合は、テストコンテナーを使用して実行時の動作をデバッグできます。</span><span class="sxs-lookup"><span data-stu-id="84aa0-130">If your control derives from the <xref:System.Windows.Forms.UserControl> class, you can debug its run-time behavior with the test container.</span></span> <span data-ttu-id="84aa0-131">詳細については、「[方法: UserControl の実行時の動作をテストする](how-to-test-the-run-time-behavior-of-a-usercontrol.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="84aa0-131">For more information, see [How to: Test the Run-Time Behavior of a UserControl](how-to-test-the-run-time-behavior-of-a-usercontrol.md).</span></span>

<span data-ttu-id="84aa0-132">他のカスタム コントロールやカスタム コンポーネントはスタンドアロン プロジェクトではありません。</span><span class="sxs-lookup"><span data-stu-id="84aa0-132">Other custom controls and components are not stand-alone projects.</span></span> <span data-ttu-id="84aa0-133">そのため、Windows フォーム プロジェクトなどのアプリケーションでホストする必要があります。</span><span class="sxs-lookup"><span data-stu-id="84aa0-133">They must be hosted by an application such as a Windows Forms project.</span></span> <span data-ttu-id="84aa0-134">コントロールまたはコンポーネントをデバッグするには、Windows フォーム プロジェクトに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="84aa0-134">To debug a control or component, you must add it to a Windows Forms project.</span></span>

### <a name="to-debug-a-control-or-component"></a><span data-ttu-id="84aa0-135">コントロールまたはコンポーネントをデバッグするには</span><span class="sxs-lookup"><span data-stu-id="84aa0-135">To debug a control or component</span></span>

1. <span data-ttu-id="84aa0-136">**[ビルド]** メニューの **[ソリューションのビルド]** をクリックして、ソリューションをビルドします。</span><span class="sxs-lookup"><span data-stu-id="84aa0-136">From the **Build** menu, click **Build Solution** to build your solution.</span></span>

2. <span data-ttu-id="84aa0-137">**[ファイル]** メニューの **[追加]** をクリックし、 **[新しいプロジェクト]** をクリックして、アプリケーションにテスト プロジェクトを追加します。</span><span class="sxs-lookup"><span data-stu-id="84aa0-137">From the **File** menu, choose **Add**, and then **New Project** to add a test project to your application.</span></span>

3. <span data-ttu-id="84aa0-138">**[新しいプロジェクトの追加]** ダイアログ ボックスで、プロジェクトの種類として **[Windows アプリケーション]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="84aa0-138">In the **Add New Project** dialog box choose **Windows Application** for the type of project.</span></span>

4. <span data-ttu-id="84aa0-139">**ソリューション エクスプローラー**で、新しいプロジェクトの **[参照設定]** ノードを右クリックします。</span><span class="sxs-lookup"><span data-stu-id="84aa0-139">In **Solution Explorer**, right-click the **References** node for the new project.</span></span> <span data-ttu-id="84aa0-140">ショートカット メニューの **[参照の追加]** をクリックして、コントロールまたはコンポーネントを含むプロジェクトへの参照を追加します。</span><span class="sxs-lookup"><span data-stu-id="84aa0-140">On the shortcut menu, click **Add Reference** to add a reference to the project containing the control or component.</span></span>

5. <span data-ttu-id="84aa0-141">テスト プロジェクトにコントロールまたはコンポーネントのインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="84aa0-141">Create an instance of your control or component in the test project.</span></span> <span data-ttu-id="84aa0-142">コンポーネントが**ツールボックス**に表示されている場合は、デザイナー画面にドラッグできます。または、次のコード例に示すように、インスタンスをプログラムで作成できます。</span><span class="sxs-lookup"><span data-stu-id="84aa0-142">If your component is in the **Toolbox**, you can drag it to your designer surface, or you can create the instance programmatically, as shown in the following code example.</span></span>

    ```vb
    Dim Component1 As New MyNeatComponent()
    ```

    ```csharp
    MyNeatComponent Component1 = new MyNeatComponent();
    ```

   <span data-ttu-id="84aa0-143">これで、コントロールまたはコンポーネントを通常どおりデバッグできるようになります。</span><span class="sxs-lookup"><span data-stu-id="84aa0-143">You can now debug your control or component as usual.</span></span>

<span data-ttu-id="84aa0-144">デバッグの詳細については、「[Visual Studio でのデバッグ](/visualstudio/debugger/debugger-feature-tour)」および「[チュートリアル : カスタム Windows フォーム コントロールのデザイン時のデバッグ](walkthrough-debugging-custom-windows-forms-controls-at-design-time.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="84aa0-144">For more information about debugging, see [Debugging in Visual Studio](/visualstudio/debugger/debugger-feature-tour) and [Walkthrough: Debugging Custom Windows Forms Controls at Design Time](walkthrough-debugging-custom-windows-forms-controls-at-design-time.md).</span></span>

## <a name="event-is-raised-twice-in-inherited-control-or-component"></a><span data-ttu-id="84aa0-145">継承されたコントロールまたはコンポーネントでイベントが 2 回発生する</span><span class="sxs-lookup"><span data-stu-id="84aa0-145">Event Is Raised Twice in Inherited Control or Component</span></span>

<span data-ttu-id="84aa0-146">`Handles` 句が重複していることが原因と考えられます。</span><span class="sxs-lookup"><span data-stu-id="84aa0-146">This is likely due to a duplicated `Handles` clause.</span></span> <span data-ttu-id="84aa0-147">詳細については、「[Visual Basic での継承されたイベント ハンドラーのトラブルシューティング](~/docs/visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="84aa0-147">For more information, see [Troubleshooting Inherited Event Handlers in Visual Basic](~/docs/visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md).</span></span>

## <a name="design-time-error-failed-to-create-component-component-name"></a><span data-ttu-id="84aa0-148">デザイン時エラー: "コンポーネント 'コンポーネント名' を生成できませんでした"</span><span class="sxs-lookup"><span data-stu-id="84aa0-148">Design-Time Error: "Failed to Create Component 'Component Name'"</span></span>

<span data-ttu-id="84aa0-149">コンポーネントまたはコントロールは、パラメーターなしのパラメーターなしのコンストラクターを提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="84aa0-149">Your component or control must provide a parameterless constructor with no parameters.</span></span> <span data-ttu-id="84aa0-150">デザイン環境では、コンポーネントまたはコントロールのインスタンスを作成するときに、パラメーターを受け取るコンストラクター オーバーロードにパラメーターを提供しません。</span><span class="sxs-lookup"><span data-stu-id="84aa0-150">When the design environment creates an instance of your component or control, it does not attempt to provide any parameters to constructor overloads that take parameters.</span></span>

## <a name="stathreadattribute"></a><span data-ttu-id="84aa0-151">STAThreadAttribute</span><span class="sxs-lookup"><span data-stu-id="84aa0-151">STAThreadAttribute</span></span>

<span data-ttu-id="84aa0-152"><xref:System.STAThreadAttribute> は、シングルスレッドアパートメントモデルを使用 Windows フォームことを共通言語ランタイム (CLR) に通知します。</span><span class="sxs-lookup"><span data-stu-id="84aa0-152">The <xref:System.STAThreadAttribute> informs the common language runtime (CLR) that Windows Forms uses the single-threaded apartment model.</span></span> <span data-ttu-id="84aa0-153">この属性を Windows フォーム アプリケーションの `Main` メソッドに適用していない場合、意図しない動作が発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="84aa0-153">You may notice unintended behavior if you do not apply this attribute to your Windows Forms application's `Main` method.</span></span> <span data-ttu-id="84aa0-154">たとえば、<xref:System.Windows.Forms.ListView>のようなコントロールでは、背景イメージが表示されない場合があります。</span><span class="sxs-lookup"><span data-stu-id="84aa0-154">For example, background images may not appear for controls like <xref:System.Windows.Forms.ListView>.</span></span> <span data-ttu-id="84aa0-155">また、一部のコントロールでは、オートコンプリートやドラッグ アンド ドロップの動作を正常に行うためにこの属性が必要になる場合もあります。</span><span class="sxs-lookup"><span data-stu-id="84aa0-155">Some controls may also require this attribute for correct AutoComplete and drag-and-drop behavior.</span></span>

## <a name="component-icon-does-not-appear-in-toolbox"></a><span data-ttu-id="84aa0-156">ツールボックスにコンポーネント アイコンが表示されない</span><span class="sxs-lookup"><span data-stu-id="84aa0-156">Component Icon Does Not Appear in Toolbox</span></span>

<span data-ttu-id="84aa0-157"><xref:System.Drawing.ToolboxBitmapAttribute> を使用してアイコンをカスタムコンポーネントに関連付けた場合、ツールボックスには自動生成されたコンポーネントのビットマップが表示されません。</span><span class="sxs-lookup"><span data-stu-id="84aa0-157">When you use <xref:System.Drawing.ToolboxBitmapAttribute> to associate an icon with your custom component, the bitmap does not appear in the Toolbox for autogenerated components.</span></span> <span data-ttu-id="84aa0-158">ビットマップを表示するには、 **[ツールボックス アイテムの選択]** ダイアログ ボックスを使用してコントロールを再読み込みします。</span><span class="sxs-lookup"><span data-stu-id="84aa0-158">To see the bitmap, reload the control by using the **Choose Toolbox Items** dialog box.</span></span> <span data-ttu-id="84aa0-159">詳細については、「[方法 : コントロールにツールボックス ビットマップを指定する](how-to-provide-a-toolbox-bitmap-for-a-control.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="84aa0-159">For more information, see [How to: Provide a Toolbox Bitmap for a Control](how-to-provide-a-toolbox-bitmap-for-a-control.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="84aa0-160">関連項目</span><span class="sxs-lookup"><span data-stu-id="84aa0-160">See also</span></span>

- [<span data-ttu-id="84aa0-161">デザイン時の Windows フォーム コントロールの開発</span><span class="sxs-lookup"><span data-stu-id="84aa0-161">Developing Windows Forms Controls at Design Time</span></span>](developing-windows-forms-controls-at-design-time.md)
- [<span data-ttu-id="84aa0-162">チュートリアル: ツールボックスへのカスタム コンポーネントの自動設定</span><span class="sxs-lookup"><span data-stu-id="84aa0-162">Walkthrough: Automatically Populating the Toolbox with Custom Components</span></span>](walkthrough-automatically-populating-the-toolbox-with-custom-components.md)
- [<span data-ttu-id="84aa0-163">方法: UserControl の実行時の動作をテストする</span><span class="sxs-lookup"><span data-stu-id="84aa0-163">How to: Test the Run-Time Behavior of a UserControl</span></span>](how-to-test-the-run-time-behavior-of-a-usercontrol.md)
- [<span data-ttu-id="84aa0-164">チュートリアル: カスタム Windows フォーム コントロールのデザイン時のデバッグ</span><span class="sxs-lookup"><span data-stu-id="84aa0-164">Walkthrough: Debugging Custom Windows Forms Controls at Design Time</span></span>](walkthrough-debugging-custom-windows-forms-controls-at-design-time.md)
