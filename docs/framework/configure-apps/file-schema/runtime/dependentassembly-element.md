---
title: <dependentAssembly> 要素
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/dependentAssembly
- http://schemas.microsoft.com/.NetConfiguration/v2.0#dependentAssembly
helpviewer_keywords:
- container tags, <dependentAssembly> element
- dependentAssembly element
- <dependentAssembly> element
ms.assetid: 14e95627-dd79-4b82-ac85-e682aa3a31d8
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4bf1a15ff27f4390f1985a2d2730b1acfcaab2c1
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/21/2019
ms.locfileid: "69663824"
---
# <a name="dependentassembly-element"></a><span data-ttu-id="d4a19-102">\<dependentAssembly > 要素</span><span class="sxs-lookup"><span data-stu-id="d4a19-102">\<dependentAssembly> Element</span></span>
<span data-ttu-id="d4a19-103">各アセンブリのバインディング ポリシーとアセンブリの場所をカプセル化します。</span><span class="sxs-lookup"><span data-stu-id="d4a19-103">Encapsulates binding policy and assembly location for each assembly.</span></span> <span data-ttu-id="d4a19-104">アセンブリごと`dependentAssembly`に1つの要素を使用します。</span><span class="sxs-lookup"><span data-stu-id="d4a19-104">Use one `dependentAssembly` element for each assembly.</span></span>  
  
 <span data-ttu-id="d4a19-105">\<configuration></span><span class="sxs-lookup"><span data-stu-id="d4a19-105">\<configuration></span></span>  
<span data-ttu-id="d4a19-106">\<ランタイム ></span><span class="sxs-lookup"><span data-stu-id="d4a19-106">\<runtime></span></span>  
<span data-ttu-id="d4a19-107">\<assemblyBinding></span><span class="sxs-lookup"><span data-stu-id="d4a19-107">\<assemblyBinding></span></span>  
<span data-ttu-id="d4a19-108">\<dependentAssembly ></span><span class="sxs-lookup"><span data-stu-id="d4a19-108">\<dependentAssembly></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d4a19-109">構文</span><span class="sxs-lookup"><span data-stu-id="d4a19-109">Syntax</span></span>  
  
```xml  
<dependentAssembly>   
</dependentAssembly>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d4a19-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="d4a19-110">Attributes and Elements</span></span>  
 <span data-ttu-id="d4a19-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="d4a19-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d4a19-112">属性</span><span class="sxs-lookup"><span data-stu-id="d4a19-112">Attributes</span></span>  
 <span data-ttu-id="d4a19-113">なし。</span><span class="sxs-lookup"><span data-stu-id="d4a19-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="d4a19-114">子要素</span><span class="sxs-lookup"><span data-stu-id="d4a19-114">Child Elements</span></span>  
  
|<span data-ttu-id="d4a19-115">要素</span><span class="sxs-lookup"><span data-stu-id="d4a19-115">Element</span></span>|<span data-ttu-id="d4a19-116">説明</span><span class="sxs-lookup"><span data-stu-id="d4a19-116">Description</span></span>|  
|-------------|-----------------|  
|`assemblyIdentity`|<span data-ttu-id="d4a19-117">アセンブリに関する識別情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="d4a19-117">Contains identifying information about the assembly.</span></span> <span data-ttu-id="d4a19-118">この要素は、各`dependentAssembly`要素に含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="d4a19-118">This element must be included in each `dependentAssembly` element.</span></span>|  
|`codeBase`|<span data-ttu-id="d4a19-119">ランタイムがコンピューターにインストールされていない場合に、共有アセンブリを見つけることができる場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="d4a19-119">Specifies where the runtime can find a shared assembly if it is not installed on the computer.</span></span>|  
|`bindingRedirect`|<span data-ttu-id="d4a19-120">1 つのアセンブリ バージョンを別のバージョンにリダイレクトします。</span><span class="sxs-lookup"><span data-stu-id="d4a19-120">Redirects one assembly version to another.</span></span>|  
|`publisherPolicy`|<span data-ttu-id="d4a19-121">ランタイムがこのアセンブリの発行者ポリシーを適用するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="d4a19-121">Specifies whether the runtime applies publisher policy for this assembly.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d4a19-122">親要素</span><span class="sxs-lookup"><span data-stu-id="d4a19-122">Parent Elements</span></span>  
  
|<span data-ttu-id="d4a19-123">要素</span><span class="sxs-lookup"><span data-stu-id="d4a19-123">Element</span></span>|<span data-ttu-id="d4a19-124">説明</span><span class="sxs-lookup"><span data-stu-id="d4a19-124">Description</span></span>|  
|-------------|-----------------|  
|`assemblyBinding`|<span data-ttu-id="d4a19-125">アセンブリ バージョンのリダイレクトおよびアセンブリの位置に関する情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="d4a19-125">Contains information about assembly version redirection and the locations of assemblies.</span></span>|  
|`configuration`|<span data-ttu-id="d4a19-126">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="d4a19-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="d4a19-127">アセンブリのバインディングとガベージ コレクションに関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="d4a19-127">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="d4a19-128">例</span><span class="sxs-lookup"><span data-stu-id="d4a19-128">Example</span></span>  
 <span data-ttu-id="d4a19-129">次の例は、2つのアセンブリのアセンブリ情報をカプセル化する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="d4a19-129">The following example shows how to encapsulate assembly information for two assemblies.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <dependentAssembly>  
            <assemblyIdentity name="myAssembly"  
                              publicKeyToken="32ab4ba45e0a69a1"  
                              culture="neutral" />  
            <!--Redirection and codeBase policy for myAssembly.-->  
         </dependentAssembly>  
         <dependentAssembly>  
            <assemblyIdentity name="mySecondAssembly"  
                              publicKeyToken="32ab4ba45e0a69a1"  
                              culture="neutral" />  
            <!--Redirection and codeBase policy for mySecondAssembly.-->  
         </dependentAssembly>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="d4a19-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="d4a19-130">See also</span></span>

- [<span data-ttu-id="d4a19-131">ランタイム設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="d4a19-131">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="d4a19-132">構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="d4a19-132">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="d4a19-133">アセンブリ バージョンのリダイレクト</span><span class="sxs-lookup"><span data-stu-id="d4a19-133">Redirecting Assembly Versions</span></span>](../../redirect-assembly-versions.md)
