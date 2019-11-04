---
title: Freezable オブジェクトの概要
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Freezable objects [WPF], description
- unfreezing Freezable objects [WPF]
- classes [WPF], Freezable
ms.assetid: 89c71692-4f43-4057-b611-67c6a8a863a2
ms.openlocfilehash: 755240859829042e9790b9c89e47bb7a2013ceef
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460452"
---
# <a name="freezable-objects-overview"></a><span data-ttu-id="77e44-102">Freezable オブジェクトの概要</span><span class="sxs-lookup"><span data-stu-id="77e44-102">Freezable Objects Overview</span></span>

<span data-ttu-id="77e44-103">このトピックでは、<xref:System.Windows.Freezable> オブジェクトを効果的に使用および作成する方法について説明します。これにより、アプリケーションのパフォーマンスを向上させるための特別な機能が提供されます。</span><span class="sxs-lookup"><span data-stu-id="77e44-103">This topic describes how to effectively use and create <xref:System.Windows.Freezable> objects, which provide special features that can help improve application performance.</span></span> <span data-ttu-id="77e44-104">Freezable オブジェクトの例としては、ブラシ、ペン、変換、ジオメトリ、アニメーションなどがあります。</span><span class="sxs-lookup"><span data-stu-id="77e44-104">Examples of freezable objects include brushes, pens, transformations, geometries, and animations.</span></span>

<a name="whatisafreezable"></a>

## <a name="what-is-a-freezable"></a><span data-ttu-id="77e44-105">Freezable とは何ですか。</span><span class="sxs-lookup"><span data-stu-id="77e44-105">What Is a Freezable?</span></span>

<span data-ttu-id="77e44-106"><xref:System.Windows.Freezable> は、固定されていない2つの状態を持つ特殊な種類のオブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="77e44-106">A <xref:System.Windows.Freezable> is a special type of object that has two states: unfrozen and frozen.</span></span> <span data-ttu-id="77e44-107">固定されていない場合、<xref:System.Windows.Freezable> は他のオブジェクトと同様に動作するように見えます。</span><span class="sxs-lookup"><span data-stu-id="77e44-107">When unfrozen, a <xref:System.Windows.Freezable> appears to behave like any other object.</span></span> <span data-ttu-id="77e44-108">固定されていない場合は、<xref:System.Windows.Freezable> を変更できなくなります。</span><span class="sxs-lookup"><span data-stu-id="77e44-108">When frozen, a <xref:System.Windows.Freezable> can no longer be modified.</span></span>

<span data-ttu-id="77e44-109"><xref:System.Windows.Freezable> には、オブジェクトに対する変更をオブザーバーに通知するための <xref:System.Windows.Freezable.Changed> イベントが用意されています。</span><span class="sxs-lookup"><span data-stu-id="77e44-109">A <xref:System.Windows.Freezable> provides a <xref:System.Windows.Freezable.Changed> event to notify observers of any modifications to the object.</span></span> <span data-ttu-id="77e44-110"><xref:System.Windows.Freezable> を固定すると、変更通知のリソースを消費する必要がなくなるため、パフォーマンスが向上します。</span><span class="sxs-lookup"><span data-stu-id="77e44-110">Freezing a <xref:System.Windows.Freezable> can improve its performance, because it no longer needs to spend resources on change notifications.</span></span> <span data-ttu-id="77e44-111">凍結された <xref:System.Windows.Freezable> はスレッド間で共有することもできますが、固定されていない <xref:System.Windows.Freezable> は使用できません。</span><span class="sxs-lookup"><span data-stu-id="77e44-111">A frozen <xref:System.Windows.Freezable> can also be shared across threads, while an unfrozen <xref:System.Windows.Freezable> cannot.</span></span>

<span data-ttu-id="77e44-112"><xref:System.Windows.Freezable> クラスには多くのアプリケーションがありますが、[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 内の <xref:System.Windows.Freezable> のオブジェクトのほとんどは、グラフィックスサブシステムに関連しています。</span><span class="sxs-lookup"><span data-stu-id="77e44-112">Although the <xref:System.Windows.Freezable> class has many applications, most <xref:System.Windows.Freezable> objects in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] are related to the graphics sub-system.</span></span>

