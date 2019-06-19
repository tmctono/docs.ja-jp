---
title: プロパティ グリッドの拡張 - WF のサンプル
ms.date: 03/30/2017
ms.assetid: 3530c3a3-756d-4712-9f10-fb2897414d3a
ms.openlocfilehash: 1cc8b8b34d6236e263f95439da84994e35d627ed
ms.sourcegitcommit: a8d3504f0eae1a40bda2b06bd441ba01f1631ef0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/18/2019
ms.locfileid: "67170363"
---
# <a name="property-grid-extensibility"></a><span data-ttu-id="f1485-102">プロパティ グリッドの拡張</span><span class="sxs-lookup"><span data-stu-id="f1485-102">Property grid extensibility</span></span>

<span data-ttu-id="f1485-103">開発者は、デザイナー内で特定のアクティビティを選択したときに表示されるプロパティ グリッドをカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="f1485-103">A developer can customize the property grid that is displayed when a given activity is selected within the designer.</span></span> <span data-ttu-id="f1485-104">これにより、高度な編集操作の作成が可能になります。</span><span class="sxs-lookup"><span data-stu-id="f1485-104">This can be done to create a rich editing experience.</span></span> <span data-ttu-id="f1485-105">このサンプルでは、その方法を示します。</span><span class="sxs-lookup"><span data-stu-id="f1485-105">This sample shows how this can be done.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="f1485-106">使用例</span><span class="sxs-lookup"><span data-stu-id="f1485-106">Demonstrates</span></span>

<span data-ttu-id="f1485-107">ワークフロー デザイナーのプロパティ グリッドの拡張。</span><span class="sxs-lookup"><span data-stu-id="f1485-107">Workflow designer property grid extensibility.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f1485-108">サンプルは、既にコンピューターにインストールされている場合があります。</span><span class="sxs-lookup"><span data-stu-id="f1485-108">The samples may already be installed on your machine.</span></span> <span data-ttu-id="f1485-109">続行する前に、次の (既定の) ディレクトリを確認してください。</span><span class="sxs-lookup"><span data-stu-id="f1485-109">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="f1485-110">このディレクトリが存在しない場合に移動[Windows Communication Foundation (WCF) と .NET Framework 4 向けの Windows Workflow Foundation (WF) サンプル](https://go.microsoft.com/fwlink/?LinkId=150780)すべて Windows Communication Foundation (WCF) をダウンロードして[!INCLUDE[wf1](../../../../includes/wf1-md.md)]サンプル。</span><span class="sxs-lookup"><span data-stu-id="f1485-110">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="f1485-111">このサンプルは、次のディレクトリに格納されます。</span><span class="sxs-lookup"><span data-stu-id="f1485-111">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Designer\PropertyGridExtensibility`

## <a name="discussion"></a><span data-ttu-id="f1485-112">説明</span><span class="sxs-lookup"><span data-stu-id="f1485-112">Discussion</span></span>

<span data-ttu-id="f1485-113">開発者がプロパティ グリッドを拡張できるように、プロパティ グリッド エディターのインラインの外観をカスタマイズするオプションと、高度な編集画面用のダイアログを表示するオプションが用意されています。</span><span class="sxs-lookup"><span data-stu-id="f1485-113">To extend the property grid, a developer has options to customize the inline appearance of a property grid editor or provide a dialog that appears for a more advanced editing surface.</span></span> <span data-ttu-id="f1485-114">このサンプルでは、インライン エディターとダイアログ エディターの 2 種類のエディターを示します。</span><span class="sxs-lookup"><span data-stu-id="f1485-114">There are two different editors demonstrated in this sample; an inline editor and a dialog editor.</span></span>

## <a name="inline-editor"></a><span data-ttu-id="f1485-115">インライン エディター</span><span class="sxs-lookup"><span data-stu-id="f1485-115">Inline editor</span></span>

<span data-ttu-id="f1485-116">インライン エディターのサンプルで示す内容は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="f1485-116">The inline editor sample demonstrates the following:</span></span>

- <span data-ttu-id="f1485-117"><xref:System.Activities.Presentation.PropertyEditing.PropertyValueEditor> から派生する型を作成します。</span><span class="sxs-lookup"><span data-stu-id="f1485-117">Creates a type that derives from <xref:System.Activities.Presentation.PropertyEditing.PropertyValueEditor>.</span></span>

- <span data-ttu-id="f1485-118">コンス トラクターで、 <xref:System.Activities.Presentation.PropertyEditing.PropertyValueEditor.InlineEditorTemplate%2A> Windows Presentation Foundation (WPF) データ テンプレートを使用して値を設定します。</span><span class="sxs-lookup"><span data-stu-id="f1485-118">In the constructor, the <xref:System.Activities.Presentation.PropertyEditing.PropertyValueEditor.InlineEditorTemplate%2A> value is set with a Windows Presentation Foundation (WPF) data template.</span></span> <span data-ttu-id="f1485-119">これは XAML テンプレートにバインドできますが、このサンプルではコードを使用してデータ バインディングを初期化します。</span><span class="sxs-lookup"><span data-stu-id="f1485-119">This can be bound to a XAML template, but in this sample, code is used to initialize data binding.</span></span>

