---
title: 暗号化
ms.date: 09/08/2020
description: データベースファイルを暗号化する方法について説明します。
ms.openlocfilehash: 1b33e1510a269aba87caba2cd39faab33791aa55
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91203411"
---
# <a name="encryption"></a><span data-ttu-id="9480d-103">暗号化</span><span class="sxs-lookup"><span data-stu-id="9480d-103">Encryption</span></span>

<span data-ttu-id="9480d-104">SQLite では、既定により、データベース ファイルの暗号化はサポートされません。</span><span class="sxs-lookup"><span data-stu-id="9480d-104">SQLite doesn't support encrypting database files by default.</span></span> <span data-ttu-id="9480d-105">代わりに、修正した SQLite バージョンの [SEE](https://www.hwaci.com/sw/sqlite/see.html)、[SQLCipher](https://www.zetetic.net/sqlcipher/)、[SQLiteCrypt](http://www.sqlite-crypt.com/)、[wxSQLite3](https://utelle.github.io/wxsqlite3) などを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9480d-105">Instead, you need to use a modified version of SQLite like [SEE](https://www.hwaci.com/sw/sqlite/see.html), [SQLCipher](https://www.zetetic.net/sqlcipher/), [SQLiteCrypt](http://www.sqlite-crypt.com/), or [wxSQLite3](https://utelle.github.io/wxsqlite3).</span></span> <span data-ttu-id="9480d-106">この記事では、SQLCipher のサポートされていないオープンソース ビルドの使用について説明しますが、他のソリューションにも当てはまります。これらも一般的に同じパターンに従っているためです。</span><span class="sxs-lookup"><span data-stu-id="9480d-106">This article demonstrates using an unsupported, open-source build of SQLCipher, but the information also applies to other solutions since they generally follow the same pattern.</span></span>

## <a name="installation"></a><span data-ttu-id="9480d-107">インストール</span><span class="sxs-lookup"><span data-stu-id="9480d-107">Installation</span></span>

### <a name="net-core-cli"></a>[<span data-ttu-id="9480d-108">.NET Core CLI</span><span class="sxs-lookup"><span data-stu-id="9480d-108">.NET Core CLI</span></span>](#tab/netcore-cli)

```dotnetcli
dotnet remove package Microsoft.Data.Sqlite
dotnet add package Microsoft.Data.Sqlite.Core
dotnet add package SQLitePCLRaw.bundle_e_sqlcipher
```

### <a name="visual-studio"></a>[<span data-ttu-id="9480d-109">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="9480d-109">Visual Studio</span></span>](#tab/visual-studio)

``` PowerShell
Remove-Package Microsoft.Data.Sqlite
Install-Package Microsoft.Data.Sqlite.Core
Install-Package SQLitePCLRaw.bundle_e_sqlcipher
```

---

<span data-ttu-id="9480d-110">暗号化に別のネイティブ ライブラリを使用する場合の詳細については、「[カスタム SQLite のバージョン](custom-versions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9480d-110">For more information about using a different native library for encryption, see [Custom SQLite versions](custom-versions.md).</span></span>

## <a name="specify-the-key"></a><span data-ttu-id="9480d-111">キーを指定する</span><span class="sxs-lookup"><span data-stu-id="9480d-111">Specify the key</span></span>

<span data-ttu-id="9480d-112">新しいデータベースで暗号化を有効にするには、`Password` 接続文字列キーワードを使用してキーを指定します。</span><span class="sxs-lookup"><span data-stu-id="9480d-112">To enable encryption on a new database, specify the key using the `Password` connection string keyword.</span></span> <span data-ttu-id="9480d-113"><xref:Microsoft.Data.Sqlite.SqliteConnectionStringBuilder> を使用して、ユーザー入力の値を追加または更新し、接続文字列のインジェクション攻撃を回避します。</span><span class="sxs-lookup"><span data-stu-id="9480d-113">Use <xref:Microsoft.Data.Sqlite.SqliteConnectionStringBuilder> to add or update the value from user input and avoid connection string injection attacks.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/EncryptionSample/Program.cs?name=snippet_ConnectionStringBuilder)]

> [!TIP]
> <span data-ttu-id="9480d-114">既存のデータベースを暗号化および暗号化解除する方法は、使用しているソリューションによって異なります。</span><span class="sxs-lookup"><span data-stu-id="9480d-114">The method for encrypting and decrypting existing databases varies depending on which solution you're using.</span></span> <span data-ttu-id="9480d-115">たとえば、SQLCipher では `sqlcipher_export()` 関数を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9480d-115">For example, you need to use the `sqlcipher_export()` function on SQLCipher.</span></span> <span data-ttu-id="9480d-116">詳細については、ソリューションのドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="9480d-116">Check your solution's documentation for details.</span></span>

## <a name="rekeying-the-database"></a><span data-ttu-id="9480d-117">データベースのキーを更新する</span><span class="sxs-lookup"><span data-stu-id="9480d-117">Rekeying the database</span></span>

<span data-ttu-id="9480d-118">暗号化されたデータベースのキーを変更する場合は、`PRAGMA rekey` ステートメントを実行します。</span><span class="sxs-lookup"><span data-stu-id="9480d-118">If you want to change the key of an encrypted database, issue a `PRAGMA rekey` statement.</span></span>

<span data-ttu-id="9480d-119">ただし、SQLite では `PRAGMA` ステートメントのパラメーターはサポートされません。</span><span class="sxs-lookup"><span data-stu-id="9480d-119">Unfortunately, SQLite doesn't support parameters in `PRAGMA` statements.</span></span> <span data-ttu-id="9480d-120">代わりに、`quote()` 関数を使用して、SQL インジェクションを防止してください。</span><span class="sxs-lookup"><span data-stu-id="9480d-120">Instead, use the `quote()` function to prevent SQL injection.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/EncryptionSample/Program.cs?name=snippet_Rekey)]
