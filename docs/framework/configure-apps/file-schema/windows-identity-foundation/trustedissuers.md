---
title: <trustedIssuers>
ms.date: 03/30/2017
ms.assetid: d818c917-07b4-40db-9801-8676561859fd
author: BrucePerlerMS
ms.openlocfilehash: cebfc2f3598f32f233db6039dfe82076d2ffce46
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61790482"
---
# <a name="trustedissuers"></a><span data-ttu-id="86c75-101">\<trustedIssuers></span><span class="sxs-lookup"><span data-stu-id="86c75-101">\<trustedIssuers></span></span>
<span data-ttu-id="86c75-102">構成ベースの発行者名レジストリによって使用される信頼された発行者証明書の一覧を構成します (<xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>)。</span><span class="sxs-lookup"><span data-stu-id="86c75-102">Configures the list of trusted issuer certificates used by the configuration-based issuer name registry (<xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>).</span></span>  
  
 <span data-ttu-id="86c75-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="86c75-103">\<system.identityModel></span></span>  
<span data-ttu-id="86c75-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="86c75-104">\<identityConfiguration></span></span>  
<span data-ttu-id="86c75-105">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="86c75-105">\<securityTokenHandlers></span></span>  
<span data-ttu-id="86c75-106">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="86c75-106">\<securityTokenHandlerConfiguration></span></span>  
<span data-ttu-id="86c75-107">\<issuerNameRegistry></span><span class="sxs-lookup"><span data-stu-id="86c75-107">\<issuerNameRegistry></span></span>  
<span data-ttu-id="86c75-108">\<trustedIssuers></span><span class="sxs-lookup"><span data-stu-id="86c75-108">\<trustedIssuers></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="86c75-109">構文</span><span class="sxs-lookup"><span data-stu-id="86c75-109">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <securityTokenHandlerConfiguration>  
        <issuerNameRegistry>  
          <trustedIssuers>  
            <add thumbprint=xs:string name=xs:string>  
            <clear>  
            <remove thumbprint=xs:string>  
          </trustedIssuers>  
        </issuerNameRegistry>  
      </securityTokenHandlerConfiguration>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="86c75-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="86c75-110">Attributes and Elements</span></span>  
 <span data-ttu-id="86c75-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="86c75-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="86c75-112">属性</span><span class="sxs-lookup"><span data-stu-id="86c75-112">Attributes</span></span>  
 <span data-ttu-id="86c75-113">なし</span><span class="sxs-lookup"><span data-stu-id="86c75-113">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="86c75-114">子要素</span><span class="sxs-lookup"><span data-stu-id="86c75-114">Child Elements</span></span>  
  
|<span data-ttu-id="86c75-115">要素</span><span class="sxs-lookup"><span data-stu-id="86c75-115">Element</span></span>|<span data-ttu-id="86c75-116">説明</span><span class="sxs-lookup"><span data-stu-id="86c75-116">Description</span></span>|  
|-------------|-----------------|  
|`<add thumbprint=xs:string name=xs:string>`|<span data-ttu-id="86c75-117">証明書を信頼された発行者のコレクションに追加します。</span><span class="sxs-lookup"><span data-stu-id="86c75-117">Adds a certificate to the collection of trusted issuers.</span></span> <span data-ttu-id="86c75-118">証明書を指定した、`thumbprint`属性。</span><span class="sxs-lookup"><span data-stu-id="86c75-118">The certificate is specified with the `thumbprint` attribute.</span></span> <span data-ttu-id="86c75-119">この属性は必須であり、証明書のサムプリントの ASN.1 エンコードされたフォームを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="86c75-119">This attribute is required and should contain the ASN.1 encoded form of the certificate thumbprint.</span></span> <span data-ttu-id="86c75-120">`name`属性は省略可能と証明書のフレンドリ名を指定するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="86c75-120">The `name` attribute is optional and can be used to specify a friendly name for the certificate.</span></span>|  
|`<clear>`|<span data-ttu-id="86c75-121">信頼された発行者のコレクションからすべての証明書をクリアします。</span><span class="sxs-lookup"><span data-stu-id="86c75-121">Clears all certificates from the collection of trusted issuers.</span></span>|  
|`<remove thumbprint=xs:string>`|<span data-ttu-id="86c75-122">証明書を信頼された発行者のコレクションから削除します。</span><span class="sxs-lookup"><span data-stu-id="86c75-122">Removes a certificate from the collection of trusted issuers.</span></span> <span data-ttu-id="86c75-123">証明書を指定した、`thumbprint`属性。</span><span class="sxs-lookup"><span data-stu-id="86c75-123">The certificate is specified with the `thumbprint` attribute.</span></span> <span data-ttu-id="86c75-124">この属性は必須です。</span><span class="sxs-lookup"><span data-stu-id="86c75-124">This attribute is required.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="86c75-125">親要素</span><span class="sxs-lookup"><span data-stu-id="86c75-125">Parent Elements</span></span>  
  
