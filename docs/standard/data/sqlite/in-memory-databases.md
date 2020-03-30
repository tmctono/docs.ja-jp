---
title: インメモリ データベース
ms.date: 12/13/2019
description: インメモリ SQLite データベースの使用方法について説明します。
ms.openlocfilehash: 408c81f538e27dcfffad20db74b7809912b7905f
ms.sourcegitcommit: a9b8945630426a575ab0a332e568edc807666d1b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/30/2020
ms.locfileid: "80391209"
---
# <a name="in-memory-databases"></a><span data-ttu-id="d83b8-103">インメモリ データベース</span><span class="sxs-lookup"><span data-stu-id="d83b8-103">In-memory databases</span></span>

<span data-ttu-id="d83b8-104">SQLite インメモリ データベースは、ディスクではなく、メモリに完全に格納されたデータベースです。</span><span class="sxs-lookup"><span data-stu-id="d83b8-104">SQLite in-memory databases are databases stored entirely in memory, not on disk.</span></span> <span data-ttu-id="d83b8-105">メモリ内データベースを作成するには`:memory:`、特殊なデータ ソース ファイル名を使用します。</span><span class="sxs-lookup"><span data-stu-id="d83b8-105">Use the special data source filename `:memory:` to create an in-memory database.</span></span> <span data-ttu-id="d83b8-106">接続が閉じられると、データベースは削除されます。</span><span class="sxs-lookup"><span data-stu-id="d83b8-106">When the connection is closed, the database is deleted.</span></span> <span data-ttu-id="d83b8-107">を使用`:memory:`すると、各接続で独自のデータベースが作成されます。</span><span class="sxs-lookup"><span data-stu-id="d83b8-107">When using `:memory:`, each connection creates its own database.</span></span>

```ConnectionString
Data Source=:memory:
```

## <a name="shareable-in-memory-databases"></a><span data-ttu-id="d83b8-108">共有可能なインメモリ データベース</span><span class="sxs-lookup"><span data-stu-id="d83b8-108">Shareable in-memory databases</span></span>

<span data-ttu-id="d83b8-109">インメモリ データベースは、接続文字列を使用`Mode=Memory`して複数`Cache=Shared`の接続間で共有できます。</span><span class="sxs-lookup"><span data-stu-id="d83b8-109">In-memory databases can be shared between multiple connections by using `Mode=Memory` and `Cache=Shared` in the connection string.</span></span> <span data-ttu-id="d83b8-110">この`Data Source`キーワードは、メモリ内データベースに名前を付けるために使用されます。</span><span class="sxs-lookup"><span data-stu-id="d83b8-110">The `Data Source` keyword is used to give the in-memory database a name.</span></span> <span data-ttu-id="d83b8-111">同じ名前を使用する接続文字列は、同じメモリ内データベースにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="d83b8-111">Connection strings using the same name will access the same in-memory database.</span></span> <span data-ttu-id="d83b8-112">データベースへの接続が少なくとも 1 つ開いている限り、データベースは保持されます。</span><span class="sxs-lookup"><span data-stu-id="d83b8-112">The database persists as long as at least one connection to it remains open.</span></span> <span data-ttu-id="d83b8-113">これを示す[サンプル](https://github.com/dotnet/docs/blob/master/samples/snippets/standard/data/sqlite/InMemorySample/Program.cs)は GitHub で入手できます。</span><span class="sxs-lookup"><span data-stu-id="d83b8-113">A [sample](https://github.com/dotnet/docs/blob/master/samples/snippets/standard/data/sqlite/InMemorySample/Program.cs) demonstrating this is available on GitHub.</span></span>

```ConnectionString
Data Source=InMemorySample;Mode=Memory;Cache=Shared
```
