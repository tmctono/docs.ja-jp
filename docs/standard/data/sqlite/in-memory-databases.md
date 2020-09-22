---
title: インメモリ データベース
ms.date: 12/13/2019
description: インメモリ SQLite データベースの使用方法について説明します。
ms.openlocfilehash: fbda5787d95a9ce462752b985f847af0b0551fa6
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/15/2020
ms.locfileid: "90555368"
---
# <a name="in-memory-databases"></a>インメモリ データベース

SQLite インメモリ データベースは、ディスク上ではなく、メモリ内に全体が格納されるデータベースです。 インメモリ データベースを作成するには、特殊なデータ ソース ファイル名 `:memory:` を使用します。 接続が閉じられると、データベースは削除されます。 `:memory:` を使用すると、各接続で独自のデータベースが作成されます。

```connectionstring
Data Source=:memory:
```

## <a name="shareable-in-memory-databases"></a>共有可能なインメモリ データベース

接続文字列で `Mode=Memory` と `Cache=Shared` を使用すると、インメモリ データベースを複数の接続間で共有できます。 インメモリ データベースに名前を付けるには、`Data Source` キーワードを使用します。 同じ名前を使用する接続文字列では、同じインメモリ データベースがアクセスされます。 データベースへの 1 つ以上の接続が開いたままになっている間は、そのデータベースは保持されます。 これを示す[サンプル](https://github.com/dotnet/docs/blob/master/samples/snippets/standard/data/sqlite/InMemorySample/Program.cs)を GitHub で入手できます。

```connectionstring
Data Source=InMemorySample;Mode=Memory;Cache=Shared
```
