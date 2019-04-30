---
title: ユーザー名クライアントを使用したメッセージ セキュリティ
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 36335cb9-76b8-4443-92c7-44f081eabb21
ms.openlocfilehash: 73e984193f87b20e0e00d8ab92a7c0fd67f7968f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62046571"
---
# <a name="message-security-with-a-user-name-client"></a><span data-ttu-id="99b8d-102">ユーザー名クライアントを使用したメッセージ セキュリティ</span><span class="sxs-lookup"><span data-stu-id="99b8d-102">Message Security with a User Name Client</span></span>
<span data-ttu-id="99b8d-103">次の図は、Windows Communication Foundation (WCF) サービスとクライアントのメッセージ レベルのセキュリティを使用して保護します。</span><span class="sxs-lookup"><span data-stu-id="99b8d-103">The following illustration shows an Windows Communication Foundation (WCF) service and client secured using message-level security.</span></span> <span data-ttu-id="99b8d-104">サービスは X.509 証明書を使用して認証されます。</span><span class="sxs-lookup"><span data-stu-id="99b8d-104">The service is authenticated with an X.509 certificate.</span></span> <span data-ttu-id="99b8d-105">クライアントはユーザー名とパスワードを使用して認証されます。</span><span class="sxs-lookup"><span data-stu-id="99b8d-105">The client authenticates using a user name and password.</span></span>  
  
 <span data-ttu-id="99b8d-106">サンプル アプリケーションでは、次を参照してください。[メッセージ セキュリティ ユーザー名](../../../../docs/framework/wcf/samples/message-security-user-name.md)します。</span><span class="sxs-lookup"><span data-stu-id="99b8d-106">For a sample application, see [Message Security User Name](../../../../docs/framework/wcf/samples/message-security-user-name.md).</span></span>  
  
 <span data-ttu-id="99b8d-107">![ユーザー名認証を使用して、メッセージ セキュリティ](../../../../docs/framework/wcf/feature-details/media/1fb10a61-7e1d-42f5-b1af-195bfee5b3c6.gif "1fb10a61-7e1d-42f5-b1af-195bfee5b3c6")</span><span class="sxs-lookup"><span data-stu-id="99b8d-107">![Message security using username authentication](../../../../docs/framework/wcf/feature-details/media/1fb10a61-7e1d-42f5-b1af-195bfee5b3c6.gif "1fb10a61-7e1d-42f5-b1af-195bfee5b3c6")</span></span>  
  
|<span data-ttu-id="99b8d-108">特徴</span><span class="sxs-lookup"><span data-stu-id="99b8d-108">Characteristic</span></span>|<span data-ttu-id="99b8d-109">説明</span><span class="sxs-lookup"><span data-stu-id="99b8d-109">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="99b8d-110">セキュリティ モード</span><span class="sxs-lookup"><span data-stu-id="99b8d-110">Security Mode</span></span>|<span data-ttu-id="99b8d-111">メッセージ</span><span class="sxs-lookup"><span data-stu-id="99b8d-111">Message</span></span>|  
|<span data-ttu-id="99b8d-112">相互運用性</span><span class="sxs-lookup"><span data-stu-id="99b8d-112">Interoperability</span></span>|<span data-ttu-id="99b8d-113">Windows Communication Foundation (WCF) のみ</span><span class="sxs-lookup"><span data-stu-id="99b8d-113">Windows Communication Foundation (WCF) only</span></span>|  
|<span data-ttu-id="99b8d-114">認証 (サーバー)</span><span class="sxs-lookup"><span data-stu-id="99b8d-114">Authentication (Server)</span></span>|<span data-ttu-id="99b8d-115">初期ネゴシエーションにはサーバー認証が必要</span><span class="sxs-lookup"><span data-stu-id="99b8d-115">Initial negotiation requires server authentication</span></span>|  
|<span data-ttu-id="99b8d-116">認証 (クライアント)</span><span class="sxs-lookup"><span data-stu-id="99b8d-116">Authentication (Client)</span></span>|<span data-ttu-id="99b8d-117">ユーザー名/パスワード</span><span class="sxs-lookup"><span data-stu-id="99b8d-117">User name/password</span></span>|  
|<span data-ttu-id="99b8d-118">整合性</span><span class="sxs-lookup"><span data-stu-id="99b8d-118">Integrity</span></span>|<span data-ttu-id="99b8d-119">はい、共有のセキュリティ コンテキストを使用します</span><span class="sxs-lookup"><span data-stu-id="99b8d-119">Yes, using shared security context</span></span>|  
|<span data-ttu-id="99b8d-120">機密性</span><span class="sxs-lookup"><span data-stu-id="99b8d-120">Confidentiality</span></span>|<span data-ttu-id="99b8d-121">はい、共有のセキュリティ コンテキストを使用します</span><span class="sxs-lookup"><span data-stu-id="99b8d-121">Yes, using shared security context</span></span>|  
|<span data-ttu-id="99b8d-122">Transport</span><span class="sxs-lookup"><span data-stu-id="99b8d-122">Transport</span></span>|<span data-ttu-id="99b8d-123">HTTP</span><span class="sxs-lookup"><span data-stu-id="99b8d-123">HTTP</span></span>|  
|<span data-ttu-id="99b8d-124">バインディング</span><span class="sxs-lookup"><span data-stu-id="99b8d-124">Binding</span></span>|<xref:System.ServiceModel.WSHttpBinding>|  
  
