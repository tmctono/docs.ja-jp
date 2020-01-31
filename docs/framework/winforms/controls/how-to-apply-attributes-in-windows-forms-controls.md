---
title: コントロールに属性を適用する
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [Windows Forms], applying attributes
- attributes [Windows Forms], applying
- Windows Forms controls, applying attributes
ms.assetid: af0a3f7f-155b-4ba1-83c4-9cf721331a06
ms.openlocfilehash: b8ecd516cf6bb189c6ad1b208dd8e3a5444f001c
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741493"
---
# <a name="how-to-apply-attributes-in-windows-forms-controls"></a><span data-ttu-id="1bfe4-102">方法 : Windows フォーム コントロールに属性を適用する</span><span class="sxs-lookup"><span data-stu-id="1bfe4-102">How to: Apply Attributes in Windows Forms Controls</span></span>
<span data-ttu-id="1bfe4-103">デザイン環境と正しく対話し、実行時に正常に実行されるコンポーネントとコントロールを開発するには、クラスおよびメンバーに属性を正しく適用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1bfe4-103">To develop components and controls that interact correctly with the design environment and execute correctly at run time, you need to apply attributes correctly to classes and members.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1bfe4-104">使用例</span><span class="sxs-lookup"><span data-stu-id="1bfe4-104">Example</span></span>  
 <span data-ttu-id="1bfe4-105">次のコード例は、カスタムコントロールでいくつかの属性を使用する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="1bfe4-105">The following code example demonstrates how to use several attributes on a custom control.</span></span> <span data-ttu-id="1bfe4-106">このコントロールは、単純なログ記録機能を示しています。</span><span class="sxs-lookup"><span data-stu-id="1bfe4-106">The control demonstrates a simple logging capability.</span></span> <span data-ttu-id="1bfe4-107">コントロールがデータソースにバインドされると、<xref:System.Windows.Forms.DataGridView> コントロールにデータソースから送信された値が表示されます。</span><span class="sxs-lookup"><span data-stu-id="1bfe4-107">When the control is bound to a data source, it displays the values sent by the data source in a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="1bfe4-108">値が `Threshold` プロパティによって指定された値を超えると、`ThresholdExceeded` イベントが発生します。</span><span class="sxs-lookup"><span data-stu-id="1bfe4-108">If a value exceeds the value specified by the `Threshold` property, a `ThresholdExceeded` event is raised.</span></span>  
  
 <span data-ttu-id="1bfe4-109">`AttributesDemoControl` は、`LogEntry` クラスを使用して値をログに記録します。</span><span class="sxs-lookup"><span data-stu-id="1bfe4-109">The `AttributesDemoControl` logs values with a `LogEntry` class.</span></span> <span data-ttu-id="1bfe4-110">`LogEntry` クラスはテンプレートクラスであり、これはログに記録される型でパラメーター化されることを意味します。</span><span class="sxs-lookup"><span data-stu-id="1bfe4-110">The `LogEntry` class is a template class, which means it is parameterized on the type that it logs.</span></span> <span data-ttu-id="1bfe4-111">たとえば、`AttributesDemoControl` が `float`型の値をログに記録している場合、各 `LogEntry` インスタンスは次のように宣言されて使用されます。</span><span class="sxs-lookup"><span data-stu-id="1bfe4-111">For example, if the `AttributesDemoControl` is logging values of type `float`, each `LogEntry` instance is declared and used as follows.</span></span>  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#110](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/form1.cs#110)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#110](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/form1.vb#110)]  
  
