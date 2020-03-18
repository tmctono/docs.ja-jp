---
title: dotnet list reference コマンド
description: dotnet list 参照コマンドは、プロジェクト間参照を列挙する便利なオプションを提供します。
ms.date: 02/14/2020
ms.openlocfilehash: 43c4dbc94b33e717c6ba0a1c1c5317ac006f5bba
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2020
ms.locfileid: "77503718"
---
# <a name="dotnet-list-reference"></a><span data-ttu-id="1f216-103">dotnet list reference</span><span class="sxs-lookup"><span data-stu-id="1f216-103">dotnet list reference</span></span>

<span data-ttu-id="1f216-104">**この記事の対象:** ✔️ .NET Core 2.x SDK 以降のバージョン</span><span class="sxs-lookup"><span data-stu-id="1f216-104">**This article applies to:** ✔️ .NET Core 2.x SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="1f216-105">name</span><span class="sxs-lookup"><span data-stu-id="1f216-105">Name</span></span>

<span data-ttu-id="1f216-106">`dotnet list reference` - プロジェクト間参照を列挙します。</span><span class="sxs-lookup"><span data-stu-id="1f216-106">`dotnet list reference` - Lists project-to-project references.</span></span>

## <a name="synopsis"></a><span data-ttu-id="1f216-107">構文</span><span class="sxs-lookup"><span data-stu-id="1f216-107">Synopsis</span></span>

`dotnet list [<PROJECT>|<SOLUTION>] reference [-h|--help]`

## <a name="description"></a><span data-ttu-id="1f216-108">[説明]</span><span class="sxs-lookup"><span data-stu-id="1f216-108">Description</span></span>

<span data-ttu-id="1f216-109">`dotnet list reference` コマンドは、特定のプロジェクトまたはソリューションのプロジェクト参照を列挙する便利なオプションを提供します。</span><span class="sxs-lookup"><span data-stu-id="1f216-109">The `dotnet list reference` command provides a convenient option to list project references for a given project or solution.</span></span>

## <a name="arguments"></a><span data-ttu-id="1f216-110">引数</span><span class="sxs-lookup"><span data-stu-id="1f216-110">Arguments</span></span>

* **`PROJECT | SOLUTION`**

  <span data-ttu-id="1f216-111">参照の一覧取得に使うプロジェクトまたはソリューション ファイルを指定します。</span><span class="sxs-lookup"><span data-stu-id="1f216-111">Specifies the project or solution file to use for listing references.</span></span> <span data-ttu-id="1f216-112">指定されていない場合、コマンドではプロジェクト ファイルを現在のディレクトリで検索します。</span><span class="sxs-lookup"><span data-stu-id="1f216-112">If not specified, the command searches the current directory for a project file.</span></span>

## <a name="options"></a><span data-ttu-id="1f216-113">オプション</span><span class="sxs-lookup"><span data-stu-id="1f216-113">Options</span></span>

* **`-h|--help`**

  <span data-ttu-id="1f216-114">コマンドの短いヘルプを印刷します。</span><span class="sxs-lookup"><span data-stu-id="1f216-114">Prints out a short help for the command.</span></span>

## <a name="examples"></a><span data-ttu-id="1f216-115">例</span><span class="sxs-lookup"><span data-stu-id="1f216-115">Examples</span></span>

* <span data-ttu-id="1f216-116">指定したプロジェクトのプロジェクト参照を列挙する:</span><span class="sxs-lookup"><span data-stu-id="1f216-116">List the project references for the specified project:</span></span>

  ```dotnetcli
  dotnet list app/app.csproj reference
  ```

* <span data-ttu-id="1f216-117">現在のディレクトリ内のプロジェクトのプロジェクト参照を列挙する:</span><span class="sxs-lookup"><span data-stu-id="1f216-117">List the project references for the project in the current directory:</span></span>

  ```dotnetcli
  dotnet list reference
  ```
