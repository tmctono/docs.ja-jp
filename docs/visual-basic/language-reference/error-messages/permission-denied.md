---
title: アクセス許可は拒否されました。(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vbrID70
ms.assetid: 71f46756-f522-4814-aab4-492bf9924245
ms.openlocfilehash: ad75c556748bf5c0f9cef55310c4ffa7b01fd458
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59318833"
---
# <a name="permission-denied-visual-basic"></a><span data-ttu-id="7e583-102">アクセス許可は拒否されました。(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7e583-102">Permission denied (Visual Basic)</span></span>
<span data-ttu-id="7e583-103">しようとは、書き込み保護されているディスクに書き込む、またはロックされたファイルにアクセスしました。</span><span class="sxs-lookup"><span data-stu-id="7e583-103">An attempt was made to write to a write-protected disk or to access a locked file.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="7e583-104">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="7e583-104">To correct this error</span></span>  
  
1. <span data-ttu-id="7e583-105">書き込みで保護されたファイルを開くには、ファイルの書き込み保護属性を変更します。</span><span class="sxs-lookup"><span data-stu-id="7e583-105">To open a write-protected file, change the write-protection attribute of the file.</span></span>  
  
2. <span data-ttu-id="7e583-106">別のプロセスでは、ファイルがロックされないことを確認し、ファイルを開き、他のプロセスでは、それを解放するまでに待機します。</span><span class="sxs-lookup"><span data-stu-id="7e583-106">Make sure that another process has not locked the file, and wait to open the file until the other process releases it.</span></span>  
  
3. <span data-ttu-id="7e583-107">レジストリにアクセスするには、ユーザーのアクセス許可がこの種類のレジストリのアクセスを含めることを確認します。</span><span class="sxs-lookup"><span data-stu-id="7e583-107">To access the registry, check that your user permissions include this type of registry access.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e583-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="7e583-108">See also</span></span>

- [<span data-ttu-id="7e583-109">エラーの種類</span><span class="sxs-lookup"><span data-stu-id="7e583-109">Error Types</span></span>](../../../visual-basic/programming-guide/language-features/error-types.md)
