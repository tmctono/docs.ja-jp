---
title: Oracle BFILE
ms.date: 03/30/2017
ms.assetid: 341bbf84-4734-4d44-8723-ccedee954e21
ms.openlocfilehash: 214140bb8fcf43154b014ea3db609d355a27af7c
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70794634"
---
# <a name="oracle-bfiles"></a><span data-ttu-id="fa02c-102">Oracle BFILE</span><span class="sxs-lookup"><span data-stu-id="fa02c-102">Oracle BFILEs</span></span>
<span data-ttu-id="fa02c-103">.NET Framework Data Provider for Oracle には、<xref:System.Data.OracleClient.OracleBFile> クラスが含まれています。このクラスは、Oracle <xref:System.Data.OracleClient.OracleType.BFile> データ型で使用されます。</span><span class="sxs-lookup"><span data-stu-id="fa02c-103">The .NET Framework Data Provider for Oracle includes the <xref:System.Data.OracleClient.OracleBFile> class, which is used to work with the Oracle <xref:System.Data.OracleClient.OracleType.BFile> data type.</span></span>  
  
 <span data-ttu-id="fa02c-104">Oracle **BFILE**データ型は、最大サイズが 4 gb のバイナリデータへの参照を含む oracle **LOB**データ型です。</span><span class="sxs-lookup"><span data-stu-id="fa02c-104">The Oracle **BFILE** data type is an Oracle **LOB** data type that contains a reference to binary data with a maximum size of 4 gigabytes.</span></span> <span data-ttu-id="fa02c-105">Oracle **BFILE**は、データがサーバー上ではなくオペレーティングシステムの物理ファイルに格納されるという点で、他の oracle **LOB**データ型とは異なります。</span><span class="sxs-lookup"><span data-stu-id="fa02c-105">An Oracle **BFILE** differs from other Oracle **LOB** data types in that its data is stored in a physical file in the operating system instead of on the server.</span></span> <span data-ttu-id="fa02c-106">**BFILE**データ型は、データへの読み取り専用アクセスを提供することに注意してください。</span><span class="sxs-lookup"><span data-stu-id="fa02c-106">Note that the **BFILE** data type provides read-only access to data.</span></span>  
  
 <span data-ttu-id="fa02c-107">**LOB**データ型と区別する、 **BFILE**データ型のその他の特性は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="fa02c-107">Other characteristics of a **BFILE** data type that distinguish it from a **LOB** data type are that it:</span></span>  
  
- <span data-ttu-id="fa02c-108">非構造化データの保持。</span><span class="sxs-lookup"><span data-stu-id="fa02c-108">Contains unstructured data.</span></span>  
  
- <span data-ttu-id="fa02c-109">サーバー側チャンキングのサポート。</span><span class="sxs-lookup"><span data-stu-id="fa02c-109">Supports server-side chunking.</span></span>  
  
