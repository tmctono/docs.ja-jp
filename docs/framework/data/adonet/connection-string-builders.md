---
title: 接続文字列ビルダー
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8434b608-c4d3-43d3-8ae3-6d8c6b726759
ms.openlocfilehash: afafe5d1eaddaef3b9f0069908b365e40ea4ed29
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70785687"
---
# <a name="connection-string-builders"></a><span data-ttu-id="e43f8-102">接続文字列ビルダー</span><span class="sxs-lookup"><span data-stu-id="e43f8-102">Connection String Builders</span></span>
<span data-ttu-id="e43f8-103">以前のバージョンの ADO.NET では、文字列値が連結された接続文字列のコンパイル時チェックは行われませんでした<xref:System.ArgumentException>。そのため、実行時に、正しくないキーワードがを生成しました。</span><span class="sxs-lookup"><span data-stu-id="e43f8-103">In earlier versions of ADO.NET, compile-time checking of connection strings with concatenated string values did not occur, so that at run time, an incorrect keyword generated an <xref:System.ArgumentException>.</span></span> <span data-ttu-id="e43f8-104">各 .NET Framework データプロバイダーでは、接続文字列キーワードに対して異なる構文がサポートされていたため、手動で有効な接続文字列を構築することは困難です。</span><span class="sxs-lookup"><span data-stu-id="e43f8-104">Each of the .NET Framework data providers supported different syntax for connection string keywords, which made constructing valid connection strings difficult if done manually.</span></span> <span data-ttu-id="e43f8-105">この問題に対処するために、ADO.NET 2.0 では、.NET Framework データプロバイダーごとに新しい接続文字列ビルダーが導入されました。</span><span class="sxs-lookup"><span data-stu-id="e43f8-105">To address this problem, ADO.NET 2.0 introduced new connection string builders for each .NET Framework data provider.</span></span> <span data-ttu-id="e43f8-106">各データ プロバイダーは、<xref:System.Data.Common.DbConnectionStringBuilder> から継承した、厳密に型指定された接続文字列ビルダー クラスを提供しています。</span><span class="sxs-lookup"><span data-stu-id="e43f8-106">Each data provider includes a strongly typed connection string builder class that inherits from <xref:System.Data.Common.DbConnectionStringBuilder>.</span></span> <span data-ttu-id="e43f8-107">次の表に、.NET Framework データプロバイダーとそれに関連付けられている接続文字列ビルダークラスを示します。</span><span class="sxs-lookup"><span data-stu-id="e43f8-107">The following table lists the .NET Framework data providers and their associated connection string builder classes.</span></span>  
  
|<span data-ttu-id="e43f8-108">プロバイダー</span><span class="sxs-lookup"><span data-stu-id="e43f8-108">Provider</span></span>|<span data-ttu-id="e43f8-109">ConnectionStringBuilder クラス</span><span class="sxs-lookup"><span data-stu-id="e43f8-109">ConnectionStringBuilder class</span></span>|  
|--------------|-----------------------------------|  
|<xref:System.Data.SqlClient>|<xref:System.Data.SqlClient.SqlConnectionStringBuilder?displayProperty=nameWithType>|  
|<xref:System.Data.OleDb>|<xref:System.Data.OleDb.OleDbConnectionStringBuilder?displayProperty=nameWithType>|  
|<xref:System.Data.Odbc>|<xref:System.Data.Odbc.OdbcConnectionStringBuilder?displayProperty=nameWithType>|  
|<xref:System.Data.OracleClient>|<xref:System.Data.OracleClient.OracleConnectionStringBuilder?displayProperty=nameWithType>|  
  
