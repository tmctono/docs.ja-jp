---
title: 照合順序
ms.date: 12/13/2019
description: カスタム照合シーケンスを作成する方法について説明します。
ms.openlocfilehash: b93c82a4ace154b8293b05effa8f9e9294fa7708
ms.sourcegitcommit: 2514f4e3655081dcfe1b22470c0c28500f952c42
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/18/2020
ms.locfileid: "79506542"
---
# <a name="collation"></a><span data-ttu-id="36056-103">照合順序</span><span class="sxs-lookup"><span data-stu-id="36056-103">Collation</span></span>

<span data-ttu-id="36056-104">照合シーケンスは、順序と等価性を決定するために TEXT 値を比較するときに SQLite によって使用されます。</span><span class="sxs-lookup"><span data-stu-id="36056-104">Collating sequences are used by SQLite when comparing TEXT values to determine order and equality.</span></span> <span data-ttu-id="36056-105">SQL クエリで列を作成するとき、または操作ごとに使用する照合順序を指定できます。</span><span class="sxs-lookup"><span data-stu-id="36056-105">You can specify which collation to use when creating columns or per-operation in SQL queries.</span></span> <span data-ttu-id="36056-106">SQLite には、デフォルトで 3 つの照合シーケンスが含まれています。</span><span class="sxs-lookup"><span data-stu-id="36056-106">SQLite includes three collating sequences by default.</span></span>

| <span data-ttu-id="36056-107">照合順序</span><span class="sxs-lookup"><span data-stu-id="36056-107">Collation</span></span> | <span data-ttu-id="36056-108">説明</span><span class="sxs-lookup"><span data-stu-id="36056-108">Description</span></span>                               |
| --------- | ----------------------------------------- |
| <span data-ttu-id="36056-109">[RTRIM]</span><span class="sxs-lookup"><span data-stu-id="36056-109">RTRIM</span></span>     | <span data-ttu-id="36056-110">末尾の空白を無視します。</span><span class="sxs-lookup"><span data-stu-id="36056-110">Ignores trailing whitespace</span></span>               |
| <span data-ttu-id="36056-111">ノーケース</span><span class="sxs-lookup"><span data-stu-id="36056-111">NOCASE</span></span>    | <span data-ttu-id="36056-112">ASCII 文字 A から Z の大文字と小文字を区別しない</span><span class="sxs-lookup"><span data-stu-id="36056-112">Case-insensitive for ASCII characters A-Z</span></span> |
| <span data-ttu-id="36056-113">BINARY</span><span class="sxs-lookup"><span data-stu-id="36056-113">BINARY</span></span>    | <span data-ttu-id="36056-114">大文字 小文字。</span><span class="sxs-lookup"><span data-stu-id="36056-114">Case-sensitive.</span></span> <span data-ttu-id="36056-115">バイトを直接比較する</span><span class="sxs-lookup"><span data-stu-id="36056-115">Compares bytes directly</span></span>   |

## <a name="custom-collation"></a><span data-ttu-id="36056-116">カスタム照合順序</span><span class="sxs-lookup"><span data-stu-id="36056-116">Custom collation</span></span>

<span data-ttu-id="36056-117">また、独自の照合順序を定義したり、組み込みシーケンスをオーバーライドしたり<xref:Microsoft.Data.Sqlite.SqliteConnection.CreateCollation%2A>することもできます。</span><span class="sxs-lookup"><span data-stu-id="36056-117">You can also define your own collating sequences or override the built-in ones using <xref:Microsoft.Data.Sqlite.SqliteConnection.CreateCollation%2A>.</span></span> <span data-ttu-id="36056-118">次の例は、UNIcode 文字をサポートするために NOCASE 照合順序をオーバーライドする方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="36056-118">The following example shows overriding the NOCASE collation to support Unicode characters.</span></span> <span data-ttu-id="36056-119">[完全なサンプル コード](https://github.com/dotnet/samples/blob/master/snippets/standard/data/sqlite/CollationSample/Program.cs)は GitHub で入手できます。</span><span class="sxs-lookup"><span data-stu-id="36056-119">The [full sample code](https://github.com/dotnet/samples/blob/master/snippets/standard/data/sqlite/CollationSample/Program.cs) is available on GitHub.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/CollationSample/Program.cs?name=snippet_Collation)]

## <a name="like-operator"></a><span data-ttu-id="36056-120">Like 演算子</span><span class="sxs-lookup"><span data-stu-id="36056-120">Like operator</span></span>

<span data-ttu-id="36056-121">SQLite の LIKE 演算子は照合順序を受け入れない。</span><span class="sxs-lookup"><span data-stu-id="36056-121">The LIKE operator in SQLite doesn't honor collations.</span></span> <span data-ttu-id="36056-122">既定の実装は、NOCASE 照合順序と同じセマンティクスを持っています。</span><span class="sxs-lookup"><span data-stu-id="36056-122">The default implementation has the same semantics as the NOCASE collation.</span></span> <span data-ttu-id="36056-123">ASCII 文字 A から Z の場合は大文字と小文字を区別しないだけです。</span><span class="sxs-lookup"><span data-stu-id="36056-123">It's only case-insensitive for the ASCII characters A through Z.</span></span>

<span data-ttu-id="36056-124">LIKE 演算子は、次のプラグマ ステートメントを使用して簡単に大文字と小文字を区別できます。</span><span class="sxs-lookup"><span data-stu-id="36056-124">You can easily make the LIKE operator case-sensitive by using the following pragma statement:</span></span>

```sql
PRAGMA case_sensitive_like = 1
```

<span data-ttu-id="36056-125">LIKE 演算子の実装のオーバーライドの詳細については、[ユーザー定義関数](user-defined-functions.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="36056-125">See [User-defined functions](user-defined-functions.md) for details on overriding the implementation of the LIKE operator.</span></span>

## <a name="see-also"></a><span data-ttu-id="36056-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="36056-126">See also</span></span>

* [<span data-ttu-id="36056-127">ユーザー定義関数</span><span class="sxs-lookup"><span data-stu-id="36056-127">User-defined functions</span></span>](user-defined-functions.md)
* [<span data-ttu-id="36056-128">SQL 構文</span><span class="sxs-lookup"><span data-stu-id="36056-128">SQL Syntax</span></span>](https://www.sqlite.org/lang.html)
