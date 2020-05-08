---
title: 相互運用性
ms.date: 12/13/2019
description: 他の SQLite ライブラリと相互運用する方法について説明します。
ms.openlocfilehash: 486e2a8e00999b8ebe9c85a5fcc1539c514676d3
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450460"
---
# <a name="interoperability"></a><span data-ttu-id="ec929-103">相互運用性</span><span class="sxs-lookup"><span data-stu-id="ec929-103">Interoperability</span></span>

<span data-ttu-id="ec929-104">Microsoft.Data.Sqlite では、SQLitePCLRaw を使用してネイティブ SQLite ライブラリと対話します。</span><span class="sxs-lookup"><span data-stu-id="ec929-104">Microsoft.Data.Sqlite uses SQLitePCLRaw to interact with the native SQLite library.</span></span> <span data-ttu-id="ec929-105">SQLitePCLRaw には、ネイティブの SQLite API より優先されるシン .NET API があります。</span><span class="sxs-lookup"><span data-stu-id="ec929-105">SQLitePCLRaw provides a thin .NET API over the native SQLite API.</span></span> <span data-ttu-id="ec929-106">SqliteConnection と SqliteDataReader では、基になる SQLitePCLRaw オブジェクトにアクセスでき、これらの API を直接呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="ec929-106">SqliteConnection and SqliteDataReader provide access to the underlying SQLitePCLRaw objects letting you call these APIs directly.</span></span>

<span data-ttu-id="ec929-107">次の例では、`sqlite3_trace` を呼び出して、実行された SQL ステートメントをコンソールに書き込む方法を示します。</span><span class="sxs-lookup"><span data-stu-id="ec929-107">The following example shows how to call `sqlite3_trace` to write executed SQL statements to the console:</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/InteropSample/Program.cs?name=snippet_Trace)]

<span data-ttu-id="ec929-108">また、次の例では、`sqlite3_stmt_status` を呼び出して、SQL ステートメントでコンパイルされた SQLite 仮想マシンのステップの数を確認します。</span><span class="sxs-lookup"><span data-stu-id="ec929-108">And the following example shows calling `sqlite3_stmt_status` to see how many SQLite virtual machine steps a SQL statement compiled into:</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/InteropSample/Program.cs?name=snippet_StatementStatus)]

<span data-ttu-id="ec929-109">SQLitePCLRaw オブジェクトではネイティブ オブジェクトへのポインターも公開され、追加のネイティブ SQLite API を P/Invoke できます。</span><span class="sxs-lookup"><span data-stu-id="ec929-109">The SQLitePCLRaw objects even expose a pointer to the native objects letting you P/Invoke additional native SQLite APIs.</span></span>
