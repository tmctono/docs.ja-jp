---
title: dotnet-sos - .NET Core
description: dotnet-sos コマンドライン ツールをインストールして使用する方法について説明します。
ms.date: 08/26/2020
ms.openlocfilehash: ba83105718909038ca56129ed8a5063aeff12e89
ms.sourcegitcommit: a69d548f90a03e105ee6701236c38390ecd9ccd1
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/14/2020
ms.locfileid: "90065085"
---
# <a name="sos-installer-dotnet-sos"></a><span data-ttu-id="a4127-103">SOS インストーラー (dotnet-sos)</span><span class="sxs-lookup"><span data-stu-id="a4127-103">SOS installer (dotnet-sos)</span></span>

<span data-ttu-id="a4127-104">**この記事の対象:** ✔️ .NET Core 2.1 SDK 以降のバージョン</span><span class="sxs-lookup"><span data-stu-id="a4127-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

## <a name="install-dotnet-sos"></a><span data-ttu-id="a4127-105">dotnet-sos をインストールする</span><span class="sxs-lookup"><span data-stu-id="a4127-105">Install dotnet-sos</span></span>

<span data-ttu-id="a4127-106">`dotnet-sos` [NuGet パッケージ](https://www.nuget.org/packages/dotnet-sos)の最新のリリース バージョンをインストールするには、次のように [dotnet tool install](../tools/dotnet-tool-install.md) コマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="a4127-106">To install the latest release version of the `dotnet-sos` [NuGet package](https://www.nuget.org/packages/dotnet-sos), use the [dotnet tool install](../tools/dotnet-tool-install.md) command:</span></span>

```dotnetcli
dotnet tool install -g dotnet-sos
```

## <a name="synopsis"></a><span data-ttu-id="a4127-107">構文</span><span class="sxs-lookup"><span data-stu-id="a4127-107">Synopsis</span></span>

```console
dotnet-sos [-h|--help] [options] [command]]
```

## <a name="description"></a><span data-ttu-id="a4127-108">説明</span><span class="sxs-lookup"><span data-stu-id="a4127-108">Description</span></span>

<span data-ttu-id="a4127-109">`dotnet-sos` グローバル ツールによって、[SOS デバッガー拡張機能](../../framework/tools/sos-dll-sos-debugging-extension.md)がインストールされます。これにより、Windows 上の WinDbg または cdb、Linux および macOS 上の lldb などのネイティブ デバッガーから[マネージド .NET Core 状態を検査](https://github.com/dotnet/diagnostics/blob/master/documentation/sos-debugging-extension.md)できるようになります。</span><span class="sxs-lookup"><span data-stu-id="a4127-109">The `dotnet-sos` global tool installs the [SOS debugger extension](../../framework/tools/sos-dll-sos-debugging-extension.md) allowing [inspection of managed .NET Core state](https://github.com/dotnet/diagnostics/blob/master/documentation/sos-debugging-extension.md) from native debuggers like WinDbg/cdb on Windows and lldb on Linux and macOS.</span></span> <span data-ttu-id="a4127-110">最新バージョンの Windows デバッガー (WinDbg または cdb のバージョン 10.0.18317.1001 以降) では、Microsoft 拡張機能ギャラリーから SOS が自動的に読み込まれます。そのため、`dotnet-sos` ツールを使用して SOS をインストールする必要があるのは、Linux および macOS の場合、または古いデバッグ ツールを使用している場合のみとなります。</span><span class="sxs-lookup"><span data-stu-id="a4127-110">Recent versions of the Windows Debugger (>= version 10.0.18317.1001 of WinDbg or cdb) will load SOS automatically from the Microsoft extension gallery, so installing SOS via the `dotnet-sos` tool is only needed on Linux and macOS or on Windows if using older debugging tools.</span></span>

## <a name="options"></a><span data-ttu-id="a4127-111">オプション</span><span class="sxs-lookup"><span data-stu-id="a4127-111">Options</span></span>

- **`--version`**

  <span data-ttu-id="a4127-112">バージョン情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="a4127-112">Displays version information.</span></span>

- **`-h|--help`**

  <span data-ttu-id="a4127-113">コマンド ライン ヘルプを表示します。</span><span class="sxs-lookup"><span data-stu-id="a4127-113">Shows command-line help.</span></span>

## <a name="dotnet-sos-install"></a><span data-ttu-id="a4127-114">dotnet-sos install</span><span class="sxs-lookup"><span data-stu-id="a4127-114">dotnet-sos install</span></span>

<span data-ttu-id="a4127-115">.NET Core プロセスをデバッグするために、[SOS 拡張機能](../../framework/tools/sos-dll-sos-debugging-extension.md)をローカルにインストールします。</span><span class="sxs-lookup"><span data-stu-id="a4127-115">Installs the [SOS extension](../../framework/tools/sos-dll-sos-debugging-extension.md) locally for debugging .NET Core processes.</span></span> <span data-ttu-id="a4127-116">macOS および Linux では、lldb の起動時に拡張機能が自動的に読み込まれるように、.lldbinit ファイルが更新されます。</span><span class="sxs-lookup"><span data-stu-id="a4127-116">On macOS and Linux, the .lldbinit file will be updated so that the extension automatically loads at lldb startup.</span></span> <span data-ttu-id="a4127-117">古いデバッグ ツール (バージョン 10.0.18317.1001 より前) を使用して Windows に SOS をインストールする場合は、WinDbg または cdb で `.load %USERPROFILE%\.dotnet\sos\sos.dll` を実行して、デバッガーで拡張機能を手動で読み込む必要があります。</span><span class="sxs-lookup"><span data-stu-id="a4127-117">If installing SOS on Windows with older debugging tools (< version 10.0.18317.1001), you will need to manually load the extension in WinDbg or cdb by running `.load %USERPROFILE%\.dotnet\sos\sos.dll` in the debugger.</span></span>

### <a name="synopsis"></a><span data-ttu-id="a4127-118">構文</span><span class="sxs-lookup"><span data-stu-id="a4127-118">Synopsis</span></span>

```console
dotnet-sos install
```

## <a name="dotnet-sos-uninstall"></a><span data-ttu-id="a4127-119">dotnet-sos uninstall</span><span class="sxs-lookup"><span data-stu-id="a4127-119">dotnet-sos uninstall</span></span>

<span data-ttu-id="a4127-120">[SOS 拡張機能](../../framework/tools/sos-dll-sos-debugging-extension.md)をアンインストールします。Linux または macOS の場合は、lldb 構成から削除します。</span><span class="sxs-lookup"><span data-stu-id="a4127-120">Uninstalls the [SOS extension](../../framework/tools/sos-dll-sos-debugging-extension.md) and, if on Linux or macOS, removes it from lldb configuration.</span></span>

### <a name="synopsis"></a><span data-ttu-id="a4127-121">構文</span><span class="sxs-lookup"><span data-stu-id="a4127-121">Synopsis</span></span>

```console
dotnet-sos uninstall
```
