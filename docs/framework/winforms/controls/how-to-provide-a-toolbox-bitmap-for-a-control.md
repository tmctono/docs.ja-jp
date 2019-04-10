---
title: '方法: コントロールにツールボックス ビットマップを指定する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Toolbox [Windows Forms], adding bitmaps for custom controls
- custom controls [Windows Forms], Toolbox bitmaps
- bitmaps [Windows Forms], custom controls
ms.assetid: 0ed0840a-616d-41ba-a27d-3573241932ad
ms.openlocfilehash: 7c26e00acd4278ced53ad29c748ac076e0215a23
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2019
ms.locfileid: "59337709"
---
# <a name="how-to-provide-a-toolbox-bitmap-for-a-control"></a><span data-ttu-id="c6c06-102">方法: コントロールにツールボックス ビットマップを指定する</span><span class="sxs-lookup"><span data-stu-id="c6c06-102">How to: Provide a Toolbox Bitmap for a Control</span></span>
<span data-ttu-id="c6c06-103">コントロールの特別なアイコンを表示する場合、**ツールボックス**、特定のイメージを使用して指定することができます、<xref:System.Drawing.ToolboxBitmapAttribute>します。</span><span class="sxs-lookup"><span data-stu-id="c6c06-103">If you want to have a special icon for your control appear in the **Toolbox**, you can specify a particular image by using the <xref:System.Drawing.ToolboxBitmapAttribute>.</span></span> <span data-ttu-id="c6c06-104">このクラスは "*属性*" であり、他のクラスに追加できる特殊なクラスです。</span><span class="sxs-lookup"><span data-stu-id="c6c06-104">This class is an *attribute*, a special kind of class you can attach to other classes.</span></span> <span data-ttu-id="c6c06-105">属性の詳細については、次を参照してください。[属性の概要 (Visual Basic)](../../../visual-basic/programming-guide/concepts/attributes/index.md) Visual basic または[属性 (c#)](../../../csharp/programming-guide/concepts/attributes/index.md) (C#)。</span><span class="sxs-lookup"><span data-stu-id="c6c06-105">For more information about attributes, see [Attributes overview (Visual Basic)](../../../visual-basic/programming-guide/concepts/attributes/index.md) for Visual Basic or [Attributes (C#)](../../../csharp/programming-guide/concepts/attributes/index.md) for C#.</span></span>  
  
 <span data-ttu-id="c6c06-106">使用して、 <xref:System.Drawing.ToolboxBitmapAttribute>16 で 16 ピクセルのビットマップのパスとファイル名を示す文字列を指定することができます。</span><span class="sxs-lookup"><span data-stu-id="c6c06-106">Using the <xref:System.Drawing.ToolboxBitmapAttribute>, you can specify a string that indicates the path and file name for a 16 by 16 pixel bitmap.</span></span> <span data-ttu-id="c6c06-107">コントロールを**ツールボックス**に追加すると、このビットマップがコントロールの横に表示されます。</span><span class="sxs-lookup"><span data-stu-id="c6c06-107">This bitmap then appears next to your control when added to the **Toolbox**.</span></span> <span data-ttu-id="c6c06-108">指定することも、 <xref:System.Type>、その種類に関連付けられたビットマップが読み込まれる場合。</span><span class="sxs-lookup"><span data-stu-id="c6c06-108">You can also specify a <xref:System.Type>, in which case the bitmap associated with that type is loaded.</span></span> <span data-ttu-id="c6c06-109">両方を指定する場合、<xref:System.Type>文字列、コントロールのイメージ リソースを検索で指定された型を含むアセンブリの文字列パラメーターで指定された名前と、<xref:System.Type>パラメーター。</span><span class="sxs-lookup"><span data-stu-id="c6c06-109">If you specify both a <xref:System.Type> and a string, the control searches for an image resource with the name specified by the string parameter in the assembly containing the type specified by the <xref:System.Type> parameter.</span></span>  
  
### <a name="to-specify-a-toolbox-bitmap-for-your-control"></a><span data-ttu-id="c6c06-110">コントロールのツールボックス ビットマップを指定するには</span><span class="sxs-lookup"><span data-stu-id="c6c06-110">To specify a Toolbox bitmap for your control</span></span>  
  
1. <span data-ttu-id="c6c06-111">追加、<xref:System.Drawing.ToolboxBitmapAttribute>前に、コントロールのクラス宣言に、 `Class` visual Basic、および Visual c# のクラスの宣言の上のキーワード。</span><span class="sxs-lookup"><span data-stu-id="c6c06-111">Add the <xref:System.Drawing.ToolboxBitmapAttribute> to the class declaration of your control before the `Class` keyword for visual Basic, and above the class declaration for Visual C#.</span></span>  
  
    ```vb  
    ' Specifies the bitmap associated with the Button type.  
    <ToolboxBitmap(GetType(Button))> Class MyControl1  
    ' Specifies a bitmap file.  
    End Class  
    <ToolboxBitmap("C:\Documents and Settings\Joe\MyPics\myImage.bmp")> _  
       Class MyControl2  
    End Class  
    ' Specifies a type that indicates the assembly to search, and the name   
    ' of an image resource to look for.  
    <ToolboxBitmap(GetType(MyControl), "MyControlBitmap")> Class MyControl  
    End Class  
    ```  
  
    ```csharp  
    // Specifies the bitmap associated with the Button type.  
    [ToolboxBitmap(typeof(Button))]  
    class MyControl1 : UserControl  
    {  
    }  
    // Specifies a bitmap file.  
    [ToolboxBitmap(@"C:\Documents and Settings\Joe\MyPics\myImage.bmp")]  
    class MyControl2 : UserControl  
    {  
    }  
    // Specifies a type that indicates the assembly to search, and the name   
    // of an image resource to look for.  
    [ToolboxBitmap(typeof(MyControl), "MyControlBitmap")]  
    class MyControl : UserControl  
    {  
    }  
    ```  
  
2. <span data-ttu-id="c6c06-112">プロジェクトをリビルドします。</span><span class="sxs-lookup"><span data-stu-id="c6c06-112">Rebuild the project.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c6c06-113">ビットマップは、自動生成されたコントロールとコンポーネントのツールボックスには表示されません。</span><span class="sxs-lookup"><span data-stu-id="c6c06-113">The bitmap does not appear in the Toolbox for autogenerated controls and components.</span></span> <span data-ttu-id="c6c06-114">ビットマップを表示するには、**[ツールボックス アイテムの選択]** ダイアログ ボックスを使用してコントロールを再読み込みします。</span><span class="sxs-lookup"><span data-stu-id="c6c06-114">To see the bitmap, reload the control by using the **Choose Toolbox Items** dialog box.</span></span> <span data-ttu-id="c6c06-115">詳細については、「[チュートリアル:カスタム コンポーネントでツールボックスが自動的に入力](walkthrough-automatically-populating-the-toolbox-with-custom-components.md)します。</span><span class="sxs-lookup"><span data-stu-id="c6c06-115">For more information, see [Walkthrough: Automatically Populating the Toolbox with Custom Components](walkthrough-automatically-populating-the-toolbox-with-custom-components.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6c06-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="c6c06-116">See also</span></span>

- <xref:System.Drawing.ToolboxBitmapAttribute>
- [<span data-ttu-id="c6c06-117">チュートリアル: ツールボックスへのカスタム コンポーネントの自動設定</span><span class="sxs-lookup"><span data-stu-id="c6c06-117">Walkthrough: Automatically Populating the Toolbox with Custom Components</span></span>](walkthrough-automatically-populating-the-toolbox-with-custom-components.md)
- [<span data-ttu-id="c6c06-118">デザイン時の Windows フォーム コントロールの開発</span><span class="sxs-lookup"><span data-stu-id="c6c06-118">Developing Windows Forms Controls at Design Time</span></span>](developing-windows-forms-controls-at-design-time.md)
- [<span data-ttu-id="c6c06-119">属性の概要 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c6c06-119">Attributes overview (Visual Basic)</span></span>](../../../visual-basic/programming-guide/concepts/attributes/index.md)
- [<span data-ttu-id="c6c06-120">属性 (C#)</span><span class="sxs-lookup"><span data-stu-id="c6c06-120">Attributes (C#)</span></span>](../../../csharp/programming-guide/concepts/attributes/index.md)
