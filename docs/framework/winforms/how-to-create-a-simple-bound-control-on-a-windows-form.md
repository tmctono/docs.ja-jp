---
title: '方法: Windows フォームに単純バインド コントロールを作成する'
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [Windows Forms], simple data binding
- Windows Forms controls, data binding
ms.assetid: 3bcaded8-0f1a-4cc0-8830-f59be253bf4e
ms.openlocfilehash: ed1d0e423a3cdf77a242ec3214720f1466f65897
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/15/2019
ms.locfileid: "69039505"
---
# <a name="how-to-create-a-simple-bound-control-on-a-windows-form"></a><span data-ttu-id="db70d-102">方法: Windows フォームに単純バインド コントロールを作成する</span><span class="sxs-lookup"><span data-stu-id="db70d-102">How to: Create a Simple-Bound Control on a Windows Form</span></span>

<span data-ttu-id="db70d-103">*単純なバインド*では、データセットテーブルの列値など、1つのデータ要素をコントロールに表示できます。</span><span class="sxs-lookup"><span data-stu-id="db70d-103">With *simple binding*, you can display a single data element, such as a column value from a dataset table, in a control.</span></span> <span data-ttu-id="db70d-104">コントロールの任意のプロパティをデータ値に単純にバインドできます。</span><span class="sxs-lookup"><span data-stu-id="db70d-104">You can simple-bind any property of a control to a data value.</span></span>

### <a name="to-simple-bind-a-control"></a><span data-ttu-id="db70d-105">コントロールを単純にバインドするには</span><span class="sxs-lookup"><span data-stu-id="db70d-105">To simple-bind a control</span></span>

1. <span data-ttu-id="db70d-106">データ ソースに接続します。</span><span class="sxs-lookup"><span data-stu-id="db70d-106">Connect to a data source.</span></span> <span data-ttu-id="db70d-107">詳細については、「[データソースへの接続](../data/adonet/connecting-to-a-data-source.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="db70d-107">For more information, see [Connecting to a Data Source](../data/adonet/connecting-to-a-data-source.md).</span></span>

2. <span data-ttu-id="db70d-108">フォームでコントロールを選択し、 **[プロパティ]** ウィンドウを表示します。</span><span class="sxs-lookup"><span data-stu-id="db70d-108">In the form, select the control and display the **Properties** window.</span></span>

3. <span data-ttu-id="db70d-109">**[(連結)]** プロパティを展開します。</span><span class="sxs-lookup"><span data-stu-id="db70d-109">Expand the **(DataBindings)** property.</span></span>

     <span data-ttu-id="db70d-110">最も頻繁にバインドされるプロパティは、 **([連結])** プロパティの下に表示されます。</span><span class="sxs-lookup"><span data-stu-id="db70d-110">The properties most often bound are displayed underneath the **(DataBindings)** property.</span></span> <span data-ttu-id="db70d-111">たとえば、ほとんどのコントロールでは、 **Text**プロパティは最も頻繁にバインドされます。</span><span class="sxs-lookup"><span data-stu-id="db70d-111">For example, in most controls, the **Text** property is most frequently bound.</span></span>

4. <span data-ttu-id="db70d-112">バインドするプロパティが一般的にバインドされるプロパティの1つでない場合は、 **[(詳細)]** ボックスの**省略記号**ボタン![(省略記号ボタン ([..](./media/how-to-create-a-simple-bound-control-on-a-windows-form/visual-studio-ellipsis-button.png)プロパティウィンドウ.]) をクリックして、 **[書式設定と詳細バインド**] ダイアログボックスで、そのコントロールのプロパティの完全な一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="db70d-112">If the property you want to bind is not one of the commonly bound properties, click the **Ellipsis** button (![The Ellipsis button (...) in the Properties window of Visual Studio.](./media/how-to-create-a-simple-bound-control-on-a-windows-form/visual-studio-ellipsis-button.png)) in the **(Advanced)** box to display the **Formatting and Advanced Binding** dialog box with a complete list of properties for that control.</span></span>

5. <span data-ttu-id="db70d-113">バインドするプロパティを選択し、 **[バインド]** の下にあるドロップダウン矢印をクリックします。</span><span class="sxs-lookup"><span data-stu-id="db70d-113">Select the property you want to bind and click the drop-down arrow under **Binding**.</span></span>

     <span data-ttu-id="db70d-114">使用できるデータ ソースの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="db70d-114">A list of available data sources is displayed.</span></span>

6. <span data-ttu-id="db70d-115">目的の 1 つのデータ要素が見つかるまで、バインド先のデータ ソースを展開します。</span><span class="sxs-lookup"><span data-stu-id="db70d-115">Expand the data source you want to bind to until you find the single data element you want.</span></span> <span data-ttu-id="db70d-116">たとえば、データセットのテーブル内の列の値にバインドする場合は、データセットの名前を展開し、次にテーブル名を展開して、列名を表示します。</span><span class="sxs-lookup"><span data-stu-id="db70d-116">For example, if you are binding to a column value in a dataset's table, expand the name of the dataset, and then expand the table name to display column names.</span></span>

7. <span data-ttu-id="db70d-117">バインド先の要素の名前をクリックします。</span><span class="sxs-lookup"><span data-stu-id="db70d-117">Click the name of an element to bind to.</span></span>

8. <span data-ttu-id="db70d-118">**[書式設定と詳細バインド]** ダイアログボックスで作業している場合は、 **[OK]** をクリックして、 **[プロパティ]** ウィンドウに戻ります。</span><span class="sxs-lookup"><span data-stu-id="db70d-118">If you were working in the **Formatting and Advanced Binding** dialog box, click **OK** to return to the **Properties** window.</span></span>

9. <span data-ttu-id="db70d-119">コントロールの追加のプロパティをバインドする場合は、手順 3. ~ 7. を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="db70d-119">If you want to bind additional properties of the control, repeat steps 3 through 7.</span></span>

    > [!NOTE]
    > <span data-ttu-id="db70d-120">単純バインドコントロールにはデータ要素が1つだけ表示されるため、単純バインドコントロールを含む Windows フォームにナビゲーションロジックを含めるのが一般的です。</span><span class="sxs-lookup"><span data-stu-id="db70d-120">Because simple-bound controls show only a single data element, it is very typical to include navigation logic in a Windows Form with simple-bound controls.</span></span>

## <a name="see-also"></a><span data-ttu-id="db70d-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="db70d-121">See also</span></span>

- <xref:System.Windows.Forms.Binding>
- [<span data-ttu-id="db70d-122">Windows フォームでのデータ バインディング</span><span class="sxs-lookup"><span data-stu-id="db70d-122">Windows Forms Data Binding</span></span>](windows-forms-data-binding.md)
- [<span data-ttu-id="db70d-123">データ連結と Windows フォーム</span><span class="sxs-lookup"><span data-stu-id="db70d-123">Data Binding and Windows Forms</span></span>](data-binding-and-windows-forms.md)
