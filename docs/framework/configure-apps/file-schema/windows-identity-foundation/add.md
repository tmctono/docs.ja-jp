---
title: <add>
ms.date: 03/30/2017
ms.assetid: 4712a888-f154-4395-8887-ef14a88a6497
author: BrucePerlerMS
ms.openlocfilehash: 7c2b6bdc62da63905d7ff33a9984808e7b7d114f
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/15/2020
ms.locfileid: "90544541"
---
# \<add>
<span data-ttu-id="b2415-101">指定されたセキュリティトークンハンドラーをトークンハンドラーコレクションに追加します。</span><span class="sxs-lookup"><span data-stu-id="b2415-101">Adds the specified security token handler to the token handler collection.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="b2415-102">構文</span><span class="sxs-lookup"><span data-stu-id="b2415-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b2415-103">属性および要素</span><span class="sxs-lookup"><span data-stu-id="b2415-103">Attributes and Elements</span></span>  
 <span data-ttu-id="b2415-104">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="b2415-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b2415-105">属性</span><span class="sxs-lookup"><span data-stu-id="b2415-105">Attributes</span></span>  
  
|<span data-ttu-id="b2415-106">属性</span><span class="sxs-lookup"><span data-stu-id="b2415-106">Attribute</span></span>|<span data-ttu-id="b2415-107">説明</span><span class="sxs-lookup"><span data-stu-id="b2415-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b2415-108">type</span><span class="sxs-lookup"><span data-stu-id="b2415-108">type</span></span>|<span data-ttu-id="b2415-109">追加するトークンハンドラーの CLR 型名。</span><span class="sxs-lookup"><span data-stu-id="b2415-109">The CLR type name of the token handler to be added.</span></span> <span data-ttu-id="b2415-110">属性を指定する方法の詳細については `type` 、「 [カスタム型参照](/previous-versions/windows-identity-foundation/gg638728(v=msdn.10)#custom-type-references)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b2415-110">For more information about how to specify the `type` attribute, see [Custom Type References](/previous-versions/windows-identity-foundation/gg638728(v=msdn.10)#custom-type-references).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b2415-111">子要素</span><span class="sxs-lookup"><span data-stu-id="b2415-111">Child Elements</span></span>  
  
|<span data-ttu-id="b2415-112">要素</span><span class="sxs-lookup"><span data-stu-id="b2415-112">Element</span></span>|<span data-ttu-id="b2415-113">説明</span><span class="sxs-lookup"><span data-stu-id="b2415-113">Description</span></span>|  
|-------------|-----------------|  
|[\<samlSecurityTokenRequirement>](samlsecuritytokenrequirement.md)|<span data-ttu-id="b2415-114">クラス、クラス、 <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> またはこれらのクラスの派生クラスの構成を提供します。</span><span class="sxs-lookup"><span data-stu-id="b2415-114">Provides configuration for the <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> class, the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class, or a derived class of either of these classes.</span></span>|  
|[\<sessionTokenRequirement>](sessiontokenrequirement.md)|<span data-ttu-id="b2415-115"><xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler>クラスまたは派生クラスの構成を提供します。</span><span class="sxs-lookup"><span data-stu-id="b2415-115">Provides configuration for the <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> class or derived classes.</span></span>|  
|[\<userNameSecurityTokenHandlerRequirement>](usernamesecuritytokenhandlerrequirement.md)|<span data-ttu-id="b2415-116"><xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler>クラスまたは派生クラスの構成を提供します。</span><span class="sxs-lookup"><span data-stu-id="b2415-116">Provides configuration for the <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> class or derived classes.</span></span>|  
|[\<x509SecurityTokenHandlerRequirement>](x509securitytokenhandlerrequirement.md)|<span data-ttu-id="b2415-117">クラスまたは派生クラスのオプションの構成を提供 <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler> します。</span><span class="sxs-lookup"><span data-stu-id="b2415-117">Provides optional configuration for the <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler> class or derived classes.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b2415-118">親要素</span><span class="sxs-lookup"><span data-stu-id="b2415-118">Parent Elements</span></span>  
  
|<span data-ttu-id="b2415-119">要素</span><span class="sxs-lookup"><span data-stu-id="b2415-119">Element</span></span>|<span data-ttu-id="b2415-120">説明</span><span class="sxs-lookup"><span data-stu-id="b2415-120">Description</span></span>|  
|-------------|-----------------|  
|[\<securityTokenHandlers>](securitytokenhandlers.md)|<span data-ttu-id="b2415-121">エンドポイントに登録されているセキュリティトークンハンドラーのコレクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="b2415-121">Specifies a collection of security token handlers that are registered with the endpoint.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b2415-122">Remarks</span><span class="sxs-lookup"><span data-stu-id="b2415-122">Remarks</span></span>  
 <span data-ttu-id="b2415-123">要素は、 `<add>` トークンハンドラーの構成を指定する1つの子要素を受け取ることができます。</span><span class="sxs-lookup"><span data-stu-id="b2415-123">The `<add>` element can take a single child element that specifies the configuration for the token handler.</span></span> <span data-ttu-id="b2415-124">これは、要素の属性を通じて参照されるハンドラークラスが `type` この機能をサポートするかどうかによって異なり `<add>` ます。</span><span class="sxs-lookup"><span data-stu-id="b2415-124">This is dependent on whether the handler class referenced through the `type` attribute of the `<add>` element provides support for this feature.</span></span> <span data-ttu-id="b2415-125">この機能を提供するトークンハンドラークラスは、オブジェクトを受け取るコンストラクターを公開する必要があり <xref:System.Xml.XmlElement> ます。</span><span class="sxs-lookup"><span data-stu-id="b2415-125">Token handler classes that provide this feature must expose a constructor that takes an <xref:System.Xml.XmlElement> object.</span></span>  

```csharp  
public class CustomTokenHandler : Microsoft.IdentityModel.Tokens.SecurityTokenHandler  
{  
    public CustomTokenHandler( XmlElement customConfig )  
    {  
    }  
}  
```  
  
 <span data-ttu-id="b2415-126">いくつかの組み込みセキュリティトークンハンドラークラスは、この機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="b2415-126">Several of the built-in security token handler classes do provide this functionality.</span></span> <span data-ttu-id="b2415-127">これらのクラスは、、、、 <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler> 、および <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> です。</span><span class="sxs-lookup"><span data-stu-id="b2415-127">These classes are <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>, <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler>, and <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler>.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="b2415-128">トークンハンドラーコレクションには、指定された任意の型の1つのハンドラーのみを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="b2415-128">The token handler collection can only contain a single handler of any given type.</span></span> <span data-ttu-id="b2415-129">これは、たとえば、クラスから派生したハンドラーをコレクションに追加する場合は、 <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> 最初にコレクションから既定で存在するを削除する必要があることを意味し <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> ます。</span><span class="sxs-lookup"><span data-stu-id="b2415-129">This means, for example, that if you want to add a handler that is derived from the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class to the collection, you must first remove the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>, which is present by default, from the collection.</span></span> <span data-ttu-id="b2415-130">要素を使用して、 [\<remove>](remove.md) コレクションから1つのハンドラーを削除することも、要素を使用してコレクションからすべてのハンドラーを削除することもでき [\<clear>](clear.md) ます。</span><span class="sxs-lookup"><span data-stu-id="b2415-130">You can use the [\<remove>](remove.md) element to remove a single handler from the collection or use the [\<clear>](clear.md) element to remove all handlers from the collection.</span></span>  
  
 <span data-ttu-id="b2415-131">ハンドラーに指定された設定は、要素の下のトークンハンドラーコレクションで指定された同等 [\<securityTokenHandlerConfiguration>](securitytokenhandlerconfiguration.md) の設定をオーバーライドし、要素の下のサービスレベルで指定され [\<identityConfiguration>](identityconfiguration.md) ます。</span><span class="sxs-lookup"><span data-stu-id="b2415-131">Settings specified on a handler override equivalent settings specified on the token handler collection under the [\<securityTokenHandlerConfiguration>](securitytokenhandlerconfiguration.md) element and those specified at the service-level under the [\<identityConfiguration>](identityconfiguration.md) element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b2415-132">例</span><span class="sxs-lookup"><span data-stu-id="b2415-132">Example</span></span>  
 <span data-ttu-id="b2415-133">次の XML は、および要素を使用して、 `<add>` `<remove>` 既定のセッショントークンハンドラーをカスタムセッショントークンハンドラーに置き換える方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="b2415-133">The following XML shows the use of the `<add>` and `<remove>` elements to replace the default session token handler with a custom session token handler.</span></span> <span data-ttu-id="b2415-134">XML は、「」のサンプルから抜粋したものです `ClaimsAwareWebFarm` 。</span><span class="sxs-lookup"><span data-stu-id="b2415-134">The XML is taken from the `ClaimsAwareWebFarm` sample.</span></span>  
  
```xml  
<securityTokenHandlers>  
  <remove type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
  <add type="System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
</securityTokenHandlers>  
```
