---
title: '方法: Tab キーで ToolStrip コントロールから移動できるようにする'
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], moving between
- TAB key [Windows Forms], enabling
- ToolStrip control [Windows Forms], moving from
ms.assetid: 40f9e88b-09a3-428e-8da8-c00bb65079c6
ms.openlocfilehash: d4de7345a4e3ce122c4e1fc0a92f09b447204eb6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61941428"
---
# <a name="how-to-enable-the-tab-key-to-move-out-of-a-toolstrip-control"></a><span data-ttu-id="83413-102">方法: Tab キーで ToolStrip コントロールから移動できるようにする</span><span class="sxs-lookup"><span data-stu-id="83413-102">How to: Enable the TAB Key to Move Out of a ToolStrip Control</span></span>
<span data-ttu-id="83413-103">タブ キーを押してから移動するユーザーを有効にする、次の手順を使用して、<xref:System.Windows.Forms.ToolStrip>タブ オーダー内で次のコントロールにします。</span><span class="sxs-lookup"><span data-stu-id="83413-103">Use the following procedure to enable the user to press the TAB key to move out of a <xref:System.Windows.Forms.ToolStrip> to the next control in the tab order.</span></span>  
  
 <span data-ttu-id="83413-104"><xref:System.Windows.Forms.ToolStrip>受け入れる、TAB キーと矢印キーの選択項目内の最初のキーを押して、<xref:System.Windows.Forms.ToolStrip>します。</span><span class="sxs-lookup"><span data-stu-id="83413-104">The <xref:System.Windows.Forms.ToolStrip> accepts the first press of the TAB key, and the arrow keys select items within the <xref:System.Windows.Forms.ToolStrip>.</span></span> <span data-ttu-id="83413-105">ユーザーは、もう一度 TAB キーを押すと、タブ オーダー内で次のコントロールにユーザーがかかります。</span><span class="sxs-lookup"><span data-stu-id="83413-105">When the user presses the TAB key a second time, it takes the user to the next control in the tab order.</span></span>  
  
### <a name="to-enable-the-user-to-press-the-tab-key-to-move-out-of-a-toolstrip-to-the-next-control"></a><span data-ttu-id="83413-106">次のコントロールにあるコマンド バーから移動するタブ キーを押すようにユーザーを有効にするには</span><span class="sxs-lookup"><span data-stu-id="83413-106">To enable the user to press the TAB key to move out of a ToolStrip to the next control</span></span>  
  
- <span data-ttu-id="83413-107">設定、<xref:System.Windows.Forms.ToolStrip.TabStop%2A>のプロパティ、<xref:System.Windows.Forms.ToolStrip>に`true`します。</span><span class="sxs-lookup"><span data-stu-id="83413-107">Set the <xref:System.Windows.Forms.ToolStrip.TabStop%2A> property of the <xref:System.Windows.Forms.ToolStrip> to `true`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83413-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="83413-108">See also</span></span>

- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStrip.TabStop%2A>
- [<span data-ttu-id="83413-109">ToolStrip コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="83413-109">ToolStrip Control Overview</span></span>](toolstrip-control-overview-windows-forms.md)
