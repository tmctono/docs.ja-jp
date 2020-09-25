---
title: <xmlElement>
ms.date: 03/30/2017
ms.assetid: 395205c2-d8c0-4a5e-90f3-7ce3c085fccd
ms.openlocfilehash: 0ab7fbd64cc92e940617f5334eeb16fcb3a50c4a
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91181233"
---
# \<xmlElement>

<span data-ttu-id="56daf-101">トークンの要求時にセキュリティ トークン サービスへのメッセージ本文で送信される XML 要素を指定します。</span><span class="sxs-lookup"><span data-stu-id="56daf-101">Specifies an XML element that is sent in the message body to the Security Token Service when requesting a token.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsFederationHttpBinding>**](wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<message>**](message-element-of-wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<tokenRequestParameters>**](tokenrequestparameters.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<xmlElement>**  
  
## <a name="syntax"></a><span data-ttu-id="56daf-102">構文</span><span class="sxs-lookup"><span data-stu-id="56daf-102">Syntax</span></span>  
  
```xml  
<tokenRequestParameters>
  <xmlElement xmlElement="String" />
</tokenRequestParameters>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="56daf-103">属性および要素</span><span class="sxs-lookup"><span data-stu-id="56daf-103">Attributes and Elements</span></span>  

 <span data-ttu-id="56daf-104">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="56daf-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="56daf-105">属性</span><span class="sxs-lookup"><span data-stu-id="56daf-105">Attributes</span></span>  
  
|<span data-ttu-id="56daf-106">属性</span><span class="sxs-lookup"><span data-stu-id="56daf-106">Attribute</span></span>|<span data-ttu-id="56daf-107">[説明]</span><span class="sxs-lookup"><span data-stu-id="56daf-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="56daf-108">xmlElement</span><span class="sxs-lookup"><span data-stu-id="56daf-108">xmlElement</span></span>|<span data-ttu-id="56daf-109">トークンの要求時にセキュリティ トークン サービスへのメッセージ本文で送信される XML 要素を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="56daf-109">A string specifying an XML element that is sent in the message body to the Security Token Service when requesting a token.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="56daf-110">子要素</span><span class="sxs-lookup"><span data-stu-id="56daf-110">Child Elements</span></span>  

 <span data-ttu-id="56daf-111">なし。</span><span class="sxs-lookup"><span data-stu-id="56daf-111">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="56daf-112">親要素</span><span class="sxs-lookup"><span data-stu-id="56daf-112">Parent Elements</span></span>  
  
|<span data-ttu-id="56daf-113">要素</span><span class="sxs-lookup"><span data-stu-id="56daf-113">Element</span></span>|<span data-ttu-id="56daf-114">説明</span><span class="sxs-lookup"><span data-stu-id="56daf-114">Description</span></span>|  
|-------------|-----------------|  
|[\<tokenRequestParameters>](tokenrequestparameters.md)|<span data-ttu-id="56daf-115">トークン要求パラメーターのコレクション。</span><span class="sxs-lookup"><span data-stu-id="56daf-115">A collection of token request parameters.</span></span> <span data-ttu-id="56daf-116">各パラメーターは、XML 要素です。</span><span class="sxs-lookup"><span data-stu-id="56daf-116">Each parameter is an XML element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="56daf-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="56daf-117">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.TokenRequestParameters%2A>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.TokenRequestParameters%2A>
- [<span data-ttu-id="56daf-118">サービス ID と認証</span><span class="sxs-lookup"><span data-stu-id="56daf-118">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="56daf-119">フェデレーションと発行済みトークン</span><span class="sxs-lookup"><span data-stu-id="56daf-119">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="56daf-120">カスタム バインディングを使用したセキュリティ機能</span><span class="sxs-lookup"><span data-stu-id="56daf-120">Security Capabilities with Custom Bindings</span></span>](../../../wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="56daf-121">フェデレーションと発行済みトークン</span><span class="sxs-lookup"><span data-stu-id="56daf-121">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="56daf-122">バインド</span><span class="sxs-lookup"><span data-stu-id="56daf-122">Bindings</span></span>](../../../wcf/bindings.md)
