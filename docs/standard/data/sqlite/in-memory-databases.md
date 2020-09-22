---
title: インメモリ データベース
ms.date: 12/13/2019
description: インメモリ SQLite データベースの使用方法について説明します。
ms.openlocfilehash: fbda5787d95a9ce462752b985f847af0b0551fa6
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/15/2020
ms.locfileid: "90555368"
---
# <a name="in-memory-databases"></a><span data-ttu-id="077c4-103">インメモリ データベース</span><span class="sxs-lookup"><span data-stu-id="077c4-103">In-memory databases</span></span>

<span data-ttu-id="077c4-104">SQLite インメモリ データベースは、ディスク上ではなく、メモリ内に全体が格納されるデータベースです。</span><span class="sxs-lookup"><span data-stu-id="077c4-104">SQLite in-memory databases are databases stored entirely in memory, not on disk.</span></span> <span data-ttu-id="077c4-105">インメモリ データベースを作成するには、特殊なデータ ソース ファイル名 `:memory:` を使用します。</span><span class="sxs-lookup"><span data-stu-id="077c4-105">Use the special data source filename `:memory:` to create an in-memory database.</span></span> <span data-ttu-id="077c4-106">接続が閉じられると、データベースは削除されます。</span><span class="sxs-lookup"><span data-stu-id="077c4-106">When the connection is closed, the database is deleted.</span></span> <span data-ttu-id="077c4-107">`:memory:` を使用すると、各接続で独自のデータベースが作成されます。</span><span class="sxs-lookup"><span data-stu-id="077c4-107">When using `:memory:`, each connection creates its own database.</span></span>

```connectionstring
Data Source=:memory:
```

## <a name="shareable-in-memory-databases"></a><span data-ttu-id="077c4-108">共有可能なインメモリ データベース</span><span class="sxs-lookup"><span data-stu-id="077c4-108">Shareable in-memory databases</span></span>

<span data-ttu-id="077c4-109">接続文字列で `Mode=Memory` と `Cache=Shared` を使用すると、インメモリ データベースを複数の接続間で共有できます。</span><span class="sxs-lookup"><span data-stu-id="077c4-109">In-memory databases can be shared between multiple connections by using `Mode=Memory` and `Cache=Shared` in the connection string.</span></span> <span data-ttu-id="077c4-110">インメモリ データベースに名前を付けるには、`Data Source` キーワードを使用します。</span><span class="sxs-lookup"><span data-stu-id="077c4-110">The `Data Source` keyword is used to give the in-memory database a name.</span></span> <span data-ttu-id="077c4-111">同じ名前を使用する接続文字列では、同じインメモリ データベースがアクセスされます。</span><span class="sxs-lookup"><span data-stu-id="077c4-111">Connection strings using the same name will access the same in-memory database.</span></span> <span data-ttu-id="077c4-112">データベースへの 1 つ以上の接続が開いたままになっている間は、そのデータベースは保持されます。</span><span class="sxs-lookup"><span data-stu-id="077c4-112">The database persists as long as at least one connection to it remains open.</span></span> <span data-ttu-id="077c4-113">これを示す[サンプル](https://github.com/dotnet/docs/blob/master/samples/snippets/standard/data/sqlite/InMemorySample/Program.cs)を GitHub で入手できます。</span><span class="sxs-lookup"><span data-stu-id="077c4-113">A [sample](https://github.com/dotnet/docs/blob/master/samples/snippets/standard/data/sqlite/InMemorySample/Program.cs) demonstrating this is available on GitHub.</span></span>

```connectionstring
Data Source=InMemorySample;Mode=Memory;Cache=Shared
```