## <a name="service"></a><span data-ttu-id="99b8d-125">サービス</span><span class="sxs-lookup"><span data-stu-id="99b8d-125">Service</span></span>  
 <span data-ttu-id="99b8d-126">次のコードと構成は、別々に実行します。</span><span class="sxs-lookup"><span data-stu-id="99b8d-126">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="99b8d-127">次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="99b8d-127">Do one of the following:</span></span>  
  
- <span data-ttu-id="99b8d-128">構成を使用せずに、コードを使用してスタンドアロン サービスを作成します。</span><span class="sxs-lookup"><span data-stu-id="99b8d-128">Create a stand-alone service using the code with no configuration.</span></span>  
  
- <span data-ttu-id="99b8d-129">提供された構成を使用してサービスを作成しますが、エンドポイントを定義しません。</span><span class="sxs-lookup"><span data-stu-id="99b8d-129">Create a service using the supplied configuration, but do not define any endpoints.</span></span>  
  
### <a name="code"></a><span data-ttu-id="99b8d-130">コード</span><span class="sxs-lookup"><span data-stu-id="99b8d-130">Code</span></span>  
 <span data-ttu-id="99b8d-131">次のコードは、メッセージ セキュリティを使用するサービス エンドポイントの作成方法を示します。</span><span class="sxs-lookup"><span data-stu-id="99b8d-131">The following code shows how to create a service endpoint that uses message security.</span></span>  
  
 [!code-csharp[C_SecurityScenarios#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#9)]
 [!code-vb[C_SecurityScenarios#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#9)]  
  
### <a name="configuration"></a><span data-ttu-id="99b8d-132">構成</span><span class="sxs-lookup"><span data-stu-id="99b8d-132">Configuration</span></span>  
 <span data-ttu-id="99b8d-133">コードの代わりに次の構成を使用できます。</span><span class="sxs-lookup"><span data-stu-id="99b8d-133">The following configuration can be used instead of the code:</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="ServiceCredentialsBehavior">  
          <serviceCredentials>  
            <serviceCertificate findValue="Contoso.com"   
                                storeLocation="LocalMachine"  
                                storeName="My"     
                                x509FindType="FindBySubjectName" />  
          </serviceCredentials>  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
    <services>  
      <service behaviorConfiguration="ServiceCredentialsBehavior"  
               name="ServiceModel.Calculator">  
        <endpoint address="http://localhost/Calculator"  
                  binding="wsHttpBinding"  
                  bindingConfiguration="MessageAndUserName"  
                  name="SecuredByTransportEndpoint"  
                  contract="ServiceModel.ICalculator" />  
      </service>  
    </services>  
    <bindings>  
      <wsHttpBinding>  
        <binding name="MessageAndUserName">  
          <security mode="Message">              
            <message clientCredentialType="UserName" />  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
    <client />  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="client"></a><span data-ttu-id="99b8d-134">クライアント</span><span class="sxs-lookup"><span data-stu-id="99b8d-134">Client</span></span>  
  
### <a name="code"></a><span data-ttu-id="99b8d-135">コード</span><span class="sxs-lookup"><span data-stu-id="99b8d-135">Code</span></span>  
 <span data-ttu-id="99b8d-136">クライアントを作成する場合のコード例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="99b8d-136">The following code creates the client.</span></span> <span data-ttu-id="99b8d-137">バインディングではメッセージ モード セキュリティを使用し、クライアント資格情報の種類は `UserName` に設定します。</span><span class="sxs-lookup"><span data-stu-id="99b8d-137">The binding is to message mode security, and the client credential type is set to `UserName`.</span></span> <span data-ttu-id="99b8d-138">ユーザー名とパスワードの指定はコードを使用する場合に限られます (構成可能ではありません)。</span><span class="sxs-lookup"><span data-stu-id="99b8d-138">The user name and password can only be specified using code (it is not configurable).</span></span> <span data-ttu-id="99b8d-139">ユーザー名とパスワードを返すコードは、アプリケーション レベルで実行される必要があるため、ここには示しません。</span><span class="sxs-lookup"><span data-stu-id="99b8d-139">The code to return the user name and password is not shown here because it must be done at the application level.</span></span> <span data-ttu-id="99b8d-140">たとえば、Windows フォーム ダイアログ ボックスを使用してユーザーにデータを照会します。</span><span class="sxs-lookup"><span data-stu-id="99b8d-140">For example, use a Windows Forms dialog box to query the user for the data.</span></span>  
  
 [!code-csharp[C_SecurityScenarios#16](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#16)]
 [!code-vb[C_SecurityScenarios#16](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#16)]  
  
### <a name="configuration"></a><span data-ttu-id="99b8d-141">構成</span><span class="sxs-lookup"><span data-stu-id="99b8d-141">Configuration</span></span>  
 <span data-ttu-id="99b8d-142">クライアントを構成する場合のコード例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="99b8d-142">The following code configures the client.</span></span> <span data-ttu-id="99b8d-143">バインディングではメッセージ モード セキュリティを使用し、クライアント資格情報の種類は `UserName` に設定します。</span><span class="sxs-lookup"><span data-stu-id="99b8d-143">The binding is to message mode security, and the client credential type is set to `UserName`.</span></span> <span data-ttu-id="99b8d-144">ユーザー名とパスワードの指定はコードを使用する場合に限られます (構成可能ではありません)。</span><span class="sxs-lookup"><span data-stu-id="99b8d-144">The user name and password can only be specified using code (it is not configurable).</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <bindings>  
      <wsHttpBinding>  
        <binding name="WSHttpBinding_ICalculator" >  
          <security mode="Message">  
            <message clientCredentialType="UserName" />  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
    <client>  
      <endpoint address="http://machineName/Calculator"   
                binding="wsHttpBinding"  
                bindingConfiguration="WSHttpBinding_ICalculator"   
                contract="ICalculator"  
                name="WSHttpBinding_ICalculator">  
        <identity>  
          <dns value ="Contoso.com" />  
        </identity>  
      </endpoint>  
    </client>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="99b8d-145">関連項目</span><span class="sxs-lookup"><span data-stu-id="99b8d-145">See also</span></span>

- [<span data-ttu-id="99b8d-146">セキュリティの概要</span><span class="sxs-lookup"><span data-stu-id="99b8d-146">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)
- [<span data-ttu-id="99b8d-147">メッセージ セキュリティ ユーザー名</span><span class="sxs-lookup"><span data-stu-id="99b8d-147">Message Security User Name</span></span>](../../../../docs/framework/wcf/samples/message-security-user-name.md)
- [<span data-ttu-id="99b8d-148">サービス ID と認証</span><span class="sxs-lookup"><span data-stu-id="99b8d-148">Service Identity and Authentication</span></span>](../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="99b8d-149">\<identity></span><span class="sxs-lookup"><span data-stu-id="99b8d-149">\<identity></span></span>](../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)
- [<span data-ttu-id="99b8d-150">Windows Server App Fabric のセキュリティ モデル</span><span class="sxs-lookup"><span data-stu-id="99b8d-150">Security Model for Windows Server App Fabric</span></span>](https://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)
