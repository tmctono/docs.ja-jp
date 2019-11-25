---
title: '方法: ファイルのコピーを同じディレクトリに作成する'
ms.date: 07/20/2015
f1_keywords:
- File.Copy
helpviewer_keywords:
- My.Computer.FileSystem.CopyFile method, copying files [Visual Basic]
- files [Visual Basic], copying
- CopyFile method [Visual Basic], copying files in Visual Basic
- I/O [Visual Basic], copying files
ms.assetid: b2fdda86-e666-42c2-9706-9527e9fa68ff
ms.openlocfilehash: 33a4f5424ac50de7b5dc988034ca15127dc1ed02
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348819"
---
# <a name="how-to-create-a-copy-of-a-file-in-the-same-directory-in-visual-basic"></a><span data-ttu-id="d8845-102">方法: Visual Basic でファイルのコピーを同じディレクトリに作成する</span><span class="sxs-lookup"><span data-stu-id="d8845-102">How to: Create a Copy of a File in the Same Directory in Visual Basic</span></span>

<span data-ttu-id="d8845-103">ファイルをコピーするには、`My.Computer.FileSystem.CopyFile` メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="d8845-103">Use the `My.Computer.FileSystem.CopyFile` method to copy files.</span></span> <span data-ttu-id="d8845-104">このパラメーターでは、既存のファイルの上書き、ファイルの名前変更、操作の進行状況の表示、ユーザーによる操作のキャンセルが可能になります。</span><span class="sxs-lookup"><span data-stu-id="d8845-104">The parameters allow you to overwrite existing files, rename the file, show the progress of the operation, and allow the user to cancel the operation.</span></span>  
  
### <a name="to-create-a-copy-of-a-file-in-the-same-folder"></a><span data-ttu-id="d8845-105">ファイルのコピーを同じフォルダーに作成するには</span><span class="sxs-lookup"><span data-stu-id="d8845-105">To create a copy of a file in the same folder</span></span>  
  
