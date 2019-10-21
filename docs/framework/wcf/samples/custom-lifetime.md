---
title: カスタムの有効期間
ms.date: 08/20/2018
ms.assetid: 52806c07-b91c-48fe-b992-88a41924f51f
ms.openlocfilehash: be6013d568e3625c5eac7e0c145db7df1c6917e3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62003160"
---
# <a name="custom-lifetime"></a><span data-ttu-id="936ad-102">カスタムの有効期間</span><span class="sxs-lookup"><span data-stu-id="936ad-102">Custom lifetime</span></span>

<span data-ttu-id="936ad-103">このサンプルでは、共有の WCF サービスのインスタンス用のカスタムの有効期間サービスを提供する Windows Communication Foundation (WCF) 拡張機能の記述方法を示します。</span><span class="sxs-lookup"><span data-stu-id="936ad-103">This sample demonstrates how to write a Windows Communication Foundation (WCF) extension to provide custom lifetime services for shared WCF service instances.</span></span>

> [!NOTE]
> <span data-ttu-id="936ad-104">このサンプルのセットアップ手順とビルド手順については、この記事の最後を参照してください。</span><span class="sxs-lookup"><span data-stu-id="936ad-104">The setup procedure and build instructions for this sample are located at the end of this article.</span></span>

## <a name="shared-instancing"></a><span data-ttu-id="936ad-105">共有インスタンス化</span><span class="sxs-lookup"><span data-stu-id="936ad-105">Shared instancing</span></span>

<span data-ttu-id="936ad-106">WCF には、サービス インスタンス用のいくつかのインスタンス化モードが用意されています。</span><span class="sxs-lookup"><span data-stu-id="936ad-106">WCF offers several instancing modes for your service instances.</span></span> <span data-ttu-id="936ad-107">この記事で説明する共有インスタンス化モードでは、複数のチャネルでのサービス インスタンスを共有する方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="936ad-107">The shared instancing mode covered in this article provides a way to share a service instance between multiple channels.</span></span> <span data-ttu-id="936ad-108">クライアントは、サービスのファクトリ メソッドにお問い合わせくださいし、の通信を開始する新しいチャネルを作成します。</span><span class="sxs-lookup"><span data-stu-id="936ad-108">Clients can contact a factory method in the service and create a new channel to start communication.</span></span> <span data-ttu-id="936ad-109">次のコード スニペットは、クライアント アプリケーションが既存のサービス インスタンスに新しいチャネルを作成する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="936ad-109">The following code snippet shows how a client application creates a new channel to an existing service instance:</span></span>

```csharp
// Create a header for the shared instance id
MessageHeader shareableInstanceContextHeader = MessageHeader.CreateHeader(
        CustomHeader.HeaderName,
        CustomHeader.HeaderNamespace,
        Guid.NewGuid().ToString());

// Create the channel factory
ChannelFactory<IEchoService> channelFactory =
    new ChannelFactory<IEchoService>("echoservice");

// Create the first channel
IEchoService proxy = channelFactory.CreateChannel();

// Call an operation to create shared service instance
using (new OperationContextScope((IClientChannel)proxy))
{
    OperationContext.Current.OutgoingMessageHeaders.Add(shareableInstanceContextHeader);
    Console.WriteLine("Service returned: " + proxy.Echo("Apple"));
}

((IChannel)proxy).Close();

// Create the second channel
IEchoService proxy2 = channelFactory.CreateChannel();

// Call an operation using the same header that will reuse the shared service instance
using (new OperationContextScope((IClientChannel)proxy2))
{
    OperationContext.Current.OutgoingMessageHeaders.Add(shareableInstanceContextHeader);
    Console.WriteLine("Service returned: " + proxy2.Echo("Apple"));
}
```

