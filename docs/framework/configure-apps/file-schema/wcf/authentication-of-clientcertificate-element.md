---
title: <authentication> <clientCertificate>要素
ms.date: 03/30/2017
ms.assetid: 4a55eea2-1826-4026-b911-b7cc9e9c8bfe
ms.openlocfilehash: 99084f6b7afbdd8586ee706cd6ec44b349d81ff2
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398264"
---
# <a name="authentication-of-clientcertificate-element"></a><span data-ttu-id="60d53-102">\<clientCertificate > 要素\<の認証 ></span><span class="sxs-lookup"><span data-stu-id="60d53-102">\<authentication> of \<clientCertificate> Element</span></span>
<span data-ttu-id="60d53-103">サービスによって使用されるクライアント証明書の認証動作を指定します。</span><span class="sxs-lookup"><span data-stu-id="60d53-103">Specifies authentication behaviors for client certificates used by a service.</span></span>  
  
<span data-ttu-id="60d53-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="60d53-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="60d53-105">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="60d53-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="60d53-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<動作 >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="60d53-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="60d53-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceBehaviors >** ](servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="60d53-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)</span></span>\
<span data-ttu-id="60d53-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<動作 >** ](behavior-of-servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="60d53-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)</span></span>\
<span data-ttu-id="60d53-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceCredentials >** ](servicecredentials.md)</span><span class="sxs-lookup"><span data-stu-id="60d53-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCredentials>**](servicecredentials.md)</span></span>\
<span data-ttu-id="60d53-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<clientCertificate >** ](clientcertificate-of-servicecredentials.md)</span><span class="sxs-lookup"><span data-stu-id="60d53-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCertificate>**](clientcertificate-of-servicecredentials.md)</span></span>\
<span data-ttu-id="60d53-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<認証 >**</span><span class="sxs-lookup"><span data-stu-id="60d53-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<authentication>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="60d53-112">構文</span><span class="sxs-lookup"><span data-stu-id="60d53-112">Syntax</span></span>  
  
