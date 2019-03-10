---
title: '方法: ToolStrip コントロールにトグル ボタンを作成します。'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- toggle buttons [Windows Forms], creating
- examples [Windows Forms], toolbars
- ToolStrip control [Windows Forms], creating toggle buttons
ms.assetid: d9c197df-4c65-43f2-beee-b68b52b2befc
ms.openlocfilehash: a059726ea410e88121a0b755295c3c492c11962a
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/09/2019
ms.locfileid: "57705520"
---
# <a name="how-to-create-toggle-buttons-in-toolstrip-controls"></a><span data-ttu-id="3cd9b-102">方法: ToolStrip コントロールにトグル ボタンを作成します。</span><span class="sxs-lookup"><span data-stu-id="3cd9b-102">How to: Create Toggle Buttons in ToolStrip Controls</span></span>
<span data-ttu-id="3cd9b-103">ユーザーには、トグル ボタンがクリックすると、くぼんで表示し、もう一度ボタンをクリックするまで、くぼんだ外観を保持します。</span><span class="sxs-lookup"><span data-stu-id="3cd9b-103">When a user clicks a toggle button, it appears sunken and retains the sunken appearance until the user clicks the button again.</span></span>  
  
### <a name="to-create-a-toggling-toolstripbutton"></a><span data-ttu-id="3cd9b-104">切り替えのオブジェクトを作成するには</span><span class="sxs-lookup"><span data-stu-id="3cd9b-104">To create a toggling ToolStripButton</span></span>  
  
-   <span data-ttu-id="3cd9b-105">次のコード例などのコードを使用します。</span><span class="sxs-lookup"><span data-stu-id="3cd9b-105">Use code such as the following code example.</span></span> <span data-ttu-id="3cd9b-106">このコードでは、フォームが含まれている前提としています、<xref:System.Windows.Forms.ToolStrip>コントロール、およびその<xref:System.Windows.Forms.ToolStrip.Items%2A>コレクションに含まれる、<xref:System.Windows.Forms.ToolStripButton>と呼ばれる`toolStripButton1`します。</span><span class="sxs-lookup"><span data-stu-id="3cd9b-106">This code assumes that your form contains a <xref:System.Windows.Forms.ToolStrip> control, and that its <xref:System.Windows.Forms.ToolStrip.Items%2A> collection contains a <xref:System.Windows.Forms.ToolStripButton> called `toolStripButton1`.</span></span> <span data-ttu-id="3cd9b-107">呼ばれるイベント ハンドラーを設定することも想定`toolStripButton1_CheckedChanged`します。</span><span class="sxs-lookup"><span data-stu-id="3cd9b-107">It also assumes that you have an event handler called `toolStripButton1_CheckedChanged`.</span></span>  
  
    ```vb  
    toolStripButton1.CheckOnClick = True  
    toolStripButton1.CheckedChanged AddressOf _  
    EventHandler(toolStripButton1_CheckedChanged);  
    ```  
  
    ```csharp  
    toolStripButton1.CheckOnClick = true;  
    toolStripButton1.CheckedChanged += new _  
    EventHandler(toolStripButton1_CheckedChanged);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="3cd9b-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="3cd9b-108">See also</span></span>
- <xref:System.Windows.Forms.ToolStripButton>
- [<span data-ttu-id="3cd9b-109">ToolStrip コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="3cd9b-109">ToolStrip Control Overview</span></span>](toolstrip-control-overview-windows-forms.md)
