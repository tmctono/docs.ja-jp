---
ms.openlocfilehash: e140b375f4f289df895052aa093f03f381d62488
ms.sourcegitcommit: 73aa9653547a1cd70ee6586221f79cc29b588ebd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2020
ms.locfileid: "82102744"
---
<span data-ttu-id="8bc43-101">[`dotnet restore`](~/docs/core/tools/dotnet-restore.md) を実行する必要がなくなりました。復元を必要とするすべてのコマンド (`dotnet new`、`dotnet build`、`dotnet run`、`dotnet test`、`dotnet publish`、`dotnet pack` など) によって暗黙的に実行されるためです。</span><span class="sxs-lookup"><span data-stu-id="8bc43-101">You don't have to run [`dotnet restore`](~/docs/core/tools/dotnet-restore.md) because it's run implicitly by all commands that require a restore to occur, such as `dotnet new`, `dotnet build`, `dotnet run`, `dotnet test`, `dotnet publish`, and `dotnet pack`.</span></span> <span data-ttu-id="8bc43-102">暗黙的な復元を無効にするには、`--no-restore` オプションを使用します。</span><span class="sxs-lookup"><span data-stu-id="8bc43-102">To disable implicit restore, use the `--no-restore` option.</span></span>

<span data-ttu-id="8bc43-103">[Azure DevOps Services の継続的インテグレーション ビルド](https://docs.microsoft.com/azure/devops/build-release/apps/aspnet/build-aspnet-core)などの、明示的な復元が意味のある一部のシナリオや、復元が行われるタイミングを明示的に制御する必要があるビルド システムでは、`dotnet restore` は引き続き有用なコマンドです。</span><span class="sxs-lookup"><span data-stu-id="8bc43-103">The `dotnet restore` command is still useful in certain scenarios where explicitly restoring makes sense, such as [continuous integration builds in Azure DevOps Services](https://docs.microsoft.com/azure/devops/build-release/apps/aspnet/build-aspnet-core) or in build systems that need to explicitly control when the restore occurs.</span></span>

<span data-ttu-id="8bc43-104">NuGet フィードの管理方法については、[`dotnet restore` のドキュメント](../docs/core/tools/dotnet-restore.md)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="8bc43-104">For information about how to manage NuGet feeds, see the [`dotnet restore` documentation](../docs/core/tools/dotnet-restore.md).</span></span>
