---
title: 弱いイベント パターン
ms.date: 03/30/2017
helpviewer_keywords:
- weak event pattern implementation [WPF]
- event handlers [WPF], weak event pattern
- IWeakEventListener interface [WPF]
ms.assetid: e7c62920-4812-4811-94d8-050a65c856f6
ms.openlocfilehash: e0cd6837de626fa6bcd560811c6a70f7f6604daa
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59316168"
---
# <a name="weak-event-patterns"></a><span data-ttu-id="d19f2-102">弱いイベント パターン</span><span class="sxs-lookup"><span data-stu-id="d19f2-102">Weak Event Patterns</span></span>
<span data-ttu-id="d19f2-103">アプリケーションでは、イベント ソースに接続されているハンドラーがハンドラーをソースに接続されているリスナーのオブジェクトと連携して破棄されないです。</span><span class="sxs-lookup"><span data-stu-id="d19f2-103">In applications, it is possible that handlers that are attached to event sources will not be destroyed in coordination with the listener object that attached the handler to the source.</span></span> <span data-ttu-id="d19f2-104">このような状況は、メモリ リークにつながります。</span><span class="sxs-lookup"><span data-stu-id="d19f2-104">This situation can lead to memory leaks.</span></span> [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] <span data-ttu-id="d19f2-105">特定のイベントの専任マネージャー クラスを提供することでそのイベントのリスナー インターフェイスを実装してこの問題に対処するために使用する設計パターンについて説明します。</span><span class="sxs-lookup"><span data-stu-id="d19f2-105">introduces a design pattern that can be used to address this issue, by providing a dedicated manager class for particular events and implementing an interface on listeners for that event.</span></span> <span data-ttu-id="d19f2-106">この設計パターンと呼ばれる、*弱いイベント パターン*します。</span><span class="sxs-lookup"><span data-stu-id="d19f2-106">This design pattern is known as the *weak event pattern*.</span></span>  
  
