---
title: チュートリアル:カスタム アニメーション ボタンの作成
ms.date: 03/30/2017
helpviewer_keywords:
- custom animated buttons [WPF]
- buttons [WPF]
- animation [WPF], buttons [WPF]
ms.assetid: e9532c72-460f-4898-9332-613fa21d746a
ms.openlocfilehash: 3c601641a0eb1024722b4f449f0ab23e54fe93dd
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62024470"
---
# <a name="walkthroughs-create-a-custom-animated-button"></a><span data-ttu-id="0a9df-102">チュートリアル:カスタム アニメーション ボタンの作成</span><span class="sxs-lookup"><span data-stu-id="0a9df-102">Walkthroughs: Create a Custom Animated Button</span></span>
<span data-ttu-id="0a9df-103">その名前からわかるように、Windows Presentation Foundation (WPF) はお客様のエクスペリエンスのリッチ プレゼンテーションを行う最適です。</span><span class="sxs-lookup"><span data-stu-id="0a9df-103">As its name suggests, Windows Presentation Foundation (WPF) is great for making rich presentation experiences for customers.</span></span> <span data-ttu-id="0a9df-104">これらのチュートリアルでは、(アニメーションを含む) ボタンの動作と外観をカスタマイズする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="0a9df-104">These walkthroughs show you how to customize the look and behavior of a button (including animations).</span></span> <span data-ttu-id="0a9df-105">このカスタマイズを行うスタイルとテンプレートを使用すると、このカスタム ボタンをアプリケーションで他のボタンに簡単に適用できます。</span><span class="sxs-lookup"><span data-stu-id="0a9df-105">This customization is done using a style and template so that you can apply this custom button easily to any buttons in your application.</span></span> <span data-ttu-id="0a9df-106">次の図はを作成してカスタマイズされたボタンを示しています。</span><span class="sxs-lookup"><span data-stu-id="0a9df-106">The following illustration shows the customized button that you will create.</span></span>  
  
 <span data-ttu-id="0a9df-107">![作成するカスタマイズされたボタン](./media/custom-button-blend-intro.jpg "custom_button_blend_Intro")</span><span class="sxs-lookup"><span data-stu-id="0a9df-107">![The customized button that you will create](./media/custom-button-blend-intro.jpg "custom_button_blend_Intro")</span></span>  
  
 <span data-ttu-id="0a9df-108">ボタンの外観を構成するベクター グラフィックスを使用して作成された[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="0a9df-108">The vector graphics that make up the appearance of the button are created by using [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span></span> [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] <span data-ttu-id="0a9df-109">強力で拡張可能な点は、HTML に似ています。</span><span class="sxs-lookup"><span data-stu-id="0a9df-109">is similar to HTML except it is more powerful and extensible.</span></span> [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] <span data-ttu-id="0a9df-110">Microsoft Visual Studio またはメモ帳を使用して手動で入力できます。 または Microsoft Expression Blend などのビジュアル デ ザイン ツールを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="0a9df-110">can be typed in manually using Microsoft Visual Studio or Notepad, or you can use a visual design tool such as Microsoft Expression Blend.</span></span> <span data-ttu-id="0a9df-111">Expression Blend では、基になる作成[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]コードは、両方のメソッドと同じグラフィックスを作成するようにします。</span><span class="sxs-lookup"><span data-stu-id="0a9df-111">Expression Blend works by creating underlying [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] code, so both methods create the same graphics.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="0a9df-112">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="0a9df-112">In This Section</span></span>  
 [<span data-ttu-id="0a9df-113">Microsoft Expression Blend を使用してボタンを作成する</span><span class="sxs-lookup"><span data-stu-id="0a9df-113">Create a Button by Using Microsoft Expression Blend</span></span>](walkthrough-create-a-button-by-using-microsoft-expression-blend.md)  
 <span data-ttu-id="0a9df-114">Expression Blend のデザイナーの機能を使用してカスタム動作をボタンを作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="0a9df-114">Demonstrates how to create buttons with custom behavior by using the designer features of Expression Blend.</span></span>  
  
 [<span data-ttu-id="0a9df-115">XAML を使用したボタンの作成</span><span class="sxs-lookup"><span data-stu-id="0a9df-115">Create a Button by Using XAML</span></span>](walkthrough-create-a-button-by-using-xaml.md)  
 <span data-ttu-id="0a9df-116">使用して、カスタム動作でボタンを作成する方法を示します[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]と Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="0a9df-116">Demonstrates how to create buttons with custom behavior by using [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] and Visual Studio.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="0a9df-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="0a9df-117">Related Sections</span></span>  
 [<span data-ttu-id="0a9df-118">スタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="0a9df-118">Styling and Templating</span></span>](styling-and-templating.md)  
 <span data-ttu-id="0a9df-119">スタイルとテンプレートを使用して、コントロールの動作と外観を決定する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="0a9df-119">Describes how styles and templates can be used to determine the appearance and behavior of controls.</span></span>  
  
 [<span data-ttu-id="0a9df-120">アニメーションの概要</span><span class="sxs-lookup"><span data-stu-id="0a9df-120">Animation Overview</span></span>](../graphics-multimedia/animation-overview.md)  
 <span data-ttu-id="0a9df-121">使用してオブジェクトをアニメーション化する方法について説明します、[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]アニメーションおよびタイミング システム。</span><span class="sxs-lookup"><span data-stu-id="0a9df-121">Describes how objects can be animated by using the [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] animation and timing system.</span></span>  
  
 [<span data-ttu-id="0a9df-122">純色およびグラデーションによる塗りつぶしの概要</span><span class="sxs-lookup"><span data-stu-id="0a9df-122">Painting with Solid Colors and Gradients Overview</span></span>](../graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)  
 <span data-ttu-id="0a9df-123">純色、線状グラデーション、および放射状グラデーションで塗りつぶすブラシ オブジェクトを使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="0a9df-123">Describes how to use brush objects to paint with solid colors, linear gradients, and radial gradients.</span></span>  
  
 [<span data-ttu-id="0a9df-124">ビットマップ効果の概要</span><span class="sxs-lookup"><span data-stu-id="0a9df-124">Bitmap Effects Overview</span></span>](../graphics-multimedia/bitmap-effects-overview.md)  
 <span data-ttu-id="0a9df-125">サポートされているビットマップ効果について説明します[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]に適用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="0a9df-125">Describes the bitmap effects supported by [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] and explains how to apply them.</span></span>
