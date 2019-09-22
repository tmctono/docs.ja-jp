---
title: dotnet list reference コマンド
description: dotnet list 参照コマンドは、プロジェクト間参照を列挙する便利なオプションを提供します。
ms.date: 06/26/2019
ms.openlocfilehash: b4b82ca1e7aeb2b73d9f99aff1c97452b2166770
ms.sourcegitcommit: a4b10e1f2a8bb4e8ff902630855474a0c4f1b37a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2019
ms.locfileid: "71117682"
---
# <a name="dotnet-list-reference"></a><span data-ttu-id="bbade-103">dotnet list reference</span><span class="sxs-lookup"><span data-stu-id="bbade-103">dotnet list reference</span></span>

<span data-ttu-id="bbade-104">**このトピックの対象: ✓** .NET Core 1.x SDK 以降のバージョン</span><span class="sxs-lookup"><span data-stu-id="bbade-104">**This topic applies to: ✓** .NET Core 1.x SDK and later versions</span></span>

<!-- todo: uncomment when all CLI commands are reviewed
[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]
-->

## <a name="name"></a><span data-ttu-id="bbade-105">name</span><span class="sxs-lookup"><span data-stu-id="bbade-105">Name</span></span>

<span data-ttu-id="bbade-106">`dotnet list reference` - プロジェクト間参照を列挙します。</span><span class="sxs-lookup"><span data-stu-id="bbade-106">`dotnet list reference` - Lists project-to-project references.</span></span>

## <a name="synopsis"></a><span data-ttu-id="bbade-107">構文</span><span class="sxs-lookup"><span data-stu-id="bbade-107">Synopsis</span></span>

`dotnet list [<PROJECT>|<SOLUTION>] reference [-h|--help]`

## <a name="description"></a><span data-ttu-id="bbade-108">説明</span><span class="sxs-lookup"><span data-stu-id="bbade-108">Description</span></span>

<span data-ttu-id="bbade-109">`dotnet list reference` コマンドは、特定のプロジェクトまたはソリューションのプロジェクト参照を列挙する便利なオプションを提供します。</span><span class="sxs-lookup"><span data-stu-id="bbade-109">The `dotnet list reference` command provides a convenient option to list project references for a given project or solution.</span></span>

## <a name="arguments"></a><span data-ttu-id="bbade-110">引数</span><span class="sxs-lookup"><span data-stu-id="bbade-110">Arguments</span></span>

* **`PROJECT | SOLUTION`**

  <span data-ttu-id="bbade-111">参照の一覧取得に使うプロジェクトまたはソリューション ファイルを指定します。</span><span class="sxs-lookup"><span data-stu-id="bbade-111">Specifies the project or solution file to use for listing references.</span></span> <span data-ttu-id="bbade-112">指定されていない場合、コマンドではプロジェクト ファイルを現在のディレクトリで検索します。</span><span class="sxs-lookup"><span data-stu-id="bbade-112">If not specified, the command searches the current directory for a project file.</span></span>

## <a name="options"></a><span data-ttu-id="bbade-113">オプション</span><span class="sxs-lookup"><span data-stu-id="bbade-113">Options</span></span>

* **`-h|--help`**

  <span data-ttu-id="bbade-114">コマンドの短いヘルプを印刷します。</span><span class="sxs-lookup"><span data-stu-id="bbade-114">Prints out a short help for the command.</span></span>

## <a name="examples"></a><span data-ttu-id="bbade-115">使用例</span><span class="sxs-lookup"><span data-stu-id="bbade-115">Examples</span></span>

* <span data-ttu-id="bbade-116">指定したプロジェクトのプロジェクト参照を列挙する:</span><span class="sxs-lookup"><span data-stu-id="bbade-116">List the project references for the specified project:</span></span>

  ```dotnetcli
  dotnet list app/app.csproj reference
  ```

* <span data-ttu-id="bbade-117">現在のディレクトリ内のプロジェクトのプロジェクト参照を列挙する:</span><span class="sxs-lookup"><span data-stu-id="bbade-117">List the project references for the project in the current directory:</span></span>

  ```dotnetcli
  dotnet list reference
  ```
