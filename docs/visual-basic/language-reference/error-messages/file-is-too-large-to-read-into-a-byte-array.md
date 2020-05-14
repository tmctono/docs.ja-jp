---
title: バイト配列に読み取るにはファイルが大きすぎます。
ms.date: 07/20/2015
ms.assetid: 686630a6-a439-46c7-8d7b-34613ae4c5d8
ms.openlocfilehash: a842205e9184355e4ea750ea2eb32e4bcf05a14d
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64665104"
---
# <a name="file-is-too-large-to-read-into-a-byte-array"></a><span data-ttu-id="f9412-102">バイト配列に読み取るにはファイルが大きすぎます。</span><span class="sxs-lookup"><span data-stu-id="f9412-102">File is too large to read into a byte array</span></span>
<span data-ttu-id="f9412-103">バイト配列に読み取ろうとしているファイルのサイズが 4 GB を超えています。</span><span class="sxs-lookup"><span data-stu-id="f9412-103">The size of the file you are attempting to read into a byte array exceeds 4 GB.</span></span> <span data-ttu-id="f9412-104">`My.Computer.FileSystem.ReadAllBytes` メソッドは、このサイズを超えるファイルを読み取ることができません。</span><span class="sxs-lookup"><span data-stu-id="f9412-104">The `My.Computer.FileSystem.ReadAllBytes` method cannot read a file that exceeds this size.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="f9412-105">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="f9412-105">To correct this error</span></span>  
  
- <span data-ttu-id="f9412-106"><xref:System.IO.StreamReader> を使用してファイルを読み取ります。</span><span class="sxs-lookup"><span data-stu-id="f9412-106">Use a <xref:System.IO.StreamReader> to read the file.</span></span> <span data-ttu-id="f9412-107">詳細については、「[.NET Framework のファイル I/O とファイル システムの基礎 (Visual Basic)](../../../visual-basic/developing-apps/programming/drives-directories-files/basics-of-net-framework-file-io-and-the-file-system.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f9412-107">For more information, see [Basics of .NET Framework File I/O and the File System (Visual Basic)](../../../visual-basic/developing-apps/programming/drives-directories-files/basics-of-net-framework-file-io-and-the-file-system.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9412-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="f9412-108">See also</span></span>

- <xref:Microsoft.VisualBasic.FileIO.FileSystem.ReadAllBytes%2A>
- <xref:System.IO.StreamReader>
- [<span data-ttu-id="f9412-109">Visual Basic におけるファイル アクセス</span><span class="sxs-lookup"><span data-stu-id="f9412-109">File Access with Visual Basic</span></span>](../../../visual-basic/developing-apps/programming/drives-directories-files/file-access.md)
- [<span data-ttu-id="f9412-110">方法: StreamReader を使用してファイルからテキストを読み取る</span><span class="sxs-lookup"><span data-stu-id="f9412-110">How to: Read Text from Files with a StreamReader</span></span>](../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-text-from-files-with-a-streamreader.md)