<span data-ttu-id="936ad-110">他のインスタンス化モードとは異なり、共有インスタンス化モードでは、独特の方法でサービス インスタンスを解放します。</span><span class="sxs-lookup"><span data-stu-id="936ad-110">Unlike other instancing modes, the shared instancing mode has a unique way of releasing the service instances.</span></span> <span data-ttu-id="936ad-111">すべてのチャネルが閉じられたときに、既定で、 <xref:System.ServiceModel.InstanceContext>、WCF サービスのランタイムをかどうかを確認しますサービス<xref:System.ServiceModel.InstanceContextMode>するように構成<xref:System.ServiceModel.InstanceContextMode.PerCall>または<xref:System.ServiceModel.InstanceContextMode.PerSession>、場合にそのため、インスタンスを解放し、リソースを要求します。</span><span class="sxs-lookup"><span data-stu-id="936ad-111">By default, when all the channels are closed for an <xref:System.ServiceModel.InstanceContext>, the WCF service runtime checks to see if the service <xref:System.ServiceModel.InstanceContextMode> is configured to <xref:System.ServiceModel.InstanceContextMode.PerCall> or <xref:System.ServiceModel.InstanceContextMode.PerSession>, and if so releases the instance and claims the resources.</span></span> <span data-ttu-id="936ad-112">場合、カスタム<xref:System.ServiceModel.Dispatcher.IInstanceContextProvider>が使用されている WCF を呼び出す、<xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A>インスタンスをリリースする前に、プロバイダーの実装のメソッド。</span><span class="sxs-lookup"><span data-stu-id="936ad-112">If a custom <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> is being used, WCF invokes the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> method of the provider implementation before releasing the instance.</span></span> <span data-ttu-id="936ad-113">場合<xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A>返します`true`、それ以外の場合、インスタンスが解放、<xref:System.ServiceModel.Dispatcher.IInstanceContextProvider>に通知するため、実装は、`Dispatcher`のコールバック メソッドを使用してアイドル状態です。</span><span class="sxs-lookup"><span data-stu-id="936ad-113">If <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> returns `true` the instance is released, otherwise the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> implementation is responsible for notifying the `Dispatcher` of the idle state by using a callback method.</span></span> <span data-ttu-id="936ad-114">これは、呼び出すことで、<xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.NotifyIdle%2A>プロバイダーのメソッド。</span><span class="sxs-lookup"><span data-stu-id="936ad-114">This is done by calling the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.NotifyIdle%2A> method of the provider.</span></span>

<span data-ttu-id="936ad-115">このサンプルでは、解放を延期する方法、 <xref:System.ServiceModel.InstanceContext> 20 秒のアイドル状態のタイムアウトを設定しています。</span><span class="sxs-lookup"><span data-stu-id="936ad-115">This sample demonstrates how you can delay releasing the <xref:System.ServiceModel.InstanceContext> with an idle timeout of 20 seconds.</span></span>

## <a name="extending-the-instancecontext"></a><span data-ttu-id="936ad-116">InstanceContext の拡張</span><span class="sxs-lookup"><span data-stu-id="936ad-116">Extending the InstanceContext</span></span>

<span data-ttu-id="936ad-117">WCF では、<xref:System.ServiceModel.InstanceContext>サービス インスタンスの間のリンクは、および`Dispatcher`します。</span><span class="sxs-lookup"><span data-stu-id="936ad-117">In WCF, <xref:System.ServiceModel.InstanceContext> is the link between the service instance and the `Dispatcher`.</span></span> <span data-ttu-id="936ad-118">WCF の拡張可能オブジェクト パターンを使用して新しい状態または動作を追加することで、このランタイム コンポーネントを拡張することができます。</span><span class="sxs-lookup"><span data-stu-id="936ad-118">WCF allows you to extend this runtime component by adding new state or behavior by using its extensible object pattern.</span></span> <span data-ttu-id="936ad-119">拡張可能オブジェクト パターンは、またはオブジェクトに新しい状態の機能を追加するか、新しい機能を既存のランタイム クラスを拡張する、WCF で使用されます。</span><span class="sxs-lookup"><span data-stu-id="936ad-119">The extensible object pattern is used in WCF to either extend existing runtime classes with new functionality or to add new state features to an object.</span></span> <span data-ttu-id="936ad-120">拡張可能オブジェクト パターンには、<xref:System.ServiceModel.IExtensibleObject%601>、<xref:System.ServiceModel.IExtension%601>、および <xref:System.ServiceModel.IExtensionCollection%601> の 3 つのインターフェイスがあります。</span><span class="sxs-lookup"><span data-stu-id="936ad-120">There are three interfaces in the extensible object pattern: <xref:System.ServiceModel.IExtensibleObject%601>, <xref:System.ServiceModel.IExtension%601>, and <xref:System.ServiceModel.IExtensionCollection%601>.</span></span>

