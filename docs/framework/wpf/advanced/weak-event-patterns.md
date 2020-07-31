---
title: 弱いイベント パターン
description: Windows Presentation Foundation の弱いイベント パターンについて説明します。破棄されていないハンドラーの問題に対処して、メモリ リークを回避します。
ms.date: 03/30/2017
helpviewer_keywords:
- weak event pattern implementation [WPF]
- event handlers [WPF], weak event pattern
- IWeakEventListener interface [WPF]
ms.assetid: e7c62920-4812-4811-94d8-050a65c856f6
ms.openlocfilehash: 75c6888c8ac20c41d13e3787005377c75248c5d9
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2020
ms.locfileid: "87168266"
---
# <a name="weak-event-patterns"></a><span data-ttu-id="ebbe6-103">弱いイベント パターン</span><span class="sxs-lookup"><span data-stu-id="ebbe6-103">Weak Event Patterns</span></span>
<span data-ttu-id="ebbe6-104">アプリケーションでは、イベント ソースにアタッチされているハンドラーが、ハンドラーをソースにアタッチしたリスナー オブジェクトと連携して破棄されない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ebbe6-104">In applications, it is possible that handlers that are attached to event sources will not be destroyed in coordination with the listener object that attached the handler to the source.</span></span> <span data-ttu-id="ebbe6-105">このような状況では、メモリ リークが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ebbe6-105">This situation can lead to memory leaks.</span></span> [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] <span data-ttu-id="ebbe6-106">では、この問題の解決に使用できる設計パターンを導入しており、特定のイベントには専用のマネージャー クラスを用意し、そのイベントのリスナーにインターフェイスを実装しています。</span><span class="sxs-lookup"><span data-stu-id="ebbe6-106">introduces a design pattern that can be used to address this issue, by providing a dedicated manager class for particular events and implementing an interface on listeners for that event.</span></span> <span data-ttu-id="ebbe6-107">この設計パターンは、"*弱いイベント パターン*" 呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="ebbe6-107">This design pattern is known as the *weak event pattern*.</span></span>  
  
