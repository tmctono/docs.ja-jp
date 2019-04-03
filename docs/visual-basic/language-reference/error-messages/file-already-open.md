---
title: ファイルは既に開かれています。
ms.date: 07/20/2015
f1_keywords:
- vbrID55
ms.assetid: d674a0fb-ef16-4cc2-9da7-709a8a07dbea
ms.openlocfilehash: e565dbd6352a8f76290f3f58d62e2e14a18ef45f
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/02/2019
ms.locfileid: "58823507"
---
# <a name="file-already-open"></a><span data-ttu-id="b2b7d-102">ファイルは既に開かれています。</span><span class="sxs-lookup"><span data-stu-id="b2b7d-102">File already open</span></span>
<span data-ttu-id="b2b7d-103">前に、別のファイルを閉じる必要が場合があります`FileOpen`または他の操作が発生することができます。</span><span class="sxs-lookup"><span data-stu-id="b2b7d-103">Sometimes a file must be closed before another `FileOpen` or other operation can occur.</span></span> <span data-ttu-id="b2b7d-104">このエラーでは以下の原因が考えられます。</span><span class="sxs-lookup"><span data-stu-id="b2b7d-104">Among the possible causes of this error are:</span></span>  
  
-   <span data-ttu-id="b2b7d-105">シーケンシャル出力モード`FileOpen`操作が既に開いているファイルに対して実行されました。</span><span class="sxs-lookup"><span data-stu-id="b2b7d-105">A sequential output mode `FileOpen` operation was executed for a file that is already open</span></span>  
  
-   <span data-ttu-id="b2b7d-106">ステートメントは、開くファイルを指します。</span><span class="sxs-lookup"><span data-stu-id="b2b7d-106">A statement refers to an open file.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="b2b7d-107">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="b2b7d-107">To correct this error</span></span>  
  
1.  <span data-ttu-id="b2b7d-108">ステートメントを実行する前に、ファイルを閉じます。</span><span class="sxs-lookup"><span data-stu-id="b2b7d-108">Close the file before executing the statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2b7d-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="b2b7d-109">See also</span></span>

- <xref:Microsoft.VisualBasic.FileSystem.FileOpen%2A>
