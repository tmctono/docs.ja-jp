---
title: <add>
ms.date: 03/30/2017
ms.assetid: 4712a888-f154-4395-8887-ef14a88a6497
author: BrucePerlerMS
ms.openlocfilehash: 83ba51cbbd5100bf7412f9914a270cac88f7faa1
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/12/2019
ms.locfileid: "73973802"
---
# <a name="add"></a><span data-ttu-id="b7563-101">\<add></span><span class="sxs-lookup"><span data-stu-id="b7563-101">\<add></span></span>
<span data-ttu-id="b7563-102">指定されたセキュリティトークンハンドラーをトークンハンドラーコレクションに追加します。</span><span class="sxs-lookup"><span data-stu-id="b7563-102">Adds the specified security token handler to the token handler collection.</span></span>  
  
<span data-ttu-id="b7563-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="b7563-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="b7563-104">&nbsp;&nbsp;[ **\<** ](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="b7563-104">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="b7563-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<の構成 >** ](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="b7563-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="b7563-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**securityTokenHandlers >** ](securitytokenhandlers.md)</span><span class="sxs-lookup"><span data-stu-id="b7563-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)</span></span>\
<span data-ttu-id="b7563-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**追加 >**</span><span class="sxs-lookup"><span data-stu-id="b7563-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b7563-108">構文</span><span class="sxs-lookup"><span data-stu-id="b7563-108">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <add type=xs:string>  
        <optionalConfigurationElement>  
        </optionalConfigurationElement>  
      </add>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b7563-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="b7563-109">Attributes and Elements</span></span>  
 <span data-ttu-id="b7563-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="b7563-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b7563-111">属性</span><span class="sxs-lookup"><span data-stu-id="b7563-111">Attributes</span></span>  
  
|<span data-ttu-id="b7563-112">属性</span><span class="sxs-lookup"><span data-stu-id="b7563-112">Attribute</span></span>|<span data-ttu-id="b7563-113">説明</span><span class="sxs-lookup"><span data-stu-id="b7563-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b7563-114">type</span><span class="sxs-lookup"><span data-stu-id="b7563-114">type</span></span>|<span data-ttu-id="b7563-115">追加するトークンハンドラーの CLR 型名。</span><span class="sxs-lookup"><span data-stu-id="b7563-115">The CLR type name of the token handler to be added.</span></span> <span data-ttu-id="b7563-116">`type` 属性を指定する方法の詳細については、「[カスタム型参照](https://docs.microsoft.com/previous-versions/windows-identity-foundation/gg638728(v=msdn.10)#custom-type-references)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b7563-116">For more information about how to specify the `type` attribute, see [Custom Type References](https://docs.microsoft.com/previous-versions/windows-identity-foundation/gg638728(v=msdn.10)#custom-type-references).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b7563-117">子要素</span><span class="sxs-lookup"><span data-stu-id="b7563-117">Child Elements</span></span>  
  
|<span data-ttu-id="b7563-118">要素</span><span class="sxs-lookup"><span data-stu-id="b7563-118">Element</span></span>|<span data-ttu-id="b7563-119">説明</span><span class="sxs-lookup"><span data-stu-id="b7563-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b7563-120">\<samlSecurityTokenRequirement ></span><span class="sxs-lookup"><span data-stu-id="b7563-120">\<samlSecurityTokenRequirement></span></span>](samlsecuritytokenrequirement.md)|<span data-ttu-id="b7563-121"><xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> クラス、<xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> クラス、またはこれらのクラスのいずれかの派生クラスの構成を提供します。</span><span class="sxs-lookup"><span data-stu-id="b7563-121">Provides configuration for the <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> class, the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class, or a derived class of either of these classes.</span></span>|  
|[<span data-ttu-id="b7563-122">\<sessionTokenRequirement ></span><span class="sxs-lookup"><span data-stu-id="b7563-122">\<sessionTokenRequirement></span></span>](sessiontokenrequirement.md)|<span data-ttu-id="b7563-123"><xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> クラスまたは派生クラスの構成を提供します。</span><span class="sxs-lookup"><span data-stu-id="b7563-123">Provides configuration for the <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> class or derived classes.</span></span>|  
|[<span data-ttu-id="b7563-124">\<userNameSecurityTokenHandlerRequirement ></span><span class="sxs-lookup"><span data-stu-id="b7563-124">\<userNameSecurityTokenHandlerRequirement></span></span>](usernamesecuritytokenhandlerrequirement.md)|<span data-ttu-id="b7563-125"><xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> クラスまたは派生クラスの構成を提供します。</span><span class="sxs-lookup"><span data-stu-id="b7563-125">Provides configuration for the <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> class or derived classes.</span></span>|  
|[<span data-ttu-id="b7563-126">\<x509SecurityTokenHandlerRequirement ></span><span class="sxs-lookup"><span data-stu-id="b7563-126">\<x509SecurityTokenHandlerRequirement></span></span>](x509securitytokenhandlerrequirement.md)|<span data-ttu-id="b7563-127"><xref:System.IdentityModel.Tokens.X509SecurityTokenHandler> クラスまたは派生クラスのオプションの構成を提供します。</span><span class="sxs-lookup"><span data-stu-id="b7563-127">Provides optional configuration for the <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler> class or derived classes.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b7563-128">親要素</span><span class="sxs-lookup"><span data-stu-id="b7563-128">Parent Elements</span></span>  
  
