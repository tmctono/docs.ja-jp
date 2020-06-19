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
ms.openlocfilehash: b1887afd19407898d8de1d92252e29778899fb89
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/09/2020
ms.locfileid: "77095191"
---
# <a name="freezable-objects-overview"></a><span data-ttu-id="d0729-102">Freezable オブジェクトの概要</span><span class="sxs-lookup"><span data-stu-id="d0729-102">Freezable Objects Overview</span></span>

<span data-ttu-id="d0729-103">このトピックでは、アプリケーションのパフォーマンス向上に役立つ特殊な機能を提供する <xref:System.Windows.Freezable> オブジェクトを効果的に使用し、作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="d0729-103">This topic describes how to effectively use and create <xref:System.Windows.Freezable> objects, which provide special features that can help improve application performance.</span></span> <span data-ttu-id="d0729-104">freezable オブジェクトの例として、ブラシ、ペン、変換、ジオメトリ、アニメーションなどがあります。</span><span class="sxs-lookup"><span data-stu-id="d0729-104">Examples of freezable objects include brushes, pens, transformations, geometries, and animations.</span></span>

<a name="whatisafreezable"></a>

## <a name="what-is-a-freezable"></a><span data-ttu-id="d0729-105">Freezable とは</span><span class="sxs-lookup"><span data-stu-id="d0729-105">What Is a Freezable?</span></span>

<span data-ttu-id="d0729-106"><xref:System.Windows.Freezable> は、非固定と固定という 2 つの状態を持つ特殊な型のオブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="d0729-106">A <xref:System.Windows.Freezable> is a special type of object that has two states: unfrozen and frozen.</span></span> <span data-ttu-id="d0729-107">非固定の場合、<xref:System.Windows.Freezable> は他のオブジェクトと同じように動作します。</span><span class="sxs-lookup"><span data-stu-id="d0729-107">When unfrozen, a <xref:System.Windows.Freezable> appears to behave like any other object.</span></span> <span data-ttu-id="d0729-108">固定されると、<xref:System.Windows.Freezable> を変更できなくなります。</span><span class="sxs-lookup"><span data-stu-id="d0729-108">When frozen, a <xref:System.Windows.Freezable> can no longer be modified.</span></span>

<span data-ttu-id="d0729-109"><xref:System.Windows.Freezable> には、オブジェクトに対する変更をオブザーバーに通知する <xref:System.Windows.Freezable.Changed> イベントが用意されています。</span><span class="sxs-lookup"><span data-stu-id="d0729-109">A <xref:System.Windows.Freezable> provides a <xref:System.Windows.Freezable.Changed> event to notify observers of any modifications to the object.</span></span> <span data-ttu-id="d0729-110"><xref:System.Windows.Freezable> を固定すると、変更通知にリソースを費やす必要がなくなるため、パフォーマンスが向上します。</span><span class="sxs-lookup"><span data-stu-id="d0729-110">Freezing a <xref:System.Windows.Freezable> can improve its performance, because it no longer needs to spend resources on change notifications.</span></span> <span data-ttu-id="d0729-111">固定された <xref:System.Windows.Freezable> は複数のスレッドで共有できますが、非固定の <xref:System.Windows.Freezable> はできません。</span><span class="sxs-lookup"><span data-stu-id="d0729-111">A frozen <xref:System.Windows.Freezable> can also be shared across threads, while an unfrozen <xref:System.Windows.Freezable> cannot.</span></span>

<span data-ttu-id="d0729-112"><xref:System.Windows.Freezable> クラスには多くのアプリケーションがありますが、[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] のほとんどの <xref:System.Windows.Freezable> オブジェクトはグラフィックス サブシステムに関連しています。</span><span class="sxs-lookup"><span data-stu-id="d0729-112">Although the <xref:System.Windows.Freezable> class has many applications, most <xref:System.Windows.Freezable> objects in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] are related to the graphics sub-system.</span></span>

