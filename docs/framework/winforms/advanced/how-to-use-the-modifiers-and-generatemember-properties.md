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
ms.openlocfilehash: 3fbaaae53aa60f6356c3a8daa0513de86ef2dacb
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65211296"
---
# <a name="how-to-use-the-modifiers-and-generatemember-properties"></a><span data-ttu-id="bd79c-102">方法: Modifiers プロパティおよび GenerateMember プロパティを使用する</span><span class="sxs-lookup"><span data-stu-id="bd79c-102">How to: Use the Modifiers and GenerateMember Properties</span></span>

<span data-ttu-id="bd79c-103">2 つのプロパティが、デザイン環境によって提供される Windows フォームにコンポーネントを配置すると:`GenerateMember`と`Modifiers`します。</span><span class="sxs-lookup"><span data-stu-id="bd79c-103">When you place a component on a Windows Form, two properties are provided by the design environment: `GenerateMember` and `Modifiers`.</span></span> <span data-ttu-id="bd79c-104">`GenerateMember`プロパティは、Windows フォーム デザイナーでコンポーネントのメンバー変数を生成するときを指定します。</span><span class="sxs-lookup"><span data-stu-id="bd79c-104">The `GenerateMember` property specifies when the Windows Forms Designer generates a member variable for a component.</span></span> <span data-ttu-id="bd79c-105">`Modifiers`プロパティは、そのメンバー変数に割り当てられているアクセス修飾子。</span><span class="sxs-lookup"><span data-stu-id="bd79c-105">The `Modifiers` property is the access modifier assigned to that member variable.</span></span> <span data-ttu-id="bd79c-106">場合の値、`GenerateMember`プロパティは`false`の値、`Modifiers`プロパティは影響を与えません。</span><span class="sxs-lookup"><span data-stu-id="bd79c-106">If the value of the `GenerateMember` property is `false`, the value of the `Modifiers` property has no effect.</span></span>

## <a name="specify-whether-a-component-is-a-member-of-the-form"></a><span data-ttu-id="bd79c-107">コンポーネント フォームのメンバーであるかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="bd79c-107">Specify whether a component is a member of the form</span></span>

1. <span data-ttu-id="bd79c-108">Windows フォーム デザイナーでの Visual Studio では、フォームを開きます。</span><span class="sxs-lookup"><span data-stu-id="bd79c-108">In Visual Studio, in the Windows Forms Designer, open your form.</span></span>

2. <span data-ttu-id="bd79c-109">開く、**ツールボックス**、フォームで、3 つの配置と<xref:System.Windows.Forms.Button>コントロール。</span><span class="sxs-lookup"><span data-stu-id="bd79c-109">Open the **Toolbox**, and on the form, place three <xref:System.Windows.Forms.Button> controls.</span></span>

3. <span data-ttu-id="bd79c-110">設定、`GenerateMember`と`Modifiers`の各プロパティ<xref:System.Windows.Forms.Button>次の表に従ってコントロール。</span><span class="sxs-lookup"><span data-stu-id="bd79c-110">Set the `GenerateMember` and `Modifiers` properties for each <xref:System.Windows.Forms.Button> control according to the following table.</span></span>

    |<span data-ttu-id="bd79c-111">Button name</span><span class="sxs-lookup"><span data-stu-id="bd79c-111">Button name</span></span>|<span data-ttu-id="bd79c-112">GenerateMember 値</span><span class="sxs-lookup"><span data-stu-id="bd79c-112">GenerateMember value</span></span>|<span data-ttu-id="bd79c-113">修飾子の値</span><span class="sxs-lookup"><span data-stu-id="bd79c-113">Modifiers value</span></span>|
    |-----------------|--------------------------|---------------------|
    |`button1`|`true`|`private`|
    |`button2`|`true`|`protected`|
    |`button3`|`false`|<span data-ttu-id="bd79c-114">変更なし</span><span class="sxs-lookup"><span data-stu-id="bd79c-114">No change</span></span>|

4. <span data-ttu-id="bd79c-115">ソリューションをビルドします。</span><span class="sxs-lookup"><span data-stu-id="bd79c-115">Build the solution.</span></span>