<span data-ttu-id="936ad-121"><xref:System.ServiceModel.IExtensibleObject%601>インターフェイスが、機能をカスタマイズする拡張機能を許可するオブジェクトによって実装されます。</span><span class="sxs-lookup"><span data-stu-id="936ad-121">The <xref:System.ServiceModel.IExtensibleObject%601> interface is implemented by objects to allow extensions that customize their functionality.</span></span>

<span data-ttu-id="936ad-122"><xref:System.ServiceModel.IExtension%601> インターフェイスは、`T` 型のクラスの拡張が可能なオブジェクトによって実装されます。</span><span class="sxs-lookup"><span data-stu-id="936ad-122">The <xref:System.ServiceModel.IExtension%601> interface is implemented by objects that can be extensions of classes of type `T`.</span></span>

<span data-ttu-id="936ad-123">最後に、<xref:System.ServiceModel.IExtensionCollection%601>インターフェイスのコレクションである<xref:System.ServiceModel.IExtension%601>の実装を取得するためにできる実装<xref:System.ServiceModel.IExtension%601>をその型。</span><span class="sxs-lookup"><span data-stu-id="936ad-123">And finally, the <xref:System.ServiceModel.IExtensionCollection%601> interface is a collection of <xref:System.ServiceModel.IExtension%601> implementations that allows for retrieving an implementation of <xref:System.ServiceModel.IExtension%601> by their type.</span></span>

<span data-ttu-id="936ad-124">そのため、拡張するには、 <xref:System.ServiceModel.InstanceContext>、実装する必要があります、<xref:System.ServiceModel.IExtension%601>インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="936ad-124">Therefore, in order to extend the <xref:System.ServiceModel.InstanceContext>, you must implement the <xref:System.ServiceModel.IExtension%601> interface.</span></span> <span data-ttu-id="936ad-125">このサンプル プロジェクトで、`CustomLeaseExtension`クラスには、この実装が含まれています。</span><span class="sxs-lookup"><span data-stu-id="936ad-125">In this sample project, the `CustomLeaseExtension` class contains this implementation.</span></span>

```csharp
class CustomLeaseExtension : IExtension<InstanceContext>
{
}
```

<span data-ttu-id="936ad-126"><xref:System.ServiceModel.IExtension%601> インターフェイスには、<xref:System.ServiceModel.IExtension%601.Attach%2A> と <xref:System.ServiceModel.IExtension%601.Detach%2A> の 2 つのメソッドが含まれています。</span><span class="sxs-lookup"><span data-stu-id="936ad-126">The <xref:System.ServiceModel.IExtension%601> interface has two methods <xref:System.ServiceModel.IExtension%601.Attach%2A> and <xref:System.ServiceModel.IExtension%601.Detach%2A>.</span></span> <span data-ttu-id="936ad-127">名前が示すように、これらの 2 つのメソッドは、ランタイムが <xref:System.ServiceModel.InstanceContext> クラスのインスタンスに拡張機能を関連付けるときと関連付けを解除するときに呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="936ad-127">As their names imply, these two methods are called when the runtime attaches and detaches the extension to an instance of the <xref:System.ServiceModel.InstanceContext> class.</span></span> <span data-ttu-id="936ad-128">このサンプルでは、`Attach` メソッドを使用して、拡張機能の現在のインスタンスに属する <xref:System.ServiceModel.InstanceContext> オブジェクトを追跡します。</span><span class="sxs-lookup"><span data-stu-id="936ad-128">In this sample, the `Attach` method is used to keep track of the <xref:System.ServiceModel.InstanceContext> object that belongs to the current instance of the extension.</span></span>

```csharp
InstanceContext owner;

public void Attach(InstanceContext owner)
{
    this.owner = owner;
}
```

