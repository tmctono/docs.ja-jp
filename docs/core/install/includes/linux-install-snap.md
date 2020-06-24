---
ms.openlocfilehash: 5e77b7bd73c09e061a94a29703cf5286814d1ebb
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84602688"
---

[<span data-ttu-id="f89d2-101">.NET Core は、Snap Store から入手できます。</span><span class="sxs-lookup"><span data-stu-id="f89d2-101">.NET Core is available from the Snap Store.</span></span>](https://snapcraft.io/dotnet-sdk)

<span data-ttu-id="f89d2-102">Snap は、アプリとその依存関係のバンドルであり、さまざまな Linux ディストリビューション間で変更を加えることなく動作します。</span><span class="sxs-lookup"><span data-stu-id="f89d2-102">A snap is a bundle of an app and its dependencies that works without modification across many different Linux distributions.</span></span> <span data-ttu-id="f89d2-103">Snap は、Snap Store で見つけてインストールできます。</span><span class="sxs-lookup"><span data-stu-id="f89d2-103">Snaps are discoverable and installable from the Snap Store.</span></span> <span data-ttu-id="f89d2-104">Snap の詳細については、[Snap の概要](https://snapcraft.io/docs/getting-started)に関するページをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="f89d2-104">For more information about Snap, see [Getting started with Snap](https://snapcraft.io/docs/getting-started).</span></span>

<span data-ttu-id="f89d2-105">Snap では、サポートされているバージョンの .NET Core のみを利用できます。</span><span class="sxs-lookup"><span data-stu-id="f89d2-105">Only supported versions of .NET Core are available through Snap.</span></span>

### <a name="install-the-sdk"></a><span data-ttu-id="f89d2-106">SDK のインストール</span><span class="sxs-lookup"><span data-stu-id="f89d2-106">Install the SDK</span></span>

<span data-ttu-id="f89d2-107">.NET Core SDK の Snap パッケージは、すべて同じ識別子 (`dotnet-sdk`) で公開されます。</span><span class="sxs-lookup"><span data-stu-id="f89d2-107">Snap packages for .NET Core SDK are all published under the same identifier: `dotnet-sdk`.</span></span> <span data-ttu-id="f89d2-108">特定のバージョンの SDK は、チャネルを指定することによってインストールできます。</span><span class="sxs-lookup"><span data-stu-id="f89d2-108">A specific version of the SDK can be installed by specifying the channel.</span></span> <span data-ttu-id="f89d2-109">SDK には、対応するランタイムが含まれています。</span><span class="sxs-lookup"><span data-stu-id="f89d2-109">The SDK includes the coresponding runtime.</span></span> <span data-ttu-id="f89d2-110">次の表に、チャネルの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="f89d2-110">The following table list the channels:</span></span>

| <span data-ttu-id="f89d2-111">.NET Core バージョン</span><span class="sxs-lookup"><span data-stu-id="f89d2-111">.NET Core version</span></span> | <span data-ttu-id="f89d2-112">Snap パッケージ</span><span class="sxs-lookup"><span data-stu-id="f89d2-112">Snap package</span></span>             |
|-------------------|--------------------------|
| <span data-ttu-id="f89d2-113">3.1 (LTS)</span><span class="sxs-lookup"><span data-stu-id="f89d2-113">3.1 (LTS)</span></span>         | <span data-ttu-id="f89d2-114">`3.1` または `latest/stable`</span><span class="sxs-lookup"><span data-stu-id="f89d2-114">`3.1` or `latest/stable`</span></span> |
| <span data-ttu-id="f89d2-115">2.1 (LTS)</span><span class="sxs-lookup"><span data-stu-id="f89d2-115">2.1 (LTS)</span></span>         | `2.1`                    |
| <span data-ttu-id="f89d2-116">.NET 5.0 preview</span><span class="sxs-lookup"><span data-stu-id="f89d2-116">.NET 5.0 preview</span></span>  | `5.0/beta`               |

<span data-ttu-id="f89d2-117">`snap install` コマンドを使用して、.NET Core SDK の Snap パッケージをインストールします。</span><span class="sxs-lookup"><span data-stu-id="f89d2-117">Use the `snap install` command to install a .NET Core SDK snap package.</span></span> <span data-ttu-id="f89d2-118">`--channel` パラメーターを使用して、インストールするバージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="f89d2-118">Use the `--channel` parameter to indicate which version to install.</span></span> <span data-ttu-id="f89d2-119">このパラメーターを省略すると、`latest/stable` が使用されます。</span><span class="sxs-lookup"><span data-stu-id="f89d2-119">If this parameter is omitted, `latest/stable` is used.</span></span> <span data-ttu-id="f89d2-120">この例では、`3.1` が指定されています。</span><span class="sxs-lookup"><span data-stu-id="f89d2-120">In this example, `3.1` is specified:</span></span>

```bash
sudo snap install dotnet-sdk --classic --channel=3.1
```

<span data-ttu-id="f89d2-121">次に、`snap alias` コマンドを使用して、システムの `dotnet` コマンドを登録します。</span><span class="sxs-lookup"><span data-stu-id="f89d2-121">Next, register the `dotnet` command for the system with the `snap alias` command:</span></span>

```bash
sudo snap alias dotnet-sdk.dotnet dotnet
```

<span data-ttu-id="f89d2-122">このコマンドの形式は次のとおりです: `sudo snap alias {package}.{command} {alias}`。</span><span class="sxs-lookup"><span data-stu-id="f89d2-122">This command is formatted as: `sudo snap alias {package}.{command} {alias}`.</span></span> <span data-ttu-id="f89d2-123">`{alias}` の名前は自由に選択できます。</span><span class="sxs-lookup"><span data-stu-id="f89d2-123">You can choose any `{alias}` name you would like.</span></span> <span data-ttu-id="f89d2-124">たとえば、snap によってインストールされた特定のバージョンにちなんでコマンドの名前を指定できます: `sudo snap alias dotnet-sdk.dotnet dotnet31`。</span><span class="sxs-lookup"><span data-stu-id="f89d2-124">For example, you could name the command after the specific version installed by snap: `sudo snap alias dotnet-sdk.dotnet dotnet31`.</span></span> <span data-ttu-id="f89d2-125">コマンド `dotnet31` を使用すると、この特定のバージョンの .NET が呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="f89d2-125">When you use the command `dotnet31`, you'll invoke this specific version of .NET.</span></span> <span data-ttu-id="f89d2-126">ただし、これはチュートリアルや例のほとんどと互換性がありません。それらでは `dotnet` コマンドが使用可能であることが想定されているためです。</span><span class="sxs-lookup"><span data-stu-id="f89d2-126">But this is incompatible with most tutorials and examples as they expect a `dotnet` command to be available.</span></span>

### <a name="install-the-runtime"></a><span data-ttu-id="f89d2-127">ランタイムをインストールする</span><span class="sxs-lookup"><span data-stu-id="f89d2-127">Install the runtime</span></span>

<span data-ttu-id="f89d2-128">.NET Core ランタイムの Snap パッケージは、それぞれ独自のパッケージ識別子で公開されます。</span><span class="sxs-lookup"><span data-stu-id="f89d2-128">Snap packages for .NET Core Runtime are each published under their own package identifier.</span></span> <span data-ttu-id="f89d2-129">次の表に、パッケージ識別子の一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="f89d2-129">The following table lists the package identifiers:</span></span>

| <span data-ttu-id="f89d2-130">.NET Core バージョン</span><span class="sxs-lookup"><span data-stu-id="f89d2-130">.NET Core version</span></span> | <span data-ttu-id="f89d2-131">Snap パッケージ</span><span class="sxs-lookup"><span data-stu-id="f89d2-131">Snap package</span></span>        |
|-------------------|---------------------|
| <span data-ttu-id="f89d2-132">3.1 (LTS)</span><span class="sxs-lookup"><span data-stu-id="f89d2-132">3.1 (LTS)</span></span>         | `dotnet-runtime-31` |
| <span data-ttu-id="f89d2-133">3.0</span><span class="sxs-lookup"><span data-stu-id="f89d2-133">3.0</span></span>               | `dotnet-runtime-30` |
| <span data-ttu-id="f89d2-134">2.2</span><span class="sxs-lookup"><span data-stu-id="f89d2-134">2.2</span></span>               | `dotnet-runtime-22` |
| <span data-ttu-id="f89d2-135">2.1 (LTS)</span><span class="sxs-lookup"><span data-stu-id="f89d2-135">2.1 (LTS)</span></span>         | `dotnet-runtime-21` |

<span data-ttu-id="f89d2-136">`snap install` コマンドを使用して、.NET Core ランタイムの Snap パッケージをインストールします。</span><span class="sxs-lookup"><span data-stu-id="f89d2-136">Use the `snap install` command to install a .NET Core Runtime snap package.</span></span> <span data-ttu-id="f89d2-137">この例では、.NET Core 3.1 がインストールされます。</span><span class="sxs-lookup"><span data-stu-id="f89d2-137">In this example, .NET Core 3.1 is installed:</span></span>

```bash
sudo snap install dotnet-runtime-31 --classic
```

<span data-ttu-id="f89d2-138">次に、`snap alias` コマンドを使用して、システムの `dotnet` コマンドを登録します。</span><span class="sxs-lookup"><span data-stu-id="f89d2-138">Next, register the `dotnet` command for the system with the `snap alias` command:</span></span>

```bash
sudo snap alias dotnet-runtime-31.dotnet dotnet
```

<span data-ttu-id="f89d2-139">このコマンドの形式は次のとおりです: `sudo snap alias {package}.{command} {alias}`。</span><span class="sxs-lookup"><span data-stu-id="f89d2-139">This command is formatted as: `sudo snap alias {package}.{command} {alias}`.</span></span> <span data-ttu-id="f89d2-140">`{alias}` の名前は自由に選択できます。</span><span class="sxs-lookup"><span data-stu-id="f89d2-140">You can choose any `{alias}` name you would like.</span></span> <span data-ttu-id="f89d2-141">たとえば、snap によってインストールされた特定のバージョンにちなんでコマンドの名前を指定できます: `sudo snap alias dotnet-runtime-31.dotnet dotnet31`。</span><span class="sxs-lookup"><span data-stu-id="f89d2-141">For example, you could name the command after the specific version installed by snap: `sudo snap alias dotnet-runtime-31.dotnet dotnet31`.</span></span> <span data-ttu-id="f89d2-142">コマンド `dotnet31` を使用すると、この特定のバージョンの .NET が呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="f89d2-142">When you use the command `dotnet31`, you'll invoke this specific version of .NET.</span></span> <span data-ttu-id="f89d2-143">ただし、これはチュートリアルや例のほとんどと互換性がありません。それらでは `dotnet` コマンドが使用可能であることが想定されているためです。</span><span class="sxs-lookup"><span data-stu-id="f89d2-143">But this is incompatible with most tutorials and examples as they expect a `dotnet` command to be available.</span></span>

### <a name="ssl-certificate-errors"></a><span data-ttu-id="f89d2-144">SSL 証明書のエラー</span><span class="sxs-lookup"><span data-stu-id="f89d2-144">SSL Certificate errors</span></span>

<span data-ttu-id="f89d2-145">Snap を使用して .NET をインストールする場合、一部のディストリビューションでは .NET の SSL 証明書が見つからないことがあり、`restore` 中に次のようなエラーが表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="f89d2-145">When .NET is installed through Snap, it's possible that on some distros the .NET SSL certificates may not be found and you may receive an error similar to the following during `restore`:</span></span>

```bash
Processing post-creation actions...
Running 'dotnet restore' on /home/myhome/test/test.csproj...
  Restoring packages for /home/myhome/test/test.csproj...
/snap/dotnet-sdk/27/sdk/2.2.103/NuGet.targets(114,5): error : Unable to load the service index for source https://api.nuget.org/v3/index.json. [/home/myhome/test/test.csproj]
/snap/dotnet-sdk/27/sdk/2.2.103/NuGet.targets(114,5): error :   The SSL connection could not be established, see inner exception. [/home/myhome/test/test.csproj]
/snap/dotnet-sdk/27/sdk/2.2.103/NuGet.targets(114,5): error :   The remote certificate is invalid according to the validation procedure. [/home/myhome/test/test.csproj]
```

<span data-ttu-id="f89d2-146">この問題を解決するには、いくつかの環境変数を設定します。</span><span class="sxs-lookup"><span data-stu-id="f89d2-146">To resolve this issue, set a few enviornment variables:</span></span>

```bash
export SSL_CERT_FILE=[path-to-certificate-file]
export SSL_CERT_DIR=/dev/null
```

<span data-ttu-id="f89d2-147">証明書の場所は、ディストリビューションによって異なります。</span><span class="sxs-lookup"><span data-stu-id="f89d2-147">The certificate location will vary by distro.</span></span> <span data-ttu-id="f89d2-148">次に、問題が発生したディストリビューションの場所を示します。</span><span class="sxs-lookup"><span data-stu-id="f89d2-148">Here are the locations for the distros where we have experienced the issue.</span></span>

* <span data-ttu-id="f89d2-149">Fedora - `/etc/pki/ca-trust/extracted/pem/tls-ca-bundle.pem`</span><span class="sxs-lookup"><span data-stu-id="f89d2-149">Fedora - `/etc/pki/ca-trust/extracted/pem/tls-ca-bundle.pem`</span></span>
* <span data-ttu-id="f89d2-150">OpenSUSE - `/etc/ssl/ca-bundle.pem`</span><span class="sxs-lookup"><span data-stu-id="f89d2-150">OpenSUSE - `/etc/ssl/ca-bundle.pem`</span></span>
* <span data-ttu-id="f89d2-151">Solus - `/etc/ssl/certs/ca-certificates.crt`</span><span class="sxs-lookup"><span data-stu-id="f89d2-151">Solus - `/etc/ssl/certs/ca-certificates.crt`</span></span>
