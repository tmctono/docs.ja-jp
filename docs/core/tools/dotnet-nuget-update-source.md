---
title: dotnet nuget update source コマンド
description: dotnet nuget update source コマンドを使うと、NuGet 構成ファイルの既存のソースを更新できます。
ms.date: 03/20/2020
ms.openlocfilehash: 38335e07f91850756c7671413e1193c2578e7e7e
ms.sourcegitcommit: 07123a475af89b6da5bb6cc51ea40ab1e8a488f0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80148472"
---
# <a name="dotnet-nuget-update-source"></a><span data-ttu-id="2d385-103">dotnet nuget update source</span><span class="sxs-lookup"><span data-stu-id="2d385-103">dotnet nuget update source</span></span>

<span data-ttu-id="2d385-104">**この記事の対象:** ✔️ .NET Core 3.1.200 SDK 以降のバージョン</span><span class="sxs-lookup"><span data-stu-id="2d385-104">**This article applies to:** ✔️ .NET Core 3.1.200 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="2d385-105">名前</span><span class="sxs-lookup"><span data-stu-id="2d385-105">Name</span></span>

<span data-ttu-id="2d385-106">`dotnet nuget update source` - NuGet ソースを更新します。</span><span class="sxs-lookup"><span data-stu-id="2d385-106">`dotnet nuget update source` - Update a NuGet source.</span></span>

## <a name="synopsis"></a><span data-ttu-id="2d385-107">構文</span><span class="sxs-lookup"><span data-stu-id="2d385-107">Synopsis</span></span>

```dotnetcli
dotnet nuget update source <NAME> [--source] [--username]
    [--password] [--store-password-in-clear-text] [--valid-authentication-types]
    [--configfile]
dotnet nuget update source [-h|--help]
```

## <a name="description"></a><span data-ttu-id="2d385-108">説明</span><span class="sxs-lookup"><span data-stu-id="2d385-108">Description</span></span>

<span data-ttu-id="2d385-109">`dotnet nuget update source` コマンドを使うと、NuGet 構成ファイルの既存のソースを更新できます。</span><span class="sxs-lookup"><span data-stu-id="2d385-109">The `dotnet nuget update source` command updates an existing source in your NuGet configuration files.</span></span>

## <a name="arguments"></a><span data-ttu-id="2d385-110">引数</span><span class="sxs-lookup"><span data-stu-id="2d385-110">Arguments</span></span>

- **`NAME`**

  <span data-ttu-id="2d385-111">ソースの名前。</span><span class="sxs-lookup"><span data-stu-id="2d385-111">Name of the source.</span></span>

## <a name="options"></a><span data-ttu-id="2d385-112">オプション</span><span class="sxs-lookup"><span data-stu-id="2d385-112">Options</span></span>

- **`--configfile`**

  <span data-ttu-id="2d385-113">NuGet 構成ファイル。</span><span class="sxs-lookup"><span data-stu-id="2d385-113">The NuGet configuration file.</span></span> <span data-ttu-id="2d385-114">指定した場合、このファイルの設定のみが使用されます。</span><span class="sxs-lookup"><span data-stu-id="2d385-114">If specified, only the settings from this file will be used.</span></span> <span data-ttu-id="2d385-115">指定しない場合、現在のディレクトリからの構成ファイルの階層が使用されます。</span><span class="sxs-lookup"><span data-stu-id="2d385-115">If not specified, the hierarchy of configuration files from the current directory will be used.</span></span> <span data-ttu-id="2d385-116">詳細については、「[一般的な NuGet 構成](https://docs.microsoft.com/nuget/consume-packages/configuring-nuget-behavior)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="2d385-116">For more information, see [Common NuGet Configurations](https://docs.microsoft.com/nuget/consume-packages/configuring-nuget-behavior).</span></span>

- **`-p|--password`**

  <span data-ttu-id="2d385-117">認証済みソースに接続するときに使用するパスワード。</span><span class="sxs-lookup"><span data-stu-id="2d385-117">Password to be used when connecting to an authenticated source.</span></span>

- **`-s|--source`**

  <span data-ttu-id="2d385-118">パッケージ ソースへのパス。</span><span class="sxs-lookup"><span data-stu-id="2d385-118">Path to the package source.</span></span>

- **`--store-password-in-clear-text`**

  <span data-ttu-id="2d385-119">パスワードの暗号化を無効にすることで、ポータブル パッケージ ソースの資格情報を保存できるようにします。</span><span class="sxs-lookup"><span data-stu-id="2d385-119">Enables storing portable package source credentials by disabling password encryption.</span></span>

- **`-u|--username`**

  <span data-ttu-id="2d385-120">認証済みソースに接続するときに使用するユーザー名。</span><span class="sxs-lookup"><span data-stu-id="2d385-120">Username to be used when connecting to an authenticated source.</span></span>

- **`--valid-authentication-types`**

  <span data-ttu-id="2d385-121">このソースに対して有効な認証の種類のコンマ区切りのリスト。</span><span class="sxs-lookup"><span data-stu-id="2d385-121">Comma-separated list of valid authentication types for this source.</span></span> <span data-ttu-id="2d385-122">サーバーによって NTLM または Negotiate がアドバタイズされていて、基本メカニズムを使用して資格情報を送信する必要がある場合は、これを `basic` に設定します。たとえば、オンプレミスの Azure DevOps Server で PAT を使用する場合などです。</span><span class="sxs-lookup"><span data-stu-id="2d385-122">Set this to `basic` if the server advertises NTLM or Negotiate and your credentials must be sent using the Basic mechanism, for instance when using a PAT with on-premises Azure DevOps Server.</span></span> <span data-ttu-id="2d385-123">その他の有効な値には、`negotiate`、`kerberos`、`ntlm`、`digest` などがありますが、これらの値は役に立たない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="2d385-123">Other valid values include `negotiate`, `kerberos`, `ntlm`, and `digest`, but these values are unlikely to be useful.</span></span>

## <a name="examples"></a><span data-ttu-id="2d385-124">使用例</span><span class="sxs-lookup"><span data-stu-id="2d385-124">Examples</span></span>

- <span data-ttu-id="2d385-125">`mySource` という名前のソースを更新します。</span><span class="sxs-lookup"><span data-stu-id="2d385-125">Update a source with name of `mySource`:</span></span>

  ```dotnetcli
  dotnet nuget update source mySource --source c:\packages
  ```

## <a name="see-also"></a><span data-ttu-id="2d385-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="2d385-126">See also</span></span>

- [<span data-ttu-id="2d385-127">NuGet.config ファイルのパッケージ ソース セクション</span><span class="sxs-lookup"><span data-stu-id="2d385-127">Package source sections in NuGet.config files</span></span>](/nuget/reference/nuget-config-file#package-source-sections)

- [<span data-ttu-id="2d385-128">sources コマンド (nuget.exe)</span><span class="sxs-lookup"><span data-stu-id="2d385-128">sources command (nuget.exe)</span></span>](/nuget/reference/cli-reference/cli-ref-sources)
