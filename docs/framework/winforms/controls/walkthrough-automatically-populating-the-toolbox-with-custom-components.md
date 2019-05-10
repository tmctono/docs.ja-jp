---
title: 'チュートリアル: ツールボックスへのカスタム コンポーネントの自動設定'
ms.date: 03/30/2017
helpviewer_keywords:
- IToolboxService interface
- Toolbox [Windows Forms], populating
- custom components [Windows Forms], adding to Toolbox
ms.assetid: 2fa1e3e8-6b9f-42b2-97c0-2be57444dba4
ms.openlocfilehash: 876de650f9c182c0f82a02d1c5b356faa4f7f118
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65211154"
---
# <a name="walkthrough-automatically-populating-the-toolbox-with-custom-components"></a><span data-ttu-id="509a1-102">チュートリアル: ツールボックスへのカスタム コンポーネントの自動設定</span><span class="sxs-lookup"><span data-stu-id="509a1-102">Walkthrough: Automatically Populating the Toolbox with Custom Components</span></span>

<span data-ttu-id="509a1-103">自動的に表示されます、コンポーネントは現在開いているソリューション内のプロジェクトで定義されている場合、**ツールボックス**操作は必要とします。</span><span class="sxs-lookup"><span data-stu-id="509a1-103">If your components are defined by a project in the currently open solution, they will automatically appear in the **Toolbox**, with no action required by you.</span></span> <span data-ttu-id="509a1-104">手動で設定することができます、**ツールボックス**を使用して、カスタム コンポーネントで、[選択ツールボックス項目 ダイアログ ボックス (Visual Studio)](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/dyca0t6t(v=vs.100))が、**ツールボックス**を考慮に入れたソリューションの内の項目の次のすべての特性を持つ出力をビルドします。</span><span class="sxs-lookup"><span data-stu-id="509a1-104">You can also manually populate the **Toolbox** with your custom components by using the [Choose Toolbox Items Dialog Box (Visual Studio)](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/dyca0t6t(v=vs.100)), but the **Toolbox** takes account of items in your solution's build outputs with all the following characteristics:</span></span>

- <span data-ttu-id="509a1-105">実装<xref:System.ComponentModel.IComponent>;</span><span class="sxs-lookup"><span data-stu-id="509a1-105">Implements <xref:System.ComponentModel.IComponent>;</span></span>

- <span data-ttu-id="509a1-106"><xref:System.ComponentModel.ToolboxItemAttribute>設定`false`;</span><span class="sxs-lookup"><span data-stu-id="509a1-106">Does not have <xref:System.ComponentModel.ToolboxItemAttribute> set to `false`;</span></span>

- <span data-ttu-id="509a1-107"><xref:System.ComponentModel.DesignTimeVisibleAttribute>設定`false`します。</span><span class="sxs-lookup"><span data-stu-id="509a1-107">Does not have <xref:System.ComponentModel.DesignTimeVisibleAttribute> set to `false`.</span></span>

> [!NOTE]
> <span data-ttu-id="509a1-108">**ツールボックス**ソリューションのプロジェクトで構築されていない項目が表示されないように、参照のチェーンに従わない。</span><span class="sxs-lookup"><span data-stu-id="509a1-108">The **Toolbox** does not follow reference chains, so it won't display items that are not built by a project in your solution.</span></span>

<span data-ttu-id="509a1-109">このチュートリアルでは、カスタム コンポーネントを自動的にでの表示方法、**ツールボックス**したら、コンポーネントが構築されます。</span><span class="sxs-lookup"><span data-stu-id="509a1-109">This walkthrough demonstrates how a custom component automatically appears in the **Toolbox** once the component is built.</span></span> <span data-ttu-id="509a1-110">このチュートリアルでは、以下のタスクを行います。</span><span class="sxs-lookup"><span data-stu-id="509a1-110">Tasks illustrated in this walkthrough include:</span></span>

- <span data-ttu-id="509a1-111">Windows フォーム プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="509a1-111">Creating a Windows Forms project.</span></span>

- <span data-ttu-id="509a1-112">カスタム コンポーネントを作成します。</span><span class="sxs-lookup"><span data-stu-id="509a1-112">Creating a custom component.</span></span>

- <span data-ttu-id="509a1-113">カスタム コンポーネントのインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="509a1-113">Creating an instance of a custom component.</span></span>

- <span data-ttu-id="509a1-114">アンロードして、カスタム コンポーネントを再読み込みします。</span><span class="sxs-lookup"><span data-stu-id="509a1-114">Unloading and reloading a custom component.</span></span>

<span data-ttu-id="509a1-115">完了したらが表示されますが、**ツールボックス**は作成したコンポーネントが格納されます。</span><span class="sxs-lookup"><span data-stu-id="509a1-115">When you are finished, you will see that the **Toolbox** is populated with a component that you have created.</span></span>

