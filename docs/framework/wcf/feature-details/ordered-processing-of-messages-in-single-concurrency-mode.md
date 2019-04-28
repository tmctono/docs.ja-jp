---
title: Single コンカレンシー モードでメッセージを順番に処理する
ms.date: 03/30/2017
ms.assetid: a90f5662-a796-46cd-ae33-30a4072838af
ms.openlocfilehash: 785c2953e57eaf967209b0d9e52ab85a3a99c450
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61769448"
---
# <a name="ordered-processing-of-messages-in-single-concurrency-mode"></a><span data-ttu-id="a6d69-102">Single コンカレンシー モードでメッセージを順番に処理する</span><span class="sxs-lookup"><span data-stu-id="a6d69-102">Ordered Processing of Messages in Single Concurrency Mode</span></span>
<span data-ttu-id="a6d69-103">WCF は、基になるチャネルがセッションフルでない限りには、メッセージの処理順序に関する保証しません。</span><span class="sxs-lookup"><span data-stu-id="a6d69-103">WCF makes no guarantees about the order in which messages are processed, unless the underlying channel is sessionful.</span></span>  <span data-ttu-id="a6d69-104">たとえば、セッションフル チャネルではない MsmqInputChannel を使用する WCF サービスは順序でメッセージの処理に失敗します。</span><span class="sxs-lookup"><span data-stu-id="a6d69-104">For instance, a WCF service that uses MsmqInputChannel, which is not a sessionful channel, will fail to process messages in order.</span></span> <span data-ttu-id="a6d69-105">これは、状況によっては、開発者を必要とする処理動作しますが、セッションを使用しない場合があります。</span><span class="sxs-lookup"><span data-stu-id="a6d69-105">There are some circumstances where a developer may want the in order processing behavior but not want to use sessions.</span></span> <span data-ttu-id="a6d69-106">このトピックでは、サービスが Single コンカレンシー モードで実行されている場合にこの動作を構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="a6d69-106">This topic describes how to configure this behavior when a service is running in Single Concurrency Mode.</span></span>  
  
## <a name="in-order-message-processing"></a><span data-ttu-id="a6d69-107">順番に従ったメッセージの処理</span><span class="sxs-lookup"><span data-stu-id="a6d69-107">In-order Message Processing</span></span>  
 <span data-ttu-id="a6d69-108"><xref:System.ServiceModel.ServiceBehaviorAttribute.EnsureOrderedDispatch%2A> という名前の新しい属性が <xref:System.ServiceModel.ServiceBehaviorAttribute> に追加されました。</span><span class="sxs-lookup"><span data-stu-id="a6d69-108">A new attribute called <xref:System.ServiceModel.ServiceBehaviorAttribute.EnsureOrderedDispatch%2A> has been added to the <xref:System.ServiceModel.ServiceBehaviorAttribute>.</span></span> <span data-ttu-id="a6d69-109"><xref:System.ServiceModel.ServiceBehaviorAttribute.EnsureOrderedDispatch%2A> を true に設定し、<xref:System.ServiceModel.ServiceBehaviorAttribute.ConcurrencyMode%2A> を <xref:System.ServiceModel.ConcurrencyMode.Single> に設定すると、サービスに送信されたメッセージは順番に処理されます。</span><span class="sxs-lookup"><span data-stu-id="a6d69-109">When <xref:System.ServiceModel.ServiceBehaviorAttribute.EnsureOrderedDispatch%2A> is set to true and <xref:System.ServiceModel.ServiceBehaviorAttribute.ConcurrencyMode%2A> is set to <xref:System.ServiceModel.ConcurrencyMode.Single> messages sent to the service will be processed in order.</span></span> <span data-ttu-id="a6d69-110">次のコードは、これらの属性の設定方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="a6d69-110">The following code snippet illustrates how to set these attributes.</span></span>  
  
```  
[ServiceBehavior(ConcurrencyMode = ConcurrencyMode.Single, EnsureOrderedDispatch = true )]  
    class Service : IService  
    {  
         // ...  
    }  
```  
  
 <span data-ttu-id="a6d69-111"><xref:System.ServiceModel.ServiceBehaviorAttribute.ConcurrencyMode%2A> をその他の値に設定すると、<xref:System.InvalidOperationException> がスローされます。</span><span class="sxs-lookup"><span data-stu-id="a6d69-111">If <xref:System.ServiceModel.ServiceBehaviorAttribute.ConcurrencyMode%2A> is set to any other value, an <xref:System.InvalidOperationException> is thrown.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6d69-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="a6d69-112">See also</span></span>

- [<span data-ttu-id="a6d69-113">セッション、インスタンス化、およびコンカレンシー</span><span class="sxs-lookup"><span data-stu-id="a6d69-113">Sessions, Instancing, and Concurrency</span></span>](../../../../docs/framework/wcf/feature-details/sessions-instancing-and-concurrency.md)
- [<span data-ttu-id="a6d69-114">コンカレンシー</span><span class="sxs-lookup"><span data-stu-id="a6d69-114">Concurrency</span></span>](../../../../docs/framework/wcf/samples/concurrency.md)
