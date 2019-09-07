---
title: <clientCredentials>
ms.date: 03/30/2017
ms.assetid: 1e6eef0d-a34e-4d74-b0f7-f65d2181858d
ms.openlocfilehash: f295fe48e194611c80b78c0c23ab3e66ea1c0b64
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400496"
---
# <a name="clientcredentials"></a><span data-ttu-id="3ce25-101">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="3ce25-101">\<clientCredentials></span></span>
<span data-ttu-id="3ce25-102">サービスに対するクライアントの認証に使用される資格情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="3ce25-102">Specifies the credentials used to authenticate the client to a service.</span></span>  
  
<span data-ttu-id="3ce25-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="3ce25-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="3ce25-104">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="3ce25-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="3ce25-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<動作 >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="3ce25-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="3ce25-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<endpointBehaviors >** ](endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="3ce25-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)</span></span>\
<span data-ttu-id="3ce25-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<動作 >** ](behavior-of-endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="3ce25-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)</span></span>\
<span data-ttu-id="3ce25-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<clientCredentials >**</span><span class="sxs-lookup"><span data-stu-id="3ce25-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clientCredentials>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3ce25-109">構文</span><span class="sxs-lookup"><span data-stu-id="3ce25-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3ce25-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="3ce25-110">Attributes and Elements</span></span>  
 <span data-ttu-id="3ce25-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="3ce25-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3ce25-112">属性</span><span class="sxs-lookup"><span data-stu-id="3ce25-112">Attributes</span></span>  
  
|<span data-ttu-id="3ce25-113">属性</span><span class="sxs-lookup"><span data-stu-id="3ce25-113">Attribute</span></span>|<span data-ttu-id="3ce25-114">説明</span><span class="sxs-lookup"><span data-stu-id="3ce25-114">Description</span></span>|  
|---------------|-----------------|  
|`supportInteractive`|<span data-ttu-id="3ce25-115">実行時にクライアントの資格情報を選択する際に、対話型ユーザーを含めるかどうかを指定するブール値。</span><span class="sxs-lookup"><span data-stu-id="3ce25-115">A Boolean value that specifies whether an interactive user can be involved in selecting a client credential at runtime.</span></span> <span data-ttu-id="3ce25-116">既定値は `true` です。</span><span class="sxs-lookup"><span data-stu-id="3ce25-116">The default value is `true`.</span></span>|  
|`type`|<span data-ttu-id="3ce25-117">この設定要素の種類を指定する文字列です。</span><span class="sxs-lookup"><span data-stu-id="3ce25-117">A string that specifies the type of this configuration element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3ce25-118">子要素</span><span class="sxs-lookup"><span data-stu-id="3ce25-118">Child Elements</span></span>  
  
|<span data-ttu-id="3ce25-119">要素</span><span class="sxs-lookup"><span data-stu-id="3ce25-119">Element</span></span>|<span data-ttu-id="3ce25-120">説明</span><span class="sxs-lookup"><span data-stu-id="3ce25-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3ce25-121">\<clientCertificate></span><span class="sxs-lookup"><span data-stu-id="3ce25-121">\<clientCertificate></span></span>](clientcertificate-of-clientcredentials-element.md)|<span data-ttu-id="3ce25-122">サービスに対するクライアントの認証に使用される証明書を指定します。</span><span class="sxs-lookup"><span data-stu-id="3ce25-122">Specifies the certificate used to authenticate the client to the service.</span></span> <span data-ttu-id="3ce25-123">この要素は <xref:System.ServiceModel.Configuration.X509InitiatorCertificateClientElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="3ce25-123">This element is of type <xref:System.ServiceModel.Configuration.X509InitiatorCertificateClientElement>.</span></span>|  
|[<span data-ttu-id="3ce25-124">\<httpDigest ></span><span class="sxs-lookup"><span data-stu-id="3ce25-124">\<httpDigest></span></span>](httpdigest-element.md)|<span data-ttu-id="3ce25-125">サービスに対するクライアントの認証に使用されるダイジェストを指定します。</span><span class="sxs-lookup"><span data-stu-id="3ce25-125">Specifies a digest used to authenticate the client to the service.</span></span> <span data-ttu-id="3ce25-126">この要素は <xref:System.ServiceModel.Configuration.HttpDigestClientElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="3ce25-126">This element is of type <xref:System.ServiceModel.Configuration.HttpDigestClientElement>.</span></span>|  
|[<span data-ttu-id="3ce25-127">\<issuedToken ></span><span class="sxs-lookup"><span data-stu-id="3ce25-127">\<issuedToken></span></span>](issuedtoken.md)|<span data-ttu-id="3ce25-128">セキュリティ トークン サービス (STS) に対するクライアントの認証に使用されるカスタム トークンの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="3ce25-128">Specifies a custom token type used to authenticate the client to a Secure Token Service (STS).</span></span> <span data-ttu-id="3ce25-129">この要素は <xref:System.ServiceModel.Configuration.IssuedTokenClientElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="3ce25-129">This element is of type <xref:System.ServiceModel.Configuration.IssuedTokenClientElement>.</span></span>|  
|[<span data-ttu-id="3ce25-130">\<peer></span><span class="sxs-lookup"><span data-stu-id="3ce25-130">\<peer></span></span>](peer-of-clientcredentials-element.md)|<span data-ttu-id="3ce25-131">現在のピア資格情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="3ce25-131">Specifies a current peer credential.</span></span> <span data-ttu-id="3ce25-132">この要素は <xref:System.ServiceModel.Configuration.PeerCredentialElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="3ce25-132">This element is of type <xref:System.ServiceModel.Configuration.PeerCredentialElement>.</span></span>|  
|[<span data-ttu-id="3ce25-133">\<serviceCertificate ></span><span class="sxs-lookup"><span data-stu-id="3ce25-133">\<serviceCertificate></span></span>](servicecertificate-of-clientcredentials-element.md)|<span data-ttu-id="3ce25-134">クライアントに対するサービスの認証に使用される証明書を指定し、証明書オプションを設定するための構造を提供します。</span><span class="sxs-lookup"><span data-stu-id="3ce25-134">Specifies the certificate used to authenticate the service to the client and provides a structure for setting certificate options.</span></span> <span data-ttu-id="3ce25-135">この証明書は、クライアントに対するサービスの帯域外に提供される必要があります。</span><span class="sxs-lookup"><span data-stu-id="3ce25-135">This certificate must be supplied out-of-band from the service to the client.</span></span> <span data-ttu-id="3ce25-136">この要素は <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="3ce25-136">This element is of type <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement>.</span></span>|  
|[<span data-ttu-id="3ce25-137">\<windows></span><span class="sxs-lookup"><span data-stu-id="3ce25-137">\<windows></span></span>](windows-of-clientcredentials-element.md)|<span data-ttu-id="3ce25-138">Windows 資格情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="3ce25-138">Specifies a Windows credential.</span></span> <span data-ttu-id="3ce25-139">既定値は、現在のスレッドの資格情報です。</span><span class="sxs-lookup"><span data-stu-id="3ce25-139">The default is the credential of the current thread.</span></span> <span data-ttu-id="3ce25-140">この要素は <xref:System.ServiceModel.Configuration.WindowsClientElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="3ce25-140">This element is of type <xref:System.ServiceModel.Configuration.WindowsClientElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="3ce25-141">親要素</span><span class="sxs-lookup"><span data-stu-id="3ce25-141">Parent Elements</span></span>  
  
