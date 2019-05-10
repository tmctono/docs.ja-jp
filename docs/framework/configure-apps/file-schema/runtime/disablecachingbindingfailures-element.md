---
title: <disableCachingBindingFailures> 要素
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#disableCachingBindingFailures
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/disableCachingBindingFailures
helpviewer_keywords:
- assemblies [.NET Framework],caching binding failures
- caching assembly binding failures
- <disableCachingBindingFailures> element
- disableCachingBindingFailures element
ms.assetid: bf598873-83b7-48de-8955-00b0504fbad0
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6c2ed46e1d26d829fbe832e44efb40844ae7d56f
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64592721"
---
# <a name="disablecachingbindingfailures-element"></a><span data-ttu-id="fe184-102">\<disableCachingBindingFailures > 要素</span><span class="sxs-lookup"><span data-stu-id="fe184-102">\<disableCachingBindingFailures> Element</span></span>
<span data-ttu-id="fe184-103">バインディングを調査して、アセンブリが見つからなかったために発生したエラーのキャッシュを無効にするかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="fe184-103">Specifies whether to disable the caching of binding failures that occur because the assembly was not found by probing.</span></span>  
  
 <span data-ttu-id="fe184-104">\<configuration > 要素</span><span class="sxs-lookup"><span data-stu-id="fe184-104">\<configuration> Element</span></span>  
<span data-ttu-id="fe184-105">\<ランタイム > 要素</span><span class="sxs-lookup"><span data-stu-id="fe184-105">\<runtime> Element</span></span>  
<span data-ttu-id="fe184-106">\<disableCachingBindingFailures></span><span class="sxs-lookup"><span data-stu-id="fe184-106">\<disableCachingBindingFailures></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fe184-107">構文</span><span class="sxs-lookup"><span data-stu-id="fe184-107">Syntax</span></span>  
  
