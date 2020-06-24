---
ms.openlocfilehash: f9ea0ee6402187365cec5cdced1617ee2ae66bed
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84602820"
---

### <a name="install-the-sdk"></a><span data-ttu-id="3a10d-101">SDK のインストール</span><span class="sxs-lookup"><span data-stu-id="3a10d-101">Install the SDK</span></span>

<span data-ttu-id="3a10d-102">.NET Core SDK を使用すると、.NET Core を使用してアプリを開発できます。</span><span class="sxs-lookup"><span data-stu-id="3a10d-102">.NET Core SDK allows you to develop apps with .NET Core.</span></span> <span data-ttu-id="3a10d-103">.NET Core SDK をインストールする場合、対応するランタイムをインストールする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="3a10d-103">If you install .NET Core SDK, you don't need to install the corresponding runtime.</span></span> <span data-ttu-id="3a10d-104">.NET Core SDK をインストールするには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="3a10d-104">To install .NET Core SDK, run the following commands:</span></span>

```bash
sudo dnf install dotnet-sdk-3.0
```

### <a name="install-the-runtime"></a><span data-ttu-id="3a10d-105">ランタイムをインストールする</span><span class="sxs-lookup"><span data-stu-id="3a10d-105">Install the runtime</span></span>

<span data-ttu-id="3a10d-106">.NET Core ランタイムを使用すると、ランタイムを含まない .NET Core を使用して作成されたアプリを実行できます。</span><span class="sxs-lookup"><span data-stu-id="3a10d-106">The .NET Core Runtime allows you to run apps that were made with .NET Core that didn't include the runtime.</span></span> <span data-ttu-id="3a10d-107">次のコマンドを実行すると、.NET Core の最も互換性の高いランタイムである ASP.NET Core ランタイムがインストールされます。</span><span class="sxs-lookup"><span data-stu-id="3a10d-107">The commands below install the ASP.NET Core Runtime, which is the most compatible runtime for .NET Core.</span></span> <span data-ttu-id="3a10d-108">ご利用のターミナルで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="3a10d-108">In your terminal, run the following commands.</span></span>

```bash
sudo dnf install aspnetcore-runtime-3.0
```

<span data-ttu-id="3a10d-109">ASP.NET Core ランタイムの代替手段として、ASP.NET Core サポートを含まない .NET Core ランタイムをインストールできます。それには、前述のコマンドの `aspnetcore-runtime-3.0` を `dotnet-runtime-3.0` で置き換えます。</span><span class="sxs-lookup"><span data-stu-id="3a10d-109">As an alternative to the ASP.NET Core Runtime, you can install the .NET Core Runtime that doesn't include ASP.NET Core support: replace `aspnetcore-runtime-3.0` in the command above with `dotnet-runtime-3.0`.</span></span>

```bash
sudo dnf install dotnet-runtime-3.0
```
