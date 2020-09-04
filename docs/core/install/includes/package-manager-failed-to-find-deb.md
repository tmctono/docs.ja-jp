---
ms.openlocfilehash: 9d4c031eda291b0a8832c824789efdffe4084926
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/30/2020
ms.locfileid: "89132946"
---

<span data-ttu-id="0b323-101">"**パッケージ {netcore-package} が見つかりません**" や "**一部のパッケージをインストールできませんでした**" のようなエラー メッセージが表示される場合は、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="0b323-101">If you receive an error message similar to **Unable to locate package {netcore-package}** or **Some packages could not be installed**, run the following commands.</span></span>

<span data-ttu-id="0b323-102">次の一連のコマンドには、2 つのプレースホルダーがあります。</span><span class="sxs-lookup"><span data-stu-id="0b323-102">There are two placeholders in the following set of commands.</span></span>

- `{dotnet-package}`\
<span data-ttu-id="0b323-103">これは、`aspnetcore-runtime-3.1` など、インストールする .NET Core パッケージを表します。</span><span class="sxs-lookup"><span data-stu-id="0b323-103">This represents the .NET Core package you're installing, such as `aspnetcore-runtime-3.1`.</span></span> <span data-ttu-id="0b323-104">これは、次の `sudo apt-get install` コマンドで使用されます。</span><span class="sxs-lookup"><span data-stu-id="0b323-104">This is used in the `sudo apt-get install` command below.</span></span>

- `{os-version}`\
<span data-ttu-id="0b323-105">これは、使用している Linux のバージョンを表します。</span><span class="sxs-lookup"><span data-stu-id="0b323-105">This represents the Linux version you are on.</span></span> <span data-ttu-id="0b323-106">これは、次の `wget` コマンドで使用されます。</span><span class="sxs-lookup"><span data-stu-id="0b323-106">This is used in the `wget` command below.</span></span>

<span data-ttu-id="0b323-107">まず、パッケージ リストを消去してみてください。</span><span class="sxs-lookup"><span data-stu-id="0b323-107">First, try purging the package list:</span></span>

```bash
sudo dpkg --purge packages-microsoft-prod && sudo dpkg -i packages-microsoft-prod.deb
sudo apt-get update
```

<span data-ttu-id="0b323-108">次に、.NET Core を再度インストールしてください。</span><span class="sxs-lookup"><span data-stu-id="0b323-108">Then, try to install .NET Core again.</span></span> <span data-ttu-id="0b323-109">それでも解決しない場合は、次のコマンドを使用して手動インストールを実行できます。</span><span class="sxs-lookup"><span data-stu-id="0b323-109">If that doesn't work, you can run a manual install with the following commands:</span></span>
