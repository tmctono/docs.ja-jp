---
title: ファイルが多すぎます。
ms.date: 07/20/2015
f1_keywords:
- vbrID67
ms.assetid: 2ff203e2-bba6-43ae-b72f-8e92a881c98f
ms.openlocfilehash: 38d39ad20f350137d714ae5d09db5d2204b83621
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2020
ms.locfileid: "84362801"
---
# <a name="too-many-files"></a><span data-ttu-id="ad399-102">ファイルが多すぎます。</span><span class="sxs-lookup"><span data-stu-id="ad399-102">Too many files</span></span>
<span data-ttu-id="ad399-103">オペレーティング システムで許可されているよりも多くのファイルがルート ディレクトリに作成されているか、CONFIG.SYS ファイルの **[files=]** 設定で指定された数よりも多くのファイルが開かれています。</span><span class="sxs-lookup"><span data-stu-id="ad399-103">Either more files have been created in the root directory than the operating system permits, or more files have been opened than the number specified in the **files=** setting in your CONFIG.SYS file.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="ad399-104">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="ad399-104">To correct this error</span></span>  
  
1. <span data-ttu-id="ad399-105">プログラムがルート ディレクトリ内のファイルを開いたり、閉じたり、または保存したりしている場合は、サブディレクトリを使用するようにプログラムを変更します。</span><span class="sxs-lookup"><span data-stu-id="ad399-105">If your program is opening, closing, or saving files in the root directory, change your program so that it uses a subdirectory.</span></span>  
  
2. <span data-ttu-id="ad399-106">CONFIG.SYS ファイルの **[files=]** 設定で指定されているファイルの数を増やして、コンピューターを再起動します。</span><span class="sxs-lookup"><span data-stu-id="ad399-106">Increase the number of files specified in your **files=** setting in your CONFIG.SYS file, and restart your computer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad399-107">関連項目</span><span class="sxs-lookup"><span data-stu-id="ad399-107">See also</span></span>

- [<span data-ttu-id="ad399-108">エラーの種類</span><span class="sxs-lookup"><span data-stu-id="ad399-108">Error Types</span></span>](../../programming-guide/language-features/error-types.md)
