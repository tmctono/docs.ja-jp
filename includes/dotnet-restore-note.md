---
ms.openlocfilehash: 975edd1bda507b46da353db788d9730560f9b573
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2019
ms.locfileid: "65632107"
---
> [!NOTE]
> <span data-ttu-id="9d863-101">.NET Core 2.0 SDK 以降、[`dotnet restore`](~/docs/core/tools/dotnet-restore.md) を実行する必要がなくなりました。`dotnet new`、`dotnet build`、`dotnet run` のような、復元を必要とするあらゆるコマンドによって暗黙的に実行されるためです。</span><span class="sxs-lookup"><span data-stu-id="9d863-101">Starting with .NET Core 2.0 SDK, you don't have to run [`dotnet restore`](~/docs/core/tools/dotnet-restore.md) because it's run implicitly by all commands that require a restore to occur, such as `dotnet new`, `dotnet build` and `dotnet run`.</span></span>
> <span data-ttu-id="9d863-102">[Azure DevOps Services の継続的インテグレーション ビルド](https://docs.microsoft.com/azure/devops/build-release/apps/aspnet/build-aspnet-core)など、明示的な復元が合理的となる一部のシナリオや、復元の時刻を明示的に制御する必要があるビルド システムでは、引き続き有効なコマンドとなります。</span><span class="sxs-lookup"><span data-stu-id="9d863-102">It's still a valid command in certain scenarios where doing an explicit restore makes sense, such as [continuous integration builds in Azure DevOps Services](https://docs.microsoft.com/azure/devops/build-release/apps/aspnet/build-aspnet-core) or in build systems that need to explicitly control the time at which the restore occurs.</span></span>
