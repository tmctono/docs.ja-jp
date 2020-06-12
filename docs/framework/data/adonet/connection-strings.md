---
title: 接続文字列
description: ADO.NET の接続文字列について説明します。これには、データ プロバイダーからデータ ソースにパラメーターとして渡される初期化情報が含まれています。
ms.date: 10/10/2018
ms.assetid: 745c5f95-2f02-4674-b378-6d51a7ec2490
ms.openlocfilehash: baa6599a532746895cbb3920f2c623dd4c2be864
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/02/2020
ms.locfileid: "84287026"
---
# <a name="connection-strings-in-adonet"></a><span data-ttu-id="476bd-103">ADO.NET での接続文字列</span><span class="sxs-lookup"><span data-stu-id="476bd-103">Connection Strings in ADO.NET</span></span>

<span data-ttu-id="476bd-104">接続文字列には、データ プロバイダーからデータ ソースにパラメーターとして渡す初期化情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="476bd-104">A connection string contains initialization information that is passed as a parameter from a data provider to a data source.</span></span> <span data-ttu-id="476bd-105">データ プロバイダーでは、<xref:System.Data.Common.DbConnection.ConnectionString?displayProperty=nameWithType> プロパティの値として接続文字列を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="476bd-105">The data provider receives the connection string as the value of the <xref:System.Data.Common.DbConnection.ConnectionString?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="476bd-106">プロバイダーによって接続文字列が解析されて、構文が正しいことと、キーワードがサポートされていることが確認されます。</span><span class="sxs-lookup"><span data-stu-id="476bd-106">The provider parses the connection string and ensures that the syntax is correct and that the keywords are supported.</span></span> <span data-ttu-id="476bd-107">その後、<xref:System.Data.Common.DbConnection.Open?displayProperty=nameWithType> メソッドにより、解析された接続パラメーターがデータ ソースに渡されます。</span><span class="sxs-lookup"><span data-stu-id="476bd-107">Then the <xref:System.Data.Common.DbConnection.Open?displayProperty=nameWithType> method passes the parsed connection parameters to the data source.</span></span> <span data-ttu-id="476bd-108">データ ソースでは、さらに検証が行われて、接続が確立されます。</span><span class="sxs-lookup"><span data-stu-id="476bd-108">The data source performs further validation and establishes a connection.</span></span>

## <a name="connection-string-syntax"></a><span data-ttu-id="476bd-109">接続文字列の構文</span><span class="sxs-lookup"><span data-stu-id="476bd-109">Connection string syntax</span></span>

<span data-ttu-id="476bd-110">接続文字列は、キーと値パラメーターのペアをセミコロンで区切ったリストです。</span><span class="sxs-lookup"><span data-stu-id="476bd-110">A connection string is a semicolon-delimited list of key/value parameter pairs:</span></span>

```csharp
keyword1=value; keyword2=value;
```