## <a name="why-implement-the-weak-event-pattern"></a><span data-ttu-id="ebbe6-108">弱いイベント パターンを実装するのはなぜですか</span><span class="sxs-lookup"><span data-stu-id="ebbe6-108">Why Implement the Weak Event Pattern?</span></span>  
 <span data-ttu-id="ebbe6-109">イベントをリッスンすると、メモリ リークが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ebbe6-109">Listening for events can lead to memory leaks.</span></span> <span data-ttu-id="ebbe6-110">イベントをリッスンする一般的な手法は、ソース上のイベントにハンドラーをアタッチする言語固有の構文を使用することです。</span><span class="sxs-lookup"><span data-stu-id="ebbe6-110">The typical technique for listening to an event is to use the language-specific syntax that attaches a handler to an event on a source.</span></span> <span data-ttu-id="ebbe6-111">たとえば、C# の場合、その構文は `source.SomeEvent += new SomeEventHandler(MyEventHandler)` です。</span><span class="sxs-lookup"><span data-stu-id="ebbe6-111">For example, in C#, that syntax is: `source.SomeEvent += new SomeEventHandler(MyEventHandler)`.</span></span>  
  
 <span data-ttu-id="ebbe6-112">この手法では、イベント ソースからイベント リスナーへの強い参照が作成されます。</span><span class="sxs-lookup"><span data-stu-id="ebbe6-112">This technique creates a strong reference from the event source to the event listener.</span></span> <span data-ttu-id="ebbe6-113">通常、リスナーのイベント ハンドラーをアタッチすると、リスナーのオブジェクトの有効期間はソースのオブジェクトの有効期間の影響を受けます (イベント ハンドラーが明示的に削除されていない場合)。</span><span class="sxs-lookup"><span data-stu-id="ebbe6-113">Ordinarily, attaching an event handler for a listener causes the listener to have an object lifetime that is influenced by the object lifetime of the source (unless the event handler is explicitly removed).</span></span> <span data-ttu-id="ebbe6-114">ただし、状況によっては、ソースの有効期間ではなく、他の要因でリスナーのオブジェクトの有効期間が制御される場合があります。たとえば、アプリケーションのビジュアル ツリーに現在属しているかどうかなどです。</span><span class="sxs-lookup"><span data-stu-id="ebbe6-114">But in certain circumstances, you might want the object lifetime of the listener to be controlled by other factors, such as whether it currently belongs to the visual tree of the application, and not by the lifetime of the source.</span></span> <span data-ttu-id="ebbe6-115">ソース オブジェクトの有効期間がリスナーのオブジェクトの有効期間を超えている場合は常に、通常のイベント パターンでメモリ リークが発生します。つまり、リスナーは意図したよりも長く存続します。</span><span class="sxs-lookup"><span data-stu-id="ebbe6-115">Whenever the source object lifetime extends beyond the object lifetime of the listener, the normal event pattern leads to a memory leak: the listener is kept alive longer than intended.</span></span>  
  
 <span data-ttu-id="ebbe6-116">弱いイベント パターンは、このメモリ リークの問題を解決するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="ebbe6-116">The weak event pattern is designed to solve this memory leak problem.</span></span> <span data-ttu-id="ebbe6-117">リスナーをイベントに登録する必要がある場合は常に弱いイベント パターンを使用できますが、リスナー側では登録を解除する正確なタイミングを認識できません。</span><span class="sxs-lookup"><span data-stu-id="ebbe6-117">The weak event pattern can be used whenever a listener needs to register for an event, but the listener does not explicitly know when to unregister.</span></span> <span data-ttu-id="ebbe6-118">ソースのオブジェクトの有効期間がリスナーの有効なオブジェクトの有効期間を超える場合にも、弱いイベント パターンを使用できます</span><span class="sxs-lookup"><span data-stu-id="ebbe6-118">The weak event pattern can also be used whenever the object lifetime of the source exceeds the useful object lifetime of the listener.</span></span> <span data-ttu-id="ebbe6-119">(この場合、"*役に立つ*" かどうかは使う側の判断次第です)。弱いイベント パターンを使用すると、リスナーでは、リスナーのオブジェクトの有効期間特性に影響を与えることなく、イベントの登録と受信を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="ebbe6-119">(In this case, *useful* is determined by you.) The weak event pattern allows the listener to register for and receive the event without affecting the object lifetime characteristics of the listener in any way.</span></span> <span data-ttu-id="ebbe6-120">実際には、ソースからの暗黙の参照によって、リスナーがガベージ コレクションの対象かどうかが判断されることはありません。</span><span class="sxs-lookup"><span data-stu-id="ebbe6-120">In effect, the implied reference from the source does not determine whether the listener is eligible for garbage collection.</span></span> <span data-ttu-id="ebbe6-121">この参照は弱い参照であるため、弱いイベント パターンと関連する API の名前が付けられます。</span><span class="sxs-lookup"><span data-stu-id="ebbe6-121">The reference is a weak reference, thus the naming of the weak event pattern and the related APIs.</span></span> <span data-ttu-id="ebbe6-122">ガベージ コレクションまたはその他の方法でリスナーを破棄することができます。また、破棄されたオブジェクトに対する収集不可能なハンドラー参照を保持することなく、ソースを継続できます。</span><span class="sxs-lookup"><span data-stu-id="ebbe6-122">The listener can be garbage collected or otherwise destroyed, and the source can continue without retaining noncollectible handler references to a now destroyed object.</span></span>  
  
## <a name="who-should-implement-the-weak-event-pattern"></a><span data-ttu-id="ebbe6-123">弱いイベント パターンを実装する必要があるのはだれですか</span><span class="sxs-lookup"><span data-stu-id="ebbe6-123">Who Should Implement the Weak Event Pattern?</span></span>  
 <span data-ttu-id="ebbe6-124">弱いイベント パターンの実装に関心を持つのは、主にコントロールの作成者です。</span><span class="sxs-lookup"><span data-stu-id="ebbe6-124">Implementing the weak event pattern is interesting primarily for control authors.</span></span> <span data-ttu-id="ebbe6-125">コントロールの作成者は、コントロールの動作とコンテインメイトと、それが挿入されているアプリケーションに与える影響について主に責任を担っています。</span><span class="sxs-lookup"><span data-stu-id="ebbe6-125">As a control author, you are largely responsible for the behavior and containment of your control and the impact it has on applications in which it is inserted.</span></span> <span data-ttu-id="ebbe6-126">これには、コントロール オブジェクトの有効期間動作、特にここで説明しているメモリ リークの問題の処理が含まれます。</span><span class="sxs-lookup"><span data-stu-id="ebbe6-126">This includes the control object lifetime behavior, in particular the handling of the described memory leak problem.</span></span>  
  
 <span data-ttu-id="ebbe6-127">弱いイベント パターンの適用に本質的に適しているシナリオがあります。</span><span class="sxs-lookup"><span data-stu-id="ebbe6-127">Certain scenarios inherently lend themselves to the application of the weak event pattern.</span></span> <span data-ttu-id="ebbe6-128">このようなシナリオの 1 つにデータ バインディングがあります。</span><span class="sxs-lookup"><span data-stu-id="ebbe6-128">One such scenario is data binding.</span></span> <span data-ttu-id="ebbe6-129">データ バインディングでは、ソース オブジェクトが、バインディングのターゲットであるリスナー オブジェクトから完全に独立しているのが一般的です。</span><span class="sxs-lookup"><span data-stu-id="ebbe6-129">In data binding, it is common for the source object to be completely independent of the listener object, which is a target of a binding.</span></span> <span data-ttu-id="ebbe6-130">[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] データ バインディングの多くの側面には、イベントの実装方法に弱いイベント パターンが既に適用されています。</span><span class="sxs-lookup"><span data-stu-id="ebbe6-130">Many aspects of [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] data binding already have the weak event pattern applied in how the events are implemented.</span></span>  
  