<span data-ttu-id="936ad-129">また、有効期間の延長をサポートするには、必要な実装を拡張機能に追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="936ad-129">In addition, you must add the necessary implementation to the extension to provide the extended lifetime support.</span></span> <span data-ttu-id="936ad-130">そのため、`ICustomLease`インターフェイスは、目的のメソッドで宣言されで実装されて、`CustomLeaseExtension`クラス。</span><span class="sxs-lookup"><span data-stu-id="936ad-130">Therefore, the `ICustomLease` interface is declared with the desired methods and is implemented in the `CustomLeaseExtension` class.</span></span>

```csharp
interface ICustomLease
{
    bool IsIdle { get; }
    InstanceContextIdleCallback Callback { get; set; }
}

class CustomLeaseExtension : IExtension<InstanceContext>, ICustomLease
{
}
```

<span data-ttu-id="936ad-131">WCF を呼び出すときに、<xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A>メソッドで、<xref:System.ServiceModel.Dispatcher.IInstanceContextProvider>実装では、この呼び出しにルーティングされます、<xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A>のメソッド、`CustomLeaseExtension`します。</span><span class="sxs-lookup"><span data-stu-id="936ad-131">When WCF invokes the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> method in the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> implementation, this call is routed to the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> method of the `CustomLeaseExtension`.</span></span> <span data-ttu-id="936ad-132">次に、`CustomLeaseExtension`して、そのプライベート状態を確認するかどうか、<xref:System.ServiceModel.InstanceContext>がアイドル状態です。</span><span class="sxs-lookup"><span data-stu-id="936ad-132">Then, the `CustomLeaseExtension` checks its private state to see whether the <xref:System.ServiceModel.InstanceContext> is idle.</span></span> <span data-ttu-id="936ad-133">返すかどうかは、アイドル状態が、`true`します。</span><span class="sxs-lookup"><span data-stu-id="936ad-133">If it is idle, it returns `true`.</span></span> <span data-ttu-id="936ad-134">それ以外の場合は、延長された指定の有効期間のタイマーが開始されます。</span><span class="sxs-lookup"><span data-stu-id="936ad-134">Otherwise, it starts a timer for a specified amount of extended lifetime.</span></span>

```csharp
public bool IsIdle
{
  get
  {
    lock (thisLock)
    {
      if (isIdle)
      {
        return true;
      }
      else
      {
        StartTimer();
        return false;
      }
    }
  }
}
```

<span data-ttu-id="936ad-135">タイマーの`Elapsed`イベント ディスパッチャーでコールバック関数は、別のクリーンアップ サイクルを開始するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="936ad-135">In the timer’s `Elapsed` event, the callback function in the Dispatcher is called in order to start another clean-up cycle.</span></span>

```csharp
void idleTimer_Elapsed(object sender, ElapsedEventArgs args)
{
    lock (thisLock)
    {
        StopTimer();
        isIdle = true;
        Utility.WriteMessageToConsole(
            ResourceHelper.GetString("MsgLeaseExpired"));
        callback(owner);
    }
}
```

<span data-ttu-id="936ad-136">アイドル状態に移行中のインスタンスに新しいメッセージが届いたときに、実行中のタイマーを更新する方法はありません。</span><span class="sxs-lookup"><span data-stu-id="936ad-136">There's no way to renew the running timer when a new message arrives for the instance being moved to the idle state.</span></span>

