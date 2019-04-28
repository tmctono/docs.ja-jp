---
title: <appDomainManagerAssembly> 要素
ms.date: 03/30/2017
helpviewer_keywords:
- <appDomainManagerAssembly> element
- appDomainManagerAssembly element
ms.assetid: c7c56e39-a700-44f5-b94e-411bfce339d9
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4fe1dfbd62a6967ae51031fa12f80e9c5563dc44
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61704922"
---
# <a name="appdomainmanagerassembly-element"></a><span data-ttu-id="3c24a-102">\<appDomainManagerAssembly > 要素</span><span class="sxs-lookup"><span data-stu-id="3c24a-102">\<appDomainManagerAssembly> Element</span></span>
<span data-ttu-id="3c24a-103">プロセスにおける既定のアプリケーション ドメインのアプリケーション ドメイン マネージャーを提供するアセンブリを指定します。</span><span class="sxs-lookup"><span data-stu-id="3c24a-103">Specifies the assembly that provides the application domain manager for the default application domain in the process.</span></span>  
  
 <span data-ttu-id="3c24a-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="3c24a-104">\<configuration></span></span>  
<span data-ttu-id="3c24a-105">\<runtime></span><span class="sxs-lookup"><span data-stu-id="3c24a-105">\<runtime></span></span>  
<span data-ttu-id="3c24a-106">\<appDomainManagerAssembly></span><span class="sxs-lookup"><span data-stu-id="3c24a-106">\<appDomainManagerAssembly></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3c24a-107">構文</span><span class="sxs-lookup"><span data-stu-id="3c24a-107">Syntax</span></span>  
  
