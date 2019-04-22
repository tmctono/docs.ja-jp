---
title: dotnet nuget delete コマンド
description: dotnet-nuget-delete コマンドは、サーバーからパッケージを削除または一覧から削除します。
author: karann-msft
ms.date: 12/04/2018
ms.openlocfilehash: a657fa273ca6b5229a1713fbcaf003217a59fd7f
ms.sourcegitcommit: 438919211260bb415fc8f96ca3eabc33cf2d681d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/16/2019
ms.locfileid: "59612629"
---
# <a name="dotnet-nuget-delete"></a><span data-ttu-id="4d44c-103">dotnet nuget delete</span><span class="sxs-lookup"><span data-stu-id="4d44c-103">dotnet nuget delete</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="4d44c-104">name</span><span class="sxs-lookup"><span data-stu-id="4d44c-104">Name</span></span>

<span data-ttu-id="4d44c-105">`dotnet nuget delete` - サーバーからパッケージを削除または一覧から削除します。</span><span class="sxs-lookup"><span data-stu-id="4d44c-105">`dotnet nuget delete` - Deletes or unlists a package from the server.</span></span>

## <a name="synopsis"></a><span data-ttu-id="4d44c-106">構文</span><span class="sxs-lookup"><span data-stu-id="4d44c-106">Synopsis</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="4d44c-107">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="4d44c-107">.NET Core 2.x</span></span>](#tab/netcore2x)

```
dotnet nuget delete [<PACKAGE_NAME> <PACKAGE_VERSION>] [--force-english-output] [--interactive] [-k|--api-key] [--no-service-endpoint]
    [--non-interactive] [-s|--source]
dotnet nuget delete [-h|--help]
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="4d44c-108">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="4d44c-108">.NET Core 1.x</span></span>](#tab/netcore1x)

```
dotnet nuget delete [<PACKAGE_NAME> <PACKAGE_VERSION>] [--force-english-output] [-k|--api-key] [--non-interactive]
    [-s|--source]
dotnet nuget delete [-h|--help]
```

---

## <a name="description"></a><span data-ttu-id="4d44c-109">説明</span><span class="sxs-lookup"><span data-stu-id="4d44c-109">Description</span></span>

<span data-ttu-id="4d44c-110">`dotnet nuget delete` コマンドは、サーバーからパッケージを削除または一覧から削除します。</span><span class="sxs-lookup"><span data-stu-id="4d44c-110">The `dotnet nuget delete` command deletes or unlists a package from the server.</span></span> <span data-ttu-id="4d44c-111">[nuget.org](https://www.nuget.org/) の場合、この操作ではパッケージを一覧から削除します。</span><span class="sxs-lookup"><span data-stu-id="4d44c-111">For [nuget.org](https://www.nuget.org/), the action is to unlist the package.</span></span>

## <a name="arguments"></a><span data-ttu-id="4d44c-112">引数</span><span class="sxs-lookup"><span data-stu-id="4d44c-112">Arguments</span></span>

* **`PACKAGE_NAME`**

  <span data-ttu-id="4d44c-113">削除するパッケージの名前または ID です。</span><span class="sxs-lookup"><span data-stu-id="4d44c-113">Name/ID of the package to delete.</span></span>

* **`PACKAGE_VERSION`**

  <span data-ttu-id="4d44c-114">削除するパッケージのバージョンです。</span><span class="sxs-lookup"><span data-stu-id="4d44c-114">Version of the package to delete.</span></span>

## <a name="options"></a><span data-ttu-id="4d44c-115">オプション</span><span class="sxs-lookup"><span data-stu-id="4d44c-115">Options</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="4d44c-116">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="4d44c-116">.NET Core 2.x</span></span>](#tab/netcore2x)

* **`--force-english-output`**

  <span data-ttu-id="4d44c-117">インバリアントの英語ベースのカルチャを使用して、アプリケーションの実行を強制します。</span><span class="sxs-lookup"><span data-stu-id="4d44c-117">Forces the application to run using an invariant, English-based culture.</span></span>

* **`-h|--help`**

  <span data-ttu-id="4d44c-118">コマンドの短いヘルプを印刷します。</span><span class="sxs-lookup"><span data-stu-id="4d44c-118">Prints out a short help for the command.</span></span>

* **`--interactive`**

  <span data-ttu-id="4d44c-119">コマンドが認証などの操作をブロックして、手動アクションを要求することを許可します。</span><span class="sxs-lookup"><span data-stu-id="4d44c-119">Allows the command to block and requires manual action for operations like authentication.</span></span> <span data-ttu-id="4d44c-120">.NET Core 2.2 SDK 以降、使用できるオプションです。</span><span class="sxs-lookup"><span data-stu-id="4d44c-120">Option available since .NET Core 2.2 SDK.</span></span>

* **`-k|--api-key <API_KEY>`**

  <span data-ttu-id="4d44c-121">サーバーの API キーです。</span><span class="sxs-lookup"><span data-stu-id="4d44c-121">The API key for the server.</span></span>

* **`--no-service-endpoint`**

  <span data-ttu-id="4d44c-122">ソース URL に "api/v2/package" を追加しません。</span><span class="sxs-lookup"><span data-stu-id="4d44c-122">Doesn't append "api/v2/package" to the source URL.</span></span> <span data-ttu-id="4d44c-123">.NET Core 2.1 SDK 以降、使用できるオプションです。</span><span class="sxs-lookup"><span data-stu-id="4d44c-123">Option available since .NET Core 2.1 SDK.</span></span>

* **`--non-interactive`**

  <span data-ttu-id="4d44c-124">ユーザーに入力や確認のメッセージ画面を表示しません。</span><span class="sxs-lookup"><span data-stu-id="4d44c-124">Doesn't prompt for user input or confirmations.</span></span>

* **`-s|--source <SOURCE>`**

  <span data-ttu-id="4d44c-125">サーバー URL を指定します。</span><span class="sxs-lookup"><span data-stu-id="4d44c-125">Specifies the server URL.</span></span> <span data-ttu-id="4d44c-126">nuget.org でサポートされている URL には、`https://www.nuget.org`、`https://www.nuget.org/api/v3`、および `https://www.nuget.org/api/v2/package` が含まれます。</span><span class="sxs-lookup"><span data-stu-id="4d44c-126">Supported URLs for nuget.org include `https://www.nuget.org`, `https://www.nuget.org/api/v3`, and `https://www.nuget.org/api/v2/package`.</span></span> <span data-ttu-id="4d44c-127">プライベート フィードの場合、ホスト名を置き換えます (`%hostname%/api/v3` など)。</span><span class="sxs-lookup"><span data-stu-id="4d44c-127">For private feeds, replace the host name (for example, `%hostname%/api/v3`).</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="4d44c-128">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="4d44c-128">.NET Core 1.x</span></span>](#tab/netcore1x)

