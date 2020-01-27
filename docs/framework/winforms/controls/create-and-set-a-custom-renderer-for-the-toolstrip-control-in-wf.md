---
title: '方法: ToolStrip コントロールのカスタムレンダラーを作成および設定する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolStrip control [Windows Forms], custom rendering
- toolbars [Windows Forms], rendering
- examples [Windows Forms], toolbars
- ToolStrip control [Windows Forms], rendering
ms.assetid: 88a804ba-679f-4ba3-938a-0dc396199c5b
ms.openlocfilehash: ad5ced42754fba6a714452220dd824c4f54fb5e5
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743410"
---
# <a name="how-to-create-and-set-a-custom-renderer-for-the-toolstrip-control-in-windows-forms"></a><span data-ttu-id="ea971-102">方法 : Windows フォームに ToolStrip コントロールのカスタム レンダラーを作成して設定する</span><span class="sxs-lookup"><span data-stu-id="ea971-102">How to: Create and Set a Custom Renderer for the ToolStrip Control in Windows Forms</span></span>
<span data-ttu-id="ea971-103"><xref:System.Windows.Forms.ToolStrip> コントロールを使うと、テーマとスタイルを簡単にサポートできます。</span><span class="sxs-lookup"><span data-stu-id="ea971-103"><xref:System.Windows.Forms.ToolStrip> controls give easy support to themes and styles.</span></span> <span data-ttu-id="ea971-104"><xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> プロパティまたは <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType> プロパティをカスタムレンダラーに設定することにより、完全にカスタムの外観と動作 (ルックアンドフィール) を実現できます。</span><span class="sxs-lookup"><span data-stu-id="ea971-104">You can achieve completely custom appearance and behavior (look and feel) by setting either the <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> property or the <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType> property to a custom renderer.</span></span>  
  
 <span data-ttu-id="ea971-105">レンダラーは、個々の <xref:System.Windows.Forms.ToolStrip>、<xref:System.Windows.Forms.MenuStrip>、<xref:System.Windows.Forms.ContextMenuStrip>、または <xref:System.Windows.Forms.StatusStrip> コントロールに割り当てることができます。また、<xref:System.Windows.Forms.ToolStripManager.Renderer%2A> プロパティを <xref:System.Windows.Forms.ToolStrip.RenderMode%2A?displayProperty=nameWithType> に設定することで、すべてのオブジェクトに影響を与えることができます。</span><span class="sxs-lookup"><span data-stu-id="ea971-105">You can assign renderers to each individual <xref:System.Windows.Forms.ToolStrip>, <xref:System.Windows.Forms.MenuStrip>, <xref:System.Windows.Forms.ContextMenuStrip>, or <xref:System.Windows.Forms.StatusStrip> control, or you can use the <xref:System.Windows.Forms.ToolStripManager.Renderer%2A> property to affect all objects by setting the <xref:System.Windows.Forms.ToolStrip.RenderMode%2A?displayProperty=nameWithType> property to <xref:System.Windows.Forms.ToolStripRenderMode.ManagerRenderMode?displayProperty=nameWithType>.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ea971-106"><xref:System.Windows.Forms.ToolStrip.RenderMode%2A> は、<xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> の値が `null`ない場合にのみ <xref:System.Windows.Forms.ToolStripRenderMode.Custom> を返します。</span><span class="sxs-lookup"><span data-stu-id="ea971-106"><xref:System.Windows.Forms.ToolStrip.RenderMode%2A> returns <xref:System.Windows.Forms.ToolStripRenderMode.Custom> only if the value of <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> is not `null`.</span></span>  
  
### <a name="to-create-a-custom-renderer"></a><span data-ttu-id="ea971-107">カスタムレンダラーを作成するには</span><span class="sxs-lookup"><span data-stu-id="ea971-107">To create a custom renderer</span></span>  
  
1. <span data-ttu-id="ea971-108"><xref:System.Windows.Forms.ToolStripRenderer> クラスを拡張します。</span><span class="sxs-lookup"><span data-stu-id="ea971-108">Extend the <xref:System.Windows.Forms.ToolStripRenderer> class.</span></span>  
  