## <a name="why-implement-the-weak-event-pattern"></a><span data-ttu-id="d19f2-107">弱いイベント パターンを実装する理由</span><span class="sxs-lookup"><span data-stu-id="d19f2-107">Why Implement the Weak Event Pattern?</span></span>  
 <span data-ttu-id="d19f2-108">イベントのリッスンは、メモリ リークにつながります。</span><span class="sxs-lookup"><span data-stu-id="d19f2-108">Listening for events can lead to memory leaks.</span></span> <span data-ttu-id="d19f2-109">イベントをリッスンするための一般的な手法では、ソースでのイベントにハンドラーをアタッチする言語固有の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="d19f2-109">The typical technique for listening to an event is to use the language-specific syntax that attaches a handler to an event on a source.</span></span> <span data-ttu-id="d19f2-110">たとえば、 C#、構文がある:`source.SomeEvent += new SomeEventHandler(MyEventHandler)`します。</span><span class="sxs-lookup"><span data-stu-id="d19f2-110">For example, in C#, that syntax is: `source.SomeEvent += new SomeEventHandler(MyEventHandler)`.</span></span>  
  
 <span data-ttu-id="d19f2-111">この手法は、イベント リスナーをイベント ソースからの強い参照を作成します。</span><span class="sxs-lookup"><span data-stu-id="d19f2-111">This technique creates a strong reference from the event source to the event listener.</span></span> <span data-ttu-id="d19f2-112">通常、リスナーのイベント ハンドラーをアタッチするオブジェクトの有効期間は、ソースのオブジェクトの有効期間によって影響を受ける (ない場合、イベント ハンドラーが明示的に削除) を使用するリスナーと、します。</span><span class="sxs-lookup"><span data-stu-id="d19f2-112">Ordinarily, attaching an event handler for a listener causes the listener to have an object lifetime that is influenced by the object lifetime of the source (unless the event handler is explicitly removed).</span></span> <span data-ttu-id="d19f2-113">ただし、特定の状況で、ソースの有効期間ではなく、アプリケーションのビジュアル ツリーに現在属しているかどうかなど、他の要因によって制御するリスナーのオブジェクトの有効期間をする可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d19f2-113">But in certain circumstances, you might want the object lifetime of the listener to be controlled by other factors, such as whether it currently belongs to the visual tree of the application, and not by the lifetime of the source.</span></span> <span data-ttu-id="d19f2-114">ソース オブジェクトの有効期間が、リスナーのオブジェクトの有効期間を超えるたびに通常のイベント パターンにより、メモリ リーク。 リスナーは長い時間動作させるためのものよりもします。</span><span class="sxs-lookup"><span data-stu-id="d19f2-114">Whenever the source object lifetime extends beyond the object lifetime of the listener, the normal event pattern leads to a memory leak: the listener is kept alive longer than intended.</span></span>  
  
 <span data-ttu-id="d19f2-115">弱いイベント パターンは、このメモリ リークの問題を解決するために設計されています。</span><span class="sxs-lookup"><span data-stu-id="d19f2-115">The weak event pattern is designed to solve this memory leak problem.</span></span> <span data-ttu-id="d19f2-116">リスナーは、イベントに登録する必要がありますが、リスナーは明示的に認識されませんの登録を解除するたびに、弱いイベント パターンを使用できます。</span><span class="sxs-lookup"><span data-stu-id="d19f2-116">The weak event pattern can be used whenever a listener needs to register for an event, but the listener does not explicitly know when to unregister.</span></span> <span data-ttu-id="d19f2-117">弱いイベント パターンは、ソースのオブジェクトの有効期間は、リスナーの役に立つオブジェクトの有効期間を超えた場合にも使用できます。</span><span class="sxs-lookup"><span data-stu-id="d19f2-117">The weak event pattern can also be used whenever the object lifetime of the source exceeds the useful object lifetime of the listener.</span></span> <span data-ttu-id="d19f2-118">(この場合、*便利な*するによって決定されます)。弱いイベント パターンは、リスナーを登録し、任意の方法でリスナーのオブジェクトの有効期間の特性に影響を与えずに、イベントを受信できます。</span><span class="sxs-lookup"><span data-stu-id="d19f2-118">(In this case, *useful* is determined by you.) The weak event pattern allows the listener to register for and receive the event without affecting the object lifetime characteristics of the listener in any way.</span></span> <span data-ttu-id="d19f2-119">実際には、ソースからの暗黙的な参照では、リスナーは、ガベージ コレクションの対象かどうかは不明です。</span><span class="sxs-lookup"><span data-stu-id="d19f2-119">In effect, the implied reference from the source does not determine whether the listener is eligible for garbage collection.</span></span> <span data-ttu-id="d19f2-120">参照が弱いイベント パターンと、関連の名前付けため、弱い参照[!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="d19f2-120">The reference is a weak reference, thus the naming of the weak event pattern and the related [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)].</span></span> <span data-ttu-id="d19f2-121">リスナーはガベージ収集または破棄されるそれ以外の場合、ソースが破棄されたオブジェクトへの要素も形成ハンドラーの参照を保持せずに続行できます。</span><span class="sxs-lookup"><span data-stu-id="d19f2-121">The listener can be garbage collected or otherwise destroyed, and the source can continue without retaining noncollectible handler references to a now destroyed object.</span></span>  
  
## <a name="who-should-implement-the-weak-event-pattern"></a><span data-ttu-id="d19f2-122">弱いイベント パターンを実装する必要がありますか。</span><span class="sxs-lookup"><span data-stu-id="d19f2-122">Who Should Implement the Weak Event Pattern?</span></span>  
 <span data-ttu-id="d19f2-123">弱いイベント パターンの実装は、主にコントロールの作成者にとって重要です。</span><span class="sxs-lookup"><span data-stu-id="d19f2-123">Implementing the weak event pattern is interesting primarily for control authors.</span></span> <span data-ttu-id="d19f2-124">コントロールの作成者は、動作と、コントロールとを挿入するアプリケーションに与える影響を抑制担当大きくします。</span><span class="sxs-lookup"><span data-stu-id="d19f2-124">As a control author, you are largely responsible for the behavior and containment of your control and the impact it has on applications in which it is inserted.</span></span> <span data-ttu-id="d19f2-125">これが含まれています、コントロール オブジェクトの有効期間動作には具体的に説明されているメモリ リークの問題の処理には。</span><span class="sxs-lookup"><span data-stu-id="d19f2-125">This includes the control object lifetime behavior, in particular the handling of the described memory leak problem.</span></span>  
  
 <span data-ttu-id="d19f2-126">特定のシナリオでは、弱いイベント パターンのアプリケーションに自体本質的に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="d19f2-126">Certain scenarios inherently lend themselves to the application of the weak event pattern.</span></span> <span data-ttu-id="d19f2-127">このような 1 つのシナリオは、データ バインディングです。</span><span class="sxs-lookup"><span data-stu-id="d19f2-127">One such scenario is data binding.</span></span> <span data-ttu-id="d19f2-128">データ バインディングでは、バインディングのターゲットとなるリスナー オブジェクトの完全に独立したソース オブジェクトの一般的なは。</span><span class="sxs-lookup"><span data-stu-id="d19f2-128">In data binding, it is common for the source object to be completely independent of the listener object, which is a target of a binding.</span></span> <span data-ttu-id="d19f2-129">さまざまな側面[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]弱いイベント パターン、イベントの実装方法に適用されるバインディングが既にデータがあります。</span><span class="sxs-lookup"><span data-stu-id="d19f2-129">Many aspects of [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] data binding already have the weak event pattern applied in how the events are implemented.</span></span>  
  
