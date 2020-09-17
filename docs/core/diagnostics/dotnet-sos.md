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
# <a name="sos-installer-dotnet-sos"></a>SOS インストーラー (dotnet-sos)

**この記事の対象:** ✔️ .NET Core 2.1 SDK 以降のバージョン

## <a name="install-dotnet-sos"></a>dotnet-sos をインストールする

`dotnet-sos` [NuGet パッケージ](https://www.nuget.org/packages/dotnet-sos)の最新のリリース バージョンをインストールするには、次のように [dotnet tool install](../tools/dotnet-tool-install.md) コマンドを使用します。

```dotnetcli
dotnet tool install -g dotnet-sos
```

## <a name="synopsis"></a>構文

```console
dotnet-sos [-h|--help] [options] [command]]
```

## <a name="description"></a>説明

`dotnet-sos` グローバル ツールによって、[SOS デバッガー拡張機能](../../framework/tools/sos-dll-sos-debugging-extension.md)がインストールされます。これにより、Windows 上の WinDbg または cdb、Linux および macOS 上の lldb などのネイティブ デバッガーから[マネージド .NET Core 状態を検査](https://github.com/dotnet/diagnostics/blob/master/documentation/sos-debugging-extension.md)できるようになります。 最新バージョンの Windows デバッガー (WinDbg または cdb のバージョン 10.0.18317.1001 以降) では、Microsoft 拡張機能ギャラリーから SOS が自動的に読み込まれます。そのため、`dotnet-sos` ツールを使用して SOS をインストールする必要があるのは、Linux および macOS の場合、または古いデバッグ ツールを使用している場合のみとなります。

## <a name="options"></a>オプション

- **`--version`**

  バージョン情報を表示します。

- **`-h|--help`**

  コマンド ライン ヘルプを表示します。

## <a name="dotnet-sos-install"></a>dotnet-sos install

.NET Core プロセスをデバッグするために、[SOS 拡張機能](../../framework/tools/sos-dll-sos-debugging-extension.md)をローカルにインストールします。 macOS および Linux では、lldb の起動時に拡張機能が自動的に読み込まれるように、.lldbinit ファイルが更新されます。 古いデバッグ ツール (バージョン 10.0.18317.1001 より前) を使用して Windows に SOS をインストールする場合は、WinDbg または cdb で `.load %USERPROFILE%\.dotnet\sos\sos.dll` を実行して、デバッガーで拡張機能を手動で読み込む必要があります。

### <a name="synopsis"></a>構文

```console
dotnet-sos install
```

## <a name="dotnet-sos-uninstall"></a>dotnet-sos uninstall

[SOS 拡張機能](../../framework/tools/sos-dll-sos-debugging-extension.md)をアンインストールします。Linux または macOS の場合は、lldb 構成から削除します。

### <a name="synopsis"></a>構文

```console
dotnet-sos uninstall
```
