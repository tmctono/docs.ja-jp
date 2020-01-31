---
title: 弱いイベント パターン
ms.date: 03/30/2017
helpviewer_keywords:
- weak event pattern implementation [WPF]
- event handlers [WPF], weak event pattern
- IWeakEventListener interface [WPF]
ms.assetid: e7c62920-4812-4811-94d8-050a65c856f6
ms.openlocfilehash: 9f61a5a60b2ba1305158d1ab570079fe6aac19ac
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2020
ms.locfileid: "76870741"
---
# <a name="weak-event-patterns"></a><span data-ttu-id="4bd5c-102">弱いイベント パターン</span><span class="sxs-lookup"><span data-stu-id="4bd5c-102">Weak Event Patterns</span></span>
<span data-ttu-id="4bd5c-103">アプリケーションでは、イベントソースにアタッチされているハンドラーが、ハンドラーをソースにアタッチしたリスナーオブジェクトと連携して破棄されない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="4bd5c-103">In applications, it is possible that handlers that are attached to event sources will not be destroyed in coordination with the listener object that attached the handler to the source.</span></span> <span data-ttu-id="4bd5c-104">このような状況では、メモリリークが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="4bd5c-104">This situation can lead to memory leaks.</span></span> [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] <span data-ttu-id="4bd5c-105">では、特定のイベントに専用のマネージャークラスを提供し、そのイベントのリスナーにインターフェイスを実装することによって、この問題に対処するために使用できるデザインパターンが導入されています。</span><span class="sxs-lookup"><span data-stu-id="4bd5c-105">introduces a design pattern that can be used to address this issue, by providing a dedicated manager class for particular events and implementing an interface on listeners for that event.</span></span> <span data-ttu-id="4bd5c-106">この設計パターンは、*弱いイベントパターン*と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="4bd5c-106">This design pattern is known as the *weak event pattern*.</span></span>  
  
