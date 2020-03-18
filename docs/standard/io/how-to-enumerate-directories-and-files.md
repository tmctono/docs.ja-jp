---
title: '方法: ディレクトリとファイルを列挙する'
ms.date: 12/27/2018
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- I/O [.NET Framework], enumerating directories and files
ms.assetid: 86b69a08-3bfa-4e5f-b4e1-3b7cb8478215
ms.openlocfilehash: 6a26d0ef529b81976c4d2caafed34bb5f08d8d46
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/15/2020
ms.locfileid: "75707746"
---
# <a name="how-to-enumerate-directories-and-files"></a><span data-ttu-id="af7b6-102">方法: ディレクトリとファイルを列挙する</span><span class="sxs-lookup"><span data-stu-id="af7b6-102">How to: Enumerate directories and files</span></span>
<span data-ttu-id="af7b6-103">列挙可能なコレクションでは、ディレクトリとファイルの大きなコレクションを操作する際に配列よりも優れたパフォーマンスが得られます。</span><span class="sxs-lookup"><span data-stu-id="af7b6-103">Enumerable collections provide better performance than arrays when you work with large collections of directories and files.</span></span> <span data-ttu-id="af7b6-104">ディレクトリとファイルを列挙するには、列挙可能なディレクトリ名またはファイル名のコレクション、またはその <xref:System.IO.DirectoryInfo>、<xref:System.IO.FileInfo>、または <xref:System.IO.FileSystemInfo> オブジェクトを返すメソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="af7b6-104">To enumerate directories and files, use methods that return an enumerable collection of directory or file names, or their <xref:System.IO.DirectoryInfo>, <xref:System.IO.FileInfo>, or <xref:System.IO.FileSystemInfo> objects.</span></span>  
  
<span data-ttu-id="af7b6-105">ディレクトリまたはファイルの名前のみを検索して返す場合は、<xref:System.IO.Directory> クラスの列挙メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="af7b6-105">If you want to search and return only the names of directories or files, use the enumeration methods of the <xref:System.IO.Directory> class.</span></span> <span data-ttu-id="af7b6-106">ディレクトリまたはファイルの他のプロパティを検索して返す場合は、<xref:System.IO.DirectoryInfo> および <xref:System.IO.FileSystemInfo> クラスを使用します。</span><span class="sxs-lookup"><span data-stu-id="af7b6-106">If you want to search and return other properties of directories or files, use the <xref:System.IO.DirectoryInfo> and <xref:System.IO.FileSystemInfo> classes.</span></span>  
  
<span data-ttu-id="af7b6-107"><xref:System.Collections.Generic.List%601> のようなコレクション クラスのコンストラクターの <xref:System.Collections.Generic.IEnumerable%601> パラメーターとして、このようなメソッドの列挙可能なコレクションを使用できます。</span><span class="sxs-lookup"><span data-stu-id="af7b6-107">You can use enumerable collections from these methods as the <xref:System.Collections.Generic.IEnumerable%601> parameter for constructors of collection classes like <xref:System.Collections.Generic.List%601>.</span></span>  
  
<span data-ttu-id="af7b6-108">次の表は、ファイルとディレクトリの列挙可能なコレクションを返すメソッドをまとめたものです。</span><span class="sxs-lookup"><span data-stu-id="af7b6-108">The following table summarizes the methods that return enumerable collections of files and directories:</span></span>  
  
|<span data-ttu-id="af7b6-109">検索して返すもの</span><span class="sxs-lookup"><span data-stu-id="af7b6-109">To search and return</span></span>|<span data-ttu-id="af7b6-110">使用するメソッド</span><span class="sxs-lookup"><span data-stu-id="af7b6-110">Use method</span></span>|  
|------------------|-------------------------------------|-------------------|  
|<span data-ttu-id="af7b6-111">ディレクトリ名</span><span class="sxs-lookup"><span data-stu-id="af7b6-111">Directory names</span></span>|<xref:System.IO.Directory.EnumerateDirectories%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="af7b6-112">ディレクトリ情報 (<xref:System.IO.DirectoryInfo>)</span><span class="sxs-lookup"><span data-stu-id="af7b6-112">Directory information (<xref:System.IO.DirectoryInfo>)</span></span>|<xref:System.IO.DirectoryInfo.EnumerateDirectories%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="af7b6-113">ファイル名</span><span class="sxs-lookup"><span data-stu-id="af7b6-113">File names</span></span>|<xref:System.IO.Directory.EnumerateFiles%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="af7b6-114">ファイル情報 (<xref:System.IO.FileInfo>)</span><span class="sxs-lookup"><span data-stu-id="af7b6-114">File information (<xref:System.IO.FileInfo>)</span></span>|<xref:System.IO.DirectoryInfo.EnumerateFiles%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="af7b6-115">ファイル システムのエントリ名</span><span class="sxs-lookup"><span data-stu-id="af7b6-115">File system entry names</span></span>|<xref:System.IO.Directory.EnumerateFileSystemEntries%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="af7b6-116">ファイル システムのエントリ情報 (<xref:System.IO.FileSystemInfo>)</span><span class="sxs-lookup"><span data-stu-id="af7b6-116">File system entry information (<xref:System.IO.FileSystemInfo>)</span></span>|<xref:System.IO.DirectoryInfo.EnumerateFileSystemInfos%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="af7b6-117">ディレクトリとファイルの名前</span><span class="sxs-lookup"><span data-stu-id="af7b6-117">Directory and file names</span></span> |<xref:System.IO.Directory.EnumerateFileSystemEntries%2A?displayProperty=nameWithType>|  

