---
title: デザイナーを使用してコントロールを型にバインドする
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], binding to a type
- BindingSource component [Windows Forms], binding to a type
- types [Windows Forms], binding controls to
ms.assetid: 5ab984b5-c2d0-4638-a572-1c84013e8746
ms.openlocfilehash: 2257489e123ceeea819ad3538952db51b726c7e5
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742019"
---
# <a name="how-to-bind-a-windows-forms-control-to-a-type-using-the-designer"></a><span data-ttu-id="9ed0a-102">方法 : デザイナーを使って Windows フォーム コントロールを型にバインドする</span><span class="sxs-lookup"><span data-stu-id="9ed0a-102">How to: Bind a Windows Forms Control to a Type Using the Designer</span></span>

<span data-ttu-id="9ed0a-103">データをやり取りするコントロールを作成する際、オブジェクトではなく型にコントロールをバインドすることが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="9ed0a-103">When you are building controls that interact with data, you sometimes need to bind a control to a type, rather than an object.</span></span> <span data-ttu-id="9ed0a-104">データを使用できないが、データ バインド コントロールで型のパブリック インターフェイスからデータを表示する必要がある場合、通常はデザイン時にコントロールを型にバインドする必要があります。</span><span class="sxs-lookup"><span data-stu-id="9ed0a-104">You typically need to bind a control to a type at design time, when data may not be available, but you still want your data-bound controls to display data from a type's public interface.</span></span> <span data-ttu-id="9ed0a-105">次の手順では、型にバインドされている新しい <xref:System.Windows.Forms.BindingSource> を作成し、その型のプロパティの1つを <xref:System.Windows.Forms.TextBox>の <xref:System.Windows.Forms.TextBox.Text%2A> プロパティにバインドする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="9ed0a-105">The following procedures demonstrate how to create a new <xref:System.Windows.Forms.BindingSource> that is bound to a type, and then how to bind one of the type's properties to the <xref:System.Windows.Forms.TextBox.Text%2A> property of a <xref:System.Windows.Forms.TextBox>.</span></span>

### <a name="to-bind-the-bindingsource-to-a-type"></a><span data-ttu-id="9ed0a-106">BindingSource を型にバインドするには</span><span class="sxs-lookup"><span data-stu-id="9ed0a-106">To bind the BindingSource to a type</span></span>

