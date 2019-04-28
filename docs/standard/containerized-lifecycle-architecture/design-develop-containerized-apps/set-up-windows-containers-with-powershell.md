---
title: DockerFile で Windows PowerShell コマンドを使用して Windows コンテナー (Docker 標準ベース) を設定するには
description: Windows コンテナーで Docker を使用する場合は、PowerShell を使用する方法について説明します
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 02/15/2019
ms.openlocfilehash: d9c0bc28f62d44eb7471b99c63055ef43da12a69
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61644646"
---
# <a name="using-windows-powershell-commands-in-a-dockerfile-to-set-up-windows-containers-docker-standard-based"></a><span data-ttu-id="db99e-103">DockerFile で Windows PowerShell コマンドを使用して Windows コンテナー (Docker 標準ベース) を設定するには</span><span class="sxs-lookup"><span data-stu-id="db99e-103">Using Windows PowerShell commands in a DockerFile to set up Windows Containers (Docker standard based)</span></span>

<span data-ttu-id="db99e-104">[Windows コンテナー](/virtualization/windowscontainers/about/index)、Docker イメージを既存の Windows アプリケーションを変換し、Docker エコシステムの残りの部分と同じツールで展開したりできます。</span><span class="sxs-lookup"><span data-stu-id="db99e-104">With [Windows Containers](/virtualization/windowscontainers/about/index), you can convert your existing Windows applications to Docker images and deploy them with the same tools as the rest of the Docker ecosystem.</span></span>

<span data-ttu-id="db99e-105">Windows コンテナーを使用するには、だけです、DockerFile で Windows PowerShell コマンドを記述する次の例に示すよう。</span><span class="sxs-lookup"><span data-stu-id="db99e-105">To use Windows Containers, you just need to write Windows PowerShell commands in the DockerFile, as demonstrated in the following example:</span></span>

```Dockerfile
FROM microsoft/windowsservercore
LABEL Description="IIS" Vendor="Microsoft" Version="10"
RUN powershell -Command Add-WindowsFeature Web-Server
CMD [ "ping", "localhost", "-t" ]
```

<span data-ttu-id="db99e-106">この場合、IIS だけでなく Windows Server Core 基本イメージをインストールする Windows PowerShell を使用しています。</span><span class="sxs-lookup"><span data-stu-id="db99e-106">In this case, we're using Windows PowerShell to install a Windows Server Core base image as well as IIS.</span></span>

<span data-ttu-id="db99e-107">同様の方法で使用することもできます Windows PowerShell コマンド、従来の ASP.NET などの追加コンポーネントを設定する 4.x および .NET 4.6、またはその他の Windows ソフトウェア、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="db99e-107">In a similar way, you also could use Windows PowerShell commands to set up additional components like the traditional ASP.NET 4.x and .NET 4.6 or any other Windows software, as shown here:</span></span>

```Dockerfile
RUN powershell add-windowsfeature web-asp-net45
```

>[!div class="step-by-step"]
><span data-ttu-id="db99e-108">[前へ](visual-studio-tools-for-docker.md)
>[次へ](build-aspnet-core-applications-linux-containers-aks-kubernetes.md)</span><span class="sxs-lookup"><span data-stu-id="db99e-108">[Previous](visual-studio-tools-for-docker.md)
[Next](build-aspnet-core-applications-linux-containers-aks-kubernetes.md)</span></span>
