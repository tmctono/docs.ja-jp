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
ms.openlocfilehash: 33309ed89b4d31580da5de3aeb38e9e1fd8ae4d0
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73117594"
---
# <a name="dependentassembly-element"></a><span data-ttu-id="e374f-102">\<dependentAssembly > 要素</span><span class="sxs-lookup"><span data-stu-id="e374f-102">\<dependentAssembly> Element</span></span>
<span data-ttu-id="e374f-103">各アセンブリのバインディング ポリシーとアセンブリの場所をカプセル化します。</span><span class="sxs-lookup"><span data-stu-id="e374f-103">Encapsulates binding policy and assembly location for each assembly.</span></span> <span data-ttu-id="e374f-104">アセンブリごとに1つの `dependentAssembly` 要素を使用します。</span><span class="sxs-lookup"><span data-stu-id="e374f-104">Use one `dependentAssembly` element for each assembly.</span></span>  
  
<span data-ttu-id="e374f-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="e374f-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="e374f-106">&nbsp;&nbsp;[ **\<runtime>** ](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="e374f-106">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="e374f-107">&nbsp; &nbsp; &nbsp; &nbsp;[ **\<assemblyBinding**](assemblybinding-element-for-runtime.md) > </span><span class="sxs-lookup"><span data-stu-id="e374f-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<assemblyBinding>**](assemblybinding-element-for-runtime.md)</span></span>\
<span data-ttu-id="e374f-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**dependentAssembly >**</span><span class="sxs-lookup"><span data-stu-id="e374f-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<dependentAssembly>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e374f-109">構文</span><span class="sxs-lookup"><span data-stu-id="e374f-109">Syntax</span></span>  
  
```xml  
<dependentAssembly>   
</dependentAssembly>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e374f-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="e374f-110">Attributes and Elements</span></span>  
 <span data-ttu-id="e374f-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="e374f-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e374f-112">属性</span><span class="sxs-lookup"><span data-stu-id="e374f-112">Attributes</span></span>  
 <span data-ttu-id="e374f-113">なし。</span><span class="sxs-lookup"><span data-stu-id="e374f-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="e374f-114">子要素</span><span class="sxs-lookup"><span data-stu-id="e374f-114">Child Elements</span></span>  
  
|<span data-ttu-id="e374f-115">要素</span><span class="sxs-lookup"><span data-stu-id="e374f-115">Element</span></span>|<span data-ttu-id="e374f-116">説明</span><span class="sxs-lookup"><span data-stu-id="e374f-116">Description</span></span>|  
|-------------|-----------------|  
|`assemblyIdentity`|<span data-ttu-id="e374f-117">アセンブリに関する識別情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="e374f-117">Contains identifying information about the assembly.</span></span> <span data-ttu-id="e374f-118">この要素は、各 `dependentAssembly` 要素に含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="e374f-118">This element must be included in each `dependentAssembly` element.</span></span>|  
|`codeBase`|<span data-ttu-id="e374f-119">ランタイムがコンピューターにインストールされていない場合に、共有アセンブリを見つけることができる場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="e374f-119">Specifies where the runtime can find a shared assembly if it is not installed on the computer.</span></span>|  
|`bindingRedirect`|<span data-ttu-id="e374f-120">1 つのアセンブリ バージョンを別のバージョンにリダイレクトします。</span><span class="sxs-lookup"><span data-stu-id="e374f-120">Redirects one assembly version to another.</span></span>|  
|`publisherPolicy`|<span data-ttu-id="e374f-121">ランタイムがこのアセンブリの発行者ポリシーを適用するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="e374f-121">Specifies whether the runtime applies publisher policy for this assembly.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e374f-122">親要素</span><span class="sxs-lookup"><span data-stu-id="e374f-122">Parent Elements</span></span>  
  
|<span data-ttu-id="e374f-123">要素</span><span class="sxs-lookup"><span data-stu-id="e374f-123">Element</span></span>|<span data-ttu-id="e374f-124">説明</span><span class="sxs-lookup"><span data-stu-id="e374f-124">Description</span></span>|  
|-------------|-----------------|  
|`assemblyBinding`|<span data-ttu-id="e374f-125">アセンブリ バージョンのリダイレクトおよびアセンブリの位置に関する情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="e374f-125">Contains information about assembly version redirection and the locations of assemblies.</span></span>|  
|`configuration`|<span data-ttu-id="e374f-126">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="e374f-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="e374f-127">アセンブリのバインディングとガベージ コレクションに関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="e374f-127">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="e374f-128">例</span><span class="sxs-lookup"><span data-stu-id="e374f-128">Example</span></span>  
 <span data-ttu-id="e374f-129">次の例は、2つのアセンブリのアセンブリ情報をカプセル化する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="e374f-129">The following example shows how to encapsulate assembly information for two assemblies.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="e374f-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="e374f-130">See also</span></span>

- [<span data-ttu-id="e374f-131">ランタイム設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="e374f-131">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="e374f-132">構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="e374f-132">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="e374f-133">アセンブリ バージョンのリダイレクト</span><span class="sxs-lookup"><span data-stu-id="e374f-133">Redirecting Assembly Versions</span></span>](../../redirect-assembly-versions.md)
