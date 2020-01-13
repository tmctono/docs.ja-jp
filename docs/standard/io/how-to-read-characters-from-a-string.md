---
title: '方法: 文字列からの文字の読み取り'
ms.date: 01/21/2019
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- reading characters from strings
- data streams, reading characters from string
- I/O [.NET Framework], reading characters from strings
- reading data, strings
- streams, reading characters from string
ms.assetid: 27ea5e52-6db8-42d8-980a-50bcfc7fd270
ms.openlocfilehash: 0c3516c4abadfd22609c3568beffc14e027ef69e
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/07/2020
ms.locfileid: "75706674"
---
# <a name="how-to-read-characters-from-a-string"></a><span data-ttu-id="bd8ea-102">方法: 文字列からの文字の読み取り</span><span class="sxs-lookup"><span data-stu-id="bd8ea-102">How to: Read characters from a string</span></span>
<span data-ttu-id="bd8ea-103">次のコード例は、文字列から同期的または非同期的に文字を読み取る方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="bd8ea-103">The following code examples show how to read characters synchronously or asynchronously from a string.</span></span>  
  
## <a name="example-read-characters-synchronously"></a><span data-ttu-id="bd8ea-104">例:同期的に文字を読み取る</span><span class="sxs-lookup"><span data-stu-id="bd8ea-104">Example: Read characters synchronously</span></span> 
 <span data-ttu-id="bd8ea-105">この例では、文字列から同期的に 13 文字を読み取り、配列に格納し、これらを表示します。</span><span class="sxs-lookup"><span data-stu-id="bd8ea-105">This example reads 13 characters synchronously from a string, stores them in an array, and displays them.</span></span> <span data-ttu-id="bd8ea-106">次に、この例では、文字列の残りの文字を読み取り、6 番目の要素で始まる配列に格納し、配列の内容を表示します。</span><span class="sxs-lookup"><span data-stu-id="bd8ea-106">The example then reads the rest of the characters in the string, stores them in the array starting at the sixth element, and displays the contents of the array.</span></span>  
  
 [!code-csharp[Conceptual.StringReader#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.stringreader/cs/source.cs#1)]
 [!code-vb[Conceptual.StringReader#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.stringreader/vb/source.vb#1)]  
  
## <a name="example-read-characters-asynchronously"></a><span data-ttu-id="bd8ea-107">例:非同期的に文字を読み取る</span><span class="sxs-lookup"><span data-stu-id="bd8ea-107">Example: Read characters asynchronously</span></span>  
 <span data-ttu-id="bd8ea-108">次の例は WPF アプリの裏側にあるコードです。</span><span class="sxs-lookup"><span data-stu-id="bd8ea-108">The next example is the code behind a WPF app.</span></span> <span data-ttu-id="bd8ea-109">ウィンドウを読み込むと、<xref:System.Windows.Controls.TextBox> コントロールから非同期的にすべての文字を読み取り、配列に格納します。</span><span class="sxs-lookup"><span data-stu-id="bd8ea-109">On window load, the example asynchronously reads all characters from a <xref:System.Windows.Controls.TextBox> control and stores them in an array.</span></span> <span data-ttu-id="bd8ea-110">次に、<xref:System.Windows.Controls.TextBlock> コントロールの個別の行に各文字または空白文字が非同期で書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="bd8ea-110">It then asynchronously writes each letter or white-space character to a separate line of a <xref:System.Windows.Controls.TextBlock> control.</span></span>  
  
 [!code-csharp[Conceptual.StringReader#2](../../../samples/snippets/csharp/VS_Snippets_Wpf/StringReaderWriter/MainWindow.xaml.cs)]
 [!code-vb[Conceptual.StringReader#2](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/StringReaderWriter/MainWindow.xaml.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="bd8ea-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="bd8ea-111">See also</span></span>

- <xref:System.IO.StringReader>  
- <xref:System.IO.StringReader.Read%2A?displayProperty=nameWithType>  
- [<span data-ttu-id="bd8ea-112">非同期ファイル I/O</span><span class="sxs-lookup"><span data-stu-id="bd8ea-112">Asynchronous file I/O</span></span>](../../../docs/standard/io/asynchronous-file-i-o.md)  
- <span data-ttu-id="bd8ea-113">[方法: ディレクトリ一覧を作成する](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/5cf8zcfh(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="bd8ea-113">[How to: Create a directory listing](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/5cf8zcfh(v=vs.100))</span></span>  
- [<span data-ttu-id="bd8ea-114">方法: 新しく作成されたデータ ファイルに対して読み書きする</span><span class="sxs-lookup"><span data-stu-id="bd8ea-114">How to: Read and write to a newly created data file</span></span>](../../../docs/standard/io/how-to-read-and-write-to-a-newly-created-data-file.md)  
- [<span data-ttu-id="bd8ea-115">方法: ログ ファイルを開いて情報を追加する</span><span class="sxs-lookup"><span data-stu-id="bd8ea-115">How to: Open and append to a log file</span></span>](../../../docs/standard/io/how-to-open-and-append-to-a-log-file.md)  
- [<span data-ttu-id="bd8ea-116">方法: ファイルからテキストを読み取る</span><span class="sxs-lookup"><span data-stu-id="bd8ea-116">How to: Read text from a file</span></span>](../../../docs/standard/io/how-to-read-text-from-a-file.md)  
- [<span data-ttu-id="bd8ea-117">方法: テキストのファイルへの書き込み</span><span class="sxs-lookup"><span data-stu-id="bd8ea-117">How to: Write text to a file</span></span>](../../../docs/standard/io/how-to-write-text-to-a-file.md)  
- [<span data-ttu-id="bd8ea-118">方法: 文字列への文字の書き込み</span><span class="sxs-lookup"><span data-stu-id="bd8ea-118">How to: Write characters to a string</span></span>](../../../docs/standard/io/how-to-write-characters-to-a-string.md)  
- [<span data-ttu-id="bd8ea-119">ファイルおよびストリーム入出力</span><span class="sxs-lookup"><span data-stu-id="bd8ea-119">File and stream I/O</span></span>](../../../docs/standard/io/index.md)
