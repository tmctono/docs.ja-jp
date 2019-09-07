---
title: <xmlElement>
ms.date: 03/30/2017
ms.assetid: 395205c2-d8c0-4a5e-90f3-7ce3c085fccd
ms.openlocfilehash: 841331f233bb8c42c25c88ad8e9b4fb1a86faa76
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398997"
---
# <a name="xmlelement"></a><span data-ttu-id="a62dd-101">\<xmlElement></span><span class="sxs-lookup"><span data-stu-id="a62dd-101">\<xmlElement></span></span>
<span data-ttu-id="a62dd-102">トークンの要求時にセキュリティ トークン サービスへのメッセージ本文で送信される XML 要素を指定します。</span><span class="sxs-lookup"><span data-stu-id="a62dd-102">Specifies an XML element that is sent in the message body to the Security Token Service when requesting a token.</span></span>  
  
<span data-ttu-id="a62dd-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="a62dd-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="a62dd-104">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="a62dd-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="a62dd-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<バインド >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="a62dd-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="a62dd-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<wsFederationHttpBinding >** ](wsfederationhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="a62dd-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsFederationHttpBinding>**](wsfederationhttpbinding.md)</span></span>\
<span data-ttu-id="a62dd-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<バインド >** </span><span class="sxs-lookup"><span data-stu-id="a62dd-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="a62dd-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<セキュリティ >** ](security-of-wsfederationhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="a62dd-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-wsfederationhttpbinding.md)</span></span>\
<span data-ttu-id="a62dd-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<メッセージ >** ](message-element-of-wsfederationhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="a62dd-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<message>**](message-element-of-wsfederationhttpbinding.md)</span></span>\
<span data-ttu-id="a62dd-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<tokenRequestParameters >** ](tokenrequestparameters.md)</span><span class="sxs-lookup"><span data-stu-id="a62dd-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<tokenRequestParameters>**](tokenrequestparameters.md)</span></span>\
<span data-ttu-id="a62dd-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<xmlElement >**</span><span class="sxs-lookup"><span data-stu-id="a62dd-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<xmlElement>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a62dd-112">構文</span><span class="sxs-lookup"><span data-stu-id="a62dd-112">Syntax</span></span>  
  
```xml  
<tokenRequestParameters>
  <xmlElement xmlElement="String" />
</tokenRequestParameters>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a62dd-113">属性および要素</span><span class="sxs-lookup"><span data-stu-id="a62dd-113">Attributes and Elements</span></span>  
 <span data-ttu-id="a62dd-114">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="a62dd-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a62dd-115">属性</span><span class="sxs-lookup"><span data-stu-id="a62dd-115">Attributes</span></span>  
  
|<span data-ttu-id="a62dd-116">属性</span><span class="sxs-lookup"><span data-stu-id="a62dd-116">Attribute</span></span>|<span data-ttu-id="a62dd-117">説明</span><span class="sxs-lookup"><span data-stu-id="a62dd-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a62dd-118">xmlElement</span><span class="sxs-lookup"><span data-stu-id="a62dd-118">xmlElement</span></span>|<span data-ttu-id="a62dd-119">トークンの要求時にセキュリティ トークン サービスへのメッセージ本文で送信される XML 要素を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="a62dd-119">A string specifying an XML element that is sent in the message body to the Security Token Service when requesting a token.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a62dd-120">子要素</span><span class="sxs-lookup"><span data-stu-id="a62dd-120">Child Elements</span></span>  
 <span data-ttu-id="a62dd-121">なし。</span><span class="sxs-lookup"><span data-stu-id="a62dd-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a62dd-122">親要素</span><span class="sxs-lookup"><span data-stu-id="a62dd-122">Parent Elements</span></span>  
  
|<span data-ttu-id="a62dd-123">要素</span><span class="sxs-lookup"><span data-stu-id="a62dd-123">Element</span></span>|<span data-ttu-id="a62dd-124">説明</span><span class="sxs-lookup"><span data-stu-id="a62dd-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a62dd-125">\<tokenRequestParameters></span><span class="sxs-lookup"><span data-stu-id="a62dd-125">\<tokenRequestParameters></span></span>](tokenrequestparameters.md)|<span data-ttu-id="a62dd-126">トークン要求パラメーターのコレクション。</span><span class="sxs-lookup"><span data-stu-id="a62dd-126">A collection of token request parameters.</span></span> <span data-ttu-id="a62dd-127">各パラメーターは、XML 要素です。</span><span class="sxs-lookup"><span data-stu-id="a62dd-127">Each parameter is an XML element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a62dd-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="a62dd-128">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.TokenRequestParameters%2A>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.TokenRequestParameters%2A>
- [<span data-ttu-id="a62dd-129">サービス ID と認証</span><span class="sxs-lookup"><span data-stu-id="a62dd-129">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="a62dd-130">フェデレーションと発行済みトークン</span><span class="sxs-lookup"><span data-stu-id="a62dd-130">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="a62dd-131">カスタム バインドを使用したセキュリティ機能</span><span class="sxs-lookup"><span data-stu-id="a62dd-131">Security Capabilities with Custom Bindings</span></span>](../../../wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="a62dd-132">フェデレーションと発行済みトークン</span><span class="sxs-lookup"><span data-stu-id="a62dd-132">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="a62dd-133">バインディング</span><span class="sxs-lookup"><span data-stu-id="a62dd-133">Bindings</span></span>](../../../wcf/bindings.md)
