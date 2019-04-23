---
title: ファイル名または番号が正しくありません。
ms.date: 07/20/2015
f1_keywords:
- vbrID52
ms.assetid: d0e96aea-7621-48f6-a78b-5d37d18aaa4e
ms.openlocfilehash: 2e5d4a3ddd66df85dc4758e22b36ac1ed495659a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59322161"
---
# <a name="bad-file-name-or-number"></a><span data-ttu-id="37057-102">ファイル名または番号が正しくありません。</span><span class="sxs-lookup"><span data-stu-id="37057-102">Bad file name or number</span></span>
<span data-ttu-id="37057-103">指定したファイルにアクセスしているときにエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="37057-103">An error occurred while trying to access the specified file.</span></span> <span data-ttu-id="37057-104">このエラーの考えられる原因には。</span><span class="sxs-lookup"><span data-stu-id="37057-104">Among the possible causes for this error are:</span></span>  
  
-   <span data-ttu-id="37057-105">ステートメントで指定されていないファイルの名前または番号のファイルを参照して、`FileOpen`で指定されたステートメントまたはを`FileOpen`ステートメントは、その後が終了します。</span><span class="sxs-lookup"><span data-stu-id="37057-105">A statement refers to a file with a file name or number that was not specified in the `FileOpen` statement or that was specified in a `FileOpen` statement but was subsequently closed.</span></span>  
  
-   <span data-ttu-id="37057-106">ステートメントは、ファイル番号の範囲外にある数値を持つファイルを参照します。</span><span class="sxs-lookup"><span data-stu-id="37057-106">A statement refers to a file with a number that is out of the range of file numbers.</span></span>  
  
-   <span data-ttu-id="37057-107">ステートメントを指すファイルの名前または番号が無効です。</span><span class="sxs-lookup"><span data-stu-id="37057-107">A statement refers to a file name or number that is not valid.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="37057-108">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="37057-108">To correct this error</span></span>  
  
1. <span data-ttu-id="37057-109">ファイル名がで指定されたことを確認、`FileOpen`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="37057-109">Make sure the file name is specified in a `FileOpen` statement.</span></span> <span data-ttu-id="37057-110">呼び出した場合、`FileClose`ステートメント引数を指定せず可能性がありますが誤って閉じたすべての開いているファイル。</span><span class="sxs-lookup"><span data-stu-id="37057-110">Note that if you invoked the `FileClose` statement without arguments, you may have inadvertently closed all open files.</span></span>  
  
2. <span data-ttu-id="37057-111">場合は、コードの生成は、ファイルの番号にアルゴリズムが、番号は有効なことを確認します。</span><span class="sxs-lookup"><span data-stu-id="37057-111">If your code is generating file numbers algorithmically, make sure the numbers are valid.</span></span>  
  
3. <span data-ttu-id="37057-112">オペレーティング システムの規約に準拠しているかどうかを確認するファイル名を確認します。</span><span class="sxs-lookup"><span data-stu-id="37057-112">Check the file names to make sure they conform to operating system conventions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37057-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="37057-113">See also</span></span>

- <xref:Microsoft.VisualBasic.FileSystem.FileOpen%2A>
- [<span data-ttu-id="37057-114">Visual Basic の名前付け規則</span><span class="sxs-lookup"><span data-stu-id="37057-114">Visual Basic Naming Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)
