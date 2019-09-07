---
title: <secureConversationAuthentication> の <serviceCredential>
ms.date: 03/30/2017
ms.assetid: 0bd3fac7-befd-4a45-ba51-c200b33be0fd
ms.openlocfilehash: 336969c654f332ae3d838d8fd6d1c4243838539c
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399934"
---
# <a name="secureconversationauthentication-of-servicecredential"></a><span data-ttu-id="95230-102">\<serviceCredential の\<secureConversationAuthentication > ></span><span class="sxs-lookup"><span data-stu-id="95230-102">\<secureConversationAuthentication> of \<serviceCredential></span></span>
<span data-ttu-id="95230-103">安全な会話サービスの設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="95230-103">Specifies the settings for a secure conversation service.</span></span>  
  
<span data-ttu-id="95230-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="95230-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="95230-105">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="95230-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="95230-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<動作 >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="95230-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="95230-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceBehaviors >** ](servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="95230-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)</span></span>\
<span data-ttu-id="95230-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<動作 >** ](behavior-of-servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="95230-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)</span></span>\
<span data-ttu-id="95230-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceCredentials >** ](servicecredentials.md)</span><span class="sxs-lookup"><span data-stu-id="95230-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCredentials>**](servicecredentials.md)</span></span>\
<span data-ttu-id="95230-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<secureConversationAuthentication >**</span><span class="sxs-lookup"><span data-stu-id="95230-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<secureConversationAuthentication>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="95230-111">構文</span><span class="sxs-lookup"><span data-stu-id="95230-111">Syntax</span></span>  
  
```xml  
<secureConversationAuthentication securityStateEncoderType="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="95230-112">属性および要素</span><span class="sxs-lookup"><span data-stu-id="95230-112">Attributes and Elements</span></span>  
 <span data-ttu-id="95230-113">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="95230-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="95230-114">属性</span><span class="sxs-lookup"><span data-stu-id="95230-114">Attributes</span></span>  
  
|<span data-ttu-id="95230-115">属性</span><span class="sxs-lookup"><span data-stu-id="95230-115">Attribute</span></span>|<span data-ttu-id="95230-116">説明</span><span class="sxs-lookup"><span data-stu-id="95230-116">Description</span></span>|  
|---------------|-----------------|  
|`securityStateEncoderType`|<span data-ttu-id="95230-117">使用される <xref:System.ServiceModel.Security.SecurityStateEncoder> の型を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="95230-117">A string that specifies the type of <xref:System.ServiceModel.Security.SecurityStateEncoder> to be used.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="95230-118">子要素</span><span class="sxs-lookup"><span data-stu-id="95230-118">Child Elements</span></span>  
 <span data-ttu-id="95230-119">なし。</span><span class="sxs-lookup"><span data-stu-id="95230-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="95230-120">親要素</span><span class="sxs-lookup"><span data-stu-id="95230-120">Parent Elements</span></span>  
  
|<span data-ttu-id="95230-121">要素</span><span class="sxs-lookup"><span data-stu-id="95230-121">Element</span></span>|<span data-ttu-id="95230-122">説明</span><span class="sxs-lookup"><span data-stu-id="95230-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="95230-123">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="95230-123">\<serviceCredentials></span></span>](servicecredentials.md)|<span data-ttu-id="95230-124">サービスの認証に使用される資格情報と、クライアントの資格情報検証関連の設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="95230-124">Specifies the credential to be used in authenticating the service, and the client credential validation-related settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="95230-125">Remarks</span><span class="sxs-lookup"><span data-stu-id="95230-125">Remarks</span></span>  
 <span data-ttu-id="95230-126">この構成要素を使用して、セキュリティ コンテキスト トークン (SCT) クッキーのシリアル化のための既知のクレームの種類のリストと、クッキーの情報をエンコードしてセキュリティで保護するためのエンコーダーを指定します。</span><span class="sxs-lookup"><span data-stu-id="95230-126">Use this configuration element to specify a list of known claim types for the Security Context Token (SCT) cookies serialization, as well as an encoder to encode and secure cookies information.</span></span> <span data-ttu-id="95230-127">SCT の詳細については、「<xref:System.ServiceModel.Security.SecureConversationServiceCredential>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="95230-127">For more information on SCT, see <xref:System.ServiceModel.Security.SecureConversationServiceCredential>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95230-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="95230-128">See also</span></span>

- <xref:System.ServiceModel.Configuration.SecureConversationServiceElement>
- <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.SecureConversationAuthentication%2A>
- <xref:System.ServiceModel.Description.ServiceCredentials.SecureConversationAuthentication%2A>
- <xref:System.ServiceModel.Security.SecureConversationServiceCredential>
