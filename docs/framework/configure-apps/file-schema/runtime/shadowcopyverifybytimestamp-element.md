---
title: <shadowCopyVerifyByTimestamp> 要素
ms.date: 03/30/2017
helpviewer_keywords:
- <shadowCopyTimeStampVerification> element
- shadowCopyTimeStampVerification element
ms.assetid: 2f1648e5-997b-435e-a4f9-d236c574c66c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4ad61b3824b8155cf3f68f61865891c023b4cf32
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61674013"
---
# <a name="shadowcopyverifybytimestamp-element"></a><span data-ttu-id="5770c-102">\<shadowCopyVerifyByTimestamp> 要素</span><span class="sxs-lookup"><span data-stu-id="5770c-102">\<shadowCopyVerifyByTimestamp> Element</span></span>
<span data-ttu-id="5770c-103">シャドウ コピーが [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] で導入された既定の起動の動作を使用するか、.NET Framework の以前のバージョンの起動の動作に戻すかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="5770c-103">Specifies whether shadow copying uses the default startup behavior introduced in the [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], or reverts to the startup behavior of earlier versions of the .NET Framework.</span></span>  
  
 <span data-ttu-id="5770c-104">\<configuration > 要素</span><span class="sxs-lookup"><span data-stu-id="5770c-104">\<configuration> Element</span></span>  
<span data-ttu-id="5770c-105">\<ランタイム > 要素</span><span class="sxs-lookup"><span data-stu-id="5770c-105">\<runtime> Element</span></span>  
<span data-ttu-id="5770c-106">\<shadowCopyVerifyByTimestamp> 要素</span><span class="sxs-lookup"><span data-stu-id="5770c-106">\<shadowCopyVerifyByTimestamp> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5770c-107">構文</span><span class="sxs-lookup"><span data-stu-id="5770c-107">Syntax</span></span>  
  
