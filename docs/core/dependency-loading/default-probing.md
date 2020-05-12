---
title: 既定のプローブ - .NET Core
description: 依存関係を特定するための .NET Core の System.Runtime.Loader.AssemblyLoadContext.Default プローブの概要。
ms.date: 08/09/2019
author: sdmaclea
ms.author: stmaclea
ms.openlocfilehash: 1e347c716c2d739a1bd03be056b57fdbda6c678f
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2020
ms.locfileid: "82859516"
---
# <a name="default-probing"></a><span data-ttu-id="59883-103">既定のプローブ</span><span class="sxs-lookup"><span data-stu-id="59883-103">Default probing</span></span>

<span data-ttu-id="59883-104"><xref:System.Runtime.Loader.AssemblyLoadContext.Default%2A?displayProperty=nameWithType> インスタンスは、アセンブリの依存関係を検索する役目を持っています。</span><span class="sxs-lookup"><span data-stu-id="59883-104">The <xref:System.Runtime.Loader.AssemblyLoadContext.Default%2A?displayProperty=nameWithType> instance is responsible for locating an assembly's dependencies.</span></span> <span data-ttu-id="59883-105">この記事では、<xref:System.Runtime.Loader.AssemblyLoadContext.Default%2A?displayProperty=nameWithType> インスタンスのプローブ ロジックについて説明します。</span><span class="sxs-lookup"><span data-stu-id="59883-105">This article describes the <xref:System.Runtime.Loader.AssemblyLoadContext.Default%2A?displayProperty=nameWithType> instance's probing logic.</span></span>

## <a name="host-configured-probing-properties"></a><span data-ttu-id="59883-106">ホストで構成されたプローブ プロパティ</span><span class="sxs-lookup"><span data-stu-id="59883-106">Host configured probing properties</span></span>

<span data-ttu-id="59883-107">ランタイムが開始されると、ランタイム ホストは <xref:System.Runtime.Loader.AssemblyLoadContext.Default%2A?displayProperty=nameWithType> プローブ パスを構成する一連の名前付きプローブ プロパティを提供します。</span><span class="sxs-lookup"><span data-stu-id="59883-107">When the runtime is started, the runtime host provides a set of named probing properties that configure <xref:System.Runtime.Loader.AssemblyLoadContext.Default%2A?displayProperty=nameWithType> probe paths.</span></span>

<span data-ttu-id="59883-108">各プローブ プロパティはオプションです。</span><span class="sxs-lookup"><span data-stu-id="59883-108">Each probing property is optional.</span></span> <span data-ttu-id="59883-109">存在する場合、各プロパティは区切り記号で区切られた絶対パスのリストを含む文字列値です。</span><span class="sxs-lookup"><span data-stu-id="59883-109">If present, each property is a string value that contains a delimited list of absolute paths.</span></span> <span data-ttu-id="59883-110">区切り記号は、Windows では ';'、他のすべてのプラットフォームでは ':' になります。</span><span class="sxs-lookup"><span data-stu-id="59883-110">The delimiter is ';' on Windows and ':' on all other platforms.</span></span>

|<span data-ttu-id="59883-111">プロパティ名</span><span class="sxs-lookup"><span data-stu-id="59883-111">Property Name</span></span>                 |<span data-ttu-id="59883-112">説明</span><span class="sxs-lookup"><span data-stu-id="59883-112">Description</span></span>  |
|------------------------------|---------|
|`TRUSTED_PLATFORM_ASSEMBLIES`   | <span data-ttu-id="59883-113">プラットフォームとアプリケーション アセンブリ ファイル パスの一覧。</span><span class="sxs-lookup"><span data-stu-id="59883-113">List of platform and application assembly file paths.</span></span> |
|`PLATFORM_RESOURCE_ROOTS`       | <span data-ttu-id="59883-114">サテライト リソース アセンブリを検索するディレクトリ パスの一覧。</span><span class="sxs-lookup"><span data-stu-id="59883-114">List of directory paths to search for satellite resource assemblies.</span></span> |
|`NATIVE_DLL_SEARCH_DIRECTORIES` | <span data-ttu-id="59883-115">アンマネージド (ネイティブ) ライブラリを検索するディレクトリ パスの一覧。</span><span class="sxs-lookup"><span data-stu-id="59883-115">List of directory paths to search for unmanaged (native) libraries.</span></span>        |
|`APP_PATHS`                     | <span data-ttu-id="59883-116">マネージド アセンブリを検索するディレクトリ パスの一覧。</span><span class="sxs-lookup"><span data-stu-id="59883-116">List of directory paths to search for managed assemblies.</span></span> |
|`APP_NI_PATHS`                  | <span data-ttu-id="59883-117">マネージド アセンブリのネイティブ イメージを検索するディレクトリ パスの一覧。</span><span class="sxs-lookup"><span data-stu-id="59883-117">List of directory paths to search for native images of managed assemblies.</span></span> |

