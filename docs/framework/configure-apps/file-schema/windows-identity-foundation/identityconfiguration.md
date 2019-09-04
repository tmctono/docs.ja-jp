---
title: <identityConfiguration>
ms.date: 03/30/2017
ms.assetid: 1db76253-07da-447b-9e7a-3705c7228cf4
author: BrucePerlerMS
ms.openlocfilehash: 0fa8c574fd5663606cf081f1000a24884306edfe
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251996"
---
# <a name="identityconfiguration"></a><span data-ttu-id="807b1-101">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="807b1-101">\<identityConfiguration></span></span>

<span data-ttu-id="807b1-102">サービスレベルの id 設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="807b1-102">Specifies service-level identity settings.</span></span>

<span data-ttu-id="807b1-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="807b1-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="807b1-104">&nbsp;&nbsp;[ **\<システムの >** ](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="807b1-104">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="807b1-105">&nbsp;&nbsp;&nbsp;&nbsp; **\<構成 >**</span><span class="sxs-lookup"><span data-stu-id="807b1-105">&nbsp;&nbsp;&nbsp;&nbsp;**\<identityConfiguration>**</span></span>  

## <a name="syntax"></a><span data-ttu-id="807b1-106">構文</span><span class="sxs-lookup"><span data-stu-id="807b1-106">Syntax</span></span>

```xml
<system.identityModel>
  <identityConfiguration
      name=xs:string
      saveBootstrapContext=xs:boolean>
      maximumClockSkew=TimeSpan >
  </identityConfiguration>
</system.identityModel>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="807b1-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="807b1-107">Attributes and Elements</span></span>

<span data-ttu-id="807b1-108">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="807b1-108">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="807b1-109">属性</span><span class="sxs-lookup"><span data-stu-id="807b1-109">Attributes</span></span>

|<span data-ttu-id="807b1-110">属性</span><span class="sxs-lookup"><span data-stu-id="807b1-110">Attribute</span></span>|<span data-ttu-id="807b1-111">説明</span><span class="sxs-lookup"><span data-stu-id="807b1-111">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="807b1-112">name</span><span class="sxs-lookup"><span data-stu-id="807b1-112">name</span></span>|<span data-ttu-id="807b1-113">Id 構成セクションの名前。</span><span class="sxs-lookup"><span data-stu-id="807b1-113">The name of the identity configuration section.</span></span> <span data-ttu-id="807b1-114">この名前を使用して、特定の構成セクションを参照することができます。</span><span class="sxs-lookup"><span data-stu-id="807b1-114">You can use this name to reference a specific configuration section.</span></span> <span data-ttu-id="807b1-115">`name`属性が指定されていない場合、セクションでは既定の構成を定義します。</span><span class="sxs-lookup"><span data-stu-id="807b1-115">If no `name` attribute is specified, the section defines the default configuration.</span></span> <span data-ttu-id="807b1-116">既定の構成は、パッシブフェデレーションシナリオでは常に使用されます。</span><span class="sxs-lookup"><span data-stu-id="807b1-116">The default configuration is always used for passive federation scenarios.</span></span> <span data-ttu-id="807b1-117">詳細については、「 [ \<federationConfiguration >](federationconfiguration.md)要素」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="807b1-117">For more information, see the [\<federationConfiguration>](federationconfiguration.md) element.</span></span>|
|<span data-ttu-id="807b1-118">saveBootstrapContext</span><span class="sxs-lookup"><span data-stu-id="807b1-118">saveBootstrapContext</span></span>|<span data-ttu-id="807b1-119">ブートストラップトークンをセッショントークンに含める必要があるかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="807b1-119">Specifies whether bootstrap tokens should be included in the session token.</span></span> <span data-ttu-id="807b1-120">また、 `saveBootstrapContext` [ \<securityTokenHandlerConfiguration >](securitytokenhandlerconfiguration.md)要素の属性を設定することによって、トークンハンドラーコレクションに値を設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="807b1-120">The value may also be set on a token handler collection by setting the `saveBootstrapContext` attribute on the [\<securityTokenHandlerConfiguration>](securitytokenhandlerconfiguration.md) element.</span></span> <span data-ttu-id="807b1-121">トークンハンドラーコレクションに設定された値は、サービスで設定された値よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="807b1-121">A value set on the token handler collection overrides the value set on the service.</span></span>|
|<span data-ttu-id="807b1-122">maximumClockSkew</span><span class="sxs-lookup"><span data-stu-id="807b1-122">maximumClockSkew</span></span>|<span data-ttu-id="807b1-123">許容される最大のクロックスキューを指定する。<xref:System.TimeSpan></span><span class="sxs-lookup"><span data-stu-id="807b1-123">A <xref:System.TimeSpan> that specifies the maximum allowed clock skew.</span></span> <span data-ttu-id="807b1-124">サインインセッションの有効期限の検証など、時間を区別する操作を実行するときに許容される最大のクロックスキューを制御します。</span><span class="sxs-lookup"><span data-stu-id="807b1-124">Controls the maximum allowed clock skew when performing time-sensitive operations, such as validating the expiration time of a sign-in session.</span></span> <span data-ttu-id="807b1-125">既定値は5分 "00:05:00" です。</span><span class="sxs-lookup"><span data-stu-id="807b1-125">The default is 5 minutes, "00:05:00".</span></span> <span data-ttu-id="807b1-126">値を指定<xref:System.TimeSpan>する方法の詳細については、「 [Timespan values](../windows-workflow-foundation/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="807b1-126">For more information about how to specify <xref:System.TimeSpan> values, see [Timespan Values](../windows-workflow-foundation/index.md).</span></span> <span data-ttu-id="807b1-127">SecurityTokenHandlerConfiguration > 要素の`maximumClockSkew`属性[を設定することによって、トークンハンドラーコレクションに最大クロックスキューを設定することもできます。 \<](securitytokenhandlerconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="807b1-127">The maximum clock skew may also be set on a token handler collection by setting the `maximumClockSkew` attribute on the [\<securityTokenHandlerConfiguration>](securitytokenhandlerconfiguration.md) element.</span></span> <span data-ttu-id="807b1-128">トークンハンドラーコレクションに設定された値は、サービスで設定された値よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="807b1-128">A value set on the token handler collection overrides the value set on the service.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="807b1-129">子要素</span><span class="sxs-lookup"><span data-stu-id="807b1-129">Child Elements</span></span>

|<span data-ttu-id="807b1-130">要素</span><span class="sxs-lookup"><span data-stu-id="807b1-130">Element</span></span>|<span data-ttu-id="807b1-131">説明</span><span class="sxs-lookup"><span data-stu-id="807b1-131">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="807b1-132">\<キャッシュ ></span><span class="sxs-lookup"><span data-stu-id="807b1-132">\<caches></span></span>](caches.md)|<span data-ttu-id="807b1-133">セッショントークンとトークンリプレイ検出に使用されるキャッシュを登録します。</span><span class="sxs-lookup"><span data-stu-id="807b1-133">Registers the caches used for session tokens and token replay detection.</span></span> <span data-ttu-id="807b1-134">は、サービスレベルまたはセキュリティトークンハンドラーコレクションで指定できます。</span><span class="sxs-lookup"><span data-stu-id="807b1-134">Can be specified at the service-level or on a security token handler collection.</span></span> <span data-ttu-id="807b1-135">任意。</span><span class="sxs-lookup"><span data-stu-id="807b1-135">Optional.</span></span>|
|[<span data-ttu-id="807b1-136">\<certificateValidation ></span><span class="sxs-lookup"><span data-stu-id="807b1-136">\<certificateValidation></span></span>](certificatevalidation.md)|<span data-ttu-id="807b1-137">トークンハンドラーが証明書を検証するために使用する設定を制御します。</span><span class="sxs-lookup"><span data-stu-id="807b1-137">Controls the settings that token handlers use to validate certificates.</span></span> <span data-ttu-id="807b1-138">は、サービスレベルまたはセキュリティトークンハンドラーコレクションで指定できます。</span><span class="sxs-lookup"><span data-stu-id="807b1-138">Can be specified at the service-level or on a security token handler collection.</span></span> <span data-ttu-id="807b1-139">任意。</span><span class="sxs-lookup"><span data-stu-id="807b1-139">Optional.</span></span>|
|[<span data-ttu-id="807b1-140">\<claimsAuthenticationManager></span><span class="sxs-lookup"><span data-stu-id="807b1-140">\<claimsAuthenticationManager></span></span>](claimsauthenticationmanager.md)|<span data-ttu-id="807b1-141">入力方向の要求に対して要求認証マネージャーを登録します。</span><span class="sxs-lookup"><span data-stu-id="807b1-141">Registers a claims authentication manager for the incoming claims.</span></span> <span data-ttu-id="807b1-142">任意。</span><span class="sxs-lookup"><span data-stu-id="807b1-142">Optional.</span></span>|
|[<span data-ttu-id="807b1-143">\<claimsAuthorizationManager ></span><span class="sxs-lookup"><span data-stu-id="807b1-143">\<claimsAuthorizationManager></span></span>](claimsauthorizationmanager.md)|<span data-ttu-id="807b1-144">入力方向の要求に対して要求承認マネージャーを登録します。</span><span class="sxs-lookup"><span data-stu-id="807b1-144">Registers a claims authorization manager for the incoming claims.</span></span> <span data-ttu-id="807b1-145">任意。</span><span class="sxs-lookup"><span data-stu-id="807b1-145">Optional.</span></span>|
|[<span data-ttu-id="807b1-146">\<claimTypeRequired></span><span class="sxs-lookup"><span data-stu-id="807b1-146">\<claimTypeRequired></span></span>](claimtyperequired.md)|<span data-ttu-id="807b1-147">受信セキュリティトークンに必要な要求のセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="807b1-147">Specifies the set of required claims for incoming security tokens.</span></span> <span data-ttu-id="807b1-148">任意。</span><span class="sxs-lookup"><span data-stu-id="807b1-148">Optional.</span></span>|
|[<span data-ttu-id="807b1-149">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="807b1-149">\<securityTokenHandlers></span></span>](securitytokenhandlers.md)|<span data-ttu-id="807b1-150">セキュリティトークンハンドラーのコレクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="807b1-150">Specifies a collection of security token handlers.</span></span> <span data-ttu-id="807b1-151">セキュリティトークンハンドラーの0個以上のコレクションを指定できます。</span><span class="sxs-lookup"><span data-stu-id="807b1-151">Zero or more collections of security token handlers can be specified.</span></span> <span data-ttu-id="807b1-152">任意。</span><span class="sxs-lookup"><span data-stu-id="807b1-152">Optional.</span></span>|
|[<span data-ttu-id="807b1-153">\<tokenReplayDetection></span><span class="sxs-lookup"><span data-stu-id="807b1-153">\<tokenReplayDetection></span></span>](tokenreplaydetection.md)|<span data-ttu-id="807b1-154">トークンリプレイ検出を有効にし、トークンの有効期限を指定します。</span><span class="sxs-lookup"><span data-stu-id="807b1-154">Enables token replay detection and specifies the expiration time for tokens.</span></span> <span data-ttu-id="807b1-155">は、サービスレベルまたはセキュリティトークンハンドラーコレクションで指定できます。</span><span class="sxs-lookup"><span data-stu-id="807b1-155">Can be specified at the service-level or on a security token handler collection.</span></span> <span data-ttu-id="807b1-156">任意。</span><span class="sxs-lookup"><span data-stu-id="807b1-156">Optional.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="807b1-157">親要素</span><span class="sxs-lookup"><span data-stu-id="807b1-157">Parent Elements</span></span>

|<span data-ttu-id="807b1-158">要素</span><span class="sxs-lookup"><span data-stu-id="807b1-158">Element</span></span>|<span data-ttu-id="807b1-159">説明</span><span class="sxs-lookup"><span data-stu-id="807b1-159">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="807b1-160">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="807b1-160">\<system.identityModel></span></span>](system-identitymodel.md)|<span data-ttu-id="807b1-161">アプリケーションで Windows Identity Foundation (WIF) オプションを有効にするための構成を提供します。</span><span class="sxs-lookup"><span data-stu-id="807b1-161">Provides configuration for enabling Windows Identity Foundation (WIF) options in applications.</span></span>|

## <a name="remarks"></a><span data-ttu-id="807b1-162">Remarks</span><span class="sxs-lookup"><span data-stu-id="807b1-162">Remarks</span></span>

<span data-ttu-id="807b1-163">複数の id 構成を定義し、それぞれに一意の名前を指定できます。</span><span class="sxs-lookup"><span data-stu-id="807b1-163">Multiple identity configurations may be defined, each with a unique name.</span></span> <span data-ttu-id="807b1-164">動作は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="807b1-164">The behavior is as follows:</span></span>

1. <span data-ttu-id="807b1-165">`<identityConfiguration>`要素が指定されていない場合は。</span><span class="sxs-lookup"><span data-stu-id="807b1-165">If no `<identityConfiguration>` element is specified.</span></span> <span data-ttu-id="807b1-166">既定の id 構成は、実行時に作成され、既定値が設定されます。</span><span class="sxs-lookup"><span data-stu-id="807b1-166">A default identity configuration is created at runtime and populated with default values.</span></span>

2. <span data-ttu-id="807b1-167">1つ`<identityConfiguration>`の要素が指定されている場合。</span><span class="sxs-lookup"><span data-stu-id="807b1-167">If a single `<identityConfiguration>` element is specified.</span></span> <span data-ttu-id="807b1-168">これは既定の id 構成です。</span><span class="sxs-lookup"><span data-stu-id="807b1-168">It is the default identity configuration.</span></span> <span data-ttu-id="807b1-169">名前が付けられているか名前が付いていないかは関係ありません。</span><span class="sxs-lookup"><span data-stu-id="807b1-169">It does not matter whether it is named or unnamed.</span></span>

3. <span data-ttu-id="807b1-170">複数`<identityConfiguration>`の要素が指定されている場合。</span><span class="sxs-lookup"><span data-stu-id="807b1-170">If multiple `<identityConfiguration>` elements are specified.</span></span> <span data-ttu-id="807b1-171">無名の要素は、既定の id 構成を指定します。</span><span class="sxs-lookup"><span data-stu-id="807b1-171">The unnamed element specifies the default identity configuration.</span></span> <span data-ttu-id="807b1-172">複数`<identityConfiguration>`の要素を指定する場合は、そのうちの1つを名前のないものにすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="807b1-172">It is recommended that when you specify multiple `<identityConfiguration>` elements, one of them should be unnamed.</span></span>

> [!WARNING]
> <span data-ttu-id="807b1-173">複数`<identityConfiguration>`の要素を指定する場合は、そのうちの1つを名前なしにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="807b1-173">If you specify multiple `<identityConfiguration>` elements, one of them should be unnamed.</span></span> <span data-ttu-id="807b1-174">名前のない要素が既定の id 構成になります。</span><span class="sxs-lookup"><span data-stu-id="807b1-174">The unnamed element will be the default identity configuration.</span></span>

 <span data-ttu-id="807b1-175">`<identityConfiguration>`要素で指定された設定の一部は、セキュリティトークンハンドラーコレクションの設定、または個々のセキュリティトークンハンドラーの設定によって上書きできます。</span><span class="sxs-lookup"><span data-stu-id="807b1-175">Some of the settings specified in the `<identityConfiguration>` element can be overridden by settings on a security token handler collection or by settings on individual security token handlers.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="807b1-176">クラスまたは<xref:System.IdentityModel.Services.ClaimsPrincipalPermission>クラスを使用して、コードにクレームベースのアクセス制御を提供する場合、 `<federationConfiguration>`要素によって参照される id 構成によって、要求承認マネージャーと、 <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute>承認の決定。</span><span class="sxs-lookup"><span data-stu-id="807b1-176">When using the <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> or the <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> class to provide claims-based access control in your code, the identity configuration that is referenced by the `<federationConfiguration>` element configures the claims authorization manager and policy that is used to make authorization decisions.</span></span> <span data-ttu-id="807b1-177">これは、Windows Communication Foundation (WCF) アプリケーションや Web ベースではないアプリケーションなど、パッシブな Web シナリオではないシナリオでも当てはまります。</span><span class="sxs-lookup"><span data-stu-id="807b1-177">This is true, even in scenarios that are not passive Web scenarios, for example Windows Communication Foundation (WCF) applications or an application that is not Web-based.</span></span> <span data-ttu-id="807b1-178">アプリケーションがパッシブな Web アプリケーション[ \<](claimsauthorizationmanager.md)でない場合は、参照される id 構成の claimsAuthorizationManager > 要素 (およびその子ポリシー要素が存在する場合) が適用される唯一の設定です。</span><span class="sxs-lookup"><span data-stu-id="807b1-178">If the application is not a passive Web application, the [\<claimsAuthorizationManager>](claimsauthorizationmanager.md) element (and its child policy elements, if present) of the referenced identity configuration are the only settings applied.</span></span> <span data-ttu-id="807b1-179">その他の設定はすべて無視されます。</span><span class="sxs-lookup"><span data-stu-id="807b1-179">All other settings are ignored.</span></span> <span data-ttu-id="807b1-180">詳細については、「 [ \<federationConfiguration >](federationconfiguration.md)要素」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="807b1-180">For more information, see the [\<federationConfiguration>](federationconfiguration.md) element.</span></span>

<span data-ttu-id="807b1-181">要素は、 <xref:System.IdentityModel.Configuration.IdentityConfigurationElement>クラスによって表されます。 `<identityConfiguration>`</span><span class="sxs-lookup"><span data-stu-id="807b1-181">The `<identityConfiguration>` element is represented by the <xref:System.IdentityModel.Configuration.IdentityConfigurationElement> class.</span></span> <span data-ttu-id="807b1-182">Id 構成セクションは、 <xref:System.IdentityModel.Configuration.IdentityConfiguration>クラスによって表されます。</span><span class="sxs-lookup"><span data-stu-id="807b1-182">An identity configuration section is represented by the <xref:System.IdentityModel.Configuration.IdentityConfiguration> class.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="807b1-183">`<identityConfiguration>`要素の子要素として次の要素を指定することは非推奨とされますが、旧バージョンとの互換性のために動作は引き続きサポートされています。</span><span class="sxs-lookup"><span data-stu-id="807b1-183">Specifying the following elements as child elements of the `<identityConfiguration>` element has been deprecated, although the behavior is still supported for backward compatibility.</span></span> <span data-ttu-id="807b1-184">代わりに、これらの要素を[ \<securityTokenHandlerConfiguration >](securitytokenhandlerconfiguration.md)要素の下に指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="807b1-184">These elements should, instead, be specified under the [\<securityTokenHandlerConfiguration>](securitytokenhandlerconfiguration.md) element.</span></span>
>
> - [<span data-ttu-id="807b1-185">\<audienceUris></span><span class="sxs-lookup"><span data-stu-id="807b1-185">\<audienceUris></span></span>](audienceuris.md)
> - [<span data-ttu-id="807b1-186">\<issuerNameRegistry ></span><span class="sxs-lookup"><span data-stu-id="807b1-186">\<issuerNameRegistry></span></span>](issuernameregistry.md)
> - [<span data-ttu-id="807b1-187">\<issuerTokenResolver ></span><span class="sxs-lookup"><span data-stu-id="807b1-187">\<issuerTokenResolver></span></span>](issuertokenresolver.md)
> - [<span data-ttu-id="807b1-188">\<serviceTokenResolver></span><span class="sxs-lookup"><span data-stu-id="807b1-188">\<serviceTokenResolver></span></span>](servicetokenresolver.md)

## <a name="example"></a><span data-ttu-id="807b1-189">例</span><span class="sxs-lookup"><span data-stu-id="807b1-189">Example</span></span>

<span data-ttu-id="807b1-190">次の例では、"alternateConfiguration" という名前の id 構成を作成します。</span><span class="sxs-lookup"><span data-stu-id="807b1-190">The following example creates an identity configuration named "alternateConfiguration".</span></span> <span data-ttu-id="807b1-191">Id 構成では、既定の設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="807b1-191">The identity configuration specifies default settings.</span></span>

```xml
<system.identityModel>
    <identityConfiguration name="alternateConfiguration"/>
</system.identityModel>
```

## <a name="see-also"></a><span data-ttu-id="807b1-192">関連項目</span><span class="sxs-lookup"><span data-stu-id="807b1-192">See also</span></span>

- <xref:System.IdentityModel.Configuration.IdentityConfiguration>
- <xref:System.IdentityModel.Configuration.IdentityConfigurationElement>