<span data-ttu-id="d0729-113"><xref:System.Windows.Freezable> クラスによって、特定のグラフィックス システム オブジェクトを簡単に使用できるようになり、アプリケーションのパフォーマンス向上に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="d0729-113">The <xref:System.Windows.Freezable> class makes it easier to use certain graphics system objects and can help improve application performance.</span></span> <span data-ttu-id="d0729-114"><xref:System.Windows.Freezable> から継承される型の例として、<xref:System.Windows.Media.Brush>、<xref:System.Windows.Media.Transform>、<xref:System.Windows.Media.Geometry> クラスなどがあります。</span><span class="sxs-lookup"><span data-stu-id="d0729-114">Examples of types that inherit from <xref:System.Windows.Freezable> include the <xref:System.Windows.Media.Brush>, <xref:System.Windows.Media.Transform>, and <xref:System.Windows.Media.Geometry> classes.</span></span> <span data-ttu-id="d0729-115">アンマネージ リソースが含まれているため、システムでこれらのオブジェクトの変更を監視し、元のオブジェクトに変更があった場合は対応するアンマネージ リソースを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d0729-115">Because they contain unmanaged resources, the system must monitor these objects for modifications, and then update their corresponding unmanaged resources when there is a change to the original object.</span></span> <span data-ttu-id="d0729-116">グラフィックス システム オブジェクトを実際に変更していなくても、変更を実行する場合に備えて、システムではオブジェクトの監視にリソースの一部を費やす必要があります。</span><span class="sxs-lookup"><span data-stu-id="d0729-116">Even if you don't actually modify a graphics system object, the system must still spend some of its resources monitoring the object, in case you do change it.</span></span>

<span data-ttu-id="d0729-117">たとえば、<xref:System.Windows.Media.SolidColorBrush> ブラシを作成し、それを使用してボタンの背景を描画するとします。</span><span class="sxs-lookup"><span data-stu-id="d0729-117">For example, suppose you create a <xref:System.Windows.Media.SolidColorBrush> brush and use it to paint the background of a button.</span></span>