### <a name="how-are-the-properties-populated"></a><span data-ttu-id="59883-118">プロパティの設定方法</span><span class="sxs-lookup"><span data-stu-id="59883-118">How are the properties populated?</span></span>

<span data-ttu-id="59883-119">*\<myapp>.deps.json* ファイルが存在するかどうかに応じて、プロパティを設定するための 2 つの主なシナリオがあります。</span><span class="sxs-lookup"><span data-stu-id="59883-119">There are two main scenarios for populating the properties depending on whether the *\<myapp>.deps.json* file exists.</span></span>

- <span data-ttu-id="59883-120">*\*.deps.json* ファイルが存在する場合は、ファイルが解析されてプローブ プロパティが設定されます。</span><span class="sxs-lookup"><span data-stu-id="59883-120">When the *\*.deps.json* file is present, it's parsed to populate the probing properties.</span></span>
- <span data-ttu-id="59883-121">*\*.deps.json* ファイルが存在しない場合、アプリケーションのディレクトリに、すべての依存関係が含まれていると見なされます。</span><span class="sxs-lookup"><span data-stu-id="59883-121">When the *\*.deps.json* file isn't present, the application's directory is assumed to contain all the dependencies.</span></span> <span data-ttu-id="59883-122">ディレクトリの内容が、プローブ プロパティを設定するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="59883-122">The directory's contents are used to populate the probing properties.</span></span>

<span data-ttu-id="59883-123">また、参照されているフレームワークの *\*.deps.json* ファイルも同様に解析されます。</span><span class="sxs-lookup"><span data-stu-id="59883-123">Additionally, the *\*.deps.json* files for any referenced frameworks are similarly parsed.</span></span>

<span data-ttu-id="59883-124">最後に、環境変数 `ADDITIONAL_DEPS` を使用して、依存関係を追加できます。</span><span class="sxs-lookup"><span data-stu-id="59883-124">Finally the environment variable `ADDITIONAL_DEPS` can be used to add additional dependencies.</span></span>

<span data-ttu-id="59883-125">`APP_PATHS` プロパティと `APP_NI_PATHS` プロパティには既定でデータが入力されず、ほとんどのアプリケーションで省略されます。</span><span class="sxs-lookup"><span data-stu-id="59883-125">The `APP_PATHS` and `APP_NI_PATHS` properties are not populated by default and are omitted for most applications.</span></span>

### <a name="how-do-i-see-the-probing-properties-from-managed-code"></a><span data-ttu-id="59883-126">マネージド コードからプローブ プロパティを参照する方法</span><span class="sxs-lookup"><span data-stu-id="59883-126">How do I see the probing properties from managed code?</span></span>

<span data-ttu-id="59883-127">各プロパティは、上記の表のプロパティ名を使用して <xref:System.AppContext.GetData(System.String)?displayProperty=nameWithType> 関数を呼び出すことによって使用できます。</span><span class="sxs-lookup"><span data-stu-id="59883-127">Each property is available by calling the <xref:System.AppContext.GetData(System.String)?displayProperty=nameWithType> function with the property name from the table above.</span></span>

### <a name="how-do-i-debug-the-probing-properties-construction"></a><span data-ttu-id="59883-128">プローブ プロパティの構築をデバッグする方法</span><span class="sxs-lookup"><span data-stu-id="59883-128">How do I debug the probing properties' construction?</span></span>

<span data-ttu-id="59883-129">以下に示す特定の環境変数が有効になっている場合、.NET Core ランタイム ホストは便利なトレース メッセージを出力します。</span><span class="sxs-lookup"><span data-stu-id="59883-129">The .NET Core runtime host will output useful trace messages when certain environment variables are enabled:</span></span>

|<span data-ttu-id="59883-130">環境変数</span><span class="sxs-lookup"><span data-stu-id="59883-130">Environment Variable</span></span>        |<span data-ttu-id="59883-131">説明</span><span class="sxs-lookup"><span data-stu-id="59883-131">Description</span></span>  |
|----------------------------|---------|
|`COREHOST_TRACE=1`          |<span data-ttu-id="59883-132">トレースを有効にします。</span><span class="sxs-lookup"><span data-stu-id="59883-132">Enables tracing.</span></span>|
|`COREHOST_TRACEFILE=<path>` |<span data-ttu-id="59883-133">既定の `stderr` ではなくファイル パスにトレースします。</span><span class="sxs-lookup"><span data-stu-id="59883-133">Traces to a file path instead of the default `stderr`.</span></span>|
|`COREHOST_TRACE_VERBOSITY`  |<span data-ttu-id="59883-134">詳細度を 1 (最低) から 4 (最高) に設定します。</span><span class="sxs-lookup"><span data-stu-id="59883-134">Sets the verbosity from 1 (lowest) to 4 (highest).</span></span>|

