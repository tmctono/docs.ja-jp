---
ms.openlocfilehash: 7d398df060c031ae891218b82a2712d74f4c33b7
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84602748"
---

<span data-ttu-id="387a0-101">"**パッケージ {netcore-package} が見つかりません**" のようなエラー メッセージが表示される場合は、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="387a0-101">If you receive an error message similar to **Unable to locate package {netcore-package}**, run the following commands.</span></span>

<span data-ttu-id="387a0-102">次の一連のコマンドには、2 つのプレースホルダーがあります。</span><span class="sxs-lookup"><span data-stu-id="387a0-102">There are two placeholders in the following set of commands.</span></span>

- `{dotnet-package}`\
<span data-ttu-id="387a0-103">これは、`aspnetcore-runtime-3.1` など、インストールする .NET Core パッケージを表します。</span><span class="sxs-lookup"><span data-stu-id="387a0-103">This represents the .NET Core package you're installing, such as `aspnetcore-runtime-3.1`.</span></span> <span data-ttu-id="387a0-104">これは、次の `sudo apt-get install` コマンドで使用されます。</span><span class="sxs-lookup"><span data-stu-id="387a0-104">This is used in the `sudo apt-get install` command below.</span></span>

- `{os-version}`\
<span data-ttu-id="387a0-105">これは、使用している Linux のバージョンを表します。</span><span class="sxs-lookup"><span data-stu-id="387a0-105">This represents the Linux version you are on.</span></span> <span data-ttu-id="387a0-106">これは、次の `wget` コマンドで使用されます。</span><span class="sxs-lookup"><span data-stu-id="387a0-106">This is used in the `wget` command below.</span></span>

<span data-ttu-id="387a0-107">パッケージ リストを消去してみてください。</span><span class="sxs-lookup"><span data-stu-id="387a0-107">Try purging the package list:</span></span>

```bash
sudo dpkg --purge packages-microsoft-prod && sudo dpkg -i packages-microsoft-prod.deb
sudo apt-get update
sudo apt-get install {dotnet-package}
```

<span data-ttu-id="387a0-108">それでも解決しない場合は、次のコマンドを使用して手動インストールを実行できます。</span><span class="sxs-lookup"><span data-stu-id="387a0-108">If that doesn't work, you can run a manual install with the following commands:</span></span>
