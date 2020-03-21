---
title: <relativeBindForResources> 要素
ms.date: 03/30/2017
helpviewer_keywords:
- RelativeBindForResources element
- <relativeBindForResources> element
ms.assetid: 846ffa47-7257-4ce3-8cac-7ff627e0e34f
ms.openlocfilehash: cd49d424019a4e8422fee0ae16217d49cfc456b1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153907"
---
# <a name="relativebindforresources-element"></a><span data-ttu-id="48232-102">\<相対バインドフォーリソース>要素</span><span class="sxs-lookup"><span data-stu-id="48232-102">\<relativeBindForResources> Element</span></span>
<span data-ttu-id="48232-103">サテライト アセンブリのプローブを最適化します。</span><span class="sxs-lookup"><span data-stu-id="48232-103">Optimizes the probe for satellite assemblies.</span></span>  
  
<span data-ttu-id="48232-104">[**\<構成>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="48232-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="48232-105">&nbsp;&nbsp;[**\<ランタイム>**](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="48232-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="48232-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<リソース>を相対的に設定します。**</span><span class="sxs-lookup"><span data-stu-id="48232-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<relativeBindForResources>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="48232-107">構文</span><span class="sxs-lookup"><span data-stu-id="48232-107">Syntax</span></span>  
  
```xml
<relativeBindForResources
   enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="48232-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="48232-108">Attributes and Elements</span></span>  
 <span data-ttu-id="48232-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="48232-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="48232-110">属性</span><span class="sxs-lookup"><span data-stu-id="48232-110">Attributes</span></span>  
  
|<span data-ttu-id="48232-111">属性</span><span class="sxs-lookup"><span data-stu-id="48232-111">Attribute</span></span>|<span data-ttu-id="48232-112">説明</span><span class="sxs-lookup"><span data-stu-id="48232-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="48232-113">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="48232-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="48232-114">共通言語ランタイムがサテライト アセンブリのプローブを最適化するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="48232-114">Specifies whether the common language runtime optimizes the probe for satellite assemblies.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="48232-115">enabled 属性</span><span class="sxs-lookup"><span data-stu-id="48232-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="48232-116">Value</span><span class="sxs-lookup"><span data-stu-id="48232-116">Value</span></span>|<span data-ttu-id="48232-117">説明</span><span class="sxs-lookup"><span data-stu-id="48232-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="48232-118">ランタイムは、サテライト アセンブリのプローブを最適化しません。</span><span class="sxs-lookup"><span data-stu-id="48232-118">The runtime does not optimize the probe for satellite assemblies.</span></span> <span data-ttu-id="48232-119">これが既定値です。</span><span class="sxs-lookup"><span data-stu-id="48232-119">This is the default value.</span></span>|  
|`true`|<span data-ttu-id="48232-120">ランタイムは、サテライト アセンブリのプローブを最適化します。</span><span class="sxs-lookup"><span data-stu-id="48232-120">The runtime optimizes the probe for satellite assemblies.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="48232-121">子要素</span><span class="sxs-lookup"><span data-stu-id="48232-121">Child Elements</span></span>  
 <span data-ttu-id="48232-122">[なし] :</span><span class="sxs-lookup"><span data-stu-id="48232-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="48232-123">親要素</span><span class="sxs-lookup"><span data-stu-id="48232-123">Parent Elements</span></span>  
  
|<span data-ttu-id="48232-124">要素</span><span class="sxs-lookup"><span data-stu-id="48232-124">Element</span></span>|<span data-ttu-id="48232-125">説明</span><span class="sxs-lookup"><span data-stu-id="48232-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="48232-126">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="48232-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="48232-127">ランタイム初期化オプションに関する情報を含んでいます。</span><span class="sxs-lookup"><span data-stu-id="48232-127">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="48232-128">解説</span><span class="sxs-lookup"><span data-stu-id="48232-128">Remarks</span></span>  
 <span data-ttu-id="48232-129">一般に、リソース マネージャーは、「リソースの[パッケージ化とデプロイ](../../../resources/packaging-and-deploying-resources-in-desktop-apps.md)」トピックで説明されているように、リソースを調査します。</span><span class="sxs-lookup"><span data-stu-id="48232-129">In general, Resource Manager probes for resources, as documented in the [Packaging and Deploying Resources](../../../resources/packaging-and-deploying-resources-in-desktop-apps.md) topic.</span></span> <span data-ttu-id="48232-130">つまり、リソース マネージャーは、リソースの特定のローカライズされたバージョンを調査するときに、グローバル アセンブリ キャッシュを検索し、アプリケーションのコード ベースでカルチャ固有のフォルダーを検索し、サテライト アセンブリの Windows インストーラーを<xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType>照会し、イベントを発生させる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="48232-130">This means that when Resource Manager probes for a particular localized version of a resource, it may look in the global assembly cache, look in a culture-specific folder in the application's code base, query Windows Installer for satellite assemblies, and raise the <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> event.</span></span> <span data-ttu-id="48232-131">この`<relativeBindForResources>`要素は、リソース マネージャーがサテライト アセンブリを調査する方法を最適化します。</span><span class="sxs-lookup"><span data-stu-id="48232-131">The `<relativeBindForResources>` element optimizes the way in which Resource Manager probes for satellite assemblies.</span></span> <span data-ttu-id="48232-132">次の条件下でリソースを調査する場合、パフォーマンスが向上します。</span><span class="sxs-lookup"><span data-stu-id="48232-132">It can improve performance when probing for resources under the following conditions:</span></span>  
  
- <span data-ttu-id="48232-133">サテライト アセンブリがコード アセンブリと同じ場所に配置される場合。</span><span class="sxs-lookup"><span data-stu-id="48232-133">When the satellite assembly is deployed in the same location as the code assembly.</span></span> <span data-ttu-id="48232-134">つまり、コード アセンブリがグローバル アセンブリ キャッシュにインストールされている場合は、サテライト アセンブリもそこにインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="48232-134">In other words, if the code assembly is installed in the global assembly cache, the satellite assemblies must also be installed there.</span></span> <span data-ttu-id="48232-135">コード アセンブリがアプリケーションのコード ベースにインストールされている場合、サテライト アセンブリはコード ベースのカルチャ固有のフォルダーにもインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="48232-135">If the code assembly is installed in the application's code base, the satellite assemblies must also be installed in a culture-specific folder in the code base.</span></span>  
  
- <span data-ttu-id="48232-136">Windows インストーラが使用されていない場合、またはサテライト アセンブリのオンデマンド インストールに使用されることはほとんどありません。</span><span class="sxs-lookup"><span data-stu-id="48232-136">When Windows Installer is not used or is used only rarely for on-demand installation of satellite assemblies.</span></span>  
  
- <span data-ttu-id="48232-137">アプリケーション コードがイベントを<xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType>処理しない場合。</span><span class="sxs-lookup"><span data-stu-id="48232-137">When application code does not handle the <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> event.</span></span>  
  
 <span data-ttu-id="48232-138">次のように`enabled`、サテライト`true`アセンブリのリソース マネージャーのプローブを最適化する要素の属性を設定します。 `<relativeBindForResources>`</span><span class="sxs-lookup"><span data-stu-id="48232-138">Setting the `enabled` attribute of the `<relativeBindForResources>` element to `true` optimizes Resource Manager's probe for satellite assemblies as follows:</span></span>  
  
- <span data-ttu-id="48232-139">このサービスは、親コード アセンブリの場所を使用して、サテライト アセンブリをプローブします。</span><span class="sxs-lookup"><span data-stu-id="48232-139">It uses the location of the parent code assembly to probe for the satellite assembly.</span></span>  
  
- <span data-ttu-id="48232-140">Windows インストーラによるサテライト アセンブリのクエリは行われません。</span><span class="sxs-lookup"><span data-stu-id="48232-140">It does not query Windows Installer for satellite assemblies.</span></span>  
  
- <span data-ttu-id="48232-141"><xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType>イベントは発生しません。</span><span class="sxs-lookup"><span data-stu-id="48232-141">It does not raise the <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> event.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48232-142">関連項目</span><span class="sxs-lookup"><span data-stu-id="48232-142">See also</span></span>

- [<span data-ttu-id="48232-143">Packaging and Deploying Resources</span><span class="sxs-lookup"><span data-stu-id="48232-143">Packaging and Deploying Resources</span></span>](../../../resources/packaging-and-deploying-resources-in-desktop-apps.md)
- [<span data-ttu-id="48232-144">ランタイム設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="48232-144">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="48232-145">構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="48232-145">Configuration File Schema</span></span>](../index.md)