## <a name="create-the-project"></a><span data-ttu-id="509a1-116">プロジェクトの作成</span><span class="sxs-lookup"><span data-stu-id="509a1-116">Create the project</span></span>

1. <span data-ttu-id="509a1-117">Visual Studio で、という名前の Windows ベースのアプリケーション プロジェクトを作成`ToolboxExample`(**ファイル** > **新規** > **プロジェクト** >  **Visual C#** または**Visual Basic** > **クラシック デスクトップ** > **Windows フォームアプリケーション**)。</span><span class="sxs-lookup"><span data-stu-id="509a1-117">In Visual Studio, create a Windows-based application project called `ToolboxExample` (**File** > **New** > **Project** > **Visual C#** or **Visual Basic** > **Classic Desktop** > **Windows Forms Application**).</span></span>

2. <span data-ttu-id="509a1-118">新しいコンポーネントをプロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="509a1-118">Add a new component to the project.</span></span> <span data-ttu-id="509a1-119">このプロジェクトに `DemoComponent`という名前を付けます。</span><span class="sxs-lookup"><span data-stu-id="509a1-119">Call it `DemoComponent`.</span></span>

     <span data-ttu-id="509a1-120">詳細については、「[方法 :新しいプロジェクト項目の追加](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/w0572c5b(v=vs.100))します。</span><span class="sxs-lookup"><span data-stu-id="509a1-120">For more information, see [How to: Add New Project Items](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/w0572c5b(v=vs.100)).</span></span>

3. <span data-ttu-id="509a1-121">プロジェクトをビルドします。</span><span class="sxs-lookup"><span data-stu-id="509a1-121">Build the project.</span></span>

4. <span data-ttu-id="509a1-122">**ツール** メニューのをクリックして、**オプション**項目。</span><span class="sxs-lookup"><span data-stu-id="509a1-122">From the **Tools** menu, click the **Options** item.</span></span> <span data-ttu-id="509a1-123">をクリックして**全般**下、 **Windows フォーム デザイナー**いることを確認し、 **AutoToolboxPopulate**にオプションが設定されている**True**します。</span><span class="sxs-lookup"><span data-stu-id="509a1-123">Click **General** under the **Windows Forms Designer** item and ensure that the **AutoToolboxPopulate** option is set to **True**.</span></span>

## <a name="create-an-instance-of-a-custom-component"></a><span data-ttu-id="509a1-124">カスタム コンポーネントのインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="509a1-124">Create an instance of a custom component</span></span>

<span data-ttu-id="509a1-125">次の手順では、フォームにカスタム コンポーネントのインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="509a1-125">The next step is to create an instance of the custom component on the form.</span></span> <span data-ttu-id="509a1-126">**ツールボックス**を自動的に新しいコンポーネントのアカウントは、これは他のコンポーネントまたはコントロールの作成と同じくらい簡単です。</span><span class="sxs-lookup"><span data-stu-id="509a1-126">Because the **Toolbox** automatically accounts for the new component, this is as easy as creating any other component or control.</span></span>

1. <span data-ttu-id="509a1-127">プロジェクトのフォームを開き、**フォーム デザイナー**します。</span><span class="sxs-lookup"><span data-stu-id="509a1-127">Open the project's form in the **Forms Designer**.</span></span>

2. <span data-ttu-id="509a1-128">**ツールボックス**と呼ばれる新しいタブをクリックします。 **ToolboxExample コンポーネント**します。</span><span class="sxs-lookup"><span data-stu-id="509a1-128">In the **Toolbox**, click the new tab called **ToolboxExample Components**.</span></span>

     <span data-ttu-id="509a1-129">このタブをクリックすると表示されます**と**します。</span><span class="sxs-lookup"><span data-stu-id="509a1-129">Once you click the tab, you will see **DemoComponent**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="509a1-130">パフォーマンス上の理由から、コンポーネントの自動設定 領域で、**ツールボックス**カスタムのビットマップを表示しないと、<xref:System.Drawing.ToolboxBitmapAttribute>はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="509a1-130">For performance reasons, components in the auto-populated area of the **Toolbox** do not display custom bitmaps, and the <xref:System.Drawing.ToolboxBitmapAttribute> is not supported.</span></span> <span data-ttu-id="509a1-131">カスタムのコンポーネントのアイコンを表示する、**ツールボックス**を使用して、**ツールボックス アイテムの選択**コンポーネントの読み込み ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="509a1-131">To display an icon for a custom component in the **Toolbox**, use the **Choose Toolbox Items** dialog box to load your component.</span></span>

3. <span data-ttu-id="509a1-132">コンポーネントをフォームにドラッグします。</span><span class="sxs-lookup"><span data-stu-id="509a1-132">Drag your component onto your form.</span></span>

     <span data-ttu-id="509a1-133">コンポーネントのインスタンスが作成されに追加、**コンポーネント トレイ**します。</span><span class="sxs-lookup"><span data-stu-id="509a1-133">An instance of the component is created and added to the **Component Tray**.</span></span>

## <a name="unload-and-reload-a-custom-component"></a><span data-ttu-id="509a1-134">アンロードし、カスタム コンポーネントを再読み込み</span><span class="sxs-lookup"><span data-stu-id="509a1-134">Unload and reload a custom component</span></span>

<span data-ttu-id="509a1-135">**ツールボックス**の各コンポーネントの実行アカウントには、プロジェクトが読み込まれ、プロジェクトが読み込まれると、プロジェクトのコンポーネントへの参照を削除します。</span><span class="sxs-lookup"><span data-stu-id="509a1-135">The **Toolbox** takes account of the components in each loaded project, and when a project is unloaded, it removes references to the project's components.</span></span>

1. <span data-ttu-id="509a1-136">ソリューションからプロジェクトをアンロードします。</span><span class="sxs-lookup"><span data-stu-id="509a1-136">Unload the project from the solution.</span></span>

     <span data-ttu-id="509a1-137">プロジェクトのアンロードの詳細については、次を参照してください。[方法。アンロードし、プロジェクトの再読み込み](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/tt479x1t(v=vs.100))します。</span><span class="sxs-lookup"><span data-stu-id="509a1-137">For more information about unloading projects, see [How to: Unload and Reload Projects](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/tt479x1t(v=vs.100)).</span></span> <span data-ttu-id="509a1-138">保存するメッセージが表示されたら、選択**はい**します。</span><span class="sxs-lookup"><span data-stu-id="509a1-138">If you are prompted to save, choose **Yes**.</span></span>

2. <span data-ttu-id="509a1-139">新しい追加**Windows アプリケーション**プロジェクトがソリューションにします。</span><span class="sxs-lookup"><span data-stu-id="509a1-139">Add a new **Windows Application** project to the solution.</span></span> <span data-ttu-id="509a1-140">フォームを開いて、**デザイナー**します。</span><span class="sxs-lookup"><span data-stu-id="509a1-140">Open the form in the **Designer**.</span></span>

     <span data-ttu-id="509a1-141">**ToolboxExample コンポーネント**前のプロジェクトからのタブがここではなくなっています。</span><span class="sxs-lookup"><span data-stu-id="509a1-141">The **ToolboxExample Components** tab from the previous project is now gone.</span></span>

3. <span data-ttu-id="509a1-142">再読み込み、`ToolboxExample`プロジェクト。</span><span class="sxs-lookup"><span data-stu-id="509a1-142">Reload the `ToolboxExample` project.</span></span>

     <span data-ttu-id="509a1-143">**ToolboxExample コンポーネント** タブのようになりましたが再表示されます。</span><span class="sxs-lookup"><span data-stu-id="509a1-143">The **ToolboxExample Components** tab now reappears.</span></span>

## <a name="next-steps"></a><span data-ttu-id="509a1-144">次の手順</span><span class="sxs-lookup"><span data-stu-id="509a1-144">Next steps</span></span>

<span data-ttu-id="509a1-145">このチュートリアルで説明する、**ツールボックス**プロジェクトのコンポーネントを考慮に入れたが、**ツールボックス**コントロールになります。</span><span class="sxs-lookup"><span data-stu-id="509a1-145">This walkthrough demonstrates that the **Toolbox** takes account of a project's components, but the **Toolbox** is also takes account of controls.</span></span> <span data-ttu-id="509a1-146">追加と管理プロジェクトをソリューションから削除して、独自のカスタム コントロールを試します。</span><span class="sxs-lookup"><span data-stu-id="509a1-146">Experiment with your own custom controls by adding and removing control projects from your solution.</span></span>

## <a name="see-also"></a><span data-ttu-id="509a1-147">関連項目</span><span class="sxs-lookup"><span data-stu-id="509a1-147">See also</span></span>

- <span data-ttu-id="509a1-148">[一般に、Windows フォーム デザイナー オプション ダイアログ ボックス](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/5aazxs78(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="509a1-148">[General, Windows Forms Designer, Options Dialog Box](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/5aazxs78(v=vs.100))</span></span>
- <span data-ttu-id="509a1-149">[方法: [ツールボックス] タブを操作する](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/66kwe227(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="509a1-149">[How to: Manipulate Toolbox Tabs](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/66kwe227(v=vs.100))</span></span>
- <span data-ttu-id="509a1-150">[[ツールボックス アイテムの選択] ダイアログ ボックス (Visual Studio)](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/dyca0t6t(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="509a1-150">[Choose Toolbox Items Dialog Box (Visual Studio)](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/dyca0t6t(v=vs.100))</span></span>
- [<span data-ttu-id="509a1-151">Windows フォームへのコントロールの追加</span><span class="sxs-lookup"><span data-stu-id="509a1-151">Putting Controls on Windows Forms</span></span>](putting-controls-on-windows-forms.md)
