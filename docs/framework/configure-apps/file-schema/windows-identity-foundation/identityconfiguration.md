---
title: <identityConfiguration>
ms.date: 03/30/2017
ms.assetid: 1db76253-07da-447b-9e7a-3705c7228cf4
author: BrucePerlerMS
ms.openlocfilehash: 0fa8c574fd5663606cf081f1000a24884306edfe
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "70251996"
---
# \<identityConfiguration>

<span data-ttu-id="eecf0-101">サービスレベルの id 設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="eecf0-101">Specifies service-level identity settings.</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<identityConfiguration>**  

## <a name="syntax"></a><span data-ttu-id="eecf0-102">構文</span><span class="sxs-lookup"><span data-stu-id="eecf0-102">Syntax</span></span>

```xml
<system.identityModel>
  <identityConfiguration
      name=xs:string
      saveBootstrapContext=xs:boolean>
      maximumClockSkew=TimeSpan >
  </identityConfiguration>
</system.identityModel>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="eecf0-103">属性および要素</span><span class="sxs-lookup"><span data-stu-id="eecf0-103">Attributes and Elements</span></span>

<span data-ttu-id="eecf0-104">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="eecf0-104">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="eecf0-105">属性</span><span class="sxs-lookup"><span data-stu-id="eecf0-105">Attributes</span></span>

|<span data-ttu-id="eecf0-106">属性</span><span class="sxs-lookup"><span data-stu-id="eecf0-106">Attribute</span></span>|<span data-ttu-id="eecf0-107">説明</span><span class="sxs-lookup"><span data-stu-id="eecf0-107">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="eecf0-108">name</span><span class="sxs-lookup"><span data-stu-id="eecf0-108">name</span></span>|<span data-ttu-id="eecf0-109">Id 構成セクションの名前。</span><span class="sxs-lookup"><span data-stu-id="eecf0-109">The name of the identity configuration section.</span></span> <span data-ttu-id="eecf0-110">この名前を使用して、特定の構成セクションを参照することができます。</span><span class="sxs-lookup"><span data-stu-id="eecf0-110">You can use this name to reference a specific configuration section.</span></span> <span data-ttu-id="eecf0-111">属性が指定されていない場合、セクションでは `name` 既定の構成を定義します。</span><span class="sxs-lookup"><span data-stu-id="eecf0-111">If no `name` attribute is specified, the section defines the default configuration.</span></span> <span data-ttu-id="eecf0-112">既定の構成は、パッシブフェデレーションシナリオでは常に使用されます。</span><span class="sxs-lookup"><span data-stu-id="eecf0-112">The default configuration is always used for passive federation scenarios.</span></span> <span data-ttu-id="eecf0-113">詳細については、要素を参照してください [\<federationConfiguration>](federationconfiguration.md) 。</span><span class="sxs-lookup"><span data-stu-id="eecf0-113">For more information, see the [\<federationConfiguration>](federationconfiguration.md) element.</span></span>|
|<span data-ttu-id="eecf0-114">saveBootstrapContext</span><span class="sxs-lookup"><span data-stu-id="eecf0-114">saveBootstrapContext</span></span>|<span data-ttu-id="eecf0-115">ブートストラップトークンをセッショントークンに含める必要があるかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="eecf0-115">Specifies whether bootstrap tokens should be included in the session token.</span></span> <span data-ttu-id="eecf0-116">また、要素の属性を設定することによって、トークンハンドラーコレクションに値を設定することもでき `saveBootstrapContext` [\<securityTokenHandlerConfiguration>](securitytokenhandlerconfiguration.md) ます。</span><span class="sxs-lookup"><span data-stu-id="eecf0-116">The value may also be set on a token handler collection by setting the `saveBootstrapContext` attribute on the [\<securityTokenHandlerConfiguration>](securitytokenhandlerconfiguration.md) element.</span></span> <span data-ttu-id="eecf0-117">トークンハンドラーコレクションに設定された値は、サービスで設定された値よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="eecf0-117">A value set on the token handler collection overrides the value set on the service.</span></span>|
|<span data-ttu-id="eecf0-118">maximumClockSkew</span><span class="sxs-lookup"><span data-stu-id="eecf0-118">maximumClockSkew</span></span>|<span data-ttu-id="eecf0-119"><xref:System.TimeSpan>許容される最大のクロックスキューを指定する。</span><span class="sxs-lookup"><span data-stu-id="eecf0-119">A <xref:System.TimeSpan> that specifies the maximum allowed clock skew.</span></span> <span data-ttu-id="eecf0-120">サインインセッションの有効期限の検証など、時間を区別する操作を実行するときに許容される最大のクロックスキューを制御します。</span><span class="sxs-lookup"><span data-stu-id="eecf0-120">Controls the maximum allowed clock skew when performing time-sensitive operations, such as validating the expiration time of a sign-in session.</span></span> <span data-ttu-id="eecf0-121">既定値は5分 "00:05:00" です。</span><span class="sxs-lookup"><span data-stu-id="eecf0-121">The default is 5 minutes, "00:05:00".</span></span> <span data-ttu-id="eecf0-122">値を指定する方法の詳細について <xref:System.TimeSpan> は、「 [Timespan values](../windows-workflow-foundation/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="eecf0-122">For more information about how to specify <xref:System.TimeSpan> values, see [Timespan Values](../windows-workflow-foundation/index.md).</span></span> <span data-ttu-id="eecf0-123">また、要素の属性を設定することによって、トークンハンドラーコレクションに最大クロックスキューを設定することもでき `maximumClockSkew` [\<securityTokenHandlerConfiguration>](securitytokenhandlerconfiguration.md) ます。</span><span class="sxs-lookup"><span data-stu-id="eecf0-123">The maximum clock skew may also be set on a token handler collection by setting the `maximumClockSkew` attribute on the [\<securityTokenHandlerConfiguration>](securitytokenhandlerconfiguration.md) element.</span></span> <span data-ttu-id="eecf0-124">トークンハンドラーコレクションに設定された値は、サービスで設定された値よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="eecf0-124">A value set on the token handler collection overrides the value set on the service.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="eecf0-125">子要素</span><span class="sxs-lookup"><span data-stu-id="eecf0-125">Child Elements</span></span>

|<span data-ttu-id="eecf0-126">要素</span><span class="sxs-lookup"><span data-stu-id="eecf0-126">Element</span></span>|<span data-ttu-id="eecf0-127">Description</span><span class="sxs-lookup"><span data-stu-id="eecf0-127">Description</span></span>|
|-------------|-----------------|
|[\<caches>](caches.md)|<span data-ttu-id="eecf0-128">セッショントークンとトークンリプレイ検出に使用されるキャッシュを登録します。</span><span class="sxs-lookup"><span data-stu-id="eecf0-128">Registers the caches used for session tokens and token replay detection.</span></span> <span data-ttu-id="eecf0-129">は、サービスレベルまたはセキュリティトークンハンドラーコレクションで指定できます。</span><span class="sxs-lookup"><span data-stu-id="eecf0-129">Can be specified at the service-level or on a security token handler collection.</span></span> <span data-ttu-id="eecf0-130">省略可能。</span><span class="sxs-lookup"><span data-stu-id="eecf0-130">Optional.</span></span>|
|[\<certificateValidation>](certificatevalidation.md)|<span data-ttu-id="eecf0-131">トークンハンドラーが証明書を検証するために使用する設定を制御します。</span><span class="sxs-lookup"><span data-stu-id="eecf0-131">Controls the settings that token handlers use to validate certificates.</span></span> <span data-ttu-id="eecf0-132">は、サービスレベルまたはセキュリティトークンハンドラーコレクションで指定できます。</span><span class="sxs-lookup"><span data-stu-id="eecf0-132">Can be specified at the service-level or on a security token handler collection.</span></span> <span data-ttu-id="eecf0-133">省略可能。</span><span class="sxs-lookup"><span data-stu-id="eecf0-133">Optional.</span></span>|
|[\<claimsAuthenticationManager>](claimsauthenticationmanager.md)|<span data-ttu-id="eecf0-134">入力方向の要求に対して要求認証マネージャーを登録します。</span><span class="sxs-lookup"><span data-stu-id="eecf0-134">Registers a claims authentication manager for the incoming claims.</span></span> <span data-ttu-id="eecf0-135">省略可能。</span><span class="sxs-lookup"><span data-stu-id="eecf0-135">Optional.</span></span>|
|[\<claimsAuthorizationManager>](claimsauthorizationmanager.md)|<span data-ttu-id="eecf0-136">入力方向の要求に対して要求承認マネージャーを登録します。</span><span class="sxs-lookup"><span data-stu-id="eecf0-136">Registers a claims authorization manager for the incoming claims.</span></span> <span data-ttu-id="eecf0-137">省略可能。</span><span class="sxs-lookup"><span data-stu-id="eecf0-137">Optional.</span></span>|
|[\<claimTypeRequired>](claimtyperequired.md)|<span data-ttu-id="eecf0-138">受信セキュリティトークンに必要な要求のセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="eecf0-138">Specifies the set of required claims for incoming security tokens.</span></span> <span data-ttu-id="eecf0-139">省略可能。</span><span class="sxs-lookup"><span data-stu-id="eecf0-139">Optional.</span></span>|
|[\<securityTokenHandlers>](securitytokenhandlers.md)|<span data-ttu-id="eecf0-140">セキュリティトークンハンドラーのコレクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="eecf0-140">Specifies a collection of security token handlers.</span></span> <span data-ttu-id="eecf0-141">セキュリティトークンハンドラーの0個以上のコレクションを指定できます。</span><span class="sxs-lookup"><span data-stu-id="eecf0-141">Zero or more collections of security token handlers can be specified.</span></span> <span data-ttu-id="eecf0-142">省略可能。</span><span class="sxs-lookup"><span data-stu-id="eecf0-142">Optional.</span></span>|
|[\<tokenReplayDetection>](tokenreplaydetection.md)|<span data-ttu-id="eecf0-143">トークンリプレイ検出を有効にし、トークンの有効期限を指定します。</span><span class="sxs-lookup"><span data-stu-id="eecf0-143">Enables token replay detection and specifies the expiration time for tokens.</span></span> <span data-ttu-id="eecf0-144">は、サービスレベルまたはセキュリティトークンハンドラーコレクションで指定できます。</span><span class="sxs-lookup"><span data-stu-id="eecf0-144">Can be specified at the service-level or on a security token handler collection.</span></span> <span data-ttu-id="eecf0-145">省略可能。</span><span class="sxs-lookup"><span data-stu-id="eecf0-145">Optional.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="eecf0-146">親要素</span><span class="sxs-lookup"><span data-stu-id="eecf0-146">Parent Elements</span></span>

|<span data-ttu-id="eecf0-147">要素</span><span class="sxs-lookup"><span data-stu-id="eecf0-147">Element</span></span>|<span data-ttu-id="eecf0-148">Description</span><span class="sxs-lookup"><span data-stu-id="eecf0-148">Description</span></span>|
|-------------|-----------------|
|[\<system.identityModel>](system-identitymodel.md)|<span data-ttu-id="eecf0-149">アプリケーションで Windows Identity Foundation (WIF) オプションを有効にするための構成を提供します。</span><span class="sxs-lookup"><span data-stu-id="eecf0-149">Provides configuration for enabling Windows Identity Foundation (WIF) options in applications.</span></span>|

## <a name="remarks"></a><span data-ttu-id="eecf0-150">解説</span><span class="sxs-lookup"><span data-stu-id="eecf0-150">Remarks</span></span>

<span data-ttu-id="eecf0-151">複数の id 構成を定義し、それぞれに一意の名前を指定できます。</span><span class="sxs-lookup"><span data-stu-id="eecf0-151">Multiple identity configurations may be defined, each with a unique name.</span></span> <span data-ttu-id="eecf0-152">動作は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="eecf0-152">The behavior is as follows:</span></span>

1. <span data-ttu-id="eecf0-153">要素が指定されていない場合は `<identityConfiguration>` 。</span><span class="sxs-lookup"><span data-stu-id="eecf0-153">If no `<identityConfiguration>` element is specified.</span></span> <span data-ttu-id="eecf0-154">既定の id 構成は、実行時に作成され、既定値が設定されます。</span><span class="sxs-lookup"><span data-stu-id="eecf0-154">A default identity configuration is created at runtime and populated with default values.</span></span>

2. <span data-ttu-id="eecf0-155">1つの `<identityConfiguration>` 要素が指定されている場合。</span><span class="sxs-lookup"><span data-stu-id="eecf0-155">If a single `<identityConfiguration>` element is specified.</span></span> <span data-ttu-id="eecf0-156">これは既定の id 構成です。</span><span class="sxs-lookup"><span data-stu-id="eecf0-156">It is the default identity configuration.</span></span> <span data-ttu-id="eecf0-157">名前が付けられているか名前が付いていないかは関係ありません。</span><span class="sxs-lookup"><span data-stu-id="eecf0-157">It does not matter whether it is named or unnamed.</span></span>

3. <span data-ttu-id="eecf0-158">複数の要素が指定されている場合 `<identityConfiguration>` 。</span><span class="sxs-lookup"><span data-stu-id="eecf0-158">If multiple `<identityConfiguration>` elements are specified.</span></span> <span data-ttu-id="eecf0-159">無名の要素は、既定の id 構成を指定します。</span><span class="sxs-lookup"><span data-stu-id="eecf0-159">The unnamed element specifies the default identity configuration.</span></span> <span data-ttu-id="eecf0-160">複数の要素を指定する場合は `<identityConfiguration>` 、そのうちの1つを名前のないものにすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="eecf0-160">It is recommended that when you specify multiple `<identityConfiguration>` elements, one of them should be unnamed.</span></span>

> [!WARNING]
> <span data-ttu-id="eecf0-161">複数の要素を指定する場合は `<identityConfiguration>` 、そのうちの1つを名前なしにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="eecf0-161">If you specify multiple `<identityConfiguration>` elements, one of them should be unnamed.</span></span> <span data-ttu-id="eecf0-162">名前のない要素が既定の id 構成になります。</span><span class="sxs-lookup"><span data-stu-id="eecf0-162">The unnamed element will be the default identity configuration.</span></span>

 <span data-ttu-id="eecf0-163">要素で指定された設定の一部 `<identityConfiguration>` は、セキュリティトークンハンドラーコレクションの設定、または個々のセキュリティトークンハンドラーの設定によって上書きできます。</span><span class="sxs-lookup"><span data-stu-id="eecf0-163">Some of the settings specified in the `<identityConfiguration>` element can be overridden by settings on a security token handler collection or by settings on individual security token handlers.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="eecf0-164">クラスまたはクラスを使用して、 <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> コード内にクレームベースのアクセス制御を提供する場合、要素によって参照される id 構成によって、 `<federationConfiguration>` 承認の決定に使用される要求承認マネージャーとポリシーが構成されます。</span><span class="sxs-lookup"><span data-stu-id="eecf0-164">When using the <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> or the <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> class to provide claims-based access control in your code, the identity configuration that is referenced by the `<federationConfiguration>` element configures the claims authorization manager and policy that is used to make authorization decisions.</span></span> <span data-ttu-id="eecf0-165">これは、Windows Communication Foundation (WCF) アプリケーションや Web ベースではないアプリケーションなど、パッシブな Web シナリオではないシナリオでも当てはまります。</span><span class="sxs-lookup"><span data-stu-id="eecf0-165">This is true, even in scenarios that are not passive Web scenarios, for example Windows Communication Foundation (WCF) applications or an application that is not Web-based.</span></span> <span data-ttu-id="eecf0-166">アプリケーションがパッシブな Web アプリケーションでない場合は、 [\<claimsAuthorizationManager>](claimsauthorizationmanager.md) 参照される id 構成の要素 (およびその子ポリシー要素が存在する場合) が適用される唯一の設定です。</span><span class="sxs-lookup"><span data-stu-id="eecf0-166">If the application is not a passive Web application, the [\<claimsAuthorizationManager>](claimsauthorizationmanager.md) element (and its child policy elements, if present) of the referenced identity configuration are the only settings applied.</span></span> <span data-ttu-id="eecf0-167">その他すべての設定は無視されます。</span><span class="sxs-lookup"><span data-stu-id="eecf0-167">All other settings are ignored.</span></span> <span data-ttu-id="eecf0-168">詳細については、要素を参照してください [\<federationConfiguration>](federationconfiguration.md) 。</span><span class="sxs-lookup"><span data-stu-id="eecf0-168">For more information, see the [\<federationConfiguration>](federationconfiguration.md) element.</span></span>

<span data-ttu-id="eecf0-169">`<identityConfiguration>`要素は、クラスによって表され <xref:System.IdentityModel.Configuration.IdentityConfigurationElement> ます。</span><span class="sxs-lookup"><span data-stu-id="eecf0-169">The `<identityConfiguration>` element is represented by the <xref:System.IdentityModel.Configuration.IdentityConfigurationElement> class.</span></span> <span data-ttu-id="eecf0-170">Id 構成セクションは、クラスによって表され <xref:System.IdentityModel.Configuration.IdentityConfiguration> ます。</span><span class="sxs-lookup"><span data-stu-id="eecf0-170">An identity configuration section is represented by the <xref:System.IdentityModel.Configuration.IdentityConfiguration> class.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="eecf0-171">要素の子要素として次の要素を指定することは `<identityConfiguration>` 非推奨とされますが、旧バージョンとの互換性のために動作は引き続きサポートされています。</span><span class="sxs-lookup"><span data-stu-id="eecf0-171">Specifying the following elements as child elements of the `<identityConfiguration>` element has been deprecated, although the behavior is still supported for backward compatibility.</span></span> <span data-ttu-id="eecf0-172">これらの要素は、代わりに要素で指定する必要があり [\<securityTokenHandlerConfiguration>](securitytokenhandlerconfiguration.md) ます。</span><span class="sxs-lookup"><span data-stu-id="eecf0-172">These elements should, instead, be specified under the [\<securityTokenHandlerConfiguration>](securitytokenhandlerconfiguration.md) element.</span></span>
>
> - [\<audienceUris>](audienceuris.md)
> - [\<issuerNameRegistry>](issuernameregistry.md)
> - [\<issuerTokenResolver>](issuertokenresolver.md)
> - [\<serviceTokenResolver>](servicetokenresolver.md)

## <a name="example"></a><span data-ttu-id="eecf0-173">例</span><span class="sxs-lookup"><span data-stu-id="eecf0-173">Example</span></span>

<span data-ttu-id="eecf0-174">次の例では、"alternateConfiguration" という名前の id 構成を作成します。</span><span class="sxs-lookup"><span data-stu-id="eecf0-174">The following example creates an identity configuration named "alternateConfiguration".</span></span> <span data-ttu-id="eecf0-175">Id 構成では、既定の設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="eecf0-175">The identity configuration specifies default settings.</span></span>

```xml
<system.identityModel>
    <identityConfiguration name="alternateConfiguration"/>
</system.identityModel>
```

## <a name="see-also"></a><span data-ttu-id="eecf0-176">関連項目</span><span class="sxs-lookup"><span data-stu-id="eecf0-176">See also</span></span>

- <xref:System.IdentityModel.Configuration.IdentityConfiguration>
- <xref:System.IdentityModel.Configuration.IdentityConfigurationElement>
