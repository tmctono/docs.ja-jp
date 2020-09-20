---
title: 非同期の制限事項
ms.date: 09/04/2020
description: 非同期 API の制限事項と、代わりに使用できるいくつかの代替手段について説明します。
ms.openlocfilehash: 8b14fcfeb12d331d8d43ca6d77332007a12ae5dc
ms.sourcegitcommit: 0c3ce6d2e7586d925a30f231f32046b7b3934acb
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/08/2020
ms.locfileid: "89515996"
---
# <a name="async-limitations"></a><span data-ttu-id="e19d0-103">非同期の制限事項</span><span class="sxs-lookup"><span data-stu-id="e19d0-103">Async limitations</span></span>

<span data-ttu-id="e19d0-104">SQLite では非同期 I/O はサポートされません。</span><span class="sxs-lookup"><span data-stu-id="e19d0-104">SQLite doesn't support asynchronous I/O.</span></span> <span data-ttu-id="e19d0-105">非同期 ADO.NET メソッドは、Microsoft.Data.Sqlite では同期的に実行されます。</span><span class="sxs-lookup"><span data-stu-id="e19d0-105">Async ADO.NET methods will execute synchronously in Microsoft.Data.Sqlite.</span></span> <span data-ttu-id="e19d0-106">これらを呼び出すのは避けてください。</span><span class="sxs-lookup"><span data-stu-id="e19d0-106">Avoid calling them.</span></span>

<span data-ttu-id="e19d0-107">代わりに、[共有キャッシュ](connection-strings.md#cache)と[先行書き込みログ](https://www.sqlite.org/wal.html)を使用して、パフォーマンスとコンカレンシーを向上させます。</span><span class="sxs-lookup"><span data-stu-id="e19d0-107">Instead, use a [shared cache](connection-strings.md#cache) and [write-ahead logging](https://www.sqlite.org/wal.html) to improve performance and concurrency.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/AsyncSample/Program.cs?name=snippet_WAL)]

> [!TIP]
> <span data-ttu-id="e19d0-108">[Entity Framework Core](/ef/core/) を使用して作成されたデータベースでは、先行書き込みログが既定で有効になっています。</span><span class="sxs-lookup"><span data-stu-id="e19d0-108">Write-ahead logging is enabled by default on databases created using [Entity Framework Core](/ef/core/).</span></span>
