---
title: FILESTREAM データ
ms.date: 03/30/2017
ms.assetid: bd8b845c-0f09-4295-b466-97ef106eefa8
ms.openlocfilehash: 87bed5dd345c240cc00b2c36aa976ec53fe63b93
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70794099"
---
# <a name="filestream-data"></a><span data-ttu-id="40c3f-102">FILESTREAM データ</span><span class="sxs-lookup"><span data-stu-id="40c3f-102">FILESTREAM Data</span></span>

<span data-ttu-id="40c3f-103">FILESTREAM ストレージ属性は、varbinary(max) 列に格納されるバイナリ (BLOB) データに対応しています。</span><span class="sxs-lookup"><span data-stu-id="40c3f-103">The FILESTREAM storage attribute is for binary (BLOB) data stored in a varbinary(max) column.</span></span> <span data-ttu-id="40c3f-104">FILESTREAM の導入前は、バイナリ データの格納するために特別な処理が必要でした。</span><span class="sxs-lookup"><span data-stu-id="40c3f-104">Before FILESTREAM, storing binary data required special handling.</span></span> <span data-ttu-id="40c3f-105">テキスト ドキュメント、イメージ、ビデオなどの非構造化データはデータベース外に保存されることが多く、そのために管理が困難でした。</span><span class="sxs-lookup"><span data-stu-id="40c3f-105">Unstructured data, such as text documents, images and video, is often stored outside of the database, making it difficult to manage.</span></span>

> [!NOTE]
> <span data-ttu-id="40c3f-106">SqlClient を使用して FILESTREAM データを操作するには、.NET Framework 3.5 SP1 以降をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="40c3f-106">You must install the .NET Framework 3.5 SP1 (or later) to work with FILESTREAM data using SqlClient.</span></span>

<span data-ttu-id="40c3f-107">varbinary(max) 列に FILESTREAM 属性を指定すると、SQL Server ではデータはデータベース ファイルではなくローカルの NTFS ファイル システムに保存されます。</span><span class="sxs-lookup"><span data-stu-id="40c3f-107">Specifying the FILESTREAM attribute on a varbinary(max) column causes SQL Server to store the data on the local NTFS file system instead of in the database file.</span></span> <span data-ttu-id="40c3f-108">データは個別に保存されますが、データベースに保存されている varbinary(max) データの操作をサポートする同じ Transact-SQL ステートメントを使用できます。</span><span class="sxs-lookup"><span data-stu-id="40c3f-108">Although it is stored separately, you can use the same Transact-SQL statements that are supported for working with varbinary(max) data that is stored in the database.</span></span>

## <a name="sqlclient-support-for-filestream"></a><span data-ttu-id="40c3f-109">FILESTREAM の SqlClient サポート</span><span class="sxs-lookup"><span data-stu-id="40c3f-109">SqlClient Support for FILESTREAM</span></span>

<span data-ttu-id="40c3f-110">SQL Server <xref:System.Data.SqlClient>の .NET Framework Data Provider では、は、 <xref:System.Data.SqlTypes>名前空間で定義されて<xref:System.Data.SqlTypes.SqlFileStream>いるクラスを使用した FILESTREAM データの読み取りと書き込みをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="40c3f-110">The .NET Framework Data Provider for SQL Server, <xref:System.Data.SqlClient>, supports reading and writing to FILESTREAM data using the <xref:System.Data.SqlTypes.SqlFileStream> class defined in the <xref:System.Data.SqlTypes> namespace.</span></span> <span data-ttu-id="40c3f-111">`SqlFileStream` は <xref:System.IO.Stream> クラスを継承します。このクラスは、データのストリームへの読み込みと書き込みを行うためのメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="40c3f-111">`SqlFileStream` inherits from the <xref:System.IO.Stream> class, which provides methods for reading and writing to streams of data.</span></span> <span data-ttu-id="40c3f-112">ストリームからデータを読み取ると、データはストリームからバイトの配列などのデータ構造に転送されます。</span><span class="sxs-lookup"><span data-stu-id="40c3f-112">Reading from a stream transfers data from the stream into a data structure, such as an array of bytes.</span></span> <span data-ttu-id="40c3f-113">書き込みを行うと、データはデータ構造からストリームに転送されます。</span><span class="sxs-lookup"><span data-stu-id="40c3f-113">Writing transfers the data from the data structure into a stream.</span></span>

### <a name="creating-the-sql-server-table"></a><span data-ttu-id="40c3f-114">SQL Server テーブルの作成</span><span class="sxs-lookup"><span data-stu-id="40c3f-114">Creating the SQL Server Table</span></span>