1. <span data-ttu-id="9ed0a-107">Windows フォームプロジェクトを作成します (**ファイル** > **新しい** > **プロジェクト** >  **C# Visual**または**Visual Basic** > **クラシックデスクトップ** > **Windows フォームアプリケーション**)。</span><span class="sxs-lookup"><span data-stu-id="9ed0a-107">Create a Windows Forms project (**File** > **New** > **Project** > **Visual C#** or **Visual Basic** > **Classic Desktop** > **Windows Forms Application**).</span></span>

2. <span data-ttu-id="9ed0a-108">**デザイン**ビューで、<xref:System.Windows.Forms.BindingSource> コンポーネントをフォームにドラッグします。</span><span class="sxs-lookup"><span data-stu-id="9ed0a-108">In **Design** view, drag a <xref:System.Windows.Forms.BindingSource> component onto the form.</span></span>

3. <span data-ttu-id="9ed0a-109">**[プロパティ]** ウィンドウで、[<xref:System.Windows.Forms.BindingSource.DataSource%2A>] プロパティの矢印をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9ed0a-109">In the **Properties** window, click the arrow for the <xref:System.Windows.Forms.BindingSource.DataSource%2A> property.</span></span>

4. <span data-ttu-id="9ed0a-110">**DataSource UI 型エディター**で、 **[プロジェクト データ ソースの追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9ed0a-110">In the **DataSource UI Type Editor**, click **Add Project Data Source**.</span></span>

5. <span data-ttu-id="9ed0a-111">**[データ ソースの種類を選択]** ページで、 **[オブジェクト]** を選択して **[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9ed0a-111">On the **Choose a Data Source Type** page, select **Object** and click **Next**.</span></span>

6. <span data-ttu-id="9ed0a-112">バインド先となる型を選択します。</span><span class="sxs-lookup"><span data-stu-id="9ed0a-112">Select the type to bind to:</span></span>

    - <span data-ttu-id="9ed0a-113">バインド先となる型が現在のプロジェクトにある場合、または、型を含むアセンブリが参照として既に追加されている場合は、ノードを展開し、目的の型を探して選択します。</span><span class="sxs-lookup"><span data-stu-id="9ed0a-113">If the type you want to bind to is in the current project, or the assembly that contains the type is already added as a reference, expand the nodes to find the type you want, and then select it.</span></span>

      <span data-ttu-id="9ed0a-114">\- または -</span><span class="sxs-lookup"><span data-stu-id="9ed0a-114">\-or-</span></span>

    - <span data-ttu-id="9ed0a-115">バインド先の型が、現在参照の一覧にない別のアセンブリにある場合は、 **[参照の追加]** をクリックし、 **[プロジェクト]** タブをクリックします。必要なビジネスオブジェクトが含まれているプロジェクトを選択し、 **[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9ed0a-115">If the type you want to bind to is in another assembly, not currently in the list of references, click **Add Reference**, and then click the **Projects** tab. Select the project that contains the business object you want and click **OK**.</span></span> <span data-ttu-id="9ed0a-116">このプロジェクトは、アセンブリの一覧に表示されるため、ノードを展開し、目的の型を探して選択します。</span><span class="sxs-lookup"><span data-stu-id="9ed0a-116">This project will appear in the list of assemblies, so you can expand the nodes to find the type you want, and then select it.</span></span>

      > [!NOTE]
      > <span data-ttu-id="9ed0a-117">フレームワークまたは Microsoft アセンブリの型にバインドする場合は、 **[Microsoft または System で始まるアセンブリを表示しない]** チェックボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="9ed0a-117">If you want to bind to a type in a framework or Microsoft assembly, clear the **Hide assemblies that begin with Microsoft or System** check box.</span></span>

7. <span data-ttu-id="9ed0a-118">**[次へ]** をクリックし、 **[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9ed0a-118">Click **Next**, and then click **Finish**.</span></span>

### <a name="to-bind-the-control-to-the-bindingsource"></a><span data-ttu-id="9ed0a-119">コントロールを BindingSource にバインドするには</span><span class="sxs-lookup"><span data-stu-id="9ed0a-119">To bind the control to the BindingSource</span></span>

1. <span data-ttu-id="9ed0a-120">フォームに <xref:System.Windows.Forms.TextBox> を追加します。</span><span class="sxs-lookup"><span data-stu-id="9ed0a-120">Add a <xref:System.Windows.Forms.TextBox> to the form.</span></span>

2. <span data-ttu-id="9ed0a-121">**[プロパティ]** ウィンドウで **(DataBindings)** ノードを展開します。</span><span class="sxs-lookup"><span data-stu-id="9ed0a-121">In the **Properties** window, expand the **(DataBindings)** node.</span></span>

3. <span data-ttu-id="9ed0a-122"><xref:System.Windows.Forms.TextBox.Text%2A> プロパティの横にある矢印をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9ed0a-122">Click the arrow next to the <xref:System.Windows.Forms.TextBox.Text%2A> property.</span></span>

4. <span data-ttu-id="9ed0a-123">**DATASOURCE UI 型エディター**で、前に追加した <xref:System.Windows.Forms.BindingSource> のノードを展開し、<xref:System.Windows.Forms.TextBox>の <xref:System.Windows.Forms.TextBox.Text%2A> プロパティにバインドするバインドされた型のプロパティを選択します。</span><span class="sxs-lookup"><span data-stu-id="9ed0a-123">In the **DataSource UI Type Editor**, expand the node for the <xref:System.Windows.Forms.BindingSource> added previously, and select the property of the bound type you want to bind to the <xref:System.Windows.Forms.TextBox.Text%2A> property of the <xref:System.Windows.Forms.TextBox>.</span></span>

## <a name="see-also"></a><span data-ttu-id="9ed0a-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="9ed0a-124">See also</span></span>

- [<span data-ttu-id="9ed0a-125">BindingSource コンポーネント</span><span class="sxs-lookup"><span data-stu-id="9ed0a-125">BindingSource Component</span></span>](bindingsource-component.md)
- [<span data-ttu-id="9ed0a-126">方法 : Windows フォーム コントロールを型にバインドする</span><span class="sxs-lookup"><span data-stu-id="9ed0a-126">How to: Bind a Windows Forms Control to a Type</span></span>](how-to-bind-a-windows-forms-control-to-a-type.md)
- [<span data-ttu-id="9ed0a-127">Visual Studio でのデータへのコントロールのバインド</span><span class="sxs-lookup"><span data-stu-id="9ed0a-127">Bind controls to data in Visual Studio</span></span>](/visualstudio/data-tools/bind-controls-to-data-in-visual-studio)