- <span data-ttu-id="d8845-106">ターゲット ファイルと場所を指定し、`CopyFile` メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="d8845-106">Use the `CopyFile` method, supplying the target file and the location.</span></span> <span data-ttu-id="d8845-107">次の例では、`test2.txt` という `test.txt` のコピーを作成します。</span><span class="sxs-lookup"><span data-stu-id="d8845-107">The following example creates a copy of `test.txt` called `test2.txt`.</span></span>  
  
     [!code-vb[VbVbcnMyFileSystem#51](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#51)]  
  
### <a name="to-create-a-copy-of-a-file-in-the-same-folder-overwriting-existing-files"></a><span data-ttu-id="d8845-108">同じフォルダーにファイルのコピーを、既存のファイルを上書きして作成するには</span><span class="sxs-lookup"><span data-stu-id="d8845-108">To create a copy of a file in the same folder, overwriting existing files</span></span>  
  
- <span data-ttu-id="d8845-109">ターゲット ファイルと場所を指定し、`overwrite` を `True` に設定して、`CopyFile` メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="d8845-109">Use the `CopyFile` method, supplying the target file and location, and setting `overwrite` to `True`.</span></span> <span data-ttu-id="d8845-110">次の例では、`test2.txt` という `test.txt` のコピーを、既存のファイルをその名前で上書きして作成します。</span><span class="sxs-lookup"><span data-stu-id="d8845-110">The following example creates a copy of `test.txt` called `test2.txt` and overwrites any existing files by that name.</span></span>  
  
     [!code-vb[VbVbcnMyFileSystem#52](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#52)]  
  
## <a name="robust-programming"></a><span data-ttu-id="d8845-111">信頼性の高いプログラミング</span><span class="sxs-lookup"><span data-stu-id="d8845-111">Robust Programming</span></span>  

 <span data-ttu-id="d8845-112">次の条件を満たす場合は、例外がスローされる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d8845-112">The following conditions may cause an exception to be thrown:</span></span>  
  
- <span data-ttu-id="d8845-113">次のいずれかの理由で、パスが正しくない。長さが 0 の文字列である、空白だけが含まれている、使用できない文字が含まれている、デバイス パスである (先頭が \\\\.\\) (<xref:System.ArgumentException>)。</span><span class="sxs-lookup"><span data-stu-id="d8845-113">The path is not valid for one of the following reasons: it is a zero-length string, it contains only white space, it contains invalid characters, or it is a device path (starts with \\\\.\\) (<xref:System.ArgumentException>).</span></span>  
  
- <span data-ttu-id="d8845-114">システムが絶対パスを取得できなかった (<xref:System.ArgumentException>)。</span><span class="sxs-lookup"><span data-stu-id="d8845-114">The system could not retrieve the absolute path (<xref:System.ArgumentException>).</span></span>  
  
- <span data-ttu-id="d8845-115">パスが `Nothing` であるため、有効でない (<xref:System.ArgumentNullException>)</span><span class="sxs-lookup"><span data-stu-id="d8845-115">The path is not valid because it is `Nothing` (<xref:System.ArgumentNullException>).</span></span>  
  
- <span data-ttu-id="d8845-116">ソース ファイルが正しくない、または存在しない (<xref:System.IO.FileNotFoundException>)。</span><span class="sxs-lookup"><span data-stu-id="d8845-116">The source file is not valid or does not exist (<xref:System.IO.FileNotFoundException>).</span></span>  
  
- <span data-ttu-id="d8845-117">結合したパスが、既存のディレクトリを指している (<xref:System.IO.IOException>)。</span><span class="sxs-lookup"><span data-stu-id="d8845-117">The combined path points to an existing directory (<xref:System.IO.IOException>).</span></span>  
  
- <span data-ttu-id="d8845-118">リンク先ファイルが存在し、`overwrite` が `False` に設定されている (<xref:System.IO.IOException>)。</span><span class="sxs-lookup"><span data-stu-id="d8845-118">The destination file exists and `overwrite` is set to `False` (<xref:System.IO.IOException>).</span></span>  
  
- <span data-ttu-id="d8845-119">ファイルにアクセスする十分なアクセス許可がユーザーにない (<xref:System.IO.IOException>)。</span><span class="sxs-lookup"><span data-stu-id="d8845-119">The user does not have sufficient permissions to access the file (<xref:System.IO.IOException>).</span></span>  
  
- <span data-ttu-id="d8845-120">同じ名前がターゲット フォルダー内のファイルで使用されている (<xref:System.IO.IOException>)。</span><span class="sxs-lookup"><span data-stu-id="d8845-120">A file in the target folder with the same name is in use (<xref:System.IO.IOException>).</span></span>  
  
- <span data-ttu-id="d8845-121">パス内のファイル名またはフォルダー名にコロン (:) が含まれている、または形式が無効である (<xref:System.NotSupportedException>)。</span><span class="sxs-lookup"><span data-stu-id="d8845-121">A file or folder name in the path contains a colon (:) or is in an invalid format (<xref:System.NotSupportedException>).</span></span>  
  
- <span data-ttu-id="d8845-122">`ShowUI` が `True` に設定され、`onUserCancel` が `ThrowException`に設定され、ユーザーが操作をキャンセルしている (<xref:System.OperationCanceledException>)。</span><span class="sxs-lookup"><span data-stu-id="d8845-122">`ShowUI` is set to `True`, `onUserCancel` is set to `ThrowException`, and the user has cancelled the operation (<xref:System.OperationCanceledException>).</span></span>  
  
- <span data-ttu-id="d8845-123">`ShowUI` が `True` に設定され、`onUserCancel` が `ThrowException` に設定され、未指定の I/O エラーが発生する (<xref:System.OperationCanceledException>)。</span><span class="sxs-lookup"><span data-stu-id="d8845-123">`ShowUI` is set to `True`, `onUserCancel` is set to `ThrowException`, and an unspecified I/O error occurs (<xref:System.OperationCanceledException>).</span></span>  
  
- <span data-ttu-id="d8845-124">パスがシステムで定義されている最大長を超えている (<xref:System.IO.PathTooLongException>)。</span><span class="sxs-lookup"><span data-stu-id="d8845-124">The path exceeds the system-defined maximum length (<xref:System.IO.PathTooLongException>).</span></span>  
  
- <span data-ttu-id="d8845-125">ユーザーに必要なアクセス許可がない (<xref:System.UnauthorizedAccessException>)。</span><span class="sxs-lookup"><span data-stu-id="d8845-125">The user does not have required permission (<xref:System.UnauthorizedAccessException>).</span></span>  
  
- <span data-ttu-id="d8845-126">ユーザーがパスを参照するのに必要なアクセス許可がない (<xref:System.Security.SecurityException>)</span><span class="sxs-lookup"><span data-stu-id="d8845-126">The user lacks necessary permissions to view the path (<xref:System.Security.SecurityException>).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8845-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="d8845-127">See also</span></span>

- <xref:Microsoft.VisualBasic.FileIO.FileSystem>
- <xref:Microsoft.VisualBasic.FileIO.FileSystem.CopyFile%2A>
- <xref:Microsoft.VisualBasic.FileIO.UICancelOption>
- [<span data-ttu-id="d8845-128">方法: 特定のパターンを持つファイルをディレクトリにコピーする</span><span class="sxs-lookup"><span data-stu-id="d8845-128">How to: Copy Files with a Specific Pattern to a Directory</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-copy-files-with-a-specific-pattern-to-a-directory.md)
- [<span data-ttu-id="d8845-129">方法: ファイルのコピーを別のディレクトリに作成する</span><span class="sxs-lookup"><span data-stu-id="d8845-129">How to: Create a Copy of a File in a Different Directory</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-create-a-copy-of-a-file-in-a-different-directory.md)
- [<span data-ttu-id="d8845-130">方法: ディレクトリを別のディレクトリにコピーする</span><span class="sxs-lookup"><span data-stu-id="d8845-130">How to: Copy a Directory to Another Directory</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-copy-a-directory-to-another-directory.md)
- [<span data-ttu-id="d8845-131">方法: ファイルの名前を変更する</span><span class="sxs-lookup"><span data-stu-id="d8845-131">How to: Rename a File</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-rename-a-file.md)
