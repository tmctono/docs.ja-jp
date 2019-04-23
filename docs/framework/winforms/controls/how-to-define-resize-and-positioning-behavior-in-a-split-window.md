---
title: '方法: 分割ウィンドウでのサイズ変更および位置指定動作を定義する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- split windows [Windows Forms], resizing
- splitter windows [Windows Forms], resizing
- SplitContainer control [Windows Forms], resizing
ms.assetid: 9bf73f36-ed2d-4a02-b15a-0770eff4fdfa
ms.openlocfilehash: 8cdcfdfaa135a92ed6a6e96d4a72de2c97f2493d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59328674"
---
# <a name="how-to-define-resize-and-positioning-behavior-in-a-split-window"></a><span data-ttu-id="9a9dc-102">方法: 分割ウィンドウでのサイズ変更および位置指定動作を定義する</span><span class="sxs-lookup"><span data-stu-id="9a9dc-102">How to: Define Resize and Positioning Behavior in a Split Window</span></span>
<span data-ttu-id="9a9dc-103">パネル、<xref:System.Windows.Forms.SplitContainer>コントロールを起こすもされているサイズを変更して、ユーザーによって操作します。</span><span class="sxs-lookup"><span data-stu-id="9a9dc-103">The panels of the <xref:System.Windows.Forms.SplitContainer> control lend themselves well to being resized and manipulated by users.</span></span> <span data-ttu-id="9a9dc-104">ただし、するは、スプリッターをプログラムで制御する場合は、場所が配置されているし、移動できるどの程度までです。</span><span class="sxs-lookup"><span data-stu-id="9a9dc-104">However, there will be times when you will want to programmatically control the splitter—where it is positioned and to what degree it can be moved.</span></span>  
  
 <span data-ttu-id="9a9dc-105"><xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A>プロパティおよびその他のプロパティを<xref:System.Windows.Forms.SplitContainer>コントロールは、ニーズに合わせてユーザー インターフェイスの動作をより正確に制御を提供します。</span><span class="sxs-lookup"><span data-stu-id="9a9dc-105">The <xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A> property and the other properties on the <xref:System.Windows.Forms.SplitContainer> control give you precise control over the behavior of your user interface to suit your needs.</span></span> <span data-ttu-id="9a9dc-106">これらのプロパティは、次の表に一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="9a9dc-106">These properties are listed in the following table.</span></span>  
  
|<span data-ttu-id="9a9dc-107">名前</span><span class="sxs-lookup"><span data-stu-id="9a9dc-107">Name</span></span>|<span data-ttu-id="9a9dc-108">説明</span><span class="sxs-lookup"><span data-stu-id="9a9dc-108">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="9a9dc-109"><xref:System.Windows.Forms.SplitContainer.IsSplitterFixed%2A> プロパティ</span><span class="sxs-lookup"><span data-stu-id="9a9dc-109"><xref:System.Windows.Forms.SplitContainer.IsSplitterFixed%2A> property</span></span>|<span data-ttu-id="9a9dc-110">分割線をキーボードやマウスを使用して移動可能なかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="9a9dc-110">Determines if the splitter is movable by means of the keyboard or mouse.</span></span>|  
|<span data-ttu-id="9a9dc-111"><xref:System.Windows.Forms.SplitContainer.SplitterDistance%2A> プロパティ</span><span class="sxs-lookup"><span data-stu-id="9a9dc-111"><xref:System.Windows.Forms.SplitContainer.SplitterDistance%2A> property</span></span>|<span data-ttu-id="9a9dc-112">移動可能な分割バーを左端または上端からのピクセル単位で距離を決定します。</span><span class="sxs-lookup"><span data-stu-id="9a9dc-112">Determines the distance in pixels from the left or upper edge to the movable splitter bar.</span></span>|  
|<span data-ttu-id="9a9dc-113"><xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A> プロパティ</span><span class="sxs-lookup"><span data-stu-id="9a9dc-113"><xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A> property</span></span>|<span data-ttu-id="9a9dc-114">最小距離 (ピクセル単位)、スプリッターをユーザーが移動できることを決定します。</span><span class="sxs-lookup"><span data-stu-id="9a9dc-114">Determines the minimum distance, in pixels, that the splitter can be moved by the user.</span></span>|  
  
 <span data-ttu-id="9a9dc-115">次の例を変更、<xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A>プロパティを「分割線にスナップ」効果を作成、ユーザーは、分割線をドラッグと、に、既定値 1 ではなく、10 ピクセル単位で増加します。</span><span class="sxs-lookup"><span data-stu-id="9a9dc-115">The example below modifies the <xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A> property to create a "snapping splitter" effect; when the user drags the splitter, it increments in units of 10 pixels rather than the default 1.</span></span>  
  
### <a name="to-define-splitcontainer-resize-behavior"></a><span data-ttu-id="9a9dc-116">SplitContainer サイズ変更動作を定義するには</span><span class="sxs-lookup"><span data-stu-id="9a9dc-116">To define SplitContainer resize behavior</span></span>  
  
1. <span data-ttu-id="9a9dc-117">プロシージャでは、次のように設定します。、<xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A>目的のサイズにプロパティ 'スナップ' スプリッターの動作を実現できるようにします。</span><span class="sxs-lookup"><span data-stu-id="9a9dc-117">In a procedure, set the <xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A> property to the desired size, so that the 'snapping' behavior of the splitter is achieved.</span></span>  
  
     <span data-ttu-id="9a9dc-118">フォームの内で、次のコード例で<xref:System.Windows.Forms.Form.Load>イベント、内のスプリッター、<xref:System.Windows.Forms.SplitContainer>コントロールをドラッグすると、10 ピクセルのジャンプを設定します。</span><span class="sxs-lookup"><span data-stu-id="9a9dc-118">In the following code example, within the form's <xref:System.Windows.Forms.Form.Load> event, the splitter within the <xref:System.Windows.Forms.SplitContainer> control is set to jump 10 pixels when dragged.</span></span>  
  
    ```vb  
    Private Sub Form1_Load(ByVal sender As System.Object, _  
        ByVal e As System.EventArgs) Handles MyBase.Load  
        Dim splitSnapper as new SplitContainer()  
        splitSnapper.SplitterIncrement = 10  
        splitSnapper.Dock = DockStyle.Fill  
        splitSnapper.Parent = me  
    End Sub  
    ```  
  
    ```csharp  
    private void Form1_Load(System.Object sender, System.EventArgs e)  
    {  
        SplitContainer splitSnapper = new SplitContainer();  
        splitSnapper.SplitterIncrement = 10;  
        splitSnapper.Dock = DockStyle.Fill;  
        splitSnapper.Parent = this;  
    }  
    ```  
  
     <span data-ttu-id="9a9dc-119">(Visual C#)イベント ハンドラーを登録するフォームのコンス トラクターでは、次のコードを配置します。</span><span class="sxs-lookup"><span data-stu-id="9a9dc-119">(Visual C#) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.Load += new System.EventHandler(this.Form1_Load);  
    ```  
  
     <span data-ttu-id="9a9dc-120">分割線の左側または右側に少し移動効果はありません厳しく;ただし、マウス ポインターでは、いずれかの方向に 10 ピクセルを移動、スプリッターが新しい位置にスナップされます。</span><span class="sxs-lookup"><span data-stu-id="9a9dc-120">Moving the splitter slightly to the left or right will have no discernible effect; however, when the mouse pointer goes 10 pixels in either direction, the splitter will snap to the new position.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a9dc-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="9a9dc-121">See also</span></span>

- <xref:System.Windows.Forms.SplitContainer>
- <xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A>
