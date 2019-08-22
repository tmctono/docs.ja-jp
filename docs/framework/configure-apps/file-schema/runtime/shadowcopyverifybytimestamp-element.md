---
title: <shadowCopyVerifyByTimestamp> 要素
ms.date: 03/30/2017
helpviewer_keywords:
- <shadowCopyTimeStampVerification> element
- shadowCopyTimeStampVerification element
ms.assetid: 2f1648e5-997b-435e-a4f9-d236c574c66c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6f3ea57364832553d16c7e34fc887b1c9f821602
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/21/2019
ms.locfileid: "69663449"
---
# <a name="shadowcopyverifybytimestamp-element"></a><span data-ttu-id="1b551-102">\<shadowCopyVerifyByTimestamp> 要素</span><span class="sxs-lookup"><span data-stu-id="1b551-102">\<shadowCopyVerifyByTimestamp> Element</span></span>
<span data-ttu-id="1b551-103">シャドウコピーで .NET Framework 4 で導入された既定の起動動作を使用するか、以前のバージョンの .NET Framework の起動動作に戻すかを指定します。</span><span class="sxs-lookup"><span data-stu-id="1b551-103">Specifies whether shadow copying uses the default startup behavior introduced in the .NET Framework 4, or reverts to the startup behavior of earlier versions of the .NET Framework.</span></span>  
  
 <span data-ttu-id="1b551-104">\<configuration> 要素</span><span class="sxs-lookup"><span data-stu-id="1b551-104">\<configuration> Element</span></span>  
<span data-ttu-id="1b551-105">\<runtime> 要素</span><span class="sxs-lookup"><span data-stu-id="1b551-105">\<runtime> Element</span></span>  
<span data-ttu-id="1b551-106">\<shadowCopyVerifyByTimestamp> 要素</span><span class="sxs-lookup"><span data-stu-id="1b551-106">\<shadowCopyVerifyByTimestamp> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1b551-107">構文</span><span class="sxs-lookup"><span data-stu-id="1b551-107">Syntax</span></span>  
  
