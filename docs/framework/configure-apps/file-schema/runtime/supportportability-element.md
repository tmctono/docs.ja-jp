---
title: <supportPortability> 要素
ms.date: 03/30/2017
helpviewer_keywords:
- supportPortability element
- <supportPortability> element
ms.assetid: 6453ef66-19b4-41f3-b712-52d0c2abc9ca
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1848db96b8f466f617c58f0fdd879ffe3b2022bd
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69927258"
---
# <a name="supportportability-element"></a><span data-ttu-id="a1dbb-102">\<supportPortability> 要素</span><span class="sxs-lookup"><span data-stu-id="a1dbb-102">\<supportPortability> Element</span></span>
<span data-ttu-id="a1dbb-103">.NET Framework の 2 つの異なる実装にある同じアセンブリを 1 つのアプリケーションから参照できるように、既定の動作を無効にすることができます。既定の動作では、アプリケーションの移植性を高めるために、このようなアセンブリは同等のものとして扱われます。</span><span class="sxs-lookup"><span data-stu-id="a1dbb-103">Specifies that an application can reference the same assembly in two different implementations of the .NET Framework, by disabling the default behavior that treats the assemblies as equivalent for application portability purposes.</span></span>  
  
 <span data-ttu-id="a1dbb-104">\<configuration> 要素</span><span class="sxs-lookup"><span data-stu-id="a1dbb-104">\<configuration> Element</span></span>  
<span data-ttu-id="a1dbb-105">\<runtime> 要素</span><span class="sxs-lookup"><span data-stu-id="a1dbb-105">\<runtime> Element</span></span>  
<span data-ttu-id="a1dbb-106">\<assemblyBinding> 要素</span><span class="sxs-lookup"><span data-stu-id="a1dbb-106">\<assemblyBinding> Element</span></span>  
<span data-ttu-id="a1dbb-107">\<supportPortability> 要素</span><span class="sxs-lookup"><span data-stu-id="a1dbb-107">\<supportPortability> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a1dbb-108">構文</span><span class="sxs-lookup"><span data-stu-id="a1dbb-108">Syntax</span></span>  
  
