---
title: DockerFile で Windows PowerShell コマンドを使用して Windows コンテナー (Docker 標準ベース) を設定する
description: Windows コンテナーで Docker を操作する場合の PowerShell の使用方法について説明します
ms.date: 08/06/2020
ms.openlocfilehash: 4e7b9e7fedf11b97b3f468aef541bf72a4e88ebc
ms.sourcegitcommit: ef50c99928183a0bba75e07b9f22895cd4c480f8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2020
ms.locfileid: "87915390"
---
# <a name="using-windows-powershell-commands-in-a-dockerfile-to-set-up-windows-containers-docker-standard-based"></a>DockerFile で Windows PowerShell コマンドを使用して Windows コンテナー (Docker 標準ベース) を設定する

[Windows コンテナー](/virtualization/windowscontainers/about/index)によって、既存の Windows アプリケーションを Docker イメージに変換して、その他の Docker エコシステムと同じツールでそれらをデプロイできます。

Windows コンテナーを使用するには、次の例に示すように、DockerFile で PowerShell コマンドを記述するだけです。

```Dockerfile
FROM microsoft/windowsservercore
LABEL Description="IIS" Vendor="Microsoft" Version="10"
RUN powershell -Command Add-WindowsFeature Web-Server
CMD [ "ping", "localhost", "-t" ]
```

この例では、Windows PowerShell を使用して、Windows Server Core 基本イメージと IIS をインストールしています。

同様に、Windows PowerShell コマンドを使用して、次に示すように、従来の ASP.NET 4.x および .NET 4.6、またはその他の任意の Windows ソフトウェアなどの追加コンポーネントを設定することもできます。

```Dockerfile
RUN powershell add-windowsfeature web-asp-net45
```

>[!div class="step-by-step"]
>[前へ](visual-studio-tools-for-docker.md)
>[次へ](build-aspnet-core-applications-linux-containers-aks-kubernetes.md)
