---
title: 'チュートリアル: DesignerSerializationVisibilityAttribute を使用した、標準データ型のコレクションのシリアル化'
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
ms.openlocfilehash: c113dcf814a252808ae3232751028947c26821ba
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62012439"
---
# <a name="walkthrough-serializing-collections-of-standard-types-with-the-designerserializationvisibilityattribute"></a><span data-ttu-id="c22e4-102">チュートリアル: DesignerSerializationVisibilityAttribute を使用した、標準データ型のコレクションのシリアル化</span><span class="sxs-lookup"><span data-stu-id="c22e4-102">Walkthrough: Serializing Collections of Standard Types with the DesignerSerializationVisibilityAttribute</span></span>

<span data-ttu-id="c22e4-103">カスタム コントロールでは、プロパティとしてコレクションを公開が場合があります。</span><span class="sxs-lookup"><span data-stu-id="c22e4-103">Your custom controls will sometimes expose a collection as a property.</span></span> <span data-ttu-id="c22e4-104">このチュートリアルを使用する方法について説明、<xref:System.ComponentModel.DesignerSerializationVisibilityAttribute>デザイン時にコレクションをシリアル化する方法を制御するクラス。</span><span class="sxs-lookup"><span data-stu-id="c22e4-104">This walkthrough demonstrates how to use the <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute> class to control how a collection is serialized at design time.</span></span> <span data-ttu-id="c22e4-105">適用、<xref:System.ComponentModel.DesignerSerializationVisibilityAttribute.Content>値をコレクション プロパティにより、プロパティをシリアル化されます。</span><span class="sxs-lookup"><span data-stu-id="c22e4-105">Applying the <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute.Content> value to your collection property ensures that the property will be serialized.</span></span>

 <span data-ttu-id="c22e4-106">このトピックのコードを単一のリストとしてコピーするには、「[方法:Designerserializationvisibilityattribute を使用、基本データ型のコレクションをシリアル化](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171833(v=vs.120))します。</span><span class="sxs-lookup"><span data-stu-id="c22e4-106">To copy the code in this topic as a single listing, see [How to: Serialize Collections of Standard Types with the DesignerSerializationVisibilityAttribute](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171833(v=vs.120)).</span></span>

> [!NOTE]
> <span data-ttu-id="c22e4-107">実際に画面に表示されるダイアログ ボックスとメニュー コマンドは、アクティブな設定またはエディションによっては、ヘルプの説明と異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="c22e4-107">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="c22e4-108">設定を変更するには、 **[ツール]** メニューの **[設定のインポートとエクスポート]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c22e4-108">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="c22e4-109">詳細については、「[Visual Studio IDE のカスタマイズ](/visualstudio/ide/personalizing-the-visual-studio-ide)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c22e4-109">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="c22e4-110">必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="c22e4-110">Prerequisites</span></span>
 <span data-ttu-id="c22e4-111">このチュートリアルを完了するための要件は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="c22e4-111">In order to complete this walkthrough, you will need:</span></span>

- <span data-ttu-id="c22e4-112">作成し、Visual Studio がインストールされているコンピューターで Windows フォーム アプリケーション プロジェクトを実行できる十分なアクセスを許可します。</span><span class="sxs-lookup"><span data-stu-id="c22e4-112">Sufficient permissions to be able to create and run Windows Forms application projects on the computer where Visual Studio is installed.</span></span>

## <a name="creating-a-control-that-has-a-serializable-collection"></a><span data-ttu-id="c22e4-113">シリアル化可能なコレクションを持つコントロールを作成します。</span><span class="sxs-lookup"><span data-stu-id="c22e4-113">Creating a Control That Has a Serializable Collection</span></span>
 <span data-ttu-id="c22e4-114">最初の手順では、プロパティとしてシリアル化可能なコレクションを持つコントロールを作成します。</span><span class="sxs-lookup"><span data-stu-id="c22e4-114">The first step is to create a control that has a serializable collection as a property.</span></span> <span data-ttu-id="c22e4-115">使用してこのコレクションの内容を編集することができます、**コレクション エディター**からアクセスできますが、**プロパティ**ウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="c22e4-115">You can edit the contents of this collection using the **Collection Editor**, which you can access from the **Properties** window.</span></span>

