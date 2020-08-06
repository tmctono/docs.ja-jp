---
title: ファイルおよびフォルダーをコピー、削除、および移動する方法 - C# プログラミング ガイド
description: File、Directory、FileInfo、および DirectoryInfo クラスを使用して、ファイルとフォルダーをコピー、削除、および移動する方法について説明します。
ms.date: 07/20/2015
helpviewer_keywords:
- I/O [C#]
ms.assetid: 62e52cd7-9597-4e4a-acf9-1315f5cdbf05
ms.openlocfilehash: 208502651080f4fd614e34d1bf5b088dfb1207a6
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/28/2020
ms.locfileid: "87303362"
---
# <a name="how-to-copy-delete-and-move-files-and-folders-c-programming-guide"></a><span data-ttu-id="42f81-103">ファイルおよびフォルダーをコピー、削除、および移動する方法 (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="42f81-103">How to copy, delete, and move files and folders (C# Programming Guide)</span></span>
<span data-ttu-id="42f81-104">次の例では、<xref:System.IO?displayProperty=nameWithType> 名前空間から <xref:System.IO.File?displayProperty=nameWithType>、<xref:System.IO.Directory?displayProperty=nameWithType>、<xref:System.IO.FileInfo?displayProperty=nameWithType>、および <xref:System.IO.DirectoryInfo?displayProperty=nameWithType> クラスを使用して、同期的な方法でファイルとフォルダーをコピー、移動および削除する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="42f81-104">The following examples show how to copy, move, and delete files and folders in a synchronous manner by using the <xref:System.IO.File?displayProperty=nameWithType>, <xref:System.IO.Directory?displayProperty=nameWithType>, <xref:System.IO.FileInfo?displayProperty=nameWithType>, and <xref:System.IO.DirectoryInfo?displayProperty=nameWithType> classes from the <xref:System.IO?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="42f81-105">これらの例では、進行状況バーやその他のユーザー インターフェイスは表示されません。</span><span class="sxs-lookup"><span data-stu-id="42f81-105">These examples do not provide a progress bar or any other user interface.</span></span> <span data-ttu-id="42f81-106">標準の進行状況ダイアログ ボックスを表示する場合は、「[ファイル操作の [進行状況] ダイアログ ボックスを表示する方法](how-to-provide-a-progress-dialog-box-for-file-operations.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="42f81-106">If you want to provide a standard progress dialog box, see [How to provide a progress dialog box for file operations](how-to-provide-a-progress-dialog-box-for-file-operations.md).</span></span>  
  
 <span data-ttu-id="42f81-107">複数のファイルを操作するときに進行状況を計算できるイベントを提供するには、<xref:System.IO.FileSystemWatcher?displayProperty=nameWithType> を使用します。</span><span class="sxs-lookup"><span data-stu-id="42f81-107">Use <xref:System.IO.FileSystemWatcher?displayProperty=nameWithType> to provide events that will enable you to calculate the progress when operating on multiple files.</span></span> <span data-ttu-id="42f81-108">プラットフォーム呼び出しを使用して、Windows シェルで関連するファイル関連メソッドを呼び出す方法もあります。</span><span class="sxs-lookup"><span data-stu-id="42f81-108">Another approach is to use platform invoke to call the relevant file-related methods in the Windows Shell.</span></span> <span data-ttu-id="42f81-109">これらのファイル操作を非同期に実行する方法については、「[非同期ファイル I/O](../../../standard/io/asynchronous-file-i-o.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="42f81-109">For information about how to perform these file operations asynchronously, see [Asynchronous File I/O](../../../standard/io/asynchronous-file-i-o.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="42f81-110">例</span><span class="sxs-lookup"><span data-stu-id="42f81-110">Example</span></span>  
 <span data-ttu-id="42f81-111">次の例では、ファイルとディレクトリをコピーする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="42f81-111">The following example shows how to copy files and directories.</span></span>  
  
 [!code-csharp[csFilesandFolders#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csFilesAndFolders/CS/FileIteration.cs#7)]  
  
## <a name="example"></a><span data-ttu-id="42f81-112">例</span><span class="sxs-lookup"><span data-stu-id="42f81-112">Example</span></span>  
 <span data-ttu-id="42f81-113">次の例では、ファイルとディレクトリを移動する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="42f81-113">The following example shows how to move files and directories.</span></span>  
  
 [!code-csharp[csFilesandFolders#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csFilesAndFolders/CS/FileIteration.cs#8)]  
  
## <a name="example"></a><span data-ttu-id="42f81-114">例</span><span class="sxs-lookup"><span data-stu-id="42f81-114">Example</span></span>  
 <span data-ttu-id="42f81-115">次の例では、ファイルとディレクトリを削除する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="42f81-115">The following example shows how to delete files and directories.</span></span>  
  
 [!code-csharp[csFilesandFolders#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csFilesAndFolders/CS/FileIteration.cs#9)]  
  
## <a name="see-also"></a><span data-ttu-id="42f81-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="42f81-116">See also</span></span>

- <xref:System.IO?displayProperty=nameWithType>
- [<span data-ttu-id="42f81-117">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="42f81-117">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="42f81-118">ファイル システムとレジストリ (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="42f81-118">File System and the Registry (C# Programming Guide)</span></span>](index.md)
- <span data-ttu-id="42f81-119">[ファイル操作の [進行状況] ダイアログ ボックスを表示する方法](how-to-provide-a-progress-dialog-box-for-file-operations.md)</span><span class="sxs-lookup"><span data-stu-id="42f81-119">[How to provide a progress dialog box for file operations](how-to-provide-a-progress-dialog-box-for-file-operations.md)</span></span>
- [<span data-ttu-id="42f81-120">ファイルおよびストリーム入出力</span><span class="sxs-lookup"><span data-stu-id="42f81-120">File and Stream I/O</span></span>](../../../standard/io/index.md)
- [<span data-ttu-id="42f81-121">共通 I/O タスク</span><span class="sxs-lookup"><span data-stu-id="42f81-121">Common I/O Tasks</span></span>](../../../standard/io/common-i-o-tasks.md)
