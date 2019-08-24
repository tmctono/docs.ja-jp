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
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: e6da7318ba481af721a9220c8f71af2a18e764a3
ms.sourcegitcommit: 121ab70c1ebedba41d276e436dd2b1502748a49f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/24/2019
ms.locfileid: "70015787"
---
# <a name="how-to-provide-a-toolbox-bitmap-for-a-control"></a><span data-ttu-id="5a7c8-102">方法: コントロールにツールボックス ビットマップを指定する</span><span class="sxs-lookup"><span data-stu-id="5a7c8-102">How to: Provide a Toolbox Bitmap for a Control</span></span>

<span data-ttu-id="5a7c8-103">コントロールの特殊なアイコンを Visual Studio の**ツールボックス**に表示する場合は、 <xref:System.Drawing.ToolboxBitmapAttribute>を使用して特定のイメージを指定できます。</span><span class="sxs-lookup"><span data-stu-id="5a7c8-103">If you want to have a special icon for your control appear in the **Toolbox** of Visual Studio, you can specify a particular image by using the <xref:System.Drawing.ToolboxBitmapAttribute>.</span></span> <span data-ttu-id="5a7c8-104">このクラスは"*属性*"であり、他のクラスに追加できる特殊なクラスです。</span><span class="sxs-lookup"><span data-stu-id="5a7c8-104">This class is an *attribute*, a special kind of class you can attach to other classes.</span></span> <span data-ttu-id="5a7c8-105">属性の詳細については、[属性の概要 (Visual Basic)](../../../visual-basic/programming-guide/concepts/attributes/index.md)(Visual basic)  または、[属性 (C#)](../../../csharp/programming-guide/concepts/attributes/index.md) (C#) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5a7c8-105">For more information about attributes, see [Attributes overview (Visual Basic)](../../../visual-basic/programming-guide/concepts/attributes/index.md) for Visual Basic or [Attributes (C#)](../../../csharp/programming-guide/concepts/attributes/index.md) for C#.</span></span>

<span data-ttu-id="5a7c8-106">を使用すると、16x16ピクセルのビットマップのパスとファイル名を示す文字列を指定できます。<xref:System.Drawing.ToolboxBitmapAttribute></span><span class="sxs-lookup"><span data-stu-id="5a7c8-106">Using the <xref:System.Drawing.ToolboxBitmapAttribute>, you can specify a string that indicates the path and file name for a 16 by 16 pixel bitmap.</span></span> <span data-ttu-id="5a7c8-107">コントロールを**ツールボックス**に追加すると、このビットマップがコントロールの横に表示されます。</span><span class="sxs-lookup"><span data-stu-id="5a7c8-107">This bitmap then appears next to your control when added to the **Toolbox**.</span></span> <span data-ttu-id="5a7c8-108">また、を指定<xref:System.Type>することもできます。この場合、その型に関連付けられているビットマップが読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="5a7c8-108">You can also specify a <xref:System.Type>, in which case the bitmap associated with that type is loaded.</span></span> <span data-ttu-id="5a7c8-109"><xref:System.Type>と文字列の両方を指定した場合、コントロールは、 <xref:System.Type>パラメーターで指定された型を含むアセンブリ内の文字列パラメーターで指定された名前を持つイメージリソースを検索します。</span><span class="sxs-lookup"><span data-stu-id="5a7c8-109">If you specify both a <xref:System.Type> and a string, the control searches for an image resource with the name specified by the string parameter in the assembly containing the type specified by the <xref:System.Type> parameter.</span></span>

## <a name="to-specify-a-toolbox-bitmap-for-your-control"></a><span data-ttu-id="5a7c8-110">コントロールのツールボックス ビットマップを指定するには</span><span class="sxs-lookup"><span data-stu-id="5a7c8-110">To specify a Toolbox bitmap for your control</span></span>

1. <span data-ttu-id="5a7c8-111"><xref:System.Drawing.ToolboxBitmapAttribute>を、コントロールのクラス宣言の Visual Basic の `Class`キーワードの前、および Visual C# のクラス宣言の上に追加します。</span><span class="sxs-lookup"><span data-stu-id="5a7c8-111">Add the <xref:System.Drawing.ToolboxBitmapAttribute> to the class declaration of your control before the `Class` keyword for visual Basic, and above the class declaration for Visual C#.</span></span>

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

2. <span data-ttu-id="5a7c8-112">プロジェクトをリビルドします。</span><span class="sxs-lookup"><span data-stu-id="5a7c8-112">Rebuild the project.</span></span>

    > [!NOTE]
    > <span data-ttu-id="5a7c8-113">ビットマップは、自動生成されたコントロールとコンポーネントのツールボックスには表示されません。</span><span class="sxs-lookup"><span data-stu-id="5a7c8-113">The bitmap does not appear in the Toolbox for autogenerated controls and components.</span></span> <span data-ttu-id="5a7c8-114">ビットマップを表示するには、 **[ツールボックス アイテムの選択]** ダイアログ ボックスを使用してコントロールを再読み込みします。</span><span class="sxs-lookup"><span data-stu-id="5a7c8-114">To see the bitmap, reload the control by using the **Choose Toolbox Items** dialog box.</span></span> <span data-ttu-id="5a7c8-115">詳細については、「[チュートリアル:ツールボックスにカスタムコンポーネント](walkthrough-automatically-populating-the-toolbox-with-custom-components.md)を自動的に設定します。</span><span class="sxs-lookup"><span data-stu-id="5a7c8-115">For more information, see [Walkthrough: Automatically Populating the Toolbox with Custom Components](walkthrough-automatically-populating-the-toolbox-with-custom-components.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="5a7c8-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="5a7c8-116">See also</span></span>

- <xref:System.Drawing.ToolboxBitmapAttribute>
- [<span data-ttu-id="5a7c8-117">チュートリアル: ツールボックスへのカスタムコンポーネントの自動設定</span><span class="sxs-lookup"><span data-stu-id="5a7c8-117">Walkthrough: Automatically Populating the Toolbox with Custom Components</span></span>](walkthrough-automatically-populating-the-toolbox-with-custom-components.md)
- [<span data-ttu-id="5a7c8-118">デザイン時の Windows フォーム コントロールの開発</span><span class="sxs-lookup"><span data-stu-id="5a7c8-118">Developing Windows Forms Controls at Design Time</span></span>](developing-windows-forms-controls-at-design-time.md)
- [<span data-ttu-id="5a7c8-119">属性の概要 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5a7c8-119">Attributes overview (Visual Basic)</span></span>](../../../visual-basic/programming-guide/concepts/attributes/index.md)
- [<span data-ttu-id="5a7c8-120">属性 (C#)</span><span class="sxs-lookup"><span data-stu-id="5a7c8-120">Attributes (C#)</span></span>](../../../csharp/programming-guide/concepts/attributes/index.md)
