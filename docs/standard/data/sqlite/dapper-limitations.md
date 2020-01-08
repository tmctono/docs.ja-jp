---
title: Dapper の制限事項
ms.date: 12/13/2019
description: Dapper を使用する際に発生する制限事項について説明します。
ms.openlocfilehash: 90c7fb24f068d663081390bdba9b1b222b4be56e
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450496"
---
# <a name="dapper-limitations"></a><span data-ttu-id="bedfc-103">Dapper の制限事項</span><span class="sxs-lookup"><span data-stu-id="bedfc-103">Dapper limitations</span></span>

<span data-ttu-id="bedfc-104">[Dapper](https://stackexchange.github.io/Dapper/)と共に使用する場合は、いくつかの制限事項に注意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bedfc-104">There are a few limitations you should be aware of when using Microsoft.Data.Sqlite with [Dapper](https://stackexchange.github.io/Dapper/).</span></span>

## <a name="parameters"></a><span data-ttu-id="bedfc-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="bedfc-105">Parameters</span></span>

<span data-ttu-id="bedfc-106">SQLite パラメーター名では大文字と小文字が区別されます。</span><span class="sxs-lookup"><span data-stu-id="bedfc-106">SQLite parameter names are case-sensitive.</span></span> <span data-ttu-id="bedfc-107">SQL で使用されるパラメーター名が、匿名オブジェクトのプロパティの大文字と小文字の区別と一致していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="bedfc-107">Ensure that the parameter names used in SQL match the case of the anonymous object's properties.</span></span> <span data-ttu-id="bedfc-108">[#18861](https://github.com/aspnet/EntityFrameworkCore/issues/18861)問題を解決すると、このエクスペリエンスが向上します。</span><span class="sxs-lookup"><span data-stu-id="bedfc-108">Issue [#18861](https://github.com/aspnet/EntityFrameworkCore/issues/18861) would improve this experience.</span></span>

<span data-ttu-id="bedfc-109">Dapper では、`@` プレフィックスを使用するパラメーターも必要です。</span><span class="sxs-lookup"><span data-stu-id="bedfc-109">Dapper also expects parameters to use the `@` prefix.</span></span> <span data-ttu-id="bedfc-110">その他のプレフィックスは機能しません。</span><span class="sxs-lookup"><span data-stu-id="bedfc-110">Other prefixes won't work.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/DapperSample/Program.cs?name=snippet_Parameter)]

## <a name="data-types"></a><span data-ttu-id="bedfc-111">データの種類</span><span class="sxs-lookup"><span data-stu-id="bedfc-111">Data types</span></span>

<span data-ttu-id="bedfc-112">Dapper は、SqliteDataReader インデクサーを使用して値を読み取ります。</span><span class="sxs-lookup"><span data-stu-id="bedfc-112">Dapper reads values using the SqliteDataReader indexer.</span></span> <span data-ttu-id="bedfc-113">このインデクサーの戻り値の型は object です。つまり、long、double、string、または byte [] の値のみが返されます。</span><span class="sxs-lookup"><span data-stu-id="bedfc-113">The return type of this indexer is object, which means it will only ever return long, double, string, or byte[] values.</span></span> <span data-ttu-id="bedfc-114">詳細については、「[データ型](types.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bedfc-114">For more information, see [Data types](types.md).</span></span> <span data-ttu-id="bedfc-115">Dapper は、これらのプリミティブ型と他のプリミティブ型とのほとんどの変換を処理します。</span><span class="sxs-lookup"><span data-stu-id="bedfc-115">Dapper handles most conversions between these and other primitive types.</span></span> <span data-ttu-id="bedfc-116">残念ながら、`DateTimeOffset`、`Guid`、`TimeSpan`は処理されません。</span><span class="sxs-lookup"><span data-stu-id="bedfc-116">Unfortunately, it doesn't handle `DateTimeOffset`, `Guid`, or `TimeSpan`.</span></span> <span data-ttu-id="bedfc-117">これらの型を結果で使用する場合は、型ハンドラーを作成します。</span><span class="sxs-lookup"><span data-stu-id="bedfc-117">Create type handlers if you want to use these types in your results.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/DapperSample/Program.cs?name=snippet_TypeHandlers)]

<span data-ttu-id="bedfc-118">クエリを実行する前に、必ず型ハンドラーを追加してください。</span><span class="sxs-lookup"><span data-stu-id="bedfc-118">Don't forget to add the type handlers before querying.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/DapperSample/Program.cs?name=snippet_AddTypeHandlers)]

## <a name="see-also"></a><span data-ttu-id="bedfc-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="bedfc-119">See also</span></span>

* [<span data-ttu-id="bedfc-120">データ型</span><span class="sxs-lookup"><span data-stu-id="bedfc-120">Data types</span></span>](types.md)
* [<span data-ttu-id="bedfc-121">非同期の制限事項</span><span class="sxs-lookup"><span data-stu-id="bedfc-121">Async limitations</span></span>](async.md)