|<span data-ttu-id="b7563-129">要素</span><span class="sxs-lookup"><span data-stu-id="b7563-129">Element</span></span>|<span data-ttu-id="b7563-130">説明</span><span class="sxs-lookup"><span data-stu-id="b7563-130">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b7563-131">\<securityTokenHandlers ></span><span class="sxs-lookup"><span data-stu-id="b7563-131">\<securityTokenHandlers></span></span>](securitytokenhandlers.md)|<span data-ttu-id="b7563-132">エンドポイントに登録されているセキュリティトークンハンドラーのコレクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="b7563-132">Specifies a collection of security token handlers that are registered with the endpoint.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b7563-133">Remarks</span><span class="sxs-lookup"><span data-stu-id="b7563-133">Remarks</span></span>  
 <span data-ttu-id="b7563-134">`<add>` 要素は、トークンハンドラーの構成を指定する1つの子要素を受け取ることができます。</span><span class="sxs-lookup"><span data-stu-id="b7563-134">The `<add>` element can take a single child element that specifies the configuration for the token handler.</span></span> <span data-ttu-id="b7563-135">これは、`<add>` 要素の `type` 属性を通じて参照されるハンドラークラスがこの機能をサポートするかどうかによって異なります。</span><span class="sxs-lookup"><span data-stu-id="b7563-135">This is dependent on whether the handler class referenced through the `type` attribute of the `<add>` element provides support for this feature.</span></span> <span data-ttu-id="b7563-136">この機能を提供するトークンハンドラークラスは、<xref:System.Xml.XmlElement> オブジェクトを受け取るコンストラクターを公開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b7563-136">Token handler classes that provide this feature must expose a constructor that takes an <xref:System.Xml.XmlElement> object.</span></span>  

```csharp  
public class CustomTokenHandler : Microsoft.IdentityModel.Tokens.SecurityTokenHandler  
{  
    public CustomTokenHandler( XmlElement customConfig )  
    {  
    }  
}  
```  
  
 <span data-ttu-id="b7563-137">いくつかの組み込みセキュリティトークンハンドラークラスは、この機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="b7563-137">Several of the built-in security token handler classes do provide this functionality.</span></span> <span data-ttu-id="b7563-138">これらのクラスは、<xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>、<xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>、<xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler>、<xref:System.IdentityModel.Tokens.X509SecurityTokenHandler>、および <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler>です。</span><span class="sxs-lookup"><span data-stu-id="b7563-138">These classes are <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>, <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler>, and <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler>.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="b7563-139">トークンハンドラーコレクションには、指定された任意の型の1つのハンドラーのみを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="b7563-139">The token handler collection can only contain a single handler of any given type.</span></span> <span data-ttu-id="b7563-140">これは、たとえば、<xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> クラスから派生したハンドラーをコレクションに追加する場合は、まず、既定で存在する <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>をコレクションから削除する必要があることを意味します。</span><span class="sxs-lookup"><span data-stu-id="b7563-140">This means, for example, that if you want to add a handler that is derived from the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class to the collection, you must first remove the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>, which is present by default, from the collection.</span></span> <span data-ttu-id="b7563-141">[\<remove >](remove.md)要素を使用してコレクションから1つのハンドラーを削除することも、 [\<clear >](clear.md)要素を使用してコレクションからすべてのハンドラーを削除することもできます。</span><span class="sxs-lookup"><span data-stu-id="b7563-141">You can use the [\<remove>](remove.md) element to remove a single handler from the collection or use the [\<clear>](clear.md) element to remove all handlers from the collection.</span></span>  
  
 <span data-ttu-id="b7563-142">ハンドラーに対して指定された設定は、 [\<securityTokenHandlerConfiguration >](securitytokenhandlerconfiguration.md)要素の下にあるトークンハンドラーコレクションで指定された同等の設定をオーバーライドし、 [\<ユーザー構成 >](identityconfiguration.md)要素の下のサービスレベルで指定されます。</span><span class="sxs-lookup"><span data-stu-id="b7563-142">Settings specified on a handler override equivalent settings specified on the token handler collection under the [\<securityTokenHandlerConfiguration>](securitytokenhandlerconfiguration.md) element and those specified at the service-level under the [\<identityConfiguration>](identityconfiguration.md) element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b7563-143">例</span><span class="sxs-lookup"><span data-stu-id="b7563-143">Example</span></span>  
 <span data-ttu-id="b7563-144">次の XML は、`<add>` と `<remove>` の要素を使用して、既定のセッショントークンハンドラーをカスタムセッショントークンハンドラーに置き換える方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="b7563-144">The following XML shows the use of the `<add>` and `<remove>` elements to replace the default session token handler with a custom session token handler.</span></span> <span data-ttu-id="b7563-145">XML は `ClaimsAwareWebFarm` サンプルから抜粋したものです。</span><span class="sxs-lookup"><span data-stu-id="b7563-145">The XML is taken from the `ClaimsAwareWebFarm` sample.</span></span>  
  
```xml  
<securityTokenHandlers>  
  <remove type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
  <add type="System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
</securityTokenHandlers>  
```
