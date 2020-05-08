---
title: バッチ
ms.date: 12/13/2019
description: 1 つのコマンドで複数の SQL ステートメントをバッチで実行する方法について説明します。
ms.openlocfilehash: 0799784471520bb279db6a4b5879ad30945bdebb
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450310"
---
# <a name="batching"></a><span data-ttu-id="8c297-103">バッチ</span><span class="sxs-lookup"><span data-stu-id="8c297-103">Batching</span></span>

<span data-ttu-id="8c297-104">SQLite では、1 つのコマンドで複数の SQL ステートメントをまとめて実行するバッチ処理はネイティブではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="8c297-104">SQLite doesn't natively support batching SQL statements together into a single command.</span></span> <span data-ttu-id="8c297-105">しかし、ネットワークは関与していないので、いずれにしても実際にパフォーマンスが向上することはありません。</span><span class="sxs-lookup"><span data-stu-id="8c297-105">But because there's no network involved, it wouldn't really help performance anyway.</span></span> <span data-ttu-id="8c297-106">ただし、Microsoft.Data.Sqlite では、他の ADO.NET プロバイダーと同様に動作するよう、便宜的にステートメントのバッチ処理が実装されています。</span><span class="sxs-lookup"><span data-stu-id="8c297-106">Microsoft.Data.Sqlite does, however, implement statement batching as a convenience to make it behave more like other ADO.NET providers.</span></span>

<span data-ttu-id="8c297-107"><xref:System.Data.Common.DbCommand.ExecuteReader%2A?displayProperty=nameWithType> を呼び出すと、ステートメントは、結果を返す最初のステートメントまで実行されます。</span><span class="sxs-lookup"><span data-stu-id="8c297-107">When calling <xref:System.Data.Common.DbCommand.ExecuteReader%2A?displayProperty=nameWithType>, statements are executed up to the first one that returns results.</span></span> <span data-ttu-id="8c297-108"><xref:System.Data.Common.DbDataReader.NextResult%2A?displayProperty=nameWithType> を呼び出すと、結果を返す次のステートメントまで、またはバッチの終わりに達するまで、ステートメントの実行が続けられます。</span><span class="sxs-lookup"><span data-stu-id="8c297-108">Calling <xref:System.Data.Common.DbDataReader.NextResult%2A?displayProperty=nameWithType> continues executing statements until the next one that returns results or until it reaches the end of the batch.</span></span> <span data-ttu-id="8c297-109"><xref:System.Data.Common.DbDataReader.Dispose%2A?displayProperty=nameWithType> または <xref:System.Data.Common.DbDataReader.Close%2A> を呼び出すと、`NextResult()` によって使用されていない残りのステートメントがすべて実行されます。</span><span class="sxs-lookup"><span data-stu-id="8c297-109">Calling <xref:System.Data.Common.DbDataReader.Dispose%2A?displayProperty=nameWithType> or <xref:System.Data.Common.DbDataReader.Close%2A> executes any remaining statements that haven't been consumed by `NextResult()`.</span></span> <span data-ttu-id="8c297-110">データ リーダーを破棄しない場合、ファイナライザーによって残りのステートメントの実行が試みられますが、エラーが発生しても無視されます。</span><span class="sxs-lookup"><span data-stu-id="8c297-110">If you don't dispose a data reader, the finalizer tries to execute the remaining statements, but any errors it encounters are ignored.</span></span> <span data-ttu-id="8c297-111">このため、バッチを使用するときは `DbDataReader` オブジェクトを破棄することが重要です。</span><span class="sxs-lookup"><span data-stu-id="8c297-111">Because of this, it's important to dispose `DbDataReader` objects when using batches.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/BatchingSample/Program.cs?name=snippet_Batching)]

## <a name="see-also"></a><span data-ttu-id="8c297-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="8c297-112">See also</span></span>

* [<span data-ttu-id="8c297-113">一括挿入</span><span class="sxs-lookup"><span data-stu-id="8c297-113">Bulk Insert</span></span>](bulk-insert.md)
