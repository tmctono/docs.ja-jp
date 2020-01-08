---
title: 匿名クライアントを使用したトランスポートセキュリティ
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 056653a5-384e-4a02-ae3c-1b0157d2ccb4
ms.openlocfilehash: c3e44c87dfa70ac3a7acc5a83ac596efc22b6155
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/25/2019
ms.locfileid: "75344758"
---
# <a name="transport-security-with-an-anonymous-client"></a><span data-ttu-id="0c3b5-102">匿名クライアントを使用したトランスポートセキュリティ</span><span class="sxs-lookup"><span data-stu-id="0c3b5-102">Transport security with an anonymous client</span></span>

<span data-ttu-id="0c3b5-103">この Windows Communication Foundation (WCF) シナリオでは、トランスポートセキュリティ (HTTPS) を使用して、機密性と整合性を確保します。</span><span class="sxs-lookup"><span data-stu-id="0c3b5-103">This Windows Communication Foundation (WCF) scenario uses transport security (HTTPS) to ensure confidentiality and integrity.</span></span> <span data-ttu-id="0c3b5-104">サーバーは SSL (Secure Sockets Layer) 証明書で認証される必要があり、クライアントはサーバーの証明書を信頼する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0c3b5-104">The server must be authenticated with a Secure Sockets Layer (SSL) certificate, and the clients must trust the server's certificate.</span></span> <span data-ttu-id="0c3b5-105">クライアントを認証する機構はないため、匿名となります。</span><span class="sxs-lookup"><span data-stu-id="0c3b5-105">The client is not authenticated by any mechanism and is, therefore, anonymous.</span></span>

