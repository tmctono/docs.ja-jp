---
title: dotnet list reference コマンド
description: dotnet list 参照コマンドは、プロジェクト間参照を列挙する便利なオプションを提供します。
ms.date: 06/26/2019
ms.openlocfilehash: 1f87ff89997cdaa6d0095a4db9f28a2e7cb7e6a9
ms.sourcegitcommit: 9b1ac36b6c80176fd4e20eb5bfcbd9d56c3264cf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/28/2019
ms.locfileid: "67421839"
---
# <a name="dotnet-list-reference"></a><span data-ttu-id="725bf-103">dotnet list reference</span><span class="sxs-lookup"><span data-stu-id="725bf-103">dotnet list reference</span></span>

<span data-ttu-id="725bf-104">**このトピックの対象: ✓** .NET Core 1.x SDK 以降のバージョン</span><span class="sxs-lookup"><span data-stu-id="725bf-104">**This topic applies to: ✓** .NET Core 1.x SDK and later versions</span></span>

<!-- todo: uncomment when all CLI commands are reviewed
[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]
-->

## <a name="name"></a><span data-ttu-id="725bf-105">name</span><span class="sxs-lookup"><span data-stu-id="725bf-105">Name</span></span>

<span data-ttu-id="725bf-106">`dotnet list reference` - プロジェクト間参照を列挙します。</span><span class="sxs-lookup"><span data-stu-id="725bf-106">`dotnet list reference` - Lists project-to-project references.</span></span>

## <a name="synopsis"></a><span data-ttu-id="725bf-107">構文</span><span class="sxs-lookup"><span data-stu-id="725bf-107">Synopsis</span></span>

`dotnet list [<PROJECT>|<SOLUTION>] reference [-h|--help]`

## <a name="description"></a><span data-ttu-id="725bf-108">説明</span><span class="sxs-lookup"><span data-stu-id="725bf-108">Description</span></span>

<span data-ttu-id="725bf-109">`dotnet list reference` コマンドは、特定のプロジェクトまたはソリューションのプロジェクト参照を列挙する便利なオプションを提供します。</span><span class="sxs-lookup"><span data-stu-id="725bf-109">The `dotnet list reference` command provides a convenient option to list project references for a given project or solution.</span></span>

## <a name="arguments"></a><span data-ttu-id="725bf-110">引数</span><span class="sxs-lookup"><span data-stu-id="725bf-110">Arguments</span></span>

* **`PROJECT | SOLUTION`**

  <span data-ttu-id="725bf-111">参照の一覧取得に使うプロジェクトまたはソリューション ファイルを指定します。</span><span class="sxs-lookup"><span data-stu-id="725bf-111">Specifies the project or solution file to use for listing references.</span></span> <span data-ttu-id="725bf-112">指定されていない場合、コマンドではプロジェクト ファイルを現在のディレクトリで検索します。</span><span class="sxs-lookup"><span data-stu-id="725bf-112">If not specified, the command searches the current directory for a project file.</span></span>

## <a name="options"></a><span data-ttu-id="725bf-113">オプション</span><span class="sxs-lookup"><span data-stu-id="725bf-113">Options</span></span>

* **`-h|--help`**

  <span data-ttu-id="725bf-114">コマンドの短いヘルプを印刷します。</span><span class="sxs-lookup"><span data-stu-id="725bf-114">Prints out a short help for the command.</span></span>

## <a name="examples"></a><span data-ttu-id="725bf-115">使用例</span><span class="sxs-lookup"><span data-stu-id="725bf-115">Examples</span></span>

* <span data-ttu-id="725bf-116">指定したプロジェクトのプロジェクト参照を列挙する:</span><span class="sxs-lookup"><span data-stu-id="725bf-116">List the project references for the specified project:</span></span>

  ```console
  dotnet list app/app.csproj reference
  ```

* <span data-ttu-id="725bf-117">現在のディレクトリ内のプロジェクトのプロジェクト参照を列挙する:</span><span class="sxs-lookup"><span data-stu-id="725bf-117">List the project references for the project in the current directory:</span></span>

  ```console
  dotnet list reference
  ```
