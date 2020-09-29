---
title: "'<functionname>' は宣言されていません (スマート デバイスおよび Visual Basic コンパイラ エラー)"
ms.date: 07/20/2015
f1_keywords:
- bc30766
- vbc30766
helpviewer_keywords:
- BC30766
ms.assetid: 13918600-6087-40d7-8134-32aa9d3bfda4
ms.openlocfilehash: 5e0f6dd2da404ed988af15fadadd8ecd4a491189
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874059"
---
# <a name="functionname-is-not-declared-smart-devicevisual-basic-compiler-error"></a><span data-ttu-id="3fca0-102">'\<functionname>' は宣言されていません (スマート デバイスおよび Visual Basic コンパイラ エラー)</span><span class="sxs-lookup"><span data-stu-id="3fca0-102">'\<functionname>' is not declared (Smart Device/Visual Basic Compiler Error)</span></span>

<span data-ttu-id="3fca0-103"><`functionname`> が宣言されていません。</span><span class="sxs-lookup"><span data-stu-id="3fca0-103"><`functionname`> is not declared.</span></span> <span data-ttu-id="3fca0-104">通常、ファイル I/O 機能は `Microsoft.VisualBasic` 名前空間で使用できますが、.NET Compact Framework のターゲット バージョンではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="3fca0-104">File I/O functionality is normally available in the `Microsoft.VisualBasic` namespace, but the targeted version of the .NET Compact Framework does not support it.</span></span>  
  
 <span data-ttu-id="3fca0-105">**エラー ID:** BC30766</span><span class="sxs-lookup"><span data-stu-id="3fca0-105">**Error ID:** BC30766</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="3fca0-106">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="3fca0-106">To correct this error</span></span>  
  
- <span data-ttu-id="3fca0-107">`System.IO` 名前空間で定義された関数を使用して、ファイル操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="3fca0-107">Perform file operations with functions defined in the `System.IO` namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3fca0-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="3fca0-108">See also</span></span>

- <xref:System.IO>
- [<span data-ttu-id="3fca0-109">Visual Basic におけるファイル アクセス</span><span class="sxs-lookup"><span data-stu-id="3fca0-109">File Access with Visual Basic</span></span>](../../developing-apps/programming/drives-directories-files/file-access.md)
