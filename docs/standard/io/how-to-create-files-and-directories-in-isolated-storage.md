---
title: '方法 : 分離ストレージでファイルおよびディレクトリを作成する'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- directories [.NET Framework], isolated storage
- files [.NET Framework], isolated storage
- isolated storage, creating files and directories
- data stores, creating files and directories
- data storage using isolated storage, creating files and directories
- stores, creating files and directories
- storing data using isolated storage, creating files and directories
ms.assetid: 2ca4d2a4-809b-4f00-bc08-bf4a64d3a5c3
ms.openlocfilehash: 83e8c800dc74d9689f1bfdb506a6b454e87b36ca
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/15/2020
ms.locfileid: "75707871"
---
# <a name="how-to-create-files-and-directories-in-isolated-storage"></a><span data-ttu-id="f1271-102">方法 : 分離ストレージでファイルおよびディレクトリを作成する</span><span class="sxs-lookup"><span data-stu-id="f1271-102">How to: Create Files and Directories in Isolated Storage</span></span>
<span data-ttu-id="f1271-103">分離ストアを取得したら、データを格納するためのファイルとディレクトリを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="f1271-103">After you have obtained an isolated store, you can create directories and files for storing data.</span></span> <span data-ttu-id="f1271-104">ストア内では、ファイル名とディレクトリ名は仮想ファイル システムのルートに対して指定されます。</span><span class="sxs-lookup"><span data-stu-id="f1271-104">Within a store, file and directory names are specified with respect to the root of the virtual file system.</span></span>  
  
 <span data-ttu-id="f1271-105">ディレクトリを作成するには、<xref:System.IO.IsolatedStorage.IsolatedStorageFile.CreateDirectory%2A?displayProperty=nameWithType> インスタンス メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="f1271-105">To create a directory, use the <xref:System.IO.IsolatedStorage.IsolatedStorageFile.CreateDirectory%2A?displayProperty=nameWithType> instance method.</span></span> <span data-ttu-id="f1271-106">存在しないディレクトリのサブディレクトリを指定した場合、両方のディレクトリが作成されます。</span><span class="sxs-lookup"><span data-stu-id="f1271-106">If you specify a subdirectory of an directory that doesn't exist, both directories are created.</span></span> <span data-ttu-id="f1271-107">既に存在するディレクトリを指定した場合、メソッドはディレクトリを作成せずに制御を返し、例外はスローされません。</span><span class="sxs-lookup"><span data-stu-id="f1271-107">If you specify a directory that already exists, the method returns without creating a directory, and no exception is thrown.</span></span> <span data-ttu-id="f1271-108">ただし、無効な文字を含むディレクトリ名を指定した場合、<xref:System.IO.IsolatedStorage.IsolatedStorageException> 例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="f1271-108">However, if you specify a directory name that contains invalid characters, an <xref:System.IO.IsolatedStorage.IsolatedStorageException> exception is thrown.</span></span>  
  
 <span data-ttu-id="f1271-109">ファイルを作成するには、<xref:System.IO.IsolatedStorage.IsolatedStorageFile.CreateFile%2A?displayProperty=nameWithType> メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="f1271-109">To create a file, use  the <xref:System.IO.IsolatedStorage.IsolatedStorageFile.CreateFile%2A?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="f1271-110">Windows オペレーティング システムでは、分離ストレージ ファイルおよびディレクトリの名前の大文字と小文字は区別されません。</span><span class="sxs-lookup"><span data-stu-id="f1271-110">In the Windows operating system, isolated storage file and directory names are case-insensitive.</span></span> <span data-ttu-id="f1271-111">つまり、`ThisFile.txt` という名前のファイルを作成してから `THISFILE.TXT` という名前の別のファイルを作成した場合、作成されるのは 1 つのファイルのみです。</span><span class="sxs-lookup"><span data-stu-id="f1271-111">That is, if you create a file named `ThisFile.txt`, and then create another file named `THISFILE.TXT`, only one file is created.</span></span> <span data-ttu-id="f1271-112">ファイル名では、表示目的で元の大文字と小文字の区別が保持されます。</span><span class="sxs-lookup"><span data-stu-id="f1271-112">The file name keeps its original casing for display purposes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f1271-113">例</span><span class="sxs-lookup"><span data-stu-id="f1271-113">Example</span></span>  
 <span data-ttu-id="f1271-114">分離ストア内にファイルおよびディレクトリを作成する方法を次のコード例で示します。</span><span class="sxs-lookup"><span data-stu-id="f1271-114">The following code example illustrates how to create files and directories in an isolated store.</span></span>  
  
 [!code-csharp[Conceptual.IsolatedStorage#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source.cs#1)]
 [!code-vb[Conceptual.IsolatedStorage#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="f1271-115">参照</span><span class="sxs-lookup"><span data-stu-id="f1271-115">See also</span></span>

- <xref:System.IO.IsolatedStorage.IsolatedStorageFile>
- <xref:System.IO.IsolatedStorage.IsolatedStorageFileStream>
- [<span data-ttu-id="f1271-116">分離ストレージ</span><span class="sxs-lookup"><span data-stu-id="f1271-116">Isolated Storage</span></span>](../../../docs/standard/io/isolated-storage.md)
