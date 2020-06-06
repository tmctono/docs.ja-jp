---
title: <supportPortability> 要素
ms.date: 03/30/2017
helpviewer_keywords:
- supportPortability element
- <supportPortability> element
ms.assetid: 6453ef66-19b4-41f3-b712-52d0c2abc9ca
ms.openlocfilehash: 63c309a8a93c1d31ed8f73a495cf5154c3590d56
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "73115653"
---
# <a name="supportportability-element"></a><span data-ttu-id="f8845-102">\<supportPortability> 要素</span><span class="sxs-lookup"><span data-stu-id="f8845-102">\<supportPortability> Element</span></span>
<span data-ttu-id="f8845-103">.NET Framework の 2 つの異なる実装にある同じアセンブリを 1 つのアプリケーションから参照できるように、既定の動作を無効にすることができます。既定の動作では、アプリケーションの移植性を高めるために、このようなアセンブリは同等のものとして扱われます。</span><span class="sxs-lookup"><span data-stu-id="f8845-103">Specifies that an application can reference the same assembly in two different implementations of the .NET Framework, by disabling the default behavior that treats the assemblies as equivalent for application portability purposes.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<assemblyBinding>**](assemblybinding-element-for-runtime.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<supportPortability>**  
  
## <a name="syntax"></a><span data-ttu-id="f8845-104">構文</span><span class="sxs-lookup"><span data-stu-id="f8845-104">Syntax</span></span>  
  
```xml  
<supportPortability PKT="public_key_token" enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f8845-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="f8845-105">Attributes and Elements</span></span>  

<span data-ttu-id="f8845-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="f8845-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f8845-107">属性</span><span class="sxs-lookup"><span data-stu-id="f8845-107">Attributes</span></span>  
  
|<span data-ttu-id="f8845-108">属性</span><span class="sxs-lookup"><span data-stu-id="f8845-108">Attribute</span></span>|<span data-ttu-id="f8845-109">説明</span><span class="sxs-lookup"><span data-stu-id="f8845-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f8845-110">PKT</span><span class="sxs-lookup"><span data-stu-id="f8845-110">PKT</span></span>|<span data-ttu-id="f8845-111">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="f8845-111">Required attribute.</span></span><br /><br /> <span data-ttu-id="f8845-112">対象となるアセンブリの公開キー トークンを文字列で指定します。</span><span class="sxs-lookup"><span data-stu-id="f8845-112">Specifies the public key token of the affected assembly, as a string.</span></span>|  
|<span data-ttu-id="f8845-113">enabled</span><span class="sxs-lookup"><span data-stu-id="f8845-113">enabled</span></span>|<span data-ttu-id="f8845-114">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="f8845-114">Optional attribute.</span></span><br /><br /> <span data-ttu-id="f8845-115">指定した .NET Framework アセンブリの複数の実装間での移植性に対するサポートを有効にするかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="f8845-115">Specifies whether support for portability between implementations of the specified .NET Framework assembly should be enabled.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="f8845-116">enabled 属性</span><span class="sxs-lookup"><span data-stu-id="f8845-116">enabled Attribute</span></span>  
  
|<span data-ttu-id="f8845-117">値</span><span class="sxs-lookup"><span data-stu-id="f8845-117">Value</span></span>|<span data-ttu-id="f8845-118">Description</span><span class="sxs-lookup"><span data-stu-id="f8845-118">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="f8845-119">true</span><span class="sxs-lookup"><span data-stu-id="f8845-119">true</span></span>|<span data-ttu-id="f8845-120">指定した .NET Framework アセンブリの複数の実装間での移植性に対するサポートを有効にします。</span><span class="sxs-lookup"><span data-stu-id="f8845-120">Enable support for portability between implementations of the specified .NET Framework assembly.</span></span> <span data-ttu-id="f8845-121">既定値です。</span><span class="sxs-lookup"><span data-stu-id="f8845-121">This is the default.</span></span>|  
|<span data-ttu-id="f8845-122">false</span><span class="sxs-lookup"><span data-stu-id="f8845-122">false</span></span>|<span data-ttu-id="f8845-123">指定した .NET Framework アセンブリの複数の実装間での移植性に対するサポートを無効にします。</span><span class="sxs-lookup"><span data-stu-id="f8845-123">Disable support for portability between implementations of the specified .NET Framework assembly.</span></span> <span data-ttu-id="f8845-124">この場合、指定したアセンブリの複数の実装をアプリケーションで参照できます。</span><span class="sxs-lookup"><span data-stu-id="f8845-124">This enables the application to have references to multiple implementations of the specified assembly.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f8845-125">子要素</span><span class="sxs-lookup"><span data-stu-id="f8845-125">Child Elements</span></span>  

<span data-ttu-id="f8845-126">なし。</span><span class="sxs-lookup"><span data-stu-id="f8845-126">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f8845-127">親要素</span><span class="sxs-lookup"><span data-stu-id="f8845-127">Parent Elements</span></span>  
  
|<span data-ttu-id="f8845-128">要素</span><span class="sxs-lookup"><span data-stu-id="f8845-128">Element</span></span>|<span data-ttu-id="f8845-129">Description</span><span class="sxs-lookup"><span data-stu-id="f8845-129">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="f8845-130">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="f8845-130">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="f8845-131">アセンブリのバインディングとガベージ コレクションに関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="f8845-131">Contains information about assembly binding and garbage collection.</span></span>|  
|`assemblyBinding`|<span data-ttu-id="f8845-132">アセンブリ バージョンのリダイレクトおよびアセンブリの位置に関する情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="f8845-132">Contains information about assembly version redirection and the locations of assemblies.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f8845-133">解説</span><span class="sxs-lookup"><span data-stu-id="f8845-133">Remarks</span></span>  

<span data-ttu-id="f8845-134">.NET Framework 4 以降、.NET Framework の2つの実装のいずれかを使用できるアプリケーションに対して、サポートが自動的に提供されます。たとえば、.NET Framework の実装や、Silverlight の実装のための .NET Framework です。</span><span class="sxs-lookup"><span data-stu-id="f8845-134">Beginning with the .NET Framework 4, support is automatically provided for applications that can use either of two implementations of the .NET Framework, for example either the .NET Framework implementation or the .NET Framework for Silverlight implementation.</span></span> <span data-ttu-id="f8845-135">特定の .NET Framework アセンブリの 2 つの実装は、アセンブリ バインダーで同等と見なされます。</span><span class="sxs-lookup"><span data-stu-id="f8845-135">The two implementations of a particular .NET Framework assembly are seen as equivalent by the assembly binder.</span></span> <span data-ttu-id="f8845-136">一部のシナリオでは、アプリケーションの移植性を高めるためのこの機能が問題になります。</span><span class="sxs-lookup"><span data-stu-id="f8845-136">In a few scenarios, this application portability feature causes problems.</span></span> <span data-ttu-id="f8845-137">そのようなシナリオでは、`<supportPortability>` 要素を使用して、この機能を無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="f8845-137">In those scenarios, the `<supportPortability>` element can be used to disable the feature.</span></span>  
  
<span data-ttu-id="f8845-138">一例として、特定の参照アセンブリの .NET Framework の実装と .NET Framework for Silverlight の実装の両方を参照する必要があるアセンブリが挙げられます。</span><span class="sxs-lookup"><span data-stu-id="f8845-138">One such scenario is an assembly that has to reference both the .NET Framework implementation and the .NET Framework for Silverlight implementation of a particular reference assembly.</span></span> <span data-ttu-id="f8845-139">たとえば、WPF (Windows Presentation Foundation) で作成された XAML デザイナーにおいて、デザイナーのユーザー インターフェイスとして WPF デスクトップの実装を参照すると共に、Silverlight の実装に組み込まれている WPF のサブセットも参照する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="f8845-139">For example, a XAML designer written in Windows Presentation Foundation (WPF) might need to reference both the WPF Desktop implementation, for the designer's user interface, and the subset of WPF that is included in the Silverlight implementation.</span></span> <span data-ttu-id="f8845-140">既定では、この 2 つのアセンブリはアセンブリ バインディングで同等と見なされるため、別々に参照するとコンパイラ エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="f8845-140">By default, the separate references cause a compiler error, because assembly binding sees the two assemblies as equivalent.</span></span> <span data-ttu-id="f8845-141">この要素を使用すると、既定の動作を無効にし、コンパイルを正常に実行できます。</span><span class="sxs-lookup"><span data-stu-id="f8845-141">This element disables the default behavior, and allows compilation to succeed.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="f8845-142">コンパイラから共通言語ランタイムのアセンブリ バインディング ロジックに情報を渡すには、`/appconfig` コンパイラ オプションを使用して、この要素を含む app.config ファイルの場所を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f8845-142">In order for the compiler to pass the information to the common language runtime's assembly-binding logic, you must use the `/appconfig` compiler option to specify the location of the app.config file that contains this element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f8845-143">例</span><span class="sxs-lookup"><span data-stu-id="f8845-143">Example</span></span>  

<span data-ttu-id="f8845-144">.NET Framework と .NET Framework for Silverlight の両方の実装に存在する .NET Framework アセンブリについて、その両方の実装をアプリケーションで参照できるようにする例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="f8845-144">The following example enables an application to have references to both the .NET Framework implementation and the .NET Framework for Silverlight implementation of any .NET Framework assembly that exists in both implementations.</span></span> <span data-ttu-id="f8845-145">`/appconfig` コンパイラ オプションを使用して、この app.config ファイルの場所を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f8845-145">The `/appconfig` compiler option must be used to specify the location of this app.config file.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="f8845-146">関連項目</span><span class="sxs-lookup"><span data-stu-id="f8845-146">See also</span></span>

- [<span data-ttu-id="f8845-147">-appconfig (C# コンパイラ オプション)</span><span class="sxs-lookup"><span data-stu-id="f8845-147">-appconfig (C# Compiler Options)</span></span>](../../../../csharp/language-reference/compiler-options/appconfig-compiler-option.md)
- <span data-ttu-id="f8845-148">[.NET Framework アセンブリ統合の概要](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/db7849ey(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="f8845-148">[.NET Framework Assembly Unification Overview](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/db7849ey(v=vs.100))</span></span>
