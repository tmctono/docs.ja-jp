---
title: <issuerTokenResolver>
ms.date: 03/30/2017
ms.assetid: f74392f6-3f5b-4880-bd8a-3a9130d31e65
author: BrucePerlerMS
ms.openlocfilehash: 08082d2e6647f07f33df72ab79dac00c15a1cd1b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61791613"
---
# <a name="issuertokenresolver"></a><span data-ttu-id="3fd66-101">\<issuerTokenResolver ></span><span class="sxs-lookup"><span data-stu-id="3fd66-101">\<issuerTokenResolver></span></span>
<span data-ttu-id="3fd66-102">トークン ハンドラー コレクションのハンドラーによって使用される発行者トークン リゾルバーを登録します。</span><span class="sxs-lookup"><span data-stu-id="3fd66-102">Registers the issuer token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="3fd66-103">発行者トークン リゾルバーを使用して、受信トークンおよびメッセージの署名トークンを解決します。</span><span class="sxs-lookup"><span data-stu-id="3fd66-103">The issuer token resolver is used to resolve the signing token on incoming tokens and messages.</span></span>  
  
 <span data-ttu-id="3fd66-104">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="3fd66-104">\<system.identityModel></span></span>  
<span data-ttu-id="3fd66-105">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="3fd66-105">\<identityConfiguration></span></span>  
<span data-ttu-id="3fd66-106">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="3fd66-106">\<securityTokenHandlers></span></span>  
<span data-ttu-id="3fd66-107">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="3fd66-107">\<securityTokenHandlerConfiguration></span></span>  
<span data-ttu-id="3fd66-108">\<issuerTokenResolver ></span><span class="sxs-lookup"><span data-stu-id="3fd66-108">\<issuerTokenResolver></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3fd66-109">構文</span><span class="sxs-lookup"><span data-stu-id="3fd66-109">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <securityTokenHandlerConfiguration>  
        <issuerTokenResolver type=xs:string>  
        </issuerTokenResolver>  
      </securityTokenHandlerConfiguration>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3fd66-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="3fd66-110">Attributes and Elements</span></span>  
 <span data-ttu-id="3fd66-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="3fd66-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3fd66-112">属性</span><span class="sxs-lookup"><span data-stu-id="3fd66-112">Attributes</span></span>  
  
|<span data-ttu-id="3fd66-113">属性</span><span class="sxs-lookup"><span data-stu-id="3fd66-113">Attribute</span></span>|<span data-ttu-id="3fd66-114">説明</span><span class="sxs-lookup"><span data-stu-id="3fd66-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3fd66-115">種類</span><span class="sxs-lookup"><span data-stu-id="3fd66-115">type</span></span>|<span data-ttu-id="3fd66-116">発行者トークン リゾルバーの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="3fd66-116">Specifies the type of the issuer token resolver.</span></span> <span data-ttu-id="3fd66-117">いずれかである必要があります、<xref:System.IdentityModel.Tokens.IssuerTokenResolver>クラスまたは型から派生した、<xref:System.IdentityModel.Tokens.IssuerTokenResolver>クラス。</span><span class="sxs-lookup"><span data-stu-id="3fd66-117">Must be either the <xref:System.IdentityModel.Tokens.IssuerTokenResolver> class or a type that derives from the <xref:System.IdentityModel.Tokens.IssuerTokenResolver> class.</span></span> <span data-ttu-id="3fd66-118">必須。</span><span class="sxs-lookup"><span data-stu-id="3fd66-118">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3fd66-119">子要素</span><span class="sxs-lookup"><span data-stu-id="3fd66-119">Child Elements</span></span>  
 <span data-ttu-id="3fd66-120">なし</span><span class="sxs-lookup"><span data-stu-id="3fd66-120">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3fd66-121">親要素</span><span class="sxs-lookup"><span data-stu-id="3fd66-121">Parent Elements</span></span>  
  