<span data-ttu-id="476bd-111">キーワードの大文字と小文字は区別されません。</span><span class="sxs-lookup"><span data-stu-id="476bd-111">Keywords are not case-sensitive.</span></span> <span data-ttu-id="476bd-112">ただし、データ ソースによっては、値の大文字小文字が区別されます。</span><span class="sxs-lookup"><span data-stu-id="476bd-112">Values, however, may be case-sensitive, depending on the data source.</span></span> <span data-ttu-id="476bd-113">キーワードと値はどちらも、[空白文字](https://en.wikipedia.org/wiki/Whitespace_character#Unicode)が含まれていてもかまいません。</span><span class="sxs-lookup"><span data-stu-id="476bd-113">Both keywords and values may contain [whitespace characters](https://en.wikipedia.org/wiki/Whitespace_character#Unicode).</span></span> <span data-ttu-id="476bd-114">キーワードおよび引用符で囲まれていない値では、先頭と末尾の空白文字は無視されます。</span><span class="sxs-lookup"><span data-stu-id="476bd-114">Leading and trailing white space is ignored in keywords and unquoted values.</span></span>

<span data-ttu-id="476bd-115">値にセミコロン、[Unicode 制御文字](https://en.wikipedia.org/wiki/Unicode_control_characters)、先頭または末尾の空白が含まれている場合は、単一引用符または二重引用符で囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="476bd-115">If a value contains the semicolon, [Unicode control characters](https://en.wikipedia.org/wiki/Unicode_control_characters), or leading or trailing white space, it must be enclosed in single or double quotation marks.</span></span> <span data-ttu-id="476bd-116">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="476bd-116">For example:</span></span>

```csharp
Keyword=" whitespace  ";
Keyword='special;character';
```

<span data-ttu-id="476bd-117">囲んでいる文字が、囲まれた値内に出現することはできません。</span><span class="sxs-lookup"><span data-stu-id="476bd-117">The enclosing character may not occur within the value it encloses.</span></span> <span data-ttu-id="476bd-118">したがって、単一引用符が含まれる値は、二重引用符でのみ囲むことができます。その逆も同様です。</span><span class="sxs-lookup"><span data-stu-id="476bd-118">Therefore, a value containing single quotation marks can be enclosed only in double quotation marks, and vice versa:</span></span>

```csharp
Keyword='double"quotation;mark';
Keyword="single'quotation;mark";
```

<span data-ttu-id="476bd-119">また、囲んでいる文字を 2 つ続けて使用することにより、エスケープすることもできます。</span><span class="sxs-lookup"><span data-stu-id="476bd-119">You can also escape the enclosing character by using two of them together:</span></span>

```csharp
Keyword="double""quotation";
Keyword='single''quotation';
```

<span data-ttu-id="476bd-120">引用符自体と等号は、エスケープする必要がないため、次の接続文字列は有効です。</span><span class="sxs-lookup"><span data-stu-id="476bd-120">The quotation marks themselves, as well as the equals sign, do not require escaping, so the following connection strings are valid:</span></span>

```csharp
Keyword=no "escaping" 'required';
Keyword=a=b=c
```

<span data-ttu-id="476bd-121">各値は、次のセミコロンまたは文字列の末尾まで読み取られるため、後者の例の値は `a=b=c` であり、最後のセミコロンは省略可能です。</span><span class="sxs-lookup"><span data-stu-id="476bd-121">Since each value is read till the next semicolon or the end of string, the value in the latter example is `a=b=c`, and the final semicolon is optional.</span></span>

<span data-ttu-id="476bd-122">すべての接続文字列の基本的な構文は、上で説明したものと同じです。</span><span class="sxs-lookup"><span data-stu-id="476bd-122">All connection strings share the same basic syntax described above.</span></span> <span data-ttu-id="476bd-123">ただし、認識されるキーワードのセットはプロバイダーによって異なり、*ODBC* などの以前の API から長年にわたって進化しています。</span><span class="sxs-lookup"><span data-stu-id="476bd-123">The set of recognized keywords depends on the provider, however, and has evolved over the years from earlier APIs such as *ODBC*.</span></span> <span data-ttu-id="476bd-124">*.NET Framework* Data Provider for *SQL Server* (`SqlClient`) では、古い API の多くのキーワードがサポートされていますが、一般に、より柔軟性が高く、多くの一般的な接続文字列キーワードに対してシノニムを受け付けます。</span><span class="sxs-lookup"><span data-stu-id="476bd-124">The *.NET Framework* data provider for *SQL Server* (`SqlClient`) supports many keywords from older APIs, but is generally more flexible and accepts synonyms for many of the common connection string keywords.</span></span>

<span data-ttu-id="476bd-125">入力ミスによってエラーが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="476bd-125">Typing mistakes can cause errors.</span></span> <span data-ttu-id="476bd-126">たとえば、`Integrated Security=true` は有効ですが、`IntegratedSecurity=true` ではエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="476bd-126">For example, `Integrated Security=true` is valid, but `IntegratedSecurity=true` causes an error.</span></span>

<span data-ttu-id="476bd-127">実行時に検証されていないユーザー入力から接続文字列を手動で構築すると、文字列のインジェクション攻撃に弱くなり、データ ソースのセキュリティが脅かされます。</span><span class="sxs-lookup"><span data-stu-id="476bd-127">Connection strings constructed manually at run time from unvalidated user input are vulnerable to string-injection attacks and jeopardize security at the data source.</span></span> <span data-ttu-id="476bd-128">こうした問題に対処するため、*ADO.NET* 2.0 では、各 *.NET Framework* データ プロバイダー用の[接続文字列ビルダー](connection-string-builders.md)が導入されました。</span><span class="sxs-lookup"><span data-stu-id="476bd-128">To address these problems, *ADO.NET* 2.0 introduced [connection string builders](connection-string-builders.md) for each *.NET Framework* data provider.</span></span> <span data-ttu-id="476bd-129">これらの接続文字列ビルダーでは、厳密に型指定されたプロパティとしてパラメーターが公開され、データ ソースに送信される前に接続文字列を検証できます。</span><span class="sxs-lookup"><span data-stu-id="476bd-129">These connection string builders expose parameters as strongly typed properties, and make it possible to validate the connection string before it's sent to the data source.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="476bd-130">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="476bd-130">In This Section</span></span>

<span data-ttu-id="476bd-131">[接続文字列ビルダー](connection-string-builders.md)</span><span class="sxs-lookup"><span data-stu-id="476bd-131">[Connection String Builders](connection-string-builders.md)</span></span>\
<span data-ttu-id="476bd-132">`ConnectionStringBuilder` クラスを使用して、有効な接続文字列を実行時に作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="476bd-132">Demonstrates how to use the `ConnectionStringBuilder` classes to construct valid connection strings at run time.</span></span>

<span data-ttu-id="476bd-133">[接続文字列と構成ファイル](connection-strings-and-configuration-files.md)</span><span class="sxs-lookup"><span data-stu-id="476bd-133">[Connection Strings and Configuration Files](connection-strings-and-configuration-files.md)</span></span>\
<span data-ttu-id="476bd-134">構成ファイルを使用した接続文字列の格納と取得の方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="476bd-134">Demonstrates how to store and retrieve connection strings in configuration files.</span></span>

<span data-ttu-id="476bd-135">[接続文字列の構文](connection-string-syntax.md)</span><span class="sxs-lookup"><span data-stu-id="476bd-135">[Connection String Syntax](connection-string-syntax.md)</span></span>\
<span data-ttu-id="476bd-136">`SqlClient`、`OracleClient`、`OleDb`、`Odbc` の各プロバイダーに固有の接続文字列を構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="476bd-136">Describes how to configure provider-specific connection strings for `SqlClient`, `OracleClient`, `OleDb`, and `Odbc`.</span></span>

<span data-ttu-id="476bd-137">[接続情報の保護](protecting-connection-information.md)</span><span class="sxs-lookup"><span data-stu-id="476bd-137">[Protecting Connection Information](protecting-connection-information.md)</span></span>\
<span data-ttu-id="476bd-138">データ ソースへの接続に使用する情報を保護する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="476bd-138">Demonstrates techniques for protecting information used to connect to a data source.</span></span>

## <a name="see-also"></a><span data-ttu-id="476bd-139">関連項目</span><span class="sxs-lookup"><span data-stu-id="476bd-139">See also</span></span>

- [<span data-ttu-id="476bd-140">データ ソースへの接続</span><span class="sxs-lookup"><span data-stu-id="476bd-140">Connecting to a Data Source</span></span>](/cpp/data/odbc/connecting-to-a-data-source)
- [<span data-ttu-id="476bd-141">ADO.NET の概要</span><span class="sxs-lookup"><span data-stu-id="476bd-141">ADO.NET Overview</span></span>](ado-net-overview.md)
