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
ms.openlocfilehash: 1b0bc360c4c04457e71115dc5caf935841a2bbc1
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64619637"
---
# <a name="freezable-objects-overview"></a><span data-ttu-id="c21ca-102">Freezable オブジェクトの概要</span><span class="sxs-lookup"><span data-stu-id="c21ca-102">Freezable Objects Overview</span></span>
<span data-ttu-id="c21ca-103">このトピックでは、効果的に使用し、作成する方法を説明します。<xref:System.Windows.Freezable>オブジェクトで、アプリケーションのパフォーマンスの向上に役立つ特殊な機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="c21ca-103">This topic describes how to effectively use and create <xref:System.Windows.Freezable> objects, which provide special features that can help improve application performance.</span></span> <span data-ttu-id="c21ca-104">Freezable オブジェクトの例には、ブラシ、ペン、変換、ジオメトリ、およびアニメーションが含まれます。</span><span class="sxs-lookup"><span data-stu-id="c21ca-104">Examples of freezable objects include brushes, pens, transformations, geometries, and animations.</span></span>  
  
<a name="whatisafreezable"></a>   
## <a name="what-is-a-freezable"></a><span data-ttu-id="c21ca-105">Freezable オブジェクトとは</span><span class="sxs-lookup"><span data-stu-id="c21ca-105">What Is a Freezable?</span></span>  
 <span data-ttu-id="c21ca-106"><xref:System.Windows.Freezable> オブジェクトは、非フリーズとフリーズの 2 つの状態を持つ特殊な型です。</span><span class="sxs-lookup"><span data-stu-id="c21ca-106">A <xref:System.Windows.Freezable> is a special type of object that has two states: unfrozen and frozen.</span></span> <span data-ttu-id="c21ca-107">非フリーズ状態では、 <xref:System.Windows.Freezable> オブジェクトはその他のオブジェクトと同様にふるまいます。</span><span class="sxs-lookup"><span data-stu-id="c21ca-107">When unfrozen, a <xref:System.Windows.Freezable> appears to behave like any other object.</span></span> <span data-ttu-id="c21ca-108">フリーズされると、 <xref:System.Windows.Freezable> オブジェクトを変更することはできなくなります。</span><span class="sxs-lookup"><span data-stu-id="c21ca-108">When frozen, a <xref:System.Windows.Freezable> can no longer be modified.</span></span>  
  
 <span data-ttu-id="c21ca-109">A<xref:System.Windows.Freezable>提供、<xref:System.Windows.Freezable.Changed>を変更したり、オブジェクトのオブザーバーに通知するイベントです。</span><span class="sxs-lookup"><span data-stu-id="c21ca-109">A <xref:System.Windows.Freezable> provides a <xref:System.Windows.Freezable.Changed> event to notify observers of any modifications to the object.</span></span> <span data-ttu-id="c21ca-110">固定、<xref:System.Windows.Freezable>変更通知にリソースを費やす必要がなくなったために、パフォーマンスが向上することができます。</span><span class="sxs-lookup"><span data-stu-id="c21ca-110">Freezing a <xref:System.Windows.Freezable> can improve its performance, because it no longer needs to spend resources on change notifications.</span></span> <span data-ttu-id="c21ca-111">固定された<xref:System.Windows.Freezable>フリーズされていないときに、スレッド間で共有することも<xref:System.Windows.Freezable>ことはできません。</span><span class="sxs-lookup"><span data-stu-id="c21ca-111">A frozen <xref:System.Windows.Freezable> can also be shared across threads, while an unfrozen <xref:System.Windows.Freezable> cannot.</span></span>  
  
 <span data-ttu-id="c21ca-112"><xref:System.Windows.Freezable> クラスには多くの用途がありますが、[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] アプリケーションで <xref:System.Windows.Freezable> オブジェクトが最も使用されているのはグラフィックス サブシステム関連です。</span><span class="sxs-lookup"><span data-stu-id="c21ca-112">Although the <xref:System.Windows.Freezable> class has many applications, most <xref:System.Windows.Freezable> objects in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] are related to the graphics sub-system.</span></span>  
  
 <span data-ttu-id="c21ca-113"><xref:System.Windows.Freezable> クラスは、グラフィックス システムの特定のオブジェクトを使用しやすくし、アプリケーションのパフォーマンスを向上させることができます。</span><span class="sxs-lookup"><span data-stu-id="c21ca-113">The <xref:System.Windows.Freezable> class makes it easier to use certain graphics system objects and can help improve application performance.</span></span> <span data-ttu-id="c21ca-114"><xref:System.Windows.Freezable> を継承する型には、 <xref:System.Windows.Media.Brush> 、 <xref:System.Windows.Media.Transform> 、 <xref:System.Windows.Media.Geometry> クラスなどがあります。</span><span class="sxs-lookup"><span data-stu-id="c21ca-114">Examples of types that inherit from <xref:System.Windows.Freezable> include the <xref:System.Windows.Media.Brush>, <xref:System.Windows.Media.Transform>, and <xref:System.Windows.Media.Geometry> classes.</span></span> <span data-ttu-id="c21ca-115">アンマネージ リソースが含まれているため、システムはこれらのオブジェクトの変更を監視し、変更時に対応するアンマネージ リソースを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c21ca-115">Because they contain unmanaged resources, the system must monitor these objects for modifications, and then update their corresponding unmanaged resources when there is a change to the original object.</span></span> <span data-ttu-id="c21ca-116">グラフィックス システムのオブジェクトを実際には変更しない場合でも、変更される場合に備えて、システムはいくらかのリソースを使ってオブジェクトを監視する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c21ca-116">Even if you don't actually modify a graphics system object, the system must still spend some of its resources monitoring the object, in case you do change it.</span></span>  
  
 <span data-ttu-id="c21ca-117">たとえば、 <xref:System.Windows.Media.SolidColorBrush> ブラシを作成し、ボタンの背景を描画するのに使用する場合を考えましょう。</span><span class="sxs-lookup"><span data-stu-id="c21ca-117">For example, suppose you create a <xref:System.Windows.Media.SolidColorBrush> brush and use it to paint the background of a button.</span></span>  
  
 [!code-csharp[freezablesample_procedural#FrozenExamplePart1](~/samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#frozenexamplepart1)]
 [!code-vb[freezablesample_procedural#FrozenExamplePart1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#frozenexamplepart1)]  
  
 <span data-ttu-id="c21ca-118">ボタンが描画されるとき、 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] グラフィックス サブシステムは、ボタンの外観を作成するために、ピクセルのグループを描画するのに指定した情報を使用します。</span><span class="sxs-lookup"><span data-stu-id="c21ca-118">When the button is rendered, the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] graphics sub-system uses the information you provided to paint a group of pixels to create the appearance of a button.</span></span> <span data-ttu-id="c21ca-119">単色ブラシを使用してボタンを描画する方法について説明しますが、単色ブラシが実際に描画するのではありません。</span><span class="sxs-lookup"><span data-stu-id="c21ca-119">Although you used a solid color brush to describe how the button should be painted, your solid color brush doesn't actually do the painting.</span></span> <span data-ttu-id="c21ca-120">グラフィックス システムは、ボタンやブラシに対応する高速で低レベルのオブジェクトを生成し、それが実際に画面に表示されます。</span><span class="sxs-lookup"><span data-stu-id="c21ca-120">The graphics system generates fast, low-level objects for the button and the brush, and it is those objects that actually appear on the screen.</span></span>  
  
 <span data-ttu-id="c21ca-121">ブラシを変更する場合は、これらの低レベルのオブジェクトを再び生成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c21ca-121">If you were to modify the brush, those low-level objects would have to be regenerated.</span></span> <span data-ttu-id="c21ca-122">Freezable クラスは、ブラシに対応する低レベル オブジェクトを検索して変更時に更新する機能を付与します。</span><span class="sxs-lookup"><span data-stu-id="c21ca-122">The freezable class is what gives a brush the ability to find its corresponding generated, low-level objects and to update them when it changes.</span></span> <span data-ttu-id="c21ca-123">この機能が有効のとき、ブラシは「非フリーズ状態」であると言われます。</span><span class="sxs-lookup"><span data-stu-id="c21ca-123">When this ability is enabled, the brush is said to be "unfrozen."</span></span>  
  
 <span data-ttu-id="c21ca-124">Freezable オブジェクトの <xref:System.Windows.Freezable.Freeze%2A> メソッドによって、この自己更新機能を無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="c21ca-124">A freezable's <xref:System.Windows.Freezable.Freeze%2A> method enables you to disable this self-updating ability.</span></span> <span data-ttu-id="c21ca-125">このメソッドを使用すると、ブラシは「フリーズ状態」つまり変更不可能な状態になります。</span><span class="sxs-lookup"><span data-stu-id="c21ca-125">You can use this method to make the brush become "frozen," or unmodifiable.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c21ca-126">すべての Freezable オブジェクトがフリーズできるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="c21ca-126">Not every Freezable object can be frozen.</span></span> <span data-ttu-id="c21ca-127"><xref:System.InvalidOperationException> をスローされることを回避するために、Freezable オブジェクトの <xref:System.Windows.Freezable.CanFreeze%2A> プロパティ値を確認して、フリーズできるかどうかを事前に判断します。</span><span class="sxs-lookup"><span data-stu-id="c21ca-127">To avoid throwing an <xref:System.InvalidOperationException>, check the value of the Freezable object's <xref:System.Windows.Freezable.CanFreeze%2A> property to determine whether it can be frozen before attempting to freeze it.</span></span>  
  
 [!code-csharp[freezablesample_procedural#FrozenExamplePart2](~/samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#frozenexamplepart2)]
 [!code-vb[freezablesample_procedural#FrozenExamplePart2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#frozenexamplepart2)]  
  
 <span data-ttu-id="c21ca-128">フリーズ可能オブジェクトを変更するが不要になったときに固定パフォーマンス上の利点を提供します。</span><span class="sxs-lookup"><span data-stu-id="c21ca-128">When you no longer need to modify a freezable, freezing it provides performance benefits.</span></span> <span data-ttu-id="c21ca-129">この例では、ブラシを固定する場合は、グラフィックス システムはその変更を監視する必要がなくなります。</span><span class="sxs-lookup"><span data-stu-id="c21ca-129">If you were to freeze the brush in this example, the graphics system would no longer need to monitor it for changes.</span></span> <span data-ttu-id="c21ca-130">グラフィックス システムは、ブラシが変更されないことを知っているために、その他の最適化をこともできます。</span><span class="sxs-lookup"><span data-stu-id="c21ca-130">The graphics system can also make other optimizations, because it knows the brush won't change.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c21ca-131">便宜上、Freezable オブジェクトは、明示的にフリーズしない限りフリーズされません。</span><span class="sxs-lookup"><span data-stu-id="c21ca-131">For convenience, freezable objects remain unfrozen unless you explicitly freeze them.</span></span>  
  
<a name="frozenfreezables"></a>   
## <a name="using-freezables"></a><span data-ttu-id="c21ca-132">Freezable オブジェクトの使用</span><span class="sxs-lookup"><span data-stu-id="c21ca-132">Using Freezables</span></span>  
 <span data-ttu-id="c21ca-133">非フリーズの Freezable オブジェクトは他の型のオブジェクトと同様に使用できます。</span><span class="sxs-lookup"><span data-stu-id="c21ca-133">Using an unfrozen freezable is like using any other type of object.</span></span> <span data-ttu-id="c21ca-134">次の例では、 <xref:System.Windows.Media.SolidColorBrush> を使用してボタンの背景を描画した後に、その色を黄色から赤に変更します。</span><span class="sxs-lookup"><span data-stu-id="c21ca-134">In the following example, the color of a <xref:System.Windows.Media.SolidColorBrush> is changed from yellow to red after it's used to paint the background of a button.</span></span> <span data-ttu-id="c21ca-135">グラフィックス システムは、次の画面更新時に、ボタンの色を黄色から赤に自動的に更新します。</span><span class="sxs-lookup"><span data-stu-id="c21ca-135">The graphics system works behind the scenes to automatically change the button from yellow to red the next time the screen is refreshed.</span></span>  
  
 [!code-csharp[freezablesample_procedural#UnFrozenExampleShort](~/samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#unfrozenexampleshort)]
 [!code-vb[freezablesample_procedural#UnFrozenExampleShort](~/samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#unfrozenexampleshort)]  
  
### <a name="freezing-a-freezable"></a><span data-ttu-id="c21ca-136">Freezable オブジェクトをフリーズする</span><span class="sxs-lookup"><span data-stu-id="c21ca-136">Freezing a Freezable</span></span>  
 <span data-ttu-id="c21ca-137"><xref:System.Windows.Freezable> オブジェクトを変更不可の状態にするには、その <xref:System.Windows.Freezable.Freeze%2A> メソッドを呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="c21ca-137">To make a <xref:System.Windows.Freezable> unmodifiable, you call its <xref:System.Windows.Freezable.Freeze%2A> method.</span></span> <span data-ttu-id="c21ca-138">Freezable オブジェクトを格納しているオブジェクトをフリーズすると、それらのオブジェクトも同様にフリーズされます。</span><span class="sxs-lookup"><span data-stu-id="c21ca-138">When you freeze an object that contains freezable objects, those objects are frozen as well.</span></span> <span data-ttu-id="c21ca-139">例えば、 <xref:System.Windows.Media.PathGeometry> をフリーズすると、それに含まれる図やセグメントも同時にフリーズされます。</span><span class="sxs-lookup"><span data-stu-id="c21ca-139">For example, if you freeze a <xref:System.Windows.Media.PathGeometry>, the figures and segments it contains would be frozen too.</span></span>  
  
 <span data-ttu-id="c21ca-140">Freezable オブジェクトは次のいずれかに該当する場合、フリーズ**できません**。</span><span class="sxs-lookup"><span data-stu-id="c21ca-140">A Freezable **can't** be frozen if any of the following are true:</span></span>  
  
- <span data-ttu-id="c21ca-141">アニメーション化されたまたは、データ バインドされたプロパティを持つ。</span><span class="sxs-lookup"><span data-stu-id="c21ca-141">It has animated or data bound properties.</span></span>  
  
- <span data-ttu-id="c21ca-142">動的リソースによって設定されるプロパティを持つ。</span><span class="sxs-lookup"><span data-stu-id="c21ca-142">It has properties set by a dynamic resource.</span></span> <span data-ttu-id="c21ca-143">(動的リソースの詳細については[XAML リソース](xaml-resources.md)を参照)</span><span class="sxs-lookup"><span data-stu-id="c21ca-143">(See the [XAML Resources](xaml-resources.md) for more information about dynamic resources.)</span></span>  
  
- <span data-ttu-id="c21ca-144">フリーズできない <xref:System.Windows.Freezable> オブジェクトを含む。</span><span class="sxs-lookup"><span data-stu-id="c21ca-144">It contains <xref:System.Windows.Freezable> sub-objects that can't be frozen.</span></span>  
  
 <span data-ttu-id="c21ca-145">これらの条件が false で、その <xref:System.Windows.Freezable> オブジェクトを変更する予定がない場合、それをフリーズすることで前述の通りパフォーマンスの利点を得られます。</span><span class="sxs-lookup"><span data-stu-id="c21ca-145">If these conditions are false, and you don't intend to modify the <xref:System.Windows.Freezable>, then you should freeze it to gain the performance benefits described earlier.</span></span>  
  
 <span data-ttu-id="c21ca-146">Freezable オブジェクトの <xref:System.Windows.Freezable.Freeze%2A> メソッドを呼び出したら、その後は変更することができません。</span><span class="sxs-lookup"><span data-stu-id="c21ca-146">Once you call a freezable's <xref:System.Windows.Freezable.Freeze%2A> method, it can no longer be modified.</span></span> <span data-ttu-id="c21ca-147">フリーズされたオブジェクトを変更しようとすると、 <xref:System.InvalidOperationException> がスローされます。</span><span class="sxs-lookup"><span data-stu-id="c21ca-147">Attempting to modify a frozen object causes an <xref:System.InvalidOperationException> to be thrown.</span></span> <span data-ttu-id="c21ca-148">次のコードは、フリーズした後にブラシを変更しようとするので、例外をスローします。</span><span class="sxs-lookup"><span data-stu-id="c21ca-148">The following code throws an exception, because we attempt to modify the brush after it's been frozen.</span></span>  
  
 [!code-csharp[freezablesample_procedural#ExceptionExample](~/samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#exceptionexample)]
 [!code-vb[freezablesample_procedural#ExceptionExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#exceptionexample)]  
  
 <span data-ttu-id="c21ca-149">この例外をスローすることを避けるために、 <xref:System.Windows.Freezable.IsFrozen%2A> メソッドを使用して <xref:System.Windows.Freezable> がフリーズされているかを調べられます。</span><span class="sxs-lookup"><span data-stu-id="c21ca-149">To avoid throwing this exception, you can use the <xref:System.Windows.Freezable.IsFrozen%2A> method to determine whether a <xref:System.Windows.Freezable> is frozen.</span></span>  
  
 [!code-csharp[freezablesample_procedural#CheckIsFrozenExample](~/samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#checkisfrozenexample)]
 [!code-vb[freezablesample_procedural#CheckIsFrozenExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#checkisfrozenexample)]  
  
 <span data-ttu-id="c21ca-150">上記のコード例では、<xref:System.Windows.Freezable.Clone%2A>メソッドを使用してフリーズされたオブジェクトの変更可能なコピーを作成しました。</span><span class="sxs-lookup"><span data-stu-id="c21ca-150">In the preceding code example, a modifiable copy was made of a frozen object using the <xref:System.Windows.Freezable.Clone%2A> method.</span></span> <span data-ttu-id="c21ca-151">次のセクションでは、複製の作成について説明します。</span><span class="sxs-lookup"><span data-stu-id="c21ca-151">The next section discusses cloning in more detail.</span></span>  
  
 <span data-ttu-id="c21ca-152">**注**ため、固定された freezable アニメーション化できません、アニメーション システムが自動的の変更可能な複製を作成固定された<xref:System.Windows.Freezable>オブジェクトを使用してアニメーション化しようとすると、 <xref:System.Windows.Media.Animation.Storyboard>。</span><span class="sxs-lookup"><span data-stu-id="c21ca-152">**Note** Because a frozen freezable cannot be animated, the animation system will automatically create modifiable clones of frozen <xref:System.Windows.Freezable> objects when you try to animate them with a <xref:System.Windows.Media.Animation.Storyboard>.</span></span> <span data-ttu-id="c21ca-153">オーバーヘッドを複製することがパフォーマンスをなくすため、オブジェクトをアニメーション化する場合にマスクされていないままにします。</span><span class="sxs-lookup"><span data-stu-id="c21ca-153">To eliminate the performance overhead caused by cloning, leave an object unfrozen if you intend to animate it.</span></span> <span data-ttu-id="c21ca-154">ストーリー ボードを使用したアニメーション化の詳細については、次を参照してください。、[ストーリー ボードの概要](../graphics-multimedia/storyboards-overview.md)します。</span><span class="sxs-lookup"><span data-stu-id="c21ca-154">For more information about animating with storyboards, see the [Storyboards Overview](../graphics-multimedia/storyboards-overview.md).</span></span>  
  
### <a name="freezing-from-markup"></a><span data-ttu-id="c21ca-155">マークアップからのフリーズ</span><span class="sxs-lookup"><span data-stu-id="c21ca-155">Freezing from Markup</span></span>  
 <span data-ttu-id="c21ca-156">固定するには、<xref:System.Windows.Freezable>オブジェクトを使用する、マークアップで宣言された、`PresentationOptions:Freeze`属性。</span><span class="sxs-lookup"><span data-stu-id="c21ca-156">To freeze a <xref:System.Windows.Freezable> object declared in markup, you use the `PresentationOptions:Freeze` attribute.</span></span> <span data-ttu-id="c21ca-157">次の例では、<xref:System.Windows.Media.SolidColorBrush>はページ リソースとして宣言されており、固定されています。</span><span class="sxs-lookup"><span data-stu-id="c21ca-157">In the following example, a <xref:System.Windows.Media.SolidColorBrush> is declared as a page resource and frozen.</span></span> <span data-ttu-id="c21ca-158">ボタンの背景を設定するのには使用されます。</span><span class="sxs-lookup"><span data-stu-id="c21ca-158">It is then used to set the background of a button.</span></span>  
  
 [!code-xaml[FreezableSample#FreezeFromMarkupWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FreezableSample/CS/FreezeFromMarkupExample.xaml#freezefrommarkupwholepage)]  
  
 <span data-ttu-id="c21ca-159">使用する、`Freeze`属性、プレゼンテーション オプションの名前空間にマップする必要があります:`http://schemas.microsoft.com/winfx/2006/xaml/presentation/options`します。</span><span class="sxs-lookup"><span data-stu-id="c21ca-159">To use the `Freeze` attribute, you must map to the presentation options namespace: `http://schemas.microsoft.com/winfx/2006/xaml/presentation/options`.</span></span> <span data-ttu-id="c21ca-160">`PresentationOptions` この名前空間をマッピングするための推奨されるプレフィックスを示します。</span><span class="sxs-lookup"><span data-stu-id="c21ca-160">`PresentationOptions` is the recommended prefix for mapping this namespace:</span></span>  
  
```  
xmlns:PresentationOptions="http://schemas.microsoft.com/winfx/2006/xaml/presentation/options"   
```  
  
 <span data-ttu-id="c21ca-161">すべての XAML リーダーは、この属性を認識しているためには、使用することをお勧め、 [mc: Ignorable 属性](mc-ignorable-attribute.md)をマークする、`Presentation:Freeze`属性を無視できます。</span><span class="sxs-lookup"><span data-stu-id="c21ca-161">Because not all XAML readers recognize this attribute, it's recommended that you use the [mc:Ignorable Attribute](mc-ignorable-attribute.md) to mark the `Presentation:Freeze` attribute as ignorable:</span></span>  
  
```  
xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"  
mc:Ignorable="PresentationOptions"  
```  
  
 <span data-ttu-id="c21ca-162">詳細については、次を参照してください。、 [mc: Ignorable 属性](mc-ignorable-attribute.md)ページ。</span><span class="sxs-lookup"><span data-stu-id="c21ca-162">For more information, see the [mc:Ignorable Attribute](mc-ignorable-attribute.md) page.</span></span>  
  
### <a name="unfreezing-a-freezable"></a><span data-ttu-id="c21ca-163">「固定解除する」フリーズ可能オブジェクト</span><span class="sxs-lookup"><span data-stu-id="c21ca-163">"Unfreezing" a Freezable</span></span>  
 <span data-ttu-id="c21ca-164">1 回凍結、<xref:System.Windows.Freezable>しない変更またはマスクされていない。 ただし、を使用して、固定された複製を作成することができます、<xref:System.Windows.Freezable.Clone%2A>または<xref:System.Windows.Freezable.CloneCurrentValue%2A>メソッド。</span><span class="sxs-lookup"><span data-stu-id="c21ca-164">Once frozen, a <xref:System.Windows.Freezable> can never be modified or unfrozen; however, you can create an unfrozen clone using the <xref:System.Windows.Freezable.Clone%2A> or <xref:System.Windows.Freezable.CloneCurrentValue%2A> method.</span></span>  
  
 <span data-ttu-id="c21ca-165">次の例では、ブラシを使用して、ボタンの背景を設定し、そのブラシが固定されてします。</span><span class="sxs-lookup"><span data-stu-id="c21ca-165">In the following example, the button's background is set with a brush and that brush is then frozen.</span></span> <span data-ttu-id="c21ca-166">使用して、ブラシの固定のコピーが行われた、<xref:System.Windows.Freezable.Clone%2A>メソッド。</span><span class="sxs-lookup"><span data-stu-id="c21ca-166">An unfrozen copy is made of the brush using the <xref:System.Windows.Freezable.Clone%2A> method.</span></span> <span data-ttu-id="c21ca-167">クローンを変更し、ボタンの背景を黄色から赤に変更するために使用します。</span><span class="sxs-lookup"><span data-stu-id="c21ca-167">The clone is modified and used to change the button's background from yellow to red.</span></span>  
  
 [!code-csharp[freezablesample_procedural#CloneExample](~/samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#cloneexample)]
 [!code-vb[freezablesample_procedural#CloneExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#cloneexample)]  
  
> [!NOTE]
>  <span data-ttu-id="c21ca-168">新しいコピーされませんアニメーションに使用する複製方法に関係なく<xref:System.Windows.Freezable>します。</span><span class="sxs-lookup"><span data-stu-id="c21ca-168">Regardless of which clone method you use, animations are never copied to the new <xref:System.Windows.Freezable>.</span></span>  
  
 <span data-ttu-id="c21ca-169"><xref:System.Windows.Freezable.Clone%2A>と<xref:System.Windows.Freezable.CloneCurrentValue%2A>メソッドは、フリーズ可能オブジェクトの詳細コピーを作成します。</span><span class="sxs-lookup"><span data-stu-id="c21ca-169">The <xref:System.Windows.Freezable.Clone%2A> and <xref:System.Windows.Freezable.CloneCurrentValue%2A> methods produce deep copies of the freezable.</span></span> <span data-ttu-id="c21ca-170">フリーズ可能オブジェクトに他のフリーズされたフリーズ可能オブジェクトが含まれている場合は、それらも複製されて変更可能になります。</span><span class="sxs-lookup"><span data-stu-id="c21ca-170">If the freezable contains other frozen freezable objects, they are also cloned and made modifiable.</span></span> <span data-ttu-id="c21ca-171">たとえば、フリーズされた<xref:System.Windows.Media.PathGeometry>を修正して修正可能にすると、それに含まれる図形とセグメントもコピーされて修正可能になります。</span><span class="sxs-lookup"><span data-stu-id="c21ca-171">For example, if you clone a frozen <xref:System.Windows.Media.PathGeometry> to make it modifiable, the figures and segments it contains are also copied and made modifiable.</span></span>  
  
<a name="createyourownfreezableclass"></a>   
## <a name="creating-your-own-freezable-class"></a><span data-ttu-id="c21ca-172">Freezable クラスの作成</span><span class="sxs-lookup"><span data-stu-id="c21ca-172">Creating Your Own Freezable Class</span></span>  
 <span data-ttu-id="c21ca-173">派生したクラス<xref:System.Windows.Freezable>次の機能を取得します。</span><span class="sxs-lookup"><span data-stu-id="c21ca-173">A class that derives from <xref:System.Windows.Freezable> gains the following features.</span></span>  
  
- <span data-ttu-id="c21ca-174">特殊な状態。 読み取り専用 (固定)、書き込み可能な状態です。</span><span class="sxs-lookup"><span data-stu-id="c21ca-174">Special states: a read-only (frozen) and a writable state.</span></span>  
  
- <span data-ttu-id="c21ca-175">スレッド セーフ。 固定された<xref:System.Windows.Freezable>スレッド間で共有することができます。</span><span class="sxs-lookup"><span data-stu-id="c21ca-175">Thread safety: a frozen <xref:System.Windows.Freezable> can be shared across threads.</span></span>  
  
- <span data-ttu-id="c21ca-176">変更の詳細についての通知:その他とは異なり<xref:System.Windows.DependencyObject>、フリーズ可能オブジェクトは変更通知サブ プロパティの値を変更するときにします。</span><span class="sxs-lookup"><span data-stu-id="c21ca-176">Detailed change notification: Unlike other <xref:System.Windows.DependencyObject>s, Freezable objects provide change notifications when sub-property values change.</span></span>  
  
- <span data-ttu-id="c21ca-177">簡単に複製: Freezable クラスは既にディープ クローンを生成するいくつかのメソッドを実装します。</span><span class="sxs-lookup"><span data-stu-id="c21ca-177">Easy cloning: the Freezable class has already implemented several methods that produce deep clones.</span></span>  
  
 <span data-ttu-id="c21ca-178">A<xref:System.Windows.Freezable>の種類は、<xref:System.Windows.DependencyObject>をそのため、依存関係プロパティ システムを使用します。</span><span class="sxs-lookup"><span data-stu-id="c21ca-178">A <xref:System.Windows.Freezable> is a type of <xref:System.Windows.DependencyObject>, and therefore uses the dependency property system.</span></span> <span data-ttu-id="c21ca-179">クラスのプロパティは、依存関係プロパティにする必要はありませんが、ために書き込むがあるコードの量を減らすは依存関係プロパティを使用して、<xref:System.Windows.Freezable>クラスは依存関係プロパティを考慮して設計されました。</span><span class="sxs-lookup"><span data-stu-id="c21ca-179">Your class properties don't have to be dependency properties, but using dependency properties will reduce the amount of code you have to write, because the <xref:System.Windows.Freezable> class was designed with dependency properties in mind.</span></span> <span data-ttu-id="c21ca-180">依存関係プロパティ システムの詳細については、次を参照してください。、[依存関係プロパティの概要](dependency-properties-overview.md)します。</span><span class="sxs-lookup"><span data-stu-id="c21ca-180">For more information about the dependency property system, see the [Dependency Properties Overview](dependency-properties-overview.md).</span></span>  
  
 <span data-ttu-id="c21ca-181">すべて<xref:System.Windows.Freezable>サブクラスをオーバーライドする必要があります、<xref:System.Windows.Freezable.CreateInstanceCore%2A>メソッド。</span><span class="sxs-lookup"><span data-stu-id="c21ca-181">Every <xref:System.Windows.Freezable> subclass must override the <xref:System.Windows.Freezable.CreateInstanceCore%2A> method.</span></span> <span data-ttu-id="c21ca-182">クラスは、そのすべてのデータの依存関係プロパティを使用している場合は、完了します。</span><span class="sxs-lookup"><span data-stu-id="c21ca-182">If your class uses dependency properties for all its data, you're finished.</span></span>  
  
 <span data-ttu-id="c21ca-183">クラスに依存関係のないプロパティのデータ メンバーが含まれている場合は、次のメソッドもオーバーライドする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c21ca-183">If your class contains non-dependency property data members, you must also override the following methods:</span></span>  
  
- <xref:System.Windows.Freezable.CloneCore%2A>  
  
- <xref:System.Windows.Freezable.CloneCurrentValueCore%2A>  
  
- <xref:System.Windows.Freezable.GetAsFrozenCore%2A>  
  
- <xref:System.Windows.Freezable.GetCurrentValueAsFrozenCore%2A>  
  
- <xref:System.Windows.Freezable.FreezeCore%2A>  
  
 <span data-ttu-id="c21ca-184">次のルールにアクセスして、依存関係プロパティではないデータ メンバーへの書き込みにも注意してください。</span><span class="sxs-lookup"><span data-stu-id="c21ca-184">You must also observe the following rules for accessing and writing to data members that are not dependency properties:</span></span>  
  
- <span data-ttu-id="c21ca-185">いずれかの先頭に[!INCLUDE[TLA#tla_api](../../../../includes/tlasharptla-api-md.md)]呼び出し、依存関係のないプロパティのデータ メンバーを読み取る、<xref:System.Windows.Freezable.ReadPreamble%2A>メソッド。</span><span class="sxs-lookup"><span data-stu-id="c21ca-185">At the beginning of any [!INCLUDE[TLA#tla_api](../../../../includes/tlasharptla-api-md.md)] that reads non-dependency property data members, call the <xref:System.Windows.Freezable.ReadPreamble%2A> method.</span></span>  
  
- <span data-ttu-id="c21ca-186">依存関係のないプロパティのデータ メンバーを書き込む任意の API の先頭には、呼び出し、<xref:System.Windows.Freezable.WritePreamble%2A>メソッド。</span><span class="sxs-lookup"><span data-stu-id="c21ca-186">At the beginning of any API that writes non-dependency property data members, call the <xref:System.Windows.Freezable.WritePreamble%2A> method.</span></span> <span data-ttu-id="c21ca-187">(呼び出したら<xref:System.Windows.Freezable.WritePreamble%2A>で、[!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)]への呼び出しを追加する必要はありません<xref:System.Windows.Freezable.ReadPreamble%2A>も非依存関係プロパティのデータ メンバーを読み取るかどうかです)。</span><span class="sxs-lookup"><span data-stu-id="c21ca-187">(Once you've called <xref:System.Windows.Freezable.WritePreamble%2A> in an [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)], you don't need to make an additional call to <xref:System.Windows.Freezable.ReadPreamble%2A> if you also read non-dependency property data members.)</span></span>  
  
- <span data-ttu-id="c21ca-188">呼び出す、<xref:System.Windows.Freezable.WritePostscript%2A>依存関係のないプロパティのデータ メンバーへの書き込みメソッドを終了する前にメソッド。</span><span class="sxs-lookup"><span data-stu-id="c21ca-188">Call the <xref:System.Windows.Freezable.WritePostscript%2A> method before exiting methods that write to non-dependency property data members.</span></span>  
  
 <span data-ttu-id="c21ca-189">クラスにある非依存関係プロパティのデータ メンバーが含まれて かどうか<xref:System.Windows.DependencyObject>オブジェクトも呼び出す必要があります、<xref:System.Windows.Freezable.OnFreezablePropertyChanged%2A>メソッドは、メンバーを設定している場合でも、その値のいずれかを変更するたびに`null`します。</span><span class="sxs-lookup"><span data-stu-id="c21ca-189">If your class contains non-dependency-property data members that are <xref:System.Windows.DependencyObject> objects, you must also call the <xref:System.Windows.Freezable.OnFreezablePropertyChanged%2A> method each time you change one of their values, even if you're setting the member to `null`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c21ca-190">各を開始することが非常に重要<xref:System.Windows.Freezable>基本実装への呼び出しでオーバーライドするメソッド。</span><span class="sxs-lookup"><span data-stu-id="c21ca-190">It's very important that you begin each <xref:System.Windows.Freezable> method you override with a call to the base implementation.</span></span>  
  
 <span data-ttu-id="c21ca-191">カスタムの例については<xref:System.Windows.Freezable>クラスを参照してください、[カスタム アニメーションのサンプル](https://go.microsoft.com/fwlink/?LinkID=159981)します。</span><span class="sxs-lookup"><span data-stu-id="c21ca-191">For an example of a custom <xref:System.Windows.Freezable> class, see the [Custom Animation Sample](https://go.microsoft.com/fwlink/?LinkID=159981).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c21ca-192">関連項目</span><span class="sxs-lookup"><span data-stu-id="c21ca-192">See also</span></span>

- <xref:System.Windows.Freezable>
- [<span data-ttu-id="c21ca-193">カスタム アニメーションのサンプル</span><span class="sxs-lookup"><span data-stu-id="c21ca-193">Custom Animation Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=159981)
- [<span data-ttu-id="c21ca-194">依存関係プロパティの概要</span><span class="sxs-lookup"><span data-stu-id="c21ca-194">Dependency Properties Overview</span></span>](dependency-properties-overview.md)
- [<span data-ttu-id="c21ca-195">カスタム依存関係プロパティ</span><span class="sxs-lookup"><span data-stu-id="c21ca-195">Custom Dependency Properties</span></span>](custom-dependency-properties.md)
