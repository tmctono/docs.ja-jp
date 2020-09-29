---
title: バイナリ データの取得
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 56c5a9e3-31f1-482f-bce0-ff1c41a658d0
ms.openlocfilehash: 11f7a81bc0d4b0e2a8d66387410d9a24503c7519
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91150662"
---
# <a name="retrieving-binary-data"></a><span data-ttu-id="c731d-102">バイナリ データの取得</span><span class="sxs-lookup"><span data-stu-id="c731d-102">Retrieving Binary Data</span></span>

<span data-ttu-id="c731d-103">既定では、データの行全体が使用可能になるとすぐに、**DataReader** によって受信データが行として読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="c731d-103">By default, the **DataReader** loads incoming data as a row as soon as an entire row of data is available.</span></span> <span data-ttu-id="c731d-104">バイナリ ラージ オブジェクト (BLOB) には、1 行に収まらない数ギガバイトのデータが含まれる場合があるため、別の処理が必要です。</span><span class="sxs-lookup"><span data-stu-id="c731d-104">Binary large objects (BLOBs) need different treatment, however, because they can contain gigabytes of data that cannot be contained in a single row.</span></span> <span data-ttu-id="c731d-105">**Command.ExecuteReader** メソッドには、<xref:System.Data.CommandBehavior> 引数を受け取って **DataReader** の既定の動作を変更するオーバーロードがあります。</span><span class="sxs-lookup"><span data-stu-id="c731d-105">The **Command.ExecuteReader** method has an overload that will take a <xref:System.Data.CommandBehavior> argument to modify the default behavior of the **DataReader**.</span></span> <span data-ttu-id="c731d-106">**ExecuteReader** メソッドに <xref:System.Data.CommandBehavior.SequentialAccess> を渡すと、データの行を読み込む代わりに、データを受け取った時点で順次読み込むように、**DataReader** の既定の動作を変更できます。</span><span class="sxs-lookup"><span data-stu-id="c731d-106">You can pass <xref:System.Data.CommandBehavior.SequentialAccess> to the **ExecuteReader** method to modify the default behavior of the **DataReader** so that instead of loading rows of data, it will load data sequentially as it is received.</span></span> <span data-ttu-id="c731d-107">これは BLOB やその他の大きなデータ構造を読み込む場合に理想的な処理です。</span><span class="sxs-lookup"><span data-stu-id="c731d-107">This is ideal for loading BLOBs or other large data structures.</span></span> <span data-ttu-id="c731d-108">この動作は、データ ソースによって異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="c731d-108">Note that this behavior may depend on your data source.</span></span> <span data-ttu-id="c731d-109">たとえば、Microsoft Access から BLOB を返すと、受け取ったデータから順に読み込むのではなく、BLOB 全体をメモリに読み込みます。</span><span class="sxs-lookup"><span data-stu-id="c731d-109">For example, returning a BLOB from Microsoft Access will load the entire BLOB being loaded into memory, rather than sequentially as it is received.</span></span>  
  
 <span data-ttu-id="c731d-110">**SequentialAccess** を使用するように **DataReader** を設定するときは、返されたフィールドにアクセスする順序に注意してください。</span><span class="sxs-lookup"><span data-stu-id="c731d-110">When setting the **DataReader** to use **SequentialAccess**, it is important to note the sequence in which you access the fields returned.</span></span> <span data-ttu-id="c731d-111">使用可能になるとすぐに行全体を読み込む **DataReader** の既定の動作では、次の行が読み取られるまでは、返されたフィールドに任意の順序でアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="c731d-111">The default behavior of the **DataReader**, which loads an entire row as soon as it is available, allows you to access the fields returned in any order until the next row is read.</span></span> <span data-ttu-id="c731d-112">しかし、**SequentialAccess** を使用しているときは、**DataReader** によって返された各フィールドに順番にアクセスする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c731d-112">When using **SequentialAccess** however, you must access the fields returned by the **DataReader** in order.</span></span> <span data-ttu-id="c731d-113">たとえば、クエリが 3 つの列 (3 番目の列は BLOB) を返す場合、最初のフィールドおよび 2 番目のフィールドの値は、3 番目のフィールドの BLOB データにアクセスする前に返す必要があります。</span><span class="sxs-lookup"><span data-stu-id="c731d-113">For example, if your query returns three columns, the third of which is a BLOB, you must return the values of the first and second fields before accessing the BLOB data in the third field.</span></span> <span data-ttu-id="c731d-114">最初のフィールドまたは 2 番目のフィールドの前に 3 番目のフィールドにアクセスした場合は、最初のフィールドと 2 番目のフィールドの値は使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="c731d-114">If you access the third field before the first or second fields, the first and second field values are no longer available.</span></span> <span data-ttu-id="c731d-115">これは、**SequentialAccess** によって、**DataReader** はデータを順番に返すように変更されており、**DataReader** による読み取りが通過した後のデータは使用できなくなるためです。</span><span class="sxs-lookup"><span data-stu-id="c731d-115">This is because **SequentialAccess** has modified the **DataReader** to return data in sequence and the data is not available after the **DataReader** has read past it.</span></span>  
  
 <span data-ttu-id="c731d-116">BLOB フィールドのデータにアクセスするときは、**DataReader** の **GetBytes** 型または **GetChars** 型のアクセサーを使用します。これらのアクセサーでは、データは配列に設定されます。</span><span class="sxs-lookup"><span data-stu-id="c731d-116">When accessing the data in the BLOB field, use the **GetBytes** or **GetChars** typed accessors of the **DataReader**, which fill an array with data.</span></span> <span data-ttu-id="c731d-117">文字データには **GetString** を使用することもできます。ただし、</span><span class="sxs-lookup"><span data-stu-id="c731d-117">You can also use **GetString** for character data; however.</span></span> <span data-ttu-id="c731d-118">システム リソースを節約するためには、BLOB 値全体を 1 つの文字列変数に読み込むことは望ましくありません。</span><span class="sxs-lookup"><span data-stu-id="c731d-118">to conserve system resources you might not want to load an entire BLOB value into a single string variable.</span></span> <span data-ttu-id="c731d-119">特定のバッファー サイズのデータを返すように指定する代わりに、返されたデータから読み込む先頭バイトまたは先頭文字の開始位置を指定できます。</span><span class="sxs-lookup"><span data-stu-id="c731d-119">You can instead specify a specific buffer size of data to be returned, and a starting location for the first byte or character to be read from the returned data.</span></span> <span data-ttu-id="c731d-120">**GetBytes** と **GetChars** では、返されたバイト数または文字数を表す `long` 値が返されます。</span><span class="sxs-lookup"><span data-stu-id="c731d-120">**GetBytes** and **GetChars** will return a `long` value, which represents the number of bytes or characters returned.</span></span> <span data-ttu-id="c731d-121">**GetBytes** または **GetChars** に null 配列を渡した場合、返される long 値は BLOB の総バイト数または総文字数になります。</span><span class="sxs-lookup"><span data-stu-id="c731d-121">If you pass a null array to **GetBytes** or **GetChars**, the long value returned will be the total number of bytes or characters in the BLOB.</span></span> <span data-ttu-id="c731d-122">オプションで、データ読み込みの開始位置を示す、配列内のインデックスを指定できます。</span><span class="sxs-lookup"><span data-stu-id="c731d-122">You can optionally specify an index in the array as a starting position for the data being read.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c731d-123">例</span><span class="sxs-lookup"><span data-stu-id="c731d-123">Example</span></span>  

 <span data-ttu-id="c731d-124">次の例では、Microsoft SQL Server の **pubs** サンプル データベースから、発行者 ID とロゴを取得します。</span><span class="sxs-lookup"><span data-stu-id="c731d-124">The following example returns the publisher ID and logo from the **pubs** sample database in Microsoft SQL Server.</span></span> <span data-ttu-id="c731d-125">発行者 ID (`pub_id`) は文字フィールドであり、ロゴはイメージ、つまり、BLOB です。</span><span class="sxs-lookup"><span data-stu-id="c731d-125">The publisher ID (`pub_id`) is a character field, and the logo is an image, which is a BLOB.</span></span> <span data-ttu-id="c731d-126">**logo** フィールドはビットマップなので、この例では、**GetBytes** を使用してバイナリ データを返します。</span><span class="sxs-lookup"><span data-stu-id="c731d-126">Because the **logo** field is a bitmap, the example returns binary data using **GetBytes**.</span></span> <span data-ttu-id="c731d-127">フィールドには順番にアクセスする必要があるため、現在の行のデータに対して発行者 ID はロゴの前にアクセスされることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="c731d-127">Notice that the publisher ID is accessed for the current row of data before the logo, because the fields must be accessed sequentially.</span></span>  
  