```xml  
<appDomainManagerAssembly   
   value="assembly display name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3c24a-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="3c24a-108">Attributes and Elements</span></span>  
 <span data-ttu-id="3c24a-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="3c24a-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3c24a-110">属性</span><span class="sxs-lookup"><span data-stu-id="3c24a-110">Attributes</span></span>  
  
|<span data-ttu-id="3c24a-111">属性</span><span class="sxs-lookup"><span data-stu-id="3c24a-111">Attribute</span></span>|<span data-ttu-id="3c24a-112">説明</span><span class="sxs-lookup"><span data-stu-id="3c24a-112">Description</span></span>|  
|---------------|-----------------|  
|`value`|<span data-ttu-id="3c24a-113">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="3c24a-113">Required attribute.</span></span> <span data-ttu-id="3c24a-114">プロセスの既定のアプリケーション ドメインのアプリケーション ドメイン マネージャーを提供するアセンブリの表示名を指定します。</span><span class="sxs-lookup"><span data-stu-id="3c24a-114">Specifies the display name of the assembly that provides the application domain manager for the default application domain in the process.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3c24a-115">子要素</span><span class="sxs-lookup"><span data-stu-id="3c24a-115">Child Elements</span></span>  
 <span data-ttu-id="3c24a-116">なし。</span><span class="sxs-lookup"><span data-stu-id="3c24a-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3c24a-117">親要素</span><span class="sxs-lookup"><span data-stu-id="3c24a-117">Parent Elements</span></span>  
  
|<span data-ttu-id="3c24a-118">要素</span><span class="sxs-lookup"><span data-stu-id="3c24a-118">Element</span></span>|<span data-ttu-id="3c24a-119">説明</span><span class="sxs-lookup"><span data-stu-id="3c24a-119">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="3c24a-120">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="3c24a-120">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="3c24a-121">アセンブリのバインディングとガベージ コレクションに関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="3c24a-121">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3c24a-122">Remarks</span><span class="sxs-lookup"><span data-stu-id="3c24a-122">Remarks</span></span>  
 <span data-ttu-id="3c24a-123">アプリケーション ドメイン マネージャーの種類を指定するには、この両方の要素を指定する必要があります、 [ \<appDomainManagerType >](../../../../../docs/framework/configure-apps/file-schema/runtime/appdomainmanagertype-element.md)要素。</span><span class="sxs-lookup"><span data-stu-id="3c24a-123">To specify the type of the application domain manager, you must specify both this element and the [\<appDomainManagerType>](../../../../../docs/framework/configure-apps/file-schema/runtime/appdomainmanagertype-element.md) element.</span></span> <span data-ttu-id="3c24a-124">これらの要素のいずれかが指定されていない場合、その他は無視されます。</span><span class="sxs-lookup"><span data-stu-id="3c24a-124">If either of these elements is not specified, the other is ignored.</span></span>  
  
 <span data-ttu-id="3c24a-125">既定のアプリケーション ドメインが読み込まれるときに<xref:System.TypeLoadException>が、指定したアセンブリが存在しない場合、またはアセンブリに指定した型が含まれていない場合にスローされます、 [ \<appDomainManagerType >](../../../../../docs/framework/configure-apps/file-schema/runtime/appdomainmanagertype-element.md)要素とプロセスは、開始に失敗します。</span><span class="sxs-lookup"><span data-stu-id="3c24a-125">When the default application domain is loaded, <xref:System.TypeLoadException> is thrown if the specified assembly does not exist or if the assembly does not contain the type specified by the [\<appDomainManagerType>](../../../../../docs/framework/configure-apps/file-schema/runtime/appdomainmanagertype-element.md) element; and the process fails to start.</span></span> <span data-ttu-id="3c24a-126">アセンブリが見つかりましたが、バージョン情報が一致しない場合、<xref:System.IO.FileLoadException>がスローされます。</span><span class="sxs-lookup"><span data-stu-id="3c24a-126">If the assembly is found but the version information does not match, a <xref:System.IO.FileLoadException> is thrown.</span></span>  
  
 <span data-ttu-id="3c24a-127">既定のアプリケーション ドメインのアプリケーション ドメイン マネージャーの種類を指定すると、既定のアプリケーション ドメインから作成されたその他のアプリケーション ドメインは、アプリケーション ドメイン マネージャーの型を継承します。</span><span class="sxs-lookup"><span data-stu-id="3c24a-127">When you specify the application domain manager type for the default application domain, other application domains created from the default application domain inherit the application domain manager type.</span></span> <span data-ttu-id="3c24a-128">使用して、<xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType>と<xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType>プロパティを新しいアプリケーション ドメインの別のアプリケーション ドメイン マネージャーの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="3c24a-128">Use the <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType> and <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType> properties to specify a different application domain manager type for a new application domain.</span></span>  
  
 <span data-ttu-id="3c24a-129">アプリケーション ドメイン マネージャーの種類を指定するには、完全な信頼のアプリケーションが必要です。</span><span class="sxs-lookup"><span data-stu-id="3c24a-129">Specifying the application domain manager type requires the application to have full trust.</span></span> <span data-ttu-id="3c24a-130">(たとえば、デスクトップで実行されているアプリケーションは完全な信頼があります。)アプリケーションには、完全な信頼がない場合、<xref:System.TypeLoadException>がスローされます。</span><span class="sxs-lookup"><span data-stu-id="3c24a-130">(For example, an application running on the desktop has full trust.) If the application does not have full trust, a <xref:System.TypeLoadException> is thrown.</span></span>  
  
 <span data-ttu-id="3c24a-131">アセンブリの表示名の形式の場合、次を参照してください。、<xref:System.Reflection.Assembly.FullName%2A?displayProperty=nameWithType>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="3c24a-131">For the format of the assembly display name, see the <xref:System.Reflection.Assembly.FullName%2A?displayProperty=nameWithType> property.</span></span>  
  
 <span data-ttu-id="3c24a-132">この構成要素はでのみ使用できますが、[!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)]以降。</span><span class="sxs-lookup"><span data-stu-id="3c24a-132">This configuration element is available only in the [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] and later.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3c24a-133">例</span><span class="sxs-lookup"><span data-stu-id="3c24a-133">Example</span></span>  
 <span data-ttu-id="3c24a-134">次の例では、プロセスの既定のアプリケーション ドメインのアプリケーション ドメイン マネージャーを指定する方法を示しています、`MyMgr`で入力、`AdMgrExample`アセンブリ。</span><span class="sxs-lookup"><span data-stu-id="3c24a-134">The following example shows how to specify that the application domain manager for the default application domain of a process is the `MyMgr` type in the `AdMgrExample` assembly.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <appDomainManagerType value="MyMgr" />  
      <appDomainManagerAssembly   
         value="AdMgrExample, Version=1.0.0.0, Culture=neutral, PublicKeyToken=6856bccf150f00b3" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="3c24a-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="3c24a-135">See also</span></span>

- <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType>
- <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType>
- [<span data-ttu-id="3c24a-136">\<appDomainManagerType > 要素</span><span class="sxs-lookup"><span data-stu-id="3c24a-136">\<appDomainManagerType> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/appdomainmanagertype-element.md)
- [<span data-ttu-id="3c24a-137">ランタイム設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="3c24a-137">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="3c24a-138">構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="3c24a-138">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="3c24a-139">SetAppDomainManagerType メソッド</span><span class="sxs-lookup"><span data-stu-id="3c24a-139">SetAppDomainManagerType Method</span></span>](../../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-setappdomainmanagertype-method.md)
