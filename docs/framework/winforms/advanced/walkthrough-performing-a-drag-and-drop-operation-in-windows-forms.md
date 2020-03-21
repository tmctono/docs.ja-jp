---
title: 'チュートリアル: ドラッグ アンド ドロップ操作を実行する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Forms, drag and drop operations
- drag and drop [Windows Forms], Windows Forms
ms.assetid: eb66f6bf-4a7d-4c2d-b276-40fefb2d3b6c
ms.openlocfilehash: b5e4bf753733cb9bd010672f40e8fbeb0cf036bf
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182444"
---
# <a name="walkthrough-performing-a-drag-and-drop-operation-in-windows-forms"></a><span data-ttu-id="c0de9-102">チュートリアル: Windows フォームにおけるドラッグ アンド ドロップ操作の実行</span><span class="sxs-lookup"><span data-stu-id="c0de9-102">Walkthrough: Performing a Drag-and-Drop Operation in Windows Forms</span></span>
<span data-ttu-id="c0de9-103">Windows ベースのアプリケーション内でドラッグ アンド ドロップ操作を実行するには、一連のイベント 、特に<xref:System.Windows.Forms.Control.DragEnter> <xref:System.Windows.Forms.Control.DragLeave>、、、、、および<xref:System.Windows.Forms.Control.DragDrop>イベントを処理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c0de9-103">To perform drag-and-drop operations within Windows-based applications you must handle a series of events, most notably the <xref:System.Windows.Forms.Control.DragEnter>, <xref:System.Windows.Forms.Control.DragLeave>, and <xref:System.Windows.Forms.Control.DragDrop> events.</span></span> <span data-ttu-id="c0de9-104">これらのイベントのイベント引数で使用できる情報を操作することで、ドラッグ アンド ドロップ操作を簡単に行うことができます。</span><span class="sxs-lookup"><span data-stu-id="c0de9-104">By working with the information available in the event arguments of these events, you can easily facilitate drag-and-drop operations.</span></span>  
  
## <a name="dragging-data"></a><span data-ttu-id="c0de9-105">データのドラッグ</span><span class="sxs-lookup"><span data-stu-id="c0de9-105">Dragging Data</span></span>  
 <span data-ttu-id="c0de9-106">ドラッグ アンド ドロップ操作はすべてドラッグから始まります。</span><span class="sxs-lookup"><span data-stu-id="c0de9-106">All drag-and-drop operations begin with dragging.</span></span> <span data-ttu-id="c0de9-107">ドラッグの開始時にデータを収集できるようにする機能が<xref:System.Windows.Forms.Control.DoDragDrop%2A>メソッドに実装されています。</span><span class="sxs-lookup"><span data-stu-id="c0de9-107">The functionality to enable data to be collected when dragging begins is implemented in the <xref:System.Windows.Forms.Control.DoDragDrop%2A> method.</span></span>  
  
 <span data-ttu-id="c0de9-108">次の例では、<xref:System.Windows.Forms.Control.MouseDown>最も直感的な操作であるため、このイベントを使用してドラッグ操作を開始しています (ドラッグ アンド ドロップ操作の大部分は、マウス ボタンが押し込まれている状態で始まります)。</span><span class="sxs-lookup"><span data-stu-id="c0de9-108">In the following example, the <xref:System.Windows.Forms.Control.MouseDown> event is used to start the drag operation because it is the most intuitive (most drag-and-drop actions begin with the mouse button being depressed).</span></span> <span data-ttu-id="c0de9-109">ただし、ドラッグ アンド ドロップ プロシージャを開始するために、どのイベントも使用できることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="c0de9-109">However, remember that any event could be used to initiate a drag-and-drop procedure.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c0de9-110">特定のコントロールには、カスタムドラッグ固有のイベントがあります。</span><span class="sxs-lookup"><span data-stu-id="c0de9-110">Certain controls have custom drag-specific events.</span></span> <span data-ttu-id="c0de9-111">コントロール<xref:System.Windows.Forms.ListView>と<xref:System.Windows.Forms.TreeView>コントロールには、たとえば、イベント<xref:System.Windows.Forms.TreeView.ItemDrag>があります。</span><span class="sxs-lookup"><span data-stu-id="c0de9-111">The <xref:System.Windows.Forms.ListView> and <xref:System.Windows.Forms.TreeView> controls, for example, have an <xref:System.Windows.Forms.TreeView.ItemDrag> event.</span></span>  
  
