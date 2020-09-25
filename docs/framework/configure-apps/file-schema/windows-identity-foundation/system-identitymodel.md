---
title: <system.identityModel>
ms.date: 03/30/2017
ms.assetid: 210ce7e9-d07b-400c-800f-5f525dcf95e8
author: BrucePerlerMS
ms.openlocfilehash: 216b4c73e06469d6577c61338ad1af0fdd2dc05e
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91185575"
---
# \<system.identityModel>

<span data-ttu-id="5d7ea-102">アプリケーションで Windows Identity Foundation (WIF) オプションを有効にするための構成を提供します。</span><span class="sxs-lookup"><span data-stu-id="5d7ea-102">Provides configuration for enabling Windows Identity Foundation (WIF) options in applications.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;**\<system.identityModel>**  
  
## <a name="syntax"></a><span data-ttu-id="5d7ea-103">構文</span><span class="sxs-lookup"><span data-stu-id="5d7ea-103">Syntax</span></span>  
  
```xml  
<system.identityModel>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5d7ea-104">属性および要素</span><span class="sxs-lookup"><span data-stu-id="5d7ea-104">Attributes and Elements</span></span>  

 <span data-ttu-id="5d7ea-105">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="5d7ea-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5d7ea-106">属性</span><span class="sxs-lookup"><span data-stu-id="5d7ea-106">Attributes</span></span>  

 <span data-ttu-id="5d7ea-107">None</span><span class="sxs-lookup"><span data-stu-id="5d7ea-107">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="5d7ea-108">子要素</span><span class="sxs-lookup"><span data-stu-id="5d7ea-108">Child Elements</span></span>  
  
|<span data-ttu-id="5d7ea-109">要素</span><span class="sxs-lookup"><span data-stu-id="5d7ea-109">Element</span></span>|<span data-ttu-id="5d7ea-110">説明</span><span class="sxs-lookup"><span data-stu-id="5d7ea-110">Description</span></span>|  
|-------------|-----------------|  
|[\<identityConfiguration>](identityconfiguration.md)|<span data-ttu-id="5d7ea-111">サービスレベルの id 設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="5d7ea-111">Specifies service-level identity settings.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="5d7ea-112">親要素</span><span class="sxs-lookup"><span data-stu-id="5d7ea-112">Parent Elements</span></span>  
  
|<span data-ttu-id="5d7ea-113">要素</span><span class="sxs-lookup"><span data-stu-id="5d7ea-113">Element</span></span>|<span data-ttu-id="5d7ea-114">説明</span><span class="sxs-lookup"><span data-stu-id="5d7ea-114">Description</span></span>|  
|-------------|-----------------|  
|`<configuration>`|<span data-ttu-id="5d7ea-115">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="5d7ea-115">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5d7ea-116">解説</span><span class="sxs-lookup"><span data-stu-id="5d7ea-116">Remarks</span></span>  

 <span data-ttu-id="5d7ea-117">`<system.identityModel>`構成ファイルにセクションを追加して、Windows Identity Foundation (WIF) を使用するようにサービスまたはアプリケーションを構成します。</span><span class="sxs-lookup"><span data-stu-id="5d7ea-117">Add a `<system.identityModel>` section to the configuration file to configure a service or application to use Windows Identity Foundation (WIF).</span></span> <span data-ttu-id="5d7ea-118">`<system.identityModel>`要素は、クラスによって表され <xref:System.IdentityModel.Configuration.SystemIdentityModelSection> ます。</span><span class="sxs-lookup"><span data-stu-id="5d7ea-118">The `<system.identityModel>` element is represented by the <xref:System.IdentityModel.Configuration.SystemIdentityModelSection> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5d7ea-119">例</span><span class="sxs-lookup"><span data-stu-id="5d7ea-119">Example</span></span>  

 <span data-ttu-id="5d7ea-120">次の例は、構成ファイルにセクションを追加する方法を示して `<system.identityModel>` います。</span><span class="sxs-lookup"><span data-stu-id="5d7ea-120">The following example shows how to add a `<system.identityModel>` section to a configuration file.</span></span> <span data-ttu-id="5d7ea-121">最初に、構成セクションと名前空間の宣言を要素の下に追加する必要があり `<configSections>` ます。</span><span class="sxs-lookup"><span data-stu-id="5d7ea-121">You must first add the configuration section and namespace declaration under the `<configSections>` element.</span></span> <span data-ttu-id="5d7ea-122">次に、要素を `<system.IdentityModel>` 構成ファイルに追加して、1つまたは複数の id 構成を指定できます。</span><span class="sxs-lookup"><span data-stu-id="5d7ea-122">Then you can add the `<system.IdentityModel>` element to your configuration file to specify one or more identity configurations.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="5d7ea-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="5d7ea-123">See also</span></span>

- <xref:System.IdentityModel.Configuration.SystemIdentityModelSection>
