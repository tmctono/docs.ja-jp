---
title: dotnet nuget disable source コマンド
description: dotnet nuget disable source コマンドを使うと、NuGet 構成ファイルの既存のソースを無効にできます。
ms.date: 03/20/2020
ms.openlocfilehash: 5aa16c842bcddeead180fdeec3d9dcdda33f7ed9
ms.sourcegitcommit: 07123a475af89b6da5bb6cc51ea40ab1e8a488f0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80148478"
---
# <a name="dotnet-nuget-disable-source"></a><span data-ttu-id="72116-103">dotnet nuget disable source</span><span class="sxs-lookup"><span data-stu-id="72116-103">dotnet nuget disable source</span></span>

<span data-ttu-id="72116-104">**この記事の対象:** ✔️ .NET Core 3.1.200 SDK 以降のバージョン</span><span class="sxs-lookup"><span data-stu-id="72116-104">**This article applies to:** ✔️ .NET Core 3.1.200 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="72116-105">名前</span><span class="sxs-lookup"><span data-stu-id="72116-105">Name</span></span>

<span data-ttu-id="72116-106">`dotnet nuget disable source` - NuGet ソースを無効にします。</span><span class="sxs-lookup"><span data-stu-id="72116-106">`dotnet nuget disable source` - Disable a NuGet source.</span></span>

## <a name="synopsis"></a><span data-ttu-id="72116-107">構文</span><span class="sxs-lookup"><span data-stu-id="72116-107">Synopsis</span></span>

```dotnetcli
dotnet nuget disable source <NAME> [--configfile]
dotnet nuget disable source [-h|--help]
```

## <a name="description"></a><span data-ttu-id="72116-108">説明</span><span class="sxs-lookup"><span data-stu-id="72116-108">Description</span></span>

<span data-ttu-id="72116-109">`dotnet nuget disable source` コマンドを使うと、NuGet 構成ファイルの既存のソースを無効にできます。</span><span class="sxs-lookup"><span data-stu-id="72116-109">The `dotnet nuget disable source` command disables an existing source in your NuGet configuration files.</span></span>

## <a name="arguments"></a><span data-ttu-id="72116-110">引数</span><span class="sxs-lookup"><span data-stu-id="72116-110">Arguments</span></span>

- **`NAME`**

  <span data-ttu-id="72116-111">ソースの名前。</span><span class="sxs-lookup"><span data-stu-id="72116-111">Name of the source.</span></span>

## <a name="options"></a><span data-ttu-id="72116-112">オプション</span><span class="sxs-lookup"><span data-stu-id="72116-112">Options</span></span>

- **`--configfile`**

  <span data-ttu-id="72116-113">NuGet 構成ファイル。</span><span class="sxs-lookup"><span data-stu-id="72116-113">The NuGet configuration file.</span></span> <span data-ttu-id="72116-114">指定した場合、このファイルの設定のみが使用されます。</span><span class="sxs-lookup"><span data-stu-id="72116-114">If specified, only the settings from this file will be used.</span></span> <span data-ttu-id="72116-115">指定しない場合、現在のディレクトリからの構成ファイルの階層が使用されます。</span><span class="sxs-lookup"><span data-stu-id="72116-115">If not specified, the hierarchy of configuration files from the current directory will be used.</span></span> <span data-ttu-id="72116-116">詳細については、「[一般的な NuGet 構成](https://docs.microsoft.com/nuget/consume-packages/configuring-nuget-behavior)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="72116-116">For more information, see [Common NuGet Configurations](https://docs.microsoft.com/nuget/consume-packages/configuring-nuget-behavior).</span></span>

## <a name="examples"></a><span data-ttu-id="72116-117">使用例</span><span class="sxs-lookup"><span data-stu-id="72116-117">Examples</span></span>

- <span data-ttu-id="72116-118">`mySource` という名前のソースを無効にします。</span><span class="sxs-lookup"><span data-stu-id="72116-118">Disable a source with name of `mySource`:</span></span>

  ```dotnetcli
  dotnet nuget disable source mySource
  ```

## <a name="see-also"></a><span data-ttu-id="72116-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="72116-119">See also</span></span>

- [<span data-ttu-id="72116-120">NuGet.config ファイルのパッケージ ソース セクション</span><span class="sxs-lookup"><span data-stu-id="72116-120">Package source sections in NuGet.config files</span></span>](/nuget/reference/nuget-config-file#package-source-sections)

- [<span data-ttu-id="72116-121">sources コマンド (nuget.exe)</span><span class="sxs-lookup"><span data-stu-id="72116-121">sources command (nuget.exe)</span></span>](/nuget/reference/cli-reference/cli-ref-sources)