- <span data-ttu-id="f1485-120">プロパティ グリッドに表示される項目の <xref:System.Activities.Presentation.PropertyEditing.PropertyValue> のデータ コンテキストは、データ テンプレートに含まれています。</span><span class="sxs-lookup"><span data-stu-id="f1485-120">The data template has a data context of the <xref:System.Activities.Presentation.PropertyEditing.PropertyValue> of the item rendered in the property grid.</span></span> <span data-ttu-id="f1485-121">次のコード (CustomInlineEditor.cs のコード) で、このコンテキストが `Value` プロパティにバインドされていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="f1485-121">Note in the following code (from CustomInlineEditor.cs) that this context then binds to the `Value` property.</span></span>

    ```csharp
    FrameworkElementFactory stack = new FrameworkElementFactory(typeof(StackPanel));
    FrameworkElementFactory slider = new FrameworkElementFactory(typeof(Slider));
    Binding sliderBinding = new Binding("Value");
    sliderBinding.Mode = BindingMode.TwoWay;
    slider.SetValue(Slider.MinimumProperty, 0.0);
    slider.SetValue(Slider.MaximumProperty, 100.0);
    slider.SetValue(Slider.ValueProperty, sliderBinding);
    stack.AppendChild(slider);
    ```

- <span data-ttu-id="f1485-122">アクティビティとデザイナーが同じアセンブリにあるため、アクティビティ デザイナーの属性の登録は、アクティビティ自体の静的コンストラクターで行われます。SimpleCodeActivity.cs の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="f1485-122">Because the activity and the designer are in the same assembly, registration of the activity designer attributes are accomplished in the static constructor of the activity itself, as shown in the following example from SimpleCodeActivity.cs.</span></span>

    ```csharp
    static SimpleCodeActivity()
    {
        AttributeTableBuilder builder = new AttributeTableBuilder();
        builder.AddCustomAttributes(typeof(SimpleCodeActivity), "RepeatCount", new EditorAttribute(typeof(CustomInlineEditor), typeof(PropertyValueEditor)));
        builder.AddCustomAttributes(typeof(SimpleCodeActivity), "FileName", new EditorAttribute(typeof(FilePickerEditor), typeof(DialogPropertyValueEditor)));
        MetadataStore.AddAttributeTable(builder.CreateTable());
    }
    ```

## <a name="dialog-editor"></a><span data-ttu-id="f1485-123">ダイアログ エディター</span><span class="sxs-lookup"><span data-stu-id="f1485-123">Dialog editor</span></span>

<span data-ttu-id="f1485-124">ダイアログ エディターのサンプルで示す内容は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="f1485-124">The dialog editor sample demonstrates the following:</span></span>

1. <span data-ttu-id="f1485-125"><xref:System.Activities.Presentation.PropertyEditing.DialogPropertyValueEditor> から派生する型を作成します。</span><span class="sxs-lookup"><span data-stu-id="f1485-125">Creates a type that derives from <xref:System.Activities.Presentation.PropertyEditing.DialogPropertyValueEditor>.</span></span>

2. <span data-ttu-id="f1485-126">セット、 <xref:System.Activities.Presentation.PropertyEditing.PropertyValueEditor.InlineEditorTemplate%2A> WPF のデータ テンプレートを使用するコンス トラクター内の値。</span><span class="sxs-lookup"><span data-stu-id="f1485-126">Sets the <xref:System.Activities.Presentation.PropertyEditing.PropertyValueEditor.InlineEditorTemplate%2A> value in the constructor with a WPF data template.</span></span> <span data-ttu-id="f1485-127">これは XAML で作成できますが、このサンプルではコードで作成します。</span><span class="sxs-lookup"><span data-stu-id="f1485-127">This can be created in XAML, but in this sample, this is created in code.</span></span>

3. <span data-ttu-id="f1485-128">プロパティ グリッドに表示される項目の <xref:System.Activities.Presentation.PropertyEditing.PropertyValue> のデータ コンテキストは、データ テンプレートに含まれています。</span><span class="sxs-lookup"><span data-stu-id="f1485-128">The data template has a data context of the <xref:System.Activities.Presentation.PropertyEditing.PropertyValue> of the item rendered in the property grid.</span></span> <span data-ttu-id="f1485-129">次のコードで、これが `Value` プロパティにバインドされています。</span><span class="sxs-lookup"><span data-stu-id="f1485-129">In the following code, this then binds to the `Value` property.</span></span> <span data-ttu-id="f1485-130">FilePickerEditor.cs では、ダイアログを起動するボタンを指定するための <xref:System.Activities.Presentation.PropertyEditing.EditModeSwitchButton> を含めることも重要です。</span><span class="sxs-lookup"><span data-stu-id="f1485-130">It is critical to also include an <xref:System.Activities.Presentation.PropertyEditing.EditModeSwitchButton> to provide the button that raises the dialog in FilePickerEditor.cs.</span></span>

    ```csharp
    this.InlineEditorTemplate = new DataTemplate();

    FrameworkElementFactory stack = new FrameworkElementFactory(typeof(StackPanel));
    stack.SetValue(StackPanel.OrientationProperty, Orientation.Horizontal);
    FrameworkElementFactory label = new FrameworkElementFactory(typeof(Label));
    Binding labelBinding = new Binding("Value");
    label.SetValue(Label.ContentProperty, labelBinding);
    label.SetValue(Label.MaxWidthProperty, 90.0);

    stack.AppendChild(label);

    FrameworkElementFactory editModeSwitch = new FrameworkElementFactory(typeof(EditModeSwitchButton));

    editModeSwitch.SetValue(EditModeSwitchButton.TargetEditModeProperty, PropertyContainerEditMode.Dialog);

    stack.AppendChild(editModeSwitch);

    this.InlineEditorTemplate.VisualTree = stack;
    ```

