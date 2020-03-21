---
title: Oracle BFILE
ms.date: 03/30/2017
ms.assetid: 341bbf84-4734-4d44-8723-ccedee954e21
ms.openlocfilehash: 40060a7ea8576e08140d972072d086606d640366
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79149441"
---
# <a name="oracle-bfiles"></a><span data-ttu-id="42d41-102">Oracle BFILE</span><span class="sxs-lookup"><span data-stu-id="42d41-102">Oracle BFILEs</span></span>
<span data-ttu-id="42d41-103">.NET Framework Data Provider for Oracle には、<xref:System.Data.OracleClient.OracleBFile> クラスが含まれています。このクラスは、Oracle <xref:System.Data.OracleClient.OracleType.BFile> データ型で使用されます。</span><span class="sxs-lookup"><span data-stu-id="42d41-103">The .NET Framework Data Provider for Oracle includes the <xref:System.Data.OracleClient.OracleBFile> class, which is used to work with the Oracle <xref:System.Data.OracleClient.OracleType.BFile> data type.</span></span>  
  
 <span data-ttu-id="42d41-104">Oracle **BFILE**データ型は、最大サイズが 4 ギガバイトのバイナリ データへの参照を含む Oracle **LOB**データ型です。</span><span class="sxs-lookup"><span data-stu-id="42d41-104">The Oracle **BFILE** data type is an Oracle **LOB** data type that contains a reference to binary data with a maximum size of 4 gigabytes.</span></span> <span data-ttu-id="42d41-105">Oracle **BFILE**は、そのデータがサーバーではなくオペレーティング システムの物理ファイルに格納されるという点で、他の Oracle **LOB**データ型とは異なります。</span><span class="sxs-lookup"><span data-stu-id="42d41-105">An Oracle **BFILE** differs from other Oracle **LOB** data types in that its data is stored in a physical file in the operating system instead of on the server.</span></span> <span data-ttu-id="42d41-106">**BFILE**データ型は、データへの読み取り専用アクセスを提供することに注意してください。</span><span class="sxs-lookup"><span data-stu-id="42d41-106">Note that the **BFILE** data type provides read-only access to data.</span></span>  
  
 <span data-ttu-id="42d41-107">**Lob**データ・タイプと区別する**BFILE**データ・タイプの他の特性は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="42d41-107">Other characteristics of a **BFILE** data type that distinguish it from a **LOB** data type are that it:</span></span>  
  
- <span data-ttu-id="42d41-108">非構造化データの保持。</span><span class="sxs-lookup"><span data-stu-id="42d41-108">Contains unstructured data.</span></span>  
  
- <span data-ttu-id="42d41-109">サーバー側チャンキングのサポート。</span><span class="sxs-lookup"><span data-stu-id="42d41-109">Supports server-side chunking.</span></span>  
  
- <span data-ttu-id="42d41-110">参照コピーのセマンティクスの使用。</span><span class="sxs-lookup"><span data-stu-id="42d41-110">Uses reference copy semantics.</span></span> <span data-ttu-id="42d41-111">たとえば **、BFILE**でコピー操作を実行すると **、BFILE**ロケーター (ファイルへの参照) のみがコピーされます。</span><span class="sxs-lookup"><span data-stu-id="42d41-111">For example, if you perform a copy operation on a **BFILE**, only the **BFILE** locator (which is a reference to the file) is copied.</span></span> <span data-ttu-id="42d41-112">ファイル内のデータはコピーされません。</span><span class="sxs-lookup"><span data-stu-id="42d41-112">The data in the file is not copied.</span></span>  
  
 <span data-ttu-id="42d41-113">**BFILE**データ型は、サイズが大きい LOB を参照するために使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="42d41-113">The **BFILE** data type should be used for referencing LOBs that are large in size, and therefore, not practical to store in the database.</span></span> <span data-ttu-id="42d41-114">**BFILE**データ・タイプを使用する場合 **、LOB**データ・タイプと比較して、より多くのクライアント、サーバー、および通信オーバーヘッドが必要になります。</span><span class="sxs-lookup"><span data-stu-id="42d41-114">More client, server, and communication overhead is involved when using a **BFILE** data type compared with the **LOB** data type.</span></span> <span data-ttu-id="42d41-115">少量のデータを取得するだけでよい場合は **、BFILE**にアクセスする方が効率的です。</span><span class="sxs-lookup"><span data-stu-id="42d41-115">It is more efficient to access a **BFILE** if you only need to obtain a small amount of data.</span></span> <span data-ttu-id="42d41-116">オブジェクト全体を取得したい場合は、データベースに常駐する LOB へのアクセスがいっそう効果的です。</span><span class="sxs-lookup"><span data-stu-id="42d41-116">It is more efficient to access database-resident LOBs if you need to obtain the entire object.</span></span>  
  
 <span data-ttu-id="42d41-117">各非 NULL **OracleBFile**オブジェクトは、基になる物理ファイルの場所を定義する 2 つのエンティティに関連付けられます。</span><span class="sxs-lookup"><span data-stu-id="42d41-117">Each non-NULL **OracleBFile** object is associated with two entities that define the location of the underlying physical file:</span></span>  
  
