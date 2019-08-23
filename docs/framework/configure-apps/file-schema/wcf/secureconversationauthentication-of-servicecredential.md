---
title: <secureConversationAuthentication> の <serviceCredential>
ms.date: 03/30/2017
ms.assetid: 0bd3fac7-befd-4a45-ba51-c200b33be0fd
ms.openlocfilehash: 61034c2c66a6d8e27a87ec5380aa7297247eb31e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69935833"
---
# <a name="secureconversationauthentication-of-servicecredential"></a><span data-ttu-id="8d62e-102">\<serviceCredential の\<secureConversationAuthentication > ></span><span class="sxs-lookup"><span data-stu-id="8d62e-102">\<secureConversationAuthentication> of \<serviceCredential></span></span>
<span data-ttu-id="8d62e-103">安全な会話サービスの設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="8d62e-103">Specifies the settings for a secure conversation service.</span></span>  
  
 <span data-ttu-id="8d62e-104">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="8d62e-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="8d62e-105">\<<behaviors></span><span class="sxs-lookup"><span data-stu-id="8d62e-105">\<behaviors></span></span>  
<span data-ttu-id="8d62e-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="8d62e-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="8d62e-107">\<behavior></span><span class="sxs-lookup"><span data-stu-id="8d62e-107">\<behavior></span></span>  
<span data-ttu-id="8d62e-108">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="8d62e-108">\<serviceCredentials></span></span>  
<span data-ttu-id="8d62e-109">\<secureConversationAuthentication ></span><span class="sxs-lookup"><span data-stu-id="8d62e-109">\<secureConversationAuthentication></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8d62e-110">構文</span><span class="sxs-lookup"><span data-stu-id="8d62e-110">Syntax</span></span>  
  
```xml  
<secureConversationAuthentication securityStateEncoderType="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8d62e-111">属性および要素</span><span class="sxs-lookup"><span data-stu-id="8d62e-111">Attributes and Elements</span></span>  
 <span data-ttu-id="8d62e-112">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="8d62e-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8d62e-113">属性</span><span class="sxs-lookup"><span data-stu-id="8d62e-113">Attributes</span></span>  
  
|<span data-ttu-id="8d62e-114">属性</span><span class="sxs-lookup"><span data-stu-id="8d62e-114">Attribute</span></span>|<span data-ttu-id="8d62e-115">説明</span><span class="sxs-lookup"><span data-stu-id="8d62e-115">Description</span></span>|  
|---------------|-----------------|  
|`securityStateEncoderType`|<span data-ttu-id="8d62e-116">使用される <xref:System.ServiceModel.Security.SecurityStateEncoder> の型を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="8d62e-116">A string that specifies the type of <xref:System.ServiceModel.Security.SecurityStateEncoder> to be used.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8d62e-117">子要素</span><span class="sxs-lookup"><span data-stu-id="8d62e-117">Child Elements</span></span>  
 <span data-ttu-id="8d62e-118">なし。</span><span class="sxs-lookup"><span data-stu-id="8d62e-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8d62e-119">親要素</span><span class="sxs-lookup"><span data-stu-id="8d62e-119">Parent Elements</span></span>  
  
|<span data-ttu-id="8d62e-120">要素</span><span class="sxs-lookup"><span data-stu-id="8d62e-120">Element</span></span>|<span data-ttu-id="8d62e-121">説明</span><span class="sxs-lookup"><span data-stu-id="8d62e-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8d62e-122">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="8d62e-122">\<serviceCredentials></span></span>](servicecredentials.md)|<span data-ttu-id="8d62e-123">サービスの認証に使用される資格情報と、クライアントの資格情報検証関連の設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="8d62e-123">Specifies the credential to be used in authenticating the service, and the client credential validation-related settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8d62e-124">Remarks</span><span class="sxs-lookup"><span data-stu-id="8d62e-124">Remarks</span></span>  
 <span data-ttu-id="8d62e-125">この構成要素を使用して、セキュリティ コンテキスト トークン (SCT) クッキーのシリアル化のための既知のクレームの種類のリストと、クッキーの情報をエンコードしてセキュリティで保護するためのエンコーダーを指定します。</span><span class="sxs-lookup"><span data-stu-id="8d62e-125">Use this configuration element to specify a list of known claim types for the Security Context Token (SCT) cookies serialization, as well as an encoder to encode and secure cookies information.</span></span> <span data-ttu-id="8d62e-126">SCT の詳細については、「<xref:System.ServiceModel.Security.SecureConversationServiceCredential>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8d62e-126">For more information on SCT, see <xref:System.ServiceModel.Security.SecureConversationServiceCredential>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d62e-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="8d62e-127">See also</span></span>

- <xref:System.ServiceModel.Configuration.SecureConversationServiceElement>
- <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.SecureConversationAuthentication%2A>
- <xref:System.ServiceModel.Description.ServiceCredentials.SecureConversationAuthentication%2A>
- <xref:System.ServiceModel.Security.SecureConversationServiceCredential>