```xml  
<shadowCopyVerifyByTimestamp enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5770c-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="5770c-108">Attributes and Elements</span></span>  
 <span data-ttu-id="5770c-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="5770c-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5770c-110">属性</span><span class="sxs-lookup"><span data-stu-id="5770c-110">Attributes</span></span>  
  
|<span data-ttu-id="5770c-111">属性</span><span class="sxs-lookup"><span data-stu-id="5770c-111">Attribute</span></span>|<span data-ttu-id="5770c-112">説明</span><span class="sxs-lookup"><span data-stu-id="5770c-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5770c-113">enabled</span><span class="sxs-lookup"><span data-stu-id="5770c-113">enabled</span></span>|<span data-ttu-id="5770c-114">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="5770c-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="5770c-115">アセンブリがアセンブリをシャドウ コピーする前に更新されているかどうかを判断する、開始するときにシャドウ コピーを使用するアプリケーション ドメインがアセンブリのタイムスタンプを比較するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="5770c-115">Specifies whether application domains that use shadow copying compare assembly time stamps when starting up, to determine whether an assembly has been updated before shadow copying the assembly.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="5770c-116">enabled 属性</span><span class="sxs-lookup"><span data-stu-id="5770c-116">enabled Attribute</span></span>  
  
|<span data-ttu-id="5770c-117">値</span><span class="sxs-lookup"><span data-stu-id="5770c-117">Value</span></span>|<span data-ttu-id="5770c-118">説明</span><span class="sxs-lookup"><span data-stu-id="5770c-118">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="5770c-119">true</span><span class="sxs-lookup"><span data-stu-id="5770c-119">true</span></span>|<span data-ttu-id="5770c-120">起動時に、前回シャドウ コピーのディレクトリにコピーされたとき以降に更新されたアセンブリだけをコピーします。</span><span class="sxs-lookup"><span data-stu-id="5770c-120">At startup, copies only assemblies that have been updated since they were last copied to the shadow copy directory.</span></span> <span data-ttu-id="5770c-121">これは、既定値は、[!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="5770c-121">This is the default for the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)].</span></span>|  
|<span data-ttu-id="5770c-122">False</span><span class="sxs-lookup"><span data-stu-id="5770c-122">false</span></span>|<span data-ttu-id="5770c-123">起動時にすべてのファイルにコピーされましたが、.NET Framework の以前のバージョンの起動の動作に戻ります。</span><span class="sxs-lookup"><span data-stu-id="5770c-123">Reverts to the startup behavior of previous versions of the .NET Framework, which was to copy all files at startup.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5770c-124">子要素</span><span class="sxs-lookup"><span data-stu-id="5770c-124">Child Elements</span></span>  
 <span data-ttu-id="5770c-125">なし。</span><span class="sxs-lookup"><span data-stu-id="5770c-125">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5770c-126">親要素</span><span class="sxs-lookup"><span data-stu-id="5770c-126">Parent Elements</span></span>  
  
|<span data-ttu-id="5770c-127">要素</span><span class="sxs-lookup"><span data-stu-id="5770c-127">Element</span></span>|<span data-ttu-id="5770c-128">説明</span><span class="sxs-lookup"><span data-stu-id="5770c-128">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="5770c-129">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="5770c-129">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="5770c-130">アセンブリのバインディングとガベージ コレクションに関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="5770c-130">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5770c-131">Remarks</span><span class="sxs-lookup"><span data-stu-id="5770c-131">Remarks</span></span>  
 <span data-ttu-id="5770c-132">以降では、[!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)]アセンブリのシャドウ コピーの場合は、そのタイムスタンプが前回、シャドウ コピーのディレクトリにコピーされたとき以降に変更されたことを示します。</span><span class="sxs-lookup"><span data-stu-id="5770c-132">Starting with the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)], assemblies are shadow copied only if their time stamps indicate that they have changed since they were last copied to the shadow copy directory.</span></span> <span data-ttu-id="5770c-133">」の説明に従って、シャドウ コピーを使用する多くのアプリケーションの起動時間が短縮これ[アセンブリのシャドウ コピー](../../../../../docs/framework/app-domains/shadow-copy-assemblies.md)します。</span><span class="sxs-lookup"><span data-stu-id="5770c-133">This improves startup times for many applications that use shadow copying, as described in [Shadow Copying Assemblies](../../../../../docs/framework/app-domains/shadow-copy-assemblies.md).</span></span> <span data-ttu-id="5770c-134">この動作の変更率が高いと、アセンブリの更新の頻度を持つアプリケーションの利点可能性があります。</span><span class="sxs-lookup"><span data-stu-id="5770c-134">Applications that have a high percentage and frequency of assembly updates might not benefit from this change in behavior.</span></span> <span data-ttu-id="5770c-135">その場合は、この要素を使用して、以前のバージョンの .NET Framework の動作を復元することができます。</span><span class="sxs-lookup"><span data-stu-id="5770c-135">In that case, you can use this element to restore the behavior of previous versions of the .NET Framework.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5770c-136">例</span><span class="sxs-lookup"><span data-stu-id="5770c-136">Example</span></span>  
 <span data-ttu-id="5770c-137">次の例でシャドウ コピーの既定のスタートアップ動作を無効にする方法を示しています、 [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)]、.NET Framework の以前のバージョンの起動の動作に戻ります。</span><span class="sxs-lookup"><span data-stu-id="5770c-137">The following example shows how to disable the default startup behavior of shadow copying in the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)], and revert to the startup behavior of previous versions of the .NET Framework.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <shadowCopyVerifyByTimestamp enabled="false" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="5770c-138">関連項目</span><span class="sxs-lookup"><span data-stu-id="5770c-138">See also</span></span>

- [<span data-ttu-id="5770c-139">ランタイム設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="5770c-139">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="5770c-140">構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="5770c-140">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="5770c-141">アセンブリのシャドウ コピー</span><span class="sxs-lookup"><span data-stu-id="5770c-141">Shadow Copying Assemblies</span></span>](../../../../../docs/framework/app-domains/shadow-copy-assemblies.md)
