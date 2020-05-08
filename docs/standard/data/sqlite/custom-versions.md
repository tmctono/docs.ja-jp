---
title: カスタム SQLite のバージョン
ms.date: 12/13/2019
description: ネイティブ SQLite ライブラリのカスタム バージョンを使用する方法について説明します。
ms.openlocfilehash: dd27278c1dbe17b12e5067d04d19043bf259b1e8
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746995"
---
# <a name="custom-sqlite-versions"></a><span data-ttu-id="5de3f-103">カスタム SQLite のバージョン</span><span class="sxs-lookup"><span data-stu-id="5de3f-103">Custom SQLite versions</span></span>

<span data-ttu-id="5de3f-104">Microsoft.Data.Sqlite は、SQLitePCLRaw に基づいて作成されています。</span><span class="sxs-lookup"><span data-stu-id="5de3f-104">Microsoft.Data.Sqlite is built on top of SQLitePCLRaw.</span></span> <span data-ttu-id="5de3f-105">カスタム バージョンのネイティブ SQLite を使用するには、バンドルを使用するか、SQLitePCLRaw プロバイダーを構成します。</span><span class="sxs-lookup"><span data-stu-id="5de3f-105">You can use custom versions of the native SQLite library by using a bundle or by configuring a SQLitePCLRaw provider.</span></span>

## <a name="bundles"></a><span data-ttu-id="5de3f-106">バンドル</span><span class="sxs-lookup"><span data-stu-id="5de3f-106">Bundles</span></span>

<span data-ttu-id="5de3f-107">SQLitePCLRaw にはバンドル パッケージが用意されているため、さまざまなプラットフォームで適切な依存関係を簡単に取り込むことができます。</span><span class="sxs-lookup"><span data-stu-id="5de3f-107">SQLitePCLRaw provides bundle packages that make it easy to bring in the right dependencies across different platforms.</span></span>

<span data-ttu-id="5de3f-108">メインの Microsoft.Data.Sqlite パッケージでは、既定で SQLitePCLRaw.bundle_e_sqlite3 が取り込まれます。</span><span class="sxs-lookup"><span data-stu-id="5de3f-108">The main Microsoft.Data.Sqlite package brings in SQLitePCLRaw.bundle_e_sqlite3 by default.</span></span>

<span data-ttu-id="5de3f-109">別のバンドルを使用するには、使用するバンドル パッケージとともに、`Microsoft.Data.Sqlite.Core` パッケージを代わりにインストールします。</span><span class="sxs-lookup"><span data-stu-id="5de3f-109">To use a different bundle, install the `Microsoft.Data.Sqlite.Core` package instead along with the bundle package you want to use.</span></span> <span data-ttu-id="5de3f-110">バンドルは、Microsoft.Data.Sqlite によって自動的に初期化されます。</span><span class="sxs-lookup"><span data-stu-id="5de3f-110">Bundles are automatically initialized by Microsoft.Data.Sqlite.</span></span>

| <span data-ttu-id="5de3f-111">バンドル</span><span class="sxs-lookup"><span data-stu-id="5de3f-111">Bundle</span></span> | <span data-ttu-id="5de3f-112">説明</span><span class="sxs-lookup"><span data-stu-id="5de3f-112">Description</span></span> |
| --- | --- |
| <span data-ttu-id="5de3f-113">SQLitePCLRaw.bundle_e_sqlite3</span><span class="sxs-lookup"><span data-stu-id="5de3f-113">SQLitePCLRaw.bundle_e_sqlite3</span></span> | <span data-ttu-id="5de3f-114">すべてのプラットフォームで同じバージョンの SQLite を提供します。</span><span class="sxs-lookup"><span data-stu-id="5de3f-114">Provides a consistent version of SQLite on all platforms.</span></span> <span data-ttu-id="5de3f-115">FTS4、FTS5、JSON1、R\*Tree 拡張機能を含みます。</span><span class="sxs-lookup"><span data-stu-id="5de3f-115">Includes the FTS4, FTS5, JSON1, and R\*Tree extensions.</span></span> <span data-ttu-id="5de3f-116">既定値です。</span><span class="sxs-lookup"><span data-stu-id="5de3f-116">This is the default.</span></span> |
| <span data-ttu-id="5de3f-117">SQLitePCLRaw.bundle_green</span><span class="sxs-lookup"><span data-stu-id="5de3f-117">SQLitePCLRaw.bundle_green</span></span> | <span data-ttu-id="5de3f-118">Bundle_e_sqlite3 と同じですが、iOS の場合は例外で、システム SQLite ライブラリを使用します。</span><span class="sxs-lookup"><span data-stu-id="5de3f-118">Same as bundle_e_sqlite3, except on iOS where it uses the system SQLite library.</span></span> |
| <span data-ttu-id="5de3f-119">SQLitePCLRaw.bundle_zetetic</span><span class="sxs-lookup"><span data-stu-id="5de3f-119">SQLitePCLRaw.bundle_zetetic</span></span> | <span data-ttu-id="5de3f-120">Zetetic の公式の SQLCipher ビルドを使用します (含まれていません)。</span><span class="sxs-lookup"><span data-stu-id="5de3f-120">Uses the official SQLCipher builds from Zetetic (not included).</span></span> |
| <span data-ttu-id="5de3f-121">SQLitePCLRaw.bundle_winsqlite3</span><span class="sxs-lookup"><span data-stu-id="5de3f-121">SQLitePCLRaw.bundle_winsqlite3</span></span> | <span data-ttu-id="5de3f-122">Windows 10 のシステム SQLite ライブラリである winsqlite3.dll を使用します。</span><span class="sxs-lookup"><span data-stu-id="5de3f-122">Uses winsqlite3.dll, the system SQLite library on Windows 10.</span></span> |
| <span data-ttu-id="5de3f-123">SQLitePCLRaw.bundle_e_sqlcipher</span><span class="sxs-lookup"><span data-stu-id="5de3f-123">SQLitePCLRaw.bundle_e_sqlcipher</span></span> | <span data-ttu-id="5de3f-124">オープン ソースの非公式の SQLCipher ビルドを提供します。</span><span class="sxs-lookup"><span data-stu-id="5de3f-124">Provides an unofficial, open-source build of SQLCipher.</span></span> |

