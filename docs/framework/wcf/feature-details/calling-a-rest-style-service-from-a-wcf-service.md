---
title: WCF サービスからの REST スタイル サービスの呼び出し
description: スコープを作成し、そのスコープから REST スタイルのサービスを呼び出すことによって、WCF サービスが REST スタイルのサービスで適切なコンテキストを使用するようにする方法について説明します。
ms.date: 03/30/2017
ms.assetid: 77df81d8-7f53-4daf-8d2d-bf7996e94d5a
ms.openlocfilehash: 15f468923cf55feb85e7aeca1a2cc5e38050d665
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/23/2020
ms.locfileid: "85245298"
---
# <a name="calling-a-rest-style-service-from-a-wcf-service"></a><span data-ttu-id="9a354-103">WCF サービスからの REST スタイル サービスの呼び出し</span><span class="sxs-lookup"><span data-stu-id="9a354-103">Calling a REST-style service from a WCF service</span></span>

<span data-ttu-id="9a354-104">標準の (SOAP ベース) WCF サービスから REST スタイルのサービスを呼び出すとき、受信要求に関する情報を含んでいるサービス メソッドの操作コンテキストは、送信要求が使用するコンテキストをオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="9a354-104">When calling a REST-style service from a regular (SOAP-based) WCF service, the operation context on the service method (which contains information about the incoming request) overrides the context which should be used by the outgoing request.</span></span> <span data-ttu-id="9a354-105">これにより、HTTP GET 要求は HTTP POST 要求に変更されます。</span><span class="sxs-lookup"><span data-stu-id="9a354-105">This causes HTTP GET requests to change to HTTP POST requests.</span></span> <span data-ttu-id="9a354-106">WCF サービスが正しいコンテキストを使用して REST スタイルのサービスを呼び出すには、新しい <xref:System.ServiceModel.OperationContextScope> を作成し、操作コンテキスト スコープ内から REST スタイルのサービスを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="9a354-106">To force the WCF service to use the right context for calling the REST-style service, create a new <xref:System.ServiceModel.OperationContextScope> and call the REST-style service from inside the operation context scope.</span></span> <span data-ttu-id="9a354-107">このトピックでは、この手法を説明する簡単なサンプルを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="9a354-107">This topic will describe how to create a simple sample that illustrates this technique.</span></span>

## <a name="define-the-rest-style-service-contract"></a><span data-ttu-id="9a354-108">REST スタイルのサービス コントラクトを定義する</span><span class="sxs-lookup"><span data-stu-id="9a354-108">Define the REST-style service contract</span></span>

<span data-ttu-id="9a354-109">簡単な REST スタイルのサービス コントラクトを定義する:</span><span class="sxs-lookup"><span data-stu-id="9a354-109">Define a simple  REST-style service contract:</span></span>

```csharp
[ServiceContract]
public interface IRestInterface
{
    [OperationContract, WebGet]
    int Add(int x, int y);

    [OperationContract, WebGet]
    string Echo(string input);
}
```

## <a name="implement-the-rest-style-service-contract"></a><span data-ttu-id="9a354-110">REST スタイルのサービス コントラクトを実装する</span><span class="sxs-lookup"><span data-stu-id="9a354-110">Implement the REST-style service contract</span></span>

<span data-ttu-id="9a354-111">REST スタイルのサービス コントラクトを実装する:</span><span class="sxs-lookup"><span data-stu-id="9a354-111">Implement the REST-style service contract:</span></span>

```csharp
public class RestService : IRestInterface
{
    public int Add(int x, int y)
    {
        return x + y;
    }

    public string Echo(string input)
    {
        return input;
    }
}
```

## <a name="define-the-wcf-service-contract"></a><span data-ttu-id="9a354-112">WCF サービス コントラクトを定義する</span><span class="sxs-lookup"><span data-stu-id="9a354-112">Define the WCF service contract</span></span>

<span data-ttu-id="9a354-113">REST スタイルのサービスの呼び出しに使用する WCF サービス コントラクトを定義する:</span><span class="sxs-lookup"><span data-stu-id="9a354-113">Define a WCF service contract  that will be used to call the REST-style service:</span></span>

