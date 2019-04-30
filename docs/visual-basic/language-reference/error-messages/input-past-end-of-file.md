---
title: ファイルにこれ以上データがありません。
ms.date: 07/20/2015
f1_keywords:
- vbrID62
ms.assetid: 65292704-6e7d-4622-9f50-eb655a59b016
ms.openlocfilehash: 5da14c7a28ecdcd023fc6439cb6ed64444c1183b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62013791"
---
# <a name="input-past-end-of-file"></a><span data-ttu-id="1060e-102">ファイルにこれ以上データがありません。</span><span class="sxs-lookup"><span data-stu-id="1060e-102">Input past end of file</span></span>
<span data-ttu-id="1060e-103">いずれか、`Input`ステートメントは空であるファイルまたはすべてのデータを使用すると、またはを使用していずれかから読み取って、`EOF`バイナリへのアクセスのファイルを使用して関数を開きます。</span><span class="sxs-lookup"><span data-stu-id="1060e-103">Either an `Input` statement is reading from a file that is empty or one in which all the data is used, or you used the `EOF` function with a file opened for binary access.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="1060e-104">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="1060e-104">To correct this error</span></span>  
  
1. <span data-ttu-id="1060e-105">使用して、`EOF`する直前に機能、`Input`ステートメント ファイルの終わりを検出します。</span><span class="sxs-lookup"><span data-stu-id="1060e-105">Use the `EOF` function immediately before the `Input` statement to detect the end of the file.</span></span>  
  
2. <span data-ttu-id="1060e-106">バイナリ アクセスのため、ファイルを開く場合は、使用`Seek`と`Loc`します。</span><span class="sxs-lookup"><span data-stu-id="1060e-106">If the file is opened for binary access, use `Seek` and `Loc`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1060e-107">関連項目</span><span class="sxs-lookup"><span data-stu-id="1060e-107">See also</span></span>

- <xref:Microsoft.VisualBasic.FileSystem.Input%2A>
- <xref:Microsoft.VisualBasic.FileSystem.EOF%2A>
- <xref:Microsoft.VisualBasic.FileSystem.Seek%2A>
- <xref:Microsoft.VisualBasic.FileSystem.Loc%2A>
