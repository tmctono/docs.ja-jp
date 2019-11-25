---
title: '方法: My Documents ディレクトリの内容を取得する'
ms.date: 07/20/2015
helpviewer_keywords:
- My Documents directory
ms.assetid: 26560d01-7dda-4457-8e95-21db23d71aea
ms.openlocfilehash: cf4470020507c581999b9d72602ddb6e3e76ed74
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74334536"
---
# <a name="how-to-retrieve-the-contents-of-the-my-documents-directory-in-visual-basic"></a><span data-ttu-id="3a8cf-102">方法: My Documents ディレクトリの内容を取得する (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3a8cf-102">How to: Retrieve the Contents of the My Documents Directory in Visual Basic</span></span>

<span data-ttu-id="3a8cf-103"><xref:Microsoft.VisualBasic.FileIO.SpecialDirectories> オブジェクトを使用すると、**My Documents** や **Desktop** など、多くの **All Users** ディレクトリを読み取ることができます。</span><span class="sxs-lookup"><span data-stu-id="3a8cf-103">The <xref:Microsoft.VisualBasic.FileIO.SpecialDirectories> object can be used to read from many of the **All Users** directories, such as **My Documents** or **Desktop**.</span></span>  
  
### <a name="to-read-from-the-my-documents-folder"></a><span data-ttu-id="3a8cf-104">My Documents フォルダーを読み取るには</span><span class="sxs-lookup"><span data-stu-id="3a8cf-104">To read from the My Documents folder</span></span>  
  
- <span data-ttu-id="3a8cf-105">`ReadAllText` メソッドを使用して、指定したディレクトリの各ファイルからテキストを読み取ります。</span><span class="sxs-lookup"><span data-stu-id="3a8cf-105">Use the `ReadAllText` method to read the text from each file in a specific directory.</span></span> <span data-ttu-id="3a8cf-106">次のコードでは、ディレクトリとファイルを指定し、`ReadAllText` を使用して、`patients` という名前の文字列に読み取ります。</span><span class="sxs-lookup"><span data-stu-id="3a8cf-106">The following code specifies a directory and file and then uses `ReadAllText` to read them into the string named `patients`.</span></span>  
  
     [!code-vb[VbVbcnMyFileSystem#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#15)]  
  
## <a name="see-also"></a><span data-ttu-id="3a8cf-107">関連項目</span><span class="sxs-lookup"><span data-stu-id="3a8cf-107">See also</span></span>

- <xref:Microsoft.VisualBasic.FileIO.SpecialDirectories>
- <xref:Microsoft.VisualBasic.FileIO.FileSystem.ReadAllText%2A>
