---
title: <secureConversationAuthentication> の <serviceCredential>
ms.date: 03/30/2017
ms.assetid: 0bd3fac7-befd-4a45-ba51-c200b33be0fd
ms.openlocfilehash: f35392b91d047c46e65ce433ef544b86cf6c88c6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61670613"
---
# <a name="secureconversationauthentication-of-servicecredential"></a><span data-ttu-id="6a6be-102">\<secureConversationAuthentication > の\<serviceCredential ></span><span class="sxs-lookup"><span data-stu-id="6a6be-102">\<secureConversationAuthentication> of \<serviceCredential></span></span>
<span data-ttu-id="6a6be-103">安全な会話サービスの設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="6a6be-103">Specifies the settings for a secure conversation service.</span></span>  
  
 <span data-ttu-id="6a6be-104">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="6a6be-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="6a6be-105">\<<behaviors></span><span class="sxs-lookup"><span data-stu-id="6a6be-105">\<behaviors></span></span>  
<span data-ttu-id="6a6be-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="6a6be-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="6a6be-107">\<behavior></span><span class="sxs-lookup"><span data-stu-id="6a6be-107">\<behavior></span></span>  
<span data-ttu-id="6a6be-108">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="6a6be-108">\<serviceCredentials></span></span>  
<span data-ttu-id="6a6be-109">\<secureConversationAuthentication></span><span class="sxs-lookup"><span data-stu-id="6a6be-109">\<secureConversationAuthentication></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6a6be-110">構文</span><span class="sxs-lookup"><span data-stu-id="6a6be-110">Syntax</span></span>  
  
```xml  
<secureConversationAuthentication securityStateEncoderType="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6a6be-111">属性および要素</span><span class="sxs-lookup"><span data-stu-id="6a6be-111">Attributes and Elements</span></span>  
 <span data-ttu-id="6a6be-112">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="6a6be-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6a6be-113">属性</span><span class="sxs-lookup"><span data-stu-id="6a6be-113">Attributes</span></span>  
  
|<span data-ttu-id="6a6be-114">属性</span><span class="sxs-lookup"><span data-stu-id="6a6be-114">Attribute</span></span>|<span data-ttu-id="6a6be-115">説明</span><span class="sxs-lookup"><span data-stu-id="6a6be-115">Description</span></span>|  
|---------------|-----------------|  
|`securityStateEncoderType`|<span data-ttu-id="6a6be-116">使用される <xref:System.ServiceModel.Security.SecurityStateEncoder> の型を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="6a6be-116">A string that specifies the type of <xref:System.ServiceModel.Security.SecurityStateEncoder> to be used.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6a6be-117">子要素</span><span class="sxs-lookup"><span data-stu-id="6a6be-117">Child Elements</span></span>  
 <span data-ttu-id="6a6be-118">なし。</span><span class="sxs-lookup"><span data-stu-id="6a6be-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6a6be-119">親要素</span><span class="sxs-lookup"><span data-stu-id="6a6be-119">Parent Elements</span></span>  
  
|<span data-ttu-id="6a6be-120">要素</span><span class="sxs-lookup"><span data-stu-id="6a6be-120">Element</span></span>|<span data-ttu-id="6a6be-121">説明</span><span class="sxs-lookup"><span data-stu-id="6a6be-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6a6be-122">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="6a6be-122">\<serviceCredentials></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md)|<span data-ttu-id="6a6be-123">サービスの認証に使用される資格情報と、クライアントの資格情報検証関連の設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="6a6be-123">Specifies the credential to be used in authenticating the service, and the client credential validation-related settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6a6be-124">Remarks</span><span class="sxs-lookup"><span data-stu-id="6a6be-124">Remarks</span></span>  
 <span data-ttu-id="6a6be-125">この構成要素を使用して、セキュリティ コンテキスト トークン (SCT) クッキーのシリアル化のための既知のクレームの種類のリストと、クッキーの情報をエンコードしてセキュリティで保護するためのエンコーダーを指定します。</span><span class="sxs-lookup"><span data-stu-id="6a6be-125">Use this configuration element to specify a list of known claim types for the Security Context Token (SCT) cookies serialization, as well as an encoder to encode and secure cookies information.</span></span> <span data-ttu-id="6a6be-126">SCT の詳細については、「<xref:System.ServiceModel.Security.SecureConversationServiceCredential>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6a6be-126">For more information on SCT, see <xref:System.ServiceModel.Security.SecureConversationServiceCredential>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a6be-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="6a6be-127">See also</span></span>

- <xref:System.ServiceModel.Configuration.SecureConversationServiceElement>
- <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.SecureConversationAuthentication%2A>
- <xref:System.ServiceModel.Description.ServiceCredentials.SecureConversationAuthentication%2A>
- <xref:System.ServiceModel.Security.SecureConversationServiceCredential>
