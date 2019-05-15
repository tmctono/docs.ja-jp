---
title: '方法: Visual Basic でファイル パスを解析する'
ms.date: 07/20/2015
helpviewer_keywords:
- file names [Visual Basic], parsing [Visual Basic]
- parsing, file paths [Visual Basic]
ms.assetid: c1bd99c9-8160-456a-b5ab-60a49139b923
ms.openlocfilehash: 6961f481126d34b18c5a11d83c4c6c37c2c81c71
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64629163"
---
# <a name="how-to-parse-file-paths-in-visual-basic"></a><span data-ttu-id="3e8ca-102">方法: Visual Basic でファイル パスを解析する</span><span class="sxs-lookup"><span data-stu-id="3e8ca-102">How to: Parse File Paths in Visual Basic</span></span>
<span data-ttu-id="3e8ca-103"><xref:Microsoft.VisualBasic.FileIO.FileSystem> オブジェクトには、ファイル パスを解析するときに役立つメソッドがいくつか用意されています。</span><span class="sxs-lookup"><span data-stu-id="3e8ca-103">The <xref:Microsoft.VisualBasic.FileIO.FileSystem> object offers a number of useful methods when parsing file paths.</span></span>  
  
- <span data-ttu-id="3e8ca-104"><xref:Microsoft.VisualBasic.FileIO.FileSystem.CombinePath%2A> メソッドは、2 つのパスを受け取り、適切な書式で結合されたパスを返します。</span><span class="sxs-lookup"><span data-stu-id="3e8ca-104">The <xref:Microsoft.VisualBasic.FileIO.FileSystem.CombinePath%2A> method takes two paths and returns a properly formatted combined path.</span></span>  
  
- <span data-ttu-id="3e8ca-105"><xref:Microsoft.VisualBasic.FileIO.FileSystem.GetParentPath%2A> メソッドは、指定されたパスの親の絶対パスを返します。</span><span class="sxs-lookup"><span data-stu-id="3e8ca-105">The <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetParentPath%2A> method returns the absolute path of the parent of the provided path.</span></span>  
  
- <span data-ttu-id="3e8ca-106"><xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFileInfo%2A> メソッドは、 <xref:System.IO.FileInfo> オブジェクトを返します。このオブジェクトを照会すると、ファイルのプロパティ (名前やパスなど) を確認できます。</span><span class="sxs-lookup"><span data-stu-id="3e8ca-106">The <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFileInfo%2A> method returns a <xref:System.IO.FileInfo> object that can be queried to determine the file's properties, such as its name and path.</span></span>  
  
 <span data-ttu-id="3e8ca-107">ファイル名の拡張子に基づいてファイルの内容を判断しないでください。</span><span class="sxs-lookup"><span data-stu-id="3e8ca-107">Do not make decisions about the contents of the file based on the file name extension.</span></span> <span data-ttu-id="3e8ca-108">たとえば、Form1.vb というファイルは Visual Basic のソース ファイルではない可能性もあります。</span><span class="sxs-lookup"><span data-stu-id="3e8ca-108">For example, the file Form1.vb may not be a Visual Basic source file.</span></span>  
  
### <a name="to-determine-a-files-name-and-path"></a><span data-ttu-id="3e8ca-109">ファイルの名前とパスを確認するには</span><span class="sxs-lookup"><span data-stu-id="3e8ca-109">To determine a file's name and path</span></span>  
  
- <span data-ttu-id="3e8ca-110"><xref:System.IO.FileInfo.DirectoryName%2A> オブジェクトの <xref:System.IO.FileInfo.Name%2A> および <xref:System.IO.FileInfo> プロパティを使用して、ファイルの名前とパスを確認します。</span><span class="sxs-lookup"><span data-stu-id="3e8ca-110">Use the <xref:System.IO.FileInfo.DirectoryName%2A> and <xref:System.IO.FileInfo.Name%2A> properties of the <xref:System.IO.FileInfo> object to determine a file's name and path.</span></span> <span data-ttu-id="3e8ca-111">この例は、名前とパスを確認し、それらを表示します。</span><span class="sxs-lookup"><span data-stu-id="3e8ca-111">This example determines the name and path and displays them.</span></span>  
  
     [!code-vb[VbVbcnMyFileSystem#54](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#54)]  
  
### <a name="to-combine-a-files-name-and-directory-to-create-the-full-path"></a><span data-ttu-id="3e8ca-112">ファイルの名前とディレクトリを結合して完全パスを作成するには</span><span class="sxs-lookup"><span data-stu-id="3e8ca-112">To combine a file's name and directory to create the full path</span></span>  
  
- <span data-ttu-id="3e8ca-113">`CombinePath` メソッドを使用し、ディレクトリと名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="3e8ca-113">Use the `CombinePath` method, supplying the directory and name.</span></span> <span data-ttu-id="3e8ca-114">この例では、前の例で作成した文字列 `folderPath` と `fileName` を受け取って、両者を結合し、結果を表示します。</span><span class="sxs-lookup"><span data-stu-id="3e8ca-114">This example takes the strings `folderPath` and `fileName` created in the previous example, combines them, and displays the result.</span></span>  
  
     [!code-vb[VbVbcnMyFileSystem#55](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#55)]  
  
## <a name="see-also"></a><span data-ttu-id="3e8ca-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="3e8ca-115">See also</span></span>

- <xref:Microsoft.VisualBasic.FileIO.FileSystem>
- <xref:Microsoft.VisualBasic.FileIO.FileSystem.CombinePath%2A>
- <xref:System.IO.FileInfo>
- <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFileInfo%2A>
- [<span data-ttu-id="3e8ca-116">方法: ディレクトリにあるファイルのコレクションを取得する</span><span class="sxs-lookup"><span data-stu-id="3e8ca-116">How to: Get the Collection of Files in a Directory</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-get-the-collection-of-files-in-a-directory.md)
