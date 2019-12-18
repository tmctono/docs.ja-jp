---
ms.openlocfilehash: 7a55641b3673dc4d8d9b328f0de99b7247ca51d4
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74998799"
---

<span data-ttu-id="20c23-101">パッケージ マネージャーのフィードに追加されたパッケージは、`{product}-{type}-{version}` のハック可能な形式で名前が付けられます。</span><span class="sxs-lookup"><span data-stu-id="20c23-101">The packages added to the package manager feeds are named in a hackable format: `{product}-{type}-{version}`.</span></span>

- <span data-ttu-id="20c23-102">**product**</span><span class="sxs-lookup"><span data-stu-id="20c23-102">**product**</span></span>\
<span data-ttu-id="20c23-103">インストールする .NET 製品の種類。</span><span class="sxs-lookup"><span data-stu-id="20c23-103">The type of .NET product to install.</span></span> <span data-ttu-id="20c23-104">有効なオプションは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="20c23-104">Valid options are:</span></span>

  - <span data-ttu-id="20c23-105">dotnet</span><span class="sxs-lookup"><span data-stu-id="20c23-105">dotnet</span></span>
  - <span data-ttu-id="20c23-106">aspnetcore</span><span class="sxs-lookup"><span data-stu-id="20c23-106">aspnetcore</span></span>

- <span data-ttu-id="20c23-107">**type**</span><span class="sxs-lookup"><span data-stu-id="20c23-107">**type**</span></span>\
<span data-ttu-id="20c23-108">SDK またはランタイムを選択します。</span><span class="sxs-lookup"><span data-stu-id="20c23-108">Chooses the SDK or the runtime.</span></span> <span data-ttu-id="20c23-109">有効なオプションは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="20c23-109">Valid options are:</span></span>

  - <span data-ttu-id="20c23-110">SDK</span><span class="sxs-lookup"><span data-stu-id="20c23-110">sdk</span></span>
  - <span data-ttu-id="20c23-111">ランタイム</span><span class="sxs-lookup"><span data-stu-id="20c23-111">runtime</span></span>

- <span data-ttu-id="20c23-112">**version**</span><span class="sxs-lookup"><span data-stu-id="20c23-112">**version**</span></span>\
<span data-ttu-id="20c23-113">インストールする SDK またはランタイムのバージョン。</span><span class="sxs-lookup"><span data-stu-id="20c23-113">The version of the SDK or runtime to install.</span></span> <span data-ttu-id="20c23-114">この記事では常に、サポートされている最新バージョンの手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="20c23-114">This article will always give the instructions for the latest supported version.</span></span> <span data-ttu-id="20c23-115">有効なオプションは、次のようなリリース バージョンです。</span><span class="sxs-lookup"><span data-stu-id="20c23-115">Valid options are any released version, such as:</span></span>

  - <span data-ttu-id="20c23-116">3.0</span><span class="sxs-lookup"><span data-stu-id="20c23-116">3.0</span></span>
  - <span data-ttu-id="20c23-117">2.2</span><span class="sxs-lookup"><span data-stu-id="20c23-117">2.2</span></span>
  - <span data-ttu-id="20c23-118">2.1</span><span class="sxs-lookup"><span data-stu-id="20c23-118">2.1</span></span>

### <a name="examples"></a><span data-ttu-id="20c23-119">使用例</span><span class="sxs-lookup"><span data-stu-id="20c23-119">Examples</span></span>

- <span data-ttu-id="20c23-120">.NET Core 2.2 SDK をインストールする: `dotnet-sdk-2.2`</span><span class="sxs-lookup"><span data-stu-id="20c23-120">Install the .NET Core 2.2 SDK: `dotnet-sdk-2.2`</span></span>
- <span data-ttu-id="20c23-121">ASP.NET Core 3.0 ランタイムをインストールする: `aspnetcore-runtime-3.0`</span><span class="sxs-lookup"><span data-stu-id="20c23-121">Install the ASP.NET Core 3.0 runtime: `aspnetcore-runtime-3.0`</span></span>
- <span data-ttu-id="20c23-122">.NET Core 2.1 ランタイムをインストールする: `dotnet-runtime-2.1`</span><span class="sxs-lookup"><span data-stu-id="20c23-122">Install the .NET Core 2.1 runtime: `dotnet-runtime-2.1`</span></span>

### <a name="troubleshoot"></a><span data-ttu-id="20c23-123">トラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="20c23-123">Troubleshoot</span></span>

<span data-ttu-id="20c23-124">パッケージの組み合わせが機能しない場合は、使用できません。</span><span class="sxs-lookup"><span data-stu-id="20c23-124">If the package combination doesn't work, it's not available.</span></span> <span data-ttu-id="20c23-125">たとえば、ASP.NET Core SDK がない場合、SDK コンポーネントは .NET Core SDK に含まれています。</span><span class="sxs-lookup"><span data-stu-id="20c23-125">For example, there isn't an ASP.NET Core SDK, the SDK components are included with the .NET Core SDK.</span></span> <span data-ttu-id="20c23-126">値 `aspnetcore-sdk-2.2` は正しくありません。これは、`dotnet-sdk-2.2` である必要があります</span><span class="sxs-lookup"><span data-stu-id="20c23-126">The value `aspnetcore-sdk-2.2` is incorrect and should be `dotnet-sdk-2.2`</span></span>
