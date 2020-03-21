---
title: パラメーターとしての XML 値の指定
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 2c4d08b8-fc29-4614-97fa-29c8ff7ca5b3
ms.openlocfilehash: acb94efd8b6b6b66d0cc84309c2d68ad692b08d3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174499"
---
# <a name="specifying-xml-values-as-parameters"></a><span data-ttu-id="268fa-102">パラメーターとしての XML 値の指定</span><span class="sxs-lookup"><span data-stu-id="268fa-102">Specifying XML Values as Parameters</span></span>
<span data-ttu-id="268fa-103">値が XML 文字列であるパラメーターがクエリに必要な場合、開発者はその値を **SqlXml** のインスタンスを使用して提供することができます。</span><span class="sxs-lookup"><span data-stu-id="268fa-103">If a query requires a parameter whose value is an XML string, developers can supply that value using an instance of the **SqlXml** data type.</span></span> <span data-ttu-id="268fa-104">特別な処理は必要ありません。SQL Server の XML 列は、他のデータ型と同じ方法でパラメーター値を受け入れます。</span><span class="sxs-lookup"><span data-stu-id="268fa-104">There really are no tricks; XML columns in SQL Server accept parameter values in exactly the same way as other data types.</span></span>  
  
## <a name="example"></a><span data-ttu-id="268fa-105">例</span><span class="sxs-lookup"><span data-stu-id="268fa-105">Example</span></span>  
 <span data-ttu-id="268fa-106">次のコンソール アプリケーションでは、**AdventureWorks** データベースに新しいテーブルを作成します。</span><span class="sxs-lookup"><span data-stu-id="268fa-106">The following console application creates a new table in the **AdventureWorks** database.</span></span> <span data-ttu-id="268fa-107">新しいテーブルには、**SalesID** という名前の列と、**SalesInfo** という名前の XML 列があります。</span><span class="sxs-lookup"><span data-stu-id="268fa-107">The new table includes a column named **SalesID** and an XML column named **SalesInfo**.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="268fa-108">**AdventureWorks** サンプル データベースは、既定では SQL Server のインストール時にはインストールされません。</span><span class="sxs-lookup"><span data-stu-id="268fa-108">The **AdventureWorks** sample database is not installed by default when you install SQL Server.</span></span> <span data-ttu-id="268fa-109">それをインストールするには、SQL Server Setup を実行します。</span><span class="sxs-lookup"><span data-stu-id="268fa-109">You can install it by running SQL Server Setup.</span></span>  
  
 <span data-ttu-id="268fa-110">この例では、新しいテーブルに行を挿入するための <xref:System.Data.SqlClient.SqlCommand> オブジェクトを準備します。</span><span class="sxs-lookup"><span data-stu-id="268fa-110">The example prepares a <xref:System.Data.SqlClient.SqlCommand> object to insert a row in the new table.</span></span> <span data-ttu-id="268fa-111">保存されたファイルは、**SalesInfo** 列に必要な XML データを提供します。</span><span class="sxs-lookup"><span data-stu-id="268fa-111">A saved file provides the XML data needed for the **SalesInfo** column.</span></span>  
  
 <span data-ttu-id="268fa-112">この例の実行に必要なファイルを作成するには、プロジェクトと同じフォルダーに新しいテキスト ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="268fa-112">To create the file needed for the example to run, create a new text file in the same folder as your project.</span></span> <span data-ttu-id="268fa-113">このファイルの名前を MyTestStoreData.xml にします。</span><span class="sxs-lookup"><span data-stu-id="268fa-113">Name the file MyTestStoreData.xml.</span></span> <span data-ttu-id="268fa-114">メモ帳でファイルを開き、次のテキストをコピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="268fa-114">Open the file in Notepad and copy and paste the following text:</span></span>  
  
```xml  
<StoreSurvey xmlns="http://schemas.microsoft.com/sqlserver/2004/07/adventure-works/StoreSurvey">  
  <AnnualSales>300000</AnnualSales>  
  <AnnualRevenue>30000</AnnualRevenue>  
  <BankName>International Bank</BankName>  
  <BusinessType>BM</BusinessType>  
  <YearOpened>1970</YearOpened>  
  <Specialty>Road</Specialty>  
  <SquareFeet>7000</SquareFeet>  
  <Brands>3</Brands>  
  <Internet>T1</Internet>  
  <NumberEmployees>2</NumberEmployees>  
</StoreSurvey>  
```  
  
