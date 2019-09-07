---
title: <userNameAuthentication>
ms.date: 03/30/2017
ms.assetid: 24d8b398-770f-418f-ba23-c4325419cfa6
ms.openlocfilehash: dc5c00a2204646863ae2570bb97b8d70e22a72d4
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399185"
---
# <a name="usernameauthentication"></a><span data-ttu-id="7d919-101">\<userNameAuthentication></span><span class="sxs-lookup"><span data-stu-id="7d919-101">\<userNameAuthentication></span></span>
<span data-ttu-id="7d919-102">ユーザー名とパスワードに基づいてサービスの資格情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="7d919-102">Specifies a service's credentials based on user name and password.</span></span>  
  
<span data-ttu-id="7d919-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="7d919-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="7d919-104">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="7d919-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="7d919-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<動作 >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="7d919-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="7d919-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceBehaviors >** ](servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="7d919-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)</span></span>\
<span data-ttu-id="7d919-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<動作 >** ](behavior-of-servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="7d919-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)</span></span>\
<span data-ttu-id="7d919-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceCredentials >** ](servicecredentials.md)</span><span class="sxs-lookup"><span data-stu-id="7d919-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCredentials>**](servicecredentials.md)</span></span>\
<span data-ttu-id="7d919-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<userNameAuthentication >**</span><span class="sxs-lookup"><span data-stu-id="7d919-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<userNameAuthentication>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7d919-110">構文</span><span class="sxs-lookup"><span data-stu-id="7d919-110">Syntax</span></span>  
  
