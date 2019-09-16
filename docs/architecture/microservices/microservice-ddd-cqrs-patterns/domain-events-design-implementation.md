---
title: 'ドメイン イベント: 設計と実装'
description: コンテナー化された .NET アプリケーションの .NET マイクロサービス アーキテクチャ | 集約間の通信を確立するための重要な概念であるドメイン イベントの詳細を表示する。
ms.date: 10/08/2018
ms.openlocfilehash: 46341bbc3ee3e5713707cc6a18b678d51102b64d
ms.sourcegitcommit: 33c8d6f7342a4bb2c577842b7f075b0e20a2fa40
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2019
ms.locfileid: "70926556"
---
# <a name="domain-events-design-and-implementation"></a><span data-ttu-id="dd983-104">ドメイン イベント: 設計と実装</span><span class="sxs-lookup"><span data-stu-id="dd983-104">Domain events: design and implementation</span></span>

<span data-ttu-id="dd983-105">ドメイン内での変更の副作用を明示的に実装するには、ドメイン イベントを使います。</span><span class="sxs-lookup"><span data-stu-id="dd983-105">Use domain events to explicitly implement side effects of changes within your domain.</span></span> <span data-ttu-id="dd983-106">DDD の用語を使って言い換えるなら、複数の集約に副作用を明示的に実装するには、ドメイン イベントを使います。</span><span class="sxs-lookup"><span data-stu-id="dd983-106">In other words, and using DDD terminology, use domain events to explicitly implement side effects across multiple aggregates.</span></span> <span data-ttu-id="dd983-107">また、スケーラビリティを向上させ、データベース ロックの影響を小さくする必要がある場合は、同じドメイン内の集約の間の最終的な整合性を使います。</span><span class="sxs-lookup"><span data-stu-id="dd983-107">Optionally, for better scalability and less impact in database locks, use eventual consistency between aggregates within the same domain.</span></span>

## <a name="what-is-a-domain-event"></a><span data-ttu-id="dd983-108">ドメイン イベントとは</span><span class="sxs-lookup"><span data-stu-id="dd983-108">What is a domain event?</span></span>

<span data-ttu-id="dd983-109">イベントとは、過去に発生した出来事です。</span><span class="sxs-lookup"><span data-stu-id="dd983-109">An event is something that has happened in the past.</span></span> <span data-ttu-id="dd983-110">ドメイン イベントはドメインで発生する出来事であり、それを同じドメイン (インプロセス) の他の部分に認識させます。</span><span class="sxs-lookup"><span data-stu-id="dd983-110">A domain event is, something that happened in the domain that you want other parts of the same domain (in-process) to be aware of.</span></span> <span data-ttu-id="dd983-111">他の部分は通知を受けると、通常、イベントに何らかの方法で対処します。</span><span class="sxs-lookup"><span data-stu-id="dd983-111">The notified parts usually react somehow to the events.</span></span>

<span data-ttu-id="dd983-112">ドメイン イベントの重要な利点は、副作用を明示的に表現できることです。</span><span class="sxs-lookup"><span data-stu-id="dd983-112">An important benefit of domain events is that side effects can be expressed explicitly.</span></span>

<span data-ttu-id="dd983-113">たとえば、Entity Framework を使用しているとき、大きな出来事に対して反応が必要であれば、おそらくそのイベントの引き金となるものの近くに必要なコードを記述することになります。</span><span class="sxs-lookup"><span data-stu-id="dd983-113">For example, if you're just using Entity Framework and there has to be a reaction to some event, you would probably code whatever you need close to what triggers the event.</span></span> <span data-ttu-id="dd983-114">そのため、そのコードに暗黙的にルールが連結されます。コードを調べ、ルールがそこに実装されていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dd983-114">So the rule gets coupled, implicitly, to the code, and you have to look into the code to, hopefully, realize the rule is implemented there.</span></span>

<span data-ttu-id="dd983-115">一方で、ドメイン イベントを使用すると、この概念が明示的になります。これは `DomainEvent` が存在するためであり、また、`DomainEventHandler` が少なくとも 1 つ関与するためです。</span><span class="sxs-lookup"><span data-stu-id="dd983-115">On the other hand, using domain events makes the concept explicit, because there is a `DomainEvent` and at least one `DomainEventHandler` involved.</span></span>

<span data-ttu-id="dd983-116">たとえば、eShopOnContainers アプリケーションで注文が作成されると、利用者は購入者になります。そのため、`OrderStartedDomainEvent` が発生し、`ValidateOrAddBuyerAggregateWhenOrderStartedDomainEventHandler` で処理されます。つまり、基礎をなす概念は明らかです。</span><span class="sxs-lookup"><span data-stu-id="dd983-116">For example, in the eShopOnContainers application, when an order is created, the user becomes a buyer, so an `OrderStartedDomainEvent` is raised and handled in the `ValidateOrAddBuyerAggregateWhenOrderStartedDomainEventHandler`, so the underlying concept is evident.</span></span>

<span data-ttu-id="dd983-117">手短に言えば、ドメインの専門家から与えられるユビキタス言語に基づいて、ドメイン ルールを明示的に表現する際にドメイン イベントが役立ちます。</span><span class="sxs-lookup"><span data-stu-id="dd983-117">In short, domain events help you to express, explicitly, the domain rules, based in the ubiquitous language provided by the domain experts.</span></span> <span data-ttu-id="dd983-118">また、ドメイン イベントを使用することにより、同じドメイン内のクラス間で問題をよりはっきりと分離できます。</span><span class="sxs-lookup"><span data-stu-id="dd983-118">Domain events also enable a better separation of concerns among classes within the same domain.</span></span>

<span data-ttu-id="dd983-119">データベース トランザクションと同様に、ドメイン イベントに関連付けられているすべての操作が正常に完了するか、1 つも完了しないようにすることが重要です。</span><span class="sxs-lookup"><span data-stu-id="dd983-119">It's important to ensure that, just like a database transaction, either all the operations related to a domain event finish successfully or none of them do.</span></span>

<span data-ttu-id="dd983-120">ドメイン イベントはメッセージング スタイルのイベントに似ていますが、重要な相違点が 1 つあります。</span><span class="sxs-lookup"><span data-stu-id="dd983-120">Domain events are similar to messaging-style events, with one important difference.</span></span> <span data-ttu-id="dd983-121">実際のメッセージング、メッセージ キュー、メッセージ ブローカー、または AMQP を使うサービス バスでは、メッセージは常に非同期に送信され、プロセスとマシンの間で通信されます。</span><span class="sxs-lookup"><span data-stu-id="dd983-121">With real messaging, message queuing, message brokers, or a service bus using AMQP, a message is always sent asynchronously and communicated across processes and machines.</span></span> <span data-ttu-id="dd983-122">これは、複数の境界コンテキスト、マイクロサービス、または異なるアプリケーションを統合する場合に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="dd983-122">This is useful for integrating multiple Bounded Contexts, microservices, or even different applications.</span></span> <span data-ttu-id="dd983-123">一方、ドメイン イベントでは、現在実行しているドメイン操作からイベントが生成されて、同じドメイン内で副作用が発生することが望まれます。</span><span class="sxs-lookup"><span data-stu-id="dd983-123">However, with domain events, you want to raise an event from the domain operation you are currently running, but you want any side effects to occur within the same domain.</span></span>

<span data-ttu-id="dd983-124">ドメイン イベントとその副作用 (その後にトリガーされる、イベント ハンドラーによって管理されるアクション) は、ほぼ瞬時に (通常はインプロセス) 同じドメイン内で発生する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dd983-124">The domain events and their side effects (the actions triggered afterwards that are managed by event handlers) should occur almost immediately, usually in-process, and within the same domain.</span></span> <span data-ttu-id="dd983-125">したがって、ドメイン イベントは同期でも非同期でもかまいません。</span><span class="sxs-lookup"><span data-stu-id="dd983-125">Thus, domain events could be synchronous or asynchronous.</span></span> <span data-ttu-id="dd983-126">ただし、統合イベントは常に非同期でなければなりません。</span><span class="sxs-lookup"><span data-stu-id="dd983-126">Integration events, however, should always be asynchronous.</span></span>

## <a name="domain-events-versus-integration-events"></a><span data-ttu-id="dd983-127">統合イベントとドメイン イベント</span><span class="sxs-lookup"><span data-stu-id="dd983-127">Domain events versus integration events</span></span>

<span data-ttu-id="dd983-128">意味としては、ドメイン イベントと統合イベントは同じものであり、発生したばかりのことに関する通知です。</span><span class="sxs-lookup"><span data-stu-id="dd983-128">Semantically, domain and integration events are the same thing: notifications about something that just happened.</span></span> <span data-ttu-id="dd983-129">しかし、それらの実装は異なっている必要があります。</span><span class="sxs-lookup"><span data-stu-id="dd983-129">However, their implementation must be different.</span></span> <span data-ttu-id="dd983-130">ドメイン イベントはドメイン イベント ディスパッチャーにプッシュされるメッセージでしかなく、IoC コンテナーまたは他の何らかの方法に基づくインメモリ メディエーターとして実装できます。</span><span class="sxs-lookup"><span data-stu-id="dd983-130">Domain events are just messages pushed to a domain event dispatcher, which could be implemented as an in-memory mediator based on an IoC container or any other method.</span></span>

