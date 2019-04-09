---
title: <clientCredentials>
ms.date: 03/30/2017
ms.assetid: 1e6eef0d-a34e-4d74-b0f7-f65d2181858d
ms.openlocfilehash: ebe976df9af0c316e95a1e089412e57a575a6df1
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59157236"
---
# <a name="clientcredentials"></a><span data-ttu-id="5edf0-101">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="5edf0-101">\<clientCredentials></span></span>
<span data-ttu-id="5edf0-102">サービスに対するクライアントの認証に使用される資格情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="5edf0-102">Specifies the credentials used to authenticate the client to a service.</span></span>  
  
 <span data-ttu-id="5edf0-103">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="5edf0-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="5edf0-104">\<<behaviors></span><span class="sxs-lookup"><span data-stu-id="5edf0-104">\<behaviors></span></span>  
<span data-ttu-id="5edf0-105">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="5edf0-105">\<endpointBehaviors></span></span>  
<span data-ttu-id="5edf0-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="5edf0-106">\<behavior></span></span>  
<span data-ttu-id="5edf0-107">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="5edf0-107">\<clientCredentials></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5edf0-108">構文</span><span class="sxs-lookup"><span data-stu-id="5edf0-108">Syntax</span></span>  
  
```xml  
<clientCredentials type="String"
                   supportInteractive="Boolean" >
  <clientCertificate>
  </clientCertificate>
  <digest>
  </digest>
  <isuedToken>
  </isuedToken>
  <peer>
  </peer>
  <serviceCertificate>
  </serviceCertificate>
  <windowsAuthentication>
  </windowsAuthentication>
</clientCredentials>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5edf0-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="5edf0-109">Attributes and Elements</span></span>  
 <span data-ttu-id="5edf0-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="5edf0-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5edf0-111">属性</span><span class="sxs-lookup"><span data-stu-id="5edf0-111">Attributes</span></span>  
  
|<span data-ttu-id="5edf0-112">属性</span><span class="sxs-lookup"><span data-stu-id="5edf0-112">Attribute</span></span>|<span data-ttu-id="5edf0-113">説明</span><span class="sxs-lookup"><span data-stu-id="5edf0-113">Description</span></span>|  
|---------------|-----------------|  
|`supportInteractive`|<span data-ttu-id="5edf0-114">実行時にクライアントの資格情報を選択する際に、対話型ユーザーを含めるかどうかを指定するブール値。</span><span class="sxs-lookup"><span data-stu-id="5edf0-114">A Boolean value that specifies whether an interactive user can be involved in selecting a client credential at runtime.</span></span> <span data-ttu-id="5edf0-115">既定値は `true` です。</span><span class="sxs-lookup"><span data-stu-id="5edf0-115">The default value is `true`.</span></span>|  
|`type`|<span data-ttu-id="5edf0-116">この設定要素の種類を指定する文字列です。</span><span class="sxs-lookup"><span data-stu-id="5edf0-116">A string that specifies the type of this configuration element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5edf0-117">子要素</span><span class="sxs-lookup"><span data-stu-id="5edf0-117">Child Elements</span></span>  
  
|<span data-ttu-id="5edf0-118">要素</span><span class="sxs-lookup"><span data-stu-id="5edf0-118">Element</span></span>|<span data-ttu-id="5edf0-119">説明</span><span class="sxs-lookup"><span data-stu-id="5edf0-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5edf0-120">\<clientCertificate></span><span class="sxs-lookup"><span data-stu-id="5edf0-120">\<clientCertificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcertificate-of-clientcredentials-element.md)|<span data-ttu-id="5edf0-121">サービスに対するクライアントの認証に使用される証明書を指定します。</span><span class="sxs-lookup"><span data-stu-id="5edf0-121">Specifies the certificate used to authenticate the client to the service.</span></span> <span data-ttu-id="5edf0-122">この要素は <xref:System.ServiceModel.Configuration.X509InitiatorCertificateClientElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="5edf0-122">This element is of type <xref:System.ServiceModel.Configuration.X509InitiatorCertificateClientElement>.</span></span>|  
|[<span data-ttu-id="5edf0-123">\<httpDigest></span><span class="sxs-lookup"><span data-stu-id="5edf0-123">\<httpDigest></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/httpdigest-element.md)|<span data-ttu-id="5edf0-124">サービスに対するクライアントの認証に使用されるダイジェストを指定します。</span><span class="sxs-lookup"><span data-stu-id="5edf0-124">Specifies a digest used to authenticate the client to the service.</span></span> <span data-ttu-id="5edf0-125">この要素は <xref:System.ServiceModel.Configuration.HttpDigestClientElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="5edf0-125">This element is of type <xref:System.ServiceModel.Configuration.HttpDigestClientElement>.</span></span>|  
|[<span data-ttu-id="5edf0-126">\<issuedToken ></span><span class="sxs-lookup"><span data-stu-id="5edf0-126">\<issuedToken></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtoken.md)|<span data-ttu-id="5edf0-127">セキュリティ トークン サービス (STS) に対するクライアントの認証に使用されるカスタム トークンの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="5edf0-127">Specifies a custom token type used to authenticate the client to a Secure Token Service (STS).</span></span> <span data-ttu-id="5edf0-128">この要素は <xref:System.ServiceModel.Configuration.IssuedTokenClientElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="5edf0-128">This element is of type <xref:System.ServiceModel.Configuration.IssuedTokenClientElement>.</span></span>|  
|[<span data-ttu-id="5edf0-129">\<ピア ></span><span class="sxs-lookup"><span data-stu-id="5edf0-129">\<peer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/peer-of-clientcredentials-element.md)|<span data-ttu-id="5edf0-130">現在のピア資格情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="5edf0-130">Specifies a current peer credential.</span></span> <span data-ttu-id="5edf0-131">この要素は <xref:System.ServiceModel.Configuration.PeerCredentialElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="5edf0-131">This element is of type <xref:System.ServiceModel.Configuration.PeerCredentialElement>.</span></span>|  
|[<span data-ttu-id="5edf0-132">\<serviceCertificate></span><span class="sxs-lookup"><span data-stu-id="5edf0-132">\<serviceCertificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-clientcredentials-element.md)|<span data-ttu-id="5edf0-133">クライアントに対するサービスの認証に使用される証明書を指定し、証明書オプションを設定するための構造を提供します。</span><span class="sxs-lookup"><span data-stu-id="5edf0-133">Specifies the certificate used to authenticate the service to the client and provides a structure for setting certificate options.</span></span> <span data-ttu-id="5edf0-134">この証明書は、クライアントに対するサービスの帯域外に提供される必要があります。</span><span class="sxs-lookup"><span data-stu-id="5edf0-134">This certificate must be supplied out-of-band from the service to the client.</span></span> <span data-ttu-id="5edf0-135">この要素は <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="5edf0-135">This element is of type <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement>.</span></span>|  
|[<span data-ttu-id="5edf0-136">\<windows></span><span class="sxs-lookup"><span data-stu-id="5edf0-136">\<windows></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/windows-of-clientcredentials-element.md)|<span data-ttu-id="5edf0-137">Windows 資格情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="5edf0-137">Specifies a Windows credential.</span></span> <span data-ttu-id="5edf0-138">既定値は、現在のスレッドの資格情報です。</span><span class="sxs-lookup"><span data-stu-id="5edf0-138">The default is the credential of the current thread.</span></span> <span data-ttu-id="5edf0-139">この要素は <xref:System.ServiceModel.Configuration.WindowsClientElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="5edf0-139">This element is of type <xref:System.ServiceModel.Configuration.WindowsClientElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="5edf0-140">親要素</span><span class="sxs-lookup"><span data-stu-id="5edf0-140">Parent Elements</span></span>  
  
|<span data-ttu-id="5edf0-141">要素</span><span class="sxs-lookup"><span data-stu-id="5edf0-141">Element</span></span>|<span data-ttu-id="5edf0-142">説明</span><span class="sxs-lookup"><span data-stu-id="5edf0-142">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5edf0-143">\<behavior></span><span class="sxs-lookup"><span data-stu-id="5edf0-143">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="5edf0-144">エンドポイントの動作を指定します。</span><span class="sxs-lookup"><span data-stu-id="5edf0-144">Specifies an endpoint behavior.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5edf0-145">Remarks</span><span class="sxs-lookup"><span data-stu-id="5edf0-145">Remarks</span></span>  
 <span data-ttu-id="5edf0-146">クライアント資格情報は、相互認証が必要な場合にサービスに対するクライアントの認証に使用されます。</span><span class="sxs-lookup"><span data-stu-id="5edf0-146">Client credentials are used to authenticate the client to services in cases where mutual authentication is required.</span></span> <span data-ttu-id="5edf0-147">また、この構成セクションを使用して、クライアントがサービスの証明書によってサービスへのメッセージをセキュリティで保護する必要がある場合に使用するサービス証明書を指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="5edf0-147">This configuration section can also be used to specify service certificates for scenarios where the client must secure messages to a service with the service's certificate.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5edf0-148">関連項目</span><span class="sxs-lookup"><span data-stu-id="5edf0-148">See also</span></span>

- <xref:System.ServiceModel.Configuration.ClientCredentialsElement>
- <xref:System.ServiceModel.Description.ClientCredentials>
- [<span data-ttu-id="5edf0-149">セキュリティ動作</span><span class="sxs-lookup"><span data-stu-id="5edf0-149">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="5edf0-150">クライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="5edf0-150">Securing Clients</span></span>](../../../../../docs/framework/wcf/securing-clients.md)
