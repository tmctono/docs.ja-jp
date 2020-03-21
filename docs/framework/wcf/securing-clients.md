---
title: クライアントのセキュリティ保護
ms.date: 03/30/2017
helpviewer_keywords:
- clients [WCF], security considerations
ms.assetid: 44c8578c-9a5b-4acd-8168-1c30a027c4c5
ms.openlocfilehash: bfb980e629ffb8f8543937a1850430c9bf6e9199
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79183127"
---
# <a name="securing-clients"></a><span data-ttu-id="ef603-102">クライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="ef603-102">Securing Clients</span></span>
<span data-ttu-id="ef603-103">WCF (WCF) では、サービスは、クライアントのセキュリティ要件を指示します。</span><span class="sxs-lookup"><span data-stu-id="ef603-103">In Windows Communication Foundation (WCF), the service dictates the security requirements for clients.</span></span> <span data-ttu-id="ef603-104">つまり、使用するセキュリティ モード、およびクライアントが資格情報を提供するかどうかは、サービスによって指定されます。</span><span class="sxs-lookup"><span data-stu-id="ef603-104">That is, the service specifies what security mode to use, and whether or not the client must provide a credential.</span></span> <span data-ttu-id="ef603-105">そのため、クライアントをセキュリティで保護するプロセスは、サービスから取得したメタデータ (公開されている場合) を使用してクライアントを構築するという簡単なものになります。</span><span class="sxs-lookup"><span data-stu-id="ef603-105">The process of securing a client, therefore, is simple: use the metadata obtained from the service (if it is published) and build a client.</span></span> <span data-ttu-id="ef603-106">クライアントを構成する方法は、メタデータによって指定されます。</span><span class="sxs-lookup"><span data-stu-id="ef603-106">The metadata specifies how to configure the client.</span></span> <span data-ttu-id="ef603-107">クライアントが資格情報を提供することをサービスが要求する場合、要件に適した資格情報を取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ef603-107">If the service requires that the client supply a credential, then you must obtain a credential that fits the requirement.</span></span> <span data-ttu-id="ef603-108">ここでは、このプロセスについて詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="ef603-108">This topic discusses the process in further detail.</span></span> <span data-ttu-id="ef603-109">セキュリティで保護されたサービスの作成の詳細については、「[サービスのセキュリティ保護](securing-services.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ef603-109">For more information about creating a secure service, see [Securing Services](securing-services.md).</span></span>  
  
## <a name="the-service-specifies-security"></a><span data-ttu-id="ef603-110">サービスによるセキュリティの指定</span><span class="sxs-lookup"><span data-stu-id="ef603-110">The Service Specifies Security</span></span>  
 <span data-ttu-id="ef603-111">既定では、WCF バインドではセキュリティ機能が有効になっています。</span><span class="sxs-lookup"><span data-stu-id="ef603-111">By default, WCF bindings have security features enabled.</span></span> <span data-ttu-id="ef603-112">(例外は<xref:System.ServiceModel.BasicHttpBinding>.)したがって、WCF を使用してサービスを作成した場合、認証、機密性、および整合性を確保するためにセキュリティを実装する可能性が高くなります。</span><span class="sxs-lookup"><span data-stu-id="ef603-112">(The exception is the <xref:System.ServiceModel.BasicHttpBinding>.) Therefore, if the service was created using WCF, there is a greater chance that it will implement security to ensure authentication, confidentiality, and integrity.</span></span> <span data-ttu-id="ef603-113">この場合、サービスが提供するメタデータによって、セキュリティで保護された通信チャネルの確立に必要なものが示されます。</span><span class="sxs-lookup"><span data-stu-id="ef603-113">In that case, the metadata the service provides will indicate what it requires to establish a secure communication channel.</span></span> <span data-ttu-id="ef603-114">サービス メタデータにセキュリティ要件がまったく含まれていない場合には、サービスでセキュリティ スキーム (SSL (Secure Sockets Layer) over HTTP など) を強制する方法はありません。</span><span class="sxs-lookup"><span data-stu-id="ef603-114">If the service metadata does not include any security requirements, there is no way to impose a security scheme, such as Secure Sockets Layer (SSL) over HTTP, on a service.</span></span> <span data-ttu-id="ef603-115">ただし、サービスがクライアントに資格情報の提供を求める場合は、クライアントの開発者、展開担当者、または管理者は、クライアントがサービスに対して認証を受けるときに実際に使用する資格情報を提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ef603-115">If, however, the service requires the client to supply a credential, then the client developer, deployer, or administrator must supply the actual credential that the client will use to authenticate itself to the service.</span></span>  
  
