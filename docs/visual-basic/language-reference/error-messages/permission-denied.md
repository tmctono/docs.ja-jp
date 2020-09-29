---
title: アクセス許可は拒否されました
ms.date: 07/20/2015
f1_keywords:
- vbrID70
ms.assetid: 71f46756-f522-4814-aab4-492bf9924245
ms.openlocfilehash: 5ac585a86a783f36642545e368b1c2e694b89f62
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "90871165"
---
# <a name="permission-denied-visual-basic"></a><span data-ttu-id="9a636-102">アクセス許可は拒否されました。(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9a636-102">Permission denied (Visual Basic)</span></span>

<span data-ttu-id="9a636-103">書き込み禁止ディスクに書き込もうとしたか、ロックされたファイルにアクセスしようとしました。</span><span class="sxs-lookup"><span data-stu-id="9a636-103">An attempt was made to write to a write-protected disk or to access a locked file.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="9a636-104">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="9a636-104">To correct this error</span></span>  
  
1. <span data-ttu-id="9a636-105">書き込み禁止ファイルを開くには、ファイルの書き込み保護属性を変更します。</span><span class="sxs-lookup"><span data-stu-id="9a636-105">To open a write-protected file, change the write-protection attribute of the file.</span></span>  
  
2. <span data-ttu-id="9a636-106">別のプロセスによってファイルがロックされていないことを確認し、他のプロセスによってファイルが解放されるまで待機します。</span><span class="sxs-lookup"><span data-stu-id="9a636-106">Make sure that another process has not locked the file, and wait to open the file until the other process releases it.</span></span>  
  
3. <span data-ttu-id="9a636-107">レジストリにアクセスするには、ユーザーのアクセス許可にこの種類のレジストリ アクセスが含まれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="9a636-107">To access the registry, check that your user permissions include this type of registry access.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a636-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="9a636-108">See also</span></span>

- [<span data-ttu-id="9a636-109">エラーの種類</span><span class="sxs-lookup"><span data-stu-id="9a636-109">Error Types</span></span>](../../programming-guide/language-features/error-types.md)