- <span data-ttu-id="fa02c-110">参照コピーのセマンティクスの使用。</span><span class="sxs-lookup"><span data-stu-id="fa02c-110">Uses reference copy semantics.</span></span> <span data-ttu-id="fa02c-111">たとえば、 **bfile**に対してコピー操作を実行すると、ファイルへの参照である**bfile**ロケーターだけがコピーされます。</span><span class="sxs-lookup"><span data-stu-id="fa02c-111">For example, if you perform a copy operation on a **BFILE**, only the **BFILE** locator (which is a reference to the file) is copied.</span></span> <span data-ttu-id="fa02c-112">ファイル内のデータはコピーされません。</span><span class="sxs-lookup"><span data-stu-id="fa02c-112">The data in the file is not copied.</span></span>  
  
 <span data-ttu-id="fa02c-113">**BFILE**データ型は、サイズが大きい lob を参照するために使用する必要があります。したがって、データベースに格納するのは現実的ではありません。</span><span class="sxs-lookup"><span data-stu-id="fa02c-113">The **BFILE** data type should be used for referencing LOBs that are large in size, and therefore, not practical to store in the database.</span></span> <span data-ttu-id="fa02c-114">**LOB**データ型と比較して、 **BFILE**データ型を使用する場合は、クライアント、サーバー、および通信のオーバーヘッドが増加します。</span><span class="sxs-lookup"><span data-stu-id="fa02c-114">More client, server, and communication overhead is involved when using a **BFILE** data type compared with the **LOB** data type.</span></span> <span data-ttu-id="fa02c-115">少量のデータだけを取得する必要がある場合は、 **BFILE**にアクセスする方が効率的です。</span><span class="sxs-lookup"><span data-stu-id="fa02c-115">It is more efficient to access a **BFILE** if you only need to obtain a small amount of data.</span></span> <span data-ttu-id="fa02c-116">オブジェクト全体を取得したい場合は、データベースに常駐する LOB へのアクセスがいっそう効果的です。</span><span class="sxs-lookup"><span data-stu-id="fa02c-116">It is more efficient to access database-resident LOBs if you need to obtain the entire object.</span></span>  
  
 <span data-ttu-id="fa02c-117">NULL 以外の各**OracleBFile**オブジェクトは、基になる物理ファイルの場所を定義する2つのエンティティに関連付けられています。</span><span class="sxs-lookup"><span data-stu-id="fa02c-117">Each non-NULL **OracleBFile** object is associated with two entities that define the location of the underlying physical file:</span></span>  
  
1. <span data-ttu-id="fa02c-118">Oracle DIRECTORY オブジェクト。ファイル システムのディレクトリに対するデータベースのエイリアスです。</span><span class="sxs-lookup"><span data-stu-id="fa02c-118">An Oracle DIRECTORY object, which is a database alias for a directory in the file system, and</span></span>  
  
2. <span data-ttu-id="fa02c-119">基になる物理ファイルのファイル名。このファイルは、DIRECTORY オブジェクトに関連付けられたディレクトリに配置されています。</span><span class="sxs-lookup"><span data-stu-id="fa02c-119">The file name of the underlying physical file, which is located in the directory associated with the DIRECTORY object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fa02c-120">例</span><span class="sxs-lookup"><span data-stu-id="fa02c-120">Example</span></span>  
 <span data-ttu-id="fa02c-121">次C#の例では、Oracle テーブルで**BFILE**を作成し、 **OracleBFile**オブジェクトの形式で取得する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="fa02c-121">The following C# example demonstrates how you can create a **BFILE** in an Oracle table and then retrieve it in the form of an **OracleBFile** object.</span></span> <span data-ttu-id="fa02c-122">この例では、 <xref:System.Data.OracleClient.OracleDataReader>オブジェクトと**OracleBFile** **Seek**メソッドと**Read**メソッドを使用する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="fa02c-122">The example demonstrates using the <xref:System.Data.OracleClient.OracleDataReader> object and the **OracleBFile** **Seek** and **Read** methods.</span></span> <span data-ttu-id="fa02c-123">このサンプルを使用するには、まず、"c:\\\bfiles" という名前のディレクトリを作成し、Oracle サーバーに "myfile.txt" という名前のファイルを作成する必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="fa02c-123">Note that in order to use this sample, you must first create a directory named "c:\\\bfiles" and file named "MyFile.jpg" on the Oracle server.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="fa02c-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="fa02c-124">See also</span></span>

- [<span data-ttu-id="fa02c-125">Oracle および ADO.NET</span><span class="sxs-lookup"><span data-stu-id="fa02c-125">Oracle and ADO.NET</span></span>](oracle-and-adonet.md)
- [<span data-ttu-id="fa02c-126">ADO.NET の概要</span><span class="sxs-lookup"><span data-stu-id="fa02c-126">ADO.NET Overview</span></span>](ado-net-overview.md)