<span data-ttu-id="5de3f-125">たとえば、オープン ソースの非公式の SQLCipher ビルドを使用するには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="5de3f-125">For example, to use the unofficial, open-source build of SQLCipher use the following commands.</span></span>

### <a name="net-core-cli"></a>[<span data-ttu-id="5de3f-126">.NET Core CLI</span><span class="sxs-lookup"><span data-stu-id="5de3f-126">.NET Core CLI</span></span>](#tab/netcore-cli)

```dotnetcli
dotnet add package Microsoft.Data.Sqlite.Core
dotnet add package SQLitePCLRaw.bundle_e_sqlcipher
```

### <a name="visual-studio"></a>[<span data-ttu-id="5de3f-127">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="5de3f-127">Visual Studio</span></span>](#tab/visual-studio)

``` PowerShell
Install-Package Microsoft.Data.Sqlite.Core
Install-Package SQLitePCLRaw.bundle_e_sqlcipher
```

---

## <a name="sqlitepclraw-providers"></a><span data-ttu-id="5de3f-128">SQLitePCLRaw プロバイダー</span><span class="sxs-lookup"><span data-stu-id="5de3f-128">SQLitePCLRaw providers</span></span>

<span data-ttu-id="5de3f-129">`SQLitePCLRaw.provider.dynamic_cdecl` パッケージを利用すると、独自の SQLite ビルドを使用できます。</span><span class="sxs-lookup"><span data-stu-id="5de3f-129">You can use your own build of SQLite by leveraging the `SQLitePCLRaw.provider.dynamic_cdecl` package.</span></span> <span data-ttu-id="5de3f-130">この場合、アプリとともにネイティブ ライブラリをデプロイする必要があります。</span><span class="sxs-lookup"><span data-stu-id="5de3f-130">In this case, you're responsible for deploying the native library with your app.</span></span> <span data-ttu-id="5de3f-131">ただし、アプリとともにネイティブ ライブラリをデプロイする場合の詳細は、使用している .NET プラットフォームとランタイムによって大きく異なります。</span><span class="sxs-lookup"><span data-stu-id="5de3f-131">Note, the details of deploying native libraries with your app vary considerably depending on which .NET platform and runtime you're using.</span></span>

<span data-ttu-id="5de3f-132">まず、IGetFunctionPointer を実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5de3f-132">First, you'll need to implement IGetFunctionPointer.</span></span> <span data-ttu-id="5de3f-133">この実装は、.NET Core では比較的簡単です。</span><span class="sxs-lookup"><span data-stu-id="5de3f-133">The implementation is fairly trivial on .NET Core.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/SystemLibrarySample/Program.cs?name=snippet_NativeLibraryAdapter)]

<span data-ttu-id="5de3f-134">次に、SQLitePCLRaw プロバイダーを構成します。</span><span class="sxs-lookup"><span data-stu-id="5de3f-134">Next, configure the SQLitePCLRaw provider.</span></span> <span data-ttu-id="5de3f-135">これは、アプリで Microsoft.Data.Sqlite が使用される前に行ってください。</span><span class="sxs-lookup"><span data-stu-id="5de3f-135">Ensure this is done before Microsoft.Data.Sqlite is used in your app.</span></span> <span data-ttu-id="5de3f-136">なお、SQLitePCLRaw バンドル パッケージを使用しないようにしてください。プロバイダーがオーバーライドされる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="5de3f-136">Also, avoid using a SQLitePCLRaw bundle package which might override your provider.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/SystemLibrarySample/Program.cs?name=snippet_SetProvider)]
