---
title: インメモリデータベース
ms.date: 12/13/2019
description: メモリ内 SQLite データベースの使用方法について説明します。
ms.openlocfilehash: b125ff5aa4128bd4c3ff558c5573b7d11802090a
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450466"
---
# <a name="in-memory-databases"></a><span data-ttu-id="2ddf9-103">インメモリデータベース</span><span class="sxs-lookup"><span data-stu-id="2ddf9-103">In-memory databases</span></span>

<span data-ttu-id="2ddf9-104">SQLite インメモリデータベースは、ディスク上ではなく、メモリ内に完全に格納されるデータベースです。</span><span class="sxs-lookup"><span data-stu-id="2ddf9-104">SQLite in-memory databases are databases stored entirely in memory, not on disk.</span></span> <span data-ttu-id="2ddf9-105">メモリ内データベースを作成するには、特殊なデータソースファイル名 `:memory:` を使用します。</span><span class="sxs-lookup"><span data-stu-id="2ddf9-105">Use the special data source filename `:memory:` to create an in-memory database.</span></span> <span data-ttu-id="2ddf9-106">接続が閉じられると、データベースは削除されます。</span><span class="sxs-lookup"><span data-stu-id="2ddf9-106">When the connection is closed, the database is deleted.</span></span> <span data-ttu-id="2ddf9-107">`:memory:`を使用する場合、各接続は独自のデータベースを作成します。</span><span class="sxs-lookup"><span data-stu-id="2ddf9-107">When using `:memory:`, each connection creates its own database.</span></span>

```ConnectionString
Data Source=:memory:
```

## <a name="shareable-in-memory-databases"></a><span data-ttu-id="2ddf9-108">共有可能なインメモリデータベース</span><span class="sxs-lookup"><span data-stu-id="2ddf9-108">Shareable in-memory databases</span></span>

<span data-ttu-id="2ddf9-109">インメモリデータベースは、接続文字列で `Mode=Memory` と `Cache=Shared` を使用して、複数の接続間で共有できます。</span><span class="sxs-lookup"><span data-stu-id="2ddf9-109">In-memory databases can be shared between multiple connections by using `Mode=Memory` and `Cache=Shared` in the connection string.</span></span> <span data-ttu-id="2ddf9-110">`Data Source` キーワードを使用して、メモリ内のデータベースに名前を付けます。</span><span class="sxs-lookup"><span data-stu-id="2ddf9-110">The `Data Source` keyword is used to give the in-memory database a name.</span></span> <span data-ttu-id="2ddf9-111">同じ名前を使用する接続文字列は、同じメモリ内のデータベースにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="2ddf9-111">Connection strings using the same name will access the same in-memory database.</span></span> <span data-ttu-id="2ddf9-112">データベースは、少なくとも1つの接続が開いたままになっている間は保持されます。</span><span class="sxs-lookup"><span data-stu-id="2ddf9-112">The database persists as long as at least one connection to it remains open.</span></span> <span data-ttu-id="2ddf9-113">これをデモンストレーションする[サンプル](https://github.com/dotnet/samples/blob/master/samples/snippets/standard/data/sqlite/InMemorySample/Program.cs)は GitHub で入手できます。</span><span class="sxs-lookup"><span data-stu-id="2ddf9-113">A [sample](https://github.com/dotnet/samples/blob/master/samples/snippets/standard/data/sqlite/InMemorySample/Program.cs) demonstrating this is available on GitHub.</span></span>

```ConnectionString
Data Source=InMemorySample;Mode=Memory;Cache=Shared
```
