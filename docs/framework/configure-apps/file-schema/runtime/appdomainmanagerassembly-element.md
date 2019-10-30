---
title: <appDomainManagerAssembly> 要素
ms.date: 03/30/2017
helpviewer_keywords:
- <appDomainManagerAssembly> element
- appDomainManagerAssembly element
ms.assetid: c7c56e39-a700-44f5-b94e-411bfce339d9
ms.openlocfilehash: 7ba52cdf0102af05954509a11fa90e9b8a337876
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73118317"
---
# <a name="appdomainmanagerassembly-element"></a><span data-ttu-id="45541-102">\<appDomainManagerAssembly > 要素</span><span class="sxs-lookup"><span data-stu-id="45541-102">\<appDomainManagerAssembly> Element</span></span>
<span data-ttu-id="45541-103">プロセスにおける既定のアプリケーション ドメインのアプリケーション ドメイン マネージャーを提供するアセンブリを指定します。</span><span class="sxs-lookup"><span data-stu-id="45541-103">Specifies the assembly that provides the application domain manager for the default application domain in the process.</span></span>  
  
<span data-ttu-id="45541-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="45541-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="45541-105">&nbsp;&nbsp;[ **\<runtime>** ](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="45541-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="45541-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<appDomainManagerAssembly >**</span><span class="sxs-lookup"><span data-stu-id="45541-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<appDomainManagerAssembly>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="45541-107">構文</span><span class="sxs-lookup"><span data-stu-id="45541-107">Syntax</span></span>  
  
```xml  
<appDomainManagerAssembly   
   value="assembly display name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="45541-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="45541-108">Attributes and Elements</span></span>  
 <span data-ttu-id="45541-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="45541-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="45541-110">属性</span><span class="sxs-lookup"><span data-stu-id="45541-110">Attributes</span></span>  
  
|<span data-ttu-id="45541-111">属性</span><span class="sxs-lookup"><span data-stu-id="45541-111">Attribute</span></span>|<span data-ttu-id="45541-112">説明</span><span class="sxs-lookup"><span data-stu-id="45541-112">Description</span></span>|  
|---------------|-----------------|  
|`value`|<span data-ttu-id="45541-113">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="45541-113">Required attribute.</span></span> <span data-ttu-id="45541-114">プロセスの既定のアプリケーションドメインのアプリケーションドメインマネージャーを提供するアセンブリの表示名を指定します。</span><span class="sxs-lookup"><span data-stu-id="45541-114">Specifies the display name of the assembly that provides the application domain manager for the default application domain in the process.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="45541-115">子要素</span><span class="sxs-lookup"><span data-stu-id="45541-115">Child Elements</span></span>  
 <span data-ttu-id="45541-116">なし。</span><span class="sxs-lookup"><span data-stu-id="45541-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="45541-117">親要素</span><span class="sxs-lookup"><span data-stu-id="45541-117">Parent Elements</span></span>  
  
|<span data-ttu-id="45541-118">要素</span><span class="sxs-lookup"><span data-stu-id="45541-118">Element</span></span>|<span data-ttu-id="45541-119">説明</span><span class="sxs-lookup"><span data-stu-id="45541-119">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="45541-120">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="45541-120">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="45541-121">アセンブリのバインディングとガベージ コレクションに関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="45541-121">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="45541-122">Remarks</span><span class="sxs-lookup"><span data-stu-id="45541-122">Remarks</span></span>  
 <span data-ttu-id="45541-123">アプリケーションドメインマネージャーの種類を指定するには、この要素と[\<appDomainManagerType >](appdomainmanagertype-element.md)要素の両方を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="45541-123">To specify the type of the application domain manager, you must specify both this element and the [\<appDomainManagerType>](appdomainmanagertype-element.md) element.</span></span> <span data-ttu-id="45541-124">これらの要素のいずれかが指定されていない場合、もう一方は無視されます。</span><span class="sxs-lookup"><span data-stu-id="45541-124">If either of these elements is not specified, the other is ignored.</span></span>  
  
 <span data-ttu-id="45541-125">既定のアプリケーションドメインが読み込まれると、指定したアセンブリが存在しない場合、またはアセンブリに[\<appDomainManagerType >](appdomainmanagertype-element.md)要素によって指定された型が含まれていない場合に <xref:System.TypeLoadException> がスローされます。また、プロセスを開始できません。</span><span class="sxs-lookup"><span data-stu-id="45541-125">When the default application domain is loaded, <xref:System.TypeLoadException> is thrown if the specified assembly does not exist or if the assembly does not contain the type specified by the [\<appDomainManagerType>](appdomainmanagertype-element.md) element; and the process fails to start.</span></span> <span data-ttu-id="45541-126">アセンブリが見つかってもバージョン情報が一致しない場合は、<xref:System.IO.FileLoadException> がスローされます。</span><span class="sxs-lookup"><span data-stu-id="45541-126">If the assembly is found but the version information does not match, a <xref:System.IO.FileLoadException> is thrown.</span></span>  
  
 <span data-ttu-id="45541-127">既定のアプリケーションドメインに対してアプリケーションドメインマネージャーの種類を指定すると、既定のアプリケーションドメインから作成された他のアプリケーションドメインは、アプリケーションドメインマネージャーの種類を継承します。</span><span class="sxs-lookup"><span data-stu-id="45541-127">When you specify the application domain manager type for the default application domain, other application domains created from the default application domain inherit the application domain manager type.</span></span> <span data-ttu-id="45541-128"><xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType> と <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType> のプロパティを使用して、新しいアプリケーションドメインに別のアプリケーションドメインマネージャーの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="45541-128">Use the <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType> and <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType> properties to specify a different application domain manager type for a new application domain.</span></span>  
  
 <span data-ttu-id="45541-129">アプリケーションドメインマネージャーの種類を指定するには、アプリケーションが完全に信頼されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="45541-129">Specifying the application domain manager type requires the application to have full trust.</span></span> <span data-ttu-id="45541-130">(たとえば、デスクトップで実行されているアプリケーションには完全な信頼があります)。アプリケーションが完全に信頼されていない場合は、<xref:System.TypeLoadException> がスローされます。</span><span class="sxs-lookup"><span data-stu-id="45541-130">(For example, an application running on the desktop has full trust.) If the application does not have full trust, a <xref:System.TypeLoadException> is thrown.</span></span>  
  
 <span data-ttu-id="45541-131">アセンブリ表示名の形式については、「<xref:System.Reflection.Assembly.FullName%2A?displayProperty=nameWithType> プロパティ」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="45541-131">For the format of the assembly display name, see the <xref:System.Reflection.Assembly.FullName%2A?displayProperty=nameWithType> property.</span></span>  
  
 <span data-ttu-id="45541-132">この構成要素は、.NET Framework 4 以降でのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="45541-132">This configuration element is available only in the .NET Framework 4 and later.</span></span>  
  
## <a name="example"></a><span data-ttu-id="45541-133">例</span><span class="sxs-lookup"><span data-stu-id="45541-133">Example</span></span>  
 <span data-ttu-id="45541-134">次の例では、プロセスの既定のアプリケーションドメインのアプリケーションドメインマネージャーが `AdMgrExample` アセンブリの `MyMgr` の種類であることを指定する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="45541-134">The following example shows how to specify that the application domain manager for the default application domain of a process is the `MyMgr` type in the `AdMgrExample` assembly.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <appDomainManagerType value="MyMgr" />  
      <appDomainManagerAssembly   
         value="AdMgrExample, Version=1.0.0.0, Culture=neutral, PublicKeyToken=6856bccf150f00b3" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="45541-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="45541-135">See also</span></span>

- <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType>
- <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType>
- [<span data-ttu-id="45541-136">\<appDomainManagerType > 要素</span><span class="sxs-lookup"><span data-stu-id="45541-136">\<appDomainManagerType> Element</span></span>](appdomainmanagertype-element.md)
- [<span data-ttu-id="45541-137">ランタイム設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="45541-137">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="45541-138">構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="45541-138">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="45541-139">SetAppDomainManagerType メソッド</span><span class="sxs-lookup"><span data-stu-id="45541-139">SetAppDomainManagerType Method</span></span>](../../../unmanaged-api/hosting/iclrcontrol-setappdomainmanagertype-method.md)