|<span data-ttu-id="3ce25-142">要素</span><span class="sxs-lookup"><span data-stu-id="3ce25-142">Element</span></span>|<span data-ttu-id="3ce25-143">説明</span><span class="sxs-lookup"><span data-stu-id="3ce25-143">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3ce25-144">\<behavior></span><span class="sxs-lookup"><span data-stu-id="3ce25-144">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="3ce25-145">エンドポイントの動作を指定します。</span><span class="sxs-lookup"><span data-stu-id="3ce25-145">Specifies an endpoint behavior.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3ce25-146">Remarks</span><span class="sxs-lookup"><span data-stu-id="3ce25-146">Remarks</span></span>  
 <span data-ttu-id="3ce25-147">クライアント資格情報は、相互認証が必要な場合にサービスに対するクライアントの認証に使用されます。</span><span class="sxs-lookup"><span data-stu-id="3ce25-147">Client credentials are used to authenticate the client to services in cases where mutual authentication is required.</span></span> <span data-ttu-id="3ce25-148">また、この構成セクションを使用して、クライアントがサービスの証明書によってサービスへのメッセージをセキュリティで保護する必要がある場合に使用するサービス証明書を指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="3ce25-148">This configuration section can also be used to specify service certificates for scenarios where the client must secure messages to a service with the service's certificate.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ce25-149">関連項目</span><span class="sxs-lookup"><span data-stu-id="3ce25-149">See also</span></span>

- <xref:System.ServiceModel.Configuration.ClientCredentialsElement>
- <xref:System.ServiceModel.Description.ClientCredentials>
- [<span data-ttu-id="3ce25-150">セキュリティ動作</span><span class="sxs-lookup"><span data-stu-id="3ce25-150">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="3ce25-151">クライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="3ce25-151">Securing Clients</span></span>](../../../wcf/securing-clients.md)
