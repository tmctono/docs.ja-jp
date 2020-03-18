---
title: '方法: ファイルのテキストの読み取り'
ms.date: 01/03/2019
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- streams, reading text from files
- reading text files
- reading data, text files
- data streams, reading text from files
- I/O [.NET Framework], reading text from files
ms.assetid: ed180baa-dfc6-4c69-a725-46e87edafb27
ms.openlocfilehash: 8676e5f0acd0646b4854df7dde060ec15548ec3e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/15/2020
ms.locfileid: "78155725"
---
# <a name="how-to-read-text-from-a-file"></a><span data-ttu-id="91dbd-102">方法: ファイルのテキストの読み取り</span><span class="sxs-lookup"><span data-stu-id="91dbd-102">How to: Read text from a file</span></span>
<span data-ttu-id="91dbd-103">次に、.NET デスクトップ アプリを使用してテキスト ファイルから同期でテキストを読み取る方法と非同期でテキストを読み取る方法の例を示します。</span><span class="sxs-lookup"><span data-stu-id="91dbd-103">The following examples show how to read text synchronously and asynchronously from a text file using .NET for desktop apps.</span></span> <span data-ttu-id="91dbd-104">どちらの例でも、<xref:System.IO.StreamReader> クラスのインスタンスを作成する場合に、ファイルの相対パスまたは絶対パスを指定します。</span><span class="sxs-lookup"><span data-stu-id="91dbd-104">In both examples, when you create the instance of the <xref:System.IO.StreamReader> class, you provide the relative or absolute path to the file.</span></span>
  
