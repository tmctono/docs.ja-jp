---
title: <userNameAuthentication>
ms.date: 03/30/2017
ms.assetid: 24d8b398-770f-418f-ba23-c4325419cfa6
ms.openlocfilehash: 5a4cf8d429198b889f2bb362294ba3841c814b26
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59083145"
---
# <a name="usernameauthentication"></a><span data-ttu-id="7b378-101">\<userNameAuthentication></span><span class="sxs-lookup"><span data-stu-id="7b378-101">\<userNameAuthentication></span></span>
<span data-ttu-id="7b378-102">ユーザー名とパスワードに基づいてサービスの資格情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="7b378-102">Specifies a service's credentials based on user name and password.</span></span>  
  
 <span data-ttu-id="7b378-103">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="7b378-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="7b378-104">\<<behaviors></span><span class="sxs-lookup"><span data-stu-id="7b378-104">\<behaviors></span></span>  
<span data-ttu-id="7b378-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="7b378-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="7b378-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="7b378-106">\<behavior></span></span>  
<span data-ttu-id="7b378-107">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="7b378-107">\<serviceCredentials></span></span>  
<span data-ttu-id="7b378-108">\<userNameAuthentication></span><span class="sxs-lookup"><span data-stu-id="7b378-108">\<userNameAuthentication></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7b378-109">構文</span><span class="sxs-lookup"><span data-stu-id="7b378-109">Syntax</span></span>  
  
