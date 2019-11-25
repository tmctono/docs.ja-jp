---
title: <issuerTokenResolver>
ms.date: 03/30/2017
ms.assetid: f74392f6-3f5b-4880-bd8a-3a9130d31e65
author: BrucePerlerMS
ms.openlocfilehash: 451750a1facd9a886b53427a8d54580d1a939fa5
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/12/2019
ms.locfileid: "73968505"
---
# <a name="issuertokenresolver"></a><span data-ttu-id="e5995-101">\<issuerTokenResolver ></span><span class="sxs-lookup"><span data-stu-id="e5995-101">\<issuerTokenResolver></span></span>
<span data-ttu-id="e5995-102">トークンハンドラーコレクションのハンドラーによって使用される発行者トークンリゾルバーを登録します。</span><span class="sxs-lookup"><span data-stu-id="e5995-102">Registers the issuer token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="e5995-103">発行者トークンリゾルバーは、受信トークンとメッセージの署名トークンを解決するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="e5995-103">The issuer token resolver is used to resolve the signing token on incoming tokens and messages.</span></span>  
  
<span data-ttu-id="e5995-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="e5995-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="e5995-105">&nbsp;&nbsp;[ **\<** ](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="e5995-105">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="e5995-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<の構成 >** ](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="e5995-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="e5995-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**securityTokenHandlers >** ](securitytokenhandlers.md)</span><span class="sxs-lookup"><span data-stu-id="e5995-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)</span></span>\
<span data-ttu-id="e5995-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<securityTokenHandlerConfiguration >** ](securitytokenhandlerconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="e5995-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlerConfiguration>**](securitytokenhandlerconfiguration.md)</span></span>\
<span data-ttu-id="e5995-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**issuerTokenResolver >**</span><span class="sxs-lookup"><span data-stu-id="e5995-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<issuerTokenResolver>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e5995-110">構文</span><span class="sxs-lookup"><span data-stu-id="e5995-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e5995-111">属性および要素</span><span class="sxs-lookup"><span data-stu-id="e5995-111">Attributes and Elements</span></span>  
 <span data-ttu-id="e5995-112">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="e5995-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e5995-113">属性</span><span class="sxs-lookup"><span data-stu-id="e5995-113">Attributes</span></span>  
  
|<span data-ttu-id="e5995-114">属性</span><span class="sxs-lookup"><span data-stu-id="e5995-114">Attribute</span></span>|<span data-ttu-id="e5995-115">説明</span><span class="sxs-lookup"><span data-stu-id="e5995-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e5995-116">type</span><span class="sxs-lookup"><span data-stu-id="e5995-116">type</span></span>|<span data-ttu-id="e5995-117">発行者トークンリゾルバーの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="e5995-117">Specifies the type of the issuer token resolver.</span></span> <span data-ttu-id="e5995-118"><xref:System.IdentityModel.Tokens.IssuerTokenResolver> クラスであるか、または <xref:System.IdentityModel.Tokens.IssuerTokenResolver> クラスから派生した型である必要があります。</span><span class="sxs-lookup"><span data-stu-id="e5995-118">Must be either the <xref:System.IdentityModel.Tokens.IssuerTokenResolver> class or a type that derives from the <xref:System.IdentityModel.Tokens.IssuerTokenResolver> class.</span></span> <span data-ttu-id="e5995-119">必須です。</span><span class="sxs-lookup"><span data-stu-id="e5995-119">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e5995-120">子要素</span><span class="sxs-lookup"><span data-stu-id="e5995-120">Child Elements</span></span>  
 <span data-ttu-id="e5995-121">None</span><span class="sxs-lookup"><span data-stu-id="e5995-121">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e5995-122">親要素</span><span class="sxs-lookup"><span data-stu-id="e5995-122">Parent Elements</span></span>  
  
