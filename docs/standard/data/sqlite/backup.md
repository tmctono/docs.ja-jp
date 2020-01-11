---
title: オンライン バックアップ。
ms.date: 12/13/2019
description: SQLite のオンラインバックアップ機能を使用する方法について説明します。
ms.openlocfilehash: d857dcb69f2b2d10b034a0abf222b30c2e20bb41
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/11/2020
ms.locfileid: "75901283"
---
# <a name="online-backup"></a><span data-ttu-id="ae6c5-103">オンライン バックアップ。</span><span class="sxs-lookup"><span data-stu-id="ae6c5-103">Online backup</span></span>

<span data-ttu-id="ae6c5-104">SQLite は、アプリの実行中にデータベースファイルをバックアップできます。</span><span class="sxs-lookup"><span data-stu-id="ae6c5-104">SQLite can back up database files while the app is running.</span></span> <span data-ttu-id="ae6c5-105">この機能は、`SqliteConnection`の <xref:Microsoft.Data.Sqlite.SqliteConnection.BackupDatabase%2A> メソッドとして、Microsoft. Data. Sqlite で使用できます。</span><span class="sxs-lookup"><span data-stu-id="ae6c5-105">This functionality is available in Microsoft.Data.Sqlite as the <xref:Microsoft.Data.Sqlite.SqliteConnection.BackupDatabase%2A> method on `SqliteConnection`.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/BackupSample/Program.cs?name=snippet_Backup)]

<span data-ttu-id="ae6c5-106">現時点では、`BackupDatabase` はできるだけ早くデータベースをバックアップし、他の接続がデータベースへの書き込みをブロックします。</span><span class="sxs-lookup"><span data-stu-id="ae6c5-106">Currently, `BackupDatabase` will back up the database as quickly as possible and blocks other connections from writing to the database.</span></span> <span data-ttu-id="ae6c5-107">問題[#13834](https://github.com/dotnet/efcore/issues/13834)は、データベースをバックグラウンドでバックアップするための代替 API を提供し、他の接続がバックアップとデータベースへの書き込みを中断できるようにします。</span><span class="sxs-lookup"><span data-stu-id="ae6c5-107">Issue [#13834](https://github.com/dotnet/efcore/issues/13834) would provide an alternative API to back up the database in the background and allow other connections to interrupt the backup and write to the database.</span></span> <span data-ttu-id="ae6c5-108">関心がある場合は、問題に関するフィードバックをお寄せください。</span><span class="sxs-lookup"><span data-stu-id="ae6c5-108">If you're interested, provide feedback on the issue.</span></span>