<span data-ttu-id="dd983-131">一方、統合イベントの目的は、コミットされたトランザクションや更新を他のサブシステムに伝達することです。サブシステムは、他のマイクロサービス、境界コンテキスト、さらには外部アプリケーションのいずれでもかまいません。</span><span class="sxs-lookup"><span data-stu-id="dd983-131">On the other hand, the purpose of integration events is to propagate committed transactions and updates to additional subsystems, whether they are other microservices, Bounded Contexts or even external applications.</span></span> <span data-ttu-id="dd983-132">したがって、エンティティが正常に保存された場合にのみ発生する必要があります。正常に保存されない場合、操作全体がもともと行われなかったかのようになります。</span><span class="sxs-lookup"><span data-stu-id="dd983-132">Hence, they should occur only if the entity is successfully persisted, otherwise it's as if the entire operation never happened.</span></span>

<span data-ttu-id="dd983-133">前述のように、統合イベントは、複数のマイクロサービス (他の境界コンテキスト) 間または外部システム/アプリケーション間の非同期通信に基づいている必要があります。</span><span class="sxs-lookup"><span data-stu-id="dd983-133">As mentioned before, integration events must be based on asynchronous communication between multiple microservices (other Bounded Contexts) or even external systems/applications.</span></span>

<span data-ttu-id="dd983-134">したがって、イベント バス インターフェイスには、場合によってはリモート サービス間でのプロセス間分散通信を可能にする何らかのインフラストラクチャが必要です。</span><span class="sxs-lookup"><span data-stu-id="dd983-134">Thus, the event bus interface needs some infrastructure that allows inter-process and distributed communication between potentially remote services.</span></span> <span data-ttu-id="dd983-135">商用のサービス バス、キュー、メールボックスとして使われる共有データベース、またはその他の分散で、できればプッシュ ベースのメッセージング システムのいずれが基になっていてもかまいません。</span><span class="sxs-lookup"><span data-stu-id="dd983-135">It can be based on a commercial service bus, queues, a shared database used as a mailbox, or any other distributed and ideally push based messaging system.</span></span>

## <a name="domain-events-as-a-preferred-way-to-trigger-side-effects-across-multiple-aggregates-within-the-same-domain"></a><span data-ttu-id="dd983-136">同じドメイン内の複数の集約間で副作用をトリガーする望ましい方法としてのドメイン イベント</span><span class="sxs-lookup"><span data-stu-id="dd983-136">Domain events as a preferred way to trigger side effects across multiple aggregates within the same domain</span></span>

<span data-ttu-id="dd983-137">ある集約インスタンスに関係のあるコマンドを実行するために、1 つ以上の他の集約で他のドメイン ルールを実行する必要がある場合は、このような副作用がドメイン イベントによってトリガーされるように設計および実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dd983-137">If executing a command related to one aggregate instance requires additional domain rules to be run on one or more additional aggregates, you should design and implement those side effects to be triggered by domain events.</span></span> <span data-ttu-id="dd983-138">図 7-14 で示すように、最も重要なユース ケースの 1 つとして、ドメイン イベントを使って、同じドメイン モデル内の複数の集約の間で状態の変化を伝達する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dd983-138">As shown in Figure 7-14, and as one of the most important use cases, a domain event should be used to propagate state changes across multiple aggregates within the same domain model.</span></span>