```xml  
<authentication customCertificateValidatorType="namespace.typeName, [,AssemblyName] [,Version=version number] [,Culture=culture] [,PublicKeyToken=token]"
                certificateValidationMode="ChainTrust/None/PeerTrust/PeerOrChainTrust/Custom"
                includeWindowsGroups="Boolean"
                mapClientCertificateToWindowsAccount="Boolean"
                revocationMode="NoCheck/Online/Offline"
                trustedStoreLocation="CurrentUser/LocalMachine" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="60d53-113">属性および要素</span><span class="sxs-lookup"><span data-stu-id="60d53-113">Attributes and Elements</span></span>  
 <span data-ttu-id="60d53-114">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="60d53-114">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="60d53-115">属性</span><span class="sxs-lookup"><span data-stu-id="60d53-115">Attributes</span></span>  
  
|<span data-ttu-id="60d53-116">属性</span><span class="sxs-lookup"><span data-stu-id="60d53-116">Attribute</span></span>|<span data-ttu-id="60d53-117">説明</span><span class="sxs-lookup"><span data-stu-id="60d53-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="60d53-118">customCertificateValidatorType</span><span class="sxs-lookup"><span data-stu-id="60d53-118">customCertificateValidatorType</span></span>|<span data-ttu-id="60d53-119">省略可能な文字列。</span><span class="sxs-lookup"><span data-stu-id="60d53-119">Optional string.</span></span> <span data-ttu-id="60d53-120">カスタム型の検証に使用される型およびアセンブリです。</span><span class="sxs-lookup"><span data-stu-id="60d53-120">A type and assembly used to validate a custom type.</span></span> <span data-ttu-id="60d53-121">`certificateValidationMode` が `Custom` に設定されている場合は、この属性を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="60d53-121">This attribute must be set when `certificateValidationMode` is set to `Custom`.</span></span>|  
|<span data-ttu-id="60d53-122">certificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="60d53-122">certificateValidationMode</span></span>|<span data-ttu-id="60d53-123">省略可能な列挙体です。</span><span class="sxs-lookup"><span data-stu-id="60d53-123">Optional enumeration.</span></span> <span data-ttu-id="60d53-124">資格情報の検証に使用されるモードのいずれかを指定します。</span><span class="sxs-lookup"><span data-stu-id="60d53-124">Specifies one of the modes used to validate credentials.</span></span> <span data-ttu-id="60d53-125">この属性は <xref:System.ServiceModel.Security.X509CertificateValidationMode> 型です。</span><span class="sxs-lookup"><span data-stu-id="60d53-125">This attribute is of the <xref:System.ServiceModel.Security.X509CertificateValidationMode> type.</span></span> <span data-ttu-id="60d53-126"><xref:System.ServiceModel.Security.X509CertificateValidationMode.Custom?displayProperty=nameWithType> に設定されている場合、`customCertificateValidator` も指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="60d53-126">If set to <xref:System.ServiceModel.Security.X509CertificateValidationMode.Custom?displayProperty=nameWithType>, then a `customCertificateValidator` must also be supplied.</span></span> <span data-ttu-id="60d53-127">既定値は、<xref:System.ServiceModel.Security.X509CertificateValidationMode.ChainTrust?displayProperty=nameWithType> です。</span><span class="sxs-lookup"><span data-stu-id="60d53-127">The default is <xref:System.ServiceModel.Security.X509CertificateValidationMode.ChainTrust?displayProperty=nameWithType>.</span></span>|  
|<span data-ttu-id="60d53-128">includeWindowsGroups</span><span class="sxs-lookup"><span data-stu-id="60d53-128">includeWindowsGroups</span></span>|<span data-ttu-id="60d53-129">省略可能なブール。</span><span class="sxs-lookup"><span data-stu-id="60d53-129">Optional Boolean.</span></span> <span data-ttu-id="60d53-130">セキュリティ コンテキストに Windows グループが含まれているかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="60d53-130">Specifies if Windows groups are included in the security context.</span></span> <span data-ttu-id="60d53-131">この属性を `true` に設定すると、グループ全体が拡張されるため、パフォーマンスに影響が及びます。</span><span class="sxs-lookup"><span data-stu-id="60d53-131">Setting this attribute to `true` has a performance impact, as it results in a full group expansion.</span></span> <span data-ttu-id="60d53-132">ユーザーが属するグループの一覧を生成する必要がない場合は、この属性を `false` に設定します。</span><span class="sxs-lookup"><span data-stu-id="60d53-132">Set this attribute to `false` if you do not need to establish the list of groups a user belongs to.</span></span>|  
|<span data-ttu-id="60d53-133">mapClientCertificateToWindowsAccount</span><span class="sxs-lookup"><span data-stu-id="60d53-133">mapClientCertificateToWindowsAccount</span></span>|<span data-ttu-id="60d53-134">ブール型。</span><span class="sxs-lookup"><span data-stu-id="60d53-134">Boolean.</span></span> <span data-ttu-id="60d53-135">証明書を使用してクライアントを Windows ID にマップできるかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="60d53-135">Specifies whether the client can be mapped to a Windows identity using the certificate.</span></span> <span data-ttu-id="60d53-136">これを行うには、Active Directory が有効である必要があります。</span><span class="sxs-lookup"><span data-stu-id="60d53-136">Active Directory must be enabled to do this.</span></span>|  
|<span data-ttu-id="60d53-137">revocationMode</span><span class="sxs-lookup"><span data-stu-id="60d53-137">revocationMode</span></span>|<span data-ttu-id="60d53-138">省略可能な列挙体です。</span><span class="sxs-lookup"><span data-stu-id="60d53-138">Optional enumeration.</span></span> <span data-ttu-id="60d53-139">証明書失効リスト (RCL) のチェックに使用されるモードのいずれかです。</span><span class="sxs-lookup"><span data-stu-id="60d53-139">One of the modes used to check for a revoked certificate lists (RCL).</span></span> <span data-ttu-id="60d53-140">既定値は、`Online` です。</span><span class="sxs-lookup"><span data-stu-id="60d53-140">The default is `Online`.</span></span> <span data-ttu-id="60d53-141">この値は、HTTP トランスポート セキュリティを使用する場合は無視されます。</span><span class="sxs-lookup"><span data-stu-id="60d53-141">This value is ignored when using HTTP transport security.</span></span>|  
|<span data-ttu-id="60d53-142">trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="60d53-142">trustedStoreLocation</span></span>|<span data-ttu-id="60d53-143">省略可能な列挙体です。</span><span class="sxs-lookup"><span data-stu-id="60d53-143">Optional enumeration.</span></span> <span data-ttu-id="60d53-144">2 つのシステム格納場所 (`LocalMachine` または `CurrentUser`) のいずれかです。</span><span class="sxs-lookup"><span data-stu-id="60d53-144">One of the two system store locations: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="60d53-145">この値は、サービス証明書がクライアントにネゴシエートされるときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="60d53-145">This value is used when a service certificate is negotiated to the client.</span></span> <span data-ttu-id="60d53-146">指定されたストアの場所にある**信頼さ**れた People ストアに対して検証が実行されます。</span><span class="sxs-lookup"><span data-stu-id="60d53-146">Validation is performed against the **Trusted People** store in the specified store location.</span></span> <span data-ttu-id="60d53-147">既定値は `CurrentUser` です。</span><span class="sxs-lookup"><span data-stu-id="60d53-147">The default is `CurrentUser`.</span></span>|  
  
## <a name="customcertificatevalidatortype-attribute"></a><span data-ttu-id="60d53-148">customCertificateValidatorType 属性</span><span class="sxs-lookup"><span data-stu-id="60d53-148">customCertificateValidatorType Attribute</span></span>  
  
|<span data-ttu-id="60d53-149">値</span><span class="sxs-lookup"><span data-stu-id="60d53-149">Value</span></span>|<span data-ttu-id="60d53-150">説明</span><span class="sxs-lookup"><span data-stu-id="60d53-150">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="60d53-151">String</span><span class="sxs-lookup"><span data-stu-id="60d53-151">String</span></span>|<span data-ttu-id="60d53-152">タイプ名およびアセンブリと、タイプの検索に使用される他のデータを指定します。</span><span class="sxs-lookup"><span data-stu-id="60d53-152">Specifies the type name and assembly and other data used to find the type.</span></span>|  
  
## <a name="certificatevalidationmode-attribute"></a><span data-ttu-id="60d53-153">certificateValidationMode 属性</span><span class="sxs-lookup"><span data-stu-id="60d53-153">certificateValidationMode Attribute</span></span>  
  
|<span data-ttu-id="60d53-154">値</span><span class="sxs-lookup"><span data-stu-id="60d53-154">Value</span></span>|<span data-ttu-id="60d53-155">説明</span><span class="sxs-lookup"><span data-stu-id="60d53-155">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="60d53-156">列挙</span><span class="sxs-lookup"><span data-stu-id="60d53-156">Enumeration</span></span>|<span data-ttu-id="60d53-157">次のいずれかの値です。None、PeerTrust、ChainTrust、PeerOrChainTrust、Custom。</span><span class="sxs-lookup"><span data-stu-id="60d53-157">One of the following values: None, PeerTrust, ChainTrust, PeerOrChainTrust, Custom.</span></span><br /><br /> <span data-ttu-id="60d53-158">詳細については、「[証明書の使用](../../../wcf/feature-details/working-with-certificates.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="60d53-158">For more information, see [Working with Certificates](../../../wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="revocationmode-attribute"></a><span data-ttu-id="60d53-159">revocationMode 属性</span><span class="sxs-lookup"><span data-stu-id="60d53-159">revocationMode Attribute</span></span>  
  
|<span data-ttu-id="60d53-160">値</span><span class="sxs-lookup"><span data-stu-id="60d53-160">Value</span></span>|<span data-ttu-id="60d53-161">説明</span><span class="sxs-lookup"><span data-stu-id="60d53-161">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="60d53-162">列挙</span><span class="sxs-lookup"><span data-stu-id="60d53-162">Enumeration</span></span>|<span data-ttu-id="60d53-163">次のいずれかの値です。NoCheck、Online、Offline。</span><span class="sxs-lookup"><span data-stu-id="60d53-163">One of the following values: NoCheck, Online, Offline.</span></span> <span data-ttu-id="60d53-164">詳細については、「[証明書の使用](../../../wcf/feature-details/working-with-certificates.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="60d53-164">For more information, see [Working with Certificates](../../../wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="trustedstorelocation-attribute"></a><span data-ttu-id="60d53-165">trustedStoreLocation 属性</span><span class="sxs-lookup"><span data-stu-id="60d53-165">trustedStoreLocation Attribute</span></span>  
  
|<span data-ttu-id="60d53-166">値</span><span class="sxs-lookup"><span data-stu-id="60d53-166">Value</span></span>|<span data-ttu-id="60d53-167">説明</span><span class="sxs-lookup"><span data-stu-id="60d53-167">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="60d53-168">列挙型</span><span class="sxs-lookup"><span data-stu-id="60d53-168">Enumeration</span></span>|<span data-ttu-id="60d53-169">`LocalMachine` または `CurrentUser` のいずれかの値にします。</span><span class="sxs-lookup"><span data-stu-id="60d53-169">One of the following values: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="60d53-170">既定値は、`CurrentUser` です。</span><span class="sxs-lookup"><span data-stu-id="60d53-170">The default is `CurrentUser`.</span></span> <span data-ttu-id="60d53-171">クライアント アプリケーションがシステム アカウントで実行されている場合、証明書は通常 `LocalMachine` の下にあります。</span><span class="sxs-lookup"><span data-stu-id="60d53-171">If the client application is running under a system account then the certificate is typically under `LocalMachine`.</span></span> <span data-ttu-id="60d53-172">クライアント アプリケーションがユーザー アカウントで実行されている場合、証明書は通常 `CurrentUser` の下にあります。</span><span class="sxs-lookup"><span data-stu-id="60d53-172">If the client application is running under a user account then the certificate is typically in `CurrentUser`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="60d53-173">子要素</span><span class="sxs-lookup"><span data-stu-id="60d53-173">Child Elements</span></span>  
 <span data-ttu-id="60d53-174">なし。</span><span class="sxs-lookup"><span data-stu-id="60d53-174">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="60d53-175">親要素</span><span class="sxs-lookup"><span data-stu-id="60d53-175">Parent Elements</span></span>  
  
|<span data-ttu-id="60d53-176">要素</span><span class="sxs-lookup"><span data-stu-id="60d53-176">Element</span></span>|<span data-ttu-id="60d53-177">説明</span><span class="sxs-lookup"><span data-stu-id="60d53-177">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="60d53-178">\<clientCertificate></span><span class="sxs-lookup"><span data-stu-id="60d53-178">\<clientCertificate></span></span>](clientcertificate-of-servicecredentials.md)|<span data-ttu-id="60d53-179">サービスに対するクライアントの認証に使用する X.509 証明書を定義します。</span><span class="sxs-lookup"><span data-stu-id="60d53-179">Defines an X.509 certificate used to authenticate a client to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="60d53-180">Remarks</span><span class="sxs-lookup"><span data-stu-id="60d53-180">Remarks</span></span>  
 <span data-ttu-id="60d53-181">`<authentication>` 要素は、<xref:System.ServiceModel.Security.X509ClientCertificateAuthentication> クラスに対応します。</span><span class="sxs-lookup"><span data-stu-id="60d53-181">The `<authentication>` element corresponds to the <xref:System.ServiceModel.Security.X509ClientCertificateAuthentication> class.</span></span> <span data-ttu-id="60d53-182">この要素を使用すると、クライアントを認証する方法をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="60d53-182">It enables you to customize how clients are authenticated.</span></span> <span data-ttu-id="60d53-183">`certificateValidationMode` 属性は、`None`、`ChainTrust`、`PeerOrChainTrust`、`PeerTrust`、または `Custom` に設定できます。</span><span class="sxs-lookup"><span data-stu-id="60d53-183">You can set the `certificateValidationMode` attribute to `None`, `ChainTrust`, `PeerOrChainTrust`, `PeerTrust`, or `Custom`.</span></span> <span data-ttu-id="60d53-184">既定では、レベルはに`ChainTrust`設定されています。これは、チェーンの最上位にあるルート証明*機関*で終了する証明書の階層構造で各証明書を検索する必要があることを指定します。</span><span class="sxs-lookup"><span data-stu-id="60d53-184">By default, the level is set to `ChainTrust`, which specifies that each certificate must be found in a hierarchy of certificates ending in a *root authority* at the top of the chain.</span></span> <span data-ttu-id="60d53-185">これは最もセキュリティで保護されているモードです。</span><span class="sxs-lookup"><span data-stu-id="60d53-185">This is the most secure mode.</span></span> <span data-ttu-id="60d53-186">また、値を `PeerOrChainTrust` に設定することもできます。これは、信頼されたチェーン内の証明書と共に、自己発行された証明書 (ピア信頼) も受け入れるよう指定します。</span><span class="sxs-lookup"><span data-stu-id="60d53-186">You can also set the value to `PeerOrChainTrust`, which specifies that self-issued certificates (peer trust) are accepted as well as certificates that are in a trusted chain.</span></span> <span data-ttu-id="60d53-187">自己発行の資格情報は信頼された証明機関から購入したものである必要はないため、この値はクライアントとサービスの開発およびデバッグに使用されます。</span><span class="sxs-lookup"><span data-stu-id="60d53-187">This value is used when developing and debugging clients and services because self-issued certificates need not be purchased from a trusted authority.</span></span> <span data-ttu-id="60d53-188">クライアントを展開するときは、代わりに `ChainTrust` 値を使用します。</span><span class="sxs-lookup"><span data-stu-id="60d53-188">When deploying a client, use the `ChainTrust` value instead.</span></span>  
  
 <span data-ttu-id="60d53-189">また、値を `Custom` に設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="60d53-189">You can also set the value to `Custom`.</span></span> <span data-ttu-id="60d53-190">`Custom` 値に設定する場合は、`customCertificateValidatorType` 属性を、証明書の検証に使用するアセンブリと型に設定する必要もあります。</span><span class="sxs-lookup"><span data-stu-id="60d53-190">When set to the `Custom` value, you must also set the `customCertificateValidatorType` attribute to an assembly and type used to validate the certificate.</span></span> <span data-ttu-id="60d53-191">独自のカスタム検証を作成するには、抽象 <xref:System.IdentityModel.Selectors.X509CertificateValidator> クラスを継承する必要があります。</span><span class="sxs-lookup"><span data-stu-id="60d53-191">To create your own custom validator, you must inherit from the abstract <xref:System.IdentityModel.Selectors.X509CertificateValidator> class.</span></span> <span data-ttu-id="60d53-192">詳細については、「[方法 :カスタム証明書検証](../../../wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md)を採用するサービスを作成します。</span><span class="sxs-lookup"><span data-stu-id="60d53-192">For more information, see [How to: Create a Service that Employs a Custom Certificate Validator](../../../wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="60d53-193">例</span><span class="sxs-lookup"><span data-stu-id="60d53-193">Example</span></span>  
 <span data-ttu-id="60d53-194">次のコードは、`<authentication>` 要素の X.509 証明書とカスタム検証タイプを指定します。</span><span class="sxs-lookup"><span data-stu-id="60d53-194">The following code specifies an X.509 certificate and a custom validation type in the `<authentication>` element.</span></span>  
  
```xml  
<serviceBehaviors>
  <behavior name="myServiceBehavior">
    <clientCertificate>
      <certificate findValue="www.cohowinery.com"
                   storeLocation="CurrentUser"
                   storeName="TrustedPeople"
                   x509FindType="FindByIssuerName" />
      <authentication customCertificateValidatorType="MyTypes.Coho"
                      certificateValidationMode="Custom"
                      revocationMode="Offline"
                      includeWindowsGroups="false"
                      mapClientCertificateToWindowsAccount="true" />
    </clientCertificate>
  </behavior>
</serviceBehaviors>
```  
  
## <a name="see-also"></a><span data-ttu-id="60d53-195">関連項目</span><span class="sxs-lookup"><span data-stu-id="60d53-195">See also</span></span>

- <xref:System.ServiceModel.Security.X509ClientCertificateAuthentication>
- <xref:System.ServiceModel.Security.X509CertificateValidationMode>
- <xref:System.ServiceModel.Security.X509CertificateInitiatorServiceCredential.Authentication%2A>
- <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement.Authentication%2A>
- <xref:System.ServiceModel.Configuration.X509ClientCertificateAuthenticationElement>
- [<span data-ttu-id="60d53-196">セキュリティ動作</span><span class="sxs-lookup"><span data-stu-id="60d53-196">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="60d53-197">方法: カスタム証明書の検証を使用するサービスを作成します。</span><span class="sxs-lookup"><span data-stu-id="60d53-197">How to: Create a Service that Employs a Custom Certificate Validator</span></span>](../../../wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md)
- [<span data-ttu-id="60d53-198">証明書の使用</span><span class="sxs-lookup"><span data-stu-id="60d53-198">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
