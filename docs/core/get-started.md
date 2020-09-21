---
title: .NET Core の概要
description: Windows、Linux、macOS で .NET Core アプリケーションをビルドする方法を学習するためのリソースを示します。
author: adegeo
ms.author: adegeo
ms.date: 12/03/2019
ms.custom: vs-dotnet
ms.openlocfilehash: 6106f66dfbbe382ee9f61eb8b7bda70ab9b72d0b
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/15/2020
ms.locfileid: "90538550"
---
# <a name="get-started-with-net-core"></a>.NET Core の概要

この記事では、.NET Core の概要について説明します。 .NET Core は、Windows、Linux、および macOS にインストールすることができます。 任意のテキスト エディターでコーディングし、クロスプラットフォーム ライブラリとアプリケーションを作成できます。

.NET Core が何であるか、またはこれが他の .NET テクノロジとどのように関連しているのかわからない場合は、まず、[.NET の概要](https://dotnet.microsoft.com/learn/dotnet/what-is-dotnet)を確認してください。 簡単に言うと、.NET Core は .NET のオープンソースのクロスプラットフォーム実装です。

## <a name="create-an-application"></a>アプリケーションの作成

まず、ご利用のコンピューターで [NET Core SDK](https://dotnet.microsoft.com/download) をダウンロードしてインストールします。

次に、**PowerShell**、**コマンド プロンプト**、**bash** などのターミナルを開きます。 次の `dotnet` コマンドを入力し、C# アプリケーションを作成して実行します。

```dotnetcli
dotnet new console --output sample1
dotnet run --project sample1
```

次の出力が表示されます。

```console
Hello World!
```

おめでとうございます! シンプルな .NET Core アプリケーションが作成されました。 [Visual Studio Code](./tutorials/with-visual-studio-code.md)、[Visual Studio](./tutorials/with-visual-studio.md) (Windows のみ)、または [Visual Studio for Mac](tutorials/with-visual-studio-mac.md) (macOS のみ) を使用して、.NET Core アプリケーションを作成することもできます。

## <a name="tutorials"></a>チュートリアル

次のステップ バイ ステップのチュートリアルに従って、.NET Core アプリケーションの開発を開始します。

<!-- markdownlint-disable MD025 -->

# <a name="windows"></a>[Windows](#tab/windows)

- [Visual Studio 2019 で最初の .NET Core コンソール アプリケーションを作成する](./tutorials/with-visual-studio.md)
- [Visual Studio で .NET Standard を使用してクラス ライブラリを構築する](./tutorials/library-with-visual-studio.md)
- [チュートリアル: Visual Studio Code を使用して .NET Core コンソール アプリを作成する](tutorials/with-visual-studio-code.md)

|   |   |
|---|---|
| ![ビデオのムービー カメラ アイコン](./media/video-icon.png "ビデオを見る") | Channel 9 で [Visual Studio Code と .NET Core をインストールして使用する方法](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-using-CSharp-and-NET-Core/)についてのビデオを見る。 |
| ![ビデオのムービー カメラ アイコン](./media/video-icon.png "ビデオを見る") | YouTube で [.NET Core 101](https://www.youtube.com/playlist?list=PLdo4fOcmZ0oWoazjhXQzBKMrFuArxpW80) に関するビデオを見る。 |

サポートされている Windows バージョンの一覧については、[.NET Core の依存関係と要件](./install/windows.md)に関する記事を参加してください。

# <a name="linux"></a>[Linux](#tab/linux)

次のステップ バイ ステップのチュートリアルに従って、.NET Core アプリケーションの開発を開始します。

- [チュートリアル: Visual Studio Code を使用して .NET Core コンソール アプリを作成する](tutorials/with-visual-studio-code.md)

|   |   |
|---|---|
| ![ビデオのムービー カメラ アイコン](./media/video-icon.png "ビデオを見る") | [Ubuntu 上の Visual Studio Code での C# と .NET Core の使用に関する概要](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-Csharp-dotnet-Core-Ubuntu)のビデオを見る。 |

サポートされている Linux のディストリビューションとバージョンの一覧については、[.NET Core の依存関係と要件](./install/linux.md)に関する記事を参加してください。

# <a name="macos"></a>[macOS](#tab/macos)

次のステップ バイ ステップのチュートリアルに従って、.NET Core アプリケーションの開発を開始します。

- [チュートリアル: Visual Studio Code を使用して .NET Core コンソール アプリケーションを作成する](tutorials/with-visual-studio-code.md)
- [チュートリアル: Visual Studio for Mac を使用して .NET Core コンソール アプリケーションを作成する](tutorials/with-visual-studio-mac.md)
- [Visual Studio for Mac を使用して macOS で .NET Standard ライブラリを構築する](tutorials/library-with-visual-studio-mac.md)

|   |   |
|---|---|
| ![ビデオのムービー カメラ アイコン](media/video-icon.png "ビデオを見る") | [macOS 上の Visual Studio Code での C# と .NET Core の使用に関する概要](https://channel9.msdn.com/Blogs/dotnet/Get-started-VSCode-NET-Core-Mac)のビデオを見る。 |

サポートされている OS X / macOS バージョンの一覧については、[.NET Core の依存関係と要件](./install/macos.md)に関する記事を参加してください。

---