![<span data-ttu-id="dd983-139">集約間の整合性はドメイン イベントによって達成されます。Order Aggregate により OrderStarted ドメイン イベントが送信されます。これが処理されて Buyer Aggregate が更新されます。</span><span class="sxs-lookup"><span data-stu-id="dd983-139">Consistency between aggregates is achieved by domain events, the Order Aggregate sends an OrderStarted domain event that's handled to update the Buyer Aggregate.</span></span> ](./media/image15.png)

<span data-ttu-id="dd983-140">**図 7-14**。</span><span class="sxs-lookup"><span data-stu-id="dd983-140">**Figure 7-14**.</span></span> <span data-ttu-id="dd983-141">同じドメイン内の複数の集約の間に整合性を適用するためのドメイン イベント</span><span class="sxs-lookup"><span data-stu-id="dd983-141">Domain events to enforce consistency between multiple aggregates within the same domain</span></span>

<span data-ttu-id="dd983-142">図では、ユーザーが注文を開始すると、OrderStarted ドメイン イベントによって、ID マイクロサービスからの元のユーザー情報 (および、CreateOrder コマンドで提供された情報) を基にした、注文マイクロサービスでの Buyer オブジェクトの作成がトリガーされます。</span><span class="sxs-lookup"><span data-stu-id="dd983-142">In the figure, when the user initiates an order, the OrderStarted domain event triggers creation of a Buyer object in the ordering microservice, based on the original user info from the identity microservice (with information provided in the CreateOrder command).</span></span> <span data-ttu-id="dd983-143">ドメイン イベントは、注文集約が最初の場所で作成されたときに生成されます。</span><span class="sxs-lookup"><span data-stu-id="dd983-143">The domain event is generated by the order aggregate when it is created in the first place.</span></span>

<span data-ttu-id="dd983-144">または、集約ルートを作成し、その集約 (子エンティティ) のメンバーによって生成されるイベントをサブスクライブすることもできます。</span><span class="sxs-lookup"><span data-stu-id="dd983-144">Alternately, you can have the aggregate root subscribed for events raised by members of its aggregates (child entities).</span></span> <span data-ttu-id="dd983-145">たとえば、OrderItem の各子エンティティは、品目の価格が指定された金額より高いとき、または製品品目の量が高すぎるとに、イベントを発生させることができます。</span><span class="sxs-lookup"><span data-stu-id="dd983-145">For instance, each OrderItem child entity can raise an event when the item price is higher than a specific amount, or when the product item amount is too high.</span></span> <span data-ttu-id="dd983-146">集約ルートは、これらのイベントを受け取って、グローバルな計算または集約を実行できます。</span><span class="sxs-lookup"><span data-stu-id="dd983-146">The aggregate root can then receive those events and perform a global calculation or aggregation.</span></span>

<span data-ttu-id="dd983-147">このイベント ベースの通信は集約内に直接実装されないことを理解しておくことが重要です。ドメイン イベント ハンドラーを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dd983-147">It is important to understand that this event-based communication is not implemented directly within the aggregates; you need to implement domain event handlers.</span></span>

<span data-ttu-id="dd983-148">ドメイン イベントの処理は、アプリケーションの問題です。</span><span class="sxs-lookup"><span data-stu-id="dd983-148">Handling the domain events is an application concern.</span></span> <span data-ttu-id="dd983-149">ドメイン モデル レイヤーでは、ハンドラーやリポジトリを使った副作用の永続化アクションといったアプリケーション インフラストラクチャに関することではなく、ドメインの専門家が理解しているドメインのロジックだけに注目する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dd983-149">The domain model layer should only focus on the domain logic—things that a domain expert would understand, not application infrastructure like handlers and side-effect persistence actions using repositories.</span></span> <span data-ttu-id="dd983-150">したがって、ドメイン イベントが発生したときのドメイン イベント ハンドラー トリガー アクションは、アプリケーション レイヤー レベルで行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="dd983-150">Therefore, the application layer level is where you should have domain event handlers triggering actions when a domain event is raised.</span></span>

<span data-ttu-id="dd983-151">また、ドメイン イベントを使って、任意の数のアプリケーション アクションをトリガーすることができます。さらに重要なことは、後でその数を他に影響を与えない方法で増やすことができる必要があります。</span><span class="sxs-lookup"><span data-stu-id="dd983-151">Domain events can also be used to trigger any number of application actions, and what is more important, must be open to increase that number in the future in a decoupled way.</span></span> <span data-ttu-id="dd983-152">たとえば、注文が開始されたら、ドメイン イベントを発行してその情報を他の集約に伝達したり、通知などのアプリケーション アクションを発生させたりすることができます。</span><span class="sxs-lookup"><span data-stu-id="dd983-152">For instance, when the order is started, you might want to publish a domain event to propagate that info to other aggregates or even to raise application actions like notifications.</span></span>

<span data-ttu-id="dd983-153">重要な点は、ドメイン イベントが発生したときに実行されるアクションの数が開放されていることです。</span><span class="sxs-lookup"><span data-stu-id="dd983-153">The key point is the open number of actions to be executed when a domain event occurs.</span></span> <span data-ttu-id="dd983-154">いずれ、ドメインおよびアプリケーション内のアクションとルールは増えていきます。</span><span class="sxs-lookup"><span data-stu-id="dd983-154">Eventually, the actions and rules in the domain and application will grow.</span></span> <span data-ttu-id="dd983-155">何かが発生したときの副作用の複雑さや数は上昇しますが、コードが "接着剤" で結合されていると (つまり、`new` で特定のオブジェクトを作成します)、新しいアクションを追加する必要があるたびに、テスト済みで動作するコードを変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dd983-155">The complexity or number of side-effect actions when something happens will grow, but if your code were coupled with “glue” (that is, creating specific objects with `new`), then every time you needed to add a new action you would also need to change working and tested code.</span></span>

<span data-ttu-id="dd983-156">この変更の結果、新しいバグが発生する可能性があります。また、この手法は [SOLID](https://en.wikipedia.org/wiki/SOLID) の[開放/閉鎖 (Open/closed) の原則](https://en.wikipedia.org/wiki/Open/closed_principle)に違反します。</span><span class="sxs-lookup"><span data-stu-id="dd983-156">This change could result in new bugs and this approach also goes against the [Open/Closed principle](https://en.wikipedia.org/wiki/Open/closed_principle) from [SOLID](https://en.wikipedia.org/wiki/SOLID).</span></span> <span data-ttu-id="dd983-157">それだけでなく、操作を調整していた元のクラスが拡大を重ね、[単一責任原則 (SRP)](https://en.wikipedia.org/wiki/Single_responsibility_principle) に反するようになります。</span><span class="sxs-lookup"><span data-stu-id="dd983-157">Not only that, the original class that was orchestrating the operations would grow and grow, which goes against the [Single Responsibility Principle (SRP)](https://en.wikipedia.org/wiki/Single_responsibility_principle).</span></span>

<span data-ttu-id="dd983-158">これに対し、ドメイン イベントでは、以下のアプローチを使って責任を隔離することにより、粒度が細かく分離された実装を作成することができます。</span><span class="sxs-lookup"><span data-stu-id="dd983-158">On the other hand, if you use domain events, you can create a fine-grained and decoupled implementation by segregating responsibilities using this approach:</span></span>

1. <span data-ttu-id="dd983-159">コマンドを送信します (例: CreateOrder)。</span><span class="sxs-lookup"><span data-stu-id="dd983-159">Send a command (for example, CreateOrder).</span></span>
2. <span data-ttu-id="dd983-160">コマンド ハンドラーでコマンドを受信します。</span><span class="sxs-lookup"><span data-stu-id="dd983-160">Receive the command in a command handler.</span></span>
   - <span data-ttu-id="dd983-161">1 つの集約のトランザクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="dd983-161">Execute a single aggregate’s transaction.</span></span>
   - <span data-ttu-id="dd983-162">(省略可能) 副作用のドメイン イベントを発生させます (例: OrderStartedDomainEvent)。</span><span class="sxs-lookup"><span data-stu-id="dd983-162">(Optional) Raise domain events for side effects (for example, OrderStartedDomainEvent).</span></span>
3. <span data-ttu-id="dd983-163">複数の集約またはアプリケーション アクションにおいて開放された数の副作用を実行する (現在のプロセス内の) ドメイン ベントを処理します。</span><span class="sxs-lookup"><span data-stu-id="dd983-163">Handle domain events (within the current process) that will execute an open number of side effects in multiple aggregates or application actions.</span></span> <span data-ttu-id="dd983-164">例:</span><span class="sxs-lookup"><span data-stu-id="dd983-164">For example:</span></span>
   - <span data-ttu-id="dd983-165">購入者および支払方法を確認または作成します。</span><span class="sxs-lookup"><span data-stu-id="dd983-165">Verify or create buyer and payment method.</span></span>
   - <span data-ttu-id="dd983-166">関連する統合イベントを作成してイベント バスに送信し、複数のマイクロサービスに状態を伝達するか、購入者へのメール送信のような外部アクションをトリガーします。</span><span class="sxs-lookup"><span data-stu-id="dd983-166">Create and send a related integration event to the event bus to propagate states across microservices or trigger external actions like sending an email to the buyer.</span></span>
   - <span data-ttu-id="dd983-167">他の副作用を処理します。</span><span class="sxs-lookup"><span data-stu-id="dd983-167">Handle other side effects.</span></span>

<span data-ttu-id="dd983-168">図 7-15 で示すように、同じドメイン イベントから開始して、統合イベントおよびイベント バスによって接続されている複数のマイクロサービスを実行するために必要な、ドメイン内の他の集約に関連する複数のアクションまたは他のアプリケーション アクションを処理できます。</span><span class="sxs-lookup"><span data-stu-id="dd983-168">As shown in Figure 7-15, starting from the same domain event, you can handle multiple actions related to other aggregates in the domain or additional application actions you need to perform across microservices connecting with integration events and the event bus.</span></span>

![アプリケーション レイヤーでは、同じイベントに対してハンドラーが複数存在することがあります。あるハンドラーで集約間の整合性を解決し、別のハンドラーで統合イベントを公開し、他のマイクロサービスがその公開されたイベントで何かの処理を行うといったことがありえます。](./media/image16.png)

<span data-ttu-id="dd983-170">**図 7-15**。</span><span class="sxs-lookup"><span data-stu-id="dd983-170">**Figure 7-15**.</span></span> <span data-ttu-id="dd983-171">ドメインごとに複数のアクションの処理</span><span class="sxs-lookup"><span data-stu-id="dd983-171">Handling multiple actions per domain</span></span>

<span data-ttu-id="dd983-172">マイクロサービスの動作にはリポジトリやアプリケーション API などのインフラストラクチャ オブジェクトを使うため、通常、イベント ハンドラーはアプリケーション レイヤーにあります。</span><span class="sxs-lookup"><span data-stu-id="dd983-172">The event handlers are typically in the application layer, because you will use infrastructure objects like repositories or an application API for the microservice’s behavior.</span></span> <span data-ttu-id="dd983-173">どちらもアプリケーション レイヤーの一部であるという意味で、イベント ハンドラーはコマンド ハンドラーに似ています。</span><span class="sxs-lookup"><span data-stu-id="dd983-173">In that sense, event handlers are similar to command handlers, so both are part of the application layer.</span></span> <span data-ttu-id="dd983-174">重要な相違点は、コマンドは 1 回だけ処理する必要があることです。</span><span class="sxs-lookup"><span data-stu-id="dd983-174">The important difference is that a command should be processed only once.</span></span> <span data-ttu-id="dd983-175">ドメイン イベントは、それぞれが異なる用途を持つ複数のレシーバーまたはイベント ハンドラーで受信できるため、ドメイン イベントはゼロ回または *n* 回処理される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="dd983-175">A domain event could be processed zero or *n* times, because it can be received by multiple receivers or event handlers with a different purpose for each handler.</span></span>

<span data-ttu-id="dd983-176">ドメイン イベントあたりのハンドラーの数を開放できるため、現在のコードに影響を与えずに必要な数だけドメイン ルールを追加できます。</span><span class="sxs-lookup"><span data-stu-id="dd983-176">Having an open number of handlers per domain event allows you to add as many domain rules without as needed, without affecting  current code.</span></span> <span data-ttu-id="dd983-177">たとえば、次のビジネス ルールは、いくつかのイベント ハンドラー (またはたった 1 つ) を追加するだけで簡単に実装できます。</span><span class="sxs-lookup"><span data-stu-id="dd983-177">For instance, implementing the following business rule might be as easy as adding a few event handlers (or even just one):</span></span>

> <span data-ttu-id="dd983-178">顧客がストアで行った任意の数の注文の合計購入金額が $6,000 を超える場合、すべての新規注文に 10% の割引を適用し、将来の注文に対するその割引のことをメールで顧客に通知します。</span><span class="sxs-lookup"><span data-stu-id="dd983-178">When the total amount purchased by a customer in the store, across any number of orders, exceeds $6,000, apply a 10% off discount to every new order and notify the customer with an email about that discount for future orders.</span></span>

## <a name="implement-domain-events"></a><span data-ttu-id="dd983-179">ドメイン イベントの実装</span><span class="sxs-lookup"><span data-stu-id="dd983-179">Implement domain events</span></span>

<span data-ttu-id="dd983-180">C# のドメイン イベントは、ドメインで発生したことに関連するすべての情報を含む、DTO のようなデータ保持構造体またはクラスです。次にその例を示します。</span><span class="sxs-lookup"><span data-stu-id="dd983-180">In C#, a domain event is simply a data-holding structure or class, like a DTO, with all the information related to what just happened in the domain, as shown in the following example:</span></span>

```csharp
public class OrderStartedDomainEvent : INotification
{
    public string UserId { get; }
    public int CardTypeId { get; }
    public string CardNumber { get; }
    public string CardSecurityNumber { get; }
    public string CardHolderName { get; }
    public DateTime CardExpiration { get; }
    public Order Order { get; }

    public OrderStartedDomainEvent(Order order,
                                   int cardTypeId, string cardNumber,
                                   string cardSecurityNumber, string cardHolderName,
                                   DateTime cardExpiration)
    {
        Order = order;
        CardTypeId = cardTypeId;
        CardNumber = cardNumber;
        CardSecurityNumber = cardSecurityNumber;
        CardHolderName = cardHolderName;
        CardExpiration = cardExpiration;
    }
}
```

<span data-ttu-id="dd983-181">これは、本質的に OrderStarted イベントに関連するすべてのデータを保持するクラスです。</span><span class="sxs-lookup"><span data-stu-id="dd983-181">This is essentially a class that holds all the data related to the OrderStarted event.</span></span>

<span data-ttu-id="dd983-182">ユビキタス言語の観点からは、イベントは過去に発生した事柄なので、イベントのクラス名は OrderStartedDomainEvent や OrderShippedDomainEvent のような過去形動詞として表される必要があります。</span><span class="sxs-lookup"><span data-stu-id="dd983-182">In terms of the ubiquitous language of the domain, since an event is something that happened in the past, the class name of the event should be represented as a past-tense verb, like OrderStartedDomainEvent or OrderShippedDomainEvent.</span></span> <span data-ttu-id="dd983-183">これは、eShopOnContainers の注文マイクロサービスでのドメイン イベントの実装方法です。</span><span class="sxs-lookup"><span data-stu-id="dd983-183">That's how the domain event is implemented in the ordering microservice in eShopOnContainers.</span></span>

<span data-ttu-id="dd983-184">前に説明したように、イベントの重要な特性は、イベントは過去に発生したことなので変更できない、ということです。</span><span class="sxs-lookup"><span data-stu-id="dd983-184">As noted earlier, an important characteristic of events is that since an event is something that happened in the past, it should not change.</span></span> <span data-ttu-id="dd983-185">したがって、不変クラスである必要があります。</span><span class="sxs-lookup"><span data-stu-id="dd983-185">Therefore, it must be an immutable class.</span></span> <span data-ttu-id="dd983-186">上のコードでは、プロパティが読み取り専用であることがわかります。</span><span class="sxs-lookup"><span data-stu-id="dd983-186">You can see in the previous code that the properties are read-only.</span></span> <span data-ttu-id="dd983-187">オブジェクトを更新する方法はありません。作成するときに値を設定することのみ可能です。</span><span class="sxs-lookup"><span data-stu-id="dd983-187">There's no way to update the object, you can only set values when you create it.</span></span>

<span data-ttu-id="dd983-188">ここで強調しておくことが重要ですが、イベント オブジェクトのシリアル化と逆シリアル化を必要としたキューを使用し、ドメイン イベントを非同期で処理するなら、おそらく、キュー解除時、デシリアライザーで値を割り当てられるよう、プロパティを読み取り専用ではなく "プライベート セット" にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="dd983-188">It’s important to highlight here that if domain events were to be handled asynchronously, using a queue that required serializing and deserializing the event objects, the properties would have to be “private set” instead of read-only, so the deserializer would be able to assign the values upon dequeuing.</span></span> <span data-ttu-id="dd983-189">ドメイン イベント パブ/サブは MediatR を利用して非同期で実装されるため、これは Ordering マイクロサービスの問題ではありません。</span><span class="sxs-lookup"><span data-stu-id="dd983-189">This is not an issue in the Ordering microservice, as the domain event pub/sub is implemented synchronously using MediatR.</span></span>

### <a name="raise-domain-events"></a><span data-ttu-id="dd983-190">ドメイン イベントを生成する</span><span class="sxs-lookup"><span data-stu-id="dd983-190">Raise domain events</span></span>

<span data-ttu-id="dd983-191">次に知りたいことは、関連するイベント ハンドラーに届くようにドメイン イベントを生成する方法です。</span><span class="sxs-lookup"><span data-stu-id="dd983-191">The next question is how to raise a domain event so it reaches its related event handlers.</span></span> <span data-ttu-id="dd983-192">複数の方法があります。</span><span class="sxs-lookup"><span data-stu-id="dd983-192">You can use multiple approaches.</span></span>

<span data-ttu-id="dd983-193">Udi Dahan がもともと提案しているのは (たとえば、「[Domain Events – Take 2](http://udidahan.com/2008/08/25/domain-events-take-2/)」(ドメイン イベント – テイク 2 などの複数の関連する投稿を参照))、イベントの管理と生成に静的クラスを使う方法です。</span><span class="sxs-lookup"><span data-stu-id="dd983-193">Udi Dahan originally proposed (for example, in several related posts, such as [Domain Events – Take 2](http://udidahan.com/2008/08/25/domain-events-take-2/)) using a static class for managing and raising the events.</span></span> <span data-ttu-id="dd983-194">これには、`DomainEvents.Raise(Event myEvent)` のような構文を使用し、呼び出されるとすぐにドメイン イベントを生成する DomainEvents という名前の静的クラスが含まれる場合があります。</span><span class="sxs-lookup"><span data-stu-id="dd983-194">This might include a static class named DomainEvents that would raise domain events immediately when it is called, using syntax like `DomainEvents.Raise(Event myEvent)`.</span></span> <span data-ttu-id="dd983-195">Jimmy Bogard も、ブログ投稿「[Strengthening your domain:Domain Events](https://lostechies.com/jimmybogard/2010/04/08/strengthening-your-domain-domain-events/)」(ドメインの強化: ドメイン イベント) で同様のアプローチを推奨しています。</span><span class="sxs-lookup"><span data-stu-id="dd983-195">Jimmy Bogard wrote a blog post ([Strengthening your domain: Domain Events](https://lostechies.com/jimmybogard/2010/04/08/strengthening-your-domain-domain-events/)) that recommends a similar approach.</span></span>

<span data-ttu-id="dd983-196">ただし、ドメイン イベント クラスが静的である場合は、ハンドラーにもすぐにディスパッチにします。</span><span class="sxs-lookup"><span data-stu-id="dd983-196">However, when the domain events class is static, it also dispatches to handlers immediately.</span></span> <span data-ttu-id="dd983-197">これにより、副作用のロジックを含むイベント ハンドラーがイベント生成直後に実行されるため、テストとデバッグが難しくなります。</span><span class="sxs-lookup"><span data-stu-id="dd983-197">This makes testing and debugging more difficult, because the event handlers with side-effects logic are executed immediately after the event is raised.</span></span> <span data-ttu-id="dd983-198">テストとデバッグを行うときは、現在の集約クラスで発生していることだけに注目する必要があります。他の集約やアプリケーション ロジックに関連する副作用に対する他のイベント ハンドラーに突然リダイレクトされるのは困ります。</span><span class="sxs-lookup"><span data-stu-id="dd983-198">When you are testing and debugging, you want to focus on and just what is happening in the current aggregate classes; you do not want to suddenly be redirected to other event handlers for side effects related to other aggregates or application logic.</span></span> <span data-ttu-id="dd983-199">このような理由から、次のセクションで説明する他のアプローチが考案されています。</span><span class="sxs-lookup"><span data-stu-id="dd983-199">This is why other approaches have evolved, as explained in the next section.</span></span>

#### <a name="the-deferred-approach-to-raise-and-dispatch-events"></a><span data-ttu-id="dd983-200">イベントを生成し、ディスパッチする遅延アプローチ</span><span class="sxs-lookup"><span data-stu-id="dd983-200">The deferred approach to raise and dispatch events</span></span>

<span data-ttu-id="dd983-201">ドメイン イベント ハンドラーにすぐにディスパッチするよりよい方法は、ドメイン イベントをコレクションに追加した後、トランザクションを (EF の SaveChanges で) コミットする "*直前*" または "*直* *後*" に、それらのドメイン イベントをディスパッチすることです</span><span class="sxs-lookup"><span data-stu-id="dd983-201">Instead of dispatching to a domain event handler immediately, a better approach is to add the domain events to a collection and then to dispatch those domain events *right before* or *right* *after* committing the transaction (as with SaveChanges in EF).</span></span> <span data-ttu-id="dd983-202">(このアプローチについては、Jimmy Bogard の「[A better domain events pattern](https://lostechies.com/jimmybogard/2014/05/13/a-better-domain-events-pattern/)」(よりよいドメイン イベント パターン) を参照)。</span><span class="sxs-lookup"><span data-stu-id="dd983-202">(This approach was described by Jimmy Bogard in this post [A better domain events pattern](https://lostechies.com/jimmybogard/2014/05/13/a-better-domain-events-pattern/).)</span></span>

<span data-ttu-id="dd983-203">ドメイン イベントの送信をトランザクションのコミットの直前または直後のどちらにするかは、副作用を同じトランザクションまたは別のトランザクションのどちらに含めればよいかに影響するので、重要な決定です。</span><span class="sxs-lookup"><span data-stu-id="dd983-203">Deciding if you send the domain events right before or right after committing the transaction is important, since it determines whether you will include the side effects as part of the same transaction or in different transactions.</span></span> <span data-ttu-id="dd983-204">後者の場合は、複数の集約の間の最終的な整合性に対処する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dd983-204">In the latter case, you need to deal with eventual consistency across multiple aggregates.</span></span> <span data-ttu-id="dd983-205">これについては、次のセクションで説明します。</span><span class="sxs-lookup"><span data-stu-id="dd983-205">This topic is discussed in the next section.</span></span>

<span data-ttu-id="dd983-206">eShopOnContainers では遅延アプローチを使っています。</span><span class="sxs-lookup"><span data-stu-id="dd983-206">The deferred approach is what eShopOnContainers uses.</span></span> <span data-ttu-id="dd983-207">最初に、エンティティで発生したイベントを、エンティティごとのコレクションまたはイベント リストに追加します。</span><span class="sxs-lookup"><span data-stu-id="dd983-207">First, you add the events happening in your entities into a collection or list of events per entity.</span></span> <span data-ttu-id="dd983-208">このリストは、エンティティ オブジェクトの一部にする必要があり、さらによい方法は、次の Entity 基底クラスの例で示すように、基本エンティティ クラスの一部にすることです。</span><span class="sxs-lookup"><span data-stu-id="dd983-208">That list should be part of the entity object, or even better, part of your base entity class, as shown in the following example of the Entity base class:</span></span>

```csharp
public abstract class Entity
{
     //... 
     private List<INotification> _domainEvents;
     public List<INotification> DomainEvents => _domainEvents; 

     public void AddDomainEvent(INotification eventItem)
     {
         _domainEvents = _domainEvents ?? new List<INotification>();
         _domainEvents.Add(eventItem);
     }

     public void RemoveDomainEvent(INotification eventItem)
     {
         _domainEvents?.Remove(eventItem);
     }
     //... Additional code
}
```

<span data-ttu-id="dd983-209">イベントを生成するときは、集約ルート エンティティの任意のメソッドのコードから、イベント コレクションにイベントを追加するだけです。</span><span class="sxs-lookup"><span data-stu-id="dd983-209">When you want to raise an event, you just add it to the event collection from code at any method of the aggregate-root entity.</span></span>

<span data-ttu-id="dd983-210">次に示すコードの例は、[eShopOnContainers の Order 集約ルート](https://github.com/dotnet-architecture/eShopOnContainers/blob/dev/src/Services/Ordering/Ordering.Domain/AggregatesModel/OrderAggregate/Order.cs)の一部です。</span><span class="sxs-lookup"><span data-stu-id="dd983-210">The following code, part of the [Order aggregate-root at eShopOnContainers](https://github.com/dotnet-architecture/eShopOnContainers/blob/dev/src/Services/Ordering/Ordering.Domain/AggregatesModel/OrderAggregate/Order.cs), shows an example:</span></span>

```csharp
var orderStartedDomainEvent = new OrderStartedDomainEvent(this, //Order object
                                                          cardTypeId, cardNumber,
                                                          cardSecurityNumber,
                                                          cardHolderName,
                                                          cardExpiration);
this.AddDomainEvent(orderStartedDomainEvent);
```

<span data-ttu-id="dd983-211">AddDomainEvent メソッドで行われているのが、リストへのイベントの追加だけであることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="dd983-211">Notice that the only thing that the AddDomainEvent method is doing is adding an event to the list.</span></span> <span data-ttu-id="dd983-212">イベントはまだディスパッチされておらず、イベント ハンドラーはまだ呼び出されていません。</span><span class="sxs-lookup"><span data-stu-id="dd983-212">No event is dispatched yet, and no event handler is invoked yet.</span></span>

<span data-ttu-id="dd983-213">実際にイベントをディスパッチするのは、後でデータベースにトランザクションをコミットするときです。</span><span class="sxs-lookup"><span data-stu-id="dd983-213">You actually want to dispatch the events later on, when you commit the transaction to the database.</span></span> <span data-ttu-id="dd983-214">Entity Framework Core を使っている場合は、次のコードのように、EF DbContext の SaveChanges メソッド内であることを意味します。</span><span class="sxs-lookup"><span data-stu-id="dd983-214">If you are using Entity Framework Core, that means in the SaveChanges method of your EF DbContext, as in the following code:</span></span>

```csharp
// EF Core DbContext
public class OrderingContext : DbContext, IUnitOfWork
{
    // ...
    public async Task<bool> SaveEntitiesAsync(CancellationToken cancellationToken = default(CancellationToken))
    {
        // Dispatch Domain Events collection.
        // Choices:
        // A) Right BEFORE committing data (EF SaveChanges) into the DB. This makes
        // a single transaction including side effects from the domain event
        // handlers that are using the same DbContext with Scope lifetime
        // B) Right AFTER committing data (EF SaveChanges) into the DB. This makes
        // multiple transactions. You will need to handle eventual consistency and
        // compensatory actions in case of failures.        
        await _mediator.DispatchDomainEventsAsync(this);

        // After this line runs, all the changes (from the Command Handler and Domain
        // event handlers) performed through the DbContext will be committed
        var result = await base.SaveChangesAsync();
    }
}
```

<span data-ttu-id="dd983-215">このコードでは、エンティティ イベントを対応するイベント ハンドラーにディスパッチします。</span><span class="sxs-lookup"><span data-stu-id="dd983-215">With this code, you dispatch the entity events to their respective event handlers.</span></span>

<span data-ttu-id="dd983-216">全体な結果として、ドメイン イベントの生成 (単にメモリ内のリストへの追加) がイベント ハンドラーへのディスパッチから切り離されます。</span><span class="sxs-lookup"><span data-stu-id="dd983-216">The overall result is that you have decoupled the raising of a domain event (a simple add into a list in memory) from dispatching it to an event handler.</span></span> <span data-ttu-id="dd983-217">さらに、使っているディスパッチャーの種類によっては、同期または非同期にイベントをディスパッチできます。</span><span class="sxs-lookup"><span data-stu-id="dd983-217">In addition, depending on what kind of dispatcher you are using, you could dispatch the events synchronously or asynchronously.</span></span>

<span data-ttu-id="dd983-218">ここでは、トランザクション境界が重要な意味を持つことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="dd983-218">Be aware that transactional boundaries come into significant play here.</span></span> <span data-ttu-id="dd983-219">作業単位とトランザクションが複数の集約にまたがることができる場合 (EF Core とリレーショナル データベースを使っている場合など)、これはうまくいきます。</span><span class="sxs-lookup"><span data-stu-id="dd983-219">If your unit of work and transaction can span more than one aggregate (as when using EF Core and a relational database), this can work well.</span></span> <span data-ttu-id="dd983-220">しかしながら、トランザクションが複数の集約にまたがることができない場合は (Azure CosmosDB のような NoSQL を使っている場合)、整合性を実現するための追加手順を実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dd983-220">But if the transaction cannot span aggregates, such as when you are using a NoSQL database like Azure CosmosDB, you have to implement additional steps to achieve consistency.</span></span> <span data-ttu-id="dd983-221">これは、永続性の無視がユニバーサルではないもう 1 つの理由であり、使っているストレージ システムに依存します。</span><span class="sxs-lookup"><span data-stu-id="dd983-221">This is another reason why persistence ignorance is not universal; it depends on the storage system you use.</span></span> 

### <a name="single-transaction-across-aggregates-versus-eventual-consistency-across-aggregates"></a><span data-ttu-id="dd983-222">複数の集約にまたがる 1 つのトランザクションと集約の間の最終的な整合性</span><span class="sxs-lookup"><span data-stu-id="dd983-222">Single transaction across aggregates versus eventual consistency across aggregates</span></span>

<span data-ttu-id="dd983-223">複数の集約にまたがる 1 つのトランザクションを実行する方がよいか、それともそれらの集約の間の最終的な整合性に依存する方がよいかは、難しい問題です。</span><span class="sxs-lookup"><span data-stu-id="dd983-223">The question of whether to perform a single transaction across aggregates versus relying on eventual consistency across those aggregates is a controversial one.</span></span> <span data-ttu-id="dd983-224">Eric Evans や Vaughn Vernon などの多くの DDD 作成者は、1 トランザクション = 1 集約のルールを推奨しており、したがって集約間の最終的な整合性を主張しています。</span><span class="sxs-lookup"><span data-stu-id="dd983-224">Many DDD authors like Eric Evans and Vaughn Vernon advocate the rule that one transaction = one aggregate and therefore argue for eventual consistency across aggregates.</span></span> <span data-ttu-id="dd983-225">たとえば、Eric Evans は『*Domain-Driven Design*』(ドメイン ドリブンの設計) で次のように書いています。</span><span class="sxs-lookup"><span data-stu-id="dd983-225">For example, in his book *Domain-Driven Design*, Eric Evans says this:</span></span>

> <span data-ttu-id="dd983-226">複数の集約に関係するルールは、常に最新の状態であることを期待できません。</span><span class="sxs-lookup"><span data-stu-id="dd983-226">Any rule that spans Aggregates will not be expected to be up-to-date at all times.</span></span> <span data-ttu-id="dd983-227">イベント処理、バッチ処理、または他の更新メカニズムにより、他の依存関係はある特定の時間内に解決できます。</span><span class="sxs-lookup"><span data-stu-id="dd983-227">Through event processing, batch processing, or other update mechanisms, other dependencies can be resolved within some specific time.</span></span> <span data-ttu-id="dd983-228">(128 ページ)</span><span class="sxs-lookup"><span data-stu-id="dd983-228">(page 128)</span></span>

<span data-ttu-id="dd983-229">Vaughn Vernon は、『[Effective Aggregate Design.Part II:Making Aggregates Work Together](https://dddcommunity.org/wp-content/uploads/files/pdf_articles/Vernon_2011_2.pdf)』(効果的な集約設計パート II: 集約処理の連携) で次のように書いています。</span><span class="sxs-lookup"><span data-stu-id="dd983-229">Vaughn Vernon says the following in [Effective Aggregate Design. Part II: Making Aggregates Work Together](https://dddcommunity.org/wp-content/uploads/files/pdf_articles/Vernon_2011_2.pdf):</span></span>

> <span data-ttu-id="dd983-230">したがって、1 つの集約インスタンスでコマンドを実行するために、他のビジネス ルールを 1 つ以上の集約で実行する必要がある場合は、最終的な整合性を使います \[...\]。DDD モデルには最終的な整合性をサポートするための実用的な方法があります。</span><span class="sxs-lookup"><span data-stu-id="dd983-230">Thus, if executing a command on one aggregate instance requires that additional business rules execute on one or more aggregates, use eventual consistency \[...\] There is a practical way to support eventual consistency in a DDD model.</span></span> <span data-ttu-id="dd983-231">集約メソッドが発行したドメイン イベントは、1 つ以上の非同期サブスクライバーに時間内に配信されます。</span><span class="sxs-lookup"><span data-stu-id="dd983-231">An aggregate method publishes a domain event that is in time delivered to one or more asynchronous subscribers.</span></span>

<span data-ttu-id="dd983-232">この原理は、多数の集約またはエンティティにまたがるトランザクションではなく、粒度が細かいトランザクションの採用に基づいています。</span><span class="sxs-lookup"><span data-stu-id="dd983-232">This rationale is based on embracing fine-grained transactions instead of transactions spanning many aggregates or entities.</span></span> <span data-ttu-id="dd983-233">考え方として、2 番目のケースでは、高いスケーラビリティが必要な大規模なアプリケーションではデータベース ロックの数がかなり多くなるということです。</span><span class="sxs-lookup"><span data-stu-id="dd983-233">The idea is that in the second case, the number of database locks will be substantial in large-scale applications with high scalability needs.</span></span> <span data-ttu-id="dd983-234">拡張性の高いアプリケーションでは複数の集約間に即時のトランザクション整合性は必要ないという事実を考えると、最終的な整合性の概念を受け入れるのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="dd983-234">Embracing the fact that highly scalable applications need not have instant transactional consistency between multiple aggregates helps with accepting the concept of eventual consistency.</span></span> <span data-ttu-id="dd983-235">アトミックな変更はビジネスで必要ないことが多く、特定の操作にアトミックなトランザクションが必要かどうかを示すのは、常にドメイン専門家の責任です。</span><span class="sxs-lookup"><span data-stu-id="dd983-235">Atomic changes are often not needed by the business, and it is in any case the responsibility of the domain experts to say whether particular operations need atomic transactions or not.</span></span> <span data-ttu-id="dd983-236">常に操作で複数の集約の間にアトミックなトランザクションが必要な場合は、集約をもっと大きくする必要があるかどうか、または集約が正しく設計されているか疑問に感じることがあります。</span><span class="sxs-lookup"><span data-stu-id="dd983-236">If an operation always needs an atomic transaction between multiple aggregates, you might ask whether your aggregate should be larger or was not correctly designed.</span></span>

<span data-ttu-id="dd983-237">一方、Jimmy Bogard のような他の開発者や設計者は、単一のトランザクションが複数の集約にまたがってもかまわないと考えています。ただし、このような追加の集約が同じ元のコマンドの副作用に関係している場合だけです。</span><span class="sxs-lookup"><span data-stu-id="dd983-237">However, other developers and architects like Jimmy Bogard are okay with spanning a single transaction across several aggregates—but only when those additional aggregates are related to side effects for the same original command.</span></span> <span data-ttu-id="dd983-238">たとえば、Bogard は「[A better domain events pattern](https://lostechies.com/jimmybogard/2014/05/13/a-better-domain-events-pattern/)」(よりよいドメイン イベント パターン) で次のように書いています。</span><span class="sxs-lookup"><span data-stu-id="dd983-238">For instance, in [A better domain events pattern](https://lostechies.com/jimmybogard/2014/05/13/a-better-domain-events-pattern/), Bogard says this:</span></span>

> <span data-ttu-id="dd983-239">通常はドメイン イベントの副作用は同じ論理トランザクション内で発生する必要がありますが、必ずしも同じドメイン イベント発生スコープ内である必要はありません \[...\]。トランザクションをコミットする直前に、対応するハンドラーにイベントをディスパッチします。</span><span class="sxs-lookup"><span data-stu-id="dd983-239">Typically, I want the side effects of a domain event to occur within the same logical transaction, but not necessarily in the same scope of raising the domain event \[...\] Just before we commit our transaction, we dispatch our events to their respective handlers.</span></span>

<span data-ttu-id="dd983-240">元のトランザクションをコミットする "*直前*" にドメイン イベントをディスパッチする場合は、これらのイベントの副作用を同じトランザクションに含まれるようにするためです。</span><span class="sxs-lookup"><span data-stu-id="dd983-240">If you dispatch the domain events right *before* committing the original transaction, it is because you want the side effects of those events to be included in the same transaction.</span></span> <span data-ttu-id="dd983-241">たとえば、EF DbContext SaveChanges メソッドが失敗した場合、トランザクションは、関連するドメイン イベント ハンドラーによって実装されているすべての副作用操作の結果を含む、すべての変更をロールバックします。</span><span class="sxs-lookup"><span data-stu-id="dd983-241">For example, if the EF DbContext SaveChanges method fails, the transaction will roll back all changes, including the result of any side effect operations implemented by the related domain event handlers.</span></span> <span data-ttu-id="dd983-242">これは、DbContext の有効期間の範囲が、既定で "スコープ" と定義されているためです。</span><span class="sxs-lookup"><span data-stu-id="dd983-242">This is because the DbContext life scope is by default defined as "scoped."</span></span> <span data-ttu-id="dd983-243">したがって、DbContext オブジェクトは、同じスコープ内またはオブジェクト グラフ内でインスタンス化されている複数のリポジトリ オブジェクト間で共有されます。</span><span class="sxs-lookup"><span data-stu-id="dd983-243">Therefore, the DbContext object is shared across multiple repository objects being instantiated within the same scope or object graph.</span></span> <span data-ttu-id="dd983-244">これは、Web API または MVC アプリを開発するときの HttpRequest スコープと一致します。</span><span class="sxs-lookup"><span data-stu-id="dd983-244">This coincides with the HttpRequest scope when developing Web API or MVC apps.</span></span>

<span data-ttu-id="dd983-245">実際には、どちらの方法 (単一のアトミック トランザクションと最終的な整合性) も適切な場合があります。</span><span class="sxs-lookup"><span data-stu-id="dd983-245">Actually, both approaches (single atomic transaction and eventual consistency) can be right.</span></span> <span data-ttu-id="dd983-246">どちらがよいかは、ドメインまたはビジネスの要件と、ドメイン専門家の意見に依存します。</span><span class="sxs-lookup"><span data-stu-id="dd983-246">It really depends on your domain or business requirements and what the domain experts tell you.</span></span> <span data-ttu-id="dd983-247">また、サービスに必要なスケーラビリティのレベルにも依存します (トランザクションの粒度が細かいほど、データベース ロックに関する影響は小さくなります)。</span><span class="sxs-lookup"><span data-stu-id="dd983-247">It also depends on how scalable you need the service to be (more granular transactions have less impact with regard to database locks).</span></span> <span data-ttu-id="dd983-248">また、最終的な整合性では、集約間で可能性のある不整合を検出するためにより複雑なコードが必要であり、補正アクションを実装する必要があるため、コードにかけられる費用によっても左右されます。</span><span class="sxs-lookup"><span data-stu-id="dd983-248">And it depends on how much investment you are willing to make in your code, since eventual consistency requires more complex code in order to detect possible inconsistencies across aggregates and the need to implement compensatory actions.</span></span> <span data-ttu-id="dd983-249">元の集約に変更をコミットした後、イベントがディスパッチされるとき、問題があってイベント ハンドラーが副作用をコミットできない場合は、集約の間に不整合が発生することを考慮してください。</span><span class="sxs-lookup"><span data-stu-id="dd983-249">Consider that if you commit changes to the original aggregate and afterwards, when the events are being dispatched, if there is an issue and the event handlers cannot commit their side effects, you will have inconsistencies between aggregates.</span></span>

<span data-ttu-id="dd983-250">補正アクションを実装するには、ドメイン イベントを追加データベース テーブルに格納して、ドメイン インベントが元のトランザクションの一部になるようにします。</span><span class="sxs-lookup"><span data-stu-id="dd983-250">A way to allow compensatory actions would be to store the domain events in additional database tables so they can be part of the original transaction.</span></span> <span data-ttu-id="dd983-251">その後は、バッチ処理で、イベントのリストと集約の現在の状態を比較することによって不整合を検出し、補正アクションを実行することができます。</span><span class="sxs-lookup"><span data-stu-id="dd983-251">Afterwards, you could have a batch process that detects inconsistencies and runs compensatory actions by comparing the list of events with the current state of the aggregates.</span></span> <span data-ttu-id="dd983-252">補正アクションは開発側からの詳細な分析が必要な複雑なトピックの一部であり、ビジネス ユーザーやドメイン専門家との検討が含まれます。</span><span class="sxs-lookup"><span data-stu-id="dd983-252">The compensatory actions are part of a complex topic that will require deep analysis from your side, which includes discussing it with the business user and domain experts.</span></span>

<span data-ttu-id="dd983-253">どのような場合でも、必要なアプローチを選ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="dd983-253">In any case, you can choose the approach you need.</span></span> <span data-ttu-id="dd983-254">ただし、EF Core とリレーショナル データベースを使うときは、初期遅延アプローチ (コミットの前にイベントを生成し、単一のトランザクションを使う) が最も簡単な方法です。</span><span class="sxs-lookup"><span data-stu-id="dd983-254">But the initial deferred approach—raising the events before committing, so you use a single transaction—is the simplest approach when using EF Core and a relational database.</span></span> <span data-ttu-id="dd983-255">実装が簡単であり、多くのビジネス ケースで有効です。</span><span class="sxs-lookup"><span data-stu-id="dd983-255">It is easier to implement and valid in many business cases.</span></span> <span data-ttu-id="dd983-256">eShopOnContainers の注文マイクロサービスでも、この方法が使われています。</span><span class="sxs-lookup"><span data-stu-id="dd983-256">It is also the approach used in the ordering microservice in eShopOnContainers.</span></span>

<span data-ttu-id="dd983-257">しかし、これらのイベントを対応するイベント ハンドラーに実際にディスパッチするにはどうすればよいでしょう。</span><span class="sxs-lookup"><span data-stu-id="dd983-257">But how do you actually dispatch those events to their respective event handlers?</span></span> <span data-ttu-id="dd983-258">前の例で確認した `_mediator` オブジェクトは何ですか。</span><span class="sxs-lookup"><span data-stu-id="dd983-258">What's the `_mediator` object you see in the previous example?</span></span> <span data-ttu-id="dd983-259">それはイベントとそのイベント ハンドラーの間をマップするために使用する手法および成果物に関係します。</span><span class="sxs-lookup"><span data-stu-id="dd983-259">It has to do with the techniques and artifacts you use to map between events and their event handlers.</span></span>

### <a name="the-domain-event-dispatcher-mapping-from-events-to-event-handlers"></a><span data-ttu-id="dd983-260">ドメイン イベント ディスパッチャー: イベントからイベント ハンドラーへのマッピング</span><span class="sxs-lookup"><span data-stu-id="dd983-260">The domain event dispatcher: mapping from events to event handlers</span></span>

<span data-ttu-id="dd983-261">イベントをディスパッチまたは発行できるようになったら、関連するすべてのハンドラーがイベントを入手し、イベントに基づいて副作用を処理できるように、イベントを発行する何らかの種類の成果物が必要です。</span><span class="sxs-lookup"><span data-stu-id="dd983-261">Once you're able to dispatch or publish the events, you need some kind of artifact that will publish the event, so that every related handler can get it and process side effects based on that event.</span></span>

<span data-ttu-id="dd983-262">1 つの方法は、おそらくインメモリ イベントではなくサービス バスに基づく、実際のメッセージング システムまたはイベント バスです。</span><span class="sxs-lookup"><span data-stu-id="dd983-262">One approach is a real messaging system or even an event bus, possibly based on a service bus as opposed to in-memory events.</span></span> <span data-ttu-id="dd983-263">ただし、最初のケースでは、必要なのは同じプロセス内でこれらのイベントを処理することだけなので (つまり、同じドメイン内および同じアプリケーション レイヤー内)、実際のメッセージングを使うのは過剰です。</span><span class="sxs-lookup"><span data-stu-id="dd983-263">However, for the first case, real messaging would be overkill for processing domain events, since you just need to process those events within the same process (that is, within the same domain and application layer).</span></span>

<span data-ttu-id="dd983-264">イベントを複数のイベント ハンドラーにマップするもう 1 つの方法は、イベントをディスパッチする場所を動的に推論できるように、IoC コンテナーへの型の登録を使うことです。</span><span class="sxs-lookup"><span data-stu-id="dd983-264">Another way to map events to multiple event handlers is by using types registration in an IoC container so you can dynamically infer where to dispatch the events.</span></span> <span data-ttu-id="dd983-265">つまり、特定のイベント ハンドラーで必要な特定のイベントを知る必要があります。</span><span class="sxs-lookup"><span data-stu-id="dd983-265">In other words, you need to know what event handlers need to get a specific event.</span></span> <span data-ttu-id="dd983-266">図 7-16 はこのアプローチの概要です。</span><span class="sxs-lookup"><span data-stu-id="dd983-266">Figure 7-16 shows a simplified approach for this approach.</span></span>

![イベントをイベント ハンドラーに関連付ける目的で依存関係挿入を使用できます。これは MediatR で使用されるアプローチです。](./media/image17.png)

<span data-ttu-id="dd983-268">**図 7-16**。</span><span class="sxs-lookup"><span data-stu-id="dd983-268">**Figure 7-16**.</span></span> <span data-ttu-id="dd983-269">IoC を使ったドメイン イベント ディスパッチャー</span><span class="sxs-lookup"><span data-stu-id="dd983-269">Domain event dispatcher using IoC</span></span>

<span data-ttu-id="dd983-270">このアプローチを実装するためのすべての仕組みと成果物を自分で作成することができます。</span><span class="sxs-lookup"><span data-stu-id="dd983-270">You can build all the plumbing and artifacts to implement that approach by yourself.</span></span> <span data-ttu-id="dd983-271">ただし、[MediatR](https://github.com/jbogard/MediatR) のようなライブラリを使うこともできます。このライブラリは内部で IoC コンテナーを使っています。</span><span class="sxs-lookup"><span data-stu-id="dd983-271">However, you can also use available libraries like [MediatR](https://github.com/jbogard/MediatR) that uses your IoC container under the covers.</span></span> <span data-ttu-id="dd983-272">したがって、定義済みのインターフェイスとメディエーター オブジェクトのパブリッシュ/ディスパッチ メソッドを直接使うことができます。</span><span class="sxs-lookup"><span data-stu-id="dd983-272">You can therefore directly use the predefined interfaces and the mediator object’s publish/dispatch methods.</span></span>

<span data-ttu-id="dd983-273">コードでは最初に、イベント ハンドラーの型を IoC コンテナーに登録する必要があります。次に示す [eShopOnContainers の Ordering マイクロサービス](https://github.com/dotnet-architecture/eShopOnContainers/blob/dev/src/Services/Ordering/Ordering.API/Infrastructure/AutofacModules/MediatorModule.cs)での例をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="dd983-273">In code, you first need to register the event handler types in your IoC container, as shown in the following example at [eShopOnContainers Ordering microservice](https://github.com/dotnet-architecture/eShopOnContainers/blob/dev/src/Services/Ordering/Ordering.API/Infrastructure/AutofacModules/MediatorModule.cs):</span></span>

```csharp
public class MediatorModule : Autofac.Module
{
    protected override void Load(ContainerBuilder builder)
    {
        // Other registrations ...
        // Register the DomainEventHandler classes (they implement IAsyncNotificationHandler<>)
        // in assembly holding the Domain Events
        builder.RegisterAssemblyTypes(typeof(ValidateOrAddBuyerAggregateWhenOrderStartedDomainEventHandler)
                                       .GetTypeInfo().Assembly)
                                         .AsClosedTypesOf(typeof(IAsyncNotificationHandler<>));
        // Other registrations ...
    }
}
```

<span data-ttu-id="dd983-274">このコードは最初に、いずれかのハンドラーを保持するアセンブリを探すことによってドメイン イベント ハンドラーが含まれているアセンブリを特定します (typeof(ValidateOrAddBuyerAggregateWhenXxxx) を使いますが、他のイベント ハンドラーを選んでアセンブリを探してもかまいません)。</span><span class="sxs-lookup"><span data-stu-id="dd983-274">The code first identifies the assembly that contains the domain event handlers by locating the assembly that holds any of the handlers (using typeof(ValidateOrAddBuyerAggregateWhenXxxx), but you could have chosen any other event handler to locate the assembly).</span></span> <span data-ttu-id="dd983-275">すべてのイベント ハンドラーは IAsyncNotificationHandler インターフェイスを実装しているので、次に、それらの型だけを検索してすべてのイベント ハンドラーを登録します。</span><span class="sxs-lookup"><span data-stu-id="dd983-275">Since all the event handlers implement the IAsyncNotificationHandler interface, the code then just searches for those types and registers all the event handlers.</span></span>

### <a name="how-to-subscribe-to-domain-events"></a><span data-ttu-id="dd983-276">ドメイン イベントをサブスクライブする方法</span><span class="sxs-lookup"><span data-stu-id="dd983-276">How to subscribe to domain events</span></span>

<span data-ttu-id="dd983-277">MediatR を使うときは、次のコードでわかるように、INotificationHandler インターフェイスのジェネリック パラメーターで提供されるイベントの型を、各イベント ハンドラーで使う必要があります。</span><span class="sxs-lookup"><span data-stu-id="dd983-277">When you use MediatR, each event handler must use an event type that is provided on the generic parameter of the INotificationHandler interface, as you can see in the following code:</span></span>

```csharp
public class ValidateOrAddBuyerAggregateWhenOrderStartedDomainEventHandler
  : IAsyncNotificationHandler<OrderStartedDomainEvent>
```

<span data-ttu-id="dd983-278">イベントとイベント ハンドラーの間の関係 (これはサブスクリプションと考えることができます) に基づいて、MediatR の成果物は各イベントのすべてのイベント ハンドラーを検出し、それらの各イベント ハンドラーをトリガーすることができます。</span><span class="sxs-lookup"><span data-stu-id="dd983-278">Based on the relationship between event and event handler, which can be considered the subscription, the MediatR artifact can discover all the event handlers for each event and trigger each one of those event handlers.</span></span>

### <a name="how-to-handle-domain-events"></a><span data-ttu-id="dd983-279">ドメイン イベントを処理する方法</span><span class="sxs-lookup"><span data-stu-id="dd983-279">How to handle domain events</span></span>

<span data-ttu-id="dd983-280">最後になりますが、通常、イベント ハンドラーでは、インフラストラクチャのリポジトリを使って必要な他の集約を取得して副作用のドメイン ロジックを実行する、アプリケーション レイヤーのコードを実装します。</span><span class="sxs-lookup"><span data-stu-id="dd983-280">Finally, the event handler usually implements application layer code that uses infrastructure repositories to obtain the required additional aggregates and to execute side-effect domain logic.</span></span> <span data-ttu-id="dd983-281">次に示すのは、[eShopOnContainers のドメイン イベント ハンドラーのコード](https://github.com/dotnet-architecture/eShopOnContainers/blob/dev/src/Services/Ordering/Ordering.API/Application/DomainEventHandlers/OrderStartedEvent/ValidateOrAddBuyerAggregateWhenOrderStartedDomainEventHandler.cs)での実装の例です。</span><span class="sxs-lookup"><span data-stu-id="dd983-281">The following [domain event handler code at eShopOnContainers](https://github.com/dotnet-architecture/eShopOnContainers/blob/dev/src/Services/Ordering/Ordering.API/Application/DomainEventHandlers/OrderStartedEvent/ValidateOrAddBuyerAggregateWhenOrderStartedDomainEventHandler.cs), shows an implementation example.</span></span>

```csharp
public class ValidateOrAddBuyerAggregateWhenOrderStartedDomainEventHandler
                   : INotificationHandler<OrderStartedDomainEvent>
{
    private readonly ILoggerFactory _logger;
    private readonly IBuyerRepository<Buyer> _buyerRepository;
    private readonly IIdentityService _identityService;

    public ValidateOrAddBuyerAggregateWhenOrderStartedDomainEventHandler(
        ILoggerFactory logger,
        IBuyerRepository<Buyer> buyerRepository,
        IIdentityService identityService)
    {
        // ...Parameter validations...
    }

    public async Task Handle(OrderStartedDomainEvent orderStartedEvent)
    {
        var cardTypeId = (orderStartedEvent.CardTypeId != 0) ? orderStartedEvent.CardTypeId : 1;        
        var userGuid = _identityService.GetUserIdentity();
        var buyer = await _buyerRepository.FindAsync(userGuid);
        bool buyerOriginallyExisted = (buyer == null) ? false : true;

        if (!buyerOriginallyExisted)
        {
            buyer = new Buyer(userGuid);
        }

        buyer.VerifyOrAddPaymentMethod(cardTypeId,
                                       $"Payment Method on {DateTime.UtcNow}",
                                       orderStartedEvent.CardNumber,
                                       orderStartedEvent.CardSecurityNumber,
                                       orderStartedEvent.CardHolderName,
                                       orderStartedEvent.CardExpiration,
                                       orderStartedEvent.Order.Id);

        var buyerUpdated = buyerOriginallyExisted ? _buyerRepository.Update(buyer) 
                                                                      : _buyerRepository.Add(buyer);

        await _buyerRepository.UnitOfWork
                .SaveEntitiesAsync();

        // Logging code using buyerUpdated info, etc.
    }
}
```

<span data-ttu-id="dd983-282">このドメイン イベント ハンドラーのコードは、インフラストラクチャ永続レイヤーについて次のセクションで説明するように、インフラストラクチャのリポジトリを使っているので、アプリケーション レイヤーのコードと考えられます。</span><span class="sxs-lookup"><span data-stu-id="dd983-282">The previous domain event handler code is considered application layer code because it uses infrastructure repositories, as explained in the next section on the infrastructure-persistence layer.</span></span> <span data-ttu-id="dd983-283">イベント ハンドラーは、他のインフラストラクチャ コンポーネントを使うこともできます。</span><span class="sxs-lookup"><span data-stu-id="dd983-283">Event handlers could also use other infrastructure components.</span></span>

#### <a name="domain-events-can-generate-integration-events-to-be-published-outside-of-the-microservice-boundaries"></a><span data-ttu-id="dd983-284">ドメイン イベントは、マイクロサービス境界の外部で発行される統合イベントを生成できます。</span><span class="sxs-lookup"><span data-stu-id="dd983-284">Domain events can generate integration events to be published outside of the microservice boundaries</span></span>

<span data-ttu-id="dd983-285">最後に、重要なこととして、複数のマイクロサービスにイベントを伝達することが必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="dd983-285">Finally, it's important to mention that you might sometimes want to propagate events across multiple microservices.</span></span> <span data-ttu-id="dd983-286">この伝達は統合イベントであり、任意の特定のドメイン イベント ハンドラーからイベント バスを介して発行できます。</span><span class="sxs-lookup"><span data-stu-id="dd983-286">That propagation is an integration event, and it could be published through an event bus from any specific domain event handler.</span></span>

## <a name="conclusions-on-domain-events"></a><span data-ttu-id="dd983-287">ドメイン イベントのまとめ</span><span class="sxs-lookup"><span data-stu-id="dd983-287">Conclusions on domain events</span></span>

<span data-ttu-id="dd983-288">説明したように、ドメイン内での変更の副作用を明示的に実装するには、ドメイン イベントを使います。</span><span class="sxs-lookup"><span data-stu-id="dd983-288">As stated, use domain events to explicitly implement side effects of changes within your domain.</span></span> <span data-ttu-id="dd983-289">DDD の用語では、1 つ以上の集約に副作用を明示的に実装するには、ドメイン イベントを使います。</span><span class="sxs-lookup"><span data-stu-id="dd983-289">To use DDD terminology, use domain events to explicitly implement side effects across one or multiple aggregates.</span></span> <span data-ttu-id="dd983-290">さらに、スケーラビリティを向上させ、データベース ロックの影響を小さくする必要がある場合は、同じドメイン内の集約の間の最終的な整合性を使います。</span><span class="sxs-lookup"><span data-stu-id="dd983-290">Additionally, and for better scalability and less impact on database locks, use eventual consistency between aggregates within the same domain.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="dd983-291">その他の技術情報</span><span class="sxs-lookup"><span data-stu-id="dd983-291">Additional resources</span></span>

- <span data-ttu-id="dd983-292">**Greg Young。ドメイン イベントとは**</span><span class="sxs-lookup"><span data-stu-id="dd983-292">**Greg Young. What is a Domain Event?**</span></span> \
  <https://cqrs.files.wordpress.com/2010/11/cqrs_documents.pdf#page=25>

- <span data-ttu-id="dd983-293">**Jan Stenberg。ドメイン イベントと最終的な整合性** </span><span class="sxs-lookup"><span data-stu-id="dd983-293">**Jan Stenberg. Domain Events and Eventual Consistency** </span></span>\
  <https://www.infoq.com/news/2015/09/domain-events-consistency>

- <span data-ttu-id="dd983-294">**Jimmy Bogard。よりよいドメイン イベント パターン** </span><span class="sxs-lookup"><span data-stu-id="dd983-294">**Jimmy Bogard. A better domain events pattern** </span></span>\
  <https://lostechies.com/jimmybogard/2014/05/13/a-better-domain-events-pattern/>

- <span data-ttu-id="dd983-295">**Vaughn Vernon。効果的な集約設計パート II:集約処理の連携** </span><span class="sxs-lookup"><span data-stu-id="dd983-295">**Vaughn Vernon. Effective Aggregate Design Part II: Making Aggregates Work Together** </span></span>\
  [https://dddcommunity.org/wp-content/uploads/files/pdf\_articles/Vernon\_2011\_2.pdf](https://dddcommunity.org/wp-content/uploads/files/pdf_articles/Vernon_2011_2.pdf)

- <span data-ttu-id="dd983-296">**Jimmy Bogard。ドメインの強化:ドメイン イベント** </span><span class="sxs-lookup"><span data-stu-id="dd983-296">**Jimmy Bogard. Strengthening your domain: Domain Events** </span></span>\
  <https://lostechies.com/jimmybogard/2010/04/08/strengthening-your-domain-domain-events/>

- <span data-ttu-id="dd983-297">**Tony Truong。ドメイン イベント パターンの例** </span><span class="sxs-lookup"><span data-stu-id="dd983-297">**Tony Truong. Domain Events Pattern Example** </span></span>\
  <https://www.tonytruong.net/domain-events-pattern-example/>

- <span data-ttu-id="dd983-298">**Udi Dahan。完全にカプセル化されたドメイン モデルを作成する方法** </span><span class="sxs-lookup"><span data-stu-id="dd983-298">**Udi Dahan. How to create fully encapsulated Domain Models** </span></span>\
  <http://udidahan.com/2008/02/29/how-to-create-fully-encapsulated-domain-models/>

- <span data-ttu-id="dd983-299">**Udi Dahan。ドメイン イベント – テイク 2** </span><span class="sxs-lookup"><span data-stu-id="dd983-299">**Udi Dahan. Domain Events – Take 2** </span></span>\
  <http://udidahan.com/2008/08/25/domain-events-take-2/>

- <span data-ttu-id="dd983-300">**Udi Dahan。ドメイン イベント – 救済** </span><span class="sxs-lookup"><span data-stu-id="dd983-300">**Udi Dahan. Domain Events – Salvation** </span></span>\
  <http://udidahan.com/2009/06/14/domain-events-salvation/>

- <span data-ttu-id="dd983-301">**Jan Kronquist。ドメイン イベントを発行しないで返す**</span><span class="sxs-lookup"><span data-stu-id="dd983-301">**Jan Kronquist. Don't publish Domain Events, return them!**</span></span> \
  <https://blog.jayway.com/2013/06/20/dont-publish-domain-events-return-them/>

- <span data-ttu-id="dd983-302">**Cesar de la Torre。DDD およびマイクロサービス アーキテクチャでのドメイン イベントとDDD の統合イベントとマイクロサービス アーキテクチャ** </span><span class="sxs-lookup"><span data-stu-id="dd983-302">**Cesar de la Torre. Domain Events vs. Integration Events in DDD and microservices architectures** </span></span>\
  <https://devblogs.microsoft.com/cesardelatorre/domain-events-vs-integration-events-in-domain-driven-design-and-microservices-architectures/>

>[!div class="step-by-step"]
><span data-ttu-id="dd983-303">[前へ](client-side-validation.md)
>[次へ](infrastructure-persistence-layer-design.md)</span><span class="sxs-lookup"><span data-stu-id="dd983-303">[Previous](client-side-validation.md)
[Next](infrastructure-persistence-layer-design.md)</span></span>
