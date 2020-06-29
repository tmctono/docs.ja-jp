---
title: パラメーター
ms.date: 12/13/2019
description: SQL パラメーターの使用方法について説明します。
ms.openlocfilehash: b24610a5cb65e2b24171452acef9bf55b4995431
ms.sourcegitcommit: 5fd4696a3e5791b2a8c449ccffda87f2cc2d4894
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/15/2020
ms.locfileid: "84768951"
---
# <a name="parameters"></a><span data-ttu-id="2085e-103">パラメーター</span><span class="sxs-lookup"><span data-stu-id="2085e-103">Parameters</span></span>

<span data-ttu-id="2085e-104">パラメーターを使用して SQL インジェクション攻撃から保護します。</span><span class="sxs-lookup"><span data-stu-id="2085e-104">Parameters are used to protect against SQL injection attacks.</span></span> <span data-ttu-id="2085e-105">ユーザー入力を SQL ステートメントと連結する代わりにパラメーターを使用することで、入力がリテラル値として扱われ、実行されないようにします。</span><span class="sxs-lookup"><span data-stu-id="2085e-105">Instead of concatenating user input with SQL statements, use parameters to ensure input is only ever treated as a literal value and never executed.</span></span> <span data-ttu-id="2085e-106">SQLite では、通常、SQL ステートメント内でリテラルを使用できるすべての場所でパラメーターを使用できます。</span><span class="sxs-lookup"><span data-stu-id="2085e-106">In SQLite, parameters are typically allowed anywhere a literal is allowed in SQL statements.</span></span>

<span data-ttu-id="2085e-107">パラメーターには、`:`、`@`、または `$` のいずれかのプレフィックスを付けることができます。</span><span class="sxs-lookup"><span data-stu-id="2085e-107">Parameters can be prefixed with either `:`, `@`, or `$`.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/HelloWorldSample/Program.cs?name=snippet_Parameter)]

<span data-ttu-id="2085e-108">.NET 値がどのように SQLite 値にマップされるかについて詳しくは、「[データ型](types.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2085e-108">See [Data types](types.md) for details about how .NET values are mapped to SQLite values.</span></span>

## <a name="truncation"></a><span data-ttu-id="2085e-109">切り捨て</span><span class="sxs-lookup"><span data-stu-id="2085e-109">Truncation</span></span>

<span data-ttu-id="2085e-110">TEXT と BLOB の値を切り捨てるには、<xref:Microsoft.Data.Sqlite.SqliteParameter.Size> プロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="2085e-110">Use the <xref:Microsoft.Data.Sqlite.SqliteParameter.Size> property to truncate TEXT and BLOB values.</span></span>

```csharp
// Truncate name to 30 characters
command.Parameters.AddWithValue("$name", name).Size = 30;
```

## <a name="alternative-types"></a><span data-ttu-id="2085e-111">代替型</span><span class="sxs-lookup"><span data-stu-id="2085e-111">Alternative types</span></span>

<span data-ttu-id="2085e-112">ときにより、代替の SQLite 型を使用する必要が生じる場合があります。</span><span class="sxs-lookup"><span data-stu-id="2085e-112">Sometimes, you may want to use an alternative SQLite type.</span></span> <span data-ttu-id="2085e-113">これを行うには、<xref:Microsoft.Data.Sqlite.SqliteParameter.SqliteType> プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="2085e-113">Do this by setting the <xref:Microsoft.Data.Sqlite.SqliteParameter.SqliteType> property.</span></span>

<span data-ttu-id="2085e-114">使用できる代替型マッピングは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="2085e-114">The following alternative type mappings can be used.</span></span> <span data-ttu-id="2085e-115">既定のマッピングについては、「[データ型](types.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2085e-115">For the default mappings, see [Data types](types.md).</span></span>

| <span data-ttu-id="2085e-116">[値]</span><span class="sxs-lookup"><span data-stu-id="2085e-116">Value</span></span>          | <span data-ttu-id="2085e-117">SqliteType</span><span class="sxs-lookup"><span data-stu-id="2085e-117">SqliteType</span></span> | <span data-ttu-id="2085e-118">Remarks</span><span class="sxs-lookup"><span data-stu-id="2085e-118">Remarks</span></span>          |
| -------------- | ---------- | ---------------- |
| <span data-ttu-id="2085e-119">Char</span><span class="sxs-lookup"><span data-stu-id="2085e-119">Char</span></span>           | <span data-ttu-id="2085e-120">整数型</span><span class="sxs-lookup"><span data-stu-id="2085e-120">Integer</span></span>    | <span data-ttu-id="2085e-121">UTF-16</span><span class="sxs-lookup"><span data-stu-id="2085e-121">UTF-16</span></span>           |
| <span data-ttu-id="2085e-122">DateTime</span><span class="sxs-lookup"><span data-stu-id="2085e-122">DateTime</span></span>       | <span data-ttu-id="2085e-123">Real</span><span class="sxs-lookup"><span data-stu-id="2085e-123">Real</span></span>       | <span data-ttu-id="2085e-124">ユリウス日の値</span><span class="sxs-lookup"><span data-stu-id="2085e-124">Julian day value</span></span> |
| <span data-ttu-id="2085e-125">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="2085e-125">DateTimeOffset</span></span> | <span data-ttu-id="2085e-126">Real</span><span class="sxs-lookup"><span data-stu-id="2085e-126">Real</span></span>       | <span data-ttu-id="2085e-127">ユリウス日の値</span><span class="sxs-lookup"><span data-stu-id="2085e-127">Julian day value</span></span> |
| <span data-ttu-id="2085e-128">GUID</span><span class="sxs-lookup"><span data-stu-id="2085e-128">Guid</span></span>           | <span data-ttu-id="2085e-129">Blob</span><span class="sxs-lookup"><span data-stu-id="2085e-129">Blob</span></span>       |                  |
| <span data-ttu-id="2085e-130">TimeSpan</span><span class="sxs-lookup"><span data-stu-id="2085e-130">TimeSpan</span></span>       | <span data-ttu-id="2085e-131">Real</span><span class="sxs-lookup"><span data-stu-id="2085e-131">Real</span></span>       | <span data-ttu-id="2085e-132">日数</span><span class="sxs-lookup"><span data-stu-id="2085e-132">In days</span></span>          |

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/DateAndTimeSample/Program.cs?name=snippet_SqliteType)]

## <a name="output-parameters"></a><span data-ttu-id="2085e-133">出力パラメーター</span><span class="sxs-lookup"><span data-stu-id="2085e-133">Output parameters</span></span>

<span data-ttu-id="2085e-134">SQLite では、出力パラメーターはサポートされません。</span><span class="sxs-lookup"><span data-stu-id="2085e-134">SQLite doesn't support output parameters.</span></span> <span data-ttu-id="2085e-135">代わりに、クエリ結果の中で値を返します。</span><span class="sxs-lookup"><span data-stu-id="2085e-135">Return values in the query results instead.</span></span>

## <a name="see-also"></a><span data-ttu-id="2085e-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="2085e-136">See also</span></span>

* [<span data-ttu-id="2085e-137">データ型</span><span class="sxs-lookup"><span data-stu-id="2085e-137">Data types</span></span>](types.md)