4. <span data-ttu-id="f1485-131">ダイアログの表示を処理するデザイナー型の <xref:System.Activities.Presentation.PropertyEditing.DialogPropertyValueEditor.ShowDialog%2A> メソッドをオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="f1485-131">Overrides the <xref:System.Activities.Presentation.PropertyEditing.DialogPropertyValueEditor.ShowDialog%2A> method in the designer type to handle the display of the dialog.</span></span> <span data-ttu-id="f1485-132">このサンプルでは、基本的な <xref:System.Windows.Forms.FileDialog> を示します。</span><span class="sxs-lookup"><span data-stu-id="f1485-132">In this sample, a basic <xref:System.Windows.Forms.FileDialog> is shown.</span></span>

    ```csharp
    public override void ShowDialog(PropertyValue propertyValue, IInputElement commandSource)
    {
        Microsoft.Win32.OpenFileDialog ofd = new Microsoft.Win32.OpenFileDialog();
        if (ofd.ShowDialog() == true)
        {
            propertyValue.Value = ofd.FileName;
        }
    }
    ```

5. <span data-ttu-id="f1485-133">アクティビティとデザイナーが同じアセンブリにあるため、アクティビティ デザイナーの属性の登録は、アクティビティ自体の静的コンストラクターで行われます。SimpleCodeActivity.cs の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="f1485-133">Because the activity and the designer are in the same assembly, registration of the activity designer attributes are accomplished in the static constructor of the activity itself, as shown in the following example from SimpleCodeActivity.cs.</span></span>

    ```csharp
    static SimpleCodeActivity()
    {
        AttributeTableBuilder builder = new AttributeTableBuilder();
        builder.AddCustomAttributes(typeof(SimpleCodeActivity), "RepeatCount", new EditorAttribute(typeof(CustomInlineEditor), typeof(PropertyValueEditor)));
        builder.AddCustomAttributes(typeof(SimpleCodeActivity), "FileName", new EditorAttribute(typeof(FilePickerEditor), typeof(DialogPropertyValueEditor)));
        MetadataStore.AddAttributeTable(builder.CreateTable());
    }
    ```

## <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="f1485-134">サンプルをセットアップ、ビルド、および実行するには</span><span class="sxs-lookup"><span data-stu-id="f1485-134">To set up, build, and run the sample</span></span>

1. <span data-ttu-id="f1485-135">ソリューションをビルドし、Workflow1.xaml を開きます。</span><span class="sxs-lookup"><span data-stu-id="f1485-135">Build the solution, and then open Workflow1.xaml.</span></span>

2. <span data-ttu-id="f1485-136">ドラッグ、 **SimpleCodeActivity**ツールボックスからデザイナー キャンバスにします。</span><span class="sxs-lookup"><span data-stu-id="f1485-136">Drag a **SimpleCodeActivity** from the toolbox onto the designer canvas.</span></span>

3. <span data-ttu-id="f1485-137">をクリックして、 **SimpleCodeActivity**スライダー コントロールが、ファイル選択コントロールし、プロパティ グリッドを開きます。</span><span class="sxs-lookup"><span data-stu-id="f1485-137">Click the **SimpleCodeActivity** and then open the property grid where there is a slider control and a file picking control.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f1485-138">サンプルは、既にコンピューターにインストールされている場合があります。</span><span class="sxs-lookup"><span data-stu-id="f1485-138">The samples may already be installed on your machine.</span></span> <span data-ttu-id="f1485-139">続行する前に、次の (既定の) ディレクトリを確認してください。</span><span class="sxs-lookup"><span data-stu-id="f1485-139">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="f1485-140">このディレクトリが存在しない場合に移動[Windows Communication Foundation (WCF) と .NET Framework 4 向けの Windows Workflow Foundation (WF) サンプル](https://go.microsoft.com/fwlink/?LinkId=150780)すべて Windows Communication Foundation (WCF) をダウンロードして[!INCLUDE[wf1](../../../../includes/wf1-md.md)]サンプル。</span><span class="sxs-lookup"><span data-stu-id="f1485-140">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="f1485-141">このサンプルは、次のディレクトリに格納されます。</span><span class="sxs-lookup"><span data-stu-id="f1485-141">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Designer\PropertyGridExtensibility`
