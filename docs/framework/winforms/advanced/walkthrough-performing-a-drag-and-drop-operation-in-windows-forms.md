---
title: 'チュートリアル: ドラッグアンドドロップ操作の実行'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Forms, drag and drop operations
- drag and drop [Windows Forms], Windows Forms
ms.assetid: eb66f6bf-4a7d-4c2d-b276-40fefb2d3b6c
ms.openlocfilehash: 265e6d4f9e3370d28a18b86dea983bb0b556be41
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746792"
---
# <a name="walkthrough-performing-a-drag-and-drop-operation-in-windows-forms"></a><span data-ttu-id="67143-102">チュートリアル: Windows フォームにおけるドラッグ アンド ドロップ操作の実行</span><span class="sxs-lookup"><span data-stu-id="67143-102">Walkthrough: Performing a Drag-and-Drop Operation in Windows Forms</span></span>
<span data-ttu-id="67143-103">Windows ベースのアプリケーション内でドラッグアンドドロップ操作を実行するには、一連のイベント (特に、<xref:System.Windows.Forms.Control.DragEnter>、<xref:System.Windows.Forms.Control.DragLeave>、および <xref:System.Windows.Forms.Control.DragDrop> イベント) を処理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="67143-103">To perform drag-and-drop operations within Windows-based applications you must handle a series of events, most notably the <xref:System.Windows.Forms.Control.DragEnter>, <xref:System.Windows.Forms.Control.DragLeave>, and <xref:System.Windows.Forms.Control.DragDrop> events.</span></span> <span data-ttu-id="67143-104">これらのイベントのイベント引数で使用できる情報を操作することにより、ドラッグアンドドロップ操作を容易に行うことができます。</span><span class="sxs-lookup"><span data-stu-id="67143-104">By working with the information available in the event arguments of these events, you can easily facilitate drag-and-drop operations.</span></span>  
  
## <a name="dragging-data"></a><span data-ttu-id="67143-105">データのドラッグ</span><span class="sxs-lookup"><span data-stu-id="67143-105">Dragging Data</span></span>  
 <span data-ttu-id="67143-106">ドラッグアンドドロップ操作はすべて、ドラッグで開始されます。</span><span class="sxs-lookup"><span data-stu-id="67143-106">All drag-and-drop operations begin with dragging.</span></span> <span data-ttu-id="67143-107">ドラッグの開始時に収集されるデータを有効にする機能は、<xref:System.Windows.Forms.Control.DoDragDrop%2A> メソッドに実装されます。</span><span class="sxs-lookup"><span data-stu-id="67143-107">The functionality to enable data to be collected when dragging begins is implemented in the <xref:System.Windows.Forms.Control.DoDragDrop%2A> method.</span></span>  
  
 <span data-ttu-id="67143-108">次の例では、<xref:System.Windows.Forms.Control.MouseDown> イベントを使用してドラッグ操作を開始しています。これは最も直観的です (ドラッグアンドドロップ操作のほとんどは、押されているマウスボタンで開始されます)。</span><span class="sxs-lookup"><span data-stu-id="67143-108">In the following example, the <xref:System.Windows.Forms.Control.MouseDown> event is used to start the drag operation because it is the most intuitive (most drag-and-drop actions begin with the mouse button being depressed).</span></span> <span data-ttu-id="67143-109">ただし、すべてのイベントを使用してドラッグアンドドロッププロシージャを開始できることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="67143-109">However, remember that any event could be used to initiate a drag-and-drop procedure.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="67143-110">特定のコントロールには、ドラッグ固有のカスタムイベントがあります。</span><span class="sxs-lookup"><span data-stu-id="67143-110">Certain controls have custom drag-specific events.</span></span> <span data-ttu-id="67143-111">たとえば、<xref:System.Windows.Forms.ListView> コントロールと <xref:System.Windows.Forms.TreeView> コントロールには、<xref:System.Windows.Forms.TreeView.ItemDrag> イベントがあります。</span><span class="sxs-lookup"><span data-stu-id="67143-111">The <xref:System.Windows.Forms.ListView> and <xref:System.Windows.Forms.TreeView> controls, for example, have an <xref:System.Windows.Forms.TreeView.ItemDrag> event.</span></span>  
  
#### <a name="to-start-a-drag-operation"></a><span data-ttu-id="67143-112">ドラッグ操作を開始するには</span><span class="sxs-lookup"><span data-stu-id="67143-112">To start a drag operation</span></span>  
  