[!code-csharp[freezablesample_procedural#FrozenExamplePart1](~/samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#frozenexamplepart1)]
[!code-vb[freezablesample_procedural#FrozenExamplePart1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#frozenexamplepart1)]

<span data-ttu-id="d0729-118">ボタンがレンダリングされると、[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] グラフィックス サブシステムでは、提供された情報を使用してピクセルのグループが描画され、ボタンの外観が作成されます。</span><span class="sxs-lookup"><span data-stu-id="d0729-118">When the button is rendered, the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] graphics sub-system uses the information you provided to paint a group of pixels to create the appearance of a button.</span></span> <span data-ttu-id="d0729-119">ボタンの描画方法を説明するために単色ブラシを使用しましたが、この単色ブラシでは実際には描画を行いません。</span><span class="sxs-lookup"><span data-stu-id="d0729-119">Although you used a solid color brush to describe how the button should be painted, your solid color brush doesn't actually do the painting.</span></span> <span data-ttu-id="d0729-120">グラフィックス システムによって、ボタンとブラシ用の高速で低レベルのオブジェクトが生成されます。実際に画面に表示されるのはこれらのオブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="d0729-120">The graphics system generates fast, low-level objects for the button and the brush, and it is those objects that actually appear on the screen.</span></span>

<span data-ttu-id="d0729-121">ブラシを変更する場合、それらの低レベル オブジェクトを再生成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d0729-121">If you were to modify the brush, those low-level objects would have to be regenerated.</span></span> <span data-ttu-id="d0729-122">freezable クラスは、生成された低レベルの対応するオブジェクトを見つけて、変更時にそれらを更新する機能をブラシに付与するものです。</span><span class="sxs-lookup"><span data-stu-id="d0729-122">The freezable class is what gives a brush the ability to find its corresponding generated, low-level objects and to update them when it changes.</span></span> <span data-ttu-id="d0729-123">この機能が有効な場合、ブラシは "非固定" と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="d0729-123">When this ability is enabled, the brush is said to be "unfrozen."</span></span>

<span data-ttu-id="d0729-124">freezable の <xref:System.Windows.Freezable.Freeze%2A> メソッドを使用すると、この自己更新機能を無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="d0729-124">A freezable's <xref:System.Windows.Freezable.Freeze%2A> method enables you to disable this self-updating ability.</span></span> <span data-ttu-id="d0729-125">この方法を使用して、ブラシを "固定"、つまり変更不可にすることができます。</span><span class="sxs-lookup"><span data-stu-id="d0729-125">You can use this method to make the brush become "frozen," or unmodifiable.</span></span>

> [!NOTE]
> <span data-ttu-id="d0729-126">すべての Freezable オブジェクトを固定できるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="d0729-126">Not every Freezable object can be frozen.</span></span> <span data-ttu-id="d0729-127"><xref:System.InvalidOperationException> がスローされないようにするには、固定する前に、Freezable オブジェクトの <xref:System.Windows.Freezable.CanFreeze%2A> プロパティの値を確認して固定できるかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="d0729-127">To avoid throwing an <xref:System.InvalidOperationException>, check the value of the Freezable object's <xref:System.Windows.Freezable.CanFreeze%2A> property to determine whether it can be frozen before attempting to freeze it.</span></span>

[!code-csharp[freezablesample_procedural#FrozenExamplePart2](~/samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#frozenexamplepart2)]
[!code-vb[freezablesample_procedural#FrozenExamplePart2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#frozenexamplepart2)]

<span data-ttu-id="d0729-128">freezable を変更する必要がなくなった場合は、固定するとパフォーマンスが向上します。</span><span class="sxs-lookup"><span data-stu-id="d0729-128">When you no longer need to modify a freezable, freezing it provides performance benefits.</span></span> <span data-ttu-id="d0729-129">この例のブラシを固定した場合、グラフィックス システムでブラシの変更を監視する必要がなくなります。</span><span class="sxs-lookup"><span data-stu-id="d0729-129">If you were to freeze the brush in this example, the graphics system would no longer need to monitor it for changes.</span></span> <span data-ttu-id="d0729-130">また、ブラシが変更されないことがわかっているため、グラフィックス システムで他の最適化を行うこともできます。</span><span class="sxs-lookup"><span data-stu-id="d0729-130">The graphics system can also make other optimizations, because it knows the brush won't change.</span></span>

> [!NOTE]
> <span data-ttu-id="d0729-131">便宜上、明示的に固定しない限り、freezable オブジェクトは固定されないままです。</span><span class="sxs-lookup"><span data-stu-id="d0729-131">For convenience, freezable objects remain unfrozen unless you explicitly freeze them.</span></span>

<a name="frozenfreezables"></a>

## <a name="using-freezables"></a><span data-ttu-id="d0729-132">Freezable の使用</span><span class="sxs-lookup"><span data-stu-id="d0729-132">Using Freezables</span></span>

<span data-ttu-id="d0729-133">固定されていない freezable の使用は、他の種類のオブジェクトの使用と同様です。</span><span class="sxs-lookup"><span data-stu-id="d0729-133">Using an unfrozen freezable is like using any other type of object.</span></span> <span data-ttu-id="d0729-134">次の例では、<xref:System.Windows.Media.SolidColorBrush> の色は、ボタンの背景の描画に使用された後、黄色から赤に変更されます。</span><span class="sxs-lookup"><span data-stu-id="d0729-134">In the following example, the color of a <xref:System.Windows.Media.SolidColorBrush> is changed from yellow to red after it's used to paint the background of a button.</span></span> <span data-ttu-id="d0729-135">グラフィックス システムはバックグラウンドで動作しており、次に画面が更新されたときにボタンは自動的に黄色から赤に変更されます。</span><span class="sxs-lookup"><span data-stu-id="d0729-135">The graphics system works behind the scenes to automatically change the button from yellow to red the next time the screen is refreshed.</span></span>

[!code-csharp[freezablesample_procedural#UnFrozenExampleShort](~/samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#unfrozenexampleshort)]
[!code-vb[freezablesample_procedural#UnFrozenExampleShort](~/samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#unfrozenexampleshort)]

### <a name="freezing-a-freezable"></a><span data-ttu-id="d0729-136">Freezable の固定</span><span class="sxs-lookup"><span data-stu-id="d0729-136">Freezing a Freezable</span></span>

<span data-ttu-id="d0729-137"><xref:System.Windows.Freezable> を変更不可にするには、その <xref:System.Windows.Freezable.Freeze%2A> メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="d0729-137">To make a <xref:System.Windows.Freezable> unmodifiable, you call its <xref:System.Windows.Freezable.Freeze%2A> method.</span></span> <span data-ttu-id="d0729-138">freezable オブジェクトを含むオブジェクトを固定すると、それらのオブジェクトも固定されます。</span><span class="sxs-lookup"><span data-stu-id="d0729-138">When you freeze an object that contains freezable objects, those objects are frozen as well.</span></span> <span data-ttu-id="d0729-139">たとえば、<xref:System.Windows.Media.PathGeometry> を固定すると、それに含まれる図とセグメントも固定されます。</span><span class="sxs-lookup"><span data-stu-id="d0729-139">For example, if you freeze a <xref:System.Windows.Media.PathGeometry>, the figures and segments it contains would be frozen too.</span></span>

<span data-ttu-id="d0729-140">次のいずれかに該当する場合、Freezable を固定**できません**。</span><span class="sxs-lookup"><span data-stu-id="d0729-140">A Freezable **can't** be frozen if any of the following are true:</span></span>

- <span data-ttu-id="d0729-141">アニメーション化された、またはデータ バインドされたプロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="d0729-141">It has animated or data bound properties.</span></span>

- <span data-ttu-id="d0729-142">動的リソースによって設定されるプロパティがあります</span><span class="sxs-lookup"><span data-stu-id="d0729-142">It has properties set by a dynamic resource.</span></span> <span data-ttu-id="d0729-143">(動的リソースの詳細については、[XAML リソース](../../../desktop-wpf/fundamentals/xaml-resources-define.md)に関する記事を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="d0729-143">(See the [XAML Resources](../../../desktop-wpf/fundamentals/xaml-resources-define.md) for more information about dynamic resources.)</span></span>

- <span data-ttu-id="d0729-144">凍結できない <xref:System.Windows.Freezable> サブオブジェクトが含まれています。</span><span class="sxs-lookup"><span data-stu-id="d0729-144">It contains <xref:System.Windows.Freezable> sub-objects that can't be frozen.</span></span>

<span data-ttu-id="d0729-145">これらの条件が false であり、<xref:System.Windows.Freezable> を変更する予定がない場合は、前述したように、固定してパフォーマンスを向上させることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="d0729-145">If these conditions are false, and you don't intend to modify the <xref:System.Windows.Freezable>, then you should freeze it to gain the performance benefits described earlier.</span></span>

<span data-ttu-id="d0729-146">freezable の <xref:System.Windows.Freezable.Freeze%2A> メソッドを呼び出すと、変更できなくなります。</span><span class="sxs-lookup"><span data-stu-id="d0729-146">Once you call a freezable's <xref:System.Windows.Freezable.Freeze%2A> method, it can no longer be modified.</span></span> <span data-ttu-id="d0729-147">固定されたオブジェクトを変更しようとすると、<xref:System.InvalidOperationException> がスローされます。</span><span class="sxs-lookup"><span data-stu-id="d0729-147">Attempting to modify a frozen object causes an <xref:System.InvalidOperationException> to be thrown.</span></span> <span data-ttu-id="d0729-148">次のコードでは、固定後にブラシを変更しようとしているため、例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="d0729-148">The following code throws an exception, because we attempt to modify the brush after it's been frozen.</span></span>

[!code-csharp[freezablesample_procedural#ExceptionExample](~/samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#exceptionexample)]
[!code-vb[freezablesample_procedural#ExceptionExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#exceptionexample)]

<span data-ttu-id="d0729-149">この例外がスローされないようにするには、<xref:System.Windows.Freezable.IsFrozen%2A> メソッドを使用して、<xref:System.Windows.Freezable> が固定されているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="d0729-149">To avoid throwing this exception, you can use the <xref:System.Windows.Freezable.IsFrozen%2A> method to determine whether a <xref:System.Windows.Freezable> is frozen.</span></span>

[!code-csharp[freezablesample_procedural#CheckIsFrozenExample](~/samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#checkisfrozenexample)]
[!code-vb[freezablesample_procedural#CheckIsFrozenExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#checkisfrozenexample)]

<span data-ttu-id="d0729-150">前のコード例では、<xref:System.Windows.Freezable.Clone%2A> メソッドを使用して、固定されたオブジェクトから変更可能なコピーが作成されました。</span><span class="sxs-lookup"><span data-stu-id="d0729-150">In the preceding code example, a modifiable copy was made of a frozen object using the <xref:System.Windows.Freezable.Clone%2A> method.</span></span> <span data-ttu-id="d0729-151">次のセクションでは、複製について詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="d0729-151">The next section discusses cloning in more detail.</span></span>

> [!NOTE]
> <span data-ttu-id="d0729-152">固定された freezable オブジェクトはアニメーション化できないため、<xref:System.Windows.Media.Animation.Storyboard> でアニメーション化しようとすると、アニメーション システムによって、固定された <xref:System.Windows.Freezable> オブジェクトの変更可能なクローンが自動的に作成されます。</span><span class="sxs-lookup"><span data-stu-id="d0729-152">Because a frozen freezable cannot be animated, the animation system will automatically create modifiable clones of frozen <xref:System.Windows.Freezable> objects when you try to animate them with a <xref:System.Windows.Media.Animation.Storyboard>.</span></span> <span data-ttu-id="d0729-153">複製によるパフォーマンスのオーバーヘッドをなくすには、アニメーション化する場合にオブジェクトを固定しないでください。</span><span class="sxs-lookup"><span data-stu-id="d0729-153">To eliminate the performance overhead caused by cloning, leave an object unfrozen if you intend to animate it.</span></span> <span data-ttu-id="d0729-154">アニメーション化とストーリーボードの詳細については、「[ストーリーボードの概要](../graphics-multimedia/storyboards-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d0729-154">For more information about animating with storyboards, see the [Storyboards Overview](../graphics-multimedia/storyboards-overview.md).</span></span>

### <a name="freezing-from-markup"></a><span data-ttu-id="d0729-155">マークアップからの固定</span><span class="sxs-lookup"><span data-stu-id="d0729-155">Freezing from Markup</span></span>

<span data-ttu-id="d0729-156">マークアップで宣言された <xref:System.Windows.Freezable> オブジェクトを固定するには、`PresentationOptions:Freeze` 属性を使用します。</span><span class="sxs-lookup"><span data-stu-id="d0729-156">To freeze a <xref:System.Windows.Freezable> object declared in markup, you use the `PresentationOptions:Freeze` attribute.</span></span> <span data-ttu-id="d0729-157">次の例では、<xref:System.Windows.Media.SolidColorBrush> がページ リソースとして宣言され、固定されています。</span><span class="sxs-lookup"><span data-stu-id="d0729-157">In the following example, a <xref:System.Windows.Media.SolidColorBrush> is declared as a page resource and frozen.</span></span> <span data-ttu-id="d0729-158">これは、ボタンの背景を設定するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="d0729-158">It is then used to set the background of a button.</span></span>

[!code-xaml[FreezableSample#FreezeFromMarkupWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FreezableSample/CS/FreezeFromMarkupExample.xaml#freezefrommarkupwholepage)]

<span data-ttu-id="d0729-159">`Freeze` 属性を使用するには、プレゼンテーション オプション名前空間 `http://schemas.microsoft.com/winfx/2006/xaml/presentation/options` にマップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d0729-159">To use the `Freeze` attribute, you must map to the presentation options namespace: `http://schemas.microsoft.com/winfx/2006/xaml/presentation/options`.</span></span> <span data-ttu-id="d0729-160">`PresentationOptions` は、この名前空間のマッピングに推奨されるプレフィックスです。</span><span class="sxs-lookup"><span data-stu-id="d0729-160">`PresentationOptions` is the recommended prefix for mapping this namespace:</span></span>

```xaml
xmlns:PresentationOptions="http://schemas.microsoft.com/winfx/2006/xaml/presentation/options"
```

<span data-ttu-id="d0729-161">すべての XAML リーダーでこの属性が認識されるわけではないため、[mc:Ignorable 属性](mc-ignorable-attribute.md)を使用して、`Presentation:Freeze` 属性を無視できるものとしてマークすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="d0729-161">Because not all XAML readers recognize this attribute, it's recommended that you use the [mc:Ignorable Attribute](mc-ignorable-attribute.md) to mark the `Presentation:Freeze` attribute as ignorable:</span></span>

```xaml
xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
mc:Ignorable="PresentationOptions"
```

<span data-ttu-id="d0729-162">詳細については、「[mc:Ignorable 属性](mc-ignorable-attribute.md)」ページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d0729-162">For more information, see the [mc:Ignorable Attribute](mc-ignorable-attribute.md) page.</span></span>

### <a name="unfreezing-a-freezable"></a><span data-ttu-id="d0729-163">Freezable の "固定解除"</span><span class="sxs-lookup"><span data-stu-id="d0729-163">"Unfreezing" a Freezable</span></span>

<span data-ttu-id="d0729-164">固定された後に、<xref:System.Windows.Freezable> を変更または固定解除することはできなくなります。ただし、<xref:System.Windows.Freezable.Clone%2A> または <xref:System.Windows.Freezable.CloneCurrentValue%2A> メソッドを使用して、固定されていない複製を作成できます。</span><span class="sxs-lookup"><span data-stu-id="d0729-164">Once frozen, a <xref:System.Windows.Freezable> can never be modified or unfrozen; however, you can create an unfrozen clone using the <xref:System.Windows.Freezable.Clone%2A> or <xref:System.Windows.Freezable.CloneCurrentValue%2A> method.</span></span>

<span data-ttu-id="d0729-165">次の例では、ボタンの背景にブラシを設定し、そのブラシを固定しています。</span><span class="sxs-lookup"><span data-stu-id="d0729-165">In the following example, the button's background is set with a brush and that brush is then frozen.</span></span> <span data-ttu-id="d0729-166">固定されていないコピーは、<xref:System.Windows.Freezable.Clone%2A> メソッドを使用してブラシから作成されます。</span><span class="sxs-lookup"><span data-stu-id="d0729-166">An unfrozen copy is made of the brush using the <xref:System.Windows.Freezable.Clone%2A> method.</span></span> <span data-ttu-id="d0729-167">ボタンの背景を黄色から赤色に変更するために、複製が変更され、使用されます。</span><span class="sxs-lookup"><span data-stu-id="d0729-167">The clone is modified and used to change the button's background from yellow to red.</span></span>

[!code-csharp[freezablesample_procedural#CloneExample](~/samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#cloneexample)]
[!code-vb[freezablesample_procedural#CloneExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#cloneexample)]

> [!NOTE]
> <span data-ttu-id="d0729-168">使用する複製方法に関係なく、アニメーションが新しい <xref:System.Windows.Freezable> にコピーされることはありません。</span><span class="sxs-lookup"><span data-stu-id="d0729-168">Regardless of which clone method you use, animations are never copied to the new <xref:System.Windows.Freezable>.</span></span>

<span data-ttu-id="d0729-169"><xref:System.Windows.Freezable.Clone%2A> および <xref:System.Windows.Freezable.CloneCurrentValue%2A> メソッドを使用すると、freezable のディープ コピーが生成されます。</span><span class="sxs-lookup"><span data-stu-id="d0729-169">The <xref:System.Windows.Freezable.Clone%2A> and <xref:System.Windows.Freezable.CloneCurrentValue%2A> methods produce deep copies of the freezable.</span></span> <span data-ttu-id="d0729-170">freezable に他の固定された freezable オブジェクトが含まれている場合は、それらも複製され、変更可能になります。</span><span class="sxs-lookup"><span data-stu-id="d0729-170">If the freezable contains other frozen freezable objects, they are also cloned and made modifiable.</span></span> <span data-ttu-id="d0729-171">たとえば、固定された <xref:System.Windows.Media.PathGeometry> を複製して変更可能にすると、そこに含まれる図形とセグメントもコピーされ、変更可能になります。</span><span class="sxs-lookup"><span data-stu-id="d0729-171">For example, if you clone a frozen <xref:System.Windows.Media.PathGeometry> to make it modifiable, the figures and segments it contains are also copied and made modifiable.</span></span>

<a name="createyourownfreezableclass"></a>

## <a name="creating-your-own-freezable-class"></a><span data-ttu-id="d0729-172">独自の Freezable クラスの作成</span><span class="sxs-lookup"><span data-stu-id="d0729-172">Creating Your Own Freezable Class</span></span>

<span data-ttu-id="d0729-173"><xref:System.Windows.Freezable> から派生するクラスには、次の機能があります。</span><span class="sxs-lookup"><span data-stu-id="d0729-173">A class that derives from <xref:System.Windows.Freezable> gains the following features.</span></span>

- <span data-ttu-id="d0729-174">特別な状態: 読み取り専用 (固定) および書き込み可能な状態。</span><span class="sxs-lookup"><span data-stu-id="d0729-174">Special states: a read-only (frozen) and a writable state.</span></span>

- <span data-ttu-id="d0729-175">スレッド セーフ: 固定された <xref:System.Windows.Freezable> はスレッド間で共有できます。</span><span class="sxs-lookup"><span data-stu-id="d0729-175">Thread safety: a frozen <xref:System.Windows.Freezable> can be shared across threads.</span></span>

- <span data-ttu-id="d0729-176">詳細な変更通知:他の <xref:System.Windows.DependencyObject> とは異なり、Freezable オブジェクトからは、サブプロパティ値が変更されたときに変更通知が提供されます。</span><span class="sxs-lookup"><span data-stu-id="d0729-176">Detailed change notification: Unlike other <xref:System.Windows.DependencyObject>s, Freezable objects provide change notifications when sub-property values change.</span></span>

- <span data-ttu-id="d0729-177">簡単な複製: Freezable クラスには、ディープ クローンを生成するいくつかのメソッドが既に実装されています。</span><span class="sxs-lookup"><span data-stu-id="d0729-177">Easy cloning: the Freezable class has already implemented several methods that produce deep clones.</span></span>

<span data-ttu-id="d0729-178"><xref:System.Windows.Freezable> は <xref:System.Windows.DependencyObject> の一種であるため、依存関係プロパティ システムが使用されます。</span><span class="sxs-lookup"><span data-stu-id="d0729-178">A <xref:System.Windows.Freezable> is a type of <xref:System.Windows.DependencyObject>, and therefore uses the dependency property system.</span></span> <span data-ttu-id="d0729-179">クラスのプロパティは必ずしも依存関係プロパティではありません。ただし、依存関係プロパティを使用する場合、<xref:System.Windows.Freezable> クラスは依存関係プロパティを考慮して設計されているため、記述しなければならないコードの量が減ります。</span><span class="sxs-lookup"><span data-stu-id="d0729-179">Your class properties don't have to be dependency properties, but using dependency properties will reduce the amount of code you have to write, because the <xref:System.Windows.Freezable> class was designed with dependency properties in mind.</span></span> <span data-ttu-id="d0729-180">依存関係プロパティ システムの詳細については、「[依存関係プロパティの概要](dependency-properties-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d0729-180">For more information about the dependency property system, see the [Dependency Properties Overview](dependency-properties-overview.md).</span></span>

<span data-ttu-id="d0729-181">すべての <xref:System.Windows.Freezable> サブクラスで <xref:System.Windows.Freezable.CreateInstanceCore%2A> メソッドをオーバーライドする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d0729-181">Every <xref:System.Windows.Freezable> subclass must override the <xref:System.Windows.Freezable.CreateInstanceCore%2A> method.</span></span> <span data-ttu-id="d0729-182">クラスで、すべてのデータに依存関係プロパティが使用されている場合は、これで完了です。</span><span class="sxs-lookup"><span data-stu-id="d0729-182">If your class uses dependency properties for all its data, you're finished.</span></span>

<span data-ttu-id="d0729-183">クラスに非依存関係プロパティ データ メンバーが含まれている場合は、次のメソッドもオーバーライドする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d0729-183">If your class contains non-dependency property data members, you must also override the following methods:</span></span>

- <xref:System.Windows.Freezable.CloneCore%2A>

- <xref:System.Windows.Freezable.CloneCurrentValueCore%2A>

- <xref:System.Windows.Freezable.GetAsFrozenCore%2A>

- <xref:System.Windows.Freezable.GetCurrentValueAsFrozenCore%2A>

- <xref:System.Windows.Freezable.FreezeCore%2A>

<span data-ttu-id="d0729-184">また、依存関係プロパティではないデータ メンバーへのアクセスと書き込みについては、次の規則に従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="d0729-184">You must also observe the following rules for accessing and writing to data members that are not dependency properties:</span></span>

- <span data-ttu-id="d0729-185">非依存関係プロパティ データ メンバーを読み取る API の先頭で、<xref:System.Windows.Freezable.ReadPreamble%2A> メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="d0729-185">At the beginning of any API that reads non-dependency property data members, call the <xref:System.Windows.Freezable.ReadPreamble%2A> method.</span></span>

- <span data-ttu-id="d0729-186">非依存関係プロパティ データ メンバーを書き込む API の先頭で、<xref:System.Windows.Freezable.WritePreamble%2A> メソッドを呼び出します</span><span class="sxs-lookup"><span data-stu-id="d0729-186">At the beginning of any API that writes non-dependency property data members, call the <xref:System.Windows.Freezable.WritePreamble%2A> method.</span></span> <span data-ttu-id="d0729-187">(API で <xref:System.Windows.Freezable.WritePreamble%2A> を呼び出した後に、非依存関係プロパティ データ メンバーも読み取る場合、<xref:System.Windows.Freezable.ReadPreamble%2A> をさらに呼び出す必要はありません)。</span><span class="sxs-lookup"><span data-stu-id="d0729-187">(Once you've called <xref:System.Windows.Freezable.WritePreamble%2A> in an API, you don't need to make an additional call to <xref:System.Windows.Freezable.ReadPreamble%2A> if you also read non-dependency property data members.)</span></span>

- <span data-ttu-id="d0729-188">非依存関係プロパティ データ メンバーに書き込むメソッドを終了する前に、<xref:System.Windows.Freezable.WritePostscript%2A> メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="d0729-188">Call the <xref:System.Windows.Freezable.WritePostscript%2A> method before exiting methods that write to non-dependency property data members.</span></span>

<span data-ttu-id="d0729-189">クラスに <xref:System.Windows.DependencyObject> オブジェクトである非依存関係プロパティ データ メンバーが含まれている場合、メンバーを `null` に設定している場合でも、いずれかの値を変更するたびに <xref:System.Windows.Freezable.OnFreezablePropertyChanged%2A> メソッドも呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="d0729-189">If your class contains non-dependency-property data members that are <xref:System.Windows.DependencyObject> objects, you must also call the <xref:System.Windows.Freezable.OnFreezablePropertyChanged%2A> method each time you change one of their values, even if you're setting the member to `null`.</span></span>

> [!NOTE]
> <span data-ttu-id="d0729-190">基本実装を呼び出すことで、オーバーライドする各 <xref:System.Windows.Freezable> メソッドを開始することが非常に重要です。</span><span class="sxs-lookup"><span data-stu-id="d0729-190">It's very important that you begin each <xref:System.Windows.Freezable> method you override with a call to the base implementation.</span></span>

<span data-ttu-id="d0729-191">カスタムの <xref:System.Windows.Freezable> クラスの例については、[カスタム アニメーションのサンプル](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/CustomAnimation)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d0729-191">For an example of a custom <xref:System.Windows.Freezable> class, see the [Custom Animation Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/CustomAnimation).</span></span>

## <a name="see-also"></a><span data-ttu-id="d0729-192">関連項目</span><span class="sxs-lookup"><span data-stu-id="d0729-192">See also</span></span>

- <xref:System.Windows.Freezable>
- [<span data-ttu-id="d0729-193">カスタム アニメーションのサンプル</span><span class="sxs-lookup"><span data-stu-id="d0729-193">Custom Animation Sample</span></span>](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/CustomAnimation)
- [<span data-ttu-id="d0729-194">依存関係プロパティの概要</span><span class="sxs-lookup"><span data-stu-id="d0729-194">Dependency Properties Overview</span></span>](dependency-properties-overview.md)
- [<span data-ttu-id="d0729-195">カスタム依存関係プロパティ</span><span class="sxs-lookup"><span data-stu-id="d0729-195">Custom Dependency Properties</span></span>](custom-dependency-properties.md)
