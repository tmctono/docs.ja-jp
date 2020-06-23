---
title: '方法: クライアントの資格情報の値を指定する'
description: WCF サービスで、クライアントがそのサービスに対して認証される方法を指定する方法について説明します。 この例では、x.509 証明書とトランスポートモードを指定します。
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 82293d7f-471a-4549-8f19-0be890e7b074
ms.openlocfilehash: 75a21a7dc083282f6b2fe839167ff1b2eddfb373
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/23/2020
ms.locfileid: "85244453"
---
# <a name="how-to-specify-client-credential-values"></a><span data-ttu-id="66dd4-104">方法: クライアントの資格情報の値を指定する</span><span class="sxs-lookup"><span data-stu-id="66dd4-104">How to: Specify Client Credential Values</span></span>

<span data-ttu-id="66dd4-105">サービスでは、Windows Communication Foundation (WCF) を使用して、サービスに対するクライアントの認証方法を指定できます。</span><span class="sxs-lookup"><span data-stu-id="66dd4-105">Using Windows Communication Foundation (WCF), the service can specify how a client is authenticated to the service.</span></span> <span data-ttu-id="66dd4-106">たとえば、証明書を使用してクライアントを認証するように指定できます。</span><span class="sxs-lookup"><span data-stu-id="66dd4-106">For example, a service can stipulate that the client be authenticated with a certificate.</span></span>

## <a name="to-determine-the-client-credential-type"></a><span data-ttu-id="66dd4-107">クライアント資格情報の種類を特定するには</span><span class="sxs-lookup"><span data-stu-id="66dd4-107">To determine the client credential type</span></span>

1. <span data-ttu-id="66dd4-108">サービスのメタデータ エンドポイントからメタデータを取得します。</span><span class="sxs-lookup"><span data-stu-id="66dd4-108">Retrieve metadata from the service's metadata endpoint.</span></span> <span data-ttu-id="66dd4-109">一般的に、メタデータは、選択したプログラミング言語 (既定は Visual C#) のクライアント コードおよび XML 構成ファイルという 2 つのファイルで構成されています。</span><span class="sxs-lookup"><span data-stu-id="66dd4-109">The metadata typically consists of two files: the client code in the programming language of your choice (the default is Visual C#), and an XML configuration file.</span></span> <span data-ttu-id="66dd4-110">メタデータは、クライアント コードおよびクライアント構成を返す Svcutil.exe ツールを使用して取得できます。</span><span class="sxs-lookup"><span data-stu-id="66dd4-110">One way to retrieve metadata is to use the Svcutil.exe tool to return the client code and client configuration.</span></span> <span data-ttu-id="66dd4-111">詳細については、「[メタデータの取得](./feature-details/retrieving-metadata.md)」および「 [ServiceModel メタデータユーティリティツール (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="66dd4-111">For more information, see [Retrieving Metadata](./feature-details/retrieving-metadata.md) and [ServiceModel Metadata Utility Tool (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md).</span></span>

2. <span data-ttu-id="66dd4-112">XML 構成ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="66dd4-112">Open the XML configuration file.</span></span> <span data-ttu-id="66dd4-113">Svcutil.exe ツールを使用する場合、ファイルの既定の名前は、Output.config です。</span><span class="sxs-lookup"><span data-stu-id="66dd4-113">If you use the Svcutil.exe tool, the default name of the file is Output.config.</span></span>

