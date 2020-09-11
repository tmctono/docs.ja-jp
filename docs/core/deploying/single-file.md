---
title: 単一ファイル アプリケーション
description: 単一ファイル アプリケーションの概要、およびこのアプリケーション デプロイ モデルの使用を検討すべき理由について説明します。
author: lakshanf
ms.author: lakshanf
ms.date: 08/28/2020
ms.openlocfilehash: 795ea98a9fd9d672b199eb2d9b24151340ef8246
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2020
ms.locfileid: "89495748"
---
# <a name="single-file-deployment-and-executable"></a>単一ファイルの配置と実行可能ファイル

アプリケーションに依存するすべてのファイルを単一のバイナリにバンドルすることで、アプリケーション開発者は、アプリケーションを単一ファイルとして配置し、配布することができます。 このデプロイ モデルは、.NET Core 3.0 以降で利用可能であり、.NET 5.0 で拡張されています。 以前の .NET Core 3.0 では、ユーザーが単一ファイル アプリを実行する場合、そのアプリケーションが実行される前に、まず .NET Core ホストがすべてのファイルを一時ディレクトリに抽出します。 .NET 5.0 では、アプリからファイルを抽出する必要がなく、コードを直接実行するので、このエクスペリエンスが向上しています。

[フレームワークに依存するデプロイ モデル](index.md#publish-framework-dependent)と[自己完結型アプリケーション](index.md#publish-self-contained)の両方で、単一ファイルの配置が可能です。 自己完結型アプリケーション内にある単一ファイルは、ランタイム ライブラリとフレームワーク ライブラリが含まれるため、大きなサイズとなります。 単一ファイル配置オプションは、[ReadyToRun](../tools/dotnet-publish.md) と [Trim (.NET 5.0 の試験的な機能)](trim-self-contained.md) の各発行オプションと組み合わせることができます。

単一ファイルを使用する場合に把握しておくべきいくつかの注意事項があります。1 つめは、アプリケーションの場所を基準としてファイルを検索するときのパス情報の使用です。 <xref:System.Reflection.Assembly.Location?displayProperty=nameWithType> API は、空の文字列を返します。これは、メモリから読み込まれたアセンブリの既定の動作です。 コンパイラは、ビルド時にこの API に対する警告を表示し、特定の動作について開発者に注意を促します。 アプリケーション ディレクトリへのパスが必要な場合、<xref:System.AppContext.BaseDirectory?displayProperty=nameWithType> API は AppHost (単一ファイル バンドル自体) が存在するディレクトリを返します。 マネージド C++ アプリケーションは、単一ファイルの配置には適していません。単一ファイルとの互換性を確保するには、アプリケーションを C# で記述することをお勧めします。

既定では、単一ファイルを使用してネイティブ ライブラリをバンドルすることができません。 Linux では、ランタイム ライブラリをバンドルに事前にリンクして、アプリケーション ネイティブ ライブラリのみを単一ファイル アプリと同じディレクトリに配置します。 Windows では、ホスト コードのみを事前にリンクして、ランタイム ライブラリとアプリケーション ネイティブ ライブラリの両方を単一ファイル アプリと同じディレクトリに配置します。 これにより、優れたデバッグ エクスペリエンスが確保されます。それには、ネイティブ ファイルを単一ファイルから除外する必要があります。 単一ファイル バンドルにネイティブ ライブラリを含めるようにフラグ `IncludeNativeLibrariesForSelfExtract` を設定するオプションがありますが、これらのファイルは、単一ファイル アプリケーションが実行されるときに、クライアント コンピューターの一時ディレクトリに抽出されます。

## <a name="exclude-files-from-being-embedded"></a>ファイルを埋め込み対象から除外する

次のメタデータを設定すると、特定のファイルを単一ファイルの埋め込み対象から明示的に除外することができます。

```xml
<ExcludeFromSingleFile>true</ExcludeFromSingleFile>
```

たとえば、いくつかのファイルを発行ディレクトリに配置するものの、単一ファイルへのバンドルは行わない場合などです。

```xml
<ItemGroup>
  <Content Update="Plugin.dll">
    <CopyToPublishDirectory>PreserveNewest</CopyToPublishDirectory>
    <ExcludeFromSingleFile>true</ExcludeFromSingleFile>
  </Content>
</ItemGroup>
```

## <a name="publish-a-single-file-app---cli"></a>単一ファイル アプリを発行する - CLI

[dotnet publish](../tools/dotnet-publish.md) コマンドを使用して、単一ファイル アプリケーションを発行します。 アプリを発行する場合、次のプロパティを設定します。

- 特定のランタイムに対して発行する: `-r win-x64`
- 単一ファイルとして発行する: `-p:PublishSingleFile=true`

次の例では、Windows 用のアプリを自己完結型の単一ファイル アプリケーションとして発行します。

```dotnetcli
dotnet publish -r win-x64 -p:PublishSingleFile=true --self-contained true
```

次の例では、Linux 用のアプリをフレームワークに依存する単一ファイル アプリケーションとして発行します。

```dotnetcli
dotnet publish -r linux-x64 -p:PublishSingleFile=true --self-contained false
```

詳細については、「[.NET Core CLI を使用して .NET Core アプリを発行する](deploy-with-cli.md)」を参照してください。

## <a name="publish-a-single-file-app---visual-studio"></a>単一ファイル アプリを発行する - Visual Studio

Visual Studio を使用すると、アプリケーションの発行方法を制御する再利用可能な発行プロファイルを作成できます。

01. **[ソリューション エクスプローラー]** ペインで、発行するプロジェクトを右クリックします。 **[発行]** を選択します。

    :::image type="content" source="media/single-file/visual-studio-solution-explorer.png" alt-text="右クリック メニューの [発行] オプションが強調表示されたソリューション エクスプローラー。":::

    発行プロファイルがまだない場合は、指示に従って作成し、ターゲットの種類として **[フォルダー]** を選択します。

01. **[編集]** を選択します。

    :::image type="content" source="media/single-file/visual-studio-publish-edit-settings.png" alt-text="Visual Studio の発行プロファイルと [編集] ボタン":::

01. **[プロファイル設定]** ダイアログで、次のオプションを設定します。

    - **[配置モード]** を **[自己完結]** に設定します。
    - **[ターゲット ランタイム]** を発行先のプラットフォームに設定します。
    - **[単一ファイルの作成]** を選択します。

    **[保存]** を選択して設定を保存し、 **[発行]** ダイアログに戻ります。

    :::image type="content" source="media/single-file/visual-studio-publish-single-file-properties.png" alt-text="[配置モード]、[ターゲット ランタイム]、[単一ファイルの作成] の各オプションが強調表示されている [プロファイル設定] ダイアログ。":::

01. **[発行]** を選択して、アプリを単一ファイルとして発行します。

詳細については、[Visual Studio を使用した .NET Core アプリの発行](deploy-with-vs.md)に関するページを参照してください。

## <a name="publish-a-single-file-app---visual-studio-for-mac"></a>単一ファイル アプリを発行する - Visual Studio for Mac

Visual Studio for Mac には、アプリを単一ファイルとして発行するためのオプションがありません。 「[単一ファイル アプリを発行する - CLI](#publish-a-single-file-app---cli)」セクションの手順に従って、手動で発行する必要があります。 詳細については、「[.NET Core CLI を使用して .NET Core アプリを発行する](deploy-with-cli.md)」を参照してください。

## <a name="see-also"></a>関連項目

- [.NET Core アプリケーションの配置](index.md)。
- [.NET Core CLI を使用して .NET Core アプリを発行する](deploy-with-cli.md)。
- [Visual Studio を使用して .NET Core アプリを発行する](deploy-with-vs.md)。
- [`dotnet publish` コマンド](../tools/dotnet-publish.md)。
