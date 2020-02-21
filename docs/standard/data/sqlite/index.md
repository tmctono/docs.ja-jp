---
title: 概要
ms.date: 12/13/2019
description: Microsoft.Data.Sqlite の概要
ms.openlocfilehash: e84c68f0615f187e8dea7ab87ac917c0ad796a1c
ms.sourcegitcommit: 771c554c84ba38cbd4ac0578324ec4cfc979cf2e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "77543600"
---
# <a name="microsoftdatasqlite-overview"></a><span data-ttu-id="96a79-103">Microsoft.Data.Sqlite 概要</span><span class="sxs-lookup"><span data-stu-id="96a79-103">Microsoft.Data.Sqlite overview</span></span>

<span data-ttu-id="96a79-104">Microsoft.Data.Sqlite は SQLite の軽量 [ADO.NET](../../../framework/data/adonet/index.md) プロバイダーです。</span><span class="sxs-lookup"><span data-stu-id="96a79-104">Microsoft.Data.Sqlite is a lightweight [ADO.NET](../../../framework/data/adonet/index.md) provider for SQLite.</span></span> <span data-ttu-id="96a79-105">SQLite 用の [Entity Framework Core](/ef/core/) プロバイダーはこのライブラリの上に構築されます。</span><span class="sxs-lookup"><span data-stu-id="96a79-105">The [Entity Framework Core](/ef/core/) provider for SQLite is built on top of this library.</span></span> <span data-ttu-id="96a79-106">ただし、非依存で使用したり、他のデータ アクセス ライブラリと共に使用したりすることもできます。</span><span class="sxs-lookup"><span data-stu-id="96a79-106">However, it can also be used independently or with other data access libraries.</span></span>

## <a name="installation"></a><span data-ttu-id="96a79-107">インストール</span><span class="sxs-lookup"><span data-stu-id="96a79-107">Installation</span></span>

<span data-ttu-id="96a79-108">最新の安定バージョンを [NuGet](https://www.nuget.org/packages/Microsoft.Data.Sqlite) で入手できます。</span><span class="sxs-lookup"><span data-stu-id="96a79-108">The latest stable version is available on [NuGet](https://www.nuget.org/packages/Microsoft.Data.Sqlite).</span></span>

### <a name="net-core-cli"></a>[<span data-ttu-id="96a79-109">.NET Core CLI</span><span class="sxs-lookup"><span data-stu-id="96a79-109">.NET Core CLI</span></span>](#tab/netcore-cli)

```dotnetcli
dotnet add package Microsoft.Data.Sqlite
```

### <a name="visual-studio"></a>[<span data-ttu-id="96a79-110">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="96a79-110">Visual Studio</span></span>](#tab/visual-studio)

``` PowerShell
Install-Package Microsoft.Data.Sqlite
```

---

## <a name="usage"></a><span data-ttu-id="96a79-111">使用方法</span><span class="sxs-lookup"><span data-stu-id="96a79-111">Usage</span></span>

<span data-ttu-id="96a79-112">このライブラリによって、接続、コマンド、データ リーダーなどのために共通の ADO.NET 抽象化が実装されます。</span><span class="sxs-lookup"><span data-stu-id="96a79-112">This library implements the common ADO.NET abstractions for connections, commands, data readers, and so on.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/HelloWorldSample/Program.cs?name=snippet_HelloWorld)]

## <a name="see-also"></a><span data-ttu-id="96a79-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="96a79-113">See also</span></span>

* [<span data-ttu-id="96a79-114">接続文字列</span><span class="sxs-lookup"><span data-stu-id="96a79-114">Connection strings</span></span>](connection-strings.md)
* [<span data-ttu-id="96a79-115">API リファレンス</span><span class="sxs-lookup"><span data-stu-id="96a79-115">API Reference</span></span>](/dotnet/api/?view=msdata-sqlite-3.0)
* [<span data-ttu-id="96a79-116">SQL 構文</span><span class="sxs-lookup"><span data-stu-id="96a79-116">SQL Syntax</span></span>](https://www.sqlite.org/lang.html)
