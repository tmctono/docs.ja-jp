---
title: Oracle BFILE
ms.date: 03/30/2017
ms.assetid: 341bbf84-4734-4d44-8723-ccedee954e21
ms.openlocfilehash: d43dfccd9735ce1ab822d7b14de2abaa0940c77b
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91166600"
---
# <a name="oracle-bfiles"></a><span data-ttu-id="3c7fc-102">Oracle BFILE</span><span class="sxs-lookup"><span data-stu-id="3c7fc-102">Oracle BFILEs</span></span>

<span data-ttu-id="3c7fc-103">.NET Framework Data Provider for Oracle には、<xref:System.Data.OracleClient.OracleBFile> クラスが含まれています。このクラスは、Oracle <xref:System.Data.OracleClient.OracleType.BFile> データ型で使用されます。</span><span class="sxs-lookup"><span data-stu-id="3c7fc-103">The .NET Framework Data Provider for Oracle includes the <xref:System.Data.OracleClient.OracleBFile> class, which is used to work with the Oracle <xref:System.Data.OracleClient.OracleType.BFile> data type.</span></span>  
  
 <span data-ttu-id="3c7fc-104">Oracle の **BFILE** データ型は、最大 4 GB までのバイナリ データへの参照を含む Oracle の **LOB** データ型です。</span><span class="sxs-lookup"><span data-stu-id="3c7fc-104">The Oracle **BFILE** data type is an Oracle **LOB** data type that contains a reference to binary data with a maximum size of 4 gigabytes.</span></span> <span data-ttu-id="3c7fc-105">Oracle の **BFILE** は、データがサーバー上にではなくオペレーティング システムの物理ファイルに保存されるという点で、他の Oracle の **LOB** データ型と異なります。</span><span class="sxs-lookup"><span data-stu-id="3c7fc-105">An Oracle **BFILE** differs from other Oracle **LOB** data types in that its data is stored in a physical file in the operating system instead of on the server.</span></span> <span data-ttu-id="3c7fc-106">**BFILE** データ型のデータ アクセスは読み取り専用であることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="3c7fc-106">Note that the **BFILE** data type provides read-only access to data.</span></span>  
  
 <span data-ttu-id="3c7fc-107">**LOB** データ型と異なる **BFILE** データ型のその他の特徴としては、次のものがあります。</span><span class="sxs-lookup"><span data-stu-id="3c7fc-107">Other characteristics of a **BFILE** data type that distinguish it from a **LOB** data type are that it:</span></span>  
  
- <span data-ttu-id="3c7fc-108">非構造化データの保持。</span><span class="sxs-lookup"><span data-stu-id="3c7fc-108">Contains unstructured data.</span></span>  
  
- <span data-ttu-id="3c7fc-109">サーバー側チャンキングのサポート。</span><span class="sxs-lookup"><span data-stu-id="3c7fc-109">Supports server-side chunking.</span></span>  
  