```csharp
[ServiceContract]
public interface INormalInterface
{
    [OperationContract]
    int CallAdd(int x, int y);

    [OperationContract]
    string CallEcho(string input);
}
```

## <a name="implement-the-wcf-service-contract"></a><span data-ttu-id="9a354-114">WCF サービス コントラクトを実装する</span><span class="sxs-lookup"><span data-stu-id="9a354-114">Implement the WCF service contract</span></span>

<span data-ttu-id="9a354-115">WCF サービス コントラクトを実装する:</span><span class="sxs-lookup"><span data-stu-id="9a354-115">Implement the WCF service contract:</span></span>

```csharp
public class NormalService : INormalInterface
{
    static MyRestClient client = new MyRestClient(RestServiceBaseAddress);
    public int CallAdd(int x, int y)
    {
        return client.Add(x, y);
    }

    public string CallEcho(string input)
    {
        return client.Echo(input);
    }
}
```

## <a name="create-the-client-proxy-for-the-rest-style-service"></a><span data-ttu-id="9a354-116">REST スタイルのサービスのクライアント プロキシを作成する</span><span class="sxs-lookup"><span data-stu-id="9a354-116">Create the client proxy for the REST-style service</span></span>

<span data-ttu-id="9a354-117">を使用して <xref:System.ServiceModel.ClientBase%601> クライアントプロキシを実装します。</span><span class="sxs-lookup"><span data-stu-id="9a354-117">Using <xref:System.ServiceModel.ClientBase%601> to implement the client proxy.</span></span> <span data-ttu-id="9a354-118">呼び出される各メソッドで、新しい <xref:System.ServiceModel.OperationContextScope> が作成され、操作の呼び出しに使用されます。</span><span class="sxs-lookup"><span data-stu-id="9a354-118">For each method called, a new <xref:System.ServiceModel.OperationContextScope> is created and used to call the operation.</span></span>

```csharp
public class MyRestClient : ClientBase<IRestInterface>, IRestInterface
{
    public MyRestClient(string address)
        : base(new WebHttpBinding(), new EndpointAddress(address))
    {
        this.Endpoint.Behaviors.Add(new WebHttpBehavior());
    }

    public int Add(int x, int y)
    {
        using (new OperationContextScope(this.InnerChannel))
        {
            return base.Channel.Add(x, y);
        }
    }

    public string Echo(string input)
    {
        using (new OperationContextScope(this.InnerChannel))
        {
            return base.Channel.Echo(input);
        }
    }
}
```

## <a name="host-and-call-the-services"></a><span data-ttu-id="9a354-119">サービスをホストし、呼び出す</span><span class="sxs-lookup"><span data-stu-id="9a354-119">Host and call the services</span></span>

<span data-ttu-id="9a354-120">コンソール アプリケーションの両方のサービスをホストし、必要なエンドポイントと動作を追加します。</span><span class="sxs-lookup"><span data-stu-id="9a354-120">Host both services in a console app, adding the needed endpoints and behaviors.</span></span> <span data-ttu-id="9a354-121">次に、通常の WCF サービスを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="9a354-121">And then call the regular WCF service:</span></span>

```csharp
public static void Main()
{
    ServiceHost restHost = new ServiceHost(typeof(RestService), new Uri(RestServiceBaseAddress));
    restHost.AddServiceEndpoint(typeof(IRestInterface), new WebHttpBinding(), "").Behaviors.Add(new WebHttpBehavior());
    restHost.Open();

    ServiceHost normalHost = new ServiceHost(typeof(NormalService), new Uri(NormalServiceBaseAddress));
    normalHost.AddServiceEndpoint(typeof(INormalInterface), new BasicHttpBinding(), "");
    normalHost.Open();

    Console.WriteLine("Hosts opened");

    ChannelFactory<INormalInterface> factory = new ChannelFactory<INormalInterface>(new BasicHttpBinding(), new EndpointAddress(NormalServiceBaseAddress));
    INormalInterface proxy = factory.CreateChannel();

    Console.WriteLine(proxy.CallAdd(123, 456));
    Console.WriteLine(proxy.CallEcho("Hello world"));
}
```

