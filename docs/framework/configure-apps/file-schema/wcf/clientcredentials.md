---
title: <clientCredentials>
ms.date: 03/30/2017
ms.assetid: 1e6eef0d-a34e-4d74-b0f7-f65d2181858d
ms.openlocfilehash: 6094006df24ee824c419a783ab29d7604757577c
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91201461"
---
# \<clientCredentials>

<span data-ttu-id="ab71b-101">サービスに対するクライアントの認証に使用される資格情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="ab71b-101">Specifies the credentials used to authenticate the client to a service.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clientCredentials>**  
  
## <a name="syntax"></a><span data-ttu-id="ab71b-102">構文</span><span class="sxs-lookup"><span data-stu-id="ab71b-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ab71b-103">属性および要素</span><span class="sxs-lookup"><span data-stu-id="ab71b-103">Attributes and Elements</span></span>  

 <span data-ttu-id="ab71b-104">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="ab71b-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ab71b-105">属性</span><span class="sxs-lookup"><span data-stu-id="ab71b-105">Attributes</span></span>  
  
|<span data-ttu-id="ab71b-106">属性</span><span class="sxs-lookup"><span data-stu-id="ab71b-106">Attribute</span></span>|<span data-ttu-id="ab71b-107">[説明]</span><span class="sxs-lookup"><span data-stu-id="ab71b-107">Description</span></span>|  
|---------------|-----------------|  
|`supportInteractive`|<span data-ttu-id="ab71b-108">実行時にクライアントの資格情報を選択する際に、対話型ユーザーを含めるかどうかを指定するブール値。</span><span class="sxs-lookup"><span data-stu-id="ab71b-108">A Boolean value that specifies whether an interactive user can be involved in selecting a client credential at runtime.</span></span> <span data-ttu-id="ab71b-109">既定値は `true` です。</span><span class="sxs-lookup"><span data-stu-id="ab71b-109">The default value is `true`.</span></span>|  
|`type`|<span data-ttu-id="ab71b-110">この設定要素の種類を指定する文字列です。</span><span class="sxs-lookup"><span data-stu-id="ab71b-110">A string that specifies the type of this configuration element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ab71b-111">子要素</span><span class="sxs-lookup"><span data-stu-id="ab71b-111">Child Elements</span></span>  
  
