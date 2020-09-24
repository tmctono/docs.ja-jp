---
title: <shadowCopyVerifyByTimestamp> 要素
ms.date: 03/30/2017
helpviewer_keywords:
- <shadowCopyTimeStampVerification> element
- shadowCopyTimeStampVerification element
ms.assetid: 2f1648e5-997b-435e-a4f9-d236c574c66c
ms.openlocfilehash: c0dc190e69ca9650d518ee297b12f79f8c47d58b
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91183976"
---
# <a name="shadowcopyverifybytimestamp-element"></a><span data-ttu-id="a561d-102">\<shadowCopyVerifyByTimestamp> 要素</span><span class="sxs-lookup"><span data-stu-id="a561d-102">\<shadowCopyVerifyByTimestamp> Element</span></span>

<span data-ttu-id="a561d-103">シャドウコピーで .NET Framework 4 で導入された既定の起動動作を使用するか、以前のバージョンの .NET Framework の起動動作に戻すかを指定します。</span><span class="sxs-lookup"><span data-stu-id="a561d-103">Specifies whether shadow copying uses the default startup behavior introduced in the .NET Framework 4, or reverts to the startup behavior of earlier versions of the .NET Framework.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<shadowCopyVerifyByTimestamp>**  
  
## <a name="syntax"></a><span data-ttu-id="a561d-104">構文</span><span class="sxs-lookup"><span data-stu-id="a561d-104">Syntax</span></span>  
  
```xml  
<shadowCopyVerifyByTimestamp enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a561d-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="a561d-105">Attributes and Elements</span></span>  

 <span data-ttu-id="a561d-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="a561d-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a561d-107">属性</span><span class="sxs-lookup"><span data-stu-id="a561d-107">Attributes</span></span>  
  
|<span data-ttu-id="a561d-108">属性</span><span class="sxs-lookup"><span data-stu-id="a561d-108">Attribute</span></span>|<span data-ttu-id="a561d-109">説明</span><span class="sxs-lookup"><span data-stu-id="a561d-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a561d-110">enabled</span><span class="sxs-lookup"><span data-stu-id="a561d-110">enabled</span></span>|<span data-ttu-id="a561d-111">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="a561d-111">Required attribute.</span></span><br /><br /> <span data-ttu-id="a561d-112">シャドウコピーを使用するアプリケーションドメインが起動時にアセンブリのタイムスタンプを比較するかどうかを指定し、アセンブリをシャドウコピーする前に更新したかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="a561d-112">Specifies whether application domains that use shadow copying compare assembly time stamps when starting up, to determine whether an assembly has been updated before shadow copying the assembly.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="a561d-113">enabled 属性</span><span class="sxs-lookup"><span data-stu-id="a561d-113">enabled Attribute</span></span>  
  
|<span data-ttu-id="a561d-114">値</span><span class="sxs-lookup"><span data-stu-id="a561d-114">Value</span></span>|<span data-ttu-id="a561d-115">説明</span><span class="sxs-lookup"><span data-stu-id="a561d-115">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="a561d-116">true</span><span class="sxs-lookup"><span data-stu-id="a561d-116">true</span></span>|<span data-ttu-id="a561d-117">起動時に、はシャドウコピーディレクトリに最後にコピーされてから更新されたアセンブリのみをコピーします。</span><span class="sxs-lookup"><span data-stu-id="a561d-117">At startup, copies only assemblies that have been updated since they were last copied to the shadow copy directory.</span></span> <span data-ttu-id="a561d-118">これは .NET Framework 4 の既定値です。</span><span class="sxs-lookup"><span data-stu-id="a561d-118">This is the default for the .NET Framework 4.</span></span>|  
|<span data-ttu-id="a561d-119">false</span><span class="sxs-lookup"><span data-stu-id="a561d-119">false</span></span>|<span data-ttu-id="a561d-120">以前のバージョンの .NET Framework の起動動作に戻ります。これは、起動時にすべてのファイルをコピーすることでした。</span><span class="sxs-lookup"><span data-stu-id="a561d-120">Reverts to the startup behavior of previous versions of the .NET Framework, which was to copy all files at startup.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a561d-121">子要素</span><span class="sxs-lookup"><span data-stu-id="a561d-121">Child Elements</span></span>  

 <span data-ttu-id="a561d-122">なし。</span><span class="sxs-lookup"><span data-stu-id="a561d-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a561d-123">親要素</span><span class="sxs-lookup"><span data-stu-id="a561d-123">Parent Elements</span></span>  
  
|<span data-ttu-id="a561d-124">要素</span><span class="sxs-lookup"><span data-stu-id="a561d-124">Element</span></span>|<span data-ttu-id="a561d-125">説明</span><span class="sxs-lookup"><span data-stu-id="a561d-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="a561d-126">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="a561d-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="a561d-127">アセンブリのバインディングとガベージ コレクションに関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="a561d-127">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a561d-128">解説</span><span class="sxs-lookup"><span data-stu-id="a561d-128">Remarks</span></span>  

 <span data-ttu-id="a561d-129">.NET Framework 4 以降、アセンブリはシャドウコピーディレクトリに最後にコピーされてから変更されたことを示すタイムスタンプがある場合にのみ、シャドウコピーされます。</span><span class="sxs-lookup"><span data-stu-id="a561d-129">Starting with the .NET Framework 4, assemblies are shadow copied only if their time stamps indicate that they have changed since they were last copied to the shadow copy directory.</span></span> <span data-ttu-id="a561d-130">これにより、「 [アセンブリのシャドウコピー](../../../app-domains/shadow-copy-assemblies.md)」で説明されているように、シャドウコピーを使用する多くのアプリケーションの起動時間が短縮されます。</span><span class="sxs-lookup"><span data-stu-id="a561d-130">This improves startup times for many applications that use shadow copying, as described in [Shadow Copying Assemblies](../../../app-domains/shadow-copy-assemblies.md).</span></span> <span data-ttu-id="a561d-131">アセンブリ更新の割合と頻度が高いアプリケーションでは、この動作の変更によるメリットが得られない場合があります。</span><span class="sxs-lookup"><span data-stu-id="a561d-131">Applications that have a high percentage and frequency of assembly updates might not benefit from this change in behavior.</span></span> <span data-ttu-id="a561d-132">その場合は、この要素を使用して、.NET Framework の以前のバージョンの動作を復元できます。</span><span class="sxs-lookup"><span data-stu-id="a561d-132">In that case, you can use this element to restore the behavior of previous versions of the .NET Framework.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a561d-133">例</span><span class="sxs-lookup"><span data-stu-id="a561d-133">Example</span></span>  

 <span data-ttu-id="a561d-134">次の例は、.NET Framework 4 でシャドウコピーの既定の起動動作を無効にして、以前のバージョンの .NET Framework の起動動作に戻す方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="a561d-134">The following example shows how to disable the default startup behavior of shadow copying in the .NET Framework 4, and revert to the startup behavior of previous versions of the .NET Framework.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <shadowCopyVerifyByTimestamp enabled="false" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="a561d-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="a561d-135">See also</span></span>

- [<span data-ttu-id="a561d-136">ランタイム設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="a561d-136">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="a561d-137">構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="a561d-137">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="a561d-138">アセンブリのシャドウ コピー</span><span class="sxs-lookup"><span data-stu-id="a561d-138">Shadow Copying Assemblies</span></span>](../../../app-domains/shadow-copy-assemblies.md)
