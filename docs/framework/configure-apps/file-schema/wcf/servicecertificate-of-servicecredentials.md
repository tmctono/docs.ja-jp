---
title: <serviceCertificate> の <serviceCredentials>
ms.date: 03/30/2017
ms.assetid: 597ae6d5-4938-4950-9f5e-b2280e816182
ms.openlocfilehash: 936661595813d7b8f3e894efb7bf6cf3aab7e89e
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91167102"
---
# <a name="servicecertificate-of-servicecredentials"></a><span data-ttu-id="48fe3-102">\<serviceCertificate> の \<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="48fe3-102">\<serviceCertificate> of \<serviceCredentials></span></span>

<span data-ttu-id="48fe3-103">メッセージ セキュリティ モードを使用しているクライアントへのサービスの認証に使用する X.509 証明書を指定します。</span><span class="sxs-lookup"><span data-stu-id="48fe3-103">Specify an X.509 certificate that will be used to authenticate the service to clients using Message security mode.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCredentials>**](servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceCertificate>**  
  
## <a name="syntax"></a><span data-ttu-id="48fe3-104">構文</span><span class="sxs-lookup"><span data-stu-id="48fe3-104">Syntax</span></span>  
  
```xml  
<serviceCertificate findValue="String"
                    storeLocation="LocalMachine/CurrentUser"
                    storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
                    x509FindType="FindByThumbprint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="48fe3-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="48fe3-105">Attributes and Elements</span></span>  

 <span data-ttu-id="48fe3-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="48fe3-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="48fe3-107">属性</span><span class="sxs-lookup"><span data-stu-id="48fe3-107">Attributes</span></span>  
  
|<span data-ttu-id="48fe3-108">属性</span><span class="sxs-lookup"><span data-stu-id="48fe3-108">Attribute</span></span>|<span data-ttu-id="48fe3-109">[説明]</span><span class="sxs-lookup"><span data-stu-id="48fe3-109">Description</span></span>|  
|---------------|-----------------|  
|`findValue`|<span data-ttu-id="48fe3-110">X.509 証明書ストアで検索する値を含む文字列。</span><span class="sxs-lookup"><span data-stu-id="48fe3-110">A string that contains the value to search for in the X.509 certificate store.</span></span> <span data-ttu-id="48fe3-111">属性に含まれている型は、指定された X509FindType の要件を満たしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="48fe3-111">The type contained in the attribute must satisfy the requirements of the specified X509FindType.</span></span> <span data-ttu-id="48fe3-112">既定値は空の文字列です。</span><span class="sxs-lookup"><span data-stu-id="48fe3-112">The default is an empty string.</span></span>|  
|`storeLocation`|<span data-ttu-id="48fe3-113">クライアントがサーバーの証明書の検証に使用する X.509 証明書ストアの場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="48fe3-113">Specifies the location of the X.509 certificate store that the client uses to validate the server’s certificate against.</span></span> <span data-ttu-id="48fe3-114">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="48fe3-114">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="48fe3-115">-LocalMachine: ローカルコンピューターに割り当てられた証明書ストア。</span><span class="sxs-lookup"><span data-stu-id="48fe3-115">-   LocalMachine: the certificate store assigned to the local machine.</span></span><br /><span data-ttu-id="48fe3-116">-CurrentUser: 現在のユーザーに割り当てられている証明書ストア。</span><span class="sxs-lookup"><span data-stu-id="48fe3-116">-   CurrentUser: the certificate store assigned to the current user.</span></span><br /><br /> <span data-ttu-id="48fe3-117">既定値は LocalMachine です。</span><span class="sxs-lookup"><span data-stu-id="48fe3-117">The default is LocalMachine.</span></span>|  
|`storeName`|<span data-ttu-id="48fe3-118">開く X.509 証明書ストアの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="48fe3-118">Specifies the name of the X.509 certificate store to open.</span></span> <span data-ttu-id="48fe3-119">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="48fe3-119">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="48fe3-120">-アドレス帳: 他のユーザーの証明書ストア。</span><span class="sxs-lookup"><span data-stu-id="48fe3-120">-   AddressBook: Certificate store for other users.</span></span><br /><span data-ttu-id="48fe3-121">-AuthRoot: サードパーティ証明機関 (Ca) の証明書ストア。</span><span class="sxs-lookup"><span data-stu-id="48fe3-121">-   AuthRoot: Certificate store for third-party certification authorities (CAs).</span></span><br /><span data-ttu-id="48fe3-122">-証明機関: 中間証明機関 (Ca) の証明書ストア。</span><span class="sxs-lookup"><span data-stu-id="48fe3-122">-   CertificatAuthority: Certificate store for intermediate certification authorities (CAs).</span></span><br /><span data-ttu-id="48fe3-123">-許可されていません: 失効した証明書の証明書ストア。</span><span class="sxs-lookup"><span data-stu-id="48fe3-123">-   Disallowed: Certificate store for revoked certificates.</span></span><br /><span data-ttu-id="48fe3-124">-My: 個人証明書の証明書ストア。</span><span class="sxs-lookup"><span data-stu-id="48fe3-124">-   My: Certificate store for personal certificates.</span></span><br /><span data-ttu-id="48fe3-125">-Root: 信頼されたルート証明機関 (Ca) の証明書ストア。</span><span class="sxs-lookup"><span data-stu-id="48fe3-125">-   Root: Certificate store for trusted root certification authorities (CAs).</span></span><br /><span data-ttu-id="48fe3-126">-TrustedPeople: 直接信頼されている人間とリソースの証明書ストア。</span><span class="sxs-lookup"><span data-stu-id="48fe3-126">-   TrustedPeople: Certificate store for directly trusted people and resources.</span></span><br /><span data-ttu-id="48fe3-127">-TrustedPublisher: 直接信頼された発行元の証明書ストア。</span><span class="sxs-lookup"><span data-stu-id="48fe3-127">-   TrustedPublisher: Certificate store for directly trusted publishers.</span></span><br /><br /> <span data-ttu-id="48fe3-128">既定値は My です。</span><span class="sxs-lookup"><span data-stu-id="48fe3-128">The default is My.</span></span>|  
|`x509FindType`|<span data-ttu-id="48fe3-129">実行する X.509 検索の種類を定義します。</span><span class="sxs-lookup"><span data-stu-id="48fe3-129">Defines the type of X.509 search to be executed.</span></span> <span data-ttu-id="48fe3-130">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="48fe3-130">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="48fe3-131">-FindByThumbprint</span><span class="sxs-lookup"><span data-stu-id="48fe3-131">-   FindByThumbprint</span></span><br /><span data-ttu-id="48fe3-132">-FindBySubjectName</span><span class="sxs-lookup"><span data-stu-id="48fe3-132">-   FindBySubjectName</span></span><br /><span data-ttu-id="48fe3-133">-Findbysubjectdistinguishedname です</span><span class="sxs-lookup"><span data-stu-id="48fe3-133">-   FindBySubjectDistinguishedName</span></span><br /><span data-ttu-id="48fe3-134">- FindByIssuerName</span><span class="sxs-lookup"><span data-stu-id="48fe3-134">-   FindByIssuerName</span></span><br /><span data-ttu-id="48fe3-135">- FindByIssuerDistinguishedName</span><span class="sxs-lookup"><span data-stu-id="48fe3-135">-   FindByIssuerDistinguishedName</span></span><br /><span data-ttu-id="48fe3-136">-FindBySerialNumber</span><span class="sxs-lookup"><span data-stu-id="48fe3-136">-   FindBySerialNumber</span></span><br /><span data-ttu-id="48fe3-137">- FindByTimeValid</span><span class="sxs-lookup"><span data-stu-id="48fe3-137">-   FindByTimeValid</span></span><br /><span data-ttu-id="48fe3-138">- FindByTimeNotYetValid</span><span class="sxs-lookup"><span data-stu-id="48fe3-138">-   FindByTimeNotYetValid</span></span><br /><span data-ttu-id="48fe3-139">- FindByTemplateName</span><span class="sxs-lookup"><span data-stu-id="48fe3-139">-   FindByTemplateName</span></span><br /><span data-ttu-id="48fe3-140">- FindByApplicationPolicy</span><span class="sxs-lookup"><span data-stu-id="48fe3-140">-   FindByApplicationPolicy</span></span><br /><span data-ttu-id="48fe3-141">- FindByCertificatePolicy</span><span class="sxs-lookup"><span data-stu-id="48fe3-141">-   FindByCertificatePolicy</span></span><br /><span data-ttu-id="48fe3-142">- FindByExtension</span><span class="sxs-lookup"><span data-stu-id="48fe3-142">-   FindByExtension</span></span><br /><span data-ttu-id="48fe3-143">- FindByKeyUsage</span><span class="sxs-lookup"><span data-stu-id="48fe3-143">-   FindByKeyUsage</span></span><br /><span data-ttu-id="48fe3-144">- FindBySubjectKeyIdentifier</span><span class="sxs-lookup"><span data-stu-id="48fe3-144">-   FindBySubjectKeyIdentifier</span></span><br /><br /> <span data-ttu-id="48fe3-145">`findValue` 属性に含まれている型は、指定された X509FindType の要件を満たしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="48fe3-145">The type contained in the `findValue` attribute must satisfy the requirements of the specified X509FindType.</span></span><br /><br /> <span data-ttu-id="48fe3-146">既定値は FindBySubjectDistinguishedName です。</span><span class="sxs-lookup"><span data-stu-id="48fe3-146">The default value is FindBySubjectDistinguishedName.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="48fe3-147">子要素</span><span class="sxs-lookup"><span data-stu-id="48fe3-147">Child Elements</span></span>  

 <span data-ttu-id="48fe3-148">None</span><span class="sxs-lookup"><span data-stu-id="48fe3-148">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="48fe3-149">親要素</span><span class="sxs-lookup"><span data-stu-id="48fe3-149">Parent Elements</span></span>  
  
|<span data-ttu-id="48fe3-150">要素</span><span class="sxs-lookup"><span data-stu-id="48fe3-150">Element</span></span>|<span data-ttu-id="48fe3-151">説明</span><span class="sxs-lookup"><span data-stu-id="48fe3-151">Description</span></span>|  
|-------------|-----------------|  
|[\<serviceCredentials>](servicecredentials.md)|<span data-ttu-id="48fe3-152">サービスの認証に使用される資格情報と、クライアントの資格情報検証関連の設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="48fe3-152">Specifies the credential to be used in authenticating the service, and the client credential validation related settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="48fe3-153">解説</span><span class="sxs-lookup"><span data-stu-id="48fe3-153">Remarks</span></span>  

 <span data-ttu-id="48fe3-154">メッセージ セキュリティ モードを使用しているクライアントへのサービスの認証に使用する X.509 証明書を指定するには、この要素を使用します。</span><span class="sxs-lookup"><span data-stu-id="48fe3-154">Use this element to specify an X.509 certificate that will be used to authenticate the service to clients using Message security mode.</span></span> <span data-ttu-id="48fe3-155">定期的に更新される証明書を使用している場合は、証明書のサムプリントが変更されます。</span><span class="sxs-lookup"><span data-stu-id="48fe3-155">If you are using a certificate that will be periodically renewed, then its thumbprint will change.</span></span> <span data-ttu-id="48fe3-156">その場合、証明書を同じサブジェクト名で再発行できるため、`x509FindType` としてサブジェクト名を使用します。</span><span class="sxs-lookup"><span data-stu-id="48fe3-156">In that case, use the subject name as the `x509FindType` because the certificate can be reissued with the same subject name.</span></span>  
  
 <span data-ttu-id="48fe3-157">要素の使用方法の詳細については、「 [方法: クライアント資格情報の値を指定する](../../../wcf/how-to-specify-client-credential-values.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="48fe3-157">For more information about using the element, see [How to: Specify Client Credential Values](../../../wcf/how-to-specify-client-credential-values.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48fe3-158">関連項目</span><span class="sxs-lookup"><span data-stu-id="48fe3-158">See also</span></span>

- <xref:System.ServiceModel.Configuration.X509RecipientCertificateServiceElement>
- <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.ServiceCertificate%2A>
- <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential>
- <xref:System.ServiceModel.Description.ServiceCredentials.ServiceCertificate%2A>
- [<span data-ttu-id="48fe3-159">方法: クライアントの資格情報の値を指定する</span><span class="sxs-lookup"><span data-stu-id="48fe3-159">How to: Specify Client Credential Values</span></span>](../../../wcf/how-to-specify-client-credential-values.md)
- [<span data-ttu-id="48fe3-160">セキュリティ動作</span><span class="sxs-lookup"><span data-stu-id="48fe3-160">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