#### <a name="to-start-a-drag-operation"></a><span data-ttu-id="c0de9-112">ドラッグ操作を開始するには</span><span class="sxs-lookup"><span data-stu-id="c0de9-112">To start a drag operation</span></span>  
  
1. <span data-ttu-id="c0de9-113">ドラッグを<xref:System.Windows.Forms.Control.MouseDown>開始するコントロールのイベントでは、`DoDragDrop`ドラッグするデータを設定するメソッドを使用し、ドラッグできる効果をドラッグできます。</span><span class="sxs-lookup"><span data-stu-id="c0de9-113">In the <xref:System.Windows.Forms.Control.MouseDown> event for the control where the drag will begin, use the `DoDragDrop` method to set the data to be dragged and the allowed effect dragging will have.</span></span> <span data-ttu-id="c0de9-114">詳細については、「 <xref:System.Windows.Forms.DragEventArgs.Data%2A> および <xref:System.Windows.Forms.DragEventArgs.AllowedEffect%2A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c0de9-114">For more information, see <xref:System.Windows.Forms.DragEventArgs.Data%2A> and <xref:System.Windows.Forms.DragEventArgs.AllowedEffect%2A>.</span></span>  
  
     <span data-ttu-id="c0de9-115">次の例は、ドラッグ操作を開始する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="c0de9-115">The following example shows how to initiate a drag operation.</span></span> <span data-ttu-id="c0de9-116">ドラッグを開始するコントロールは<xref:System.Windows.Forms.Button>コントロール、ドラッグされるデータは<xref:System.Windows.Forms.Control.Text%2A><xref:System.Windows.Forms.Button>コントロールのプロパティを表す文字列、許可された効果はコピーまたは移動のいずれかになります。</span><span class="sxs-lookup"><span data-stu-id="c0de9-116">The control where the drag begins is a <xref:System.Windows.Forms.Button> control, the data being dragged is the string representing the <xref:System.Windows.Forms.Control.Text%2A> property of the <xref:System.Windows.Forms.Button> control, and the allowed effects are either copying or moving.</span></span>  
  
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
    > <span data-ttu-id="c0de9-117">メソッドでは、任意の`DoDragDrop`データをパラメーターとして使用できます。上の例では、<xref:System.Windows.Forms.Control.Text%2A><xref:System.Windows.Forms.Button>コントロールのプロパティが (値をハードコーディングしたり、データセットからデータを取得したりするのではなく) 使用しました。 <xref:System.Windows.Forms.Button></span><span class="sxs-lookup"><span data-stu-id="c0de9-117">Any data can be used as a parameter in the `DoDragDrop` method; in the example above, the <xref:System.Windows.Forms.Control.Text%2A> property of the <xref:System.Windows.Forms.Button> control was used (rather than hard-coding a value or retrieving data from a dataset) because the property was related to the location being dragged from (the <xref:System.Windows.Forms.Button> control).</span></span> <span data-ttu-id="c0de9-118">Windows ベースのアプリケーションにドラッグ アンド ドロップ操作を組み込む際には、この点に留意してください。</span><span class="sxs-lookup"><span data-stu-id="c0de9-118">Keep this in mind as you incorporate drag-and-drop operations into your Windows-based applications.</span></span>  
  
 <span data-ttu-id="c0de9-119">ドラッグ操作が有効な場合、ドラッグ操作を<xref:System.Windows.Forms.Control.QueryContinueDrag>続行するためにシステムの「許可を要求する」イベントを処理できます。</span><span class="sxs-lookup"><span data-stu-id="c0de9-119">While a drag operation is in effect, you can handle the <xref:System.Windows.Forms.Control.QueryContinueDrag> event, which "asks permission" of the system to continue the drag operation.</span></span> <span data-ttu-id="c0de9-120">このメソッドを処理する場合は、ドラッグ操作<xref:System.Windows.Forms.TreeNode><xref:System.Windows.Forms.TreeView>に影響を与えるメソッドを呼び出すのも適切なポイントです。</span><span class="sxs-lookup"><span data-stu-id="c0de9-120">When handling this method, it is also the appropriate point for you to call methods that will have an effect on the drag operation, such as expanding a <xref:System.Windows.Forms.TreeNode> in a <xref:System.Windows.Forms.TreeView> control when the cursor hovers over it.</span></span>  
  
