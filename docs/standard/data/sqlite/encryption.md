---
title: '[暗号化]'
ms.date: 12/13/2019
description: データベースファイルを暗号化する方法について説明します。
ms.openlocfilehash: ccdd4b6b8642b3cde1c2667c9ca432a9b0ef21f2
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450484"
---
# <a name="encryption"></a><span data-ttu-id="0939e-103">[暗号化]</span><span class="sxs-lookup"><span data-stu-id="0939e-103">Encryption</span></span>

<span data-ttu-id="0939e-104">SQLite は、既定ではデータベースファイルの暗号化をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="0939e-104">SQLite doesn't support encrypting database files by default.</span></span> <span data-ttu-id="0939e-105">代わりに、 [「」、「](https://www.hwaci.com/sw/sqlite/see.html) [Sqlcipher](https://www.zetetic.net/sqlcipher/)」、「 [SQLiteCrypt](http://www.sqlite-crypt.com/)」、「 [wxSQLite3](https://utelle.github.io/wxsqlite3)」のように、改変されたバージョンの SQLite を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0939e-105">Instead, you need to use a modified version of SQLite like [SEE](https://www.hwaci.com/sw/sqlite/see.html), [SQLCipher](https://www.zetetic.net/sqlcipher/), [SQLiteCrypt](http://www.sqlite-crypt.com/), or [wxSQLite3](https://utelle.github.io/wxsqlite3).</span></span> <span data-ttu-id="0939e-106">この記事では、SQLCipher のサポートされていないオープンソースビルドを使用する方法について説明しますが、この情報は通常、同じパターンに従っているため、他のソリューションにも当てはまります。</span><span class="sxs-lookup"><span data-stu-id="0939e-106">This article demonstrates using an unsupported, open-source build of SQLCipher, but the information also applies to other solutions since they generally follow the same pattern.</span></span>

## <a name="installation"></a><span data-ttu-id="0939e-107">のインストール</span><span class="sxs-lookup"><span data-stu-id="0939e-107">Installation</span></span>

### <a name="net-core-clitabnetcore-cli"></a>[<span data-ttu-id="0939e-108">.NET Core CLI</span><span class="sxs-lookup"><span data-stu-id="0939e-108">.NET Core CLI</span></span>](#tab/netcore-cli)

```dotnetcli
dotnet remove package Microsoft.Data.Sqlite
dotnet add package Microsoft.Data.Sqlite.Core
dotnet add package SQLitePCLRaw.bundle_e_sqlcipher
```

### <a name="visual-studiotabvisual-studio"></a>[<span data-ttu-id="0939e-109">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="0939e-109">Visual Studio</span></span>](#tab/visual-studio)

``` PowerShell
Remove-Package Microsoft.Data.Sqlite
Install-Package Microsoft.Data.Sqlite.Core
Install-Package SQLitePCLRaw.bundle_e_sqlcipher
```

---

<span data-ttu-id="0939e-110">暗号化に別のネイティブライブラリを使用する方法の詳細については、「[カスタム SQLite バージョン](custom-versions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0939e-110">For more information about using a different native library for encryption, see [Custom SQLite versions](custom-versions.md).</span></span>

## <a name="specify-the-key"></a><span data-ttu-id="0939e-111">キーを指定します</span><span class="sxs-lookup"><span data-stu-id="0939e-111">Specify the key</span></span>

<span data-ttu-id="0939e-112">暗号化を有効にするには、`Password` 接続文字列キーワードを使用してキーを指定します。</span><span class="sxs-lookup"><span data-stu-id="0939e-112">To enable encryption, specify the key using the `Password` connection string keyword.</span></span> <span data-ttu-id="0939e-113"><xref:Microsoft.Data.Sqlite.SqliteConnectionStringBuilder> を使用して、ユーザー入力の値を追加または更新し、接続文字列のインジェクション攻撃を回避します。</span><span class="sxs-lookup"><span data-stu-id="0939e-113">Use <xref:Microsoft.Data.Sqlite.SqliteConnectionStringBuilder> to add or update the value from user input and avoid connection string injection attacks.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/EncryptionSample/Program.cs?name=snippet_ConnectionStringBuilder)]

## <a name="rekeying-the-database"></a><span data-ttu-id="0939e-114">データベースのキーの更新</span><span class="sxs-lookup"><span data-stu-id="0939e-114">Rekeying the database</span></span>

<span data-ttu-id="0939e-115">データベースの暗号化キーを変更する場合は、`PRAGMA rekey` ステートメントを実行します。</span><span class="sxs-lookup"><span data-stu-id="0939e-115">If you want to change the encryption key of a database, issue a `PRAGMA rekey` statement.</span></span> <span data-ttu-id="0939e-116">データベースの暗号化を解除するには、`NULL`を指定します。</span><span class="sxs-lookup"><span data-stu-id="0939e-116">To decrypt the database, specify `NULL`.</span></span>

<span data-ttu-id="0939e-117">残念ながら、SQLite では `PRAGMA` ステートメントのパラメーターはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="0939e-117">Unfortunately, SQLite doesn't support parameters in `PRAGMA` statements.</span></span> <span data-ttu-id="0939e-118">代わりに、`quote()` 関数を使用して、SQL インジェクションを防止します。</span><span class="sxs-lookup"><span data-stu-id="0939e-118">Instead, use the `quote()` function to prevent SQL injection.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/EncryptionSample/Program.cs?name=snippet_Rekey)]
