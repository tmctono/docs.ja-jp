---
title: 接続文字列ビルダー
description: ADO.NET のさまざまなプロバイダー向けに使用される接続文字列ビルダー クラスについて説明します。これらはすべて DbConnectionStringBuilder から継承されます。
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8434b608-c4d3-43d3-8ae3-6d8c6b726759
ms.openlocfilehash: e493140b4cf5a939e8ae8f42b617fb739ed09dec
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/02/2020
ms.locfileid: "84287065"
---
# <a name="connection-string-builders"></a><span data-ttu-id="ccf4f-103">接続文字列ビルダー</span><span class="sxs-lookup"><span data-stu-id="ccf4f-103">Connection String Builders</span></span>
<span data-ttu-id="ccf4f-104">以前のバージョンの ADO.NET では、文字列値の連結によって構築された接続文字列がコンパイル時にはチェックされません。そのため、不適切なキーワードが使用された場合、実行時に <xref:System.ArgumentException> が発生します。</span><span class="sxs-lookup"><span data-stu-id="ccf4f-104">In earlier versions of ADO.NET, compile-time checking of connection strings with concatenated string values did not occur, so that at run time, an incorrect keyword generated an <xref:System.ArgumentException>.</span></span> <span data-ttu-id="ccf4f-105">接続文字列のキーワードの構文は .NET Framework データ プロバイダーごとに異なるため、有効な接続文字列を手動で作成するのが難しいという問題がありました。</span><span class="sxs-lookup"><span data-stu-id="ccf4f-105">Each of the .NET Framework data providers supported different syntax for connection string keywords, which made constructing valid connection strings difficult if done manually.</span></span> <span data-ttu-id="ccf4f-106">この問題に対処するため、ADO.NET 2.0 では、各 .NET Framework データ プロバイダー用の新しい接続文字列ビルダーが導入されました。</span><span class="sxs-lookup"><span data-stu-id="ccf4f-106">To address this problem, ADO.NET 2.0 introduced new connection string builders for each .NET Framework data provider.</span></span> <span data-ttu-id="ccf4f-107">各データ プロバイダーは、<xref:System.Data.Common.DbConnectionStringBuilder> を継承した、厳密に型指定された接続文字列ビルダー クラスを提供しています。</span><span class="sxs-lookup"><span data-stu-id="ccf4f-107">Each data provider includes a strongly typed connection string builder class that inherits from <xref:System.Data.Common.DbConnectionStringBuilder>.</span></span> <span data-ttu-id="ccf4f-108">次の表は、各 .NET Framework データ プロバイダーおよび対応する接続文字列ビルダー クラスの一覧です。</span><span class="sxs-lookup"><span data-stu-id="ccf4f-108">The following table lists the .NET Framework data providers and their associated connection string builder classes.</span></span>  
  
|<span data-ttu-id="ccf4f-109">プロバイダー</span><span class="sxs-lookup"><span data-stu-id="ccf4f-109">Provider</span></span>|<span data-ttu-id="ccf4f-110">ConnectionStringBuilder クラス</span><span class="sxs-lookup"><span data-stu-id="ccf4f-110">ConnectionStringBuilder class</span></span>|  
|--------------|-----------------------------------|  
|<xref:System.Data.SqlClient>|<xref:System.Data.SqlClient.SqlConnectionStringBuilder?displayProperty=nameWithType>|  
|<xref:System.Data.OleDb>|<xref:System.Data.OleDb.OleDbConnectionStringBuilder?displayProperty=nameWithType>|  
|<xref:System.Data.Odbc>|<xref:System.Data.Odbc.OdbcConnectionStringBuilder?displayProperty=nameWithType>|  
|<xref:System.Data.OracleClient>|<xref:System.Data.OracleClient.OracleConnectionStringBuilder?displayProperty=nameWithType>|  
  
