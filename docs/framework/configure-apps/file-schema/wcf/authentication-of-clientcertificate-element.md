---
title: <authentication><clientCertificate>要素の
ms.date: 03/30/2017
ms.assetid: 4a55eea2-1826-4026-b911-b7cc9e9c8bfe
ms.openlocfilehash: 13296dbc2b3bc8836770197a1549586c841b4635
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91201604"
---
# <a name="authentication-of-clientcertificate-element"></a><span data-ttu-id="80fac-102">\<authentication>\<clientCertificate>要素の</span><span class="sxs-lookup"><span data-stu-id="80fac-102">\<authentication> of \<clientCertificate> Element</span></span>

<span data-ttu-id="80fac-103">サービスによって使用されるクライアント証明書の認証動作を指定します。</span><span class="sxs-lookup"><span data-stu-id="80fac-103">Specifies authentication behaviors for client certificates used by a service.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCredentials>**](servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCertificate>**](clientcertificate-of-servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<authentication>**  
  
## <a name="syntax"></a><span data-ttu-id="80fac-104">構文</span><span class="sxs-lookup"><span data-stu-id="80fac-104">Syntax</span></span>  
  
```xml  
<authentication customCertificateValidatorType="namespace.typeName, [,AssemblyName] [,Version=version number] [,Culture=culture] [,PublicKeyToken=token]"
                certificateValidationMode="ChainTrust/None/PeerTrust/PeerOrChainTrust/Custom"
                includeWindowsGroups="Boolean"
                mapClientCertificateToWindowsAccount="Boolean"
                revocationMode="NoCheck/Online/Offline"
                trustedStoreLocation="CurrentUser/LocalMachine" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="80fac-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="80fac-105">Attributes and Elements</span></span>  

 <span data-ttu-id="80fac-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="80fac-106">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="80fac-107">属性</span><span class="sxs-lookup"><span data-stu-id="80fac-107">Attributes</span></span>  
  
|<span data-ttu-id="80fac-108">属性</span><span class="sxs-lookup"><span data-stu-id="80fac-108">Attribute</span></span>|<span data-ttu-id="80fac-109">[説明]</span><span class="sxs-lookup"><span data-stu-id="80fac-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="80fac-110">customCertificateValidatorType</span><span class="sxs-lookup"><span data-stu-id="80fac-110">customCertificateValidatorType</span></span>|<span data-ttu-id="80fac-111">省略可能な文字列。</span><span class="sxs-lookup"><span data-stu-id="80fac-111">Optional string.</span></span> <span data-ttu-id="80fac-112">カスタム型の検証に使用される型およびアセンブリです。</span><span class="sxs-lookup"><span data-stu-id="80fac-112">A type and assembly used to validate a custom type.</span></span> <span data-ttu-id="80fac-113">`certificateValidationMode` が `Custom` に設定されている場合は、この属性を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="80fac-113">This attribute must be set when `certificateValidationMode` is set to `Custom`.</span></span>|  
|<span data-ttu-id="80fac-114">certificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="80fac-114">certificateValidationMode</span></span>|<span data-ttu-id="80fac-115">省略可能な列挙体です。</span><span class="sxs-lookup"><span data-stu-id="80fac-115">Optional enumeration.</span></span> <span data-ttu-id="80fac-116">資格情報の検証に使用されるモードのいずれかを指定します。</span><span class="sxs-lookup"><span data-stu-id="80fac-116">Specifies one of the modes used to validate credentials.</span></span> <span data-ttu-id="80fac-117">この属性は <xref:System.ServiceModel.Security.X509CertificateValidationMode> 型です。</span><span class="sxs-lookup"><span data-stu-id="80fac-117">This attribute is of the <xref:System.ServiceModel.Security.X509CertificateValidationMode> type.</span></span> <span data-ttu-id="80fac-118"><xref:System.ServiceModel.Security.X509CertificateValidationMode.Custom?displayProperty=nameWithType> に設定されている場合、`customCertificateValidator` も指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="80fac-118">If set to <xref:System.ServiceModel.Security.X509CertificateValidationMode.Custom?displayProperty=nameWithType>, then a `customCertificateValidator` must also be supplied.</span></span> <span data-ttu-id="80fac-119">既定値は、<xref:System.ServiceModel.Security.X509CertificateValidationMode.ChainTrust?displayProperty=nameWithType> です。</span><span class="sxs-lookup"><span data-stu-id="80fac-119">The default is <xref:System.ServiceModel.Security.X509CertificateValidationMode.ChainTrust?displayProperty=nameWithType>.</span></span>|  
|<span data-ttu-id="80fac-120">includeWindowsGroups</span><span class="sxs-lookup"><span data-stu-id="80fac-120">includeWindowsGroups</span></span>|<span data-ttu-id="80fac-121">省略可能なブール。</span><span class="sxs-lookup"><span data-stu-id="80fac-121">Optional Boolean.</span></span> <span data-ttu-id="80fac-122">セキュリティ コンテキストに Windows グループが含まれているかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="80fac-122">Specifies if Windows groups are included in the security context.</span></span> <span data-ttu-id="80fac-123">この属性を `true` に設定すると、グループ全体が拡張されるため、パフォーマンスに影響が及びます。</span><span class="sxs-lookup"><span data-stu-id="80fac-123">Setting this attribute to `true` has a performance impact, as it results in a full group expansion.</span></span> <span data-ttu-id="80fac-124">ユーザーが属するグループの一覧を生成する必要がない場合は、この属性を `false` に設定します。</span><span class="sxs-lookup"><span data-stu-id="80fac-124">Set this attribute to `false` if you do not need to establish the list of groups a user belongs to.</span></span>|  
|<span data-ttu-id="80fac-125">mapClientCertificateToWindowsAccount</span><span class="sxs-lookup"><span data-stu-id="80fac-125">mapClientCertificateToWindowsAccount</span></span>|<span data-ttu-id="80fac-126">Boolean です。</span><span class="sxs-lookup"><span data-stu-id="80fac-126">Boolean.</span></span> <span data-ttu-id="80fac-127">証明書を使用してクライアントを Windows ID にマップできるかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="80fac-127">Specifies whether the client can be mapped to a Windows identity using the certificate.</span></span> <span data-ttu-id="80fac-128">これを行うには、Active Directory が有効である必要があります。</span><span class="sxs-lookup"><span data-stu-id="80fac-128">Active Directory must be enabled to do this.</span></span>|  
|<span data-ttu-id="80fac-129">revocationMode</span><span class="sxs-lookup"><span data-stu-id="80fac-129">revocationMode</span></span>|<span data-ttu-id="80fac-130">省略可能な列挙体です。</span><span class="sxs-lookup"><span data-stu-id="80fac-130">Optional enumeration.</span></span> <span data-ttu-id="80fac-131">証明書失効リスト (RCL) のチェックに使用されるモードのいずれかです。</span><span class="sxs-lookup"><span data-stu-id="80fac-131">One of the modes used to check for a revoked certificate lists (RCL).</span></span> <span data-ttu-id="80fac-132">既定では、 `Online`です。</span><span class="sxs-lookup"><span data-stu-id="80fac-132">The default is `Online`.</span></span> <span data-ttu-id="80fac-133">この値は、HTTP トランスポート セキュリティを使用する場合は無視されます。</span><span class="sxs-lookup"><span data-stu-id="80fac-133">This value is ignored when using HTTP transport security.</span></span>|  
|<span data-ttu-id="80fac-134">trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="80fac-134">trustedStoreLocation</span></span>|<span data-ttu-id="80fac-135">省略可能な列挙体です。</span><span class="sxs-lookup"><span data-stu-id="80fac-135">Optional enumeration.</span></span> <span data-ttu-id="80fac-136">2 つのシステム格納場所 (`LocalMachine` または `CurrentUser`) のいずれかです。</span><span class="sxs-lookup"><span data-stu-id="80fac-136">One of the two system store locations: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="80fac-137">この値は、サービス証明書がクライアントにネゴシエートされるときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="80fac-137">This value is used when a service certificate is negotiated to the client.</span></span> <span data-ttu-id="80fac-138">指定されたストアの場所にある **信頼さ** れた People ストアに対して検証が実行されます。</span><span class="sxs-lookup"><span data-stu-id="80fac-138">Validation is performed against the **Trusted People** store in the specified store location.</span></span> <span data-ttu-id="80fac-139">既定では、 `CurrentUser`です。</span><span class="sxs-lookup"><span data-stu-id="80fac-139">The default is `CurrentUser`.</span></span>|  
  
## <a name="customcertificatevalidatortype-attribute"></a><span data-ttu-id="80fac-140">customCertificateValidatorType 属性</span><span class="sxs-lookup"><span data-stu-id="80fac-140">customCertificateValidatorType Attribute</span></span>  
  
|<span data-ttu-id="80fac-141">値</span><span class="sxs-lookup"><span data-stu-id="80fac-141">Value</span></span>|<span data-ttu-id="80fac-142">説明</span><span class="sxs-lookup"><span data-stu-id="80fac-142">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="80fac-143">String</span><span class="sxs-lookup"><span data-stu-id="80fac-143">String</span></span>|<span data-ttu-id="80fac-144">タイプ名およびアセンブリと、タイプの検索に使用される他のデータを指定します。</span><span class="sxs-lookup"><span data-stu-id="80fac-144">Specifies the type name and assembly and other data used to find the type.</span></span>|  
  
## <a name="certificatevalidationmode-attribute"></a><span data-ttu-id="80fac-145">certificateValidationMode 属性</span><span class="sxs-lookup"><span data-stu-id="80fac-145">certificateValidationMode Attribute</span></span>  
  
|<span data-ttu-id="80fac-146">値</span><span class="sxs-lookup"><span data-stu-id="80fac-146">Value</span></span>|<span data-ttu-id="80fac-147">[説明]</span><span class="sxs-lookup"><span data-stu-id="80fac-147">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="80fac-148">列挙</span><span class="sxs-lookup"><span data-stu-id="80fac-148">Enumeration</span></span>|<span data-ttu-id="80fac-149">None、PeerTrust、ChainTrust、PeerOrChainTrust、Custom のいずれかの値にします。</span><span class="sxs-lookup"><span data-stu-id="80fac-149">One of the following values: None, PeerTrust, ChainTrust, PeerOrChainTrust, Custom.</span></span><br /><br /> <span data-ttu-id="80fac-150">詳細については、「 [証明書の使用](../../../wcf/feature-details/working-with-certificates.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="80fac-150">For more information, see [Working with Certificates](../../../wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="revocationmode-attribute"></a><span data-ttu-id="80fac-151">revocationMode 属性</span><span class="sxs-lookup"><span data-stu-id="80fac-151">revocationMode Attribute</span></span>  
  
|<span data-ttu-id="80fac-152">値</span><span class="sxs-lookup"><span data-stu-id="80fac-152">Value</span></span>|<span data-ttu-id="80fac-153">[説明]</span><span class="sxs-lookup"><span data-stu-id="80fac-153">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="80fac-154">列挙</span><span class="sxs-lookup"><span data-stu-id="80fac-154">Enumeration</span></span>|<span data-ttu-id="80fac-155">NoCheck、Online、Offline のいずれかの値にします。</span><span class="sxs-lookup"><span data-stu-id="80fac-155">One of the following values: NoCheck, Online, Offline.</span></span> <span data-ttu-id="80fac-156">詳細については、「 [証明書の使用](../../../wcf/feature-details/working-with-certificates.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="80fac-156">For more information, see [Working with Certificates](../../../wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="trustedstorelocation-attribute"></a><span data-ttu-id="80fac-157">trustedStoreLocation 属性</span><span class="sxs-lookup"><span data-stu-id="80fac-157">trustedStoreLocation Attribute</span></span>  
  
|<span data-ttu-id="80fac-158">値</span><span class="sxs-lookup"><span data-stu-id="80fac-158">Value</span></span>|<span data-ttu-id="80fac-159">[説明]</span><span class="sxs-lookup"><span data-stu-id="80fac-159">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="80fac-160">列挙</span><span class="sxs-lookup"><span data-stu-id="80fac-160">Enumeration</span></span>|<span data-ttu-id="80fac-161">次のいずれかの値を指定できます。`LocalMachine` または `CurrentUser`。</span><span class="sxs-lookup"><span data-stu-id="80fac-161">One of the following values: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="80fac-162">既定では、 `CurrentUser`です。</span><span class="sxs-lookup"><span data-stu-id="80fac-162">The default is `CurrentUser`.</span></span> <span data-ttu-id="80fac-163">クライアント アプリケーションがシステム アカウントで実行されている場合、証明書は通常 `LocalMachine` の下にあります。</span><span class="sxs-lookup"><span data-stu-id="80fac-163">If the client application is running under a system account then the certificate is typically under `LocalMachine`.</span></span> <span data-ttu-id="80fac-164">クライアント アプリケーションがユーザー アカウントで実行されている場合、証明書は通常 `CurrentUser` の下にあります。</span><span class="sxs-lookup"><span data-stu-id="80fac-164">If the client application is running under a user account then the certificate is typically in `CurrentUser`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="80fac-165">子要素</span><span class="sxs-lookup"><span data-stu-id="80fac-165">Child Elements</span></span>  

 <span data-ttu-id="80fac-166">なし。</span><span class="sxs-lookup"><span data-stu-id="80fac-166">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="80fac-167">親要素</span><span class="sxs-lookup"><span data-stu-id="80fac-167">Parent Elements</span></span>  
  
|<span data-ttu-id="80fac-168">要素</span><span class="sxs-lookup"><span data-stu-id="80fac-168">Element</span></span>|<span data-ttu-id="80fac-169">説明</span><span class="sxs-lookup"><span data-stu-id="80fac-169">Description</span></span>|  
|-------------|-----------------|  
|[\<clientCertificate>](clientcertificate-of-servicecredentials.md)|<span data-ttu-id="80fac-170">サービスに対するクライアントの認証に使用する X.509 証明書を定義します。</span><span class="sxs-lookup"><span data-stu-id="80fac-170">Defines an X.509 certificate used to authenticate a client to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="80fac-171">解説</span><span class="sxs-lookup"><span data-stu-id="80fac-171">Remarks</span></span>  

 <span data-ttu-id="80fac-172">`<authentication>` 要素は、<xref:System.ServiceModel.Security.X509ClientCertificateAuthentication> クラスに対応します。</span><span class="sxs-lookup"><span data-stu-id="80fac-172">The `<authentication>` element corresponds to the <xref:System.ServiceModel.Security.X509ClientCertificateAuthentication> class.</span></span> <span data-ttu-id="80fac-173">この要素を使用すると、クライアントを認証する方法をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="80fac-173">It enables you to customize how clients are authenticated.</span></span> <span data-ttu-id="80fac-174">`certificateValidationMode` 属性は、`None`、`ChainTrust`、`PeerOrChainTrust`、`PeerTrust`、または `Custom` に設定できます。</span><span class="sxs-lookup"><span data-stu-id="80fac-174">You can set the `certificateValidationMode` attribute to `None`, `ChainTrust`, `PeerOrChainTrust`, `PeerTrust`, or `Custom`.</span></span> <span data-ttu-id="80fac-175">既定では、レベルはに設定されています `ChainTrust` 。これは、チェーンの最上位にあるルート証明 *機関* で終了する証明書の階層構造で各証明書を検索する必要があることを指定します。</span><span class="sxs-lookup"><span data-stu-id="80fac-175">By default, the level is set to `ChainTrust`, which specifies that each certificate must be found in a hierarchy of certificates ending in a *root authority* at the top of the chain.</span></span> <span data-ttu-id="80fac-176">これは最もセキュリティで保護されているモードです。</span><span class="sxs-lookup"><span data-stu-id="80fac-176">This is the most secure mode.</span></span> <span data-ttu-id="80fac-177">また、値を `PeerOrChainTrust` に設定することもできます。これは、信頼されたチェーン内の証明書と共に、自己発行された証明書 (ピア信頼) も受け入れるよう指定します。</span><span class="sxs-lookup"><span data-stu-id="80fac-177">You can also set the value to `PeerOrChainTrust`, which specifies that self-issued certificates (peer trust) are accepted as well as certificates that are in a trusted chain.</span></span> <span data-ttu-id="80fac-178">自己発行の資格情報は信頼された証明機関から購入したものである必要はないため、この値はクライアントとサービスの開発およびデバッグに使用されます。</span><span class="sxs-lookup"><span data-stu-id="80fac-178">This value is used when developing and debugging clients and services because self-issued certificates need not be purchased from a trusted authority.</span></span> <span data-ttu-id="80fac-179">クライアントを展開するときは、代わりに `ChainTrust` 値を使用します。</span><span class="sxs-lookup"><span data-stu-id="80fac-179">When deploying a client, use the `ChainTrust` value instead.</span></span>  
  
 <span data-ttu-id="80fac-180">また、値を `Custom` に設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="80fac-180">You can also set the value to `Custom`.</span></span> <span data-ttu-id="80fac-181">`Custom` 値に設定する場合は、`customCertificateValidatorType` 属性を、証明書の検証に使用するアセンブリと型に設定する必要もあります。</span><span class="sxs-lookup"><span data-stu-id="80fac-181">When set to the `Custom` value, you must also set the `customCertificateValidatorType` attribute to an assembly and type used to validate the certificate.</span></span> <span data-ttu-id="80fac-182">独自のカスタム検証を作成するには、抽象 <xref:System.IdentityModel.Selectors.X509CertificateValidator> クラスを継承する必要があります。</span><span class="sxs-lookup"><span data-stu-id="80fac-182">To create your own custom validator, you must inherit from the abstract <xref:System.IdentityModel.Selectors.X509CertificateValidator> class.</span></span> <span data-ttu-id="80fac-183">詳細については、「 [方法: カスタム証明書検証を使用するサービスを作成](../../../wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="80fac-183">For more information, see [How to: Create a Service that Employs a Custom Certificate Validator](../../../wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="80fac-184">例</span><span class="sxs-lookup"><span data-stu-id="80fac-184">Example</span></span>  

 <span data-ttu-id="80fac-185">次のコードは、`<authentication>` 要素の X.509 証明書とカスタム検証タイプを指定します。</span><span class="sxs-lookup"><span data-stu-id="80fac-185">The following code specifies an X.509 certificate and a custom validation type in the `<authentication>` element.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="80fac-186">関連項目</span><span class="sxs-lookup"><span data-stu-id="80fac-186">See also</span></span>

- <xref:System.ServiceModel.Security.X509ClientCertificateAuthentication>
- <xref:System.ServiceModel.Security.X509CertificateValidationMode>
- <xref:System.ServiceModel.Security.X509CertificateInitiatorServiceCredential.Authentication%2A>
- <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement.Authentication%2A>
- <xref:System.ServiceModel.Configuration.X509ClientCertificateAuthenticationElement>
- [<span data-ttu-id="80fac-187">セキュリティ動作</span><span class="sxs-lookup"><span data-stu-id="80fac-187">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="80fac-188">方法: カスタム証明書検証を使用するサービスを作成する</span><span class="sxs-lookup"><span data-stu-id="80fac-188">How to: Create a Service that Employs a Custom Certificate Validator</span></span>](../../../wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md)
- [<span data-ttu-id="80fac-189">証明書の使用</span><span class="sxs-lookup"><span data-stu-id="80fac-189">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
