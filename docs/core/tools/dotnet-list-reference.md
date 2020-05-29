---
title: dotnet list reference コマンド
description: dotnet list 参照コマンドは、プロジェクト間参照を列挙する便利なオプションを提供します。
ms.date: 02/14/2020
ms.openlocfilehash: b9b34c17102c6218f3d99f6e2620e99f70140284
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/22/2020
ms.locfileid: "83802763"
---
# <a name="dotnet-list-reference"></a><span data-ttu-id="03cfa-103">dotnet list reference</span><span class="sxs-lookup"><span data-stu-id="03cfa-103">dotnet list reference</span></span>

<span data-ttu-id="03cfa-104">**この記事の対象:** ✔️ .NET Core 2.x SDK 以降のバージョン</span><span class="sxs-lookup"><span data-stu-id="03cfa-104">**This article applies to:** ✔️ .NET Core 2.x SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="03cfa-105">名前</span><span class="sxs-lookup"><span data-stu-id="03cfa-105">Name</span></span>

<span data-ttu-id="03cfa-106">`dotnet list reference` - プロジェクト間参照を列挙します。</span><span class="sxs-lookup"><span data-stu-id="03cfa-106">`dotnet list reference` - Lists project-to-project references.</span></span>

## <a name="synopsis"></a><span data-ttu-id="03cfa-107">構文</span><span class="sxs-lookup"><span data-stu-id="03cfa-107">Synopsis</span></span>

```dotnetcli
dotnet list [<PROJECT>] reference

dotnet list -h|--help
```

## <a name="description"></a><span data-ttu-id="03cfa-108">説明</span><span class="sxs-lookup"><span data-stu-id="03cfa-108">Description</span></span>

<span data-ttu-id="03cfa-109">`dotnet list reference` コマンドは、特定のプロジェクトのプロジェクト参照を列挙する便利なオプションを提供します。</span><span class="sxs-lookup"><span data-stu-id="03cfa-109">The `dotnet list reference` command provides a convenient option to list project references for a given project.</span></span>

## <a name="arguments"></a><span data-ttu-id="03cfa-110">引数</span><span class="sxs-lookup"><span data-stu-id="03cfa-110">Arguments</span></span>

* **`PROJECT`**

  <span data-ttu-id="03cfa-111">操作するプロジェクト ファイル。</span><span class="sxs-lookup"><span data-stu-id="03cfa-111">The project file to operate on.</span></span> <span data-ttu-id="03cfa-112">ファイルを指定しない場合、コマンドによって現在のディレクトリから検索されます。</span><span class="sxs-lookup"><span data-stu-id="03cfa-112">If a file is not specified, the command will search the current directory for one.</span></span>

## <a name="options"></a><span data-ttu-id="03cfa-113">オプション</span><span class="sxs-lookup"><span data-stu-id="03cfa-113">Options</span></span>

* **`-h|--help`**

  <span data-ttu-id="03cfa-114">コマンドの短いヘルプを印刷します。</span><span class="sxs-lookup"><span data-stu-id="03cfa-114">Prints out a short help for the command.</span></span>

## <a name="examples"></a><span data-ttu-id="03cfa-115">使用例</span><span class="sxs-lookup"><span data-stu-id="03cfa-115">Examples</span></span>

* <span data-ttu-id="03cfa-116">指定したプロジェクトのプロジェクト参照を列挙する:</span><span class="sxs-lookup"><span data-stu-id="03cfa-116">List the project references for the specified project:</span></span>

  ```dotnetcli
  dotnet list app/app.csproj reference
  ```

* <span data-ttu-id="03cfa-117">現在のディレクトリ内のプロジェクトのプロジェクト参照を列挙する:</span><span class="sxs-lookup"><span data-stu-id="03cfa-117">List the project references for the project in the current directory:</span></span>

  ```dotnetcli
  dotnet list reference
  ```
