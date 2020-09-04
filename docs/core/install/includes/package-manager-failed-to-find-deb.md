---
ms.openlocfilehash: 9d4c031eda291b0a8832c824789efdffe4084926
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/30/2020
ms.locfileid: "89132946"
---

"**パッケージ {netcore-package} が見つかりません**" や "**一部のパッケージをインストールできませんでした**" のようなエラー メッセージが表示される場合は、次のコマンドを実行します。

次の一連のコマンドには、2 つのプレースホルダーがあります。

- `{dotnet-package}`\
これは、`aspnetcore-runtime-3.1` など、インストールする .NET Core パッケージを表します。 これは、次の `sudo apt-get install` コマンドで使用されます。

- `{os-version}`\
これは、使用している Linux のバージョンを表します。 これは、次の `wget` コマンドで使用されます。

まず、パッケージ リストを消去してみてください。

```bash
sudo dpkg --purge packages-microsoft-prod && sudo dpkg -i packages-microsoft-prod.deb
sudo apt-get update
```

次に、.NET Core を再度インストールしてください。 それでも解決しない場合は、次のコマンドを使用して手動インストールを実行できます。
