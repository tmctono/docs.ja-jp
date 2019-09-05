---
title: <appDomainManagerType> 要素
ms.date: 03/30/2017
helpviewer_keywords:
- appDomainManagerType element
- <appDomainManagerType> element
ms.assetid: ae8d5a7e-e7f7-47f7-98d9-455cc243a322
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7ffb297cc38f20917e720b216607e9ccfc966866
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252840"
---
# <a name="appdomainmanagertype-element"></a><span data-ttu-id="64da1-102">\<appDomainManagerType > 要素</span><span class="sxs-lookup"><span data-stu-id="64da1-102">\<appDomainManagerType> Element</span></span>
<span data-ttu-id="64da1-103">既定のアプリケーション ドメインのアプリケーション ドメイン マネージャーの役割を果たす種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="64da1-103">Specifies the type that serves as the application domain manager for the default application domain.</span></span>  
  
<span data-ttu-id="64da1-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="64da1-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="64da1-105">&nbsp;&nbsp;[ **\<ランタイム >** ](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="64da1-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="64da1-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<appDomainManagerType>**</span><span class="sxs-lookup"><span data-stu-id="64da1-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<appDomainManagerType>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="64da1-107">構文</span><span class="sxs-lookup"><span data-stu-id="64da1-107">Syntax</span></span>  
  
```xml  
<appDomainManagerAssembly   
   value="type name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="64da1-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="64da1-108">Attributes and Elements</span></span>  
 <span data-ttu-id="64da1-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="64da1-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="64da1-110">属性</span><span class="sxs-lookup"><span data-stu-id="64da1-110">Attributes</span></span>  
  
|<span data-ttu-id="64da1-111">属性</span><span class="sxs-lookup"><span data-stu-id="64da1-111">Attribute</span></span>|<span data-ttu-id="64da1-112">説明</span><span class="sxs-lookup"><span data-stu-id="64da1-112">Description</span></span>|  
|---------------|-----------------|  
|`value`|<span data-ttu-id="64da1-113">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="64da1-113">Required attribute.</span></span> <span data-ttu-id="64da1-114">プロセス内の既定のアプリケーションドメインのアプリケーションドメインマネージャーとして機能する、名前空間を含む型の名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="64da1-114">Specifies the name of the type, including the namespace, that serves as the application domain manager for the default application domain in the process.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="64da1-115">子要素</span><span class="sxs-lookup"><span data-stu-id="64da1-115">Child Elements</span></span>  
 <span data-ttu-id="64da1-116">なし。</span><span class="sxs-lookup"><span data-stu-id="64da1-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="64da1-117">親要素</span><span class="sxs-lookup"><span data-stu-id="64da1-117">Parent Elements</span></span>  
  
|<span data-ttu-id="64da1-118">要素</span><span class="sxs-lookup"><span data-stu-id="64da1-118">Element</span></span>|<span data-ttu-id="64da1-119">説明</span><span class="sxs-lookup"><span data-stu-id="64da1-119">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="64da1-120">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="64da1-120">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="64da1-121">アセンブリのバインディングとガベージ コレクションに関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="64da1-121">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="64da1-122">Remarks</span><span class="sxs-lookup"><span data-stu-id="64da1-122">Remarks</span></span>  
 <span data-ttu-id="64da1-123">アプリケーションドメインマネージャーの種類を指定するには、この要素と[ \<appDomainManagerAssembly >](appdomainmanagerassembly-element.md)要素の両方を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="64da1-123">To specify the type of the application domain manager, you must specify both this element and the [\<appDomainManagerAssembly>](appdomainmanagerassembly-element.md) element.</span></span> <span data-ttu-id="64da1-124">これらの要素のいずれかが指定されていない場合、もう一方は無視されます。</span><span class="sxs-lookup"><span data-stu-id="64da1-124">If either of these elements is not specified, the other is ignored.</span></span>  
  
 <span data-ttu-id="64da1-125">既定のアプリケーションドメインが読み込まれる<xref:System.TypeLoadException>と、指定された型が[ \<appDomainManagerAssembly >](appdomainmanagerassembly-element.md)要素によって指定されたアセンブリに存在しない場合にがスローされ、プロセスを開始できません。</span><span class="sxs-lookup"><span data-stu-id="64da1-125">When the default application domain is loaded, <xref:System.TypeLoadException> is thrown if the specified type does not exist in the assembly that is specified by the [\<appDomainManagerAssembly>](appdomainmanagerassembly-element.md) element; and the process fails to start.</span></span>  
  
 <span data-ttu-id="64da1-126">既定のアプリケーションドメインに対してアプリケーションドメインマネージャーの種類を指定すると、既定のアプリケーションドメインから作成された他のアプリケーションドメインは、アプリケーションドメインマネージャーの種類を継承します。</span><span class="sxs-lookup"><span data-stu-id="64da1-126">When you specify the application domain manager type for the default application domain, other application domains created from the default application domain inherit the application domain manager type.</span></span> <span data-ttu-id="64da1-127"><xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType>プロパティと<xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType>プロパティを使用して、新しいアプリケーションドメインに別のアプリケーションドメインマネージャーの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="64da1-127">Use the <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType> and <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType> properties to specify a different application domain manager type for a new application domain.</span></span>  
  
 <span data-ttu-id="64da1-128">アプリケーションドメインマネージャーの種類を指定するには、アプリケーションが完全に信頼されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="64da1-128">Specifying the application domain manager type requires the application to have full trust.</span></span> <span data-ttu-id="64da1-129">(たとえば、デスクトップで実行されているアプリケーションには完全な信頼があります)。アプリケーションが完全に<xref:System.TypeLoadException>信頼されていない場合は、がスローされます。</span><span class="sxs-lookup"><span data-stu-id="64da1-129">(For example, an application running on the desktop has full trust.) If the application does not have full trust, a <xref:System.TypeLoadException> is thrown.</span></span>  
  
 <span data-ttu-id="64da1-130">型と名前空間の形式は、 <xref:System.Type.FullName%2A?displayProperty=nameWithType>プロパティで使用される形式と同じです。</span><span class="sxs-lookup"><span data-stu-id="64da1-130">The format of the type and namespace is the same format that is used for the <xref:System.Type.FullName%2A?displayProperty=nameWithType> property.</span></span>  
  
 <span data-ttu-id="64da1-131">この構成要素は、.NET Framework 4 以降でのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="64da1-131">This configuration element is available only in the .NET Framework 4 and later.</span></span>  
  
## <a name="example"></a><span data-ttu-id="64da1-132">例</span><span class="sxs-lookup"><span data-stu-id="64da1-132">Example</span></span>  
 <span data-ttu-id="64da1-133">次の例は、プロセスの既定のアプリケーションドメインのアプリケーションドメインマネージャーが`MyMgr` `AdMgrExample`アセンブリ内の型であることを指定する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="64da1-133">The following example shows how to specify that the application domain manager for the default application domain of a process is the `MyMgr` type in the `AdMgrExample` assembly.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <appDomainManagerType value="MyMgr" />  
      <appDomainManagerAssembly   
         value="AdMgrExample, Version=1.0.0.0, Culture=neutral, PublicKeyToken=6856bccf150f00b3" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="64da1-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="64da1-134">See also</span></span>

- <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType>
- <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType>
- [<span data-ttu-id="64da1-135">\<appDomainManagerAssembly > 要素</span><span class="sxs-lookup"><span data-stu-id="64da1-135">\<appDomainManagerAssembly> Element</span></span>](appdomainmanagerassembly-element.md)
- [<span data-ttu-id="64da1-136">ランタイム設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="64da1-136">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="64da1-137">構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="64da1-137">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="64da1-138">SetAppDomainManagerType メソッド</span><span class="sxs-lookup"><span data-stu-id="64da1-138">SetAppDomainManagerType Method</span></span>](../../../unmanaged-api/hosting/iclrcontrol-setappdomainmanagertype-method.md)
