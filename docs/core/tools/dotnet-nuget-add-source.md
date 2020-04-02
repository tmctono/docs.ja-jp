---
title: dotnet nuget add source コマンド
description: dotnet nuget add source コマンドを使うと、NuGet 構成ファイルに新しいパッケージ ソースを追加できます。
ms.date: 03/20/2020
ms.openlocfilehash: c1e398699c7482a69b750cde718e6f9178b5c4bd
ms.sourcegitcommit: 07123a475af89b6da5bb6cc51ea40ab1e8a488f0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80148490"
---
# <a name="dotnet-nuget-add-source"></a><span data-ttu-id="7572a-103">dotnet nuget add source</span><span class="sxs-lookup"><span data-stu-id="7572a-103">dotnet nuget add source</span></span>

<span data-ttu-id="7572a-104">**この記事の対象:** ✔️ .NET Core 3.1.200 SDK 以降のバージョン</span><span class="sxs-lookup"><span data-stu-id="7572a-104">**This article applies to:** ✔️ .NET Core 3.1.200 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="7572a-105">名前</span><span class="sxs-lookup"><span data-stu-id="7572a-105">Name</span></span>

<span data-ttu-id="7572a-106">`dotnet nuget add source` - NuGet ソースを追加にします。</span><span class="sxs-lookup"><span data-stu-id="7572a-106">`dotnet nuget add source` - Add a NuGet source.</span></span>

## <a name="synopsis"></a><span data-ttu-id="7572a-107">構文</span><span class="sxs-lookup"><span data-stu-id="7572a-107">Synopsis</span></span>

```dotnetcli
dotnet nuget add source <PACKAGE_SOURCE_PATH> [--name] [--username]
    [--password] [--store-password-in-clear-text] [--valid-authentication-types]
    [--configfile]
dotnet nuget add source [-h|--help]
```

## <a name="description"></a><span data-ttu-id="7572a-108">説明</span><span class="sxs-lookup"><span data-stu-id="7572a-108">Description</span></span>

<span data-ttu-id="7572a-109">`dotnet nuget add source` コマンドを使うと、NuGet 構成ファイルに新しいパッケージ ソースを追加できます。</span><span class="sxs-lookup"><span data-stu-id="7572a-109">The `dotnet nuget add source` command adds a new package source to your NuGet configuration files.</span></span>

## <a name="arguments"></a><span data-ttu-id="7572a-110">引数</span><span class="sxs-lookup"><span data-stu-id="7572a-110">Arguments</span></span>

- **`PACKAGE_SOURCE_PATH`**

  <span data-ttu-id="7572a-111">パッケージ ソースへのパス。</span><span class="sxs-lookup"><span data-stu-id="7572a-111">Path to the package source.</span></span>

## <a name="options"></a><span data-ttu-id="7572a-112">オプション</span><span class="sxs-lookup"><span data-stu-id="7572a-112">Options</span></span>

