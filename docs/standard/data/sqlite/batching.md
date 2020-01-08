---
title: バッチ
ms.date: 12/13/2019
description: 1つのコマンドで SQL ステートメントのバッチを実行する方法について説明します。
ms.openlocfilehash: 0799784471520bb279db6a4b5879ad30945bdebb
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450310"
---
# <a name="batching"></a><span data-ttu-id="3f244-103">バッチ</span><span class="sxs-lookup"><span data-stu-id="3f244-103">Batching</span></span>

<span data-ttu-id="3f244-104">SQLite は、SQL ステートメントのバッチ処理を1つのコマンドにネイティブではサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="3f244-104">SQLite doesn't natively support batching SQL statements together into a single command.</span></span> <span data-ttu-id="3f244-105">しかし、ネットワークが関係していないので、パフォーマンスを向上させることはできません。</span><span class="sxs-lookup"><span data-stu-id="3f244-105">But because there's no network involved, it wouldn't really help performance anyway.</span></span> <span data-ttu-id="3f244-106">ただし、他の ADO.NET プロバイダーと同じように動作させるために、ステートメントのバッチ処理が便宜的に実装されます。</span><span class="sxs-lookup"><span data-stu-id="3f244-106">Microsoft.Data.Sqlite does, however, implement statement batching as a convenience to make it behave more like other ADO.NET providers.</span></span>

<span data-ttu-id="3f244-107"><xref:System.Data.Common.DbCommand.ExecuteReader%2A?displayProperty=nameWithType>を呼び出すと、ステートメントは、結果を返す最初のステートメントまで実行されます。</span><span class="sxs-lookup"><span data-stu-id="3f244-107">When calling <xref:System.Data.Common.DbCommand.ExecuteReader%2A?displayProperty=nameWithType>, statements are executed up to the first one that returns results.</span></span> <span data-ttu-id="3f244-108"><xref:System.Data.Common.DbDataReader.NextResult%2A?displayProperty=nameWithType> を呼び出すと、ステートメントは、結果を返す次のステートメントまたはバッチの末尾に到達するまで実行を続けます。</span><span class="sxs-lookup"><span data-stu-id="3f244-108">Calling <xref:System.Data.Common.DbDataReader.NextResult%2A?displayProperty=nameWithType> continues executing statements until the next one that returns results or until it reaches the end of the batch.</span></span> <span data-ttu-id="3f244-109"><xref:System.Data.Common.DbDataReader.Dispose%2A?displayProperty=nameWithType> または <xref:System.Data.Common.DbDataReader.Close%2A> を呼び出すと、`NextResult()`によって使用されていない残りのステートメントが実行されます。</span><span class="sxs-lookup"><span data-stu-id="3f244-109">Calling <xref:System.Data.Common.DbDataReader.Dispose%2A?displayProperty=nameWithType> or <xref:System.Data.Common.DbDataReader.Close%2A> executes any remaining statements that haven't been consumed by `NextResult()`.</span></span> <span data-ttu-id="3f244-110">データリーダーを破棄しない場合、ファイナライザーは残りのステートメントを実行しようとしますが、エラーが発生した場合は無視されます。</span><span class="sxs-lookup"><span data-stu-id="3f244-110">If you don't dispose a data reader, the finalizer tries to execute the remaining statements, but any errors it encounters are ignored.</span></span> <span data-ttu-id="3f244-111">このため、バッチを使用するときに `DbDataReader` オブジェクトを破棄することが重要です。</span><span class="sxs-lookup"><span data-stu-id="3f244-111">Because of this, it's important to dispose `DbDataReader` objects when using batches.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/BatchingSample/Program.cs?name=snippet_Batching)]

## <a name="see-also"></a><span data-ttu-id="3f244-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="3f244-112">See also</span></span>

* [<span data-ttu-id="3f244-113">一括挿入</span><span class="sxs-lookup"><span data-stu-id="3f244-113">Bulk Insert</span></span>](bulk-insert.md)
