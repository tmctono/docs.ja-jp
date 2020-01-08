---
title: 非同期の制限事項
ms.date: 12/13/2019
description: 非同期 Api の制限と代わりに使用できるいくつかの代替手段について説明します。
ms.openlocfilehash: 350237dc5c03023f60e9680e8b9c94aabb62606f
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450334"
---
# <a name="async-limitations"></a><span data-ttu-id="f5676-103">非同期の制限事項</span><span class="sxs-lookup"><span data-stu-id="f5676-103">Async limitations</span></span>

<span data-ttu-id="f5676-104">SQLite は、非同期 i/o をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="f5676-104">SQLite doesn't support asynchronous I/O.</span></span> <span data-ttu-id="f5676-105">非同期 ADO.NET メソッドは、同期的に実行されます。</span><span class="sxs-lookup"><span data-stu-id="f5676-105">Async ADO.NET methods will execute synchronously in Microsoft.Data.Sqlite.</span></span> <span data-ttu-id="f5676-106">これらの呼び出しは避けてください。</span><span class="sxs-lookup"><span data-stu-id="f5676-106">Avoid calling them.</span></span>

<span data-ttu-id="f5676-107">代わりに、[先行書き込みログ](https://www.sqlite.org/wal.html)を使用して、パフォーマンスと同時実行性を向上させます。</span><span class="sxs-lookup"><span data-stu-id="f5676-107">Instead, use [write-ahead logging](https://www.sqlite.org/wal.html) to improve performance and concurrency.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/AsyncSample/Program.cs?name=snippet_WAL)]

> [!TIP]
> <span data-ttu-id="f5676-108">[Entity Framework Core](/ef/core/)を使用して作成されたデータベースでは、先行書き込みログが既定で有効になっています。</span><span class="sxs-lookup"><span data-stu-id="f5676-108">Write-ahead logging is enabled by default on databases created using [Entity Framework Core](/ef/core/).</span></span>
