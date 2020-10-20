---
title: F# をインストールする
description: 'さまざまな方法で F # をインストールする方法について説明します。'
ms.date: 12/20/2019
ms.openlocfilehash: 302e04f7cf3271516dff88d9d5f18f620b6ede80
ms.sourcegitcommit: 67ebdb695fd017d79d9f1f7f35d145042d5a37f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/20/2020
ms.locfileid: "92224282"
---
# <a name="install-f"></a>F のインストール\#

F # は、環境に応じて複数の方法でインストールできます。

## <a name="install-f-with-visual-studio"></a>Visual Studio を使用して F # をインストールする

1. [Visual Studio](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019)を初めてダウンロードする場合は、最初に Visual Studio インストーラーをインストールします。 インストーラーから適切なエディションの Visual Studio をインストールします。

   Visual Studio が既にインストールされている場合は、F # を追加するエディションの横にある [ **変更** ] を選択します。

2. [ワークロード] ページで、 **ASP.NET および web 開発** ワークロードを選択します。これには ASP.NET Core プロジェクトの F # と .net Core のサポートが含まれます。

3. 右下隅にある [ **変更** ] を選択して、選択したすべてのものをインストールします。

   その後、[Visual Studio インストーラーで **起動** ] を選択すると、F # を使用して Visual Studio を開くことができます。

## <a name="install-f-with-visual-studio-code"></a>Visual Studio Code を使用して F # をインストールする

1. [Git](https://git-scm.com/download)がインストールされ、パスに使用できることを確認します。 `git --version`コマンドプロンプトで「 **」** と入力し、enter キーを押すと、正しくインストールされていることを確認できます。

2. [.NET Core SDK](https://dotnet.microsoft.com/download)と[Visual Studio Code](https://code.visualstudio.com)をインストールします。

3. 拡張機能のアイコンを選択し、"Ionide" を検索します。

   Visual Studio Code で F # をサポートするために必要なプラグインは、 [Ionide fsharp.core](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp)だけです。 ただし、Ionide をインストールして、[偽](https://fake.build/)[の](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-FAKE)サポートと[Ionide](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-Paket)を取得し、[パケット](https://fsprojects.github.io/Paket/)のサポートを取得することもできます。 フェイクとパケットは、プロジェクトをビルドし、依存関係を管理するための追加の F # コミュニティツールです。

## <a name="install-f-with-visual-studio-for-mac"></a>Visual Studio for Mac を使用して F # をインストールする

F # は、選択した構成に関係なく、既定で [Visual Studio for Mac](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link)にインストールされます。

インストールが完了したら、[ **Visual Studio の開始**] を選択します。 MacOS で Finder を使用して Visual Studio を開くこともできます。

## <a name="install-f-on-a-build-server"></a>ビルドサーバーに F # をインストールする

.Net Core または .net SDK を使用して .NET Framework を使用している場合は、単に .NET SDK をビルドサーバーにインストールする必要があります。 必要なものがすべて揃っています。

.NET Framework を使用していて、.NET SDK を使用して **いない** 場合は、 [Visual Studio Build Tools SKU](https://visualstudio.microsoft.com/thank-you-downloading-visual-studio/?sku=BuildTools&rel=16) を Windows Server にインストールする必要があります。 インストーラーで、[ **.net デスクトップビルドツール**] を選択し、インストーラーメニューの右側にある **F # コンパイラ** コンポーネントを選択します。
