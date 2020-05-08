---
title: BLOB の I/O
ms.date: 12/13/2019
description: SQLite の BLOB I/O 機能の使用方法について説明します。
ms.openlocfilehash: 0c133deacdc19684eca3a6724fb398dc01fda558
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450304"
---
# <a name="blob-io"></a><span data-ttu-id="2c09c-103">BLOB の I/O</span><span class="sxs-lookup"><span data-stu-id="2c09c-103">Blob I/O</span></span>

<span data-ttu-id="2c09c-104">データベースとの間でデータをストリーミングして、ラージ オブジェクトの読み取りと書き込み中のメモリ使用量を削減できます。</span><span class="sxs-lookup"><span data-stu-id="2c09c-104">You can reduce memory usage while reading and writing large objects by streaming the data into and out of the database.</span></span> <span data-ttu-id="2c09c-105">これは、データを解析または変換するときに特に有用です。</span><span class="sxs-lookup"><span data-stu-id="2c09c-105">This can be especially useful when parsing or transforming the data.</span></span>

<span data-ttu-id="2c09c-106">最初に、行を通常どおりに挿入します。</span><span class="sxs-lookup"><span data-stu-id="2c09c-106">Start by inserting a row as normal.</span></span> <span data-ttu-id="2c09c-107">`zeroblob()` SQL 関数を使用して、ラージ オブジェクトを保持するデータベースの領域を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="2c09c-107">Use the `zeroblob()` SQL function to allocate space in the database to hold the large object.</span></span> <span data-ttu-id="2c09c-108">`last_insert_rowid()` 関数を使用すると、rowid を簡単に取得できます。</span><span class="sxs-lookup"><span data-stu-id="2c09c-108">The `last_insert_rowid()` function provides a convenient way to get its rowid.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/StreamingSample/Program.cs?name=snippet_Insert)]

<span data-ttu-id="2c09c-109">行を挿入したら、<xref:Microsoft.Data.Sqlite.SqliteBlob> を使用してストリームを開き、ラージ オブジェクトを書き込みます。</span><span class="sxs-lookup"><span data-stu-id="2c09c-109">After inserting the row, open a stream to write the large object using <xref:Microsoft.Data.Sqlite.SqliteBlob>.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/StreamingSample/Program.cs?name=snippet_Write)]

<span data-ttu-id="2c09c-110">データベースからラージ オブジェクトをストリーミングするには、ラージ オブジェクトの列のほか、ここに示すように、rowid またはその別名のいずれかを選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2c09c-110">To stream the large object out of the database, you must select the rowid or one of its aliases as show here in addition to the large object's column.</span></span> <span data-ttu-id="2c09c-111">rowid を選択しない場合、オブジェクト全体がメモリに読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="2c09c-111">If you don't select the rowid, the entire object will be loaded into memory.</span></span> <span data-ttu-id="2c09c-112">正常に完了すると、`GetStream()` によって返されるオブジェクトは `SqliteBlob` になります。</span><span class="sxs-lookup"><span data-stu-id="2c09c-112">The object returned by `GetStream()` will be a `SqliteBlob` when done correctly.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/StreamingSample/Program.cs?name=snippet_Read)]
