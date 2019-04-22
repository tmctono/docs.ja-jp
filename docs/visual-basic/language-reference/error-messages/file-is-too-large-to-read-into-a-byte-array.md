---
title: バイト配列に読み取るにはファイルが大きすぎます。
ms.date: 07/20/2015
ms.assetid: 686630a6-a439-46c7-8d7b-34613ae4c5d8
ms.openlocfilehash: 0c7d35e08eeb42e35c4c40e47434a64393d829b1
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "58831515"
---
# <a name="file-is-too-large-to-read-into-a-byte-array"></a><span data-ttu-id="1d6ff-102">バイト配列に読み取るにはファイルが大きすぎます。</span><span class="sxs-lookup"><span data-stu-id="1d6ff-102">File is too large to read into a byte array</span></span>
<span data-ttu-id="1d6ff-103">バイト配列に読み取るしようとするファイルのサイズが 4 GB を超えています。</span><span class="sxs-lookup"><span data-stu-id="1d6ff-103">The size of the file you are attempting to read into a byte array exceeds 4 GB.</span></span> <span data-ttu-id="1d6ff-104">`My.Computer.FileSystem.ReadAllBytes`メソッドは、このサイズを超えるファイルを読み取ることができません。</span><span class="sxs-lookup"><span data-stu-id="1d6ff-104">The `My.Computer.FileSystem.ReadAllBytes` method cannot read a file that exceeds this size.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="1d6ff-105">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="1d6ff-105">To correct this error</span></span>  
  
-   <span data-ttu-id="1d6ff-106">使用して、<xref:System.IO.StreamReader>ファイルを読み取れません。</span><span class="sxs-lookup"><span data-stu-id="1d6ff-106">Use a <xref:System.IO.StreamReader> to read the file.</span></span> <span data-ttu-id="1d6ff-107">詳細については、次を参照してください。 [.NET Framework ファイル I/O の基礎と、ファイル システム (Visual Basic)](../../../visual-basic/developing-apps/programming/drives-directories-files/basics-of-net-framework-file-io-and-the-file-system.md)します。</span><span class="sxs-lookup"><span data-stu-id="1d6ff-107">For more information, see [Basics of .NET Framework File I/O and the File System (Visual Basic)](../../../visual-basic/developing-apps/programming/drives-directories-files/basics-of-net-framework-file-io-and-the-file-system.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d6ff-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="1d6ff-108">See also</span></span>

- <xref:Microsoft.VisualBasic.FileIO.FileSystem.ReadAllBytes%2A>
- <xref:System.IO.StreamReader>
- [<span data-ttu-id="1d6ff-109">Visual Basic におけるファイル アクセス</span><span class="sxs-lookup"><span data-stu-id="1d6ff-109">File Access with Visual Basic</span></span>](../../../visual-basic/developing-apps/programming/drives-directories-files/file-access.md)
- [<span data-ttu-id="1d6ff-110">方法: StreamReader を使用してファイルからテキストを読み取る</span><span class="sxs-lookup"><span data-stu-id="1d6ff-110">How to: Read Text from Files with a StreamReader</span></span>](../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-text-from-files-with-a-streamreader.md)
