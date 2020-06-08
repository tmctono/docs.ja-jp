---
title: テキスト ファイルを 1 行ずつ読み取る方法 - C# プログラミング ガイド
ms.date: 07/20/2015
helpviewer_keywords:
- ReadLine method [C#]
- reading text files, line by line
- text files [C#]
ms.assetid: d62e22c5-a13c-48db-af9b-f10c801b0cb1
ms.openlocfilehash: b54d072ce9837f9b15694f2d7100817de62e9762
ms.sourcegitcommit: a241301495a84cc8c64fe972330d16edd619868b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/01/2020
ms.locfileid: "84241774"
---
# <a name="how-to-read-a-text-file-one-line-at-a-time-c-programming-guide"></a><span data-ttu-id="47605-102">テキスト ファイルを 1 行ずつ読み取る方法 (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="47605-102">How to read a text file one line at a time (C# Programming Guide)</span></span>
<span data-ttu-id="47605-103">次の例では、`StreamReader` クラスの `ReadLine` メソッドを使用して、テキスト ファイルの内容を一度に 1 行ずつ文字列に読み込みます。</span><span class="sxs-lookup"><span data-stu-id="47605-103">This example reads the contents of a text file, one line at a time, into a string using the `ReadLine` method of the `StreamReader` class.</span></span> <span data-ttu-id="47605-104">各テキスト行は文字列 `line` に格納され、画面に表示されます。</span><span class="sxs-lookup"><span data-stu-id="47605-104">Each text line is stored into the string `line` and displayed on the screen.</span></span>  
  
## <a name="example"></a><span data-ttu-id="47605-105">例</span><span class="sxs-lookup"><span data-stu-id="47605-105">Example</span></span>  
  
```csharp
int counter = 0;  
string line;  
  
// Read the file and display it line by line.  
System.IO.StreamReader file =
    new System.IO.StreamReader(@"c:\test.txt");  
while((line = file.ReadLine()) != null)  
{  
    System.Console.WriteLine(line);  
    counter++;  
}  
  
file.Close();  
System.Console.WriteLine("There were {0} lines.", counter);  
// Suspend the screen.  
System.Console.ReadLine();  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="47605-106">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="47605-106">Compiling the Code</span></span>  
 <span data-ttu-id="47605-107">コードをコピーし、コンソール アプリケーションの `Main` メソッドに貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="47605-107">Copy the code and paste it into the `Main` method of a console application.</span></span>  
  
 <span data-ttu-id="47605-108">`"c:\test.txt"` を実際のファイル名に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="47605-108">Replace `"c:\test.txt"` with the actual file name.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="47605-109">信頼性の高いプログラミング</span><span class="sxs-lookup"><span data-stu-id="47605-109">Robust Programming</span></span>  
 <span data-ttu-id="47605-110">次の条件を満たす場合は、例外が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="47605-110">The following conditions may cause an exception:</span></span>  
  
- <span data-ttu-id="47605-111">ファイルが存在しない。</span><span class="sxs-lookup"><span data-stu-id="47605-111">The file may not exist.</span></span>  
  
## <a name="net-security"></a><span data-ttu-id="47605-112">.NET セキュリティ</span><span class="sxs-lookup"><span data-stu-id="47605-112">.NET Security</span></span>  
 <span data-ttu-id="47605-113">ファイル名からファイルの内容を判断しないでください。</span><span class="sxs-lookup"><span data-stu-id="47605-113">Do not make decisions about the contents of the file based on the name of the file.</span></span> <span data-ttu-id="47605-114">たとえば、`myFile.cs` ファイルが C# ソース ファイルとは限りません。</span><span class="sxs-lookup"><span data-stu-id="47605-114">For example, the file `myFile.cs` may not be a C# source file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47605-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="47605-115">See also</span></span>

- <xref:System.IO?displayProperty=nameWithType>
- [<span data-ttu-id="47605-116">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="47605-116">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="47605-117">ファイル システムとレジストリ (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="47605-117">File System and the Registry (C# Programming Guide)</span></span>](./index.md)
