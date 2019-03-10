---
title: '方法: TAB キーで ToolStrip コントロールから移動を有効にします。'
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], moving between
- TAB key [Windows Forms], enabling
- ToolStrip control [Windows Forms], moving from
ms.assetid: 40f9e88b-09a3-428e-8da8-c00bb65079c6
ms.openlocfilehash: e1d7917d7e12ba286e7ddf4e95a68769852a17f7
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/09/2019
ms.locfileid: "57704337"
---
# <a name="how-to-enable-the-tab-key-to-move-out-of-a-toolstrip-control"></a><span data-ttu-id="392e8-102">方法: TAB キーで ToolStrip コントロールから移動を有効にします。</span><span class="sxs-lookup"><span data-stu-id="392e8-102">How to: Enable the TAB Key to Move Out of a ToolStrip Control</span></span>
<span data-ttu-id="392e8-103">タブ キーを押してから移動するユーザーを有効にする、次の手順を使用して、<xref:System.Windows.Forms.ToolStrip>タブ オーダー内で次のコントロールにします。</span><span class="sxs-lookup"><span data-stu-id="392e8-103">Use the following procedure to enable the user to press the TAB key to move out of a <xref:System.Windows.Forms.ToolStrip> to the next control in the tab order.</span></span>  
  
 <span data-ttu-id="392e8-104"><xref:System.Windows.Forms.ToolStrip>受け入れる、TAB キーと矢印キーの選択項目内の最初のキーを押して、<xref:System.Windows.Forms.ToolStrip>します。</span><span class="sxs-lookup"><span data-stu-id="392e8-104">The <xref:System.Windows.Forms.ToolStrip> accepts the first press of the TAB key, and the arrow keys select items within the <xref:System.Windows.Forms.ToolStrip>.</span></span> <span data-ttu-id="392e8-105">ユーザーは、もう一度 TAB キーを押すと、タブ オーダー内で次のコントロールにユーザーがかかります。</span><span class="sxs-lookup"><span data-stu-id="392e8-105">When the user presses the TAB key a second time, it takes the user to the next control in the tab order.</span></span>  
  
### <a name="to-enable-the-user-to-press-the-tab-key-to-move-out-of-a-toolstrip-to-the-next-control"></a><span data-ttu-id="392e8-106">次のコントロールにあるコマンド バーから移動するタブ キーを押すようにユーザーを有効にするには</span><span class="sxs-lookup"><span data-stu-id="392e8-106">To enable the user to press the TAB key to move out of a ToolStrip to the next control</span></span>  
  
-   <span data-ttu-id="392e8-107">設定、<xref:System.Windows.Forms.ToolStrip.TabStop%2A>のプロパティ、<xref:System.Windows.Forms.ToolStrip>に`true`します。</span><span class="sxs-lookup"><span data-stu-id="392e8-107">Set the <xref:System.Windows.Forms.ToolStrip.TabStop%2A> property of the <xref:System.Windows.Forms.ToolStrip> to `true`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="392e8-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="392e8-108">See also</span></span>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStrip.TabStop%2A>
- [<span data-ttu-id="392e8-109">ToolStrip コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="392e8-109">ToolStrip Control Overview</span></span>](toolstrip-control-overview-windows-forms.md)