<span data-ttu-id="936ad-137">このサンプルでは、<xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> メソッドの呼び出しを受け取って <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> にルーティングするために `CustomLeaseExtension` を実装します。</span><span class="sxs-lookup"><span data-stu-id="936ad-137">The sample implements <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> to intercept the calls to the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> method and route them to the `CustomLeaseExtension`.</span></span> <span data-ttu-id="936ad-138"><xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> 実装は、`CustomLifetimeLease` クラスに含まれています。</span><span class="sxs-lookup"><span data-stu-id="936ad-138">The <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> implementation is contained in `CustomLifetimeLease` class.</span></span> <span data-ttu-id="936ad-139"><xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> WCF がサービス インスタンスを解放するときにメソッドが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="936ad-139">The <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> method is invoked when WCF is about to release the service instance.</span></span> <span data-ttu-id="936ad-140">ただし、ServiceBehavior の `ISharedSessionInstance` コレクションに存在する特定の <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> 実装のインスタンスは 1 つだけです。</span><span class="sxs-lookup"><span data-stu-id="936ad-140">However, there is only one instance of a particular `ISharedSessionInstance` implementation in the ServiceBehavior’s <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> collection.</span></span> <span data-ttu-id="936ad-141">つまり、知る必要が場合の方法はありません、 <xref:System.ServiceModel.InstanceContext> WCF チェック時に、<xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A>メソッド。</span><span class="sxs-lookup"><span data-stu-id="936ad-141">This means there's no way of knowing if the <xref:System.ServiceModel.InstanceContext> is closed at the time WCF checks the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> method.</span></span> <span data-ttu-id="936ad-142">そのため、このサンプルはスレッドへの要求をシリアル化するロックを使用、<xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A>メソッド。</span><span class="sxs-lookup"><span data-stu-id="936ad-142">Therefore, this sample uses thread locking to serialize requests to the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> method.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="936ad-143">シリアル化はアプリケーションのパフォーマンスに大きな影響を及ぼす可能性があるので、スレッド ロックは使用しないことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="936ad-143">Using thread locking is not a recommended approach because serialization can severely affect the performance of your application.</span></span>

<span data-ttu-id="936ad-144">プライベート メンバー フィールドが使用される、`CustomLifetimeLease`アイドル状態を追跡するためにクラスし、によって返される、<xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A>メソッド。</span><span class="sxs-lookup"><span data-stu-id="936ad-144">A private member field is used in the `CustomLifetimeLease` class to track the idle state and is returned by the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> method.</span></span> <span data-ttu-id="936ad-145">毎回、<xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A>メソッドが呼び出される、`isIdle`フィールドが返され、リセット`false`します。</span><span class="sxs-lookup"><span data-stu-id="936ad-145">Each time the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> method is called, the `isIdle` field is returned and reset to `false`.</span></span>  <span data-ttu-id="936ad-146">ディスパッチャーが `false` メソッドを呼び出すようにするには、この値を <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.NotifyIdle%2A> に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="936ad-146">It is essential to set this value to `false` in order to make sure the Dispatcher calls the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.NotifyIdle%2A> method.</span></span>

```csharp
public bool IsIdle(InstanceContext instanceContext)
{
    get
    {
        lock (thisLock)
        {
            //...
            bool idleCopy = isIdle;
            isIdle = false;
            return idleCopy;
        }
    }
}
```

<span data-ttu-id="936ad-147">場合、<xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A?displayProperty=nameWithType>メソッドを返します。 `false`、ディスパッチャーを使用して、コールバック関数の登録、<xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.NotifyIdle%2A>メソッド。</span><span class="sxs-lookup"><span data-stu-id="936ad-147">If the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A?displayProperty=nameWithType> method returns `false`, the Dispatcher registers a callback function by using the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.NotifyIdle%2A> method.</span></span> <span data-ttu-id="936ad-148">このメソッドは、解放される <xref:System.ServiceModel.InstanceContext> への参照を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="936ad-148">This method receives a reference to the <xref:System.ServiceModel.InstanceContext> being released.</span></span> <span data-ttu-id="936ad-149">そのため、サンプル コードを問い合わせることができます、`ICustomLease`拡張子を入力し、確認、`ICustomLease.IsIdle`拡張状態プロパティ。</span><span class="sxs-lookup"><span data-stu-id="936ad-149">Therefore, the sample code can query the `ICustomLease` type extension and check the `ICustomLease.IsIdle` property in the extended state.</span></span>

```csharp
public void NotifyIdle(InstanceContextIdleCallback callback,
            InstanceContext instanceContext)
{
    lock (thisLock)
    {
       ICustomLease customLease =
           instanceContext.Extensions.Find<ICustomLease>();
       customLease.Callback = callback;
       isIdle = customLease.IsIdle;
       if (isIdle)
       {
             callback(instanceContext);
       }
    }
}
```

