---
title: 区切りファイルのフィールドの順序を変更する方法 (LINQ) (C#)
ms.date: 07/20/2015
ms.assetid: 4e62d82c-61b7-4f18-b9a1-86723746d7d2
ms.openlocfilehash: 6bc502ff12a908edf43f9ff7f5f63f98c3ff29c4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2020
ms.locfileid: "75347654"
---
# <a name="how-to-reorder-the-fields-of-a-delimited-file-linq-c"></a><span data-ttu-id="3ce61-102">区切りファイルのフィールドの順序を変更する方法 (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="3ce61-102">How to reorder the fields of a delimited file (LINQ) (C#)</span></span>
<span data-ttu-id="3ce61-103">コンマ区切り (CSV) ファイルは、テキスト ファイルです。多くの場合、行と列で表されるスプレッドシート データや他の表形式データの格納に使用されます。</span><span class="sxs-lookup"><span data-stu-id="3ce61-103">A comma-separated value (CSV) file is a text file that is often used to store spreadsheet data or other tabular data that is represented by rows and columns.</span></span> <span data-ttu-id="3ce61-104"><xref:System.String.Split%2A> メソッドを使用してフィールドを区切ると、LINQ を使用した CSV ファイルのクエリと操作がとても簡単になります。</span><span class="sxs-lookup"><span data-stu-id="3ce61-104">By using the <xref:System.String.Split%2A> method to separate the fields, it is very easy to query and manipulate CSV files by using LINQ.</span></span> <span data-ttu-id="3ce61-105">この手法は、CSV ファイルに限らず、行が構造化されているテキストの一部を並べ替えるときに利用できます。</span><span class="sxs-lookup"><span data-stu-id="3ce61-105">In fact, the same technique can be used to reorder the parts of any structured line of text; it is not limited to CSV files.</span></span>  
  
 <span data-ttu-id="3ce61-106">次の例では、学生の "名"、"姓"、"ID" を表す 3 つの列があります。</span><span class="sxs-lookup"><span data-stu-id="3ce61-106">In the following example, assume that the three columns represent students' "last name," "first name", and "ID."</span></span> <span data-ttu-id="3ce61-107">これらのフィールドは、学生の姓に基づいてアルファベット順に並べられています。</span><span class="sxs-lookup"><span data-stu-id="3ce61-107">The fields are in alphabetical order based on the students' last names.</span></span> <span data-ttu-id="3ce61-108">クエリによって、ID 列が最初に表示され、学生の姓と名を結合して 2 列目に表示されるように列順を変えます。</span><span class="sxs-lookup"><span data-stu-id="3ce61-108">The query produces a new sequence in which the ID column appears first, followed by a second column that combines the student's first name and last name.</span></span> <span data-ttu-id="3ce61-109">行は ID フィールドの順に並べ替えられます。</span><span class="sxs-lookup"><span data-stu-id="3ce61-109">The lines are reordered according to the ID field.</span></span> <span data-ttu-id="3ce61-110">結果は新しいファイルに保存され、元のデータは変更されません。</span><span class="sxs-lookup"><span data-stu-id="3ce61-110">The results are saved into a new file and the original data is not modified.</span></span>  
  
### <a name="to-create-the-data-file"></a><span data-ttu-id="3ce61-111">データ ファイルを作成するには</span><span class="sxs-lookup"><span data-stu-id="3ce61-111">To create the data file</span></span>  
  
1. <span data-ttu-id="3ce61-112">次の行を、spreadsheet1.csv というプレーン テキスト ファイルにコピーします。</span><span class="sxs-lookup"><span data-stu-id="3ce61-112">Copy the following lines into a plain text file that is named spreadsheet1.csv.</span></span> <span data-ttu-id="3ce61-113">プロジェクト フォルダーにファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="3ce61-113">Save the file in your project folder.</span></span>  
  
    ```csv  
    Adams,Terry,120  
    Fakhouri,Fadi,116  
    Feng,Hanying,117  
    Garcia,Cesar,114  
    Garcia,Debra,115  
    Garcia,Hugo,118  
    Mortensen,Sven,113  
    O'Donnell,Claire,112  
    Omelchenko,Svetlana,111  
    Tucker,Lance,119  
    Tucker,Michael,122  
    Zabokritski,Eugene,121  
    ```  
  
## <a name="example"></a><span data-ttu-id="3ce61-114">例</span><span class="sxs-lookup"><span data-stu-id="3ce61-114">Example</span></span>  
  
```csharp  
class CSVFiles  
{  
    static void Main(string[] args)  
    {  
        // Create the IEnumerable data source  
        string[] lines = System.IO.File.ReadAllLines(@"../../../spreadsheet1.csv");  
  
        // Create the query. Put field 2 first, then  
        // reverse and combine fields 0 and 1 from the old field  
        IEnumerable<string> query =  
            from line in lines  
            let x = line.Split(',')  
            orderby x[2]  
            select x[2] + ", " + (x[1] + " " + x[0]);  
  
        // Execute the query and write out the new file. Note that WriteAllLines  
        // takes a string[], so ToArray is called on the query.  
        System.IO.File.WriteAllLines(@"../../../spreadsheet2.csv", query.ToArray());  
  
        Console.WriteLine("Spreadsheet2.csv written to disk. Press any key to exit");  
        Console.ReadKey();  
    }  
}  
/* Output to spreadsheet2.csv:  
111, Svetlana Omelchenko  
112, Claire O'Donnell  
113, Sven Mortensen  
114, Cesar Garcia  
115, Debra Garcia  
116, Fadi Fakhouri  
117, Hanying Feng  
118, Hugo Garcia  
119, Lance Tucker  
120, Terry Adams  
121, Eugene Zabokritski  
122, Michael Tucker  
 */  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="3ce61-115">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="3ce61-115">Compiling the Code</span></span>  
<span data-ttu-id="3ce61-116">System.Linq 名前空間と System.IO 名前空間に `using` ディレクティブを使用して、C# コンソール アプリケーション プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="3ce61-116">Create a C# console application project, with `using` directives for the System.Linq and System.IO namespaces.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="3ce61-117">参照</span><span class="sxs-lookup"><span data-stu-id="3ce61-117">See also</span></span>

- [<span data-ttu-id="3ce61-118">LINQ と文字列 (C#)</span><span class="sxs-lookup"><span data-stu-id="3ce61-118">LINQ and Strings (C#)</span></span>](./linq-and-strings.md)
- [<span data-ttu-id="3ce61-119">LINQ とファイル ディレクトリ (C#)</span><span class="sxs-lookup"><span data-stu-id="3ce61-119">LINQ and File Directories (C#)</span></span>](./linq-and-file-directories.md)
- [<span data-ttu-id="3ce61-120">CSV ファイルから XML を生成する方法 (C#)</span><span class="sxs-lookup"><span data-stu-id="3ce61-120">How to generate XML from CSV files (C#)</span></span>](./how-to-generate-xml-from-csv-files.md)
