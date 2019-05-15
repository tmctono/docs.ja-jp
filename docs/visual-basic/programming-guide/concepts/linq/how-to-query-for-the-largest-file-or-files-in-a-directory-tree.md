---
title: '方法: 最大ファイルまたはディレクトリ ツリー (LINQ) (Visual Basic) 内のファイルのクエリ'
ms.date: 07/20/2015
ms.assetid: 8c1c9f0c-95dd-4222-9be2-9ec026a13e81
ms.openlocfilehash: 91cfba02bade5811dbc5f45a5106731ff637efcf
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2019
ms.locfileid: "65593286"
---
# <a name="how-to-query-for-the-largest-file-or-files-in-a-directory-tree-linq-visual-basic"></a><span data-ttu-id="ec5b9-102">方法: 最大ファイルまたはディレクトリ ツリー (LINQ) (Visual Basic) 内のファイルのクエリ</span><span class="sxs-lookup"><span data-stu-id="ec5b9-102">How to: Query for the Largest File or Files in a Directory Tree (LINQ) (Visual Basic)</span></span>
<span data-ttu-id="ec5b9-103">この例では、ファイル サイズ (バイト単位) に関連した 5 つのクエリを紹介しています。</span><span class="sxs-lookup"><span data-stu-id="ec5b9-103">This example shows five queries related to file size in bytes:</span></span>  
  
- <span data-ttu-id="ec5b9-104">最もサイズ (バイト単位) の大きいファイルを取得する方法。</span><span class="sxs-lookup"><span data-stu-id="ec5b9-104">How to retrieve the size in bytes of the largest file.</span></span>  
  
- <span data-ttu-id="ec5b9-105">最もサイズ (バイト単位) の小さいファイルを取得する方法。</span><span class="sxs-lookup"><span data-stu-id="ec5b9-105">How to retrieve the size in bytes of the smallest file.</span></span>  
  
- <span data-ttu-id="ec5b9-106">指定したルート フォルダー配下のフォルダーから <xref:System.IO.FileInfo> オブジェクトの最大ファイルまたは最小ファイルを取得する方法。</span><span class="sxs-lookup"><span data-stu-id="ec5b9-106">How to retrieve the <xref:System.IO.FileInfo> object largest or smallest file from one or more folders under a specified root folder.</span></span>  
  
- <span data-ttu-id="ec5b9-107">サイズが上位 10 番目までのファイルなど、一定の条件に該当するファイルを取得する方法。</span><span class="sxs-lookup"><span data-stu-id="ec5b9-107">How to retrieve a sequence such as the 10 largest files.</span></span>  
  
- <span data-ttu-id="ec5b9-108">指定サイズ未満のファイルを無視しながらバイト単位のサイズに基づいてファイルをグループ化する方法。</span><span class="sxs-lookup"><span data-stu-id="ec5b9-108">How to order files into groups based on their file size in bytes, ignoring files that are less than a specified size.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ec5b9-109">例</span><span class="sxs-lookup"><span data-stu-id="ec5b9-109">Example</span></span>  
 <span data-ttu-id="ec5b9-110">以下のコードでは 5 つのクエリを使用して、バイト単位のサイズに基づいてファイルを照会し、グループ化しています。</span><span class="sxs-lookup"><span data-stu-id="ec5b9-110">The following example contains five separate queries that show how to query and group files, depending on their file size in bytes.</span></span> <span data-ttu-id="ec5b9-111">サンプル コードを参考にして、<xref:System.IO.FileInfo> オブジェクトが備えている他のさまざまなプロパティを簡単に照会することができます。</span><span class="sxs-lookup"><span data-stu-id="ec5b9-111">You can easily modify these examples to base the query on some other property of the <xref:System.IO.FileInfo> object.</span></span>  
  
