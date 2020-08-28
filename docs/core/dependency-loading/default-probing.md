---
title: 既定のプローブ - .NET Core
description: 依存関係を特定するための .NET Core の System.Runtime.Loader.AssemblyLoadContext.Default プローブの概要。
ms.date: 08/09/2019
author: sdmaclea
ms.author: stmaclea
ms.openlocfilehash: 13ce4c7de5f6ce1b76b2e61db810c0f19717540f
ms.sourcegitcommit: cbb19e56d48cf88375d35d0c27554d4722761e0d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/19/2020
ms.locfileid: "88608428"
---
# <a name="default-probing"></a><span data-ttu-id="f7665-103">既定のプローブ</span><span class="sxs-lookup"><span data-stu-id="f7665-103">Default probing</span></span>

<span data-ttu-id="f7665-104"><xref:System.Runtime.Loader.AssemblyLoadContext.Default%2A?displayProperty=nameWithType> インスタンスは、アセンブリの依存関係を検索する役目を持っています。</span><span class="sxs-lookup"><span data-stu-id="f7665-104">The <xref:System.Runtime.Loader.AssemblyLoadContext.Default%2A?displayProperty=nameWithType> instance is responsible for locating an assembly's dependencies.</span></span> <span data-ttu-id="f7665-105">この記事では、<xref:System.Runtime.Loader.AssemblyLoadContext.Default%2A?displayProperty=nameWithType> インスタンスのプローブ ロジックについて説明します。</span><span class="sxs-lookup"><span data-stu-id="f7665-105">This article describes the <xref:System.Runtime.Loader.AssemblyLoadContext.Default%2A?displayProperty=nameWithType> instance's probing logic.</span></span>

## <a name="host-configured-probing-properties"></a><span data-ttu-id="f7665-106">ホストで構成されたプローブ プロパティ</span><span class="sxs-lookup"><span data-stu-id="f7665-106">Host configured probing properties</span></span>

<span data-ttu-id="f7665-107">ランタイムが開始されると、ランタイム ホストは <xref:System.Runtime.Loader.AssemblyLoadContext.Default%2A?displayProperty=nameWithType> プローブ パスを構成する一連の名前付きプローブ プロパティを提供します。</span><span class="sxs-lookup"><span data-stu-id="f7665-107">When the runtime is started, the runtime host provides a set of named probing properties that configure <xref:System.Runtime.Loader.AssemblyLoadContext.Default%2A?displayProperty=nameWithType> probe paths.</span></span>

<span data-ttu-id="f7665-108">各プローブ プロパティはオプションです。</span><span class="sxs-lookup"><span data-stu-id="f7665-108">Each probing property is optional.</span></span> <span data-ttu-id="f7665-109">存在する場合、各プロパティは区切り記号で区切られた絶対パスのリストを含む文字列値です。</span><span class="sxs-lookup"><span data-stu-id="f7665-109">If present, each property is a string value that contains a delimited list of absolute paths.</span></span> <span data-ttu-id="f7665-110">区切り記号は、Windows では ';'、他のすべてのプラットフォームでは ':' になります。</span><span class="sxs-lookup"><span data-stu-id="f7665-110">The delimiter is ';' on Windows and ':' on all other platforms.</span></span>

|<span data-ttu-id="f7665-111">プロパティ名</span><span class="sxs-lookup"><span data-stu-id="f7665-111">Property Name</span></span>                 |<span data-ttu-id="f7665-112">説明</span><span class="sxs-lookup"><span data-stu-id="f7665-112">Description</span></span>  |
|------------------------------|---------|
|`TRUSTED_PLATFORM_ASSEMBLIES`   | <span data-ttu-id="f7665-113">プラットフォームとアプリケーション アセンブリ ファイル パスの一覧。</span><span class="sxs-lookup"><span data-stu-id="f7665-113">List of platform and application assembly file paths.</span></span> |
|`PLATFORM_RESOURCE_ROOTS`       | <span data-ttu-id="f7665-114">サテライト リソース アセンブリを検索するディレクトリ パスの一覧。</span><span class="sxs-lookup"><span data-stu-id="f7665-114">List of directory paths to search for satellite resource assemblies.</span></span> |
|`NATIVE_DLL_SEARCH_DIRECTORIES` | <span data-ttu-id="f7665-115">アンマネージド (ネイティブ) ライブラリを検索するディレクトリ パスの一覧。</span><span class="sxs-lookup"><span data-stu-id="f7665-115">List of directory paths to search for unmanaged (native) libraries.</span></span>        |
|`APP_PATHS`                     | <span data-ttu-id="f7665-116">マネージド アセンブリを検索するディレクトリ パスの一覧。</span><span class="sxs-lookup"><span data-stu-id="f7665-116">List of directory paths to search for managed assemblies.</span></span> |
|`APP_NI_PATHS`                  | <span data-ttu-id="f7665-117">マネージド アセンブリのネイティブ イメージを検索するディレクトリ パスの一覧。</span><span class="sxs-lookup"><span data-stu-id="f7665-117">List of directory paths to search for native images of managed assemblies.</span></span> |