## <a name="obtaining-metadata"></a><span data-ttu-id="ef603-116">メタデータの取得</span><span class="sxs-lookup"><span data-stu-id="ef603-116">Obtaining Metadata</span></span>  
 <span data-ttu-id="ef603-117">クライアントを作成する場合、最初の手順はクライアントが通信を行うサービスからメタデータを取得することです。</span><span class="sxs-lookup"><span data-stu-id="ef603-117">When creating a client, the first step is to obtain the metadata for the service that the client will communicate with.</span></span> <span data-ttu-id="ef603-118">これは、次の 2 つの方法で行うことができます。</span><span class="sxs-lookup"><span data-stu-id="ef603-118">This can be done in two ways.</span></span> <span data-ttu-id="ef603-119">まず、サービスがメタデータ交換 (MEX) エンドポイントを公開するか、そのメタデータを HTTP または HTTPS 経由で使用できるようにする場合は、クライアントと構成ファイルの両方のコード ファイルを生成する[ServiceModel メタデータ ユーティリティ ツール (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md)を使用してメタデータをダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="ef603-119">First, if the service publishes a metadata exchange (MEX) endpoint or makes its metadata available over HTTP or HTTPS, you can download the metadata using the [ServiceModel Metadata Utility Tool (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md), which generates both code files for a client as well as a configuration file.</span></span> <span data-ttu-id="ef603-120">(ツールの使用の詳細については[、「WCF クライアントを使用したサービスへのアクセス](accessing-services-using-a-wcf-client.md)」を参照してください)。サービスが MEX エンドポイントを公開せず、そのメタデータを HTTP または HTTPS で使用できない場合は、セキュリティ要件とメタデータに関するドキュメントについてサービス作成者に問い合わせる必要があります。</span><span class="sxs-lookup"><span data-stu-id="ef603-120">(For more information about using the tool, see [Accessing Services Using a WCF Client](accessing-services-using-a-wcf-client.md).) If the service does not publish a MEX endpoint and also does not make its metadata available over HTTP or HTTPS, you must contact the service creator for documentation that describes the security requirements and the metadata.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="ef603-121">メタデータが信頼されたソースのものであり、改ざんされていないことを確認することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="ef603-121">It is recommended that the metadata come from a trusted source and that it not be tampered with.</span></span> <span data-ttu-id="ef603-122">HTTP プロトコルを使用して取得したメタデータはクリア テキストで送信されるため、改ざんされるおそれがあります。</span><span class="sxs-lookup"><span data-stu-id="ef603-122">Metadata retrieved using the HTTP protocol is sent in clear text and can be tampered with.</span></span> <span data-ttu-id="ef603-123">サービスで <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpsGetEnabled%2A> プロパティおよび <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpsGetUrl%2A> プロパティを使用している場合は、サービス作成者から提供された URL で、HTTPS プロトコルを使用してデータをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="ef603-123">If the service uses the <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpsGetEnabled%2A> and <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpsGetUrl%2A> properties, use the URL the service creator supplied to download the data using the HTTPS protocol.</span></span>  
  
## <a name="validating-security"></a><span data-ttu-id="ef603-124">セキュリティの検証</span><span class="sxs-lookup"><span data-stu-id="ef603-124">Validating Security</span></span>  
 <span data-ttu-id="ef603-125">メタデータのソースは、信頼されたソースと信頼関係のないソースの 2 つに大きく分けられます。</span><span class="sxs-lookup"><span data-stu-id="ef603-125">Metadata sources can be divided into two broad categories: trust sources and untrusted sources.</span></span> <span data-ttu-id="ef603-126">ソースを信頼しており、そのソースのセキュリティで保護された MEX エンドポイントからクライアント コードとその他のメタデータをダウンロードしている場合、何の懸念もなく、クライアントをビルドし、適切な資格情報を提供して実行できます。</span><span class="sxs-lookup"><span data-stu-id="ef603-126">If you trust a source and have downloaded the client code and other metadata from that source's secure MEX endpoint, then you can build the client, supply it with the right credentials, and run it with no other concerns.</span></span>  
  
 <span data-ttu-id="ef603-127">ただし、ほとんど未知のソースからクライアントとメタデータをダウンロードする場合は、コードで使用しているセキュリティ対策を検証する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ef603-127">However, if you elect to download a client and metadata from a source that you know little about, be sure to validate the security measures the code uses.</span></span> <span data-ttu-id="ef603-128">たとえば、サービスにより (最低でも) 機密性と整合性とが要求されていない場合は、個人情報や財務情報を送信するクライアントを作成するようなことは絶対に避けてください。</span><span class="sxs-lookup"><span data-stu-id="ef603-128">For example, you must not simply create a client that sends your personal or financial information to a service unless the service demands confidentiality and integrity (at the very least).</span></span> <span data-ttu-id="ef603-129">そのような情報は、その情報が公開されるので、サービスの所有者を信頼する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ef603-129">You should trust the owner of the service to the extent that you are willing to disclose such information, because such information will be visible to them.</span></span>  
  
 <span data-ttu-id="ef603-130">したがって、信頼できないソースから受け取ったコードとメタデータを使用する場合には、それがこちらの必要とするセキュリティ レベルを満たしていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ef603-130">As a rule, therefore, when using code and metadata from an untrusted source, check the code and metadata to ensure that it meets the security level that you require.</span></span>  
  
## <a name="setting-a-client-credential"></a><span data-ttu-id="ef603-131">クライアント資格情報の設定</span><span class="sxs-lookup"><span data-stu-id="ef603-131">Setting a Client Credential</span></span>  
 <span data-ttu-id="ef603-132">クライアントへの資格情報の設定には、次の 2 つの手順があります。</span><span class="sxs-lookup"><span data-stu-id="ef603-132">Setting a client credential on a client consists of two steps:</span></span>  
  
1. <span data-ttu-id="ef603-133">サービスに必要な*クライアント資格情報の種類*を決定します。</span><span class="sxs-lookup"><span data-stu-id="ef603-133">Determine the *client credential type* the service requires.</span></span> <span data-ttu-id="ef603-134">これは、2 つある方法のどちらかによって行います。</span><span class="sxs-lookup"><span data-stu-id="ef603-134">This is accomplished by one of two methods.</span></span> <span data-ttu-id="ef603-135">1 つ目の方法として、サービス作成者からドキュメントを入手している場合は、このドキュメントにサービスが要求するクライアント資格情報の種類が示されています (クライアント資格情報の種類が指定されている場合)。</span><span class="sxs-lookup"><span data-stu-id="ef603-135">First, if you have documentation from the service creator, it should specify the client credential type (if any) the service requires.</span></span> <span data-ttu-id="ef603-136">2 番目の方法は Svcutil.exe ツールによって作成された構成ファイルしかない場合で、個々のバインディングを調べることで必要な資格情報の種類を特定できます。</span><span class="sxs-lookup"><span data-stu-id="ef603-136">Second, if you have only a configuration file generated by the Svcutil.exe tool, you can examine the individual bindings to determine what credential type is required.</span></span>  
  
2. <span data-ttu-id="ef603-137">実際のクライアント資格情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="ef603-137">Specify an actual client credential.</span></span> <span data-ttu-id="ef603-138">実際のクライアント資格情報は、型と区別するために*クライアント資格情報値*と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="ef603-138">The actual client credential is called a *client credential value* to distinguish it from the type.</span></span> <span data-ttu-id="ef603-139">たとえば、クライアント資格情報の種類として証明書が指定されている場合、サービスが信頼する証明機関によって発行された X.509 証明書を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ef603-139">For example, if the client credential type specifies a certificate, you must supply an X.509 certificate that is issued by a certification authority the service trusts.</span></span>  
  
### <a name="determining-the-client-credential-type"></a><span data-ttu-id="ef603-140">クライアント資格情報の種類の特定</span><span class="sxs-lookup"><span data-stu-id="ef603-140">Determining the Client Credential Type</span></span>  
 <span data-ttu-id="ef603-141">Svcutil.exe ツールが生成した構成ファイルがある場合は、[\<バインディング>](../configure-apps/file-schema/wcf/bindings.md)セクションを調べて、必要なクライアント資格情報の種類を確認します。</span><span class="sxs-lookup"><span data-stu-id="ef603-141">If you have the configuration file the Svcutil.exe tool generated, examine the [\<bindings>](../configure-apps/file-schema/wcf/bindings.md) section to determine what client credential type is required.</span></span> <span data-ttu-id="ef603-142">このセクション内には、セキュリティ要件を指定するバインド要素があります。</span><span class="sxs-lookup"><span data-stu-id="ef603-142">Within the section are binding elements that specify the security requirements.</span></span> <span data-ttu-id="ef603-143">具体的には、各\<バインディングのセキュリティ>要素を調べます。</span><span class="sxs-lookup"><span data-stu-id="ef603-143">Specifically, examine the \<security> Element of each binding.</span></span> <span data-ttu-id="ef603-144">この要素には `mode` 属性が含まれており、3 つの値のいずれか (`Message`、`Transport`、または `TransportWithMessageCredential`) に設定できます。</span><span class="sxs-lookup"><span data-stu-id="ef603-144">That element includes the `mode` attribute, which you can set to one of three possible values (`Message`, `Transport`, or `TransportWithMessageCredential`).</span></span> <span data-ttu-id="ef603-145">この属性の値によってモードが決定され、このモードによってどの子要素が有効なのかが決定されます。</span><span class="sxs-lookup"><span data-stu-id="ef603-145">The value of the attribute determines the mode, and the mode determines which of the child elements is significant.</span></span>  
  
 <span data-ttu-id="ef603-146">要素`<security>`には、 または`<transport>`要素`<message>`、またはその両方を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="ef603-146">The `<security>` element can contain either a `<transport>` or `<message>` element, or both.</span></span> <span data-ttu-id="ef603-147">セキュリティ モードと一致する要素が有効な要素です。</span><span class="sxs-lookup"><span data-stu-id="ef603-147">The significant element is the one that matches the security mode.</span></span> <span data-ttu-id="ef603-148">たとえば、次のコードでは、セキュリティ モードを `"Message"`、`<message>` 要素のクライアント資格情報の種類を `"Certificate"` に指定しています。</span><span class="sxs-lookup"><span data-stu-id="ef603-148">For example, the following code specifies that the security mode is `"Message"`, and the client credential type for the `<message>` element is `"Certificate"`.</span></span> <span data-ttu-id="ef603-149">この場合、`<transport>` 要素は無視できます。</span><span class="sxs-lookup"><span data-stu-id="ef603-149">In this case, the `<transport>` element can be ignored.</span></span> <span data-ttu-id="ef603-150">ただし、`<message>` 要素で X.509 証明書を提示する必要があることが指定されています。</span><span class="sxs-lookup"><span data-stu-id="ef603-150">However, the `<message>` element specifies that an X.509 certificate must be supplied.</span></span>  

```xml  
<wsHttpBinding>  
    <binding name="WSHttpBinding_ICalculator">  
       <security mode="Message">  
           <transport clientCredentialType="Windows"
                      realm="" />  
           <message clientCredentialType="Certificate"
                    negotiateServiceCredential="true"  
                    algorithmSuite="Default"
                    establishSecurityContext="true" />  
       </security>  
    </binding>  
</wsHttpBinding>  
```  

 <span data-ttu-id="ef603-151">次の例に示すように、`clientCredentialType` 属性が `"Windows"` に設定されている場合は、実際の資格情報の値を指定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="ef603-151">Note that if the `clientCredentialType` attribute is set to `"Windows"`, as shown in the following example, you do not need to supply an actual credential value.</span></span> <span data-ttu-id="ef603-152">これは、Windows 統合セキュリティでは、クライアントを実行しているユーザーの実際の資格情報 (Kerberos トークン) が提供されるためです。</span><span class="sxs-lookup"><span data-stu-id="ef603-152">This is because the Windows integrated security provides the actual credential (a Kerberos token) of the person who is running the client.</span></span>  
  
```xml  
<security mode="Message">  
    <transport clientCredentialType="Windows "
        realm="" />  
</security>  
```  
  
### <a name="setting-the-client-credential-value"></a><span data-ttu-id="ef603-153">クライアント資格情報の値の設定</span><span class="sxs-lookup"><span data-stu-id="ef603-153">Setting the Client Credential Value</span></span>  
 <span data-ttu-id="ef603-154">クライアントが資格情報を提供する必要があると特定された場合は、クライアントを構成する適切なメソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="ef603-154">If it is determined that the client must supply a credential, use the appropriate method to configure the client.</span></span> <span data-ttu-id="ef603-155">たとえば、クライアント証明書を設定するには、<xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A> メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="ef603-155">For example, to set a client certificate, use the <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A> method.</span></span>  
  
 <span data-ttu-id="ef603-156">X.509 証明書は広く使用されている資格情報の形式です。</span><span class="sxs-lookup"><span data-stu-id="ef603-156">A common form of credential is the X.509 certificate.</span></span> <span data-ttu-id="ef603-157">資格情報は次の 2 つの方法で提供できます。</span><span class="sxs-lookup"><span data-stu-id="ef603-157">You can supply the credential in two ways:</span></span>  
  
- <span data-ttu-id="ef603-158">クライアント コードで (`SetCertificate` メソッドを使用して) プログラミングする方法。</span><span class="sxs-lookup"><span data-stu-id="ef603-158">By programming it in your client code (using the `SetCertificate` method).</span></span>  
  
 <span data-ttu-id="ef603-159">クライアント[\<の](../configure-apps/file-schema/wcf/behaviors.md)構成ファイルの>セクションの動作を追加し、`clientCredentials`要素を使用します (下図)。</span><span class="sxs-lookup"><span data-stu-id="ef603-159">By adding a [\<behaviors>](../configure-apps/file-schema/wcf/behaviors.md) section of the configuration file for the client and using the `clientCredentials` element (shown below).</span></span>  
  
#### <a name="setting-a-clientcredentials-value-in-code"></a><span data-ttu-id="ef603-160">クライアント資格情報\<の設定 コード内の資格情報>値</span><span class="sxs-lookup"><span data-stu-id="ef603-160">Setting a \<clientCredentials> Value in Code</span></span>  
 <span data-ttu-id="ef603-161">コード内の[\<クライアント資格情報>](../configure-apps/file-schema/wcf/clientcredentials.md)値を設定するには、クラスのプロパティに<xref:System.ServiceModel.ClientBase%601.ClientCredentials%2A>アクセスする<xref:System.ServiceModel.ClientBase%601>必要があります。</span><span class="sxs-lookup"><span data-stu-id="ef603-161">To set a [\<clientCredentials>](../configure-apps/file-schema/wcf/clientcredentials.md) value in code, you must access the <xref:System.ServiceModel.ClientBase%601.ClientCredentials%2A> property of the <xref:System.ServiceModel.ClientBase%601> class.</span></span> <span data-ttu-id="ef603-162">このプロパティは、次の表に示すように、各種の資格情報の種類にアクセスできる <xref:System.ServiceModel.Description.ClientCredentials> オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="ef603-162">The property returns a <xref:System.ServiceModel.Description.ClientCredentials> object that allows access to various credential types, as shown in the following table.</span></span>  
  
|<span data-ttu-id="ef603-163">ClientCredential プロパティ</span><span class="sxs-lookup"><span data-stu-id="ef603-163">ClientCredential Property</span></span>|<span data-ttu-id="ef603-164">説明</span><span class="sxs-lookup"><span data-stu-id="ef603-164">Description</span></span>|<span data-ttu-id="ef603-165">Notes</span><span class="sxs-lookup"><span data-stu-id="ef603-165">Notes</span></span>|  
|-------------------------------|-----------------|-----------|  
|<xref:System.ServiceModel.Description.ClientCredentials.ClientCertificate%2A>|<span data-ttu-id="ef603-166"><xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential> を返します</span><span class="sxs-lookup"><span data-stu-id="ef603-166">Returns an <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential></span></span>|<span data-ttu-id="ef603-167">クライアントがサービスに対して自身を認証するために提供する X.509 証明書を表します。</span><span class="sxs-lookup"><span data-stu-id="ef603-167">Represents an X.509 certificate provided by the client to authenticate itself to the service.</span></span>|  
|<xref:System.ServiceModel.Description.ClientCredentials.HttpDigest%2A>|<span data-ttu-id="ef603-168"><xref:System.ServiceModel.Security.HttpDigestClientCredential> を返します</span><span class="sxs-lookup"><span data-stu-id="ef603-168">Returns an <xref:System.ServiceModel.Security.HttpDigestClientCredential></span></span>|<span data-ttu-id="ef603-169">HTTP ダイジェスト資格情報を表します。</span><span class="sxs-lookup"><span data-stu-id="ef603-169">Represents an HTTP digest credential.</span></span> <span data-ttu-id="ef603-170">この資格情報は、ユーザー名とパスワードのハッシュです。</span><span class="sxs-lookup"><span data-stu-id="ef603-170">The credential is a hash of the user name and password.</span></span>|  
|<xref:System.ServiceModel.Description.ClientCredentials.IssuedToken%2A>|<span data-ttu-id="ef603-171"><xref:System.ServiceModel.Security.IssuedTokenClientCredential> を返します</span><span class="sxs-lookup"><span data-stu-id="ef603-171">Returns an <xref:System.ServiceModel.Security.IssuedTokenClientCredential></span></span>|<span data-ttu-id="ef603-172">フェデレーション シナリオで通常使用される、セキュリティ トークン サービスによって発行されるカスタム セキュリティ トークンを表します。</span><span class="sxs-lookup"><span data-stu-id="ef603-172">Represents a custom security token issued by a Security Token Service, commonly used in federation scenarios.</span></span>|  
|<xref:System.ServiceModel.Description.ClientCredentials.Peer%2A>|<span data-ttu-id="ef603-173"><xref:System.ServiceModel.Security.PeerCredential> を返します</span><span class="sxs-lookup"><span data-stu-id="ef603-173">Returns a <xref:System.ServiceModel.Security.PeerCredential></span></span>|<span data-ttu-id="ef603-174">Windows ドメインのピア メッシュに参加するためのピア資格情報を表します。</span><span class="sxs-lookup"><span data-stu-id="ef603-174">Represents a Peer credential for participation in a Peer mesh on a Windows domain.</span></span>|  
|<xref:System.ServiceModel.Description.ClientCredentials.ServiceCertificate%2A>|<span data-ttu-id="ef603-175"><xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential> を返します</span><span class="sxs-lookup"><span data-stu-id="ef603-175">Returns an <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential></span></span>|<span data-ttu-id="ef603-176">帯域外ネゴシエーションでサービスによって提供される X.509 証明書を表します。</span><span class="sxs-lookup"><span data-stu-id="ef603-176">Represents an X.509 certificate provided by the service in an out-of-band negotiation.</span></span>|  
|<xref:System.ServiceModel.Description.ClientCredentials.UserName%2A>|<span data-ttu-id="ef603-177"><xref:System.ServiceModel.Security.UserNamePasswordClientCredential> を返します</span><span class="sxs-lookup"><span data-stu-id="ef603-177">Returns a <xref:System.ServiceModel.Security.UserNamePasswordClientCredential></span></span>|<span data-ttu-id="ef603-178">ユーザー名とパスワードのペアを表します。</span><span class="sxs-lookup"><span data-stu-id="ef603-178">Represents a user name and password pair.</span></span>|  
|<xref:System.ServiceModel.Description.ClientCredentials.Windows%2A>|<span data-ttu-id="ef603-179"><xref:System.ServiceModel.Security.WindowsClientCredential> を返します</span><span class="sxs-lookup"><span data-stu-id="ef603-179">Returns a <xref:System.ServiceModel.Security.WindowsClientCredential></span></span>|<span data-ttu-id="ef603-180">Windows クライアントの資格情報 (Kerberos 資格情報) を表します。</span><span class="sxs-lookup"><span data-stu-id="ef603-180">Represents a Windows client credential (a Kerberos credential).</span></span> <span data-ttu-id="ef603-181">このクラスのプロパティは読み取り専用です。</span><span class="sxs-lookup"><span data-stu-id="ef603-181">The properties of the class are read-only.</span></span>|  
  
#### <a name="setting-a-clientcredentials-value-in-configuration"></a><span data-ttu-id="ef603-182">クライアントの\<設定構成でのクライアント資格情報>値</span><span class="sxs-lookup"><span data-stu-id="ef603-182">Setting a \<clientCredentials> Value in Configuration</span></span>  
 <span data-ttu-id="ef603-183">資格情報の値は、エンドポイントの動作を[\<clientCredentials>](../configure-apps/file-schema/wcf/clientcredentials.md)要素の子要素として使用して指定します。</span><span class="sxs-lookup"><span data-stu-id="ef603-183">Credential values are specified by using an endpoint behavior as child elements of the [\<clientCredentials>](../configure-apps/file-schema/wcf/clientcredentials.md) element.</span></span> <span data-ttu-id="ef603-184">使用される要素は、クライアントの資格情報の種類によって異なります。</span><span class="sxs-lookup"><span data-stu-id="ef603-184">The element used depends on the client credential type.</span></span> <span data-ttu-id="ef603-185">たとえば、次の例は、<[ \<clientCertificate>](../configure-apps/file-schema/wcf/clientcertificate-of-clientcredentials-element.md)を使用して X.509 証明書を設定する構成を示しています。</span><span class="sxs-lookup"><span data-stu-id="ef603-185">For example, the following example shows the configuration to set an X.509 certificate using the <[\<clientCertificate>](../configure-apps/file-schema/wcf/clientcertificate-of-clientcredentials-element.md).</span></span>  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <endpointBehaviors>
        <behavior name="myEndpointBehavior">  
          <clientCredentials>  
            <clientCertificate findvalue="myMachineName"
            storeLocation="Current" X509FindType="FindBySubjectName" />  
          </clientCredentials>  
        </behavior>
      </endpointBehaviors>
    </behaviors>
  </system.serviceModel>  
</configuration>  
```  
  
 <span data-ttu-id="ef603-186">構成でクライアント資格情報を設定するには、構成ファイルに[\<endpointBehaviors>](../configure-apps/file-schema/wcf/endpointbehaviors.md)要素を追加します。</span><span class="sxs-lookup"><span data-stu-id="ef603-186">To set the client credential in configuration, add an [\<endpointBehaviors>](../configure-apps/file-schema/wcf/endpointbehaviors.md) element to the configuration file.</span></span> <span data-ttu-id="ef603-187">さらに、追加された動作要素は、次の例に示すように、クライアント>`behaviorConfiguration`要素の[\<エンドポイント>の\<](../configure-apps/file-schema/wcf/endpoint-of-client.md)属性を使用して、サービスのエンドポイントにリンクする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ef603-187">Additionally, the added behavior element must be linked to the service's endpoint using the `behaviorConfiguration` attribute of the [\<endpoint> of \<client>](../configure-apps/file-schema/wcf/endpoint-of-client.md) element as shown in the following example.</span></span> <span data-ttu-id="ef603-188">`behaviorConfiguration` 属性の値は、動作の `name` 属性の値と一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ef603-188">The value of the `behaviorConfiguration` attribute must match the value of the behavior `name` attribute.</span></span>  

```xml
<configuration>
  <system.serviceModel>
    <client>
      <endpoint address="http://localhost/servicemodelsamples/service.svc"
                binding="wsHttpBinding"
                bindingConfiguration="Binding1"
                behaviorConfiguration="myEndpointBehavior"
                contract="Microsoft.ServiceModel.Samples.ICalculator" />
    </client>
  </system.serviceModel>
</configuration>
```
  
> [!NOTE]
> <span data-ttu-id="ef603-189">クライアント資格情報の値の中には、アプリケーション構成ファイルを使用して設定できないものがあります (ユーザー名とパスワードや、Windows ユーザーとパスワードの値など)。</span><span class="sxs-lookup"><span data-stu-id="ef603-189">Some of the client credential values cannot be set using application configuration files, for example, user name and password, or Windows user and password values.</span></span> <span data-ttu-id="ef603-190">このような資格情報の値は、コードでのみ指定できます。</span><span class="sxs-lookup"><span data-stu-id="ef603-190">Such credential values can be specified only in code.</span></span>  
  
 <span data-ttu-id="ef603-191">クライアント資格情報の設定の詳細については、「方法[: クライアント資格情報の値を指定する](how-to-specify-client-credential-values.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ef603-191">For more information about setting the client credential, see [How to: Specify Client Credential Values](how-to-specify-client-credential-values.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ef603-192">次の構成例に示すように、`ClientCredentialType` が `SecurityMode` に設定されている場合、`"TransportWithMessageCredential",` は無視されます。</span><span class="sxs-lookup"><span data-stu-id="ef603-192">`ClientCredentialType` is ignored when `SecurityMode` is set to `"TransportWithMessageCredential",` as shown in the following sample configuration.</span></span>  
  
```xml  
<wsHttpBinding>  
    <binding name="PingBinding">  
        <security mode="TransportWithMessageCredential"  >  
           <message  clientCredentialType="UserName"
               establishSecurityContext="false"
               negotiateServiceCredential="false" />  
           <transport clientCredentialType="Certificate"  />  
         </security>  
    </binding>  
</wsHttpBinding>  
```  
  
## <a name="see-also"></a><span data-ttu-id="ef603-193">関連項目</span><span class="sxs-lookup"><span data-stu-id="ef603-193">See also</span></span>

- <xref:System.ServiceModel.ClientBase%601.ClientCredentials%2A>
- <xref:System.ServiceModel.ClientBase%601>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpsGetEnabled%2A>
- <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpsGetUrl%2A>
- [<span data-ttu-id="ef603-194">\<バインディング></span><span class="sxs-lookup"><span data-stu-id="ef603-194">\<bindings></span></span>](../configure-apps/file-schema/wcf/bindings.md)
- [<span data-ttu-id="ef603-195">構成エディター ツール (SvcConfigEditor.exe)</span><span class="sxs-lookup"><span data-stu-id="ef603-195">Configuration Editor Tool (SvcConfigEditor.exe)</span></span>](configuration-editor-tool-svcconfigeditor-exe.md)
- [<span data-ttu-id="ef603-196">サービスのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="ef603-196">Securing Services</span></span>](securing-services.md)
- [<span data-ttu-id="ef603-197">WCF クライアントを使用したサービスへのアクセス</span><span class="sxs-lookup"><span data-stu-id="ef603-197">Accessing Services Using a WCF Client</span></span>](accessing-services-using-a-wcf-client.md)
- [<span data-ttu-id="ef603-198">方法: クライアントの資格情報の値を指定する</span><span class="sxs-lookup"><span data-stu-id="ef603-198">How to: Specify Client Credential Values</span></span>](how-to-specify-client-credential-values.md)
- [<span data-ttu-id="ef603-199">ServiceModel メタデータ ユーティリティ ツール (Svcutil.exe)</span><span class="sxs-lookup"><span data-stu-id="ef603-199">ServiceModel Metadata Utility Tool (Svcutil.exe)</span></span>](servicemodel-metadata-utility-tool-svcutil-exe.md)
- [<span data-ttu-id="ef603-200">方法 : クライアントの資格情報の種類を指定する</span><span class="sxs-lookup"><span data-stu-id="ef603-200">How to: Specify the Client Credential Type</span></span>](how-to-specify-the-client-credential-type.md)
