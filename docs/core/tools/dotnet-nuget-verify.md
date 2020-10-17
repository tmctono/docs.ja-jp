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
# <a name="dotnet-nuget-verify"></a>dotnet nuget verify

**この記事の対象:** ✔️ .NET 5.0.100-rc.2.x SDK 以降のバージョン

## <a name="name"></a>名前

`dotnet nuget verify` - 署名済みの NuGet パッケージを検証します。

## <a name="synopsis"></a>構文

```dotnetcli
dotnet nuget verify [<package-path(s)>]
    [--all]
    [--certificate-fingerprint <FINGERPRINT>]
    [-v|--verbosity <LEVEL>]

dotnet nuget verify -h|--help
```

## <a name="description"></a>説明

`dotnet nuget verify` コマンドによって、署名済みの NuGet パッケージが検証されます。

## <a name="arguments"></a>引数

- **`package-path(s)`**

  検証されるパッケージのファイル パスを指定します。 複数のパッケージを検証するために、複数の位置引数を渡すことができます。

## <a name="options"></a>オプション

- **`--all`**

  可能なすべての検証をパッケージに対して実行する必要があることを指定します。 既定では、`signatures` のみ検証されます。

> [!NOTE]
> このコマンドで現在サポートされているのは、`signature` 検証のみとなります。

- **`--certificate-fingerprint <FINGERPRINT>`**

  署名者の証明書が、指定されたいずれかの `SHA256` 指紋と一致していることを検証します。 このオプションを複数回指定することで複数のフィンガープリントを提供できます。

* **`-v|--verbosity <LEVEL>`**

  MSBuild の詳細レベルを設定します。 指定できる値は、`q[uiet]`、`m[inimal]`、`n[ormal]`、`d[etailed]`、および `diag[nostic]` です。 既定値は、`normal` です。

* **`-h|--help`**

  コマンドの短いヘルプを印刷します。

## <a name="examples"></a>使用例

- *foo.nupkg* を検証します。

  ```dotnetcli
  dotnet nuget verify foo.nupkg
  ```

- 複数の NuGet パッケージを検証します - *foo. nupkg* および "*指定されたディレクトリ内のすべての .nupkg ファイル*"。

  ```dotnetcli
  dotnet nuget verify foo.nupkg c:\mydir\*.nupkg
  ```

- *foo. nupkg* の署名が、指定された証明書のフィンガープリントと一致していることを検証します。

  ```dotnetcli
  dotnet nuget verify foo.nupkg --certificate-fingerprint CE40881FF5F0AD3E58965DA20A9F571EF1651A56933748E1BF1C99E537C4E039
  ```

- *foo. nupkg* の署名が、指定された証明書のフィンガープリントのいずれかと一致していることを検証します。

  ```dotnetcli
  dotnet nuget verify foo.nupkg --certificate-fingerprint CE40881FF5F0AD3E58965DA20A9F571EF1651A56933748E1BF1C99E537C4E039 --certificate-fingerprint EC10992GG5F0AD3E58965DA20A9F571EF1651A56933748E1BF1C99E537C4E027
  ```