- <span data-ttu-id="3c7fc-110">参照コピーのセマンティクスの使用。</span><span class="sxs-lookup"><span data-stu-id="3c7fc-110">Uses reference copy semantics.</span></span> <span data-ttu-id="3c7fc-111">たとえば、**BFILE** 上でコピー操作を行う場合、ファイルへの参照である **BFILE** ロケーターだけがコピーされます。</span><span class="sxs-lookup"><span data-stu-id="3c7fc-111">For example, if you perform a copy operation on a **BFILE**, only the **BFILE** locator (which is a reference to the file) is copied.</span></span> <span data-ttu-id="3c7fc-112">ファイル内のデータはコピーされません。</span><span class="sxs-lookup"><span data-stu-id="3c7fc-112">The data in the file is not copied.</span></span>  
  
 <span data-ttu-id="3c7fc-113">**BFILE** データ型は、大きいサイズの LOB の参照用として使用してください。データベースへの保存には適しません。</span><span class="sxs-lookup"><span data-stu-id="3c7fc-113">The **BFILE** data type should be used for referencing LOBs that are large in size, and therefore, not practical to store in the database.</span></span> <span data-ttu-id="3c7fc-114">**BFILE** データ型を使用すると、クライアント、サーバー、および通信において、**LOB** データ型よりも、いっそう多くのオーバーヘッドを必要とします。</span><span class="sxs-lookup"><span data-stu-id="3c7fc-114">More client, server, and communication overhead is involved when using a **BFILE** data type compared with the **LOB** data type.</span></span> <span data-ttu-id="3c7fc-115">少量のデータを取得するだけの場合は、**BFILE** へのアクセスがいっそう効果的です。</span><span class="sxs-lookup"><span data-stu-id="3c7fc-115">It is more efficient to access a **BFILE** if you only need to obtain a small amount of data.</span></span> <span data-ttu-id="3c7fc-116">オブジェクト全体を取得したい場合は、データベースに常駐する LOB へのアクセスがいっそう効果的です。</span><span class="sxs-lookup"><span data-stu-id="3c7fc-116">It is more efficient to access database-resident LOBs if you need to obtain the entire object.</span></span>  
  
 <span data-ttu-id="3c7fc-117">NULL 以外の **OracleBFile** オブジェクトは、基になる物理ファイルの場所を定義する次の 2 つのエンティティに関連付けられます。</span><span class="sxs-lookup"><span data-stu-id="3c7fc-117">Each non-NULL **OracleBFile** object is associated with two entities that define the location of the underlying physical file:</span></span>  
  
1. <span data-ttu-id="3c7fc-118">Oracle DIRECTORY オブジェクト。ファイル システムのディレクトリに対するデータベースのエイリアスです。</span><span class="sxs-lookup"><span data-stu-id="3c7fc-118">An Oracle DIRECTORY object, which is a database alias for a directory in the file system, and</span></span>  
  
2. <span data-ttu-id="3c7fc-119">基になる物理ファイルのファイル名。このファイルは、DIRECTORY オブジェクトに関連付けられたディレクトリに配置されています。</span><span class="sxs-lookup"><span data-stu-id="3c7fc-119">The file name of the underlying physical file, which is located in the directory associated with the DIRECTORY object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3c7fc-120">例</span><span class="sxs-lookup"><span data-stu-id="3c7fc-120">Example</span></span>  

 <span data-ttu-id="3c7fc-121">次の C# の例では、Oracle テーブルに **BFILE** を作成し、**OracleBFile** オブジェクトの形式で取得する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="3c7fc-121">The following C# example demonstrates how you can create a **BFILE** in an Oracle table and then retrieve it in the form of an **OracleBFile** object.</span></span> <span data-ttu-id="3c7fc-122">この例では、<xref:System.Data.OracleClient.OracleDataReader> オブジェクトと **OracleBFile** の **Seek** および **Read** メソッドを使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="3c7fc-122">The example demonstrates using the <xref:System.Data.OracleClient.OracleDataReader> object and the **OracleBFile** **Seek** and **Read** methods.</span></span> <span data-ttu-id="3c7fc-123">このサンプルを使用するには、はじめに "c:\\\bfiles" というディレクトリと "MyFile.jpg" というファイルを Oracle サーバーに作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3c7fc-123">Note that in order to use this sample, you must first create a directory named "c:\\\bfiles" and file named "MyFile.jpg" on the Oracle server.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="3c7fc-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="3c7fc-124">See also</span></span>

- [<span data-ttu-id="3c7fc-125">Oracle および ADO.NET</span><span class="sxs-lookup"><span data-stu-id="3c7fc-125">Oracle and ADO.NET</span></span>](oracle-and-adonet.md)
- [<span data-ttu-id="3c7fc-126">ADO.NET の概要</span><span class="sxs-lookup"><span data-stu-id="3c7fc-126">ADO.NET Overview</span></span>](ado-net-overview.md)