## <a name="connection-string-injection-attacks"></a><span data-ttu-id="e43f8-110">接続文字列のインジェクション攻撃</span><span class="sxs-lookup"><span data-stu-id="e43f8-110">Connection String Injection Attacks</span></span>  
 <span data-ttu-id="e43f8-111">ユーザー入力から文字列を動的に連結することによって接続文字列を構築している場合、接続文字列のインジェクション攻撃を受ける可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e43f8-111">A connection string injection attack can occur when dynamic string concatenation is used to build connection strings that are based on user input.</span></span> <span data-ttu-id="e43f8-112">文字列の検証や悪意のある文字のエスケープを怠ると、機密データなど、サーバー上のリソースへのアクセスを攻撃者に許してしまうことも考えられます。</span><span class="sxs-lookup"><span data-stu-id="e43f8-112">If the string is not validated and malicious text or characters not escaped, an attacker can potentially access sensitive data or other resources on the server.</span></span> <span data-ttu-id="e43f8-113">たとえば、セミコロンに続けて値を追加するだけでも攻撃が成立します。</span><span class="sxs-lookup"><span data-stu-id="e43f8-113">For example, an attacker could mount an attack by supplying a semicolon and appending an additional value.</span></span> <span data-ttu-id="e43f8-114">接続文字列は "後勝ち" のアルゴリズムで解析されるため、悪質な入力データによって本来の値が置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="e43f8-114">The connection string is parsed by using a "last one wins" algorithm, and the hostile input is substituted for a legitimate value.</span></span>  
  
 <span data-ttu-id="e43f8-115">接続文字列ビルダー クラスは推測に頼った作業を排除し、構文エラーやセキュリティ上の脆弱性を防ぐことを目的に設計されています。</span><span class="sxs-lookup"><span data-stu-id="e43f8-115">The connection string builder classes are designed to eliminate guesswork and protect against syntax errors and security vulnerabilities.</span></span> <span data-ttu-id="e43f8-116">このクラスには、各データ プロバイダーによってサポートされた既知のキーと値のペアに対応するプロパティおよびメソッドが存在します。</span><span class="sxs-lookup"><span data-stu-id="e43f8-116">They provide methods and properties corresponding to the known key/value pairs permitted by each data provider.</span></span> <span data-ttu-id="e43f8-117">それぞれのクラスは、あらかじめ決められた一連のシノニムを管理しており、特定のシノニムを対応する既知のキー名に変換することができます。</span><span class="sxs-lookup"><span data-stu-id="e43f8-117">Each class maintains a fixed collection of synonyms and can translate from a synonym to the corresponding well-known key name.</span></span> <span data-ttu-id="e43f8-118">有効なキーと値のペアに対してチェックが実行され、無効なペアが見つかると例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="e43f8-118">Checks are performed for valid key/value pairs and an invalid pair throws an exception.</span></span> <span data-ttu-id="e43f8-119">また、挿入された値は安全な方法で処理されます。</span><span class="sxs-lookup"><span data-stu-id="e43f8-119">In addition, injected values are handled in a safe manner.</span></span>  
  
 <span data-ttu-id="e43f8-120">次の例を実行すると、<xref:System.Data.SqlClient.SqlConnectionStringBuilder> の設定に対して挿入された余分な値が、`Initial Catalog` によってどのように処理されるかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="e43f8-120">The following example demonstrates how the <xref:System.Data.SqlClient.SqlConnectionStringBuilder> handles an inserted extra value for the `Initial Catalog` setting.</span></span>  
  
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
  
 <span data-ttu-id="e43f8-121">出力結果を見ると、挿入された値が <xref:System.Data.SqlClient.SqlConnectionStringBuilder> によって適切に処理されていることがわかります。二重引用符内の余分な値は、新しいキーと値のペアとして接続文字列に追加されるのではなくエスケープされています。</span><span class="sxs-lookup"><span data-stu-id="e43f8-121">The output shows that the <xref:System.Data.SqlClient.SqlConnectionStringBuilder> handled this correctly by escaping the extra value in double quotation marks instead of appending it to the connection string as a new key/value pair.</span></span>  
  
```  
data source=(local);Integrated Security=True;  
initial catalog="AdventureWorks;NewValue=Bad"  
```  
  