```vb  
Imports System  
Imports System.Data.SqlClient  
Imports System.Data.SqlTypes  
Imports System.Xml  
  
Module Module1  
    Sub Main()  
  
        Using connection As SqlConnection = New SqlConnection(GetConnectionString())  
        connection.Open()  
  
        ' Create a sample table (dropping first if it already  
        ' exists.)  
        Dim commandNewTable As String = _  
         "IF EXISTS (SELECT * FROM dbo.sysobjects " & _  
         "WHERE id = object_id(N'[dbo].[XmlDataTypeSample]') " & _  
         "AND OBJECTPROPERTY(id, N'IsUserTable') = 1) " & _  
         "DROP TABLE [dbo].[XmlDataTypeSample];" & _  
         "CREATE TABLE [dbo].[XmlDataTypeSample](" & _  
         "[SalesID] [int] IDENTITY(1,1) NOT NULL, " & _  
         "[SalesInfo] [xml])"  
  
        Dim commandAdd As New _  
         SqlCommand(commandNewTable, connection)  
        commandAdd.ExecuteNonQuery()  
  
        Dim commandText As String = _  
         "INSERT INTO [dbo].[XmlDataTypeSample] " & _  
           "([SalesInfo] ) " & _  
           "VALUES(@xmlParameter )"  
  
        Dim command As New SqlCommand(commandText, connection)  
  
        ' Read the saved XML document as a
        ' SqlXml-data typed variable.  
        Dim newXml As SqlXml = _  
         New SqlXml(New XmlTextReader("MyTestStoreData.xml"))  
  
        ' Supply the SqlXml value for the value of the parameter.  
        command.Parameters.AddWithValue("@xmlParameter", newXml)  
  
        Dim result As Integer = command.ExecuteNonQuery()  
        Console.WriteLine(result & " row was added.")  
        Console.WriteLine("Press Enter to continue.")  
        Console.ReadLine()  
    End Using  
End Sub  
  
    Private Function GetConnectionString() As String  
        ' To avoid storing the connection string in your code,
        ' you can retrieve it from a configuration file.
        Return "Data Source=(local);Integrated Security=SSPI;" & _  
          "Initial Catalog=AdventureWorks"  
    End Function  
End Module  
```  
  
```csharp  
using System;  
using System.Data;  
using System.Data.SqlClient;  
using System.Xml;  
using System.Data.SqlTypes;  
  
class Class1  
{  
    static void Main()  
    {  
        using (SqlConnection connection = new SqlConnection(GetConnectionString()))  
       {  
        connection.Open();  
        //  Create a sample table (dropping first if it already  
        //  exists.)  
  
        string commandNewTable =
            "IF EXISTS (SELECT * FROM dbo.sysobjects " +
            "WHERE id = " +  
                  "object_id(N'[dbo].[XmlDataTypeSample]') " +
            "AND OBJECTPROPERTY(id, N'IsUserTable') = 1) " +
            "DROP TABLE [dbo].[XmlDataTypeSample];" +
            "CREATE TABLE [dbo].[XmlDataTypeSample](" +
            "[SalesID] [int] IDENTITY(1,1) NOT NULL, " +
            "[SalesInfo] [xml])";  
        SqlCommand commandAdd =
                   new SqlCommand(commandNewTable, connection);  
        commandAdd.ExecuteNonQuery();  
        string commandText =
            "INSERT INTO [dbo].[XmlDataTypeSample] " +
            "([SalesInfo] ) " +
            "VALUES(@xmlParameter )";  
        SqlCommand command =
                  new SqlCommand(commandText, connection);  
  
        //  Read the saved XML document as a
        //  SqlXml-data typed variable.  
        SqlXml newXml =
            new SqlXml(new XmlTextReader("MyTestStoreData.xml"));  
  
        //  Supply the SqlXml value for the value of the parameter.  
        command.Parameters.AddWithValue("@xmlParameter", newXml);  
  
        int result = command.ExecuteNonQuery();  
        Console.WriteLine(result + " row was added.");  
        Console.WriteLine("Press Enter to continue.");  
        Console.ReadLine();  
    }  
  }  
  
    private static string GetConnectionString()  
    {  
        // To avoid storing the connection string in your code,
        // you can retrieve it from a configuration file.
        return "Data Source=(local);Integrated Security=true;" +  
        "Initial Catalog=AdventureWorks; ";  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="268fa-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="268fa-115">See also</span></span>

- <xref:System.Data.SqlTypes.SqlXml>
- [<span data-ttu-id="268fa-116">XML データの SQL サーバー</span><span class="sxs-lookup"><span data-stu-id="268fa-116">XML Data in SQL Server</span></span>](xml-data-in-sql-server.md)
- [<span data-ttu-id="268fa-117">ADO.NET の概要</span><span class="sxs-lookup"><span data-stu-id="268fa-117">ADO.NET Overview</span></span>](../ado-net-overview.md)
