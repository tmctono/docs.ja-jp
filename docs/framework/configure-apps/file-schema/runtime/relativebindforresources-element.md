---
title: <relativeBindForResources> 要素
ms.date: 03/30/2017
helpviewer_keywords:
- RelativeBindForResources element
- <relativeBindForResources> element
ms.assetid: 846ffa47-7257-4ce3-8cac-7ff627e0e34f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 859e8a12421ea92aa48c54317e052683eb8e83f8
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/21/2019
ms.locfileid: "69663485"
---
# <a name="relativebindforresources-element"></a><span data-ttu-id="29b08-102">\<relativeBindForResources> 要素</span><span class="sxs-lookup"><span data-stu-id="29b08-102">\<relativeBindForResources> Element</span></span>
<span data-ttu-id="29b08-103">サテライト アセンブリのプローブを最適化します。</span><span class="sxs-lookup"><span data-stu-id="29b08-103">Optimizes the probe for satellite assemblies.</span></span>  
  
 <span data-ttu-id="29b08-104">\<configuration> 要素</span><span class="sxs-lookup"><span data-stu-id="29b08-104">\<configuration> Element</span></span>  
<span data-ttu-id="29b08-105">\<runtime> 要素</span><span class="sxs-lookup"><span data-stu-id="29b08-105">\<runtime> Element</span></span>  
<span data-ttu-id="29b08-106">\<relativeBindForResources> 要素</span><span class="sxs-lookup"><span data-stu-id="29b08-106">\<relativeBindForResources> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="29b08-107">構文</span><span class="sxs-lookup"><span data-stu-id="29b08-107">Syntax</span></span>  
  
