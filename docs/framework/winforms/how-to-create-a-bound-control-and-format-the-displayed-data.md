---
title: '方法: バインド コントロールを作成して表示データの書式を設定する'
ms.date: 03/30/2017
helpviewer_keywords:
- data [Windows Forms], formatting
- bound controls [Windows Forms], creating
- bound controls [Windows Forms], formatting data
ms.assetid: d5a56228-899d-41d9-8af8-87b3f4ec2f94
ms.openlocfilehash: b5ad85a9477ca32cd28f246abe4ece3cace43182
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/21/2019
ms.locfileid: "69666781"
---
# <a name="how-to-create-a-bound-control-and-format-the-displayed-data"></a><span data-ttu-id="dfa88-102">方法: バインド コントロールを作成して表示データの書式を設定する</span><span class="sxs-lookup"><span data-stu-id="dfa88-102">How to: Create a Bound Control and Format the Displayed Data</span></span>

<span data-ttu-id="dfa88-103">Windows フォームデータバインディングでは、 **[書式設定と詳細バインド]** ダイアログボックスを使用して、データバインドコントロールに表示されるデータの書式を設定できます。</span><span class="sxs-lookup"><span data-stu-id="dfa88-103">With Windows Forms data binding, you can format the data displayed in a data-bound control by using the **Formatting and Advanced Binding** dialog box.</span></span>

### <a name="to-bind-a-control-and-format-the-displayed-data"></a><span data-ttu-id="dfa88-104">コントロールをバインドして表示データの書式を設定するには</span><span class="sxs-lookup"><span data-stu-id="dfa88-104">To bind a control and format the displayed data</span></span>

