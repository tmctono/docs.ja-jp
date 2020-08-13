---
title: ControlBuilderInterceptor クラス
ms.date: 08/11/2020
api_name:
- System.Web.Compilation.ControlBuilderInterceptor
api_location:
- System.Web.dll
api_type:
- Assembly
topic_type:
- apiref
ms.openlocfilehash: 0cd7409deb9cb84783cfa70600999fa4b2a2d2e2
ms.sourcegitcommit: d337df55f83325918cbbd095eb573400bea49064
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/13/2020
ms.locfileid: "88187986"
---
# <a name="controlbuilderinterceptor-class"></a><span data-ttu-id="c622b-102">ControlBuilderInterceptor クラス</span><span class="sxs-lookup"><span data-stu-id="c622b-102">ControlBuilderInterceptor class</span></span>

<span data-ttu-id="c622b-103">`ControlBuilderInterceptor`クラスを使用すると、コンパイルプロセスをカスタマイズまたは制御できます。</span><span class="sxs-lookup"><span data-stu-id="c622b-103">The `ControlBuilderInterceptor` class allows the compilation process to be customized or controlled.</span></span>

## <a name="syntax"></a><span data-ttu-id="c622b-104">構文</span><span class="sxs-lookup"><span data-stu-id="c622b-104">Syntax</span></span>

```csharp
internal class ControlBuilderInterceptor
```

> [!WARNING]
> <span data-ttu-id="c622b-105">`ControlBuilderInterceptor`クラスは内部であり、コードで直接使用するためのものではありません。</span><span class="sxs-lookup"><span data-stu-id="c622b-105">The `ControlBuilderInterceptor` class is internal and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="c622b-106">「解説」で説明されているように、この型の存在は、インターセプター型のサポートが存在するかどうかを確認するために確認できます。</span><span class="sxs-lookup"><span data-stu-id="c622b-106">As described in the Remarks section, the existence of this type can be checked to determine whether interceptor type support is present.</span></span> <span data-ttu-id="c622b-107">Microsoft では、どのような状況でも、実稼働アプリケーションでこのクラスを使用することはサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="c622b-107">Microsoft does not support any other use of this class in a production application under any circumstance.</span></span>

## <a name="remarks"></a><span data-ttu-id="c622b-108">解説</span><span class="sxs-lookup"><span data-stu-id="c622b-108">Remarks</span></span>

