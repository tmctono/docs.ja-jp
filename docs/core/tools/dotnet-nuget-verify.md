---
title: dotnet nuget verify コマンド
description: dotnet nuget verify コマンドによって、署名されたパッケージが検証されます。
author: kartheekp-ms
ms.date: 10/08/2020
ms.openlocfilehash: 6cb368e2b6c203f3774b4450c0831c5d6b2dc0e8
ms.sourcegitcommit: b59237ca4ec763969a0dd775a3f8f39f8c59fe24
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/12/2020
ms.locfileid: "91957101"
---
# <a name="dotnet-nuget-verify"></a><span data-ttu-id="b15d8-103">dotnet nuget verify</span><span class="sxs-lookup"><span data-stu-id="b15d8-103">dotnet nuget verify</span></span>

<span data-ttu-id="b15d8-104">**この記事の対象:** ✔️ .NET 5.0.100-rc.2.x SDK 以降のバージョン</span><span class="sxs-lookup"><span data-stu-id="b15d8-104">**This article applies to:** ✔️ .NET 5.0.100-rc.2.x SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="b15d8-105">名前</span><span class="sxs-lookup"><span data-stu-id="b15d8-105">Name</span></span>

<span data-ttu-id="b15d8-106">`dotnet nuget verify` - 署名済みの NuGet パッケージを検証します。</span><span class="sxs-lookup"><span data-stu-id="b15d8-106">`dotnet nuget verify` - Verifies a signed NuGet package.</span></span>

## <a name="synopsis"></a><span data-ttu-id="b15d8-107">構文</span><span class="sxs-lookup"><span data-stu-id="b15d8-107">Synopsis</span></span>

```dotnetcli
dotnet nuget verify [<package-path(s)>]
    [--all]
    [--certificate-fingerprint <FINGERPRINT>]
    [-v|--verbosity <LEVEL>]

dotnet nuget verify -h|--help
```

## <a name="description"></a><span data-ttu-id="b15d8-108">説明</span><span class="sxs-lookup"><span data-stu-id="b15d8-108">Description</span></span>

<span data-ttu-id="b15d8-109">`dotnet nuget verify` コマンドによって、署名済みの NuGet パッケージが検証されます。</span><span class="sxs-lookup"><span data-stu-id="b15d8-109">The `dotnet nuget verify` command verifies a signed NuGet package.</span></span>

## <a name="arguments"></a><span data-ttu-id="b15d8-110">引数</span><span class="sxs-lookup"><span data-stu-id="b15d8-110">Arguments</span></span>

- **`package-path(s)`**

  <span data-ttu-id="b15d8-111">検証されるパッケージのファイル パスを指定します。</span><span class="sxs-lookup"><span data-stu-id="b15d8-111">Specifies the file path to the package(s) to be verified.</span></span> <span data-ttu-id="b15d8-112">複数のパッケージを検証するために、複数の位置引数を渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="b15d8-112">Multiple position arguments can be passed in to verify multiple packages.</span></span>

## <a name="options"></a><span data-ttu-id="b15d8-113">オプション</span><span class="sxs-lookup"><span data-stu-id="b15d8-113">Options</span></span>

- **`--all`**

  <span data-ttu-id="b15d8-114">可能なすべての検証をパッケージに対して実行する必要があることを指定します。</span><span class="sxs-lookup"><span data-stu-id="b15d8-114">Specifies that all verifications possible should be performed on the package(s).</span></span> <span data-ttu-id="b15d8-115">既定では、`signatures` のみ検証されます。</span><span class="sxs-lookup"><span data-stu-id="b15d8-115">By default, only `signatures` are verified.</span></span>

> [!NOTE]
> <span data-ttu-id="b15d8-116">このコマンドで現在サポートされているのは、`signature` 検証のみとなります。</span><span class="sxs-lookup"><span data-stu-id="b15d8-116">This command currently supports only `signature` verification.</span></span>

- **`--certificate-fingerprint <FINGERPRINT>`**

  <span data-ttu-id="b15d8-117">署名者の証明書が、指定されたいずれかの `SHA256` 指紋と一致していることを検証します。</span><span class="sxs-lookup"><span data-stu-id="b15d8-117">Verify that the signer certificate matches with one of the specified `SHA256` fingerprints.</span></span> <span data-ttu-id="b15d8-118">このオプションを複数回指定することで複数のフィンガープリントを提供できます。</span><span class="sxs-lookup"><span data-stu-id="b15d8-118">This option can be supplied multiple times to provide multiple fingerprints.</span></span>

* **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="b15d8-119">MSBuild の詳細レベルを設定します。</span><span class="sxs-lookup"><span data-stu-id="b15d8-119">Sets the MSBuild verbosity level.</span></span> <span data-ttu-id="b15d8-120">指定できる値は、`q[uiet]`、`m[inimal]`、`n[ormal]`、`d[etailed]`、および `diag[nostic]` です。</span><span class="sxs-lookup"><span data-stu-id="b15d8-120">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="b15d8-121">既定値は、`normal` です。</span><span class="sxs-lookup"><span data-stu-id="b15d8-121">The default is `normal`.</span></span>

* **`-h|--help`**

  <span data-ttu-id="b15d8-122">コマンドの短いヘルプを印刷します。</span><span class="sxs-lookup"><span data-stu-id="b15d8-122">Prints out a short help for the command.</span></span>

## <a name="examples"></a><span data-ttu-id="b15d8-123">使用例</span><span class="sxs-lookup"><span data-stu-id="b15d8-123">Examples</span></span>

- <span data-ttu-id="b15d8-124">*foo.nupkg* を検証します。</span><span class="sxs-lookup"><span data-stu-id="b15d8-124">Verify *foo.nupkg*:</span></span>

  ```dotnetcli
  dotnet nuget verify foo.nupkg
  ```

- <span data-ttu-id="b15d8-125">複数の NuGet パッケージを検証します - *foo. nupkg* および "*指定されたディレクトリ内のすべての .nupkg ファイル*"。</span><span class="sxs-lookup"><span data-stu-id="b15d8-125">Verify multiple NuGet packages - *foo.nupkg* and *all .nupkg files in the directory specified*:</span></span>

  ```dotnetcli
  dotnet nuget verify foo.nupkg c:\mydir\*.nupkg
  ```

- <span data-ttu-id="b15d8-126">*foo. nupkg* の署名が、指定された証明書のフィンガープリントと一致していることを検証します。</span><span class="sxs-lookup"><span data-stu-id="b15d8-126">Verify *foo.nupkg* signature matches with the specified certificate fingerprint:</span></span>

  ```dotnetcli
  dotnet nuget verify foo.nupkg --certificate-fingerprint CE40881FF5F0AD3E58965DA20A9F571EF1651A56933748E1BF1C99E537C4E039
  ```

- <span data-ttu-id="b15d8-127">*foo. nupkg* の署名が、指定された証明書のフィンガープリントのいずれかと一致していることを検証します。</span><span class="sxs-lookup"><span data-stu-id="b15d8-127">Verify *foo.nupkg* signature matches with one of the specified certificate fingerprints:</span></span>

  ```dotnetcli
  dotnet nuget verify foo.nupkg --certificate-fingerprint CE40881FF5F0AD3E58965DA20A9F571EF1651A56933748E1BF1C99E537C4E039 --certificate-fingerprint EC10992GG5F0AD3E58965DA20A9F571EF1651A56933748E1BF1C99E537C4E027
  ```