## <a name="connection-string-injection-attacks"></a><span data-ttu-id="ccf4f-111">接続文字列のインジェクション攻撃</span><span class="sxs-lookup"><span data-stu-id="ccf4f-111">Connection String Injection Attacks</span></span>  
 <span data-ttu-id="ccf4f-112">ユーザー入力から文字列を動的に連結することによって接続文字列を構築している場合、接続文字列のインジェクション攻撃を受ける可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ccf4f-112">A connection string injection attack can occur when dynamic string concatenation is used to build connection strings that are based on user input.</span></span> <span data-ttu-id="ccf4f-113">文字列の検証や悪意のある文字のエスケープを怠ると、機密データなど、サーバー上のリソースへのアクセスを攻撃者に許してしまうことも考えられます。</span><span class="sxs-lookup"><span data-stu-id="ccf4f-113">If the string is not validated and malicious text or characters not escaped, an attacker can potentially access sensitive data or other resources on the server.</span></span> <span data-ttu-id="ccf4f-114">たとえば、セミコロンに続けて値を追加するだけでも攻撃が成立します。</span><span class="sxs-lookup"><span data-stu-id="ccf4f-114">For example, an attacker could mount an attack by supplying a semicolon and appending an additional value.</span></span> <span data-ttu-id="ccf4f-115">接続文字列は "後勝ち" のアルゴリズムで解析されるため、悪質な入力データによって本来の値が置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="ccf4f-115">The connection string is parsed by using a "last one wins" algorithm, and the hostile input is substituted for a legitimate value.</span></span>  
  
 <span data-ttu-id="ccf4f-116">接続文字列ビルダー クラスは推測に頼った作業を排除し、構文エラーやセキュリティ上の脆弱性を防ぐことを目的に設計されています。</span><span class="sxs-lookup"><span data-stu-id="ccf4f-116">The connection string builder classes are designed to eliminate guesswork and protect against syntax errors and security vulnerabilities.</span></span> <span data-ttu-id="ccf4f-117">このクラスには、各データ プロバイダーによってサポートされた既知のキーと値のペアに対応するプロパティおよびメソッドが存在します。</span><span class="sxs-lookup"><span data-stu-id="ccf4f-117">They provide methods and properties corresponding to the known key/value pairs permitted by each data provider.</span></span> <span data-ttu-id="ccf4f-118">それぞれのクラスは、あらかじめ決められた一連のシノニムを管理しており、特定のシノニムを対応する既知のキー名に変換することができます。</span><span class="sxs-lookup"><span data-stu-id="ccf4f-118">Each class maintains a fixed collection of synonyms and can translate from a synonym to the corresponding well-known key name.</span></span> <span data-ttu-id="ccf4f-119">有効なキーと値のペアに対してチェックが実行され、無効なペアが見つかると例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="ccf4f-119">Checks are performed for valid key/value pairs and an invalid pair throws an exception.</span></span> <span data-ttu-id="ccf4f-120">また、挿入された値は安全な方法で処理されます。</span><span class="sxs-lookup"><span data-stu-id="ccf4f-120">In addition, injected values are handled in a safe manner.</span></span>  
  
 <span data-ttu-id="ccf4f-121">次の例を実行すると、<xref:System.Data.SqlClient.SqlConnectionStringBuilder> の設定に対して挿入された余分な値が、`Initial Catalog` によってどのように処理されるかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="ccf4f-121">The following example demonstrates how the <xref:System.Data.SqlClient.SqlConnectionStringBuilder> handles an inserted extra value for the `Initial Catalog` setting.</span></span>  
  
```vb  
Dim builder As New System.Data.SqlClient.SqlConnectionStringBuilder  
builder("Data Source") = "(local)"  
builder("Integrated Security") = True  
builder("Initial Catalog") = "AdventureWorks;NewValue=Bad"  
Console.WriteLine(builder.ConnectionString)  
```  
  
```csharp  
System.Data.SqlClient.SqlConnectionStringBuilder builder =  
  new System.Data.SqlClient.SqlConnectionStringBuilder();  
builder["Data Source"] = "(local)";  
builder["integrated Security"] = true;  
builder["Initial Catalog"] = "AdventureWorks;NewValue=Bad";  
Console.WriteLine(builder.ConnectionString);  
```  
  
 <span data-ttu-id="ccf4f-122">出力結果を見ると、挿入された値が <xref:System.Data.SqlClient.SqlConnectionStringBuilder> によって適切に処理されていることがわかります。二重引用符内の余分な値は、新しいキーと値のペアとして接続文字列に追加されるのではなくエスケープされています。</span><span class="sxs-lookup"><span data-stu-id="ccf4f-122">The output shows that the <xref:System.Data.SqlClient.SqlConnectionStringBuilder> handled this correctly by escaping the extra value in double quotation marks instead of appending it to the connection string as a new key/value pair.</span></span>  
  
```output  
data source=(local);Integrated Security=True;  
initial catalog="AdventureWorks;NewValue=Bad"  
```  
  
