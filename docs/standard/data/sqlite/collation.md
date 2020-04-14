---
title: 照合順序
ms.date: 12/13/2019
description: カスタム照合シーケンスを作成する方法について説明します。
ms.openlocfilehash: 9879846cc191a62c4cb47a0fbaa47c59153ba61c
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/13/2020
ms.locfileid: "81242973"
---
# <a name="collation"></a><span data-ttu-id="700b1-103">照合順序</span><span class="sxs-lookup"><span data-stu-id="700b1-103">Collation</span></span>

<span data-ttu-id="700b1-104">照合シーケンスは、順序と等価性を決定するために TEXT 値を比較するときに SQLite によって使用されます。</span><span class="sxs-lookup"><span data-stu-id="700b1-104">Collating sequences are used by SQLite when comparing TEXT values to determine order and equality.</span></span> <span data-ttu-id="700b1-105">SQL クエリで列を作成するとき、または操作ごとに使用する照合順序を指定できます。</span><span class="sxs-lookup"><span data-stu-id="700b1-105">You can specify which collation to use when creating columns or per-operation in SQL queries.</span></span> <span data-ttu-id="700b1-106">SQLite には、デフォルトで 3 つの照合シーケンスが含まれています。</span><span class="sxs-lookup"><span data-stu-id="700b1-106">SQLite includes three collating sequences by default.</span></span>

| <span data-ttu-id="700b1-107">照合順序</span><span class="sxs-lookup"><span data-stu-id="700b1-107">Collation</span></span> | <span data-ttu-id="700b1-108">説明</span><span class="sxs-lookup"><span data-stu-id="700b1-108">Description</span></span>                               |
| --------- | ----------------------------------------- |
| <span data-ttu-id="700b1-109">RTRIM</span><span class="sxs-lookup"><span data-stu-id="700b1-109">RTRIM</span></span>     | <span data-ttu-id="700b1-110">末尾の空白を無視します。</span><span class="sxs-lookup"><span data-stu-id="700b1-110">Ignores trailing whitespace</span></span>               |
| <span data-ttu-id="700b1-111">ノーケース</span><span class="sxs-lookup"><span data-stu-id="700b1-111">NOCASE</span></span>    | <span data-ttu-id="700b1-112">ASCII 文字 A から Z の大文字と小文字を区別しない</span><span class="sxs-lookup"><span data-stu-id="700b1-112">Case-insensitive for ASCII characters A-Z</span></span> |
| <span data-ttu-id="700b1-113">BINARY</span><span class="sxs-lookup"><span data-stu-id="700b1-113">BINARY</span></span>    | <span data-ttu-id="700b1-114">大文字 小文字。</span><span class="sxs-lookup"><span data-stu-id="700b1-114">Case-sensitive.</span></span> <span data-ttu-id="700b1-115">バイトを直接比較する</span><span class="sxs-lookup"><span data-stu-id="700b1-115">Compares bytes directly</span></span>   |

## <a name="custom-collation"></a><span data-ttu-id="700b1-116">カスタム照合順序</span><span class="sxs-lookup"><span data-stu-id="700b1-116">Custom collation</span></span>

<span data-ttu-id="700b1-117">また、独自の照合順序を定義したり、組み込みシーケンスをオーバーライドしたり<xref:Microsoft.Data.Sqlite.SqliteConnection.CreateCollation%2A>することもできます。</span><span class="sxs-lookup"><span data-stu-id="700b1-117">You can also define your own collating sequences or override the built-in ones using <xref:Microsoft.Data.Sqlite.SqliteConnection.CreateCollation%2A>.</span></span> <span data-ttu-id="700b1-118">次の例は、UNIcode 文字をサポートするために NOCASE 照合順序をオーバーライドする方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="700b1-118">The following example shows overriding the NOCASE collation to support Unicode characters.</span></span> <span data-ttu-id="700b1-119">[完全なサンプル コード](https://github.com/dotnet/docs/blob/master/samples/snippets/standard/data/sqlite/CollationSample/Program.cs)は GitHub で入手できます。</span><span class="sxs-lookup"><span data-stu-id="700b1-119">The [full sample code](https://github.com/dotnet/docs/blob/master/samples/snippets/standard/data/sqlite/CollationSample/Program.cs) is available on GitHub.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/CollationSample/Program.cs?name=snippet_Collation)]

## <a name="like-operator"></a><span data-ttu-id="700b1-120">Like 演算子</span><span class="sxs-lookup"><span data-stu-id="700b1-120">Like operator</span></span>

<span data-ttu-id="700b1-121">SQLite の LIKE 演算子は照合順序を受け入れない。</span><span class="sxs-lookup"><span data-stu-id="700b1-121">The LIKE operator in SQLite doesn't honor collations.</span></span> <span data-ttu-id="700b1-122">既定の実装は、NOCASE 照合順序と同じセマンティクスを持っています。</span><span class="sxs-lookup"><span data-stu-id="700b1-122">The default implementation has the same semantics as the NOCASE collation.</span></span> <span data-ttu-id="700b1-123">ASCII 文字 A から Z の場合は大文字と小文字を区別しないだけです。</span><span class="sxs-lookup"><span data-stu-id="700b1-123">It's only case-insensitive for the ASCII characters A through Z.</span></span>

<span data-ttu-id="700b1-124">LIKE 演算子は、次のプラグマ ステートメントを使用して簡単に大文字と小文字を区別できます。</span><span class="sxs-lookup"><span data-stu-id="700b1-124">You can easily make the LIKE operator case-sensitive by using the following pragma statement:</span></span>

```sql
PRAGMA case_sensitive_like = 1
```

<span data-ttu-id="700b1-125">LIKE 演算子の実装のオーバーライドの詳細については、[ユーザー定義関数](user-defined-functions.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="700b1-125">See [User-defined functions](user-defined-functions.md) for details on overriding the implementation of the LIKE operator.</span></span>

## <a name="see-also"></a><span data-ttu-id="700b1-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="700b1-126">See also</span></span>

* [<span data-ttu-id="700b1-127">ユーザー定義関数</span><span class="sxs-lookup"><span data-stu-id="700b1-127">User-defined functions</span></span>](user-defined-functions.md)
* [<span data-ttu-id="700b1-128">SQL 構文</span><span class="sxs-lookup"><span data-stu-id="700b1-128">SQL Syntax</span></span>](https://www.sqlite.org/lang.html)
