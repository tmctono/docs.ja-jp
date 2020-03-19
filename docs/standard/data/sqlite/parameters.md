---
title: パラメーター
ms.date: 12/13/2019
description: SQL パラメーターの使用方法について説明します。
ms.openlocfilehash: 1d2f818ad392a919faedd785394de28a9c6f56c3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401203"
---
# <a name="parameters"></a><span data-ttu-id="5189b-103">パラメーター</span><span class="sxs-lookup"><span data-stu-id="5189b-103">Parameters</span></span>

<span data-ttu-id="5189b-104">パラメータは、SQL インジェクション攻撃から保護するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="5189b-104">Parameters are used to protect against SQL injection attacks.</span></span> <span data-ttu-id="5189b-105">ユーザー入力を SQL ステートメントと連結する代わりに、入力がリテラル値としてのみ扱われ、決して実行されないようにするためのパラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="5189b-105">Instead of concatenating user input with SQL statements, use parameters to ensure input is only ever treated as a literal value and never executed.</span></span> <span data-ttu-id="5189b-106">SQLite では、通常、SQL ステートメントでリテラルが許可されている場所であれば、パラメーターを使用できます。</span><span class="sxs-lookup"><span data-stu-id="5189b-106">In SQLite, parameters are typically allowed anywhere a literal is allowed in SQL statements.</span></span>

<span data-ttu-id="5189b-107">パラメータの先頭には、 、 `:` `@`、または`$`を付けることができます。</span><span class="sxs-lookup"><span data-stu-id="5189b-107">Parameters can be prefixed with either `:`, `@`, or `$`.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/HelloWorldSample/Program.cs?name=snippet_Parameter)]

<span data-ttu-id="5189b-108">NET 値が SQLite 値にマップされる方法の詳細については、「[データ型](types.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5189b-108">See [Data types](types.md) for details about how .NET values are mapped to SQLite values.</span></span>

## <a name="truncation"></a><span data-ttu-id="5189b-109">切り捨て</span><span class="sxs-lookup"><span data-stu-id="5189b-109">Truncation</span></span>

<span data-ttu-id="5189b-110"><xref:Microsoft.Data.Sqlite.SqliteParameter.Size> TEXT 値と BLOB 値を切り捨てるには、このプロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="5189b-110">Use the <xref:Microsoft.Data.Sqlite.SqliteParameter.Size> property to truncate TEXT and BLOB values.</span></span>

```csharp
// Truncate name to 30 characters
command.Parameters.AddWithValue("$name", name).Length = 30;
```

## <a name="alternative-types"></a><span data-ttu-id="5189b-111">代替タイプ</span><span class="sxs-lookup"><span data-stu-id="5189b-111">Alternative types</span></span>

<span data-ttu-id="5189b-112">代替 SQLite タイプを使用する場合があります。</span><span class="sxs-lookup"><span data-stu-id="5189b-112">Sometimes, you may want to use an alternative SQLite type.</span></span> <span data-ttu-id="5189b-113">プロパティを設定して、<xref:Microsoft.Data.Sqlite.SqliteParameter.SqliteType>これを行います。</span><span class="sxs-lookup"><span data-stu-id="5189b-113">Do this by setting the <xref:Microsoft.Data.Sqlite.SqliteParameter.SqliteType> property.</span></span>

<span data-ttu-id="5189b-114">次の代替型マッピングを使用できます。</span><span class="sxs-lookup"><span data-stu-id="5189b-114">The following alternative type mappings can be used.</span></span> <span data-ttu-id="5189b-115">デフォルトのマッピングについては、[データ型](types.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5189b-115">For the default mappings, see [Data types](types.md).</span></span>

| <span data-ttu-id="5189b-116">Value</span><span class="sxs-lookup"><span data-stu-id="5189b-116">Value</span></span>          | <span data-ttu-id="5189b-117">Sqlite 型</span><span class="sxs-lookup"><span data-stu-id="5189b-117">SqliteType</span></span> | <span data-ttu-id="5189b-118">解説</span><span class="sxs-lookup"><span data-stu-id="5189b-118">Remarks</span></span>          |
| -------------- | ---------- | ---------------- |
| <span data-ttu-id="5189b-119">Char</span><span class="sxs-lookup"><span data-stu-id="5189b-119">Char</span></span>           | <span data-ttu-id="5189b-120">Integer</span><span class="sxs-lookup"><span data-stu-id="5189b-120">Integer</span></span>    | <span data-ttu-id="5189b-121">UTF-16</span><span class="sxs-lookup"><span data-stu-id="5189b-121">UTF-16</span></span>           |
| <span data-ttu-id="5189b-122">DateTime</span><span class="sxs-lookup"><span data-stu-id="5189b-122">DateTime</span></span>       | <span data-ttu-id="5189b-123">Real</span><span class="sxs-lookup"><span data-stu-id="5189b-123">Real</span></span>       | <span data-ttu-id="5189b-124">ユリウス日の値</span><span class="sxs-lookup"><span data-stu-id="5189b-124">Julian day value</span></span> |
| <span data-ttu-id="5189b-125">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="5189b-125">DateTimeOffset</span></span> | <span data-ttu-id="5189b-126">Real</span><span class="sxs-lookup"><span data-stu-id="5189b-126">Real</span></span>       | <span data-ttu-id="5189b-127">ユリウス日の値</span><span class="sxs-lookup"><span data-stu-id="5189b-127">Julian day value</span></span> |
| <span data-ttu-id="5189b-128">Guid</span><span class="sxs-lookup"><span data-stu-id="5189b-128">Guid</span></span>           | <span data-ttu-id="5189b-129">BLOB</span><span class="sxs-lookup"><span data-stu-id="5189b-129">Blob</span></span>       |                  |
| <span data-ttu-id="5189b-130">TimeSpan</span><span class="sxs-lookup"><span data-stu-id="5189b-130">TimeSpan</span></span>       | <span data-ttu-id="5189b-131">Real</span><span class="sxs-lookup"><span data-stu-id="5189b-131">Real</span></span>       | <span data-ttu-id="5189b-132">数日で</span><span class="sxs-lookup"><span data-stu-id="5189b-132">In days</span></span>          |

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/DateAndTimeSample/Program.cs?name=snippet_SqliteType)]

## <a name="output-parameters"></a><span data-ttu-id="5189b-133">出力パラメーター</span><span class="sxs-lookup"><span data-stu-id="5189b-133">Output parameters</span></span>

<span data-ttu-id="5189b-134">SQLite は出力パラメータをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="5189b-134">SQLite doesn't support output parameters.</span></span> <span data-ttu-id="5189b-135">代わりにクエリ結果の値を返します。</span><span class="sxs-lookup"><span data-stu-id="5189b-135">Return values in the query results instead.</span></span>

## <a name="see-also"></a><span data-ttu-id="5189b-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="5189b-136">See also</span></span>

* [<span data-ttu-id="5189b-137">データ型</span><span class="sxs-lookup"><span data-stu-id="5189b-137">Data types</span></span>](types.md)
