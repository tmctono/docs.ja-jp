---
title: ファイルは既に開かれています。
ms.date: 07/20/2015
f1_keywords:
- vbrID55
ms.assetid: d674a0fb-ef16-4cc2-9da7-709a8a07dbea
ms.openlocfilehash: 97f9e13e6802e793f7c7baf1f03ec51205eb6d42
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874167"
---
# <a name="file-already-open"></a><span data-ttu-id="9d503-102">ファイルは既に開かれています。</span><span class="sxs-lookup"><span data-stu-id="9d503-102">File already open</span></span>

<span data-ttu-id="9d503-103">別の `FileOpen` またはその他の操作を実行する前に、ファイルを閉じる必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="9d503-103">Sometimes a file must be closed before another `FileOpen` or other operation can occur.</span></span> <span data-ttu-id="9d503-104">このエラーでは以下の原因が考えられます。</span><span class="sxs-lookup"><span data-stu-id="9d503-104">Among the possible causes of this error are:</span></span>  
  
- <span data-ttu-id="9d503-105">既に開いているファイルに対して順次出力モードの `FileOpen` 操作が実行されました</span><span class="sxs-lookup"><span data-stu-id="9d503-105">A sequential output mode `FileOpen` operation was executed for a file that is already open</span></span>  
  
- <span data-ttu-id="9d503-106">ステートメントが開いているファイルを参照しています。</span><span class="sxs-lookup"><span data-stu-id="9d503-106">A statement refers to an open file.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="9d503-107">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="9d503-107">To correct this error</span></span>  
  
1. <span data-ttu-id="9d503-108">ステートメントを実行する前に、ファイルを閉じます。</span><span class="sxs-lookup"><span data-stu-id="9d503-108">Close the file before executing the statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d503-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="9d503-109">See also</span></span>

- <xref:Microsoft.VisualBasic.FileSystem.FileOpen%2A>
