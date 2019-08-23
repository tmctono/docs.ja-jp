---
title: <system.identityModel>
ms.date: 03/30/2017
ms.assetid: 210ce7e9-d07b-400c-800f-5f525dcf95e8
author: BrucePerlerMS
ms.openlocfilehash: 286ae88946692e6894ca3c7ee9e1348415c84ade
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69943598"
---
# <a name="systemidentitymodel"></a><span data-ttu-id="1517b-102">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="1517b-102">\<system.identityModel></span></span>
<span data-ttu-id="1517b-103">アプリケーションで Windows Identity Foundation (WIF) オプションを有効にするための構成を提供します。</span><span class="sxs-lookup"><span data-stu-id="1517b-103">Provides configuration for enabling Windows Identity Foundation (WIF) options in applications.</span></span>  
  
 <span data-ttu-id="1517b-104">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="1517b-104">\<system.identityModel></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1517b-105">構文</span><span class="sxs-lookup"><span data-stu-id="1517b-105">Syntax</span></span>  
  
```xml  
<system.identityModel>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1517b-106">属性および要素</span><span class="sxs-lookup"><span data-stu-id="1517b-106">Attributes and Elements</span></span>  
 <span data-ttu-id="1517b-107">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="1517b-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1517b-108">属性</span><span class="sxs-lookup"><span data-stu-id="1517b-108">Attributes</span></span>  
 <span data-ttu-id="1517b-109">なし</span><span class="sxs-lookup"><span data-stu-id="1517b-109">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="1517b-110">子要素</span><span class="sxs-lookup"><span data-stu-id="1517b-110">Child Elements</span></span>  
  
|<span data-ttu-id="1517b-111">要素</span><span class="sxs-lookup"><span data-stu-id="1517b-111">Element</span></span>|<span data-ttu-id="1517b-112">説明</span><span class="sxs-lookup"><span data-stu-id="1517b-112">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1517b-113">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="1517b-113">\<identityConfiguration></span></span>](identityconfiguration.md)|<span data-ttu-id="1517b-114">サービスレベルの id 設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="1517b-114">Specifies service-level identity settings.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="1517b-115">親要素</span><span class="sxs-lookup"><span data-stu-id="1517b-115">Parent Elements</span></span>  
  
|<span data-ttu-id="1517b-116">要素</span><span class="sxs-lookup"><span data-stu-id="1517b-116">Element</span></span>|<span data-ttu-id="1517b-117">説明</span><span class="sxs-lookup"><span data-stu-id="1517b-117">Description</span></span>|  
|-------------|-----------------|  
|`<configuration>`|<span data-ttu-id="1517b-118">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="1517b-118">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1517b-119">Remarks</span><span class="sxs-lookup"><span data-stu-id="1517b-119">Remarks</span></span>  
 <span data-ttu-id="1517b-120">構成ファイル`<system.identityModel>`にセクションを追加して、Windows Identity Foundation (WIF) を使用するようにサービスまたはアプリケーションを構成します。</span><span class="sxs-lookup"><span data-stu-id="1517b-120">Add a `<system.identityModel>` section to the configuration file to configure a service or application to use Windows Identity Foundation (WIF).</span></span> <span data-ttu-id="1517b-121">要素は、 <xref:System.IdentityModel.Configuration.SystemIdentityModelSection>クラスによって表されます。 `<system.identityModel>`</span><span class="sxs-lookup"><span data-stu-id="1517b-121">The `<system.identityModel>` element is represented by the <xref:System.IdentityModel.Configuration.SystemIdentityModelSection> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1517b-122">例</span><span class="sxs-lookup"><span data-stu-id="1517b-122">Example</span></span>  
 <span data-ttu-id="1517b-123">次の例は、構成ファイルに`<system.identityModel>`セクションを追加する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="1517b-123">The following example shows how to add a `<system.identityModel>` section to a configuration file.</span></span> <span data-ttu-id="1517b-124">最初に、構成セクションと名前空間の宣言を要素`<configSections>`の下に追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1517b-124">You must first add the configuration section and namespace declaration under the `<configSections>` element.</span></span> <span data-ttu-id="1517b-125">次に、要素を`<system.IdentityModel>`構成ファイルに追加して、1つまたは複数の id 構成を指定できます。</span><span class="sxs-lookup"><span data-stu-id="1517b-125">Then you can add the `<system.IdentityModel>` element to your configuration file to specify one or more identity configurations.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="1517b-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="1517b-126">See also</span></span>

- <xref:System.IdentityModel.Configuration.SystemIdentityModelSection>
