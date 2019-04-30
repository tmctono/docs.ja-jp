---
title: 標準エンドポイントの使用
ms.date: 03/30/2017
ms.assetid: ecd6a62f-9619-4778-a497-6f888087a9ea
ms.openlocfilehash: 4ef0714acad12db1414e34fbb476b4ae7d1d9fb2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62006336"
---
# <a name="usage-of-standard-endpoints"></a><span data-ttu-id="a1cf2-102">標準エンドポイントの使用</span><span class="sxs-lookup"><span data-stu-id="a1cf2-102">Usage of Standard Endpoints</span></span>

<span data-ttu-id="a1cf2-103">このサンプルでは、サービスの構成ファイルでの標準エンドポイントの使用方法を示します。</span><span class="sxs-lookup"><span data-stu-id="a1cf2-103">This sample demonstrates how to use standard endpoints in service configuration files.</span></span> <span data-ttu-id="a1cf2-104">標準エンドポイントでは、単一のプロパティを使用してアドレス、バインディング、およびコントラクトの組み合わせをそのエンドポイントに関連付けられている追加のプロパティで記述することで、エンドポイントの定義を簡単に行うことができます。</span><span class="sxs-lookup"><span data-stu-id="a1cf2-104">A standard endpoint allows the user to simplify endpoint definitions by using a single property to describe an address, binding and contract combination with additional properties associated to it.</span></span> <span data-ttu-id="a1cf2-105">このサンプルでは、カスタムの標準エンドポイントを定義して実装する方法、およびエンドポイントの特定のプロパティを定義する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="a1cf2-105">This sample demonstrates how to define and implement a custom standard endpoint and how to define specific properties in the endpoint.</span></span>

## <a name="sample-details"></a><span data-ttu-id="a1cf2-106">サンプルの詳細</span><span class="sxs-lookup"><span data-stu-id="a1cf2-106">Sample Details</span></span>

<span data-ttu-id="a1cf2-107">サービス エンドポイントは、アドレス、バインディング、およびコントラクトの 3 つのパラメーターを指定して指定できます。</span><span class="sxs-lookup"><span data-stu-id="a1cf2-107">Service endpoints can be specified by supplying three parameters: address, binding and contract.</span></span> <span data-ttu-id="a1cf2-108">指定できるその他のパラメーターには、動作構成、ヘッダー、リッスン URI などがあります。</span><span class="sxs-lookup"><span data-stu-id="a1cf2-108">Other parameters that can be supplied include behavior configuration, headers, listen URI, and so on.</span></span> <span data-ttu-id="a1cf2-109">アドレス、バインディング、およびコントラクトのいずれかまたはすべてに、変更できない値が含まれている場合があります。</span><span class="sxs-lookup"><span data-stu-id="a1cf2-109">In some cases, any or all of addresses, bindings and contracts have values that cannot change.</span></span> <span data-ttu-id="a1cf2-110">このような理由から、標準エンドポイントを使用できます。</span><span class="sxs-lookup"><span data-stu-id="a1cf2-110">For this reason, it is possible to use standard endpoints.</span></span> <span data-ttu-id="a1cf2-111">このようなエンドポイントの例として、メタデータ交換エンドポイントや探索エンドポイントがあります。</span><span class="sxs-lookup"><span data-stu-id="a1cf2-111">Some examples of such endpoints include metadata exchange endpoints and discovery endpoints.</span></span> <span data-ttu-id="a1cf2-112">また、標準エンドポイントでは、固定された性質の情報を提供したり、独自の標準エンドポイントを作成したりしなくても、サービス エンドポイントを構成できるため、ユーザビリティが向上します。たとえば、適切な既定の値のセットを指定し、構成ファイルの詳細を削減してユーザビリティを向上させることができます。</span><span class="sxs-lookup"><span data-stu-id="a1cf2-112">Standard endpoints also improve usability by allowing configuration of service endpoints without having to provide information of a fixed nature or to create their own standard endpoints, for example to improve usability by supplying a reasonable set of default values and thus reducing the verbosity of configuration files.</span></span>

<span data-ttu-id="a1cf2-113">このサンプルは、2 つの標準エンドポイントを定義するサービスおよびサービスと通信するクライアントの 2 つのプロジェクトで構成されています。</span><span class="sxs-lookup"><span data-stu-id="a1cf2-113">This sample consists of two projects: the service that defines two standard endpoints and the client that communicates with the service.</span></span> <span data-ttu-id="a1cf2-114">構成ファイルでサービスの標準エンドポイントを定義する方法を次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="a1cf2-114">The way the standard endpoints are defined for the service in the configuration file is show in the following example.</span></span>