<span data-ttu-id="0c3b5-106">サンプルアプリケーションについては、「 [WS トランスポートセキュリティ](../samples/ws-transport-security.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0c3b5-106">For a sample application, see [WS Transport Security](../samples/ws-transport-security.md).</span></span> <span data-ttu-id="0c3b5-107">トランスポートセキュリティの詳細については、「[トランスポートセキュリティの概要](transport-security-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0c3b5-107">For more information about transport security, see [Transport Security Overview](transport-security-overview.md).</span></span>

<span data-ttu-id="0c3b5-108">サービスで証明書を使用する方法の詳細については、「[証明書の操作](working-with-certificates.md)」および「[方法: SSL 証明書を使用してポートを構成する](how-to-configure-a-port-with-an-ssl-certificate.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0c3b5-108">For more information about using a certificate with a service, see [Working with Certificates](working-with-certificates.md) and [How to: Configure a Port with an SSL Certificate](how-to-configure-a-port-with-an-ssl-certificate.md).</span></span>

![匿名クライアントを利用したトランスポート セキュリティの使用](./media/8fa2e931-0cfb-4aaa-9272-91d652b85d8d.gif)

|<span data-ttu-id="0c3b5-110">特徴</span><span class="sxs-lookup"><span data-stu-id="0c3b5-110">Characteristic</span></span>|<span data-ttu-id="0c3b5-111">説明</span><span class="sxs-lookup"><span data-stu-id="0c3b5-111">Description</span></span>|
|--------------------|-----------------|
|<span data-ttu-id="0c3b5-112">セキュリティ モード</span><span class="sxs-lookup"><span data-stu-id="0c3b5-112">Security Mode</span></span>|<span data-ttu-id="0c3b5-113">Transport</span><span class="sxs-lookup"><span data-stu-id="0c3b5-113">Transport</span></span>|
|<span data-ttu-id="0c3b5-114">相互運用性</span><span class="sxs-lookup"><span data-stu-id="0c3b5-114">Interoperability</span></span>|<span data-ttu-id="0c3b5-115">既存の Web サービスとクライアントを使用する</span><span class="sxs-lookup"><span data-stu-id="0c3b5-115">With existing Web services and clients</span></span>|
|<span data-ttu-id="0c3b5-116">認証 (サーバー)</span><span class="sxs-lookup"><span data-stu-id="0c3b5-116">Authentication (Server)</span></span><br /><br /> <span data-ttu-id="0c3b5-117">認証 (クライアント)</span><span class="sxs-lookup"><span data-stu-id="0c3b5-117">Authentication (Client)</span></span>|<span data-ttu-id="0c3b5-118">○</span><span class="sxs-lookup"><span data-stu-id="0c3b5-118">Yes</span></span><br /><br /> <span data-ttu-id="0c3b5-119">アプリケーションレベル (WCF サポートなし)</span><span class="sxs-lookup"><span data-stu-id="0c3b5-119">Application level (no WCF support)</span></span>|
|<span data-ttu-id="0c3b5-120">整合性</span><span class="sxs-lookup"><span data-stu-id="0c3b5-120">Integrity</span></span>|<span data-ttu-id="0c3b5-121">○</span><span class="sxs-lookup"><span data-stu-id="0c3b5-121">Yes</span></span>|
|<span data-ttu-id="0c3b5-122">機密性</span><span class="sxs-lookup"><span data-stu-id="0c3b5-122">Confidentiality</span></span>|<span data-ttu-id="0c3b5-123">○</span><span class="sxs-lookup"><span data-stu-id="0c3b5-123">Yes</span></span>|
|<span data-ttu-id="0c3b5-124">Transport</span><span class="sxs-lookup"><span data-stu-id="0c3b5-124">Transport</span></span>|<span data-ttu-id="0c3b5-125">HTTPS</span><span class="sxs-lookup"><span data-stu-id="0c3b5-125">HTTPS</span></span>|
|<span data-ttu-id="0c3b5-126">バインディング</span><span class="sxs-lookup"><span data-stu-id="0c3b5-126">Binding</span></span>|<xref:System.ServiceModel.WSHttpBinding>|

## <a name="service"></a><span data-ttu-id="0c3b5-127">サービス</span><span class="sxs-lookup"><span data-stu-id="0c3b5-127">Service</span></span>

<span data-ttu-id="0c3b5-128">次のコードと構成は、別々に実行します。</span><span class="sxs-lookup"><span data-stu-id="0c3b5-128">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="0c3b5-129">以下のいずれかを実行します。</span><span class="sxs-lookup"><span data-stu-id="0c3b5-129">Do one of the following:</span></span>

- <span data-ttu-id="0c3b5-130">構成を使用せずに、コードを使用してスタンドアロン サービスを作成します。</span><span class="sxs-lookup"><span data-stu-id="0c3b5-130">Create a stand-alone service using the code with no configuration.</span></span>

- <span data-ttu-id="0c3b5-131">提供された構成を使用してサービスを作成しますが、エンドポイントを定義しません。</span><span class="sxs-lookup"><span data-stu-id="0c3b5-131">Create a service using the supplied configuration, but do not define any endpoints.</span></span>

### <a name="code"></a><span data-ttu-id="0c3b5-132">コード</span><span class="sxs-lookup"><span data-stu-id="0c3b5-132">Code</span></span>

<span data-ttu-id="0c3b5-133">次のコードは、トランスポート セキュリティを使用してエンドポイントを作成する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="0c3b5-133">The following code shows how to create an endpoint using transport security:</span></span>

[!code-csharp[c_SecurityScenarios#5](~/samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#5)]
[!code-vb[c_SecurityScenarios#5](~/samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#5)]

### <a name="configuration"></a><span data-ttu-id="0c3b5-134">の構成</span><span class="sxs-lookup"><span data-stu-id="0c3b5-134">Configuration</span></span>

<span data-ttu-id="0c3b5-135">次のコードは、構成を使用して同一のエンドポイントをセットアップします。</span><span class="sxs-lookup"><span data-stu-id="0c3b5-135">The following code sets up the same endpoint using configuration.</span></span> <span data-ttu-id="0c3b5-136">クライアントを認証する機構はないため、匿名となります。</span><span class="sxs-lookup"><span data-stu-id="0c3b5-136">The client is not authenticated by any mechanism, and is therefore anonymous.</span></span>

```xml
<?xml version="1.0" encoding="utf-8"?>
<configuration>
  <system.serviceModel>
    <services>
      <service name="ServiceModel.Calculator">
        <endpoint address="https://localhost/Calculator"
                  binding="wsHttpBinding"
                  bindingConfiguration="WSHttpBinding_ICalculator"
                  name="SecuredByTransportEndpoint"
                  contract="ServiceModel.ICalculator" />
      </service>
    </services>
    <bindings>
      <wsHttpBinding>
        <binding name="WSHttpBinding_ICalculator">
          <security mode="Transport">
            <transport clientCredentialType="None" />
          </security>
        </binding>
      </wsHttpBinding>
    </bindings>
    <client />
  </system.serviceModel>
</configuration>
```

## <a name="client"></a><span data-ttu-id="0c3b5-137">クライアント</span><span class="sxs-lookup"><span data-stu-id="0c3b5-137">Client</span></span>

<span data-ttu-id="0c3b5-138">次のコードと構成は、別々に実行します。</span><span class="sxs-lookup"><span data-stu-id="0c3b5-138">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="0c3b5-139">以下のいずれかを実行します。</span><span class="sxs-lookup"><span data-stu-id="0c3b5-139">Do one of the following:</span></span>

- <span data-ttu-id="0c3b5-140">コード (およびクライアント コード) を使用してスタンドアロン クライアントを作成します。</span><span class="sxs-lookup"><span data-stu-id="0c3b5-140">Create a stand-alone client using the code (and client code).</span></span>

- <span data-ttu-id="0c3b5-141">エンドポイント アドレスを定義しないクライアントを作成します。</span><span class="sxs-lookup"><span data-stu-id="0c3b5-141">Create a client that does not define any endpoint addresses.</span></span> <span data-ttu-id="0c3b5-142">代わりに、引数として構成名を受け取るクライアント コンストラクターを使用します。</span><span class="sxs-lookup"><span data-stu-id="0c3b5-142">Instead, use the client constructor that takes the configuration name as an argument.</span></span> <span data-ttu-id="0c3b5-143">例:</span><span class="sxs-lookup"><span data-stu-id="0c3b5-143">For example:</span></span>

     [!code-csharp[C_SecurityScenarios#0](~/samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#0)]
     [!code-vb[C_SecurityScenarios#0](~/samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#0)]

### <a name="code"></a><span data-ttu-id="0c3b5-144">コード</span><span class="sxs-lookup"><span data-stu-id="0c3b5-144">Code</span></span>

[!code-csharp[c_SecurityScenarios#6](~/samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#6)]
[!code-vb[c_SecurityScenarios#6](~/samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#6)]

### <a name="configuration"></a><span data-ttu-id="0c3b5-145">の構成</span><span class="sxs-lookup"><span data-stu-id="0c3b5-145">Configuration</span></span>

<span data-ttu-id="0c3b5-146">コードの代わりに次の構成を使用して、サービスをセットアップできます。</span><span class="sxs-lookup"><span data-stu-id="0c3b5-146">The following configuration can be used instead of the code to set up the service.</span></span>

```xml
<configuration>
  <system.serviceModel>
    <bindings>
      <wsHttpBinding>
        <binding name="WSHttpBinding_ICalculator" >
          <security mode="Transport">
            <transport clientCredentialType="None" />
          </security>
        </binding>
      </wsHttpBinding>
    </bindings>
    <client>
      <endpoint address="https://machineName/Calculator"
                binding="wsHttpBinding"
                bindingConfiguration="WSHttpBinding_ICalculator"
                contract="ICalculator"
                name="WSHttpBinding_ICalculator" />
    </client>
  </system.serviceModel>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="0c3b5-147">関連項目</span><span class="sxs-lookup"><span data-stu-id="0c3b5-147">See also</span></span>

- [<span data-ttu-id="0c3b5-148">セキュリティの概要</span><span class="sxs-lookup"><span data-stu-id="0c3b5-148">Security Overview</span></span>](security-overview.md)
- [<span data-ttu-id="0c3b5-149">WS トランスポート セキュリティ</span><span class="sxs-lookup"><span data-stu-id="0c3b5-149">WS Transport Security</span></span>](../samples/ws-transport-security.md)
- [<span data-ttu-id="0c3b5-150">トランスポート セキュリティの概要</span><span class="sxs-lookup"><span data-stu-id="0c3b5-150">Transport Security Overview</span></span>](transport-security-overview.md)
- <span data-ttu-id="0c3b5-151">[Windows Server App Fabric のセキュリティモデル](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="0c3b5-151">[Security Model for Windows Server App Fabric](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))</span></span>
