---
title: <windowsAuthentication> の <serviceCredentials>
ms.date: 03/30/2017
ms.assetid: e0709473-0997-4de3-8f49-783527309a48
ms.openlocfilehash: ded04f6e87fce2e12dac8f681ba2d4178f8fd204
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399110"
---
# <a name="windowsauthentication-of-servicecredentials"></a><span data-ttu-id="47b15-102">\<serviceCredentials > の\<windowsauthentication ></span><span class="sxs-lookup"><span data-stu-id="47b15-102">\<windowsAuthentication> of \<serviceCredentials></span></span>
<span data-ttu-id="47b15-103">Windows サービス資格情報の設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="47b15-103">Specifies the settings of a Windows service credential.</span></span>  
  
<span data-ttu-id="47b15-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="47b15-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="47b15-105">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="47b15-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="47b15-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<動作 >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="47b15-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="47b15-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceBehaviors >** ](servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="47b15-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)</span></span>\
<span data-ttu-id="47b15-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<動作 >** ](behavior-of-servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="47b15-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)</span></span>\
<span data-ttu-id="47b15-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceCredentials >** ](servicecredentials.md)</span><span class="sxs-lookup"><span data-stu-id="47b15-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCredentials>**](servicecredentials.md)</span></span>\
<span data-ttu-id="47b15-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<windowsAuthentication >**</span><span class="sxs-lookup"><span data-stu-id="47b15-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<windowsAuthentication>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="47b15-111">構文</span><span class="sxs-lookup"><span data-stu-id="47b15-111">Syntax</span></span>  
  
```xml  
<windowsAuthentication allowAnonymousLogons="Boolean"
                       includeWindowsGroups="Boolean" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="47b15-112">属性および要素</span><span class="sxs-lookup"><span data-stu-id="47b15-112">Attributes and Elements</span></span>  
 <span data-ttu-id="47b15-113">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="47b15-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="47b15-114">属性</span><span class="sxs-lookup"><span data-stu-id="47b15-114">Attributes</span></span>  
  
|<span data-ttu-id="47b15-115">属性</span><span class="sxs-lookup"><span data-stu-id="47b15-115">Attribute</span></span>|<span data-ttu-id="47b15-116">説明</span><span class="sxs-lookup"><span data-stu-id="47b15-116">Description</span></span>|  
|---------------|-----------------|  
|`includeWindowsGroups`|<span data-ttu-id="47b15-117">セキュリティ コンテキストに Windows グループが含まれるかどうかを指定する省略可能なブール属性。</span><span class="sxs-lookup"><span data-stu-id="47b15-117">An optional Boolean attribute that specifies whether the system includes Windows groups in the security context.</span></span> <span data-ttu-id="47b15-118">既定値は `true` です。</span><span class="sxs-lookup"><span data-stu-id="47b15-118">The default is `true`.</span></span><br /><br /> <span data-ttu-id="47b15-119">この属性を `true` に設定すると、グループ全体が拡張されるため、パフォーマンスに影響が及びます。</span><span class="sxs-lookup"><span data-stu-id="47b15-119">Setting this attribute to `true` has a performance impact as it results in a full-group expansion.</span></span> <span data-ttu-id="47b15-120">ユーザーが属するグループの一覧を生成する必要がない場合は、この属性を `false` に設定します。</span><span class="sxs-lookup"><span data-stu-id="47b15-120">Set this attribute to `false` if you do not need to establish the list of groups a user belongs to.</span></span>|  
|`allowAnonymousLogons`|<span data-ttu-id="47b15-121">認証されていない匿名の呼び出し元を許可するかどうかを指定する省略可能なブール属性。</span><span class="sxs-lookup"><span data-stu-id="47b15-121">An optional Boolean attribute that specifies whether anonymous, unauthenticated callers are allowed.</span></span> <span data-ttu-id="47b15-122">既定値は `false` です。</span><span class="sxs-lookup"><span data-stu-id="47b15-122">The default is `false`.</span></span><br /><br /> <span data-ttu-id="47b15-123">バインディングの `clientCredentialType` 属性が `Windows` に設定されている場合、匿名の呼び出し元は許可されません。</span><span class="sxs-lookup"><span data-stu-id="47b15-123">When the `clientCredentialType` attribute of a binding is set to `Windows`, the system does not allow anonymous callers.</span></span> <span data-ttu-id="47b15-124">これは、ドメインまたはワークグループの認証済み呼び出し元だけがシステムへのアクセスを許可されていることを示します。</span><span class="sxs-lookup"><span data-stu-id="47b15-124">This means that only domain or workgroup authenticated callers are allowed to access the system.</span></span> <span data-ttu-id="47b15-125">この動作は、この属性を使用してオーバーライドできます。</span><span class="sxs-lookup"><span data-stu-id="47b15-125">You can override this behavior by using this attribute.</span></span><br /><br /> <span data-ttu-id="47b15-126">この設定を使用するときは十分に注意してください。</span><span class="sxs-lookup"><span data-stu-id="47b15-126">Use this setting with extreme caution.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="47b15-127">子要素</span><span class="sxs-lookup"><span data-stu-id="47b15-127">Child Elements</span></span>  
 <span data-ttu-id="47b15-128">なし。</span><span class="sxs-lookup"><span data-stu-id="47b15-128">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="47b15-129">親要素</span><span class="sxs-lookup"><span data-stu-id="47b15-129">Parent Elements</span></span>  
  
|<span data-ttu-id="47b15-130">要素</span><span class="sxs-lookup"><span data-stu-id="47b15-130">Element</span></span>|<span data-ttu-id="47b15-131">説明</span><span class="sxs-lookup"><span data-stu-id="47b15-131">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="47b15-132">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="47b15-132">\<serviceCredentials></span></span>](servicecredentials.md)|<span data-ttu-id="47b15-133">サービスの認証に使用される資格情報と、クライアントの資格情報検証関連の設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="47b15-133">Specifies the credential to be used in authenticating the service, and the client credential validation-related settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="47b15-134">Remarks</span><span class="sxs-lookup"><span data-stu-id="47b15-134">Remarks</span></span>  
 <span data-ttu-id="47b15-135">匿名の Windows ユーザーのアクセスを許可するかどうかを指定するには、この要素を使用して、`allowAnonymousLogons` 属性を設定します。</span><span class="sxs-lookup"><span data-stu-id="47b15-135">Use this element to specify whether to allow anonymous Windows users access by setting the `allowAnonymousLogons` attribute.</span></span> <span data-ttu-id="47b15-136">また、`includeWindowsGroups` 属性を設定すると、ユーザーが属するグループの情報を AuthorizationContext に含めるかどうかも指定できます。</span><span class="sxs-lookup"><span data-stu-id="47b15-136">You can also specify whether to include group information to which users belong in the AuthorizationContext by setting the `includeWindowsGroups` attribute.</span></span> <span data-ttu-id="47b15-137">この属性が `true` (既定値) に設定されている場合、サービスはクライアントが属している Windows グループを特定できます。</span><span class="sxs-lookup"><span data-stu-id="47b15-137">If it is set to `true` (the default setting), the service can determine the Windows groups to which the client belongs.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47b15-138">関連項目</span><span class="sxs-lookup"><span data-stu-id="47b15-138">See also</span></span>

- <xref:System.ServiceModel.Configuration.WindowsServiceElement>
- <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.WindowsAuthentication%2A>
- <xref:System.ServiceModel.Description.ServiceCredentials.WindowsAuthentication%2A>
- <xref:System.ServiceModel.Security.WindowsServiceCredential>
