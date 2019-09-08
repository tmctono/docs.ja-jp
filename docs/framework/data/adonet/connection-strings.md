---
title: ADO.NET での接続文字列
ms.date: 10/10/2018
ms.assetid: 745c5f95-2f02-4674-b378-6d51a7ec2490
ms.openlocfilehash: 8f726ca71ba955ef542d15e0e8318c2b310e607e
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70784911"
---
# <a name="connection-strings-in-adonet"></a><span data-ttu-id="6ed5f-102">ADO.NET での接続文字列</span><span class="sxs-lookup"><span data-stu-id="6ed5f-102">Connection Strings in ADO.NET</span></span>

<span data-ttu-id="6ed5f-103">接続文字列には、データ プロバイダーからデータ ソースにパラメーターとして渡す初期化情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="6ed5f-103">A connection string contains initialization information that is passed as a parameter from a data provider to a data source.</span></span> <span data-ttu-id="6ed5f-104">データプロバイダーは、 <xref:System.Data.Common.DbConnection.ConnectionString?displayProperty=nameWithType>プロパティの値として接続文字列を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="6ed5f-104">The data provider receives the connection string as the value of the <xref:System.Data.Common.DbConnection.ConnectionString?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="6ed5f-105">プロバイダーは接続文字列を解析して、構文が正しいことと、キーワードがサポートされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="6ed5f-105">The provider parses the connection string and ensures that the syntax is correct and that the keywords are supported.</span></span> <span data-ttu-id="6ed5f-106">次に<xref:System.Data.Common.DbConnection.Open?displayProperty=nameWithType> 、解析された接続パラメーターをデータソースに渡します。</span><span class="sxs-lookup"><span data-stu-id="6ed5f-106">Then the <xref:System.Data.Common.DbConnection.Open?displayProperty=nameWithType> method passes the parsed connection parameters to the data source.</span></span> <span data-ttu-id="6ed5f-107">データソースは、さらに検証を実行し、接続を確立します。</span><span class="sxs-lookup"><span data-stu-id="6ed5f-107">The data source performs further validation and establishes a connection.</span></span>

## <a name="connection-string-syntax"></a><span data-ttu-id="6ed5f-108">接続文字列の構文</span><span class="sxs-lookup"><span data-stu-id="6ed5f-108">Connection string syntax</span></span>

<span data-ttu-id="6ed5f-109">接続文字列は、キーと値のパラメーターのペアをセミコロンで区切ったリストです。</span><span class="sxs-lookup"><span data-stu-id="6ed5f-109">A connection string is a semicolon-delimited list of key/value parameter pairs:</span></span>

```
keyword1=value; keyword2=value;
```