> [!NOTE]
> <span data-ttu-id="af7b6-118">省略可能な <xref:System.IO.SearchOption> 列挙型の <xref:System.IO.SearchOption.AllDirectories> オプションを使用すると、親ディレクトリのサブディレクトリ内にあるすべてのファイルをすぐに列挙できますが、<xref:System.UnauthorizedAccessException> のエラーによって列挙が不完全になる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="af7b6-118">Although you can immediately enumerate all the files in the subdirectories of a parent directory by using the <xref:System.IO.SearchOption.AllDirectories> option of the optional <xref:System.IO.SearchOption> enumeration, <xref:System.UnauthorizedAccessException> errors may make the enumeration incomplete.</span></span> <span data-ttu-id="af7b6-119">このような例外をキャッチするには、まずディレクトリを列挙してからファイルを列挙します。</span><span class="sxs-lookup"><span data-stu-id="af7b6-119">You can catch these exceptions by first enumerating directories and then enumerating files.</span></span>  
  
## <a name="examples-use-the-directory-class"></a><span data-ttu-id="af7b6-120">次に例を示します。 Directory クラスを使用する</span><span class="sxs-lookup"><span data-stu-id="af7b6-120">Examples: Use the Directory class</span></span>  
  
<span data-ttu-id="af7b6-121">次の例では、<xref:System.IO.Directory.EnumerateDirectories%28System.String%29?displayProperty=nameWithType> メソッドを使用して、指定されたパスの最上位レベルのディレクトリ名のリストを取得します。</span><span class="sxs-lookup"><span data-stu-id="af7b6-121">The following example uses the <xref:System.IO.Directory.EnumerateDirectories%28System.String%29?displayProperty=nameWithType> method to get a list of the top-level directory names in a specified path.</span></span>  

[!code-csharp[System.IO.EnumDirs1#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.enumdirs1/cs/program.cs#1)]
[!code-vb[System.IO.EnumDirs1#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.enumdirs1/vb/program.vb#1)]  

<span data-ttu-id="af7b6-122">次の例では、<xref:System.IO.Directory.EnumerateFiles%28System.String%2CSystem.String%2CSystem.IO.SearchOption%29?displayProperty=nameWithType> メソッドを使用して、特定のパターンに一致するディレクトリとサブディレクトリ内にあるすべてのファイル名を再帰的に列挙します。</span><span class="sxs-lookup"><span data-stu-id="af7b6-122">The following example uses the <xref:System.IO.Directory.EnumerateFiles%28System.String%2CSystem.String%2CSystem.IO.SearchOption%29?displayProperty=nameWithType> method to recursively enumerate all file names in a directory and subdirectories that match a certain pattern.</span></span> <span data-ttu-id="af7b6-123">次に、各ファイルの各行を読み取り、指定された文字列を含む行をファイル名とパスと共に表示します。</span><span class="sxs-lookup"><span data-stu-id="af7b6-123">It then reads each line of each file and displays the lines that contain a specified string, with their filenames and paths.</span></span>

[!code-csharp[System.IO.Directory.EnumerateFiles#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.directory.enumeratefiles/cs/program.cs#1)]
[!code-vb[System.IO.Directory.EnumerateFiles#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.directory.enumeratefiles/vb/program.vb#1)]  
  
## <a name="examples-use-the-directoryinfo-class"></a><span data-ttu-id="af7b6-124">次に例を示します。 DirectoryInfo クラスを使用する</span><span class="sxs-lookup"><span data-stu-id="af7b6-124">Examples: Use the DirectoryInfo class</span></span>  
  
<span data-ttu-id="af7b6-125">次の例では、<xref:System.IO.DirectoryInfo.EnumerateDirectories%2A?displayProperty=nameWithType> メソッドを使用して、<xref:System.IO.FileSystemInfo.CreationTimeUtc> が特定の <xref:System.DateTime> 値より前の最上位ディレクトリのコレクションを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="af7b6-125">The following example uses the <xref:System.IO.DirectoryInfo.EnumerateDirectories%2A?displayProperty=nameWithType> method to list a collection of top-level directories whose <xref:System.IO.FileSystemInfo.CreationTimeUtc> is earlier than a certain <xref:System.DateTime> value.</span></span>  

[!code-csharp[System.IO.DirectoryInfo.EnumDirs#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.directoryinfo.enumdirs/cs/program.cs)]
[!code-vb[System.IO.DirectoryInfo.EnumDirs#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.directoryinfo.enumdirs/vb/module1.vb)]  
  
<span data-ttu-id="af7b6-126">次の例では、<xref:System.IO.DirectoryInfo.EnumerateFiles%2A?displayProperty=nameWithType> メソッドを使用して、<xref:System.IO.FileInfo.Length> が 10 MB を超えるすべてのファイルを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="af7b6-126">The following example uses the <xref:System.IO.DirectoryInfo.EnumerateFiles%2A?displayProperty=nameWithType> method to list all files whose <xref:System.IO.FileInfo.Length> exceeds 10MB.</span></span> <span data-ttu-id="af7b6-127">この例では、まず、最上位レベルのディレクトリを列挙して考えられる未承認アクセス例外をキャッチしてから、ファイルを列挙します。</span><span class="sxs-lookup"><span data-stu-id="af7b6-127">This example first enumerates the top-level directories, to catch possible unauthorized access exceptions, and then enumerates the files.</span></span>  

[!code-csharp[System.IO.DirectoryInfo.EnumerateDirectories#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.directoryinfo.enumeratedirectories/cs/program.cs#1)]
[!code-vb[System.IO.DirectoryInfo.EnumerateDirectories#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.directoryinfo.enumeratedirectories/vb/program.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="af7b6-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="af7b6-128">See also</span></span>

- [<span data-ttu-id="af7b6-129">ファイルおよびストリーム入出力</span><span class="sxs-lookup"><span data-stu-id="af7b6-129">File and stream I/O</span></span>](../../../docs/standard/io/index.md)