## <a name="building-connection-strings-from-configuration-files"></a><span data-ttu-id="ccf4f-123">構成ファイルからの接続文字列の作成</span><span class="sxs-lookup"><span data-stu-id="ccf4f-123">Building Connection Strings from Configuration Files</span></span>  
 <span data-ttu-id="ccf4f-124">接続文字列の特定の要素があらかじめわかっている場合、接続文字列を構成ファイルに格納しておき、それを実行時に取得することによって完全な接続文字列を作成できます。</span><span class="sxs-lookup"><span data-stu-id="ccf4f-124">If certain elements of a connection string are known beforehand, they can be stored in a configuration file and retrieved at run time to construct a complete connection string.</span></span> <span data-ttu-id="ccf4f-125">たとえば、サーバー名は不明でも、データベースの名前はあらかじめ把握できる場合があります。</span><span class="sxs-lookup"><span data-stu-id="ccf4f-125">For example, the name of the database might be known in advance, but not the name of the server.</span></span> <span data-ttu-id="ccf4f-126">または、ユーザーに名前とパスワードだけを実行時に指定してもらい、それ以外の値を接続文字列に挿入できないようにしたい場合もあります。</span><span class="sxs-lookup"><span data-stu-id="ccf4f-126">Or you might want a user to supply a name and password at run time without being able to inject other values into the connection string.</span></span>  
  
 <span data-ttu-id="ccf4f-127">接続文字列ビルダーには、<xref:System.String> を引数として受け取るオーバーロード コンストラクターがあります。この引数に対して接続文字列を部分的に指定しておき、それ以外の部分をユーザー入力で補完することも可能です。</span><span class="sxs-lookup"><span data-stu-id="ccf4f-127">One of the overloaded constructors for a connection string builder takes a <xref:System.String> as an argument, which enables you to supply a partial connection string that can then be completed from user input.</span></span> <span data-ttu-id="ccf4f-128">部分的な接続文字列は構成ファイルに保存し、実行時に取得できます。</span><span class="sxs-lookup"><span data-stu-id="ccf4f-128">The partial connection string can be stored in a configuration file and retrieved at run time.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ccf4f-129">構成ファイルへのプログラム アクセスは <xref:System.Configuration> 名前空間によって実現できます。Web アプリケーションの場合は <xref:System.Web.Configuration.WebConfigurationManager> を、Windows アプリケーションの場合は <xref:System.Configuration.ConfigurationManager> を使用します。</span><span class="sxs-lookup"><span data-stu-id="ccf4f-129">The <xref:System.Configuration> namespace allows programmatic access to configuration files that use the <xref:System.Web.Configuration.WebConfigurationManager> for Web applications and the <xref:System.Configuration.ConfigurationManager> for Windows applications.</span></span> <span data-ttu-id="ccf4f-130">接続文字列と構成ファイルの使用について詳しくは、「[接続文字列と構成ファイル](connection-strings-and-configuration-files.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="ccf4f-130">For more information about working with connection strings and configuration files, see [Connection Strings and Configuration Files](connection-strings-and-configuration-files.md).</span></span>  
  
### <a name="example"></a><span data-ttu-id="ccf4f-131">例</span><span class="sxs-lookup"><span data-stu-id="ccf4f-131">Example</span></span>  
 <span data-ttu-id="ccf4f-132">この例では、接続文字列の一部を構成ファイルから取得し、<xref:System.Data.SqlClient.SqlConnectionStringBuilder.DataSource%2A> の <xref:System.Data.SqlClient.SqlConnectionStringBuilder.UserID%2A> プロパティ、<xref:System.Data.SqlClient.SqlConnectionStringBuilder.Password%2A> プロパティ、および <xref:System.Data.SqlClient.SqlConnectionStringBuilder> プロパティを設定することによって接続文字列全体を作成します。</span><span class="sxs-lookup"><span data-stu-id="ccf4f-132">This example demonstrates retrieving a partial connection string from a configuration file and completing it by setting the <xref:System.Data.SqlClient.SqlConnectionStringBuilder.DataSource%2A>, <xref:System.Data.SqlClient.SqlConnectionStringBuilder.UserID%2A>, and <xref:System.Data.SqlClient.SqlConnectionStringBuilder.Password%2A> properties of the <xref:System.Data.SqlClient.SqlConnectionStringBuilder>.</span></span> <span data-ttu-id="ccf4f-133">構成ファイルは次のように定義されています。</span><span class="sxs-lookup"><span data-stu-id="ccf4f-133">The configuration file is defined as follows.</span></span>  
  
```xml  
<connectionStrings>  
  <clear/>  
  <add name="partialConnectString"
    connectionString="Initial Catalog=Northwind;"  
    providerName="System.Data.SqlClient" />  
</connectionStrings>  
```  
  
> [!NOTE]
> <span data-ttu-id="ccf4f-134">このコードを実行するには、プロジェクトで `System.Configuration.dll` を参照設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ccf4f-134">You must set a reference to the `System.Configuration.dll` in your project for the code to run.</span></span>  
  
 [!code-csharp[DataWorks SqlConnectionStringBuilder.UserNamePwd#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlConnectionStringBuilder.UserNamePwd/CS/source.cs#1)]
 [!code-vb[DataWorks SqlConnectionStringBuilder.UserNamePwd#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlConnectionStringBuilder.UserNamePwd/VB/source.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="ccf4f-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="ccf4f-135">See also</span></span>

- [<span data-ttu-id="ccf4f-136">接続文字列</span><span class="sxs-lookup"><span data-stu-id="ccf4f-136">Connection Strings</span></span>](connection-strings.md)
- [<span data-ttu-id="ccf4f-137">プライバシーとデータ セキュリティ</span><span class="sxs-lookup"><span data-stu-id="ccf4f-137">Privacy and Data Security</span></span>](privacy-and-data-security.md)
- [<span data-ttu-id="ccf4f-138">ADO.NET の概要</span><span class="sxs-lookup"><span data-stu-id="ccf4f-138">ADO.NET Overview</span></span>](ado-net-overview.md)
