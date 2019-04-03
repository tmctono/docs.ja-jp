---
title: ファイルが多すぎます。
ms.date: 07/20/2015
f1_keywords:
- vbrID67
ms.assetid: 2ff203e2-bba6-43ae-b72f-8e92a881c98f
ms.openlocfilehash: ceacb5d83fcfc9fcbd341cc5d9579c4e2e181353
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/02/2019
ms.locfileid: "58829890"
---
# <a name="too-many-files"></a><span data-ttu-id="bf8f1-102">ファイルが多すぎます。</span><span class="sxs-lookup"><span data-stu-id="bf8f1-102">Too many files</span></span>
<span data-ttu-id="bf8f1-103">指定された数よりも多くのファイルが開かれているまたは以上のファイルは、オペレーティング システムの制限よりも、ルート ディレクトリに作成されましたが、**ファイル =** の構成で設定します。SYS ファイルです。</span><span class="sxs-lookup"><span data-stu-id="bf8f1-103">Either more files have been created in the root directory than the operating system permits, or more files have been opened than the number specified in the **files=** setting in your CONFIG.SYS file.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="bf8f1-104">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="bf8f1-104">To correct this error</span></span>  
  
1.  <span data-ttu-id="bf8f1-105">プログラムが開く、閉じるか、ルート ディレクトリでファイルを保存している場合、は、サブディレクトリを使用するようにプログラムを変更します。</span><span class="sxs-lookup"><span data-stu-id="bf8f1-105">If your program is opening, closing, or saving files in the root directory, change your program so that it uses a subdirectory.</span></span>  
  
2.  <span data-ttu-id="bf8f1-106">指定されたファイルの数を増やす、**ファイル =** の構成で設定します。SYS ファイルを開き、コンピューターを再起動します。</span><span class="sxs-lookup"><span data-stu-id="bf8f1-106">Increase the number of files specified in your **files=** setting in your CONFIG.SYS file, and restart your computer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf8f1-107">関連項目</span><span class="sxs-lookup"><span data-stu-id="bf8f1-107">See also</span></span>

- [<span data-ttu-id="bf8f1-108">エラーの種類</span><span class="sxs-lookup"><span data-stu-id="bf8f1-108">Error Types</span></span>](../../../visual-basic/programming-guide/language-features/error-types.md)
