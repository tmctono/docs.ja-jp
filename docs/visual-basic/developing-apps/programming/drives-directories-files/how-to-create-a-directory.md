---
title: '方法: Visual Basic でディレクトリを作成する'
ms.date: 07/20/2015
helpviewer_keywords:
- directories [Visual Basic], creating
- folders [Visual Basic], creating
ms.assetid: 0351a2ca-24d8-43b5-bb39-9b99e6401cff
ms.openlocfilehash: e94bd597b022e5e380651a62832e1f71fa72cec9
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "58818710"
---
# <a name="how-to-create-a-directory-in-visual-basic"></a><span data-ttu-id="88aa5-102">方法: Visual Basic でディレクトリを作成する</span><span class="sxs-lookup"><span data-stu-id="88aa5-102">How to: Create a Directory in Visual Basic</span></span>
<span data-ttu-id="88aa5-103">ディレクトリを作成するには、`My.Computer.FileSystem` オブジェクトの `CreateDirectory` メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="88aa5-103">Use the `CreateDirectory` method of the `My.Computer.FileSystem` object to create directories.</span></span>  
  
 <span data-ttu-id="88aa5-104">ディレクトリが既にある場合、例外はスローされません。</span><span class="sxs-lookup"><span data-stu-id="88aa5-104">If the directory already exists, no exception is thrown.</span></span>  
  
### <a name="to-create-a-directory"></a><span data-ttu-id="88aa5-105">ディレクトリを作成するには</span><span class="sxs-lookup"><span data-stu-id="88aa5-105">To create a directory</span></span>  
  
-   <span data-ttu-id="88aa5-106">ディレクトリを作成する場所を完全にパスに指定して、`CreateDirectory` メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="88aa5-106">Use the `CreateDirectory` method by specifying the full path of the location where the directory should be created.</span></span> <span data-ttu-id="88aa5-107">この例では、`C:\Documents and Settings\All Users\Documents` に `NewDirectory` ディレクトリを作成します。</span><span class="sxs-lookup"><span data-stu-id="88aa5-107">This example creates the directory `NewDirectory` in `C:\Documents and Settings\All Users\Documents`.</span></span>  
  
     [!code-vb[VbVbcnMyFileSystem#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#2)]  
  
## <a name="robust-programming"></a><span data-ttu-id="88aa5-108">信頼性の高いプログラミング</span><span class="sxs-lookup"><span data-stu-id="88aa5-108">Robust Programming</span></span>  
 <span data-ttu-id="88aa5-109">次の条件を満たす場合は、例外が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="88aa5-109">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="88aa5-110">ディレクトリ名が不正な場合。</span><span class="sxs-lookup"><span data-stu-id="88aa5-110">The directory name is malformed.</span></span> <span data-ttu-id="88aa5-111">たとえば、不正な文字が含まれている場合や、空白だけの場合などです (<xref:System.ArgumentException>)。</span><span class="sxs-lookup"><span data-stu-id="88aa5-111">For example, it contains illegal characters or is only white space (<xref:System.ArgumentException>).</span></span>  
  
-   <span data-ttu-id="88aa5-112">作成するディレクトリの親ディレクトリが読み取り専用である場合 (<xref:System.IO.IOException>)。</span><span class="sxs-lookup"><span data-stu-id="88aa5-112">The parent directory of the directory to be created is read-only (<xref:System.IO.IOException>).</span></span>  
  
-   <span data-ttu-id="88aa5-113">ディレクトリ名が `Nothing` の場合 (<xref:System.ArgumentNullException>)｡</span><span class="sxs-lookup"><span data-stu-id="88aa5-113">The directory name is `Nothing` (<xref:System.ArgumentNullException>).</span></span>  
  
-   <span data-ttu-id="88aa5-114">ディレクトリ名が長すぎる場合 (<xref:System.IO.PathTooLongException>)｡</span><span class="sxs-lookup"><span data-stu-id="88aa5-114">The directory name is too long (<xref:System.IO.PathTooLongException>).</span></span>  
  
-   <span data-ttu-id="88aa5-115">ディレクトリ名がコロン ":" の場合 (<xref:System.NotSupportedException>)｡</span><span class="sxs-lookup"><span data-stu-id="88aa5-115">The directory name is a colon ":" (<xref:System.NotSupportedException>).</span></span>  
  
-   <span data-ttu-id="88aa5-116">ユーザーがディレクトリを作成するアクセス許可を持っていない場合 (<xref:System.UnauthorizedAccessException>)。</span><span class="sxs-lookup"><span data-stu-id="88aa5-116">The user does not have permission to create the directory (<xref:System.UnauthorizedAccessException>).</span></span>  
  
-   <span data-ttu-id="88aa5-117">部分的に信頼されている状況でユーザーにアクセス許可がない場合 (<xref:System.Security.SecurityException>)。</span><span class="sxs-lookup"><span data-stu-id="88aa5-117">The user lacks permissions in a partial-trust situation (<xref:System.Security.SecurityException>).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88aa5-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="88aa5-118">See also</span></span>

- <xref:Microsoft.VisualBasic.FileIO.FileSystem.CreateDirectory%2A>
- [<span data-ttu-id="88aa5-119">ファイルおよびディレクトリの作成、削除、および移動</span><span class="sxs-lookup"><span data-stu-id="88aa5-119">Creating, Deleting, and Moving Files and Directories</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/creating-deleting-and-moving-files-and-directories.md)
