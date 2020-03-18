---
title: テキスト ファイルから読み取る方法 - C# プログラミング ガイド
ms.date: 07/20/2015
f1_keywords:
- StreamReader.ReadToEnd
helpviewer_keywords:
- text files, writing to
- reading text files
- reading data, text files
- text files, reading
ms.assetid: 92246c5b-e819-4eea-9370-1a9460e12de3
ms.openlocfilehash: d401a1d1bb2c6fccb203c440f367bd14c80e70e3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2020
ms.locfileid: "75705016"
---
# <a name="how-to-read-from-a-text-file-c-programming-guide"></a><span data-ttu-id="6f533-102">テキスト ファイルから読み取る方法 (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="6f533-102">How to read from a text file (C# Programming Guide)</span></span>
<span data-ttu-id="6f533-103">この例では、<xref:System.IO.File.ReadAllText%2A> クラスの静的メソッド <xref:System.IO.File.ReadAllLines%2A> と <xref:System.IO.File?displayProperty=nameWithType> を使用してテキスト ファイルの内容を読み取ります。</span><span class="sxs-lookup"><span data-stu-id="6f533-103">This example reads the contents of a text file by using the static methods <xref:System.IO.File.ReadAllText%2A> and <xref:System.IO.File.ReadAllLines%2A> from the <xref:System.IO.File?displayProperty=nameWithType> class.</span></span>  
  
<span data-ttu-id="6f533-104"><xref:System.IO.StreamReader> の使用例については、「[テキスト ファイルを 1 行ずつ読み取る方法](./how-to-read-a-text-file-one-line-at-a-time.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6f533-104">For an example that uses <xref:System.IO.StreamReader>, see [How to read a text file one line at a time](./how-to-read-a-text-file-one-line-at-a-time.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="6f533-105">この例では、「[テキスト ファイルに書き込む方法](./how-to-write-to-a-text-file.md)」トピックで作成したファイルを使用しています。</span><span class="sxs-lookup"><span data-stu-id="6f533-105">The files that are used in this example are created in the topic [How to write to a text file](./how-to-write-to-a-text-file.md).</span></span>
  
## <a name="example"></a><span data-ttu-id="6f533-106">例</span><span class="sxs-lookup"><span data-stu-id="6f533-106">Example</span></span>  
 [!code-csharp[csFilesandFolders#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csFilesAndFolders/CS/FileIteration.cs#4)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="6f533-107">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="6f533-107">Compiling the Code</span></span>  
 <span data-ttu-id="6f533-108">コードをコピーし、C# のコンソール アプリケーションに貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="6f533-108">Copy the code and paste it into a C# console application.</span></span>  
  
<span data-ttu-id="6f533-109">「[テキスト ファイルに書き込む方法](./how-to-write-to-a-text-file.md)」のテキスト ファイルを使用せずに独自のテキスト ファイルを使用する場合は、`ReadAllText` と `ReadAllLines` の引数を、ご使用のコンピューター上の該当するパスおよびファイル名に置き換えてください。</span><span class="sxs-lookup"><span data-stu-id="6f533-109">If you are not using the text files from [How to write to a text file](./how-to-write-to-a-text-file.md), replace the argument to `ReadAllText` and `ReadAllLines` with the appropriate path and file name on your computer.</span></span>
  
## <a name="robust-programming"></a><span data-ttu-id="6f533-110">信頼性の高いプログラミング</span><span class="sxs-lookup"><span data-stu-id="6f533-110">Robust Programming</span></span>  
 <span data-ttu-id="6f533-111">次の条件を満たす場合は、例外が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="6f533-111">The following conditions may cause an exception:</span></span>  
  
- <span data-ttu-id="6f533-112">ファイルが存在しない、または指定した場所に存在しない。</span><span class="sxs-lookup"><span data-stu-id="6f533-112">The file doesn't exist or doesn't exist at the specified location.</span></span> <span data-ttu-id="6f533-113">ファイル名のパスとスペルを確認してください。</span><span class="sxs-lookup"><span data-stu-id="6f533-113">Check the path and the spelling of the file name.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="6f533-114">.NET Framework のセキュリティ</span><span class="sxs-lookup"><span data-stu-id="6f533-114">.NET Framework Security</span></span>  
 <span data-ttu-id="6f533-115">ファイル名に基づいてファイルの内容を判断しないでください。</span><span class="sxs-lookup"><span data-stu-id="6f533-115">Do not rely on the name of a file to determine the contents of the file.</span></span> <span data-ttu-id="6f533-116">たとえば、`myFile.cs` というファイルが C# のソース ファイルではない可能性もあります。</span><span class="sxs-lookup"><span data-stu-id="6f533-116">For example, the file `myFile.cs` might not be a C# source file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f533-117">参照</span><span class="sxs-lookup"><span data-stu-id="6f533-117">See also</span></span>

- <xref:System.IO?displayProperty=nameWithType>
- [<span data-ttu-id="6f533-118">C# プログラミングガイド</span><span class="sxs-lookup"><span data-stu-id="6f533-118">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="6f533-119">ファイル システムとレジストリ (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="6f533-119">File System and the Registry (C# Programming Guide)</span></span>](./index.md)
