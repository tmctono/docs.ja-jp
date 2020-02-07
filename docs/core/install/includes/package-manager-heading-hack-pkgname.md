---
ms.openlocfilehash: ef3e4f9f8145677732b9d2e66d416be277697f55
ms.sourcegitcommit: cdf5084648bf5e77970cbfeaa23f1cab3e6e234e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2020
ms.locfileid: "76920667"
---

<span data-ttu-id="bdc14-101">パッケージ マネージャーのフィードに追加されたパッケージは、`{product}-{type}-{version}` のハック可能な形式で名前が付けられます。</span><span class="sxs-lookup"><span data-stu-id="bdc14-101">The packages added to the package manager feeds are named in a hackable format: `{product}-{type}-{version}`.</span></span>

- <span data-ttu-id="bdc14-102">**product**</span><span class="sxs-lookup"><span data-stu-id="bdc14-102">**product**</span></span>\
<span data-ttu-id="bdc14-103">インストールする .NET 製品の種類。</span><span class="sxs-lookup"><span data-stu-id="bdc14-103">The type of .NET product to install.</span></span> <span data-ttu-id="bdc14-104">有効なオプションは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="bdc14-104">Valid options are:</span></span>

  - <span data-ttu-id="bdc14-105">dotnet</span><span class="sxs-lookup"><span data-stu-id="bdc14-105">dotnet</span></span>
  - <span data-ttu-id="bdc14-106">aspnetcore</span><span class="sxs-lookup"><span data-stu-id="bdc14-106">aspnetcore</span></span>

- <span data-ttu-id="bdc14-107">**type**</span><span class="sxs-lookup"><span data-stu-id="bdc14-107">**type**</span></span>\
<span data-ttu-id="bdc14-108">SDK またはランタイムを選択します。</span><span class="sxs-lookup"><span data-stu-id="bdc14-108">Chooses the SDK or the runtime.</span></span> <span data-ttu-id="bdc14-109">有効なオプションは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="bdc14-109">Valid options are:</span></span>

  - <span data-ttu-id="bdc14-110">SDK</span><span class="sxs-lookup"><span data-stu-id="bdc14-110">sdk</span></span>
  - <span data-ttu-id="bdc14-111">ランタイム</span><span class="sxs-lookup"><span data-stu-id="bdc14-111">runtime</span></span>

- <span data-ttu-id="bdc14-112">**version**</span><span class="sxs-lookup"><span data-stu-id="bdc14-112">**version**</span></span>\
<span data-ttu-id="bdc14-113">インストールする SDK またはランタイムのバージョン。</span><span class="sxs-lookup"><span data-stu-id="bdc14-113">The version of the SDK or runtime to install.</span></span> <span data-ttu-id="bdc14-114">この記事では常に、サポートされている最新バージョンの手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="bdc14-114">This article will always give the instructions for the latest supported version.</span></span> <span data-ttu-id="bdc14-115">有効なオプションは、次のようなリリース バージョンです。</span><span class="sxs-lookup"><span data-stu-id="bdc14-115">Valid options are any released version, such as:</span></span>

  - <span data-ttu-id="bdc14-116">3.0</span><span class="sxs-lookup"><span data-stu-id="bdc14-116">3.0</span></span>
  - <span data-ttu-id="bdc14-117">2.2</span><span class="sxs-lookup"><span data-stu-id="bdc14-117">2.2</span></span>
  - <span data-ttu-id="bdc14-118">2.1</span><span class="sxs-lookup"><span data-stu-id="bdc14-118">2.1</span></span>

### <a name="examples"></a><span data-ttu-id="bdc14-119">使用例</span><span class="sxs-lookup"><span data-stu-id="bdc14-119">Examples</span></span>

- <span data-ttu-id="bdc14-120">.NET Core 2.2 SDK をインストールする: `dotnet-sdk-2.2`</span><span class="sxs-lookup"><span data-stu-id="bdc14-120">Install the .NET Core 2.2 SDK: `dotnet-sdk-2.2`</span></span>
- <span data-ttu-id="bdc14-121">ASP.NET Core 3.1 ランタイムをインストールする: `aspnetcore-runtime-3.1`</span><span class="sxs-lookup"><span data-stu-id="bdc14-121">Install the ASP.NET Core 3.1 runtime: `aspnetcore-runtime-3.1`</span></span>
- <span data-ttu-id="bdc14-122">.NET Core 2.1 ランタイムをインストールする: `dotnet-runtime-2.1`</span><span class="sxs-lookup"><span data-stu-id="bdc14-122">Install the .NET Core 2.1 runtime: `dotnet-runtime-2.1`</span></span>

### <a name="package-missing"></a><span data-ttu-id="bdc14-123">パッケージがない</span><span class="sxs-lookup"><span data-stu-id="bdc14-123">Package missing</span></span>

<span data-ttu-id="bdc14-124">パッケージ バージョンの組み合わせが正しくない場合は、使用できません。</span><span class="sxs-lookup"><span data-stu-id="bdc14-124">If the package-version combination doesn't work, it's not available.</span></span> <span data-ttu-id="bdc14-125">たとえば、ASP.NET Core SDK がない場合、SDK コンポーネントは .NET Core SDK に含まれています。</span><span class="sxs-lookup"><span data-stu-id="bdc14-125">For example, there isn't an ASP.NET Core SDK, the SDK components are included with the .NET Core SDK.</span></span> <span data-ttu-id="bdc14-126">値 `aspnetcore-sdk-2.2` は正しくありません。`dotnet-sdk-2.2` にする必要があります</span><span class="sxs-lookup"><span data-stu-id="bdc14-126">The value `aspnetcore-sdk-2.2` is incorrect and should be `dotnet-sdk-2.2`.</span></span>