1. <span data-ttu-id="dfa88-105">データ ソースに接続します。</span><span class="sxs-lookup"><span data-stu-id="dfa88-105">Connect to a data source.</span></span>

     <span data-ttu-id="dfa88-106">詳細については、「[データソースへの接続](../data/adonet/connecting-to-a-data-source.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dfa88-106">For more information, see [Connecting to a Data Source](../data/adonet/connecting-to-a-data-source.md).</span></span>

2. <span data-ttu-id="dfa88-107">フォームでコントロールを選択し、[プロパティ] ウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="dfa88-107">In the form, select the control, and then open the Properties window.</span></span>

3. <span data-ttu-id="dfa88-108">**[(連結)]** プロパティを展開し、 **[(詳細)]** ボックスで、省略記号ボタン![(Visual Studio のプロパティウィンドウの省略記号ボタン ([...]](./media/how-to-create-a-bound-control-and-format-the-displayed-data/visual-studio-ellipsis-button.png)) をクリックして、**書式設定と詳細設定を表示します。[バインド**] ダイアログボックス。このダイアログボックスには、そのコントロールのプロパティの完全な一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="dfa88-108">Expand the **(DataBindings)** property, and then in the **(Advanced)** box, click the ellipsis button (![The Ellipsis button (...) in the Properties window of Visual Studio.](./media/how-to-create-a-bound-control-and-format-the-displayed-data/visual-studio-ellipsis-button.png)) to display the **Formatting and Advanced Binding** dialog box, which has a complete list of properties for that control.</span></span>

4. <span data-ttu-id="dfa88-109">バインドするプロパティを選択し、 **[バインド]** 矢印をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dfa88-109">Select the property you want to bind, and then click the **Binding** arrow.</span></span>

     <span data-ttu-id="dfa88-110">使用できるデータ ソースの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="dfa88-110">A list of available data sources is displayed.</span></span>

5. <span data-ttu-id="dfa88-111">目的の 1 つのデータ要素が見つかるまで、バインド先のデータ ソースを展開します。</span><span class="sxs-lookup"><span data-stu-id="dfa88-111">Expand the data source you want to bind to until you find the single data element you want.</span></span>

     <span data-ttu-id="dfa88-112">たとえば、データセットのテーブル内の列の値にバインドする場合は、データセットの名前を展開し、次にテーブル名を展開して、列名を表示します。</span><span class="sxs-lookup"><span data-stu-id="dfa88-112">For example, if you are binding to a column value in a dataset's table, expand the name of the dataset, and then expand the table name to display column names.</span></span>

6. <span data-ttu-id="dfa88-113">バインド先の要素の名前をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dfa88-113">Click the name of an element to bind to.</span></span>

7. <span data-ttu-id="dfa88-114">**[形式の種類]** ボックスで、コントロールに表示されるデータに適用する形式をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dfa88-114">In the **Format type** box, click the format you want to apply to the data displayed in the control.</span></span>

     <span data-ttu-id="dfa88-115">どの形式でも、データ ソースに <xref:System.DBNull> が含まれている場合には、コントロールに表示する値を指定できます。</span><span class="sxs-lookup"><span data-stu-id="dfa88-115">In every case, you can specify the value displayed in the control if the data source contains <xref:System.DBNull>.</span></span> <span data-ttu-id="dfa88-116">それ以外の場合、オプションは、選択する形式の種類に応じて多少変わります。</span><span class="sxs-lookup"><span data-stu-id="dfa88-116">Otherwise, the options vary slightly, depending on the format type you choose.</span></span> <span data-ttu-id="dfa88-117">次の表に、形式の種類とオプションを示します。</span><span class="sxs-lookup"><span data-stu-id="dfa88-117">The following table shows the format types and options.</span></span>

    |<span data-ttu-id="dfa88-118">形式の種類</span><span class="sxs-lookup"><span data-stu-id="dfa88-118">Format type</span></span>|<span data-ttu-id="dfa88-119">書式設定のオプション</span><span class="sxs-lookup"><span data-stu-id="dfa88-119">Formatting option</span></span>|
    |-----------------|-----------------------|
    |<span data-ttu-id="dfa88-120">書式設定なし</span><span class="sxs-lookup"><span data-stu-id="dfa88-120">No Formatting</span></span>|<span data-ttu-id="dfa88-121">オプションはありません。</span><span class="sxs-lookup"><span data-stu-id="dfa88-121">No options.</span></span>|
    |<span data-ttu-id="dfa88-122">数字</span><span class="sxs-lookup"><span data-stu-id="dfa88-122">Numeric</span></span>|<span data-ttu-id="dfa88-123">小数点**以下**の桁数をアップダウンコントロールで指定します。</span><span class="sxs-lookup"><span data-stu-id="dfa88-123">Specify number of decimal places by using **Decimal places** up-down control.</span></span>|
    |<span data-ttu-id="dfa88-124">通貨</span><span class="sxs-lookup"><span data-stu-id="dfa88-124">Currency</span></span>|<span data-ttu-id="dfa88-125">小数点**以下**の桁数をアップダウンコントロールで指定します。</span><span class="sxs-lookup"><span data-stu-id="dfa88-125">Specify number of decimal places by using **Decimal places** up-down control.</span></span>|
    |<span data-ttu-id="dfa88-126">日付と時刻</span><span class="sxs-lookup"><span data-stu-id="dfa88-126">Date Time</span></span>|<span data-ttu-id="dfa88-127">[**種類**の選択] ボックスでいずれかの項目を選択して、日付と時刻を表示する方法を選択します。</span><span class="sxs-lookup"><span data-stu-id="dfa88-127">Select how the date and time should be displayed by selecting one of the items in the **Type** selection box.</span></span>|
    |<span data-ttu-id="dfa88-128">指数</span><span class="sxs-lookup"><span data-stu-id="dfa88-128">Scientific</span></span>|<span data-ttu-id="dfa88-129">小数点**以下**の桁数をアップダウンコントロールで指定します。</span><span class="sxs-lookup"><span data-stu-id="dfa88-129">Specify number of decimal places by using **Decimal places** up-down control.</span></span>|
    |<span data-ttu-id="dfa88-130">カスタム</span><span class="sxs-lookup"><span data-stu-id="dfa88-130">Custom</span></span>|<span data-ttu-id="dfa88-131">カスタム書式指定文字列を使用するように指定します。</span><span class="sxs-lookup"><span data-stu-id="dfa88-131">Specify a custom format string using.</span></span><br /><br /> <span data-ttu-id="dfa88-132">詳細については、[型の書式設定](../../standard/base-types/formatting-types.md)に関するページをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="dfa88-132">For more information, see [Formatting Types](../../standard/base-types/formatting-types.md).</span></span> <span data-ttu-id="dfa88-133">**注:** カスタム書式指定文字列を使用した場合、データ ソースとバインド コントロールの間を往復したときにデータが正常に維持される保証はありません</span><span class="sxs-lookup"><span data-stu-id="dfa88-133">**Note:**  Custom format strings are not guaranteed to successfully round trip between the data source and bound control.</span></span> <span data-ttu-id="dfa88-134">その代わりに、バインディングで <xref:System.Windows.Forms.Binding.Parse> イベントまたは <xref:System.Windows.Forms.Binding.Format> イベントを処理し、イベント処理コードでカスタム書式を適用します。</span><span class="sxs-lookup"><span data-stu-id="dfa88-134">Instead handle the <xref:System.Windows.Forms.Binding.Parse> or <xref:System.Windows.Forms.Binding.Format> event for the binding and apply custom formatting in the event-handling code.</span></span>|

8. <span data-ttu-id="dfa88-135">**[OK]** をクリックして **[書式設定と詳細バインド]** ダイアログボックスを閉じ、プロパティウィンドウに戻ります。</span><span class="sxs-lookup"><span data-stu-id="dfa88-135">Click **OK** to close the **Formatting and Advanced Binding** dialog box and return to the Properties window.</span></span>

## <a name="see-also"></a><span data-ttu-id="dfa88-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="dfa88-136">See also</span></span>

- [<span data-ttu-id="dfa88-137">方法: Windows フォームに単純バインド コントロールを作成する</span><span class="sxs-lookup"><span data-stu-id="dfa88-137">How to: Create a Simple-Bound Control on a Windows Form</span></span>](how-to-create-a-simple-bound-control-on-a-windows-form.md)
- [<span data-ttu-id="dfa88-138">Windows フォームでのユーザー入力の検証</span><span class="sxs-lookup"><span data-stu-id="dfa88-138">User Input Validation in Windows Forms</span></span>](user-input-validation-in-windows-forms.md)
- [<span data-ttu-id="dfa88-139">Windows フォームでのデータ バインディング</span><span class="sxs-lookup"><span data-stu-id="dfa88-139">Windows Forms Data Binding</span></span>](windows-forms-data-binding.md)
