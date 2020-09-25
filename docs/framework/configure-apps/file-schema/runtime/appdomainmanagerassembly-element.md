---
title: <appDomainManagerAssembly> 要素
ms.date: 03/30/2017
helpviewer_keywords:
- <appDomainManagerAssembly> element
- appDomainManagerAssembly element
ms.assetid: c7c56e39-a700-44f5-b94e-411bfce339d9
ms.openlocfilehash: 1716b11106775bed2c0d6ccb62e8d5b032b6e8be
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91176137"
---
# <a name="appdomainmanagerassembly-element"></a><span data-ttu-id="41348-102">\<appDomainManagerAssembly> 要素</span><span class="sxs-lookup"><span data-stu-id="41348-102">\<appDomainManagerAssembly> Element</span></span>

<span data-ttu-id="41348-103">プロセスにおける既定のアプリケーション ドメインのアプリケーション ドメイン マネージャーを提供するアセンブリを指定します。</span><span class="sxs-lookup"><span data-stu-id="41348-103">Specifies the assembly that provides the application domain manager for the default application domain in the process.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<appDomainManagerAssembly>**  
  
## <a name="syntax"></a><span data-ttu-id="41348-104">構文</span><span class="sxs-lookup"><span data-stu-id="41348-104">Syntax</span></span>  
  
