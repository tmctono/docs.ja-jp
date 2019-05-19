---
title: ADO.NET での接続文字列
ms.date: 10/10/2018
ms.assetid: 745c5f95-2f02-4674-b378-6d51a7ec2490
ms.openlocfilehash: 3b7cb0ab061da8364a9fecc3868ba9aaf7501577
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2019
ms.locfileid: "65881162"
---
# <a name="connection-strings-in-adonet"></a><span data-ttu-id="2f5ec-102">ADO.NET での接続文字列</span><span class="sxs-lookup"><span data-stu-id="2f5ec-102">Connection Strings in ADO.NET</span></span>

<span data-ttu-id="2f5ec-103">接続文字列には、データ プロバイダーからデータ ソースにパラメーターとして渡す初期化情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="2f5ec-103">A connection string contains initialization information that is passed as a parameter from a data provider to a data source.</span></span> <span data-ttu-id="2f5ec-104">データ プロバイダーの値として、接続文字列を受け取る、<xref:System.Data.Common.DbConnection.ConnectionString?displayProperty=nameWithType>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="2f5ec-104">The data provider receives the connection string as the value of the <xref:System.Data.Common.DbConnection.ConnectionString?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="2f5ec-105">プロバイダーは、接続文字列を解析し、により、構文が正しいことと、キーワードがサポートされていること。</span><span class="sxs-lookup"><span data-stu-id="2f5ec-105">The provider parses the connection string and ensures that the syntax is correct and that the keywords are supported.</span></span> <span data-ttu-id="2f5ec-106">次に、<xref:System.Data.Common.DbConnection.Open?displayProperty=nameWithType>メソッドは、データ ソースに解析された接続パラメーターを渡します。</span><span class="sxs-lookup"><span data-stu-id="2f5ec-106">Then the <xref:System.Data.Common.DbConnection.Open?displayProperty=nameWithType> method passes the parsed connection parameters to the data source.</span></span> <span data-ttu-id="2f5ec-107">データ ソースは、さらに検証を実行し、接続を確立します。</span><span class="sxs-lookup"><span data-stu-id="2f5ec-107">The data source performs further validation and establishes a connection.</span></span>

## <a name="connection-string-syntax"></a><span data-ttu-id="2f5ec-108">接続文字列の構文</span><span class="sxs-lookup"><span data-stu-id="2f5ec-108">Connection string syntax</span></span>

<span data-ttu-id="2f5ec-109">接続文字列は、パラメーターのキー/値ペアのセミコロンで区切られた一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="2f5ec-109">A connection string is a semicolon-delimited list of key/value parameter pairs:</span></span>

```
keyword1=value; keyword2=value;
```

