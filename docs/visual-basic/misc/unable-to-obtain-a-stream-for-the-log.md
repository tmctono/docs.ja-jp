---
title: ログのストリームを取得できません
ms.date: 07/20/2015
f1_keywords:
- vbrApplicationLog_ExhaustedPossibleStreamNames
ms.assetid: 33994f52-8efb-4790-a459-033e5c1db632
ms.openlocfilehash: 540ff3fbba72d33b2efaa58ad7a8019628f5e83f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59344755"
---
# <a name="unable-to-obtain-a-stream-for-the-log"></a><span data-ttu-id="ce8f1-102">ログのストリームを取得できません</span><span class="sxs-lookup"><span data-stu-id="ce8f1-102">Unable to obtain a stream for the log</span></span>
<span data-ttu-id="ce8f1-103">ログのストリームを取得できません。</span><span class="sxs-lookup"><span data-stu-id="ce8f1-103">Unable to obtain a stream for the log.</span></span> <span data-ttu-id="ce8f1-104">基づくファイル名の潜在的な\<名 > は既に使用します。</span><span class="sxs-lookup"><span data-stu-id="ce8f1-104">Potential file names based on \<name> are already in use.</span></span>  
  
 <span data-ttu-id="ce8f1-105"><xref:Microsoft.VisualBasic.Logging.FileLogTraceListener>可能性のあるすべてのログ ファイル名が基づいているために、クラスは、新しいログ ファイルを作成できませんでした\<名 > は既に使用します。</span><span class="sxs-lookup"><span data-stu-id="ce8f1-105">The <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> class could not create a new log file because all potential log file names based on \<name> are already in use.</span></span>  
  
 <span data-ttu-id="ce8f1-106">ログ ファイルが多すぎる場合、アプリケーションにアーキテクチャの問題がある可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ce8f1-106">Having too many log files may indicate an architectural problem with the application.</span></span> <span data-ttu-id="ce8f1-107">詳細については、 <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> クラスのドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ce8f1-107">See the documentation for the <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> class for more information.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="ce8f1-108">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="ce8f1-108">To correct this error</span></span>  
  
1. <span data-ttu-id="ce8f1-109"><xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.LogFileCreationSchedule%2A> プロパティを <xref:Microsoft.VisualBasic.Logging.LogFileCreationScheduleOption.Daily> または <xref:Microsoft.VisualBasic.Logging.LogFileCreationScheduleOption.Weekly> に設定して、ログ ファイル名に日付スタンプを含めます。</span><span class="sxs-lookup"><span data-stu-id="ce8f1-109">Set the <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.LogFileCreationSchedule%2A> property to <xref:Microsoft.VisualBasic.Logging.LogFileCreationScheduleOption.Daily> or <xref:Microsoft.VisualBasic.Logging.LogFileCreationScheduleOption.Weekly> to include a date-stamp in the log file name.</span></span>  
  
2. <span data-ttu-id="ce8f1-110">既存のログをアーカイブし、それらをコンピューターから削除して、 <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> オブジェクトが新しいログを作成できるようにします。</span><span class="sxs-lookup"><span data-stu-id="ce8f1-110">Archive the existing logs and remove them from the computer to allow the <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> object to create new logs.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce8f1-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="ce8f1-111">See also</span></span>

- <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener>
- <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.LogFileCreationSchedule%2A>
- [<span data-ttu-id="ce8f1-112">My.Application.Log</span><span class="sxs-lookup"><span data-stu-id="ce8f1-112">My.Application.Log</span></span>](xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.Log)
- [<span data-ttu-id="ce8f1-113">My.Application.Info.DirectoryPath</span><span class="sxs-lookup"><span data-stu-id="ce8f1-113">My.Application.Info.DirectoryPath</span></span>](xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.Log)
