---
ms.openlocfilehash: 47811d3fab2e4fa531d383dfe818e3cac5613eb3
ms.sourcegitcommit: dfd612ba454ce775a766bcc6fe93bc1d43dfda47
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/09/2019
ms.locfileid: "72179975"
---
> [!NOTE]
> <span data-ttu-id="d0a49-101">.NET Core 2.0 以降、[`dotnet restore`](~/docs/core/tools/dotnet-restore.md) を実行する必要がなくなりました。`dotnet build` や `dotnet run` のような、復元を必要とするあらゆるコマンドによって暗黙的に実行されるためです。</span><span class="sxs-lookup"><span data-stu-id="d0a49-101">Starting with .NET Core 2.0, you don't have to run [`dotnet restore`](~/docs/core/tools/dotnet-restore.md) because it's run implicitly by all commands that require a restore to occur, such as `dotnet build` and `dotnet run`.</span></span> <span data-ttu-id="d0a49-102">[Azure DevOps Services の継続的インテグレーション ビルド](/azure/devops/build-release/apps/aspnet/build-aspnet-core)など、明示的な復元が合理的となる一部のシナリオや、復元の時刻を明示的に制御する必要があるビルド システムでは、引き続き有効なコマンドとなります。</span><span class="sxs-lookup"><span data-stu-id="d0a49-102">It's still a valid command in certain scenarios where doing an explicit restore makes sense, such as [continuous integration builds in Azure DevOps Services](/azure/devops/build-release/apps/aspnet/build-aspnet-core) or in build systems that need to explicitly control the time at which the restore occurs.</span></span>
>
> <span data-ttu-id="d0a49-103">このコマンドには `dotnet restore` オプションを指定できますが、`--source` のように長い形式で指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d0a49-103">This command also supports the `dotnet restore` options when passed in the long form (for example, `--source`).</span></span> <span data-ttu-id="d0a49-104">`-s` のような短い形式のオプションはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="d0a49-104">Short form options, such as `-s`, are not supported.</span></span>
