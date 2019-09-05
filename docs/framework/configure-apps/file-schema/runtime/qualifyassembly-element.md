---
title: <qualifyAssembly> 要素
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#qualifyAssembly
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/qualifyAssembly
helpviewer_keywords:
- container tags, <qualifyAssembly> element
- <qualifyAssembly> element
- qualifyAssembly element
ms.assetid: ad6442f6-1a9d-43b6-b733-04ac1b7f9b82
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 581b19cf74dcb5c2d5c4a549847629503fe0b6ff
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252371"
---
# <a name="qualifyassembly-element"></a><span data-ttu-id="17762-102">\<qualifyAssembly > 要素</span><span class="sxs-lookup"><span data-stu-id="17762-102">\<qualifyAssembly> Element</span></span>
<span data-ttu-id="17762-103">部分名が使用された場合に動的に読み込む必要があるアセンブリの完全名を指定します。</span><span class="sxs-lookup"><span data-stu-id="17762-103">Specifies the full name of the assembly that should be dynamically loaded when a partial name is used.</span></span>  
  
<span data-ttu-id="17762-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="17762-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="17762-105">&nbsp;&nbsp;[ **\<ランタイム >** ](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="17762-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="17762-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<assemblyBinding >** ](assemblybinding-element-for-runtime.md)</span><span class="sxs-lookup"><span data-stu-id="17762-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<assemblyBinding>**](assemblybinding-element-for-runtime.md)</span></span>\
<span data-ttu-id="17762-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<qualifyAssembly>**</span><span class="sxs-lookup"><span data-stu-id="17762-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<qualifyAssembly>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="17762-108">構文</span><span class="sxs-lookup"><span data-stu-id="17762-108">Syntax</span></span>  
  
