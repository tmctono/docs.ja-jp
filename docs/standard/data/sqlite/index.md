---
title: 概要
ms.date: 12/13/2019
description: Microsoft.Data.Sqlite の概要
ms.openlocfilehash: a5dc1366cc0ddfcd5501e26bf2a994456bcd5d98
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/25/2019
ms.locfileid: "75353467"
---
# <a name="microsoftdatasqlite-overview"></a><span data-ttu-id="25b5a-103">Microsoft.Data.Sqlite 概要</span><span class="sxs-lookup"><span data-stu-id="25b5a-103">Microsoft.Data.Sqlite overview</span></span>

<span data-ttu-id="25b5a-104">Microsoft.Data.Sqlite は SQLite の軽量 [ADO.NET](../../../framework/data/adonet/index.md) プロバイダーです。</span><span class="sxs-lookup"><span data-stu-id="25b5a-104">Microsoft.Data.Sqlite is a lightweight [ADO.NET](../../../framework/data/adonet/index.md) provider for SQLite.</span></span> <span data-ttu-id="25b5a-105">SQLite 用の [Entity Framework Core](/ef/core/) プロバイダーはこのライブラリの上に構築されます。</span><span class="sxs-lookup"><span data-stu-id="25b5a-105">The [Entity Framework Core](/ef/core/) provider for SQLite is built on top of this library.</span></span> <span data-ttu-id="25b5a-106">ただし、非依存で使用したり、他のデータ アクセス ライブラリと共に使用したりすることもできます。</span><span class="sxs-lookup"><span data-stu-id="25b5a-106">However, it can also be used independently or with other data access libraries.</span></span>

## <a name="installation"></a><span data-ttu-id="25b5a-107">インストール</span><span class="sxs-lookup"><span data-stu-id="25b5a-107">Installation</span></span>

<span data-ttu-id="25b5a-108">最新の安定バージョンを [NuGet](https://www.nuget.org/packages/Microsoft.Data.Sqlite) で入手できます。</span><span class="sxs-lookup"><span data-stu-id="25b5a-108">The latest stable version is available on [NuGet](https://www.nuget.org/packages/Microsoft.Data.Sqlite).</span></span>

### <a name="net-core-clitabnetcore-cli"></a>[<span data-ttu-id="25b5a-109">.NET Core CLI</span><span class="sxs-lookup"><span data-stu-id="25b5a-109">.NET Core CLI</span></span>](#tab/netcore-cli)

```dotnetcli
dotnet add package Microsoft.Data.Sqlite
```

### <a name="visual-studiotabvisual-studio"></a>[<span data-ttu-id="25b5a-110">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="25b5a-110">Visual Studio</span></span>](#tab/visual-studio)

``` PowerShell
Install-Package Microsoft.Data.Sqlite
```

---

## <a name="usage"></a><span data-ttu-id="25b5a-111">使用方法</span><span class="sxs-lookup"><span data-stu-id="25b5a-111">Usage</span></span>

<span data-ttu-id="25b5a-112">このライブラリによって、接続、コマンド、データ リーダーなどのために共通の ADO.NET 抽象化が実装されます。</span><span class="sxs-lookup"><span data-stu-id="25b5a-112">This library implements the common ADO.NET abstractions for connections, commands, data readers, and so on.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/HelloWorldSample/Program.cs?name=snippet_HelloWorld)]

## <a name="see-also"></a><span data-ttu-id="25b5a-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="25b5a-113">See also</span></span>

* [<span data-ttu-id="25b5a-114">接続文字列</span><span class="sxs-lookup"><span data-stu-id="25b5a-114">Connection strings</span></span>](connection-strings.md)
* [<span data-ttu-id="25b5a-115">API リファレンス</span><span class="sxs-lookup"><span data-stu-id="25b5a-115">API Reference</span></span>](/dotnet/api/?view=msdata-sqlite-3.0.0)
* [<span data-ttu-id="25b5a-116">SQL 構文</span><span class="sxs-lookup"><span data-stu-id="25b5a-116">SQL Syntax</span></span>](https://www.sqlite.org/lang.html)
