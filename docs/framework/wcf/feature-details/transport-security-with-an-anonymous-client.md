---
title: 匿名クライアントを使用したトランスポートセキュリティ
description: この WCF シナリオを確認します。このシナリオでは、トランスポートセキュリティを使用して、クライアントが信頼する証明書を使用してサーバーを認証します。 クライアントは認証されていません。
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 056653a5-384e-4a02-ae3c-1b0157d2ccb4
ms.openlocfilehash: 5e8bcab4cdd8f27e9ea27e66fe4c848ccd35e99c
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/15/2020
ms.locfileid: "90556812"
---
# <a name="transport-security-with-an-anonymous-client"></a><span data-ttu-id="e558c-104">匿名クライアントを使用したトランスポートセキュリティ</span><span class="sxs-lookup"><span data-stu-id="e558c-104">Transport security with an anonymous client</span></span>

<span data-ttu-id="e558c-105">この Windows Communication Foundation (WCF) シナリオでは、トランスポートセキュリティ (HTTPS) を使用して、機密性と整合性を確保します。</span><span class="sxs-lookup"><span data-stu-id="e558c-105">This Windows Communication Foundation (WCF) scenario uses transport security (HTTPS) to ensure confidentiality and integrity.</span></span> <span data-ttu-id="e558c-106">サーバーは SSL (Secure Sockets Layer) 証明書で認証される必要があり、クライアントはサーバーの証明書を信頼する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e558c-106">The server must be authenticated with a Secure Sockets Layer (SSL) certificate, and the clients must trust the server's certificate.</span></span> <span data-ttu-id="e558c-107">クライアントを認証する機構はないため、匿名となります。</span><span class="sxs-lookup"><span data-stu-id="e558c-107">The client is not authenticated by any mechanism and is, therefore, anonymous.</span></span>

