---
title: '方法: Tab キーで ToolStrip コントロールから移動できるようにする'
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], moving between
- TAB key [Windows Forms], enabling
- ToolStrip control [Windows Forms], moving from
ms.assetid: 40f9e88b-09a3-428e-8da8-c00bb65079c6
ms.openlocfilehash: 7fee9f685b9a9b402cbfe9c265669f7905434986
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64609835"
---
# <a name="how-to-enable-the-tab-key-to-move-out-of-a-toolstrip-control"></a><span data-ttu-id="ca0ed-102">方法: Tab キーで ToolStrip コントロールから移動できるようにする</span><span class="sxs-lookup"><span data-stu-id="ca0ed-102">How to: Enable the TAB Key to Move Out of a ToolStrip Control</span></span>
<span data-ttu-id="ca0ed-103">タブ キーを押してから移動するユーザーを有効にする、次の手順を使用して、<xref:System.Windows.Forms.ToolStrip>タブ オーダー内で次のコントロールにします。</span><span class="sxs-lookup"><span data-stu-id="ca0ed-103">Use the following procedure to enable the user to press the TAB key to move out of a <xref:System.Windows.Forms.ToolStrip> to the next control in the tab order.</span></span>  
  
 <span data-ttu-id="ca0ed-104"><xref:System.Windows.Forms.ToolStrip>受け入れる、TAB キーと矢印キーの選択項目内の最初のキーを押して、<xref:System.Windows.Forms.ToolStrip>します。</span><span class="sxs-lookup"><span data-stu-id="ca0ed-104">The <xref:System.Windows.Forms.ToolStrip> accepts the first press of the TAB key, and the arrow keys select items within the <xref:System.Windows.Forms.ToolStrip>.</span></span> <span data-ttu-id="ca0ed-105">ユーザーは、もう一度 TAB キーを押すと、タブ オーダー内で次のコントロールにユーザーがかかります。</span><span class="sxs-lookup"><span data-stu-id="ca0ed-105">When the user presses the TAB key a second time, it takes the user to the next control in the tab order.</span></span>  
  
### <a name="to-enable-the-user-to-press-the-tab-key-to-move-out-of-a-toolstrip-to-the-next-control"></a><span data-ttu-id="ca0ed-106">次のコントロールにあるコマンド バーから移動するタブ キーを押すようにユーザーを有効にするには</span><span class="sxs-lookup"><span data-stu-id="ca0ed-106">To enable the user to press the TAB key to move out of a ToolStrip to the next control</span></span>  
  
- <span data-ttu-id="ca0ed-107">設定、<xref:System.Windows.Forms.ToolStrip.TabStop%2A>のプロパティ、<xref:System.Windows.Forms.ToolStrip>に`true`します。</span><span class="sxs-lookup"><span data-stu-id="ca0ed-107">Set the <xref:System.Windows.Forms.ToolStrip.TabStop%2A> property of the <xref:System.Windows.Forms.ToolStrip> to `true`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca0ed-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="ca0ed-108">See also</span></span>

- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStrip.TabStop%2A>
- [<span data-ttu-id="ca0ed-109">ToolStrip コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="ca0ed-109">ToolStrip Control Overview</span></span>](toolstrip-control-overview-windows-forms.md)
