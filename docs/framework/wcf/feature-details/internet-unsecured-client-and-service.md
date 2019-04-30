---
title: セキュリティで保護されていないインターネット環境のクライアントとサービス
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 97a10d79-3e7d-4bd1-9a99-fd9807fd70bc
ms.openlocfilehash: ca6b028ef20095d6faeb125151772eedf1500fa0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62038728"
---
# <a name="internet-unsecured-client-and-service"></a><span data-ttu-id="914b9-102">セキュリティで保護されていないインターネット環境のクライアントとサービス</span><span class="sxs-lookup"><span data-stu-id="914b9-102">Internet Unsecured Client and Service</span></span>
<span data-ttu-id="914b9-103">次の図は、パブリック、セキュリティ保護されていない Windows Communication Foundation (WCF) クライアントとサービスの例を示します。</span><span class="sxs-lookup"><span data-stu-id="914b9-103">The following illustration shows an example of a public, unsecured Windows Communication Foundation (WCF) client and service:</span></span>  
  
 ![セキュリティ保護されていないインターネットのシナリオを示すスクリーン ショット](./media/internet-unsecured-client-and-service/public-unsecured-internet.gif)  
  
|<span data-ttu-id="914b9-105">特徴</span><span class="sxs-lookup"><span data-stu-id="914b9-105">Characteristic</span></span>|<span data-ttu-id="914b9-106">説明</span><span class="sxs-lookup"><span data-stu-id="914b9-106">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="914b9-107">セキュリティ モード</span><span class="sxs-lookup"><span data-stu-id="914b9-107">Security Mode</span></span>|<span data-ttu-id="914b9-108">なし</span><span class="sxs-lookup"><span data-stu-id="914b9-108">None</span></span>|  
|<span data-ttu-id="914b9-109">Transport</span><span class="sxs-lookup"><span data-stu-id="914b9-109">Transport</span></span>|<span data-ttu-id="914b9-110">HTTP</span><span class="sxs-lookup"><span data-stu-id="914b9-110">HTTP</span></span>|  
|<span data-ttu-id="914b9-111">バインディング</span><span class="sxs-lookup"><span data-stu-id="914b9-111">Binding</span></span>|<span data-ttu-id="914b9-112"><xref:System.ServiceModel.BasicHttpBinding> コードでは、または[ \<basicHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md)構成内の要素。</span><span class="sxs-lookup"><span data-stu-id="914b9-112"><xref:System.ServiceModel.BasicHttpBinding> in code, or the [\<basicHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md) element in configuration.</span></span>|  
|<span data-ttu-id="914b9-113">相互運用性</span><span class="sxs-lookup"><span data-stu-id="914b9-113">Interoperability</span></span>|<span data-ttu-id="914b9-114">既存の Web サービス クライアントとサービスを使用する</span><span class="sxs-lookup"><span data-stu-id="914b9-114">With existing Web service clients and services</span></span>|  
|<span data-ttu-id="914b9-115">認証</span><span class="sxs-lookup"><span data-stu-id="914b9-115">Authentication</span></span>|<span data-ttu-id="914b9-116">なし</span><span class="sxs-lookup"><span data-stu-id="914b9-116">None</span></span>|  
|<span data-ttu-id="914b9-117">整合性</span><span class="sxs-lookup"><span data-stu-id="914b9-117">Integrity</span></span>|<span data-ttu-id="914b9-118">なし</span><span class="sxs-lookup"><span data-stu-id="914b9-118">None</span></span>|  
|<span data-ttu-id="914b9-119">機密性</span><span class="sxs-lookup"><span data-stu-id="914b9-119">Confidentiality</span></span>|<span data-ttu-id="914b9-120">なし</span><span class="sxs-lookup"><span data-stu-id="914b9-120">None</span></span>|  
  
## <a name="service"></a><span data-ttu-id="914b9-121">サービス</span><span class="sxs-lookup"><span data-stu-id="914b9-121">Service</span></span>  
 <span data-ttu-id="914b9-122">次のコードと構成は、別々に実行します。</span><span class="sxs-lookup"><span data-stu-id="914b9-122">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="914b9-123">次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="914b9-123">Do one of the following:</span></span>  
  
- <span data-ttu-id="914b9-124">構成を使用せずに、コードを使用してスタンドアロン サービスを作成します。</span><span class="sxs-lookup"><span data-stu-id="914b9-124">Create a stand-alone service using the code with no configuration.</span></span>  
  
- <span data-ttu-id="914b9-125">提供された構成を使用してサービスを作成しますが、エンドポイントを定義しません。</span><span class="sxs-lookup"><span data-stu-id="914b9-125">Create a service using the supplied configuration, but do not define any endpoints.</span></span>  
  