```xml  
<shadowCopyVerifyByTimestamp enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1b551-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="1b551-108">Attributes and Elements</span></span>  
 <span data-ttu-id="1b551-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="1b551-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1b551-110">属性</span><span class="sxs-lookup"><span data-stu-id="1b551-110">Attributes</span></span>  
  
|<span data-ttu-id="1b551-111">属性</span><span class="sxs-lookup"><span data-stu-id="1b551-111">Attribute</span></span>|<span data-ttu-id="1b551-112">説明</span><span class="sxs-lookup"><span data-stu-id="1b551-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1b551-113">enabled</span><span class="sxs-lookup"><span data-stu-id="1b551-113">enabled</span></span>|<span data-ttu-id="1b551-114">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="1b551-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="1b551-115">シャドウコピーを使用するアプリケーションドメインが起動時にアセンブリのタイムスタンプを比較するかどうかを指定し、アセンブリをシャドウコピーする前に更新したかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="1b551-115">Specifies whether application domains that use shadow copying compare assembly time stamps when starting up, to determine whether an assembly has been updated before shadow copying the assembly.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="1b551-116">enabled 属性</span><span class="sxs-lookup"><span data-stu-id="1b551-116">enabled Attribute</span></span>  
  
|<span data-ttu-id="1b551-117">値</span><span class="sxs-lookup"><span data-stu-id="1b551-117">Value</span></span>|<span data-ttu-id="1b551-118">説明</span><span class="sxs-lookup"><span data-stu-id="1b551-118">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="1b551-119">true</span><span class="sxs-lookup"><span data-stu-id="1b551-119">true</span></span>|<span data-ttu-id="1b551-120">起動時に、はシャドウコピーディレクトリに最後にコピーされてから更新されたアセンブリのみをコピーします。</span><span class="sxs-lookup"><span data-stu-id="1b551-120">At startup, copies only assemblies that have been updated since they were last copied to the shadow copy directory.</span></span> <span data-ttu-id="1b551-121">これは .NET Framework 4 の既定値です。</span><span class="sxs-lookup"><span data-stu-id="1b551-121">This is the default for the .NET Framework 4.</span></span>|  
|<span data-ttu-id="1b551-122">False</span><span class="sxs-lookup"><span data-stu-id="1b551-122">false</span></span>|<span data-ttu-id="1b551-123">以前のバージョンの .NET Framework の起動動作に戻ります。これは、起動時にすべてのファイルをコピーすることでした。</span><span class="sxs-lookup"><span data-stu-id="1b551-123">Reverts to the startup behavior of previous versions of the .NET Framework, which was to copy all files at startup.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1b551-124">子要素</span><span class="sxs-lookup"><span data-stu-id="1b551-124">Child Elements</span></span>  
 <span data-ttu-id="1b551-125">なし。</span><span class="sxs-lookup"><span data-stu-id="1b551-125">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1b551-126">親要素</span><span class="sxs-lookup"><span data-stu-id="1b551-126">Parent Elements</span></span>  
  
|<span data-ttu-id="1b551-127">要素</span><span class="sxs-lookup"><span data-stu-id="1b551-127">Element</span></span>|<span data-ttu-id="1b551-128">説明</span><span class="sxs-lookup"><span data-stu-id="1b551-128">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="1b551-129">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="1b551-129">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="1b551-130">アセンブリのバインディングとガベージ コレクションに関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="1b551-130">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1b551-131">Remarks</span><span class="sxs-lookup"><span data-stu-id="1b551-131">Remarks</span></span>  
 <span data-ttu-id="1b551-132">.NET Framework 4 以降、アセンブリはシャドウコピーディレクトリに最後にコピーされてから変更されたことを示すタイムスタンプがある場合にのみ、シャドウコピーされます。</span><span class="sxs-lookup"><span data-stu-id="1b551-132">Starting with the .NET Framework 4, assemblies are shadow copied only if their time stamps indicate that they have changed since they were last copied to the shadow copy directory.</span></span> <span data-ttu-id="1b551-133">これにより、「[アセンブリのシャドウコピー](../../../app-domains/shadow-copy-assemblies.md)」で説明されているように、シャドウコピーを使用する多くのアプリケーションの起動時間が短縮されます。</span><span class="sxs-lookup"><span data-stu-id="1b551-133">This improves startup times for many applications that use shadow copying, as described in [Shadow Copying Assemblies](../../../app-domains/shadow-copy-assemblies.md).</span></span> <span data-ttu-id="1b551-134">アセンブリ更新の割合と頻度が高いアプリケーションでは、この動作の変更によるメリットが得られない場合があります。</span><span class="sxs-lookup"><span data-stu-id="1b551-134">Applications that have a high percentage and frequency of assembly updates might not benefit from this change in behavior.</span></span> <span data-ttu-id="1b551-135">その場合は、この要素を使用して、.NET Framework の以前のバージョンの動作を復元できます。</span><span class="sxs-lookup"><span data-stu-id="1b551-135">In that case, you can use this element to restore the behavior of previous versions of the .NET Framework.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1b551-136">例</span><span class="sxs-lookup"><span data-stu-id="1b551-136">Example</span></span>  
 <span data-ttu-id="1b551-137">次の例は、.NET Framework 4 でシャドウコピーの既定の起動動作を無効にして、以前のバージョンの .NET Framework の起動動作に戻す方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="1b551-137">The following example shows how to disable the default startup behavior of shadow copying in the .NET Framework 4, and revert to the startup behavior of previous versions of the .NET Framework.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <shadowCopyVerifyByTimestamp enabled="false" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="1b551-138">関連項目</span><span class="sxs-lookup"><span data-stu-id="1b551-138">See also</span></span>

- [<span data-ttu-id="1b551-139">ランタイム設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="1b551-139">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="1b551-140">構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="1b551-140">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="1b551-141">アセンブリのシャドウ コピー</span><span class="sxs-lookup"><span data-stu-id="1b551-141">Shadow Copying Assemblies</span></span>](../../../app-domains/shadow-copy-assemblies.md)
