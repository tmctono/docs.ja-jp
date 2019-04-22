---
title: '方法: StreamWriter を使用してファイルにテキストを書き込む (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- files [Visual Basic], writing to
- text, writing to files
- writing to files [Visual Basic], StreamWriter
ms.assetid: 99762e57-ef46-4dcc-8959-a8f79c22f067
ms.openlocfilehash: ca792106bdd341fa4be8f3554ce70cd7d3f22522
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "58816069"
---
# <a name="how-to-write-text-to-files-with-a-streamwriter-in-visual-basic"></a><span data-ttu-id="2872a-102">方法: StreamWriter を使用してファイルにテキストを書き込む (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2872a-102">How to: Write Text to Files with a StreamWriter in Visual Basic</span></span>
<span data-ttu-id="2872a-103">この例では、`My.Computer.FileSystem.OpenTextFileWriter` メソッドで <xref:System.IO.StreamWriter> オブジェクトを開き、そのオブジェクトを使用し、<xref:System.IO.StreamWriter> クラスの <xref:System.IO.TextWriter.WriteLine%2A> メソッドでテキスト ファイルに文字列を書き込みます。</span><span class="sxs-lookup"><span data-stu-id="2872a-103">This example opens a <xref:System.IO.StreamWriter> object with the `My.Computer.FileSystem.OpenTextFileWriter` method and uses it to write a string to a text file with the <xref:System.IO.TextWriter.WriteLine%2A> method of the <xref:System.IO.StreamWriter> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2872a-104">例</span><span class="sxs-lookup"><span data-stu-id="2872a-104">Example</span></span>  
 [!code-vb[VbFileIOWrite#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIOWrite/VB/Class1.vb#5)]  
  
## <a name="robust-programming"></a><span data-ttu-id="2872a-105">信頼性の高いプログラミング</span><span class="sxs-lookup"><span data-stu-id="2872a-105">Robust Programming</span></span>  
 <span data-ttu-id="2872a-106">次の条件を満たす場合は、例外が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="2872a-106">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="2872a-107">ファイルが存在するものの、読み取り専用の場合 (<xref:System.IO.IOException>)</span><span class="sxs-lookup"><span data-stu-id="2872a-107">The file exists and is read-only (<xref:System.IO.IOException>).</span></span>  
  
-   <span data-ttu-id="2872a-108">ディスクの空き領域がない場合 (<xref:System.IO.IOException>)</span><span class="sxs-lookup"><span data-stu-id="2872a-108">The disk is full (<xref:System.IO.IOException>).</span></span>  
  
-   <span data-ttu-id="2872a-109">パス名が長すぎる場合 (<xref:System.IO.PathTooLongException>)。</span><span class="sxs-lookup"><span data-stu-id="2872a-109">The pathname is too long (<xref:System.IO.PathTooLongException>).</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="2872a-110">.NET Framework セキュリティ</span><span class="sxs-lookup"><span data-stu-id="2872a-110">.NET Framework Security</span></span>  
 <span data-ttu-id="2872a-111">次のコード例では、ファイルが存在しない場合は新規にファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="2872a-111">This example creates a new file, if the file does not already exist.</span></span> <span data-ttu-id="2872a-112">アプリケーションでファイルを作成する必要がある場合、そのアプリケーションにはフォルダーに対する `Create` アクセスが必要です。</span><span class="sxs-lookup"><span data-stu-id="2872a-112">If an application needs to create a file, that application needs `Create` access for the folder.</span></span> <span data-ttu-id="2872a-113">ファイルが既に存在する場合、アプリケーションに必要なのは、より低い権限である `Write` アクセスだけです。</span><span class="sxs-lookup"><span data-stu-id="2872a-113">If the file already exists, the application needs only `Write` access, a lesser privilege.</span></span> <span data-ttu-id="2872a-114">フォルダーに対して `Read` アクセスを許可するのではなく、可能な限りアプリケーションの配置時にファイルを作成しておき、1 つのファイルに対してのみ `Create` アクセスを許可する方が安全です。</span><span class="sxs-lookup"><span data-stu-id="2872a-114">Where possible, it is more secure to create the file during deployment, and only grant `Read` access to a single file, rather than `Create` access for a folder.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2872a-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="2872a-115">See also</span></span>

- <xref:System.IO.StreamWriter>
- <xref:Microsoft.VisualBasic.FileIO.FileSystem.OpenTextFileWriter%2A>
- [<span data-ttu-id="2872a-116">方法: テキスト ファイルからデータを読み取る</span><span class="sxs-lookup"><span data-stu-id="2872a-116">How to: Read from Text Files</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-text-files.md)
- [<span data-ttu-id="2872a-117">ファイルへの書き込み</span><span class="sxs-lookup"><span data-stu-id="2872a-117">Writing to Files</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/writing-to-files.md)