## <a name="complete-code-listing"></a><span data-ttu-id="9a354-122">完全なコード リスト</span><span class="sxs-lookup"><span data-stu-id="9a354-122">Complete code listing</span></span>

<span data-ttu-id="9a354-123">このトピックで実装されるサンプルの完全なコード リストを次に示します。</span><span class="sxs-lookup"><span data-stu-id="9a354-123">The following is a complete listing of the sample implemented in this topic:</span></span>

```csharp
public class CallingRESTSample
{
    static readonly string RestServiceBaseAddress = "http://" + Environment.MachineName + ":8008/Service";
    static readonly string NormalServiceBaseAddress = "http://" + Environment.MachineName + ":8000/Service";

    [ServiceContract]
    public interface IRestInterface
    {
        [OperationContract, WebGet]
        int Add(int x, int y);
        [OperationContract, WebGet]
        string Echo(string input);
    }

    [ServiceContract]
    public interface INormalInterface
    {
        [OperationContract]
        int CallAdd(int x, int y);
        [OperationContract]
        string CallEcho(string input);
    }

    public class RestService : IRestInterface
    {
        public int Add(int x, int y)
        {
            return x + y;
        }

        public string Echo(string input)
        {
            return input;
        }
    }

    public class MyRestClient : ClientBase<IRestInterface>, IRestInterface
    {
        public MyRestClient(string address)
            : base(new WebHttpBinding(), new EndpointAddress(address))
        {
            this.Endpoint.Behaviors.Add(new WebHttpBehavior());
        }

        public int Add(int x, int y)
        {
            using (new OperationContextScope(this.InnerChannel))
            {
                return base.Channel.Add(x, y);
            }
        }

        public string Echo(string input)
        {
            using (new OperationContextScope(this.InnerChannel))
            {
                return base.Channel.Echo(input);
            }
        }
    }

    public class NormalService : INormalInterface
    {
        static MyRestClient client = new MyRestClient(RestServiceBaseAddress);
        public int CallAdd(int x, int y)
        {
            return client.Add(x, y);
        }

        public string CallEcho(string input)
        {
            return client.Echo(input);
        }
    }

    public static void Main()
    {
        ServiceHost restHost = new ServiceHost(typeof(RestService), new Uri(RestServiceBaseAddress));
        restHost.AddServiceEndpoint(typeof(IRestInterface), new WebHttpBinding(), "").Behaviors.Add(new WebHttpBehavior());
        restHost.Open();

        ServiceHost normalHost = new ServiceHost(typeof(NormalService), new Uri(NormalServiceBaseAddress));
        normalHost.AddServiceEndpoint(typeof(INormalInterface), new BasicHttpBinding(), "");
        normalHost.Open();

        Console.WriteLine("Hosts opened");

        ChannelFactory<INormalInterface> factory = new ChannelFactory<INormalInterface>(new BasicHttpBinding(), new EndpointAddress(NormalServiceBaseAddress));
        INormalInterface proxy = factory.CreateChannel();

        Console.WriteLine(proxy.CallAdd(123, 456));
        Console.WriteLine(proxy.CallEcho("Hello world"));
    }
}
```

## <a name="see-also"></a><span data-ttu-id="9a354-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="9a354-124">See also</span></span>

- [<span data-ttu-id="9a354-125">方法: 基本的な WCF Web HTTP サービスを作成する</span><span class="sxs-lookup"><span data-stu-id="9a354-125">How to: Create a Basic WCF Web HTTP Service</span></span>](how-to-create-a-basic-wcf-web-http-service.md)
- [<span data-ttu-id="9a354-126">WCF Web HTTP プログラミング オブジェクト モデル</span><span class="sxs-lookup"><span data-stu-id="9a354-126">WCF Web HTTP Programming Object Model</span></span>](wcf-web-http-programming-object-model.md)
