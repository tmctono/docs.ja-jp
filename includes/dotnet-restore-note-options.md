---
ms.openlocfilehash: 19002cce40fdc929716a761a5e01303be4decb35
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/15/2020
ms.locfileid: "90537830"
---
<span data-ttu-id="88bbf-101">[`dotnet restore`](~/docs/core/tools/dotnet-restore.md) を実行する必要がなくなりました。復元を必要とするすべてのコマンド (`dotnet new`、`dotnet build`、`dotnet run`、`dotnet test`、`dotnet publish`、`dotnet pack` など) によって暗黙的に実行されるためです。</span><span class="sxs-lookup"><span data-stu-id="88bbf-101">You don't have to run [`dotnet restore`](~/docs/core/tools/dotnet-restore.md) because it's run implicitly by all commands that require a restore to occur, such as `dotnet new`, `dotnet build`, `dotnet run`, `dotnet test`, `dotnet publish`, and `dotnet pack`.</span></span> <span data-ttu-id="88bbf-102">暗黙的な復元を無効にするには、`--no-restore` オプションを使用します。</span><span class="sxs-lookup"><span data-stu-id="88bbf-102">To disable implicit restore, use the `--no-restore` option.</span></span>

<span data-ttu-id="88bbf-103">[Azure DevOps Services の継続的インテグレーション ビルド](/azure/devops/build-release/apps/aspnet/build-aspnet-core)などの、明示的な復元が意味のある一部のシナリオや、復元が行われるタイミングを明示的に制御する必要があるビルド システムでは、`dotnet restore` は引き続き有用なコマンドです。</span><span class="sxs-lookup"><span data-stu-id="88bbf-103">The `dotnet restore` command is still useful in certain scenarios where explicitly restoring makes sense, such as [continuous integration builds in Azure DevOps Services](/azure/devops/build-release/apps/aspnet/build-aspnet-core) or in build systems that need to explicitly control when the restore occurs.</span></span>

<span data-ttu-id="88bbf-104">NuGet フィードの管理方法については、[`dotnet restore` のドキュメント](../docs/core/tools/dotnet-restore.md)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="88bbf-104">For information about how to manage NuGet feeds, see the [`dotnet restore` documentation](../docs/core/tools/dotnet-restore.md).</span></span>

<span data-ttu-id="88bbf-105">このコマンドには `dotnet restore` オプションを指定できますが、`--source` のように長い形式で指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="88bbf-105">This command supports the `dotnet restore` options when passed in the long form (for example, `--source`).</span></span> <span data-ttu-id="88bbf-106">`-s` のような短い形式のオプションはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="88bbf-106">Short form options, such as `-s`, are not supported.</span></span>