<span data-ttu-id="77e44-113"><xref:System.Windows.Freezable> クラスを使用すると、特定のグラフィックスシステムオブジェクトを簡単に使用できるようになり、アプリケーションのパフォーマンスを向上させることができます。</span><span class="sxs-lookup"><span data-stu-id="77e44-113">The <xref:System.Windows.Freezable> class makes it easier to use certain graphics system objects and can help improve application performance.</span></span> <span data-ttu-id="77e44-114"><xref:System.Windows.Freezable> から継承する型の例には、<xref:System.Windows.Media.Brush>、<xref:System.Windows.Media.Transform>、および <xref:System.Windows.Media.Geometry> クラスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="77e44-114">Examples of types that inherit from <xref:System.Windows.Freezable> include the <xref:System.Windows.Media.Brush>, <xref:System.Windows.Media.Transform>, and <xref:System.Windows.Media.Geometry> classes.</span></span> <span data-ttu-id="77e44-115">アンマネージリソースが含まれているため、システムはこれらのオブジェクトを監視して変更する必要があり、元のオブジェクトに変更があった場合に対応するアンマネージリソースを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="77e44-115">Because they contain unmanaged resources, the system must monitor these objects for modifications, and then update their corresponding unmanaged resources when there is a change to the original object.</span></span> <span data-ttu-id="77e44-116">グラフィックスシステムオブジェクトを実際に変更していない場合でも、オブジェクトを変更する場合は、そのリソースを監視する必要があります。</span><span class="sxs-lookup"><span data-stu-id="77e44-116">Even if you don't actually modify a graphics system object, the system must still spend some of its resources monitoring the object, in case you do change it.</span></span>

<span data-ttu-id="77e44-117">たとえば、<xref:System.Windows.Media.SolidColorBrush> ブラシを作成し、それを使用してボタンの背景を描画するとします。</span><span class="sxs-lookup"><span data-stu-id="77e44-117">For example, suppose you create a <xref:System.Windows.Media.SolidColorBrush> brush and use it to paint the background of a button.</span></span>

