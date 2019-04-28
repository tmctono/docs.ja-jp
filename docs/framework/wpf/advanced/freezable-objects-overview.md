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
ms.openlocfilehash: 8df19e69ff3be06704878ea290a3f4a2997127eb
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61703316"
---
# <a name="freezable-objects-overview"></a><span data-ttu-id="7fd22-102">Freezable オブジェクトの概要</span><span class="sxs-lookup"><span data-stu-id="7fd22-102">Freezable Objects Overview</span></span>
<span data-ttu-id="7fd22-103">このトピックでは、効果的に使用し、作成する方法を説明します。<xref:System.Windows.Freezable>オブジェクトで、アプリケーションのパフォーマンスの向上に役立つ特殊な機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="7fd22-103">This topic describes how to effectively use and create <xref:System.Windows.Freezable> objects, which provide special features that can help improve application performance.</span></span> <span data-ttu-id="7fd22-104">Freezable オブジェクトの例には、ブラシ、ペン、変換、ジオメトリ、およびアニメーションが含まれます。</span><span class="sxs-lookup"><span data-stu-id="7fd22-104">Examples of freezable objects include brushes, pens, transformations, geometries, and animations.</span></span>  
  
<a name="whatisafreezable"></a>   
## <a name="what-is-a-freezable"></a><span data-ttu-id="7fd22-105">フリーズ可能オブジェクトとは</span><span class="sxs-lookup"><span data-stu-id="7fd22-105">What Is a Freezable?</span></span>  
 <span data-ttu-id="7fd22-106">A<xref:System.Windows.Freezable>は 2 つの状態を持つオブジェクトの特殊な型です: 非フリーズし、フリーズします。</span><span class="sxs-lookup"><span data-stu-id="7fd22-106">A <xref:System.Windows.Freezable> is a special type of object that has two states: unfrozen and frozen.</span></span> <span data-ttu-id="7fd22-107">フリーズ、<xref:System.Windows.Freezable>するその他のオブジェクトと同様に動作が表示されます。</span><span class="sxs-lookup"><span data-stu-id="7fd22-107">When unfrozen, a <xref:System.Windows.Freezable> appears to behave like any other object.</span></span> <span data-ttu-id="7fd22-108">固定されると、<xref:System.Windows.Freezable>変更できます。</span><span class="sxs-lookup"><span data-stu-id="7fd22-108">When frozen, a <xref:System.Windows.Freezable> can no longer be modified.</span></span>  
  
 <span data-ttu-id="7fd22-109">A<xref:System.Windows.Freezable>提供、<xref:System.Windows.Freezable.Changed>を変更したり、オブジェクトのオブザーバーに通知するイベントです。</span><span class="sxs-lookup"><span data-stu-id="7fd22-109">A <xref:System.Windows.Freezable> provides a <xref:System.Windows.Freezable.Changed> event to notify observers of any modifications to the object.</span></span> <span data-ttu-id="7fd22-110">固定、<xref:System.Windows.Freezable>変更通知にリソースを費やす必要がなくなったために、パフォーマンスが向上することができます。</span><span class="sxs-lookup"><span data-stu-id="7fd22-110">Freezing a <xref:System.Windows.Freezable> can improve its performance, because it no longer needs to spend resources on change notifications.</span></span> <span data-ttu-id="7fd22-111">固定された<xref:System.Windows.Freezable>フリーズされていないときに、スレッド間で共有することも<xref:System.Windows.Freezable>ことはできません。</span><span class="sxs-lookup"><span data-stu-id="7fd22-111">A frozen <xref:System.Windows.Freezable> can also be shared across threads, while an unfrozen <xref:System.Windows.Freezable> cannot.</span></span>  
  
 <span data-ttu-id="7fd22-112">ですが、<xref:System.Windows.Freezable>クラスには多くのアプリケーションで最も<xref:System.Windows.Freezable>オブジェクト[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]グラフィックス サブシステムに関連します。</span><span class="sxs-lookup"><span data-stu-id="7fd22-112">Although the <xref:System.Windows.Freezable> class has many applications, most <xref:System.Windows.Freezable> objects in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] are related to the graphics sub-system.</span></span>  
  
 <span data-ttu-id="7fd22-113"><xref:System.Windows.Freezable>クラスは、特定のグラフィックス システム オブジェクトを使用するが容易し、アプリケーションのパフォーマンスを向上させることができます。</span><span class="sxs-lookup"><span data-stu-id="7fd22-113">The <xref:System.Windows.Freezable> class makes it easier to use certain graphics system objects and can help improve application performance.</span></span> <span data-ttu-id="7fd22-114">継承する型の例<xref:System.Windows.Freezable>含める、 <xref:System.Windows.Media.Brush>、 <xref:System.Windows.Media.Transform>、および<xref:System.Windows.Media.Geometry>クラス。</span><span class="sxs-lookup"><span data-stu-id="7fd22-114">Examples of types that inherit from <xref:System.Windows.Freezable> include the <xref:System.Windows.Media.Brush>, <xref:System.Windows.Media.Transform>, and <xref:System.Windows.Media.Geometry> classes.</span></span> <span data-ttu-id="7fd22-115">アンマネージ リソースが含まれているため、システムはこれらのオブジェクトの変更を監視し、元のオブジェクトへの変更がある場合に、対応するアンマネージ リソースを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7fd22-115">Because they contain unmanaged resources, the system must monitor these objects for modifications, and then update their corresponding unmanaged resources when there is a change to the original object.</span></span> <span data-ttu-id="7fd22-116">グラフィックス システム オブジェクトを実際に変更しない場合でもシステムする必要があります十オブジェクトの監視、リソースのいくつかこれを変更する場合。</span><span class="sxs-lookup"><span data-stu-id="7fd22-116">Even if you don't actually modify a graphics system object, the system must still spend some of its resources monitoring the object, in case you do change it.</span></span>  
  
 <span data-ttu-id="7fd22-117">たとえば、作成する、<xref:System.Windows.Media.SolidColorBrush>ブラシを使用して、ボタンの背景を描画します。</span><span class="sxs-lookup"><span data-stu-id="7fd22-117">For example, suppose you create a <xref:System.Windows.Media.SolidColorBrush> brush and use it to paint the background of a button.</span></span>  
  
 [!code-csharp[freezablesample_procedural#FrozenExamplePart1](~/samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#frozenexamplepart1)]
 [!code-vb[freezablesample_procedural#FrozenExamplePart1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#frozenexamplepart1)]  
  
 <span data-ttu-id="7fd22-118">ボタンが表示されるときに、[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]グラフィックス サブシステムは、ボタンの外観を作成するためのピクセルのグループを描画するのには指定した情報を使用します。</span><span class="sxs-lookup"><span data-stu-id="7fd22-118">When the button is rendered, the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] graphics sub-system uses the information you provided to paint a group of pixels to create the appearance of a button.</span></span> <span data-ttu-id="7fd22-119">単色ブラシを使用して、ボタンを描画する方法について説明しますが、単色ブラシは、描画を実際にはありません。</span><span class="sxs-lookup"><span data-stu-id="7fd22-119">Although you used a solid color brush to describe how the button should be painted, your solid color brush doesn't actually do the painting.</span></span> <span data-ttu-id="7fd22-120">グラフィックス システムは、ボタンと、ブラシの高速で低レベルのオブジェクトを生成して、実際には、画面に表示されるこれらのオブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="7fd22-120">The graphics system generates fast, low-level objects for the button and the brush, and it is those objects that actually appear on the screen.</span></span>  
  
 <span data-ttu-id="7fd22-121">ブラシを変更する場合は、これらの低レベルのオブジェクトが再生成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7fd22-121">If you were to modify the brush, those low-level objects would have to be regenerated.</span></span> <span data-ttu-id="7fd22-122">Freezable クラスは、ブラシを変更するときに、それらを更新して、対応する生成された、低レベルのオブジェクトを検索する機能を提供内容です。</span><span class="sxs-lookup"><span data-stu-id="7fd22-122">The freezable class is what gives a brush the ability to find its corresponding generated, low-level objects and to update them when it changes.</span></span> <span data-ttu-id="7fd22-123">この機能を有効にすると、ブラシができない「固定」と言います。</span><span class="sxs-lookup"><span data-stu-id="7fd22-123">When this ability is enabled, the brush is said to be "unfrozen."</span></span>  
  
 <span data-ttu-id="7fd22-124">Freezable の<xref:System.Windows.Freezable.Freeze%2A>メソッドでは、この自己更新機能を無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="7fd22-124">A freezable's <xref:System.Windows.Freezable.Freeze%2A> method enables you to disable this self-updating ability.</span></span> <span data-ttu-id="7fd22-125">このメソッドを使用すると、「固定」、または変更不可能な状態になるブラシを作成します。</span><span class="sxs-lookup"><span data-stu-id="7fd22-125">You can use this method to make the brush become "frozen," or unmodifiable.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7fd22-126">すべて Freezable オブジェクトは固定されていることができます。</span><span class="sxs-lookup"><span data-stu-id="7fd22-126">Not every Freezable object can be frozen.</span></span> <span data-ttu-id="7fd22-127">スローすることを回避するために、 <xref:System.InvalidOperationException>、Freezable オブジェクトの値を確認<xref:System.Windows.Freezable.CanFreeze%2A>プロパティを固定することを試みる前に固定できるかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="7fd22-127">To avoid throwing an <xref:System.InvalidOperationException>, check the value of the Freezable object's <xref:System.Windows.Freezable.CanFreeze%2A> property to determine whether it can be frozen before attempting to freeze it.</span></span>  
  
 [!code-csharp[freezablesample_procedural#FrozenExamplePart2](~/samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#frozenexamplepart2)]
 [!code-vb[freezablesample_procedural#FrozenExamplePart2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#frozenexamplepart2)]  
  
 <span data-ttu-id="7fd22-128">フリーズ可能オブジェクトを変更するが不要になったときに固定パフォーマンス上の利点を提供します。</span><span class="sxs-lookup"><span data-stu-id="7fd22-128">When you no longer need to modify a freezable, freezing it provides performance benefits.</span></span> <span data-ttu-id="7fd22-129">この例では、ブラシを固定する場合は、グラフィックス システムはその変更を監視する必要がなくなります。</span><span class="sxs-lookup"><span data-stu-id="7fd22-129">If you were to freeze the brush in this example, the graphics system would no longer need to monitor it for changes.</span></span> <span data-ttu-id="7fd22-130">グラフィックス システムは、ブラシが変更されないことを知っているために、その他の最適化をこともできます。</span><span class="sxs-lookup"><span data-stu-id="7fd22-130">The graphics system can also make other optimizations, because it knows the brush won't change.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7fd22-131">便宜上、フリーズ可能オブジェクトは、明示的に固定する場合を除き、固定されていない残ります。</span><span class="sxs-lookup"><span data-stu-id="7fd22-131">For convenience, freezable objects remain unfrozen unless you explicitly freeze them.</span></span>  
  
<a name="frozenfreezables"></a>   
## <a name="using-freezables"></a><span data-ttu-id="7fd22-132">フリーズ可能オブジェクトを使用します。</span><span class="sxs-lookup"><span data-stu-id="7fd22-132">Using Freezables</span></span>  
 <span data-ttu-id="7fd22-133">フリーズされていないを使用して freezable はオブジェクトの他の任意の型の使用と同様です。</span><span class="sxs-lookup"><span data-stu-id="7fd22-133">Using an unfrozen freezable is like using any other type of object.</span></span> <span data-ttu-id="7fd22-134">次の例での色、<xref:System.Windows.Media.SolidColorBrush>が黄色から赤に変更されて後、ボタンの背景を描画に使用されます。</span><span class="sxs-lookup"><span data-stu-id="7fd22-134">In the following example, the color of a <xref:System.Windows.Media.SolidColorBrush> is changed from yellow to red after it's used to paint the background of a button.</span></span> <span data-ttu-id="7fd22-135">グラフィックス システムは、バック グラウンドで自動的に変更するボタン黄色から赤に、次に、画面が更新された日時は機能します。</span><span class="sxs-lookup"><span data-stu-id="7fd22-135">The graphics system works behind the scenes to automatically change the button from yellow to red the next time the screen is refreshed.</span></span>  
  
 [!code-csharp[freezablesample_procedural#UnFrozenExampleShort](~/samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#unfrozenexampleshort)]
 [!code-vb[freezablesample_procedural#UnFrozenExampleShort](~/samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#unfrozenexampleshort)]  
  
### <a name="freezing-a-freezable"></a><span data-ttu-id="7fd22-136">フリーズ可能オブジェクトを固定</span><span class="sxs-lookup"><span data-stu-id="7fd22-136">Freezing a Freezable</span></span>  
 <span data-ttu-id="7fd22-137">させる、<xref:System.Windows.Freezable>呼び出す変更不可能な状態は、その<xref:System.Windows.Freezable.Freeze%2A>メソッド。</span><span class="sxs-lookup"><span data-stu-id="7fd22-137">To make a <xref:System.Windows.Freezable> unmodifiable, you call its <xref:System.Windows.Freezable.Freeze%2A> method.</span></span> <span data-ttu-id="7fd22-138">Freezable オブジェクトを格納しているオブジェクトを固定すると、それらのオブジェクトが同様に固定します。</span><span class="sxs-lookup"><span data-stu-id="7fd22-138">When you freeze an object that contains freezable objects, those objects are frozen as well.</span></span> <span data-ttu-id="7fd22-139">固定する場合など、<xref:System.Windows.Media.PathGeometry>図とセグメントが含まれているをすぎるに固定するとします。</span><span class="sxs-lookup"><span data-stu-id="7fd22-139">For example, if you freeze a <xref:System.Windows.Media.PathGeometry>, the figures and segments it contains would be frozen too.</span></span>  
  
 <span data-ttu-id="7fd22-140">Freezable**できません**次のいずれかに該当する場合にフリーズします。</span><span class="sxs-lookup"><span data-stu-id="7fd22-140">A Freezable **can't** be frozen if any of the following are true:</span></span>  
  
- <span data-ttu-id="7fd22-141">アニメーション化されたまたは、データ バインドされたプロパティ。</span><span class="sxs-lookup"><span data-stu-id="7fd22-141">It has animated or data bound properties.</span></span>  
  
- <span data-ttu-id="7fd22-142">動的リソースによって設定されるプロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="7fd22-142">It has properties set by a dynamic resource.</span></span> <span data-ttu-id="7fd22-143">(を参照してください、 [XAML リソース](xaml-resources.md)動的リソースの詳細について)。</span><span class="sxs-lookup"><span data-stu-id="7fd22-143">(See the [XAML Resources](xaml-resources.md) for more information about dynamic resources.)</span></span>  
  
- <span data-ttu-id="7fd22-144">含まれている<xref:System.Windows.Freezable>サブオブジェクトを固定することはできません。</span><span class="sxs-lookup"><span data-stu-id="7fd22-144">It contains <xref:System.Windows.Freezable> sub-objects that can't be frozen.</span></span>  
  
 <span data-ttu-id="7fd22-145">これらの条件が false の場合と、変更する予定がないかどうか、 <xref:System.Windows.Freezable>、その前に説明したパフォーマンスの利点を活用できますを固定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7fd22-145">If these conditions are false, and you don't intend to modify the <xref:System.Windows.Freezable>, then you should freeze it to gain the performance benefits described earlier.</span></span>  
  
 <span data-ttu-id="7fd22-146">Freezable の呼び出す<xref:System.Windows.Freezable.Freeze%2A>メソッドを変更できません。</span><span class="sxs-lookup"><span data-stu-id="7fd22-146">Once you call a freezable's <xref:System.Windows.Freezable.Freeze%2A> method, it can no longer be modified.</span></span> <span data-ttu-id="7fd22-147">固定された変更しようとして原因をオブジェクト、<xref:System.InvalidOperationException>がスローされます。</span><span class="sxs-lookup"><span data-stu-id="7fd22-147">Attempting to modify a frozen object causes an <xref:System.InvalidOperationException> to be thrown.</span></span> <span data-ttu-id="7fd22-148">次のコードは、フリーズした後に、ブラシを変更するために、例外をスローします。</span><span class="sxs-lookup"><span data-stu-id="7fd22-148">The following code throws an exception, because we attempt to modify the brush after it's been frozen.</span></span>  
  
 [!code-csharp[freezablesample_procedural#ExceptionExample](~/samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#exceptionexample)]
 [!code-vb[freezablesample_procedural#ExceptionExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#exceptionexample)]  
  
 <span data-ttu-id="7fd22-149">この例外をスローすることを避けるために使用することができます、<xref:System.Windows.Freezable.IsFrozen%2A>メソッドを決定するかどうかを<xref:System.Windows.Freezable>が固定されています。</span><span class="sxs-lookup"><span data-stu-id="7fd22-149">To avoid throwing this exception, you can use the <xref:System.Windows.Freezable.IsFrozen%2A> method to determine whether a <xref:System.Windows.Freezable> is frozen.</span></span>  
  
 [!code-csharp[freezablesample_procedural#CheckIsFrozenExample](~/samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#checkisfrozenexample)]
 [!code-vb[freezablesample_procedural#CheckIsFrozenExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#checkisfrozenexample)]  
  
 <span data-ttu-id="7fd22-150">上記のコード例では、変更可能なコピーがの固定されたオブジェクトを使用して行われた、<xref:System.Windows.Freezable.Clone%2A>メソッド。</span><span class="sxs-lookup"><span data-stu-id="7fd22-150">In the preceding code example, a modifiable copy was made of a frozen object using the <xref:System.Windows.Freezable.Clone%2A> method.</span></span> <span data-ttu-id="7fd22-151">次のセクションでは、複製の詳細について説明します。</span><span class="sxs-lookup"><span data-stu-id="7fd22-151">The next section discusses cloning in more detail.</span></span>  
  
 <span data-ttu-id="7fd22-152">**注**ため、固定された freezable アニメーション化できません、アニメーション システムが自動的の変更可能な複製を作成固定された<xref:System.Windows.Freezable>オブジェクトを使用してアニメーション化しようとすると、 <xref:System.Windows.Media.Animation.Storyboard>。</span><span class="sxs-lookup"><span data-stu-id="7fd22-152">**Note** Because a frozen freezable cannot be animated, the animation system will automatically create modifiable clones of frozen <xref:System.Windows.Freezable> objects when you try to animate them with a <xref:System.Windows.Media.Animation.Storyboard>.</span></span> <span data-ttu-id="7fd22-153">オーバーヘッドを複製することがパフォーマンスをなくすため、オブジェクトをアニメーション化する場合にマスクされていないままにします。</span><span class="sxs-lookup"><span data-stu-id="7fd22-153">To eliminate the performance overhead caused by cloning, leave an object unfrozen if you intend to animate it.</span></span> <span data-ttu-id="7fd22-154">ストーリー ボードを使用したアニメーション化の詳細については、次を参照してください。、[ストーリー ボードの概要](../graphics-multimedia/storyboards-overview.md)します。</span><span class="sxs-lookup"><span data-stu-id="7fd22-154">For more information about animating with storyboards, see the [Storyboards Overview](../graphics-multimedia/storyboards-overview.md).</span></span>  
  
### <a name="freezing-from-markup"></a><span data-ttu-id="7fd22-155">マークアップからのフリーズ</span><span class="sxs-lookup"><span data-stu-id="7fd22-155">Freezing from Markup</span></span>  
 <span data-ttu-id="7fd22-156">固定するには、<xref:System.Windows.Freezable>オブジェクトを使用する、マークアップで宣言された、`PresentationOptions:Freeze`属性。</span><span class="sxs-lookup"><span data-stu-id="7fd22-156">To freeze a <xref:System.Windows.Freezable> object declared in markup, you use the `PresentationOptions:Freeze` attribute.</span></span> <span data-ttu-id="7fd22-157">次の例では、<xref:System.Windows.Media.SolidColorBrush>はページ リソースとして宣言されており、固定されています。</span><span class="sxs-lookup"><span data-stu-id="7fd22-157">In the following example, a <xref:System.Windows.Media.SolidColorBrush> is declared as a page resource and frozen.</span></span> <span data-ttu-id="7fd22-158">ボタンの背景を設定するのには使用されます。</span><span class="sxs-lookup"><span data-stu-id="7fd22-158">It is then used to set the background of a button.</span></span>  
  
 [!code-xaml[FreezableSample#FreezeFromMarkupWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FreezableSample/CS/FreezeFromMarkupExample.xaml#freezefrommarkupwholepage)]  
  
 <span data-ttu-id="7fd22-159">使用する、`Freeze`属性、プレゼンテーション オプションの名前空間にマップする必要があります:`http://schemas.microsoft.com/winfx/2006/xaml/presentation/options`します。</span><span class="sxs-lookup"><span data-stu-id="7fd22-159">To use the `Freeze` attribute, you must map to the presentation options namespace: `http://schemas.microsoft.com/winfx/2006/xaml/presentation/options`.</span></span> <span data-ttu-id="7fd22-160">`PresentationOptions` この名前空間をマッピングするための推奨されるプレフィックスを示します。</span><span class="sxs-lookup"><span data-stu-id="7fd22-160">`PresentationOptions` is the recommended prefix for mapping this namespace:</span></span>  
  
```  
xmlns:PresentationOptions="http://schemas.microsoft.com/winfx/2006/xaml/presentation/options"   
```  
  
 <span data-ttu-id="7fd22-161">すべての XAML リーダーは、この属性を認識しているためには、使用することをお勧め、 [mc: Ignorable 属性](mc-ignorable-attribute.md)をマークする、`Presentation:Freeze`属性を無視できます。</span><span class="sxs-lookup"><span data-stu-id="7fd22-161">Because not all XAML readers recognize this attribute, it's recommended that you use the [mc:Ignorable Attribute](mc-ignorable-attribute.md) to mark the `Presentation:Freeze` attribute as ignorable:</span></span>  
  
```  
xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"  
mc:Ignorable="PresentationOptions"  
```  
  
 <span data-ttu-id="7fd22-162">詳細については、次を参照してください。、 [mc: Ignorable 属性](mc-ignorable-attribute.md)ページ。</span><span class="sxs-lookup"><span data-stu-id="7fd22-162">For more information, see the [mc:Ignorable Attribute](mc-ignorable-attribute.md) page.</span></span>  
  
### <a name="unfreezing-a-freezable"></a><span data-ttu-id="7fd22-163">「固定解除する」フリーズ可能オブジェクト</span><span class="sxs-lookup"><span data-stu-id="7fd22-163">"Unfreezing" a Freezable</span></span>  
 <span data-ttu-id="7fd22-164">1 回凍結、<xref:System.Windows.Freezable>しない変更またはマスクされていない。 ただし、を使用して、固定された複製を作成することができます、<xref:System.Windows.Freezable.Clone%2A>または<xref:System.Windows.Freezable.CloneCurrentValue%2A>メソッド。</span><span class="sxs-lookup"><span data-stu-id="7fd22-164">Once frozen, a <xref:System.Windows.Freezable> can never be modified or unfrozen; however, you can create an unfrozen clone using the <xref:System.Windows.Freezable.Clone%2A> or <xref:System.Windows.Freezable.CloneCurrentValue%2A> method.</span></span>  
  
 <span data-ttu-id="7fd22-165">次の例では、ブラシを使用して、ボタンの背景を設定し、そのブラシが固定されてします。</span><span class="sxs-lookup"><span data-stu-id="7fd22-165">In the following example, the button's background is set with a brush and that brush is then frozen.</span></span> <span data-ttu-id="7fd22-166">使用して、ブラシの固定のコピーが行われた、<xref:System.Windows.Freezable.Clone%2A>メソッド。</span><span class="sxs-lookup"><span data-stu-id="7fd22-166">An unfrozen copy is made of the brush using the <xref:System.Windows.Freezable.Clone%2A> method.</span></span> <span data-ttu-id="7fd22-167">クローンを変更し、ボタンの背景を黄色から赤に変更するために使用します。</span><span class="sxs-lookup"><span data-stu-id="7fd22-167">The clone is modified and used to change the button's background from yellow to red.</span></span>  
  
 [!code-csharp[freezablesample_procedural#CloneExample](~/samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#cloneexample)]
 [!code-vb[freezablesample_procedural#CloneExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#cloneexample)]  
  
> [!NOTE]
>  <span data-ttu-id="7fd22-168">新しいコピーされませんアニメーションに使用する複製方法に関係なく<xref:System.Windows.Freezable>します。</span><span class="sxs-lookup"><span data-stu-id="7fd22-168">Regardless of which clone method you use, animations are never copied to the new <xref:System.Windows.Freezable>.</span></span>  
  
 <span data-ttu-id="7fd22-169"><xref:System.Windows.Freezable.Clone%2A>と<xref:System.Windows.Freezable.CloneCurrentValue%2A>メソッドは、フリーズ可能オブジェクトの詳細コピーを生成します。</span><span class="sxs-lookup"><span data-stu-id="7fd22-169">The <xref:System.Windows.Freezable.Clone%2A> and <xref:System.Windows.Freezable.CloneCurrentValue%2A> methods produce deep copies of the freezable.</span></span> <span data-ttu-id="7fd22-170">フリーズ可能オブジェクトが含まれている他の freezable オブジェクトのフリーズされた場合も複製、変更可能です。</span><span class="sxs-lookup"><span data-stu-id="7fd22-170">If the freezable contains other frozen freezable objects, they are also cloned and made modifiable.</span></span> <span data-ttu-id="7fd22-171">たとえば、固定された複製する<xref:System.Windows.Media.PathGeometry>を変更できるようにの数値が含まれているセグメントもコピーし、は変更可能です。</span><span class="sxs-lookup"><span data-stu-id="7fd22-171">For example, if you clone a frozen <xref:System.Windows.Media.PathGeometry> to make it modifiable, the figures and segments it contains are also copied and made modifiable.</span></span>  
  
<a name="createyourownfreezableclass"></a>   
## <a name="creating-your-own-freezable-class"></a><span data-ttu-id="7fd22-172">Freezable クラスの作成</span><span class="sxs-lookup"><span data-stu-id="7fd22-172">Creating Your Own Freezable Class</span></span>  
 <span data-ttu-id="7fd22-173">派生したクラス<xref:System.Windows.Freezable>次の機能を取得します。</span><span class="sxs-lookup"><span data-stu-id="7fd22-173">A class that derives from <xref:System.Windows.Freezable> gains the following features.</span></span>  
  
- <span data-ttu-id="7fd22-174">特殊な状態。 読み取り専用 (固定)、書き込み可能な状態です。</span><span class="sxs-lookup"><span data-stu-id="7fd22-174">Special states: a read-only (frozen) and a writable state.</span></span>  
  
- <span data-ttu-id="7fd22-175">スレッド セーフ。 固定された<xref:System.Windows.Freezable>スレッド間で共有することができます。</span><span class="sxs-lookup"><span data-stu-id="7fd22-175">Thread safety: a frozen <xref:System.Windows.Freezable> can be shared across threads.</span></span>  
  
- <span data-ttu-id="7fd22-176">変更の詳細についての通知:その他とは異なり<xref:System.Windows.DependencyObject>、フリーズ可能オブジェクトは変更通知サブ プロパティの値を変更するときにします。</span><span class="sxs-lookup"><span data-stu-id="7fd22-176">Detailed change notification: Unlike other <xref:System.Windows.DependencyObject>s, Freezable objects provide change notifications when sub-property values change.</span></span>  
  
- <span data-ttu-id="7fd22-177">簡単に複製: Freezable クラスは既にディープ クローンを生成するいくつかのメソッドを実装します。</span><span class="sxs-lookup"><span data-stu-id="7fd22-177">Easy cloning: the Freezable class has already implemented several methods that produce deep clones.</span></span>  
  
 <span data-ttu-id="7fd22-178">A<xref:System.Windows.Freezable>の種類は、<xref:System.Windows.DependencyObject>をそのため、依存関係プロパティ システムを使用します。</span><span class="sxs-lookup"><span data-stu-id="7fd22-178">A <xref:System.Windows.Freezable> is a type of <xref:System.Windows.DependencyObject>, and therefore uses the dependency property system.</span></span> <span data-ttu-id="7fd22-179">クラスのプロパティは、依存関係プロパティにする必要はありませんが、ために書き込むがあるコードの量を減らすは依存関係プロパティを使用して、<xref:System.Windows.Freezable>クラスは依存関係プロパティを考慮して設計されました。</span><span class="sxs-lookup"><span data-stu-id="7fd22-179">Your class properties don't have to be dependency properties, but using dependency properties will reduce the amount of code you have to write, because the <xref:System.Windows.Freezable> class was designed with dependency properties in mind.</span></span> <span data-ttu-id="7fd22-180">依存関係プロパティ システムの詳細については、次を参照してください。、[依存関係プロパティの概要](dependency-properties-overview.md)します。</span><span class="sxs-lookup"><span data-stu-id="7fd22-180">For more information about the dependency property system, see the [Dependency Properties Overview](dependency-properties-overview.md).</span></span>  
  
 <span data-ttu-id="7fd22-181">すべて<xref:System.Windows.Freezable>サブクラスをオーバーライドする必要があります、<xref:System.Windows.Freezable.CreateInstanceCore%2A>メソッド。</span><span class="sxs-lookup"><span data-stu-id="7fd22-181">Every <xref:System.Windows.Freezable> subclass must override the <xref:System.Windows.Freezable.CreateInstanceCore%2A> method.</span></span> <span data-ttu-id="7fd22-182">クラスは、そのすべてのデータの依存関係プロパティを使用している場合は、完了します。</span><span class="sxs-lookup"><span data-stu-id="7fd22-182">If your class uses dependency properties for all its data, you're finished.</span></span>  
  
 <span data-ttu-id="7fd22-183">クラスに依存関係のないプロパティのデータ メンバーが含まれている場合は、次のメソッドもオーバーライドする必要があります。</span><span class="sxs-lookup"><span data-stu-id="7fd22-183">If your class contains non-dependency property data members, you must also override the following methods:</span></span>  
  
- <xref:System.Windows.Freezable.CloneCore%2A>  
  
- <xref:System.Windows.Freezable.CloneCurrentValueCore%2A>  
  
- <xref:System.Windows.Freezable.GetAsFrozenCore%2A>  
  
- <xref:System.Windows.Freezable.GetCurrentValueAsFrozenCore%2A>  
  
- <xref:System.Windows.Freezable.FreezeCore%2A>  
  
 <span data-ttu-id="7fd22-184">次のルールにアクセスして、依存関係プロパティではないデータ メンバーへの書き込みにも注意してください。</span><span class="sxs-lookup"><span data-stu-id="7fd22-184">You must also observe the following rules for accessing and writing to data members that are not dependency properties:</span></span>  
  
- <span data-ttu-id="7fd22-185">いずれかの先頭に[!INCLUDE[TLA#tla_api](../../../../includes/tlasharptla-api-md.md)]呼び出し、依存関係のないプロパティのデータ メンバーを読み取る、<xref:System.Windows.Freezable.ReadPreamble%2A>メソッド。</span><span class="sxs-lookup"><span data-stu-id="7fd22-185">At the beginning of any [!INCLUDE[TLA#tla_api](../../../../includes/tlasharptla-api-md.md)] that reads non-dependency property data members, call the <xref:System.Windows.Freezable.ReadPreamble%2A> method.</span></span>  
  
- <span data-ttu-id="7fd22-186">依存関係のないプロパティのデータ メンバーを書き込む任意の API の先頭には、呼び出し、<xref:System.Windows.Freezable.WritePreamble%2A>メソッド。</span><span class="sxs-lookup"><span data-stu-id="7fd22-186">At the beginning of any API that writes non-dependency property data members, call the <xref:System.Windows.Freezable.WritePreamble%2A> method.</span></span> <span data-ttu-id="7fd22-187">(呼び出したら<xref:System.Windows.Freezable.WritePreamble%2A>で、[!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)]への呼び出しを追加する必要はありません<xref:System.Windows.Freezable.ReadPreamble%2A>も非依存関係プロパティのデータ メンバーを読み取るかどうかです)。</span><span class="sxs-lookup"><span data-stu-id="7fd22-187">(Once you've called <xref:System.Windows.Freezable.WritePreamble%2A> in an [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)], you don't need to make an additional call to <xref:System.Windows.Freezable.ReadPreamble%2A> if you also read non-dependency property data members.)</span></span>  
  
- <span data-ttu-id="7fd22-188">呼び出す、<xref:System.Windows.Freezable.WritePostscript%2A>依存関係のないプロパティのデータ メンバーへの書き込みメソッドを終了する前にメソッド。</span><span class="sxs-lookup"><span data-stu-id="7fd22-188">Call the <xref:System.Windows.Freezable.WritePostscript%2A> method before exiting methods that write to non-dependency property data members.</span></span>  
  
 <span data-ttu-id="7fd22-189">クラスにある非依存関係プロパティのデータ メンバーが含まれて かどうか<xref:System.Windows.DependencyObject>オブジェクトも呼び出す必要があります、<xref:System.Windows.Freezable.OnFreezablePropertyChanged%2A>メソッドは、メンバーを設定している場合でも、その値のいずれかを変更するたびに`null`します。</span><span class="sxs-lookup"><span data-stu-id="7fd22-189">If your class contains non-dependency-property data members that are <xref:System.Windows.DependencyObject> objects, you must also call the <xref:System.Windows.Freezable.OnFreezablePropertyChanged%2A> method each time you change one of their values, even if you're setting the member to `null`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7fd22-190">各を開始することが非常に重要<xref:System.Windows.Freezable>基本実装への呼び出しでオーバーライドするメソッド。</span><span class="sxs-lookup"><span data-stu-id="7fd22-190">It's very important that you begin each <xref:System.Windows.Freezable> method you override with a call to the base implementation.</span></span>  
  
 <span data-ttu-id="7fd22-191">カスタムの例については<xref:System.Windows.Freezable>クラスを参照してください、[カスタム アニメーションのサンプル](https://go.microsoft.com/fwlink/?LinkID=159981)します。</span><span class="sxs-lookup"><span data-stu-id="7fd22-191">For an example of a custom <xref:System.Windows.Freezable> class, see the [Custom Animation Sample](https://go.microsoft.com/fwlink/?LinkID=159981).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7fd22-192">関連項目</span><span class="sxs-lookup"><span data-stu-id="7fd22-192">See also</span></span>

- <xref:System.Windows.Freezable>
- [<span data-ttu-id="7fd22-193">カスタム アニメーションのサンプル</span><span class="sxs-lookup"><span data-stu-id="7fd22-193">Custom Animation Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=159981)
- [<span data-ttu-id="7fd22-194">依存関係プロパティの概要</span><span class="sxs-lookup"><span data-stu-id="7fd22-194">Dependency Properties Overview</span></span>](dependency-properties-overview.md)
- [<span data-ttu-id="7fd22-195">カスタム依存関係プロパティ</span><span class="sxs-lookup"><span data-stu-id="7fd22-195">Custom Dependency Properties</span></span>](custom-dependency-properties.md)