## <a name="how-to-implement-the-weak-event-pattern"></a><span data-ttu-id="d19f2-130">弱いイベント パターンを実装する方法</span><span class="sxs-lookup"><span data-stu-id="d19f2-130">How to Implement the Weak Event Pattern</span></span>  
 <span data-ttu-id="d19f2-131">弱いイベント パターンを実装する次の 3 つの方法はあります。</span><span class="sxs-lookup"><span data-stu-id="d19f2-131">There are three ways to implement weak event pattern.</span></span> <span data-ttu-id="d19f2-132">次の表は、3 つの方法を示し、それぞれを使用する際のガイダンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="d19f2-132">The following table lists the three approaches and provides some guidance for when you should use each.</span></span>  
  
|<span data-ttu-id="d19f2-133">方法</span><span class="sxs-lookup"><span data-stu-id="d19f2-133">Approach</span></span>|<span data-ttu-id="d19f2-134">いつ実装するには</span><span class="sxs-lookup"><span data-stu-id="d19f2-134">When to Implement</span></span>|  
|--------------|-----------------------|  
|<span data-ttu-id="d19f2-135">既存の弱いイベント マネージャー クラスを使用して、</span><span class="sxs-lookup"><span data-stu-id="d19f2-135">Use an existing weak event manager class</span></span>|<span data-ttu-id="d19f2-136">サブスクライブするイベントに対応する場合<xref:System.Windows.WeakEventManager>、既存の弱いイベント マネージャーを使用します。</span><span class="sxs-lookup"><span data-stu-id="d19f2-136">If the event you want to subscribe to has a corresponding <xref:System.Windows.WeakEventManager>, use the existing weak event manager.</span></span> <span data-ttu-id="d19f2-137">WPF に含まれている弱いイベント マネージャーの一覧での継承階層を参照してください、<xref:System.Windows.WeakEventManager>クラス。</span><span class="sxs-lookup"><span data-stu-id="d19f2-137">For a list of weak event managers that are included with WPF, see the inheritance hierarchy in the <xref:System.Windows.WeakEventManager> class.</span></span> <span data-ttu-id="d19f2-138">弱いイベントが含まれるマネージャーは、制限付きであるために、他の方法のいずれかを選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d19f2-138">Because the included weak event managers are limited, you will probably need to choose one of the other approaches.</span></span>|  
|<span data-ttu-id="d19f2-139">ジェネリックの弱いイベント マネージャー クラスを使用します。</span><span class="sxs-lookup"><span data-stu-id="d19f2-139">Use a generic weak event manager class</span></span>|<span data-ttu-id="d19f2-140">ジェネリックを使用して、<xref:System.Windows.WeakEventManager%602>既存<xref:System.Windows.WeakEventManager>効率性について利用できないを実装する簡単な方法を必要し、していない懸念しています。</span><span class="sxs-lookup"><span data-stu-id="d19f2-140">Use a generic <xref:System.Windows.WeakEventManager%602> when an existing <xref:System.Windows.WeakEventManager> is not available, you want an easy way to implement, and you are not concerned about efficiency.</span></span> <span data-ttu-id="d19f2-141">ジェネリック<xref:System.Windows.WeakEventManager%602>既存またはカスタムの弱いイベント マネージャーより非効率です。</span><span class="sxs-lookup"><span data-stu-id="d19f2-141">The generic <xref:System.Windows.WeakEventManager%602> is less efficient than an existing or custom weak event manager.</span></span> <span data-ttu-id="d19f2-142">たとえば、ジェネリック クラスは、discover イベントのイベントの名前を指定するために複数のリフレクションが。</span><span class="sxs-lookup"><span data-stu-id="d19f2-142">For example, the generic class does more reflection to discover the event given the event's name.</span></span> <span data-ttu-id="d19f2-143">ジェネリックを使用して、イベントを登録するコードも、<xref:System.Windows.WeakEventManager%602>より既存を使用するよりも詳細またはカスタム<xref:System.Windows.WeakEventManager>します。</span><span class="sxs-lookup"><span data-stu-id="d19f2-143">Also, the code to register the event by using the generic <xref:System.Windows.WeakEventManager%602> is more verbose than using an existing or custom <xref:System.Windows.WeakEventManager>.</span></span>|  
|<span data-ttu-id="d19f2-144">カスタムの弱いイベント マネージャー クラスを作成します。</span><span class="sxs-lookup"><span data-stu-id="d19f2-144">Create a custom weak event manager class</span></span>|<span data-ttu-id="d19f2-145">カスタムを作成する<xref:System.Windows.WeakEventManager>既存<xref:System.Windows.WeakEventManager>をご利用いただけません最適な効率性を必要とします。</span><span class="sxs-lookup"><span data-stu-id="d19f2-145">Create a custom <xref:System.Windows.WeakEventManager> when an existing <xref:System.Windows.WeakEventManager> is not available and you want the best efficiency.</span></span> <span data-ttu-id="d19f2-146">カスタムを使用して<xref:System.Windows.WeakEventManager>をサブスクライブするイベントをより効率的になりますが、先頭に複数のコードを作成するコストが発生する操作を行います。</span><span class="sxs-lookup"><span data-stu-id="d19f2-146">Using a custom <xref:System.Windows.WeakEventManager> to subscribe to an event will be more efficient, but you do incur the cost of writing more code at the beginning.</span></span>|  
|<span data-ttu-id="d19f2-147">サード パーティ製の弱いイベント マネージャーを使用します。</span><span class="sxs-lookup"><span data-stu-id="d19f2-147">Use a third-party weak event manager</span></span>|<span data-ttu-id="d19f2-148">NuGet が[いくつかの弱いイベント マネージャー](https://www.nuget.org/packages?q=weak+event+manager&prerel=false)と WPF の多くのフレームワークは、パターンもサポート (たとえばを参照してください[疎結合イベント サブスクリプションの Prism のドキュメント](https://github.com/PrismLibrary/Prism-Documentation/blob/master/docs/wpf/Communication.md#subscribing-to-events))。</span><span class="sxs-lookup"><span data-stu-id="d19f2-148">NuGet has [several weak event managers](https://www.nuget.org/packages?q=weak+event+manager&prerel=false) and many WPF frameworks also support the pattern (for instance, see [Prism's documentation on loosely coupled event subscription](https://github.com/PrismLibrary/Prism-Documentation/blob/master/docs/wpf/Communication.md#subscribing-to-events)).</span></span>|

 <span data-ttu-id="d19f2-149">次のセクションでは、弱いイベント パターンを実装する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="d19f2-149">The following sections describe how to implement the weak event pattern.</span></span>  <span data-ttu-id="d19f2-150">この説明のためは、サブスクライブするイベントは、次の特性を持ちます。</span><span class="sxs-lookup"><span data-stu-id="d19f2-150">For purposes of this discussion, the event to subscribe to has the following characteristics.</span></span>  
  
-   <span data-ttu-id="d19f2-151">イベントの名前は`SomeEvent`します。</span><span class="sxs-lookup"><span data-stu-id="d19f2-151">The event name is `SomeEvent`.</span></span>  
  
-   <span data-ttu-id="d19f2-152">イベントが発生した、`EventSource`クラス。</span><span class="sxs-lookup"><span data-stu-id="d19f2-152">The event is raised by the `EventSource` class.</span></span>  
  
-   <span data-ttu-id="d19f2-153">イベント ハンドラーが型: `SomeEventEventHandler` (または`EventHandler<SomeEventEventArgs>`)。</span><span class="sxs-lookup"><span data-stu-id="d19f2-153">The event handler has type: `SomeEventEventHandler` (or `EventHandler<SomeEventEventArgs>`).</span></span>  
  
-   <span data-ttu-id="d19f2-154">このイベントは、型のパラメーターを渡します`SomeEventEventArgs`イベント ハンドラーにします。</span><span class="sxs-lookup"><span data-stu-id="d19f2-154">The event passes a parameter of type `SomeEventEventArgs` to the event handlers.</span></span>  
  
### <a name="using-an-existing-weak-event-manager-class"></a><span data-ttu-id="d19f2-155">既存の弱いイベント マネージャー クラスを使用します。</span><span class="sxs-lookup"><span data-stu-id="d19f2-155">Using an Existing Weak Event Manager Class</span></span>  
  
1. <span data-ttu-id="d19f2-156">既存の弱いイベント マネージャーを検索します。</span><span class="sxs-lookup"><span data-stu-id="d19f2-156">Find an existing weak event manager.</span></span>  
  
     <span data-ttu-id="d19f2-157">WPF に含まれている弱いイベント マネージャーの一覧での継承階層を参照してください、<xref:System.Windows.WeakEventManager>クラス。</span><span class="sxs-lookup"><span data-stu-id="d19f2-157">For a list of weak event managers that are included with WPF, see the inheritance hierarchy in the <xref:System.Windows.WeakEventManager> class.</span></span>  
  
2. <span data-ttu-id="d19f2-158">通常のイベント フックアップではなく、新しい弱いイベント マネージャーを使用します。</span><span class="sxs-lookup"><span data-stu-id="d19f2-158">Use the new weak event manager instead of the normal event hookup.</span></span>  
  
     <span data-ttu-id="d19f2-159">たとえば、コードでは、次のパターンを使用して、イベントにサブスクライブするとします。</span><span class="sxs-lookup"><span data-stu-id="d19f2-159">For example, if your code uses the following pattern to subscribe to an event:</span></span>  
  
    ```  
    source.SomeEvent += new SomeEventEventHandler(OnSomeEvent);  
    ```  
  
     <span data-ttu-id="d19f2-160">次のパターンに変更します。</span><span class="sxs-lookup"><span data-stu-id="d19f2-160">Change it to the following pattern:</span></span>  
  
    ```  
    SomeEventWeakEventManager.AddHandler(source, OnSomeEvent);  
    ```  
  
     <span data-ttu-id="d19f2-161">同様に、コードでは、次のパターンを使用して、イベント サブスクリプションを解除する場合。</span><span class="sxs-lookup"><span data-stu-id="d19f2-161">Similarly, if your code uses the following pattern to unsubscribe from an event:</span></span>  
  
    ```  
    source.SomeEvent -= new SomeEventEventHandler(OnSome);  
    ```  
  
     <span data-ttu-id="d19f2-162">次のパターンに変更します。</span><span class="sxs-lookup"><span data-stu-id="d19f2-162">Change it to the following pattern:</span></span>  
  
    ```  
    SomeEventWeakEventManager.RemoveHandler(source, OnSomeEvent);  
    ```  
  
### <a name="using-the-generic-weak-event-manager-class"></a><span data-ttu-id="d19f2-163">ジェネリックの弱いイベント マネージャー クラスを使用します。</span><span class="sxs-lookup"><span data-stu-id="d19f2-163">Using the Generic Weak Event Manager Class</span></span>  
  
1. <span data-ttu-id="d19f2-164">ジェネリックを使用して、<xref:System.Windows.WeakEventManager%602>通常のイベント フックアップではなくクラス。</span><span class="sxs-lookup"><span data-stu-id="d19f2-164">Use the generic <xref:System.Windows.WeakEventManager%602> class instead of the normal event hookup.</span></span>  
  
     <span data-ttu-id="d19f2-165">使用すると<xref:System.Windows.WeakEventManager%602>イベント リスナーを登録するには、イベント ソースを指定し、<xref:System.EventArgs>クラスと呼び出しに型パラメーターとして型<xref:System.Windows.WeakEventManager%602.AddHandler%2A>次のコードに示すように。</span><span class="sxs-lookup"><span data-stu-id="d19f2-165">When you use <xref:System.Windows.WeakEventManager%602> to register event listeners, you supply the event source and <xref:System.EventArgs> type as the type parameters to the class and call <xref:System.Windows.WeakEventManager%602.AddHandler%2A> as shown in the following code:</span></span>  
  
    ```  
    WeakEventManager<EventSource, SomeEventEventArgs>.AddHandler(source, "SomeEvent", source_SomeEvent);  
    ```  
  
### <a name="creating-a-custom-weak-event-manager-class"></a><span data-ttu-id="d19f2-166">カスタムの弱いイベント マネージャー クラスを作成します。</span><span class="sxs-lookup"><span data-stu-id="d19f2-166">Creating a Custom Weak Event Manager Class</span></span>  
  
1. <span data-ttu-id="d19f2-167">次のクラス テンプレートをプロジェクトにコピーします。</span><span class="sxs-lookup"><span data-stu-id="d19f2-167">Copy the following class template to your project.</span></span>  
  
     <span data-ttu-id="d19f2-168">このクラスから継承、<xref:System.Windows.WeakEventManager>クラス。</span><span class="sxs-lookup"><span data-stu-id="d19f2-168">This class inherits from the <xref:System.Windows.WeakEventManager> class.</span></span>  
  
     [!code-csharp[WeakEvents#WeakEventManagerTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/WeakEvents/CSharp/WeakEventManagerTemplate.cs#weakeventmanagertemplate)]  
  
2. <span data-ttu-id="d19f2-169">置換、`SomeEventWeakEventManager`名に置き換えて名前。</span><span class="sxs-lookup"><span data-stu-id="d19f2-169">Replace the `SomeEventWeakEventManager` name with your own name.</span></span>  
  
3. <span data-ttu-id="d19f2-170">前に、イベントの名前と説明した 3 つの名前に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="d19f2-170">Replace the three names described previously with the corresponding names for your event.</span></span> <span data-ttu-id="d19f2-171">(`SomeEvent`、 `EventSource`、および`SomeEventEventArgs`)</span><span class="sxs-lookup"><span data-stu-id="d19f2-171">(`SomeEvent`, `EventSource`, and `SomeEventEventArgs`)</span></span>  
  
4. <span data-ttu-id="d19f2-172">管理イベントと同様に表示するには、弱いイベント マネージャー クラスの可視性 (パブリック/内部/プライベート) を設定します。</span><span class="sxs-lookup"><span data-stu-id="d19f2-172">Set the visibility (public / internal / private) of the weak event manager class to the same visibility as event it manages.</span></span>  
  
5. <span data-ttu-id="d19f2-173">通常のイベント フックアップではなく、新しい弱いイベント マネージャーを使用します。</span><span class="sxs-lookup"><span data-stu-id="d19f2-173">Use the new weak event manager instead of the normal event hookup.</span></span>  
  
     <span data-ttu-id="d19f2-174">たとえば、コードでは、次のパターンを使用して、イベントにサブスクライブするとします。</span><span class="sxs-lookup"><span data-stu-id="d19f2-174">For example, if your code uses the following pattern to subscribe to an event:</span></span>  
  
    ```  
    source.SomeEvent += new SomeEventEventHandler(OnSomeEvent);  
    ```  
  
     <span data-ttu-id="d19f2-175">次のパターンに変更します。</span><span class="sxs-lookup"><span data-stu-id="d19f2-175">Change it to the following pattern:</span></span>  
  
    ```  
    SomeEventWeakEventManager.AddHandler(source, OnSomeEvent);  
    ```  
  
     <span data-ttu-id="d19f2-176">同様に、コードは、イベントをアンサブスク ライブする次のパターンを使用する場合。</span><span class="sxs-lookup"><span data-stu-id="d19f2-176">Similarly, if your code uses the following pattern to unsubscribe to an event:</span></span>  
  
    ```  
    source.SomeEvent -= new SomeEventEventHandler(OnSome);  
    ```  
  
     <span data-ttu-id="d19f2-177">次のパターンに変更します。</span><span class="sxs-lookup"><span data-stu-id="d19f2-177">Change it to the following pattern:</span></span>  
  
    ```  
    SomeEventWeakEventManager.RemoveHandler(source, OnSomeEvent);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="d19f2-178">関連項目</span><span class="sxs-lookup"><span data-stu-id="d19f2-178">See also</span></span>

- <xref:System.Windows.WeakEventManager>
- <xref:System.Windows.IWeakEventListener>
- [<span data-ttu-id="d19f2-179">ルーティング イベントの概要</span><span class="sxs-lookup"><span data-stu-id="d19f2-179">Routed Events Overview</span></span>](routed-events-overview.md)
- [<span data-ttu-id="d19f2-180">データ バインディングの概要</span><span class="sxs-lookup"><span data-stu-id="d19f2-180">Data Binding Overview</span></span>](../data/data-binding-overview.md)
