---
title: Dapper の制限事項
ms.date: 12/13/2019
description: Dapper の使用時に生じる制限事項について説明します。
ms.openlocfilehash: 396507f25f591a9ab5c3bb07c0af6fd8d175e4ea
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/11/2020
ms.locfileid: "75901208"
---
# <a name="dapper-limitations"></a><span data-ttu-id="44b64-103">Dapper の制限事項</span><span class="sxs-lookup"><span data-stu-id="44b64-103">Dapper limitations</span></span>

<span data-ttu-id="44b64-104">Microsoft.Data.Sqlite を [Dapper](https://stackexchange.github.io/Dapper/) とともに使用する場合に、知っておく必要がある制限事項がいくつか存在します。</span><span class="sxs-lookup"><span data-stu-id="44b64-104">There are a few limitations you should be aware of when using Microsoft.Data.Sqlite with [Dapper](https://stackexchange.github.io/Dapper/).</span></span>

## <a name="parameters"></a><span data-ttu-id="44b64-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="44b64-105">Parameters</span></span>

<span data-ttu-id="44b64-106">SQLite パラメーター名では大文字と小文字が区別されます。</span><span class="sxs-lookup"><span data-stu-id="44b64-106">SQLite parameter names are case-sensitive.</span></span> <span data-ttu-id="44b64-107">SQL で使用されるパラメーター名と匿名オブジェクトのプロパティで、大文字と小文字が一致していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="44b64-107">Ensure that the parameter names used in SQL match the case of the anonymous object's properties.</span></span> <span data-ttu-id="44b64-108">問題 [#18861](https://github.com/dotnet/efcore/issues/18861) が、この動作の改善について取り上げています。</span><span class="sxs-lookup"><span data-stu-id="44b64-108">Issue [#18861](https://github.com/dotnet/efcore/issues/18861) would improve this experience.</span></span>

<span data-ttu-id="44b64-109">Dapper では、パラメーターに `@` プレフィックスを使用する必要もあります。</span><span class="sxs-lookup"><span data-stu-id="44b64-109">Dapper also expects parameters to use the `@` prefix.</span></span> <span data-ttu-id="44b64-110">他のプレフィックスは機能しません。</span><span class="sxs-lookup"><span data-stu-id="44b64-110">Other prefixes won't work.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/DapperSample/Program.cs?name=snippet_Parameter)]

## <a name="data-types"></a><span data-ttu-id="44b64-111">データの種類</span><span class="sxs-lookup"><span data-stu-id="44b64-111">Data types</span></span>

<span data-ttu-id="44b64-112">Dapper では、SqliteDataReader インデクサーを使用して値が読み取られます。</span><span class="sxs-lookup"><span data-stu-id="44b64-112">Dapper reads values using the SqliteDataReader indexer.</span></span> <span data-ttu-id="44b64-113">このインデクサーの戻り値の型は object です。つまり、long、double、string、または byte [] の値のみが返されます。</span><span class="sxs-lookup"><span data-stu-id="44b64-113">The return type of this indexer is object, which means it will only ever return long, double, string, or byte[] values.</span></span> <span data-ttu-id="44b64-114">詳細については、「[データ型](types.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="44b64-114">For more information, see [Data types](types.md).</span></span> <span data-ttu-id="44b64-115">これらの型と他のプリミティブ型との間の変換は、ほとんどが Dapper によって処理されます。</span><span class="sxs-lookup"><span data-stu-id="44b64-115">Dapper handles most conversions between these and other primitive types.</span></span> <span data-ttu-id="44b64-116">ただし、`DateTimeOffset`、`Guid`、`TimeSpan` は処理されません。</span><span class="sxs-lookup"><span data-stu-id="44b64-116">Unfortunately, it doesn't handle `DateTimeOffset`, `Guid`, or `TimeSpan`.</span></span> <span data-ttu-id="44b64-117">これらの型を結果で使用する場合は、型ハンドラーを作成してください。</span><span class="sxs-lookup"><span data-stu-id="44b64-117">Create type handlers if you want to use these types in your results.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/DapperSample/Program.cs?name=snippet_TypeHandlers)]

<span data-ttu-id="44b64-118">この型ハンドラーは、クエリを実行する前に忘れずに追加してください。</span><span class="sxs-lookup"><span data-stu-id="44b64-118">Don't forget to add the type handlers before querying.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/DapperSample/Program.cs?name=snippet_AddTypeHandlers)]

## <a name="see-also"></a><span data-ttu-id="44b64-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="44b64-119">See also</span></span>

* [<span data-ttu-id="44b64-120">データ型</span><span class="sxs-lookup"><span data-stu-id="44b64-120">Data types</span></span>](types.md)
* [<span data-ttu-id="44b64-121">非同期の制限事項</span><span class="sxs-lookup"><span data-stu-id="44b64-121">Async limitations</span></span>](async.md)
