---
title: '方法: Visual Basic でファイルのコピーを別のディレクトリに作成する'
ms.date: 07/20/2015
helpviewer_keywords:
- My.Computer.FileSystem.CopyFile method, copying files [Visual Basic]
- files [Visual Basic], copying
- CopyFile method [Visual Basic], copying files in Visual Basic
- I/O [Visual Basic], copying files
ms.assetid: 88e2145c-d414-45a5-ad03-6f5d58ecca26
ms.openlocfilehash: fa4289f33a8c9498648dc71cb92d6403ece30524
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64628810"
---
# <a name="how-to-create-a-copy-of-a-file-in-a-different-directory-in-visual-basic"></a><span data-ttu-id="3ca58-102">方法: Visual Basic でファイルのコピーを別のディレクトリに作成する</span><span class="sxs-lookup"><span data-stu-id="3ca58-102">How to: Create a Copy of a File in a Different Directory in Visual Basic</span></span>
<span data-ttu-id="3ca58-103">`My.Computer.FileSystem.CopyFile` メソッドでは、ファイルをコピーできます。</span><span class="sxs-lookup"><span data-stu-id="3ca58-103">The `My.Computer.FileSystem.CopyFile` method allows you to copy files.</span></span> <span data-ttu-id="3ca58-104">このパラメーターでは、既存のファイルの上書き、ファイルの名前変更、操作の進行状況の表示、ユーザーによる操作のキャンセルが可能になります。</span><span class="sxs-lookup"><span data-stu-id="3ca58-104">Its parameters provide the ability to overwrite existing files, rename the file, show the progress of the operation, and allow the user to cancel the operation.</span></span>  
  
### <a name="to-copy-a-text-file-to-another-folder"></a><span data-ttu-id="3ca58-105">テキスト ファイルを別のフォルダーにコピーするには</span><span class="sxs-lookup"><span data-stu-id="3ca58-105">To copy a text file to another folder</span></span>  
  