<span data-ttu-id="2f5ec-110">キーワードは区別されません。</span><span class="sxs-lookup"><span data-stu-id="2f5ec-110">Keywords are not case-sensitive.</span></span> <span data-ttu-id="2f5ec-111">値、ただし、可能性があります、データ ソースによって、大文字小文字が区別されます。</span><span class="sxs-lookup"><span data-stu-id="2f5ec-111">Values, however, may be case-sensitive, depending on the data source.</span></span> <span data-ttu-id="2f5ec-112">キーワードと値の両方を含めることができます[空白文字](https://en.wikipedia.org/wiki/Whitespace_character#Unicode)します。</span><span class="sxs-lookup"><span data-stu-id="2f5ec-112">Both keywords and values may contain [whitespace characters](https://en.wikipedia.org/wiki/Whitespace_character#Unicode).</span></span> <span data-ttu-id="2f5ec-113">先頭および末尾の空白文字がキーワードで無視され、引用符の値。</span><span class="sxs-lookup"><span data-stu-id="2f5ec-113">Leading and trailing white space is ignored in keywords and unquoted values.</span></span>

<span data-ttu-id="2f5ec-114">値には、セミコロンが含まれている場合[Unicode コントロール文字](https://en.wikipedia.org/wiki/Unicode_control_characters)、先頭または末尾の空白文字、単一引用符または二重引用符で囲む必要がありますか。</span><span class="sxs-lookup"><span data-stu-id="2f5ec-114">If a value contains the semicolon, [Unicode control characters](https://en.wikipedia.org/wiki/Unicode_control_characters), or leading or trailing white space, it must be enclosed in single or double quotation marks.</span></span> <span data-ttu-id="2f5ec-115">例:</span><span class="sxs-lookup"><span data-stu-id="2f5ec-115">For example:</span></span>

```
Keyword=" whitespace  ";
Keyword='special;character';
```

<span data-ttu-id="2f5ec-116">それを囲む文字を囲む値内で発生しません。</span><span class="sxs-lookup"><span data-stu-id="2f5ec-116">The enclosing character may not occur within the value it encloses.</span></span> <span data-ttu-id="2f5ec-117">そのため、単一引用符を含む値を囲む二重引用符でのみ、またはその逆ことができます。</span><span class="sxs-lookup"><span data-stu-id="2f5ec-117">Therefore, a value containing single quotation marks can be enclosed only in double quotation marks, and vice versa:</span></span>

```
Keyword='double"quotation;mark';
Keyword="single'quotation;mark";
```

<span data-ttu-id="2f5ec-118">、等号と同様に、引用符は不要、エスケープため、次の接続文字列が無効です。</span><span class="sxs-lookup"><span data-stu-id="2f5ec-118">The quotation marks themselves, as well as the equals sign, do not require escaping, so the following connection strings are valid:</span></span>

```
Keyword=no "escaping" 'required';
Keyword=a=b=c
```

<span data-ttu-id="2f5ec-119">後者の例の値は、各値は、[次へ] のセミコロンまたは文字列の末尾まで読み取ることが、ため`a=b=c`、最後のセミコロンは省略可能です。</span><span class="sxs-lookup"><span data-stu-id="2f5ec-119">Since each value is read till the next semicolon or the end of string, the value in the latter example is `a=b=c`, and the final semicolon is optional.</span></span>

<span data-ttu-id="2f5ec-120">すべての接続文字列は、上記で説明した同じ基本的な構文を共有します。</span><span class="sxs-lookup"><span data-stu-id="2f5ec-120">All connection strings share the same basic syntax described above.</span></span> <span data-ttu-id="2f5ec-121">認識されているキーワードのセットは、ただしは、プロバイダーに依存しなど、以前の Api から長年にわたって進化してきた*ODBC*します。</span><span class="sxs-lookup"><span data-stu-id="2f5ec-121">The set of recognized keywords depends on the provider, however, and has evolved over the years from earlier APIs such as *ODBC*.</span></span> <span data-ttu-id="2f5ec-122">*.NET Framework*用データ プロバイダーの*SQL Server* (`SqlClient`) 従来の Api から多くのキーワードをサポートしていますが、一般より柔軟な一般的な接続文字列の多くのシノニムを受け入れる、キーワード。</span><span class="sxs-lookup"><span data-stu-id="2f5ec-122">The *.NET Framework* data provider for *SQL Server* (`SqlClient`) supports many keywords from older APIs, but is generally more flexible and accepts synonyms for many of the common connection string keywords.</span></span>

<span data-ttu-id="2f5ec-123">入力ミス エラーが発生することができます。</span><span class="sxs-lookup"><span data-stu-id="2f5ec-123">Typing mistakes can cause errors.</span></span> <span data-ttu-id="2f5ec-124">たとえば、`Integrated Security=true`が有効では`IntegratedSecurity=true`エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="2f5ec-124">For example, `Integrated Security=true` is valid, but `IntegratedSecurity=true` causes an error.</span></span>

<span data-ttu-id="2f5ec-125">未検証のユーザー入力からの実行時に手動で構築された接続文字列は、文字列のインジェクション攻撃に対して脆弱なし、データ ソースでセキュリティを損ないます。</span><span class="sxs-lookup"><span data-stu-id="2f5ec-125">Connection strings constructed manually at run time from unvalidated user input are vulnerable to string-injection attacks and jeopardize security at the data source.</span></span> <span data-ttu-id="2f5ec-126">これらの問題に対処する*ADO.NET* 2.0 で[接続文字列ビルダー](../../../../docs/framework/data/adonet/connection-string-builders.md)各 *.NET Framework*データ プロバイダー。</span><span class="sxs-lookup"><span data-stu-id="2f5ec-126">To address these problems, *ADO.NET* 2.0 introduced [connection string builders](../../../../docs/framework/data/adonet/connection-string-builders.md) for each *.NET Framework* data provider.</span></span> <span data-ttu-id="2f5ec-127">これらの接続文字列ビルダーは、厳密に型指定されたプロパティとしてパラメーターを公開し、データ ソースに送信される前に、接続文字列を検証すること。</span><span class="sxs-lookup"><span data-stu-id="2f5ec-127">These connection string builders expose parameters as strongly-typed properties, and make it possible to validate the connection string before it's sent to the data source.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="2f5ec-128">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="2f5ec-128">In This Section</span></span>

<span data-ttu-id="2f5ec-129">[接続文字列ビルダー](../../../../docs/framework/data/adonet/connection-string-builders.md)\\</span><span class="sxs-lookup"><span data-stu-id="2f5ec-129">[Connection String Builders](../../../../docs/framework/data/adonet/connection-string-builders.md)\\</span></span>
<span data-ttu-id="2f5ec-130">`ConnectionStringBuilder` クラスを使用して、有効な接続文字列を実行時に作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="2f5ec-130">Demonstrates how to use the `ConnectionStringBuilder` classes to construct valid connection strings at run time.</span></span>

<span data-ttu-id="2f5ec-131">[接続文字列と構成ファイル](../../../../docs/framework/data/adonet/connection-strings-and-configuration-files.md)\\</span><span class="sxs-lookup"><span data-stu-id="2f5ec-131">[Connection Strings and Configuration Files](../../../../docs/framework/data/adonet/connection-strings-and-configuration-files.md)\\</span></span>
<span data-ttu-id="2f5ec-132">構成ファイルを使用した接続文字列の格納と取得の方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="2f5ec-132">Demonstrates how to store and retrieve connection strings in configuration files.</span></span>

<span data-ttu-id="2f5ec-133">[接続文字列の構文](../../../../docs/framework/data/adonet/connection-string-syntax.md)\\</span><span class="sxs-lookup"><span data-stu-id="2f5ec-133">[Connection String Syntax](../../../../docs/framework/data/adonet/connection-string-syntax.md)\\</span></span>
<span data-ttu-id="2f5ec-134">`SqlClient`、`OracleClient`、`OleDb`、`Odbc` の各プロバイダーに固有の接続文字列を構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="2f5ec-134">Describes how to configure provider-specific connection strings for `SqlClient`, `OracleClient`, `OleDb`, and `Odbc`.</span></span>

<span data-ttu-id="2f5ec-135">[接続情報の保護](../../../../docs/framework/data/adonet/protecting-connection-information.md)\\</span><span class="sxs-lookup"><span data-stu-id="2f5ec-135">[Protecting Connection Information](../../../../docs/framework/data/adonet/protecting-connection-information.md)\\</span></span>
<span data-ttu-id="2f5ec-136">データ ソースへの接続に使用する情報を保護する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="2f5ec-136">Demonstrates techniques for protecting information used to connect to a data source.</span></span>

## <a name="see-also"></a><span data-ttu-id="2f5ec-137">関連項目</span><span class="sxs-lookup"><span data-stu-id="2f5ec-137">See also</span></span>

- [<span data-ttu-id="2f5ec-138">データ ソースへの接続</span><span class="sxs-lookup"><span data-stu-id="2f5ec-138">Connecting to a Data Source</span></span>](/cpp/data/odbc/connecting-to-a-data-source)
- [<span data-ttu-id="2f5ec-139">ADO.NET のマネージド プロバイダーと DataSet デベロッパー センター</span><span class="sxs-lookup"><span data-stu-id="2f5ec-139">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
