---
title: '方法: ToolStrip コントロールのカスタム レンダラーを作成および設定する'
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
ms.openlocfilehash: 49db0d785155f19b7220ac64011eaf4253aaa7e9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182401"
---
# <a name="how-to-create-and-set-a-custom-renderer-for-the-toolstrip-control-in-windows-forms"></a><span data-ttu-id="4e721-102">方法 : Windows フォームに ToolStrip コントロールのカスタム レンダラーを作成して設定する</span><span class="sxs-lookup"><span data-stu-id="4e721-102">How to: Create and Set a Custom Renderer for the ToolStrip Control in Windows Forms</span></span>
<span data-ttu-id="4e721-103"><xref:System.Windows.Forms.ToolStrip>コントロールは、テーマやスタイルに簡単にサポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="4e721-103"><xref:System.Windows.Forms.ToolStrip> controls give easy support to themes and styles.</span></span> <span data-ttu-id="4e721-104">プロパティまたはプロパティをカスタム レンダラに設定することで、完全にカスタムの<xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType>外観と<xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType>動作 (ルック アンド フィール) を実現できます。</span><span class="sxs-lookup"><span data-stu-id="4e721-104">You can achieve completely custom appearance and behavior (look and feel) by setting either the <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> property or the <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType> property to a custom renderer.</span></span>  
  
 <span data-ttu-id="4e721-105">レンダラーは<xref:System.Windows.Forms.ToolStrip>、 、 、<xref:System.Windows.Forms.MenuStrip><xref:System.Windows.Forms.ContextMenuStrip>または<xref:System.Windows.Forms.StatusStrip>コントロールに割り当てることも、<xref:System.Windows.Forms.ToolStripManager.Renderer%2A>プロパティを使用して すべてのオブジェクト<xref:System.Windows.Forms.ToolStrip.RenderMode%2A?displayProperty=nameWithType>に影響<xref:System.Windows.Forms.ToolStripRenderMode.ManagerRenderMode?displayProperty=nameWithType>を与える場合は、 プロパティを に設定します。</span><span class="sxs-lookup"><span data-stu-id="4e721-105">You can assign renderers to each individual <xref:System.Windows.Forms.ToolStrip>, <xref:System.Windows.Forms.MenuStrip>, <xref:System.Windows.Forms.ContextMenuStrip>, or <xref:System.Windows.Forms.StatusStrip> control, or you can use the <xref:System.Windows.Forms.ToolStripManager.Renderer%2A> property to affect all objects by setting the <xref:System.Windows.Forms.ToolStrip.RenderMode%2A?displayProperty=nameWithType> property to <xref:System.Windows.Forms.ToolStripRenderMode.ManagerRenderMode?displayProperty=nameWithType>.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4e721-106"><xref:System.Windows.Forms.ToolStrip.RenderMode%2A>の<xref:System.Windows.Forms.ToolStripRenderMode.Custom>値<xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType>がでない`null`場合にのみ返されます。</span><span class="sxs-lookup"><span data-stu-id="4e721-106"><xref:System.Windows.Forms.ToolStrip.RenderMode%2A> returns <xref:System.Windows.Forms.ToolStripRenderMode.Custom> only if the value of <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> is not `null`.</span></span>  
  
### <a name="to-create-a-custom-renderer"></a><span data-ttu-id="4e721-107">カスタム レンダラーを作成するには</span><span class="sxs-lookup"><span data-stu-id="4e721-107">To create a custom renderer</span></span>  
  
1. <span data-ttu-id="4e721-108">クラスを<xref:System.Windows.Forms.ToolStripRenderer>拡張します。</span><span class="sxs-lookup"><span data-stu-id="4e721-108">Extend the <xref:System.Windows.Forms.ToolStripRenderer> class.</span></span>  
  
2. <span data-ttu-id="4e721-109">適切な*On..* をオーバーライドして、目的のカスタム レンダリングを実装します。</span><span class="sxs-lookup"><span data-stu-id="4e721-109">Implement desired custom rendering by overriding appropriate *On…*</span></span> <span data-ttu-id="4e721-110">members</span><span class="sxs-lookup"><span data-stu-id="4e721-110">members</span></span>  
  
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
  
### <a name="to-set-the-custom-renderer-to-be-the-current-renderer"></a><span data-ttu-id="4e721-111">カスタム レンダラーを現在のレンダラーに設定するには</span><span class="sxs-lookup"><span data-stu-id="4e721-111">To set the custom renderer to be the current renderer</span></span>  
  
1. <span data-ttu-id="4e721-112">カスタム レンダラーを 1<xref:System.Windows.Forms.ToolStrip>つに設定<xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType>するには、プロパティをカスタム レンダラーに設定します。</span><span class="sxs-lookup"><span data-stu-id="4e721-112">To set the custom renderer for one <xref:System.Windows.Forms.ToolStrip>, set the <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> property to the custom renderer.</span></span>  
  
    ```vb  
    toolStrip1.Renderer = New RedTextRenderer()  
    ```  
  
    ```csharp  
    toolStrip1.Renderer = new RedTextRenderer();  
    ```  
  
2. <span data-ttu-id="4e721-113">または、アプリケーションに<xref:System.Windows.Forms.ToolStrip>含まれるすべてのクラスにカスタム レンダラーを設定するには<xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType>、次の手順に<xref:System.Windows.Forms.ToolStrip.RenderMode%2A>従います。 <xref:System.Windows.Forms.ToolStripRenderMode.ManagerRenderMode></span><span class="sxs-lookup"><span data-stu-id="4e721-113">Or to set the custom renderer for all <xref:System.Windows.Forms.ToolStrip> classes contained in your application: Set the <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType> property to the custom renderer and set the <xref:System.Windows.Forms.ToolStrip.RenderMode%2A> property to <xref:System.Windows.Forms.ToolStripRenderMode.ManagerRenderMode>.</span></span>  
  
    ```vb  
    toolStrip1.RenderMode = ToolStripRenderMode.ManagerRenderMode  
    ToolStripManager.Renderer = New RedTextRenderer()  
    ```  
  
    ```csharp  
    toolStrip1.RenderMode = ToolStripRenderMode.ManagerRenderMode;  
    ToolStripManager.Renderer = new RedTextRenderer();  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="4e721-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="4e721-114">See also</span></span>

- <xref:System.Windows.Forms.ToolStripManager.Renderer%2A>
- <xref:System.Windows.Forms.ToolStripRenderer>
- <xref:System.Windows.Forms.ToolStrip.RenderMode%2A>
- [<span data-ttu-id="4e721-115">ToolStrip コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="4e721-115">ToolStrip Control Overview</span></span>](toolstrip-control-overview-windows-forms.md)
- [<span data-ttu-id="4e721-116">ToolStrip コントロールのアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="4e721-116">ToolStrip Control Architecture</span></span>](toolstrip-control-architecture.md)
- [<span data-ttu-id="4e721-117">ToolStrip テクノロジの概要</span><span class="sxs-lookup"><span data-stu-id="4e721-117">ToolStrip Technology Summary</span></span>](toolstrip-technology-summary.md)
