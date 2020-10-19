---
title: ファイルは既に開かれています。
ms.date: 07/20/2015
f1_keywords:
- vbrID55
ms.assetid: d674a0fb-ef16-4cc2-9da7-709a8a07dbea
ms.openlocfilehash: ce8f8bf96d7355e45b2df82e8a131472c2ed2367
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "92162753"
---
# <a name="file-already-open"></a><span data-ttu-id="114c6-102">ファイルは既に開かれています。</span><span class="sxs-lookup"><span data-stu-id="114c6-102">File already open</span></span>

<span data-ttu-id="114c6-103">別の `FileOpen` またはその他の操作を実行する前に、ファイルを閉じる必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="114c6-103">Sometimes a file must be closed before another `FileOpen` or other operation can occur.</span></span> <span data-ttu-id="114c6-104">このエラーでは以下の原因が考えられます。</span><span class="sxs-lookup"><span data-stu-id="114c6-104">Among the possible causes of this error are:</span></span>

- <span data-ttu-id="114c6-105">既に開いているファイルに対して順次出力モードの `FileOpen` 操作が実行されました</span><span class="sxs-lookup"><span data-stu-id="114c6-105">A sequential output mode `FileOpen` operation was executed for a file that is already open</span></span>

- <span data-ttu-id="114c6-106">ステートメントが開いているファイルを参照しています。</span><span class="sxs-lookup"><span data-stu-id="114c6-106">A statement refers to an open file.</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="114c6-107">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="114c6-107">To correct this error</span></span>

- <span data-ttu-id="114c6-108">ステートメントを実行する前に、ファイルを閉じます。</span><span class="sxs-lookup"><span data-stu-id="114c6-108">Close the file before executing the statement.</span></span>

## <a name="see-also"></a><span data-ttu-id="114c6-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="114c6-109">See also</span></span>

- <xref:Microsoft.VisualBasic.FileSystem.FileOpen%2A>
