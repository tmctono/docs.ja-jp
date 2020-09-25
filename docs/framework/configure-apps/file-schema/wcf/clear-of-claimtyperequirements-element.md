---
title: <clear><claimTypeRequirements>要素の
ms.date: 03/30/2017
ms.assetid: ef42fde7-f292-4610-9111-9fea382c3b5f
ms.openlocfilehash: aa94a012da11bcec6fb5fe270ad9f3574f88e6d7
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91172906"
---
# <a name="clear-of-claimtyperequirements-element"></a><span data-ttu-id="c4240-102">\<clear>\<claimTypeRequirements>要素の</span><span class="sxs-lookup"><span data-stu-id="c4240-102">\<clear> of \<claimTypeRequirements> element</span></span>

<span data-ttu-id="c4240-103">すべてのクレームの種類をフェデレーション資格情報から削除するように指定します。</span><span class="sxs-lookup"><span data-stu-id="c4240-103">Specifies that all the claim types to be removed in the federated credential.</span></span> <span data-ttu-id="c4240-104">これにより、コレクションの初期値を確実に空にできます。</span><span class="sxs-lookup"><span data-stu-id="c4240-104">This ensures that the collection starts empty.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsFederationHttpBinding>**](wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<message>**](message-element-of-wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<claimTypeRequirements>**](claimtyperequirements-for-message.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**  
  
## <a name="syntax"></a><span data-ttu-id="c4240-105">構文</span><span class="sxs-lookup"><span data-stu-id="c4240-105">Syntax</span></span>  
  
```xml  
<claimTypeRequirements>
  <clear />
</claimTypeRequirements>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c4240-106">属性および要素</span><span class="sxs-lookup"><span data-stu-id="c4240-106">Attributes and Elements</span></span>  

 <span data-ttu-id="c4240-107">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="c4240-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c4240-108">属性</span><span class="sxs-lookup"><span data-stu-id="c4240-108">Attributes</span></span>  

 <span data-ttu-id="c4240-109">なし。</span><span class="sxs-lookup"><span data-stu-id="c4240-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="c4240-110">子要素</span><span class="sxs-lookup"><span data-stu-id="c4240-110">Child Elements</span></span>  

 <span data-ttu-id="c4240-111">なし。</span><span class="sxs-lookup"><span data-stu-id="c4240-111">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c4240-112">親要素</span><span class="sxs-lookup"><span data-stu-id="c4240-112">Parent Elements</span></span>  
  
|<span data-ttu-id="c4240-113">要素</span><span class="sxs-lookup"><span data-stu-id="c4240-113">Element</span></span>|<span data-ttu-id="c4240-114">説明</span><span class="sxs-lookup"><span data-stu-id="c4240-114">Description</span></span>|  
|-------------|-----------------|  
|[\<claimTypeRequirements>](claimtyperequirements-for-message.md)|<span data-ttu-id="c4240-115">必須のクレームの種類のコレクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="c4240-115">Specifies a collection of required claim types.</span></span> <span data-ttu-id="c4240-116">各要素は <xref:System.ServiceModel.Configuration.ClaimTypeElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="c4240-116">Each element is of type <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span></span><br /><br /> <span data-ttu-id="c4240-117">フェデレーション シナリオでは、サービスが受信資格情報についての要件を記述します。</span><span class="sxs-lookup"><span data-stu-id="c4240-117">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="c4240-118">たとえば、受信資格情報は、特定のクレーム タイプのセットを処理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c4240-118">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="c4240-119">このコレクションの要素はそれぞれ、フェデレーション資格情報に表示されると予想される必須の要求および省略可能な要求の種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="c4240-119">Each element in this collection specifies the types of required and optional claims expected to appear in a federated credential.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c4240-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="c4240-120">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Security.Tokens.ClaimTypeRequirement>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Configuration.ClaimTypeElementCollection>
- <xref:System.ServiceModel.Configuration.ClaimTypeElement>