### <a name="how-are-the-properties-populated"></a><span data-ttu-id="f7665-118">プロパティの設定方法</span><span class="sxs-lookup"><span data-stu-id="f7665-118">How are the properties populated?</span></span>

<span data-ttu-id="f7665-119">*\<myapp>.deps.json* ファイルが存在するかどうかに応じて、プロパティを設定するための 2 つの主なシナリオがあります。</span><span class="sxs-lookup"><span data-stu-id="f7665-119">There are two main scenarios for populating the properties depending on whether the *\<myapp>.deps.json* file exists.</span></span>

- <span data-ttu-id="f7665-120">*\*.deps.json* ファイルが存在する場合は、ファイルが解析されてプローブ プロパティが設定されます。</span><span class="sxs-lookup"><span data-stu-id="f7665-120">When the *\*.deps.json* file is present, it's parsed to populate the probing properties.</span></span>
- <span data-ttu-id="f7665-121">*\*.deps.json* ファイルが存在しない場合、アプリケーションのディレクトリに、すべての依存関係が含まれていると見なされます。</span><span class="sxs-lookup"><span data-stu-id="f7665-121">When the *\*.deps.json* file isn't present, the application's directory is assumed to contain all the dependencies.</span></span> <span data-ttu-id="f7665-122">ディレクトリの内容が、プローブ プロパティを設定するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="f7665-122">The directory's contents are used to populate the probing properties.</span></span>

<span data-ttu-id="f7665-123">また、参照されているフレームワークの *\*.deps.json* ファイルも同様に解析されます。</span><span class="sxs-lookup"><span data-stu-id="f7665-123">Additionally, the *\*.deps.json* files for any referenced frameworks are similarly parsed.</span></span>

<span data-ttu-id="f7665-124">最後に、環境変数 `ADDITIONAL_DEPS` を使用して、依存関係を追加できます。</span><span class="sxs-lookup"><span data-stu-id="f7665-124">Finally the environment variable `ADDITIONAL_DEPS` can be used to add additional dependencies.</span></span>  <span data-ttu-id="f7665-125">`dotnet.exe` には、アプリケーションの起動時にこの値を設定するための省略可能なパラメーター `--additional-deps` も含まれます。</span><span class="sxs-lookup"><span data-stu-id="f7665-125">`dotnet.exe` also contains an `--additional-deps` optional parameter to set this value on application startup.</span></span>

<span data-ttu-id="f7665-126">`APP_PATHS` プロパティと `APP_NI_PATHS` プロパティには既定でデータが入力されず、ほとんどのアプリケーションで省略されます。</span><span class="sxs-lookup"><span data-stu-id="f7665-126">The `APP_PATHS` and `APP_NI_PATHS` properties are not populated by default and are omitted for most applications.</span></span>

<span data-ttu-id="f7665-127">アプリケーションで使用されるすべての *\*.deps.json* ファイルの一覧は、`System.AppContext.GetData("APP_CONTEXT_DEPS_FILES")` を使用してアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="f7665-127">The list of all *\*.deps.json* files used by the application can be accessed via `System.AppContext.GetData("APP_CONTEXT_DEPS_FILES")`.</span></span>

### <a name="how-do-i-see-the-probing-properties-from-managed-code"></a><span data-ttu-id="f7665-128">マネージド コードからプローブ プロパティを参照する方法</span><span class="sxs-lookup"><span data-stu-id="f7665-128">How do I see the probing properties from managed code?</span></span>

<span data-ttu-id="f7665-129">各プロパティは、上記の表のプロパティ名を使用して <xref:System.AppContext.GetData(System.String)?displayProperty=nameWithType> 関数を呼び出すことによって使用できます。</span><span class="sxs-lookup"><span data-stu-id="f7665-129">Each property is available by calling the <xref:System.AppContext.GetData(System.String)?displayProperty=nameWithType> function with the property name from the table above.</span></span>

### <a name="how-do-i-debug-the-probing-properties-construction"></a><span data-ttu-id="f7665-130">プローブ プロパティの構築をデバッグする方法</span><span class="sxs-lookup"><span data-stu-id="f7665-130">How do I debug the probing properties' construction?</span></span>

<span data-ttu-id="f7665-131">以下に示す特定の環境変数が有効になっている場合、.NET Core ランタイム ホストは便利なトレース メッセージを出力します。</span><span class="sxs-lookup"><span data-stu-id="f7665-131">The .NET Core runtime host will output useful trace messages when certain environment variables are enabled:</span></span>

