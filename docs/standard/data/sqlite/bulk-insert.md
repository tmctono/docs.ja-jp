---
title: 一括挿入
ms.date: 12/13/2019
description: データベースに多数の変更を加えるときに使用できる、パフォーマンスに関するヒントです。
ms.openlocfilehash: 9d87d5c8d70f8e70479f9aa02b7802f73b88de9e
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450298"
---
# <a name="bulk-insert"></a><span data-ttu-id="12f8f-103">一括挿入</span><span class="sxs-lookup"><span data-stu-id="12f8f-103">Bulk insert</span></span>

<span data-ttu-id="12f8f-104">SQLite には、データを一括挿入するための特別な方法はありません。</span><span class="sxs-lookup"><span data-stu-id="12f8f-104">SQLite doesn't have any special way to bulk insert data.</span></span> <span data-ttu-id="12f8f-105">データの挿入または更新時に最適なパフォーマンスを得るには、以下を行ってください。</span><span class="sxs-lookup"><span data-stu-id="12f8f-105">To get optimal performance when inserting or updating data, ensure that you do the following:</span></span>

- <span data-ttu-id="12f8f-106">トランザクションの使用。</span><span class="sxs-lookup"><span data-stu-id="12f8f-106">Use a transaction.</span></span>
- <span data-ttu-id="12f8f-107">同じパラメーター化コマンドの再利用。</span><span class="sxs-lookup"><span data-stu-id="12f8f-107">Reuse the same parameterized command.</span></span> <span data-ttu-id="12f8f-108">後続の実行で、最初の実行のコンパイルを再利用します。</span><span class="sxs-lookup"><span data-stu-id="12f8f-108">Subsequent executions will reuse the compilation of the first one.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/BulkInsertSample/Program.cs?name=snippet_BulkInsert)]
