---
title: <relativeBindForResources> 要素
ms.date: 03/30/2017
helpviewer_keywords:
- RelativeBindForResources element
- <relativeBindForResources> element
ms.assetid: 846ffa47-7257-4ce3-8cac-7ff627e0e34f
ms.openlocfilehash: cd49d424019a4e8422fee0ae16217d49cfc456b1
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "79153907"
---
# <a name="relativebindforresources-element"></a><span data-ttu-id="f3d9d-102">\<relativeBindForResources> 要素</span><span class="sxs-lookup"><span data-stu-id="f3d9d-102">\<relativeBindForResources> Element</span></span>
<span data-ttu-id="f3d9d-103">サテライト アセンブリのプローブを最適化します。</span><span class="sxs-lookup"><span data-stu-id="f3d9d-103">Optimizes the probe for satellite assemblies.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<relativeBindForResources>**  
  
## <a name="syntax"></a><span data-ttu-id="f3d9d-104">構文</span><span class="sxs-lookup"><span data-stu-id="f3d9d-104">Syntax</span></span>  
  
```xml
<relativeBindForResources
   enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f3d9d-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="f3d9d-105">Attributes and Elements</span></span>  
 <span data-ttu-id="f3d9d-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="f3d9d-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f3d9d-107">属性</span><span class="sxs-lookup"><span data-stu-id="f3d9d-107">Attributes</span></span>  
  
|<span data-ttu-id="f3d9d-108">属性</span><span class="sxs-lookup"><span data-stu-id="f3d9d-108">Attribute</span></span>|<span data-ttu-id="f3d9d-109">説明</span><span class="sxs-lookup"><span data-stu-id="f3d9d-109">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="f3d9d-110">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="f3d9d-110">Required attribute.</span></span><br /><br /> <span data-ttu-id="f3d9d-111">共通言語ランタイムがサテライトアセンブリのプローブを最適化するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="f3d9d-111">Specifies whether the common language runtime optimizes the probe for satellite assemblies.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="f3d9d-112">enabled 属性</span><span class="sxs-lookup"><span data-stu-id="f3d9d-112">enabled Attribute</span></span>  
  
|<span data-ttu-id="f3d9d-113">値</span><span class="sxs-lookup"><span data-stu-id="f3d9d-113">Value</span></span>|<span data-ttu-id="f3d9d-114">Description</span><span class="sxs-lookup"><span data-stu-id="f3d9d-114">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="f3d9d-115">ランタイムは、サテライトアセンブリのプローブを最適化しません。</span><span class="sxs-lookup"><span data-stu-id="f3d9d-115">The runtime does not optimize the probe for satellite assemblies.</span></span> <span data-ttu-id="f3d9d-116">これが既定値です。</span><span class="sxs-lookup"><span data-stu-id="f3d9d-116">This is the default value.</span></span>|  
|`true`|<span data-ttu-id="f3d9d-117">ランタイムは、サテライトアセンブリのプローブを最適化します。</span><span class="sxs-lookup"><span data-stu-id="f3d9d-117">The runtime optimizes the probe for satellite assemblies.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f3d9d-118">子要素</span><span class="sxs-lookup"><span data-stu-id="f3d9d-118">Child Elements</span></span>  
 <span data-ttu-id="f3d9d-119">なし。</span><span class="sxs-lookup"><span data-stu-id="f3d9d-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f3d9d-120">親要素</span><span class="sxs-lookup"><span data-stu-id="f3d9d-120">Parent Elements</span></span>  
  
|<span data-ttu-id="f3d9d-121">要素</span><span class="sxs-lookup"><span data-stu-id="f3d9d-121">Element</span></span>|<span data-ttu-id="f3d9d-122">Description</span><span class="sxs-lookup"><span data-stu-id="f3d9d-122">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="f3d9d-123">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="f3d9d-123">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="f3d9d-124">ランタイム初期化オプションに関する情報を含んでいます。</span><span class="sxs-lookup"><span data-stu-id="f3d9d-124">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f3d9d-125">解説</span><span class="sxs-lookup"><span data-stu-id="f3d9d-125">Remarks</span></span>  
 <span data-ttu-id="f3d9d-126">一般に、リソースの[パッケージ化とデプロイ](../../../resources/packaging-and-deploying-resources-in-desktop-apps.md)に関するトピックで説明されているように、Resource Manager はリソースをプローブします。</span><span class="sxs-lookup"><span data-stu-id="f3d9d-126">In general, Resource Manager probes for resources, as documented in the [Packaging and Deploying Resources](../../../resources/packaging-and-deploying-resources-in-desktop-apps.md) topic.</span></span> <span data-ttu-id="f3d9d-127">これは、resource Manager が特定のローカライズされたバージョンのリソースをプローブするときに、グローバルアセンブリキャッシュを検索し、アプリケーションのコードベースでカルチャ固有のフォルダーを検索し、サテライトアセンブリの Windows インストーラーを照会して、イベントを発生させることができることを意味し <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> ます。</span><span class="sxs-lookup"><span data-stu-id="f3d9d-127">This means that when Resource Manager probes for a particular localized version of a resource, it may look in the global assembly cache, look in a culture-specific folder in the application's code base, query Windows Installer for satellite assemblies, and raise the <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> event.</span></span> <span data-ttu-id="f3d9d-128">要素は、 `<relativeBindForResources>` リソースマネージャーがサテライトアセンブリをプローブする方法を最適化します。</span><span class="sxs-lookup"><span data-stu-id="f3d9d-128">The `<relativeBindForResources>` element optimizes the way in which Resource Manager probes for satellite assemblies.</span></span> <span data-ttu-id="f3d9d-129">次の条件下でリソースを調査するときにパフォーマンスを向上させることができます。</span><span class="sxs-lookup"><span data-stu-id="f3d9d-129">It can improve performance when probing for resources under the following conditions:</span></span>  
  
- <span data-ttu-id="f3d9d-130">サテライトアセンブリがコードアセンブリと同じ場所に配置されている場合。</span><span class="sxs-lookup"><span data-stu-id="f3d9d-130">When the satellite assembly is deployed in the same location as the code assembly.</span></span> <span data-ttu-id="f3d9d-131">つまり、コードアセンブリがグローバルアセンブリキャッシュにインストールされている場合は、サテライトアセンブリもインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f3d9d-131">In other words, if the code assembly is installed in the global assembly cache, the satellite assemblies must also be installed there.</span></span> <span data-ttu-id="f3d9d-132">コードアセンブリがアプリケーションのコードベースにインストールされている場合は、サテライトアセンブリをコードベースのカルチャ固有のフォルダーにもインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f3d9d-132">If the code assembly is installed in the application's code base, the satellite assemblies must also be installed in a culture-specific folder in the code base.</span></span>  
  
- <span data-ttu-id="f3d9d-133">Windows インストーラーが使用されていない場合、またはサテライトアセンブリのオンデマンドインストールではあまり使用されない場合。</span><span class="sxs-lookup"><span data-stu-id="f3d9d-133">When Windows Installer is not used or is used only rarely for on-demand installation of satellite assemblies.</span></span>  
  
- <span data-ttu-id="f3d9d-134">アプリケーションコードがイベントを処理しない場合 <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> 。</span><span class="sxs-lookup"><span data-stu-id="f3d9d-134">When application code does not handle the <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> event.</span></span>  
  
 <span data-ttu-id="f3d9d-135">`enabled`要素の属性 `<relativeBindForResources>` をに設定すると、次のように、 `true` サテライトアセンブリのリソースマネージャーのプローブが最適化されます。</span><span class="sxs-lookup"><span data-stu-id="f3d9d-135">Setting the `enabled` attribute of the `<relativeBindForResources>` element to `true` optimizes Resource Manager's probe for satellite assemblies as follows:</span></span>  
  
- <span data-ttu-id="f3d9d-136">親コードアセンブリの場所を使用して、サテライトアセンブリをプローブします。</span><span class="sxs-lookup"><span data-stu-id="f3d9d-136">It uses the location of the parent code assembly to probe for the satellite assembly.</span></span>  
  
- <span data-ttu-id="f3d9d-137">サテライトアセンブリの Windows インストーラーに対してはクエリを実行しません。</span><span class="sxs-lookup"><span data-stu-id="f3d9d-137">It does not query Windows Installer for satellite assemblies.</span></span>  
  
- <span data-ttu-id="f3d9d-138">イベントは発生しません <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> 。</span><span class="sxs-lookup"><span data-stu-id="f3d9d-138">It does not raise the <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> event.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3d9d-139">関連項目</span><span class="sxs-lookup"><span data-stu-id="f3d9d-139">See also</span></span>

- [<span data-ttu-id="f3d9d-140">リソースのパッケージ化と配置</span><span class="sxs-lookup"><span data-stu-id="f3d9d-140">Packaging and Deploying Resources</span></span>](../../../resources/packaging-and-deploying-resources-in-desktop-apps.md)
- [<span data-ttu-id="f3d9d-141">ランタイム設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="f3d9d-141">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="f3d9d-142">構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="f3d9d-142">Configuration File Schema</span></span>](../index.md)
