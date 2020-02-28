---
title: dotnet remove package コマンド
description: dotnet remove package コマンドは、プロジェクトへの NuGet パッケージ参照を削除する便利なオプションを提供します。
ms.date: 02/14/2020
ms.openlocfilehash: 8eaa311748c5627351ef149012dc4dddd2ab2793
ms.sourcegitcommit: f38e527623883b92010cf4760246203073e12898
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/20/2020
ms.locfileid: "77503639"
---
# <a name="dotnet-remove-package"></a><span data-ttu-id="74599-103">dotnet remove package</span><span class="sxs-lookup"><span data-stu-id="74599-103">dotnet remove package</span></span>

<span data-ttu-id="74599-104">**この記事の対象:** ✔️ .NET Core 2.x SDK 以降のバージョン</span><span class="sxs-lookup"><span data-stu-id="74599-104">**This article applies to:** ✔️ .NET Core 2.x SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="74599-105">名前</span><span class="sxs-lookup"><span data-stu-id="74599-105">Name</span></span>

<span data-ttu-id="74599-106">`dotnet remove package` - プロジェクト ファイルからパッケージ参照を削除します。</span><span class="sxs-lookup"><span data-stu-id="74599-106">`dotnet remove package` - Removes package reference from a project file.</span></span>

## <a name="synopsis"></a><span data-ttu-id="74599-107">構文</span><span class="sxs-lookup"><span data-stu-id="74599-107">Synopsis</span></span>

```dotnetcli
dotnet remove [<PROJECT>] package <PACKAGE_NAME> [-h|--help]
```

## <a name="description"></a><span data-ttu-id="74599-108">説明</span><span class="sxs-lookup"><span data-stu-id="74599-108">Description</span></span>

<span data-ttu-id="74599-109">`dotnet remove package` コマンドは、NuGet パッケージ参照をプロジェクトから削除する便利なオプションを提供します。</span><span class="sxs-lookup"><span data-stu-id="74599-109">The `dotnet remove package` command provides a convenient option to remove a NuGet package reference from a project.</span></span>

## <a name="arguments"></a><span data-ttu-id="74599-110">引数</span><span class="sxs-lookup"><span data-stu-id="74599-110">Arguments</span></span>

`PROJECT`

<span data-ttu-id="74599-111">プロジェクト ファイルを指定します。</span><span class="sxs-lookup"><span data-stu-id="74599-111">Specifies the project file.</span></span> <span data-ttu-id="74599-112">指定されていない場合、現在のディレクトリで検索されます。</span><span class="sxs-lookup"><span data-stu-id="74599-112">If not specified, the command searches the current directory for one.</span></span>

`PACKAGE_NAME`

<span data-ttu-id="74599-113">削除するパッケージ参照。</span><span class="sxs-lookup"><span data-stu-id="74599-113">The package reference to remove.</span></span>

## <a name="options"></a><span data-ttu-id="74599-114">オプション</span><span class="sxs-lookup"><span data-stu-id="74599-114">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="74599-115">コマンドの短いヘルプを印刷します。</span><span class="sxs-lookup"><span data-stu-id="74599-115">Prints out a short help for the command.</span></span>

## <a name="examples"></a><span data-ttu-id="74599-116">使用例</span><span class="sxs-lookup"><span data-stu-id="74599-116">Examples</span></span>

- <span data-ttu-id="74599-117">現在のディレクトリにあるプロジェクトから `Newtonsoft.Json` NuGet パッケージを削除する:</span><span class="sxs-lookup"><span data-stu-id="74599-117">Remove `Newtonsoft.Json` NuGet package from a project in the current directory:</span></span>

  ```dotnetcli
  dotnet remove package Newtonsoft.Json
  ```