```vb  
' Assumes that connection is a valid SqlConnection object.  
Dim command As SqlCommand = New SqlCommand( _  
  "SELECT pub_id, logo FROM pub_info", connection)  
  
' Writes the BLOB to a file (*.bmp).  
Dim stream As FileStream
' Streams the binary data to the FileStream object.  
Dim writer As BinaryWriter
' The size of the BLOB buffer.  
Dim bufferSize As Integer = 100
' The BLOB byte() buffer to be filled by GetBytes.  
Dim outByte(bufferSize - 1) As Byte
' The bytes returned from GetBytes.  
Dim retval As Long
' The starting position in the BLOB output.  
Dim startIndex As Long = 0
  
' The publisher id to use in the file name.  
Dim pubID As String = ""
  
' Open the connection and read data into the DataReader.  
connection.Open()  
Dim reader As SqlDataReader = command.ExecuteReader(CommandBehavior.SequentialAccess)  
  
Do While reader.Read()  
  ' Get the publisher id, which must occur before getting the logo.  
  pubID = reader.GetString(0)  
  
  ' Create a file to hold the output.  
  stream = New FileStream( _  
    "logo" & pubID & ".bmp", FileMode.OpenOrCreate, FileAccess.Write)  
  writer = New BinaryWriter(stream)  
  
  ' Reset the starting byte for a new BLOB.  
  startIndex = 0  
  
  ' Read bytes into outByte() and retain the number of bytes returned.  
  retval = reader.GetBytes(1, startIndex, outByte, 0, bufferSize)  
  
  ' Continue while there are bytes beyond the size of the buffer.  
  Do While retval = bufferSize  
    writer.Write(outByte)  
    writer.Flush()  
  
    ' Reposition start index to end of the last buffer and fill buffer.  
    startIndex += bufferSize  
    retval = reader.GetBytes(1, startIndex, outByte, 0, bufferSize)  
  Loop  
  
  ' Write the remaining buffer.  
  writer.Write(outByte, 0 , retval - 1)  
  writer.Flush()  
  
  ' Close the output file.  
  writer.Close()  
  stream.Close()  
Loop  
  
' Close the reader and the connection.  
reader.Close()  
connection.Close()  
```  
  