### <a name="code"></a><span data-ttu-id="914b9-126">コード</span><span class="sxs-lookup"><span data-stu-id="914b9-126">Code</span></span>  
 <span data-ttu-id="914b9-127">次のコードは、セキュリティで保護されないエンドポイントを作成する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="914b9-127">The following code shows how to create an endpoint with no security.</span></span> <span data-ttu-id="914b9-128">既定では、<xref:System.ServiceModel.BasicHttpBinding> のセキュリティ モードは <xref:System.ServiceModel.BasicHttpSecurityMode.None> に設定されます。</span><span class="sxs-lookup"><span data-stu-id="914b9-128">By default, the <xref:System.ServiceModel.BasicHttpBinding> has the security mode set to <xref:System.ServiceModel.BasicHttpSecurityMode.None>.</span></span>  
  
 [!code-csharp[C_UnsecuredService#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_unsecuredservice/cs/source.cs#1)]
 [!code-vb[C_UnsecuredService#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_unsecuredservice/vb/source.vb#1)]  
  
### <a name="service-configuration"></a><span data-ttu-id="914b9-129">サービス構成</span><span class="sxs-lookup"><span data-stu-id="914b9-129">Service Configuration</span></span>  
 <span data-ttu-id="914b9-130">次のコードは、構成を使用して同一のエンドポイントをセットアップします。</span><span class="sxs-lookup"><span data-stu-id="914b9-130">The following code sets up the same endpoint using configuration.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <behaviors />  
    <services>  
      <service behaviorConfiguration="" name="ServiceModel.Calculator">  
        <endpoint address="http://localhost/Calculator"   
                  binding="basicHttpBinding"  
                  bindingConfiguration="Basic_Unsecured"   
                  name="BasicHttp_ICalculator"  
                  contract="ServiceModel.ICalculator" />  
      </service>  
    </services>  
    <bindings>  
      <basicHttpBinding>  
        <binding name="Basic_Unsecured" />  
      </basicHttpBinding>  
    </bindings>  
    <client />  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="client"></a><span data-ttu-id="914b9-131">クライアント</span><span class="sxs-lookup"><span data-stu-id="914b9-131">Client</span></span>  
 <span data-ttu-id="914b9-132">次のコードと構成は、別々に実行します。</span><span class="sxs-lookup"><span data-stu-id="914b9-132">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="914b9-133">次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="914b9-133">Do one of the following:</span></span>  
  
- <span data-ttu-id="914b9-134">コード (およびクライアント コード) を使用してスタンドアロン クライアントを作成します。</span><span class="sxs-lookup"><span data-stu-id="914b9-134">Create a stand-alone client using the code (and client code).</span></span>  
  
- <span data-ttu-id="914b9-135">エンドポイント アドレスを定義しないクライアントを作成します。</span><span class="sxs-lookup"><span data-stu-id="914b9-135">Create a client that does not define any endpoint addresses.</span></span> <span data-ttu-id="914b9-136">代わりに、引数として構成名を受け取るクライアント コンストラクターを使用します。</span><span class="sxs-lookup"><span data-stu-id="914b9-136">Instead, use the client constructor that takes the configuration name as an argument.</span></span> <span data-ttu-id="914b9-137">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="914b9-137">For example:</span></span>  
  
     [!code-csharp[C_SecurityScenarios#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#0)]
     [!code-vb[C_SecurityScenarios#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#0)]  
  
### <a name="code"></a><span data-ttu-id="914b9-138">コード</span><span class="sxs-lookup"><span data-stu-id="914b9-138">Code</span></span>  
 <span data-ttu-id="914b9-139">次のコードでは、セキュリティ保護されていないエンドポイントにアクセスする基本的な WCF クライアントを示します。</span><span class="sxs-lookup"><span data-stu-id="914b9-139">The following code shows a basic WCF client that accesses an unsecured endpoint.</span></span>  
  
 [!code-csharp[C_UnsecuredClient#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_unsecuredclient/cs/source.cs#1)]
 [!code-vb[C_UnsecuredClient#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_unsecuredclient/vb/source.vb#1)]  
  
### <a name="client-configuration"></a><span data-ttu-id="914b9-140">クライアント構成</span><span class="sxs-lookup"><span data-stu-id="914b9-140">Client Configuration</span></span>  
 <span data-ttu-id="914b9-141">クライアントを構成する場合のコード例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="914b9-141">The following code configures the client.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <bindings>  
      <basicHttpBinding>  
        <binding name="BasicHttpBinding_ICalculator" >  
          <security mode="None">  
          </security>  
        </binding>  
      </basicHttpBinding>  
    </bindings>  
    <client>  
      <endpoint address="http://localhost/Calculator/Unsecured"  
          binding="basicHttpBinding"   
          bindingConfiguration="BasicHttpBinding_ICalculator"  
          contract="ICalculator"   
          name="BasicHttpBinding_ICalculator" />  
    </client>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="914b9-142">関連項目</span><span class="sxs-lookup"><span data-stu-id="914b9-142">See also</span></span>

- [<span data-ttu-id="914b9-143">一般的なセキュリティ シナリオ</span><span class="sxs-lookup"><span data-stu-id="914b9-143">Common Security Scenarios</span></span>](../../../../docs/framework/wcf/feature-details/common-security-scenarios.md)
- [<span data-ttu-id="914b9-144">セキュリティの概要</span><span class="sxs-lookup"><span data-stu-id="914b9-144">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)
- [<span data-ttu-id="914b9-145">Windows Server App Fabric のセキュリティ モデル</span><span class="sxs-lookup"><span data-stu-id="914b9-145">Security Model for Windows Server App Fabric</span></span>](https://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)
