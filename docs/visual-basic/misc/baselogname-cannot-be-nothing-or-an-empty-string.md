---
title: BaseLogName は、Nothing または空文字列にできません
ms.date: 07/20/2015
f1_keywords:
- vbrApplicationLogBaseNameNull
ms.assetid: 8e7665e3-5343-45fa-bc79-64e235a0477f
ms.openlocfilehash: a0e46eccb29d1ced1a979f86f96f761141720174
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2020
ms.locfileid: "91083138"
---
# <a name="baselogname-cannot-be-nothing-or-an-empty-string"></a><span data-ttu-id="22175-102">BaseLogName は、Nothing または空文字列にできません</span><span class="sxs-lookup"><span data-stu-id="22175-102">BaseLogName cannot be Nothing or an empty String</span></span>

<span data-ttu-id="22175-103"><xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.BaseFileName%2A> プロパティの値を `Nothing` または空の文字列にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="22175-103">The value of the <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.BaseFileName%2A> property cannot be `Nothing` or an empty string.</span></span>  
  
 <span data-ttu-id="22175-104"><xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.BaseFileName%2A> プロパティは、ログ ファイルのベース名を指定します。</span><span class="sxs-lookup"><span data-stu-id="22175-104">The <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.BaseFileName%2A> property specifies the base name for the log files.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="22175-105">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="22175-105">To correct this error</span></span>  
  
- <span data-ttu-id="22175-106"><xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.BaseFileName%2A> プロパティを、少なくとも 1 つの文字を含む文字列に設定します。</span><span class="sxs-lookup"><span data-stu-id="22175-106">Set the <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.BaseFileName%2A> property to a string that contains at least one character.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22175-107">こちらもご覧ください</span><span class="sxs-lookup"><span data-stu-id="22175-107">See also</span></span>

- <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.BaseFileName%2A>
- [<span data-ttu-id="22175-108">.Log</span><span class="sxs-lookup"><span data-stu-id="22175-108">My.Application.Log</span></span>](xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.Log)
- <span data-ttu-id="22175-109">[[DirectoryPath]](xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.Log)</span><span class="sxs-lookup"><span data-stu-id="22175-109">[My.Application.Info.DirectoryPath](xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.Log)</span></span>