[!code-csharp[freezablesample_procedural#FrozenExamplePart1](~/samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#frozenexamplepart1)]
[!code-vb[freezablesample_procedural#FrozenExamplePart1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#frozenexamplepart1)]

<span data-ttu-id="77e44-118">ボタンがレンダリングされると、[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] グラフィックスサブシステムは、指定した情報を使用して、ピクセルのグループを描画し、ボタンの外観を作成します。</span><span class="sxs-lookup"><span data-stu-id="77e44-118">When the button is rendered, the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] graphics sub-system uses the information you provided to paint a group of pixels to create the appearance of a button.</span></span> <span data-ttu-id="77e44-119">単色ブラシを使用してボタンを描画する方法を記述していますが、純色ブラシは実際には描画を行いません。</span><span class="sxs-lookup"><span data-stu-id="77e44-119">Although you used a solid color brush to describe how the button should be painted, your solid color brush doesn't actually do the painting.</span></span> <span data-ttu-id="77e44-120">グラフィックスシステムでは、ボタンとブラシ用の高速で低レベルのオブジェクトが生成されます。これは、実際に画面に表示されるオブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="77e44-120">The graphics system generates fast, low-level objects for the button and the brush, and it is those objects that actually appear on the screen.</span></span>

<span data-ttu-id="77e44-121">ブラシを変更する場合は、それらの下位レベルのオブジェクトを再生成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="77e44-121">If you were to modify the brush, those low-level objects would have to be regenerated.</span></span> <span data-ttu-id="77e44-122">Freezable クラスは、ブラシが、それに対応する生成された低レベルのオブジェクトを検索し、変更されたときにそれらを更新する機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="77e44-122">The freezable class is what gives a brush the ability to find its corresponding generated, low-level objects and to update them when it changes.</span></span> <span data-ttu-id="77e44-123">この機能が有効になっている場合、ブラシは "凍結解除" と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="77e44-123">When this ability is enabled, the brush is said to be "unfrozen."</span></span>

<span data-ttu-id="77e44-124">Freezable の <xref:System.Windows.Freezable.Freeze%2A> メソッドを使用すると、この自己更新機能を無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="77e44-124">A freezable's <xref:System.Windows.Freezable.Freeze%2A> method enables you to disable this self-updating ability.</span></span> <span data-ttu-id="77e44-125">このメソッドを使用して、ブラシが "フリーズ" されるか、変更不可能になるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="77e44-125">You can use this method to make the brush become "frozen," or unmodifiable.</span></span>

> [!NOTE]
> <span data-ttu-id="77e44-126">すべての Freezable オブジェクトを固定することはできません。</span><span class="sxs-lookup"><span data-stu-id="77e44-126">Not every Freezable object can be frozen.</span></span> <span data-ttu-id="77e44-127"><xref:System.InvalidOperationException>がスローされないようにするには、Freezable オブジェクトの <xref:System.Windows.Freezable.CanFreeze%2A> プロパティの値を調べて、凍結を試行する前に固定できるかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="77e44-127">To avoid throwing an <xref:System.InvalidOperationException>, check the value of the Freezable object's <xref:System.Windows.Freezable.CanFreeze%2A> property to determine whether it can be frozen before attempting to freeze it.</span></span>

[!code-csharp[freezablesample_procedural#FrozenExamplePart2](~/samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#frozenexamplepart2)]
[!code-vb[freezablesample_procedural#FrozenExamplePart2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#frozenexamplepart2)]

<span data-ttu-id="77e44-128">Freezable を変更する必要がなくなった場合は、固定するとパフォーマンス上の利点が得られます。</span><span class="sxs-lookup"><span data-stu-id="77e44-128">When you no longer need to modify a freezable, freezing it provides performance benefits.</span></span> <span data-ttu-id="77e44-129">この例でブラシをフリーズさせた場合、グラフィックスシステムは、変更を監視する必要がなくなります。</span><span class="sxs-lookup"><span data-stu-id="77e44-129">If you were to freeze the brush in this example, the graphics system would no longer need to monitor it for changes.</span></span> <span data-ttu-id="77e44-130">また、グラフィックスシステムは、ブラシが変更されないことを認識しているため、他の最適化を行うこともできます。</span><span class="sxs-lookup"><span data-stu-id="77e44-130">The graphics system can also make other optimizations, because it knows the brush won't change.</span></span>

> [!NOTE]
> <span data-ttu-id="77e44-131">便宜上、freezable オブジェクトは、明示的に固定しない限り、凍結されたままになります。</span><span class="sxs-lookup"><span data-stu-id="77e44-131">For convenience, freezable objects remain unfrozen unless you explicitly freeze them.</span></span>

<a name="frozenfreezables"></a>

## <a name="using-freezables"></a><span data-ttu-id="77e44-132">Freezable の使用</span><span class="sxs-lookup"><span data-stu-id="77e44-132">Using Freezables</span></span>

<span data-ttu-id="77e44-133">凍結されていない freezable の使用は、他の種類のオブジェクトを使用するのと似ています。</span><span class="sxs-lookup"><span data-stu-id="77e44-133">Using an unfrozen freezable is like using any other type of object.</span></span> <span data-ttu-id="77e44-134">次の例では、ボタンの背景を描画するために使用された <xref:System.Windows.Media.SolidColorBrush> の色が黄色から赤に変更されています。</span><span class="sxs-lookup"><span data-stu-id="77e44-134">In the following example, the color of a <xref:System.Windows.Media.SolidColorBrush> is changed from yellow to red after it's used to paint the background of a button.</span></span> <span data-ttu-id="77e44-135">グラフィックスシステムはバックグラウンドで動作し、次に画面が更新されたときにボタンを黄色から赤に自動的に変更します。</span><span class="sxs-lookup"><span data-stu-id="77e44-135">The graphics system works behind the scenes to automatically change the button from yellow to red the next time the screen is refreshed.</span></span>

[!code-csharp[freezablesample_procedural#UnFrozenExampleShort](~/samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#unfrozenexampleshort)]
[!code-vb[freezablesample_procedural#UnFrozenExampleShort](~/samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#unfrozenexampleshort)]

### <a name="freezing-a-freezable"></a><span data-ttu-id="77e44-136">Freezable の凍結</span><span class="sxs-lookup"><span data-stu-id="77e44-136">Freezing a Freezable</span></span>

<span data-ttu-id="77e44-137"><xref:System.Windows.Freezable> 変更不可能な状態にするには、その <xref:System.Windows.Freezable.Freeze%2A> メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="77e44-137">To make a <xref:System.Windows.Freezable> unmodifiable, you call its <xref:System.Windows.Freezable.Freeze%2A> method.</span></span> <span data-ttu-id="77e44-138">Freezable オブジェクトを含むオブジェクトを固定すると、それらのオブジェクトも固定されます。</span><span class="sxs-lookup"><span data-stu-id="77e44-138">When you freeze an object that contains freezable objects, those objects are frozen as well.</span></span> <span data-ttu-id="77e44-139">たとえば、<xref:System.Windows.Media.PathGeometry>を固定すると、その中に含まれる図形とセグメントも固定されます。</span><span class="sxs-lookup"><span data-stu-id="77e44-139">For example, if you freeze a <xref:System.Windows.Media.PathGeometry>, the figures and segments it contains would be frozen too.</span></span>

<span data-ttu-id="77e44-140">次のいずれかに該当する場合、Freezable をフリーズする**ことはできません**。</span><span class="sxs-lookup"><span data-stu-id="77e44-140">A Freezable **can't** be frozen if any of the following are true:</span></span>

- <span data-ttu-id="77e44-141">アニメーション化されたプロパティまたはデータバインドされたプロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="77e44-141">It has animated or data bound properties.</span></span>

- <span data-ttu-id="77e44-142">動的リソースによって設定されるプロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="77e44-142">It has properties set by a dynamic resource.</span></span> <span data-ttu-id="77e44-143">(動的リソースの詳細については、「 [XAML リソース](../../../desktop-wpf/fundamentals/xaml-resources-define.md)」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="77e44-143">(See the [XAML Resources](../../../desktop-wpf/fundamentals/xaml-resources-define.md) for more information about dynamic resources.)</span></span>

- <span data-ttu-id="77e44-144">これには、固定できない <xref:System.Windows.Freezable> サブオブジェクトが含まれます。</span><span class="sxs-lookup"><span data-stu-id="77e44-144">It contains <xref:System.Windows.Freezable> sub-objects that can't be frozen.</span></span>

<span data-ttu-id="77e44-145">これらの条件が false で、<xref:System.Windows.Freezable>を変更する予定がない場合は、前に説明したパフォーマンス上の利点を得るために、これらの条件を固定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="77e44-145">If these conditions are false, and you don't intend to modify the <xref:System.Windows.Freezable>, then you should freeze it to gain the performance benefits described earlier.</span></span>

<span data-ttu-id="77e44-146">Freezable の <xref:System.Windows.Freezable.Freeze%2A> メソッドを呼び出すと、変更できなくなります。</span><span class="sxs-lookup"><span data-stu-id="77e44-146">Once you call a freezable's <xref:System.Windows.Freezable.Freeze%2A> method, it can no longer be modified.</span></span> <span data-ttu-id="77e44-147">固定されたオブジェクトを変更しようとすると、<xref:System.InvalidOperationException> がスローされます。</span><span class="sxs-lookup"><span data-stu-id="77e44-147">Attempting to modify a frozen object causes an <xref:System.InvalidOperationException> to be thrown.</span></span> <span data-ttu-id="77e44-148">次のコードは、凍結された後にブラシを変更しようとしているため、例外をスローします。</span><span class="sxs-lookup"><span data-stu-id="77e44-148">The following code throws an exception, because we attempt to modify the brush after it's been frozen.</span></span>

[!code-csharp[freezablesample_procedural#ExceptionExample](~/samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#exceptionexample)]
[!code-vb[freezablesample_procedural#ExceptionExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#exceptionexample)]

<span data-ttu-id="77e44-149">この例外がスローされないようにするには、<xref:System.Windows.Freezable.IsFrozen%2A> メソッドを使用して、<xref:System.Windows.Freezable> が固定されているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="77e44-149">To avoid throwing this exception, you can use the <xref:System.Windows.Freezable.IsFrozen%2A> method to determine whether a <xref:System.Windows.Freezable> is frozen.</span></span>

[!code-csharp[freezablesample_procedural#CheckIsFrozenExample](~/samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#checkisfrozenexample)]
[!code-vb[freezablesample_procedural#CheckIsFrozenExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#checkisfrozenexample)]

<span data-ttu-id="77e44-150">前のコード例では、<xref:System.Windows.Freezable.Clone%2A> メソッドを使用して、固定されたオブジェクトで変更可能なコピーを作成しました。</span><span class="sxs-lookup"><span data-stu-id="77e44-150">In the preceding code example, a modifiable copy was made of a frozen object using the <xref:System.Windows.Freezable.Clone%2A> method.</span></span> <span data-ttu-id="77e44-151">次のセクションでは、複製の詳細について説明します。</span><span class="sxs-lookup"><span data-stu-id="77e44-151">The next section discusses cloning in more detail.</span></span>

> [!NOTE]
> <span data-ttu-id="77e44-152">フリーズした freezable はアニメーション化できないため、<xref:System.Windows.Media.Animation.Storyboard>でアニメーション化しようとすると、固定された <xref:System.Windows.Freezable> オブジェクトの変更可能な複製がアニメーションシステムによって自動的に作成されます。</span><span class="sxs-lookup"><span data-stu-id="77e44-152">Because a frozen freezable cannot be animated, the animation system will automatically create modifiable clones of frozen <xref:System.Windows.Freezable> objects when you try to animate them with a <xref:System.Windows.Media.Animation.Storyboard>.</span></span> <span data-ttu-id="77e44-153">複製によって発生するパフォーマンスのオーバーヘッドを回避するには、オブジェクトをアニメーション化する場合は、固定されていないままにします。</span><span class="sxs-lookup"><span data-stu-id="77e44-153">To eliminate the performance overhead caused by cloning, leave an object unfrozen if you intend to animate it.</span></span> <span data-ttu-id="77e44-154">ストーリーボードを使用したアニメーション化の詳細については、「[ストーリーボードの概要](../graphics-multimedia/storyboards-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="77e44-154">For more information about animating with storyboards, see the [Storyboards Overview](../graphics-multimedia/storyboards-overview.md).</span></span>

### <a name="freezing-from-markup"></a><span data-ttu-id="77e44-155">マークアップからの凍結</span><span class="sxs-lookup"><span data-stu-id="77e44-155">Freezing from Markup</span></span>

<span data-ttu-id="77e44-156">マークアップで宣言された <xref:System.Windows.Freezable> オブジェクトを固定するには、`PresentationOptions:Freeze` 属性を使用します。</span><span class="sxs-lookup"><span data-stu-id="77e44-156">To freeze a <xref:System.Windows.Freezable> object declared in markup, you use the `PresentationOptions:Freeze` attribute.</span></span> <span data-ttu-id="77e44-157">次の例では、<xref:System.Windows.Media.SolidColorBrush> がページリソースとして宣言され、固定されています。</span><span class="sxs-lookup"><span data-stu-id="77e44-157">In the following example, a <xref:System.Windows.Media.SolidColorBrush> is declared as a page resource and frozen.</span></span> <span data-ttu-id="77e44-158">次に、ボタンの背景を設定するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="77e44-158">It is then used to set the background of a button.</span></span>

[!code-xaml[FreezableSample#FreezeFromMarkupWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FreezableSample/CS/FreezeFromMarkupExample.xaml#freezefrommarkupwholepage)]

<span data-ttu-id="77e44-159">`Freeze` 属性を使用するには、[プレゼンテーションオプション] [名前空間: `http://schemas.microsoft.com/winfx/2006/xaml/presentation/options`] にマップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="77e44-159">To use the `Freeze` attribute, you must map to the presentation options namespace: `http://schemas.microsoft.com/winfx/2006/xaml/presentation/options`.</span></span> <span data-ttu-id="77e44-160">`PresentationOptions` は、この名前空間のマッピングに推奨されるプレフィックスです。</span><span class="sxs-lookup"><span data-stu-id="77e44-160">`PresentationOptions` is the recommended prefix for mapping this namespace:</span></span>

```xaml
xmlns:PresentationOptions="http://schemas.microsoft.com/winfx/2006/xaml/presentation/options"
```

<span data-ttu-id="77e44-161">すべての XAML リーダーがこの属性を認識しているわけではないため、 [mc: Ignorable 属性](mc-ignorable-attribute.md)を使用して `Presentation:Freeze` 属性を無視としてマークすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="77e44-161">Because not all XAML readers recognize this attribute, it's recommended that you use the [mc:Ignorable Attribute](mc-ignorable-attribute.md) to mark the `Presentation:Freeze` attribute as ignorable:</span></span>

```xaml
xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
mc:Ignorable="PresentationOptions"
```

<span data-ttu-id="77e44-162">詳細については、「 [mc: Ignorable 属性](mc-ignorable-attribute.md)」ページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="77e44-162">For more information, see the [mc:Ignorable Attribute](mc-ignorable-attribute.md) page.</span></span>

### <a name="unfreezing-a-freezable"></a><span data-ttu-id="77e44-163">Freezable の "固定解除"</span><span class="sxs-lookup"><span data-stu-id="77e44-163">"Unfreezing" a Freezable</span></span>

<span data-ttu-id="77e44-164">固定された <xref:System.Windows.Freezable> は、変更したり、凍結解除したりすることはできません。ただし、<xref:System.Windows.Freezable.Clone%2A> または <xref:System.Windows.Freezable.CloneCurrentValue%2A> 方法を使用して、凍結解除された複製を作成することができます。</span><span class="sxs-lookup"><span data-stu-id="77e44-164">Once frozen, a <xref:System.Windows.Freezable> can never be modified or unfrozen; however, you can create an unfrozen clone using the <xref:System.Windows.Freezable.Clone%2A> or <xref:System.Windows.Freezable.CloneCurrentValue%2A> method.</span></span>

<span data-ttu-id="77e44-165">次の例では、ボタンの背景がブラシで設定され、そのブラシが固定されています。</span><span class="sxs-lookup"><span data-stu-id="77e44-165">In the following example, the button's background is set with a brush and that brush is then frozen.</span></span> <span data-ttu-id="77e44-166">ブラシでは、<xref:System.Windows.Freezable.Clone%2A> メソッドを使用して、固定されていないコピーが作成されます。</span><span class="sxs-lookup"><span data-stu-id="77e44-166">An unfrozen copy is made of the brush using the <xref:System.Windows.Freezable.Clone%2A> method.</span></span> <span data-ttu-id="77e44-167">複製が変更され、ボタンの背景を黄色から赤に変更するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="77e44-167">The clone is modified and used to change the button's background from yellow to red.</span></span>

[!code-csharp[freezablesample_procedural#CloneExample](~/samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#cloneexample)]
[!code-vb[freezablesample_procedural#CloneExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#cloneexample)]

> [!NOTE]
> <span data-ttu-id="77e44-168">使用する複製方法に関係なく、アニメーションは新しい <xref:System.Windows.Freezable>にコピーされません。</span><span class="sxs-lookup"><span data-stu-id="77e44-168">Regardless of which clone method you use, animations are never copied to the new <xref:System.Windows.Freezable>.</span></span>

<span data-ttu-id="77e44-169"><xref:System.Windows.Freezable.Clone%2A> メソッドと <xref:System.Windows.Freezable.CloneCurrentValue%2A> メソッドは、freezable のディープコピーを作成します。</span><span class="sxs-lookup"><span data-stu-id="77e44-169">The <xref:System.Windows.Freezable.Clone%2A> and <xref:System.Windows.Freezable.CloneCurrentValue%2A> methods produce deep copies of the freezable.</span></span> <span data-ttu-id="77e44-170">Freezable に他のフリーズした freezable オブジェクトが含まれている場合は、それらも複製され、変更可能になります。</span><span class="sxs-lookup"><span data-stu-id="77e44-170">If the freezable contains other frozen freezable objects, they are also cloned and made modifiable.</span></span> <span data-ttu-id="77e44-171">たとえば、固定された <xref:System.Windows.Media.PathGeometry> を複製して変更可能にする場合、含まれる図形とセグメントもコピーされ、変更可能になります。</span><span class="sxs-lookup"><span data-stu-id="77e44-171">For example, if you clone a frozen <xref:System.Windows.Media.PathGeometry> to make it modifiable, the figures and segments it contains are also copied and made modifiable.</span></span>

<a name="createyourownfreezableclass"></a>

## <a name="creating-your-own-freezable-class"></a><span data-ttu-id="77e44-172">独自の Freezable クラスを作成する</span><span class="sxs-lookup"><span data-stu-id="77e44-172">Creating Your Own Freezable Class</span></span>

<span data-ttu-id="77e44-173"><xref:System.Windows.Freezable> から派生するクラスでは、次の機能が得られます。</span><span class="sxs-lookup"><span data-stu-id="77e44-173">A class that derives from <xref:System.Windows.Freezable> gains the following features.</span></span>

- <span data-ttu-id="77e44-174">特別な状態: 読み取り専用 (固定) と書き込み可能な状態。</span><span class="sxs-lookup"><span data-stu-id="77e44-174">Special states: a read-only (frozen) and a writable state.</span></span>

- <span data-ttu-id="77e44-175">スレッドセーフ: 固定された <xref:System.Windows.Freezable> は、スレッド間で共有できます。</span><span class="sxs-lookup"><span data-stu-id="77e44-175">Thread safety: a frozen <xref:System.Windows.Freezable> can be shared across threads.</span></span>

- <span data-ttu-id="77e44-176">詳細な変更通知: 他の <xref:System.Windows.DependencyObject>とは異なり、Freezable オブジェクトは、サブプロパティ値が変更したときに変更通知を提供します。</span><span class="sxs-lookup"><span data-stu-id="77e44-176">Detailed change notification: Unlike other <xref:System.Windows.DependencyObject>s, Freezable objects provide change notifications when sub-property values change.</span></span>

- <span data-ttu-id="77e44-177">簡単な複製: Freezable クラスには、ディープクローンを生成するいくつかのメソッドが既に実装されています。</span><span class="sxs-lookup"><span data-stu-id="77e44-177">Easy cloning: the Freezable class has already implemented several methods that produce deep clones.</span></span>

<span data-ttu-id="77e44-178"><xref:System.Windows.Freezable> は <xref:System.Windows.DependencyObject>の一種であるため、依存関係プロパティシステムを使用します。</span><span class="sxs-lookup"><span data-stu-id="77e44-178">A <xref:System.Windows.Freezable> is a type of <xref:System.Windows.DependencyObject>, and therefore uses the dependency property system.</span></span> <span data-ttu-id="77e44-179">クラスのプロパティは依存関係プロパティである必要はありませんが、依存関係プロパティを使用すると、記述する必要のあるコードの量が少なくなります。これは、<xref:System.Windows.Freezable> クラスが依存関係プロパティを念頭に置いて設計されているためです。</span><span class="sxs-lookup"><span data-stu-id="77e44-179">Your class properties don't have to be dependency properties, but using dependency properties will reduce the amount of code you have to write, because the <xref:System.Windows.Freezable> class was designed with dependency properties in mind.</span></span> <span data-ttu-id="77e44-180">依存関係プロパティシステムの詳細については、「[依存関係プロパティの概要](dependency-properties-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="77e44-180">For more information about the dependency property system, see the [Dependency Properties Overview](dependency-properties-overview.md).</span></span>

<span data-ttu-id="77e44-181">すべての <xref:System.Windows.Freezable> サブクラスは、<xref:System.Windows.Freezable.CreateInstanceCore%2A> メソッドをオーバーライドする必要があります。</span><span class="sxs-lookup"><span data-stu-id="77e44-181">Every <xref:System.Windows.Freezable> subclass must override the <xref:System.Windows.Freezable.CreateInstanceCore%2A> method.</span></span> <span data-ttu-id="77e44-182">クラスがすべてのデータに依存関係プロパティを使用している場合は、これで完了です。</span><span class="sxs-lookup"><span data-stu-id="77e44-182">If your class uses dependency properties for all its data, you're finished.</span></span>

<span data-ttu-id="77e44-183">クラスに依存関係のないプロパティのデータメンバーが含まれている場合は、次のメソッドもオーバーライドする必要があります。</span><span class="sxs-lookup"><span data-stu-id="77e44-183">If your class contains non-dependency property data members, you must also override the following methods:</span></span>

- <xref:System.Windows.Freezable.CloneCore%2A>

- <xref:System.Windows.Freezable.CloneCurrentValueCore%2A>

- <xref:System.Windows.Freezable.GetAsFrozenCore%2A>

- <xref:System.Windows.Freezable.GetCurrentValueAsFrozenCore%2A>

- <xref:System.Windows.Freezable.FreezeCore%2A>

<span data-ttu-id="77e44-184">また、依存関係プロパティでないデータメンバーにアクセスして書き込む場合は、次の規則に従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="77e44-184">You must also observe the following rules for accessing and writing to data members that are not dependency properties:</span></span>

- <span data-ttu-id="77e44-185">非依存関係プロパティのデータメンバーを読み取る API の先頭で、<xref:System.Windows.Freezable.ReadPreamble%2A> メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="77e44-185">At the beginning of any API that reads non-dependency property data members, call the <xref:System.Windows.Freezable.ReadPreamble%2A> method.</span></span>

- <span data-ttu-id="77e44-186">非依存プロパティのデータメンバーを書き込む API の先頭で、<xref:System.Windows.Freezable.WritePreamble%2A> メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="77e44-186">At the beginning of any API that writes non-dependency property data members, call the <xref:System.Windows.Freezable.WritePreamble%2A> method.</span></span> <span data-ttu-id="77e44-187">(API で <xref:System.Windows.Freezable.WritePreamble%2A> を呼び出した後に、依存関係のないプロパティのデータメンバーも読み取る場合は、<xref:System.Windows.Freezable.ReadPreamble%2A> を追加で呼び出す必要はありません)。</span><span class="sxs-lookup"><span data-stu-id="77e44-187">(Once you've called <xref:System.Windows.Freezable.WritePreamble%2A> in an API, you don't need to make an additional call to <xref:System.Windows.Freezable.ReadPreamble%2A> if you also read non-dependency property data members.)</span></span>

- <span data-ttu-id="77e44-188">非依存プロパティのデータメンバーに書き込むメソッドを終了する前に、<xref:System.Windows.Freezable.WritePostscript%2A> メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="77e44-188">Call the <xref:System.Windows.Freezable.WritePostscript%2A> method before exiting methods that write to non-dependency property data members.</span></span>

<span data-ttu-id="77e44-189">クラスに <xref:System.Windows.DependencyObject> オブジェクトである非依存プロパティデータメンバーが含まれている場合は、メンバーを `null`に設定している場合でも、値のいずれかを変更するたびに <xref:System.Windows.Freezable.OnFreezablePropertyChanged%2A> メソッドを呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="77e44-189">If your class contains non-dependency-property data members that are <xref:System.Windows.DependencyObject> objects, you must also call the <xref:System.Windows.Freezable.OnFreezablePropertyChanged%2A> method each time you change one of their values, even if you're setting the member to `null`.</span></span>

> [!NOTE]
> <span data-ttu-id="77e44-190">基本実装を呼び出すことで、オーバーライドする各 <xref:System.Windows.Freezable> メソッドを開始することが非常に重要です。</span><span class="sxs-lookup"><span data-stu-id="77e44-190">It's very important that you begin each <xref:System.Windows.Freezable> method you override with a call to the base implementation.</span></span>

<span data-ttu-id="77e44-191">カスタム <xref:System.Windows.Freezable> クラスの例については、「[カスタムアニメーションのサンプル](https://go.microsoft.com/fwlink/?LinkID=159981)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="77e44-191">For an example of a custom <xref:System.Windows.Freezable> class, see the [Custom Animation Sample](https://go.microsoft.com/fwlink/?LinkID=159981).</span></span>

## <a name="see-also"></a><span data-ttu-id="77e44-192">関連項目</span><span class="sxs-lookup"><span data-stu-id="77e44-192">See also</span></span>

- <xref:System.Windows.Freezable>
- [<span data-ttu-id="77e44-193">カスタム アニメーションのサンプル</span><span class="sxs-lookup"><span data-stu-id="77e44-193">Custom Animation Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=159981)
- [<span data-ttu-id="77e44-194">依存関係プロパティの概要</span><span class="sxs-lookup"><span data-stu-id="77e44-194">Dependency Properties Overview</span></span>](dependency-properties-overview.md)
- [<span data-ttu-id="77e44-195">カスタム依存関係プロパティ</span><span class="sxs-lookup"><span data-stu-id="77e44-195">Custom Dependency Properties</span></span>](custom-dependency-properties.md)