## <a name="building-connection-strings-from-configuration-files"></a><span data-ttu-id="e43f8-122">構成ファイルからの接続文字列の作成</span><span class="sxs-lookup"><span data-stu-id="e43f8-122">Building Connection Strings from Configuration Files</span></span>  
 <span data-ttu-id="e43f8-123">接続文字列の特定の要素があらかじめわかっている場合、接続文字列を構成ファイルに格納しておき、それを実行時に取得することによって完全な接続文字列を作成できます。</span><span class="sxs-lookup"><span data-stu-id="e43f8-123">If certain elements of a connection string are known beforehand, they can be stored in a configuration file and retrieved at run time to construct a complete connection string.</span></span> <span data-ttu-id="e43f8-124">たとえば、サーバー名は不明でも、データベースの名前はあらかじめ把握できる場合があります。</span><span class="sxs-lookup"><span data-stu-id="e43f8-124">For example, the name of the database might be known in advance, but not the name of the server.</span></span> <span data-ttu-id="e43f8-125">または、ユーザーに名前とパスワードだけを実行時に指定してもらい、それ以外の値を接続文字列に挿入できないようにしたい場合もあります。</span><span class="sxs-lookup"><span data-stu-id="e43f8-125">Or you might want a user to supply a name and password at run time without being able to inject other values into the connection string.</span></span>  
  
 <span data-ttu-id="e43f8-126">接続文字列ビルダーには、<xref:System.String> を引数として受け取るオーバーロード コンストラクターがあります。この引数に対して接続文字列を部分的に指定しておき、それ以外の部分をユーザー入力で補完することも可能です。</span><span class="sxs-lookup"><span data-stu-id="e43f8-126">One of the overloaded constructors for a connection string builder takes a <xref:System.String> as an argument, which enables you to supply a partial connection string that can then be completed from user input.</span></span> <span data-ttu-id="e43f8-127">部分的な接続文字列は構成ファイルに保存し、実行時に取得できます。</span><span class="sxs-lookup"><span data-stu-id="e43f8-127">The partial connection string can be stored in a configuration file and retrieved at run time.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e43f8-128">構成ファイルへのプログラム アクセスは <xref:System.Configuration> 名前空間によって実現できます。Web アプリケーションの場合は <xref:System.Web.Configuration.WebConfigurationManager> を、Windows アプリケーションの場合は <xref:System.Configuration.ConfigurationManager> を使用します。</span><span class="sxs-lookup"><span data-stu-id="e43f8-128">The <xref:System.Configuration> namespace allows programmatic access to configuration files that use the <xref:System.Web.Configuration.WebConfigurationManager> for Web applications and the <xref:System.Configuration.ConfigurationManager> for Windows applications.</span></span> <span data-ttu-id="e43f8-129">接続文字列と構成ファイルの操作の詳細については、「[接続文字列と構成ファイル](connection-strings-and-configuration-files.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e43f8-129">For more information about working with connection strings and configuration files, see [Connection Strings and Configuration Files](connection-strings-and-configuration-files.md).</span></span>  
  
### <a name="example"></a><span data-ttu-id="e43f8-130">例</span><span class="sxs-lookup"><span data-stu-id="e43f8-130">Example</span></span>  
 <span data-ttu-id="e43f8-131">この例では、接続文字列の一部を構成ファイルから取得し、<xref:System.Data.SqlClient.SqlConnectionStringBuilder.DataSource%2A> の <xref:System.Data.SqlClient.SqlConnectionStringBuilder.UserID%2A> プロパティ、<xref:System.Data.SqlClient.SqlConnectionStringBuilder.Password%2A> プロパティ、および <xref:System.Data.SqlClient.SqlConnectionStringBuilder> プロパティを設定することによって接続文字列全体を作成します。</span><span class="sxs-lookup"><span data-stu-id="e43f8-131">This example demonstrates retrieving a partial connection string from a configuration file and completing it by setting the <xref:System.Data.SqlClient.SqlConnectionStringBuilder.DataSource%2A>, <xref:System.Data.SqlClient.SqlConnectionStringBuilder.UserID%2A>, and <xref:System.Data.SqlClient.SqlConnectionStringBuilder.Password%2A> properties of the <xref:System.Data.SqlClient.SqlConnectionStringBuilder>.</span></span> <span data-ttu-id="e43f8-132">構成ファイルは次のように定義されています。</span><span class="sxs-lookup"><span data-stu-id="e43f8-132">The configuration file is defined as follows.</span></span>  
  
```xml  
<connectionStrings>  
  <clear/>  
  <add name="partialConnectString"   
    connectionString="Initial Catalog=Northwind;"  
    providerName="System.Data.SqlClient" />  
</connectionStrings>  
```  
  
> [!NOTE]
> <span data-ttu-id="e43f8-133">このコードを実行するには、プロジェクトで `System.Configuration.dll` を参照設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e43f8-133">You must set a reference to the `System.Configuration.dll` in your project for the code to run.</span></span>  
  
 [!code-csharp[DataWorks SqlConnectionStringBuilder.UserNamePwd#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlConnectionStringBuilder.UserNamePwd/CS/source.cs#1)]
 [!code-vb[DataWorks SqlConnectionStringBuilder.UserNamePwd#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlConnectionStringBuilder.UserNamePwd/VB/source.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="e43f8-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="e43f8-134">See also</span></span>

- [<span data-ttu-id="e43f8-135">接続文字列</span><span class="sxs-lookup"><span data-stu-id="e43f8-135">Connection Strings</span></span>](connection-strings.md)
- [<span data-ttu-id="e43f8-136">プライバシーとデータ セキュリティ</span><span class="sxs-lookup"><span data-stu-id="e43f8-136">Privacy and Data Security</span></span>](privacy-and-data-security.md)
- [<span data-ttu-id="e43f8-137">ADO.NET の概要</span><span class="sxs-lookup"><span data-stu-id="e43f8-137">ADO.NET Overview</span></span>](ado-net-overview.md)
