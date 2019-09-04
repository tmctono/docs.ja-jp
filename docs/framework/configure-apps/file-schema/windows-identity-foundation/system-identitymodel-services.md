---
title: <system.identityModel.services>
ms.date: 03/30/2017
ms.assetid: fa1624dd-2d74-4ae3-942e-498cee261ac5
author: BrucePerlerMS
ms.openlocfilehash: e9488c0681e1a5f0fe94112a36b65ec73bf9fd09
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251806"
---
# <a name="systemidentitymodelservices"></a><span data-ttu-id="c6f7a-102">\<system.identityModel.services></span><span class="sxs-lookup"><span data-stu-id="c6f7a-102">\<system.identityModel.services></span></span>
<span data-ttu-id="c6f7a-103">WS-FEDERATION プロトコルを使用した認証の構成セクション。</span><span class="sxs-lookup"><span data-stu-id="c6f7a-103">Configuration section for authentication using the WS-Federation protocol.</span></span>  
  
<span data-ttu-id="c6f7a-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="c6f7a-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="c6f7a-105">&nbsp;&nbsp; **\<> のシステム**</span><span class="sxs-lookup"><span data-stu-id="c6f7a-105">&nbsp;&nbsp;**\<system.identityModel.services>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c6f7a-106">構文</span><span class="sxs-lookup"><span data-stu-id="c6f7a-106">Syntax</span></span>  
  
```xml  
<system.identityModel.services>  
  <federationConfiguration name=xs:string identityConfigurationName=xs:string>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c6f7a-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="c6f7a-107">Attributes and Elements</span></span>  
 <span data-ttu-id="c6f7a-108">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="c6f7a-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c6f7a-109">属性</span><span class="sxs-lookup"><span data-stu-id="c6f7a-109">Attributes</span></span>  
 <span data-ttu-id="c6f7a-110">なし</span><span class="sxs-lookup"><span data-stu-id="c6f7a-110">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="c6f7a-111">子要素</span><span class="sxs-lookup"><span data-stu-id="c6f7a-111">Child Elements</span></span>  
  
|<span data-ttu-id="c6f7a-112">要素</span><span class="sxs-lookup"><span data-stu-id="c6f7a-112">Element</span></span>|<span data-ttu-id="c6f7a-113">説明</span><span class="sxs-lookup"><span data-stu-id="c6f7a-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c6f7a-114">\<federationConfiguration></span><span class="sxs-lookup"><span data-stu-id="c6f7a-114">\<federationConfiguration></span></span>](federationconfiguration.md)|<span data-ttu-id="c6f7a-115"><xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (Wsfam) <xref:System.IdentityModel.Services.SessionAuthenticationModule>および (SAM) HTTP モジュールを構成する設定が含まれています。</span><span class="sxs-lookup"><span data-stu-id="c6f7a-115">Contains the settings that configure the <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) and the <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM) HTTP modules.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c6f7a-116">親要素</span><span class="sxs-lookup"><span data-stu-id="c6f7a-116">Parent Elements</span></span>  
 <span data-ttu-id="c6f7a-117">なし</span><span class="sxs-lookup"><span data-stu-id="c6f7a-117">None</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c6f7a-118">Remarks</span><span class="sxs-lookup"><span data-stu-id="c6f7a-118">Remarks</span></span>  
 <span data-ttu-id="c6f7a-119">アプリケーションの`<system.identityModel.services>`構成ファイルにセクションを追加して、SAM と wsfam の設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="c6f7a-119">Add a `<system.identityModel.services>` section to your application’s configuration file to provide settings for the SAM and WSFAM.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="c6f7a-120"><xref:System.IdentityModel.Services.ClaimsPrincipalPermission> `<identityConfiguration>`クラスまたはクラスを使用して、コード内にクレームベースのアクセス制御を提供する場合、<xref:System.Security.Claims.ClaimsAuthorizationManager>承認の決定に使用される要求承認マネージャー () とポリシーは、 <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute>このセクションの`<federationConfiguration>`要素から暗黙的または明示的に参照される要素。</span><span class="sxs-lookup"><span data-stu-id="c6f7a-120">When using the <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> or the <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> class to provide claims-based access control in your code, the claims authorization manager (<xref:System.Security.Claims.ClaimsAuthorizationManager>) and policy that is used to make authorization decisions are configured through an `<identityConfiguration>` element that is implicitly or explicitly referenced from a `<federationConfiguration>` element in this section.</span></span> <span data-ttu-id="c6f7a-121">詳細については、「 [ \<federationConfiguration >](federationconfiguration.md)要素」の「**解説**」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c6f7a-121">For more information, see the **Remarks** under the [\<federationConfiguration>](federationconfiguration.md) element.</span></span>  
  
 <span data-ttu-id="c6f7a-122">セクションは、 <xref:System.IdentityModel.Services.Configuration.SystemIdentityModelServicesSection>クラスによって表されます。 `<system.identityModel.services>`</span><span class="sxs-lookup"><span data-stu-id="c6f7a-122">The `<system.identityModel.services>` section is represented by the <xref:System.IdentityModel.Services.Configuration.SystemIdentityModelServicesSection> class.</span></span> <span data-ttu-id="c6f7a-123">セクションで構成さ`<federationConfiguration>`れた子要素のコレクションは、 <xref:System.IdentityModel.Services.Configuration.FederationConfigurationElementCollection>クラスによって表されます。</span><span class="sxs-lookup"><span data-stu-id="c6f7a-123">The collection of child `<federationConfiguration>` elements configured in the section is represented by the <xref:System.IdentityModel.Services.Configuration.FederationConfigurationElementCollection> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c6f7a-124">例</span><span class="sxs-lookup"><span data-stu-id="c6f7a-124">Example</span></span>  
 <span data-ttu-id="c6f7a-125">次の XML は、構成ファイルに`<system.identityModel.services>`セクションを追加する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="c6f7a-125">The following XML shows how to add a `<system.identityModel.services>` section to a configuration file.</span></span> <span data-ttu-id="c6f7a-126">まず、セクション`<system.identityModel.services>` `<system.identityModel>`とセクションの両方にセクション宣言を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c6f7a-126">You must first add section declarations for both the `<system.identityModel.services>` section and the `<system.identityModel>` sections.</span></span> <span data-ttu-id="c6f7a-127">( `<system.identityModel.services>`セクションを追加する場合は、必要に応じて、ランタイムが`<system.identityModel>`既定`<identityConfiguration>`のセクションを作成できるように、セクションの宣言も追加する必要があります)。セクション宣言を追加した後、要素の`<system.identityModel.services>`下にフェデレーション認証設定を構成できます。</span><span class="sxs-lookup"><span data-stu-id="c6f7a-127">(When you add a `<system.identityModel.services>` section, you should also add a declaration for the `<system.identityModel>` section to ensure that a default `<identityConfiguration>` section can be created by the runtime if necessary.) After the section declarations have been added, you can configure federated authentication settings under the `<system.identityModel.services>` element.</span></span>  
  
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
