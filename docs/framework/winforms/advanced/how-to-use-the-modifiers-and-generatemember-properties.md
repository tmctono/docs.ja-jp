---
title: '方法: Modifiers プロパティおよび GenerateMember プロパティを使用する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
f1_keywords:
- Designer_GenerateMember
- Designer_Modifiers
helpviewer_keywords:
- base forms
- inheritance [Windows Forms], forms
- inherited forms [Windows Forms], Windows Forms
- inherited forms
- form inheritance
- Windows Forms, inheritance
ms.assetid: 3381a5e4-e1a3-44e2-a765-a0b758937b85
ms.openlocfilehash: 6194ef288bd43267c2b00fa6d7c6250e90b37c75
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61778860"
---
# <a name="how-to-use-the-modifiers-and-generatemember-properties"></a><span data-ttu-id="0971b-102">方法: Modifiers プロパティおよび GenerateMember プロパティを使用する</span><span class="sxs-lookup"><span data-stu-id="0971b-102">How to: Use the Modifiers and GenerateMember Properties</span></span>
<span data-ttu-id="0971b-103">2 つのプロパティが、デザイン環境によって提供される Windows フォームにコンポーネントを配置すると:`GenerateMember`と`Modifiers`します。</span><span class="sxs-lookup"><span data-stu-id="0971b-103">When you place a component on a Windows Form, two properties are provided by the design environment: `GenerateMember` and `Modifiers`.</span></span> <span data-ttu-id="0971b-104">`GenerateMember`プロパティは、Windows フォーム デザイナーでコンポーネントのメンバー変数を生成するときを指定します。</span><span class="sxs-lookup"><span data-stu-id="0971b-104">The `GenerateMember` property specifies when the Windows Forms Designer generates a member variable for a component.</span></span> <span data-ttu-id="0971b-105">`Modifiers`プロパティは、そのメンバー変数に割り当てられているアクセス修飾子。</span><span class="sxs-lookup"><span data-stu-id="0971b-105">The `Modifiers` property is the access modifier assigned to that member variable.</span></span> <span data-ttu-id="0971b-106">場合の値、`GenerateMember`プロパティは`false`の値、`Modifiers`プロパティは影響を与えません。</span><span class="sxs-lookup"><span data-stu-id="0971b-106">If the value of the `GenerateMember` property is `false`, the value of the `Modifiers` property has no effect.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0971b-107">実際に画面に表示されるダイアログ ボックスとメニュー コマンドは、アクティブな設定またはエディションによっては、ヘルプの説明と異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="0971b-107">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="0971b-108">設定を変更するには、 **[ツール]** メニューの **[設定のインポートとエクスポート]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0971b-108">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="0971b-109">詳細については、「[Visual Studio IDE のカスタマイズ](/visualstudio/ide/personalizing-the-visual-studio-ide)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0971b-109">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-specify-whether-a-component-is-a-member-of-the-form"></a><span data-ttu-id="0971b-110">コンポーネント フォームのメンバーであるかどうかを指定するには</span><span class="sxs-lookup"><span data-stu-id="0971b-110">To specify whether a component is a member of the form</span></span>  
  
1. <span data-ttu-id="0971b-111">Windows フォーム デザイナーでフォームを開きます。</span><span class="sxs-lookup"><span data-stu-id="0971b-111">In the Windows Forms Designer, open your form.</span></span>  
  
2. <span data-ttu-id="0971b-112">開く、**ツールボックス**、フォームで、3 つの配置と<xref:System.Windows.Forms.Button>コントロール。</span><span class="sxs-lookup"><span data-stu-id="0971b-112">Open the **Toolbox**, and on the form, place three <xref:System.Windows.Forms.Button> controls.</span></span>  
  
3. <span data-ttu-id="0971b-113">設定、`GenerateMember`と`Modifiers`の各プロパティ<xref:System.Windows.Forms.Button>次の表に従ってコントロール。</span><span class="sxs-lookup"><span data-stu-id="0971b-113">Set the `GenerateMember` and `Modifiers` properties for each <xref:System.Windows.Forms.Button> control according to the following table.</span></span>  
  
    |<span data-ttu-id="0971b-114">Button name</span><span class="sxs-lookup"><span data-stu-id="0971b-114">Button name</span></span>|<span data-ttu-id="0971b-115">GenerateMember 値</span><span class="sxs-lookup"><span data-stu-id="0971b-115">GenerateMember value</span></span>|<span data-ttu-id="0971b-116">修飾子の値</span><span class="sxs-lookup"><span data-stu-id="0971b-116">Modifiers value</span></span>|  
    |-----------------|--------------------------|---------------------|  
    |`button1`|`true`|`private`|  
    |`button2`|`true`|`protected`|  
    |`button3`|`false`|<span data-ttu-id="0971b-117">変更なし</span><span class="sxs-lookup"><span data-stu-id="0971b-117">No change</span></span>|  
  
