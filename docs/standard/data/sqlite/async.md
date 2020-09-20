---
title: 非同期の制限事項
ms.date: 09/04/2020
description: 非同期 API の制限事項と、代わりに使用できるいくつかの代替手段について説明します。
ms.openlocfilehash: 8b14fcfeb12d331d8d43ca6d77332007a12ae5dc
ms.sourcegitcommit: 0c3ce6d2e7586d925a30f231f32046b7b3934acb
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/08/2020
ms.locfileid: "89515996"
---
# <a name="async-limitations"></a>非同期の制限事項

SQLite では非同期 I/O はサポートされません。 非同期 ADO.NET メソッドは、Microsoft.Data.Sqlite では同期的に実行されます。 これらを呼び出すのは避けてください。

代わりに、[共有キャッシュ](connection-strings.md#cache)と[先行書き込みログ](https://www.sqlite.org/wal.html)を使用して、パフォーマンスとコンカレンシーを向上させます。

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/AsyncSample/Program.cs?name=snippet_WAL)]

> [!TIP]
> [Entity Framework Core](/ef/core/) を使用して作成されたデータベースでは、先行書き込みログが既定で有効になっています。
