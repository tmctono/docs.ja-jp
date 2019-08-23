---
title: <clientCredentials>
ms.date: 03/30/2017
ms.assetid: 1e6eef0d-a34e-4d74-b0f7-f65d2181858d
ms.openlocfilehash: c3e756f49b7054d6553eb6c3f1850f0fbce14943
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69926103"
---
# <a name="clientcredentials"></a><span data-ttu-id="04733-101">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="04733-101">\<clientCredentials></span></span>
<span data-ttu-id="04733-102">サービスに対するクライアントの認証に使用される資格情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="04733-102">Specifies the credentials used to authenticate the client to a service.</span></span>  
  
 <span data-ttu-id="04733-103">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="04733-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="04733-104">\<<behaviors></span><span class="sxs-lookup"><span data-stu-id="04733-104">\<behaviors></span></span>  
<span data-ttu-id="04733-105">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="04733-105">\<endpointBehaviors></span></span>  
<span data-ttu-id="04733-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="04733-106">\<behavior></span></span>  
<span data-ttu-id="04733-107">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="04733-107">\<clientCredentials></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="04733-108">構文</span><span class="sxs-lookup"><span data-stu-id="04733-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="04733-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="04733-109">Attributes and Elements</span></span>  
 <span data-ttu-id="04733-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="04733-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="04733-111">属性</span><span class="sxs-lookup"><span data-stu-id="04733-111">Attributes</span></span>  
  
|<span data-ttu-id="04733-112">属性</span><span class="sxs-lookup"><span data-stu-id="04733-112">Attribute</span></span>|<span data-ttu-id="04733-113">説明</span><span class="sxs-lookup"><span data-stu-id="04733-113">Description</span></span>|  
|---------------|-----------------|  
|`supportInteractive`|<span data-ttu-id="04733-114">実行時にクライアントの資格情報を選択する際に、対話型ユーザーを含めるかどうかを指定するブール値。</span><span class="sxs-lookup"><span data-stu-id="04733-114">A Boolean value that specifies whether an interactive user can be involved in selecting a client credential at runtime.</span></span> <span data-ttu-id="04733-115">既定値は `true` です。</span><span class="sxs-lookup"><span data-stu-id="04733-115">The default value is `true`.</span></span>|  
|`type`|<span data-ttu-id="04733-116">この設定要素の種類を指定する文字列です。</span><span class="sxs-lookup"><span data-stu-id="04733-116">A string that specifies the type of this configuration element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="04733-117">子要素</span><span class="sxs-lookup"><span data-stu-id="04733-117">Child Elements</span></span>  
  
