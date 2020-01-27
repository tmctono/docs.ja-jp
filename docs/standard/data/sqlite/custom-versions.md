---
title: カスタム SQLite のバージョン
ms.date: 12/13/2019
description: ネイティブ SQLite ライブラリのカスタムバージョンを使用する方法について説明します。
ms.openlocfilehash: dd27278c1dbe17b12e5067d04d19043bf259b1e8
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746995"
---
# <a name="custom-sqlite-versions"></a><span data-ttu-id="96227-103">カスタム SQLite のバージョン</span><span class="sxs-lookup"><span data-stu-id="96227-103">Custom SQLite versions</span></span>

<span data-ttu-id="96227-104">SQLitePCLRaw は、上に構築されています。</span><span class="sxs-lookup"><span data-stu-id="96227-104">Microsoft.Data.Sqlite is built on top of SQLitePCLRaw.</span></span> <span data-ttu-id="96227-105">バンドルを使用するか、SQLitePCLRaw プロバイダーを構成することによって、ネイティブ SQLite ライブラリのカスタムバージョンを使用できます。</span><span class="sxs-lookup"><span data-stu-id="96227-105">You can use custom versions of the native SQLite library by using a bundle or by configuring a SQLitePCLRaw provider.</span></span>

## <a name="bundles"></a><span data-ttu-id="96227-106">同梱</span><span class="sxs-lookup"><span data-stu-id="96227-106">Bundles</span></span>

<span data-ttu-id="96227-107">SQLitePCLRaw にはバンドルパッケージが用意されているため、さまざまなプラットフォーム間で適切な依存関係を簡単に取り込むことができます。</span><span class="sxs-lookup"><span data-stu-id="96227-107">SQLitePCLRaw provides bundle packages that make it easy to bring in the right dependencies across different platforms.</span></span>

<span data-ttu-id="96227-108">メインの SQLitePCLRaw パッケージは、既定で bundle_e_sqlite3 になります。</span><span class="sxs-lookup"><span data-stu-id="96227-108">The main Microsoft.Data.Sqlite package brings in SQLitePCLRaw.bundle_e_sqlite3 by default.</span></span>

<span data-ttu-id="96227-109">別のバンドルを使用するには、使用するバンドルパッケージと共に `Microsoft.Data.Sqlite.Core` パッケージをインストールします。</span><span class="sxs-lookup"><span data-stu-id="96227-109">To use a different bundle, install the `Microsoft.Data.Sqlite.Core` package instead along with the bundle package you want to use.</span></span> <span data-ttu-id="96227-110">バンドルは、自動的に Microsoft. Data. Sqlite によって初期化されます。</span><span class="sxs-lookup"><span data-stu-id="96227-110">Bundles are automatically initialized by Microsoft.Data.Sqlite.</span></span>

| <span data-ttu-id="96227-111">・</span><span class="sxs-lookup"><span data-stu-id="96227-111">Bundle</span></span> | <span data-ttu-id="96227-112">説明</span><span class="sxs-lookup"><span data-stu-id="96227-112">Description</span></span> |
| --- | --- |
| <span data-ttu-id="96227-113">Bundle_e_sqlite3 SQLitePCLRaw</span><span class="sxs-lookup"><span data-stu-id="96227-113">SQLitePCLRaw.bundle_e_sqlite3</span></span> | <span data-ttu-id="96227-114">すべてのプラットフォームで SQLite の一貫性のあるバージョンを提供します。</span><span class="sxs-lookup"><span data-stu-id="96227-114">Provides a consistent version of SQLite on all platforms.</span></span> <span data-ttu-id="96227-115">には、FTS4、FTS5、JSON1、および R \* ツリー拡張が含まれています。</span><span class="sxs-lookup"><span data-stu-id="96227-115">Includes the FTS4, FTS5, JSON1, and R\*Tree extensions.</span></span> <span data-ttu-id="96227-116">これは既定です。</span><span class="sxs-lookup"><span data-stu-id="96227-116">This is the default.</span></span> |
| <span data-ttu-id="96227-117">Bundle_green SQLitePCLRaw</span><span class="sxs-lookup"><span data-stu-id="96227-117">SQLitePCLRaw.bundle_green</span></span> | <span data-ttu-id="96227-118">Bundle_e_sqlite3 と同じですが、システム SQLite ライブラリを使用する iOS を除きます。</span><span class="sxs-lookup"><span data-stu-id="96227-118">Same as bundle_e_sqlite3, except on iOS where it uses the system SQLite library.</span></span> |
| <span data-ttu-id="96227-119">Bundle_zetetic SQLitePCLRaw</span><span class="sxs-lookup"><span data-stu-id="96227-119">SQLitePCLRaw.bundle_zetetic</span></span> | <span data-ttu-id="96227-120">では、Zetetic (含まれていません) からの公式の SQLCipher ビルドが使用されます。</span><span class="sxs-lookup"><span data-stu-id="96227-120">Uses the official SQLCipher builds from Zetetic (not included).</span></span> |
| <span data-ttu-id="96227-121">Bundle_winsqlite3 SQLitePCLRaw</span><span class="sxs-lookup"><span data-stu-id="96227-121">SQLitePCLRaw.bundle_winsqlite3</span></span> | <span data-ttu-id="96227-122">Windows 10 のシステム SQLite ライブラリである winsqlite3 を使用します。</span><span class="sxs-lookup"><span data-stu-id="96227-122">Uses winsqlite3.dll, the system SQLite library on Windows 10.</span></span> |
| <span data-ttu-id="96227-123">Bundle_e_sqlcipher SQLitePCLRaw</span><span class="sxs-lookup"><span data-stu-id="96227-123">SQLitePCLRaw.bundle_e_sqlcipher</span></span> | <span data-ttu-id="96227-124">SQLCipher の非公式なオープンソースビルドを提供します。</span><span class="sxs-lookup"><span data-stu-id="96227-124">Provides an unofficial, open-source build of SQLCipher.</span></span> |

