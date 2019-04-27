---
title: DLL 読み込み時のエラーです。(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vbrID48
ms.assetid: 4226cd1f-028c-477d-88a5-cb57f7e0cdc8
ms.openlocfilehash: c3f88a5a3c37c89d23055aa413957b2add38ed67
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61803468"
---
# <a name="error-in-loading-dll-visual-basic"></a><span data-ttu-id="5de1d-102">DLL 読み込み時のエラーです。(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5de1d-102">Error in loading DLL (Visual Basic)</span></span>
<span data-ttu-id="5de1d-103">ダイナミック リンク ライブラリ (DLL) がで指定されているライブラリ、`Lib`の句、`Declare`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="5de1d-103">A dynamic-link library (DLL) is a library specified in the `Lib` clause of a `Declare` statement.</span></span> <span data-ttu-id="5de1d-104">このエラーの考えられる原因は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="5de1d-104">Possible causes for this error include:</span></span>  
  
-   <span data-ttu-id="5de1d-105">ファイルは、DLL の実行可能ファイルではありません。</span><span class="sxs-lookup"><span data-stu-id="5de1d-105">The file is not DLL executable.</span></span>  
  
-   <span data-ttu-id="5de1d-106">ファイルは、Microsoft Windows の DLL ではありません。</span><span class="sxs-lookup"><span data-stu-id="5de1d-106">The file is not a Microsoft Windows DLL.</span></span>  
  
-   <span data-ttu-id="5de1d-107">DLL が存在しない別の DLL を参照します。</span><span class="sxs-lookup"><span data-stu-id="5de1d-107">The DLL references another DLL that is not present.</span></span>  
  
-   <span data-ttu-id="5de1d-108">DLL または参照される DLL がパスに指定されたディレクトリではありません。</span><span class="sxs-lookup"><span data-stu-id="5de1d-108">The DLL or referenced DLL is not in a directory specified in the path.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="5de1d-109">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="5de1d-109">To correct this error</span></span>  
  
-   <span data-ttu-id="5de1d-110">ソース テキスト ファイルとそのための DLL が実行可能ファイルがある場合に、コンパイルして DLL の実行可能ファイル形式にリンクする必要があります。</span><span class="sxs-lookup"><span data-stu-id="5de1d-110">If the file is a source-text file and therefore not DLL executable, it must be compiled and linked to a DLL-executable form.</span></span>  
  
-   <span data-ttu-id="5de1d-111">ファイルが Microsoft Windows DLL でない場合は、同等の Microsoft Windows を入手します。</span><span class="sxs-lookup"><span data-stu-id="5de1d-111">If the file is not a Microsoft Windows DLL, obtain the Microsoft Windows equivalent.</span></span>  
  
-   <span data-ttu-id="5de1d-112">DLL が存在しない別の DLL を参照する場合は、参照される DLL を入手して使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="5de1d-112">If the DLL references another DLL that is not present, obtain the referenced DLL and make it available.</span></span>  
  
-   <span data-ttu-id="5de1d-113">DLL または参照される DLL がパスで指定されたディレクトリにない場合は、DLL を参照先のディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="5de1d-113">If the DLL or referenced DLL is not in a directory specified by the path, move the DLL to a referenced directory.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5de1d-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="5de1d-114">See also</span></span>

- [<span data-ttu-id="5de1d-115">Declare ステートメント</span><span class="sxs-lookup"><span data-stu-id="5de1d-115">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)
