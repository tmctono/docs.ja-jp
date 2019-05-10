---
title: EventLogSource で指定したソース名は、EventLogName で指定したログ以外のログに登録されています
ms.date: 07/20/2015
ms.assetid: 7317e100-098b-408d-86e5-7c74cf8558c7
ms.openlocfilehash: 226516e48a7f658d2ec95283e0b0d60fa3f856eb
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64619233"
---
# <a name="source-name-specified-in-eventlogsource-is-registered-to-a-log-other-than-that-specified-in-eventlogname"></a><span data-ttu-id="52e64-102">EventLogSource で指定したソース名は、EventLogName で指定したログ以外のログに登録されています</span><span class="sxs-lookup"><span data-stu-id="52e64-102">Source name specified in EventLogSource is registered to a log other than that specified in EventLogName</span></span>
<span data-ttu-id="52e64-103">`EventLog` が、別のログに登録されているソースを参照しようとしています。</span><span class="sxs-lookup"><span data-stu-id="52e64-103">The `EventLog` is attempting to refer to a source that is registered to a different log.</span></span> <span data-ttu-id="52e64-104">イベント ログにエントリを書き込んでいる場合は、 <xref:System.Diagnostics.EventLog.Source%2A> プロパティを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="52e64-104">If you are writing entries to an event log, you must specify the <xref:System.Diagnostics.EventLog.Source%2A> property.</span></span> <span data-ttu-id="52e64-105"><xref:System.Diagnostics.EventLog.Source%2A> プロパティはコンポーネントを有効なエントリのソースとしてイベント ログに登録します。</span><span class="sxs-lookup"><span data-stu-id="52e64-105">The <xref:System.Diagnostics.EventLog.Source%2A> property registers your component with the event log as a valid source of entries.</span></span> <span data-ttu-id="52e64-106">1 つのソースは一度に 1 つのイベント ログにのみ関連付ける (つまり、エントリを書き込む) ことができます。</span><span class="sxs-lookup"><span data-stu-id="52e64-106">A single source can be associated with (and therefore write entries to) only one event log at a time.</span></span>  
  
 <span data-ttu-id="52e64-107">既定では、先にコンポーネントを有効なソースとして登録しないでエントリを書き込もうとした場合、 <xref:System.Diagnostics.EventLog.Source%2A> プロパティの値をソース文字列として使用して、自動的にソースがイベント ログに登録されます。</span><span class="sxs-lookup"><span data-stu-id="52e64-107">By default, if you try to write an entry without first having registered your component as a valid source, the system automatically registers the source with the event log, using the value of the <xref:System.Diagnostics.EventLog.Source%2A> property as the source string.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="52e64-108">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="52e64-108">To correct this error</span></span>  
  
- <span data-ttu-id="52e64-109">ソースが、正しいログに登録されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="52e64-109">Make sure the source is registered to the correct log.</span></span> <span data-ttu-id="52e64-110">これを行うには、 <xref:System.Diagnostics.EventLog.CreateEventSource%2A> メソッドまたをそのオーバーロードのいずれかを使用して、コンポーネントを一意に識別する文字列をイベント ログに指定します。</span><span class="sxs-lookup"><span data-stu-id="52e64-110">To do this, use the <xref:System.Diagnostics.EventLog.CreateEventSource%2A> method or one of its overloads to specify a string that uniquely identifies your component to the event log.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52e64-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="52e64-111">See also</span></span>

- <span data-ttu-id="52e64-112">[イベント ログの管理](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/4f69axw4(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="52e64-112">[Administering Event Logs](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/4f69axw4(v=vs.90))</span></span>
- <span data-ttu-id="52e64-113">[イベント ログの参照](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/k43k9z2a(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="52e64-113">[Event Log References](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/k43k9z2a(v=vs.90))</span></span>
- <span data-ttu-id="52e64-114">[方法: イベント ログ エントリのソースとして、アプリケーションを追加します。](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/xz73e171(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="52e64-114">[How to: Add Your Application as a Source of Event Log Entries](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/xz73e171(v=vs.90))</span></span>
- <span data-ttu-id="52e64-115">[方法: イベント ソースを削除します。](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/k57466fc(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="52e64-115">[How to: Remove an Event Source](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/k57466fc(v=vs.90))</span></span>
