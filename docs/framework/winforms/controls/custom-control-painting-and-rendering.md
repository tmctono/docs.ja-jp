---
title: コントロールのカスタム描画およびレンダリング
ms.date: 03/30/2017
helpviewer_keywords:
- custom controls [Windows Forms], rendering
- custom controls [Windows Forms], painting
- user controls [Windows Forms], painting
ms.assetid: a09dbf76-0966-4cbf-a66a-2083ba98e068
ms.openlocfilehash: ec9002ffa4a7e2c82f59d52344764a01afe4c568
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62011485"
---
# <a name="custom-control-painting-and-rendering"></a><span data-ttu-id="6b0cb-102">コントロールのカスタム描画およびレンダリング</span><span class="sxs-lookup"><span data-stu-id="6b0cb-102">Custom Control Painting and Rendering</span></span>
<span data-ttu-id="6b0cb-103">コントロールのカスタム描画では、.NET Framework で簡単、多くの複雑なタスクの 1 つです。</span><span class="sxs-lookup"><span data-stu-id="6b0cb-103">Custom painting of controls is one of the many complicated tasks made easy by the .NET Framework.</span></span> <span data-ttu-id="6b0cb-104">カスタム コントロールを作成するときは、コントロールの外観に関する多くのオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="6b0cb-104">When authoring a custom control, you have many options regarding your control's graphical appearance.</span></span> <span data-ttu-id="6b0cb-105">継承するコントロールを作成している場合、 `Control`、により、コントロールはそのグラフィカル表現を表示するためにコードを提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6b0cb-105">If you are authoring a control that inherits from the `Control`, you must provide code that allows your control to render its graphical representation.</span></span> <span data-ttu-id="6b0cb-106">継承することによって、ユーザー コントロールを作成するかどうかは、 `UserControl`、継承は、Windows フォーム コントロールのいずれかでは、標準のグラフィカル表示をオーバーライドしてグラフィックス コードを指定します。</span><span class="sxs-lookup"><span data-stu-id="6b0cb-106">If you are creating a user control by inheriting from the `UserControl`, or are inheriting from one of the Windows Forms controls, you may override the standard graphical representation and provide your own graphics code.</span></span> <span data-ttu-id="6b0cb-107">カスタムの内在コントロールのレンダリングを提供するかどうか、`UserControl`を作成する、オプションが制限されますがも、さまざまなコントロールとアプリケーションのグラフィカル表現を許可します。</span><span class="sxs-lookup"><span data-stu-id="6b0cb-107">If you want to provide custom rendering for the constituent controls of a `UserControl` you are authoring, your options become more limited, but still allow a wide range of graphical possibilities for your controls and applications.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6b0cb-108">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="6b0cb-108">In This Section</span></span>  
 [<span data-ttu-id="6b0cb-109">Windows フォーム コントロールのレンダリング</span><span class="sxs-lookup"><span data-stu-id="6b0cb-109">Rendering a Windows Forms Control</span></span>](rendering-a-windows-forms-control.md)  
 <span data-ttu-id="6b0cb-110">コントロールの表示ロジックをプログラミングする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="6b0cb-110">Shows how to program the logic that displays a control.</span></span>  
  
 [<span data-ttu-id="6b0cb-111">ユーザー描画コントロール</span><span class="sxs-lookup"><span data-stu-id="6b0cb-111">User-Drawn Controls</span></span>](user-drawn-controls.md)  
 <span data-ttu-id="6b0cb-112">書き込みと、コントロールのレンダリング コードをオーバーライドするための手順の概要を示します。</span><span class="sxs-lookup"><span data-stu-id="6b0cb-112">Gives an overview of the steps involved in writing and overriding rendering code for your control.</span></span>  
  
 [<span data-ttu-id="6b0cb-113">内在コントロール</span><span class="sxs-lookup"><span data-stu-id="6b0cb-113">Constituent Controls</span></span>](constituent-controls.md)  
 <span data-ttu-id="6b0cb-114">ユーザー コントロールとフォームの内在コントロールのカスタム レンダリング コードを実装する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="6b0cb-114">Describes how to implement custom rendering code for constituent controls in your user controls and forms.</span></span>  
  
 [<span data-ttu-id="6b0cb-115">方法: 実行時にコントロールを非表示にします。</span><span class="sxs-lookup"><span data-stu-id="6b0cb-115">How to: Make Your Control Invisible at Run Time</span></span>](how-to-make-your-control-invisible-at-run-time.md)  
 <span data-ttu-id="6b0cb-116">使用する方法を示しています、<xref:System.Windows.Forms.Control.Visible%2A>プロパティを非表示とコントロールを表示します。</span><span class="sxs-lookup"><span data-stu-id="6b0cb-116">Shows how to use the <xref:System.Windows.Forms.Control.Visible%2A> property to hide and show a control.</span></span>  
  
 [<span data-ttu-id="6b0cb-117">方法: コントロールに透明な背景を提供します。</span><span class="sxs-lookup"><span data-stu-id="6b0cb-117">How to: Give Your Control a Transparent Background</span></span>](how-to-give-your-control-a-transparent-background.md)  
 <span data-ttu-id="6b0cb-118">使用する方法を示しています、<xref:System.Windows.Forms.Control.SetStyle%2A>が不透明、透明または部分的に透明な背景色を作成します。</span><span class="sxs-lookup"><span data-stu-id="6b0cb-118">Shows how to use the <xref:System.Windows.Forms.Control.SetStyle%2A> method to create a background color that is opaque, transparent, or partially transparent.</span></span>  
  
 [<span data-ttu-id="6b0cb-119">visual スタイルが使用されているコントロールのレンダリング</span><span class="sxs-lookup"><span data-stu-id="6b0cb-119">Rendering Controls with Visual Styles</span></span>](rendering-controls-with-visual-styles.md)  
 <span data-ttu-id="6b0cb-120">それらをサポートするオペレーティング システムで visual スタイルを使用してコントロールをレンダリングする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="6b0cb-120">Shows how to render controls using visual styles in operating systems that support them.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="6b0cb-121">参照</span><span class="sxs-lookup"><span data-stu-id="6b0cb-121">Reference</span></span>  
 <xref:System.Windows.Forms.Control>  
 <span data-ttu-id="6b0cb-122">このクラスについて説明し、すべてのメンバーへのリンクの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="6b0cb-122">Describes this class and has links to all of its members.</span></span>  
  
 <xref:System.Windows.Forms.UserControl>  
 <span data-ttu-id="6b0cb-123">このクラスについて説明し、すべてのメンバーへのリンクの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="6b0cb-123">Describes this class and has links to all of its members.</span></span>  
  
 <xref:System.Windows.Forms.Control.OnPaint%2A>  
 <span data-ttu-id="6b0cb-124">このメソッドをについて説明します。</span><span class="sxs-lookup"><span data-stu-id="6b0cb-124">Describes this method.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="6b0cb-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="6b0cb-125">Related Sections</span></span>  
 [<span data-ttu-id="6b0cb-126">方法: 描画の Graphics オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="6b0cb-126">How to: Create Graphics Objects for Drawing</span></span>](../advanced/how-to-create-graphics-objects-for-drawing.md)  
 <span data-ttu-id="6b0cb-127">紹介[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]詳細については、Visual Studio の観点と、リンクからのグラフィックス機能。</span><span class="sxs-lookup"><span data-stu-id="6b0cb-127">Introduces [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] graphics functionality from a Visual Studio perspective and gives links to more information.</span></span>  
  
 [<span data-ttu-id="6b0cb-128">さまざまなカスタム コントロール</span><span class="sxs-lookup"><span data-stu-id="6b0cb-128">Varieties of Custom Controls</span></span>](varieties-of-custom-controls.md)  
 <span data-ttu-id="6b0cb-129">作成できるカスタム コントロールの種類について説明します。</span><span class="sxs-lookup"><span data-stu-id="6b0cb-129">Describes the kinds of custom controls you can author.</span></span>
