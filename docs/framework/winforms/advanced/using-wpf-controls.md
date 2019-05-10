---
title: WPF コントロールの使用
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms Designer [Windows Forms], interoperability with WPF
- interoperability [WPF]
ms.assetid: 03c85dce-26ad-44cd-bc1d-8e0cb56de096
ms.openlocfilehash: 149a2da1303e6b801a439494254a416a38b145a7
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65211307"
---
# <a name="use-wpf-controls"></a><span data-ttu-id="6bdb9-102">WPF コントロールを使用します。</span><span class="sxs-lookup"><span data-stu-id="6bdb9-102">Use WPF controls</span></span>

<span data-ttu-id="6bdb9-103">Windows フォーム ベースのアプリケーションでは、Windows Presentation Foundation (WPF) コントロールを使用できます。</span><span class="sxs-lookup"><span data-stu-id="6bdb9-103">You can use Windows Presentation Foundation (WPF) controls in your Windows Forms-based applications.</span></span> <span data-ttu-id="6bdb9-104">これらは、2 つの異なるビュー テクノロジが円滑に相互運用します。</span><span class="sxs-lookup"><span data-stu-id="6bdb9-104">Although these are two different view technologies, they interoperate smoothly.</span></span>

<span data-ttu-id="6bdb9-105">Visual Studio での Windows フォーム デザイナーでは、Windows Presentation Foundation コントロールをホストするためのビジュアル デ ザイン環境を提供します。</span><span class="sxs-lookup"><span data-stu-id="6bdb9-105">The Windows Forms Designer in Visual Studio provides a visual design environment for hosting Windows Presentation Foundation controls.</span></span> <span data-ttu-id="6bdb9-106">WPF コントロールがという特殊な Windows フォーム コントロールによってホストされている<xref:System.Windows.Forms.Integration.ElementHost>します。</span><span class="sxs-lookup"><span data-stu-id="6bdb9-106">A WPF control is hosted by a special Windows Forms control that is named <xref:System.Windows.Forms.Integration.ElementHost>.</span></span> <span data-ttu-id="6bdb9-107">このコントロールは、フォームのレイアウトに参加して、キーボードとマウスのメッセージを受信する WPF コントロールを使用します。</span><span class="sxs-lookup"><span data-stu-id="6bdb9-107">This control enables the WPF control to participate in the form's layout and to receive keyboard and mouse messages.</span></span> <span data-ttu-id="6bdb9-108">デザイン時に配置することができます、<xref:System.Windows.Forms.Integration.ElementHost>任意の Windows フォーム コントロールと同様に制御します。</span><span class="sxs-lookup"><span data-stu-id="6bdb9-108">At design time, you can arrange the <xref:System.Windows.Forms.Integration.ElementHost> control just as you would any Windows Forms control.</span></span>

<span data-ttu-id="6bdb9-109">Windows フォーム コントロールは WPF ベースのアプリケーションで使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="6bdb9-109">You can also use Windows Forms controls in your WPF-based applications.</span></span> <span data-ttu-id="6bdb9-110">詳細については、次を参照してください。 [Visual Studio で XAML をデザイン](/visualstudio/designers/designing-xaml-in-visual-studio)します。</span><span class="sxs-lookup"><span data-stu-id="6bdb9-110">For more information, see [Design XAML in Visual Studio](/visualstudio/designers/designing-xaml-in-visual-studio).</span></span>

## <a name="in-this-section"></a><span data-ttu-id="6bdb9-111">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="6bdb9-111">In This Section</span></span>

<span data-ttu-id="6bdb9-112">[方法: コピーして、デザイン時に ElementHost コントロールを貼り付ける](how-to-copy-and-paste-an-elementhost-control-at-design-time.md)\\</span><span class="sxs-lookup"><span data-stu-id="6bdb9-112">[How to: Copy and Paste an ElementHost Control at Design Time](how-to-copy-and-paste-an-elementhost-control-at-design-time.md)\\</span></span>
<span data-ttu-id="6bdb9-113">Windows フォーム上の Windows Presentation Foundation コントロールをコピーする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="6bdb9-113">Shows how to copy a Windows Presentation Foundation control on a Windows Form.</span></span>

<span data-ttu-id="6bdb9-114">[チュートリアル: デザイン時に Windows フォームでの WPF コンテンツの配置](walkthrough-arranging-wpf-content-on-windows-forms-at-design-time.md)\\</span><span class="sxs-lookup"><span data-stu-id="6bdb9-114">[Walkthrough: Arranging WPF Content on Windows Forms at Design Time](walkthrough-arranging-wpf-content-on-windows-forms-at-design-time.md)\\</span></span>
<span data-ttu-id="6bdb9-115">固定やスナップ線をなど、Windows フォームのレイアウト機能を使用して、Windows Presentation Foundation コントロールを配置する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="6bdb9-115">Shows how to use the Windows Forms layout features, such as anchoring and snaplines, to arrange Windows Presentation Foundation controls.</span></span>