<span data-ttu-id="40c3f-115">次の Transact-SQL ステートメントによって、従業員の名前の付いたテーブルが作成され、データ行が挿入されます。</span><span class="sxs-lookup"><span data-stu-id="40c3f-115">The following Transact-SQL statements creates a table named employees and inserts a row of data.</span></span> <span data-ttu-id="40c3f-116">FILESTREAM ストレージを有効にすると、このテーブルを次のようなコード例と共に使用できます。</span><span class="sxs-lookup"><span data-stu-id="40c3f-116">Once you have enabled FILESTREAM storage, you can use this table in conjunction with the code examples that follow.</span></span> <span data-ttu-id="40c3f-117">SQL Server オンラインブックのリソースへのリンクについては、このトピックの最後に記載されています。</span><span class="sxs-lookup"><span data-stu-id="40c3f-117">The links to resources in SQL Server Books Online are located at the end of this topic.</span></span>

```sql
CREATE TABLE employees
(
  EmployeeId INT  NOT NULL  PRIMARY KEY,
  Photo VARBINARY(MAX) FILESTREAM  NULL,
  RowGuid UNIQUEIDENTIFIER  NOT NULL  ROWGUIDCOL
  UNIQUE DEFAULT NEWID()
)
GO
Insert into employees
Values(1, 0x00, default)
GO
```

### <a name="example-reading-overwriting-and-inserting-filestream-data"></a><span data-ttu-id="40c3f-118">例:FILESTREAM データの読み取り、上書き、および挿入</span><span class="sxs-lookup"><span data-stu-id="40c3f-118">Example: Reading, Overwriting, and Inserting FILESTREAM Data</span></span>

<span data-ttu-id="40c3f-119">次のサンプルでは、FILESTREAM からデータを読み取る方法を示します。</span><span class="sxs-lookup"><span data-stu-id="40c3f-119">The following sample demonstrates how to read data from a FILESTREAM.</span></span> <span data-ttu-id="40c3f-120">コードはファイルへの論理パスを取得し、`FileAccess` を `Read` に、`FileOptions` を `SequentialScan` に設定します。</span><span class="sxs-lookup"><span data-stu-id="40c3f-120">The code gets the logical path to the file, setting the `FileAccess` to `Read` and the `FileOptions` to `SequentialScan`.</span></span> <span data-ttu-id="40c3f-121">次に、コードは SqlFileStream からバイトをバッファーに読み取ります。</span><span class="sxs-lookup"><span data-stu-id="40c3f-121">The code then reads the bytes from the SqlFileStream into the buffer.</span></span> <span data-ttu-id="40c3f-122">バイトはコンソール ウィンドウに書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="40c3f-122">The bytes are then written to the console window.</span></span>

<span data-ttu-id="40c3f-123">また、このサンプルでは、すべての既存のデータを上書きする FILESTREAM にデータを書き込む方法も示します。</span><span class="sxs-lookup"><span data-stu-id="40c3f-123">The sample also demonstrates how to write data to a FILESTREAM in which all existing data is overwritten.</span></span> <span data-ttu-id="40c3f-124">コードはファイルへの論理パスを取得し、`SqlFileStream` を作成し、`FileAccess` を `Write` に、`FileOptions` を `SequentialScan` に設定します。</span><span class="sxs-lookup"><span data-stu-id="40c3f-124">The code gets the logical path to the file and creates the `SqlFileStream`, setting the `FileAccess` to `Write` and the `FileOptions` to `SequentialScan`.</span></span> <span data-ttu-id="40c3f-125">1 バイトが `SqlFileStream` に書き込まれ、ファイルのデータは置換されます。</span><span class="sxs-lookup"><span data-stu-id="40c3f-125">A single byte is written to the `SqlFileStream`, replacing any data in the file.</span></span>

<span data-ttu-id="40c3f-126">このサンプルでは、Seek メソッドを使用してファイルの末尾にデータを追加することによって、データを FILESTREAM に書き込む方法も示します。</span><span class="sxs-lookup"><span data-stu-id="40c3f-126">The sample also demonstrates how to write data to a FILESTREAM by using the Seek method to append data to the end of the file.</span></span> <span data-ttu-id="40c3f-127">コードはファイルへの論理パスを取得し、`SqlFileStream` を作成し、`FileAccess` を `ReadWrite` に、`FileOptions` を `SequentialScan` に設定します。</span><span class="sxs-lookup"><span data-stu-id="40c3f-127">The code gets the logical path to the file and creates the `SqlFileStream`, setting the `FileAccess` to `ReadWrite` and the `FileOptions` to `SequentialScan`.</span></span> <span data-ttu-id="40c3f-128">コードは Seek メソッドを使用してファイルの末尾をシークし、1 バイトを既存のファイルに追加します。</span><span class="sxs-lookup"><span data-stu-id="40c3f-128">The code uses the Seek method to seek to the end of the file, appending a single byte to the existing file.</span></span>

