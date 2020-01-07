---
title: オンライン バックアップ。
ms.date: 12/13/2019
description: SQLite のオンラインバックアップ機能を使用する方法について説明します。
ms.openlocfilehash: 885aa2c5555b58deb2551c0a4e6933742a093457
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450346"
---
# <a name="online-backup"></a><span data-ttu-id="14fbd-103">オンライン バックアップ。</span><span class="sxs-lookup"><span data-stu-id="14fbd-103">Online backup</span></span>

<span data-ttu-id="14fbd-104">SQLite は、アプリの実行中にデータベースファイルをバックアップできます。</span><span class="sxs-lookup"><span data-stu-id="14fbd-104">SQLite can back up database files while the app is running.</span></span> <span data-ttu-id="14fbd-105">この機能は、`SqliteConnection`の <xref:Microsoft.Data.Sqlite.SqliteConnection.BackupDatabase%2A> メソッドとして、Microsoft. Data. Sqlite で使用できます。</span><span class="sxs-lookup"><span data-stu-id="14fbd-105">This functionality is available in Microsoft.Data.Sqlite as the <xref:Microsoft.Data.Sqlite.SqliteConnection.BackupDatabase%2A> method on `SqliteConnection`.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/BackupSample/Program.cs?name=snippet_Backup)]

<span data-ttu-id="14fbd-106">現時点では、`BackupDatabase` はできるだけ早くデータベースをバックアップし、他の接続がデータベースへの書き込みをブロックします。</span><span class="sxs-lookup"><span data-stu-id="14fbd-106">Currently, `BackupDatabase` will back up the database as quickly as possible and blocks other connections from writing to the database.</span></span> <span data-ttu-id="14fbd-107">問題[#13834](https://github.com/aspnet/EntityFrameworkCore/issues/13834)は、データベースをバックグラウンドでバックアップするための代替 API を提供し、他の接続がバックアップとデータベースへの書き込みを中断できるようにします。</span><span class="sxs-lookup"><span data-stu-id="14fbd-107">Issue [#13834](https://github.com/aspnet/EntityFrameworkCore/issues/13834) would provide an alternative API to back up the database in the background and allow other connections to interrupt the backup and write to the database.</span></span> <span data-ttu-id="14fbd-108">関心がある場合は、問題に関するフィードバックをお寄せください。</span><span class="sxs-lookup"><span data-stu-id="14fbd-108">If you're interested, provide feedback on the issue.</span></span>
