---
title: オンライン バックアップ
ms.date: 12/13/2019
description: SQLite のオンライン バックアップ機能を使用する方法について説明します。
ms.openlocfilehash: d857dcb69f2b2d10b034a0abf222b30c2e20bb41
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/11/2020
ms.locfileid: "75901283"
---
# <a name="online-backup"></a><span data-ttu-id="322d5-103">オンライン バックアップ</span><span class="sxs-lookup"><span data-stu-id="322d5-103">Online backup</span></span>

<span data-ttu-id="322d5-104">SQLite では、アプリの実行中にデータベース ファイルをバックアップできます。</span><span class="sxs-lookup"><span data-stu-id="322d5-104">SQLite can back up database files while the app is running.</span></span> <span data-ttu-id="322d5-105">この機能は、Microsoft.Data.Sqlite で `SqliteConnection` の <xref:Microsoft.Data.Sqlite.SqliteConnection.BackupDatabase%2A> メソッドとして用意されています。</span><span class="sxs-lookup"><span data-stu-id="322d5-105">This functionality is available in Microsoft.Data.Sqlite as the <xref:Microsoft.Data.Sqlite.SqliteConnection.BackupDatabase%2A> method on `SqliteConnection`.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/BackupSample/Program.cs?name=snippet_Backup)]

<span data-ttu-id="322d5-106">現時点では、`BackupDatabase` を使用すると、データベースができるだけ迅速にバックアップされ、他の接続によってそのデータベースへの書き込みが行われないようになります。</span><span class="sxs-lookup"><span data-stu-id="322d5-106">Currently, `BackupDatabase` will back up the database as quickly as possible and blocks other connections from writing to the database.</span></span> <span data-ttu-id="322d5-107">問題 [#13834](https://github.com/dotnet/efcore/issues/13834) では、バックグラウンドでデータベースをバックアップするための代替 API が提供され、他の接続によってバックアップを中断し、データベースに書き込むことができます。</span><span class="sxs-lookup"><span data-stu-id="322d5-107">Issue [#13834](https://github.com/dotnet/efcore/issues/13834) would provide an alternative API to back up the database in the background and allow other connections to interrupt the backup and write to the database.</span></span> <span data-ttu-id="322d5-108">関心がある場合は、この問題に関するフィードバックをお寄せください。</span><span class="sxs-lookup"><span data-stu-id="322d5-108">If you're interested, provide feedback on the issue.</span></span>
