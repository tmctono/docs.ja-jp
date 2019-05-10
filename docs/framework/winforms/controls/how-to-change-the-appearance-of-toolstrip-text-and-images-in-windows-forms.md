---
title: '方法: Windows フォーム内の ToolStrip テキストとイメージの外観を変更する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolStrip control [Windows Forms], appearance
- toolbars [Windows Forms], images
- examples [Windows Forms], toolbars
- toolbars [Windows Forms], appearance
- ToolStrip control [Windows Forms], images
- ToolStrip control [Windows Forms], text
- toolbars [Windows Forms], text
ms.assetid: d62dc9d1-2edd-4dfa-aed7-1335d6e13d86
ms.openlocfilehash: cf2f332b17bf6ff5b6ffb7cbc2d5777649728ec6
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64650856"
---
# <a name="how-to-change-the-appearance-of-toolstrip-text-and-images-in-windows-forms"></a><span data-ttu-id="59073-102">方法: Windows フォーム内の ToolStrip テキストとイメージの外観を変更する</span><span class="sxs-lookup"><span data-stu-id="59073-102">How to: Change the Appearance of ToolStrip Text and Images in Windows Forms</span></span>
<span data-ttu-id="59073-103">テキストとイメージを表示するかどうかを制御できます、<xref:System.Windows.Forms.ToolStripItem>と相対的な配置と<xref:System.Windows.Forms.ToolStrip>します。</span><span class="sxs-lookup"><span data-stu-id="59073-103">You can control whether text and images are displayed on a <xref:System.Windows.Forms.ToolStripItem> and how they are aligned relative to each other and the <xref:System.Windows.Forms.ToolStrip>.</span></span>  
  
### <a name="to-define-what-is-displayed-on-a-toolstripitem"></a><span data-ttu-id="59073-104">Toolstripitem の表示される内容を定義するには</span><span class="sxs-lookup"><span data-stu-id="59073-104">To define what is displayed on a ToolStripItem</span></span>  
  
- <span data-ttu-id="59073-105">設定、<xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A>プロパティを目的の値にします。</span><span class="sxs-lookup"><span data-stu-id="59073-105">Set the <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> property to the desired value.</span></span> <span data-ttu-id="59073-106">可能性は`Image`、 `ImageAndText`、 `None`、および`Text`します。</span><span class="sxs-lookup"><span data-stu-id="59073-106">The possibilities are `Image`, `ImageAndText`, `None`, and `Text`.</span></span> <span data-ttu-id="59073-107">既定値は `ImageAndText` です。</span><span class="sxs-lookup"><span data-stu-id="59073-107">The default is `ImageAndText`.</span></span>  
  
    ```vb  
    ToolStripButton2.DisplayStyle = _  
        System.Windows.Forms.ToolStripItemDisplayStyle.Image  
    ```  
  
    ```csharp  
    toolStripButton2.DisplayStyle = System.Windows.Forms.ToolStripItemDisplayStyle.Image;  
    ```  
  
### <a name="to-align-text-on-a-toolstripitem"></a><span data-ttu-id="59073-108">Toolstripitem のテキストを配置するには</span><span class="sxs-lookup"><span data-stu-id="59073-108">To align text on a ToolStripItem</span></span>  
  
- <span data-ttu-id="59073-109">設定、<xref:System.Windows.Forms.ToolStripItem.TextAlign%2A>プロパティを目的の値にします。</span><span class="sxs-lookup"><span data-stu-id="59073-109">Set the <xref:System.Windows.Forms.ToolStripItem.TextAlign%2A> property to the desired value.</span></span> <span data-ttu-id="59073-110">可能性は、上部、中央、およびでは、left、center、および右下の任意の組み合わせです。</span><span class="sxs-lookup"><span data-stu-id="59073-110">The possibilities are any combination of top, middle, and bottom with left, center, and right.</span></span> <span data-ttu-id="59073-111">既定値は `MiddleCenter` です。</span><span class="sxs-lookup"><span data-stu-id="59073-111">The default is `MiddleCenter`.</span></span>  
  
    ```vb  
    ToolStripSplitButton1.TextAlign = _  
        System.Drawing.ContentAlignment.MiddleRight  
    ```  
  
    ```csharp  
    toolStripSplitButton1.TextAlign = System.Drawing.ContentAlignment.MiddleRight;  
    ```  
  
