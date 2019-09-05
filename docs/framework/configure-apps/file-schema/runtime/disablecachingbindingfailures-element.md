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
ms.openlocfilehash: d5b45ea4b30677d17e72685b16c19f9192c8c144
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252673"
---
# <a name="disablecachingbindingfailures-element"></a><span data-ttu-id="2bc6b-102">\<disableCachingBindingFailures > 要素</span><span class="sxs-lookup"><span data-stu-id="2bc6b-102">\<disableCachingBindingFailures> Element</span></span>
<span data-ttu-id="2bc6b-103">プローブによってアセンブリが見つからなかったために発生するバインドエラーのキャッシュを無効にするかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="2bc6b-103">Specifies whether to disable the caching of binding failures that occur because the assembly was not found by probing.</span></span>  
  
<span data-ttu-id="2bc6b-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="2bc6b-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="2bc6b-105">&nbsp;&nbsp;[ **\<ランタイム >** ](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="2bc6b-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="2bc6b-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<disableCachingBindingFailures >**</span><span class="sxs-lookup"><span data-stu-id="2bc6b-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<disableCachingBindingFailures>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2bc6b-107">構文</span><span class="sxs-lookup"><span data-stu-id="2bc6b-107">Syntax</span></span>  
  
```xml  
<disableCachingBindingFailures enabled="0|1"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2bc6b-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="2bc6b-108">Attributes and Elements</span></span>  
 <span data-ttu-id="2bc6b-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="2bc6b-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2bc6b-110">属性</span><span class="sxs-lookup"><span data-stu-id="2bc6b-110">Attributes</span></span>  
  
|<span data-ttu-id="2bc6b-111">属性</span><span class="sxs-lookup"><span data-stu-id="2bc6b-111">Attribute</span></span>|<span data-ttu-id="2bc6b-112">説明</span><span class="sxs-lookup"><span data-stu-id="2bc6b-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2bc6b-113">enabled</span><span class="sxs-lookup"><span data-stu-id="2bc6b-113">enabled</span></span>|<span data-ttu-id="2bc6b-114">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="2bc6b-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="2bc6b-115">プローブによってアセンブリが見つからなかったために発生するバインドエラーのキャッシュを無効にするかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="2bc6b-115">Specifies whether to disable the caching of binding failures that occur because the assembly was not found by probing.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="2bc6b-116">enabled 属性</span><span class="sxs-lookup"><span data-stu-id="2bc6b-116">enabled Attribute</span></span>  
  
|<span data-ttu-id="2bc6b-117">値</span><span class="sxs-lookup"><span data-stu-id="2bc6b-117">Value</span></span>|<span data-ttu-id="2bc6b-118">説明</span><span class="sxs-lookup"><span data-stu-id="2bc6b-118">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="2bc6b-119">0</span><span class="sxs-lookup"><span data-stu-id="2bc6b-119">0</span></span>|<span data-ttu-id="2bc6b-120">プローブによってアセンブリが見つからなかったために発生するバインドエラーのキャッシュを無効にしないでください。</span><span class="sxs-lookup"><span data-stu-id="2bc6b-120">Do not disable the caching of binding failures that occur because the assembly was not found by probing.</span></span> <span data-ttu-id="2bc6b-121">これは .NET Framework バージョン2.0 以降の既定のバインディング動作です。</span><span class="sxs-lookup"><span data-stu-id="2bc6b-121">This is the default binding behavior starting with the .NET Framework version 2.0.</span></span>|  
|<span data-ttu-id="2bc6b-122">1</span><span class="sxs-lookup"><span data-stu-id="2bc6b-122">1</span></span>|<span data-ttu-id="2bc6b-123">プローブによってアセンブリが見つからなかったために発生するバインドエラーのキャッシュを無効にします。</span><span class="sxs-lookup"><span data-stu-id="2bc6b-123">Disable the caching of binding failures that occur because the assembly was not found by probing.</span></span> <span data-ttu-id="2bc6b-124">この設定は、.NET Framework バージョン1.1 のバインド動作に戻ります。</span><span class="sxs-lookup"><span data-stu-id="2bc6b-124">This setting reverts to the binding behavior of the .NET Framework version 1.1.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2bc6b-125">子要素</span><span class="sxs-lookup"><span data-stu-id="2bc6b-125">Child Elements</span></span>  
 <span data-ttu-id="2bc6b-126">なし。</span><span class="sxs-lookup"><span data-stu-id="2bc6b-126">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2bc6b-127">親要素</span><span class="sxs-lookup"><span data-stu-id="2bc6b-127">Parent Elements</span></span>  
  
|<span data-ttu-id="2bc6b-128">要素</span><span class="sxs-lookup"><span data-stu-id="2bc6b-128">Element</span></span>|<span data-ttu-id="2bc6b-129">説明</span><span class="sxs-lookup"><span data-stu-id="2bc6b-129">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="2bc6b-130">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="2bc6b-130">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="2bc6b-131">アセンブリのバインディングとガベージ コレクションに関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="2bc6b-131">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2bc6b-132">Remarks</span><span class="sxs-lookup"><span data-stu-id="2bc6b-132">Remarks</span></span>  
 <span data-ttu-id="2bc6b-133">.NET Framework バージョン2.0 以降では、アセンブリを読み込む既定の動作では、すべてのバインドおよび読み込みエラーがキャッシュされます。</span><span class="sxs-lookup"><span data-stu-id="2bc6b-133">Starting with the .NET Framework version 2.0, the default behavior for loading assemblies is to cache all binding and loading failures.</span></span> <span data-ttu-id="2bc6b-134">つまり、アセンブリの読み込みに失敗した場合、同じアセンブリを読み込むための後続の要求は、アセンブリを特定しなくてもすぐに失敗します。</span><span class="sxs-lookup"><span data-stu-id="2bc6b-134">That is, if an attempt to load an assembly fails, subsequent requests to load the same assembly fail immediately, without any attempt to locate the assembly.</span></span> <span data-ttu-id="2bc6b-135">この要素は、プローブパスにアセンブリが見つからなかったために発生するバインディングエラーの既定の動作を無効にします。</span><span class="sxs-lookup"><span data-stu-id="2bc6b-135">This element disables that default behavior for binding failures that occur because the assembly could not be found in the probing path.</span></span> <span data-ttu-id="2bc6b-136">これらのエラー <xref:System.IO.FileNotFoundException>はスローします。</span><span class="sxs-lookup"><span data-stu-id="2bc6b-136">These failures throw <xref:System.IO.FileNotFoundException>.</span></span>  
  
 <span data-ttu-id="2bc6b-137">この要素の影響を受けないバインドと読み込みのエラーもあります。この要素は常にキャッシュされます。</span><span class="sxs-lookup"><span data-stu-id="2bc6b-137">Some binding and loading failures are not affected by this element, and are always cached.</span></span> <span data-ttu-id="2bc6b-138">これらのエラーは、アセンブリが見つかりましたが、読み込むことができなかったことが原因で発生します。</span><span class="sxs-lookup"><span data-stu-id="2bc6b-138">These failures occur because the assembly was found but could not be loaded.</span></span> <span data-ttu-id="2bc6b-139">または<xref:System.BadImageFormatException> <xref:System.IO.FileLoadException>をスローします。</span><span class="sxs-lookup"><span data-stu-id="2bc6b-139">They throw <xref:System.BadImageFormatException> or <xref:System.IO.FileLoadException>.</span></span> <span data-ttu-id="2bc6b-140">このようなエラーの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="2bc6b-140">The following list includes some examples of such failures.</span></span>  
  
- <span data-ttu-id="2bc6b-141">ファイルを読み込もうとしても有効なアセンブリではない場合、不適切なファイルが正しいアセンブリに置き換えられても、その後のアセンブリの読み込み試行は失敗します。</span><span class="sxs-lookup"><span data-stu-id="2bc6b-141">If you attempt to load a file is not a valid assembly, subsequent attempts to load the assembly will fail even if the bad file is replaced with the correct assembly.</span></span>  
  
- <span data-ttu-id="2bc6b-142">ファイルシステムによってロックされているアセンブリを読み込もうとすると、ファイルシステムによってアセンブリが解放された後でも、その後のアセンブリの読み込み試行は失敗します。</span><span class="sxs-lookup"><span data-stu-id="2bc6b-142">If you attempt to load an assembly that is locked by the file system, subsequent attempts to load the assembly will fail even after the assembly is released by the file system.</span></span>  
  
- <span data-ttu-id="2bc6b-143">読み込もうとしているアセンブリの1つまたは複数のバージョンがプローブパスに存在するが、要求している特定のバージョンがそれらの中にない場合は、正しいバージョンがプローブパスに移動されても、そのバージョンを読み込もうとすると失敗します。</span><span class="sxs-lookup"><span data-stu-id="2bc6b-143">If one or more versions of the assembly that you are attempting to load is in the probing path, but the specific version you are requesting is not among them, subsequent attempts to load that version will fail even if the correct version is moved into the probing path.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2bc6b-144">例</span><span class="sxs-lookup"><span data-stu-id="2bc6b-144">Example</span></span>  
 <span data-ttu-id="2bc6b-145">次の例では、プローブによってアセンブリが見つからなかったために発生したアセンブリバインディングエラーのキャッシュを無効にする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="2bc6b-145">The following example shows how to disable the caching of assembly binding failures that occur because the assembly was not found by probing.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <disableCachingBindingFailures enabled="1" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="2bc6b-146">関連項目</span><span class="sxs-lookup"><span data-stu-id="2bc6b-146">See also</span></span>

- [<span data-ttu-id="2bc6b-147">ランタイム設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="2bc6b-147">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="2bc6b-148">構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="2bc6b-148">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="2bc6b-149">ランタイムがアセンブリを検索する方法</span><span class="sxs-lookup"><span data-stu-id="2bc6b-149">How the Runtime Locates Assemblies</span></span>](../../../deployment/how-the-runtime-locates-assemblies.md)
