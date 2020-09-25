---
title: <windowsAuthentication> の <serviceCredentials>
ms.date: 03/30/2017
ms.assetid: e0709473-0997-4de3-8f49-783527309a48
ms.openlocfilehash: bda375959b535ce5f2996d594f719893164b0bd4
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91195000"
---
# <a name="windowsauthentication-of-servicecredentials"></a><span data-ttu-id="44b18-102">\<windowsAuthentication> の \<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="44b18-102">\<windowsAuthentication> of \<serviceCredentials></span></span>

<span data-ttu-id="44b18-103">Windows サービス資格情報の設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="44b18-103">Specifies the settings of a Windows service credential.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCredentials>**](servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<windowsAuthentication>**  
  
## <a name="syntax"></a><span data-ttu-id="44b18-104">構文</span><span class="sxs-lookup"><span data-stu-id="44b18-104">Syntax</span></span>  
  
```xml  
<windowsAuthentication allowAnonymousLogons="Boolean"
                       includeWindowsGroups="Boolean" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="44b18-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="44b18-105">Attributes and Elements</span></span>  

 <span data-ttu-id="44b18-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="44b18-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="44b18-107">属性</span><span class="sxs-lookup"><span data-stu-id="44b18-107">Attributes</span></span>  
  
|<span data-ttu-id="44b18-108">属性</span><span class="sxs-lookup"><span data-stu-id="44b18-108">Attribute</span></span>|<span data-ttu-id="44b18-109">[説明]</span><span class="sxs-lookup"><span data-stu-id="44b18-109">Description</span></span>|  
|---------------|-----------------|  
|`includeWindowsGroups`|<span data-ttu-id="44b18-110">セキュリティ コンテキストに Windows グループが含まれるかどうかを指定する省略可能なブール属性。</span><span class="sxs-lookup"><span data-stu-id="44b18-110">An optional Boolean attribute that specifies whether the system includes Windows groups in the security context.</span></span> <span data-ttu-id="44b18-111">既定では、 `true`です。</span><span class="sxs-lookup"><span data-stu-id="44b18-111">The default is `true`.</span></span><br /><br /> <span data-ttu-id="44b18-112">この属性を `true` に設定すると、グループ全体が拡張されるため、パフォーマンスに影響が及びます。</span><span class="sxs-lookup"><span data-stu-id="44b18-112">Setting this attribute to `true` has a performance impact as it results in a full-group expansion.</span></span> <span data-ttu-id="44b18-113">ユーザーが属するグループの一覧を生成する必要がない場合は、この属性を `false` に設定します。</span><span class="sxs-lookup"><span data-stu-id="44b18-113">Set this attribute to `false` if you do not need to establish the list of groups a user belongs to.</span></span>|  
|`allowAnonymousLogons`|<span data-ttu-id="44b18-114">認証されていない匿名の呼び出し元を許可するかどうかを指定する省略可能なブール属性。</span><span class="sxs-lookup"><span data-stu-id="44b18-114">An optional Boolean attribute that specifies whether anonymous, unauthenticated callers are allowed.</span></span> <span data-ttu-id="44b18-115">既定では、 `false`です。</span><span class="sxs-lookup"><span data-stu-id="44b18-115">The default is `false`.</span></span><br /><br /> <span data-ttu-id="44b18-116">バインディングの `clientCredentialType` 属性が `Windows` に設定されている場合、匿名の呼び出し元は許可されません。</span><span class="sxs-lookup"><span data-stu-id="44b18-116">When the `clientCredentialType` attribute of a binding is set to `Windows`, the system does not allow anonymous callers.</span></span> <span data-ttu-id="44b18-117">これは、ドメインまたはワークグループの認証済み呼び出し元だけがシステムへのアクセスを許可されていることを示します。</span><span class="sxs-lookup"><span data-stu-id="44b18-117">This means that only domain or workgroup authenticated callers are allowed to access the system.</span></span> <span data-ttu-id="44b18-118">この動作は、この属性を使用してオーバーライドできます。</span><span class="sxs-lookup"><span data-stu-id="44b18-118">You can override this behavior by using this attribute.</span></span><br /><br /> <span data-ttu-id="44b18-119">この設定を使用するときは十分に注意してください。</span><span class="sxs-lookup"><span data-stu-id="44b18-119">Use this setting with extreme caution.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="44b18-120">子要素</span><span class="sxs-lookup"><span data-stu-id="44b18-120">Child Elements</span></span>  

 <span data-ttu-id="44b18-121">なし。</span><span class="sxs-lookup"><span data-stu-id="44b18-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="44b18-122">親要素</span><span class="sxs-lookup"><span data-stu-id="44b18-122">Parent Elements</span></span>  
  
|<span data-ttu-id="44b18-123">要素</span><span class="sxs-lookup"><span data-stu-id="44b18-123">Element</span></span>|<span data-ttu-id="44b18-124">説明</span><span class="sxs-lookup"><span data-stu-id="44b18-124">Description</span></span>|  
|-------------|-----------------|  
|[\<serviceCredentials>](servicecredentials.md)|<span data-ttu-id="44b18-125">サービスの認証に使用される資格情報と、クライアントの資格情報検証関連の設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="44b18-125">Specifies the credential to be used in authenticating the service, and the client credential validation-related settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="44b18-126">解説</span><span class="sxs-lookup"><span data-stu-id="44b18-126">Remarks</span></span>  

 <span data-ttu-id="44b18-127">匿名の Windows ユーザーのアクセスを許可するかどうかを指定するには、この要素を使用して、`allowAnonymousLogons` 属性を設定します。</span><span class="sxs-lookup"><span data-stu-id="44b18-127">Use this element to specify whether to allow anonymous Windows users access by setting the `allowAnonymousLogons` attribute.</span></span> <span data-ttu-id="44b18-128">また、`includeWindowsGroups` 属性を設定すると、ユーザーが属するグループの情報を AuthorizationContext に含めるかどうかも指定できます。</span><span class="sxs-lookup"><span data-stu-id="44b18-128">You can also specify whether to include group information to which users belong in the AuthorizationContext by setting the `includeWindowsGroups` attribute.</span></span> <span data-ttu-id="44b18-129">この属性が `true` (既定値) に設定されている場合、サービスはクライアントが属している Windows グループを特定できます。</span><span class="sxs-lookup"><span data-stu-id="44b18-129">If it is set to `true` (the default setting), the service can determine the Windows groups to which the client belongs.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44b18-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="44b18-130">See also</span></span>

- <xref:System.ServiceModel.Configuration.WindowsServiceElement>
- <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.WindowsAuthentication%2A>
- <xref:System.ServiceModel.Description.ServiceCredentials.WindowsAuthentication%2A>
- <xref:System.ServiceModel.Security.WindowsServiceCredential>
