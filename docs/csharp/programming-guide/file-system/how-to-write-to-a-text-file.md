---
title: '方法: テキスト ファイルに書き込む - C# プログラミング ガイド'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- TextWriter.WriteLine
- StreamWriter.Close
helpviewer_keywords:
- files [C#], text files
- text, writing to files [C#]
ms.assetid: 2e99f184-d88b-4719-a7f1-d9ec482aa809
ms.openlocfilehash: e3fa0eb12c9259629ff8151ff2d057f2744e9e36
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64595630"
---
# <a name="how-to-write-to-a-text-file-c-programming-guide"></a><span data-ttu-id="c4e69-102">方法: テキスト ファイルに書き込む (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="c4e69-102">How to: Write to a Text File (C# Programming Guide)</span></span>
<span data-ttu-id="c4e69-103">テキストをファイルに書き込むさまざまな方法を次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="c4e69-103">These examples show various ways to write text to a file.</span></span> <span data-ttu-id="c4e69-104">最初の 2 つの例では、<xref:System.IO.File?displayProperty=nameWithType> クラスの便利な静的メソッドを使用して、すべての `IEnumerable<string>` の各要素と文字列をテキスト ファイルに記述しています。</span><span class="sxs-lookup"><span data-stu-id="c4e69-104">The first two examples use static convenience methods on the <xref:System.IO.File?displayProperty=nameWithType> class to write each element of any `IEnumerable<string>` and a string to a text file.</span></span> <span data-ttu-id="c4e69-105">例 3 は、ファイルに書き込むときに各行を個別に処理する必要がある場合にテキストをファイルに追加する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="c4e69-105">Example 3 shows how to add text to a file when you have to process each line individually as you write to the file.</span></span> <span data-ttu-id="c4e69-106">例 1 ～ 3 ではすべての既存の内容が上書きされます。例 4 に、既存のファイルにテキストを追加する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="c4e69-106">Examples 1-3 overwrite all existing content in the file, but example 4 shows you how to append text to an existing file.</span></span>  
  
 <span data-ttu-id="c4e69-107">これらの例はいずれもリテラル文字列をファイルに書き込みます。</span><span class="sxs-lookup"><span data-stu-id="c4e69-107">These examples all write string literals to files.</span></span> <span data-ttu-id="c4e69-108">ファイルに書き込まれるテキストの書式を設定する場合は、<xref:System.String.Format%2A> メソッドまたは C# の[文字列補間](../../../csharp/language-reference/tokens/interpolated.md)機能を使用します。</span><span class="sxs-lookup"><span data-stu-id="c4e69-108">If you want to format text written to a file, use the <xref:System.String.Format%2A> method or C# [string interpolation](../../../csharp/language-reference/tokens/interpolated.md) feature.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c4e69-109">例</span><span class="sxs-lookup"><span data-stu-id="c4e69-109">Example</span></span>  
 [!code-csharp[csFilesandFolders#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csFilesAndFolders/CS/FileIteration.cs#3)]  
  
## <a name="robust-programming"></a><span data-ttu-id="c4e69-110">信頼性の高いプログラミング</span><span class="sxs-lookup"><span data-stu-id="c4e69-110">Robust Programming</span></span>  
 <span data-ttu-id="c4e69-111">次の条件を満たす場合は、例外が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c4e69-111">The following conditions may cause an exception:</span></span>  
  
- <span data-ttu-id="c4e69-112">ファイルは存在するが、読み取り専用である。</span><span class="sxs-lookup"><span data-stu-id="c4e69-112">The file exists and is read-only.</span></span>  
  
- <span data-ttu-id="c4e69-113">パス名が長すぎる。</span><span class="sxs-lookup"><span data-stu-id="c4e69-113">The path name may be too long.</span></span>  
  
- <span data-ttu-id="c4e69-114">ディスクがいっぱいになっている。</span><span class="sxs-lookup"><span data-stu-id="c4e69-114">The disk may be full.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4e69-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="c4e69-115">See also</span></span>

- [<span data-ttu-id="c4e69-116">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="c4e69-116">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="c4e69-117">ファイル システムとレジストリ (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="c4e69-117">File System and the Registry (C# Programming Guide)</span></span>](../../../csharp/programming-guide/file-system/index.md)
- [<span data-ttu-id="c4e69-118">サンプル: コレクションをアプリケーション ストレージに保存する</span><span class="sxs-lookup"><span data-stu-id="c4e69-118">Sample: Save a collection to Application Storage</span></span>](https://code.msdn.microsoft.com/CSWinStoreAppSaveCollection-bed5d6e6)
