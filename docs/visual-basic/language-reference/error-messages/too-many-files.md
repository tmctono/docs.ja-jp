---
title: ファイルが多すぎます。
ms.date: 07/20/2015
f1_keywords:
- vbrID67
ms.assetid: 2ff203e2-bba6-43ae-b72f-8e92a881c98f
ms.openlocfilehash: 1d7fc769a0a2d0f8474c0a72a5600b84c8396201
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61982424"
---
# <a name="too-many-files"></a><span data-ttu-id="bcd09-102">ファイルが多すぎます。</span><span class="sxs-lookup"><span data-stu-id="bcd09-102">Too many files</span></span>
<span data-ttu-id="bcd09-103">オペレーティング システムで許可されているよりも多くのファイルがルート ディレクトリに作成されているか、CONFIG.SYS ファイルの **[files=]** 設定で指定された数よりも多くのファイルが開かれています。</span><span class="sxs-lookup"><span data-stu-id="bcd09-103">Either more files have been created in the root directory than the operating system permits, or more files have been opened than the number specified in the **files=** setting in your CONFIG.SYS file.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="bcd09-104">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="bcd09-104">To correct this error</span></span>  
  
1. <span data-ttu-id="bcd09-105">プログラムがルート ディレクトリ内のファイルを開いたり、閉じたり、または保存したりしている場合は、サブディレクトリを使用するようにプログラムを変更します。</span><span class="sxs-lookup"><span data-stu-id="bcd09-105">If your program is opening, closing, or saving files in the root directory, change your program so that it uses a subdirectory.</span></span>  
  
2. <span data-ttu-id="bcd09-106">CONFIG.SYS ファイルの **[files=]** 設定で指定されているファイルの数を増やして、コンピューターを再起動します。</span><span class="sxs-lookup"><span data-stu-id="bcd09-106">Increase the number of files specified in your **files=** setting in your CONFIG.SYS file, and restart your computer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bcd09-107">関連項目</span><span class="sxs-lookup"><span data-stu-id="bcd09-107">See also</span></span>

- [<span data-ttu-id="bcd09-108">エラーの種類</span><span class="sxs-lookup"><span data-stu-id="bcd09-108">Error Types</span></span>](../../../visual-basic/programming-guide/language-features/error-types.md)
