---
title: 自己完結型アプリケーションのトリミング
description: 自己完結型アプリケーションをトリミングしてサイズを縮小する方法について説明します。 .NET Core は、自己完結型で公開されているアプリケーションでランタイムをバンドルし、通常は必要以上のランタイムを含んでいます。
author: jamshedd
ms.author: jamshedd
ms.date: 01/23/2020
ms.openlocfilehash: 5206ca255c500b382402ac4e7dd3300b7face1cf
ms.sourcegitcommit: 45cced471d59d5dac3f0c92abc9d4849716098a2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/04/2020
ms.locfileid: "80665621"
---
# <a name="trim-self-contained-deployments-and-executables"></a><span data-ttu-id="471c5-104">自己完結型の展開と実行可能ファイルのトリミング</span><span class="sxs-lookup"><span data-stu-id="471c5-104">Trim self-contained deployments and executables</span></span>

<span data-ttu-id="471c5-105">自己完結型アプリケーションを公開する場合、.NET Core ランタイムにはアプリケーションもバンドルされます。</span><span class="sxs-lookup"><span data-stu-id="471c5-105">When publishing an application self-contained, the .NET Core runtime is bundled together with the application.</span></span> <span data-ttu-id="471c5-106">このバンドルにより、パッケージ アプリケーションに大量のコンテンツが追加されます。</span><span class="sxs-lookup"><span data-stu-id="471c5-106">This bundling adds a significant amount of content to your packaged application.</span></span>

<span data-ttu-id="471c5-107">アプリケーションの展開では、多くの場合、サイズが重要な要素になります。</span><span class="sxs-lookup"><span data-stu-id="471c5-107">When it comes to deploying your application, size is often an important factor.</span></span> <span data-ttu-id="471c5-108">通常は、パッケージ アプリケーションのサイズをなるべく小さく保つことが、アプリケーション開発者の目標となります。</span><span class="sxs-lookup"><span data-stu-id="471c5-108">Keeping the size of the package application as small as possible is typically a goal for application developers.</span></span>

<span data-ttu-id="471c5-109">アプリケーションの複雑さによっては、アプリケーションの実行にランタイムのサブセットだけが必要となります。</span><span class="sxs-lookup"><span data-stu-id="471c5-109">Depending on the complexity of the application, only a subset of the runtime is required to run the application.</span></span> <span data-ttu-id="471c5-110">このようなランタイムの未使用部分は不要であり、パッケージ化されたアプリケーションから削除することができます。</span><span class="sxs-lookup"><span data-stu-id="471c5-110">These unused parts of the runtime are unnecessary and can be trimmed from the packaged application.</span></span>

> [!NOTE]
> <span data-ttu-id="471c5-111">トリミングは .NET Core 3.1 の実験的な機能であり、自己完結型で公開されるアプリケーションで_のみ_使用できます。</span><span class="sxs-lookup"><span data-stu-id="471c5-111">Trimming is an experimental feature in .NET Core 3.1 and is _only_ available to applications that are published self-contained.</span></span>

## <a name="trim-your-application"></a><span data-ttu-id="471c5-112">アプリケーションをトリミングする</span><span class="sxs-lookup"><span data-stu-id="471c5-112">Trim your application</span></span>

<span data-ttu-id="471c5-113">次の例は、[dotnet publish](../tools/dotnet-publish.md) コマンドを使用してアプリケーションをトリミングする方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="471c5-113">The following example shows how to trim your application using the [dotnet publish](../tools/dotnet-publish.md) command:</span></span>

```dotnetcli
dotnet publish -c Release -r win10-x64 --self-contained true /p:PublishSingleFile=false /p:PublishTrimmed=true
```

<span data-ttu-id="471c5-114">トリミング機能は、アプリケーション バイナリを調べて、必要なランタイム アセンブリのグラフを検出し、構築することで機能します。</span><span class="sxs-lookup"><span data-stu-id="471c5-114">The trimming feature works by examining the application binaries to discover and build a graph of the required runtime assemblies.</span></span> <span data-ttu-id="471c5-115">参照されていないその他のランタイム アセンブリはトリミングされます。</span><span class="sxs-lookup"><span data-stu-id="471c5-115">The remaining runtime assemblies that aren't referenced are trimmed.</span></span>

## <a name="trimming-issues-when-using-reflection"></a><span data-ttu-id="471c5-116">リフレクションを使用するときのトリミングの問題</span><span class="sxs-lookup"><span data-stu-id="471c5-116">Trimming issues when using reflection</span></span>

<span data-ttu-id="471c5-117">トリミング機能が参照の検出に失敗するシナリオがあります。</span><span class="sxs-lookup"><span data-stu-id="471c5-117">There are scenarios in which the trimming functionality will fail to detect references.</span></span> <span data-ttu-id="471c5-118">たとえば、リフレクションを使用するアプリケーションでは、アセンブリの依存関係が実行時にのみ認識されるため、この問題が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="471c5-118">For example, an application that uses reflection could run into this issue because the dependency on the assembly will only be known at run time.</span></span>

<span data-ttu-id="471c5-119">トリミングは、リフレクションの使用が、直接参照されていないランタイム アセンブリに依存している場合にのみ問題になります。</span><span class="sxs-lookup"><span data-stu-id="471c5-119">Trimming is only a problem if the reflection usage depends on a runtime assembly that isn't referenced directly.</span></span> <span data-ttu-id="471c5-120">お使いのアプリケーション コードがリフレクションを直接使用していない可能性がありますが、参照しているサードパーティ アセンブリがそれを使用している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="471c5-120">Keep in mind that your application code may not be using reflection directly, but a third-party assembly you're referencing may be using it.</span></span>

<span data-ttu-id="471c5-121">コードがリフレクションを通じて API を参照していて、その API を含むアセンブリをリンカーでトリミングしたくない場合は、プロジェクト ファイルを変更して、トリミング プロセスからアセンブリを除外することができます。</span><span class="sxs-lookup"><span data-stu-id="471c5-121">When the code is referencing an API through reflection and you don't want the linker to trim the assembly that contains that API, you can modify your project file to exclude the assembly from the trimming process.</span></span> <span data-ttu-id="471c5-122">次の例は、`System.Security` という名前のアセンブリがトリミングされないようにする方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="471c5-122">The following example shows how to prevent an assembly called `System.Security` from being trimmed:</span></span>

```xml
<ItemGroup>
    <TrimmerRootAssembly Include="System.Security" />
</ItemGroup>
```

## <a name="see-also"></a><span data-ttu-id="471c5-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="471c5-123">See also</span></span>

- [<span data-ttu-id="471c5-124">.NET Core アプリケーションの展開</span><span class="sxs-lookup"><span data-stu-id="471c5-124">.NET Core application deployment</span></span>](index.md)
