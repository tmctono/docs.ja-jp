---
title: カスタム SQLite のバージョン
ms.date: 05/14/2020
description: ネイティブ SQLite ライブラリのカスタム バージョンを使用する方法について説明します。
ms.openlocfilehash: 15db10db26bc7c5017313ca020a0e1e528ba207a
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/16/2020
ms.locfileid: "83440838"
---
# <a name="custom-sqlite-versions"></a><span data-ttu-id="c4e59-103">カスタム SQLite のバージョン</span><span class="sxs-lookup"><span data-stu-id="c4e59-103">Custom SQLite versions</span></span>

<span data-ttu-id="c4e59-104">`Microsoft.Data.Sqlite` は、`SQLitePCLRaw` に基づいています。</span><span class="sxs-lookup"><span data-stu-id="c4e59-104">`Microsoft.Data.Sqlite` is built on top of `SQLitePCLRaw`.</span></span> <span data-ttu-id="c4e59-105">カスタム バージョンのネイティブ SQLite ライブラリを使用するには、バンドルを使用するか、`SQLitePCLRaw` プロバイダーを構成します。</span><span class="sxs-lookup"><span data-stu-id="c4e59-105">You can use custom versions of the native SQLite library by using a bundle or by configuring a `SQLitePCLRaw` provider.</span></span>

## <a name="bundles"></a><span data-ttu-id="c4e59-106">バンドル</span><span class="sxs-lookup"><span data-stu-id="c4e59-106">Bundles</span></span>

<span data-ttu-id="c4e59-107">`SQLitePCLRaw` には利便性に基づくバンドル パッケージが用意されているため、さまざまなプラットフォームで適切な依存関係を簡単に取り込むことができます。</span><span class="sxs-lookup"><span data-stu-id="c4e59-107">`SQLitePCLRaw` provides convenience-based bundle packages, that make it easy to bring in the right dependencies across different platforms.</span></span> <span data-ttu-id="c4e59-108">メインの `Microsoft.Data.Sqlite` パッケージでは、既定で `SQLitePCLRaw.bundle_e_sqlite3` が取り込まれます。</span><span class="sxs-lookup"><span data-stu-id="c4e59-108">The main `Microsoft.Data.Sqlite` package brings in `SQLitePCLRaw.bundle_e_sqlite3` by default.</span></span> <span data-ttu-id="c4e59-109">別のバンドルを使用するには、使用するバンドル パッケージとともに、`Microsoft.Data.Sqlite.Core` パッケージを代わりにインストールします。</span><span class="sxs-lookup"><span data-stu-id="c4e59-109">To use a different bundle, install the `Microsoft.Data.Sqlite.Core` package instead along with the bundle package you want to use.</span></span> <span data-ttu-id="c4e59-110">バンドルは、`Microsoft.Data.Sqlite` によって自動的に初期化されます。</span><span class="sxs-lookup"><span data-stu-id="c4e59-110">Bundles are automatically initialized by `Microsoft.Data.Sqlite`.</span></span>