<span data-ttu-id="e558c-108">サンプルアプリケーションについては、「 [WS トランスポートセキュリティ](../samples/ws-transport-security.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e558c-108">For a sample application, see [WS Transport Security](../samples/ws-transport-security.md).</span></span> <span data-ttu-id="e558c-109">トランスポートセキュリティの詳細については、「 [トランスポートセキュリティの概要](transport-security-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e558c-109">For more information about transport security, see [Transport Security Overview](transport-security-overview.md).</span></span>

<span data-ttu-id="e558c-110">サービスで証明書を使用する方法の詳細については、「 [証明書の操作](working-with-certificates.md) 」および「 [方法: SSL 証明書を使用してポートを構成する](how-to-configure-a-port-with-an-ssl-certificate.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e558c-110">For more information about using a certificate with a service, see [Working with Certificates](working-with-certificates.md) and [How to: Configure a Port with an SSL Certificate](how-to-configure-a-port-with-an-ssl-certificate.md).</span></span>

![匿名クライアントを使用する場合のトランスポート セキュリティ](./media/8fa2e931-0cfb-4aaa-9272-91d652b85d8d.gif)

|<span data-ttu-id="e558c-112">特徴</span><span class="sxs-lookup"><span data-stu-id="e558c-112">Characteristic</span></span>|<span data-ttu-id="e558c-113">説明</span><span class="sxs-lookup"><span data-stu-id="e558c-113">Description</span></span>|
|--------------------|-----------------|
|<span data-ttu-id="e558c-114">セキュリティ モード</span><span class="sxs-lookup"><span data-stu-id="e558c-114">Security Mode</span></span>|<span data-ttu-id="e558c-115">トランスポート</span><span class="sxs-lookup"><span data-stu-id="e558c-115">Transport</span></span>|
|<span data-ttu-id="e558c-116">相互運用性</span><span class="sxs-lookup"><span data-stu-id="e558c-116">Interoperability</span></span>|<span data-ttu-id="e558c-117">既存の Web サービスとクライアントを使用する</span><span class="sxs-lookup"><span data-stu-id="e558c-117">With existing Web services and clients</span></span>|
|<span data-ttu-id="e558c-118">認証 (サーバー)</span><span class="sxs-lookup"><span data-stu-id="e558c-118">Authentication (Server)</span></span><br /><br /> <span data-ttu-id="e558c-119">認証 (クライアント)</span><span class="sxs-lookup"><span data-stu-id="e558c-119">Authentication (Client)</span></span>|<span data-ttu-id="e558c-120">はい</span><span class="sxs-lookup"><span data-stu-id="e558c-120">Yes</span></span><br /><br /> <span data-ttu-id="e558c-121">アプリケーションレベル (WCF サポートなし)</span><span class="sxs-lookup"><span data-stu-id="e558c-121">Application level (no WCF support)</span></span>|
|<span data-ttu-id="e558c-122">整合性</span><span class="sxs-lookup"><span data-stu-id="e558c-122">Integrity</span></span>|<span data-ttu-id="e558c-123">はい</span><span class="sxs-lookup"><span data-stu-id="e558c-123">Yes</span></span>|
|<span data-ttu-id="e558c-124">機密性</span><span class="sxs-lookup"><span data-stu-id="e558c-124">Confidentiality</span></span>|<span data-ttu-id="e558c-125">はい</span><span class="sxs-lookup"><span data-stu-id="e558c-125">Yes</span></span>|
|<span data-ttu-id="e558c-126">トランスポート</span><span class="sxs-lookup"><span data-stu-id="e558c-126">Transport</span></span>|<span data-ttu-id="e558c-127">HTTPS</span><span class="sxs-lookup"><span data-stu-id="e558c-127">HTTPS</span></span>|
|<span data-ttu-id="e558c-128">バインド</span><span class="sxs-lookup"><span data-stu-id="e558c-128">Binding</span></span>|<xref:System.ServiceModel.WSHttpBinding>|

## <a name="service"></a><span data-ttu-id="e558c-129">サービス</span><span class="sxs-lookup"><span data-stu-id="e558c-129">Service</span></span>

<span data-ttu-id="e558c-130">次のコードと構成は、別々に実行します。</span><span class="sxs-lookup"><span data-stu-id="e558c-130">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="e558c-131">次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="e558c-131">Do one of the following:</span></span>

- <span data-ttu-id="e558c-132">構成を使用せずに、コードを使用してスタンドアロン サービスを作成します。</span><span class="sxs-lookup"><span data-stu-id="e558c-132">Create a stand-alone service using the code with no configuration.</span></span>

- <span data-ttu-id="e558c-133">提供された構成を使用してサービスを作成しますが、エンドポイントを定義しません。</span><span class="sxs-lookup"><span data-stu-id="e558c-133">Create a service using the supplied configuration, but do not define any endpoints.</span></span>

### <a name="code"></a><span data-ttu-id="e558c-134">コード</span><span class="sxs-lookup"><span data-stu-id="e558c-134">Code</span></span>

<span data-ttu-id="e558c-135">次のコードは、トランスポート セキュリティを使用してエンドポイントを作成する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="e558c-135">The following code shows how to create an endpoint using transport security:</span></span>

[!code-csharp[c_SecurityScenarios#5](~/samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#5)]
[!code-vb[c_SecurityScenarios#5](~/samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#5)]

### <a name="configuration"></a><span data-ttu-id="e558c-136">構成</span><span class="sxs-lookup"><span data-stu-id="e558c-136">Configuration</span></span>

<span data-ttu-id="e558c-137">次のコードは、構成を使用して同一のエンドポイントをセットアップします。</span><span class="sxs-lookup"><span data-stu-id="e558c-137">The following code sets up the same endpoint using configuration.</span></span> <span data-ttu-id="e558c-138">クライアントを認証する機構はないため、匿名となります。</span><span class="sxs-lookup"><span data-stu-id="e558c-138">The client is not authenticated by any mechanism, and is therefore anonymous.</span></span>

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

## <a name="client"></a><span data-ttu-id="e558c-139">クライアント</span><span class="sxs-lookup"><span data-stu-id="e558c-139">Client</span></span>

<span data-ttu-id="e558c-140">次のコードと構成は、別々に実行します。</span><span class="sxs-lookup"><span data-stu-id="e558c-140">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="e558c-141">次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="e558c-141">Do one of the following:</span></span>

- <span data-ttu-id="e558c-142">コード (およびクライアント コード) を使用してスタンドアロン クライアントを作成します。</span><span class="sxs-lookup"><span data-stu-id="e558c-142">Create a stand-alone client using the code (and client code).</span></span>

- <span data-ttu-id="e558c-143">エンドポイント アドレスを定義しないクライアントを作成します。</span><span class="sxs-lookup"><span data-stu-id="e558c-143">Create a client that does not define any endpoint addresses.</span></span> <span data-ttu-id="e558c-144">代わりに、引数として構成名を受け取るクライアント コンストラクターを使用します。</span><span class="sxs-lookup"><span data-stu-id="e558c-144">Instead, use the client constructor that takes the configuration name as an argument.</span></span> <span data-ttu-id="e558c-145">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="e558c-145">For example:</span></span>

     [!code-csharp[C_SecurityScenarios#0](~/samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#0)]
     [!code-vb[C_SecurityScenarios#0](~/samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#0)]

### <a name="code"></a><span data-ttu-id="e558c-146">コード</span><span class="sxs-lookup"><span data-stu-id="e558c-146">Code</span></span>

[!code-csharp[c_SecurityScenarios#6](~/samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#6)]
[!code-vb[c_SecurityScenarios#6](~/samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#6)]

### <a name="configuration"></a><span data-ttu-id="e558c-147">構成</span><span class="sxs-lookup"><span data-stu-id="e558c-147">Configuration</span></span>

<span data-ttu-id="e558c-148">コードの代わりに次の構成を使用して、サービスをセットアップできます。</span><span class="sxs-lookup"><span data-stu-id="e558c-148">The following configuration can be used instead of the code to set up the service.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="e558c-149">関連項目</span><span class="sxs-lookup"><span data-stu-id="e558c-149">See also</span></span>

- [<span data-ttu-id="e558c-150">セキュリティの概要</span><span class="sxs-lookup"><span data-stu-id="e558c-150">Security Overview</span></span>](security-overview.md)
- [<span data-ttu-id="e558c-151">WS トランスポート セキュリティ</span><span class="sxs-lookup"><span data-stu-id="e558c-151">WS Transport Security</span></span>](../samples/ws-transport-security.md)
- [<span data-ttu-id="e558c-152">トランスポート セキュリティの概要</span><span class="sxs-lookup"><span data-stu-id="e558c-152">Transport Security Overview</span></span>](transport-security-overview.md)
- <span data-ttu-id="e558c-153">[Windows Server AppFabric のセキュリティ モデル](/previous-versions/appfabric/ee677202(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="e558c-153">[Security Model for Windows Server App Fabric](/previous-versions/appfabric/ee677202(v=azure.10))</span></span>
