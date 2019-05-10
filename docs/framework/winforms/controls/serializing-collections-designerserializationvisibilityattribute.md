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
ms.openlocfilehash: c8321f98b25026e32e7c69f7029f2c589d0567f7
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65211597"
---
# <a name="walkthrough-serializing-collections-of-standard-types-with-the-designerserializationvisibilityattribute"></a><span data-ttu-id="e42bf-102">チュートリアル: DesignerSerializationVisibilityAttribute を使用した、標準データ型のコレクションのシリアル化</span><span class="sxs-lookup"><span data-stu-id="e42bf-102">Walkthrough: Serializing Collections of Standard Types with the DesignerSerializationVisibilityAttribute</span></span>

<span data-ttu-id="e42bf-103">カスタム コントロールでは、プロパティとしてコレクションを公開が場合があります。</span><span class="sxs-lookup"><span data-stu-id="e42bf-103">Your custom controls will sometimes expose a collection as a property.</span></span> <span data-ttu-id="e42bf-104">このチュートリアルを使用する方法について説明、<xref:System.ComponentModel.DesignerSerializationVisibilityAttribute>デザイン時にコレクションをシリアル化する方法を制御するクラス。</span><span class="sxs-lookup"><span data-stu-id="e42bf-104">This walkthrough demonstrates how to use the <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute> class to control how a collection is serialized at design time.</span></span> <span data-ttu-id="e42bf-105">適用、<xref:System.ComponentModel.DesignerSerializationVisibilityAttribute.Content>値をコレクション プロパティにより、プロパティをシリアル化されます。</span><span class="sxs-lookup"><span data-stu-id="e42bf-105">Applying the <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute.Content> value to your collection property ensures that the property will be serialized.</span></span>

<span data-ttu-id="e42bf-106">このトピックのコードを単一のリストとしてコピーするには、「[方法:Designerserializationvisibilityattribute を使用、基本データ型のコレクションをシリアル化](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171833(v=vs.120))します。</span><span class="sxs-lookup"><span data-stu-id="e42bf-106">To copy the code in this topic as a single listing, see [How to: Serialize Collections of Standard Types with the DesignerSerializationVisibilityAttribute](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171833(v=vs.120)).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="e42bf-107">必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="e42bf-107">Prerequisites</span></span>

<span data-ttu-id="e42bf-108">このチュートリアルを完了するには Visual Studio が必要です。</span><span class="sxs-lookup"><span data-stu-id="e42bf-108">You need Visual Studio to complete this walkthrough.</span></span>

## <a name="create-a-control-with-a-serializable-collection"></a><span data-ttu-id="e42bf-109">シリアル化可能なコレクションを使用してコントロールを作成します。</span><span class="sxs-lookup"><span data-stu-id="e42bf-109">Create a control with a serializable collection</span></span>

<span data-ttu-id="e42bf-110">最初の手順では、プロパティとしてシリアル化可能なコレクションを持つコントロールを作成します。</span><span class="sxs-lookup"><span data-stu-id="e42bf-110">The first step is to create a control that has a serializable collection as a property.</span></span> <span data-ttu-id="e42bf-111">使用してこのコレクションの内容を編集することができます、**コレクション エディター**からアクセスできますが、**プロパティ**ウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="e42bf-111">You can edit the contents of this collection using the **Collection Editor**, which you can access from the **Properties** window.</span></span>

