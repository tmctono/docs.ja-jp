---
title: テキスト ファイルを 1 行ずつ読み取る方法 - C# プログラミング ガイド
description: テキスト ファイルを一度に 1 行読み取る方法について説明します。 コード例を参照し、使用可能なその他のリソースを確認します。
ms.date: 07/20/2015
helpviewer_keywords:
- ReadLine method [C#]
- reading text files, line by line
- text files [C#]
ms.assetid: d62e22c5-a13c-48db-af9b-f10c801b0cb1
ms.openlocfilehash: 1e29013b1008e1000c23804dc3056014cc7c104b
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/28/2020
ms.locfileid: "87301958"
---
# <a name="how-to-read-a-text-file-one-line-at-a-time-c-programming-guide"></a><span data-ttu-id="ff410-104">テキスト ファイルを 1 行ずつ読み取る方法 (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="ff410-104">How to read a text file one line at a time (C# Programming Guide)</span></span>
<span data-ttu-id="ff410-105">次の例では、`StreamReader` クラスの `ReadLine` メソッドを使用して、テキスト ファイルの内容を一度に 1 行ずつ文字列に読み込みます。</span><span class="sxs-lookup"><span data-stu-id="ff410-105">This example reads the contents of a text file, one line at a time, into a string using the `ReadLine` method of the `StreamReader` class.</span></span> <span data-ttu-id="ff410-106">各テキスト行は文字列 `line` に格納され、画面に表示されます。</span><span class="sxs-lookup"><span data-stu-id="ff410-106">Each text line is stored into the string `line` and displayed on the screen.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ff410-107">例</span><span class="sxs-lookup"><span data-stu-id="ff410-107">Example</span></span>  
  
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
  
## <a name="compiling-the-code"></a><span data-ttu-id="ff410-108">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="ff410-108">Compiling the Code</span></span>  
 <span data-ttu-id="ff410-109">コードをコピーし、コンソール アプリケーションの `Main` メソッドに貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="ff410-109">Copy the code and paste it into the `Main` method of a console application.</span></span>  
  
 <span data-ttu-id="ff410-110">`"c:\test.txt"` を実際のファイル名に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="ff410-110">Replace `"c:\test.txt"` with the actual file name.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="ff410-111">信頼性の高いプログラミング</span><span class="sxs-lookup"><span data-stu-id="ff410-111">Robust Programming</span></span>  
 <span data-ttu-id="ff410-112">次の条件を満たす場合は、例外が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ff410-112">The following conditions may cause an exception:</span></span>  
  
- <span data-ttu-id="ff410-113">ファイルが存在しない。</span><span class="sxs-lookup"><span data-stu-id="ff410-113">The file may not exist.</span></span>  
  
## <a name="net-security"></a><span data-ttu-id="ff410-114">.NET セキュリティ</span><span class="sxs-lookup"><span data-stu-id="ff410-114">.NET Security</span></span>  
 <span data-ttu-id="ff410-115">ファイル名からファイルの内容を判断しないでください。</span><span class="sxs-lookup"><span data-stu-id="ff410-115">Do not make decisions about the contents of the file based on the name of the file.</span></span> <span data-ttu-id="ff410-116">たとえば、`myFile.cs` ファイルが C# ソース ファイルとは限りません。</span><span class="sxs-lookup"><span data-stu-id="ff410-116">For example, the file `myFile.cs` may not be a C# source file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff410-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="ff410-117">See also</span></span>

- <xref:System.IO?displayProperty=nameWithType>
- [<span data-ttu-id="ff410-118">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="ff410-118">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="ff410-119">ファイル システムとレジストリ (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="ff410-119">File System and the Registry (C# Programming Guide)</span></span>](./index.md)