> [!NOTE]
> <span data-ttu-id="1bfe4-112">`LogEntry` は任意の型によってパラメーター化されるため、パラメーターの型を操作するにはリフレクションを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1bfe4-112">Because `LogEntry` is parameterized by an arbitrary type, it must use reflection to operate on the parameter type.</span></span> <span data-ttu-id="1bfe4-113">しきい値機能を機能させるには、パラメーターの型 `T` が <xref:System.IComparable> インターフェイスを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1bfe4-113">For the threshold feature to work, the parameter type `T` must implement the <xref:System.IComparable> interface.</span></span>  
  
 <span data-ttu-id="1bfe4-114">`AttributesDemoControl` をホストするフォームは、パフォーマンスカウンターを定期的に照会します。</span><span class="sxs-lookup"><span data-stu-id="1bfe4-114">The form that hosts the `AttributesDemoControl` queries a performance counter periodically.</span></span> <span data-ttu-id="1bfe4-115">各値は、適切な型の `LogEntry` にパッケージ化され、フォームの <xref:System.Windows.Forms.BindingSource>に追加されます。</span><span class="sxs-lookup"><span data-stu-id="1bfe4-115">Each value is packaged in a `LogEntry` of the appropriate type and added to the form's <xref:System.Windows.Forms.BindingSource>.</span></span> <span data-ttu-id="1bfe4-116">`AttributesDemoControl` は、データバインディングを介して値を受け取り、<xref:System.Windows.Forms.DataGridView> コントロールに値を表示します。</span><span class="sxs-lookup"><span data-stu-id="1bfe4-116">The `AttributesDemoControl` receives the value through its data binding and displays the value in a <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#1)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#1)]  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#100](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/form1.cs#100)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#100](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/form1.vb#100)]  
  
 <span data-ttu-id="1bfe4-117">最初のコード例は、`AttributesDemoControl` の実装です。</span><span class="sxs-lookup"><span data-stu-id="1bfe4-117">The first code example is the `AttributesDemoControl` implementation.</span></span> <span data-ttu-id="1bfe4-118">2番目のコード例は、`AttributesDemoControl`を使用するフォームを示しています。</span><span class="sxs-lookup"><span data-stu-id="1bfe4-118">The second code example demonstrates a form that uses the `AttributesDemoControl`.</span></span>  
  
## <a name="class-level-attributes"></a><span data-ttu-id="1bfe4-119">クラスレベルの属性</span><span class="sxs-lookup"><span data-stu-id="1bfe4-119">Class-level Attributes</span></span>  
 <span data-ttu-id="1bfe4-120">一部の属性はクラスレベルで適用されます。</span><span class="sxs-lookup"><span data-stu-id="1bfe4-120">Some attributes are applied at the class level.</span></span> <span data-ttu-id="1bfe4-121">次のコード例は、Windows フォームコントロールに一般的に適用される属性を示しています。</span><span class="sxs-lookup"><span data-stu-id="1bfe4-121">The following code example shows the attributes that are commonly applied to a Windows Forms control.</span></span>  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#20)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#20)]  
  
### <a name="typeconverter-attribute"></a><span data-ttu-id="1bfe4-122">TypeConverter 属性</span><span class="sxs-lookup"><span data-stu-id="1bfe4-122">TypeConverter Attribute</span></span>  
 <span data-ttu-id="1bfe4-123"><xref:System.ComponentModel.TypeConverterAttribute> は、一般的に使用されるもう1つのクラスレベルの属性です。</span><span class="sxs-lookup"><span data-stu-id="1bfe4-123"><xref:System.ComponentModel.TypeConverterAttribute> is another commonly used class-level attribute.</span></span> <span data-ttu-id="1bfe4-124">次のコード例は、`LogEntry` クラスの使用方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="1bfe4-124">The following code example shows its use for the `LogEntry` class.</span></span> <span data-ttu-id="1bfe4-125">この例では、`LogEntryTypeConverter`と呼ばれる `LogEntry` 型の <xref:System.ComponentModel.TypeConverter> の実装も示しています。</span><span class="sxs-lookup"><span data-stu-id="1bfe4-125">This example also shows an implementation of a <xref:System.ComponentModel.TypeConverter> for the `LogEntry` type, called `LogEntryTypeConverter`.</span></span>  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#5)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#5)]  
  
## <a name="member-level-attributes"></a><span data-ttu-id="1bfe4-126">メンバーレベルの属性</span><span class="sxs-lookup"><span data-stu-id="1bfe4-126">Member-level Attributes</span></span>  
 <span data-ttu-id="1bfe4-127">一部の属性は、メンバーレベルで適用されます。</span><span class="sxs-lookup"><span data-stu-id="1bfe4-127">Some attributes are applied at the member level.</span></span> <span data-ttu-id="1bfe4-128">次のコード例は、Windows フォームコントロールのプロパティに一般的に適用されるいくつかの属性を示しています。</span><span class="sxs-lookup"><span data-stu-id="1bfe4-128">The following code examples show some attributes that are commonly applied to properties of Windows Forms controls.</span></span>  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#21)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#21)]  
  