4. <span data-ttu-id="0971b-118">ソリューションをビルドします。</span><span class="sxs-lookup"><span data-stu-id="0971b-118">Build the solution.</span></span>  
  
5. <span data-ttu-id="0971b-119">**ソリューション エクスプローラー**で、**[すべてのファイルを表示]** ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="0971b-119">In **Solution Explorer**, click the **Show All Files** button.</span></span>  
  
6. <span data-ttu-id="0971b-120">開く、 **Form1**ノード、および、**コード エディター**、オープン、 **Form1.Designer.vb**または**Form1.Designer.cs**ファイル。</span><span class="sxs-lookup"><span data-stu-id="0971b-120">Open the **Form1** node, and in the **Code Editor**,open the **Form1.Designer.vb** or **Form1.Designer.cs** file.</span></span> <span data-ttu-id="0971b-121">このファイルには、Windows フォーム デザイナーによって出力されるコードが含まれています。</span><span class="sxs-lookup"><span data-stu-id="0971b-121">This file contains the code emitted by the Windows Forms Designer.</span></span>  
  
7. <span data-ttu-id="0971b-122">3 つのボタンの宣言を探します。</span><span class="sxs-lookup"><span data-stu-id="0971b-122">Find the declarations for the three buttons.</span></span> <span data-ttu-id="0971b-123">次のコード例で指定された相違点を示しています、`GenerateMember`と`Modifiers`プロパティ。</span><span class="sxs-lookup"><span data-stu-id="0971b-123">The following code example shows the differences specified by the `GenerateMember` and `Modifiers` properties.</span></span>  
  
     [!code-csharp[System.Windows.Forms.GenerateMember#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.GenerateMember/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.GenerateMember#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.GenerateMember/VB/Form1.vb#3)]  
  
     [!code-csharp[System.Windows.Forms.GenerateMember#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.GenerateMember/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.GenerateMember#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.GenerateMember/VB/Form1.vb#2)]  
  
> [!NOTE]
>  <span data-ttu-id="0971b-124">既定では、Windows フォーム デザイナーによって、 `private` (`Friend` Visual basic) 修飾子などのコンテナー コントロールを<xref:System.Windows.Forms.Panel>します。</span><span class="sxs-lookup"><span data-stu-id="0971b-124">By default, the Windows Forms Designer assigns the `private` (`Friend` in Visual Basic) modifier to container controls like <xref:System.Windows.Forms.Panel>.</span></span> <span data-ttu-id="0971b-125">場合、ベース<xref:System.Windows.Forms.UserControl>または<xref:System.Windows.Forms.Form>がコンテナー コントロールでは、継承されたコントロールとフォーム内の新しい子を受け付けることができません。</span><span class="sxs-lookup"><span data-stu-id="0971b-125">If your base <xref:System.Windows.Forms.UserControl> or <xref:System.Windows.Forms.Form> has a container control, it will not accept new children in inherited controls and forms.</span></span> <span data-ttu-id="0971b-126">ソリューションは、基本のコンテナー コントロールの修飾子を変更する`protected`または`public`します。</span><span class="sxs-lookup"><span data-stu-id="0971b-126">The solution is to change the modifier of the base container control to `protected` or `public`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0971b-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="0971b-127">See also</span></span>

- <xref:System.Windows.Forms.Button>
- [<span data-ttu-id="0971b-128">Windows フォームのビジュアルの継承</span><span class="sxs-lookup"><span data-stu-id="0971b-128">Windows Forms Visual Inheritance</span></span>](windows-forms-visual-inheritance.md)
- [<span data-ttu-id="0971b-129">チュートリアル: ビジュアル継承のデモンストレーション</span><span class="sxs-lookup"><span data-stu-id="0971b-129">Walkthrough: Demonstrating Visual Inheritance</span></span>](walkthrough-demonstrating-visual-inheritance.md)
- [<span data-ttu-id="0971b-130">方法: Windows フォームを継承する</span><span class="sxs-lookup"><span data-stu-id="0971b-130">How to: Inherit Windows Forms</span></span>](how-to-inherit-windows-forms.md)