```xml  
<appDomainManagerAssembly
   value="assembly display name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="41348-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="41348-105">Attributes and Elements</span></span>  

 <span data-ttu-id="41348-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="41348-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="41348-107">属性</span><span class="sxs-lookup"><span data-stu-id="41348-107">Attributes</span></span>  
  
|<span data-ttu-id="41348-108">属性</span><span class="sxs-lookup"><span data-stu-id="41348-108">Attribute</span></span>|<span data-ttu-id="41348-109">説明</span><span class="sxs-lookup"><span data-stu-id="41348-109">Description</span></span>|  
|---------------|-----------------|  
|`value`|<span data-ttu-id="41348-110">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="41348-110">Required attribute.</span></span> <span data-ttu-id="41348-111">プロセスの既定のアプリケーションドメインのアプリケーションドメインマネージャーを提供するアセンブリの表示名を指定します。</span><span class="sxs-lookup"><span data-stu-id="41348-111">Specifies the display name of the assembly that provides the application domain manager for the default application domain in the process.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="41348-112">子要素</span><span class="sxs-lookup"><span data-stu-id="41348-112">Child Elements</span></span>  

 <span data-ttu-id="41348-113">なし。</span><span class="sxs-lookup"><span data-stu-id="41348-113">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="41348-114">親要素</span><span class="sxs-lookup"><span data-stu-id="41348-114">Parent Elements</span></span>  
  
|<span data-ttu-id="41348-115">要素</span><span class="sxs-lookup"><span data-stu-id="41348-115">Element</span></span>|<span data-ttu-id="41348-116">説明</span><span class="sxs-lookup"><span data-stu-id="41348-116">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="41348-117">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="41348-117">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="41348-118">アセンブリのバインディングとガベージ コレクションに関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="41348-118">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="41348-119">解説</span><span class="sxs-lookup"><span data-stu-id="41348-119">Remarks</span></span>  

 <span data-ttu-id="41348-120">アプリケーションドメインマネージャーの種類を指定するには、この要素と要素の両方を指定する必要があり [\<appDomainManagerType>](appdomainmanagertype-element.md) ます。</span><span class="sxs-lookup"><span data-stu-id="41348-120">To specify the type of the application domain manager, you must specify both this element and the [\<appDomainManagerType>](appdomainmanagertype-element.md) element.</span></span> <span data-ttu-id="41348-121">これらの要素のいずれかが指定されていない場合、もう一方は無視されます。</span><span class="sxs-lookup"><span data-stu-id="41348-121">If either of these elements is not specified, the other is ignored.</span></span>  
  
 <span data-ttu-id="41348-122">既定のアプリケーションドメインが読み込まれると、 <xref:System.TypeLoadException> 指定したアセンブリが存在しない場合、またはアセンブリに要素によって指定された型が含まれていない場合にがスローされ、 [\<appDomainManagerType>](appdomainmanagertype-element.md) プロセスの開始に失敗します。</span><span class="sxs-lookup"><span data-stu-id="41348-122">When the default application domain is loaded, <xref:System.TypeLoadException> is thrown if the specified assembly does not exist or if the assembly does not contain the type specified by the [\<appDomainManagerType>](appdomainmanagertype-element.md) element; and the process fails to start.</span></span> <span data-ttu-id="41348-123">アセンブリが見つかってもバージョン情報が一致しない場合は、 <xref:System.IO.FileLoadException> がスローされます。</span><span class="sxs-lookup"><span data-stu-id="41348-123">If the assembly is found but the version information does not match, a <xref:System.IO.FileLoadException> is thrown.</span></span>  
  
 <span data-ttu-id="41348-124">既定のアプリケーションドメインに対してアプリケーションドメインマネージャーの種類を指定すると、既定のアプリケーションドメインから作成された他のアプリケーションドメインは、アプリケーションドメインマネージャーの種類を継承します。</span><span class="sxs-lookup"><span data-stu-id="41348-124">When you specify the application domain manager type for the default application domain, other application domains created from the default application domain inherit the application domain manager type.</span></span> <span data-ttu-id="41348-125">プロパティとプロパティを使用して、 <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType> <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType> 新しいアプリケーションドメインに別のアプリケーションドメインマネージャーの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="41348-125">Use the <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType> and <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType> properties to specify a different application domain manager type for a new application domain.</span></span>  
  
 <span data-ttu-id="41348-126">アプリケーションドメインマネージャーの種類を指定するには、アプリケーションが完全に信頼されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="41348-126">Specifying the application domain manager type requires the application to have full trust.</span></span> <span data-ttu-id="41348-127">(たとえば、デスクトップで実行されているアプリケーションには完全な信頼があります)。アプリケーションが完全に信頼されていない場合は、 <xref:System.TypeLoadException> がスローされます。</span><span class="sxs-lookup"><span data-stu-id="41348-127">(For example, an application running on the desktop has full trust.) If the application does not have full trust, a <xref:System.TypeLoadException> is thrown.</span></span>  
  
 <span data-ttu-id="41348-128">アセンブリ表示名の形式については、プロパティを参照してください <xref:System.Reflection.Assembly.FullName%2A?displayProperty=nameWithType> 。</span><span class="sxs-lookup"><span data-stu-id="41348-128">For the format of the assembly display name, see the <xref:System.Reflection.Assembly.FullName%2A?displayProperty=nameWithType> property.</span></span>  
  
 <span data-ttu-id="41348-129">この構成要素は、.NET Framework 4 以降でのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="41348-129">This configuration element is available only in the .NET Framework 4 and later.</span></span>  
  
## <a name="example"></a><span data-ttu-id="41348-130">例</span><span class="sxs-lookup"><span data-stu-id="41348-130">Example</span></span>  

 <span data-ttu-id="41348-131">次の例は、プロセスの既定のアプリケーションドメインのアプリケーションドメインマネージャーがアセンブリ内の型であることを指定する方法を示してい `MyMgr` `AdMgrExample` ます。</span><span class="sxs-lookup"><span data-stu-id="41348-131">The following example shows how to specify that the application domain manager for the default application domain of a process is the `MyMgr` type in the `AdMgrExample` assembly.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <appDomainManagerType value="MyMgr" />  
      <appDomainManagerAssembly
         value="AdMgrExample, Version=1.0.0.0, Culture=neutral, PublicKeyToken=6856bccf150f00b3" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="41348-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="41348-132">See also</span></span>

- <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType>
- <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType>
- [<span data-ttu-id="41348-133">\<appDomainManagerType> 要素</span><span class="sxs-lookup"><span data-stu-id="41348-133">\<appDomainManagerType> Element</span></span>](appdomainmanagertype-element.md)
- [<span data-ttu-id="41348-134">ランタイム設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="41348-134">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="41348-135">構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="41348-135">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="41348-136">SetAppDomainManagerType メソッド</span><span class="sxs-lookup"><span data-stu-id="41348-136">SetAppDomainManagerType Method</span></span>](../../../unmanaged-api/hosting/iclrcontrol-setappdomainmanagertype-method.md)