## <a name="managed-assembly-default-probing"></a><span data-ttu-id="59883-135">マネージド アセンブリの既定のプローブ</span><span class="sxs-lookup"><span data-stu-id="59883-135">Managed assembly default probing</span></span>

<span data-ttu-id="59883-136">マネージド アセンブリを探すためにプローブするとき、<xref:System.Runtime.Loader.AssemblyLoadContext.Default%2A?displayProperty=nameWithType> は次の順序で検索します。</span><span class="sxs-lookup"><span data-stu-id="59883-136">When probing to locate a managed assembly, the <xref:System.Runtime.Loader.AssemblyLoadContext.Default%2A?displayProperty=nameWithType> looks in order at:</span></span>

- <span data-ttu-id="59883-137">`TRUSTED_PLATFORM_ASSEMBLIES` 内の <xref:System.Reflection.AssemblyName.Name?displayProperty=nameWithType> に一致するファイル (ファイル拡張子を削除した後)。</span><span class="sxs-lookup"><span data-stu-id="59883-137">Files matching the <xref:System.Reflection.AssemblyName.Name?displayProperty=nameWithType> in `TRUSTED_PLATFORM_ASSEMBLIES` (after removing file extensions).</span></span>
- <span data-ttu-id="59883-138">共通のファイル拡張子を持つ `APP_NI_PATHS` のネイティブ イメージ アセンブリ ファイル。</span><span class="sxs-lookup"><span data-stu-id="59883-138">Native image assembly files in `APP_NI_PATHS` with common file extensions.</span></span>
- <span data-ttu-id="59883-139">共通のファイル拡張子を持つ `APP_PATHS` のアセンブリ ファイル。</span><span class="sxs-lookup"><span data-stu-id="59883-139">Assembly files in `APP_PATHS` with common file extensions.</span></span>

## <a name="satellite-resource-assembly-probing"></a><span data-ttu-id="59883-140">サテライト (リソース) アセンブリのプローブ</span><span class="sxs-lookup"><span data-stu-id="59883-140">Satellite (resource) assembly probing</span></span>

<span data-ttu-id="59883-141">サテライト アセンブリを検索して特定のカルチャを見つけるために、一連のファイル パスを構築します。</span><span class="sxs-lookup"><span data-stu-id="59883-141">To find a satellite assembly for a specific culture, construct a set of file paths.</span></span>

<span data-ttu-id="59883-142">`PLATFORM_RESOURCE_ROOTS` および `APP_PATHS` の各パスに対して、<xref:System.Globalization.CultureInfo.Name?displayProperty=nameWithType> 文字列、ディレクトリ区切り記号、<xref:System.Reflection.AssemblyName.Name?displayProperty=nameWithType> 文字列、および拡張子 '.dll' を追加します。</span><span class="sxs-lookup"><span data-stu-id="59883-142">For each path in `PLATFORM_RESOURCE_ROOTS` and then `APP_PATHS`, append the <xref:System.Globalization.CultureInfo.Name?displayProperty=nameWithType> string, a directory separator, the <xref:System.Reflection.AssemblyName.Name?displayProperty=nameWithType> string, and the extension '.dll'.</span></span>

<span data-ttu-id="59883-143">一致するファイルが存在する場合は、それを読み込んで返すことを試行します。</span><span class="sxs-lookup"><span data-stu-id="59883-143">If any matching file exists, attempt to load and return it.</span></span>

## <a name="unmanaged-native-library-probing"></a><span data-ttu-id="59883-144">アンマネージド (ネイティブ) ライブラリのプローブ</span><span class="sxs-lookup"><span data-stu-id="59883-144">Unmanaged (native) library probing</span></span>

<span data-ttu-id="59883-145">アンマネージド ライブラリを探すためにプローブする場合、一致するライブラリを見つけるために `NATIVE_DLL_SEARCH_DIRECTORIES` が検索されます。</span><span class="sxs-lookup"><span data-stu-id="59883-145">When probing to locate an unmanaged library, the `NATIVE_DLL_SEARCH_DIRECTORIES` are searched looking for a matching library.</span></span>