```xml  
<userNameAuthentication cacheLogonTokenLifetime="TimeSpan"
                        cacheLogonTokens="Boolean"
                        customUserNamePasswordValidatorType="String"
                        includeWindowsGroups="Boolean"
                        maxCacheLogonTokens="Integer"
                        membershipProviderName="String"
                        userNamePasswordValidationMode="Windows/MembershipProvider/Custom" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7d919-111">属性および要素</span><span class="sxs-lookup"><span data-stu-id="7d919-111">Attributes and Elements</span></span>  
 <span data-ttu-id="7d919-112">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="7d919-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7d919-113">属性</span><span class="sxs-lookup"><span data-stu-id="7d919-113">Attributes</span></span>  
  
|<span data-ttu-id="7d919-114">属性</span><span class="sxs-lookup"><span data-stu-id="7d919-114">Attribute</span></span>|<span data-ttu-id="7d919-115">説明</span><span class="sxs-lookup"><span data-stu-id="7d919-115">Description</span></span>|  
|---------------|-----------------|  
|`cacheLogonTokenLifetime`|<span data-ttu-id="7d919-116">トークンがキャッシュ内に保持される最大時間を指定する <xref:System.TimeSpan>。</span><span class="sxs-lookup"><span data-stu-id="7d919-116">A <xref:System.TimeSpan> that specifies the maximum length of time a token is cached.</span></span> <span data-ttu-id="7d919-117">既定値は 00:15:00 です。</span><span class="sxs-lookup"><span data-stu-id="7d919-117">The default is 00:15:00.</span></span>|  
|`cacheLogonTokens`|<span data-ttu-id="7d919-118">ログオン トークンがキャッシュされるかどうかを指定するブール値。</span><span class="sxs-lookup"><span data-stu-id="7d919-118">A Boolean value that specifies whether logon tokens are cached.</span></span> <span data-ttu-id="7d919-119">既定値は `false` です。</span><span class="sxs-lookup"><span data-stu-id="7d919-119">The default is `false`.</span></span>|  
|`customUserNamePasswordValidatorType`|<span data-ttu-id="7d919-120">使用されるカスタム ユーザー名およびパスワード検証の種類を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="7d919-120">A string that specifies the type of custom username password validator to be used.</span></span> <span data-ttu-id="7d919-121">既定値は空の文字列です。</span><span class="sxs-lookup"><span data-stu-id="7d919-121">The default is an empty string.</span></span>|  
|`includeWindowsGroups`|<span data-ttu-id="7d919-122">セキュリティ コンテキストに Windows グループが含まれるかどうかを指定するブール値。</span><span class="sxs-lookup"><span data-stu-id="7d919-122">A Boolean value that specifies whether Windows groups are included in the security context.</span></span> <span data-ttu-id="7d919-123">既定値は `true` です。</span><span class="sxs-lookup"><span data-stu-id="7d919-123">The default is `true`.</span></span><br /><br /> <span data-ttu-id="7d919-124">この属性を `true` に設定すると、グループ全体が拡張されるため、パフォーマンスに影響が及びます。</span><span class="sxs-lookup"><span data-stu-id="7d919-124">Setting this attribute to `true` has a performance impact as it results in a full-group expansion.</span></span> <span data-ttu-id="7d919-125">ユーザーが属するグループの一覧を生成する必要がない場合は、このプロパティを `false` に設定します。</span><span class="sxs-lookup"><span data-stu-id="7d919-125">Set this property to `false` if you do not need to establish the list of groups a user belongs to.</span></span>|  
|`maxCacheLogonTokens`|<span data-ttu-id="7d919-126">キャッシュするログオン トークンの最大数を指定する整数。</span><span class="sxs-lookup"><span data-stu-id="7d919-126">An integer that specifies the maximum number of logon tokens to cache.</span></span> <span data-ttu-id="7d919-127">この値は、ゼロより大きい値である必要があります。</span><span class="sxs-lookup"><span data-stu-id="7d919-127">This value should be larger than zero.</span></span> <span data-ttu-id="7d919-128">既定値は 128 です。</span><span class="sxs-lookup"><span data-stu-id="7d919-128">The default is 128.</span></span>|  
|`membershipProviderName`|<span data-ttu-id="7d919-129">バインディングの `clientCredentialType` 属性が `username` に設定されている場合、ユーザー名は Windows アカウントにマップされます。</span><span class="sxs-lookup"><span data-stu-id="7d919-129">When the `clientCredentialType` attribute of a binding is set to `username`, the username is mapped to Windows accounts.</span></span> <span data-ttu-id="7d919-130">関連するパスワード検証機構を提供する <xref:System.Web.Security.MembershipProvider> 値の名前を含む文字列であるこの属性を使用して動作をオーバーライドできます。</span><span class="sxs-lookup"><span data-stu-id="7d919-130">You can override this behavior using this attribute, which is a string that contains the name of the <xref:System.Web.Security.MembershipProvider> value that provides the relevant password validation mechanism.</span></span>|  
|`userNamePasswordValidationMode`|<span data-ttu-id="7d919-131">ユーザー名とパスワードを検証する方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="7d919-131">Specifies the manner in which username password is validated.</span></span> <span data-ttu-id="7d919-132">有効な値は、</span><span class="sxs-lookup"><span data-stu-id="7d919-132">Valid values are:</span></span><br /><br /> <span data-ttu-id="7d919-133">-Windows</span><span class="sxs-lookup"><span data-stu-id="7d919-133">-   Windows</span></span><br /><span data-ttu-id="7d919-134">-MembershipProvider</span><span class="sxs-lookup"><span data-stu-id="7d919-134">-   MembershipProvider</span></span><br /><span data-ttu-id="7d919-135">-カスタム</span><span class="sxs-lookup"><span data-stu-id="7d919-135">-   Custom</span></span><br /><br /> <span data-ttu-id="7d919-136">既定は Windows です。</span><span class="sxs-lookup"><span data-stu-id="7d919-136">The default is Windows.</span></span> <span data-ttu-id="7d919-137">この属性は <xref:System.ServiceModel.Security.UserNamePasswordValidationMode> 型です。</span><span class="sxs-lookup"><span data-stu-id="7d919-137">This attribute is of type <xref:System.ServiceModel.Security.UserNamePasswordValidationMode>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7d919-138">子要素</span><span class="sxs-lookup"><span data-stu-id="7d919-138">Child Elements</span></span>  
 <span data-ttu-id="7d919-139">なし。</span><span class="sxs-lookup"><span data-stu-id="7d919-139">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7d919-140">親要素</span><span class="sxs-lookup"><span data-stu-id="7d919-140">Parent Elements</span></span>  
  
|<span data-ttu-id="7d919-141">要素</span><span class="sxs-lookup"><span data-stu-id="7d919-141">Element</span></span>|<span data-ttu-id="7d919-142">説明</span><span class="sxs-lookup"><span data-stu-id="7d919-142">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7d919-143">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="7d919-143">\<serviceCredentials></span></span>](servicecredentials.md)|<span data-ttu-id="7d919-144">サービスの認証に使用される資格情報と、クライアントの資格情報検証関連の設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="7d919-144">Specifies the credential to be used in authenticating the service, and the client credential validation related settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7d919-145">Remarks</span><span class="sxs-lookup"><span data-stu-id="7d919-145">Remarks</span></span>  
 <span data-ttu-id="7d919-146">サービスで使用されるバインディングがユーザー名とパスワード ベースの認証を使用するように構成されていない場合、この要素の属性は無視されます。</span><span class="sxs-lookup"><span data-stu-id="7d919-146">If none of the bindings used by a service is configured for user name/password-based authentication, the attributes for this element are ignored.</span></span> <span data-ttu-id="7d919-147">これには、`customUserNamePasswordValidatorType`、`includeWindowsGroups`、`membershipProviderName`、および `userNamePasswordValidationMode` が含まれます。</span><span class="sxs-lookup"><span data-stu-id="7d919-147">These include `customUserNamePasswordValidatorType`, `includeWindowsGroups`, `membershipProviderName`, and `userNamePasswordValidationMode`.</span></span>  
  
 <span data-ttu-id="7d919-148">サービスで使用されるバインディングが Windows 認証のユーザー名とパスワードを使用するように構成されていない場合、ログオン トークンのキャッシュに関連する設定は無視されます。</span><span class="sxs-lookup"><span data-stu-id="7d919-148">If none of the bindings used by a service is configured to use Windows authentication for user name/password, the settings related to caching of logon tokens are ignored.</span></span> <span data-ttu-id="7d919-149">これには、`cacheLogonTokenLifetime`、`cacheLogonTokens`、および `maxCacheLogonTokens`、が含まれます。</span><span class="sxs-lookup"><span data-stu-id="7d919-149">These include the `cacheLogonTokenLifetime`, `cacheLogonTokens`, and `maxCacheLogonTokens`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d919-150">関連項目</span><span class="sxs-lookup"><span data-stu-id="7d919-150">See also</span></span>

- <xref:System.ServiceModel.Configuration.UserNameServiceElement>
- <xref:System.ServiceModel.Description.ServiceCredentials.UserNameAuthentication%2A>
- <xref:System.ServiceModel.Security.UserNamePasswordServiceCredential>
- <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.UserNameAuthentication%2A>