<span data-ttu-id="936ad-150">前に、`ICustomLease.IsIdle`プロパティをチェックして、コールバック プロパティは、これには、重要な設定が必要`CustomLeaseExtension`アイドル状態になったときに、ディスパッチャーに通知します。</span><span class="sxs-lookup"><span data-stu-id="936ad-150">Before the `ICustomLease.IsIdle` property is checked, the Callback property needs to be set as this is essential for `CustomLeaseExtension` to notify the Dispatcher when it becomes idle.</span></span> <span data-ttu-id="936ad-151">`ICustomLease.IsIdle` が `true` を返す場合は、`isIdle` プライベート メンバーが `CustomLifetimeLease` で単に `true` に設定され、コールバック メソッドが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="936ad-151">If `ICustomLease.IsIdle` returns `true`, the `isIdle` private member is simply set in `CustomLifetimeLease` to `true` and calls the callback method.</span></span> <span data-ttu-id="936ad-152">コードでは、ロックを保持しているために、他のスレッドは、このプライベート メンバーの値を変更できません。</span><span class="sxs-lookup"><span data-stu-id="936ad-152">Because the code holds a lock, other threads can't change the value of this private member.</span></span> <span data-ttu-id="936ad-153">次回ディスパッチャーを呼び出すと、<xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A?displayProperty=nameWithType>を返します`true`でき、ディスパッチャーのインスタンスを解放します。</span><span class="sxs-lookup"><span data-stu-id="936ad-153">And the next time Dispatcher calls the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A?displayProperty=nameWithType>, it returns `true` and lets Dispatcher release the instance.</span></span>

<span data-ttu-id="936ad-154">これでカスタム拡張機能の基礎が完成したので、この拡張機能をサービス モデルにフックする必要があります。</span><span class="sxs-lookup"><span data-stu-id="936ad-154">Now that the groundwork for the custom extension is completed, it has to be hooked up to the service model.</span></span> <span data-ttu-id="936ad-155">フックするため、`CustomLeaseExtension`を実装、 <xref:System.ServiceModel.InstanceContext>、WCF の提供、<xref:System.ServiceModel.Dispatcher.IInstanceContextInitializer>のブートス トラップを実行するインターフェイス<xref:System.ServiceModel.InstanceContext>。</span><span class="sxs-lookup"><span data-stu-id="936ad-155">To hook up the `CustomLeaseExtension` implementation to the <xref:System.ServiceModel.InstanceContext>, WCF provides the <xref:System.ServiceModel.Dispatcher.IInstanceContextInitializer> interface to perform the bootstrapping of <xref:System.ServiceModel.InstanceContext>.</span></span> <span data-ttu-id="936ad-156">このサンプルでは、`CustomLeaseInitializer` クラスでこのインターフェイスを実装し、`CustomLeaseExtension` のインスタンスを唯一のメソッドの初期化から得られる <xref:System.ServiceModel.InstanceContext.Extensions%2A> コレクションに追加します。</span><span class="sxs-lookup"><span data-stu-id="936ad-156">In the sample, the `CustomLeaseInitializer` class implements this interface and adds an instance of `CustomLeaseExtension` to the <xref:System.ServiceModel.InstanceContext.Extensions%2A> collection from the only method initialization.</span></span> <span data-ttu-id="936ad-157">このメソッドは、<xref:System.ServiceModel.InstanceContext> の初期化中にディスパッチャーによって呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="936ad-157">This method is called by Dispatcher while initializing the <xref:System.ServiceModel.InstanceContext>.</span></span>

```csharp
public void InitializeInstanceContext(InstanceContext instanceContext,
    System.ServiceModel.Channels.Message message, IContextChannel channel)

    //...

    IExtension<InstanceContext> customLeaseExtension =
        new CustomLeaseExtension(timeout, headerId);
    instanceContext.Extensions.Add(customLeaseExtension);
}
```

 <span data-ttu-id="936ad-158">最後に、<xref:System.ServiceModel.Dispatcher.IInstanceContextProvider>実装にフックされる、サービス モデルを使用して、<xref:System.ServiceModel.Description.IServiceBehavior>実装します。</span><span class="sxs-lookup"><span data-stu-id="936ad-158">Finally the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> implementation is hooked up to the service model by using the <xref:System.ServiceModel.Description.IServiceBehavior> implementation.</span></span> <span data-ttu-id="936ad-159">この実装は、`CustomLeaseTimeAttribute` クラスに配置されています。また、<xref:System.Attribute> 基本クラスから派生してこの動作を属性として公開します。</span><span class="sxs-lookup"><span data-stu-id="936ad-159">This implementation is placed in the `CustomLeaseTimeAttribute` class and it also derives from the <xref:System.Attribute> base class to expose this behavior as an attribute.</span></span>