```xml  
<supportPortability PKT="public_key_token" enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a1dbb-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="a1dbb-109">Attributes and Elements</span></span>  
 <span data-ttu-id="a1dbb-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="a1dbb-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a1dbb-111">属性</span><span class="sxs-lookup"><span data-stu-id="a1dbb-111">Attributes</span></span>  
  
|<span data-ttu-id="a1dbb-112">属性</span><span class="sxs-lookup"><span data-stu-id="a1dbb-112">Attribute</span></span>|<span data-ttu-id="a1dbb-113">説明</span><span class="sxs-lookup"><span data-stu-id="a1dbb-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a1dbb-114">PKT</span><span class="sxs-lookup"><span data-stu-id="a1dbb-114">PKT</span></span>|<span data-ttu-id="a1dbb-115">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="a1dbb-115">Required attribute.</span></span><br /><br /> <span data-ttu-id="a1dbb-116">対象となるアセンブリの公開キー トークンを文字列で指定します。</span><span class="sxs-lookup"><span data-stu-id="a1dbb-116">Specifies the public key token of the affected assembly, as a string.</span></span>|  
|<span data-ttu-id="a1dbb-117">enabled</span><span class="sxs-lookup"><span data-stu-id="a1dbb-117">enabled</span></span>|<span data-ttu-id="a1dbb-118">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="a1dbb-118">Optional attribute.</span></span><br /><br /> <span data-ttu-id="a1dbb-119">指定した .NET Framework アセンブリの複数の実装間での移植性に対するサポートを有効にするかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="a1dbb-119">Specifies whether support for portability between implementations of the specified .NET Framework assembly should be enabled.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="a1dbb-120">enabled 属性</span><span class="sxs-lookup"><span data-stu-id="a1dbb-120">enabled Attribute</span></span>  
  
|<span data-ttu-id="a1dbb-121">値</span><span class="sxs-lookup"><span data-stu-id="a1dbb-121">Value</span></span>|<span data-ttu-id="a1dbb-122">説明</span><span class="sxs-lookup"><span data-stu-id="a1dbb-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="a1dbb-123">true</span><span class="sxs-lookup"><span data-stu-id="a1dbb-123">true</span></span>|<span data-ttu-id="a1dbb-124">指定した .NET Framework アセンブリの複数の実装間での移植性に対するサポートを有効にします。</span><span class="sxs-lookup"><span data-stu-id="a1dbb-124">Enable support for portability between implementations of the specified .NET Framework assembly.</span></span> <span data-ttu-id="a1dbb-125">既定値です。</span><span class="sxs-lookup"><span data-stu-id="a1dbb-125">This is the default.</span></span>|  
|<span data-ttu-id="a1dbb-126">False</span><span class="sxs-lookup"><span data-stu-id="a1dbb-126">false</span></span>|<span data-ttu-id="a1dbb-127">指定した .NET Framework アセンブリの複数の実装間での移植性に対するサポートを無効にします。</span><span class="sxs-lookup"><span data-stu-id="a1dbb-127">Disable support for portability between implementations of the specified .NET Framework assembly.</span></span> <span data-ttu-id="a1dbb-128">この場合、指定したアセンブリの複数の実装をアプリケーションで参照できます。</span><span class="sxs-lookup"><span data-stu-id="a1dbb-128">This enables the application to have references to multiple implementations of the specified assembly.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a1dbb-129">子要素</span><span class="sxs-lookup"><span data-stu-id="a1dbb-129">Child Elements</span></span>  
 <span data-ttu-id="a1dbb-130">なし。</span><span class="sxs-lookup"><span data-stu-id="a1dbb-130">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a1dbb-131">親要素</span><span class="sxs-lookup"><span data-stu-id="a1dbb-131">Parent Elements</span></span>  
  
|<span data-ttu-id="a1dbb-132">要素</span><span class="sxs-lookup"><span data-stu-id="a1dbb-132">Element</span></span>|<span data-ttu-id="a1dbb-133">説明</span><span class="sxs-lookup"><span data-stu-id="a1dbb-133">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="a1dbb-134">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="a1dbb-134">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="a1dbb-135">アセンブリのバインディングとガベージ コレクションに関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="a1dbb-135">Contains information about assembly binding and garbage collection.</span></span>|  
|`assemblyBinding`|<span data-ttu-id="a1dbb-136">アセンブリ バージョンのリダイレクトおよびアセンブリの位置に関する情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="a1dbb-136">Contains information about assembly version redirection and the locations of assemblies.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a1dbb-137">Remarks</span><span class="sxs-lookup"><span data-stu-id="a1dbb-137">Remarks</span></span>  
 <span data-ttu-id="a1dbb-138">.NET Framework 4 以降、.NET Framework の2つの実装のいずれかを使用できるアプリケーションに対して、サポートが自動的に提供されます。たとえば、.NET Framework の実装や、Silverlight の実装のための .NET Framework です。</span><span class="sxs-lookup"><span data-stu-id="a1dbb-138">Beginning with the .NET Framework 4, support is automatically provided for applications that can use either of two implementations of the .NET Framework, for example either the .NET Framework implementation or the .NET Framework for Silverlight implementation.</span></span> <span data-ttu-id="a1dbb-139">特定の .NET Framework アセンブリの 2 つの実装は、アセンブリ バインダーで同等と見なされます。</span><span class="sxs-lookup"><span data-stu-id="a1dbb-139">The two implementations of a particular .NET Framework assembly are seen as equivalent by the assembly binder.</span></span> <span data-ttu-id="a1dbb-140">一部のシナリオでは、アプリケーションの移植性を高めるためのこの機能が問題になります。</span><span class="sxs-lookup"><span data-stu-id="a1dbb-140">In a few scenarios, this application portability feature causes problems.</span></span> <span data-ttu-id="a1dbb-141">そのようなシナリオでは、`<supportPortability>` 要素を使用して、この機能を無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="a1dbb-141">In those scenarios, the `<supportPortability>` element can be used to disable the feature.</span></span>  
  
 <span data-ttu-id="a1dbb-142">一例として、特定の参照アセンブリの .NET Framework の実装と .NET Framework for Silverlight の実装の両方を参照する必要があるアセンブリが挙げられます。</span><span class="sxs-lookup"><span data-stu-id="a1dbb-142">One such scenario is an assembly that has to reference both the .NET Framework implementation and the .NET Framework for Silverlight implementation of a particular reference assembly.</span></span> <span data-ttu-id="a1dbb-143">たとえば、WPF (Windows Presentation Foundation) で作成された XAML デザイナーにおいて、デザイナーのユーザー インターフェイスとして WPF デスクトップの実装を参照すると共に、Silverlight の実装に組み込まれている WPF のサブセットも参照する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="a1dbb-143">For example, a XAML designer written in Windows Presentation Foundation (WPF) might need to reference both the WPF Desktop implementation, for the designer's user interface, and the subset of WPF that is included in the Silverlight implementation.</span></span> <span data-ttu-id="a1dbb-144">既定では、この 2 つのアセンブリはアセンブリ バインディングで同等と見なされるため、別々に参照するとコンパイラ エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="a1dbb-144">By default, the separate references cause a compiler error, because assembly binding sees the two assemblies as equivalent.</span></span> <span data-ttu-id="a1dbb-145">この要素を使用すると、既定の動作を無効にし、コンパイルを正常に実行できます。</span><span class="sxs-lookup"><span data-stu-id="a1dbb-145">This element disables the default behavior, and allows compilation to succeed.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="a1dbb-146">コンパイラから共通言語ランタイムのアセンブリ バインディング ロジックに情報を渡すには、`/appconfig` コンパイラ オプションを使用して、この要素を含む app.config ファイルの場所を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a1dbb-146">In order for the compiler to pass the information to the common language runtime's assembly-binding logic, you must use the `/appconfig` compiler option to specify the location of the app.config file that contains this element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a1dbb-147">例</span><span class="sxs-lookup"><span data-stu-id="a1dbb-147">Example</span></span>  
 <span data-ttu-id="a1dbb-148">.NET Framework と .NET Framework for Silverlight の両方の実装に存在する .NET Framework アセンブリについて、その両方の実装をアプリケーションで参照できるようにする例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="a1dbb-148">The following example enables an application to have references to both the .NET Framework implementation and the .NET Framework for Silverlight implementation of any .NET Framework assembly that exists in both implementations.</span></span> <span data-ttu-id="a1dbb-149">`/appconfig` コンパイラ オプションを使用して、この app.config ファイルの場所を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a1dbb-149">The `/appconfig` compiler option must be used to specify the location of this app.config file.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding>  
         <supportPortability PKT="7cec85d7bea7798e" enable="false"/>  
         <supportPortability PKT="31bf3856ad364e35" enable="false"/>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="a1dbb-150">関連項目</span><span class="sxs-lookup"><span data-stu-id="a1dbb-150">See also</span></span>

- [<span data-ttu-id="a1dbb-151">/appconfig (C#コンパイラオプション)</span><span class="sxs-lookup"><span data-stu-id="a1dbb-151">/appconfig (C# Compiler Options)</span></span>](../../../../csharp/language-reference/compiler-options/appconfig-compiler-option.md)
- <span data-ttu-id="a1dbb-152">[.NET Framework アセンブリの統一の概要](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/db7849ey(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="a1dbb-152">[.NET Framework Assembly Unification Overview](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/db7849ey(v=vs.100))</span></span>