1. <span data-ttu-id="67143-113">ドラッグが開始されるコントロールの <xref:System.Windows.Forms.Control.MouseDown> イベントで、`DoDragDrop` メソッドを使用して、ドラッグするデータを設定します。ドラッグすると、許可される効果はになります。</span><span class="sxs-lookup"><span data-stu-id="67143-113">In the <xref:System.Windows.Forms.Control.MouseDown> event for the control where the drag will begin, use the `DoDragDrop` method to set the data to be dragged and the allowed effect dragging will have.</span></span> <span data-ttu-id="67143-114">詳細については、「<xref:System.Windows.Forms.DragEventArgs.Data%2A>」および「<xref:System.Windows.Forms.DragEventArgs.AllowedEffect%2A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="67143-114">For more information, see <xref:System.Windows.Forms.DragEventArgs.Data%2A> and <xref:System.Windows.Forms.DragEventArgs.AllowedEffect%2A>.</span></span>  
  
     <span data-ttu-id="67143-115">次の例は、ドラッグ操作を開始する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="67143-115">The following example shows how to initiate a drag operation.</span></span> <span data-ttu-id="67143-116">ドラッグが開始するコントロールは <xref:System.Windows.Forms.Button> コントロールで、ドラッグされるデータは <xref:System.Windows.Forms.Button> コントロールの <xref:System.Windows.Forms.Control.Text%2A> プロパティを表す文字列です。また、許可される効果はコピーまたは移動します。</span><span class="sxs-lookup"><span data-stu-id="67143-116">The control where the drag begins is a <xref:System.Windows.Forms.Button> control, the data being dragged is the string representing the <xref:System.Windows.Forms.Control.Text%2A> property of the <xref:System.Windows.Forms.Button> control, and the allowed effects are either copying or moving.</span></span>  
  
    ```vb  
    Private Sub Button1_MouseDown(ByVal sender As Object, ByVal e As System.Windows.Forms.MouseEventArgs) Handles Button1.MouseDown  
       Button1.DoDragDrop(Button1.Text, DragDropEffects.Copy Or DragDropEffects.Move)  
    End Sub  
    ```  
  
    ```csharp  
    private void button1_MouseDown(object sender,   
    System.Windows.Forms.MouseEventArgs e)  
    {  
       button1.DoDragDrop(button1.Text, DragDropEffects.Copy |   
          DragDropEffects.Move);  
    }  
    ```  
  
    > [!NOTE]
    > <span data-ttu-id="67143-117">`DoDragDrop` メソッドでは、任意のデータをパラメーターとして使用できます。上の例では、プロパティがドラッグ元 (<xref:System.Windows.Forms.Button> コントロール) に関連付けられていたため、<xref:System.Windows.Forms.Button> コントロールの <xref:System.Windows.Forms.Control.Text%2A> プロパティが使用されていました (値をハードコーディングしたり、データセットからデータを取得したりするのではありません)。</span><span class="sxs-lookup"><span data-stu-id="67143-117">Any data can be used as a parameter in the `DoDragDrop` method; in the example above, the <xref:System.Windows.Forms.Control.Text%2A> property of the <xref:System.Windows.Forms.Button> control was used (rather than hard-coding a value or retrieving data from a dataset) because the property was related to the location being dragged from (the <xref:System.Windows.Forms.Button> control).</span></span> <span data-ttu-id="67143-118">ドラッグアンドドロップ操作を Windows ベースのアプリケーションに組み込むときは、この点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="67143-118">Keep this in mind as you incorporate drag-and-drop operations into your Windows-based applications.</span></span>  
  
 <span data-ttu-id="67143-119">ドラッグ操作が有効になっている間に、ドラッグ操作を続行するためにシステムの "アクセス許可" を要求する <xref:System.Windows.Forms.Control.QueryContinueDrag> イベントを処理できます。</span><span class="sxs-lookup"><span data-stu-id="67143-119">While a drag operation is in effect, you can handle the <xref:System.Windows.Forms.Control.QueryContinueDrag> event, which "asks permission" of the system to continue the drag operation.</span></span> <span data-ttu-id="67143-120">このメソッドを処理する場合は、ドラッグ操作に影響を与えるメソッドを呼び出すこともできます。たとえば、カーソルがカーソルを置いたときに <xref:System.Windows.Forms.TreeView> コントロールの <xref:System.Windows.Forms.TreeNode> を展開する場合などです。</span><span class="sxs-lookup"><span data-stu-id="67143-120">When handling this method, it is also the appropriate point for you to call methods that will have an effect on the drag operation, such as expanding a <xref:System.Windows.Forms.TreeNode> in a <xref:System.Windows.Forms.TreeView> control when the cursor hovers over it.</span></span>  
  