### <a name="to-create-a-control-with-a-serializable-collection"></a><span data-ttu-id="c22e4-116">シリアル化可能なコレクションを使用してコントロールを作成するには</span><span class="sxs-lookup"><span data-stu-id="c22e4-116">To create a control with a serializable collection</span></span>

1. <span data-ttu-id="c22e4-117">という名前の Windows コントロール ライブラリ プロジェクトを作成する`SerializationDemoControlLib`します。</span><span class="sxs-lookup"><span data-stu-id="c22e4-117">Create a Windows Control Library project called `SerializationDemoControlLib`.</span></span> <span data-ttu-id="c22e4-118">詳細については、次を参照してください。 [Windows コントロール ライブラリ テンプレート](https://docs.microsoft.com/previous-versions/kxczf775(v=vs.100))します。</span><span class="sxs-lookup"><span data-stu-id="c22e4-118">For more information, see [Windows Control Library Template](https://docs.microsoft.com/previous-versions/kxczf775(v=vs.100)).</span></span>

2. <span data-ttu-id="c22e4-119">名前を変更`UserControl1`に`SerializationDemoControl`します。</span><span class="sxs-lookup"><span data-stu-id="c22e4-119">Rename `UserControl1` to `SerializationDemoControl`.</span></span> <span data-ttu-id="c22e4-120">詳細については、次を参照してください。[コード シンボルのリファクタリングの名前を変更](/visualstudio/ide/reference/rename)します。</span><span class="sxs-lookup"><span data-stu-id="c22e4-120">For more information, see [Rename a code symbol refactoring](/visualstudio/ide/reference/rename).</span></span>

3. <span data-ttu-id="c22e4-121">**プロパティ**ウィンドウで、設定の値、<xref:System.Windows.Forms.Padding.All%2A?displayProperty=nameWithType>プロパティを`10`します。</span><span class="sxs-lookup"><span data-stu-id="c22e4-121">In the **Properties** window, set the value of the <xref:System.Windows.Forms.Padding.All%2A?displayProperty=nameWithType> property to `10`.</span></span>

4. <span data-ttu-id="c22e4-122">場所、<xref:System.Windows.Forms.TextBox>を制御、`SerializationDemoControl`します。</span><span class="sxs-lookup"><span data-stu-id="c22e4-122">Place a <xref:System.Windows.Forms.TextBox> control in the `SerializationDemoControl`.</span></span>

5. <span data-ttu-id="c22e4-123"><xref:System.Windows.Forms.TextBox> コントロールを選択します。</span><span class="sxs-lookup"><span data-stu-id="c22e4-123">Select the <xref:System.Windows.Forms.TextBox> control.</span></span> <span data-ttu-id="c22e4-124">**プロパティ**ウィンドウで、次のプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="c22e4-124">In the **Properties** window, set the following properties.</span></span>

    |<span data-ttu-id="c22e4-125">プロパティ</span><span class="sxs-lookup"><span data-stu-id="c22e4-125">Property</span></span>|<span data-ttu-id="c22e4-126">変更後の値</span><span class="sxs-lookup"><span data-stu-id="c22e4-126">Change to</span></span>|
    |--------------|---------------|
    |<span data-ttu-id="c22e4-127">**Multiline**</span><span class="sxs-lookup"><span data-stu-id="c22e4-127">**Multiline**</span></span>|`true`|
    |<span data-ttu-id="c22e4-128">**ドッキング ステーション**</span><span class="sxs-lookup"><span data-stu-id="c22e4-128">**Dock**</span></span>|<xref:System.Windows.Forms.DockStyle.Fill>|
    |<span data-ttu-id="c22e4-129">**ScrollBars**</span><span class="sxs-lookup"><span data-stu-id="c22e4-129">**ScrollBars**</span></span>|<xref:System.Windows.Forms.ScrollBars.Vertical>|
    |<span data-ttu-id="c22e4-130">**ReadOnly**</span><span class="sxs-lookup"><span data-stu-id="c22e4-130">**ReadOnly**</span></span>|`true`|

6. <span data-ttu-id="c22e4-131">**コード エディター**、という名前の文字列配列フィールドを宣言`stringsValue`で`SerializationDemoControl`します。</span><span class="sxs-lookup"><span data-stu-id="c22e4-131">In the **Code Editor**, declare a string array field named `stringsValue` in `SerializationDemoControl`.</span></span>

     [!code-cpp[System.ComponentModel.DesignerSerializationVisibilityAttribute#4](~/samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/cpp/form1.cpp#4)]
     [!code-csharp[System.ComponentModel.DesignerSerializationVisibilityAttribute#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/CS/form1.cs#4)]
     [!code-vb[System.ComponentModel.DesignerSerializationVisibilityAttribute#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/VB/form1.vb#4)]

7. <span data-ttu-id="c22e4-132">定義、`Strings`プロパティを`SerializationDemoControl`します。</span><span class="sxs-lookup"><span data-stu-id="c22e4-132">Define the `Strings` property on the `SerializationDemoControl`.</span></span>

> [!NOTE]
> <span data-ttu-id="c22e4-133"><xref:System.ComponentModel.DesignerSerializationVisibilityAttribute.Content>値を使用して、コレクションのシリアル化を有効にします。</span><span class="sxs-lookup"><span data-stu-id="c22e4-133">The <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute.Content> value is used to enable serialization of the collection.</span></span>

 [!code-cpp[System.ComponentModel.DesignerSerializationVisibilityAttribute#5](~/samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/cpp/form1.cpp#5)]
 [!code-csharp[System.ComponentModel.DesignerSerializationVisibilityAttribute#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/CS/form1.cs#5)]
 [!code-vb[System.ComponentModel.DesignerSerializationVisibilityAttribute#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/VB/form1.vb#5)]

1. <span data-ttu-id="c22e4-134">F5 キーを押してプロジェクトをビルドし、**UserControl Test Container** でコントロールを実行します。</span><span class="sxs-lookup"><span data-stu-id="c22e4-134">Press F5 to build the project and run your control in the **UserControl Test Container**.</span></span>

2. <span data-ttu-id="c22e4-135">検索、`Strings`プロパティ、<xref:System.Windows.Forms.PropertyGrid>の**UserControl Test Container**します。</span><span class="sxs-lookup"><span data-stu-id="c22e4-135">Find the `Strings` property in the <xref:System.Windows.Forms.PropertyGrid> of the **UserControl Test Container**.</span></span> <span data-ttu-id="c22e4-136">をクリックして、`Strings`プロパティ、省略記号をクリックします (![VisualStudioEllipsesButton スクリーン ショット](../media/vbellipsesbutton.png "vbEllipsesButton")) ボタンをクリックする、 **の文字列コレクションエディター**.</span><span class="sxs-lookup"><span data-stu-id="c22e4-136">Click the `Strings` property, then click the ellipsis (![VisualStudioEllipsesButton screenshot](../media/vbellipsesbutton.png "vbEllipsesButton")) button to open the **String Collection Editor**.</span></span>

3. <span data-ttu-id="c22e4-137">内のいくつかの文字列を入力、**文字列コレクション エディター**します。</span><span class="sxs-lookup"><span data-stu-id="c22e4-137">Enter several strings in the **String Collection Editor**.</span></span> <span data-ttu-id="c22e4-138">各文字列の最後に ENTER キーを押すで区切ります。</span><span class="sxs-lookup"><span data-stu-id="c22e4-138">Separate them by pressing the ENTER key at the end of each string.</span></span> <span data-ttu-id="c22e4-139">クリックして**OK**文字列の入力が完了したら。</span><span class="sxs-lookup"><span data-stu-id="c22e4-139">Click **OK** when you are finished entering strings.</span></span>

> [!NOTE]
> <span data-ttu-id="c22e4-140">入力した文字列に表示されます、<xref:System.Windows.Forms.TextBox>の`SerializationDemoControl`します。</span><span class="sxs-lookup"><span data-stu-id="c22e4-140">The strings you typed appear in the <xref:System.Windows.Forms.TextBox> of the `SerializationDemoControl`.</span></span>

## <a name="serializing-a-collection-property"></a><span data-ttu-id="c22e4-141">コレクション プロパティをシリアル化します。</span><span class="sxs-lookup"><span data-stu-id="c22e4-141">Serializing a Collection Property</span></span>

<span data-ttu-id="c22e4-142">コントロールのシリアル化動作をテストするをフォームに配置を使用して、コレクションの内容を変更するが、**コレクション エディター**します。</span><span class="sxs-lookup"><span data-stu-id="c22e4-142">To test the serialization behavior of your control, you will place it on a form and change the contents of the collection with the **Collection Editor**.</span></span> <span data-ttu-id="c22e4-143">特殊なデザイナー ファイルを調べることで、シリアル化されたコレクションの状態を確認できます、 **Windows フォーム デザイナー**はコードを出力します。</span><span class="sxs-lookup"><span data-stu-id="c22e4-143">You can see the serialized collection state by looking at a special designer file, into which the **Windows Forms Designer** emits code.</span></span>

### <a name="to-serialize-a-collection"></a><span data-ttu-id="c22e4-144">コレクションをシリアル化するには</span><span class="sxs-lookup"><span data-stu-id="c22e4-144">To serialize a collection</span></span>

1. <span data-ttu-id="c22e4-145">Windows アプリケーション プロジェクトをソリューションに追加します。</span><span class="sxs-lookup"><span data-stu-id="c22e4-145">Add a Windows Application project to the solution.</span></span> <span data-ttu-id="c22e4-146">プロジェクトに `SerializationDemoControlTest` という名前を付けます。</span><span class="sxs-lookup"><span data-stu-id="c22e4-146">Name the project `SerializationDemoControlTest`.</span></span>

2. <span data-ttu-id="c22e4-147">**ツールボックス**、という名前のタブを見つける**SerializationDemoControlLib コンポーネント**します。</span><span class="sxs-lookup"><span data-stu-id="c22e4-147">In the **Toolbox**, find the tab named **SerializationDemoControlLib Components**.</span></span> <span data-ttu-id="c22e4-148">このタブでは紹介、`SerializationDemoControl`します。</span><span class="sxs-lookup"><span data-stu-id="c22e4-148">In this tab, you will find the `SerializationDemoControl`.</span></span> <span data-ttu-id="c22e4-149">詳細については、「[チュートリアル:カスタム コンポーネントでツールボックスが自動的に入力](walkthrough-automatically-populating-the-toolbox-with-custom-components.md)します。</span><span class="sxs-lookup"><span data-stu-id="c22e4-149">For more information, see [Walkthrough: Automatically Populating the Toolbox with Custom Components](walkthrough-automatically-populating-the-toolbox-with-custom-components.md).</span></span>

3. <span data-ttu-id="c22e4-150">場所、`SerializationDemoControl`フォームにします。</span><span class="sxs-lookup"><span data-stu-id="c22e4-150">Place a `SerializationDemoControl` on your form.</span></span>

4. <span data-ttu-id="c22e4-151">検索、`Strings`プロパティ、**プロパティ**ウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="c22e4-151">Find the `Strings` property in the **Properties** window.</span></span> <span data-ttu-id="c22e4-152">をクリックして、`Strings`プロパティ、省略記号をクリックします (![VisualStudioEllipsesButton スクリーン ショット](../media/vbellipsesbutton.png "vbEllipsesButton")) ボタンをクリックする、 **の文字列コレクションエディター**.</span><span class="sxs-lookup"><span data-stu-id="c22e4-152">Click the `Strings` property, then click the ellipsis (![VisualStudioEllipsesButton screenshot](../media/vbellipsesbutton.png "vbEllipsesButton")) button to open the **String Collection Editor**.</span></span>

5. <span data-ttu-id="c22e4-153">内のいくつかの文字列を入力、**文字列コレクション エディター**します。</span><span class="sxs-lookup"><span data-stu-id="c22e4-153">Type several strings in the **String Collection Editor**.</span></span> <span data-ttu-id="c22e4-154">各文字列の最後に ENTER キーを押すで区切ります。</span><span class="sxs-lookup"><span data-stu-id="c22e4-154">Separate them by pressing the ENTER key at the end of each string.</span></span> <span data-ttu-id="c22e4-155">クリックして**OK**文字列の入力が完了したら。</span><span class="sxs-lookup"><span data-stu-id="c22e4-155">Click **OK** when you are finished entering strings.</span></span>

> [!NOTE]
> <span data-ttu-id="c22e4-156">入力した文字列に表示されます、<xref:System.Windows.Forms.TextBox>の`SerializationDemoControl`します。</span><span class="sxs-lookup"><span data-stu-id="c22e4-156">The strings you typed appear in the <xref:System.Windows.Forms.TextBox> of the `SerializationDemoControl`.</span></span>

1. <span data-ttu-id="c22e4-157">**ソリューション エクスプローラー**で、**[すべてのファイルを表示]** ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="c22e4-157">In **Solution Explorer**, click the **Show All Files** button.</span></span>

2. <span data-ttu-id="c22e4-158">開く、 **Form1**ノード。</span><span class="sxs-lookup"><span data-stu-id="c22e4-158">Open the **Form1** node.</span></span> <span data-ttu-id="c22e4-159">という名前のファイルは、その下に**Form1.Designer.cs**または**Form1.Designer.vb**します。</span><span class="sxs-lookup"><span data-stu-id="c22e4-159">Beneath it is a file called **Form1.Designer.cs** or **Form1.Designer.vb**.</span></span> <span data-ttu-id="c22e4-160">これは、ファイルに、 **Windows フォーム デザイナー**フォームとその子コントロールのデザイン時の状態を表すコードを出力します。</span><span class="sxs-lookup"><span data-stu-id="c22e4-160">This is the file into which the **Windows Forms Designer** emits code representing the design-time state of your form and its child controls.</span></span> <span data-ttu-id="c22e4-161">このファイルを**コード エディター**で開きます。</span><span class="sxs-lookup"><span data-stu-id="c22e4-161">Open this file in the **Code Editor**.</span></span>

3. <span data-ttu-id="c22e4-162">呼ばれる領域を開く**Windows フォーム デザイナーで生成されたコード**というラベルの付いたセクションを見つけて**serializationDemoControl1**します。</span><span class="sxs-lookup"><span data-stu-id="c22e4-162">Open the region called **Windows Form Designer generated code** and find the section labeled **serializationDemoControl1**.</span></span> <span data-ttu-id="c22e4-163">このラベルの下には、コントロールのシリアル化された状態を表すコードです。</span><span class="sxs-lookup"><span data-stu-id="c22e4-163">Beneath this label is the code representing the serialized state of your control.</span></span> <span data-ttu-id="c22e4-164">代入に表示される手順 5. で入力した文字列、`Strings`プロパティ。</span><span class="sxs-lookup"><span data-stu-id="c22e4-164">The strings you typed in step 5 appear in an assignment to the `Strings` property.</span></span> <span data-ttu-id="c22e4-165">C# および Visual Basic では、次のコード例は、表示される内容の文字列"red"、「オレンジ」および「黄色」を入力したかどうかのようなコードを示します。</span><span class="sxs-lookup"><span data-stu-id="c22e4-165">The following code examples in C# and Visual Basic, show code similar to what you will see if you typed the strings "red", "orange", and "yellow".</span></span>

    ```csharp
    this.serializationDemoControl1.Strings = new string[] {
            "red",
            "orange",
            "yellow"};
    ```

    ```vb
    Me.serializationDemoControl1.Strings = New String() {"red", "orange", "yellow"}
    ```

4. <span data-ttu-id="c22e4-166">**コード エディター**の値を変更、<xref:System.ComponentModel.DesignerSerializationVisibilityAttribute>上、`Strings`プロパティを<xref:System.ComponentModel.DesignerSerializationVisibility.Hidden>します。</span><span class="sxs-lookup"><span data-stu-id="c22e4-166">In the **Code Editor**, change the value of the <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute> on the `Strings` property to <xref:System.ComponentModel.DesignerSerializationVisibility.Hidden>.</span></span>

    ```csharp
    [DesignerSerializationVisibility(DesignerSerializationVisibility.Hidden)]
    ```

    ```vb
    <DesignerSerializationVisibility(DesignerSerializationVisibility.Hidden)> _
    ```

5. <span data-ttu-id="c22e4-167">ソリューションを再構築、手順 3. および 4. を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="c22e4-167">Rebuild the solution and repeat steps 3 and 4.</span></span>

> [!NOTE]
> <span data-ttu-id="c22e4-168">ここで、 **Windows フォーム デザイナー**への割り当ては出力されません、`Strings`プロパティ。</span><span class="sxs-lookup"><span data-stu-id="c22e4-168">In this case, the **Windows Forms Designer** emits no assignment to the `Strings` property.</span></span>

## <a name="next-steps"></a><span data-ttu-id="c22e4-169">次の手順</span><span class="sxs-lookup"><span data-stu-id="c22e4-169">Next Steps</span></span>

<span data-ttu-id="c22e4-170">基本データ型のコレクションをシリアル化する方法を理解、デザイン時環境に、カスタム コントロールをより深く統合を検討してください。</span><span class="sxs-lookup"><span data-stu-id="c22e4-170">Once you know how to serialize a collection of standard types, consider integrating your custom controls more deeply into the design-time environment.</span></span> <span data-ttu-id="c22e4-171">次のトピックでは、カスタム コントロールのデザイン時の統合を強化する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c22e4-171">The following topics describe how to enhance the design-time integration of your custom controls:</span></span>

- <span data-ttu-id="c22e4-172">[デザイン時アーキテクチャ](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/c5z9s1h4(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="c22e4-172">[Design-Time Architecture](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/c5z9s1h4(v=vs.120))</span></span>

- [<span data-ttu-id="c22e4-173">Windows フォーム コントロールの属性</span><span class="sxs-lookup"><span data-stu-id="c22e4-173">Attributes in Windows Forms Controls</span></span>](attributes-in-windows-forms-controls.md)

- <span data-ttu-id="c22e4-174">[デザイナーのシリアル化の概要](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171834(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="c22e4-174">[Designer Serialization Overview](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171834(v=vs.120))</span></span>

- [<span data-ttu-id="c22e4-175">チュートリアル: Visual Studio のデザイン時機能を活用した Windows フォーム コントロールの作成</span><span class="sxs-lookup"><span data-stu-id="c22e4-175">Walkthrough: Creating a Windows Forms Control That Takes Advantage of Visual Studio Design-Time Features</span></span>](creating-a-wf-control-design-time-features.md)

## <a name="see-also"></a><span data-ttu-id="c22e4-176">関連項目</span><span class="sxs-lookup"><span data-stu-id="c22e4-176">See also</span></span>

- <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute>
- <span data-ttu-id="c22e4-177">[デザイナーのシリアル化の概要](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171834(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="c22e4-177">[Designer Serialization Overview](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171834(v=vs.120))</span></span>
- <span data-ttu-id="c22e4-178">[方法: Designerserializationvisibilityattribute を使用、基本データ型のコレクションをシリアル化します。](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171833(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="c22e4-178">[How to: Serialize Collections of Standard Types with the DesignerSerializationVisibilityAttribute](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171833(v=vs.120))</span></span>
- [<span data-ttu-id="c22e4-179">チュートリアル: カスタム コンポーネントでツールボックスが自動的に入力</span><span class="sxs-lookup"><span data-stu-id="c22e4-179">Walkthrough: Automatically Populating the Toolbox with Custom Components</span></span>](walkthrough-automatically-populating-the-toolbox-with-custom-components.md)
