---
title: フォルダー内のテキスト ファイルの内容にクエリを実行する方法 (LINQ) (C#)
description: C# で LINQ を使用してディレクトリ ツリーに含まれるすべてのファイルを照会し、個々のファイルを開いて、その内容を調べる方法について説明します。
ms.date: 07/20/2015
ms.assetid: f5b4dce7-1a34-4eb4-9bf1-60d5bdda264c
ms.openlocfilehash: 216edc2ee6fc43fd06a3c89b1b6b73f693f752f8
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/23/2020
ms.locfileid: "87104270"
---
# <a name="how-to-query-the-contents-of-text-files-in-a-folder-linq-c"></a><span data-ttu-id="3c3f0-103">フォルダー内のテキスト ファイルの内容にクエリを実行する方法 (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="3c3f0-103">How to query the contents of text files in a folder (LINQ) (C#)</span></span>
<span data-ttu-id="3c3f0-104">この例では、指定したディレクトリ ツリーに含まれるすべてのファイルを照会し、個々のファイルを開いて、その内容を調べています。</span><span class="sxs-lookup"><span data-stu-id="3c3f0-104">This example shows how to query over all the files in a specified directory tree, open each file, and inspect its contents.</span></span> <span data-ttu-id="3c3f0-105">同様の手法を使えば、ディレクトリ ツリーの内容に対するインデックスや逆インデックスを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="3c3f0-105">This type of technique could be used to create indexes or reverse indexes of the contents of a directory tree.</span></span> <span data-ttu-id="3c3f0-106">この例で行っているのは単純な文字列検索です。</span><span class="sxs-lookup"><span data-stu-id="3c3f0-106">A simple string search is performed in this example.</span></span> <span data-ttu-id="3c3f0-107">しかし正規表現を使うと、もっと複雑なパターン マッチングを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="3c3f0-107">However, more complex types of pattern matching can be performed with a regular expression.</span></span> <span data-ttu-id="3c3f0-108">詳細については、「[LINQ クエリと正規表現を組み合わせる方法 (C#)](./how-to-combine-linq-queries-with-regular-expressions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3c3f0-108">For more information, see [How to combine LINQ queries with regular expressions (C#)](./how-to-combine-linq-queries-with-regular-expressions.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="3c3f0-109">例</span><span class="sxs-lookup"><span data-stu-id="3c3f0-109">Example</span></span>  
  
```csharp  
class QueryContents  
{  
    public static void Main()  
    {  
        // Modify this path as necessary.  
        string startFolder = @"c:\program files\Microsoft Visual Studio 9.0\";  
  
        // Take a snapshot of the file system.  
        System.IO.DirectoryInfo dir = new System.IO.DirectoryInfo(startFolder);  
  
        // This method assumes that the application has discovery permissions  
        // for all folders under the specified path.  
        IEnumerable<System.IO.FileInfo> fileList = dir.GetFiles("*.*", System.IO.SearchOption.AllDirectories);  
  
        string searchTerm = @"Visual Studio";  
  
        // Search the contents of each file.  
        // A regular expression created with the RegEx class  
        // could be used instead of the Contains method.  
        // queryMatchingFiles is an IEnumerable<string>.  
        var queryMatchingFiles =  
            from file in fileList  
            where file.Extension == ".htm"  
            let fileText = GetFileText(file.FullName)  
            where fileText.Contains(searchTerm)  
            select file.FullName;  
  
        // Execute the query.  
        Console.WriteLine("The term \"{0}\" was found in:", searchTerm);  
        foreach (string filename in queryMatchingFiles)  
        {  
            Console.WriteLine(filename);  
        }  
  
        // Keep the console window open in debug mode.  
        Console.WriteLine("Press any key to exit");  
        Console.ReadKey();  
    }  
  
    // Read the contents of the file.  
    static string GetFileText(string name)  
    {  
        string fileContents = String.Empty;  
  
        // If the file has been deleted since we took
        // the snapshot, ignore it and return the empty string.  
        if (System.IO.File.Exists(name))  
        {  
            fileContents = System.IO.File.ReadAllText(name);  
        }  
        return fileContents;  
    }  
}  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="3c3f0-110">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="3c3f0-110">Compiling the Code</span></span>  
<span data-ttu-id="3c3f0-111">System.Linq 名前空間と System.IO 名前空間に `using` ディレクティブを使用して、C# コンソール アプリケーション プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="3c3f0-111">Create a C# console application project, with `using` directives for the System.Linq and System.IO namespaces.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="3c3f0-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="3c3f0-112">See also</span></span>

- [<span data-ttu-id="3c3f0-113">LINQ とファイル ディレクトリ (C#)</span><span class="sxs-lookup"><span data-stu-id="3c3f0-113">LINQ and File Directories (C#)</span></span>](./linq-and-file-directories.md)
- [<span data-ttu-id="3c3f0-114">LINQ to Objects (C#)</span><span class="sxs-lookup"><span data-stu-id="3c3f0-114">LINQ to Objects (C#)</span></span>](./linq-to-objects.md)