### <a name="ambientvalue-attribute"></a><span data-ttu-id="1bfe4-129">AmbientValue 属性</span><span class="sxs-lookup"><span data-stu-id="1bfe4-129">AmbientValue Attribute</span></span>  
 <span data-ttu-id="1bfe4-130">次の例では、<xref:System.ComponentModel.AmbientValueAttribute> を示し、デザイン環境との対話をサポートするコードを示します。</span><span class="sxs-lookup"><span data-stu-id="1bfe4-130">The following example demonstrates the <xref:System.ComponentModel.AmbientValueAttribute> and shows code that supports its interaction with the design environment.</span></span> <span data-ttu-id="1bfe4-131">この相互作用は、"*アンビエント*" と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="1bfe4-131">This interaction is called *ambience*.</span></span>  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#23](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#23)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#23](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#23)]  
  
### <a name="databinding-attributes"></a><span data-ttu-id="1bfe4-132">Databinding 属性</span><span class="sxs-lookup"><span data-stu-id="1bfe4-132">Databinding Attributes</span></span>  
 <span data-ttu-id="1bfe4-133">次の例は、複合データバインディングの実装を示しています。</span><span class="sxs-lookup"><span data-stu-id="1bfe4-133">The following examples demonstrate an implementation of complex data binding.</span></span> <span data-ttu-id="1bfe4-134">前に示したクラスレベルの <xref:System.ComponentModel.ComplexBindingPropertiesAttribute>では、データバインディングに使用する `DataSource` と `DataMember` のプロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="1bfe4-134">The class-level <xref:System.ComponentModel.ComplexBindingPropertiesAttribute>, shown previously, specifies the `DataSource` and `DataMember` properties to use for data binding.</span></span> <span data-ttu-id="1bfe4-135"><xref:System.ComponentModel.AttributeProviderAttribute> は、`DataSource` プロパティのバインド先となる型を指定します。</span><span class="sxs-lookup"><span data-stu-id="1bfe4-135">The <xref:System.ComponentModel.AttributeProviderAttribute> specifies the type to which the `DataSource` property will bind.</span></span>  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#25](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#25)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#25](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#25)]  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#26](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#26)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#26](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#26)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="1bfe4-136">コードのコンパイル方法</span><span class="sxs-lookup"><span data-stu-id="1bfe4-136">Compiling the Code</span></span>  
  
- <span data-ttu-id="1bfe4-137">`AttributesDemoControl` をホストするフォームは、ビルドするために `AttributesDemoControl` アセンブリへの参照を必要とします。</span><span class="sxs-lookup"><span data-stu-id="1bfe4-137">The form that hosts the `AttributesDemoControl` requires a reference to the `AttributesDemoControl` assembly in order to build.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1bfe4-138">関連項目</span><span class="sxs-lookup"><span data-stu-id="1bfe4-138">See also</span></span>

- <xref:System.IComparable>
- <xref:System.Windows.Forms.DataGridView>
- [<span data-ttu-id="1bfe4-139">.NET Framework を使用したカスタム Windows フォーム コントロールの開発</span><span class="sxs-lookup"><span data-stu-id="1bfe4-139">Developing Custom Windows Forms Controls with the .NET Framework</span></span>](developing-custom-windows-forms-controls.md)
- [<span data-ttu-id="1bfe4-140">Windows フォーム コントロールの属性</span><span class="sxs-lookup"><span data-stu-id="1bfe4-140">Attributes in Windows Forms Controls</span></span>](attributes-in-windows-forms-controls.md)
- <span data-ttu-id="1bfe4-141">[方法: DesignerSerializationVisibilityAttribute を使用して標準型のコレクションをシリアル化する](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171833(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="1bfe4-141">[How to: Serialize Collections of Standard Types with the DesignerSerializationVisibilityAttribute](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171833(v=vs.120))</span></span>