```vb  
Module QueryBySize  
    Sub Main()  
  
        ' Change the drive\path if necessary  
        Dim root As String = "C:\Program Files\Microsoft Visual Studio 9.0"  
  
        'Take a snapshot of the folder contents  
        Dim dir As New System.IO.DirectoryInfo(root)  
        Dim fileList = dir.GetFiles("*.*", System.IO.SearchOption.AllDirectories)  
  
        ' Return the size of the largest file  
        Dim maxSize = Aggregate aFile In fileList Into Max(GetFileLength(aFile))  
  
        'Dim maxSize = fileLengths.Max  
        Console.WriteLine("The length of the largest file under {0} is {1}", _  
                          root, maxSize)  
  
        ' Return the FileInfo object of the largest file  
        ' by sorting and selecting from the beginning of the list  
        Dim filesByLengDesc = From file In fileList _  
                              Let filelength = GetFileLength(file) _  
                              Where filelength > 0 _  
                              Order By filelength Descending _  
                              Select file  
  
        Dim longestFile = filesByLengDesc.First  
  
        Console.WriteLine("The largest file under {0} is {1} with a length of {2} bytes", _  
                          root, longestFile.FullName, longestFile.Length)  
  
        Dim smallestFile = filesByLengDesc.Last  
  
        Console.WriteLine("The smallest file under {0} is {1} with a length of {2} bytes", _  
                                root, smallestFile.FullName, smallestFile.Length)  
  
        ' Return the FileInfos for the 10 largest files  
        ' Based on a previous query, but nothing is executed  
        ' until the For Each statement below.  
        Dim tenLargest = From file In filesByLengDesc Take 10  
  
        Console.WriteLine("The 10 largest files under {0} are:", root)  
  
        For Each fi As System.IO.FileInfo In tenLargest  
            Console.WriteLine("{0}: {1} bytes", fi.FullName, fi.Length)  
        Next  
  
        ' Group files according to their size,  
        ' leaving out the ones under 200K  
        Dim sizeGroups = From file As System.IO.FileInfo In fileList _  
                         Where file.Length > 0 _  
                         Let groupLength = file.Length / 100000 _  
                         Group file By groupLength Into fileGroup = Group _  
                         Where groupLength >= 2 _  
                         Order By groupLength Descending  
  
        For Each group In sizeGroups  
            Console.WriteLine(group.groupLength + "00000")  
  
            For Each item As System.IO.FileInfo In group.fileGroup  
                Console.WriteLine("   {0}: {1}", item.Name, item.Length)  
            Next  
        Next  
  
        ' Keep the console window open in debug mode  
        Console.WriteLine("Press any key to exit.")  
        Console.ReadKey()  
  
    End Sub  
  
    ' This method is used to catch the possible exception  
    ' that can be raised when accessing the FileInfo.Length property.  
    ' In this particular case, it is safe to ignore the exception.  
    Function GetFileLength(ByVal fi As System.IO.FileInfo) As Long  
        Dim retval As Long  
        Try  
            retval = fi.Length  
        Catch ex As FileNotFoundException  
            ' If a file is no longer present,  
            ' just return zero bytes.   
            retval = 0  
        End Try  
  
        Return retval  
    End Function  
End Module  
```  
  
 <span data-ttu-id="ec5b9-112">このクエリは、完全な <xref:System.IO.FileInfo> オブジェクトを返すために、まずデータ ソース内の各ファイルを調べ、それらのファイルを Length プロパティの値で並べ替えています。</span><span class="sxs-lookup"><span data-stu-id="ec5b9-112">To return one or more complete <xref:System.IO.FileInfo> objects, the query first must examine each one in the data source, and then sort them by the value of their Length property.</span></span> <span data-ttu-id="ec5b9-113">そうすることで、長さが最大である単一のファイルまたは一連のファイルを取得することができます。</span><span class="sxs-lookup"><span data-stu-id="ec5b9-113">Then it can return the single one or the sequence with the greatest lengths.</span></span> <span data-ttu-id="ec5b9-114">リスト内の最初の要素は、<xref:System.Linq.Enumerable.First%2A> を使用して取得します。</span><span class="sxs-lookup"><span data-stu-id="ec5b9-114">Use <xref:System.Linq.Enumerable.First%2A> to return the first element in a list.</span></span> <span data-ttu-id="ec5b9-115">先頭から n 件の要素を取得するには、<xref:System.Linq.Enumerable.Take%2A> を使用します。</span><span class="sxs-lookup"><span data-stu-id="ec5b9-115">Use <xref:System.Linq.Enumerable.Take%2A> to return the first n number of elements.</span></span> <span data-ttu-id="ec5b9-116">並べ替え順序に Descending を指定することによって、最小の要素がリストの先頭に来るようにしています。</span><span class="sxs-lookup"><span data-stu-id="ec5b9-116">Specify a descending sort order to put the smallest elements at the start of the list.</span></span>  
  
 <span data-ttu-id="ec5b9-117">このクエリでは、`GetFiles` の呼び出しで <xref:System.IO.FileInfo> オブジェクトが作成された後に別のスレッドでファイルが削除された場合に発生する例外の可能性に対処するために、別途設けられたメソッドを呼び出してファイル サイズ (バイト単位) を取得しています。</span><span class="sxs-lookup"><span data-stu-id="ec5b9-117">The query calls out to a separate method to obtain the file size in bytes in order to consume the possible exception that will be raised in the case where a file was deleted on another thread in the time period since the <xref:System.IO.FileInfo> object was created in the call to `GetFiles`.</span></span> <span data-ttu-id="ec5b9-118"><xref:System.IO.FileInfo> オブジェクトの作成後であっても、例外は発生する可能性があります。<xref:System.IO.FileInfo> オブジェクトは、<xref:System.IO.FileInfo.Length%2A> プロパティが最初にアクセスされたときに最新のサイズ (バイト単位) に基づいてそのプロパティを更新しようと試みるためです。</span><span class="sxs-lookup"><span data-stu-id="ec5b9-118">Even through the <xref:System.IO.FileInfo> object has already been created, the exception can occur because a <xref:System.IO.FileInfo> object will try to refresh its <xref:System.IO.FileInfo.Length%2A> property by using the most current size in bytes the first time the property is accessed.</span></span> <span data-ttu-id="ec5b9-119">この操作をクエリの外側の try-catch ブロックに置くことで、"副作用の原因となりうるような操作はクエリ内では行わない" という原則に従っているのです。</span><span class="sxs-lookup"><span data-stu-id="ec5b9-119">By putting this operation in a try-catch block outside the query, we follow the rule of avoiding operations in queries that can cause side-effects.</span></span> <span data-ttu-id="ec5b9-120">一般に、アプリケーションが不明な状態に陥ることのないよう、例外を処理する際には十分な注意が必要です。</span><span class="sxs-lookup"><span data-stu-id="ec5b9-120">In general, great care must be taken when consuming exceptions, to make sure that an application is not left in an unknown state.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="ec5b9-121">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="ec5b9-121">Compiling the Code</span></span>  
<span data-ttu-id="ec5b9-122">VB.NET コンソール アプリケーション プロジェクトを作成、 `Imports` System.Linq 名前空間のステートメント。</span><span class="sxs-lookup"><span data-stu-id="ec5b9-122">Create a VB.NET console application project, with an `Imports` statement for the System.Linq namespace.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="ec5b9-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="ec5b9-123">See also</span></span>

- [<span data-ttu-id="ec5b9-124">LINQ to Objects (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ec5b9-124">LINQ to Objects (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md)
- [<span data-ttu-id="ec5b9-125">LINQ とファイル ディレクトリ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ec5b9-125">LINQ and File Directories (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-and-file-directories.md)
