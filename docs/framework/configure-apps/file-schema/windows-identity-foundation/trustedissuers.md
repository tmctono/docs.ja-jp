---
title: <trustedIssuers>
ms.date: 03/30/2017
ms.assetid: d818c917-07b4-40db-9801-8676561859fd
author: BrucePerlerMS
ms.openlocfilehash: 32aad3529ded6d0234b1bcb388ecbbc3b0a11c87
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69944273"
---
# <a name="trustedissuers"></a><span data-ttu-id="32b54-101">\<trustedIssuers ></span><span class="sxs-lookup"><span data-stu-id="32b54-101">\<trustedIssuers></span></span>
<span data-ttu-id="32b54-102">構成ベースの発行者名レジストリ (<xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>) によって使用される、信頼された発行者の証明書の一覧を構成します。</span><span class="sxs-lookup"><span data-stu-id="32b54-102">Configures the list of trusted issuer certificates used by the configuration-based issuer name registry (<xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>).</span></span>  
  
 <span data-ttu-id="32b54-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="32b54-103">\<system.identityModel></span></span>  
<span data-ttu-id="32b54-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="32b54-104">\<identityConfiguration></span></span>  
<span data-ttu-id="32b54-105">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="32b54-105">\<securityTokenHandlers></span></span>  
<span data-ttu-id="32b54-106">\<securityTokenHandlerConfiguration ></span><span class="sxs-lookup"><span data-stu-id="32b54-106">\<securityTokenHandlerConfiguration></span></span>  
<span data-ttu-id="32b54-107">\<issuerNameRegistry ></span><span class="sxs-lookup"><span data-stu-id="32b54-107">\<issuerNameRegistry></span></span>  
<span data-ttu-id="32b54-108">\<trustedIssuers ></span><span class="sxs-lookup"><span data-stu-id="32b54-108">\<trustedIssuers></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="32b54-109">構文</span><span class="sxs-lookup"><span data-stu-id="32b54-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="32b54-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="32b54-110">Attributes and Elements</span></span>  
 <span data-ttu-id="32b54-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="32b54-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="32b54-112">属性</span><span class="sxs-lookup"><span data-stu-id="32b54-112">Attributes</span></span>  
 <span data-ttu-id="32b54-113">なし</span><span class="sxs-lookup"><span data-stu-id="32b54-113">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="32b54-114">子要素</span><span class="sxs-lookup"><span data-stu-id="32b54-114">Child Elements</span></span>  
  
|<span data-ttu-id="32b54-115">要素</span><span class="sxs-lookup"><span data-stu-id="32b54-115">Element</span></span>|<span data-ttu-id="32b54-116">説明</span><span class="sxs-lookup"><span data-stu-id="32b54-116">Description</span></span>|  
|-------------|-----------------|  
|`<add thumbprint=xs:string name=xs:string>`|<span data-ttu-id="32b54-117">信頼された発行者のコレクションに証明書を追加します。</span><span class="sxs-lookup"><span data-stu-id="32b54-117">Adds a certificate to the collection of trusted issuers.</span></span> <span data-ttu-id="32b54-118">証明書は`thumbprint`属性で指定されます。</span><span class="sxs-lookup"><span data-stu-id="32b54-118">The certificate is specified with the `thumbprint` attribute.</span></span> <span data-ttu-id="32b54-119">この属性は必須であり、証明書の拇印の asn.1 エンコード形式を含んでいる必要があります。</span><span class="sxs-lookup"><span data-stu-id="32b54-119">This attribute is required and should contain the ASN.1 encoded form of the certificate thumbprint.</span></span> <span data-ttu-id="32b54-120">`name`属性は省略可能で、証明書のフレンドリ名を指定するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="32b54-120">The `name` attribute is optional and can be used to specify a friendly name for the certificate.</span></span>|  
|`<clear>`|<span data-ttu-id="32b54-121">信頼された発行者のコレクションからすべての証明書を削除します。</span><span class="sxs-lookup"><span data-stu-id="32b54-121">Clears all certificates from the collection of trusted issuers.</span></span>|  
|`<remove thumbprint=xs:string>`|<span data-ttu-id="32b54-122">信頼された発行者のコレクションから証明書を削除します。</span><span class="sxs-lookup"><span data-stu-id="32b54-122">Removes a certificate from the collection of trusted issuers.</span></span> <span data-ttu-id="32b54-123">証明書は`thumbprint`属性で指定されます。</span><span class="sxs-lookup"><span data-stu-id="32b54-123">The certificate is specified with the `thumbprint` attribute.</span></span> <span data-ttu-id="32b54-124">この属性は必須です。</span><span class="sxs-lookup"><span data-stu-id="32b54-124">This attribute is required.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="32b54-125">親要素</span><span class="sxs-lookup"><span data-stu-id="32b54-125">Parent Elements</span></span>  
  