<span data-ttu-id="6bdb9-116">[チュートリアル: デザイン時に Windows フォームで新しい WPF コンテンツを作成します。](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md)\\</span><span class="sxs-lookup"><span data-stu-id="6bdb9-116">[Walkthrough: Creating New WPF Content on Windows Forms at Design Time](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md)\\</span></span>
<span data-ttu-id="6bdb9-117">Windows フォーム ベースのアプリケーションで使用するための Windows Presentation Foundation コントロールを作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="6bdb9-117">Shows how to create a Windows Presentation Foundation control for use in your Windows Forms-based applications.</span></span>

<span data-ttu-id="6bdb9-118">[チュートリアル: デザイン時に Windows フォームでの WPF コンテンツの割り当てください。](walkthrough-assigning-wpf-content-on-windows-forms-at-design-time.md)\\</span><span class="sxs-lookup"><span data-stu-id="6bdb9-118">[Walkthrough: Assigning WPF Content on Windows Forms at Design Time](walkthrough-assigning-wpf-content-on-windows-forms-at-design-time.md)\\</span></span>
<span data-ttu-id="6bdb9-119">フォームに表示する Windows Presentation Foundation コントロールの種類を選択する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="6bdb9-119">Shows how to select the Windows Presentation Foundation control types you want to display on your form.</span></span>

<span data-ttu-id="6bdb9-120">[チュートリアル: WPF コンテンツのスタイル設定](walkthrough-styling-wpf-content.md)\\</span><span class="sxs-lookup"><span data-stu-id="6bdb9-120">[Walkthrough: Styling WPF Content](walkthrough-styling-wpf-content.md)\\</span></span>
<span data-ttu-id="6bdb9-121">Windows フォーム デザイナー間のワークフローを示しています、 [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)] Windows Presentation Foundation コントロールにスタイルを適用するためです。</span><span class="sxs-lookup"><span data-stu-id="6bdb9-121">Shows the workflow between the Windows Forms Designer and the [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)] for applying styles to Windows Presentation Foundation controls.</span></span>

## <a name="reference"></a><span data-ttu-id="6bdb9-122">参照</span><span class="sxs-lookup"><span data-stu-id="6bdb9-122">Reference</span></span>

<xref:System.Windows.Forms.Integration.ElementHost>\
<span data-ttu-id="6bdb9-123">Windows フォーム ベースのアプリケーションでホストの Windows Presentation Foundation コントロールに使用できるクラスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="6bdb9-123">Describes a class which you can use to host Windows Presentation Foundation controls in your Windows Forms-based applications.</span></span>

<xref:System.Windows.Forms.Integration.WindowsFormsHost>\
<span data-ttu-id="6bdb9-124">Windows フォーム コントロールをホストする Windows Presentation Foundation ベースのアプリケーションで使用できるクラスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="6bdb9-124">Describes a class which you can use to host Windows Forms controls in your Windows Presentation Foundation-based application.</span></span>

## <a name="related-sections"></a><span data-ttu-id="6bdb9-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="6bdb9-125">Related sections</span></span>

<span data-ttu-id="6bdb9-126">[移行と相互運用性](../../wpf/advanced/migration-and-interoperability.md)\\</span><span class="sxs-lookup"><span data-stu-id="6bdb9-126">[Migration and Interoperability](../../wpf/advanced/migration-and-interoperability.md)\\</span></span>
<span data-ttu-id="6bdb9-127">Windows Presentation Foundation と Windows フォーム テクノロジ間の相互運用をについて説明します。</span><span class="sxs-lookup"><span data-stu-id="6bdb9-127">Describes interoperation between the Windows Presentation Foundation and Windows Forms technologies.</span></span>

<span data-ttu-id="6bdb9-128">[Visual Studio で XAML の設計](/visualstudio/designers/designing-xaml-in-visual-studio)\\</span><span class="sxs-lookup"><span data-stu-id="6bdb9-128">[Design XAML in Visual Studio](/visualstudio/designers/designing-xaml-in-visual-studio)\\</span></span>
<span data-ttu-id="6bdb9-129">Visual Studio での Windows Presentation Foundation コントロールをデザインする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="6bdb9-129">Describes how to design Windows Presentation Foundation controls in Visual Studio.</span></span>
