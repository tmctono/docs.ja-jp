---
title: dotnet nuget disable source コマンド
description: dotnet nuget disable source コマンドを使うと、NuGet 構成ファイルの既存のソースを無効にできます。
ms.date: 03/20/2020
ms.openlocfilehash: af37a6589cebaf0501ee5647ebadb83125d0f56e
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/15/2020
ms.locfileid: "90537952"
---
# <a name="dotnet-nuget-disable-source"></a>dotnet nuget disable source

**この記事の対象:** ✔️ .NET Core 3.1.200 SDK 以降のバージョン

## <a name="name"></a>名前

`dotnet nuget disable source` - NuGet ソースを無効にします。

## <a name="synopsis"></a>構文

```dotnetcli
dotnet nuget disable source <NAME> [--configfile <FILE>]

dotnet nuget disable source -h|--help
```

## <a name="description"></a>説明

`dotnet nuget disable source` コマンドを使うと、NuGet 構成ファイルの既存のソースを無効にできます。

## <a name="arguments"></a>引数

- **`NAME`**

  ソースの名前。

## <a name="options"></a>オプション

- **`--configfile <FILE>`**

  NuGet 構成ファイル。 指定した場合、このファイルの設定のみが使用されます。 指定しない場合、現在のディレクトリからの構成ファイルの階層が使用されます。 詳細については、「[一般的な NuGet 構成](/nuget/consume-packages/configuring-nuget-behavior)」をご覧ください。

## <a name="examples"></a>使用例

- `mySource` という名前のソースを無効にします。

  ```dotnetcli
  dotnet nuget disable source mySource
  ```

## <a name="see-also"></a>関連項目

- [NuGet.config ファイルのパッケージ ソース セクション](/nuget/reference/nuget-config-file#package-source-sections)

- [sources コマンド (nuget.exe)](/nuget/reference/cli-reference/cli-ref-sources)
