---
title: <secureConversationAuthentication> の <serviceCredential>
ms.date: 03/30/2017
ms.assetid: 0bd3fac7-befd-4a45-ba51-c200b33be0fd
ms.openlocfilehash: 336969c654f332ae3d838d8fd6d1c4243838539c
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "70399934"
---
# <a name="secureconversationauthentication-of-servicecredential"></a><span data-ttu-id="e9a2f-102">\<secureConversationAuthentication> の \<serviceCredential></span><span class="sxs-lookup"><span data-stu-id="e9a2f-102">\<secureConversationAuthentication> of \<serviceCredential></span></span>
<span data-ttu-id="e9a2f-103">安全な会話サービスの設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="e9a2f-103">Specifies the settings for a secure conversation service.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCredentials>**](servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<secureConversationAuthentication>**  
  
## <a name="syntax"></a><span data-ttu-id="e9a2f-104">構文</span><span class="sxs-lookup"><span data-stu-id="e9a2f-104">Syntax</span></span>  
  
```xml  
<secureConversationAuthentication securityStateEncoderType="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e9a2f-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="e9a2f-105">Attributes and Elements</span></span>  
 <span data-ttu-id="e9a2f-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="e9a2f-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e9a2f-107">属性</span><span class="sxs-lookup"><span data-stu-id="e9a2f-107">Attributes</span></span>  
  
|<span data-ttu-id="e9a2f-108">属性</span><span class="sxs-lookup"><span data-stu-id="e9a2f-108">Attribute</span></span>|<span data-ttu-id="e9a2f-109">説明</span><span class="sxs-lookup"><span data-stu-id="e9a2f-109">Description</span></span>|  
|---------------|-----------------|  
|`securityStateEncoderType`|<span data-ttu-id="e9a2f-110">使用される <xref:System.ServiceModel.Security.SecurityStateEncoder> の型を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="e9a2f-110">A string that specifies the type of <xref:System.ServiceModel.Security.SecurityStateEncoder> to be used.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e9a2f-111">子要素</span><span class="sxs-lookup"><span data-stu-id="e9a2f-111">Child Elements</span></span>  
 <span data-ttu-id="e9a2f-112">なし。</span><span class="sxs-lookup"><span data-stu-id="e9a2f-112">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e9a2f-113">親要素</span><span class="sxs-lookup"><span data-stu-id="e9a2f-113">Parent Elements</span></span>  
  
|<span data-ttu-id="e9a2f-114">要素</span><span class="sxs-lookup"><span data-stu-id="e9a2f-114">Element</span></span>|<span data-ttu-id="e9a2f-115">Description</span><span class="sxs-lookup"><span data-stu-id="e9a2f-115">Description</span></span>|  
|-------------|-----------------|  
|[\<serviceCredentials>](servicecredentials.md)|<span data-ttu-id="e9a2f-116">サービスの認証に使用される資格情報と、クライアントの資格情報検証関連の設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="e9a2f-116">Specifies the credential to be used in authenticating the service, and the client credential validation-related settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e9a2f-117">解説</span><span class="sxs-lookup"><span data-stu-id="e9a2f-117">Remarks</span></span>  
 <span data-ttu-id="e9a2f-118">この構成要素を使用して、セキュリティ コンテキスト トークン (SCT) クッキーのシリアル化のための既知のクレームの種類のリストと、クッキーの情報をエンコードしてセキュリティで保護するためのエンコーダーを指定します。</span><span class="sxs-lookup"><span data-stu-id="e9a2f-118">Use this configuration element to specify a list of known claim types for the Security Context Token (SCT) cookies serialization, as well as an encoder to encode and secure cookies information.</span></span> <span data-ttu-id="e9a2f-119">SCT の詳細については、「<xref:System.ServiceModel.Security.SecureConversationServiceCredential>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e9a2f-119">For more information on SCT, see <xref:System.ServiceModel.Security.SecureConversationServiceCredential>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9a2f-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="e9a2f-120">See also</span></span>

- <xref:System.ServiceModel.Configuration.SecureConversationServiceElement>
- <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.SecureConversationAuthentication%2A>
- <xref:System.ServiceModel.Description.ServiceCredentials.SecureConversationAuthentication%2A>
- <xref:System.ServiceModel.Security.SecureConversationServiceCredential>
