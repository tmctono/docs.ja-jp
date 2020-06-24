---
ms.openlocfilehash: 0d29407896145bc3b2ed8284c839ae8f2f0521b2
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84602718"
---

<span data-ttu-id="85076-101">[dotnet-install スクリプト](../../tools/dotnet-install-script.md)は、**SDK** のインストールの自動化および管理者以外によるインストールに使用されます。</span><span class="sxs-lookup"><span data-stu-id="85076-101">The [dotnet-install scripts](../../tools/dotnet-install-script.md) are used for automation and non-admin installs of the **SDK**.</span></span> <span data-ttu-id="85076-102">このスクリプトは <https://dot.net/v1/dotnet-install.sh> からダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="85076-102">You can download the script from <https://dot.net/v1/dotnet-install.sh>.</span></span>

<span data-ttu-id="85076-103">スクリプトでは、既定で最新の [長期サポート (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) バージョン (.NET Core 3.1) がインストールされます。</span><span class="sxs-lookup"><span data-stu-id="85076-103">The script defaults to installing the latest [long term support (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) version, which is .NET Core 3.1.</span></span> <span data-ttu-id="85076-104">(LTS) バージョンではない場合がある現在のリリースをインストールするには、`-c Current` パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="85076-104">To install the current release, which may not be an (LTS) version, use the `-c Current` parameter.</span></span>

```bash
./dotnet-install.sh -c Current
```

<span data-ttu-id="85076-105">SDK の代わりに .NET Core ランタイムをインストールするには、`--runtime` パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="85076-105">To install .NET Core Runtime instead of the SDK, use the `--runtime` parameter.</span></span>

```bash
./dotnet-install.sh -c Current --runtime
```

<span data-ttu-id="85076-106">特定のバージョンをインストールするには、`-c` パラメーターを変更して特定のバージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="85076-106">You can install a specific version by altering the `-c` parameter to indicate the specific version.</span></span> <span data-ttu-id="85076-107">次のコマンドでは、.NET Core SDK 3.1 がインストールされます。</span><span class="sxs-lookup"><span data-stu-id="85076-107">The following command installs .NET Core SDK 3.1.</span></span>

```bash
./dotnet-install.sh -c 3.1
```

<span data-ttu-id="85076-108">詳細については、「[dotnet-install スクリプト リファレンス](../../tools/dotnet-install-script.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="85076-108">For more information, see [dotnet-install scripts reference](../../tools/dotnet-install-script.md).</span></span>