|<span data-ttu-id="f7665-132">環境変数</span><span class="sxs-lookup"><span data-stu-id="f7665-132">Environment Variable</span></span>        |<span data-ttu-id="f7665-133">説明</span><span class="sxs-lookup"><span data-stu-id="f7665-133">Description</span></span>  |
|----------------------------|---------|
|`COREHOST_TRACE=1`          |<span data-ttu-id="f7665-134">トレースを有効にします。</span><span class="sxs-lookup"><span data-stu-id="f7665-134">Enables tracing.</span></span>|
|`COREHOST_TRACEFILE=<path>` |<span data-ttu-id="f7665-135">既定の `stderr` ではなくファイル パスにトレースします。</span><span class="sxs-lookup"><span data-stu-id="f7665-135">Traces to a file path instead of the default `stderr`.</span></span>|
|`COREHOST_TRACE_VERBOSITY`  |<span data-ttu-id="f7665-136">詳細度を 1 (最低) から 4 (最高) に設定します。</span><span class="sxs-lookup"><span data-stu-id="f7665-136">Sets the verbosity from 1 (lowest) to 4 (highest).</span></span>|

## <a name="managed-assembly-default-probing"></a><span data-ttu-id="f7665-137">マネージド アセンブリの既定のプローブ</span><span class="sxs-lookup"><span data-stu-id="f7665-137">Managed assembly default probing</span></span>

<span data-ttu-id="f7665-138">マネージド アセンブリを探すためにプローブするとき、<xref:System.Runtime.Loader.AssemblyLoadContext.Default%2A?displayProperty=nameWithType> は次の順序で検索します。</span><span class="sxs-lookup"><span data-stu-id="f7665-138">When probing to locate a managed assembly, the <xref:System.Runtime.Loader.AssemblyLoadContext.Default%2A?displayProperty=nameWithType> looks in order at:</span></span>

- <span data-ttu-id="f7665-139">`TRUSTED_PLATFORM_ASSEMBLIES` 内の <xref:System.Reflection.AssemblyName.Name?displayProperty=nameWithType> に一致するファイル (ファイル拡張子を削除した後)。</span><span class="sxs-lookup"><span data-stu-id="f7665-139">Files matching the <xref:System.Reflection.AssemblyName.Name?displayProperty=nameWithType> in `TRUSTED_PLATFORM_ASSEMBLIES` (after removing file extensions).</span></span>
- <span data-ttu-id="f7665-140">共通のファイル拡張子を持つ `APP_NI_PATHS` のネイティブ イメージ アセンブリ ファイル。</span><span class="sxs-lookup"><span data-stu-id="f7665-140">Native image assembly files in `APP_NI_PATHS` with common file extensions.</span></span>
- <span data-ttu-id="f7665-141">共通のファイル拡張子を持つ `APP_PATHS` のアセンブリ ファイル。</span><span class="sxs-lookup"><span data-stu-id="f7665-141">Assembly files in `APP_PATHS` with common file extensions.</span></span>

## <a name="satellite-resource-assembly-probing"></a><span data-ttu-id="f7665-142">サテライト (リソース) アセンブリのプローブ</span><span class="sxs-lookup"><span data-stu-id="f7665-142">Satellite (resource) assembly probing</span></span>

<span data-ttu-id="f7665-143">サテライト アセンブリを検索して特定のカルチャを見つけるために、一連のファイル パスを構築します。</span><span class="sxs-lookup"><span data-stu-id="f7665-143">To find a satellite assembly for a specific culture, construct a set of file paths.</span></span>

<span data-ttu-id="f7665-144">`PLATFORM_RESOURCE_ROOTS` および `APP_PATHS` の各パスに対して、<xref:System.Globalization.CultureInfo.Name?displayProperty=nameWithType> 文字列、ディレクトリ区切り記号、<xref:System.Reflection.AssemblyName.Name?displayProperty=nameWithType> 文字列、および拡張子 '.dll' を追加します。</span><span class="sxs-lookup"><span data-stu-id="f7665-144">For each path in `PLATFORM_RESOURCE_ROOTS` and then `APP_PATHS`, append the <xref:System.Globalization.CultureInfo.Name?displayProperty=nameWithType> string, a directory separator, the <xref:System.Reflection.AssemblyName.Name?displayProperty=nameWithType> string, and the extension '.dll'.</span></span>

<span data-ttu-id="f7665-145">一致するファイルが存在する場合は、それを読み込んで返すことを試行します。</span><span class="sxs-lookup"><span data-stu-id="f7665-145">If any matching file exists, attempt to load and return it.</span></span>

## <a name="unmanaged-native-library-probing"></a><span data-ttu-id="f7665-146">アンマネージド (ネイティブ) ライブラリのプローブ</span><span class="sxs-lookup"><span data-stu-id="f7665-146">Unmanaged (native) library probing</span></span>

<span data-ttu-id="f7665-147">アンマネージド ライブラリを探すためにプローブする場合、一致するライブラリを見つけるために `NATIVE_DLL_SEARCH_DIRECTORIES` が検索されます。</span><span class="sxs-lookup"><span data-stu-id="f7665-147">When probing to locate an unmanaged library, the `NATIVE_DLL_SEARCH_DIRECTORIES` are searched looking for a matching library.</span></span>
