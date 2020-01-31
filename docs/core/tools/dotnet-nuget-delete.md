---
title: dotnet nuget delete コマンド
description: dotnet-nuget-delete コマンドは、サーバーからパッケージを削除または一覧から削除します。
author: karann-msft
ms.date: 06/26/2019
ms.openlocfilehash: 0950f03c0986bde17ae3e2e7170d402ea8222853
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2020
ms.locfileid: "76733122"
---
# <a name="dotnet-nuget-delete"></a><span data-ttu-id="28ab2-103">dotnet nuget delete</span><span class="sxs-lookup"><span data-stu-id="28ab2-103">dotnet nuget delete</span></span>

<span data-ttu-id="28ab2-104">**この記事の対象:** ✔️ .NET Core 1.x SDK 以降のバージョン</span><span class="sxs-lookup"><span data-stu-id="28ab2-104">**This article applies to:** ✔️ .NET Core 1.x SDK and later versions</span></span>

<!-- todo: uncomment when all CLI commands are reviewed
[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]
-->

## <a name="name"></a><span data-ttu-id="28ab2-105">名前</span><span class="sxs-lookup"><span data-stu-id="28ab2-105">Name</span></span>

<span data-ttu-id="28ab2-106">`dotnet nuget delete` - サーバーからパッケージを削除または一覧から削除します。</span><span class="sxs-lookup"><span data-stu-id="28ab2-106">`dotnet nuget delete` - Deletes or unlists a package from the server.</span></span>

## <a name="synopsis"></a><span data-ttu-id="28ab2-107">構文</span><span class="sxs-lookup"><span data-stu-id="28ab2-107">Synopsis</span></span>

```dotnetcli
dotnet nuget delete [<PACKAGE_NAME> <PACKAGE_VERSION>] [--force-english-output] [--interactive] [-k|--api-key] [--no-service-endpoint]
    [--non-interactive] [-s|--source]
dotnet nuget delete [-h|--help]
```

## <a name="description"></a><span data-ttu-id="28ab2-108">説明</span><span class="sxs-lookup"><span data-stu-id="28ab2-108">Description</span></span>