- **`--configfile`**

  <span data-ttu-id="7572a-113">NuGet 構成ファイル。</span><span class="sxs-lookup"><span data-stu-id="7572a-113">The NuGet configuration file.</span></span> <span data-ttu-id="7572a-114">指定した場合、このファイルの設定のみが使用されます。</span><span class="sxs-lookup"><span data-stu-id="7572a-114">If specified, only the settings from this file will be used.</span></span> <span data-ttu-id="7572a-115">指定しない場合、現在のディレクトリからの構成ファイルの階層が使用されます。</span><span class="sxs-lookup"><span data-stu-id="7572a-115">If not specified, the hierarchy of configuration files from the current directory will be used.</span></span> <span data-ttu-id="7572a-116">詳細については、「[一般的な NuGet 構成](https://docs.microsoft.com/nuget/consume-packages/configuring-nuget-behavior)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="7572a-116">For more information, see [Common NuGet Configurations](https://docs.microsoft.com/nuget/consume-packages/configuring-nuget-behavior).</span></span>

- **`-n|--name`**

  <span data-ttu-id="7572a-117">ソースの名前。</span><span class="sxs-lookup"><span data-stu-id="7572a-117">Name of the source.</span></span>

- **`-p|--password`**

  <span data-ttu-id="7572a-118">認証済みソースに接続するときに使用するパスワード。</span><span class="sxs-lookup"><span data-stu-id="7572a-118">Password to be used when connecting to an authenticated source.</span></span>

- **`--store-password-in-clear-text`**

  <span data-ttu-id="7572a-119">パスワードの暗号化を無効にすることで、ポータブル パッケージ ソースの資格情報を保存できるようにします。</span><span class="sxs-lookup"><span data-stu-id="7572a-119">Enables storing portable package source credentials by disabling password encryption.</span></span>

- **`-u|--username`**

  <span data-ttu-id="7572a-120">認証済みソースに接続するときに使用するユーザー名。</span><span class="sxs-lookup"><span data-stu-id="7572a-120">Username to be used when connecting to an authenticated source.</span></span>

- **`--valid-authentication-types`**

  <span data-ttu-id="7572a-121">このソースに対して有効な認証の種類のコンマ区切りのリスト。</span><span class="sxs-lookup"><span data-stu-id="7572a-121">Comma-separated list of valid authentication types for this source.</span></span> <span data-ttu-id="7572a-122">サーバーによって NTLM または Negotiate がアドバタイズされていて、基本メカニズムを使用して資格情報を送信する必要がある場合は、これを `basic` に設定します。たとえば、オンプレミスの Azure DevOps Server で PAT を使用する場合などです。</span><span class="sxs-lookup"><span data-stu-id="7572a-122">Set this to `basic` if the server advertises NTLM or Negotiate and your credentials must be sent using the Basic mechanism, for instance when using a PAT with on-premises Azure DevOps Server.</span></span> <span data-ttu-id="7572a-123">その他の有効な値には、`negotiate`、`kerberos`、`ntlm`、`digest` などがありますが、これらの値は役に立たない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="7572a-123">Other valid values include `negotiate`, `kerberos`, `ntlm`, and `digest`, but these values are unlikely to be useful.</span></span>

## <a name="examples"></a><span data-ttu-id="7572a-124">使用例</span><span class="sxs-lookup"><span data-stu-id="7572a-124">Examples</span></span>

- <span data-ttu-id="7572a-125">`nuget.org` をソースとして追加します。</span><span class="sxs-lookup"><span data-stu-id="7572a-125">Add `nuget.org` as a source:</span></span>

  ```dotnetcli
  dotnet nuget add source https://api.nuget.org/v3/index.json -n nuget.org
  ```

- <span data-ttu-id="7572a-126">`c:\packages` をローカル ソースとして追加します。</span><span class="sxs-lookup"><span data-stu-id="7572a-126">Add `c:\packages` as a local source:</span></span>

  ```dotnetcli
  dotnet nuget add source c:\packages
  ```

- <span data-ttu-id="7572a-127">認証が必要なソースを追加します。</span><span class="sxs-lookup"><span data-stu-id="7572a-127">Add a source that needs authentication:</span></span>

  ```dotnetcli
  dotnet nuget add source https://someServer/myTeam -n myTeam -u myUsername -p myPassword --store-password-in-clear-text
  ```

- <span data-ttu-id="7572a-128">認証が必要なソースを追加します (その後資格情報プロバイダーをインストールします)。</span><span class="sxs-lookup"><span data-stu-id="7572a-128">Add a source that needs authentication (then go install credential provider):</span></span>

  ```dotnetcli
  dotnet nuget add source https://azureartifacts.microsoft.com/myTeam -n myTeam
  ```

## <a name="see-also"></a><span data-ttu-id="7572a-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="7572a-129">See also</span></span>

- [<span data-ttu-id="7572a-130">NuGet.config ファイルのパッケージ ソース セクション</span><span class="sxs-lookup"><span data-stu-id="7572a-130">Package source sections in NuGet.config files</span></span>](/nuget/reference/nuget-config-file#package-source-sections)

- [<span data-ttu-id="7572a-131">sources コマンド (nuget.exe)</span><span class="sxs-lookup"><span data-stu-id="7572a-131">sources command (nuget.exe)</span></span>](/nuget/reference/cli-reference/cli-ref-sources)
