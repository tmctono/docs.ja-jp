---
title: <remove><claimTypeRequirements>要素の
ms.date: 03/30/2017
ms.assetid: 8ef05bc4-1950-4ee4-95c5-1c6a394eff7e
ms.openlocfilehash: 84f4208d3f4581cf7e8c4455bf3f5d78f7e13b9f
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "70399996"
---
# <a name="remove-of-claimtyperequirements-element"></a><span data-ttu-id="d69ca-102">\<remove>\<claimTypeRequirements>要素の</span><span class="sxs-lookup"><span data-stu-id="d69ca-102">\<remove> of \<claimTypeRequirements> element</span></span>
<span data-ttu-id="d69ca-103">フェデレーション資格情報から削除するクレームの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="d69ca-103">Specifies the types of claims to be removed in the federated credential.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsFederationHttpBinding>**](wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<message>**](message-element-of-wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<claimTypeRequirements>**](claimtyperequirements-for-message.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**  
  
## <a name="syntax"></a><span data-ttu-id="d69ca-104">構文</span><span class="sxs-lookup"><span data-stu-id="d69ca-104">Syntax</span></span>  
  
```xml  
<claimTypeRequirements>
  <remove claimType="URI" />
</claimTypeRequirements>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d69ca-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="d69ca-105">Attributes and Elements</span></span>  
 <span data-ttu-id="d69ca-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="d69ca-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d69ca-107">属性</span><span class="sxs-lookup"><span data-stu-id="d69ca-107">Attributes</span></span>  
  
|<span data-ttu-id="d69ca-108">属性</span><span class="sxs-lookup"><span data-stu-id="d69ca-108">Attribute</span></span>|<span data-ttu-id="d69ca-109">説明</span><span class="sxs-lookup"><span data-stu-id="d69ca-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d69ca-110">claimType</span><span class="sxs-lookup"><span data-stu-id="d69ca-110">claimType</span></span>|<span data-ttu-id="d69ca-111">削除するクレームの種類を定義する URI。</span><span class="sxs-lookup"><span data-stu-id="d69ca-111">A URI that defines the type of a claim to be removed.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d69ca-112">子要素</span><span class="sxs-lookup"><span data-stu-id="d69ca-112">Child Elements</span></span>  
 <span data-ttu-id="d69ca-113">なし。</span><span class="sxs-lookup"><span data-stu-id="d69ca-113">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d69ca-114">親要素</span><span class="sxs-lookup"><span data-stu-id="d69ca-114">Parent Elements</span></span>  
  
|<span data-ttu-id="d69ca-115">要素</span><span class="sxs-lookup"><span data-stu-id="d69ca-115">Element</span></span>|<span data-ttu-id="d69ca-116">Description</span><span class="sxs-lookup"><span data-stu-id="d69ca-116">Description</span></span>|  
|-------------|-----------------|  
|[\<claimTypeRequirements>](claimtyperequirements-for-message.md)|<span data-ttu-id="d69ca-117">必須のクレームの種類のコレクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="d69ca-117">Specifies a collection of required claim types.</span></span> <span data-ttu-id="d69ca-118">各要素は <xref:System.ServiceModel.Configuration.ClaimTypeElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="d69ca-118">Each element is of type <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span></span><br /><br /> <span data-ttu-id="d69ca-119">フェデレーション シナリオでは、サービスが受信資格情報についての要件を記述します。</span><span class="sxs-lookup"><span data-stu-id="d69ca-119">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="d69ca-120">たとえば、受信資格情報は、特定のクレーム タイプのセットを処理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d69ca-120">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="d69ca-121">このコレクションの要素はそれぞれ、フェデレーション資格情報に表示されると予想される必須の要求および省略可能な要求の種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="d69ca-121">Each element in this collection specifies the types of required and optional claims expected to appear in a federated credential.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d69ca-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="d69ca-122">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Security.Tokens.ClaimTypeRequirement>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Configuration.ClaimTypeElementCollection>
- <xref:System.ServiceModel.Configuration.ClaimTypeElement>