## <a name="dropping-data"></a><span data-ttu-id="c0de9-121">データの削除</span><span class="sxs-lookup"><span data-stu-id="c0de9-121">Dropping Data</span></span>  
 <span data-ttu-id="c0de9-122">Windows フォームまたはコントロール上の場所からデータをドラッグし始めたら、自然な場所にドロップします。</span><span class="sxs-lookup"><span data-stu-id="c0de9-122">Once you have begun dragging data from a location on a Windows Form or control, you will naturally want to drop it somewhere.</span></span> <span data-ttu-id="c0de9-123">データをドロップするように正しく構成されているフォームまたはコントロールの領域を横切ると、カーソルは変化します。</span><span class="sxs-lookup"><span data-stu-id="c0de9-123">The cursor will change when it crosses an area of a form or control that is correctly configured for dropping data.</span></span> <span data-ttu-id="c0de9-124">Windows フォームまたはコントロール内の任意の領域は、プロパティを設定し<xref:System.Windows.Forms.Control.AllowDrop%2A><xref:System.Windows.Forms.Control.DragEnter>、および<xref:System.Windows.Forms.Control.DragDrop>イベントを処理することによって、ドロップされたデータを受け入れることができます。</span><span class="sxs-lookup"><span data-stu-id="c0de9-124">Any area within a Windows Form or control can be made to accept dropped data by setting the <xref:System.Windows.Forms.Control.AllowDrop%2A> property and handling the <xref:System.Windows.Forms.Control.DragEnter> and <xref:System.Windows.Forms.Control.DragDrop> events.</span></span>  
  
#### <a name="to-perform-a-drop"></a><span data-ttu-id="c0de9-125">ドロップを実行するには</span><span class="sxs-lookup"><span data-stu-id="c0de9-125">To perform a drop</span></span>  
  
1. <span data-ttu-id="c0de9-126">プロパティを<xref:System.Windows.Forms.Control.AllowDrop%2A>true に設定します。</span><span class="sxs-lookup"><span data-stu-id="c0de9-126">Set the <xref:System.Windows.Forms.Control.AllowDrop%2A> property to true.</span></span>  
  
2. <span data-ttu-id="c0de9-127">ドロップが`DragEnter`発生するコントロールのイベントで、ドラッグされるデータが許容可能な型 (この場合は<xref:System.Windows.Forms.Control.Text%2A>) であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="c0de9-127">In the `DragEnter` event for the control where the drop will occur, ensure that the data being dragged is of an acceptable type (in this case, <xref:System.Windows.Forms.Control.Text%2A>).</span></span> <span data-ttu-id="c0de9-128">次に、ドロップが発生したときに発生する影響を列挙型の値に設定します<xref:System.Windows.Forms.DragDropEffects>。</span><span class="sxs-lookup"><span data-stu-id="c0de9-128">The code then sets the effect that will happen when the drop occurs to a value in the <xref:System.Windows.Forms.DragDropEffects> enumeration.</span></span> <span data-ttu-id="c0de9-129">詳細については、<xref:System.Windows.Forms.DragEventArgs.Effect%2A> を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c0de9-129">For more information, see <xref:System.Windows.Forms.DragEventArgs.Effect%2A>.</span></span>  
  
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
    > <span data-ttu-id="c0de9-130">独自の<xref:System.Windows.Forms.DataFormats>オブジェクトをメソッドのパラメータとして指定することで、独自の<xref:System.Object>オブジェクトを<xref:System.Windows.Forms.DataObject.SetData%2A>定義できます。</span><span class="sxs-lookup"><span data-stu-id="c0de9-130">You can define your own <xref:System.Windows.Forms.DataFormats> by specifying your own object as the <xref:System.Object> parameter of the <xref:System.Windows.Forms.DataObject.SetData%2A> method.</span></span> <span data-ttu-id="c0de9-131">これを行う際には、指定されたオブジェクトがシリアル化可能であることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="c0de9-131">Be sure, when doing this, that the object specified is serializable.</span></span> <span data-ttu-id="c0de9-132">詳細については、<xref:System.Runtime.Serialization.ISerializable> を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c0de9-132">For more information, see <xref:System.Runtime.Serialization.ISerializable>.</span></span>  
  