|<span data-ttu-id="86c75-126">要素</span><span class="sxs-lookup"><span data-stu-id="86c75-126">Element</span></span>|<span data-ttu-id="86c75-127">説明</span><span class="sxs-lookup"><span data-stu-id="86c75-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="86c75-128">\<issuerNameRegistry></span><span class="sxs-lookup"><span data-stu-id="86c75-128">\<issuerNameRegistry></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/issuernameregistry.md)|<span data-ttu-id="86c75-129">発行者名レジストリを構成します。</span><span class="sxs-lookup"><span data-stu-id="86c75-129">Configures the issuer name registry.</span></span> <span data-ttu-id="86c75-130">**重要:** `type`の属性、`<issuerNameRegistry>`要素を参照する必要があります、<xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>クラス、`<trustedIssuers>`を有効にする要素。</span><span class="sxs-lookup"><span data-stu-id="86c75-130">**Important:**  The `type` attribute of the `<issuerNameRegistry>` element must reference the <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> class for the `<trustedIssuers>` element to be valid.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="86c75-131">Remarks</span><span class="sxs-lookup"><span data-stu-id="86c75-131">Remarks</span></span>  
 <span data-ttu-id="86c75-132">Windows Identity Foundation (WIF) の単一の実装を提供する、<xref:System.IdentityModel.Tokens.IssuerNameRegistry>すぐに使えるクラス、<xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>クラス。</span><span class="sxs-lookup"><span data-stu-id="86c75-132">Windows Identity Foundation (WIF) provides a single implementation of the <xref:System.IdentityModel.Tokens.IssuerNameRegistry> class out of the box, the <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> class.</span></span> <span data-ttu-id="86c75-133">構成の発行者名レジストリは、構成から読み込まれる信頼された発行者の一覧を保持します。</span><span class="sxs-lookup"><span data-stu-id="86c75-133">The configuration issuer name registry maintains a list of trusted issuers that is loaded from configuration.</span></span> <span data-ttu-id="86c75-134">一覧は、各発行者名を発行者によって生成されたトークンの署名を検証するために必要な X.509 証明書に関連付けます。</span><span class="sxs-lookup"><span data-stu-id="86c75-134">The list associates each issuer name with the X.509 certificate that is needed to verify the signature of tokens produced by the issuer.</span></span> <span data-ttu-id="86c75-135">信頼された発行者の証明書の一覧が指定されて、`<trustedIssuers>`要素。</span><span class="sxs-lookup"><span data-stu-id="86c75-135">The list of trusted issuer certificates is specified under the `<trustedIssuers>` element.</span></span> <span data-ttu-id="86c75-136">リスト内の各要素は、その発行者によって生成されたトークンの署名を検証するために必要な X.509 証明書をニーモニックの発行者名を関連付けます。</span><span class="sxs-lookup"><span data-stu-id="86c75-136">Each element in the list associates a mnemonic issuer name with the X.509 certificate that is needed to verify the signature of tokens produced by that issuer.</span></span> <span data-ttu-id="86c75-137">信頼された証明書が証明書の拇印の形式でエンコードされた ASN.1 を使用して、指定され、を使用して、コレクションに追加されます`<add>`要素。</span><span class="sxs-lookup"><span data-stu-id="86c75-137">Trusted certificates are specified using the ASN.1 encoded form of the certificate thumbprint and are added the collection by using `<add>` element.</span></span> <span data-ttu-id="86c75-138">オフにしたり、発行者 (証明書) を使用して一覧から削除、`<clear>`と`<remove>`要素。</span><span class="sxs-lookup"><span data-stu-id="86c75-138">You can clear or remove issuers (certificates) from the list by using the `<clear>` and `<remove>` elements.</span></span>  
  
 <span data-ttu-id="86c75-139">`type`の属性、`<issuerNameRegistry>`要素を参照する必要があります、<xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>クラス、`<trustedIssuers>`を有効にする要素。</span><span class="sxs-lookup"><span data-stu-id="86c75-139">The `type` attribute of the `<issuerNameRegistry>` element must reference the <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> class for the `<trustedIssuers>` element to be valid.</span></span>  
  
## <a name="example"></a><span data-ttu-id="86c75-140">例</span><span class="sxs-lookup"><span data-stu-id="86c75-140">Example</span></span>  
 <span data-ttu-id="86c75-141">次の XML では、名前のレジストリをベースの構成の発行者を指定する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="86c75-141">The following XML shows how to specify the configuration based issuer name registry.</span></span>  
  
```xml  
<issuerNameRegistry type="System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">  
  <trustedIssuers>  
    <add thumbprint="9B74CB2F32 … B1DC01EF40D0" name="LocalSTS" />  
  </trustedIssuers>  
</issuerNameRegistry>  
```  
  
## <a name="see-also"></a><span data-ttu-id="86c75-142">関連項目</span><span class="sxs-lookup"><span data-stu-id="86c75-142">See also</span></span>

- <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>
- <xref:System.IdentityModel.Tokens.IssuerNameRegistry>
