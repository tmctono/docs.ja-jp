---
title: 拡張
ms.date: 12/13/2019
description: SQLite 拡張機能を読み込む方法について説明します。
ms.openlocfilehash: ab00ccf31b8a22407fc177c18149fe4825a19091
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450478"
---
# <a name="extensions"></a><span data-ttu-id="2390f-103">拡張</span><span class="sxs-lookup"><span data-stu-id="2390f-103">Extensions</span></span>

<span data-ttu-id="2390f-104">SQLite では、実行時の拡張機能の読み込みがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="2390f-104">SQLite supports loading extensions at run time.</span></span> <span data-ttu-id="2390f-105">拡張機能には、追加の SQL 関数、照合順序、仮想テーブルなどが含まれます。</span><span class="sxs-lookup"><span data-stu-id="2390f-105">Extensions include things like additional SQL functions, collations, virtual tables, and more.</span></span>

<span data-ttu-id="2390f-106">.NET Core には、参照される NuGet パッケージなどの追加の場所でネイティブライブラリを検索するための追加のロジックが含まれています。</span><span class="sxs-lookup"><span data-stu-id="2390f-106">.NET Core includes additional logic for locating native libraries in additional places like referenced NuGet packages.</span></span> <span data-ttu-id="2390f-107">残念ながら、SQLite はこのロジックを利用できません。ライブラリを読み込むために、プラットフォーム API を直接呼び出します。</span><span class="sxs-lookup"><span data-stu-id="2390f-107">Unfortunately, SQLite can't leverage this logic; it calls the platform API directly to load libraries.</span></span> <span data-ttu-id="2390f-108">このため、アプリケーションでは、SQLite 拡張機能を読み込む前に、パス、LD_LIBRARY_PATH、または DYLD_LIBRARY_PATH 環境変数の変更が必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="2390f-108">Because of this, your app may need to modify the PATH, LD_LIBRARY_PATH, or DYLD_LIBRARY_PATH environment variables before loading SQLite extensions.</span></span> <span data-ttu-id="2390f-109">GitHub に[は](https://github.com/dotnet/samples/blob/master/samples/snippets/standard/data/sqlite/ExtensionsSample/Program.cs)、参照される NuGet パッケージ内の現在のランタイムのバイナリを検索する例があります。</span><span class="sxs-lookup"><span data-stu-id="2390f-109">There's [a sample](https://github.com/dotnet/samples/blob/master/samples/snippets/standard/data/sqlite/ExtensionsSample/Program.cs) on GitHub that demonstrates finding binaries for the current runtime inside a referenced NuGet package.</span></span>

<span data-ttu-id="2390f-110">拡張機能を読み込むには、<xref:Microsoft.Data.Sqlite.SqliteConnection.LoadExtension%2A> メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="2390f-110">To load an extension, call the <xref:Microsoft.Data.Sqlite.SqliteConnection.LoadExtension%2A> method.</span></span> <span data-ttu-id="2390f-111">接続が閉じられてから再び開かれた場合でも、拡張機能は読み込まれたままになります。</span><span class="sxs-lookup"><span data-stu-id="2390f-111">Microsoft.Data.Sqlite will ensure that the extension remains loaded even if the connection is closed and reopened.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/ExtensionsSample/Program.cs?name=snippet_LoadExtension)]

## <a name="see-also"></a><span data-ttu-id="2390f-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="2390f-112">See also</span></span>

* [<span data-ttu-id="2390f-113">実行時の読み込み可能な拡張機能</span><span class="sxs-lookup"><span data-stu-id="2390f-113">Run-Time Loadable Extensions</span></span>](https://www.sqlite.org/loadext.html)