<span data-ttu-id="28ab2-109">`dotnet nuget delete` コマンドは、サーバーからパッケージを削除または一覧から削除します。</span><span class="sxs-lookup"><span data-stu-id="28ab2-109">The `dotnet nuget delete` command deletes or unlists a package from the server.</span></span> <span data-ttu-id="28ab2-110">[nuget.org](https://www.nuget.org/) の場合、この操作ではパッケージを一覧から削除します。</span><span class="sxs-lookup"><span data-stu-id="28ab2-110">For [nuget.org](https://www.nuget.org/), the action is to unlist the package.</span></span>

## <a name="arguments"></a><span data-ttu-id="28ab2-111">引数</span><span class="sxs-lookup"><span data-stu-id="28ab2-111">Arguments</span></span>

* **`PACKAGE_NAME`**

  <span data-ttu-id="28ab2-112">削除するパッケージの名前または ID です。</span><span class="sxs-lookup"><span data-stu-id="28ab2-112">Name/ID of the package to delete.</span></span>

* **`PACKAGE_VERSION`**

  <span data-ttu-id="28ab2-113">削除するパッケージのバージョンです。</span><span class="sxs-lookup"><span data-stu-id="28ab2-113">Version of the package to delete.</span></span>

## <a name="options"></a><span data-ttu-id="28ab2-114">オプション</span><span class="sxs-lookup"><span data-stu-id="28ab2-114">Options</span></span>

* **`--force-english-output`**

  <span data-ttu-id="28ab2-115">インバリアントの英語ベースのカルチャを使用して、アプリケーションの実行を強制します。</span><span class="sxs-lookup"><span data-stu-id="28ab2-115">Forces the application to run using an invariant, English-based culture.</span></span>

* **`-h|--help`**

  <span data-ttu-id="28ab2-116">コマンドの短いヘルプを印刷します。</span><span class="sxs-lookup"><span data-stu-id="28ab2-116">Prints out a short help for the command.</span></span>

* **`--interactive`**

  <span data-ttu-id="28ab2-117">コマンドが認証などの操作をブロックして、手動アクションを要求することを許可します。</span><span class="sxs-lookup"><span data-stu-id="28ab2-117">Allows the command to block and requires manual action for operations like authentication.</span></span> <span data-ttu-id="28ab2-118">.NET Core 2.2 SDK 以降、使用できるオプションです。</span><span class="sxs-lookup"><span data-stu-id="28ab2-118">Option available since .NET Core 2.2 SDK.</span></span>

* **`-k|--api-key <API_KEY>`**

  <span data-ttu-id="28ab2-119">サーバーの API キーです。</span><span class="sxs-lookup"><span data-stu-id="28ab2-119">The API key for the server.</span></span>

* **`--no-service-endpoint`**

  <span data-ttu-id="28ab2-120">ソース URL に "api/v2/package" を追加しません。</span><span class="sxs-lookup"><span data-stu-id="28ab2-120">Doesn't append "api/v2/package" to the source URL.</span></span> <span data-ttu-id="28ab2-121">.NET Core 2.1 SDK 以降、使用できるオプションです。</span><span class="sxs-lookup"><span data-stu-id="28ab2-121">Option available since .NET Core 2.1 SDK.</span></span>

* **`--non-interactive`**

  <span data-ttu-id="28ab2-122">ユーザーに入力や確認のメッセージ画面を表示しません。</span><span class="sxs-lookup"><span data-stu-id="28ab2-122">Doesn't prompt for user input or confirmations.</span></span>

* **`-s|--source <SOURCE>`**

  <span data-ttu-id="28ab2-123">サーバー URL を指定します。</span><span class="sxs-lookup"><span data-stu-id="28ab2-123">Specifies the server URL.</span></span> <span data-ttu-id="28ab2-124">nuget.org でサポートされている URL には、`https://www.nuget.org`、`https://www.nuget.org/api/v3`、および `https://www.nuget.org/api/v2/package` が含まれます。</span><span class="sxs-lookup"><span data-stu-id="28ab2-124">Supported URLs for nuget.org include `https://www.nuget.org`, `https://www.nuget.org/api/v3`, and `https://www.nuget.org/api/v2/package`.</span></span> <span data-ttu-id="28ab2-125">プライベート フィードの場合、ホスト名を置き換えます (`%hostname%/api/v3` など)。</span><span class="sxs-lookup"><span data-stu-id="28ab2-125">For private feeds, replace the host name (for example, `%hostname%/api/v3`).</span></span>

## <a name="examples"></a><span data-ttu-id="28ab2-126">使用例</span><span class="sxs-lookup"><span data-stu-id="28ab2-126">Examples</span></span>

* <span data-ttu-id="28ab2-127">`Microsoft.AspNetCore.Mvc` パッケージのバージョン 1.0 を削除します。</span><span class="sxs-lookup"><span data-stu-id="28ab2-127">Deletes version 1.0 of package `Microsoft.AspNetCore.Mvc`:</span></span>

  ```dotnetcli
  dotnet nuget delete Microsoft.AspNetCore.Mvc 1.0
  ```

* <span data-ttu-id="28ab2-128">ユーザーに資格情報やその他の入力を求めずに、`Microsoft.AspNetCore.Mvc` パッケージのバージョン 1.0 を削除します。</span><span class="sxs-lookup"><span data-stu-id="28ab2-128">Deletes version 1.0 of package `Microsoft.AspNetCore.Mvc`, not prompting user for credentials or other input:</span></span>

  ```dotnetcli
  dotnet nuget delete Microsoft.AspNetCore.Mvc 1.0 --non-interactive
  ```