|<span data-ttu-id="e5995-123">要素</span><span class="sxs-lookup"><span data-stu-id="e5995-123">Element</span></span>|<span data-ttu-id="e5995-124">説明</span><span class="sxs-lookup"><span data-stu-id="e5995-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e5995-125">\<securityTokenHandlerConfiguration ></span><span class="sxs-lookup"><span data-stu-id="e5995-125">\<securityTokenHandlerConfiguration></span></span>](securitytokenhandlerconfiguration.md)|<span data-ttu-id="e5995-126">セキュリティトークンハンドラーのコレクションの構成を提供します。</span><span class="sxs-lookup"><span data-stu-id="e5995-126">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e5995-127">Remarks</span><span class="sxs-lookup"><span data-stu-id="e5995-127">Remarks</span></span>  
 <span data-ttu-id="e5995-128">発行者トークンリゾルバーは、受信トークンとメッセージの署名トークンを解決するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="e5995-128">The issuer token resolver is used to resolve the signing token on incoming tokens and messages.</span></span> <span data-ttu-id="e5995-129">署名の確認に使用される暗号化マテリアルを取得するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="e5995-129">It is used to retrieve the cryptographic material that is used for checking the signature.</span></span> <span data-ttu-id="e5995-130">`type` 属性を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e5995-130">You must specify the `type` attribute.</span></span> <span data-ttu-id="e5995-131">指定する型は <xref:System.IdentityModel.Tokens.IssuerTokenResolver> か、または <xref:System.IdentityModel.Tokens.IssuerTokenResolver> クラスから派生したカスタム型にすることができます。</span><span class="sxs-lookup"><span data-stu-id="e5995-131">The type specified can be either <xref:System.IdentityModel.Tokens.IssuerTokenResolver> or a custom type that derives from the <xref:System.IdentityModel.Tokens.IssuerTokenResolver> class.</span></span>  
  
 <span data-ttu-id="e5995-132">一部のトークンハンドラーでは、構成で発行者トークンリゾルバーの設定を指定できます。</span><span class="sxs-lookup"><span data-stu-id="e5995-132">Some token handlers allow you to specify issuer token resolver settings in configuration.</span></span> <span data-ttu-id="e5995-133">個々のトークンハンドラーの設定は、セキュリティトークンハンドラーコレクションで指定された設定よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="e5995-133">Settings on individual token handlers override those specified on the security token handler collection.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e5995-134">`<issuerTokenResolver>` 要素を\<の [identity [configuration >](identityconfiguration.md)要素の子要素として指定することは非推奨とされていますが、旧バージョンとの互換性のために引き続きサポートされています。</span><span class="sxs-lookup"><span data-stu-id="e5995-134">Specifying the `<issuerTokenResolver>` element as a child element of the [\<identityConfiguration>](identityconfiguration.md) element has been deprecated, but is still supported for backward compatibility.</span></span> <span data-ttu-id="e5995-135">`<securityTokenHandlerConfiguration>` 要素の設定は、`<identityConfiguration>` 要素の設定よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="e5995-135">Settings on the `<securityTokenHandlerConfiguration>` element override those on the `<identityConfiguration>` element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e5995-136">例</span><span class="sxs-lookup"><span data-stu-id="e5995-136">Example</span></span>  
 <span data-ttu-id="e5995-137">次の XML は、<xref:System.IdentityModel.Tokens.IssuerTokenResolver>から派生したカスタムクラスに基づく発行者トークンリゾルバーの構成を示しています。</span><span class="sxs-lookup"><span data-stu-id="e5995-137">The following XML shows configuration for an issuer token resolver that is based on a custom class that derives from <xref:System.IdentityModel.Tokens.IssuerTokenResolver>.</span></span> <span data-ttu-id="e5995-138">トークンリゾルバーは、クラスに対して定義されたカスタム構成要素 (`<AddAudienceKeyPair>`) から初期化される、ユーザーとキーのペアのディクショナリを保持します。</span><span class="sxs-lookup"><span data-stu-id="e5995-138">The token resolver maintains a dictionary of audience-key pairs that is initialized from a custom configuration element (`<AddAudienceKeyPair>`) defined for the class.</span></span> <span data-ttu-id="e5995-139">クラスは、<xref:System.IdentityModel.Selectors.SecurityTokenResolver.LoadCustomConfiguration%2A> メソッドをオーバーライドして、この要素を処理します。</span><span class="sxs-lookup"><span data-stu-id="e5995-139">The class overrides the <xref:System.IdentityModel.Selectors.SecurityTokenResolver.LoadCustomConfiguration%2A> method to process this element.</span></span> <span data-ttu-id="e5995-140">オーバーライドを次の例に示します。ただし、簡潔にするために呼び出すメソッドは表示されません。</span><span class="sxs-lookup"><span data-stu-id="e5995-140">The override is shown in the following example; however, the methods it calls are not shown for brevity.</span></span> <span data-ttu-id="e5995-141">完全な例については、`CustomToken` のサンプルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e5995-141">For the complete example, see the `CustomToken` sample.</span></span>  
  
```xml  
<issuerTokenResolver type="SimpleWebToken.CustomIssuerTokenResolver, SimpleWebToken">  
  <AddAudienceKeyPair  symmetricKey="wAVkldQiFypTQ+kdNdGWCYCHRcee8XmXxOvgmak8vSY=" audience="http://localhost:19851/" />  
</issuerTokenResolver>  
```  
  
## <a name="example"></a><span data-ttu-id="e5995-142">例</span><span class="sxs-lookup"><span data-stu-id="e5995-142">Example</span></span>
  
```csharp
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
  
## <a name="see-also"></a><span data-ttu-id="e5995-143">関連項目</span><span class="sxs-lookup"><span data-stu-id="e5995-143">See also</span></span>

- <xref:System.IdentityModel.Tokens.IssuerTokenResolver>