5. <span data-ttu-id="bd79c-116">**ソリューション エクスプローラー**で、**[すべてのファイルを表示]** ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="bd79c-116">In **Solution Explorer**, click the **Show All Files** button.</span></span>

6. <span data-ttu-id="bd79c-117">開く、 **Form1**ノード、および、**コード エディター**、オープン、 **Form1.Designer.vb**または**Form1.Designer.cs**ファイル。</span><span class="sxs-lookup"><span data-stu-id="bd79c-117">Open the **Form1** node, and in the **Code Editor**,open the **Form1.Designer.vb** or **Form1.Designer.cs** file.</span></span> <span data-ttu-id="bd79c-118">このファイルには、Windows フォーム デザイナーによって出力されるコードが含まれています。</span><span class="sxs-lookup"><span data-stu-id="bd79c-118">This file contains the code emitted by the Windows Forms Designer.</span></span>

7. <span data-ttu-id="bd79c-119">3 つのボタンの宣言を探します。</span><span class="sxs-lookup"><span data-stu-id="bd79c-119">Find the declarations for the three buttons.</span></span> <span data-ttu-id="bd79c-120">次のコード例で指定された相違点を示しています、`GenerateMember`と`Modifiers`プロパティ。</span><span class="sxs-lookup"><span data-stu-id="bd79c-120">The following code example shows the differences specified by the `GenerateMember` and `Modifiers` properties.</span></span>

     [!code-csharp[System.Windows.Forms.GenerateMember#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.GenerateMember/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.GenerateMember#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.GenerateMember/VB/Form1.vb#3)]

     [!code-csharp[System.Windows.Forms.GenerateMember#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.GenerateMember/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.GenerateMember#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.GenerateMember/VB/Form1.vb#2)]

> [!NOTE]
> <span data-ttu-id="bd79c-121">既定では、Windows フォーム デザイナーによって、 `private` (`Friend` Visual basic) 修飾子などのコンテナー コントロールを<xref:System.Windows.Forms.Panel>します。</span><span class="sxs-lookup"><span data-stu-id="bd79c-121">By default, the Windows Forms Designer assigns the `private` (`Friend` in Visual Basic) modifier to container controls like <xref:System.Windows.Forms.Panel>.</span></span> <span data-ttu-id="bd79c-122">場合、ベース<xref:System.Windows.Forms.UserControl>または<xref:System.Windows.Forms.Form>がコンテナー コントロールでは、継承されたコントロールとフォーム内の新しい子を受け付けることができません。</span><span class="sxs-lookup"><span data-stu-id="bd79c-122">If your base <xref:System.Windows.Forms.UserControl> or <xref:System.Windows.Forms.Form> has a container control, it will not accept new children in inherited controls and forms.</span></span> <span data-ttu-id="bd79c-123">ソリューションは、基本のコンテナー コントロールの修飾子を変更する`protected`または`public`します。</span><span class="sxs-lookup"><span data-stu-id="bd79c-123">The solution is to change the modifier of the base container control to `protected` or `public`.</span></span>

## <a name="see-also"></a><span data-ttu-id="bd79c-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="bd79c-124">See also</span></span>

- <xref:System.Windows.Forms.Button>
- [<span data-ttu-id="bd79c-125">Windows フォームのビジュアルの継承</span><span class="sxs-lookup"><span data-stu-id="bd79c-125">Windows Forms Visual Inheritance</span></span>](windows-forms-visual-inheritance.md)
- [<span data-ttu-id="bd79c-126">チュートリアル: ビジュアル継承のデモンストレーション</span><span class="sxs-lookup"><span data-stu-id="bd79c-126">Walkthrough: Demonstrating Visual Inheritance</span></span>](walkthrough-demonstrating-visual-inheritance.md)
- [<span data-ttu-id="bd79c-127">方法: Windows フォームを継承する</span><span class="sxs-lookup"><span data-stu-id="bd79c-127">How to: Inherit Windows Forms</span></span>](how-to-inherit-windows-forms.md)