## <a name="why-implement-the-weak-event-pattern"></a><span data-ttu-id="4bd5c-107">弱いイベントパターンを実装する理由</span><span class="sxs-lookup"><span data-stu-id="4bd5c-107">Why Implement the Weak Event Pattern?</span></span>  
 <span data-ttu-id="4bd5c-108">イベントをリッスンすると、メモリリークが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="4bd5c-108">Listening for events can lead to memory leaks.</span></span> <span data-ttu-id="4bd5c-109">イベントをリッスンする一般的な方法は、ソースのイベントにハンドラーを関連付ける言語固有の構文を使用することです。</span><span class="sxs-lookup"><span data-stu-id="4bd5c-109">The typical technique for listening to an event is to use the language-specific syntax that attaches a handler to an event on a source.</span></span> <span data-ttu-id="4bd5c-110">たとえば、でC#は、この構文は `source.SomeEvent += new SomeEventHandler(MyEventHandler)`です。</span><span class="sxs-lookup"><span data-stu-id="4bd5c-110">For example, in C#, that syntax is: `source.SomeEvent += new SomeEventHandler(MyEventHandler)`.</span></span>  
  
 <span data-ttu-id="4bd5c-111">この手法では、イベントソースからイベントリスナーへの強い参照が作成されます。</span><span class="sxs-lookup"><span data-stu-id="4bd5c-111">This technique creates a strong reference from the event source to the event listener.</span></span> <span data-ttu-id="4bd5c-112">通常、リスナーのイベントハンドラーをアタッチすると、リスナーには、ソースのオブジェクトの有効期間の影響を受けるオブジェクトの有効期間が設定されます (イベントハンドラーが明示的に削除されていない場合)。</span><span class="sxs-lookup"><span data-stu-id="4bd5c-112">Ordinarily, attaching an event handler for a listener causes the listener to have an object lifetime that is influenced by the object lifetime of the source (unless the event handler is explicitly removed).</span></span> <span data-ttu-id="4bd5c-113">ただし、特定の状況では、リスナーのオブジェクトの有効期間を、ソースの有効期間ではなく、アプリケーションのビジュアルツリーに現在属しているかどうかなど、他の要因によって制御する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="4bd5c-113">But in certain circumstances, you might want the object lifetime of the listener to be controlled by other factors, such as whether it currently belongs to the visual tree of the application, and not by the lifetime of the source.</span></span> <span data-ttu-id="4bd5c-114">ソースオブジェクトの有効期間がリスナーのオブジェクトの有効期間を超えた場合、通常のイベントパターンはメモリリークにつながります。リスナーは意図した時間より長く維持されます。</span><span class="sxs-lookup"><span data-stu-id="4bd5c-114">Whenever the source object lifetime extends beyond the object lifetime of the listener, the normal event pattern leads to a memory leak: the listener is kept alive longer than intended.</span></span>  
  
 <span data-ttu-id="4bd5c-115">弱いイベントパターンは、このメモリリークの問題を解決するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="4bd5c-115">The weak event pattern is designed to solve this memory leak problem.</span></span> <span data-ttu-id="4bd5c-116">弱いイベントパターンは、リスナーがイベントに登録する必要がある場合に使用できますが、登録解除のタイミングをリスナーが明示的に認識していません。</span><span class="sxs-lookup"><span data-stu-id="4bd5c-116">The weak event pattern can be used whenever a listener needs to register for an event, but the listener does not explicitly know when to unregister.</span></span> <span data-ttu-id="4bd5c-117">弱いイベントパターンは、ソースのオブジェクトの有効期間がリスナーの有効なオブジェクトの有効期間を超えた場合にも使用できます。</span><span class="sxs-lookup"><span data-stu-id="4bd5c-117">The weak event pattern can also be used whenever the object lifetime of the source exceeds the useful object lifetime of the listener.</span></span> <span data-ttu-id="4bd5c-118">(この場合、*役に立ち*ます)。弱いイベントパターンを使用すると、リスナーは、リスナーのオブジェクトの有効期間特性に一切影響を与えずに、イベントの登録と受信を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="4bd5c-118">(In this case, *useful* is determined by you.) The weak event pattern allows the listener to register for and receive the event without affecting the object lifetime characteristics of the listener in any way.</span></span> <span data-ttu-id="4bd5c-119">実際には、ソースからの暗黙的な参照では、リスナーがガベージコレクションの対象であるかどうかは判断されません。</span><span class="sxs-lookup"><span data-stu-id="4bd5c-119">In effect, the implied reference from the source does not determine whether the listener is eligible for garbage collection.</span></span> <span data-ttu-id="4bd5c-120">参照は弱い参照であるため、弱いイベントパターンと関連する Api の名前が付けられます。</span><span class="sxs-lookup"><span data-stu-id="4bd5c-120">The reference is a weak reference, thus the naming of the weak event pattern and the related APIs.</span></span> <span data-ttu-id="4bd5c-121">リスナーは、ガベージコレクションを実行したり、破棄したりすることができます。また、破棄されたオブジェクトへの非収集ハンドラー参照を保持せずに、ソースを継続できます。</span><span class="sxs-lookup"><span data-stu-id="4bd5c-121">The listener can be garbage collected or otherwise destroyed, and the source can continue without retaining noncollectible handler references to a now destroyed object.</span></span>  
  
## <a name="who-should-implement-the-weak-event-pattern"></a><span data-ttu-id="4bd5c-122">弱いイベントパターンを実装する必要があるのはだれですか。</span><span class="sxs-lookup"><span data-stu-id="4bd5c-122">Who Should Implement the Weak Event Pattern?</span></span>  
 <span data-ttu-id="4bd5c-123">弱いイベントパターンの実装は、主にコントロールの作成者を対象としています。</span><span class="sxs-lookup"><span data-stu-id="4bd5c-123">Implementing the weak event pattern is interesting primarily for control authors.</span></span> <span data-ttu-id="4bd5c-124">コントロールの作成者は、コントロールの動作とコンテインメント、およびコントロールが挿入されるアプリケーションに与える影響について、ほとんどの責任を担います。</span><span class="sxs-lookup"><span data-stu-id="4bd5c-124">As a control author, you are largely responsible for the behavior and containment of your control and the impact it has on applications in which it is inserted.</span></span> <span data-ttu-id="4bd5c-125">これには、コントロールオブジェクトの有効期間の動作が含まれます。特に、説明されているメモリリークの問題を処理します。</span><span class="sxs-lookup"><span data-stu-id="4bd5c-125">This includes the control object lifetime behavior, in particular the handling of the described memory leak problem.</span></span>  
  
 <span data-ttu-id="4bd5c-126">特定のシナリオでは、弱いイベントパターンの適用が本質的に適しています。</span><span class="sxs-lookup"><span data-stu-id="4bd5c-126">Certain scenarios inherently lend themselves to the application of the weak event pattern.</span></span> <span data-ttu-id="4bd5c-127">このようなシナリオの1つに、データバインディングがあります。</span><span class="sxs-lookup"><span data-stu-id="4bd5c-127">One such scenario is data binding.</span></span> <span data-ttu-id="4bd5c-128">データバインディングでは、ソースオブジェクトがバインディングのターゲットであるリスナーオブジェクトと完全に独立していることが一般的です。</span><span class="sxs-lookup"><span data-stu-id="4bd5c-128">In data binding, it is common for the source object to be completely independent of the listener object, which is a target of a binding.</span></span> <span data-ttu-id="4bd5c-129">[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] データバインディングの多くの側面では、イベントの実装方法に弱いイベントパターンが既に適用されています。</span><span class="sxs-lookup"><span data-stu-id="4bd5c-129">Many aspects of [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] data binding already have the weak event pattern applied in how the events are implemented.</span></span>  
  
