---
title: <system.identityModel.services>
ms.date: 03/30/2017
ms.assetid: fa1624dd-2d74-4ae3-942e-498cee261ac5
author: BrucePerlerMS
ms.openlocfilehash: 57757aaec39bc5c552e7ba12c9779cb3a92a9025
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152505"
---
# <a name="systemidentitymodelservices"></a><span data-ttu-id="6f01c-102">\<サービス></span><span class="sxs-lookup"><span data-stu-id="6f01c-102">\<system.identityModel.services></span></span>
<span data-ttu-id="6f01c-103">WS フェデレーション プロトコルを使用した認証の構成セクション。</span><span class="sxs-lookup"><span data-stu-id="6f01c-103">Configuration section for authentication using the WS-Federation protocol.</span></span>  
  
<span data-ttu-id="6f01c-104">[**\<構成>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="6f01c-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="6f01c-105">&nbsp;&nbsp;**\<サービス>**</span><span class="sxs-lookup"><span data-stu-id="6f01c-105">&nbsp;&nbsp;**\<system.identityModel.services>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6f01c-106">構文</span><span class="sxs-lookup"><span data-stu-id="6f01c-106">Syntax</span></span>  
  
```xml  
<system.identityModel.services>  
  <federationConfiguration name=xs:string identityConfigurationName=xs:string>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6f01c-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="6f01c-107">Attributes and Elements</span></span>  
 <span data-ttu-id="6f01c-108">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="6f01c-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6f01c-109">属性</span><span class="sxs-lookup"><span data-stu-id="6f01c-109">Attributes</span></span>  
 <span data-ttu-id="6f01c-110">なし</span><span class="sxs-lookup"><span data-stu-id="6f01c-110">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="6f01c-111">子要素</span><span class="sxs-lookup"><span data-stu-id="6f01c-111">Child Elements</span></span>  
  
|<span data-ttu-id="6f01c-112">要素</span><span class="sxs-lookup"><span data-stu-id="6f01c-112">Element</span></span>|<span data-ttu-id="6f01c-113">説明</span><span class="sxs-lookup"><span data-stu-id="6f01c-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6f01c-114">\<フェデレーション構成></span><span class="sxs-lookup"><span data-stu-id="6f01c-114">\<federationConfiguration></span></span>](federationconfiguration.md)|<span data-ttu-id="6f01c-115">(WSFAM)<xref:System.IdentityModel.Services.WSFederationAuthenticationModule>および (SAM) HTTP<xref:System.IdentityModel.Services.SessionAuthenticationModule>モジュールを構成する設定が含まれています。</span><span class="sxs-lookup"><span data-stu-id="6f01c-115">Contains the settings that configure the <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) and the <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM) HTTP modules.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="6f01c-116">親要素</span><span class="sxs-lookup"><span data-stu-id="6f01c-116">Parent Elements</span></span>  
 <span data-ttu-id="6f01c-117">なし</span><span class="sxs-lookup"><span data-stu-id="6f01c-117">None</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6f01c-118">解説</span><span class="sxs-lookup"><span data-stu-id="6f01c-118">Remarks</span></span>  
 <span data-ttu-id="6f01c-119">アプリケーションの`<system.identityModel.services>`構成ファイルにセクションを追加して、SAM と WSFAM の設定を提供します。</span><span class="sxs-lookup"><span data-stu-id="6f01c-119">Add a `<system.identityModel.services>` section to your application’s configuration file to provide settings for the SAM and WSFAM.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="6f01c-120"><xref:System.IdentityModel.Services.ClaimsPrincipalPermission>または<xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute>クラスを使用してコード内でクレーム ベースのアクセス制御を提供する場合、承認の<xref:System.Security.Claims.ClaimsAuthorizationManager>決定を行うために使用されるクレーム承認マネージャー ( )`<identityConfiguration>`とポリシーは、このセクションの要素から暗黙的または明示的`<federationConfiguration>`に参照される要素を使用して構成されます。</span><span class="sxs-lookup"><span data-stu-id="6f01c-120">When using the <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> or the <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> class to provide claims-based access control in your code, the claims authorization manager (<xref:System.Security.Claims.ClaimsAuthorizationManager>) and policy that is used to make authorization decisions are configured through an `<identityConfiguration>` element that is implicitly or explicitly referenced from a `<federationConfiguration>` element in this section.</span></span> <span data-ttu-id="6f01c-121">詳細については、[\<フェデレーション構成>](federationconfiguration.md)要素の**下の解説**を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6f01c-121">For more information, see the **Remarks** under the [\<federationConfiguration>](federationconfiguration.md) element.</span></span>  
  
 <span data-ttu-id="6f01c-122">セクション`<system.identityModel.services>`は<xref:System.IdentityModel.Services.Configuration.SystemIdentityModelServicesSection>クラスによって表されます。</span><span class="sxs-lookup"><span data-stu-id="6f01c-122">The `<system.identityModel.services>` section is represented by the <xref:System.IdentityModel.Services.Configuration.SystemIdentityModelServicesSection> class.</span></span> <span data-ttu-id="6f01c-123">セクションで構成された`<federationConfiguration>`子要素のコレクションは、<xref:System.IdentityModel.Services.Configuration.FederationConfigurationElementCollection>クラスによって表されます。</span><span class="sxs-lookup"><span data-stu-id="6f01c-123">The collection of child `<federationConfiguration>` elements configured in the section is represented by the <xref:System.IdentityModel.Services.Configuration.FederationConfigurationElementCollection> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6f01c-124">例</span><span class="sxs-lookup"><span data-stu-id="6f01c-124">Example</span></span>  
 <span data-ttu-id="6f01c-125">次の XML は、構成`<system.identityModel.services>`ファイルにセクションを追加する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="6f01c-125">The following XML shows how to add a `<system.identityModel.services>` section to a configuration file.</span></span> <span data-ttu-id="6f01c-126">まず、セクションとセクションの両方にセクション宣言`<system.identityModel.services>`を追加する`<system.identityModel>`必要があります。</span><span class="sxs-lookup"><span data-stu-id="6f01c-126">You must first add section declarations for both the `<system.identityModel.services>` section and the `<system.identityModel>` sections.</span></span> <span data-ttu-id="6f01c-127">(セクションを`<system.identityModel.services>`追加する場合は、必要に応じてランタイムが既定`<system.identityModel>``<identityConfiguration>`のセクションを作成できるように、セクションの宣言も追加する必要があります)。セクション宣言を追加した後、要素の下でフェデレーション認証設定を`<system.identityModel.services>`構成できます。</span><span class="sxs-lookup"><span data-stu-id="6f01c-127">(When you add a `<system.identityModel.services>` section, you should also add a declaration for the `<system.identityModel>` section to ensure that a default `<identityConfiguration>` section can be created by the runtime if necessary.) After the section declarations have been added, you can configure federated authentication settings under the `<system.identityModel.services>` element.</span></span>  
  
```xml  
<configuration>  
  <configSections>  
    <section name="system.identityModel" type="System.IdentityModel.Configuration.SystemIdentityModelSection, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=B77A5C561934E089" />  
    <section name="system.identityModel.services" type="System.IdentityModel.Services.Configuration.SystemIdentityModelServicesSection, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=B77A5C561934E089" />  
  </configSections>  
  
  <!-- Additional elements (not shown) -->  
  
  <system.identityModel.services>  
    <federationConfiguration>  
      <wsFederation passiveRedirectEnabled="true"
        issuer="http://localhost:15839/wsFederationSTS/Issue"
        realm="http://localhost:50969/" reply="http://localhost:50969/"
        requireHttps="false"
        signOutReply="http://localhost:50969/SignedOutPage.html"
        signOutQueryString="Param1=value2&Param2=value2"
        persistentCookiesOnPassiveRedirects="true" />  
      <cookieHandler requireSsl="false" />  
    </federationConfiguration>  
  </system.identityModel.services>  
  
</configuration>  
```