* **`--force-english-output`**

  <span data-ttu-id="4d44c-129">インバリアントの英語ベースのカルチャを使用して、アプリケーションの実行を強制します。</span><span class="sxs-lookup"><span data-stu-id="4d44c-129">Forces the application to run using an invariant, English-based culture.</span></span>

* **`-h|--help`**

  <span data-ttu-id="4d44c-130">コマンドの短いヘルプを印刷します。</span><span class="sxs-lookup"><span data-stu-id="4d44c-130">Prints out a short help for the command.</span></span>

* **`-k|--api-key <API_KEY>`**

  <span data-ttu-id="4d44c-131">サーバーの API キーです。</span><span class="sxs-lookup"><span data-stu-id="4d44c-131">The API key for the server.</span></span>

* **`--non-interactive`**

  <span data-ttu-id="4d44c-132">ユーザーに入力や確認のメッセージ画面を表示しません。</span><span class="sxs-lookup"><span data-stu-id="4d44c-132">Doesn't prompt for user input or confirmations.</span></span>

* **`-s|--source <SOURCE>`**

  <span data-ttu-id="4d44c-133">サーバー URL を指定します。</span><span class="sxs-lookup"><span data-stu-id="4d44c-133">Specifies the server URL.</span></span> <span data-ttu-id="4d44c-134">nuget.org でサポートされている URL には、`https://www.nuget.org`、`https://www.nuget.org/api/v3`、および `https://www.nuget.org/api/v2/package` が含まれます。</span><span class="sxs-lookup"><span data-stu-id="4d44c-134">Supported URLs for nuget.org include `https://www.nuget.org`, `https://www.nuget.org/api/v3`, and `https://www.nuget.org/api/v2/package`.</span></span> <span data-ttu-id="4d44c-135">プライベート フィードの場合、ホスト名を置き換えます (`%hostname%/api/v3` など)。</span><span class="sxs-lookup"><span data-stu-id="4d44c-135">For private feeds, replace the host name (for example, `%hostname%/api/v3`).</span></span>

---

## <a name="examples"></a><span data-ttu-id="4d44c-136">使用例</span><span class="sxs-lookup"><span data-stu-id="4d44c-136">Examples</span></span>

* <span data-ttu-id="4d44c-137">`Microsoft.AspNetCore.Mvc` パッケージのバージョン 1.0 を削除します。</span><span class="sxs-lookup"><span data-stu-id="4d44c-137">Deletes version 1.0 of package `Microsoft.AspNetCore.Mvc`:</span></span>

  ```console
  dotnet nuget delete Microsoft.AspNetCore.Mvc 1.0
  ```

* <span data-ttu-id="4d44c-138">ユーザーに資格情報やその他の入力を求めずに、`Microsoft.AspNetCore.Mvc` パッケージのバージョン 1.0 を削除します。</span><span class="sxs-lookup"><span data-stu-id="4d44c-138">Deletes version 1.0 of package `Microsoft.AspNetCore.Mvc`, not prompting user for credentials or other input:</span></span>

  ```console
  dotnet nuget delete Microsoft.AspNetCore.Mvc 1.0 --non-interactive
  ```