```xml
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
  <system.serviceModel>
    <extensions>
      <endpointExtensions>
        <add name="customEndpoint" type="Microsoft.Samples.StandardEndpoints.CustomEndpointCollectionElement, service" />
      </endpointExtensions>
    </extensions>
    <services>
      <service name="Microsoft.Samples.StandardEndpoints.CalculatorService">
        <endpoint address="http://localhost:8000/Samples/Service.svc/customEndpoint" contract="Microsoft.Samples.StandardEndpoints.ICalculator" kind="customEndpoint" />
        <endpoint kind="mexEndpoint" />
      </service>
    </services>
    <behaviors>
      <serviceBehaviors>
        <behavior>
          <serviceMetadata httpGetEnabled="True"/>
        </behavior>
      </serviceBehaviors>
    </behaviors>
    <standardEndpoints>
      <customEndpoint>
        <standardEndpoint property="True" />
      </customEndpoint>
    </standardEndpoints>
  </system.serviceModel>
</configuration>
```

<span data-ttu-id="a1cf2-115">サービスに定義されている最初のエンドポイントは、`customEndpoint` の一種で、その定義については、`<standardEndpoints>` セクションで確認できます。このセクションでは、プロパティ `property` に `true` の値が指定されています。</span><span class="sxs-lookup"><span data-stu-id="a1cf2-115">The first endpoint defined for the service is of kind `customEndpoint`, whose definition can be seen in the `<standardEndpoints>` section, in which the property `property` is given the value `true`.</span></span> <span data-ttu-id="a1cf2-116">これは、新しいプロパティでカスタマイズされたエンドポイントの例です。</span><span class="sxs-lookup"><span data-stu-id="a1cf2-116">This is the case of an endpoint customized with a new property.</span></span> <span data-ttu-id="a1cf2-117">2 つ目のエンドポイントはメタデータ エンドポイントを表します。このエンドポイントでは、アドレス、バインディング、およびコントラクトの値が固定されています。</span><span class="sxs-lookup"><span data-stu-id="a1cf2-117">The second endpoint corresponds to a metadata endpoint, in which the values for address, binding and contract are fixed.</span></span>

<span data-ttu-id="a1cf2-118">標準エンドポイント要素を定義するには、`StandardEndpointElement` から派生するクラスを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a1cf2-118">To define the standard endpoint element, a class that derives from `StandardEndpointElement` must be created.</span></span> <span data-ttu-id="a1cf2-119">このサンプルでは、`CustomEndpointElement` クラスは、次の例のように定義されています。</span><span class="sxs-lookup"><span data-stu-id="a1cf2-119">In the case of this sample, the `CustomEndpointElement` class has been defined as shown in the following example.</span></span>

```csharp
public class CustomEndpointElement : StandardEndpointElement
{
    public bool Property
    {
        get { return (bool)base["property"]; }
        set { base["property"] = value; }
    }

    protected override ConfigurationPropertyCollection Properties
    {
        get
        {
            ConfigurationPropertyCollection properties = base.Properties;
            properties.Add(new ConfigurationProperty("property", typeof(bool), false, ConfigurationPropertyOptions.None));
            return properties;
        }
    }

    protected override Type EndpointType
    {
        get { return typeof(CustomEndpoint); }
    }

    protected override ServiceEndpoint CreateServiceEndpoint(ContractDescription contract)
    {
        return new CustomEndpoint();
    }

    protected override void OnApplyConfiguration(ServiceEndpoint endpoint, ServiceEndpointElement serviceEndpointElement)
    {
        CustomEndpoint customEndpoint = (CustomEndpoint)endpoint;
        customEndpoint.Property = this.Property;
    }

    protected override void OnApplyConfiguration(ServiceEndpoint endpoint, ChannelEndpointElement channelEndpointElement)
    {
        CustomEndpoint customEndpoint = (CustomEndpoint)endpoint;
        customEndpoint.Property = this.Property;
    }

    protected override void OnInitializeAndValidate(ServiceEndpointElement serviceEndpointElement)
    {
    }

    protected override void OnInitializeAndValidate(ChannelEndpointElement channelEndpointElement)
    {
    }
}
```

<span data-ttu-id="a1cf2-120">`CreateServiceEndpoint` 関数で、`CustomEndpoint` オブジェクトが作成されます。</span><span class="sxs-lookup"><span data-stu-id="a1cf2-120">In the `CreateServiceEndpoint` function, a `CustomEndpoint` object is created.</span></span> <span data-ttu-id="a1cf2-121">その定義は、次の例に示されます。</span><span class="sxs-lookup"><span data-stu-id="a1cf2-121">Its definition is shown in the following example:</span></span>

```csharp
public class CustomEndpoint : ServiceEndpoint
{
    public CustomEndpoint()
        : this(string.Empty)
    {
    }

    public CustomEndpoint(string address)
        : this(address, ContractDescription.GetContract(typeof(ICalculator)))
    {
    }

    public CustomEndpoint(string address, ContractDescription contract)
        : base(contract)
    {
        this.Binding = new BasicHttpBinding();
        this.IsSystemEndpoint = false;
    }

    public bool Property
    {
        get;
        set;
    }
}
```

 <span data-ttu-id="a1cf2-122">サービスとクライアントとの間で通信を実行するために、クライアントでサービスに対するサービス参照が作成されます。</span><span class="sxs-lookup"><span data-stu-id="a1cf2-122">To perform the communication between service and client, a service reference is created in the client to the service.</span></span> <span data-ttu-id="a1cf2-123">このサンプルをビルドして実行した場合、サービスが実行されて、クライアントはそのサービスと通信します。</span><span class="sxs-lookup"><span data-stu-id="a1cf2-123">When the sample is built and executed, the service executes and the client communicates with it.</span></span> <span data-ttu-id="a1cf2-124">サービスが変更されるたびに、サービス参照を更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a1cf2-124">Note that the service reference should be updated every time there is some change in the service.</span></span>