```xml
<relativeBindForResources    
   enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="29b08-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="29b08-108">Attributes and Elements</span></span>  
 <span data-ttu-id="29b08-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="29b08-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="29b08-110">属性</span><span class="sxs-lookup"><span data-stu-id="29b08-110">Attributes</span></span>  
  
|<span data-ttu-id="29b08-111">属性</span><span class="sxs-lookup"><span data-stu-id="29b08-111">Attribute</span></span>|<span data-ttu-id="29b08-112">説明</span><span class="sxs-lookup"><span data-stu-id="29b08-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="29b08-113">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="29b08-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="29b08-114">共通言語ランタイムがサテライトアセンブリのプローブを最適化するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="29b08-114">Specifies whether the common language runtime optimizes the probe for satellite assemblies.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="29b08-115">enabled 属性</span><span class="sxs-lookup"><span data-stu-id="29b08-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="29b08-116">値</span><span class="sxs-lookup"><span data-stu-id="29b08-116">Value</span></span>|<span data-ttu-id="29b08-117">説明</span><span class="sxs-lookup"><span data-stu-id="29b08-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="29b08-118">ランタイムは、サテライトアセンブリのプローブを最適化しません。</span><span class="sxs-lookup"><span data-stu-id="29b08-118">The runtime does not optimize the probe for satellite assemblies.</span></span> <span data-ttu-id="29b08-119">これが既定値です。</span><span class="sxs-lookup"><span data-stu-id="29b08-119">This is the default value.</span></span>|  
|`true`|<span data-ttu-id="29b08-120">ランタイムは、サテライトアセンブリのプローブを最適化します。</span><span class="sxs-lookup"><span data-stu-id="29b08-120">The runtime optimizes the probe for satellite assemblies.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="29b08-121">子要素</span><span class="sxs-lookup"><span data-stu-id="29b08-121">Child Elements</span></span>  
 <span data-ttu-id="29b08-122">なし。</span><span class="sxs-lookup"><span data-stu-id="29b08-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="29b08-123">親要素</span><span class="sxs-lookup"><span data-stu-id="29b08-123">Parent Elements</span></span>  
  
|<span data-ttu-id="29b08-124">要素</span><span class="sxs-lookup"><span data-stu-id="29b08-124">Element</span></span>|<span data-ttu-id="29b08-125">説明</span><span class="sxs-lookup"><span data-stu-id="29b08-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="29b08-126">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="29b08-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="29b08-127">ランタイム初期化オプションに関する情報を含んでいます。</span><span class="sxs-lookup"><span data-stu-id="29b08-127">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="29b08-128">Remarks</span><span class="sxs-lookup"><span data-stu-id="29b08-128">Remarks</span></span>  
 <span data-ttu-id="29b08-129">一般に、リソースの[パッケージ化とデプロイ](../../../resources/packaging-and-deploying-resources-in-desktop-apps.md)に関するトピックで説明されているように、Resource Manager はリソースをプローブします。</span><span class="sxs-lookup"><span data-stu-id="29b08-129">In general, Resource Manager probes for resources, as documented in the [Packaging and Deploying Resources](../../../resources/packaging-and-deploying-resources-in-desktop-apps.md) topic.</span></span> <span data-ttu-id="29b08-130">これは、resource Manager が特定のローカライズされたバージョンのリソースをプローブするときに、グローバルアセンブリキャッシュを検索し、アプリケーションのコードベースでカルチャ固有のフォルダーを検索し、サテライトアセンブリに対してクエリ Windows インストーラーを実行し、<xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType>イベント。</span><span class="sxs-lookup"><span data-stu-id="29b08-130">This means that when Resource Manager probes for a particular localized version of a resource, it may look in the global assembly cache, look in a culture-specific folder in the application's code base, query Windows Installer for satellite assemblies, and raise the <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> event.</span></span> <span data-ttu-id="29b08-131">要素`<relativeBindForResources>`は、リソースマネージャーがサテライトアセンブリをプローブする方法を最適化します。</span><span class="sxs-lookup"><span data-stu-id="29b08-131">The `<relativeBindForResources>` element optimizes the way in which Resource Manager probes for satellite assemblies.</span></span> <span data-ttu-id="29b08-132">次の条件下でリソースを調査するときにパフォーマンスを向上させることができます。</span><span class="sxs-lookup"><span data-stu-id="29b08-132">It can improve performance when probing for resources under the following conditions:</span></span>  
  
- <span data-ttu-id="29b08-133">サテライトアセンブリがコードアセンブリと同じ場所に配置されている場合。</span><span class="sxs-lookup"><span data-stu-id="29b08-133">When the satellite assembly is deployed in the same location as the code assembly.</span></span> <span data-ttu-id="29b08-134">つまり、コードアセンブリがグローバルアセンブリキャッシュにインストールされている場合は、サテライトアセンブリもインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="29b08-134">In other words, if the code assembly is installed in the global assembly cache, the satellite assemblies must also be installed there.</span></span> <span data-ttu-id="29b08-135">コードアセンブリがアプリケーションのコードベースにインストールされている場合は、サテライトアセンブリをコードベースのカルチャ固有のフォルダーにもインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="29b08-135">If the code assembly is installed in the application's code base, the satellite assemblies must also be installed in a culture-specific folder in the code base.</span></span>  
  
- <span data-ttu-id="29b08-136">Windows インストーラーが使用されていない場合、またはサテライトアセンブリのオンデマンドインストールではあまり使用されない場合。</span><span class="sxs-lookup"><span data-stu-id="29b08-136">When Windows Installer is not used or is used only rarely for on-demand installation of satellite assemblies.</span></span>  
  
- <span data-ttu-id="29b08-137">アプリケーションコードがイベントを<xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType>処理しない場合。</span><span class="sxs-lookup"><span data-stu-id="29b08-137">When application code does not handle the <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> event.</span></span>  
  
 <span data-ttu-id="29b08-138">要素の`enabled`属性をに`<relativeBindForResources>`設定する`true`と、次のように、サテライトアセンブリのリソースマネージャーのプローブが最適化されます。</span><span class="sxs-lookup"><span data-stu-id="29b08-138">Setting the `enabled` attribute of the `<relativeBindForResources>` element to `true` optimizes Resource Manager's probe for satellite assemblies as follows:</span></span>  
  
- <span data-ttu-id="29b08-139">親コードアセンブリの場所を使用して、サテライトアセンブリをプローブします。</span><span class="sxs-lookup"><span data-stu-id="29b08-139">It uses the location of the parent code assembly to probe for the satellite assembly.</span></span>  
  
- <span data-ttu-id="29b08-140">サテライトアセンブリの Windows インストーラーに対してはクエリを実行しません。</span><span class="sxs-lookup"><span data-stu-id="29b08-140">It does not query Windows Installer for satellite assemblies.</span></span>  
  
- <span data-ttu-id="29b08-141">イベントは<xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType>発生しません。</span><span class="sxs-lookup"><span data-stu-id="29b08-141">It does not raise the <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> event.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29b08-142">関連項目</span><span class="sxs-lookup"><span data-stu-id="29b08-142">See also</span></span>

- [<span data-ttu-id="29b08-143">リソースのパッケージ化と配置</span><span class="sxs-lookup"><span data-stu-id="29b08-143">Packaging and Deploying Resources</span></span>](../../../resources/packaging-and-deploying-resources-in-desktop-apps.md)
- [<span data-ttu-id="29b08-144">ランタイム設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="29b08-144">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="29b08-145">構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="29b08-145">Configuration File Schema</span></span>](../index.md)
