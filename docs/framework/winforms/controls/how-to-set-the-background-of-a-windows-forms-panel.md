---
title: パネルの背景を設定する
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- background colors [Windows Forms], Windows Forms Panel controls
- background images [Windows Forms], Windows Forms Panel controls
- Panel control [Windows Forms], background
- colors [Windows Forms], Windows Forms Panel controls
ms.assetid: 096cbd8d-45cc-47b8-b1ef-a27f60ea8be0
ms.openlocfilehash: 36e552475334c25b9d5a6fafb82155c6ebcba266
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182105"
---
# <a name="how-to-set-the-background-of-a-windows-forms-panel"></a><span data-ttu-id="6d55f-102">方法 : Windows フォーム パネルの背景を設定する</span><span class="sxs-lookup"><span data-stu-id="6d55f-102">How to: Set the Background of a Windows Forms Panel</span></span>
<span data-ttu-id="6d55f-103">Windows フォーム<xref:System.Windows.Forms.Panel>コントロールでは、背景色と背景イメージの両方を表示できます。</span><span class="sxs-lookup"><span data-stu-id="6d55f-103">A Windows Forms <xref:System.Windows.Forms.Panel> control can display both a background color and a background image.</span></span> <span data-ttu-id="6d55f-104">この<xref:System.Windows.Forms.Control.BackColor%2A>プロパティは、ラベルやラジオ ボタンなど、含まれているコントロールの背景色を設定します。</span><span class="sxs-lookup"><span data-stu-id="6d55f-104">The <xref:System.Windows.Forms.Control.BackColor%2A> property sets the background color for the contained controls, such as labels and radio buttons.</span></span> <span data-ttu-id="6d55f-105">このプロパティ<xref:System.Windows.Forms.Control.BackgroundImage%2A>が設定されていない場合、<xref:System.Windows.Forms.Control.BackColor%2A>選択範囲はパネル全体に表示されます。</span><span class="sxs-lookup"><span data-stu-id="6d55f-105">If the <xref:System.Windows.Forms.Control.BackgroundImage%2A> property is not set, the <xref:System.Windows.Forms.Control.BackColor%2A> selection will fill the entire panel.</span></span> <span data-ttu-id="6d55f-106">プロパティが<xref:System.Windows.Forms.Control.BackgroundImage%2A>設定されている場合、含まれているコントロールの背後にイメージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6d55f-106">If the <xref:System.Windows.Forms.Control.BackgroundImage%2A> property is set, the image will be displayed behind the contained controls.</span></span>  
  
### <a name="to-set-the-background-programmatically"></a><span data-ttu-id="6d55f-107">プログラムで背景を設定するには</span><span class="sxs-lookup"><span data-stu-id="6d55f-107">To set the background programmatically</span></span>  
  
1. <span data-ttu-id="6d55f-108">パネルの<xref:System.Windows.Forms.Control.BackColor%2A>プロパティを type<xref:System.Drawing.Color?displayProperty=nameWithType>の値に設定します。</span><span class="sxs-lookup"><span data-stu-id="6d55f-108">Set the panel's <xref:System.Windows.Forms.Control.BackColor%2A> property to a value of type <xref:System.Drawing.Color?displayProperty=nameWithType>.</span></span>  
  
    ```vb  
    Panel1.BackColor = Color.AliceBlue  
    ```  
  
    ```csharp  
    panel1.BackColor = Color.AliceBlue;  
    ```  
  
    ```cpp  
    panel1->BackColor = Color::AliceBlue;  
    ```  
  
2. <span data-ttu-id="6d55f-109">クラスのメソッドを使用<xref:System.Windows.Forms.Control.BackgroundImage%2A>して、パネル<xref:System.Drawing.Image.FromFile%2A>のプロパティを<xref:System.Drawing.Image?displayProperty=nameWithType>設定します。</span><span class="sxs-lookup"><span data-stu-id="6d55f-109">Set the panel's <xref:System.Windows.Forms.Control.BackgroundImage%2A> property using the <xref:System.Drawing.Image.FromFile%2A> method of the <xref:System.Drawing.Image?displayProperty=nameWithType> class.</span></span>  
  
    ```vb  
    ' You should replace the bolded image
    ' in the sample below with an image of your own choosing.  
    Panel1.BackgroundImage = Image.FromFile _  
        (System.Environment.GetFolderPath _  
        (System.Environment.SpecialFolder.Personal) _  
        & "\Image.gif")  
    ```  
  
    ```csharp  
    // You should replace the bolded image
    // in the sample below with an image of your own choosing.  
    // Note the escape character used (@) when specifying the path.  
    panel1.BackgroundImage = Image.FromFile  
       (System.Environment.GetFolderPath  
       (System.Environment.SpecialFolder.Personal)  
       + @"\Image.gif");  
    ```  
  
    ```cpp  
    // You should replace the bolded image
    // in the sample below with an image of your own choosing.  
    panel1->BackgroundImage = Image::FromFile(String::Concat(  
       System::Environment::GetFolderPath  
       (System::Environment::SpecialFolder::Personal),  
       "\\Image.gif"));  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="6d55f-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="6d55f-110">See also</span></span>

- <xref:System.Windows.Forms.Control.BackColor%2A>
- <xref:System.Windows.Forms.Control.BackgroundImage%2A>
- [<span data-ttu-id="6d55f-111">Panel コントロール</span><span class="sxs-lookup"><span data-stu-id="6d55f-111">Panel Control</span></span>](panel-control-windows-forms.md)
- [<span data-ttu-id="6d55f-112">Panel コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="6d55f-112">Panel Control Overview</span></span>](panel-control-overview-windows-forms.md)