```xml  
<userNameAuthentication cacheLogonTokenLifetime="TimeSpan"
                        cacheLogonTokens="Boolean"
                        customUserNamePasswordValidatorType="String"
                        includeWindowsGroups="Boolean"
                        maxCacheLogonTokens="Integer"
                        membershipProviderName="String"
                        userNamePasswordValidationMode="Windows/MembershipProvider/Custom" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7b378-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="7b378-110">Attributes and Elements</span></span>  
 <span data-ttu-id="7b378-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="7b378-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7b378-112">属性</span><span class="sxs-lookup"><span data-stu-id="7b378-112">Attributes</span></span>  
  
|<span data-ttu-id="7b378-113">属性</span><span class="sxs-lookup"><span data-stu-id="7b378-113">Attribute</span></span>|<span data-ttu-id="7b378-114">説明</span><span class="sxs-lookup"><span data-stu-id="7b378-114">Description</span></span>|  
|---------------|-----------------|  
|`cacheLogonTokenLifetime`|<span data-ttu-id="7b378-115">トークンがキャッシュ内に保持される最大時間を指定する <xref:System.TimeSpan>。</span><span class="sxs-lookup"><span data-stu-id="7b378-115">A <xref:System.TimeSpan> that specifies the maximum length of time a token is cached.</span></span> <span data-ttu-id="7b378-116">既定値は 00:15:00 です。</span><span class="sxs-lookup"><span data-stu-id="7b378-116">The default is 00:15:00.</span></span>|  
|`cacheLogonTokens`|<span data-ttu-id="7b378-117">ログオン トークンがキャッシュされるかどうかを指定するブール値。</span><span class="sxs-lookup"><span data-stu-id="7b378-117">A Boolean value that specifies whether logon tokens are cached.</span></span> <span data-ttu-id="7b378-118">既定値は `false` です。</span><span class="sxs-lookup"><span data-stu-id="7b378-118">The default is `false`.</span></span>|  
|`customUserNamePasswordValidatorType`|<span data-ttu-id="7b378-119">使用されるカスタム ユーザー名およびパスワード検証の種類を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="7b378-119">A string that specifies the type of custom username password validator to be used.</span></span> <span data-ttu-id="7b378-120">既定値は空の文字列です。</span><span class="sxs-lookup"><span data-stu-id="7b378-120">The default is an empty string.</span></span>|  
|`includeWindowsGroups`|<span data-ttu-id="7b378-121">セキュリティ コンテキストに Windows グループが含まれるかどうかを指定するブール値。</span><span class="sxs-lookup"><span data-stu-id="7b378-121">A Boolean value that specifies whether Windows groups are included in the security context.</span></span> <span data-ttu-id="7b378-122">既定値は `true` です。</span><span class="sxs-lookup"><span data-stu-id="7b378-122">The default is `true`.</span></span><br /><br /> <span data-ttu-id="7b378-123">この属性を `true` に設定すると、グループ全体が拡張されるため、パフォーマンスに影響が及びます。</span><span class="sxs-lookup"><span data-stu-id="7b378-123">Setting this attribute to `true` has a performance impact as it results in a full-group expansion.</span></span> <span data-ttu-id="7b378-124">ユーザーが属するグループの一覧を生成する必要がない場合は、このプロパティを `false` に設定します。</span><span class="sxs-lookup"><span data-stu-id="7b378-124">Set this property to `false` if you do not need to establish the list of groups a user belongs to.</span></span>|  
|`maxCacheLogonTokens`|<span data-ttu-id="7b378-125">キャッシュするログオン トークンの最大数を指定する整数。</span><span class="sxs-lookup"><span data-stu-id="7b378-125">An integer that specifies the maximum number of logon tokens to cache.</span></span> <span data-ttu-id="7b378-126">この値は、ゼロより大きい値である必要があります。</span><span class="sxs-lookup"><span data-stu-id="7b378-126">This value should be larger than zero.</span></span> <span data-ttu-id="7b378-127">既定値は 128 です。</span><span class="sxs-lookup"><span data-stu-id="7b378-127">The default is 128.</span></span>|  
|`membershipProviderName`|<span data-ttu-id="7b378-128">バインディングの `clientCredentialType` 属性が `username` に設定されている場合、ユーザー名は Windows アカウントにマップされます。</span><span class="sxs-lookup"><span data-stu-id="7b378-128">When the `clientCredentialType` attribute of a binding is set to `username`, the username is mapped to Windows accounts.</span></span> <span data-ttu-id="7b378-129">関連するパスワード検証機構を提供する <xref:System.Web.Security.MembershipProvider> 値の名前を含む文字列であるこの属性を使用して動作をオーバーライドできます。</span><span class="sxs-lookup"><span data-stu-id="7b378-129">You can override this behavior using this attribute, which is a string that contains the name of the <xref:System.Web.Security.MembershipProvider> value that provides the relevant password validation mechanism.</span></span>|  
|`userNamePasswordValidationMode`|<span data-ttu-id="7b378-130">ユーザー名とパスワードを検証する方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="7b378-130">Specifies the manner in which username password is validated.</span></span> <span data-ttu-id="7b378-131">次の値を指定できます。</span><span class="sxs-lookup"><span data-stu-id="7b378-131">Valid values are:</span></span><br /><br /> <span data-ttu-id="7b378-132">-Windows</span><span class="sxs-lookup"><span data-stu-id="7b378-132">-   Windows</span></span><br /><span data-ttu-id="7b378-133">-MembershipProvider</span><span class="sxs-lookup"><span data-stu-id="7b378-133">-   MembershipProvider</span></span><br /><span data-ttu-id="7b378-134">-カスタム</span><span class="sxs-lookup"><span data-stu-id="7b378-134">-   Custom</span></span><br /><br /> <span data-ttu-id="7b378-135">既定は Windows です。</span><span class="sxs-lookup"><span data-stu-id="7b378-135">The default is Windows.</span></span> <span data-ttu-id="7b378-136">この属性は <xref:System.ServiceModel.Security.UserNamePasswordValidationMode> 型です。</span><span class="sxs-lookup"><span data-stu-id="7b378-136">This attribute is of type <xref:System.ServiceModel.Security.UserNamePasswordValidationMode>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7b378-137">子要素</span><span class="sxs-lookup"><span data-stu-id="7b378-137">Child Elements</span></span>  
 <span data-ttu-id="7b378-138">なし。</span><span class="sxs-lookup"><span data-stu-id="7b378-138">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7b378-139">親要素</span><span class="sxs-lookup"><span data-stu-id="7b378-139">Parent Elements</span></span>  
  
|<span data-ttu-id="7b378-140">要素</span><span class="sxs-lookup"><span data-stu-id="7b378-140">Element</span></span>|<span data-ttu-id="7b378-141">説明</span><span class="sxs-lookup"><span data-stu-id="7b378-141">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7b378-142">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="7b378-142">\<serviceCredentials></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md)|<span data-ttu-id="7b378-143">サービスの認証に使用される資格情報と、クライアントの資格情報検証関連の設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="7b378-143">Specifies the credential to be used in authenticating the service, and the client credential validation related settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7b378-144">Remarks</span><span class="sxs-lookup"><span data-stu-id="7b378-144">Remarks</span></span>  
 <span data-ttu-id="7b378-145">サービスで使用されるバインディングがユーザー名とパスワード ベースの認証を使用するように構成されていない場合、この要素の属性は無視されます。</span><span class="sxs-lookup"><span data-stu-id="7b378-145">If none of the bindings used by a service is configured for user name/password-based authentication, the attributes for this element are ignored.</span></span> <span data-ttu-id="7b378-146">これには、`customUserNamePasswordValidatorType`、`includeWindowsGroups`、`membershipProviderName`、および `userNamePasswordValidationMode` が含まれます。</span><span class="sxs-lookup"><span data-stu-id="7b378-146">These include `customUserNamePasswordValidatorType`, `includeWindowsGroups`, `membershipProviderName`, and `userNamePasswordValidationMode`.</span></span>  
  
 <span data-ttu-id="7b378-147">サービスで使用されるバインディングが Windows 認証のユーザー名とパスワードを使用するように構成されていない場合、ログオン トークンのキャッシュに関連する設定は無視されます。</span><span class="sxs-lookup"><span data-stu-id="7b378-147">If none of the bindings used by a service is configured to use Windows authentication for user name/password, the settings related to caching of logon tokens are ignored.</span></span> <span data-ttu-id="7b378-148">これには、`cacheLogonTokenLifetime`、`cacheLogonTokens`、および `maxCacheLogonTokens`、が含まれます。</span><span class="sxs-lookup"><span data-stu-id="7b378-148">These include the `cacheLogonTokenLifetime`, `cacheLogonTokens`, and `maxCacheLogonTokens`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b378-149">関連項目</span><span class="sxs-lookup"><span data-stu-id="7b378-149">See also</span></span>

- <xref:System.ServiceModel.Configuration.UserNameServiceElement>
- <xref:System.ServiceModel.Description.ServiceCredentials.UserNameAuthentication%2A>
- <xref:System.ServiceModel.Security.UserNamePasswordServiceCredential>
- <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.UserNameAuthentication%2A>
