---
title: '方法: ディレクトリをコピーする'
ms.date: 12/27/2018
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- directory copying
- I/O [.NET Framework], copying directories
- subdirectory copying
- copying directories
- directories [.NET Framework], copying
ms.assetid: 5a969765-e5f8-4b4e-977e-90e2b0a1fe3c
ms.openlocfilehash: 223e83a5ff6a73825985ec4e3b6b601fb196fe5e
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/07/2020
ms.locfileid: "75707901"
---
# <a name="how-to-copy-directories"></a><span data-ttu-id="9dc9d-102">方法: ディレクトリをコピーする</span><span class="sxs-lookup"><span data-stu-id="9dc9d-102">How to: Copy directories</span></span>
<span data-ttu-id="9dc9d-103">このトピックでは、I/O クラスを使用して、別の場所にディレクトリの内容を同期的にコピーする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="9dc9d-103">This topic demonstrates how to use I/O classes to synchronously copy the contents of a directory to another location.</span></span> 

<span data-ttu-id="9dc9d-104">ファイルを非同期的にコピーする例については、「[非同期ファイル I/O](../../../docs/standard/io/asynchronous-file-i-o.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9dc9d-104">For an example of asynchronous file copy, see [Asynchronous file I/O](../../../docs/standard/io/asynchronous-file-i-o.md).</span></span> 

<span data-ttu-id="9dc9d-105">この例では、`DirectoryCopy` メソッドの `copySubDirs` を `true` に設定することでサブディレクトリをコピーします。</span><span class="sxs-lookup"><span data-stu-id="9dc9d-105">This example copies subdirectories by setting the `copySubDirs` of the `DirectoryCopy` method to `true`.</span></span> <span data-ttu-id="9dc9d-106">`DirectoryCopy` メソッドは各サブディレクトリでそれ自体を呼び出すことで、コピーするサブディレクトリがなくなるまでサブディレクトリを再帰的にコピーします。</span><span class="sxs-lookup"><span data-stu-id="9dc9d-106">The `DirectoryCopy` method recursively copies subdirectories by calling itself on each subdirectory until there are no more to copy.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9dc9d-107">例</span><span class="sxs-lookup"><span data-stu-id="9dc9d-107">Example</span></span>  
 [!code-csharp[System.IO.Directory_Copy#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.Directory_Copy/cs/program.cs#1)]
 [!code-vb[System.IO.Directory_Copy#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.Directory_Copy/vb/Program.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="9dc9d-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="9dc9d-108">See also</span></span>

- <xref:System.IO.FileInfo>
- <xref:System.IO.DirectoryInfo>
- <xref:System.IO.FileStream>
- [<span data-ttu-id="9dc9d-109">ファイルおよびストリーム入出力</span><span class="sxs-lookup"><span data-stu-id="9dc9d-109">File and stream I/O</span></span>](../../../docs/standard/io/index.md)
- [<span data-ttu-id="9dc9d-110">共通 I/O タスク</span><span class="sxs-lookup"><span data-stu-id="9dc9d-110">Common I/O tasks</span></span>](../../../docs/standard/io/common-i-o-tasks.md)
- [<span data-ttu-id="9dc9d-111">非同期ファイル I/O</span><span class="sxs-lookup"><span data-stu-id="9dc9d-111">Asynchronous file I/O</span></span>](../../../docs/standard/io/asynchronous-file-i-o.md)