### <a name="to-align-an-image-on-a-toolstripitem"></a><span data-ttu-id="59073-112">Toolstripitem のイメージを配置するには</span><span class="sxs-lookup"><span data-stu-id="59073-112">To align an image on a ToolStripItem</span></span>  
  
- <span data-ttu-id="59073-113">設定、<xref:System.Windows.Forms.ToolStripItem.ImageAlign%2A>プロパティを目的の値にします。</span><span class="sxs-lookup"><span data-stu-id="59073-113">Set the <xref:System.Windows.Forms.ToolStripItem.ImageAlign%2A> property to the desired value.</span></span> <span data-ttu-id="59073-114">可能性は、上部、中央、およびでは、left、center、および右下の任意の組み合わせです。</span><span class="sxs-lookup"><span data-stu-id="59073-114">The possibilities are any combination of top, middle, and bottom with left, center, and right.</span></span> <span data-ttu-id="59073-115">既定値は `MiddleLeft` です。</span><span class="sxs-lookup"><span data-stu-id="59073-115">The default is `MiddleLeft`.</span></span>  
  
    ```vb  
    ToolStripSplitButton1.ImageAlign = _  
        System.Drawing.ContentAlignment.MiddleRight  
    ```  
  
    ```csharp  
    toolStripSplitButton1.ImageAlign = System.Drawing.ContentAlignment.MiddleRight;  
    ```  
  
### <a name="to-define-how-toolstripitem-text-and-images-are-displayed-relative-to-each-other"></a><span data-ttu-id="59073-116">相互に比較した ToolStripItem テキストとイメージを表示する方法を定義するには</span><span class="sxs-lookup"><span data-stu-id="59073-116">To define how ToolStripItem text and images are displayed relative to each other</span></span>  
  
- <span data-ttu-id="59073-117">設定、<xref:System.Windows.Forms.ToolStripItem.TextImageRelation%2A>プロパティを目的の値にします。</span><span class="sxs-lookup"><span data-stu-id="59073-117">Set the <xref:System.Windows.Forms.ToolStripItem.TextImageRelation%2A> property to the desired value.</span></span> <span data-ttu-id="59073-118">可能性は`ImageAboveText`、 `ImageBeforeText`、 `Overlay`、 `TextAboveImage`、および`TextBeforeImage`します。</span><span class="sxs-lookup"><span data-stu-id="59073-118">The possibilities are `ImageAboveText`, `ImageBeforeText`, `Overlay`, `TextAboveImage`, and `TextBeforeImage`.</span></span> <span data-ttu-id="59073-119">既定値は `ImageBeforeText` です。</span><span class="sxs-lookup"><span data-stu-id="59073-119">The default is `ImageBeforeText`.</span></span>  
  
    ```vb  
    ToolStripButton1.TextImageRelation = _  
        System.Windows.Forms.TextImageRelation.ImageAboveText  
    ```  
  
    ```csharp  
    toolStripButton1.TextImageRelation = System.Windows.Forms.TextImageRelation.ImageAboveText;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="59073-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="59073-120">See also</span></span>

- <xref:System.Windows.Forms.ToolStrip>
- [<span data-ttu-id="59073-121">ToolStrip コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="59073-121">ToolStrip Control Overview</span></span>](toolstrip-control-overview-windows-forms.md)
- [<span data-ttu-id="59073-122">ToolStrip コントロールのアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="59073-122">ToolStrip Control Architecture</span></span>](toolstrip-control-architecture.md)
- [<span data-ttu-id="59073-123">ToolStrip テクノロジの概要</span><span class="sxs-lookup"><span data-stu-id="59073-123">ToolStrip Technology Summary</span></span>](toolstrip-technology-summary.md)
