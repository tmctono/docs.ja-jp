---
title: 区切りファイルのフィールドの順序を変更する方法 (LINQ) (C#)
description: C# の LINQ で .csv ファイルのフィールドを再配置する方法について学習します。 この例では、列の順序を変更し、列にマージして、列の値で行を並べ替えます。
ms.date: 07/20/2015
ms.assetid: 4e62d82c-61b7-4f18-b9a1-86723746d7d2
ms.openlocfilehash: 3ebc56b418d2732a296896a19d770136a56e2fbb
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/23/2020
ms.locfileid: "87103409"
---
# <a name="how-to-reorder-the-fields-of-a-delimited-file-linq-c"></a>区切りファイルのフィールドの順序を変更する方法 (LINQ) (C#)
コンマ区切り (CSV) ファイルは、テキスト ファイルです。多くの場合、行と列で表されるスプレッドシート データや他の表形式データの格納に使用されます。 <xref:System.String.Split%2A> メソッドを使用してフィールドを区切ると、LINQ を使用した CSV ファイルのクエリと操作がとても簡単になります。 この手法は、CSV ファイルに限らず、行が構造化されているテキストの一部を並べ替えるときに利用できます。  
  
 次の例では、学生の "名"、"姓"、"ID" を表す 3 つの列があります。 これらのフィールドは、学生の姓に基づいてアルファベット順に並べられています。 クエリによって、ID 列が最初に表示され、学生の姓と名を結合して 2 列目に表示されるように列順を変えます。 行は ID フィールドの順に並べ替えられます。 結果は新しいファイルに保存され、元のデータは変更されません。  
  
### <a name="to-create-the-data-file"></a>データ ファイルを作成するには  
  
1. 次の行を、spreadsheet1.csv というプレーン テキスト ファイルにコピーします。 プロジェクト フォルダーにファイルを保存します。  
  
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
  
## <a name="example"></a>例  
  
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
  
## <a name="compiling-the-code"></a>コードのコンパイル  
System.Linq 名前空間と System.IO 名前空間に `using` ディレクティブを使用して、C# コンソール アプリケーション プロジェクトを作成します。
  
## <a name="see-also"></a>関連項目

- [LINQ と文字列 (C#)](./linq-and-strings.md)
- [LINQ とファイル ディレクトリ (C#)](./linq-and-file-directories.md)
- [CSV ファイルから XML を生成する方法 (C#)](./how-to-generate-xml-from-csv-files.md)