## <a name="how-to-implement-the-weak-event-pattern"></a><span data-ttu-id="4bd5c-130">弱いイベントパターンを実装する方法</span><span class="sxs-lookup"><span data-stu-id="4bd5c-130">How to Implement the Weak Event Pattern</span></span>  
 <span data-ttu-id="4bd5c-131">弱いイベントパターンを実装するには、3つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="4bd5c-131">There are three ways to implement weak event pattern.</span></span> <span data-ttu-id="4bd5c-132">次の表に、3つの方法を示し、それぞれを使用する必要がある場合のガイダンスを示します。</span><span class="sxs-lookup"><span data-stu-id="4bd5c-132">The following table lists the three approaches and provides some guidance for when you should use each.</span></span>  
  
|<span data-ttu-id="4bd5c-133">方法</span><span class="sxs-lookup"><span data-stu-id="4bd5c-133">Approach</span></span>|<span data-ttu-id="4bd5c-134">実装する場合</span><span class="sxs-lookup"><span data-stu-id="4bd5c-134">When to Implement</span></span>|  
|--------------|-----------------------|  
|<span data-ttu-id="4bd5c-135">既存の weak イベントマネージャークラスを使用する</span><span class="sxs-lookup"><span data-stu-id="4bd5c-135">Use an existing weak event manager class</span></span>|<span data-ttu-id="4bd5c-136">サブスクライブするイベントに対応する <xref:System.Windows.WeakEventManager>がある場合は、既存の弱いイベントマネージャーを使用します。</span><span class="sxs-lookup"><span data-stu-id="4bd5c-136">If the event you want to subscribe to has a corresponding <xref:System.Windows.WeakEventManager>, use the existing weak event manager.</span></span> <span data-ttu-id="4bd5c-137">WPF に含まれる弱いイベントマネージャーの一覧については、<xref:System.Windows.WeakEventManager> クラスの継承階層を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4bd5c-137">For a list of weak event managers that are included with WPF, see the inheritance hierarchy in the <xref:System.Windows.WeakEventManager> class.</span></span> <span data-ttu-id="4bd5c-138">含まれている弱いイベントマネージャーには制限があるため、他の方法のいずれかを選択する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="4bd5c-138">Because the included weak event managers are limited, you will probably need to choose one of the other approaches.</span></span>|  
|<span data-ttu-id="4bd5c-139">汎用の弱いイベントマネージャークラスを使用する</span><span class="sxs-lookup"><span data-stu-id="4bd5c-139">Use a generic weak event manager class</span></span>|<span data-ttu-id="4bd5c-140">既存の <xref:System.Windows.WeakEventManager> を使用できない場合は、汎用 <xref:System.Windows.WeakEventManager%602> を使用します。これにより簡単に実装できます。効率について心配する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="4bd5c-140">Use a generic <xref:System.Windows.WeakEventManager%602> when an existing <xref:System.Windows.WeakEventManager> is not available, you want an easy way to implement, and you are not concerned about efficiency.</span></span> <span data-ttu-id="4bd5c-141">汎用 <xref:System.Windows.WeakEventManager%602> は、既存またはカスタムの弱いイベントマネージャーよりも効率が悪くなります。</span><span class="sxs-lookup"><span data-stu-id="4bd5c-141">The generic <xref:System.Windows.WeakEventManager%602> is less efficient than an existing or custom weak event manager.</span></span> <span data-ttu-id="4bd5c-142">たとえば、ジェネリッククラスは、イベントの名前を指定してイベントを検出するために、より多くのリフレクションを行います。</span><span class="sxs-lookup"><span data-stu-id="4bd5c-142">For example, the generic class does more reflection to discover the event given the event's name.</span></span> <span data-ttu-id="4bd5c-143">また、ジェネリック <xref:System.Windows.WeakEventManager%602> を使用してイベントを登録するコードは、既存またはカスタムの <xref:System.Windows.WeakEventManager>を使用するよりも詳細です。</span><span class="sxs-lookup"><span data-stu-id="4bd5c-143">Also, the code to register the event by using the generic <xref:System.Windows.WeakEventManager%602> is more verbose than using an existing or custom <xref:System.Windows.WeakEventManager>.</span></span>|  
|<span data-ttu-id="4bd5c-144">カスタムの weak イベントマネージャークラスを作成する</span><span class="sxs-lookup"><span data-stu-id="4bd5c-144">Create a custom weak event manager class</span></span>|<span data-ttu-id="4bd5c-145">既存の <xref:System.Windows.WeakEventManager> を使用できず、効率を上げるために、カスタム <xref:System.Windows.WeakEventManager> を作成します。</span><span class="sxs-lookup"><span data-stu-id="4bd5c-145">Create a custom <xref:System.Windows.WeakEventManager> when an existing <xref:System.Windows.WeakEventManager> is not available and you want the best efficiency.</span></span> <span data-ttu-id="4bd5c-146">カスタム <xref:System.Windows.WeakEventManager> を使用してイベントをサブスクライブする方が効率的ですが、最初により多くのコードを記述するコストが発生します。</span><span class="sxs-lookup"><span data-stu-id="4bd5c-146">Using a custom <xref:System.Windows.WeakEventManager> to subscribe to an event will be more efficient, but you do incur the cost of writing more code at the beginning.</span></span>|  
|<span data-ttu-id="4bd5c-147">サードパーティの弱いイベントマネージャーを使用する</span><span class="sxs-lookup"><span data-stu-id="4bd5c-147">Use a third-party weak event manager</span></span>|<span data-ttu-id="4bd5c-148">NuGet には[いくつかの弱いイベントマネージャー](https://www.nuget.org/packages?q=weak+event+manager&prerel=false)があり、多くの WPF フレームワークでもパターンがサポートされています (例については、[疎結合イベントサブスクリプションに関する Prism のドキュメント](https://github.com/PrismLibrary/Prism-Documentation/blob/master/docs/wpf/legacy/Communication.md#subscribing-to-events)を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="4bd5c-148">NuGet has [several weak event managers](https://www.nuget.org/packages?q=weak+event+manager&prerel=false) and many WPF frameworks also support the pattern (for instance, see [Prism's documentation on loosely coupled event subscription](https://github.com/PrismLibrary/Prism-Documentation/blob/master/docs/wpf/legacy/Communication.md#subscribing-to-events)).</span></span>|

 <span data-ttu-id="4bd5c-149">以下のセクションでは、弱いイベントパターンを実装する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="4bd5c-149">The following sections describe how to implement the weak event pattern.</span></span>  <span data-ttu-id="4bd5c-150">この説明のために、サブスクライブするイベントには次の特性があります。</span><span class="sxs-lookup"><span data-stu-id="4bd5c-150">For purposes of this discussion, the event to subscribe to has the following characteristics.</span></span>  
  
- <span data-ttu-id="4bd5c-151">イベント名が `SomeEvent`。</span><span class="sxs-lookup"><span data-stu-id="4bd5c-151">The event name is `SomeEvent`.</span></span>  
  
- <span data-ttu-id="4bd5c-152">イベントは `EventSource` クラスによって発生します。</span><span class="sxs-lookup"><span data-stu-id="4bd5c-152">The event is raised by the `EventSource` class.</span></span>  
  
- <span data-ttu-id="4bd5c-153">イベントハンドラーには、`SomeEventEventHandler` (または `EventHandler<SomeEventEventArgs>`) の型があります。</span><span class="sxs-lookup"><span data-stu-id="4bd5c-153">The event handler has type: `SomeEventEventHandler` (or `EventHandler<SomeEventEventArgs>`).</span></span>  
  
- <span data-ttu-id="4bd5c-154">イベントは、`SomeEventEventArgs` 型のパラメーターをイベントハンドラーに渡します。</span><span class="sxs-lookup"><span data-stu-id="4bd5c-154">The event passes a parameter of type `SomeEventEventArgs` to the event handlers.</span></span>  
  
### <a name="using-an-existing-weak-event-manager-class"></a><span data-ttu-id="4bd5c-155">既存の Weak イベントマネージャークラスを使用する</span><span class="sxs-lookup"><span data-stu-id="4bd5c-155">Using an Existing Weak Event Manager Class</span></span>  
  
1. <span data-ttu-id="4bd5c-156">既存の弱いイベントマネージャーを検索します。</span><span class="sxs-lookup"><span data-stu-id="4bd5c-156">Find an existing weak event manager.</span></span>  
  
     <span data-ttu-id="4bd5c-157">WPF に含まれる弱いイベントマネージャーの一覧については、<xref:System.Windows.WeakEventManager> クラスの継承階層を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4bd5c-157">For a list of weak event managers that are included with WPF, see the inheritance hierarchy in the <xref:System.Windows.WeakEventManager> class.</span></span>  
  
2. <span data-ttu-id="4bd5c-158">通常のイベントフックアップではなく、新しい弱いイベントマネージャーを使用します。</span><span class="sxs-lookup"><span data-stu-id="4bd5c-158">Use the new weak event manager instead of the normal event hookup.</span></span>  
  
     <span data-ttu-id="4bd5c-159">たとえば、コードで次のパターンを使用してイベントをサブスクライブしているとします。</span><span class="sxs-lookup"><span data-stu-id="4bd5c-159">For example, if your code uses the following pattern to subscribe to an event:</span></span>  
  
    ```csharp  
    source.SomeEvent += new SomeEventEventHandler(OnSomeEvent);  
    ```  
  
     <span data-ttu-id="4bd5c-160">次のパターンに変更します。</span><span class="sxs-lookup"><span data-stu-id="4bd5c-160">Change it to the following pattern:</span></span>  
  
    ```csharp  
    SomeEventWeakEventManager.AddHandler(source, OnSomeEvent);  
    ```  
  
     <span data-ttu-id="4bd5c-161">同様に、コードで次のパターンを使用してイベントのサブスクリプションを解除します。</span><span class="sxs-lookup"><span data-stu-id="4bd5c-161">Similarly, if your code uses the following pattern to unsubscribe from an event:</span></span>  
  
    ```csharp  
    source.SomeEvent -= new SomeEventEventHandler(OnSomeEvent);  
    ```  
  
     <span data-ttu-id="4bd5c-162">次のパターンに変更します。</span><span class="sxs-lookup"><span data-stu-id="4bd5c-162">Change it to the following pattern:</span></span>  
  
    ```csharp  
    SomeEventWeakEventManager.RemoveHandler(source, OnSomeEvent);  
    ```  
  
### <a name="using-the-generic-weak-event-manager-class"></a><span data-ttu-id="4bd5c-163">汎用弱いイベントマネージャークラスの使用</span><span class="sxs-lookup"><span data-stu-id="4bd5c-163">Using the Generic Weak Event Manager Class</span></span>  
  
1. <span data-ttu-id="4bd5c-164">通常のイベントフックの代わりに、ジェネリック <xref:System.Windows.WeakEventManager%602> クラスを使用します。</span><span class="sxs-lookup"><span data-stu-id="4bd5c-164">Use the generic <xref:System.Windows.WeakEventManager%602> class instead of the normal event hookup.</span></span>  
  
     <span data-ttu-id="4bd5c-165"><xref:System.Windows.WeakEventManager%602> を使用してイベントリスナーを登録する場合は、イベントソースと <xref:System.EventArgs> 型をクラスの型パラメーターとして指定し、次のコードに示すように <xref:System.Windows.WeakEventManager%602.AddHandler%2A> を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="4bd5c-165">When you use <xref:System.Windows.WeakEventManager%602> to register event listeners, you supply the event source and <xref:System.EventArgs> type as the type parameters to the class and call <xref:System.Windows.WeakEventManager%602.AddHandler%2A> as shown in the following code:</span></span>  
  
    ```csharp  
    WeakEventManager<EventSource, SomeEventEventArgs>.AddHandler(source, "SomeEvent", source_SomeEvent);  
    ```  
  
### <a name="creating-a-custom-weak-event-manager-class"></a><span data-ttu-id="4bd5c-166">カスタムの弱いイベントマネージャークラスを作成する</span><span class="sxs-lookup"><span data-stu-id="4bd5c-166">Creating a Custom Weak Event Manager Class</span></span>  
  
1. <span data-ttu-id="4bd5c-167">次のクラステンプレートをプロジェクトにコピーします。</span><span class="sxs-lookup"><span data-stu-id="4bd5c-167">Copy the following class template to your project.</span></span>  
  
     <span data-ttu-id="4bd5c-168">このクラスは、<xref:System.Windows.WeakEventManager> クラスから継承されます。</span><span class="sxs-lookup"><span data-stu-id="4bd5c-168">This class inherits from the <xref:System.Windows.WeakEventManager> class.</span></span>  
  
     [!code-csharp[WeakEvents#WeakEventManagerTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/WeakEvents/CSharp/WeakEventManagerTemplate.cs#weakeventmanagertemplate)]  
  
2. <span data-ttu-id="4bd5c-169">`SomeEventWeakEventManager` 名を実際の名前に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="4bd5c-169">Replace the `SomeEventWeakEventManager` name with your own name.</span></span>  
  
3. <span data-ttu-id="4bd5c-170">前に説明した3つの名前を、対応するイベントの名前に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="4bd5c-170">Replace the three names described previously with the corresponding names for your event.</span></span> <span data-ttu-id="4bd5c-171">(`SomeEvent`、`EventSource`、および `SomeEventEventArgs`)</span><span class="sxs-lookup"><span data-stu-id="4bd5c-171">(`SomeEvent`, `EventSource`, and `SomeEventEventArgs`)</span></span>  
  
4. <span data-ttu-id="4bd5c-172">弱いイベントマネージャークラスの可視性 (公開/内部/プライベート) を、それが管理するイベントと同じ可視性に設定します。</span><span class="sxs-lookup"><span data-stu-id="4bd5c-172">Set the visibility (public / internal / private) of the weak event manager class to the same visibility as event it manages.</span></span>  
  
5. <span data-ttu-id="4bd5c-173">通常のイベントフックアップではなく、新しい弱いイベントマネージャーを使用します。</span><span class="sxs-lookup"><span data-stu-id="4bd5c-173">Use the new weak event manager instead of the normal event hookup.</span></span>  
  
     <span data-ttu-id="4bd5c-174">たとえば、コードで次のパターンを使用してイベントをサブスクライブしているとします。</span><span class="sxs-lookup"><span data-stu-id="4bd5c-174">For example, if your code uses the following pattern to subscribe to an event:</span></span>  
  
    ```csharp  
    source.SomeEvent += new SomeEventEventHandler(OnSomeEvent);  
    ```  
  
     <span data-ttu-id="4bd5c-175">次のパターンに変更します。</span><span class="sxs-lookup"><span data-stu-id="4bd5c-175">Change it to the following pattern:</span></span>  
  
    ```csharp  
    SomeEventWeakEventManager.AddHandler(source, OnSomeEvent);  
    ```  
  
     <span data-ttu-id="4bd5c-176">同様に、コードで次のパターンを使用してイベントのサブスクリプションを解除します。</span><span class="sxs-lookup"><span data-stu-id="4bd5c-176">Similarly, if your code uses the following pattern to unsubscribe to an event:</span></span>  
  
    ```csharp  
    source.SomeEvent -= new SomeEventEventHandler(OnSome);  
    ```  
  
     <span data-ttu-id="4bd5c-177">次のパターンに変更します。</span><span class="sxs-lookup"><span data-stu-id="4bd5c-177">Change it to the following pattern:</span></span>  
  
    ```csharp  
    SomeEventWeakEventManager.RemoveHandler(source, OnSomeEvent);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="4bd5c-178">関連項目</span><span class="sxs-lookup"><span data-stu-id="4bd5c-178">See also</span></span>

- <xref:System.Windows.WeakEventManager>
- <xref:System.Windows.IWeakEventListener>
- [<span data-ttu-id="4bd5c-179">ルーティング イベントの概要</span><span class="sxs-lookup"><span data-stu-id="4bd5c-179">Routed Events Overview</span></span>](routed-events-overview.md)
- [<span data-ttu-id="4bd5c-180">データ バインディングの概要</span><span class="sxs-lookup"><span data-stu-id="4bd5c-180">Data Binding Overview</span></span>](../../../desktop-wpf/data/data-binding-overview.md)
