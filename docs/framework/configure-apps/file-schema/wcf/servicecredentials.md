---
title: <serviceCredentials>
ms.date: 03/30/2017
ms.assetid: 96db336c-4f7a-4193-81a5-910b8ffd804f
ms.openlocfilehash: 63368355027856118546bc70183b41864eddb0e6
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91172880"
---
# \<serviceCredentials>

<span data-ttu-id="a596c-101">サービスの認証に使用される資格情報と、クライアントの資格情報検証関連の設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="a596c-101">Specifies the credential to be used in authenticating the service and the client credential validation-related settings.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceCredentials>**  
  
## <a name="syntax"></a><span data-ttu-id="a596c-102">構文</span><span class="sxs-lookup"><span data-stu-id="a596c-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a596c-103">属性および要素</span><span class="sxs-lookup"><span data-stu-id="a596c-103">Attributes and Elements</span></span>  

 <span data-ttu-id="a596c-104">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="a596c-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a596c-105">属性</span><span class="sxs-lookup"><span data-stu-id="a596c-105">Attributes</span></span>  
  
|<span data-ttu-id="a596c-106">属性</span><span class="sxs-lookup"><span data-stu-id="a596c-106">Attribute</span></span>|<span data-ttu-id="a596c-107">[説明]</span><span class="sxs-lookup"><span data-stu-id="a596c-107">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="a596c-108">この設定要素の種類を指定する文字列です。</span><span class="sxs-lookup"><span data-stu-id="a596c-108">A string that specifies the type of this configuration element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a596c-109">子要素</span><span class="sxs-lookup"><span data-stu-id="a596c-109">Child Elements</span></span>  
  
|<span data-ttu-id="a596c-110">要素</span><span class="sxs-lookup"><span data-stu-id="a596c-110">Element</span></span>|<span data-ttu-id="a596c-111">説明</span><span class="sxs-lookup"><span data-stu-id="a596c-111">Description</span></span>|  
|-------------|-----------------|  
|[\<clientCertificate>](clientcertificate-of-servicecredentials.md)|<span data-ttu-id="a596c-112">クライアント証明書を帯域外で使用できるときに使用される証明書を指定します。</span><span class="sxs-lookup"><span data-stu-id="a596c-112">Specifies the certificate to be used when the client certificate is available out-of-band.</span></span> <span data-ttu-id="a596c-113">この要素は、クライアント証明書の検証設定も指定します。</span><span class="sxs-lookup"><span data-stu-id="a596c-113">This element also specifies client certificate validation settings.</span></span> <span data-ttu-id="a596c-114">この要素は <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="a596c-114">This element is of type <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement>.</span></span>|  
|[\<issuedTokenAuthentication>](issuedtokenauthentication-of-servicecredentials.md)|<span data-ttu-id="a596c-115">このサービス用に現在発行されているトークンを指定します。</span><span class="sxs-lookup"><span data-stu-id="a596c-115">Specifies the current issued token for this service.</span></span> <span data-ttu-id="a596c-116">この要素は <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="a596c-116">This element is of type <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement>.</span></span>|  
|[\<peer>](peer-of-servicecredentials.md)|<span data-ttu-id="a596c-117">ピア ノードの現在の資格情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="a596c-117">Specifies the current credentials for a peer node.</span></span> <span data-ttu-id="a596c-118">この要素は <xref:System.ServiceModel.Configuration.PeerCredentialElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="a596c-118">This element is of type <xref:System.ServiceModel.Configuration.PeerCredentialElement>.</span></span>|  
|[\<secureConversationAuthentication>](secureconversationauthentication-of-servicecredential.md)|<span data-ttu-id="a596c-119">セキュリティで保護されたメッセージ交換の現在の資格情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="a596c-119">Specifies the current credentials for a secure conversation.</span></span> <span data-ttu-id="a596c-120">この要素は <xref:System.ServiceModel.Configuration.SecureConversationServiceElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="a596c-120">This element is of type <xref:System.ServiceModel.Configuration.SecureConversationServiceElement>.</span></span>|  
|[\<serviceCertificate>](servicecertificate-of-servicecredentials.md)|<span data-ttu-id="a596c-121">サービスが自身を識別するために使用する証明書を指定します。</span><span class="sxs-lookup"><span data-stu-id="a596c-121">Specifies a certificate used by a service to identify itself.</span></span> <span data-ttu-id="a596c-122">この要素は <xref:System.ServiceModel.Configuration.X509RecipientCertificateServiceElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="a596c-122">This element is of type <xref:System.ServiceModel.Configuration.X509RecipientCertificateServiceElement>.</span></span>|  
|[\<userNameAuthentication>](usernameauthentication.md)|<span data-ttu-id="a596c-123">ユーザー名とパスワードの検証の設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="a596c-123">Specifies the settings for username password validation.</span></span> <span data-ttu-id="a596c-124">この要素は <xref:System.ServiceModel.Configuration.UserNameServiceElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="a596c-124">This element is of type <xref:System.ServiceModel.Configuration.UserNameServiceElement>.</span></span>|  
|[\<windowsAuthentication>](windowsauthentication-of-servicecredentials.md)|<span data-ttu-id="a596c-125">Windows 資格情報の検証の設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="a596c-125">Specifies the settings for Windows credential validation.</span></span> <span data-ttu-id="a596c-126">この要素は <xref:System.ServiceModel.Configuration.WindowsServiceElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="a596c-126">This element is of type <xref:System.ServiceModel.Configuration.WindowsServiceElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a596c-127">親要素</span><span class="sxs-lookup"><span data-stu-id="a596c-127">Parent Elements</span></span>  
  
|<span data-ttu-id="a596c-128">要素</span><span class="sxs-lookup"><span data-stu-id="a596c-128">Element</span></span>|<span data-ttu-id="a596c-129">説明</span><span class="sxs-lookup"><span data-stu-id="a596c-129">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="a596c-130">動作の要素を指定します。</span><span class="sxs-lookup"><span data-stu-id="a596c-130">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a596c-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="a596c-131">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceCredentialsElement>
- <xref:System.ServiceModel.Description.ServiceCredentials>
- [<span data-ttu-id="a596c-132">セキュリティ動作</span><span class="sxs-lookup"><span data-stu-id="a596c-132">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