1. <span data-ttu-id="e42bf-112">Visual Studio で、という名前の Windows コントロール ライブラリ プロジェクトを作成`SerializationDemoControlLib`です。</span><span class="sxs-lookup"><span data-stu-id="e42bf-112">In Visual Studio, create a Windows Control Library project called `SerializationDemoControlLib`.</span></span> <span data-ttu-id="e42bf-113">詳細については、次を参照してください。 [Windows コントロール ライブラリ テンプレート](https://docs.microsoft.com/previous-versions/kxczf775(v=vs.100))します。</span><span class="sxs-lookup"><span data-stu-id="e42bf-113">For more information, see [Windows Control Library Template](https://docs.microsoft.com/previous-versions/kxczf775(v=vs.100)).</span></span>

2. <span data-ttu-id="e42bf-114">名前を変更`UserControl1`に`SerializationDemoControl`します。</span><span class="sxs-lookup"><span data-stu-id="e42bf-114">Rename `UserControl1` to `SerializationDemoControl`.</span></span> <span data-ttu-id="e42bf-115">詳細については、次を参照してください。[コード シンボルのリファクタリングの名前を変更](/visualstudio/ide/reference/rename)します。</span><span class="sxs-lookup"><span data-stu-id="e42bf-115">For more information, see [Rename a code symbol refactoring](/visualstudio/ide/reference/rename).</span></span>

3. <span data-ttu-id="e42bf-116">**プロパティ**ウィンドウで、設定の値、<xref:System.Windows.Forms.Padding.All%2A?displayProperty=nameWithType>プロパティを`10`します。</span><span class="sxs-lookup"><span data-stu-id="e42bf-116">In the **Properties** window, set the value of the <xref:System.Windows.Forms.Padding.All%2A?displayProperty=nameWithType> property to `10`.</span></span>

4. <span data-ttu-id="e42bf-117">場所、<xref:System.Windows.Forms.TextBox>を制御、`SerializationDemoControl`します。</span><span class="sxs-lookup"><span data-stu-id="e42bf-117">Place a <xref:System.Windows.Forms.TextBox> control in the `SerializationDemoControl`.</span></span>

5. <span data-ttu-id="e42bf-118"><xref:System.Windows.Forms.TextBox> コントロールを選択します。</span><span class="sxs-lookup"><span data-stu-id="e42bf-118">Select the <xref:System.Windows.Forms.TextBox> control.</span></span> <span data-ttu-id="e42bf-119">**プロパティ**ウィンドウで、次のプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="e42bf-119">In the **Properties** window, set the following properties.</span></span>

    |<span data-ttu-id="e42bf-120">プロパティ</span><span class="sxs-lookup"><span data-stu-id="e42bf-120">Property</span></span>|<span data-ttu-id="e42bf-121">変更後の値</span><span class="sxs-lookup"><span data-stu-id="e42bf-121">Change to</span></span>|
    |--------------|---------------|
    |<span data-ttu-id="e42bf-122">**Multiline**</span><span class="sxs-lookup"><span data-stu-id="e42bf-122">**Multiline**</span></span>|`true`|
    |<span data-ttu-id="e42bf-123">**ドッキング ステーション**</span><span class="sxs-lookup"><span data-stu-id="e42bf-123">**Dock**</span></span>|<xref:System.Windows.Forms.DockStyle.Fill>|
    |<span data-ttu-id="e42bf-124">**ScrollBars**</span><span class="sxs-lookup"><span data-stu-id="e42bf-124">**ScrollBars**</span></span>|<xref:System.Windows.Forms.ScrollBars.Vertical>|
    |<span data-ttu-id="e42bf-125">**ReadOnly**</span><span class="sxs-lookup"><span data-stu-id="e42bf-125">**ReadOnly**</span></span>|`true`|

6. <span data-ttu-id="e42bf-126">**コード エディター**、という名前の文字列配列フィールドを宣言`stringsValue`で`SerializationDemoControl`します。</span><span class="sxs-lookup"><span data-stu-id="e42bf-126">In the **Code Editor**, declare a string array field named `stringsValue` in `SerializationDemoControl`.</span></span>

     [!code-cpp[System.ComponentModel.DesignerSerializationVisibilityAttribute#4](~/samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/cpp/form1.cpp#4)]
     [!code-csharp[System.ComponentModel.DesignerSerializationVisibilityAttribute#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/CS/form1.cs#4)]
     [!code-vb[System.ComponentModel.DesignerSerializationVisibilityAttribute#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/VB/form1.vb#4)]

7. <span data-ttu-id="e42bf-127">定義、`Strings`プロパティを`SerializationDemoControl`します。</span><span class="sxs-lookup"><span data-stu-id="e42bf-127">Define the `Strings` property on the `SerializationDemoControl`.</span></span>

   > [!NOTE]
   > <span data-ttu-id="e42bf-128"><xref:System.ComponentModel.DesignerSerializationVisibilityAttribute.Content>値を使用して、コレクションのシリアル化を有効にします。</span><span class="sxs-lookup"><span data-stu-id="e42bf-128">The <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute.Content> value is used to enable serialization of the collection.</span></span>

   [!code-cpp[System.ComponentModel.DesignerSerializationVisibilityAttribute#5](~/samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/cpp/form1.cpp#5)]
   [!code-csharp[System.ComponentModel.DesignerSerializationVisibilityAttribute#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/CS/form1.cs#5)]
   [!code-vb[System.ComponentModel.DesignerSerializationVisibilityAttribute#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/VB/form1.vb#5)]

8. <span data-ttu-id="e42bf-129">キーを押して**F5**プロジェクトをビルドしでコントロールを実行する、 **UserControl Test Container**します。</span><span class="sxs-lookup"><span data-stu-id="e42bf-129">Press **F5** to build the project and run your control in the **UserControl Test Container**.</span></span>

9. <span data-ttu-id="e42bf-130">検索、`Strings`プロパティ、<xref:System.Windows.Forms.PropertyGrid>の**UserControl Test Container**します。</span><span class="sxs-lookup"><span data-stu-id="e42bf-130">Find the `Strings` property in the <xref:System.Windows.Forms.PropertyGrid> of the **UserControl Test Container**.</span></span> <span data-ttu-id="e42bf-131">をクリックして、`Strings`プロパティ、省略記号をクリックします (![VisualStudioEllipsesButton スクリーン ショット](../media/vbellipsesbutton.png "vbEllipsesButton")) ボタンをクリックする、 **の文字列コレクションエディター**.</span><span class="sxs-lookup"><span data-stu-id="e42bf-131">Click the `Strings` property, then click the ellipsis (![VisualStudioEllipsesButton screenshot](../media/vbellipsesbutton.png "vbEllipsesButton")) button to open the **String Collection Editor**.</span></span>

10. <span data-ttu-id="e42bf-132">内のいくつかの文字列を入力、**文字列コレクション エディター**します。</span><span class="sxs-lookup"><span data-stu-id="e42bf-132">Enter several strings in the **String Collection Editor**.</span></span> <span data-ttu-id="e42bf-133">キーを押して区切ります、 **Enter**各文字列の末尾にあるキー。</span><span class="sxs-lookup"><span data-stu-id="e42bf-133">Separate them by pressing the **Enter** key at the end of each string.</span></span> <span data-ttu-id="e42bf-134">クリックして**OK**文字列の入力が完了したら。</span><span class="sxs-lookup"><span data-stu-id="e42bf-134">Click **OK** when you are finished entering strings.</span></span>

   > [!NOTE]
   > <span data-ttu-id="e42bf-135">入力した文字列に表示されます、<xref:System.Windows.Forms.TextBox>の`SerializationDemoControl`します。</span><span class="sxs-lookup"><span data-stu-id="e42bf-135">The strings you typed appear in the <xref:System.Windows.Forms.TextBox> of the `SerializationDemoControl`.</span></span>

## <a name="serializing-a-collection-property"></a><span data-ttu-id="e42bf-136">コレクション プロパティをシリアル化します。</span><span class="sxs-lookup"><span data-stu-id="e42bf-136">Serializing a Collection Property</span></span>

<span data-ttu-id="e42bf-137">コントロールのシリアル化動作をテストするをフォームに配置を使用して、コレクションの内容を変更するが、**コレクション エディター**します。</span><span class="sxs-lookup"><span data-stu-id="e42bf-137">To test the serialization behavior of your control, you will place it on a form and change the contents of the collection with the **Collection Editor**.</span></span> <span data-ttu-id="e42bf-138">特殊なデザイナー ファイルを調べることで、シリアル化されたコレクションの状態を確認できます、 **Windows フォーム デザイナー**はコードを出力します。</span><span class="sxs-lookup"><span data-stu-id="e42bf-138">You can see the serialized collection state by looking at a special designer file into which the **Windows Forms Designer** emits code.</span></span>

### <a name="to-serialize-a-collection"></a><span data-ttu-id="e42bf-139">コレクションをシリアル化するには</span><span class="sxs-lookup"><span data-stu-id="e42bf-139">To serialize a collection</span></span>

1. <span data-ttu-id="e42bf-140">Windows アプリケーション プロジェクトをソリューションに追加します。</span><span class="sxs-lookup"><span data-stu-id="e42bf-140">Add a Windows Application project to the solution.</span></span> <span data-ttu-id="e42bf-141">プロジェクトに `SerializationDemoControlTest` という名前を付けます。</span><span class="sxs-lookup"><span data-stu-id="e42bf-141">Name the project `SerializationDemoControlTest`.</span></span>

2. <span data-ttu-id="e42bf-142">**ツールボックス**、という名前のタブを見つける**SerializationDemoControlLib コンポーネント**します。</span><span class="sxs-lookup"><span data-stu-id="e42bf-142">In the **Toolbox**, find the tab named **SerializationDemoControlLib Components**.</span></span> <span data-ttu-id="e42bf-143">このタブでは紹介、`SerializationDemoControl`します。</span><span class="sxs-lookup"><span data-stu-id="e42bf-143">In this tab, you will find the `SerializationDemoControl`.</span></span> <span data-ttu-id="e42bf-144">詳細については、「[チュートリアル:カスタム コンポーネントでツールボックスが自動的に入力](walkthrough-automatically-populating-the-toolbox-with-custom-components.md)します。</span><span class="sxs-lookup"><span data-stu-id="e42bf-144">For more information, see [Walkthrough: Automatically Populating the Toolbox with Custom Components](walkthrough-automatically-populating-the-toolbox-with-custom-components.md).</span></span>

3. <span data-ttu-id="e42bf-145">場所、`SerializationDemoControl`フォームにします。</span><span class="sxs-lookup"><span data-stu-id="e42bf-145">Place a `SerializationDemoControl` on your form.</span></span>

4. <span data-ttu-id="e42bf-146">検索、`Strings`プロパティ、**プロパティ**ウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="e42bf-146">Find the `Strings` property in the **Properties** window.</span></span> <span data-ttu-id="e42bf-147">をクリックして、`Strings`プロパティ、省略記号をクリックします (![VisualStudioEllipsesButton スクリーン ショット](../media/vbellipsesbutton.png "vbEllipsesButton")) ボタンをクリックする、 **の文字列コレクションエディター**.</span><span class="sxs-lookup"><span data-stu-id="e42bf-147">Click the `Strings` property, then click the ellipsis (![VisualStudioEllipsesButton screenshot](../media/vbellipsesbutton.png "vbEllipsesButton")) button to open the **String Collection Editor**.</span></span>

5. <span data-ttu-id="e42bf-148">内のいくつかの文字列を入力、**文字列コレクション エディター**します。</span><span class="sxs-lookup"><span data-stu-id="e42bf-148">Type several strings in the **String Collection Editor**.</span></span> <span data-ttu-id="e42bf-149">各文字列の最後に ENTER キーを押すで区切ります。</span><span class="sxs-lookup"><span data-stu-id="e42bf-149">Separate them by pressing the ENTER key at the end of each string.</span></span> <span data-ttu-id="e42bf-150">クリックして**OK**文字列の入力が完了したら。</span><span class="sxs-lookup"><span data-stu-id="e42bf-150">Click **OK** when you are finished entering strings.</span></span>

> [!NOTE]
> <span data-ttu-id="e42bf-151">入力した文字列に表示されます、<xref:System.Windows.Forms.TextBox>の`SerializationDemoControl`します。</span><span class="sxs-lookup"><span data-stu-id="e42bf-151">The strings you typed appear in the <xref:System.Windows.Forms.TextBox> of the `SerializationDemoControl`.</span></span>

1. <span data-ttu-id="e42bf-152">**ソリューション エクスプローラー**で、**[すべてのファイルを表示]** ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="e42bf-152">In **Solution Explorer**, click the **Show All Files** button.</span></span>

2. <span data-ttu-id="e42bf-153">開く、 **Form1**ノード。</span><span class="sxs-lookup"><span data-stu-id="e42bf-153">Open the **Form1** node.</span></span> <span data-ttu-id="e42bf-154">という名前のファイルは、その下に**Form1.Designer.cs**または**Form1.Designer.vb**します。</span><span class="sxs-lookup"><span data-stu-id="e42bf-154">Beneath it is a file called **Form1.Designer.cs** or **Form1.Designer.vb**.</span></span> <span data-ttu-id="e42bf-155">これは、ファイルに、 **Windows フォーム デザイナー**フォームとその子コントロールのデザイン時の状態を表すコードを出力します。</span><span class="sxs-lookup"><span data-stu-id="e42bf-155">This is the file into which the **Windows Forms Designer** emits code representing the design-time state of your form and its child controls.</span></span> <span data-ttu-id="e42bf-156">このファイルを**コード エディター**で開きます。</span><span class="sxs-lookup"><span data-stu-id="e42bf-156">Open this file in the **Code Editor**.</span></span>

3. <span data-ttu-id="e42bf-157">呼ばれる領域を開く**Windows フォーム デザイナーで生成されたコード**というラベルの付いたセクションを見つけて**serializationDemoControl1**します。</span><span class="sxs-lookup"><span data-stu-id="e42bf-157">Open the region called **Windows Form Designer generated code** and find the section labeled **serializationDemoControl1**.</span></span> <span data-ttu-id="e42bf-158">このラベルの下には、コントロールのシリアル化された状態を表すコードです。</span><span class="sxs-lookup"><span data-stu-id="e42bf-158">Beneath this label is the code representing the serialized state of your control.</span></span> <span data-ttu-id="e42bf-159">代入に表示される手順 5. で入力した文字列、`Strings`プロパティ。</span><span class="sxs-lookup"><span data-stu-id="e42bf-159">The strings you typed in step 5 appear in an assignment to the `Strings` property.</span></span> <span data-ttu-id="e42bf-160">C# および Visual Basic では、次のコード例は、表示される内容の文字列"red"、「オレンジ」および「黄色」を入力したかどうかのようなコードを示します。</span><span class="sxs-lookup"><span data-stu-id="e42bf-160">The following code examples in C# and Visual Basic, show code similar to what you will see if you typed the strings "red", "orange", and "yellow".</span></span>

    ```csharp
    this.serializationDemoControl1.Strings = new string[] {
            "red",
            "orange",
            "yellow"};
    ```

    ```vb
    Me.serializationDemoControl1.Strings = New String() {"red", "orange", "yellow"}
    ```

4. <span data-ttu-id="e42bf-161">**コード エディター**の値を変更、<xref:System.ComponentModel.DesignerSerializationVisibilityAttribute>上、`Strings`プロパティを<xref:System.ComponentModel.DesignerSerializationVisibility.Hidden>します。</span><span class="sxs-lookup"><span data-stu-id="e42bf-161">In the **Code Editor**, change the value of the <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute> on the `Strings` property to <xref:System.ComponentModel.DesignerSerializationVisibility.Hidden>.</span></span>

    ```csharp
    [DesignerSerializationVisibility(DesignerSerializationVisibility.Hidden)]
    ```

    ```vb
    <DesignerSerializationVisibility(DesignerSerializationVisibility.Hidden)> _
    ```

5. <span data-ttu-id="e42bf-162">ソリューションを再構築、手順 3. および 4. を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="e42bf-162">Rebuild the solution and repeat steps 3 and 4.</span></span>

> [!NOTE]
> <span data-ttu-id="e42bf-163">ここで、 **Windows フォーム デザイナー**への割り当ては出力されません、`Strings`プロパティ。</span><span class="sxs-lookup"><span data-stu-id="e42bf-163">In this case, the **Windows Forms Designer** emits no assignment to the `Strings` property.</span></span>

## <a name="next-steps"></a><span data-ttu-id="e42bf-164">次の手順</span><span class="sxs-lookup"><span data-stu-id="e42bf-164">Next Steps</span></span>

<span data-ttu-id="e42bf-165">基本データ型のコレクションをシリアル化する方法を理解、デザイン時環境に、カスタム コントロールをより深く統合を検討してください。</span><span class="sxs-lookup"><span data-stu-id="e42bf-165">Once you know how to serialize a collection of standard types, consider integrating your custom controls more deeply into the design-time environment.</span></span> <span data-ttu-id="e42bf-166">次のトピックでは、カスタム コントロールのデザイン時の統合を強化する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="e42bf-166">The following topics describe how to enhance the design-time integration of your custom controls:</span></span>

- <span data-ttu-id="e42bf-167">[デザイン時アーキテクチャ](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/c5z9s1h4(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="e42bf-167">[Design-Time Architecture](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/c5z9s1h4(v=vs.120))</span></span>

- [<span data-ttu-id="e42bf-168">Windows フォーム コントロールの属性</span><span class="sxs-lookup"><span data-stu-id="e42bf-168">Attributes in Windows Forms Controls</span></span>](attributes-in-windows-forms-controls.md)

- <span data-ttu-id="e42bf-169">[デザイナーのシリアル化の概要](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171834(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="e42bf-169">[Designer Serialization Overview](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171834(v=vs.120))</span></span>

- [<span data-ttu-id="e42bf-170">チュートリアル: Visual Studio のデザイン時機能を活用した Windows フォーム コントロールの作成</span><span class="sxs-lookup"><span data-stu-id="e42bf-170">Walkthrough: Creating a Windows Forms Control That Takes Advantage of Visual Studio Design-Time Features</span></span>](creating-a-wf-control-design-time-features.md)

## <a name="see-also"></a><span data-ttu-id="e42bf-171">関連項目</span><span class="sxs-lookup"><span data-stu-id="e42bf-171">See also</span></span>

- <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute>
- <span data-ttu-id="e42bf-172">[デザイナーのシリアル化の概要](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171834(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="e42bf-172">[Designer Serialization Overview](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171834(v=vs.120))</span></span>
- <span data-ttu-id="e42bf-173">[方法: Designerserializationvisibilityattribute を使用、基本データ型のコレクションをシリアル化します。](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171833(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="e42bf-173">[How to: Serialize Collections of Standard Types with the DesignerSerializationVisibilityAttribute](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171833(v=vs.120))</span></span>
- [<span data-ttu-id="e42bf-174">チュートリアル: カスタム コンポーネントでツールボックスが自動的に入力</span><span class="sxs-lookup"><span data-stu-id="e42bf-174">Walkthrough: Automatically Populating the Toolbox with Custom Components</span></span>](walkthrough-automatically-populating-the-toolbox-with-custom-components.md)
