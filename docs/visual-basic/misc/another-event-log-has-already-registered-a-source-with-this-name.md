---
title: 別のイベント ログが、既にこの名前のソースを登録しています
ms.date: 07/20/2015
ms.assetid: e6f5cd95-bb3f-4845-84fb-ae623a9bd44e
ms.openlocfilehash: 333c28036e2d1b7514c7370b98ff70a6d195a9dd
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2020
ms.locfileid: "91058392"
---
# <a name="another-event-log-has-already-registered-a-source-with-this-name"></a><span data-ttu-id="be2d5-102">別のイベント ログが、既にこの名前のソースを登録しています</span><span class="sxs-lookup"><span data-stu-id="be2d5-102">Another event log has already registered a source with this name</span></span>

<span data-ttu-id="be2d5-103">イベント ログにエントリを書き込もうとしましたが、指定のソースは別のイベント ログに登録されています。</span><span class="sxs-lookup"><span data-stu-id="be2d5-103">An attempt was made to write an entry to an event log where the specified source is registered with another event log.</span></span>  
  
 <span data-ttu-id="be2d5-104"><xref:System.Diagnostics.EventLog.Source%2A> コンポーネントのインスタンスの <xref:System.Diagnostics.EventLog> プロパティを設定しておかなければ、コンポーネントはログにエントリを書き込めません。</span><span class="sxs-lookup"><span data-stu-id="be2d5-104">You must set the <xref:System.Diagnostics.EventLog.Source%2A> property of your <xref:System.Diagnostics.EventLog> component instance before your component writes an entry to a log.</span></span> <span data-ttu-id="be2d5-105">書き込み時、システムは、指定したソースがコンポーネントの書き込み先のイベント ログに登録されているかどうかを確認し、必要に応じて <xref:System.Diagnostics.EventLog.CreateEventSource%2A> を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="be2d5-105">When this happens, the system checks that the source you specified is registered with the event log to which the component is writing, and calls <xref:System.Diagnostics.EventLog.CreateEventSource%2A> if needed.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="be2d5-106">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="be2d5-106">To correct this error</span></span>  
  
1. <span data-ttu-id="be2d5-107"><xref:System.Diagnostics.EventLog.DeleteEventSource%2A> または <xref:System.Diagnostics.EventLog.DeleteEventSource%2A> メソッドを使用して、最初のログに対するソースの関連付けを削除します。</span><span class="sxs-lookup"><span data-stu-id="be2d5-107">Remove the association of the source with the first log using the <xref:System.Diagnostics.EventLog.DeleteEventSource%2A> or the <xref:System.Diagnostics.EventLog.DeleteEventSource%2A> method.</span></span>  
  
2. <span data-ttu-id="be2d5-108">ソースを新しいログに登録します。</span><span class="sxs-lookup"><span data-stu-id="be2d5-108">Register the source with the new log.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be2d5-109">こちらもご覧ください</span><span class="sxs-lookup"><span data-stu-id="be2d5-109">See also</span></span>

- [<span data-ttu-id="be2d5-110">.Log</span><span class="sxs-lookup"><span data-stu-id="be2d5-110">My.Application.Log</span></span>](xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.Log)
