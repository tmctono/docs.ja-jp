---
title: ファイル名または番号が正しくありません。
ms.date: 07/20/2015
f1_keywords:
- vbrID52
ms.assetid: d0e96aea-7621-48f6-a78b-5d37d18aaa4e
ms.openlocfilehash: 7a16e951030731bdcbb48b5fbb1a0d1881d5e1ec
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64619389"
---
# <a name="bad-file-name-or-number"></a><span data-ttu-id="c8f1f-102">ファイル名または番号が正しくありません。</span><span class="sxs-lookup"><span data-stu-id="c8f1f-102">Bad file name or number</span></span>
<span data-ttu-id="c8f1f-103">指定したファイルにアクセスしようとして、エラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="c8f1f-103">An error occurred while trying to access the specified file.</span></span> <span data-ttu-id="c8f1f-104">このエラーでは以下の原因が考えられます。</span><span class="sxs-lookup"><span data-stu-id="c8f1f-104">Among the possible causes for this error are:</span></span>  
  
- <span data-ttu-id="c8f1f-105">ステートメントで、`FileOpen` ステートメントに指定されていないファイル名または番号を使用してファイルを参照しているか、または `FileOpen` ステートメントにそれが指定されていても、その後閉じられました。</span><span class="sxs-lookup"><span data-stu-id="c8f1f-105">A statement refers to a file with a file name or number that was not specified in the `FileOpen` statement or that was specified in a `FileOpen` statement but was subsequently closed.</span></span>  
  
- <span data-ttu-id="c8f1f-106">ステートメントで、ファイル番号の範囲外の番号を使用してファイルを参照しています。</span><span class="sxs-lookup"><span data-stu-id="c8f1f-106">A statement refers to a file with a number that is out of the range of file numbers.</span></span>  
  
- <span data-ttu-id="c8f1f-107">ステートメントで、無効なファイル名または番号を参照しています。</span><span class="sxs-lookup"><span data-stu-id="c8f1f-107">A statement refers to a file name or number that is not valid.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="c8f1f-108">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="c8f1f-108">To correct this error</span></span>  
  
1. <span data-ttu-id="c8f1f-109">`FileOpen` ステートメントでファイル名が指定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="c8f1f-109">Make sure the file name is specified in a `FileOpen` statement.</span></span> <span data-ttu-id="c8f1f-110">引数を指定せずに `FileClose` ステートメントを呼び出した場合、開いているすべてのファイルが誤って閉じられた可能性があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="c8f1f-110">Note that if you invoked the `FileClose` statement without arguments, you may have inadvertently closed all open files.</span></span>  
  
2. <span data-ttu-id="c8f1f-111">コードでアルゴリズムによってファイル番号を生成している場合、番号が有効であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="c8f1f-111">If your code is generating file numbers algorithmically, make sure the numbers are valid.</span></span>  
  
3. <span data-ttu-id="c8f1f-112">ファイル名をチェックして、それらがオペレーティング システムの規則に従っていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="c8f1f-112">Check the file names to make sure they conform to operating system conventions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8f1f-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="c8f1f-113">See also</span></span>

- <xref:Microsoft.VisualBasic.FileSystem.FileOpen%2A>
- [<span data-ttu-id="c8f1f-114">Visual Basic の名前付け規則</span><span class="sxs-lookup"><span data-stu-id="c8f1f-114">Visual Basic Naming Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)
