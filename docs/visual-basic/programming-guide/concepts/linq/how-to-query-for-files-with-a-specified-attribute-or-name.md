---
title: '方法: 指定した属性または名前 (Visual Basic) のファイルをクエリ'
ms.date: 07/20/2015
ms.assetid: b26026a3-3f43-448f-a582-259997af6be0
ms.openlocfilehash: 05dfe3e88274efe8d817defcac2f47efe053b12b
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2019
ms.locfileid: "65586493"
---
# <a name="how-to-query-for-files-with-a-specified-attribute-or-name-visual-basic"></a><span data-ttu-id="39a7c-102">方法: 指定した属性または名前 (Visual Basic) のファイルをクエリ</span><span class="sxs-lookup"><span data-stu-id="39a7c-102">How to: Query for Files with a Specified Attribute or Name (Visual Basic)</span></span>
<span data-ttu-id="39a7c-103">この例では、指定されたディレクトリ ツリーで、指定されたファイル名拡張子 (".txt" など) を持つすべてのファイルを検索する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="39a7c-103">This example shows how to find all files that have a specified file name extension (for example ".txt") in a specified directory tree.</span></span> <span data-ttu-id="39a7c-104">また、ファイルの作成日時に基づいて、ツリー内の最も新しいファイルまたは最も古いファイルを返す方法も示します。</span><span class="sxs-lookup"><span data-stu-id="39a7c-104">It also shows how to return either the newest or oldest file in the tree based on the creation time.</span></span>  
  
## <a name="example"></a><span data-ttu-id="39a7c-105">例</span><span class="sxs-lookup"><span data-stu-id="39a7c-105">Example</span></span>  
  
```vb  
Module FindFileByExtension  
    Sub Main()  
  
        ' Change the drive\path if necessary  
        Dim root As String = "C:\Program Files\Microsoft Visual Studio 9.0"  
  
        'Take a snapshot of the folder contents  
        Dim dir As New System.IO.DirectoryInfo(root)  
  
        Dim fileList = dir.GetFiles("*.*", System.IO.SearchOption.AllDirectories)  
  
        ' This query will produce the full path for all .txt files  
        ' under the specified folder including subfolders.  
        ' It orders the list according to the file name.  
        Dim fileQuery = From file In fileList _  
                        Where file.Extension = ".txt" _  
                        Order By file.Name _  
                        Select file  
  
        For Each file In fileQuery  
            Console.WriteLine(file.FullName)  
        Next  
  
        ' Create and execute a new query by using  
        ' the previous query as a starting point.  
        ' fileQuery is not executed again until the  
        ' call to Last  
        Dim fileQuery2 = From file In fileQuery _  
                         Order By file.CreationTime _  
                         Select file.Name, file.CreationTime  
  
        ' Execute the query  
        Dim newestFile = fileQuery2.Last  
  
        Console.WriteLine("\r\nThe newest .txt file is {0}. Creation time: {1}", _  
                newestFile.Name, newestFile.CreationTime)  
  
        ' Keep the console window open in debug mode  
        Console.WriteLine("Press any key to exit.")  
        Console.ReadKey()  
  
    End Sub  
End Module  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="39a7c-106">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="39a7c-106">Compiling the Code</span></span>  
<span data-ttu-id="39a7c-107">VB.NET コンソール アプリケーション プロジェクトを作成、 `Imports` System.Linq 名前空間のステートメント。</span><span class="sxs-lookup"><span data-stu-id="39a7c-107">Create a VB.NET console application project, with an `Imports` statement for the System.Linq namespace.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="39a7c-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="39a7c-108">See also</span></span>

- [<span data-ttu-id="39a7c-109">LINQ to Objects (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="39a7c-109">LINQ to Objects (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md)
- [<span data-ttu-id="39a7c-110">LINQ とファイル ディレクトリ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="39a7c-110">LINQ and File Directories (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-and-file-directories.md)