```csharp
using System;
using System.Data.SqlClient;
using System.Data.SqlTypes;
using System.Data;
using System.IO;

namespace FileStreamTest
{
    class Program
    {
        static void Main(string[] args)
        {
            SqlConnectionStringBuilder builder = new SqlConnectionStringBuilder("server=(local);integrated security=true;database=myDB");
            ReadFileStream(builder);
            OverwriteFileStream(builder);
            InsertFileStream(builder);

            Console.WriteLine("Done");
        }

        private static void ReadFileStream(SqlConnectionStringBuilder connStringBuilder)
        {
            using (SqlConnection connection = new SqlConnection(connStringBuilder.ToString()))
            {
                connection.Open();
                SqlCommand command = new SqlCommand("SELECT TOP(1) Photo.PathName(), GET_FILESTREAM_TRANSACTION_CONTEXT() FROM employees", connection);

                SqlTransaction tran = connection.BeginTransaction(IsolationLevel.ReadCommitted);
                command.Transaction = tran;

                using (SqlDataReader reader = command.ExecuteReader())
                {
                    while (reader.Read())
                    {
                        // Get the pointer for the file
                        string path = reader.GetString(0);
                        byte[] transactionContext = reader.GetSqlBytes(1).Buffer;

                        // Create the SqlFileStream
                        using (Stream fileStream = new SqlFileStream(path, transactionContext, FileAccess.Read, FileOptions.SequentialScan, allocationSize: 0))
                        {
                            // Read the contents as bytes and write them to the console
                            for (long index = 0; index < fileStream.Length; index++)
                            {
                                Console.WriteLine(fileStream.ReadByte());
                            }
                        }
                    }
                }
                tran.Commit();
            }
        }

        private static void OverwriteFileStream(SqlConnectionStringBuilder connStringBuilder)
        {
            using (SqlConnection connection = new SqlConnection(connStringBuilder.ToString()))
            {
                connection.Open();

                SqlCommand command = new SqlCommand("SELECT TOP(1) Photo.PathName(), GET_FILESTREAM_TRANSACTION_CONTEXT() FROM employees", connection);

                SqlTransaction tran = connection.BeginTransaction(IsolationLevel.ReadCommitted);
                command.Transaction = tran;

                using (SqlDataReader reader = command.ExecuteReader())
                {
                    while (reader.Read())
                    {
                        // Get the pointer for file
                        string path = reader.GetString(0);
                        byte[] transactionContext = reader.GetSqlBytes(1).Buffer;

                        // Create the SqlFileStream
                        using (Stream fileStream = new SqlFileStream(path, transactionContext, FileAccess.Write, FileOptions.SequentialScan, allocationSize: 0))
                        {
                            // Write a single byte to the file. This will
                            // replace any data in the file.
                            fileStream.WriteByte(0x01);
                        }
                    }
                }
                tran.Commit();
            }
        }

        private static void InsertFileStream(SqlConnectionStringBuilder connStringBuilder)
        {
            using (SqlConnection connection = new SqlConnection(connStringBuilder.ToString()))
            {
                connection.Open();

                SqlCommand command = new SqlCommand("SELECT TOP(1) Photo.PathName(), GET_FILESTREAM_TRANSACTION_CONTEXT() FROM employees", connection);

                SqlTransaction tran = connection.BeginTransaction(IsolationLevel.ReadCommitted);
                command.Transaction = tran;

                using (SqlDataReader reader = command.ExecuteReader())
                {
                    while (reader.Read())
                    {
                        // Get the pointer for file
                        string path = reader.GetString(0);
                        byte[] transactionContext = reader.GetSqlBytes(1).Buffer;

                        using (Stream fileStream = new SqlFileStream(path, transactionContext, FileAccess.ReadWrite, FileOptions.SequentialScan, allocationSize: 0))
                        {
                            // Seek to the end of the file
                            fileStream.Seek(0, SeekOrigin.End);

                            // Append a single byte
                            fileStream.WriteByte(0x01);
                        }
                    }
                }
                tran.Commit();
            }

        }
    }
}
```