|<span data-ttu-id="ab71b-112">要素</span><span class="sxs-lookup"><span data-stu-id="ab71b-112">Element</span></span>|<span data-ttu-id="ab71b-113">説明</span><span class="sxs-lookup"><span data-stu-id="ab71b-113">Description</span></span>|  
|-------------|-----------------|  
|[\<clientCertificate>](clientcertificate-of-clientcredentials-element.md)|<span data-ttu-id="ab71b-114">サービスに対するクライアントの認証に使用される証明書を指定します。</span><span class="sxs-lookup"><span data-stu-id="ab71b-114">Specifies the certificate used to authenticate the client to the service.</span></span> <span data-ttu-id="ab71b-115">この要素は <xref:System.ServiceModel.Configuration.X509InitiatorCertificateClientElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="ab71b-115">This element is of type <xref:System.ServiceModel.Configuration.X509InitiatorCertificateClientElement>.</span></span>|  
|[\<httpDigest>](httpdigest-element.md)|<span data-ttu-id="ab71b-116">サービスに対するクライアントの認証に使用されるダイジェストを指定します。</span><span class="sxs-lookup"><span data-stu-id="ab71b-116">Specifies a digest used to authenticate the client to the service.</span></span> <span data-ttu-id="ab71b-117">この要素は <xref:System.ServiceModel.Configuration.HttpDigestClientElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="ab71b-117">This element is of type <xref:System.ServiceModel.Configuration.HttpDigestClientElement>.</span></span>|  
|[\<issuedToken>](issuedtoken.md)|<span data-ttu-id="ab71b-118">セキュリティ トークン サービス (STS) に対するクライアントの認証に使用されるカスタム トークンの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="ab71b-118">Specifies a custom token type used to authenticate the client to a Secure Token Service (STS).</span></span> <span data-ttu-id="ab71b-119">この要素は <xref:System.ServiceModel.Configuration.IssuedTokenClientElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="ab71b-119">This element is of type <xref:System.ServiceModel.Configuration.IssuedTokenClientElement>.</span></span>|  
|[\<peer>](peer-of-clientcredentials-element.md)|<span data-ttu-id="ab71b-120">現在のピア資格情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="ab71b-120">Specifies a current peer credential.</span></span> <span data-ttu-id="ab71b-121">この要素は <xref:System.ServiceModel.Configuration.PeerCredentialElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="ab71b-121">This element is of type <xref:System.ServiceModel.Configuration.PeerCredentialElement>.</span></span>|  
|[\<serviceCertificate>](servicecertificate-of-clientcredentials-element.md)|<span data-ttu-id="ab71b-122">クライアントに対するサービスの認証に使用される証明書を指定し、証明書オプションを設定するための構造を提供します。</span><span class="sxs-lookup"><span data-stu-id="ab71b-122">Specifies the certificate used to authenticate the service to the client and provides a structure for setting certificate options.</span></span> <span data-ttu-id="ab71b-123">この証明書は、クライアントに対するサービスの帯域外に提供される必要があります。</span><span class="sxs-lookup"><span data-stu-id="ab71b-123">This certificate must be supplied out-of-band from the service to the client.</span></span> <span data-ttu-id="ab71b-124">この要素は <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="ab71b-124">This element is of type <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement>.</span></span>|  
|[\<windows>](windows-of-clientcredentials-element.md)|<span data-ttu-id="ab71b-125">Windows 資格情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="ab71b-125">Specifies a Windows credential.</span></span> <span data-ttu-id="ab71b-126">既定値は、現在のスレッドの資格情報です。</span><span class="sxs-lookup"><span data-stu-id="ab71b-126">The default is the credential of the current thread.</span></span> <span data-ttu-id="ab71b-127">この要素は <xref:System.ServiceModel.Configuration.WindowsClientElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="ab71b-127">This element is of type <xref:System.ServiceModel.Configuration.WindowsClientElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ab71b-128">親要素</span><span class="sxs-lookup"><span data-stu-id="ab71b-128">Parent Elements</span></span>  
  
|<span data-ttu-id="ab71b-129">要素</span><span class="sxs-lookup"><span data-stu-id="ab71b-129">Element</span></span>|<span data-ttu-id="ab71b-130">説明</span><span class="sxs-lookup"><span data-stu-id="ab71b-130">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="ab71b-131">エンドポイントの動作を指定します。</span><span class="sxs-lookup"><span data-stu-id="ab71b-131">Specifies an endpoint behavior.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ab71b-132">解説</span><span class="sxs-lookup"><span data-stu-id="ab71b-132">Remarks</span></span>  

 <span data-ttu-id="ab71b-133">クライアント資格情報は、相互認証が必要な場合にサービスに対するクライアントの認証に使用されます。</span><span class="sxs-lookup"><span data-stu-id="ab71b-133">Client credentials are used to authenticate the client to services in cases where mutual authentication is required.</span></span> <span data-ttu-id="ab71b-134">また、この構成セクションを使用して、クライアントがサービスの証明書によってサービスへのメッセージをセキュリティで保護する必要がある場合に使用するサービス証明書を指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="ab71b-134">This configuration section can also be used to specify service certificates for scenarios where the client must secure messages to a service with the service's certificate.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab71b-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="ab71b-135">See also</span></span>

- <xref:System.ServiceModel.Configuration.ClientCredentialsElement>
- <xref:System.ServiceModel.Description.ClientCredentials>
- [<span data-ttu-id="ab71b-136">セキュリティ動作</span><span class="sxs-lookup"><span data-stu-id="ab71b-136">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="ab71b-137">クライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="ab71b-137">Securing Clients</span></span>](../../../wcf/securing-clients.md)