```csharp
public void ApplyDispatchBehavior(ServiceDescription description,
           ServiceHostBase serviceHostBase)
{
    CustomLifetimeLease customLease = new CustomLifetimeLease(timeout);

    foreach (ChannelDispatcherBase cdb in serviceHostBase.ChannelDispatchers)
    {
        ChannelDispatcher cd = cdb as ChannelDispatcher;

        if (cd != null)
        {
            foreach (EndpointDispatcher ed in cd.Endpoints)
            {
                ed.DispatchRuntime.InstanceContextProvider = customLease;
            }
        }
    }
}
```

<span data-ttu-id="936ad-160">この動作は、`CustomLeaseTime` 属性を使用して注釈を付けることにより、サンプル サービス クラスに追加できます。</span><span class="sxs-lookup"><span data-stu-id="936ad-160">This behavior can be added to a sample service class by annotating it with the `CustomLeaseTime` attribute.</span></span>

```csharp
[CustomLeaseTime(Timeout = 20000)]
public class EchoService : IEchoService
{
  //…
}
```

<span data-ttu-id="936ad-161">このサンプルを実行すると、操作要求と応答がサービスとクライアントの両方のコンソール ウィンドウに表示されます。</span><span class="sxs-lookup"><span data-stu-id="936ad-161">When you run the sample, the operation requests and responses are displayed in both the service and client console windows.</span></span> <span data-ttu-id="936ad-162">どちらかのコンソールで Enter キーを押すと、サービスとクライアントがどちらもシャットダウンされます。</span><span class="sxs-lookup"><span data-stu-id="936ad-162">Press ENTER in each console window to shut down the service and client.</span></span>

### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="936ad-163">サンプルをセットアップ、ビルド、および実行するには</span><span class="sxs-lookup"><span data-stu-id="936ad-163">To set up, build, and run the sample</span></span>

1. <span data-ttu-id="936ad-164">実行したことを確認、 [Windows Communication Foundation サンプルの 1 回限りのセットアップ手順](one-time-setup-procedure-for-the-wcf-samples.md)します。</span><span class="sxs-lookup"><span data-stu-id="936ad-164">Ensure that you've performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>

2. <span data-ttu-id="936ad-165">ソリューションの C# 版または Visual Basic .NET 版をビルドするには、「 [Windows Communication Foundation サンプルのビルド](building-the-samples.md)」の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="936ad-165">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>

3. <span data-ttu-id="936ad-166">1 つまたは複数コンピュータ構成では、サンプルを実行する手順については、 [Windows Communication Foundation サンプルの実行](running-the-samples.md)します。</span><span class="sxs-lookup"><span data-stu-id="936ad-166">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="936ad-167">サンプルは、既にコンピューターにインストールされている場合があります。</span><span class="sxs-lookup"><span data-stu-id="936ad-167">The samples may already be installed on your machine.</span></span> <span data-ttu-id="936ad-168">続行する前に、次の (既定の) ディレクトリを確認してください。</span><span class="sxs-lookup"><span data-stu-id="936ad-168">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="936ad-169">このディレクトリが存在しない場合に移動[Windows Communication Foundation (WCF) と .NET Framework 4 向けの Windows Workflow Foundation (WF) サンプル](https://go.microsoft.com/fwlink/?LinkId=150780)すべて Windows Communication Foundation (WCF) をダウンロードして[!INCLUDE[wf1](../../../../includes/wf1-md.md)]サンプル。</span><span class="sxs-lookup"><span data-stu-id="936ad-169">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="936ad-170">このサンプルは、次のディレクトリに格納されます。</span><span class="sxs-lookup"><span data-stu-id="936ad-170">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Instancing\Lifetime`