```csharp  
// Assumes that connection is a valid SqlConnection object.  
SqlCommand command = new SqlCommand(  
  "SELECT pub_id, logo FROM pub_info", connection);  
  
// Writes the BLOB to a file (*.bmp).  
FileStream stream;
// Streams the BLOB to the FileStream object.  
BinaryWriter writer;
  
// Size of the BLOB buffer.  
int bufferSize = 100;
// The BLOB byte[] buffer to be filled by GetBytes.  
byte[] outByte = new byte[bufferSize];
// The bytes returned from GetBytes.  
long retval;
// The starting position in the BLOB output.  
long startIndex = 0;
  
// The publisher id to use in the file name.  
string pubID = "";
  
// Open the connection and read data into the DataReader.  
connection.Open();  
SqlDataReader reader = command.ExecuteReader(CommandBehavior.SequentialAccess);  
  
while (reader.Read())  
{  
  // Get the publisher id, which must occur before getting the logo.  
  pubID = reader.GetString(0);
  
  // Create a file to hold the output.  
  stream = new FileStream(  
    "logo" + pubID + ".bmp", FileMode.OpenOrCreate, FileAccess.Write);  
  writer = new BinaryWriter(stream);  
  
  // Reset the starting byte for the new BLOB.  
  startIndex = 0;  
  
  // Read bytes into outByte[] and retain the number of bytes returned.  
  retval = reader.GetBytes(1, startIndex, outByte, 0, bufferSize);  
  
  // Continue while there are bytes beyond the size of the buffer.  
  while (retval == bufferSize)  
  {  
    writer.Write(outByte);  
    writer.Flush();  
  
    // Reposition start index to end of last buffer and fill buffer.  
    startIndex += bufferSize;  
    retval = reader.GetBytes(1, startIndex, outByte, 0, bufferSize);  
  }  
  
  // Write the remaining buffer.  
  writer.Write(outByte, 0, (int)retval);  
  writer.Flush();  
  
  // Close the output file.  
  writer.Close();  
  stream.Close();  
}  
  
// Close the reader and the connection.  
reader.Close();  
connection.Close();  
```  
  
## <a name="see-also"></a><span data-ttu-id="c731d-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="c731d-128">See also</span></span>

- [<span data-ttu-id="c731d-129">SQL Server のバイナリ データと大きな値のデータ</span><span class="sxs-lookup"><span data-stu-id="c731d-129">SQL Server Binary and Large-Value Data</span></span>](./sql/sql-server-binary-and-large-value-data.md)
- [<span data-ttu-id="c731d-130">ADO.NET の概要</span><span class="sxs-lookup"><span data-stu-id="c731d-130">ADO.NET Overview</span></span>](ado-net-overview.md)