#### <a name="to-use-this-sample"></a><span data-ttu-id="a1cf2-125">このサンプルを使用するには</span><span class="sxs-lookup"><span data-stu-id="a1cf2-125">To use this sample</span></span>

1. <span data-ttu-id="a1cf2-126">Visual Studio 2012 を使用して、StandardEndpoints.sln ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="a1cf2-126">Using Visual Studio 2012, open the StandardEndpoints.sln file.</span></span>

2. <span data-ttu-id="a1cf2-127">複数のプロジェクトを起動できるようにします。</span><span class="sxs-lookup"><span data-stu-id="a1cf2-127">Enable multiple projects to start up.</span></span>

    1. <span data-ttu-id="a1cf2-128">**ソリューション エクスプ ローラー**標準エンドポイント ソリューションを右クリックし、**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="a1cf2-128">In **Solution Explorer**, right-click the Standard Endpoints solution and then select **Properties**.</span></span>

    2. <span data-ttu-id="a1cf2-129">**共通プロパティ**を選択します**スタートアップ プロジェクト**、 をクリックし、**マルチ スタートアップ プロジェクト**します。</span><span class="sxs-lookup"><span data-stu-id="a1cf2-129">In **Common Properties**, select **Startup Project**, and then click **Multiple Startup Projects**.</span></span>

    3. <span data-ttu-id="a1cf2-130">サービス プロジェクトをリストの先頭に移動、**アクション**設定**開始**します。</span><span class="sxs-lookup"><span data-stu-id="a1cf2-130">Move the Service project to the beginning of the list, with the **Action** set to **Start**.</span></span>

    4. <span data-ttu-id="a1cf2-131">も、サービス プロジェクトの後に、クライアント プロジェクトに移動、**アクション**設定**開始**します。</span><span class="sxs-lookup"><span data-stu-id="a1cf2-131">Move the Client project after the Service project, also with the **Action** set to **Start**.</span></span>

         <span data-ttu-id="a1cf2-132">これで、Client プロジェクトは Service プロジェクトの後に実行されます。</span><span class="sxs-lookup"><span data-stu-id="a1cf2-132">This specifies that the Client project is executed after the Service project.</span></span>

3. <span data-ttu-id="a1cf2-133">ソリューションを実行するには、F5 キーを押します。</span><span class="sxs-lookup"><span data-stu-id="a1cf2-133">To run the solution, press F5.</span></span>

> [!NOTE]
> <span data-ttu-id="a1cf2-134">次の手順が機能しない場合は、環境が設定されている正しく、次の手順を使用してを確認します。</span><span class="sxs-lookup"><span data-stu-id="a1cf2-134">If these steps don't work, then make sure that your environment has been properly set up, using the following steps:</span></span>
>
> 1. <span data-ttu-id="a1cf2-135">実行したことを確認、 [Windows Communication Foundation サンプルの 1 回限りのセットアップ手順](one-time-setup-procedure-for-the-wcf-samples.md)します。</span><span class="sxs-lookup"><span data-stu-id="a1cf2-135">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>
> 2. <span data-ttu-id="a1cf2-136">ソリューションをビルドする手順については、 [Windows Communication Foundation サンプルのビルド](building-the-samples.md)します。</span><span class="sxs-lookup"><span data-stu-id="a1cf2-136">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>
> 3. <span data-ttu-id="a1cf2-137">1 つまたは複数のコンピューター構成でサンプルを実行する手順については、 [Windows Communication Foundation サンプルの実行](running-the-samples.md)します。</span><span class="sxs-lookup"><span data-stu-id="a1cf2-137">To run the sample in a single or multiple computer configurations, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a1cf2-138">サンプルは、既にコンピューターにインストールされている場合があります。</span><span class="sxs-lookup"><span data-stu-id="a1cf2-138">The samples may already be installed on your machine.</span></span> <span data-ttu-id="a1cf2-139">続行する前に、次の (既定の) ディレクトリを確認してください。</span><span class="sxs-lookup"><span data-stu-id="a1cf2-139">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="a1cf2-140">このディレクトリが存在しない場合に移動[Windows Communication Foundation (WCF) と .NET Framework 4 向けの Windows Workflow Foundation (WF) サンプル](https://go.microsoft.com/fwlink/?LinkId=150780)すべて Windows Communication Foundation (WCF) をダウンロードして[!INCLUDE[wf1](../../../../includes/wf1-md.md)]サンプル。</span><span class="sxs-lookup"><span data-stu-id="a1cf2-140">If this directory doesn't exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="a1cf2-141">このサンプルは、次のディレクトリに格納されます。</span><span class="sxs-lookup"><span data-stu-id="a1cf2-141">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\StandardEndpoints`
