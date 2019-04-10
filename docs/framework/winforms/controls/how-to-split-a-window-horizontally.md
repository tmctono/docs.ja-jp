---
title: '方法: ウィンドウを水平方向に分割する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- SplitContainer control [Windows Forms], horizontal splitter
- splitter windows [Windows Forms], changing splitter orientation
- splitter windows [Windows Forms], horizontal
- windows [Windows Forms], splitting horizontally
ms.assetid: a1f74f29-048c-4723-85fa-b9d375ab8f4b
ms.openlocfilehash: d10616e2f09eabec1209a26aabe501ea0af903cb
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59189649"
---
# <a name="how-to-split-a-window-horizontally"></a><span data-ttu-id="a1da7-102">方法: ウィンドウを水平方向に分割する</span><span class="sxs-lookup"><span data-stu-id="a1da7-102">How to: Split a Window Horizontally</span></span>
<span data-ttu-id="a1da7-103">次のコード例は、分割するスプリッター、<xref:System.Windows.Forms.SplitContainer>コントロールの水平方向。</span><span class="sxs-lookup"><span data-stu-id="a1da7-103">The following code example makes the splitter that divides the <xref:System.Windows.Forms.SplitContainer> control horizontal.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a1da7-104"><xref:System.Windows.Forms.SplitContainer.Orientation%2A>のプロパティ、<xref:System.Windows.Forms.SplitContainer>コントロール、コントロール自体のない、スプリッターの方向を決定します。</span><span class="sxs-lookup"><span data-stu-id="a1da7-104">The <xref:System.Windows.Forms.SplitContainer.Orientation%2A> property of the <xref:System.Windows.Forms.SplitContainer> control determines the direction of the splitter, not of the control itself.</span></span>  
  
### <a name="to-split-a-window-horizontally"></a><span data-ttu-id="a1da7-105">ウィンドウを水平方向に分割するには</span><span class="sxs-lookup"><span data-stu-id="a1da7-105">To split a window horizontally</span></span>  
  
1.  <span data-ttu-id="a1da7-106">プロシージャ内で、設定、<xref:System.Windows.Forms.SplitContainer.Orientation%2A>のプロパティ、<xref:System.Windows.Forms.SplitContainer>に制御を<xref:System.Windows.Forms.Orientation.Horizontal>。</span><span class="sxs-lookup"><span data-stu-id="a1da7-106">Within a procedure, set the <xref:System.Windows.Forms.SplitContainer.Orientation%2A> property of the <xref:System.Windows.Forms.SplitContainer> control to <xref:System.Windows.Forms.Orientation.Horizontal>.</span></span>  
  
    ```vb  
    Sub ShowSplitContainer()  
        Dim splitContainer1 as new SplitContainer()  
        splitContainer1.BorderStyle = BorderStyle.Fixed3D  
        splitContainer1.Location = New System.Drawing.Point(74, 20)  
        splitContainer1.Name = "DemoSplitContainer"  
        splitContainer1.Size = New System.Drawing.Size(212, 435)  
        splitContainer1.TabIndex = 0  
        splitContainer1.Orientation = Orientation.Horizontal  
        Controls.Add(splitContainer1)  
    End Sub  
    ```  
  
    ```csharp  
    public void showSplitContainer()  
    {  
        SplitContainer splitContainer1 = new SplitContainer ();  
        splitContainer1.BorderStyle = BorderStyle.Fixed3D;  
        splitContainer1.Location = new System.Drawing.Point (74, 20);  
        splitContainer1.Name = "DemoSplitContainer";  
        splitContainer1.Size = new System.Drawing.Size (212, 435);  
        splitContainer1.TabIndex = 0;  
        splitContainer1.Orientation = Orientation.Horizontal;  
        this.Controls.Add (splitContainer1);  
  
    }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="a1da7-107">関連項目</span><span class="sxs-lookup"><span data-stu-id="a1da7-107">See also</span></span>

- <xref:System.Windows.Forms.SplitContainer>
- [<span data-ttu-id="a1da7-108">SplitContainer コントロール</span><span class="sxs-lookup"><span data-stu-id="a1da7-108">SplitContainer Control</span></span>](splitcontainer-control-windows-forms.md)