<span data-ttu-id="96227-125">たとえば、非公式のオープンソースの SQLCipher ビルドを使用するには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="96227-125">For example, to use the unofficial, open-source build of SQLCipher use the following commands.</span></span>

### <a name="net-core-clitabnetcore-cli"></a>[<span data-ttu-id="96227-126">.NET Core CLI</span><span class="sxs-lookup"><span data-stu-id="96227-126">.NET Core CLI</span></span>](#tab/netcore-cli)

```dotnetcli
dotnet add package Microsoft.Data.Sqlite.Core
dotnet add package SQLitePCLRaw.bundle_e_sqlcipher
```

### <a name="visual-studiotabvisual-studio"></a>[<span data-ttu-id="96227-127">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="96227-127">Visual Studio</span></span>](#tab/visual-studio)

``` PowerShell
Install-Package Microsoft.Data.Sqlite.Core
Install-Package SQLitePCLRaw.bundle_e_sqlcipher
```

---

## <a name="sqlitepclraw-providers"></a><span data-ttu-id="96227-128">SQLitePCLRaw プロバイダー</span><span class="sxs-lookup"><span data-stu-id="96227-128">SQLitePCLRaw providers</span></span>

<span data-ttu-id="96227-129">`SQLitePCLRaw.provider.dynamic_cdecl` パッケージを利用することで、独自の SQLite ビルドを使用できます。</span><span class="sxs-lookup"><span data-stu-id="96227-129">You can use your own build of SQLite by leveraging the `SQLitePCLRaw.provider.dynamic_cdecl` package.</span></span> <span data-ttu-id="96227-130">この場合、アプリと共にネイティブライブラリをデプロイする必要があります。</span><span class="sxs-lookup"><span data-stu-id="96227-130">In this case, you're responsible for deploying the native library with your app.</span></span> <span data-ttu-id="96227-131">アプリでのネイティブライブラリのデプロイの詳細は、使用している .NET プラットフォームとランタイムによって大きく異なります。</span><span class="sxs-lookup"><span data-stu-id="96227-131">Note, the details of deploying native libraries with your app vary considerably depending on which .NET platform and runtime you're using.</span></span>

<span data-ttu-id="96227-132">まず、IGetFunctionPointer を実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="96227-132">First, you'll need to implement IGetFunctionPointer.</span></span> <span data-ttu-id="96227-133">.NET Core では、実装は非常に簡単です。</span><span class="sxs-lookup"><span data-stu-id="96227-133">The implementation is fairly trivial on .NET Core.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/SystemLibrarySample/Program.cs?name=snippet_NativeLibraryAdapter)]

<span data-ttu-id="96227-134">次に、SQLitePCLRaw プロバイダーを構成します。</span><span class="sxs-lookup"><span data-stu-id="96227-134">Next, configure the SQLitePCLRaw provider.</span></span> <span data-ttu-id="96227-135">これは、アプリで使用される前に実行されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="96227-135">Ensure this is done before Microsoft.Data.Sqlite is used in your app.</span></span> <span data-ttu-id="96227-136">また、プロバイダーをオーバーライドする可能性のある SQLitePCLRaw バンドルパッケージを使用しないようにしてください。</span><span class="sxs-lookup"><span data-stu-id="96227-136">Also, avoid using a SQLitePCLRaw bundle package which might override your provider.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/SystemLibrarySample/Program.cs?name=snippet_SetProvider)]