```xml  
      <qualifyAssembly partialName=  
      "PartialAssemblyName"  
                 fullName="FullAssemblyName"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="17762-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="17762-109">Attributes and Elements</span></span>  
 <span data-ttu-id="17762-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="17762-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="17762-111">属性</span><span class="sxs-lookup"><span data-stu-id="17762-111">Attributes</span></span>  
  
|<span data-ttu-id="17762-112">属性</span><span class="sxs-lookup"><span data-stu-id="17762-112">Attribute</span></span>|<span data-ttu-id="17762-113">説明</span><span class="sxs-lookup"><span data-stu-id="17762-113">Description</span></span>|  
|---------------|-----------------|  
|`partialName`|<span data-ttu-id="17762-114">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="17762-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="17762-115">コードに表示されるアセンブリの名前の一部を指定します。</span><span class="sxs-lookup"><span data-stu-id="17762-115">Specifies the partial name of the assembly as it appears in the code.</span></span>|  
|`fullName`|<span data-ttu-id="17762-116">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="17762-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="17762-117">グローバルアセンブリキャッシュに表示されるアセンブリの完全名を指定します。</span><span class="sxs-lookup"><span data-stu-id="17762-117">Specifies the full name of the assembly as it appears in the global assembly cache.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="17762-118">子要素</span><span class="sxs-lookup"><span data-stu-id="17762-118">Child Elements</span></span>  
 <span data-ttu-id="17762-119">なし。</span><span class="sxs-lookup"><span data-stu-id="17762-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="17762-120">親要素</span><span class="sxs-lookup"><span data-stu-id="17762-120">Parent Elements</span></span>  
  
|<span data-ttu-id="17762-121">要素</span><span class="sxs-lookup"><span data-stu-id="17762-121">Element</span></span>|<span data-ttu-id="17762-122">説明</span><span class="sxs-lookup"><span data-stu-id="17762-122">Description</span></span>|  
|-------------|-----------------|  
|`assemblyBinding`|<span data-ttu-id="17762-123">アセンブリ バージョンのリダイレクトおよびアセンブリの位置に関する情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="17762-123">Contains information about assembly version redirection and the locations of assemblies.</span></span>|  
|`configuration`|<span data-ttu-id="17762-124">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="17762-124">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="17762-125">アセンブリのバインディングとガベージ コレクションに関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="17762-125">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="17762-126">Remarks</span><span class="sxs-lookup"><span data-stu-id="17762-126">Remarks</span></span>  
 <span data-ttu-id="17762-127">部分的なアセンブリ名を使用してメソッドを呼び出すと、共通言語ランタイムによって、アプリケーションのベースディレクトリでのみアセンブリが検索されます。<xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="17762-127">Calling the <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> method using partial assembly names causes the common language runtime to look for the assembly only in the application base directory.</span></span> <span data-ttu-id="17762-128">アプリケーション構成ファイルの **qualifyAssembly>要素を使用してアセンブリの完全な情報(名前、バージョン、公開キートークン、およびカルチャ)を指定すると、共通言語ランタイムによって、\<** グローバルアセンブリキャッシュ。</span><span class="sxs-lookup"><span data-stu-id="17762-128">Use the **\<qualifyAssembly>** element in your application configuration file to provide the full assembly information (name, version, public key token, and culture) and cause the common language runtime to search for the assembly in the global assembly cache.</span></span>  
  
 <span data-ttu-id="17762-129">**FullName**属性には、アセンブリ id の4つのフィールド (名前、バージョン、公開キートークン、およびカルチャ) を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="17762-129">The **fullName** attribute must include the four fields of assembly identity: name, version, public key token, and culture.</span></span> <span data-ttu-id="17762-130">**Partialname**属性は、アセンブリを部分的に参照する必要があります。</span><span class="sxs-lookup"><span data-stu-id="17762-130">The **partialName** attribute must partially reference an assembly.</span></span> <span data-ttu-id="17762-131">少なくともアセンブリのテキスト名 (最も一般的なケース) を指定する必要がありますが、バージョン、公開キートークン、またはカルチャ (または4つすべての4つの組み合わせを含む) を含めることもできます。</span><span class="sxs-lookup"><span data-stu-id="17762-131">You must specify at least the assembly's text name (the most common case), but you can also include version, public key token, or culture (or any combination of the four, but not all four).</span></span> <span data-ttu-id="17762-132">**Partialname**は、呼び出しで指定された名前と一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="17762-132">The **partialName** must match the name specified in your call.</span></span> <span data-ttu-id="17762-133">たとえば、構成ファイルで**partialname**属性としてを指定`Assembly.Load("math, Version=3.3.3.3")` `"math"`し、コードでを呼び出すことはできません。</span><span class="sxs-lookup"><span data-stu-id="17762-133">For example, you cannot specify `"math"` as the **partialName** attribute in your configuration file and call `Assembly.Load("math, Version=3.3.3.3")` in your code.</span></span>  
  
## <a name="example"></a><span data-ttu-id="17762-134">例</span><span class="sxs-lookup"><span data-stu-id="17762-134">Example</span></span>  
 <span data-ttu-id="17762-135">次の例では、呼び出し`Assembly.Load("math")`を`Assembly.Load("math,version=1.0.0.0,publicKeyToken=a1690a5ea44bab32,culture=neutral")`論理的にに変換します。</span><span class="sxs-lookup"><span data-stu-id="17762-135">The following example logically turns the call `Assembly.Load("math")` into `Assembly.Load("math,version=1.0.0.0,publicKeyToken=a1690a5ea44bab32,culture=neutral")`.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <qualifyAssembly partialName="math"   
                         fullName=  
"math,version=1.0.0.0,publicKeyToken=a1690a5ea44bab32,culture=neutral"/>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="17762-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="17762-136">See also</span></span>

- [<span data-ttu-id="17762-137">ランタイム設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="17762-137">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="17762-138">ランタイムがアセンブリを検索する方法</span><span class="sxs-lookup"><span data-stu-id="17762-138">How the Runtime Locates Assemblies</span></span>](../../../deployment/how-the-runtime-locates-assemblies.md)
- <span data-ttu-id="17762-139">[部分アセンブリ参照](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/0a7zy9z5(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="17762-139">[Partial Assembly References](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/0a7zy9z5(v=vs.100))</span></span>