1. <span data-ttu-id="42d41-118">Oracle DIRECTORY オブジェクト。ファイル システムのディレクトリに対するデータベースのエイリアスです。</span><span class="sxs-lookup"><span data-stu-id="42d41-118">An Oracle DIRECTORY object, which is a database alias for a directory in the file system, and</span></span>  
  
2. <span data-ttu-id="42d41-119">基になる物理ファイルのファイル名。このファイルは、DIRECTORY オブジェクトに関連付けられたディレクトリに配置されています。</span><span class="sxs-lookup"><span data-stu-id="42d41-119">The file name of the underlying physical file, which is located in the directory associated with the DIRECTORY object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="42d41-120">例</span><span class="sxs-lookup"><span data-stu-id="42d41-120">Example</span></span>  
 <span data-ttu-id="42d41-121">次の C# の例では、Oracle テーブルに**BFILE**を作成し **、OracleBFile**オブジェクトの形式で取得する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="42d41-121">The following C# example demonstrates how you can create a **BFILE** in an Oracle table and then retrieve it in the form of an **OracleBFile** object.</span></span> <span data-ttu-id="42d41-122">この例<xref:System.Data.OracleClient.OracleDataReader>では、オブジェクトと**OracleBFile** **のシーク**および**読み取り**メソッドの使用方法を示します。</span><span class="sxs-lookup"><span data-stu-id="42d41-122">The example demonstrates using the <xref:System.Data.OracleClient.OracleDataReader> object and the **OracleBFile** **Seek** and **Read** methods.</span></span> <span data-ttu-id="42d41-123">このサンプルを使用するには、まず、Oracle サーバー上に "c:\\\bfiles" という名前のディレクトリと "MyFile.jpg" という名前のファイルを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="42d41-123">Note that in order to use this sample, you must first create a directory named "c:\\\bfiles" and file named "MyFile.jpg" on the Oracle server.</span></span>  
  
```csharp  
using System;  
using System.IO;  
using System.Data;  
using System.Data.OracleClient;  
  
public class Sample  
{  
   public static void Main(string[] args)  
   {  
      OracleConnection connection = new OracleConnection(  
        "Data Source=Oracle8i;Integrated Security=yes");  
      connection.Open();  
  
      OracleCommand command = connection.CreateCommand();  
      command.CommandText =
        "CREATE or REPLACE DIRECTORY MyDir as 'c:\\bfiles'";  
      command.ExecuteNonQuery();  
      command.CommandText =
        "DROP TABLE MyBFileTable";  
      try {  
        command.ExecuteNonQuery();  
      }  
      catch {  
      }  
      command.CommandText =
        "CREATE TABLE MyBFileTable(col1 number, col2 BFILE)";  
      command.ExecuteNonQuery();  
      command.CommandText =
        "INSERT INTO MyBFileTable values ('2', BFILENAME('MyDir', " +  
        "'MyFile.jpg'))";  
      command.ExecuteNonQuery();  
      command.CommandText = "SELECT * FROM MyBFileTable";  
  
        byte[] buffer = new byte[100];  
  
      OracleDataReader reader = command.ExecuteReader();  
      using (reader) {  
          if (reader.Read()) {  
                OracleBFile bFile = reader.GetOracleBFile(1);  
                using (bFile) {  
                  bFile.Seek(0, SeekOrigin.Begin);  
                  bFile.Read(buffer, 0, 100);  
              }  
          }  
      }  
  
      connection.Close();  
   }  
  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="42d41-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="42d41-124">See also</span></span>

- [<span data-ttu-id="42d41-125">Oracle および ADO.NET</span><span class="sxs-lookup"><span data-stu-id="42d41-125">Oracle and ADO.NET</span></span>](oracle-and-adonet.md)
- [<span data-ttu-id="42d41-126">ADO.NET の概要</span><span class="sxs-lookup"><span data-stu-id="42d41-126">ADO.NET Overview</span></span>](ado-net-overview.md)
