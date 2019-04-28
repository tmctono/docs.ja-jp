---
title: <serviceCredentials>
ms.date: 03/30/2017
ms.assetid: 96db336c-4f7a-4193-81a5-910b8ffd804f
ms.openlocfilehash: d9f8fdf272962916cd08aede484e9bbde55b96a3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61670288"
---
# <a name="servicecredentials"></a><span data-ttu-id="8259a-101">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="8259a-101">\<serviceCredentials></span></span>
<span data-ttu-id="8259a-102">サービスの認証に使用される資格情報と、クライアントの資格情報検証関連の設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="8259a-102">Specifies the credential to be used in authenticating the service and the client credential validation-related settings.</span></span>  
  
 <span data-ttu-id="8259a-103">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="8259a-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="8259a-104">\<<behaviors></span><span class="sxs-lookup"><span data-stu-id="8259a-104">\<behaviors></span></span>  
<span data-ttu-id="8259a-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="8259a-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="8259a-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="8259a-106">\<behavior></span></span>  
<span data-ttu-id="8259a-107">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="8259a-107">\<serviceCredentials></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8259a-108">構文</span><span class="sxs-lookup"><span data-stu-id="8259a-108">Syntax</span></span>  
  
```xml  
<serviceCredentials type="String">
  <clientCertificate>
  </clientCertificate>
  <issuedTokenAuthentication>
  </issuedTokenAuthentication>
  <peer>
  </peer>
  <secureConversationAuthentication>
  </secureConversationAuthentication>
  <serviceCertificate>
  </serviceCertificate>
  <userNameAuthentication>
  </userNameAuthentication>
  <windowsAuthentication>
  </windowsAuthentication>
</serviceCredentials>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8259a-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="8259a-109">Attributes and Elements</span></span>  
 <span data-ttu-id="8259a-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="8259a-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8259a-111">属性</span><span class="sxs-lookup"><span data-stu-id="8259a-111">Attributes</span></span>  
  
|<span data-ttu-id="8259a-112">属性</span><span class="sxs-lookup"><span data-stu-id="8259a-112">Attribute</span></span>|<span data-ttu-id="8259a-113">説明</span><span class="sxs-lookup"><span data-stu-id="8259a-113">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="8259a-114">この設定要素の種類を指定する文字列です。</span><span class="sxs-lookup"><span data-stu-id="8259a-114">A string that specifies the type of this configuration element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8259a-115">子要素</span><span class="sxs-lookup"><span data-stu-id="8259a-115">Child Elements</span></span>  
  
|<span data-ttu-id="8259a-116">要素</span><span class="sxs-lookup"><span data-stu-id="8259a-116">Element</span></span>|<span data-ttu-id="8259a-117">説明</span><span class="sxs-lookup"><span data-stu-id="8259a-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8259a-118">\<clientCertificate></span><span class="sxs-lookup"><span data-stu-id="8259a-118">\<clientCertificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcertificate-of-servicecredentials.md)|<span data-ttu-id="8259a-119">クライアント証明書を帯域外で使用できるときに使用される証明書を指定します。</span><span class="sxs-lookup"><span data-stu-id="8259a-119">Specifies the certificate to be used when the client certificate is available out-of-band.</span></span> <span data-ttu-id="8259a-120">この要素は、クライアント証明書の検証設定も指定します。</span><span class="sxs-lookup"><span data-stu-id="8259a-120">This element also specifies client certificate validation settings.</span></span> <span data-ttu-id="8259a-121">この要素は <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="8259a-121">This element is of type <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement>.</span></span>|  
|[<span data-ttu-id="8259a-122">\<issuedTokenAuthentication></span><span class="sxs-lookup"><span data-stu-id="8259a-122">\<issuedTokenAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md)|<span data-ttu-id="8259a-123">このサービス用に現在発行されているトークンを指定します。</span><span class="sxs-lookup"><span data-stu-id="8259a-123">Specifies the current issued token for this service.</span></span> <span data-ttu-id="8259a-124">この要素は <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="8259a-124">This element is of type <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement>.</span></span>|  
|[<span data-ttu-id="8259a-125">\<peer></span><span class="sxs-lookup"><span data-stu-id="8259a-125">\<peer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/peer-of-servicecredentials.md)|<span data-ttu-id="8259a-126">ピア ノードの現在の資格情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="8259a-126">Specifies the current credentials for a peer node.</span></span> <span data-ttu-id="8259a-127">この要素は <xref:System.ServiceModel.Configuration.PeerCredentialElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="8259a-127">This element is of type <xref:System.ServiceModel.Configuration.PeerCredentialElement>.</span></span>|  
|[<span data-ttu-id="8259a-128">\<secureConversationAuthentication></span><span class="sxs-lookup"><span data-stu-id="8259a-128">\<secureConversationAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationauthentication-of-servicecredential.md)|<span data-ttu-id="8259a-129">セキュリティで保護されたメッセージ交換の現在の資格情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="8259a-129">Specifies the current credentials for a secure conversation.</span></span> <span data-ttu-id="8259a-130">この要素は <xref:System.ServiceModel.Configuration.SecureConversationServiceElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="8259a-130">This element is of type <xref:System.ServiceModel.Configuration.SecureConversationServiceElement>.</span></span>|  
|[<span data-ttu-id="8259a-131">\<serviceCertificate></span><span class="sxs-lookup"><span data-stu-id="8259a-131">\<serviceCertificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md)|<span data-ttu-id="8259a-132">サービスが自身を識別するために使用する証明書を指定します。</span><span class="sxs-lookup"><span data-stu-id="8259a-132">Specifies a certificate used by a service to identify itself.</span></span> <span data-ttu-id="8259a-133">この要素は <xref:System.ServiceModel.Configuration.X509RecipientCertificateServiceElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="8259a-133">This element is of type <xref:System.ServiceModel.Configuration.X509RecipientCertificateServiceElement>.</span></span>|  
|[<span data-ttu-id="8259a-134">\<userNameAuthentication></span><span class="sxs-lookup"><span data-stu-id="8259a-134">\<userNameAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/usernameauthentication.md)|<span data-ttu-id="8259a-135">ユーザー名とパスワードの検証の設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="8259a-135">Specifies the settings for username password validation.</span></span> <span data-ttu-id="8259a-136">この要素は <xref:System.ServiceModel.Configuration.UserNameServiceElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="8259a-136">This element is of type <xref:System.ServiceModel.Configuration.UserNameServiceElement>.</span></span>|  
|[<span data-ttu-id="8259a-137">\<windowsAuthentication></span><span class="sxs-lookup"><span data-stu-id="8259a-137">\<windowsAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/windowsauthentication-of-servicecredentials.md)|<span data-ttu-id="8259a-138">Windows 資格情報の検証の設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="8259a-138">Specifies the settings for Windows credential validation.</span></span> <span data-ttu-id="8259a-139">この要素は <xref:System.ServiceModel.Configuration.WindowsServiceElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="8259a-139">This element is of type <xref:System.ServiceModel.Configuration.WindowsServiceElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="8259a-140">親要素</span><span class="sxs-lookup"><span data-stu-id="8259a-140">Parent Elements</span></span>  
  
|<span data-ttu-id="8259a-141">要素</span><span class="sxs-lookup"><span data-stu-id="8259a-141">Element</span></span>|<span data-ttu-id="8259a-142">説明</span><span class="sxs-lookup"><span data-stu-id="8259a-142">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8259a-143">\<behavior></span><span class="sxs-lookup"><span data-stu-id="8259a-143">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="8259a-144">動作の要素を指定します。</span><span class="sxs-lookup"><span data-stu-id="8259a-144">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8259a-145">関連項目</span><span class="sxs-lookup"><span data-stu-id="8259a-145">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceCredentialsElement>
- <xref:System.ServiceModel.Description.ServiceCredentials>
- [<span data-ttu-id="8259a-146">セキュリティ動作</span><span class="sxs-lookup"><span data-stu-id="8259a-146">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)
