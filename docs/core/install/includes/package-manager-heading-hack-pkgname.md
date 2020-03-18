---
ms.openlocfilehash: 51b3c1b3e3d61b23a0511ca807afef0269ac9ee4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2020
ms.locfileid: "77466121"
---

<span data-ttu-id="36f76-101">パッケージ マネージャーのフィードに追加されたパッケージは、`{product}-{type}-{version}` のハック可能な形式で名前が付けられます。</span><span class="sxs-lookup"><span data-stu-id="36f76-101">The packages added to the package manager feeds are named in a hackable format: `{product}-{type}-{version}`.</span></span>

- <span data-ttu-id="36f76-102">**product**</span><span class="sxs-lookup"><span data-stu-id="36f76-102">**product**</span></span>\
<span data-ttu-id="36f76-103">インストールする .NET 製品の種類。</span><span class="sxs-lookup"><span data-stu-id="36f76-103">The type of .NET product to install.</span></span> <span data-ttu-id="36f76-104">有効なオプションは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="36f76-104">Valid options are:</span></span>

  - <span data-ttu-id="36f76-105">dotnet</span><span class="sxs-lookup"><span data-stu-id="36f76-105">dotnet</span></span>
  - <span data-ttu-id="36f76-106">aspnetcore</span><span class="sxs-lookup"><span data-stu-id="36f76-106">aspnetcore</span></span>

- <span data-ttu-id="36f76-107">**type**</span><span class="sxs-lookup"><span data-stu-id="36f76-107">**type**</span></span>\
<span data-ttu-id="36f76-108">SDK またはランタイムを選択します。</span><span class="sxs-lookup"><span data-stu-id="36f76-108">Chooses the SDK or the runtime.</span></span> <span data-ttu-id="36f76-109">有効なオプションは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="36f76-109">Valid options are:</span></span>

  - <span data-ttu-id="36f76-110">SDK</span><span class="sxs-lookup"><span data-stu-id="36f76-110">sdk</span></span>
  - <span data-ttu-id="36f76-111">ランタイム</span><span class="sxs-lookup"><span data-stu-id="36f76-111">runtime</span></span>

- <span data-ttu-id="36f76-112">**version**</span><span class="sxs-lookup"><span data-stu-id="36f76-112">**version**</span></span>\
<span data-ttu-id="36f76-113">インストールする SDK またはランタイムのバージョン。</span><span class="sxs-lookup"><span data-stu-id="36f76-113">The version of the SDK or runtime to install.</span></span> <span data-ttu-id="36f76-114">この記事では常に、サポートされている最新バージョンの手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="36f76-114">This article will always give the instructions for the latest supported version.</span></span> <span data-ttu-id="36f76-115">有効なオプションは、次のようなリリース バージョンです。</span><span class="sxs-lookup"><span data-stu-id="36f76-115">Valid options are any released version, such as:</span></span>

  - <span data-ttu-id="36f76-116">3.1</span><span class="sxs-lookup"><span data-stu-id="36f76-116">3.1</span></span>
  - <span data-ttu-id="36f76-117">3.0</span><span class="sxs-lookup"><span data-stu-id="36f76-117">3.0</span></span>
  - <span data-ttu-id="36f76-118">2.1</span><span class="sxs-lookup"><span data-stu-id="36f76-118">2.1</span></span>

  <span data-ttu-id="36f76-119">ダウンロードしようとしている SDK/ランタイムが Linux ディストリビューションで使用できない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="36f76-119">It's possible the SDK/runtime you're trying to download is not available for your Linux distribution.</span></span> <span data-ttu-id="36f76-120">サポートされているディストリビューションの一覧については、「[.NET Core の依存関係と要件](../dependencies.md?pivots=os-linux)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="36f76-120">For a list of supported distributions, see [.NET Core dependencies and requirements](../dependencies.md?pivots=os-linux).</span></span>

### <a name="examples"></a><span data-ttu-id="36f76-121">例</span><span class="sxs-lookup"><span data-stu-id="36f76-121">Examples</span></span>

- <span data-ttu-id="36f76-122">ASP.NET Core 3.1 ランタイムをインストールする: `aspnetcore-runtime-3.1`</span><span class="sxs-lookup"><span data-stu-id="36f76-122">Install the ASP.NET Core 3.1 runtime: `aspnetcore-runtime-3.1`</span></span>
- <span data-ttu-id="36f76-123">.NET Core 2.1 ランタイムをインストールする: `dotnet-runtime-2.1`</span><span class="sxs-lookup"><span data-stu-id="36f76-123">Install the .NET Core 2.1 runtime: `dotnet-runtime-2.1`</span></span>
- <span data-ttu-id="36f76-124">.NET Core 3.0 SDK をインストールする: `dotnet-sdk-3.0`</span><span class="sxs-lookup"><span data-stu-id="36f76-124">Install the .NET Core 3.0 SDK: `dotnet-sdk-3.0`</span></span>

### <a name="package-missing"></a><span data-ttu-id="36f76-125">パッケージがない</span><span class="sxs-lookup"><span data-stu-id="36f76-125">Package missing</span></span>

<span data-ttu-id="36f76-126">パッケージ バージョンの組み合わせが正しくない場合は、使用できません。</span><span class="sxs-lookup"><span data-stu-id="36f76-126">If the package-version combination doesn't work, it's not available.</span></span> <span data-ttu-id="36f76-127">たとえば、ASP.NET Core SDK がない場合、SDK コンポーネントは .NET Core SDK に含まれています。</span><span class="sxs-lookup"><span data-stu-id="36f76-127">For example, there isn't an ASP.NET Core SDK, the SDK components are included with the .NET Core SDK.</span></span> <span data-ttu-id="36f76-128">値 `aspnetcore-sdk-2.2` は正しくありません。`dotnet-sdk-2.2` にする必要があります</span><span class="sxs-lookup"><span data-stu-id="36f76-128">The value `aspnetcore-sdk-2.2` is incorrect and should be `dotnet-sdk-2.2`.</span></span> <span data-ttu-id="36f76-129">.NET Core によってサポートされている Linux ディストリビューションの一覧については、「[.NET Core の依存関係と要件](../dependencies.md?pivots=os-linux)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="36f76-129">For a list of Linux distributions supported by .NET Core, see [.NET Core dependencies and requirements](../dependencies.md?pivots=os-linux).</span></span>