|<span data-ttu-id="32b54-126">要素</span><span class="sxs-lookup"><span data-stu-id="32b54-126">Element</span></span>|<span data-ttu-id="32b54-127">説明</span><span class="sxs-lookup"><span data-stu-id="32b54-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="32b54-128">\<issuerNameRegistry ></span><span class="sxs-lookup"><span data-stu-id="32b54-128">\<issuerNameRegistry></span></span>](issuernameregistry.md)|<span data-ttu-id="32b54-129">発行者名レジストリを構成します。</span><span class="sxs-lookup"><span data-stu-id="32b54-129">Configures the issuer name registry.</span></span> <span data-ttu-id="32b54-130">**重要:** 要素`type` <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>の属性は、 `<trustedIssuers>`要素を有効にするためにクラスを参照する必要があります。 `<issuerNameRegistry>`</span><span class="sxs-lookup"><span data-stu-id="32b54-130">**Important:**  The `type` attribute of the `<issuerNameRegistry>` element must reference the <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> class for the `<trustedIssuers>` element to be valid.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="32b54-131">Remarks</span><span class="sxs-lookup"><span data-stu-id="32b54-131">Remarks</span></span>  
 <span data-ttu-id="32b54-132">Windows Identity Foundation (WIF) は、クラスの1つ<xref:System.IdentityModel.Tokens.IssuerNameRegistry>の実装を、 <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>クラスのすぐに使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="32b54-132">Windows Identity Foundation (WIF) provides a single implementation of the <xref:System.IdentityModel.Tokens.IssuerNameRegistry> class out of the box, the <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> class.</span></span> <span data-ttu-id="32b54-133">構成発行者名レジストリは、構成から読み込まれる信頼された発行者の一覧を保持します。</span><span class="sxs-lookup"><span data-stu-id="32b54-133">The configuration issuer name registry maintains a list of trusted issuers that is loaded from configuration.</span></span> <span data-ttu-id="32b54-134">リストでは、発行者によって生成されたトークンの署名を検証するために必要な x.509 証明書に各発行者名が関連付けられます。</span><span class="sxs-lookup"><span data-stu-id="32b54-134">The list associates each issuer name with the X.509 certificate that is needed to verify the signature of tokens produced by the issuer.</span></span> <span data-ttu-id="32b54-135">信頼された発行者の証明書の`<trustedIssuers>`一覧は、要素の下で指定されます。</span><span class="sxs-lookup"><span data-stu-id="32b54-135">The list of trusted issuer certificates is specified under the `<trustedIssuers>` element.</span></span> <span data-ttu-id="32b54-136">リスト内の各要素は、ニーモニック発行者名と、その発行者によって生成されるトークンの署名を検証するために必要な x.509 証明書を関連付けます。</span><span class="sxs-lookup"><span data-stu-id="32b54-136">Each element in the list associates a mnemonic issuer name with the X.509 certificate that is needed to verify the signature of tokens produced by that issuer.</span></span> <span data-ttu-id="32b54-137">信頼された証明書は、asn.1 エンコード形式の証明書の拇印を使用して指定さ`<add>`れ、要素を使用してコレクションに追加されます。</span><span class="sxs-lookup"><span data-stu-id="32b54-137">Trusted certificates are specified using the ASN.1 encoded form of the certificate thumbprint and are added the collection by using `<add>` element.</span></span> <span data-ttu-id="32b54-138">要素`<clear>` と`<remove>`要素を使用して、一覧から発行者 (証明書) を消去または削除できます。</span><span class="sxs-lookup"><span data-stu-id="32b54-138">You can clear or remove issuers (certificates) from the list by using the `<clear>` and `<remove>` elements.</span></span>  
  
 <span data-ttu-id="32b54-139">要素`type` <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>の属性は、 `<trustedIssuers>`要素を有効にするためにクラスを参照する必要があります。 `<issuerNameRegistry>`</span><span class="sxs-lookup"><span data-stu-id="32b54-139">The `type` attribute of the `<issuerNameRegistry>` element must reference the <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> class for the `<trustedIssuers>` element to be valid.</span></span>  
  
## <a name="example"></a><span data-ttu-id="32b54-140">例</span><span class="sxs-lookup"><span data-stu-id="32b54-140">Example</span></span>  
 <span data-ttu-id="32b54-141">次の XML は、構成ベースの発行者名レジストリを指定する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="32b54-141">The following XML shows how to specify the configuration based issuer name registry.</span></span>  
  
```xml  
<issuerNameRegistry type="System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">  
  <trustedIssuers>  
    <add thumbprint="9B74CB2F32 … B1DC01EF40D0" name="LocalSTS" />  
  </trustedIssuers>  
</issuerNameRegistry>  
```  
  
## <a name="see-also"></a><span data-ttu-id="32b54-142">関連項目</span><span class="sxs-lookup"><span data-stu-id="32b54-142">See also</span></span>

- <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>
- <xref:System.IdentityModel.Tokens.IssuerNameRegistry>
