---
title: <userNameAuthentication>
ms.date: 03/30/2017
ms.assetid: 24d8b398-770f-418f-ba23-c4325419cfa6
ms.openlocfilehash: 30fd78d6c56e8b22e0e744a38f18ac076dc70162
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91178035"
---
# \<userNameAuthentication>

<span data-ttu-id="c919a-101">ユーザー名とパスワードに基づいてサービスの資格情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="c919a-101">Specifies a service's credentials based on user name and password.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCredentials>**](servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<userNameAuthentication>**  
  
## <a name="syntax"></a><span data-ttu-id="c919a-102">構文</span><span class="sxs-lookup"><span data-stu-id="c919a-102">Syntax</span></span>  
  
```xml  
<userNameAuthentication cacheLogonTokenLifetime="TimeSpan"
                        cacheLogonTokens="Boolean"
                        customUserNamePasswordValidatorType="String"
                        includeWindowsGroups="Boolean"
                        maxCacheLogonTokens="Integer"
                        membershipProviderName="String"
                        userNamePasswordValidationMode="Windows/MembershipProvider/Custom" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c919a-103">属性および要素</span><span class="sxs-lookup"><span data-stu-id="c919a-103">Attributes and Elements</span></span>  

 <span data-ttu-id="c919a-104">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="c919a-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c919a-105">属性</span><span class="sxs-lookup"><span data-stu-id="c919a-105">Attributes</span></span>  
  
|<span data-ttu-id="c919a-106">属性</span><span class="sxs-lookup"><span data-stu-id="c919a-106">Attribute</span></span>|<span data-ttu-id="c919a-107">[説明]</span><span class="sxs-lookup"><span data-stu-id="c919a-107">Description</span></span>|  
|---------------|-----------------|  
|`cacheLogonTokenLifetime`|<span data-ttu-id="c919a-108">トークンがキャッシュ内に保持される最大時間を指定する <xref:System.TimeSpan>。</span><span class="sxs-lookup"><span data-stu-id="c919a-108">A <xref:System.TimeSpan> that specifies the maximum length of time a token is cached.</span></span> <span data-ttu-id="c919a-109">既定値は 00:15:00 です。</span><span class="sxs-lookup"><span data-stu-id="c919a-109">The default is 00:15:00.</span></span>|  
|`cacheLogonTokens`|<span data-ttu-id="c919a-110">ログオン トークンがキャッシュされるかどうかを指定するブール値。</span><span class="sxs-lookup"><span data-stu-id="c919a-110">A Boolean value that specifies whether logon tokens are cached.</span></span> <span data-ttu-id="c919a-111">既定では、 `false`です。</span><span class="sxs-lookup"><span data-stu-id="c919a-111">The default is `false`.</span></span>|  
|`customUserNamePasswordValidatorType`|<span data-ttu-id="c919a-112">使用されるカスタム ユーザー名およびパスワード検証の種類を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="c919a-112">A string that specifies the type of custom username password validator to be used.</span></span> <span data-ttu-id="c919a-113">既定値は空の文字列です。</span><span class="sxs-lookup"><span data-stu-id="c919a-113">The default is an empty string.</span></span>|  
|`includeWindowsGroups`|<span data-ttu-id="c919a-114">セキュリティ コンテキストに Windows グループが含まれるかどうかを指定するブール値。</span><span class="sxs-lookup"><span data-stu-id="c919a-114">A Boolean value that specifies whether Windows groups are included in the security context.</span></span> <span data-ttu-id="c919a-115">既定では、 `true`です。</span><span class="sxs-lookup"><span data-stu-id="c919a-115">The default is `true`.</span></span><br /><br /> <span data-ttu-id="c919a-116">この属性を `true` に設定すると、グループ全体が拡張されるため、パフォーマンスに影響が及びます。</span><span class="sxs-lookup"><span data-stu-id="c919a-116">Setting this attribute to `true` has a performance impact as it results in a full-group expansion.</span></span> <span data-ttu-id="c919a-117">ユーザーが属するグループの一覧を生成する必要がない場合は、このプロパティを `false` に設定します。</span><span class="sxs-lookup"><span data-stu-id="c919a-117">Set this property to `false` if you do not need to establish the list of groups a user belongs to.</span></span>|  
|`maxCacheLogonTokens`|<span data-ttu-id="c919a-118">キャッシュするログオン トークンの最大数を指定する整数。</span><span class="sxs-lookup"><span data-stu-id="c919a-118">An integer that specifies the maximum number of logon tokens to cache.</span></span> <span data-ttu-id="c919a-119">この値は、ゼロより大きい値である必要があります。</span><span class="sxs-lookup"><span data-stu-id="c919a-119">This value should be larger than zero.</span></span> <span data-ttu-id="c919a-120">既定値は 128 です。</span><span class="sxs-lookup"><span data-stu-id="c919a-120">The default is 128.</span></span>|  
|`membershipProviderName`|<span data-ttu-id="c919a-121">バインディングの `clientCredentialType` 属性が `username` に設定されている場合、ユーザー名は Windows アカウントにマップされます。</span><span class="sxs-lookup"><span data-stu-id="c919a-121">When the `clientCredentialType` attribute of a binding is set to `username`, the username is mapped to Windows accounts.</span></span> <span data-ttu-id="c919a-122">関連するパスワード検証機構を提供する <xref:System.Web.Security.MembershipProvider> 値の名前を含む文字列であるこの属性を使用して動作をオーバーライドできます。</span><span class="sxs-lookup"><span data-stu-id="c919a-122">You can override this behavior using this attribute, which is a string that contains the name of the <xref:System.Web.Security.MembershipProvider> value that provides the relevant password validation mechanism.</span></span>|  
|`userNamePasswordValidationMode`|<span data-ttu-id="c919a-123">ユーザー名とパスワードを検証する方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="c919a-123">Specifies the manner in which username password is validated.</span></span> <span data-ttu-id="c919a-124">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="c919a-124">Valid values are:</span></span><br /><br /> <span data-ttu-id="c919a-125">-Windows</span><span class="sxs-lookup"><span data-stu-id="c919a-125">-   Windows</span></span><br /><span data-ttu-id="c919a-126">-MembershipProvider</span><span class="sxs-lookup"><span data-stu-id="c919a-126">-   MembershipProvider</span></span><br /><span data-ttu-id="c919a-127">-カスタム</span><span class="sxs-lookup"><span data-stu-id="c919a-127">-   Custom</span></span><br /><br /> <span data-ttu-id="c919a-128">既定は Windows です。</span><span class="sxs-lookup"><span data-stu-id="c919a-128">The default is Windows.</span></span> <span data-ttu-id="c919a-129">この属性は <xref:System.ServiceModel.Security.UserNamePasswordValidationMode> 型です。</span><span class="sxs-lookup"><span data-stu-id="c919a-129">This attribute is of type <xref:System.ServiceModel.Security.UserNamePasswordValidationMode>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c919a-130">子要素</span><span class="sxs-lookup"><span data-stu-id="c919a-130">Child Elements</span></span>  

 <span data-ttu-id="c919a-131">なし。</span><span class="sxs-lookup"><span data-stu-id="c919a-131">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c919a-132">親要素</span><span class="sxs-lookup"><span data-stu-id="c919a-132">Parent Elements</span></span>  
  
|<span data-ttu-id="c919a-133">要素</span><span class="sxs-lookup"><span data-stu-id="c919a-133">Element</span></span>|<span data-ttu-id="c919a-134">説明</span><span class="sxs-lookup"><span data-stu-id="c919a-134">Description</span></span>|  
|-------------|-----------------|  
|[\<serviceCredentials>](servicecredentials.md)|<span data-ttu-id="c919a-135">サービスの認証に使用される資格情報と、クライアントの資格情報検証関連の設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="c919a-135">Specifies the credential to be used in authenticating the service, and the client credential validation related settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c919a-136">解説</span><span class="sxs-lookup"><span data-stu-id="c919a-136">Remarks</span></span>  

 <span data-ttu-id="c919a-137">サービスで使用されるバインディングがユーザー名とパスワード ベースの認証を使用するように構成されていない場合、この要素の属性は無視されます。</span><span class="sxs-lookup"><span data-stu-id="c919a-137">If none of the bindings used by a service is configured for user name/password-based authentication, the attributes for this element are ignored.</span></span> <span data-ttu-id="c919a-138">これには、`customUserNamePasswordValidatorType`、`includeWindowsGroups`、`membershipProviderName`、および `userNamePasswordValidationMode` が含まれます。</span><span class="sxs-lookup"><span data-stu-id="c919a-138">These include `customUserNamePasswordValidatorType`, `includeWindowsGroups`, `membershipProviderName`, and `userNamePasswordValidationMode`.</span></span>  
  
 <span data-ttu-id="c919a-139">サービスで使用されるバインディングが Windows 認証のユーザー名とパスワードを使用するように構成されていない場合、ログオン トークンのキャッシュに関連する設定は無視されます。</span><span class="sxs-lookup"><span data-stu-id="c919a-139">If none of the bindings used by a service is configured to use Windows authentication for user name/password, the settings related to caching of logon tokens are ignored.</span></span> <span data-ttu-id="c919a-140">これには、`cacheLogonTokenLifetime`、`cacheLogonTokens`、および `maxCacheLogonTokens`、が含まれます。</span><span class="sxs-lookup"><span data-stu-id="c919a-140">These include the `cacheLogonTokenLifetime`, `cacheLogonTokens`, and `maxCacheLogonTokens`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c919a-141">関連項目</span><span class="sxs-lookup"><span data-stu-id="c919a-141">See also</span></span>

- <xref:System.ServiceModel.Configuration.UserNameServiceElement>
- <xref:System.ServiceModel.Description.ServiceCredentials.UserNameAuthentication%2A>
- <xref:System.ServiceModel.Security.UserNamePasswordServiceCredential>
- <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.UserNameAuthentication%2A>
