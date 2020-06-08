---
title: 必要な一時ファイルを作成できません。
ms.date: 07/20/2015
f1_keywords:
- vbrID322
ms.assetid: 53617b5b-eb06-4188-b4c2-8607cb9fbc79
ms.openlocfilehash: 1a1464e0ac0d87bf9763efe63f2e09927a157a24
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2020
ms.locfileid: "84415428"
---
# <a name="cant-create-necessary-temporary-file"></a><span data-ttu-id="c4007-102">必要な一時ファイルを作成できません。</span><span class="sxs-lookup"><span data-stu-id="c4007-102">Can't create necessary temporary file</span></span>
<span data-ttu-id="c4007-103">TEMP 環境変数によって指定されたディレクトリを含むドライブがいっぱいになっているか、TEMP 環境変数が無効または読み取り専用のドライブまたはディレクトリを指定しています。</span><span class="sxs-lookup"><span data-stu-id="c4007-103">Either the drive is full that contains the directory specified by the TEMP environment variable, or the TEMP environment variable specifies an invalid or read-only drive or directory.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="c4007-104">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="c4007-104">To correct this error</span></span>  
  
1. <span data-ttu-id="c4007-105">いっぱいになっている場合は、ドライブからファイルを削除します。</span><span class="sxs-lookup"><span data-stu-id="c4007-105">Delete files from the drive, if full.</span></span>  
  
2. <span data-ttu-id="c4007-106">TEMP 環境変数に別のドライブを指定します。</span><span class="sxs-lookup"><span data-stu-id="c4007-106">Specify a different drive in the TEMP environment variable.</span></span>  
  
3. <span data-ttu-id="c4007-107">TEMP 環境変数に有効なドライブを指定します。</span><span class="sxs-lookup"><span data-stu-id="c4007-107">Specify a valid drive for the TEMP environment variable.</span></span>  
  
4. <span data-ttu-id="c4007-108">現在指定されているドライブまたはディレクトリから読み取り専用の制限を削除します。</span><span class="sxs-lookup"><span data-stu-id="c4007-108">Remove the read-only restriction from the currently specified drive or directory.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4007-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="c4007-109">See also</span></span>

- [<span data-ttu-id="c4007-110">エラーの種類</span><span class="sxs-lookup"><span data-stu-id="c4007-110">Error Types</span></span>](../../programming-guide/language-features/error-types.md)