3. <span data-ttu-id="c0de9-133">ドロップが<xref:System.Windows.Forms.Control.DragDrop>発生するコントロールのイベントでは、メソッドを<xref:System.Windows.Forms.DataObject.GetData%2A>使用して、ドラッグするデータを取得します。</span><span class="sxs-lookup"><span data-stu-id="c0de9-133">In the <xref:System.Windows.Forms.Control.DragDrop> event for the control where the drop will occur, use the <xref:System.Windows.Forms.DataObject.GetData%2A> method to retrieve the data being dragged.</span></span> <span data-ttu-id="c0de9-134">詳細については、<xref:System.Security.Cryptography.Xml.DataObject.Data%2A> を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c0de9-134">For more information, see <xref:System.Security.Cryptography.Xml.DataObject.Data%2A>.</span></span>  
  
     <span data-ttu-id="c0de9-135">次の例では、<xref:System.Windows.Forms.TextBox>コントロールはドラッグ先のコントロールです (ドロップが発生します)。</span><span class="sxs-lookup"><span data-stu-id="c0de9-135">In the example below, a <xref:System.Windows.Forms.TextBox> control is the control being dragged to (where the drop will occur).</span></span> <span data-ttu-id="c0de9-136">このコードは、<xref:System.Windows.Forms.Control.Text%2A>ドラッグするデータ<xref:System.Windows.Forms.TextBox>と同じコントロールのプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="c0de9-136">The code sets the <xref:System.Windows.Forms.Control.Text%2A> property of the <xref:System.Windows.Forms.TextBox> control equal to the data being dragged.</span></span>  
  
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
    > <span data-ttu-id="c0de9-137">また、<xref:System.Windows.Forms.DragEventArgs.KeyState%2A>ドラッグ アンド ドロップ操作中に押されたキーによっては、特定の効果が発生するようにプロパティを操作することもできます (たとえば、Ctrl キーを押したときにドラッグされたデータをコピーするのが標準です)。</span><span class="sxs-lookup"><span data-stu-id="c0de9-137">Additionally, you can work with the <xref:System.Windows.Forms.DragEventArgs.KeyState%2A> property, so that, depending on keys depressed during the drag-and-drop operation, certain effects occur (for example, it is standard to copy the dragged data when the CTRL key is pressed).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0de9-138">関連項目</span><span class="sxs-lookup"><span data-stu-id="c0de9-138">See also</span></span>

- [<span data-ttu-id="c0de9-139">方法 : クリップボードにデータを追加する</span><span class="sxs-lookup"><span data-stu-id="c0de9-139">How to: Add Data to the Clipboard</span></span>](how-to-add-data-to-the-clipboard.md)
- [<span data-ttu-id="c0de9-140">方法 : クリップボードからデータを取得する</span><span class="sxs-lookup"><span data-stu-id="c0de9-140">How to: Retrieve Data from the Clipboard</span></span>](how-to-retrieve-data-from-the-clipboard.md)
- [<span data-ttu-id="c0de9-141">ドラッグ アンド ドロップ操作とクリップボードのサポート</span><span class="sxs-lookup"><span data-stu-id="c0de9-141">Drag-and-Drop Operations and Clipboard Support</span></span>](drag-and-drop-operations-and-clipboard-support.md)
