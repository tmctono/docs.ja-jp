---
title: ファイルにこれ以上データがありません。
ms.date: 07/20/2015
f1_keywords:
- vbrID62
ms.assetid: 65292704-6e7d-4622-9f50-eb655a59b016
ms.openlocfilehash: c0cb0373fb0652e9600ac8651661708414561aca
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "90873961"
---
# <a name="input-past-end-of-file"></a><span data-ttu-id="19c12-102">ファイルにこれ以上データがありません。</span><span class="sxs-lookup"><span data-stu-id="19c12-102">Input past end of file</span></span>

<span data-ttu-id="19c12-103">`Input` ステートメントが空のファイル、またはすべてのデータが使用されているファイルから読み取っているか、またはバイナリ アクセス用に開かれたファイルで `EOF` 関数を使用しました。</span><span class="sxs-lookup"><span data-stu-id="19c12-103">Either an `Input` statement is reading from a file that is empty or one in which all the data is used, or you used the `EOF` function with a file opened for binary access.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="19c12-104">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="19c12-104">To correct this error</span></span>  
  
1. <span data-ttu-id="19c12-105">`Input` ステートメントの直前で `EOF` 関数を使用して、ファイルの末尾を検出します。</span><span class="sxs-lookup"><span data-stu-id="19c12-105">Use the `EOF` function immediately before the `Input` statement to detect the end of the file.</span></span>  
  
2. <span data-ttu-id="19c12-106">ファイルがバイナリ アクセス用に開かれている場合は、`Seek` と `Loc` を使用します。</span><span class="sxs-lookup"><span data-stu-id="19c12-106">If the file is opened for binary access, use `Seek` and `Loc`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19c12-107">関連項目</span><span class="sxs-lookup"><span data-stu-id="19c12-107">See also</span></span>

- <xref:Microsoft.VisualBasic.FileSystem.Input%2A>
- <xref:Microsoft.VisualBasic.FileSystem.EOF%2A>
- <xref:Microsoft.VisualBasic.FileSystem.Seek%2A>
- <xref:Microsoft.VisualBasic.FileSystem.Loc%2A>
