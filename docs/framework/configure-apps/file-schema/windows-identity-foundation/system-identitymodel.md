---
title: <system.identityModel>
ms.date: 03/30/2017
ms.assetid: 210ce7e9-d07b-400c-800f-5f525dcf95e8
author: BrucePerlerMS
ms.openlocfilehash: fd17c0318480f5e157c8c9114116735b82bbfcef
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2019
ms.locfileid: "57351295"
---
# <a name="systemidentitymodel"></a><span data-ttu-id="f51da-102">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="f51da-102">\<system.identityModel></span></span>
<span data-ttu-id="f51da-103">アプリケーションの Windows Identity Foundation (WIF) オプションを有効にするための構成を提供します。</span><span class="sxs-lookup"><span data-stu-id="f51da-103">Provides configuration for enabling Windows Identity Foundation (WIF) options in applications.</span></span>  
  
 <span data-ttu-id="f51da-104">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="f51da-104">\<system.identityModel></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f51da-105">構文</span><span class="sxs-lookup"><span data-stu-id="f51da-105">Syntax</span></span>  
  
```xml  
<system.identityModel>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f51da-106">属性および要素</span><span class="sxs-lookup"><span data-stu-id="f51da-106">Attributes and Elements</span></span>  
 <span data-ttu-id="f51da-107">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="f51da-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f51da-108">属性</span><span class="sxs-lookup"><span data-stu-id="f51da-108">Attributes</span></span>  
 <span data-ttu-id="f51da-109">なし</span><span class="sxs-lookup"><span data-stu-id="f51da-109">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="f51da-110">子要素</span><span class="sxs-lookup"><span data-stu-id="f51da-110">Child Elements</span></span>  
  
|<span data-ttu-id="f51da-111">要素</span><span class="sxs-lookup"><span data-stu-id="f51da-111">Element</span></span>|<span data-ttu-id="f51da-112">説明</span><span class="sxs-lookup"><span data-stu-id="f51da-112">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f51da-113">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="f51da-113">\<identityConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|<span data-ttu-id="f51da-114">サービス レベルの id の設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="f51da-114">Specifies service-level identity settings.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f51da-115">親要素</span><span class="sxs-lookup"><span data-stu-id="f51da-115">Parent Elements</span></span>  
  
|<span data-ttu-id="f51da-116">要素</span><span class="sxs-lookup"><span data-stu-id="f51da-116">Element</span></span>|<span data-ttu-id="f51da-117">説明</span><span class="sxs-lookup"><span data-stu-id="f51da-117">Description</span></span>|  
|-------------|-----------------|  
|`<configuration>`|<span data-ttu-id="f51da-118">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="f51da-118">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f51da-119">Remarks</span><span class="sxs-lookup"><span data-stu-id="f51da-119">Remarks</span></span>  
 <span data-ttu-id="f51da-120">追加、`<system.identityModel>`サービスまたは Windows Identity Foundation (WIF) を使用するアプリケーションを構成する構成ファイルにセクション。</span><span class="sxs-lookup"><span data-stu-id="f51da-120">Add a `<system.identityModel>` section to the configuration file to configure a service or application to use Windows Identity Foundation (WIF).</span></span> <span data-ttu-id="f51da-121">`<system.identityModel>`要素が表される、<xref:System.IdentityModel.Configuration.SystemIdentityModelSection>クラス。</span><span class="sxs-lookup"><span data-stu-id="f51da-121">The `<system.identityModel>` element is represented by the <xref:System.IdentityModel.Configuration.SystemIdentityModelSection> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f51da-122">例</span><span class="sxs-lookup"><span data-stu-id="f51da-122">Example</span></span>  
 <span data-ttu-id="f51da-123">次の例は、追加する方法を示します、`<system.identityModel>`構成ファイルにセクション。</span><span class="sxs-lookup"><span data-stu-id="f51da-123">The following example shows how to add a `<system.identityModel>` section to a configuration file.</span></span> <span data-ttu-id="f51da-124">構成セクションと名前空間宣言を追加する必要があります最初、`<configSections>`要素。</span><span class="sxs-lookup"><span data-stu-id="f51da-124">You must first add the configuration section and namespace declaration under the `<configSections>` element.</span></span> <span data-ttu-id="f51da-125">追加することができ、`<system.IdentityModel>`要素を 1 つまたは複数の id 構成を指定する構成ファイル。</span><span class="sxs-lookup"><span data-stu-id="f51da-125">Then you can add the `<system.IdentityModel>` element to your configuration file to specify one or more identity configurations.</span></span>  
  
```xml  
<configuration>  
  <configSections>  
    <!--WIF 4.5 sections -->  
    <section name="system.identityModel" type="System.IdentityModel.Configuration.SystemIdentityModelSection, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=B77A5C561934E089"/>  
    <section name="system.identityModel.services" type="System.IdentityModel.Services.Configuration.SystemIdentityModelServicesSection, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=B77A5C561934E089"/>  
  </configSections>  
  
  ...  
  
  <system.identityModel>  
    <identityConfiguration>  
      <audienceUris>  
        <add value="http://localhost/WebApplication1/" />  
      </audienceUris>  
      <issuerNameRegistry type="System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=B77A5C561934E089">  
        <trustedIssuers>  
          <add thumbprint="313D3B … 9106A9EC" name="SelfSTS" />  
        </trustedIssuers>  
      </issuerNameRegistry>  
      <certificateValidation certificateValidationMode="None"/>  
    </identityConfiguration>  
  </system.identityModel>  
  
  ...  
  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="f51da-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="f51da-126">See also</span></span>
- <xref:System.IdentityModel.Configuration.SystemIdentityModelSection>