## <a name="dropping-data"></a><span data-ttu-id="67143-121">データの削除</span><span class="sxs-lookup"><span data-stu-id="67143-121">Dropping Data</span></span>  
 <span data-ttu-id="67143-122">Windows フォームまたはコントロール上の場所からデータのドラッグを開始した後は、どこかにデータをドロップすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="67143-122">Once you have begun dragging data from a location on a Windows Form or control, you will naturally want to drop it somewhere.</span></span> <span data-ttu-id="67143-123">カーソルは、データの削除用に正しく構成されているフォームまたはコントロールの領域と交差すると変更されます。</span><span class="sxs-lookup"><span data-stu-id="67143-123">The cursor will change when it crosses an area of a form or control that is correctly configured for dropping data.</span></span> <span data-ttu-id="67143-124">Windows フォームまたはコントロール内の領域は、<xref:System.Windows.Forms.Control.AllowDrop%2A> プロパティを設定し、<xref:System.Windows.Forms.Control.DragEnter> イベントと <xref:System.Windows.Forms.Control.DragDrop> イベントを処理することによって、削除されたデータを受け入れることができます。</span><span class="sxs-lookup"><span data-stu-id="67143-124">Any area within a Windows Form or control can be made to accept dropped data by setting the <xref:System.Windows.Forms.Control.AllowDrop%2A> property and handling the <xref:System.Windows.Forms.Control.DragEnter> and <xref:System.Windows.Forms.Control.DragDrop> events.</span></span>  
  
#### <a name="to-perform-a-drop"></a><span data-ttu-id="67143-125">削除を実行するには</span><span class="sxs-lookup"><span data-stu-id="67143-125">To perform a drop</span></span>  
  
1. <span data-ttu-id="67143-126"><xref:System.Windows.Forms.Control.AllowDrop%2A> プロパティを true に設定します。</span><span class="sxs-lookup"><span data-stu-id="67143-126">Set the <xref:System.Windows.Forms.Control.AllowDrop%2A> property to true.</span></span>  
  
2. <span data-ttu-id="67143-127">ドロップが発生するコントロールの `DragEnter` イベントで、ドラッグされるデータが許容される型 (この場合は <xref:System.Windows.Forms.Control.Text%2A>) であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="67143-127">In the `DragEnter` event for the control where the drop will occur, ensure that the data being dragged is of an acceptable type (in this case, <xref:System.Windows.Forms.Control.Text%2A>).</span></span> <span data-ttu-id="67143-128">次に、このコードでは、<xref:System.Windows.Forms.DragDropEffects> 列挙体の値にドロップすると発生する効果を設定します。</span><span class="sxs-lookup"><span data-stu-id="67143-128">The code then sets the effect that will happen when the drop occurs to a value in the <xref:System.Windows.Forms.DragDropEffects> enumeration.</span></span> <span data-ttu-id="67143-129">詳細については、「 <xref:System.Windows.Forms.DragEventArgs.Effect%2A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="67143-129">For more information, see <xref:System.Windows.Forms.DragEventArgs.Effect%2A>.</span></span>  
  
    ```vb  
    Private Sub TextBox1_DragEnter(ByVal sender As Object, ByVal e As System.Windows.Forms.DragEventArgs) Handles TextBox1.DragEnter  
       If (e.Data.GetDataPresent(DataFormats.Text)) Then  
         e.Effect = DragDropEffects.Copy  
       Else  
         e.Effect = DragDropEffects.None  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    private void textBox1_DragEnter(object sender,   
    System.Windows.Forms.DragEventArgs e)  
    {  
       if (e.Data.GetDataPresent(DataFormats.Text))   
          e.Effect = DragDropEffects.Copy;  
       else  
          e.Effect = DragDropEffects.None;  
    }  
    ```  
  
    > [!NOTE]
    > <span data-ttu-id="67143-130">独自のオブジェクトを <xref:System.Windows.Forms.DataObject.SetData%2A> メソッドの <xref:System.Object> パラメーターとして指定することで、独自の <xref:System.Windows.Forms.DataFormats> を定義できます。</span><span class="sxs-lookup"><span data-stu-id="67143-130">You can define your own <xref:System.Windows.Forms.DataFormats> by specifying your own object as the <xref:System.Object> parameter of the <xref:System.Windows.Forms.DataObject.SetData%2A> method.</span></span> <span data-ttu-id="67143-131">これを行うときは、指定されたオブジェクトがシリアル化可能であることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="67143-131">Be sure, when doing this, that the object specified is serializable.</span></span> <span data-ttu-id="67143-132">詳細については、「 <xref:System.Runtime.Serialization.ISerializable>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="67143-132">For more information, see <xref:System.Runtime.Serialization.ISerializable>.</span></span>  
  
