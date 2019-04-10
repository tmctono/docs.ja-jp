---
title: <xmlElement>
ms.date: 03/30/2017
ms.assetid: 395205c2-d8c0-4a5e-90f3-7ce3c085fccd
ms.openlocfilehash: a72641b438801cfd493c322297e7c384e83e687c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59230500"
---
# <a name="xmlelement"></a><span data-ttu-id="91c7e-101">\<xmlElement></span><span class="sxs-lookup"><span data-stu-id="91c7e-101">\<xmlElement></span></span>
<span data-ttu-id="91c7e-102">トークンの要求時にセキュリティ トークン サービスへのメッセージ本文で送信される XML 要素を指定します。</span><span class="sxs-lookup"><span data-stu-id="91c7e-102">Specifies an XML element that is sent in the message body to the Security Token Service when requesting a token.</span></span>  
  
 <span data-ttu-id="91c7e-103">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="91c7e-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="91c7e-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="91c7e-104">\<bindings></span></span>  
<span data-ttu-id="91c7e-105">\<wsFederatedBinding></span><span class="sxs-lookup"><span data-stu-id="91c7e-105">\<wsFederatedBinding></span></span>  
<span data-ttu-id="91c7e-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="91c7e-106">\<binding></span></span>  
<span data-ttu-id="91c7e-107">\<セキュリティ ></span><span class="sxs-lookup"><span data-stu-id="91c7e-107">\<security></span></span>  
<span data-ttu-id="91c7e-108">\<message></span><span class="sxs-lookup"><span data-stu-id="91c7e-108">\<message></span></span>  
<span data-ttu-id="91c7e-109">\<tokenRequestParameters></span><span class="sxs-lookup"><span data-stu-id="91c7e-109">\<tokenRequestParameters></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="91c7e-110">構文</span><span class="sxs-lookup"><span data-stu-id="91c7e-110">Syntax</span></span>  
  
```xml  
<tokenRequestParameters>
  <xmlElement xmlElement="String" />
</tokenRequestParameters>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="91c7e-111">属性および要素</span><span class="sxs-lookup"><span data-stu-id="91c7e-111">Attributes and Elements</span></span>  
 <span data-ttu-id="91c7e-112">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="91c7e-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="91c7e-113">属性</span><span class="sxs-lookup"><span data-stu-id="91c7e-113">Attributes</span></span>  
  
|<span data-ttu-id="91c7e-114">属性</span><span class="sxs-lookup"><span data-stu-id="91c7e-114">Attribute</span></span>|<span data-ttu-id="91c7e-115">説明</span><span class="sxs-lookup"><span data-stu-id="91c7e-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="91c7e-116">xmlElement</span><span class="sxs-lookup"><span data-stu-id="91c7e-116">xmlElement</span></span>|<span data-ttu-id="91c7e-117">トークンの要求時にセキュリティ トークン サービスへのメッセージ本文で送信される XML 要素を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="91c7e-117">A string specifying an XML element that is sent in the message body to the Security Token Service when requesting a token.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="91c7e-118">子要素</span><span class="sxs-lookup"><span data-stu-id="91c7e-118">Child Elements</span></span>  
 <span data-ttu-id="91c7e-119">なし。</span><span class="sxs-lookup"><span data-stu-id="91c7e-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="91c7e-120">親要素</span><span class="sxs-lookup"><span data-stu-id="91c7e-120">Parent Elements</span></span>  
  
|<span data-ttu-id="91c7e-121">要素</span><span class="sxs-lookup"><span data-stu-id="91c7e-121">Element</span></span>|<span data-ttu-id="91c7e-122">説明</span><span class="sxs-lookup"><span data-stu-id="91c7e-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="91c7e-123">\<tokenRequestParameters></span><span class="sxs-lookup"><span data-stu-id="91c7e-123">\<tokenRequestParameters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/tokenrequestparameters.md)|<span data-ttu-id="91c7e-124">トークン要求パラメーターのコレクション。</span><span class="sxs-lookup"><span data-stu-id="91c7e-124">A collection of token request parameters.</span></span> <span data-ttu-id="91c7e-125">各パラメーターは、XML 要素です。</span><span class="sxs-lookup"><span data-stu-id="91c7e-125">Each parameter is an XML element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="91c7e-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="91c7e-126">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.TokenRequestParameters%2A>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.TokenRequestParameters%2A>
- [<span data-ttu-id="91c7e-127">サービス ID と認証</span><span class="sxs-lookup"><span data-stu-id="91c7e-127">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="91c7e-128">フェデレーションと発行済みトークン</span><span class="sxs-lookup"><span data-stu-id="91c7e-128">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="91c7e-129">カスタム バインドを使用したセキュリティ機能</span><span class="sxs-lookup"><span data-stu-id="91c7e-129">Security Capabilities with Custom Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="91c7e-130">フェデレーションと発行済みトークン</span><span class="sxs-lookup"><span data-stu-id="91c7e-130">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="91c7e-131">バインディング</span><span class="sxs-lookup"><span data-stu-id="91c7e-131">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
