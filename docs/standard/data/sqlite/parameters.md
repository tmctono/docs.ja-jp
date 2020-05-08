---
title: パラメーター
ms.date: 12/13/2019
description: SQL パラメーターの使用方法について説明します。
ms.openlocfilehash: 1d2f818ad392a919faedd785394de28a9c6f56c3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401203"
---
# <a name="parameters"></a><span data-ttu-id="72632-103">パラメーター</span><span class="sxs-lookup"><span data-stu-id="72632-103">Parameters</span></span>

<span data-ttu-id="72632-104">パラメーターを使用して SQL インジェクション攻撃から保護します。</span><span class="sxs-lookup"><span data-stu-id="72632-104">Parameters are used to protect against SQL injection attacks.</span></span> <span data-ttu-id="72632-105">ユーザー入力を SQL ステートメントと連結する代わりにパラメーターを使用することで、入力がリテラル値として扱われ、実行されないようにします。</span><span class="sxs-lookup"><span data-stu-id="72632-105">Instead of concatenating user input with SQL statements, use parameters to ensure input is only ever treated as a literal value and never executed.</span></span> <span data-ttu-id="72632-106">SQLite では、通常、SQL ステートメント内でリテラルを使用できるすべての場所でパラメーターを使用できます。</span><span class="sxs-lookup"><span data-stu-id="72632-106">In SQLite, parameters are typically allowed anywhere a literal is allowed in SQL statements.</span></span>

<span data-ttu-id="72632-107">パラメーターには、`:`、`@`、または `$` のいずれかのプレフィックスを付けることができます。</span><span class="sxs-lookup"><span data-stu-id="72632-107">Parameters can be prefixed with either `:`, `@`, or `$`.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/HelloWorldSample/Program.cs?name=snippet_Parameter)]

<span data-ttu-id="72632-108">.NET 値がどのように SQLite 値にマップされるかについて詳しくは、「[データ型](types.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="72632-108">See [Data types](types.md) for details about how .NET values are mapped to SQLite values.</span></span>

## <a name="truncation"></a><span data-ttu-id="72632-109">切り捨て</span><span class="sxs-lookup"><span data-stu-id="72632-109">Truncation</span></span>

<span data-ttu-id="72632-110">TEXT と BLOB の値を切り捨てるには、<xref:Microsoft.Data.Sqlite.SqliteParameter.Size> プロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="72632-110">Use the <xref:Microsoft.Data.Sqlite.SqliteParameter.Size> property to truncate TEXT and BLOB values.</span></span>

```csharp
// Truncate name to 30 characters
command.Parameters.AddWithValue("$name", name).Length = 30;
```

## <a name="alternative-types"></a><span data-ttu-id="72632-111">代替型</span><span class="sxs-lookup"><span data-stu-id="72632-111">Alternative types</span></span>

<span data-ttu-id="72632-112">ときにより、代替の SQLite 型を使用する必要が生じる場合があります。</span><span class="sxs-lookup"><span data-stu-id="72632-112">Sometimes, you may want to use an alternative SQLite type.</span></span> <span data-ttu-id="72632-113">これを行うには、<xref:Microsoft.Data.Sqlite.SqliteParameter.SqliteType> プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="72632-113">Do this by setting the <xref:Microsoft.Data.Sqlite.SqliteParameter.SqliteType> property.</span></span>

<span data-ttu-id="72632-114">使用できる代替型マッピングは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="72632-114">The following alternative type mappings can be used.</span></span> <span data-ttu-id="72632-115">既定のマッピングについては、「[データ型](types.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="72632-115">For the default mappings, see [Data types](types.md).</span></span>

| <span data-ttu-id="72632-116">[値]</span><span class="sxs-lookup"><span data-stu-id="72632-116">Value</span></span>          | <span data-ttu-id="72632-117">SqliteType</span><span class="sxs-lookup"><span data-stu-id="72632-117">SqliteType</span></span> | <span data-ttu-id="72632-118">Remarks</span><span class="sxs-lookup"><span data-stu-id="72632-118">Remarks</span></span>          |
| -------------- | ---------- | ---------------- |
| <span data-ttu-id="72632-119">Char</span><span class="sxs-lookup"><span data-stu-id="72632-119">Char</span></span>           | <span data-ttu-id="72632-120">整数型</span><span class="sxs-lookup"><span data-stu-id="72632-120">Integer</span></span>    | <span data-ttu-id="72632-121">UTF-16</span><span class="sxs-lookup"><span data-stu-id="72632-121">UTF-16</span></span>           |
| <span data-ttu-id="72632-122">DateTime</span><span class="sxs-lookup"><span data-stu-id="72632-122">DateTime</span></span>       | <span data-ttu-id="72632-123">Real</span><span class="sxs-lookup"><span data-stu-id="72632-123">Real</span></span>       | <span data-ttu-id="72632-124">ユリウス日の値</span><span class="sxs-lookup"><span data-stu-id="72632-124">Julian day value</span></span> |
| <span data-ttu-id="72632-125">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="72632-125">DateTimeOffset</span></span> | <span data-ttu-id="72632-126">Real</span><span class="sxs-lookup"><span data-stu-id="72632-126">Real</span></span>       | <span data-ttu-id="72632-127">ユリウス日の値</span><span class="sxs-lookup"><span data-stu-id="72632-127">Julian day value</span></span> |
| <span data-ttu-id="72632-128">GUID</span><span class="sxs-lookup"><span data-stu-id="72632-128">Guid</span></span>           | <span data-ttu-id="72632-129">Blob</span><span class="sxs-lookup"><span data-stu-id="72632-129">Blob</span></span>       |                  |
| <span data-ttu-id="72632-130">TimeSpan</span><span class="sxs-lookup"><span data-stu-id="72632-130">TimeSpan</span></span>       | <span data-ttu-id="72632-131">Real</span><span class="sxs-lookup"><span data-stu-id="72632-131">Real</span></span>       | <span data-ttu-id="72632-132">日数</span><span class="sxs-lookup"><span data-stu-id="72632-132">In days</span></span>          |

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/DateAndTimeSample/Program.cs?name=snippet_SqliteType)]

## <a name="output-parameters"></a><span data-ttu-id="72632-133">出力パラメーター</span><span class="sxs-lookup"><span data-stu-id="72632-133">Output parameters</span></span>

<span data-ttu-id="72632-134">SQLite では、出力パラメーターはサポートされません。</span><span class="sxs-lookup"><span data-stu-id="72632-134">SQLite doesn't support output parameters.</span></span> <span data-ttu-id="72632-135">代わりに、クエリ結果の中で値を返します。</span><span class="sxs-lookup"><span data-stu-id="72632-135">Return values in the query results instead.</span></span>

## <a name="see-also"></a><span data-ttu-id="72632-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="72632-136">See also</span></span>

* [<span data-ttu-id="72632-137">データ型</span><span class="sxs-lookup"><span data-stu-id="72632-137">Data types</span></span>](types.md)