<span data-ttu-id="6ed5f-110">キーワードでは、大文字と小文字は区別されません。</span><span class="sxs-lookup"><span data-stu-id="6ed5f-110">Keywords are not case-sensitive.</span></span> <span data-ttu-id="6ed5f-111">ただし、データソースによっては、値によって大文字と小文字が区別されることがあります。</span><span class="sxs-lookup"><span data-stu-id="6ed5f-111">Values, however, may be case-sensitive, depending on the data source.</span></span> <span data-ttu-id="6ed5f-112">キーワードと値の両方に[空白文字](https://en.wikipedia.org/wiki/Whitespace_character#Unicode)を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="6ed5f-112">Both keywords and values may contain [whitespace characters](https://en.wikipedia.org/wiki/Whitespace_character#Unicode).</span></span> <span data-ttu-id="6ed5f-113">キーワードおよび引用符で囲まれていない値では、先頭と末尾の空白文字は無視されます。</span><span class="sxs-lookup"><span data-stu-id="6ed5f-113">Leading and trailing white space is ignored in keywords and unquoted values.</span></span>

<span data-ttu-id="6ed5f-114">値にセミコロン、 [Unicode 制御文字](https://en.wikipedia.org/wiki/Unicode_control_characters)、または先頭または末尾の空白が含まれている場合は、一重引用符または二重引用符で囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="6ed5f-114">If a value contains the semicolon, [Unicode control characters](https://en.wikipedia.org/wiki/Unicode_control_characters), or leading or trailing white space, it must be enclosed in single or double quotation marks.</span></span> <span data-ttu-id="6ed5f-115">例えば:</span><span class="sxs-lookup"><span data-stu-id="6ed5f-115">For example:</span></span>

```
Keyword=" whitespace  ";
Keyword='special;character';
```

<span data-ttu-id="6ed5f-116">囲んでいる文字が、囲まれた値内に出現しない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="6ed5f-116">The enclosing character may not occur within the value it encloses.</span></span> <span data-ttu-id="6ed5f-117">したがって、単一引用符を含む値は、二重引用符で囲むことができます。また、その逆も可能です。</span><span class="sxs-lookup"><span data-stu-id="6ed5f-117">Therefore, a value containing single quotation marks can be enclosed only in double quotation marks, and vice versa:</span></span>

```
Keyword='double"quotation;mark';
Keyword="single'quotation;mark";
```

<span data-ttu-id="6ed5f-118">また、2つの文字を一緒に使用して、囲み文字をエスケープすることもできます。</span><span class="sxs-lookup"><span data-stu-id="6ed5f-118">You can also escape the enclosing character by using two of them together:</span></span>

```
Keyword="double""quotation";
Keyword='single''quotation';
```

<span data-ttu-id="6ed5f-119">引用符自体と等号だけでは、エスケープは必要ないため、次の接続文字列が有効です。</span><span class="sxs-lookup"><span data-stu-id="6ed5f-119">The quotation marks themselves, as well as the equals sign, do not require escaping, so the following connection strings are valid:</span></span>

```
Keyword=no "escaping" 'required';
Keyword=a=b=c
```

<span data-ttu-id="6ed5f-120">各値は、次のセミコロンまたは文字列の末尾まで読み取られるため、後者の例の値`a=b=c`はになり、最後のセミコロンは省略可能です。</span><span class="sxs-lookup"><span data-stu-id="6ed5f-120">Since each value is read till the next semicolon or the end of string, the value in the latter example is `a=b=c`, and the final semicolon is optional.</span></span>

<span data-ttu-id="6ed5f-121">すべての接続文字列は、上記で説明したのと同じ基本的な構文を共有します。</span><span class="sxs-lookup"><span data-stu-id="6ed5f-121">All connection strings share the same basic syntax described above.</span></span> <span data-ttu-id="6ed5f-122">認識されるキーワードのセットはプロバイダーによって異なり、 *ODBC*などの以前の api から長年にわたって進化しています。</span><span class="sxs-lookup"><span data-stu-id="6ed5f-122">The set of recognized keywords depends on the provider, however, and has evolved over the years from earlier APIs such as *ODBC*.</span></span> <span data-ttu-id="6ed5f-123">*.NET Framework* data provider for *SQL Server* (`SqlClient`) では、古い api からの多くのキーワードがサポートされていますが、一般的に、多くの一般的な接続文字列キーワードに対しては、より柔軟性が高く、シノニムを使用できます。</span><span class="sxs-lookup"><span data-stu-id="6ed5f-123">The *.NET Framework* data provider for *SQL Server* (`SqlClient`) supports many keywords from older APIs, but is generally more flexible and accepts synonyms for many of the common connection string keywords.</span></span>

<span data-ttu-id="6ed5f-124">入力ミスによってエラーが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="6ed5f-124">Typing mistakes can cause errors.</span></span> <span data-ttu-id="6ed5f-125">たとえば、 `Integrated Security=true`は有効ですが`IntegratedSecurity=true` 、エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="6ed5f-125">For example, `Integrated Security=true` is valid, but `IntegratedSecurity=true` causes an error.</span></span>

<span data-ttu-id="6ed5f-126">実行時に未検証ユーザー入力から手動で構築された接続文字列は、文字列インジェクション攻撃に対して脆弱で、データソースのセキュリティが危険にさらされます。</span><span class="sxs-lookup"><span data-stu-id="6ed5f-126">Connection strings constructed manually at run time from unvalidated user input are vulnerable to string-injection attacks and jeopardize security at the data source.</span></span> <span data-ttu-id="6ed5f-127">これらの問題に対処するために、 *ADO.NET* 2.0 では *.NET Framework*データプロバイダーごとに[接続文字列ビルダー](connection-string-builders.md)が導入されました。</span><span class="sxs-lookup"><span data-stu-id="6ed5f-127">To address these problems, *ADO.NET* 2.0 introduced [connection string builders](connection-string-builders.md) for each *.NET Framework* data provider.</span></span> <span data-ttu-id="6ed5f-128">これらの接続文字列ビルダーは、パラメーターを厳密に型指定されたプロパティとして公開し、データソースに送信される前に接続文字列を検証できるようにします。</span><span class="sxs-lookup"><span data-stu-id="6ed5f-128">These connection string builders expose parameters as strongly-typed properties, and make it possible to validate the connection string before it's sent to the data source.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="6ed5f-129">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="6ed5f-129">In This Section</span></span>

<span data-ttu-id="6ed5f-130">[接続文字列ビルダー](connection-string-builders.md)</span><span class="sxs-lookup"><span data-stu-id="6ed5f-130">[Connection String Builders](connection-string-builders.md)</span></span>\
<span data-ttu-id="6ed5f-131">`ConnectionStringBuilder` クラスを使用して、有効な接続文字列を実行時に作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="6ed5f-131">Demonstrates how to use the `ConnectionStringBuilder` classes to construct valid connection strings at run time.</span></span>

<span data-ttu-id="6ed5f-132">[接続文字列と構成ファイル](connection-strings-and-configuration-files.md)</span><span class="sxs-lookup"><span data-stu-id="6ed5f-132">[Connection Strings and Configuration Files](connection-strings-and-configuration-files.md)</span></span>\
<span data-ttu-id="6ed5f-133">構成ファイルを使用した接続文字列の格納と取得の方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="6ed5f-133">Demonstrates how to store and retrieve connection strings in configuration files.</span></span>

<span data-ttu-id="6ed5f-134">[接続文字列の構文](connection-string-syntax.md)</span><span class="sxs-lookup"><span data-stu-id="6ed5f-134">[Connection String Syntax](connection-string-syntax.md)</span></span>\
<span data-ttu-id="6ed5f-135">`SqlClient`、`OracleClient`、`OleDb`、`Odbc` の各プロバイダーに固有の接続文字列を構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="6ed5f-135">Describes how to configure provider-specific connection strings for `SqlClient`, `OracleClient`, `OleDb`, and `Odbc`.</span></span>

<span data-ttu-id="6ed5f-136">[接続情報の保護](protecting-connection-information.md)</span><span class="sxs-lookup"><span data-stu-id="6ed5f-136">[Protecting Connection Information](protecting-connection-information.md)</span></span>\
<span data-ttu-id="6ed5f-137">データ ソースへの接続に使用する情報を保護する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="6ed5f-137">Demonstrates techniques for protecting information used to connect to a data source.</span></span>

## <a name="see-also"></a><span data-ttu-id="6ed5f-138">関連項目</span><span class="sxs-lookup"><span data-stu-id="6ed5f-138">See also</span></span>

- [<span data-ttu-id="6ed5f-139">データ ソースへの接続</span><span class="sxs-lookup"><span data-stu-id="6ed5f-139">Connecting to a Data Source</span></span>](/cpp/data/odbc/connecting-to-a-data-source)
- [<span data-ttu-id="6ed5f-140">ADO.NET の概要</span><span class="sxs-lookup"><span data-stu-id="6ed5f-140">ADO.NET Overview</span></span>](ado-net-overview.md)