<span data-ttu-id="c622b-109">.NET Framework 2.0 および .NET Framework 3.5 では、 [年 8 2020 月](https://portal.msrc.microsoft.com/security-guidance/releasenotedetail/2020-Aug) の更新プログラムにより、インターセプターの種類を使用してコンパイルプロセスをカスタマイズまたは制御するためのサポートが追加されました。</span><span class="sxs-lookup"><span data-stu-id="c622b-109">In .NET Framework 2.0 and .NET Framework 3.5, the [August 2020](https://portal.msrc.microsoft.com/security-guidance/releasenotedetail/2020-Aug) updates added support for using an interceptor type to customize or control the compilation process.</span></span> <span data-ttu-id="c622b-110">このサポートが存在するかどうかを判断するには、 <xref:System.Type.GetType?displayProperty=nameWithType> 次の `ControlBuilderInterceptor` コードに示すように、を使用して型の存在を確認します。</span><span class="sxs-lookup"><span data-stu-id="c622b-110">You can determine whether this support is present by using <xref:System.Type.GetType?displayProperty=nameWithType> to check the existence of the `ControlBuilderInterceptor` type, as demonstrated in the following code.</span></span>

```csharp
Type type = Type.GetType("System.Web.Compilation.ControlBuilderInterceptor, System.Web, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a");
```

<span data-ttu-id="c622b-111">戻り値が null 以外の場合は、インターセプターのサポートが存在します。</span><span class="sxs-lookup"><span data-stu-id="c622b-111">If the return value is non-null, then interceptor support is present.</span></span> <span data-ttu-id="c622b-112">戻り値がの場合、 `null` または例外がスローされた場合は、2020年8月の更新プログラムがインストールされておらず、インターセプターのサポートは存在しません。</span><span class="sxs-lookup"><span data-stu-id="c622b-112">If the return value is `null`, or if an exception is thrown, then the August 2020 updates have not been installed, and interceptor support is absent.</span></span>

<span data-ttu-id="c622b-113">インターセプターのサポートが存在する場合は、 <xref:System.Web.Compilation.ControlBuilderInterceptor> 以降のバージョンの .NET Framework とまったく同じ方法で、コンパイルプロセスと対話するインターセプター型を記述して登録できます。</span><span class="sxs-lookup"><span data-stu-id="c622b-113">If interceptor support is present, you can write and register an interceptor type that will interact with the compilation process in exactly the same way that <xref:System.Web.Compilation.ControlBuilderInterceptor> does on later versions of .NET Framework.</span></span> <span data-ttu-id="c622b-114">.NET Framework 2.0 および .NET Framework 3.5 では、次の要件を満たす任意のクラスをインターセプター型にすることができます。</span><span class="sxs-lookup"><span data-stu-id="c622b-114">In .NET Framework 2.0 and .NET Framework 3.5, the interceptor type can be any class that meets the following requirements:</span></span>

* <span data-ttu-id="c622b-115">には、パブリックなパラメーターなしのコンストラクターがあります。</span><span class="sxs-lookup"><span data-stu-id="c622b-115">Has a public, parameterless constructor.</span></span>
* <span data-ttu-id="c622b-116">には、とという名前のパブリックな非静的メソッドがあります。このメソッドは、 `PreControlBuilderInit` `OnProcessGeneratedCode` およびメソッドと同じシグネチャとセマンティクスを持ち <xref:System.Web.Compilation.ControlBuilderInterceptor.PreControlBuilderInit(System.Web.UI.ControlBuilder,System.Web.UI.TemplateParser,System.Web.UI.ControlBuilder,System.Type,System.String,System.String,System.Collections.IDictionary,System.Collections.IDictionary)> <xref:System.Web.Compilation.ControlBuilderInterceptor.OnProcessGeneratedCode(System.Web.UI.ControlBuilder,System.CodeDom.CodeCompileUnit,System.CodeDom.CodeTypeDeclaration,System.CodeDom.CodeTypeDeclaration,System.CodeDom.CodeMemberMethod,System.CodeDom.CodeMemberMethod,System.Collections.IDictionary)> ます。これは、.NET Framework の新しいバージョンに存在します。</span><span class="sxs-lookup"><span data-stu-id="c622b-116">Has public, non-static methods named `PreControlBuilderInit` and `OnProcessGeneratedCode` that have the same signature and semantics as the <xref:System.Web.Compilation.ControlBuilderInterceptor.PreControlBuilderInit(System.Web.UI.ControlBuilder,System.Web.UI.TemplateParser,System.Web.UI.ControlBuilder,System.Type,System.String,System.String,System.Collections.IDictionary,System.Collections.IDictionary)> and <xref:System.Web.Compilation.ControlBuilderInterceptor.OnProcessGeneratedCode(System.Web.UI.ControlBuilder,System.CodeDom.CodeCompileUnit,System.CodeDom.CodeTypeDeclaration,System.CodeDom.CodeTypeDeclaration,System.CodeDom.CodeMemberMethod,System.CodeDom.CodeMemberMethod,System.Collections.IDictionary)> methods, which exist in later versions of .NET Framework.</span></span>

<span data-ttu-id="c622b-117">`aspnet:20ControlBuilderInterceptor`ASP.NET アプリケーション設定 () のキーを使用して、インターセプターの種類を登録し `<appSettings>` ます。</span><span class="sxs-lookup"><span data-stu-id="c622b-117">Register the interceptor type by using the `aspnet:20ControlBuilderInterceptor` key in ASP.NET application settings (`<appSettings>`).</span></span> <span data-ttu-id="c622b-118">このアプリケーション設定は、コンピューターまたはアプリケーションの *web.config* ファイルに一覧表示されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="c622b-118">This application setting must be listed in your computer or application *web.config* file.</span></span> <span data-ttu-id="c622b-119">アセンブリ修飾型名を使用して、インターセプターの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="c622b-119">Specify the interceptor type by using its assembly-qualified type name.</span></span> <span data-ttu-id="c622b-120">次の例は、という名前のインターセプター型を登録する方法を示して `Fabrikam.Interceptor` います。</span><span class="sxs-lookup"><span data-stu-id="c622b-120">The following example shows how to register an interceptor type named `Fabrikam.Interceptor`.</span></span>

```xml
<configuration>
  ...
  <appSettings>
    ...
    <add key="aspnet:20ControlBuilderInterceptor"
         value="Fabrikam.Interceptor, Fabrikam, Version=1.0.0.0, Culture=neutral, PublicKeyToken=2b3831f2f2b744f7" />
  </appSettings>
</configuration>
```

<span data-ttu-id="c622b-121">型のアセンブリ修飾名を取得するには、次の <xref:System.Type.AssemblyQualifiedName?displayProperty=nameWithType> コードに示すように、プロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="c622b-121">To retrieve the assembly-qualified name of a type, use the <xref:System.Type.AssemblyQualifiedName?displayProperty=nameWithType> property, as demonstrated in the following code.</span></span>

```csharp
string assemblyQualifiedName = typeof(Fabrikam.Interceptor).AssemblyQualifiedName;
```

<span data-ttu-id="c622b-122">インターセプターのサポートが存在する場合、コンパイルプロセスは、前述の方法で表示されている型と対話します。</span><span class="sxs-lookup"><span data-stu-id="c622b-122">When interceptor support is present, the compilation process interacts with the listed type in the manner described above.</span></span> <span data-ttu-id="c622b-123">インターセプターのサポートが存在しない場合、アプリケーションの設定は無視され、効果はありません。</span><span class="sxs-lookup"><span data-stu-id="c622b-123">When interceptor support is absent, the application setting is ignored and has no effect.</span></span>

## <a name="requirements"></a><span data-ttu-id="c622b-124">必要条件</span><span class="sxs-lookup"><span data-stu-id="c622b-124">Requirements</span></span>

<span data-ttu-id="c622b-125">**名前空間:** System.web. コンパイル</span><span class="sxs-lookup"><span data-stu-id="c622b-125">**Namespace:** System.Web.Compilation</span></span>

<span data-ttu-id="c622b-126">**アセンブリ:** System.web (System.Web.dll)</span><span class="sxs-lookup"><span data-stu-id="c622b-126">**Assembly:** System.Web (in System.Web.dll)</span></span>

<span data-ttu-id="c622b-127">**.NET Framework のバージョン:** 3.5、2.0</span><span class="sxs-lookup"><span data-stu-id="c622b-127">**.NET Framework versions:** 3.5, 2.0</span></span>