|<span data-ttu-id="3fd66-122">要素</span><span class="sxs-lookup"><span data-stu-id="3fd66-122">Element</span></span>|<span data-ttu-id="3fd66-123">説明</span><span class="sxs-lookup"><span data-stu-id="3fd66-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3fd66-124">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="3fd66-124">\<securityTokenHandlerConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|<span data-ttu-id="3fd66-125">トークン ハンドラー コレクションのセキュリティの構成を提供します。</span><span class="sxs-lookup"><span data-stu-id="3fd66-125">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3fd66-126">Remarks</span><span class="sxs-lookup"><span data-stu-id="3fd66-126">Remarks</span></span>  
 <span data-ttu-id="3fd66-127">発行者トークン リゾルバーを使用して、受信トークンおよびメッセージの署名トークンを解決します。</span><span class="sxs-lookup"><span data-stu-id="3fd66-127">The issuer token resolver is used to resolve the signing token on incoming tokens and messages.</span></span> <span data-ttu-id="3fd66-128">これを使用して、署名を確認するために使用される暗号化マテリアルを取得します。</span><span class="sxs-lookup"><span data-stu-id="3fd66-128">It is used to retrieve the cryptographic material that is used for checking the signature.</span></span> <span data-ttu-id="3fd66-129">指定する必要があります、`type`属性。</span><span class="sxs-lookup"><span data-stu-id="3fd66-129">You must specify the `type` attribute.</span></span> <span data-ttu-id="3fd66-130">指定された型には、いずれかを指定できる<xref:System.IdentityModel.Tokens.IssuerTokenResolver>またはカスタム型から派生した、<xref:System.IdentityModel.Tokens.IssuerTokenResolver>クラス。</span><span class="sxs-lookup"><span data-stu-id="3fd66-130">The type specified can be either <xref:System.IdentityModel.Tokens.IssuerTokenResolver> or a custom type that derives from the <xref:System.IdentityModel.Tokens.IssuerTokenResolver> class.</span></span>  
  
 <span data-ttu-id="3fd66-131">いくつかのトークン ハンドラーを使用すると、発行者トークン リゾルバーの設定を構成で指定できます。</span><span class="sxs-lookup"><span data-stu-id="3fd66-131">Some token handlers allow you to specify issuer token resolver settings in configuration.</span></span> <span data-ttu-id="3fd66-132">セキュリティ トークン ハンドラー コレクションの指定された個々 のトークン ハンドラーの設定をオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="3fd66-132">Settings on individual token handlers override those specified on the security token handler collection.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3fd66-133">指定する、`<issuerTokenResolver>`要素の子要素として、 [ \<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)要素は非推奨とされましたが、旧バージョンとの互換性もサポートします。</span><span class="sxs-lookup"><span data-stu-id="3fd66-133">Specifying the `<issuerTokenResolver>` element as a child element of the [\<identityConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) element has been deprecated, but is still supported for backward compatibility.</span></span> <span data-ttu-id="3fd66-134">上の設定、`<securityTokenHandlerConfiguration>`要素のオーバーライド、`<identityConfiguration>`要素。</span><span class="sxs-lookup"><span data-stu-id="3fd66-134">Settings on the `<securityTokenHandlerConfiguration>` element override those on the `<identityConfiguration>` element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3fd66-135">例</span><span class="sxs-lookup"><span data-stu-id="3fd66-135">Example</span></span>  
 <span data-ttu-id="3fd66-136">次の XML から派生したカスタム クラスに基づいている発行者トークン リゾルバーの構成を表示する<xref:System.IdentityModel.Tokens.IssuerTokenResolver>します。</span><span class="sxs-lookup"><span data-stu-id="3fd66-136">The following XML shows configuration for an issuer token resolver that is based on a custom class that derives from <xref:System.IdentityModel.Tokens.IssuerTokenResolver>.</span></span> <span data-ttu-id="3fd66-137">トークン リゾルバーは、カスタム構成要素から初期化された対象ユーザー キーのペアのディクショナリを保持 (`<AddAudienceKeyPair>`) クラスに対して定義されています。</span><span class="sxs-lookup"><span data-stu-id="3fd66-137">The token resolver maintains a dictionary of audience-key pairs that is initialized from a custom configuration element (`<AddAudienceKeyPair>`) defined for the class.</span></span> <span data-ttu-id="3fd66-138">クラスのオーバーライド、<xref:System.IdentityModel.Selectors.SecurityTokenResolver.LoadCustomConfiguration%2A>この要素を処理するメソッド。</span><span class="sxs-lookup"><span data-stu-id="3fd66-138">The class overrides the <xref:System.IdentityModel.Selectors.SecurityTokenResolver.LoadCustomConfiguration%2A> method to process this element.</span></span> <span data-ttu-id="3fd66-139">次の例で、上書きを表示します。ただし、呼び出すメソッドは、簡潔にするためには表示されません。</span><span class="sxs-lookup"><span data-stu-id="3fd66-139">The override is shown in the following example; however, the methods it calls are not shown for brevity.</span></span> <span data-ttu-id="3fd66-140">完全な例では、次を参照してください。、`CustomToken`サンプル。</span><span class="sxs-lookup"><span data-stu-id="3fd66-140">For the complete example, see the `CustomToken` sample.</span></span>  
  
```xml  
<issuerTokenResolver type="SimpleWebToken.CustomIssuerTokenResolver, SimpleWebToken">  
  <AddAudienceKeyPair  symmetricKey="wAVkldQiFypTQ+kdNdGWCYCHRcee8XmXxOvgmak8vSY=" audience="http://localhost:19851/" />  
</issuerTokenResolver>  
```  
  
## <a name="example"></a><span data-ttu-id="3fd66-141">例</span><span class="sxs-lookup"><span data-stu-id="3fd66-141">Example</span></span>  
  
```  
public override void LoadCustomConfiguration(System.Xml.XmlNodeList nodelist)  
{  
    foreach (XmlNode node in nodelist)  
    {  
        XmlDictionaryReader rdr = XmlDictionaryReader.CreateDictionaryReader(new XmlTextReader(new StringReader(node.OuterXml)));  
        rdr.MoveToContent();  
  
        string symmetricKey = rdr.GetAttribute("symmetricKey");  
        string audience = rdr.GetAttribute("audience");  
  
        this.AddAudienceKeyPair(audience, symmetricKey);  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="3fd66-142">関連項目</span><span class="sxs-lookup"><span data-stu-id="3fd66-142">See also</span></span>

- <xref:System.IdentityModel.Tokens.IssuerTokenResolver>