- <span data-ttu-id="3ca58-106">`CopyFile` メソッドを使用し、ソース ファイルとターゲット ディレクトリを指定してファイルをコピーします。</span><span class="sxs-lookup"><span data-stu-id="3ca58-106">Use the `CopyFile` method to copy a file, specifying a source file and the target directory.</span></span> <span data-ttu-id="3ca58-107">`overwrite` パラメーターでは、既存のファイルを上書きするかどうかを指定できます。</span><span class="sxs-lookup"><span data-stu-id="3ca58-107">The `overwrite` parameter allows you to specify whether or not to overwrite existing files.</span></span> <span data-ttu-id="3ca58-108">次のコード例では、`CopyFile` の使用方法を示します。</span><span class="sxs-lookup"><span data-stu-id="3ca58-108">The following code examples demonstrate how to use `CopyFile`.</span></span>  
  
     [!code-vb[VbFileIOMisc#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIOMisc/VB/Class1.vb#24)]  
  
## <a name="robust-programming"></a><span data-ttu-id="3ca58-109">信頼性の高いプログラミング</span><span class="sxs-lookup"><span data-stu-id="3ca58-109">Robust Programming</span></span>  
 <span data-ttu-id="3ca58-110">次の条件を満たす場合は、例外がスローされる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="3ca58-110">The following conditions may cause an exception to be thrown:</span></span>  
  
- <span data-ttu-id="3ca58-111">次のいずれかの理由で、パスが正しくない。長さが 0 の文字列である、空白だけが含まれている、使用できない文字が含まれている、デバイス パスである (先頭が \\\\.\\) (<xref:System.ArgumentException>)。</span><span class="sxs-lookup"><span data-stu-id="3ca58-111">The path is not valid for one of the following reasons: it is a zero-length string, it contains only white space, it contains invalid characters, or it is a device path (starts with \\\\.\\) (<xref:System.ArgumentException>).</span></span>  
  
- <span data-ttu-id="3ca58-112">システムが絶対パスを取得できなかった (<xref:System.ArgumentException>)。</span><span class="sxs-lookup"><span data-stu-id="3ca58-112">The system could not retrieve the absolute path (<xref:System.ArgumentException>).</span></span>  
  
- <span data-ttu-id="3ca58-113">パスが `Nothing` であるため、有効でない (<xref:System.ArgumentNullException>)</span><span class="sxs-lookup"><span data-stu-id="3ca58-113">The path is not valid because it is `Nothing` (<xref:System.ArgumentNullException>).</span></span>  
  
- <span data-ttu-id="3ca58-114">ソース ファイルが正しくない、または存在しない (<xref:System.IO.FileNotFoundException>)。</span><span class="sxs-lookup"><span data-stu-id="3ca58-114">The source file is not valid or does not exist (<xref:System.IO.FileNotFoundException>).</span></span>  
  
- <span data-ttu-id="3ca58-115">結合したパスが、既存のディレクトリを指している (<xref:System.IO.IOException>)。</span><span class="sxs-lookup"><span data-stu-id="3ca58-115">The combined path points to an existing directory (<xref:System.IO.IOException>).</span></span>  
  
- <span data-ttu-id="3ca58-116">リンク先ファイルが存在し、`overwrite` が `False` に設定されている (<xref:System.IO.IOException>)。</span><span class="sxs-lookup"><span data-stu-id="3ca58-116">The destination file exists and `overwrite` is set to `False` (<xref:System.IO.IOException>).</span></span>  
  
- <span data-ttu-id="3ca58-117">ファイルにアクセスする十分なアクセス許可がユーザーにない (<xref:System.IO.IOException>)。</span><span class="sxs-lookup"><span data-stu-id="3ca58-117">The user does not have sufficient permissions to access the file (<xref:System.IO.IOException>).</span></span>  
  
- <span data-ttu-id="3ca58-118">同じ名前がターゲット フォルダー内のファイルで使用されている (<xref:System.IO.IOException>)。</span><span class="sxs-lookup"><span data-stu-id="3ca58-118">A file in the target folder with the same name is in use (<xref:System.IO.IOException>).</span></span>  
  
- <span data-ttu-id="3ca58-119">パス内のファイル名またはフォルダー名にコロン (:) が含まれている、または形式が無効である (<xref:System.NotSupportedException>)。</span><span class="sxs-lookup"><span data-stu-id="3ca58-119">A file or folder name in the path contains a colon (:) or is in an invalid format (<xref:System.NotSupportedException>).</span></span>  
  
- <span data-ttu-id="3ca58-120">`ShowUI` が `True` に設定され、`onUserCancel` が `ThrowException`に設定され、ユーザーが操作をキャンセルしている (<xref:System.OperationCanceledException>)。</span><span class="sxs-lookup"><span data-stu-id="3ca58-120">`ShowUI` is set to `True`, `onUserCancel` is set to `ThrowException`, and the user has cancelled the operation (<xref:System.OperationCanceledException>).</span></span>  
  
- <span data-ttu-id="3ca58-121">`ShowUI` が `True` に設定され、`onUserCancel` が `ThrowException` に設定され、未指定の I/O エラーが発生する (<xref:System.OperationCanceledException>)。</span><span class="sxs-lookup"><span data-stu-id="3ca58-121">`ShowUI` is set to `True`, `onUserCancel` is set to `ThrowException`, and an unspecified I/O error occurs (<xref:System.OperationCanceledException>).</span></span>  
  
- <span data-ttu-id="3ca58-122">パスがシステムで定義されている最大長を超えている (<xref:System.IO.PathTooLongException>)。</span><span class="sxs-lookup"><span data-stu-id="3ca58-122">The path exceeds the system-defined maximum length (<xref:System.IO.PathTooLongException>).</span></span>  
  
- <span data-ttu-id="3ca58-123">ユーザーに必要なアクセス許可がない (<xref:System.UnauthorizedAccessException>)。</span><span class="sxs-lookup"><span data-stu-id="3ca58-123">The user does not have required permission (<xref:System.UnauthorizedAccessException>).</span></span>  
  
- <span data-ttu-id="3ca58-124">ユーザーがパスを参照するのに必要なアクセス許可がない (<xref:System.Security.SecurityException>)</span><span class="sxs-lookup"><span data-stu-id="3ca58-124">The user lacks necessary permissions to view the path (<xref:System.Security.SecurityException>).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ca58-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="3ca58-125">See also</span></span>

- <xref:Microsoft.VisualBasic.FileIO.FileSystem>
- <xref:Microsoft.VisualBasic.FileIO.FileSystem.CopyFile%2A>
- <xref:Microsoft.VisualBasic.FileIO.UICancelOption>
- [<span data-ttu-id="3ca58-126">方法: 特定のパターンを持つファイルをディレクトリにコピーする</span><span class="sxs-lookup"><span data-stu-id="3ca58-126">How to: Copy Files with a Specific Pattern to a Directory</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-copy-files-with-a-specific-pattern-to-a-directory.md)
- [<span data-ttu-id="3ca58-127">方法: ファイルのコピーを同じディレクトリに作成する</span><span class="sxs-lookup"><span data-stu-id="3ca58-127">How to: Create a Copy of a File in the Same Directory</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-create-a-copy-of-a-file-in-the-same-directory.md)
- [<span data-ttu-id="3ca58-128">方法: ディレクトリを別のディレクトリにコピーする</span><span class="sxs-lookup"><span data-stu-id="3ca58-128">How to: Copy a Directory to Another Directory</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-copy-a-directory-to-another-directory.md)
- [<span data-ttu-id="3ca58-129">方法: ファイルの名前を変更する</span><span class="sxs-lookup"><span data-stu-id="3ca58-129">How to: Rename a File</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-rename-a-file.md)
