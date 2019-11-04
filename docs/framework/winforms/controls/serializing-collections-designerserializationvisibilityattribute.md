---
title: 'チュートリアル : DesignerSerializationVisibilityAttribute を使用した、標準データ型のコレクションのシリアル化'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- serialization [Windows Forms], collections
- standard types [Windows Forms], collections
- collections [Windows Forms], serializing
- collections [Windows Forms], standard types
ms.assetid: 020c9df4-fdc5-4dae-815a-963ecae5668c
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 297a7080b0c34fa10f976cbbbfb48d8c35786aca
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458080"
---
# <a name="walkthrough-serialize-collections-of-standard-types"></a><span data-ttu-id="23063-102">チュートリアル: 標準型のコレクションのシリアル化</span><span class="sxs-lookup"><span data-stu-id="23063-102">Walkthrough: Serialize collections of standard types</span></span>

<span data-ttu-id="23063-103">カスタムコントロールによって、コレクションがプロパティとして公開されることがあります。</span><span class="sxs-lookup"><span data-stu-id="23063-103">Your custom controls will sometimes expose a collection as a property.</span></span> <span data-ttu-id="23063-104">このチュートリアルでは、<xref:System.ComponentModel.DesignerSerializationVisibilityAttribute> クラスを使用して、デザイン時にコレクションをシリアル化する方法を制御する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="23063-104">This walkthrough demonstrates how to use the <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute> class to control how a collection is serialized at design time.</span></span> <span data-ttu-id="23063-105">コレクションプロパティに <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute.Content> 値を適用すると、プロパティが確実にシリアル化されます。</span><span class="sxs-lookup"><span data-stu-id="23063-105">Applying the <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute.Content> value to your collection property ensures that the property will be serialized.</span></span>

<span data-ttu-id="23063-106">このトピックのコードを単一のリストとしてコピーする方法については、「[方法: DesignerSerializationVisibilityAttribute を使用して標準型のコレクションをシリアル化](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171833(v=vs.120))する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="23063-106">To copy the code in this topic as a single listing, see [How to: Serialize Collections of Standard Types with the DesignerSerializationVisibilityAttribute](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171833(v=vs.120)).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="23063-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="23063-107">Prerequisites</span></span>

<span data-ttu-id="23063-108">このチュートリアルを完了するには Visual Studio が必要です。</span><span class="sxs-lookup"><span data-stu-id="23063-108">You need Visual Studio to complete this walkthrough.</span></span>

## <a name="create-a-control-with-a-serializable-collection"></a><span data-ttu-id="23063-109">シリアル化可能なコレクションを持つコントロールを作成する</span><span class="sxs-lookup"><span data-stu-id="23063-109">Create a control with a serializable collection</span></span>

<span data-ttu-id="23063-110">最初の手順では、シリアル化可能なコレクションをプロパティとして持つコントロールを作成します。</span><span class="sxs-lookup"><span data-stu-id="23063-110">The first step is to create a control that has a serializable collection as a property.</span></span> <span data-ttu-id="23063-111">このコレクションの内容は、 **[プロパティ]** ウィンドウからアクセスできる**コレクションエディター**を使用して編集できます。</span><span class="sxs-lookup"><span data-stu-id="23063-111">You can edit the contents of this collection using the **Collection Editor**, which you can access from the **Properties** window.</span></span>

1. <span data-ttu-id="23063-112">Visual Studio で、Windows コントロールライブラリプロジェクトを作成し、「 **Serializationdemocontrollib**」という名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="23063-112">In Visual Studio, create a Windows Control Library project, and name it **SerializationDemoControlLib**.</span></span>

2. <span data-ttu-id="23063-113">`UserControl1` 名を `SerializationDemoControl`に変更します。</span><span class="sxs-lookup"><span data-stu-id="23063-113">Rename `UserControl1` to `SerializationDemoControl`.</span></span> <span data-ttu-id="23063-114">詳細については、「[コードシンボルの名前変更のリファクタリング](/visualstudio/ide/reference/rename)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="23063-114">For more information, see [Rename a code symbol refactoring](/visualstudio/ide/reference/rename).</span></span>