## <a name="how-to-implement-the-weak-event-pattern"></a><span data-ttu-id="ebbe6-131">弱いイベント パターンを実装する方法</span><span class="sxs-lookup"><span data-stu-id="ebbe6-131">How to Implement the Weak Event Pattern</span></span>  
 <span data-ttu-id="ebbe6-132">弱いイベント パターンを実装するには、3 つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="ebbe6-132">There are three ways to implement weak event pattern.</span></span> <span data-ttu-id="ebbe6-133">その 3 つの方法と、それぞれを使用すべき場合についてのガイダンスを次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="ebbe6-133">The following table lists the three approaches and provides some guidance for when you should use each.</span></span>  
  
|<span data-ttu-id="ebbe6-134">方法</span><span class="sxs-lookup"><span data-stu-id="ebbe6-134">Approach</span></span>|<span data-ttu-id="ebbe6-135">実装する場合</span><span class="sxs-lookup"><span data-stu-id="ebbe6-135">When to Implement</span></span>|  
|--------------|-----------------------|  
|<span data-ttu-id="ebbe6-136">既存の弱いイベント マネージャー クラスを使用する</span><span class="sxs-lookup"><span data-stu-id="ebbe6-136">Use an existing weak event manager class</span></span>|<span data-ttu-id="ebbe6-137">サブスクライブするイベントに対応する <xref:System.Windows.WeakEventManager> がある場合は、既存の弱いイベント マネージャーを使用します。</span><span class="sxs-lookup"><span data-stu-id="ebbe6-137">If the event you want to subscribe to has a corresponding <xref:System.Windows.WeakEventManager>, use the existing weak event manager.</span></span> <span data-ttu-id="ebbe6-138">WPF に含まれている弱いイベント マネージャーの一覧については、<xref:System.Windows.WeakEventManager> クラスの継承階層を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ebbe6-138">For a list of weak event managers that are included with WPF, see the inheritance hierarchy in the <xref:System.Windows.WeakEventManager> class.</span></span> <span data-ttu-id="ebbe6-139">含まれている弱いイベント マネージャーは限られているため、おそらく他の方法のいずれかを選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ebbe6-139">Because the included weak event managers are limited, you will probably need to choose one of the other approaches.</span></span>|  
|<span data-ttu-id="ebbe6-140">ジェネリックの弱いイベント マネージャー クラスを使用する</span><span class="sxs-lookup"><span data-stu-id="ebbe6-140">Use a generic weak event manager class</span></span>|<span data-ttu-id="ebbe6-141">既存の <xref:System.Windows.WeakEventManager> を使用できず、簡単な実装方法が必要で、効率については気にしない場合は、ジェネリック <xref:System.Windows.WeakEventManager%602> を使用します。</span><span class="sxs-lookup"><span data-stu-id="ebbe6-141">Use a generic <xref:System.Windows.WeakEventManager%602> when an existing <xref:System.Windows.WeakEventManager> is not available, you want an easy way to implement, and you are not concerned about efficiency.</span></span> <span data-ttu-id="ebbe6-142">ジェネリック <xref:System.Windows.WeakEventManager%602> は、既存またはカスタムの弱いイベント マネージャーよりも非効率的です。</span><span class="sxs-lookup"><span data-stu-id="ebbe6-142">The generic <xref:System.Windows.WeakEventManager%602> is less efficient than an existing or custom weak event manager.</span></span> <span data-ttu-id="ebbe6-143">たとえば、ジェネリック クラスでは、イベントの名前を指定してイベントを検出するために、より多くのリフレクションを行います。</span><span class="sxs-lookup"><span data-stu-id="ebbe6-143">For example, the generic class does more reflection to discover the event given the event's name.</span></span> <span data-ttu-id="ebbe6-144">また、ジェネリック <xref:System.Windows.WeakEventManager%602> を使用してイベントを登録するコードは、既存またはカスタムの <xref:System.Windows.WeakEventManager> を使用するよりも詳細です。</span><span class="sxs-lookup"><span data-stu-id="ebbe6-144">Also, the code to register the event by using the generic <xref:System.Windows.WeakEventManager%602> is more verbose than using an existing or custom <xref:System.Windows.WeakEventManager>.</span></span>|  
|<span data-ttu-id="ebbe6-145">カスタムの弱いイベント マネージャー クラスを作成する</span><span class="sxs-lookup"><span data-stu-id="ebbe6-145">Create a custom weak event manager class</span></span>|<span data-ttu-id="ebbe6-146">既存の <xref:System.Windows.WeakEventManager> を使用できず、最高の効率が必要な場合は、カスタムの <xref:System.Windows.WeakEventManager> を作成します。</span><span class="sxs-lookup"><span data-stu-id="ebbe6-146">Create a custom <xref:System.Windows.WeakEventManager> when an existing <xref:System.Windows.WeakEventManager> is not available and you want the best efficiency.</span></span> <span data-ttu-id="ebbe6-147">カスタムの <xref:System.Windows.WeakEventManager> を使用してイベントをサブスクライブする方が効率的ですが、最初からコードを作成するコストが発生します。</span><span class="sxs-lookup"><span data-stu-id="ebbe6-147">Using a custom <xref:System.Windows.WeakEventManager> to subscribe to an event will be more efficient, but you do incur the cost of writing more code at the beginning.</span></span>|  
|<span data-ttu-id="ebbe6-148">サードパーティの弱いイベント マネージャーを使用する</span><span class="sxs-lookup"><span data-stu-id="ebbe6-148">Use a third-party weak event manager</span></span>|<span data-ttu-id="ebbe6-149">NuGet には[複数の弱いイベント マネージャー](https://www.nuget.org/packages?q=weak+event+manager&prerel=false)があり、多くの WPF フレームワークもそのパターンをサポートしています (たとえば、[疎結合イベント サブスクリプションに関する Prism のドキュメント](https://github.com/PrismLibrary/Prism-Documentation/blob/master/docs/wpf/legacy/Communication.md#subscribing-to-events)を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="ebbe6-149">NuGet has [several weak event managers](https://www.nuget.org/packages?q=weak+event+manager&prerel=false) and many WPF frameworks also support the pattern (for instance, see [Prism's documentation on loosely coupled event subscription](https://github.com/PrismLibrary/Prism-Documentation/blob/master/docs/wpf/legacy/Communication.md#subscribing-to-events)).</span></span>|

 <span data-ttu-id="ebbe6-150">以下のセクションでは、弱いイベント パターンを実装する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="ebbe6-150">The following sections describe how to implement the weak event pattern.</span></span>  <span data-ttu-id="ebbe6-151">この説明のために、サブスクライブするイベントには次の特性があります。</span><span class="sxs-lookup"><span data-stu-id="ebbe6-151">For purposes of this discussion, the event to subscribe to has the following characteristics.</span></span>  
  
- <span data-ttu-id="ebbe6-152">イベント名は `SomeEvent` です。</span><span class="sxs-lookup"><span data-stu-id="ebbe6-152">The event name is `SomeEvent`.</span></span>  
  
- <span data-ttu-id="ebbe6-153">イベントは `EventSource` クラスによって発生します。</span><span class="sxs-lookup"><span data-stu-id="ebbe6-153">The event is raised by the `EventSource` class.</span></span>  
  
- <span data-ttu-id="ebbe6-154">イベント ハンドラーの型は `SomeEventEventHandler` (または `EventHandler<SomeEventEventArgs>`) です。</span><span class="sxs-lookup"><span data-stu-id="ebbe6-154">The event handler has type: `SomeEventEventHandler` (or `EventHandler<SomeEventEventArgs>`).</span></span>  
  
- <span data-ttu-id="ebbe6-155">イベントからイベント ハンドラーに型 `SomeEventEventArgs` のパラメーターが渡されます。</span><span class="sxs-lookup"><span data-stu-id="ebbe6-155">The event passes a parameter of type `SomeEventEventArgs` to the event handlers.</span></span>  
  
### <a name="using-an-existing-weak-event-manager-class"></a><span data-ttu-id="ebbe6-156">既存の弱いイベント マネージャー クラスの使用</span><span class="sxs-lookup"><span data-stu-id="ebbe6-156">Using an Existing Weak Event Manager Class</span></span>  
  
1. <span data-ttu-id="ebbe6-157">既存の弱いイベント マネージャーを見つけます。</span><span class="sxs-lookup"><span data-stu-id="ebbe6-157">Find an existing weak event manager.</span></span>  
  
     <span data-ttu-id="ebbe6-158">WPF に含まれている弱いイベント マネージャーの一覧については、<xref:System.Windows.WeakEventManager> クラスの継承階層を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ebbe6-158">For a list of weak event managers that are included with WPF, see the inheritance hierarchy in the <xref:System.Windows.WeakEventManager> class.</span></span>  
  
2. <span data-ttu-id="ebbe6-159">通常のイベント フックアップではなく、新しい弱いイベント マネージャーを使用します。</span><span class="sxs-lookup"><span data-stu-id="ebbe6-159">Use the new weak event manager instead of the normal event hookup.</span></span>  
  
     <span data-ttu-id="ebbe6-160">たとえば、コードで次のパターンを使用してイベントをサブスクライブするとします。</span><span class="sxs-lookup"><span data-stu-id="ebbe6-160">For example, if your code uses the following pattern to subscribe to an event:</span></span>  
  
    ```csharp  
    source.SomeEvent += new SomeEventEventHandler(OnSomeEvent);  
    ```  
  
     <span data-ttu-id="ebbe6-161">次のパターンに変更します。</span><span class="sxs-lookup"><span data-stu-id="ebbe6-161">Change it to the following pattern:</span></span>  
  
    ```csharp  
    SomeEventWeakEventManager.AddHandler(source, OnSomeEvent);  
    ```  
  
     <span data-ttu-id="ebbe6-162">同様に、コードで次のパターンを使用してイベントのサブスクライブを解除するとします。</span><span class="sxs-lookup"><span data-stu-id="ebbe6-162">Similarly, if your code uses the following pattern to unsubscribe from an event:</span></span>  
  
    ```csharp  
    source.SomeEvent -= new SomeEventEventHandler(OnSomeEvent);  
    ```  
  
     <span data-ttu-id="ebbe6-163">次のパターンに変更します。</span><span class="sxs-lookup"><span data-stu-id="ebbe6-163">Change it to the following pattern:</span></span>  
  
    ```csharp  
    SomeEventWeakEventManager.RemoveHandler(source, OnSomeEvent);  
    ```  
  
### <a name="using-the-generic-weak-event-manager-class"></a><span data-ttu-id="ebbe6-164">ジェネリックの弱いイベント マネージャー クラスの使用</span><span class="sxs-lookup"><span data-stu-id="ebbe6-164">Using the Generic Weak Event Manager Class</span></span>  
  
1. <span data-ttu-id="ebbe6-165">通常のイベント フックアップではなく、ジェネリック <xref:System.Windows.WeakEventManager%602> クラスを使用します。</span><span class="sxs-lookup"><span data-stu-id="ebbe6-165">Use the generic <xref:System.Windows.WeakEventManager%602> class instead of the normal event hookup.</span></span>  
  
     <span data-ttu-id="ebbe6-166"><xref:System.Windows.WeakEventManager%602> を使用してイベント リスナーを登録する場合、次のコードに示すように、イベント ソースと <xref:System.EventArgs> 型を型パラメーターとしてクラスに指定し、<xref:System.Windows.WeakEventManager%602.AddHandler%2A> を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="ebbe6-166">When you use <xref:System.Windows.WeakEventManager%602> to register event listeners, you supply the event source and <xref:System.EventArgs> type as the type parameters to the class and call <xref:System.Windows.WeakEventManager%602.AddHandler%2A> as shown in the following code:</span></span>  
  
    ```csharp  
    WeakEventManager<EventSource, SomeEventEventArgs>.AddHandler(source, "SomeEvent", source_SomeEvent);  
    ```  
  
### <a name="creating-a-custom-weak-event-manager-class"></a><span data-ttu-id="ebbe6-167">カスタムの弱いイベント マネージャー クラスの作成</span><span class="sxs-lookup"><span data-stu-id="ebbe6-167">Creating a Custom Weak Event Manager Class</span></span>  
  
1. <span data-ttu-id="ebbe6-168">次のクラス テンプレートをプロジェクトにコピーします。</span><span class="sxs-lookup"><span data-stu-id="ebbe6-168">Copy the following class template to your project.</span></span>  
  
     <span data-ttu-id="ebbe6-169">このクラスは、<xref:System.Windows.WeakEventManager> クラスから継承されます。</span><span class="sxs-lookup"><span data-stu-id="ebbe6-169">This class inherits from the <xref:System.Windows.WeakEventManager> class.</span></span>  
  
     [!code-csharp[WeakEvents#WeakEventManagerTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/WeakEvents/CSharp/WeakEventManagerTemplate.cs#weakeventmanagertemplate)]  
  
2. <span data-ttu-id="ebbe6-170">`SomeEventWeakEventManager` の名前を実際の名前に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="ebbe6-170">Replace the `SomeEventWeakEventManager` name with your own name.</span></span>  
  
3. <span data-ttu-id="ebbe6-171">前述の 3 つの名前を、実際のイベントの対応する名前に置き換えます</span><span class="sxs-lookup"><span data-stu-id="ebbe6-171">Replace the three names described previously with the corresponding names for your event.</span></span> <span data-ttu-id="ebbe6-172">(`SomeEvent`、`EventSource`、および `SomeEventEventArgs`)。</span><span class="sxs-lookup"><span data-stu-id="ebbe6-172">(`SomeEvent`, `EventSource`, and `SomeEventEventArgs`)</span></span>  
  
4. <span data-ttu-id="ebbe6-173">弱いイベント マネージャー クラスの可視性 (public、internal、private) を、管理対象のイベントと同じ可視性に設定します。</span><span class="sxs-lookup"><span data-stu-id="ebbe6-173">Set the visibility (public / internal / private) of the weak event manager class to the same visibility as event it manages.</span></span>  
  
5. <span data-ttu-id="ebbe6-174">通常のイベント フックアップではなく、新しい弱いイベント マネージャーを使用します。</span><span class="sxs-lookup"><span data-stu-id="ebbe6-174">Use the new weak event manager instead of the normal event hookup.</span></span>  
  
     <span data-ttu-id="ebbe6-175">たとえば、コードで次のパターンを使用してイベントをサブスクライブするとします。</span><span class="sxs-lookup"><span data-stu-id="ebbe6-175">For example, if your code uses the following pattern to subscribe to an event:</span></span>  
  
    ```csharp  
    source.SomeEvent += new SomeEventEventHandler(OnSomeEvent);  
    ```  
  
     <span data-ttu-id="ebbe6-176">次のパターンに変更します。</span><span class="sxs-lookup"><span data-stu-id="ebbe6-176">Change it to the following pattern:</span></span>  
  
    ```csharp  
    SomeEventWeakEventManager.AddHandler(source, OnSomeEvent);  
    ```  
  
     <span data-ttu-id="ebbe6-177">同様に、コードで次のパターンを使用してイベントのサブスクライブを解除するとします。</span><span class="sxs-lookup"><span data-stu-id="ebbe6-177">Similarly, if your code uses the following pattern to unsubscribe to an event:</span></span>  
  
    ```csharp  
    source.SomeEvent -= new SomeEventEventHandler(OnSome);  
    ```  
  
     <span data-ttu-id="ebbe6-178">次のパターンに変更します。</span><span class="sxs-lookup"><span data-stu-id="ebbe6-178">Change it to the following pattern:</span></span>  
  
    ```csharp  
    SomeEventWeakEventManager.RemoveHandler(source, OnSomeEvent);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="ebbe6-179">関連項目</span><span class="sxs-lookup"><span data-stu-id="ebbe6-179">See also</span></span>

- <xref:System.Windows.WeakEventManager>
- <xref:System.Windows.IWeakEventListener>
- [<span data-ttu-id="ebbe6-180">ルーティング イベントの概要</span><span class="sxs-lookup"><span data-stu-id="ebbe6-180">Routed Events Overview</span></span>](routed-events-overview.md)
- [<span data-ttu-id="ebbe6-181">データ バインディングの概要</span><span class="sxs-lookup"><span data-stu-id="ebbe6-181">Data Binding Overview</span></span>](../../../desktop-wpf/data/data-binding-overview.md)
