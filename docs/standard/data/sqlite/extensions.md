---
title: 拡張機能
ms.date: 12/13/2019
description: SQLite 拡張機能を読み込む方法について説明します。
ms.openlocfilehash: 51c705349c25240fe42e0edda8004a3e3b013ca3
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/13/2020
ms.locfileid: "81242960"
---
# <a name="extensions"></a><span data-ttu-id="67323-103">拡張機能</span><span class="sxs-lookup"><span data-stu-id="67323-103">Extensions</span></span>

<span data-ttu-id="67323-104">SQLite は、実行時に拡張機能の読み込みをサポートします。</span><span class="sxs-lookup"><span data-stu-id="67323-104">SQLite supports loading extensions at run time.</span></span> <span data-ttu-id="67323-105">拡張機能には、追加の SQL 関数、照合順序、仮想テーブルなどが含まれます。</span><span class="sxs-lookup"><span data-stu-id="67323-105">Extensions include things like additional SQL functions, collations, virtual tables, and more.</span></span>

<span data-ttu-id="67323-106">.NET Core には、参照される NuGet パッケージなどの追加の場所でネイティブ ライブラリを検索するための追加のロジックが含まれています。</span><span class="sxs-lookup"><span data-stu-id="67323-106">.NET Core includes additional logic for locating native libraries in additional places like referenced NuGet packages.</span></span> <span data-ttu-id="67323-107">残念ながら、SQLiteはこのロジックを活用できません。プラットフォーム API を直接呼び出してライブラリを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="67323-107">Unfortunately, SQLite can't leverage this logic; it calls the platform API directly to load libraries.</span></span> <span data-ttu-id="67323-108">このため、SQLite 拡張機能をロードする前に、PATH、LD_LIBRARY_PATH、またはDYLD_LIBRARY_PATH環境変数を変更する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="67323-108">Because of this, you may need to modify the PATH, LD_LIBRARY_PATH, or DYLD_LIBRARY_PATH environment variables before loading SQLite extensions.</span></span> <span data-ttu-id="67323-109">GitHub には、参照される NuGet パッケージ内の現在のランタイムのバイナリを見つける方法を示す[サンプル](https://github.com/dotnet/docs/blob/master/samples/snippets/standard/data/sqlite/ExtensionsSample/Program.cs)があります。</span><span class="sxs-lookup"><span data-stu-id="67323-109">There's [a sample](https://github.com/dotnet/docs/blob/master/samples/snippets/standard/data/sqlite/ExtensionsSample/Program.cs) on GitHub that demonstrates finding binaries for the current runtime inside a referenced NuGet package.</span></span>

<span data-ttu-id="67323-110">内線番号を読み込<xref:Microsoft.Data.Sqlite.SqliteConnection.LoadExtension%2A>むには、メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="67323-110">To load an extension, call the <xref:Microsoft.Data.Sqlite.SqliteConnection.LoadExtension%2A> method.</span></span> <span data-ttu-id="67323-111">Microsoft.Data.Sqlite は、接続が閉じられ、再び開かれた場合でも、拡張機能が読み込まれたままであることを確認します。</span><span class="sxs-lookup"><span data-stu-id="67323-111">Microsoft.Data.Sqlite will ensure that the extension remains loaded even if the connection is closed and reopened.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/ExtensionsSample/Program.cs?name=snippet_LoadExtension)]

## <a name="see-also"></a><span data-ttu-id="67323-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="67323-112">See also</span></span>

* [<span data-ttu-id="67323-113">ランタイムロード可能拡張機能</span><span class="sxs-lookup"><span data-stu-id="67323-113">Run-Time Loadable Extensions</span></span>](https://www.sqlite.org/loadext.html)