|<span data-ttu-id="04733-118">要素</span><span class="sxs-lookup"><span data-stu-id="04733-118">Element</span></span>|<span data-ttu-id="04733-119">説明</span><span class="sxs-lookup"><span data-stu-id="04733-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="04733-120">\<clientCertificate></span><span class="sxs-lookup"><span data-stu-id="04733-120">\<clientCertificate></span></span>](clientcertificate-of-clientcredentials-element.md)|<span data-ttu-id="04733-121">サービスに対するクライアントの認証に使用される証明書を指定します。</span><span class="sxs-lookup"><span data-stu-id="04733-121">Specifies the certificate used to authenticate the client to the service.</span></span> <span data-ttu-id="04733-122">この要素は <xref:System.ServiceModel.Configuration.X509InitiatorCertificateClientElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="04733-122">This element is of type <xref:System.ServiceModel.Configuration.X509InitiatorCertificateClientElement>.</span></span>|  
|[<span data-ttu-id="04733-123">\<httpDigest ></span><span class="sxs-lookup"><span data-stu-id="04733-123">\<httpDigest></span></span>](httpdigest-element.md)|<span data-ttu-id="04733-124">サービスに対するクライアントの認証に使用されるダイジェストを指定します。</span><span class="sxs-lookup"><span data-stu-id="04733-124">Specifies a digest used to authenticate the client to the service.</span></span> <span data-ttu-id="04733-125">この要素は <xref:System.ServiceModel.Configuration.HttpDigestClientElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="04733-125">This element is of type <xref:System.ServiceModel.Configuration.HttpDigestClientElement>.</span></span>|  
|[<span data-ttu-id="04733-126">\<issuedToken ></span><span class="sxs-lookup"><span data-stu-id="04733-126">\<issuedToken></span></span>](issuedtoken.md)|<span data-ttu-id="04733-127">セキュリティ トークン サービス (STS) に対するクライアントの認証に使用されるカスタム トークンの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="04733-127">Specifies a custom token type used to authenticate the client to a Secure Token Service (STS).</span></span> <span data-ttu-id="04733-128">この要素は <xref:System.ServiceModel.Configuration.IssuedTokenClientElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="04733-128">This element is of type <xref:System.ServiceModel.Configuration.IssuedTokenClientElement>.</span></span>|  
|[<span data-ttu-id="04733-129">\<peer></span><span class="sxs-lookup"><span data-stu-id="04733-129">\<peer></span></span>](peer-of-clientcredentials-element.md)|<span data-ttu-id="04733-130">現在のピア資格情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="04733-130">Specifies a current peer credential.</span></span> <span data-ttu-id="04733-131">この要素は <xref:System.ServiceModel.Configuration.PeerCredentialElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="04733-131">This element is of type <xref:System.ServiceModel.Configuration.PeerCredentialElement>.</span></span>|  
|[<span data-ttu-id="04733-132">\<serviceCertificate ></span><span class="sxs-lookup"><span data-stu-id="04733-132">\<serviceCertificate></span></span>](servicecertificate-of-clientcredentials-element.md)|<span data-ttu-id="04733-133">クライアントに対するサービスの認証に使用される証明書を指定し、証明書オプションを設定するための構造を提供します。</span><span class="sxs-lookup"><span data-stu-id="04733-133">Specifies the certificate used to authenticate the service to the client and provides a structure for setting certificate options.</span></span> <span data-ttu-id="04733-134">この証明書は、クライアントに対するサービスの帯域外に提供される必要があります。</span><span class="sxs-lookup"><span data-stu-id="04733-134">This certificate must be supplied out-of-band from the service to the client.</span></span> <span data-ttu-id="04733-135">この要素は <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="04733-135">This element is of type <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement>.</span></span>|  
|[<span data-ttu-id="04733-136">\<windows></span><span class="sxs-lookup"><span data-stu-id="04733-136">\<windows></span></span>](windows-of-clientcredentials-element.md)|<span data-ttu-id="04733-137">Windows 資格情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="04733-137">Specifies a Windows credential.</span></span> <span data-ttu-id="04733-138">既定値は、現在のスレッドの資格情報です。</span><span class="sxs-lookup"><span data-stu-id="04733-138">The default is the credential of the current thread.</span></span> <span data-ttu-id="04733-139">この要素は <xref:System.ServiceModel.Configuration.WindowsClientElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="04733-139">This element is of type <xref:System.ServiceModel.Configuration.WindowsClientElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="04733-140">親要素</span><span class="sxs-lookup"><span data-stu-id="04733-140">Parent Elements</span></span>  
  
|<span data-ttu-id="04733-141">要素</span><span class="sxs-lookup"><span data-stu-id="04733-141">Element</span></span>|<span data-ttu-id="04733-142">説明</span><span class="sxs-lookup"><span data-stu-id="04733-142">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="04733-143">\<behavior></span><span class="sxs-lookup"><span data-stu-id="04733-143">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="04733-144">エンドポイントの動作を指定します。</span><span class="sxs-lookup"><span data-stu-id="04733-144">Specifies an endpoint behavior.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="04733-145">Remarks</span><span class="sxs-lookup"><span data-stu-id="04733-145">Remarks</span></span>  
 <span data-ttu-id="04733-146">クライアント資格情報は、相互認証が必要な場合にサービスに対するクライアントの認証に使用されます。</span><span class="sxs-lookup"><span data-stu-id="04733-146">Client credentials are used to authenticate the client to services in cases where mutual authentication is required.</span></span> <span data-ttu-id="04733-147">また、この構成セクションを使用して、クライアントがサービスの証明書によってサービスへのメッセージをセキュリティで保護する必要がある場合に使用するサービス証明書を指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="04733-147">This configuration section can also be used to specify service certificates for scenarios where the client must secure messages to a service with the service's certificate.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04733-148">関連項目</span><span class="sxs-lookup"><span data-stu-id="04733-148">See also</span></span>

- <xref:System.ServiceModel.Configuration.ClientCredentialsElement>
- <xref:System.ServiceModel.Description.ClientCredentials>
- [<span data-ttu-id="04733-149">セキュリティ動作</span><span class="sxs-lookup"><span data-stu-id="04733-149">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="04733-150">クライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="04733-150">Securing Clients</span></span>](../../../wcf/securing-clients.md)
