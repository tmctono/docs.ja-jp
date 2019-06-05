---
title: '方法: Windows フォームに単純バインド コントロールを作成する'
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [Windows Forms], simple data binding
- Windows Forms controls, data binding
ms.assetid: 3bcaded8-0f1a-4cc0-8830-f59be253bf4e
ms.openlocfilehash: 5c92b7bfd5026b0569397dc05cca216fbdab0753
ms.sourcegitcommit: d8ebe0ee198f5d38387a80ba50f395386779334f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/05/2019
ms.locfileid: "66689305"
---
# <a name="how-to-create-a-simple-bound-control-on-a-windows-form"></a><span data-ttu-id="47b28-102">方法: Windows フォームに単純バインド コントロールを作成する</span><span class="sxs-lookup"><span data-stu-id="47b28-102">How to: Create a Simple-Bound Control on a Windows Form</span></span>

<span data-ttu-id="47b28-103">*単純バインディング*コントロールでデータセット テーブルの列の値などの 1 つのデータ要素を表示することができます。</span><span class="sxs-lookup"><span data-stu-id="47b28-103">With *simple binding*, you can display a single data element, such as a column value from a dataset table, in a control.</span></span> <span data-ttu-id="47b28-104">できます単純にバインドするコントロールの任意のプロパティのデータ値にします。</span><span class="sxs-lookup"><span data-stu-id="47b28-104">You can simple-bind any property of a control to a data value.</span></span>

> [!NOTE]
> <span data-ttu-id="47b28-105">実際に画面に表示されるダイアログ ボックスとメニュー コマンドは、アクティブな設定またはエディションによっては、ヘルプの説明と異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="47b28-105">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="47b28-106">設定を変更するには、 **[ツール]** メニューの **[設定のインポートとエクスポート]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="47b28-106">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="47b28-107">詳細については、「[Visual Studio IDE のカスタマイズ](/visualstudio/ide/personalizing-the-visual-studio-ide)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="47b28-107">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>

### <a name="to-simple-bind-a-control"></a><span data-ttu-id="47b28-108">単純なコントロールをバインドする</span><span class="sxs-lookup"><span data-stu-id="47b28-108">To simple-bind a control</span></span>

1. <span data-ttu-id="47b28-109">データ ソースに接続します。</span><span class="sxs-lookup"><span data-stu-id="47b28-109">Connect to a data source.</span></span> <span data-ttu-id="47b28-110">詳細については、次を参照してください。[データ ソースに接続する](../data/adonet/connecting-to-a-data-source.md)します。</span><span class="sxs-lookup"><span data-stu-id="47b28-110">For more information, see [Connecting to a Data Source](../data/adonet/connecting-to-a-data-source.md).</span></span>

2. <span data-ttu-id="47b28-111">フォームのコントロールを選択し、表示、**プロパティ**ウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="47b28-111">In the form, select the control and display the **Properties** window.</span></span>

3. <span data-ttu-id="47b28-112">展開、 **(DataBindings)** プロパティ。</span><span class="sxs-lookup"><span data-stu-id="47b28-112">Expand the **(DataBindings)** property.</span></span>

     <span data-ttu-id="47b28-113">最も頻繁にバインドされるプロパティは、下に表示されます、 **(DataBindings)** プロパティ。</span><span class="sxs-lookup"><span data-stu-id="47b28-113">The properties most often bound are displayed underneath the **(DataBindings)** property.</span></span> <span data-ttu-id="47b28-114">たとえば、ほとんどのコントロールで、**テキスト**プロパティが最も頻繁にバインドされています。</span><span class="sxs-lookup"><span data-stu-id="47b28-114">For example, in most controls, the **Text** property is most frequently bound.</span></span>

4. <span data-ttu-id="47b28-115">たいプロパティのバインドが一般にバインドされるプロパティのいずれかをクリックして、**省略記号**ボタン (![. Visual Studio の [プロパティ] ウィンドウで、省略記号ボタン (…)](./media/how-to-create-a-simple-bound-control-on-a-windows-form/visual-studio-ellipsis-button.png)) で、 **(詳細設定)** ボックスを表示する、**フォーマットと詳細バインド**そのコントロールのプロパティの完全な一覧がダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="47b28-115">If the property you want to bind is not one of the commonly bound properties, click the **Ellipsis** button (![The Ellipsis button (...) in the Properties window of Visual Studio.](./media/how-to-create-a-simple-bound-control-on-a-windows-form/visual-studio-ellipsis-button.png)) in the **(Advanced)** box to display the **Formatting and Advanced Binding** dialog box with a complete list of properties for that control.</span></span>

5. <span data-ttu-id="47b28-116">バインドし、下のドロップダウン矢印をクリックします。 プロパティを選択**バインド**します。</span><span class="sxs-lookup"><span data-stu-id="47b28-116">Select the property you want to bind and click the drop-down arrow under **Binding**.</span></span>

     <span data-ttu-id="47b28-117">使用できるデータ ソースの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="47b28-117">A list of available data sources is displayed.</span></span>

6. <span data-ttu-id="47b28-118">目的の 1 つのデータ要素が見つかるまで、バインド先のデータ ソースを展開します。</span><span class="sxs-lookup"><span data-stu-id="47b28-118">Expand the data source you want to bind to until you find the single data element you want.</span></span> <span data-ttu-id="47b28-119">たとえば、データセットのテーブル内の列の値にバインドする場合は、データセットの名前を展開し、次にテーブル名を展開して、列名を表示します。</span><span class="sxs-lookup"><span data-stu-id="47b28-119">For example, if you are binding to a column value in a dataset's table, expand the name of the dataset, and then expand the table name to display column names.</span></span>

7. <span data-ttu-id="47b28-120">バインド先の要素の名前をクリックします。</span><span class="sxs-lookup"><span data-stu-id="47b28-120">Click the name of an element to bind to.</span></span>

8. <span data-ttu-id="47b28-121">作業している場合、**フォーマットと詳細バインド**ダイアログ ボックスで、をクリックして **[ok]** に戻る、**プロパティ**ウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="47b28-121">If you were working in the **Formatting and Advanced Binding** dialog box, click **OK** to return to the **Properties** window.</span></span>

9. <span data-ttu-id="47b28-122">コントロールの追加のプロパティをバインドする場合は、手順 3. ~ 7. を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="47b28-122">If you want to bind additional properties of the control, repeat steps 3 through 7.</span></span>

    > [!NOTE]
    > <span data-ttu-id="47b28-123">単純バインド コントロールでは、1 つのデータ要素のみを表示するためには、Windows フォームに単純バインド コントロールにナビゲーション ロジックを含める非常に一般的です。</span><span class="sxs-lookup"><span data-stu-id="47b28-123">Because simple-bound controls show only a single data element, it is very typical to include navigation logic in a Windows Form with simple-bound controls.</span></span>

## <a name="see-also"></a><span data-ttu-id="47b28-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="47b28-124">See also</span></span>

- <xref:System.Windows.Forms.Binding>
- [<span data-ttu-id="47b28-125">Windows フォームでのデータ バインディング</span><span class="sxs-lookup"><span data-stu-id="47b28-125">Windows Forms Data Binding</span></span>](windows-forms-data-binding.md)
- [<span data-ttu-id="47b28-126">データ連結と Windows フォーム</span><span class="sxs-lookup"><span data-stu-id="47b28-126">Data Binding and Windows Forms</span></span>](data-binding-and-windows-forms.md)