> [!NOTE]
> <span data-ttu-id="91dbd-105">Windows ランタイムではファイルに対する読み取りと書き込みに別のストリーム型が用意されているため、これらのコード例はユニバーサル Windows プラットフォーム (UWP) アプリの開発には適用されません。</span><span class="sxs-lookup"><span data-stu-id="91dbd-105">These code examples do not apply to developing for Universal Windows (UWP) apps, because the Windows Runtime provides different stream types for reading and writing to files.</span></span> <span data-ttu-id="91dbd-106">UWP アプリのファイルからテキストを読み取る方法を示す例については、「[Quickstart: Reading and writing files](https://docs.microsoft.com/previous-versions/windows/apps/hh758325(v=win.10))」 (クイック スタート: ファイルの読み取りと書き込み) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="91dbd-106">For an example that shows how to read text from a file in a UWP app, see [Quickstart: Reading and writing files](https://docs.microsoft.com/previous-versions/windows/apps/hh758325(v=win.10)).</span></span> <span data-ttu-id="91dbd-107">.NET Framework ストリームと Windows ランタイム ストリーム間で変換を行う方法を示す例については、「[方法: .NET Framework ストリームと Windows ランタイム ストリームの間で変換を行う](../../../docs/standard/io/how-to-convert-between-dotnet-streams-and-winrt-streams.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="91dbd-107">For examples that show how to convert between .NET Framework streams and Windows Runtime streams, see [How to: Convert between .NET Framework streams and Windows Runtime streams](../../../docs/standard/io/how-to-convert-between-dotnet-streams-and-winrt-streams.md).</span></span>  
  
## <a name="example-synchronous-read-in-a-console-app"></a><span data-ttu-id="91dbd-108">例:コンソール アプリの同期読み取り</span><span class="sxs-lookup"><span data-stu-id="91dbd-108">Example: Synchronous read in a console app</span></span>  
<span data-ttu-id="91dbd-109">次の例では、コンソール アプリ内での同期読み取り操作を示します。</span><span class="sxs-lookup"><span data-stu-id="91dbd-109">The following example shows a synchronous read operation within a console app.</span></span> <span data-ttu-id="91dbd-110">この例では、ストリーム リーダーを使用してテキスト ファイルを開き、コンテンツが文字列にコピーされ、文字列がコンソールに出力されます。</span><span class="sxs-lookup"><span data-stu-id="91dbd-110">This example opens the text file using a stream reader, copies the contents to a string, and outputs the string to the console.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="91dbd-111">サンプルでは、*TestFile.txt* という名前のファイルがアプリと同じフォルダーに入っていると想定しています。</span><span class="sxs-lookup"><span data-stu-id="91dbd-111">The example assumes that a file named *TestFile.txt* already exists in the same folder as the app.</span></span>  

 [!code-csharp[Conceptual.BasicIO.TextFiles#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.basicio.textfiles/cs/source3.cs#3)]
 [!code-vb[Conceptual.BasicIO.TextFiles#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.basicio.textfiles/vb/source3.vb#3)]  
  
## <a name="example-asynchronous-read-in-a-wpf-app"></a><span data-ttu-id="91dbd-112">例:WPF アプリの非同期読み取り</span><span class="sxs-lookup"><span data-stu-id="91dbd-112">Example: Asynchronous read in a WPF app</span></span>
 <span data-ttu-id="91dbd-113">次の例では、Windows Presentation Foundation (WPF) アプリ内での非同期読み取り操作を示します。</span><span class="sxs-lookup"><span data-stu-id="91dbd-113">The following example shows an asynchronous read operation in a Windows Presentation Foundation (WPF) app.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="91dbd-114">サンプルでは、*TestFile.txt* という名前のファイルがアプリと同じフォルダーに入っていると想定しています。</span><span class="sxs-lookup"><span data-stu-id="91dbd-114">The example assumes that a file named *TestFile.txt* already exists in the same folder as the app.</span></span>  

 [!code-csharp[TextFiles](../../../samples/snippets/csharp/VS_Snippets_Wpf/TextFiles/MainWindow.xaml.cs)]
 [!code-vb[TextFiles](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextFiles/MainWindow.xaml.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="91dbd-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="91dbd-115">See also</span></span>

- <xref:System.IO.StreamReader>  
- <xref:System.IO.File.OpenText%2A?displayProperty=nameWithType>  
- <xref:System.IO.StreamReader.ReadLine%2A?displayProperty=nameWithType>  
- [<span data-ttu-id="91dbd-116">非同期ファイル I/O</span><span class="sxs-lookup"><span data-stu-id="91dbd-116">Asynchronous file I/O</span></span>](../../../docs/standard/io/asynchronous-file-i-o.md)  
- <span data-ttu-id="91dbd-117">[方法: ディレクトリ一覧を作成する](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/5cf8zcfh(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="91dbd-117">[How to: Create a directory listing](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/5cf8zcfh(v=vs.100))</span></span>  
- [<span data-ttu-id="91dbd-118">クイック スタート:ファイルの読み書き</span><span class="sxs-lookup"><span data-stu-id="91dbd-118">Quickstart: Reading and writing files</span></span>](https://docs.microsoft.com/previous-versions/windows/apps/hh758325%28v=win.10%29)  
- [<span data-ttu-id="91dbd-119">方法: .NET Framework ストリームと Windows ランタイム ストリームの間で変換を行う</span><span class="sxs-lookup"><span data-stu-id="91dbd-119">How to: Convert between .NET Framework streams and Windows Runtime streams</span></span>](../../../docs/standard/io/how-to-convert-between-dotnet-streams-and-winrt-streams.md)  
- [<span data-ttu-id="91dbd-120">方法: 新しく作成されたデータ ファイルに対して読み書きする</span><span class="sxs-lookup"><span data-stu-id="91dbd-120">How to: Read and write to a newly created data file</span></span>](../../../docs/standard/io/how-to-read-and-write-to-a-newly-created-data-file.md)  
- [<span data-ttu-id="91dbd-121">方法: ログ ファイルを開いて情報を追加する</span><span class="sxs-lookup"><span data-stu-id="91dbd-121">How to: Open and append to a log file</span></span>](../../../docs/standard/io/how-to-open-and-append-to-a-log-file.md)  
- [<span data-ttu-id="91dbd-122">方法: テキストのファイルへの書き込み</span><span class="sxs-lookup"><span data-stu-id="91dbd-122">How to: Write text to a file</span></span>](../../../docs/standard/io/how-to-write-text-to-a-file.md)  
- [<span data-ttu-id="91dbd-123">方法: 文字列からの文字の読み取り</span><span class="sxs-lookup"><span data-stu-id="91dbd-123">How to: Read characters from a string</span></span>](../../../docs/standard/io/how-to-read-characters-from-a-string.md)  
- [<span data-ttu-id="91dbd-124">方法: 文字列への文字の書き込み</span><span class="sxs-lookup"><span data-stu-id="91dbd-124">How to: Write characters to a string</span></span>](../../../docs/standard/io/how-to-write-characters-to-a-string.md)  
- [<span data-ttu-id="91dbd-125">ファイルおよびストリーム入出力</span><span class="sxs-lookup"><span data-stu-id="91dbd-125">File and stream I/O</span></span>](../../../docs/standard/io/index.md)