| <span data-ttu-id="c4e59-111">バンドル</span><span class="sxs-lookup"><span data-stu-id="c4e59-111">Bundle</span></span> | <span data-ttu-id="c4e59-112">説明</span><span class="sxs-lookup"><span data-stu-id="c4e59-112">Description</span></span> |
|--|--|
| [<span data-ttu-id="c4e59-113">SQLitePCLRaw.bundle_e_sqlite3</span><span class="sxs-lookup"><span data-stu-id="c4e59-113">SQLitePCLRaw.bundle_e_sqlite3</span></span>](https://www.nuget.org/packages/SQLitePCLRaw.bundle_e_sqlite3) | <span data-ttu-id="c4e59-114">すべてのプラットフォームで同じバージョンの SQLite を提供します。</span><span class="sxs-lookup"><span data-stu-id="c4e59-114">Provides a consistent version of SQLite on all platforms.</span></span> <span data-ttu-id="c4e59-115">FTS4、FTS5、JSON1、R\*Tree 拡張機能を含みます。</span><span class="sxs-lookup"><span data-stu-id="c4e59-115">Includes the FTS4, FTS5, JSON1, and R\*Tree extensions.</span></span> <span data-ttu-id="c4e59-116">既定値です。</span><span class="sxs-lookup"><span data-stu-id="c4e59-116">This is the default.</span></span> |
| [<span data-ttu-id="c4e59-117">SQLitePCLRaw.bundle_e_sqlcipher</span><span class="sxs-lookup"><span data-stu-id="c4e59-117">SQLitePCLRaw.bundle_e_sqlcipher</span></span>](https://www.nuget.org/packages/SQLitePCLRaw.bundle_e_sqlcipher) | <span data-ttu-id="c4e59-118">オープン ソースの非公式の `SQLCipher` ビルドを提供します。</span><span class="sxs-lookup"><span data-stu-id="c4e59-118">Provides an unofficial, open-source build of `SQLCipher`.</span></span> |
| [<span data-ttu-id="c4e59-119">SQLitePCLRaw.bundle_green</span><span class="sxs-lookup"><span data-stu-id="c4e59-119">SQLitePCLRaw.bundle_green</span></span>](https://www.nuget.org/packages/SQLitePCLRaw.bundle_green) | <span data-ttu-id="c4e59-120">`bundle_e_sqlite3` と同じですが、iOS の場合はシステム SQLite ライブラリが使用されます。</span><span class="sxs-lookup"><span data-stu-id="c4e59-120">Same as `bundle_e_sqlite3`, except on iOS where it uses the system SQLite library.</span></span> |
| [<span data-ttu-id="c4e59-121">SQLitePCLRaw.bundle_winsqlite3</span><span class="sxs-lookup"><span data-stu-id="c4e59-121">SQLitePCLRaw.bundle_winsqlite3</span></span>](https://www.nuget.org/packages/SQLitePCLRaw.bundle_winsqlite3) | <span data-ttu-id="c4e59-122">Windows 10 のシステム SQLite ライブラリである `winsqlite3.dll` が使用されます。</span><span class="sxs-lookup"><span data-stu-id="c4e59-122">Uses `winsqlite3.dll`, the system SQLite library on Windows 10.</span></span> |
| [<span data-ttu-id="c4e59-123">SQLitePCLRaw.bundle_zetetic</span><span class="sxs-lookup"><span data-stu-id="c4e59-123">SQLitePCLRaw.bundle_zetetic</span></span>](https://www.nuget.org/packages/SQLitePCLRaw.bundle_zetetic) | <span data-ttu-id="c4e59-124">Zetetic の公式の `SQLCipher` ビルドが使用されます (含まれていません)。</span><span class="sxs-lookup"><span data-stu-id="c4e59-124">Uses the official `SQLCipher` builds from Zetetic (not included).</span></span> |

<span data-ttu-id="c4e59-125">たとえば、オープン ソースの非公式の `SQLCipher` ビルドを使用するには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="c4e59-125">For example, to use the unofficial, open-source build of `SQLCipher` use the following commands.</span></span>

### <a name="net-core-cli"></a>[<span data-ttu-id="c4e59-126">.NET Core CLI</span><span class="sxs-lookup"><span data-stu-id="c4e59-126">.NET Core CLI</span></span>](#tab/netcore-cli)

```dotnetcli
dotnet add package Microsoft.Data.Sqlite.Core
dotnet add package SQLitePCLRaw.bundle_e_sqlcipher
```

### <a name="visual-studio"></a>[<span data-ttu-id="c4e59-127">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="c4e59-127">Visual Studio</span></span>](#tab/visual-studio)

``` PowerShell
Install-Package Microsoft.Data.Sqlite.Core
Install-Package SQLitePCLRaw.bundle_e_sqlcipher
```

---

## <a name="sqlitepclraw-available-providers"></a><span data-ttu-id="c4e59-128">SQLitePCLRaw を利用できるプロバイダー</span><span class="sxs-lookup"><span data-stu-id="c4e59-128">SQLitePCLRaw available providers</span></span>

<span data-ttu-id="c4e59-129">バンドルに依存しない場合は、コア アセンブリで SQLite の利用可能なプロバイダーを使用できます。</span><span class="sxs-lookup"><span data-stu-id="c4e59-129">When not relying on a bundle, you can use the available providers of SQLite with the core assembly.</span></span>

| <span data-ttu-id="c4e59-130">プロバイダー</span><span class="sxs-lookup"><span data-stu-id="c4e59-130">Provider</span></span> | <span data-ttu-id="c4e59-131">説明</span><span class="sxs-lookup"><span data-stu-id="c4e59-131">Description</span></span> |
|--|--|
| [<span data-ttu-id="c4e59-132">SQLitePCLRaw.provider.dynamic</span><span class="sxs-lookup"><span data-stu-id="c4e59-132">SQLitePCLRaw.provider.dynamic</span></span>](https://www.nuget.org/packages/SQLitePCLRaw.provider.dynamic) | <span data-ttu-id="c4e59-133">`dynamic` プロバイダーでは <xref:System.Runtime.InteropServices.DllImportAttribute?displayProperty=nameWithType> 属性を使用する代わりにネイティブ ライブラリが読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="c4e59-133">The `dynamic` provider loads the native library instead of using <xref:System.Runtime.InteropServices.DllImportAttribute?displayProperty=nameWithType> attributes.</span></span> <span data-ttu-id="c4e59-134">このプロバイダーの使用方法の詳細については、「[動的プロバイダーを使用する](#use-the-dynamic-provider)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="c4e59-134">For more information on using this provider, see [use the dynamic provider](#use-the-dynamic-provider).</span></span> |
| [<span data-ttu-id="c4e59-135">SQLitePCLRaw.provider.e_sqlite3</span><span class="sxs-lookup"><span data-stu-id="c4e59-135">SQLitePCLRaw.provider.e_sqlite3</span></span>](https://www.nuget.org/packages/SQLitePCLRaw.provider.e_sqlite3) | <span data-ttu-id="c4e59-136">`e_sqlite3` は既定のプロバイダーです。</span><span class="sxs-lookup"><span data-stu-id="c4e59-136">The `e_sqlite3` is the default provider.</span></span> |
| [<span data-ttu-id="c4e59-137">SQLitePCLRaw.provider.e_sqlcipher</span><span class="sxs-lookup"><span data-stu-id="c4e59-137">SQLitePCLRaw.provider.e_sqlcipher</span></span>](https://www.nuget.org/packages/SQLitePCLRaw.provider.e_sqlcipher) | <span data-ttu-id="c4e59-138">`e_sqlcipher` プロバイダーは、非公式でサポートされていない `SQLCipher` です。</span><span class="sxs-lookup"><span data-stu-id="c4e59-138">The `e_sqlcipher` provider is the unofficial and unsupported `SQLCipher`.</span></span> |
| [<span data-ttu-id="c4e59-139">SQLitePCLRaw.provider.sqlite3</span><span class="sxs-lookup"><span data-stu-id="c4e59-139">SQLitePCLRaw.provider.sqlite3</span></span>](https://www.nuget.org/packages/SQLitePCLRaw.provider.sqlite3) | <span data-ttu-id="c4e59-140">`sqlite3` プロバイダーは、iOS、macOS、Linux 用のシステム提供の `SQLite` です。</span><span class="sxs-lookup"><span data-stu-id="c4e59-140">The `sqlite3` provider is a system-provided `SQLite` for iOS, macOS, and Linux.</span></span> |
| [<span data-ttu-id="c4e59-141">SQLitePCLRaw.provider.sqlcipher</span><span class="sxs-lookup"><span data-stu-id="c4e59-141">SQLitePCLRaw.provider.sqlcipher</span></span>](https://www.nuget.org/packages/SQLitePCLRaw.provider.sqlcipher) | <span data-ttu-id="c4e59-142">`sqlcipher` プロバイダーは、`Zetetic` からの公式 `SQLCipher` ビルド用です。</span><span class="sxs-lookup"><span data-stu-id="c4e59-142">The `sqlcipher` provider is for official `SQLCipher` builds from `Zetetic`.</span></span> |
| [<span data-ttu-id="c4e59-143">SQLitePCLRaw.provider.winsqlite3</span><span class="sxs-lookup"><span data-stu-id="c4e59-143">SQLitePCLRaw.provider.winsqlite3</span></span>](https://www.nuget.org/packages/SQLitePCLRaw.provider.winsqlite3) | <span data-ttu-id="c4e59-144">`winsqlite3` プロバイダーは Windows 10 環境用です。</span><span class="sxs-lookup"><span data-stu-id="c4e59-144">The `winsqlite3` provider is for Windows 10 environments.</span></span> |

<span data-ttu-id="c4e59-145">`sqlite3` プロバイダーを使用するには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="c4e59-145">To use the `sqlite3` provider use the following commands:</span></span>

### <a name="net-core-cli"></a>[<span data-ttu-id="c4e59-146">.NET Core CLI</span><span class="sxs-lookup"><span data-stu-id="c4e59-146">.NET Core CLI</span></span>](#tab/netcore-cli)

```dotnetcli
dotnet add package Microsoft.Data.Sqlite.Core
dotnet add package SQLitePCLRaw.core
dotnet add package SQLitePCLRaw.provider.sqlite3
```

### <a name="visual-studio"></a>[<span data-ttu-id="c4e59-147">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="c4e59-147">Visual Studio</span></span>](#tab/visual-studio)

``` PowerShell
Install-Package Microsoft.Data.Sqlite.Core
Install-Package SQLitePCLRaw.core
Install-Package SQLitePCLRaw.provider.sqlite3
```

---

<span data-ttu-id="c4e59-148">パッケージをインストールしたら、プロバイダーを `sqlite3` インスタンスに設定します。</span><span class="sxs-lookup"><span data-stu-id="c4e59-148">With the packages installed, you then set the provider to the `sqlite3` instance.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/SqliteProviderSample/Program.cs)]

## <a name="use-the-dynamic-provider"></a><span data-ttu-id="c4e59-149">動的プロバイダーを使用する</span><span class="sxs-lookup"><span data-stu-id="c4e59-149">Use the dynamic provider</span></span>

<span data-ttu-id="c4e59-150">`SQLitePCLRaw.provider.dynamic_cdecl` パッケージを利用すると、独自の SQLite ビルドを使用できます。</span><span class="sxs-lookup"><span data-stu-id="c4e59-150">You can use your own build of SQLite by leveraging the `SQLitePCLRaw.provider.dynamic_cdecl` package.</span></span> <span data-ttu-id="c4e59-151">この場合、アプリとともにネイティブ ライブラリをデプロイする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c4e59-151">In this case, you're responsible for deploying the native library with your app.</span></span> <span data-ttu-id="c4e59-152">ただし、アプリとともにネイティブ ライブラリをデプロイする場合の詳細は、使用している .NET プラットフォームとランタイムによって大きく異なります。</span><span class="sxs-lookup"><span data-stu-id="c4e59-152">Note, the details of deploying native libraries with your app vary considerably depending on which .NET platform and runtime you're using.</span></span>

<span data-ttu-id="c4e59-153">まず、`IGetFunctionPointer` を実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c4e59-153">First, you'll need to implement `IGetFunctionPointer`.</span></span> <span data-ttu-id="c4e59-154">.NET Core での実装は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="c4e59-154">The implementation on .NET Core is as follows:</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/SystemLibrarySample/Program.cs?name=snippet_NativeLibraryAdapter)]

<span data-ttu-id="c4e59-155">次に、`SQLitePCLRaw` プロバイダーを構成します。</span><span class="sxs-lookup"><span data-stu-id="c4e59-155">Next, configure the `SQLitePCLRaw` provider.</span></span> <span data-ttu-id="c4e59-156">これは、アプリで `Microsoft.Data.Sqlite` が使用される前に行ってください。</span><span class="sxs-lookup"><span data-stu-id="c4e59-156">Ensure this is done before `Microsoft.Data.Sqlite` is used in your app.</span></span> <span data-ttu-id="c4e59-157">また、プロバイダーがオーバーライドされる可能性のある `SQLitePCLRaw` バンドル パッケージを使用しないようにしてください。</span><span class="sxs-lookup"><span data-stu-id="c4e59-157">Also, avoid using a `SQLitePCLRaw` bundle package which might override your provider.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/SystemLibrarySample/Program.cs?name=snippet_SetProvider)]
