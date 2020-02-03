---
title: コントロールのプロパティ
ms.date: 03/30/2017
helpviewer_keywords:
- custom controls [Windows Forms], properties overview (using code)
- controls [Windows Forms], properties
- properties [Windows Forms]
ms.assetid: 2785279b-fb57-4937-8f6b-2050e475db6f
ms.openlocfilehash: 82bfab15cef4946661a37d2d88fbe1b797f3d816
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741182"
---
# <a name="properties-in-windows-forms-controls"></a><span data-ttu-id="dd634-102">Windows フォーム コントロールのプロパティ</span><span class="sxs-lookup"><span data-stu-id="dd634-102">Properties in Windows Forms Controls</span></span>
<span data-ttu-id="dd634-103">Windows フォームコントロールは、基本クラス <xref:System.Windows.Forms.Control?displayProperty=nameWithType>を形成する多くのプロパティを継承します。</span><span class="sxs-lookup"><span data-stu-id="dd634-103">A Windows Forms control inherits many properties form the base class <xref:System.Windows.Forms.Control?displayProperty=nameWithType>.</span></span> <span data-ttu-id="dd634-104">これには、<xref:System.Windows.Forms.Control.Font%2A>、<xref:System.Windows.Forms.Control.ForeColor%2A>、<xref:System.Windows.Forms.Control.BackColor%2A>、<xref:System.Windows.Forms.Control.Bounds%2A>、<xref:System.Windows.Forms.Control.ClientRectangle%2A>、<xref:System.Windows.Forms.Control.DisplayRectangle%2A>、<xref:System.Windows.Forms.Control.Enabled%2A>、<xref:System.Windows.Forms.Control.Focused%2A>、<xref:System.Windows.Forms.Control.Height%2A>、<xref:System.Windows.Forms.Control.Width%2A>、<xref:System.Windows.Forms.Control.Visible%2A>、<xref:System.Windows.Forms.Control.AutoSize%2A>などのプロパティが含まれます。</span><span class="sxs-lookup"><span data-stu-id="dd634-104">These include properties such as <xref:System.Windows.Forms.Control.Font%2A>, <xref:System.Windows.Forms.Control.ForeColor%2A>, <xref:System.Windows.Forms.Control.BackColor%2A>, <xref:System.Windows.Forms.Control.Bounds%2A>, <xref:System.Windows.Forms.Control.ClientRectangle%2A>, <xref:System.Windows.Forms.Control.DisplayRectangle%2A>, <xref:System.Windows.Forms.Control.Enabled%2A>, <xref:System.Windows.Forms.Control.Focused%2A>, <xref:System.Windows.Forms.Control.Height%2A>, <xref:System.Windows.Forms.Control.Width%2A>, <xref:System.Windows.Forms.Control.Visible%2A>, <xref:System.Windows.Forms.Control.AutoSize%2A>, and many others.</span></span> <span data-ttu-id="dd634-105">継承されたプロパティの詳細については、「<xref:System.Windows.Forms.Control?displayProperty=nameWithType>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dd634-105">For details about inherited properties, see <xref:System.Windows.Forms.Control?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="dd634-106">コントロールで継承されたプロパティをオーバーライドしたり、新しいプロパティを定義したりできます。</span><span class="sxs-lookup"><span data-stu-id="dd634-106">You can override inherited properties in your control as well as define new properties.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="dd634-107">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="dd634-107">In This Section</span></span>  
 [<span data-ttu-id="dd634-108">プロパティの定義</span><span class="sxs-lookup"><span data-stu-id="dd634-108">Defining a Property</span></span>](defining-a-property-in-windows-forms-controls.md)  
 <span data-ttu-id="dd634-109">カスタム コントロールまたはカスタム コンポーネントのプロパティを実装する方法と、そのプロパティをデザイン環境に統合する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="dd634-109">Shows how to implement a property for a custom control or component and shows how to integrate the property into the design environment.</span></span>  
  
 [<span data-ttu-id="dd634-110">ShouldSerialize メソッドと Reset メソッドによる既定値の定義</span><span class="sxs-lookup"><span data-stu-id="dd634-110">Defining Default Values with the ShouldSerialize and Reset Methods</span></span>](defining-default-values-with-the-shouldserialize-and-reset-methods.md)  
 <span data-ttu-id="dd634-111">カスタム コントロールまたはカスタム コンポーネントの既定のプロパティ値を定義する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="dd634-111">Shows how to define default property values for a custom control or component.</span></span>  
  
 [<span data-ttu-id="dd634-112">プロパティ変更イベント</span><span class="sxs-lookup"><span data-stu-id="dd634-112">Property-Changed Events</span></span>](property-changed-events.md)  
 <span data-ttu-id="dd634-113">プロパティ値が変更されたときに、プロパティ変更通知を有効にする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="dd634-113">Describes how to enable property-change notifications when a property value changes.</span></span>  
  
 [<span data-ttu-id="dd634-114">方法 : 内在コントロールのプロパティを公開する</span><span class="sxs-lookup"><span data-stu-id="dd634-114">How to: Expose Properties of Constituent Controls</span></span>](how-to-expose-properties-of-constituent-controls.md)  
 <span data-ttu-id="dd634-115">カスタム複合コントロール内の内在コントロールのプロパティを公開する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="dd634-115">Shows how to expose properties of constituent controls in a custom composite control.</span></span>  
  
 [<span data-ttu-id="dd634-116">カスタム コントロールへのメソッドの実装</span><span class="sxs-lookup"><span data-stu-id="dd634-116">Method Implementation in Custom Controls</span></span>](method-implementation-in-custom-controls.md)  
 <span data-ttu-id="dd634-117">カスタム コントロールおよびカスタム コンポーネントにメソッドを実装する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="dd634-117">Describes how to implement methods in custom controls and components.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="dd634-118">リファレンス</span><span class="sxs-lookup"><span data-stu-id="dd634-118">Reference</span></span>  
 <xref:System.Windows.Forms.UserControl>  
 <span data-ttu-id="dd634-119">複合コントロールを実装するための基本クラスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="dd634-119">Documents the base class for implementing composite controls.</span></span>  
  
 <xref:System.ComponentModel.TypeConverterAttribute>  
 <span data-ttu-id="dd634-120">カスタムプロパティ型に使用する <xref:System.ComponentModel.TypeConverter> を指定する属性を文書にします。</span><span class="sxs-lookup"><span data-stu-id="dd634-120">Documents the attribute that specifies the <xref:System.ComponentModel.TypeConverter> to use for a custom property type.</span></span>  
  
 <xref:System.ComponentModel.EditorAttribute>  
 <span data-ttu-id="dd634-121">カスタムプロパティに使用する <xref:System.Drawing.Design.UITypeEditor> を指定する属性を文書にします。</span><span class="sxs-lookup"><span data-stu-id="dd634-121">Documents the attribute that specifies the <xref:System.Drawing.Design.UITypeEditor> to use for a custom property.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="dd634-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="dd634-122">Related Sections</span></span>  
 [<span data-ttu-id="dd634-123">Windows フォーム コントロールの属性</span><span class="sxs-lookup"><span data-stu-id="dd634-123">Attributes in Windows Forms Controls</span></span>](attributes-in-windows-forms-controls.md)  
 <span data-ttu-id="dd634-124">カスタム コントロールとコンポーネントのプロパティや他のメンバーに適用できる属性について説明します。</span><span class="sxs-lookup"><span data-stu-id="dd634-124">Describes the attributes you can apply to properties or other members of your custom controls and components.</span></span>  
  
 <span data-ttu-id="dd634-125">[コンポーネントのデザイン時属性](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/tk67c2t8(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="dd634-125">[Design-Time Attributes for Components](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/tk67c2t8(v=vs.120))</span></span>  
 <span data-ttu-id="dd634-126">ビジュアル デザイナーでデザインするときに正しく表示されるようにコンポーネントとコントロールに適用するメタデータ属性の一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="dd634-126">Lists metadata attributes to apply to components and controls so that they are displayed correctly at design time in visual designers.</span></span>  
  
 <span data-ttu-id="dd634-127">[デザイン時サポートの拡張](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/37899azc(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="dd634-127">[Extending Design-Time Support](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/37899azc(v=vs.120))</span></span>  
 <span data-ttu-id="dd634-128">デザイン時サポートを提供するエディターやデザイナーなどのクラスを実装する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="dd634-128">Describes how to implement classes such as editors and designers that provide design-time support.</span></span>