2. <span data-ttu-id="ea971-109">適切にオーバーライドして、必要なカスタムレンダリングを実装します. *.*</span><span class="sxs-lookup"><span data-stu-id="ea971-109">Implement desired custom rendering by overriding appropriate *On…*</span></span> <span data-ttu-id="ea971-110">メンバー</span><span class="sxs-lookup"><span data-stu-id="ea971-110">members</span></span>  
  
    ```vb  
    Public Class RedTextRenderer  
        Inherits System.Windows.Forms.ToolStripRenderer  
        Protected Overrides Sub OnRenderItemText(ByVal e As _  
            ToolStripItemTextRenderEventArgs)   
            e.TextColor = Color.Red  
            e.TextFont = New Font("Helvetica", 7, FontStyle.Bold)  
            MyBase.OnRenderItemText(e)  
        End Sub  
    End Class  
    ```  
  
    ```csharp  
    public class RedTextRenderer : _  
        System.Windows.Forms.ToolStripRenderer  
    {  
        protected override void _  
            OnRenderItemText(ToolStripItemTextRenderEventArgs e)  
        {  
            e.TextColor = Color.Red;  
            e.TextFont = new Font("Helvetica", 7, FontStyle.Bold);  
           base.OnRenderItemText(e);  
        }  
    }  
    ```  
  
### <a name="to-set-the-custom-renderer-to-be-the-current-renderer"></a><span data-ttu-id="ea971-111">カスタムレンダラーを現在のレンダラーに設定するには</span><span class="sxs-lookup"><span data-stu-id="ea971-111">To set the custom renderer to be the current renderer</span></span>  
  
1. <span data-ttu-id="ea971-112">1つの <xref:System.Windows.Forms.ToolStrip>に対してカスタムレンダラーを設定するには、<xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> プロパティをカスタムレンダラーに設定します。</span><span class="sxs-lookup"><span data-stu-id="ea971-112">To set the custom renderer for one <xref:System.Windows.Forms.ToolStrip>, set the <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> property to the custom renderer.</span></span>  
  
    ```vb  
    toolStrip1.Renderer = New RedTextRenderer()  
    ```  
  
    ```csharp  
    toolStrip1.Renderer = new RedTextRenderer();  
    ```  
  
2. <span data-ttu-id="ea971-113">または、アプリケーションに含まれるすべての <xref:System.Windows.Forms.ToolStrip> クラスのカスタムレンダラーを設定するには、<xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType> プロパティをカスタムレンダラーに設定し、<xref:System.Windows.Forms.ToolStrip.RenderMode%2A> プロパティを <xref:System.Windows.Forms.ToolStripRenderMode.ManagerRenderMode>に設定します。</span><span class="sxs-lookup"><span data-stu-id="ea971-113">Or to set the custom renderer for all <xref:System.Windows.Forms.ToolStrip> classes contained in your application: Set the <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType> property to the custom renderer and set the <xref:System.Windows.Forms.ToolStrip.RenderMode%2A> property to <xref:System.Windows.Forms.ToolStripRenderMode.ManagerRenderMode>.</span></span>  
  
    ```vb  
    toolStrip1.RenderMode = ToolStripRenderMode.ManagerRenderMode  
    ToolStripManager.Renderer = New RedTextRenderer()  
    ```  
  
    ```csharp  
    toolStrip1.RenderMode = ToolStripRenderMode.ManagerRenderMode;  
    ToolStripManager.Renderer = new RedTextRenderer();  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="ea971-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="ea971-114">See also</span></span>

- <xref:System.Windows.Forms.ToolStripManager.Renderer%2A>
- <xref:System.Windows.Forms.ToolStripRenderer>
- <xref:System.Windows.Forms.ToolStrip.RenderMode%2A>
- [<span data-ttu-id="ea971-115">ToolStrip コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="ea971-115">ToolStrip Control Overview</span></span>](toolstrip-control-overview-windows-forms.md)
- [<span data-ttu-id="ea971-116">ToolStrip コントロールのアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="ea971-116">ToolStrip Control Architecture</span></span>](toolstrip-control-architecture.md)
- [<span data-ttu-id="ea971-117">ToolStrip テクノロジの概要</span><span class="sxs-lookup"><span data-stu-id="ea971-117">ToolStrip Technology Summary</span></span>](toolstrip-technology-summary.md)
