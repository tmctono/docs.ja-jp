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
ms.openlocfilehash: 6a924b1998651c923c64429029a118dd1e9ede69
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91199004"
---
# <a name="dependentassembly-element"></a><span data-ttu-id="0414a-102">\<dependentAssembly> 要素</span><span class="sxs-lookup"><span data-stu-id="0414a-102">\<dependentAssembly> Element</span></span>

<span data-ttu-id="0414a-103">各アセンブリのバインディング ポリシーとアセンブリの場所をカプセル化します。</span><span class="sxs-lookup"><span data-stu-id="0414a-103">Encapsulates binding policy and assembly location for each assembly.</span></span> <span data-ttu-id="0414a-104">`dependentAssembly`アセンブリごとに1つの要素を使用します。</span><span class="sxs-lookup"><span data-stu-id="0414a-104">Use one `dependentAssembly` element for each assembly.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<assemblyBinding>**](assemblybinding-element-for-runtime.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<dependentAssembly>**  
  
## <a name="syntax"></a><span data-ttu-id="0414a-105">構文</span><span class="sxs-lookup"><span data-stu-id="0414a-105">Syntax</span></span>  
  
```xml  
<dependentAssembly>
</dependentAssembly>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0414a-106">属性および要素</span><span class="sxs-lookup"><span data-stu-id="0414a-106">Attributes and Elements</span></span>  

 <span data-ttu-id="0414a-107">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="0414a-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0414a-108">属性</span><span class="sxs-lookup"><span data-stu-id="0414a-108">Attributes</span></span>  

 <span data-ttu-id="0414a-109">なし。</span><span class="sxs-lookup"><span data-stu-id="0414a-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="0414a-110">子要素</span><span class="sxs-lookup"><span data-stu-id="0414a-110">Child Elements</span></span>  
  
|<span data-ttu-id="0414a-111">要素</span><span class="sxs-lookup"><span data-stu-id="0414a-111">Element</span></span>|<span data-ttu-id="0414a-112">説明</span><span class="sxs-lookup"><span data-stu-id="0414a-112">Description</span></span>|  
|-------------|-----------------|  
|`assemblyIdentity`|<span data-ttu-id="0414a-113">アセンブリに関する識別情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="0414a-113">Contains identifying information about the assembly.</span></span> <span data-ttu-id="0414a-114">この要素は、各要素に含める必要があり `dependentAssembly` ます。</span><span class="sxs-lookup"><span data-stu-id="0414a-114">This element must be included in each `dependentAssembly` element.</span></span>|  
|`codeBase`|<span data-ttu-id="0414a-115">ランタイムがコンピューターにインストールされていない場合に、共有アセンブリを見つけることができる場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="0414a-115">Specifies where the runtime can find a shared assembly if it is not installed on the computer.</span></span>|  
|`bindingRedirect`|<span data-ttu-id="0414a-116">1 つのアセンブリ バージョンを別のバージョンにリダイレクトします。</span><span class="sxs-lookup"><span data-stu-id="0414a-116">Redirects one assembly version to another.</span></span>|  
|`publisherPolicy`|<span data-ttu-id="0414a-117">ランタイムがこのアセンブリの発行者ポリシーを適用するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="0414a-117">Specifies whether the runtime applies publisher policy for this assembly.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="0414a-118">親要素</span><span class="sxs-lookup"><span data-stu-id="0414a-118">Parent Elements</span></span>  
  
|<span data-ttu-id="0414a-119">要素</span><span class="sxs-lookup"><span data-stu-id="0414a-119">Element</span></span>|<span data-ttu-id="0414a-120">説明</span><span class="sxs-lookup"><span data-stu-id="0414a-120">Description</span></span>|  
|-------------|-----------------|  
|`assemblyBinding`|<span data-ttu-id="0414a-121">アセンブリ バージョンのリダイレクトおよびアセンブリの位置に関する情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="0414a-121">Contains information about assembly version redirection and the locations of assemblies.</span></span>|  
|`configuration`|<span data-ttu-id="0414a-122">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="0414a-122">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="0414a-123">アセンブリのバインディングとガベージ コレクションに関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="0414a-123">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="0414a-124">例</span><span class="sxs-lookup"><span data-stu-id="0414a-124">Example</span></span>  

 <span data-ttu-id="0414a-125">次の例は、2つのアセンブリのアセンブリ情報をカプセル化する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="0414a-125">The following example shows how to encapsulate assembly information for two assemblies.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="0414a-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="0414a-126">See also</span></span>

- [<span data-ttu-id="0414a-127">ランタイム設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="0414a-127">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="0414a-128">構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="0414a-128">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="0414a-129">アセンブリ バージョンのリダイレクト</span><span class="sxs-lookup"><span data-stu-id="0414a-129">Redirecting Assembly Versions</span></span>](../../redirect-assembly-versions.md)