3. <span data-ttu-id="67143-133">ドロップが発生するコントロールの <xref:System.Windows.Forms.Control.DragDrop> イベントで、<xref:System.Windows.Forms.DataObject.GetData%2A> メソッドを使用して、ドラッグされているデータを取得します。</span><span class="sxs-lookup"><span data-stu-id="67143-133">In the <xref:System.Windows.Forms.Control.DragDrop> event for the control where the drop will occur, use the <xref:System.Windows.Forms.DataObject.GetData%2A> method to retrieve the data being dragged.</span></span> <span data-ttu-id="67143-134">詳細については、「 <xref:System.Security.Cryptography.Xml.DataObject.Data%2A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="67143-134">For more information, see <xref:System.Security.Cryptography.Xml.DataObject.Data%2A>.</span></span>  
  
     <span data-ttu-id="67143-135">次の例では、<xref:System.Windows.Forms.TextBox> コントロールがドラッグされているコントロールです (ドロップが発生します)。</span><span class="sxs-lookup"><span data-stu-id="67143-135">In the example below, a <xref:System.Windows.Forms.TextBox> control is the control being dragged to (where the drop will occur).</span></span> <span data-ttu-id="67143-136">このコードは、ドラッグされているデータと同じ <xref:System.Windows.Forms.TextBox> コントロールの <xref:System.Windows.Forms.Control.Text%2A> プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="67143-136">The code sets the <xref:System.Windows.Forms.Control.Text%2A> property of the <xref:System.Windows.Forms.TextBox> control equal to the data being dragged.</span></span>  
  
    ```vb  
    Private Sub TextBox1_DragDrop(ByVal sender As Object, ByVal e As System.Windows.Forms.DragEventArgs) Handles TextBox1.DragDrop  
       TextBox1.Text = e.Data.GetData(DataFormats.Text).ToString  
    End Sub  
    ```  
  
    ```csharp  
    private void textBox1_DragDrop(object sender,   
    System.Windows.Forms.DragEventArgs e)  
    {  
       textBox1.Text = e.Data.GetData(DataFormats.Text).ToString();  
    }  
    ```  
  
    > [!NOTE]
    > <span data-ttu-id="67143-137">また、<xref:System.Windows.Forms.DragEventArgs.KeyState%2A> プロパティを操作することもできます。これにより、ドラッグアンドドロップ操作中に押されたキーに応じて、特定の効果が発生します (たとえば、CTRL キーが押されたときにドラッグしたデータをコピーするのは標準です)。</span><span class="sxs-lookup"><span data-stu-id="67143-137">Additionally, you can work with the <xref:System.Windows.Forms.DragEventArgs.KeyState%2A> property, so that, depending on keys depressed during the drag-and-drop operation, certain effects occur (for example, it is standard to copy the dragged data when the CTRL key is pressed).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67143-138">関連項目</span><span class="sxs-lookup"><span data-stu-id="67143-138">See also</span></span>

- [<span data-ttu-id="67143-139">方法: クリップボードにデータを追加する</span><span class="sxs-lookup"><span data-stu-id="67143-139">How to: Add Data to the Clipboard</span></span>](how-to-add-data-to-the-clipboard.md)
- [<span data-ttu-id="67143-140">方法: クリップボードからデータを取得する</span><span class="sxs-lookup"><span data-stu-id="67143-140">How to: Retrieve Data from the Clipboard</span></span>](how-to-retrieve-data-from-the-clipboard.md)
- [<span data-ttu-id="67143-141">ドラッグ アンド ドロップ操作とクリップボードのサポート</span><span class="sxs-lookup"><span data-stu-id="67143-141">Drag-and-Drop Operations and Clipboard Support</span></span>](drag-and-drop-operations-and-clipboard-support.md)
