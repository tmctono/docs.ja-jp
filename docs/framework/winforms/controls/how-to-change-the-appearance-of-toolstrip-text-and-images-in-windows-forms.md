---
title: '方法: ToolStrip のテキストとイメージの外観を変更する'
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
ms.openlocfilehash: 7816e138e44554683c201895ece1f886ace8bfa6
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746601"
---
# <a name="how-to-change-the-appearance-of-toolstrip-text-and-images-in-windows-forms"></a><span data-ttu-id="12049-102">方法 : Windows フォーム内の ToolStrip テキストとイメージの外観を変更する</span><span class="sxs-lookup"><span data-stu-id="12049-102">How to: Change the Appearance of ToolStrip Text and Images in Windows Forms</span></span>
<span data-ttu-id="12049-103"><xref:System.Windows.Forms.ToolStripItem> にテキストと画像を表示するかどうか、およびそれら <xref:System.Windows.Forms.ToolStrip>を互いに相対的にどのように調整するかを制御できます。</span><span class="sxs-lookup"><span data-stu-id="12049-103">You can control whether text and images are displayed on a <xref:System.Windows.Forms.ToolStripItem> and how they are aligned relative to each other and the <xref:System.Windows.Forms.ToolStrip>.</span></span>  
  
### <a name="to-define-what-is-displayed-on-a-toolstripitem"></a><span data-ttu-id="12049-104">ToolStripItem に表示される内容を定義するには</span><span class="sxs-lookup"><span data-stu-id="12049-104">To define what is displayed on a ToolStripItem</span></span>  
  
- <span data-ttu-id="12049-105"><xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> プロパティを目的の値に設定します。</span><span class="sxs-lookup"><span data-stu-id="12049-105">Set the <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> property to the desired value.</span></span> <span data-ttu-id="12049-106">`Image`、`ImageAndText`、`None`、および `Text`の可能性があります。</span><span class="sxs-lookup"><span data-stu-id="12049-106">The possibilities are `Image`, `ImageAndText`, `None`, and `Text`.</span></span> <span data-ttu-id="12049-107">既定では、 `ImageAndText`です。</span><span class="sxs-lookup"><span data-stu-id="12049-107">The default is `ImageAndText`.</span></span>  
  
    ```vb  
    ToolStripButton2.DisplayStyle = _  
        System.Windows.Forms.ToolStripItemDisplayStyle.Image  
    ```  
  
    ```csharp  
    toolStripButton2.DisplayStyle = System.Windows.Forms.ToolStripItemDisplayStyle.Image;  
    ```  
  
### <a name="to-align-text-on-a-toolstripitem"></a><span data-ttu-id="12049-108">ToolStripItem のテキストを揃えるには</span><span class="sxs-lookup"><span data-stu-id="12049-108">To align text on a ToolStripItem</span></span>  
  
- <span data-ttu-id="12049-109"><xref:System.Windows.Forms.ToolStripItem.TextAlign%2A> プロパティを目的の値に設定します。</span><span class="sxs-lookup"><span data-stu-id="12049-109">Set the <xref:System.Windows.Forms.ToolStripItem.TextAlign%2A> property to the desired value.</span></span> <span data-ttu-id="12049-110">Left、center、right を使用すると、上下左右の任意の組み合わせを使用できます。</span><span class="sxs-lookup"><span data-stu-id="12049-110">The possibilities are any combination of top, middle, and bottom with left, center, and right.</span></span> <span data-ttu-id="12049-111">既定では、 `MiddleCenter`です。</span><span class="sxs-lookup"><span data-stu-id="12049-111">The default is `MiddleCenter`.</span></span>  
  
    ```vb  
    ToolStripSplitButton1.TextAlign = _  
        System.Drawing.ContentAlignment.MiddleRight  
    ```  
  
    ```csharp  
    toolStripSplitButton1.TextAlign = System.Drawing.ContentAlignment.MiddleRight;  
    ```  
  
### <a name="to-align-an-image-on-a-toolstripitem"></a><span data-ttu-id="12049-112">ToolStripItem 上のイメージを整列させるには</span><span class="sxs-lookup"><span data-stu-id="12049-112">To align an image on a ToolStripItem</span></span>  
  
- <span data-ttu-id="12049-113"><xref:System.Windows.Forms.ToolStripItem.ImageAlign%2A> プロパティを目的の値に設定します。</span><span class="sxs-lookup"><span data-stu-id="12049-113">Set the <xref:System.Windows.Forms.ToolStripItem.ImageAlign%2A> property to the desired value.</span></span> <span data-ttu-id="12049-114">Left、center、right を使用すると、上下左右の任意の組み合わせを使用できます。</span><span class="sxs-lookup"><span data-stu-id="12049-114">The possibilities are any combination of top, middle, and bottom with left, center, and right.</span></span> <span data-ttu-id="12049-115">既定では、 `MiddleLeft`です。</span><span class="sxs-lookup"><span data-stu-id="12049-115">The default is `MiddleLeft`.</span></span>  
  
    ```vb  
    ToolStripSplitButton1.ImageAlign = _  
        System.Drawing.ContentAlignment.MiddleRight  
    ```  
  
    ```csharp  
    toolStripSplitButton1.ImageAlign = System.Drawing.ContentAlignment.MiddleRight;  
    ```  
  
### <a name="to-define-how-toolstripitem-text-and-images-are-displayed-relative-to-each-other"></a><span data-ttu-id="12049-116">ToolStripItem テキストと画像を相互に相対的に表示する方法を定義するには</span><span class="sxs-lookup"><span data-stu-id="12049-116">To define how ToolStripItem text and images are displayed relative to each other</span></span>  
  
- <span data-ttu-id="12049-117"><xref:System.Windows.Forms.ToolStripItem.TextImageRelation%2A> プロパティを目的の値に設定します。</span><span class="sxs-lookup"><span data-stu-id="12049-117">Set the <xref:System.Windows.Forms.ToolStripItem.TextImageRelation%2A> property to the desired value.</span></span> <span data-ttu-id="12049-118">設定できる値は、`ImageAboveText`、`ImageBeforeText`、`Overlay`、`TextAboveImage`、および `TextBeforeImage` です。</span><span class="sxs-lookup"><span data-stu-id="12049-118">The possibilities are `ImageAboveText`, `ImageBeforeText`, `Overlay`, `TextAboveImage`, and `TextBeforeImage`.</span></span> <span data-ttu-id="12049-119">既定では、 `ImageBeforeText`です。</span><span class="sxs-lookup"><span data-stu-id="12049-119">The default is `ImageBeforeText`.</span></span>  
  
    ```vb  
    ToolStripButton1.TextImageRelation = _  
        System.Windows.Forms.TextImageRelation.ImageAboveText  
    ```  
  
    ```csharp  
    toolStripButton1.TextImageRelation = System.Windows.Forms.TextImageRelation.ImageAboveText;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="12049-120">参照</span><span class="sxs-lookup"><span data-stu-id="12049-120">See also</span></span>

- <xref:System.Windows.Forms.ToolStrip>
- [<span data-ttu-id="12049-121">ToolStrip コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="12049-121">ToolStrip Control Overview</span></span>](toolstrip-control-overview-windows-forms.md)
- [<span data-ttu-id="12049-122">ToolStrip コントロールのアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="12049-122">ToolStrip Control Architecture</span></span>](toolstrip-control-architecture.md)
- [<span data-ttu-id="12049-123">ToolStrip テクノロジの概要</span><span class="sxs-lookup"><span data-stu-id="12049-123">ToolStrip Technology Summary</span></span>](toolstrip-technology-summary.md)