3. <span data-ttu-id="23063-115">**[プロパティ]** ウィンドウで、[<xref:System.Windows.Forms.Padding.All%2A?displayProperty=nameWithType>] プロパティの値を**10**に設定します。</span><span class="sxs-lookup"><span data-stu-id="23063-115">In the **Properties** window, set the value of the <xref:System.Windows.Forms.Padding.All%2A?displayProperty=nameWithType> property to **10**.</span></span>

4. <span data-ttu-id="23063-116">`SerializationDemoControl`に <xref:System.Windows.Forms.TextBox> コントロールを配置します。</span><span class="sxs-lookup"><span data-stu-id="23063-116">Place a <xref:System.Windows.Forms.TextBox> control in the `SerializationDemoControl`.</span></span>

5. <span data-ttu-id="23063-117"><xref:System.Windows.Forms.TextBox> コントロールを選択します。</span><span class="sxs-lookup"><span data-stu-id="23063-117">Select the <xref:System.Windows.Forms.TextBox> control.</span></span> <span data-ttu-id="23063-118">**[プロパティ]** ウィンドウで、次のプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="23063-118">In the **Properties** window, set the following properties.</span></span>

    |<span data-ttu-id="23063-119">property</span><span class="sxs-lookup"><span data-stu-id="23063-119">Property</span></span>|<span data-ttu-id="23063-120">変更後の値</span><span class="sxs-lookup"><span data-stu-id="23063-120">Change to</span></span>|
    |--------------|---------------|
    |<span data-ttu-id="23063-121">**Multiline**</span><span class="sxs-lookup"><span data-stu-id="23063-121">**Multiline**</span></span>|`true`|
    |<span data-ttu-id="23063-122">**装着**</span><span class="sxs-lookup"><span data-stu-id="23063-122">**Dock**</span></span>|<xref:System.Windows.Forms.DockStyle.Fill>|
    |<span data-ttu-id="23063-123">**ScrollBars**</span><span class="sxs-lookup"><span data-stu-id="23063-123">**ScrollBars**</span></span>|<xref:System.Windows.Forms.ScrollBars.Vertical>|
    |<span data-ttu-id="23063-124">**ReadOnly**</span><span class="sxs-lookup"><span data-stu-id="23063-124">**ReadOnly**</span></span>|`true`|