```xml  
<disableCachingBindingFailures enabled="0|1"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fe184-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="fe184-108">Attributes and Elements</span></span>  
 <span data-ttu-id="fe184-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="fe184-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fe184-110">属性</span><span class="sxs-lookup"><span data-stu-id="fe184-110">Attributes</span></span>  
  
|<span data-ttu-id="fe184-111">属性</span><span class="sxs-lookup"><span data-stu-id="fe184-111">Attribute</span></span>|<span data-ttu-id="fe184-112">説明</span><span class="sxs-lookup"><span data-stu-id="fe184-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="fe184-113">enabled</span><span class="sxs-lookup"><span data-stu-id="fe184-113">enabled</span></span>|<span data-ttu-id="fe184-114">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="fe184-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="fe184-115">バインディングを調査して、アセンブリが見つからなかったために発生したエラーのキャッシュを無効にするかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="fe184-115">Specifies whether to disable the caching of binding failures that occur because the assembly was not found by probing.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="fe184-116">enabled 属性</span><span class="sxs-lookup"><span data-stu-id="fe184-116">enabled Attribute</span></span>  
  
|<span data-ttu-id="fe184-117">値</span><span class="sxs-lookup"><span data-stu-id="fe184-117">Value</span></span>|<span data-ttu-id="fe184-118">説明</span><span class="sxs-lookup"><span data-stu-id="fe184-118">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="fe184-119">0</span><span class="sxs-lookup"><span data-stu-id="fe184-119">0</span></span>|<span data-ttu-id="fe184-120">バインディングを調査して、アセンブリが見つからなかったために発生したエラーのキャッシュを無効にできません。</span><span class="sxs-lookup"><span data-stu-id="fe184-120">Do not disable the caching of binding failures that occur because the assembly was not found by probing.</span></span> <span data-ttu-id="fe184-121">これは、.NET Framework version 2.0 以降で既定のバインドの動作です。</span><span class="sxs-lookup"><span data-stu-id="fe184-121">This is the default binding behavior starting with the .NET Framework version 2.0.</span></span>|  
|<span data-ttu-id="fe184-122">1</span><span class="sxs-lookup"><span data-stu-id="fe184-122">1</span></span>|<span data-ttu-id="fe184-123">バインディングを調査して、アセンブリが見つからなかったために発生したエラーのキャッシュを無効にします。</span><span class="sxs-lookup"><span data-stu-id="fe184-123">Disable the caching of binding failures that occur because the assembly was not found by probing.</span></span> <span data-ttu-id="fe184-124">この設定は、.NET Framework version 1.1 のバインドの動作に戻ります。</span><span class="sxs-lookup"><span data-stu-id="fe184-124">This setting reverts to the binding behavior of the .NET Framework version 1.1.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="fe184-125">子要素</span><span class="sxs-lookup"><span data-stu-id="fe184-125">Child Elements</span></span>  
 <span data-ttu-id="fe184-126">なし。</span><span class="sxs-lookup"><span data-stu-id="fe184-126">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="fe184-127">親要素</span><span class="sxs-lookup"><span data-stu-id="fe184-127">Parent Elements</span></span>  
  
|<span data-ttu-id="fe184-128">要素</span><span class="sxs-lookup"><span data-stu-id="fe184-128">Element</span></span>|<span data-ttu-id="fe184-129">説明</span><span class="sxs-lookup"><span data-stu-id="fe184-129">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="fe184-130">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="fe184-130">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="fe184-131">アセンブリのバインディングとガベージ コレクションに関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="fe184-131">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fe184-132">Remarks</span><span class="sxs-lookup"><span data-stu-id="fe184-132">Remarks</span></span>  
 <span data-ttu-id="fe184-133">以降、.NET Framework version 2.0 では、アセンブリを読み込むための既定の動作は、すべてのバインドと読み込みエラーをキャッシュするのには。</span><span class="sxs-lookup"><span data-stu-id="fe184-133">Starting with the .NET Framework version 2.0, the default behavior for loading assemblies is to cache all binding and loading failures.</span></span> <span data-ttu-id="fe184-134">アセンブリを読み込もうとしましたが失敗した場合、後続の要求に同じアセンブリの読み込みは即座に失敗、アセンブリを検索しようとするとします。</span><span class="sxs-lookup"><span data-stu-id="fe184-134">That is, if an attempt to load an assembly fails, subsequent requests to load the same assembly fail immediately, without any attempt to locate the assembly.</span></span> <span data-ttu-id="fe184-135">この要素は、バインディング、アセンブリをプローブ パスに見つかりませんだったために発生したエラーの既定の動作を無効にします。</span><span class="sxs-lookup"><span data-stu-id="fe184-135">This element disables that default behavior for binding failures that occur because the assembly could not be found in the probing path.</span></span> <span data-ttu-id="fe184-136">このようなエラーをスロー<xref:System.IO.FileNotFoundException>します。</span><span class="sxs-lookup"><span data-stu-id="fe184-136">These failures throw <xref:System.IO.FileNotFoundException>.</span></span>  
  
 <span data-ttu-id="fe184-137">いくつかのバインドと読み込みエラーは、この要素の影響は受けませんされ、常にキャッシュされます。</span><span class="sxs-lookup"><span data-stu-id="fe184-137">Some binding and loading failures are not affected by this element, and are always cached.</span></span> <span data-ttu-id="fe184-138">アセンブリが見つかりましたが、読み込むことができないために、このようなエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="fe184-138">These failures occur because the assembly was found but could not be loaded.</span></span> <span data-ttu-id="fe184-139">スロー<xref:System.BadImageFormatException>または<xref:System.IO.FileLoadException>します。</span><span class="sxs-lookup"><span data-stu-id="fe184-139">They throw <xref:System.BadImageFormatException> or <xref:System.IO.FileLoadException>.</span></span> <span data-ttu-id="fe184-140">次の一覧には、このようなエラーのいくつかの例が含まれています。</span><span class="sxs-lookup"><span data-stu-id="fe184-140">The following list includes some examples of such failures.</span></span>  
  
- <span data-ttu-id="fe184-141">ロードしようとした場合、ファイルが有効なアセンブリではない、悪意のあるファイルは、適切なアセンブリに置き換えられます場合でも、後続のアセンブリの読み込みは失敗します。</span><span class="sxs-lookup"><span data-stu-id="fe184-141">If you attempt to load a file is not a valid assembly, subsequent attempts to load the assembly will fail even if the bad file is replaced with the correct assembly.</span></span>  
  
- <span data-ttu-id="fe184-142">ファイル システムによってロックされているアセンブリをロードしようとすると、アセンブリは、ファイル システムでリリースされた後でもアセンブリの読み込みを後続の試行は失敗します。</span><span class="sxs-lookup"><span data-stu-id="fe184-142">If you attempt to load an assembly that is locked by the file system, subsequent attempts to load the assembly will fail even after the assembly is released by the file system.</span></span>  
  
- <span data-ttu-id="fe184-143">プローブのパスがロードしようとしているアセンブリの 1 つまたは複数のバージョンが、それらの間で要求している特定のバージョンがない、正しいバージョンがプローブ パスに移動された場合でもそのバージョンをロードしようは失敗します。</span><span class="sxs-lookup"><span data-stu-id="fe184-143">If one or more versions of the assembly that you are attempting to load is in the probing path, but the specific version you are requesting is not among them, subsequent attempts to load that version will fail even if the correct version is moved into the probing path.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fe184-144">例</span><span class="sxs-lookup"><span data-stu-id="fe184-144">Example</span></span>  
 <span data-ttu-id="fe184-145">次の例では、アセンブリ バインディング エラーを調査して、アセンブリが見つからなかったために発生したのキャッシュを無効にする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="fe184-145">The following example shows how to disable the caching of assembly binding failures that occur because the assembly was not found by probing.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <disableCachingBindingFailures enabled="1" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="fe184-146">関連項目</span><span class="sxs-lookup"><span data-stu-id="fe184-146">See also</span></span>

- [<span data-ttu-id="fe184-147">ランタイム設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="fe184-147">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="fe184-148">構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="fe184-148">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="fe184-149">ランタイムがアセンブリを検索する方法</span><span class="sxs-lookup"><span data-stu-id="fe184-149">How the Runtime Locates Assemblies</span></span>](../../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