<span data-ttu-id="40c3f-129">別のサンプルについては、「[ファイルストリーム列にバイナリデータを格納およびフェッチする方法](https://www.codeproject.com/Articles/32216/How-to-store-and-fetch-binary-data-into-a-file-str)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="40c3f-129">For another sample, see [How to store and fetch binary data into a file stream column](https://www.codeproject.com/Articles/32216/How-to-store-and-fetch-binary-data-into-a-file-str).</span></span>

## <a name="resources-in-sql-server-books-online"></a><span data-ttu-id="40c3f-130">SQL Server オンライン ブックの関連トピック</span><span class="sxs-lookup"><span data-stu-id="40c3f-130">Resources in SQL Server Books Online</span></span>

<span data-ttu-id="40c3f-131">FILESTREAM の完全なドキュメントは、SQL Server オンラインブックの次のセクションにあります。</span><span class="sxs-lookup"><span data-stu-id="40c3f-131">The complete documentation for FILESTREAM is located in the following sections in SQL Server Books Online.</span></span>

|<span data-ttu-id="40c3f-132">トピック</span><span class="sxs-lookup"><span data-stu-id="40c3f-132">Topic</span></span>|<span data-ttu-id="40c3f-133">説明</span><span class="sxs-lookup"><span data-stu-id="40c3f-133">Description</span></span>|
|-----------|-----------------|
|[<span data-ttu-id="40c3f-134">FILESTREAM (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="40c3f-134">FILESTREAM (SQL Server)</span></span>](/sql/relational-databases/blob/filestream-sql-server)|<span data-ttu-id="40c3f-135">FILESTREAM ストレージを使用するタイミング、および SQL Server データベース エンジンと NTFS ファイル システムを統合する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="40c3f-135">Describes when to use FILESTREAM storage and how it integrates the SQL Server Database Engine with an NTFS file system.</span></span>|
|[<span data-ttu-id="40c3f-136">FILESTREAM データ用のクライアントアプリケーションの作成</span><span class="sxs-lookup"><span data-stu-id="40c3f-136">Create Client Applications for FILESTREAM Data</span></span>](/sql/relational-databases/blob/create-client-applications-for-filestream-data)|<span data-ttu-id="40c3f-137">FILESTREAM データを操作するための Windows API 関数について説明します。</span><span class="sxs-lookup"><span data-stu-id="40c3f-137">Describes the Windows API functions for working with FILESTREAM data.</span></span>|
|[<span data-ttu-id="40c3f-138">FILESTREAM とその他の SQL Server 機能</span><span class="sxs-lookup"><span data-stu-id="40c3f-138">FILESTREAM and Other SQL Server Features</span></span>](/sql/relational-databases/blob/filestream-compatibility-with-other-sql-server-features)|<span data-ttu-id="40c3f-139">FILESTREAM データを SQL Server の他の機能と共に使用する際の注意事項、ガイドライン、および制限事項について説明します。</span><span class="sxs-lookup"><span data-stu-id="40c3f-139">Provides considerations, guidelines and limitations for using FILESTREAM data with other features of SQL Server.</span></span>|

## <a name="see-also"></a><span data-ttu-id="40c3f-140">関連項目</span><span class="sxs-lookup"><span data-stu-id="40c3f-140">See also</span></span>

- [<span data-ttu-id="40c3f-141">SQL Server データ型と ADO.NET</span><span class="sxs-lookup"><span data-stu-id="40c3f-141">SQL Server Data Types and ADO.NET</span></span>](sql-server-data-types.md)
- [<span data-ttu-id="40c3f-142">ADO.NET でのデータの取得および変更</span><span class="sxs-lookup"><span data-stu-id="40c3f-142">Retrieving and Modifying Data in ADO.NET</span></span>](../retrieving-and-modifying-data.md)
- [<span data-ttu-id="40c3f-143">コード アクセス セキュリティと ADO.NET</span><span class="sxs-lookup"><span data-stu-id="40c3f-143">Code Access Security and ADO.NET</span></span>](../code-access-security.md)
- [<span data-ttu-id="40c3f-144">SQL Server のバイナリ データと大きな値のデータ</span><span class="sxs-lookup"><span data-stu-id="40c3f-144">SQL Server Binary and Large-Value Data</span></span>](sql-server-binary-and-large-value-data.md)
- [<span data-ttu-id="40c3f-145">ADO.NET の概要</span><span class="sxs-lookup"><span data-stu-id="40c3f-145">ADO.NET Overview</span></span>](../ado-net-overview.md)