6. <span data-ttu-id="23063-125">**コードエディター**で、`SerializationDemoControl`内の `stringsValue` という名前の文字列配列フィールドを宣言します。</span><span class="sxs-lookup"><span data-stu-id="23063-125">In the **Code Editor**, declare a string array field named `stringsValue` in `SerializationDemoControl`.</span></span>

     [!code-cpp[System.ComponentModel.DesignerSerializationVisibilityAttribute#4](~/samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/cpp/form1.cpp#4)]
     [!code-csharp[System.ComponentModel.DesignerSerializationVisibilityAttribute#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/CS/form1.cs#4)]
     [!code-vb[System.ComponentModel.DesignerSerializationVisibilityAttribute#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/VB/form1.vb#4)]

7. <span data-ttu-id="23063-126">`SerializationDemoControl`で `Strings` プロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="23063-126">Define the `Strings` property on the `SerializationDemoControl`.</span></span>

   > [!NOTE]
   > <span data-ttu-id="23063-127"><xref:System.ComponentModel.DesignerSerializationVisibilityAttribute.Content> 値は、コレクションのシリアル化を有効にするために使用されます。</span><span class="sxs-lookup"><span data-stu-id="23063-127">The <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute.Content> value is used to enable serialization of the collection.</span></span>

   [!code-cpp[System.ComponentModel.DesignerSerializationVisibilityAttribute#5](~/samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/cpp/form1.cpp#5)]
   [!code-csharp[System.ComponentModel.DesignerSerializationVisibilityAttribute#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/CS/form1.cs#5)]
   [!code-vb[System.ComponentModel.DesignerSerializationVisibilityAttribute#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/VB/form1.vb#5)]

8. <span data-ttu-id="23063-128">**F5**キーを押してプロジェクトをビルドし、 **UserControl テストコンテナー**でコントロールを実行します。</span><span class="sxs-lookup"><span data-stu-id="23063-128">Press **F5** to build the project and run your control in the **UserControl Test Container**.</span></span>

9. <span data-ttu-id="23063-129">**UserControl テストコンテナー**の <xref:System.Windows.Forms.PropertyGrid> で、 **Strings**プロパティを見つけます。</span><span class="sxs-lookup"><span data-stu-id="23063-129">Find the **Strings** property in the <xref:System.Windows.Forms.PropertyGrid> of the **UserControl Test Container**.</span></span> <span data-ttu-id="23063-130">**[文字列]** プロパティを選択し、省略記号![(省略記号ボタン ([...]) を選択して [Visual Studio のプロパティウィンドウ](./media/visual-studio-ellipsis-button.png))] ボタンをクリックし、**文字列コレクションエディター**を開きます。</span><span class="sxs-lookup"><span data-stu-id="23063-130">Select the **Strings** property, then select the ellipsis (![The Ellipsis button (...) in the Properties window of Visual Studio](./media/visual-studio-ellipsis-button.png)) button to open the **String Collection Editor**.</span></span>

10. <span data-ttu-id="23063-131">**文字列コレクションエディター**でいくつかの文字列を入力します。</span><span class="sxs-lookup"><span data-stu-id="23063-131">Enter several strings in the **String Collection Editor**.</span></span> <span data-ttu-id="23063-132">各文字列の末尾にある**enter**キーを押して区切ります。</span><span class="sxs-lookup"><span data-stu-id="23063-132">Separate them by pressing the **Enter** key at the end of each string.</span></span> <span data-ttu-id="23063-133">文字列の入力が完了したら、 **[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="23063-133">Click **OK** when you are finished entering strings.</span></span>

   > [!NOTE]
   > <span data-ttu-id="23063-134">入力した文字列は、`SerializationDemoControl`の <xref:System.Windows.Forms.TextBox> に表示されます。</span><span class="sxs-lookup"><span data-stu-id="23063-134">The strings you typed appear in the <xref:System.Windows.Forms.TextBox> of the `SerializationDemoControl`.</span></span>

## <a name="serialize-a-collection-property"></a><span data-ttu-id="23063-135">コレクションプロパティをシリアル化する</span><span class="sxs-lookup"><span data-stu-id="23063-135">Serialize a collection property</span></span>

<span data-ttu-id="23063-136">コントロールのシリアル化動作をテストするには、コントロールをフォームに配置し、コレクション**エディター**を使用してコレクションの内容を変更します。</span><span class="sxs-lookup"><span data-stu-id="23063-136">To test the serialization behavior of your control, you will place it on a form and change the contents of the collection with the **Collection Editor**.</span></span> <span data-ttu-id="23063-137">シリアル化されたコレクションの状態を確認するには、 **Windows フォームデザイナー**がコードを出力する特別なデザイナーファイルを調べます。</span><span class="sxs-lookup"><span data-stu-id="23063-137">You can see the serialized collection state by looking at a special designer file into which the **Windows Forms Designer** emits code.</span></span>

1. <span data-ttu-id="23063-138">Windows アプリケーションプロジェクトをソリューションに追加します。</span><span class="sxs-lookup"><span data-stu-id="23063-138">Add a Windows Application project to the solution.</span></span> <span data-ttu-id="23063-139">プロジェクトに `SerializationDemoControlTest` という名前を付けます。</span><span class="sxs-lookup"><span data-stu-id="23063-139">Name the project `SerializationDemoControlTest`.</span></span>

2. <span data-ttu-id="23063-140">**[ツールボックス]** で、 **[Serializationdemocontrollib Components]** という名前のタブを探します。</span><span class="sxs-lookup"><span data-stu-id="23063-140">In the **Toolbox**, find the tab named **SerializationDemoControlLib Components**.</span></span> <span data-ttu-id="23063-141">このタブには、`SerializationDemoControl`が表示されます。</span><span class="sxs-lookup"><span data-stu-id="23063-141">In this tab, you will find the `SerializationDemoControl`.</span></span> <span data-ttu-id="23063-142">詳細については、「[チュートリアル: ツールボックスへのカスタム コンポーネントの自動設定](walkthrough-automatically-populating-the-toolbox-with-custom-components.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="23063-142">For more information, see [Walkthrough: Automatically Populating the Toolbox with Custom Components](walkthrough-automatically-populating-the-toolbox-with-custom-components.md).</span></span>

3. <span data-ttu-id="23063-143">フォームに `SerializationDemoControl` を配置します。</span><span class="sxs-lookup"><span data-stu-id="23063-143">Place a `SerializationDemoControl` on your form.</span></span>

4. <span data-ttu-id="23063-144">**[プロパティ]** ウィンドウで、[`Strings`] プロパティを見つけます。</span><span class="sxs-lookup"><span data-stu-id="23063-144">Find the `Strings` property in the **Properties** window.</span></span> <span data-ttu-id="23063-145">[`Strings`] プロパティをクリックし、省略記号 (![の省略記号ボタン ([...] プロパティウィンドウ) をクリックして、[](./media/visual-studio-ellipsis-button.png))] ボタンをクリックし、**文字列コレクションエディター**を開きます。</span><span class="sxs-lookup"><span data-stu-id="23063-145">Click the `Strings` property, then click the ellipsis (![The Ellipsis button (...) in the Properties window of Visual Studio.](./media/visual-studio-ellipsis-button.png)) button to open the **String Collection Editor**.</span></span>

5. <span data-ttu-id="23063-146">**文字列コレクションエディター**でいくつかの文字列を入力します。</span><span class="sxs-lookup"><span data-stu-id="23063-146">Type several strings in the **String Collection Editor**.</span></span> <span data-ttu-id="23063-147">各文字列の末尾で**enter**キーを押して区切ります。</span><span class="sxs-lookup"><span data-stu-id="23063-147">Separate them by pressing **Enter** at the end of each string.</span></span> <span data-ttu-id="23063-148">文字列の入力が完了したら、 **[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="23063-148">Click **OK** when you are finished entering strings.</span></span>

    > [!NOTE]
    > <span data-ttu-id="23063-149">入力した文字列は、`SerializationDemoControl`の <xref:System.Windows.Forms.TextBox> に表示されます。</span><span class="sxs-lookup"><span data-stu-id="23063-149">The strings you typed appear in the <xref:System.Windows.Forms.TextBox> of the `SerializationDemoControl`.</span></span>

6. <span data-ttu-id="23063-150">**ソリューション エクスプローラー**で、 **[すべてのファイルを表示]** ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="23063-150">In **Solution Explorer**, click the **Show All Files** button.</span></span>

7. <span data-ttu-id="23063-151">**Form1**ノードを開きます。</span><span class="sxs-lookup"><span data-stu-id="23063-151">Open the **Form1** node.</span></span> <span data-ttu-id="23063-152">その下には、 **Form1.Designer.cs**または**form1.vb**という名前のファイルがあります。</span><span class="sxs-lookup"><span data-stu-id="23063-152">Beneath it is a file called **Form1.Designer.cs** or **Form1.Designer.vb**.</span></span> <span data-ttu-id="23063-153">これは、フォームとその子コントロールのデザイン時の状態を表すコードを**Windows フォームデザイナー**が出力するファイルです。</span><span class="sxs-lookup"><span data-stu-id="23063-153">This is the file into which the **Windows Forms Designer** emits code representing the design-time state of your form and its child controls.</span></span> <span data-ttu-id="23063-154">このファイルを**コード エディター**で開きます。</span><span class="sxs-lookup"><span data-stu-id="23063-154">Open this file in the **Code Editor**.</span></span>

8. <span data-ttu-id="23063-155">**Windows フォームデザイナーで生成されたコード**という名前の領域を開き、 **serializationDemoControl1**というラベルが付いたセクションを検索します。</span><span class="sxs-lookup"><span data-stu-id="23063-155">Open the region called **Windows Form Designer generated code** and find the section labeled **serializationDemoControl1**.</span></span> <span data-ttu-id="23063-156">このラベルの下には、コントロールのシリアル化された状態を表すコードがあります。</span><span class="sxs-lookup"><span data-stu-id="23063-156">Beneath this label is the code representing the serialized state of your control.</span></span> <span data-ttu-id="23063-157">手順 5. で入力した文字列は、`Strings` プロパティへの割り当てに表示されます。</span><span class="sxs-lookup"><span data-stu-id="23063-157">The strings you typed in step 5 appear in an assignment to the `Strings` property.</span></span> <span data-ttu-id="23063-158">C#と Visual Basic の次のコード例では、文字列 "red"、"オレンジ"、および "黄" を入力した場合と同様のコードが表示されます。</span><span class="sxs-lookup"><span data-stu-id="23063-158">The following code examples in C# and Visual Basic, show code similar to what you will see if you typed the strings "red", "orange", and "yellow".</span></span>

    ```csharp
    this.serializationDemoControl1.Strings = new string[] {
            "red",
            "orange",
            "yellow"};
    ```

    ```vb
    Me.serializationDemoControl1.Strings = New String() {"red", "orange", "yellow"}
    ```

9. <span data-ttu-id="23063-159">**コードエディター**で、`Strings` プロパティの <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute> の値を <xref:System.ComponentModel.DesignerSerializationVisibility.Hidden>に変更します。</span><span class="sxs-lookup"><span data-stu-id="23063-159">In the **Code Editor**, change the value of the <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute> on the `Strings` property to <xref:System.ComponentModel.DesignerSerializationVisibility.Hidden>.</span></span>

    ```csharp
    [DesignerSerializationVisibility(DesignerSerializationVisibility.Hidden)]
    ```

    ```vb
    <DesignerSerializationVisibility(DesignerSerializationVisibility.Hidden)> _
    ```

10. <span data-ttu-id="23063-160">ソリューションをリビルドし、手順3と4を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="23063-160">Rebuild the solution and repeat steps 3 and 4.</span></span>

> [!NOTE]
> <span data-ttu-id="23063-161">この場合、 **Windows フォームデザイナー**は `Strings` プロパティに割り当てを出力しません。</span><span class="sxs-lookup"><span data-stu-id="23063-161">In this case, the **Windows Forms Designer** emits no assignment to the `Strings` property.</span></span>

## <a name="next-steps"></a><span data-ttu-id="23063-162">次のステップ</span><span class="sxs-lookup"><span data-stu-id="23063-162">Next steps</span></span>

<span data-ttu-id="23063-163">標準型のコレクションをシリアル化する方法を理解したら、カスタムコントロールをデザイン時環境により深く統合することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="23063-163">Once you know how to serialize a collection of standard types, consider integrating your custom controls more deeply into the design-time environment.</span></span> <span data-ttu-id="23063-164">次のトピックでは、カスタムコントロールのデザイン時統合を強化する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="23063-164">The following topics describe how to enhance the design-time integration of your custom controls:</span></span>

- <span data-ttu-id="23063-165">[デザイン時アーキテクチャ](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/c5z9s1h4(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="23063-165">[Design-Time Architecture](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/c5z9s1h4(v=vs.120))</span></span>

- [<span data-ttu-id="23063-166">Windows フォーム コントロールの属性</span><span class="sxs-lookup"><span data-stu-id="23063-166">Attributes in Windows Forms Controls</span></span>](attributes-in-windows-forms-controls.md)

- <span data-ttu-id="23063-167">[デザイナーのシリアル化の概要](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171834(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="23063-167">[Designer Serialization Overview](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171834(v=vs.120))</span></span>

- [<span data-ttu-id="23063-168">チュートリアル: Visual Studio のデザイン時機能を活用した Windows フォーム コントロールの作成</span><span class="sxs-lookup"><span data-stu-id="23063-168">Walkthrough: Creating a Windows Forms Control That Takes Advantage of Visual Studio Design-Time Features</span></span>](creating-a-wf-control-design-time-features.md)

## <a name="see-also"></a><span data-ttu-id="23063-169">関連項目</span><span class="sxs-lookup"><span data-stu-id="23063-169">See also</span></span>

- <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute>
- [<span data-ttu-id="23063-170">チュートリアル: ツールボックスへのカスタム コンポーネントの自動設定</span><span class="sxs-lookup"><span data-stu-id="23063-170">Walkthrough: Automatically Populating the Toolbox with Custom Components</span></span>](walkthrough-automatically-populating-the-toolbox-with-custom-components.md)