3. <span data-ttu-id="66dd4-114">**\<security>** **Mode**属性を持つ要素を検索し **\<security mode =**`MessageOrTransport`**>** `MessageOrTransport` ます (は、いずれかのセキュリティモードに設定されています)。</span><span class="sxs-lookup"><span data-stu-id="66dd4-114">Find the **\<security>** element with the **mode** attribute (**\<security mode =**`MessageOrTransport`**>** where `MessageOrTransport` is set to one of the security modes.</span></span>

4. <span data-ttu-id="66dd4-115">mode 値に一致する子要素を見つけます。</span><span class="sxs-lookup"><span data-stu-id="66dd4-115">Find the child element that matches the mode value.</span></span> <span data-ttu-id="66dd4-116">たとえば、モードが**Message**に設定されている場合は、 **\<message>** 要素に含まれる要素を検索し **\<security>** ます。</span><span class="sxs-lookup"><span data-stu-id="66dd4-116">For example, if the mode is set to **Message**, find the **\<message>** element contained in the **\<security>** element.</span></span>

5. <span data-ttu-id="66dd4-117">**ClientCredentialType**属性に割り当てられている値を確認します。</span><span class="sxs-lookup"><span data-stu-id="66dd4-117">Note the value assigned to the **clientCredentialType** attribute.</span></span> <span data-ttu-id="66dd4-118">実際の値は、使用されているモード (トランスポートまたはメッセージ) に依存します。</span><span class="sxs-lookup"><span data-stu-id="66dd4-118">The actual value depends on which mode is used, transport or message.</span></span>

<span data-ttu-id="66dd4-119">次の XML コードは、メッセージ セキュリティを使用し、クライアントの認証に証明書を要求するクライアントの構成を示します。</span><span class="sxs-lookup"><span data-stu-id="66dd4-119">The following XML code shows configuration for a client using message security and requiring a certificate to authenticate the client.</span></span>

```xml
<security mode="Message">
    <transport clientCredentialType="Windows" proxyCredentialType="None"
        realm="" />
     <message clientCredentialType="Certificate" negotiateServiceCredential="true"
    algorithmSuite="Default" establishSecurityContext="true" />
</security>
```

## <a name="example-tcp-transport-mode-with-certificate-as-client-credential"></a><span data-ttu-id="66dd4-120">例: クライアント資格情報としての証明書による TCP トランスポート モード</span><span class="sxs-lookup"><span data-stu-id="66dd4-120">Example: TCP Transport Mode with Certificate as Client Credential</span></span>

<span data-ttu-id="66dd4-121">この例では、セキュリティ モードを "Transport (トランスポート)" モードに設定し、クライアント資格情報の値を X.509 証明書に設定します。</span><span class="sxs-lookup"><span data-stu-id="66dd4-121">This example sets the security mode to Transport mode and sets the client credential value to an X.509 certificate.</span></span> <span data-ttu-id="66dd4-122">次の手順では、クライアントでクライアント資格情報の値をコードと構成を使用して設定する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="66dd4-122">The following procedures demonstrate how to set the client credential value on the client in code and configuration.</span></span> <span data-ttu-id="66dd4-123">これは、 [ServiceModel メタデータユーティリティツール (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md)を使用して、サービスからメタデータ (コードと構成) を返すことを前提としています。</span><span class="sxs-lookup"><span data-stu-id="66dd4-123">This assumes that you have used the [ServiceModel Metadata Utility Tool (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md) to return the metadata (code and configuration) from the service.</span></span> <span data-ttu-id="66dd4-124">詳細については、「[方法: クライアントを作成](how-to-create-a-wcf-client.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="66dd4-124">For more information, see [How to: Create a Client](how-to-create-a-wcf-client.md).</span></span>

### <a name="to-specify-the-client-credential-value-on-the-client-in-code"></a><span data-ttu-id="66dd4-125">クライアントでクライアント資格情報の値をコードによって指定するには</span><span class="sxs-lookup"><span data-stu-id="66dd4-125">To specify the client credential value on the client in code</span></span>

1. <span data-ttu-id="66dd4-126">[ServiceModel メタデータユーティリティツール (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md)を使用して、サービスからコードと構成を生成します。</span><span class="sxs-lookup"><span data-stu-id="66dd4-126">Use the [ServiceModel Metadata Utility Tool (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md) to generate code and configuration from the service.</span></span>

2. <span data-ttu-id="66dd4-127">生成されたコードを使用して、WCF クライアントのインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="66dd4-127">Create an instance of the WCF client using the generated code.</span></span>

3. <span data-ttu-id="66dd4-128">クライアント クラスで、<xref:System.ServiceModel.ClientBase%601.ClientCredentials%2A> クラスの <xref:System.ServiceModel.ClientBase%601> プロパティを適切な値に設定します。</span><span class="sxs-lookup"><span data-stu-id="66dd4-128">On the client class, set the <xref:System.ServiceModel.ClientBase%601.ClientCredentials%2A> property of the <xref:System.ServiceModel.ClientBase%601> class to an appropriate value.</span></span> <span data-ttu-id="66dd4-129">この例では、<xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A> クラスの <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential> メソッドを使用して、このプロパティを X.509 証明書に設定します。</span><span class="sxs-lookup"><span data-stu-id="66dd4-129">This example sets the property to an X.509 certificate using the <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A> method of the <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential> class.</span></span>

     [!code-csharp[c_TcpService#4](../../../samples/snippets/csharp/VS_Snippets_CFX/c_tcpservice/cs/source.cs#4)]
     [!code-vb[c_TcpService#4](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_tcpservice/vb/source.vb#4)]

     <span data-ttu-id="66dd4-130"><xref:System.Security.Cryptography.X509Certificates.X509FindType> クラスの任意の列挙体を使用できます。</span><span class="sxs-lookup"><span data-stu-id="66dd4-130">You can use any of the enumerations of the <xref:System.Security.Cryptography.X509Certificates.X509FindType> class.</span></span> <span data-ttu-id="66dd4-131">ここでは、有効期限が切れて証明書が変更された場合に備えて、サブジェクト名を使用しています。</span><span class="sxs-lookup"><span data-stu-id="66dd4-131">The subject name is used here in case the certificate is changed (due to an expiration date).</span></span> <span data-ttu-id="66dd4-132">サブジェクト名を使用することにより、インフラストラクチャは証明書を再検索できます。</span><span class="sxs-lookup"><span data-stu-id="66dd4-132">Using the subject name enables the infrastructure to find the certificate again.</span></span>

### <a name="to-specify-the-client-credential-value-on-the-client-in-configuration"></a><span data-ttu-id="66dd4-133">クライアントでクライアント資格情報の値を構成によって指定するには</span><span class="sxs-lookup"><span data-stu-id="66dd4-133">To specify the client credential value on the client in configuration</span></span>

1. <span data-ttu-id="66dd4-134">要素 [\<behavior>](../configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) に要素を追加 [\<behaviors>](../configure-apps/file-schema/wcf/behaviors.md) します。</span><span class="sxs-lookup"><span data-stu-id="66dd4-134">Add a [\<behavior>](../configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) element to the [\<behaviors>](../configure-apps/file-schema/wcf/behaviors.md) element.</span></span>

2. <span data-ttu-id="66dd4-135">要素 [\<clientCredentials>](../configure-apps/file-schema/wcf/clientcredentials.md) に要素を追加 [\<behaviors>](../configure-apps/file-schema/wcf/behaviors.md) します。</span><span class="sxs-lookup"><span data-stu-id="66dd4-135">Add a [\<clientCredentials>](../configure-apps/file-schema/wcf/clientcredentials.md) element to the [\<behaviors>](../configure-apps/file-schema/wcf/behaviors.md) element.</span></span> <span data-ttu-id="66dd4-136">`name` 属性 (必須) を適切な値に必ず設定してください。</span><span class="sxs-lookup"><span data-stu-id="66dd4-136">Be sure to set the required `name` attribute to an appropriate value.</span></span>

3. <span data-ttu-id="66dd4-137">要素 [\<clientCertificate>](../configure-apps/file-schema/wcf/clientcertificate-of-servicecredentials.md) に要素を追加 [\<clientCredentials>](../configure-apps/file-schema/wcf/clientcredentials.md) します。</span><span class="sxs-lookup"><span data-stu-id="66dd4-137">Add a [\<clientCertificate>](../configure-apps/file-schema/wcf/clientcertificate-of-servicecredentials.md) element to the [\<clientCredentials>](../configure-apps/file-schema/wcf/clientcredentials.md) element.</span></span>

4. <span data-ttu-id="66dd4-138">次のコードに示すように、`storeLocation`、`storeName`、`x509FindType`、および `findValue` の各属性を適切な値に設定します。</span><span class="sxs-lookup"><span data-stu-id="66dd4-138">Set the following attributes to appropriate values: `storeLocation`, `storeName`, `x509FindType`, and `findValue`, as shown in the following code.</span></span> <span data-ttu-id="66dd4-139">証明書の詳細については、「[証明書の使用](./feature-details/working-with-certificates.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="66dd4-139">For more information about certificates, see [Working with Certificates](./feature-details/working-with-certificates.md).</span></span>

    ```xml
    <behaviors>
       <endpointBehaviors>
          <behavior name="endpointCredentialBehavior">
            <clientCredentials>
              <clientCertificate findValue="Contoso.com"
                                 storeLocation="LocalMachine"
                                 storeName="TrustedPeople"
                                 x509FindType="FindBySubjectName" />
            </clientCredentials>
          </behavior>
       </endpointBehaviors>
    </behaviors>
    ```

5. <span data-ttu-id="66dd4-140">クライアントを構成するときは、次のコードに示すように、`behaviorConfiguration` 要素の `<endpoint>` 属性を設定して動作を指定します。</span><span class="sxs-lookup"><span data-stu-id="66dd4-140">When configuring the client, specify the behavior by setting the `behaviorConfiguration` attribute of the `<endpoint>` element, as shown in the following code.</span></span> <span data-ttu-id="66dd4-141">エンドポイント要素は要素の子です [\<client>](../configure-apps/file-schema/wcf/client.md) 。</span><span class="sxs-lookup"><span data-stu-id="66dd4-141">The endpoint element is a child of the [\<client>](../configure-apps/file-schema/wcf/client.md) element.</span></span> <span data-ttu-id="66dd4-142">また、`bindingConfiguration` 属性をクライアントのバインディングに設定することにより、バインド構成の名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="66dd4-142">Also, specify the name of the binding configuration by setting the `bindingConfiguration` attribute to the binding for the client.</span></span> <span data-ttu-id="66dd4-143">生成された構成ファイルを使用している場合は、バインディングの名前は自動的に生成されます。</span><span class="sxs-lookup"><span data-stu-id="66dd4-143">If you are using a generated configuration file, the binding's name is automatically generated.</span></span> <span data-ttu-id="66dd4-144">この例では、名前は `"tcpBindingWithCredential"` です。</span><span class="sxs-lookup"><span data-stu-id="66dd4-144">In this example, the name is `"tcpBindingWithCredential"`.</span></span>

    ```xml
    <client>
      <endpoint name =""
                address="net.tcp://contoso.com:8036/aloha"
                binding="netTcpBinding"
                bindingConfiguration="tcpBindingWithCredential"
                behaviorConfiguration="endpointCredentialBehavior" />
    </client>
    ```

## <a name="see-also"></a><span data-ttu-id="66dd4-145">関連項目</span><span class="sxs-lookup"><span data-stu-id="66dd4-145">See also</span></span>

- <xref:System.ServiceModel.NetTcpBinding>
- <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential.SetCertificate%2A>
- <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential>
- <xref:System.ServiceModel.ClientBase%601>
- <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential>
- [<span data-ttu-id="66dd4-146">WCF セキュリティのプログラミング</span><span class="sxs-lookup"><span data-stu-id="66dd4-146">Programming WCF Security</span></span>](./feature-details/programming-wcf-security.md)
- [<span data-ttu-id="66dd4-147">資格情報の種類の選択</span><span class="sxs-lookup"><span data-stu-id="66dd4-147">Selecting a Credential Type</span></span>](./feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="66dd4-148">ServiceModel メタデータ ユーティリティ ツール (Svcutil.exe)</span><span class="sxs-lookup"><span data-stu-id="66dd4-148">ServiceModel Metadata Utility Tool (Svcutil.exe)</span></span>](servicemodel-metadata-utility-tool-svcutil-exe.md)
- [<span data-ttu-id="66dd4-149">証明書の使用</span><span class="sxs-lookup"><span data-stu-id="66dd4-149">Working with Certificates</span></span>](./feature-details/working-with-certificates.md)
- [<span data-ttu-id="66dd4-150">方法: クライアントを作成する</span><span class="sxs-lookup"><span data-stu-id="66dd4-150">How to: Create a Client</span></span>](how-to-create-a-wcf-client.md)
- [\<netTcpBinding>](../configure-apps/file-schema/wcf/nettcpbinding.md)
- [\<security>](../configure-apps/file-schema/wcf/security-of-nettcpbinding.md)
- [\<message>](../configure-apps/file-schema/wcf/message-element-of-nettcpbinding.md)
- [\<behavior>](../configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)
- [\<behaviors>](../configure-apps/file-schema/wcf/behaviors.md)
- [\<clientCertificate>](../configure-apps/file-schema/wcf/clientcertificate-of-servicecredentials.md)
- [\<clientCredentials>](../configure-apps/file-schema/wcf/clientcredentials.md)
