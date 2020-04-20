---
title: dotnet nuget enable source コマンド
description: dotnet nuget enable source コマンドを使うと、NuGet 構成ファイルの既存のソースを有効にできます。
ms.date: 03/20/2020
ms.openlocfilehash: 38fb5917361bd7952fef9c31ed897fb81f005155
ms.sourcegitcommit: 927b7ea6b2ea5a440c8f23e3e66503152eb85591
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/16/2020
ms.locfileid: "81463558"
---
# <a name="dotnet-nuget-enable-source"></a><span data-ttu-id="f1a2a-103">dotnet nuget enable source</span><span class="sxs-lookup"><span data-stu-id="f1a2a-103">dotnet nuget enable source</span></span>

<span data-ttu-id="f1a2a-104">**この記事の対象:** ✔️ .NET Core 3.1.200 SDK 以降のバージョン</span><span class="sxs-lookup"><span data-stu-id="f1a2a-104">**This article applies to:** ✔️ .NET Core 3.1.200 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="f1a2a-105">名前</span><span class="sxs-lookup"><span data-stu-id="f1a2a-105">Name</span></span>

<span data-ttu-id="f1a2a-106">`dotnet nuget enable source` - NuGet ソースを有効にします。</span><span class="sxs-lookup"><span data-stu-id="f1a2a-106">`dotnet nuget enable source` - Enable a NuGet source.</span></span>

## <a name="synopsis"></a><span data-ttu-id="f1a2a-107">構文</span><span class="sxs-lookup"><span data-stu-id="f1a2a-107">Synopsis</span></span>

```dotnetcli
dotnet nuget enable source <NAME> [--configfile <FILE>]

dotnet nuget enable source -h|--help
```

## <a name="description"></a><span data-ttu-id="f1a2a-108">説明</span><span class="sxs-lookup"><span data-stu-id="f1a2a-108">Description</span></span>

<span data-ttu-id="f1a2a-109">`dotnet nuget enable source` コマンドを使うと、NuGet 構成ファイルの既存のソースを有効にできます。</span><span class="sxs-lookup"><span data-stu-id="f1a2a-109">The `dotnet nuget enable source` command enables an existing source in your NuGet configuration files.</span></span>

## <a name="arguments"></a><span data-ttu-id="f1a2a-110">引数</span><span class="sxs-lookup"><span data-stu-id="f1a2a-110">Arguments</span></span>

- **`NAME`**

  <span data-ttu-id="f1a2a-111">ソースの名前。</span><span class="sxs-lookup"><span data-stu-id="f1a2a-111">Name of the source.</span></span>

## <a name="options"></a><span data-ttu-id="f1a2a-112">オプション</span><span class="sxs-lookup"><span data-stu-id="f1a2a-112">Options</span></span>

- **`--configfile <FILE>`**

  <span data-ttu-id="f1a2a-113">NuGet 構成ファイル。</span><span class="sxs-lookup"><span data-stu-id="f1a2a-113">The NuGet configuration file.</span></span> <span data-ttu-id="f1a2a-114">指定した場合、このファイルの設定のみが使用されます。</span><span class="sxs-lookup"><span data-stu-id="f1a2a-114">If specified, only the settings from this file will be used.</span></span> <span data-ttu-id="f1a2a-115">指定しない場合、現在のディレクトリからの構成ファイルの階層が使用されます。</span><span class="sxs-lookup"><span data-stu-id="f1a2a-115">If not specified, the hierarchy of configuration files from the current directory will be used.</span></span> <span data-ttu-id="f1a2a-116">詳細については、「[一般的な NuGet 構成](https://docs.microsoft.com/nuget/consume-packages/configuring-nuget-behavior)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="f1a2a-116">For more information, see [Common NuGet Configurations](https://docs.microsoft.com/nuget/consume-packages/configuring-nuget-behavior).</span></span>

## <a name="examples"></a><span data-ttu-id="f1a2a-117">使用例</span><span class="sxs-lookup"><span data-stu-id="f1a2a-117">Examples</span></span>

- <span data-ttu-id="f1a2a-118">`mySource` という名前のソースを有効にします。</span><span class="sxs-lookup"><span data-stu-id="f1a2a-118">Enable a source with name of `mySource`:</span></span>

  ```dotnetcli
  dotnet nuget enable source mySource
  ```

## <a name="see-also"></a><span data-ttu-id="f1a2a-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="f1a2a-119">See also</span></span>

- [<span data-ttu-id="f1a2a-120">NuGet.config ファイルのパッケージ ソース セクション</span><span class="sxs-lookup"><span data-stu-id="f1a2a-120">Package source sections in NuGet.config files</span></span>](/nuget/reference/nuget-config-file#package-source-sections)

- [<span data-ttu-id="f1a2a-121">sources コマンド (nuget.exe)</span><span class="sxs-lookup"><span data-stu-id="f1a2a-121">sources command (nuget.exe)</span></span>](/nuget/reference/cli-reference/cli-ref-sources)
