---
title: 不適切なチェックサム値です。16 進数ではないか、または奇数の 16 進数です。
ms.date: 07/20/2015
f1_keywords:
- bc42033
- vbc42033
helpviewer_keywords:
- BC42033
ms.assetid: 4575554d-3615-46e4-9c6a-18e9c338e4ed
ms.openlocfilehash: 1ae4113505ca63df9b20e6e71aa0b418da4ef924
ms.sourcegitcommit: 5a28f8eb071fcc09b045b0c4ae4b96898673192e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2019
ms.locfileid: "73197352"
---
# <a name="bad-checksum-value-non-hex-digits-or-odd-number-of-hex-digits"></a><span data-ttu-id="6c0f1-102">不適切なチェックサム値です。16 進数ではないか、または奇数の 16 進数です。</span><span class="sxs-lookup"><span data-stu-id="6c0f1-102">Bad checksum value, non hex digits or odd number of hex digits</span></span>
<span data-ttu-id="6c0f1-103">チェックサムの値に無効な 16 進数が含まれるか、桁数が奇数です。</span><span class="sxs-lookup"><span data-stu-id="6c0f1-103">A checksum value contains invalid hexadecimal digits or has an odd number of digits.</span></span>  
  
 <span data-ttu-id="6c0f1-104">ASP.NET は Visual Basic のソース ファイル (拡張子 .vb) を生成するとき、チェックサムを計算して `#externalchecksum` で指定された隠しソース ファイルに格納します。</span><span class="sxs-lookup"><span data-stu-id="6c0f1-104">When ASP.NET generates a Visual Basic source file (extension .vb), it calculates a checksum and places it in a hidden source file identified by `#externalchecksum`.</span></span> <span data-ttu-id="6c0f1-105">ユーザーが同じ目的で .vb ファイルを生成することもできますが、このプロセスは内部使用のままにしておくことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="6c0f1-105">It is possible for a user generating a .vb file to do this also, but this process is best left to internal use.</span></span>  
  
 <span data-ttu-id="6c0f1-106">既定では、このメッセージは警告です。</span><span class="sxs-lookup"><span data-stu-id="6c0f1-106">By default, this message is a warning.</span></span> <span data-ttu-id="6c0f1-107">警告を非表示にする方法や、警告をエラーとして扱う方法については、「 [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6c0f1-107">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="6c0f1-108">**エラー ID:** BC42033</span><span class="sxs-lookup"><span data-stu-id="6c0f1-108">**Error ID:** BC42033</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="6c0f1-109">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="6c0f1-109">To correct this error</span></span>  
  
1. <span data-ttu-id="6c0f1-110">ASP.NET が Visual Basic ソース ファイルを生成している場合は、プロジェクト ビルドを再起動してください。</span><span class="sxs-lookup"><span data-stu-id="6c0f1-110">If ASP.NET is generating the Visual Basic source file, restart the project build.</span></span>  
  
2. <span data-ttu-id="6c0f1-111">再起動してもこの警告が続く場合は、ASP.NET をインストールし直してもう一度ビルドしてください。</span><span class="sxs-lookup"><span data-stu-id="6c0f1-111">If this warning persists after restarting, reinstall ASP.NET and try the build again.</span></span>  
  
3. <span data-ttu-id="6c0f1-112">それでも警告が続くか、ASP.NET を使用していない場合は、状況に関する情報を収集し、マイクロソフト プロダクト サポート サービスに通知してください。</span><span class="sxs-lookup"><span data-stu-id="6c0f1-112">If the warning still persists, or if you are not using ASP.NET, gather information about the circumstances and notify Microsoft Product Support Services.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c0f1-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="6c0f1-113">See also</span></span>

- [<span data-ttu-id="6c0f1-114">ASP.NET の概要</span><span class="sxs-lookup"><span data-stu-id="6c0f1-114">ASP.NET Overview</span></span>](/aspnet/overview)
- [<span data-ttu-id="6c0f1-115">ご意見</span><span class="sxs-lookup"><span data-stu-id="6c0f1-115">Talk to Us</span></span>](/visualstudio/ide/feedback-options)
