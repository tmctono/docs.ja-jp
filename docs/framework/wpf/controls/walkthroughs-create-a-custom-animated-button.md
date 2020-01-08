---
title: 'チュートリアル : カスタム アニメーション ボタンの作成'
ms.date: 03/30/2017
helpviewer_keywords:
- custom animated buttons [WPF]
- buttons [WPF]
- animation [WPF], buttons [WPF]
ms.assetid: e9532c72-460f-4898-9332-613fa21d746a
ms.openlocfilehash: 0f881c19516eb42a71e6cd91d612caf8f5cf7b5e
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/03/2020
ms.locfileid: "75636186"
---
# <a name="walkthroughs-create-a-custom-animated-button"></a><span data-ttu-id="4ac7d-102">チュートリアル : カスタム アニメーション ボタンの作成</span><span class="sxs-lookup"><span data-stu-id="4ac7d-102">Walkthroughs: Create a Custom Animated Button</span></span>
<span data-ttu-id="4ac7d-103">名前が示すように、Windows Presentation Foundation (WPF) は、お客様に豊富なプレゼンテーションエクスペリエンスを提供するために適しています。</span><span class="sxs-lookup"><span data-stu-id="4ac7d-103">As its name suggests, Windows Presentation Foundation (WPF) is great for making rich presentation experiences for customers.</span></span> <span data-ttu-id="4ac7d-104">これらのチュートリアルでは、ボタン (アニメーションを含む) の外観と動作をカスタマイズする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="4ac7d-104">These walkthroughs show you how to customize the look and behavior of a button (including animations).</span></span> <span data-ttu-id="4ac7d-105">このカスタマイズはスタイルとテンプレートを使用して行います。これにより、このカスタムボタンをアプリケーションの任意のボタンに簡単に適用できます。</span><span class="sxs-lookup"><span data-stu-id="4ac7d-105">This customization is done using a style and template so that you can apply this custom button easily to any buttons in your application.</span></span> <span data-ttu-id="4ac7d-106">次の図は、作成するカスタマイズされたボタンを示しています。</span><span class="sxs-lookup"><span data-stu-id="4ac7d-106">The following illustration shows the customized button that you will create.</span></span>

 <span data-ttu-id="4ac7d-107">![作成するカスタマイズされたボタン](./media/custom-button-blend-intro.jpg "custom_button_blend_Intro")</span><span class="sxs-lookup"><span data-stu-id="4ac7d-107">![The customized button that you will create](./media/custom-button-blend-intro.jpg "custom_button_blend_Intro")</span></span>

 <span data-ttu-id="4ac7d-108">ボタンの外観を構成するベクターグラフィックスは、[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]を使用して作成されます。</span><span class="sxs-lookup"><span data-stu-id="4ac7d-108">The vector graphics that make up the appearance of the button are created by using [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span></span> [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] <span data-ttu-id="4ac7d-109">は HTML に似ていますが、より強力で拡張可能です。</span><span class="sxs-lookup"><span data-stu-id="4ac7d-109">is similar to HTML except it is more powerful and extensible.</span></span> [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] <span data-ttu-id="4ac7d-110">は、Visual Studio またはメモ帳を使用して手動で入力することも、Blend for Visual Studio などのビジュアルデザインツールを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="4ac7d-110">can be typed in manually using Visual Studio or Notepad, or you can use a visual design tool such as Blend for Visual Studio.</span></span> <span data-ttu-id="4ac7d-111">Blend は、基になる XAML コードを作成することによって機能するため、どちらの方法でも同じグラフィックスが作成されます。</span><span class="sxs-lookup"><span data-stu-id="4ac7d-111">Blend works by creating underlying XAML code, so both methods create the same graphics.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="4ac7d-112">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="4ac7d-112">In This Section</span></span>
 <span data-ttu-id="4ac7d-113">[Microsoft Expression Blend を使用してボタンを作成](walkthrough-create-a-button-by-using-microsoft-expression-blend.md)するExpression Blend のデザイナー機能を使用して、カスタム動作のボタンを作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="4ac7d-113">[Create a Button by Using Microsoft Expression Blend](walkthrough-create-a-button-by-using-microsoft-expression-blend.md) Demonstrates how to create buttons with custom behavior by using the designer features of Expression Blend.</span></span>

 <span data-ttu-id="4ac7d-114">[XAML を使用してボタンを作成](walkthrough-create-a-button-by-using-xaml.md)する[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] と Visual Studio を使用して、カスタム動作のボタンを作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="4ac7d-114">[Create a Button by Using XAML](walkthrough-create-a-button-by-using-xaml.md) Demonstrates how to create buttons with custom behavior by using [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] and Visual Studio.</span></span>

## <a name="related-sections"></a><span data-ttu-id="4ac7d-115">関連セクション</span><span class="sxs-lookup"><span data-stu-id="4ac7d-115">Related Sections</span></span>
 <span data-ttu-id="4ac7d-116">[スタイルとテンプレート](../../../desktop-wpf/fundamentals/styles-templates-overview.md)スタイルとテンプレートを使用して、コントロールの外観と動作を決定する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="4ac7d-116">[Styling and Templating](../../../desktop-wpf/fundamentals/styles-templates-overview.md) Describes how styles and templates can be used to determine the appearance and behavior of controls.</span></span>

 <span data-ttu-id="4ac7d-117">[アニメーションの概要](../graphics-multimedia/animation-overview.md)WPF アニメーションとタイミングシステムを使用してオブジェクトをアニメーション化する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="4ac7d-117">[Animation Overview](../graphics-multimedia/animation-overview.md) Describes how objects can be animated by using the WPF animation and timing system.</span></span>

 <span data-ttu-id="4ac7d-118">[純色とグラデーションによる塗りつぶしの概要](../graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)ブラシオブジェクトを使用して、純色、線状グラデーション、および放射状グラデーションで描画する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="4ac7d-118">[Painting with Solid Colors and Gradients Overview](../graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md) Describes how to use brush objects to paint with solid colors, linear gradients, and radial gradients.</span></span>

 <span data-ttu-id="4ac7d-119">[ビットマップ効果の概要](../graphics-multimedia/bitmap-effects-overview.md)WPF でサポートされるビットマップ効果について説明し、それらを適用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="4ac7d-119">[Bitmap Effects Overview](../graphics-multimedia/bitmap-effects-overview.md) Describes the bitmap effects supported by WPF and explains how to apply them.</span></span>
