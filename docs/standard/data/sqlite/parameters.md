---
title: パラメーター
ms.date: 12/13/2019
description: SQL パラメーターの使用方法について説明します。
ms.openlocfilehash: 1d2f818ad392a919faedd785394de28a9c6f56c3
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450424"
---
# <a name="parameters"></a><span data-ttu-id="4727f-103">パラメーター</span><span class="sxs-lookup"><span data-stu-id="4727f-103">Parameters</span></span>

<span data-ttu-id="4727f-104">パラメーターは、SQL インジェクション攻撃から保護するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="4727f-104">Parameters are used to protect against SQL injection attacks.</span></span> <span data-ttu-id="4727f-105">ユーザー入力を SQL ステートメントと連結するのではなく、パラメーターを使用して入力がリテラル値として扱われ、実行されないようにします。</span><span class="sxs-lookup"><span data-stu-id="4727f-105">Instead of concatenating user input with SQL statements, use parameters to ensure input is only ever treated as a literal value and never executed.</span></span> <span data-ttu-id="4727f-106">SQLite では、パラメーターは通常、リテラルが SQL ステートメントで許可されているすべての場所で使用できます。</span><span class="sxs-lookup"><span data-stu-id="4727f-106">In SQLite, parameters are typically allowed anywhere a literal is allowed in SQL statements.</span></span>

<span data-ttu-id="4727f-107">パラメーターには、`:`、`@`、`$`のいずれかのプレフィックスを付けることができます。</span><span class="sxs-lookup"><span data-stu-id="4727f-107">Parameters can be prefixed with either `:`, `@`, or `$`.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/HelloWorldSample/Program.cs?name=snippet_Parameter)]

<span data-ttu-id="4727f-108">.NET 値を SQLite 値にマップする方法の詳細については、「[データ型](types.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4727f-108">See [Data types](types.md) for details about how .NET values are mapped to SQLite values.</span></span>

## <a name="truncation"></a><span data-ttu-id="4727f-109">[切り捨て]</span><span class="sxs-lookup"><span data-stu-id="4727f-109">Truncation</span></span>

<span data-ttu-id="4727f-110">テキストと BLOB の値を切り捨てるには、<xref:Microsoft.Data.Sqlite.SqliteParameter.Size> プロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="4727f-110">Use the <xref:Microsoft.Data.Sqlite.SqliteParameter.Size> property to truncate TEXT and BLOB values.</span></span>

```csharp
// Truncate name to 30 characters
command.Parameters.AddWithValue("$name", name).Length = 30;
```

## <a name="alternative-types"></a><span data-ttu-id="4727f-111">代替型</span><span class="sxs-lookup"><span data-stu-id="4727f-111">Alternative types</span></span>

<span data-ttu-id="4727f-112">場合によっては、代替の SQLite 型を使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="4727f-112">Sometimes, you may want to use an alternative SQLite type.</span></span> <span data-ttu-id="4727f-113">これを行うには、<xref:Microsoft.Data.Sqlite.SqliteParameter.SqliteType> プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="4727f-113">Do this by setting the <xref:Microsoft.Data.Sqlite.SqliteParameter.SqliteType> property.</span></span>

<span data-ttu-id="4727f-114">次の代替の型マッピングを使用できます。</span><span class="sxs-lookup"><span data-stu-id="4727f-114">The following alternative type mappings can be used.</span></span> <span data-ttu-id="4727f-115">既定のマッピングについては、「[データ型](types.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4727f-115">For the default mappings, see [Data types](types.md).</span></span>

| <span data-ttu-id="4727f-116">Value</span><span class="sxs-lookup"><span data-stu-id="4727f-116">Value</span></span>          | <span data-ttu-id="4727f-117">SqliteType</span><span class="sxs-lookup"><span data-stu-id="4727f-117">SqliteType</span></span> | <span data-ttu-id="4727f-118">コメント</span><span class="sxs-lookup"><span data-stu-id="4727f-118">Remarks</span></span>          |
| -------------- | ---------- | ---------------- |
| <span data-ttu-id="4727f-119">Char</span><span class="sxs-lookup"><span data-stu-id="4727f-119">Char</span></span>           | <span data-ttu-id="4727f-120">整数型</span><span class="sxs-lookup"><span data-stu-id="4727f-120">Integer</span></span>    | <span data-ttu-id="4727f-121">UTF-16</span><span class="sxs-lookup"><span data-stu-id="4727f-121">UTF-16</span></span>           |
| <span data-ttu-id="4727f-122">DateTime</span><span class="sxs-lookup"><span data-stu-id="4727f-122">DateTime</span></span>       | <span data-ttu-id="4727f-123">Real</span><span class="sxs-lookup"><span data-stu-id="4727f-123">Real</span></span>       | <span data-ttu-id="4727f-124">ユリウス日の値</span><span class="sxs-lookup"><span data-stu-id="4727f-124">Julian day value</span></span> |
| <span data-ttu-id="4727f-125">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="4727f-125">DateTimeOffset</span></span> | <span data-ttu-id="4727f-126">Real</span><span class="sxs-lookup"><span data-stu-id="4727f-126">Real</span></span>       | <span data-ttu-id="4727f-127">ユリウス日の値</span><span class="sxs-lookup"><span data-stu-id="4727f-127">Julian day value</span></span> |
| <span data-ttu-id="4727f-128">GUID</span><span class="sxs-lookup"><span data-stu-id="4727f-128">Guid</span></span>           | <span data-ttu-id="4727f-129">Blob</span><span class="sxs-lookup"><span data-stu-id="4727f-129">Blob</span></span>       |                  |
| <span data-ttu-id="4727f-130">TimeSpan</span><span class="sxs-lookup"><span data-stu-id="4727f-130">TimeSpan</span></span>       | <span data-ttu-id="4727f-131">Real</span><span class="sxs-lookup"><span data-stu-id="4727f-131">Real</span></span>       | <span data-ttu-id="4727f-132">日数</span><span class="sxs-lookup"><span data-stu-id="4727f-132">In days</span></span>          |

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/DateAndTimeSample/Program.cs?name=snippet_SqliteType)]

## <a name="output-parameters"></a><span data-ttu-id="4727f-133">出力パラメーター</span><span class="sxs-lookup"><span data-stu-id="4727f-133">Output parameters</span></span>

<span data-ttu-id="4727f-134">SQLite では、出力パラメーターはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="4727f-134">SQLite doesn't support output parameters.</span></span> <span data-ttu-id="4727f-135">代わりに、クエリ結果の値を返します。</span><span class="sxs-lookup"><span data-stu-id="4727f-135">Return values in the query results instead.</span></span>

## <a name="see-also"></a><span data-ttu-id="4727f-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="4727f-136">See also</span></span>

* [<span data-ttu-id="4727f-137">データ型</span><span class="sxs-lookup"><span data-stu-id="4727f-137">Data types</span></span>](types.md)
