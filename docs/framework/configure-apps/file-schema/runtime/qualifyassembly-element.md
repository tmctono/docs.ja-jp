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
ms.openlocfilehash: 74e83900c68ab4b3fe01beb3f97657b0140d78ad
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153920"
---
# <a name="qualifyassembly-element"></a><span data-ttu-id="9b477-102">\<アセンブリ>要素を修飾する</span><span class="sxs-lookup"><span data-stu-id="9b477-102">\<qualifyAssembly> Element</span></span>
<span data-ttu-id="9b477-103">部分名が使用された場合に動的に読み込む必要があるアセンブリの完全名を指定します。</span><span class="sxs-lookup"><span data-stu-id="9b477-103">Specifies the full name of the assembly that should be dynamically loaded when a partial name is used.</span></span>  
  
<span data-ttu-id="9b477-104">[**\<構成>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="9b477-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="9b477-105">&nbsp;&nbsp;[**\<ランタイム>**](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="9b477-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="9b477-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<アセンブリバインディング>**](assemblybinding-element-for-runtime.md)</span><span class="sxs-lookup"><span data-stu-id="9b477-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<assemblyBinding>**](assemblybinding-element-for-runtime.md)</span></span>\
<span data-ttu-id="9b477-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<アセンブリ>を修飾する**</span><span class="sxs-lookup"><span data-stu-id="9b477-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<qualifyAssembly>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9b477-108">構文</span><span class="sxs-lookup"><span data-stu-id="9b477-108">Syntax</span></span>  
  
```xml  
      <qualifyAssembly partialName=  
      "PartialAssemblyName"  
                 fullName="FullAssemblyName"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9b477-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="9b477-109">Attributes and Elements</span></span>  
 <span data-ttu-id="9b477-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="9b477-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9b477-111">属性</span><span class="sxs-lookup"><span data-stu-id="9b477-111">Attributes</span></span>  
  
|<span data-ttu-id="9b477-112">属性</span><span class="sxs-lookup"><span data-stu-id="9b477-112">Attribute</span></span>|<span data-ttu-id="9b477-113">説明</span><span class="sxs-lookup"><span data-stu-id="9b477-113">Description</span></span>|  
|---------------|-----------------|  
|`partialName`|<span data-ttu-id="9b477-114">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="9b477-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="9b477-115">コードに表示されるアセンブリの部分名を指定します。</span><span class="sxs-lookup"><span data-stu-id="9b477-115">Specifies the partial name of the assembly as it appears in the code.</span></span>|  
|`fullName`|<span data-ttu-id="9b477-116">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="9b477-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="9b477-117">グローバル アセンブリ キャッシュに表示されるアセンブリの完全な名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="9b477-117">Specifies the full name of the assembly as it appears in the global assembly cache.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9b477-118">子要素</span><span class="sxs-lookup"><span data-stu-id="9b477-118">Child Elements</span></span>  
 <span data-ttu-id="9b477-119">[なし] :</span><span class="sxs-lookup"><span data-stu-id="9b477-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9b477-120">親要素</span><span class="sxs-lookup"><span data-stu-id="9b477-120">Parent Elements</span></span>  
  
|<span data-ttu-id="9b477-121">要素</span><span class="sxs-lookup"><span data-stu-id="9b477-121">Element</span></span>|<span data-ttu-id="9b477-122">説明</span><span class="sxs-lookup"><span data-stu-id="9b477-122">Description</span></span>|  
|-------------|-----------------|  
|`assemblyBinding`|<span data-ttu-id="9b477-123">アセンブリ バージョンのリダイレクトおよびアセンブリの位置に関する情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="9b477-123">Contains information about assembly version redirection and the locations of assemblies.</span></span>|  
|`configuration`|<span data-ttu-id="9b477-124">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="9b477-124">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="9b477-125">アセンブリのバインディングとガベージ コレクションに関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="9b477-125">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9b477-126">解説</span><span class="sxs-lookup"><span data-stu-id="9b477-126">Remarks</span></span>  
 <span data-ttu-id="9b477-127">部分アセンブリ<xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType>名を使用してメソッドを呼び出すと、共通言語ランタイムはアプリケーションベースディレクトリ内でのみアセンブリを検索します。</span><span class="sxs-lookup"><span data-stu-id="9b477-127">Calling the <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> method using partial assembly names causes the common language runtime to look for the assembly only in the application base directory.</span></span> <span data-ttu-id="9b477-128">アプリケーション構成ファイルの **[アセンブリ>の要素を修飾する] を使用して、完全なアセンブリ情報 (名前、バージョン、公開キー トークン、およびカルチャ) を提供し、共通言語ランタイムがグローバル アセンブリ キャッシュ内のアセンブリを検索するようにします。 \<**</span><span class="sxs-lookup"><span data-stu-id="9b477-128">Use the **\<qualifyAssembly>** element in your application configuration file to provide the full assembly information (name, version, public key token, and culture) and cause the common language runtime to search for the assembly in the global assembly cache.</span></span>  
  
 <span data-ttu-id="9b477-129">**fullName**属性には、アセンブリ ID の 4 つのフィールド (名前、バージョン、公開キー トークン、およびカルチャ) を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="9b477-129">The **fullName** attribute must include the four fields of assembly identity: name, version, public key token, and culture.</span></span> <span data-ttu-id="9b477-130">**partialName**属性は、アセンブリを部分的に参照する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9b477-130">The **partialName** attribute must partially reference an assembly.</span></span> <span data-ttu-id="9b477-131">少なくともアセンブリのテキスト名 (最も一般的なケース) を指定する必要がありますが、バージョン、公開キー トークン、またはカルチャ (または 4 つの組み合わせ)を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="9b477-131">You must specify at least the assembly's text name (the most common case), but you can also include version, public key token, or culture (or any combination of the four, but not all four).</span></span> <span data-ttu-id="9b477-132">**partialName**は、呼び出しで指定された名前と一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9b477-132">The **partialName** must match the name specified in your call.</span></span> <span data-ttu-id="9b477-133">たとえば、構成ファイルで`"math"`**partialName**属性として指定してコードを呼び`Assembly.Load("math, Version=3.3.3.3")`出すことはできません。</span><span class="sxs-lookup"><span data-stu-id="9b477-133">For example, you cannot specify `"math"` as the **partialName** attribute in your configuration file and call `Assembly.Load("math, Version=3.3.3.3")` in your code.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9b477-134">例</span><span class="sxs-lookup"><span data-stu-id="9b477-134">Example</span></span>  
 <span data-ttu-id="9b477-135">次の例では、呼び出`Assembly.Load("math")`し`Assembly.Load("math,version=1.0.0.0,publicKeyToken=a1690a5ea44bab32,culture=neutral")`を論理的に に に に変換します。</span><span class="sxs-lookup"><span data-stu-id="9b477-135">The following example logically turns the call `Assembly.Load("math")` into `Assembly.Load("math,version=1.0.0.0,publicKeyToken=a1690a5ea44bab32,culture=neutral")`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="9b477-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="9b477-136">See also</span></span>

- [<span data-ttu-id="9b477-137">ランタイム設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="9b477-137">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="9b477-138">ランタイムがアセンブリを検索する方法</span><span class="sxs-lookup"><span data-stu-id="9b477-138">How the Runtime Locates Assemblies</span></span>](../../../deployment/how-the-runtime-locates-assemblies.md)
- <span data-ttu-id="9b477-139">[部分アセンブリ参照](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/0a7zy9z5(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="9b477-139">[Partial Assembly References](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/0a7zy9z5(v=vs.100))</span></span>
