---
title: HTTP、TCP、または名前付きパイプを使用した非同期シナリオ
ms.date: 03/30/2017
ms.assetid: a4d62402-43a4-48a4-9ced-220633ebc4ce
ms.openlocfilehash: d08f70186a59b8717c4441167ee720ba1c20b9dc
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61998291"
---
# <a name="asynchronous-scenarios-using-http-tcp-or-named-pipe"></a><span data-ttu-id="8c0cb-102">HTTP、TCP、または名前付きパイプを使用した非同期シナリオ</span><span class="sxs-lookup"><span data-stu-id="8c0cb-102">Asynchronous Scenarios using HTTP, TCP, or Named-Pipe</span></span>
<span data-ttu-id="8c0cb-103">ここでは、マルチスレッド要求で HTTP、TCP、または名前付きパイプを使用したときの、さまざまな非同期要求/応答シナリオでのアクティビティおよび転送について説明します。</span><span class="sxs-lookup"><span data-stu-id="8c0cb-103">This topic describes the activities and transfers for different asynchronous request/reply scenarios, with multithreaded requests using HTTP, TCP, or named pipe.</span></span>  
  
## <a name="asynchronous-requestreply-without-errors"></a><span data-ttu-id="8c0cb-104">エラーを伴わない非同期要求/応答</span><span class="sxs-lookup"><span data-stu-id="8c0cb-104">Asynchronous Request/Reply without Errors</span></span>  
 <span data-ttu-id="8c0cb-105">ここでは、マルチスレッド クライアントを使用したときの、非同期要求/応答シナリオでのアクティビティおよび転送について説明します。</span><span class="sxs-lookup"><span data-stu-id="8c0cb-105">This section describes the activities and transfers for an asynchronous request/reply scenario, with multithreaded clients.</span></span>  
  
 <span data-ttu-id="8c0cb-106">呼び出し元アクティビティは、`beginCall` が返され、`endCall` が返されると終了します。</span><span class="sxs-lookup"><span data-stu-id="8c0cb-106">The caller activity terminates when `beginCall` returns, and `endCall` returns.</span></span> <span data-ttu-id="8c0cb-107">コールバックが呼び出されたときは、そのコールバックが返されます。</span><span class="sxs-lookup"><span data-stu-id="8c0cb-107">If a callback is called, the callback returns.</span></span>  
  
 <span data-ttu-id="8c0cb-108">呼び出されたアクティビティは、`beginCall` が返され、`endCall` が返されると終了します。または、そのアクティビティからコールバックが呼び出された場合は、コールバックが返されると終了します。</span><span class="sxs-lookup"><span data-stu-id="8c0cb-108">The called activity terminates when `beginCall` returns, `endCall` returns, or when the callback returns if it was called from that activity.</span></span>  
  
### <a name="asynchronous-client-without-callback"></a><span data-ttu-id="8c0cb-109">コールバックを伴わない非同期クライアント</span><span class="sxs-lookup"><span data-stu-id="8c0cb-109">Asynchronous Client without Callback</span></span>  
  
#### <a name="propagation-is-enabled-on-both-sides-using-http"></a><span data-ttu-id="8c0cb-110">HTTP を使用して、両方の側で伝達が有効になっている場合</span><span class="sxs-lookup"><span data-stu-id="8c0cb-110">Propagation is Enabled on Both Sides, using HTTP</span></span>  
 <span data-ttu-id="8c0cb-111">![非同期シナリオ](../../../../../docs/framework/wcf/diagnostics/tracing/media/asyn1.gif "Asyn1")</span><span class="sxs-lookup"><span data-stu-id="8c0cb-111">![Asynchronous scenarios](../../../../../docs/framework/wcf/diagnostics/tracing/media/asyn1.gif "Asyn1")</span></span>  
  
 <span data-ttu-id="8c0cb-112">図 1.</span><span class="sxs-lookup"><span data-stu-id="8c0cb-112">Figure 1.</span></span> <span data-ttu-id="8c0cb-113">非同期クライアント、コールバックなし、 `propagateActivity` = `true`両方の側では、HTTP で</span><span class="sxs-lookup"><span data-stu-id="8c0cb-113">Asynchronous client, no callback, `propagateActivity`=`true` on both sides, HTTP</span></span>  
  
 <span data-ttu-id="8c0cb-114">場合`propagateActivity` = `true`ProcessMessage は ProcessAction アクティビティへの転送を示します。</span><span class="sxs-lookup"><span data-stu-id="8c0cb-114">If `propagateActivity`=`true`, ProcessMessage indicates which ProcessAction activity to transfer to.</span></span>  
  
 <span data-ttu-id="8c0cb-115">HTTP ベースのシナリオでは、最初に送信するメッセージで "バイトを受信" が呼び出され、要求の有効期間だけ存在します。</span><span class="sxs-lookup"><span data-stu-id="8c0cb-115">For HTTP-based scenarios, ReceiveBytes is invoked on the first message to send, and exists for the lifetime of the request.</span></span>  
  
#### <a name="propagation-is-disabled-on-either-sides-using-http"></a><span data-ttu-id="8c0cb-116">HTTP を使用して、両方の側で伝達が無効になっている場合</span><span class="sxs-lookup"><span data-stu-id="8c0cb-116">Propagation is Disabled on Either Sides, using HTTP</span></span>  
 <span data-ttu-id="8c0cb-117">場合`propagateActivity` = `false`いずれかの側では、ProcessMessage は示しませんアクティビティへの転送を示しません。</span><span class="sxs-lookup"><span data-stu-id="8c0cb-117">If `propagateActivity`=`false` on either side, ProcessMessage does not indicate which ProcessAction activity to transfer to.</span></span> <span data-ttu-id="8c0cb-118">したがって、新しい ID を使用して、新しい一時的な "アクションを処理" アクティビティが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="8c0cb-118">Therefore, a new temporary ProcessAction activity with a new ID is invoked.</span></span> <span data-ttu-id="8c0cb-119">非同期応答と ServiceModel コード内の要求が一致する場合は、アクティビティ ID をローカル コンテキストから取得できます。</span><span class="sxs-lookup"><span data-stu-id="8c0cb-119">When the asynchronous response is matched to the request in ServiceModel code, the Activity ID can be retrieved from the local context.</span></span> <span data-ttu-id="8c0cb-120">その ID を使用して、実際の "アクションを処理" アクティビティに転送できます。</span><span class="sxs-lookup"><span data-stu-id="8c0cb-120">The actual ProcessAction activity can be transferred to with that ID.</span></span>  
  
 <span data-ttu-id="8c0cb-121">![HTTP を使用した非同期シナリオ&#47;TCP&#47;名前付きパイプ](../../../../../docs/framework/wcf/diagnostics/tracing/media/async2.gif "Async2")</span><span class="sxs-lookup"><span data-stu-id="8c0cb-121">![Asynchronous scenarios using HTTP&#47;TCP&#47;Named Pipe](../../../../../docs/framework/wcf/diagnostics/tracing/media/async2.gif "Async2")</span></span>  
  
 <span data-ttu-id="8c0cb-122">図 2.</span><span class="sxs-lookup"><span data-stu-id="8c0cb-122">Figure 2.</span></span> <span data-ttu-id="8c0cb-123">非同期クライアント、コールバックなし、 `propagateActivity` = `false`右辺でも左辺でも、HTTP</span><span class="sxs-lookup"><span data-stu-id="8c0cb-123">Asynchronous client, no callback, `propagateActivity`=`false` on either side, HTTP</span></span>  
  
 <span data-ttu-id="8c0cb-124">HTTP ベースのシナリオでは、最初に送信するメッセージで "バイトを受信" が呼び出され、要求の有効期間だけ存在します。</span><span class="sxs-lookup"><span data-stu-id="8c0cb-124">For HTTP-based scenarios, ReceiveBytes is invoked on the first message to send, and exists for the lifetime of the request.</span></span>  
  
 <span data-ttu-id="8c0cb-125">プロセスのアクション アクティビティが、非同期クライアントで作成されたときに`propagateActivity` = `false`呼び出し元または呼び出し先、および応答メッセージに Action ヘッダーが含まれていない場合。</span><span class="sxs-lookup"><span data-stu-id="8c0cb-125">A Process Action activity is created on an asynchronous client when `propagateActivity`=`false` at the caller or callee, and when the response message does not include an Action header.</span></span>  
  
#### <a name="propagation-is-enabled-on-both-sides-using-tcp-or-named-pipe"></a><span data-ttu-id="8c0cb-126">TCP または名前付きパイプを使用して、両方の側で伝達が有効になっている場合</span><span class="sxs-lookup"><span data-stu-id="8c0cb-126">Propagation is Enabled on Both Sides, using TCP or Named Pipe</span></span>  
 <span data-ttu-id="8c0cb-127">![HTTP を使用した非同期シナリオ&#47;TCP&#47;名前付きパイプ](../../../../../docs/framework/wcf/diagnostics/tracing/media/async3.gif "Async3")</span><span class="sxs-lookup"><span data-stu-id="8c0cb-127">![Asynchronous scenarios using HTTP&#47;TCP&#47;Named Pipe](../../../../../docs/framework/wcf/diagnostics/tracing/media/async3.gif "Async3")</span></span>  
  
 <span data-ttu-id="8c0cb-128">図 3.</span><span class="sxs-lookup"><span data-stu-id="8c0cb-128">Figure 3.</span></span> <span data-ttu-id="8c0cb-129">非同期クライアント、コールバックなし、 `propagateActivity` = `true`で両方の側では、名前付きパイプ/TCP</span><span class="sxs-lookup"><span data-stu-id="8c0cb-129">Asynchronous client, no callback, `propagateActivity`=`true` on both sides, Named-Pipe/TCP</span></span>  
  
 <span data-ttu-id="8c0cb-130">名前付きパイプまたは TCP ベースのシナリオでは、クライアントが開かれるときに "バイトを受信" が呼び出され、接続の有効期間だけ存在します。</span><span class="sxs-lookup"><span data-stu-id="8c0cb-130">For a Named-Pipe or TCP-based scenario, ReceiveBytes is invoked when the client is opened, and exists for the lifetime of the connection.</span></span>  
  
 <span data-ttu-id="8c0cb-131">場合 1 を図のような`propagateActivity` = `true`ProcessMessage は ProcessAction アクティビティへの転送を示します。</span><span class="sxs-lookup"><span data-stu-id="8c0cb-131">Similar to Figure 1, if `propagateActivity`=`true`, ProcessMessage indicates which ProcessAction activity to transfer to.</span></span>  
  
#### <a name="propagation-is-disabled-on-either-sides-using-tcp-or-named-pipe"></a><span data-ttu-id="8c0cb-132">TCP または名前付きパイプを使用して、両方の側で伝達が無効になっている場合</span><span class="sxs-lookup"><span data-stu-id="8c0cb-132">Propagation is Disabled on Either Sides, using TCP or Named Pipe</span></span>  
 <span data-ttu-id="8c0cb-133">名前付きパイプまたは TCP ベースのシナリオでは、クライアントが開かれるときに "バイトを受信" が呼び出され、接続の有効期間だけ存在します。</span><span class="sxs-lookup"><span data-stu-id="8c0cb-133">For a Named-Pipe or TCP-based scenario, ReceiveBytes is invoked when the client is opened, and exists for the lifetime of the connection.</span></span>  
  
 <span data-ttu-id="8c0cb-134">図 2 では、ような場合`propagateActivity` = `false`いずれかの側では、ProcessMessage は示しません ProcessAction アクティビティに転送します。</span><span class="sxs-lookup"><span data-stu-id="8c0cb-134">Similar to Fig.2, If `propagateActivity`=`false` on either side, ProcessMessage does not indicate which ProcessAction activity to transfer to.</span></span> <span data-ttu-id="8c0cb-135">したがって、新しい ID を使用して、新しい一時的な "アクションを処理" アクティビティが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="8c0cb-135">Therefore, a new temporary ProcessAction activity with a new ID is invoked.</span></span> <span data-ttu-id="8c0cb-136">非同期応答と ServiceModel コード内の要求が一致する場合は、アクティビティ ID をローカル コンテキストから取得できます。</span><span class="sxs-lookup"><span data-stu-id="8c0cb-136">When the asynchronous response is matched to the request in ServiceModel code, the Activity ID can be retrieved from the local context.</span></span> <span data-ttu-id="8c0cb-137">その ID を使用して、実際の "アクションを処理" アクティビティに転送できます。</span><span class="sxs-lookup"><span data-stu-id="8c0cb-137">The actual ProcessAction activity can be transferred to with that ID.</span></span>  
  
 <span data-ttu-id="8c0cb-138">![HTTP を使用した非同期シナリオ&#47;TCP&#47;名前付きパイプ](../../../../../docs/framework/wcf/diagnostics/tracing/media/async4.gif "Async4")</span><span class="sxs-lookup"><span data-stu-id="8c0cb-138">![Asynchronous scenarios using HTTP&#47;TCP&#47; Named Pipes](../../../../../docs/framework/wcf/diagnostics/tracing/media/async4.gif "Async4")</span></span>  
  
 <span data-ttu-id="8c0cb-139">図 4。</span><span class="sxs-lookup"><span data-stu-id="8c0cb-139">Figure 4.</span></span> <span data-ttu-id="8c0cb-140">非同期クライアント、コールバックなし、 `propagateActivity` = `false`右辺でも左辺でも、名前付きパイプ/TCP</span><span class="sxs-lookup"><span data-stu-id="8c0cb-140">Asynchronous client, no callback, `propagateActivity`=`false` on either side, Named-Pipe/TCP</span></span>  
  
### <a name="asynchronous-client-with-callback"></a><span data-ttu-id="8c0cb-141">コールバックを伴う非同期クライアント</span><span class="sxs-lookup"><span data-stu-id="8c0cb-141">Asynchronous client with Callback</span></span>  
 <span data-ttu-id="8c0cb-142">このシナリオでは、コールバックと `endCall` に対するアクティビティ G と A’、およびその転送 (送受信) が追加されています。</span><span class="sxs-lookup"><span data-stu-id="8c0cb-142">This scenario adds activities G and A’, for the callback and `endCall`, and their transfers in/out.</span></span>  
  
 <span data-ttu-id="8c0cb-143">このセクションでは HTTP との使用方法を示しますのみ`propragateActivity` =`true`します。</span><span class="sxs-lookup"><span data-stu-id="8c0cb-143">This section only demonstrates using HTTP with `propragateActivity`=`true`.</span></span> <span data-ttu-id="8c0cb-144">ただし、それ以外の場合にも適用の他のアクティビティおよび転送 (つまり、 `propagateActivity` = `false`、TCP または名前付きパイプを使用して)。</span><span class="sxs-lookup"><span data-stu-id="8c0cb-144">However, the additional activities and transfers also apply to the other cases (that is, `propagateActivity`=`false`, using TCP or Named-Pipe).</span></span>  
  
 <span data-ttu-id="8c0cb-145">クライアントがユーザー コードを呼び出して結果の準備が完了したことを通知すると、コールバックは新しいアクティビティ (G) を作成します。</span><span class="sxs-lookup"><span data-stu-id="8c0cb-145">The callback creates a new activity (G) when the client calls user code to notify that results are ready.</span></span> <span data-ttu-id="8c0cb-146">ユーザー コードは、次に、コールバック内 (図 5 を参照) またはコールバック外 (図 6 を参照) で `endCall` を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="8c0cb-146">User code then calls `endCall` within the callback (as shown in Figure 5) or outside the callback (Figure 6).</span></span> <span data-ttu-id="8c0cb-147">どのユーザー アクティビティが不明なので`endCall`が呼び出されるから、このアクティビティがというラベルが付いた`A’`します。</span><span class="sxs-lookup"><span data-stu-id="8c0cb-147">Because it is not known which user activity `endCall` is being called from, this activity is labeled `A’`.</span></span> <span data-ttu-id="8c0cb-148">A’ と A が同じである場合もありますし、異なる場合もあります。</span><span class="sxs-lookup"><span data-stu-id="8c0cb-148">It is possible that A’ can be identical to or different from A.</span></span>  
  
 <span data-ttu-id="8c0cb-149">![非同期シナリオ](../../../../../docs/framework/wcf/diagnostics/tracing/media/asynccallback1.gif "AsyncCallback1")</span><span class="sxs-lookup"><span data-stu-id="8c0cb-149">![Asynchronous scenarios](../../../../../docs/framework/wcf/diagnostics/tracing/media/asynccallback1.gif "AsyncCallback1")</span></span>  
  
 <span data-ttu-id="8c0cb-150">図 5。</span><span class="sxs-lookup"><span data-stu-id="8c0cb-150">Figure 5.</span></span> <span data-ttu-id="8c0cb-151">非同期クライアント、コールバックあり、コールバック内での `endCall`</span><span class="sxs-lookup"><span data-stu-id="8c0cb-151">Asynchronous client with callback, `endCall` in Callback</span></span>  
  
 <span data-ttu-id="8c0cb-152">![非同期シナリオ](../../../../../docs/framework/wcf/diagnostics/tracing/media/asynccallback2.gif "AsyncCallback2")</span><span class="sxs-lookup"><span data-stu-id="8c0cb-152">![Asynchronous Scenarios](../../../../../docs/framework/wcf/diagnostics/tracing/media/asynccallback2.gif "AsyncCallback2")</span></span>  
  
 <span data-ttu-id="8c0cb-153">図 6。</span><span class="sxs-lookup"><span data-stu-id="8c0cb-153">Figure 6.</span></span> <span data-ttu-id="8c0cb-154">非同期クライアント、コールバックあり、コールバック外での `endCall`</span><span class="sxs-lookup"><span data-stu-id="8c0cb-154">Asynchronous client with callback, `endCall` outside of Callback</span></span>  
  
### <a name="asynchronous-server-with-callback"></a><span data-ttu-id="8c0cb-155">コールバックを伴う非同期サーバー</span><span class="sxs-lookup"><span data-stu-id="8c0cb-155">Asynchronous Server with Callback</span></span>  
 <span data-ttu-id="8c0cb-156">![HTTP を使用した非同期シナリオ&#47;TCP&#47;名前付き&#45;パイプ](../../../../../docs/framework/wcf/diagnostics/tracing/media/aynchserver.gif "AynchServer")</span><span class="sxs-lookup"><span data-stu-id="8c0cb-156">![Asynchronous scenarios using HTTP&#47;TCP&#47; Named&#45;Pipe](../../../../../docs/framework/wcf/diagnostics/tracing/media/aynchserver.gif "AynchServer")</span></span>  
  
 <span data-ttu-id="8c0cb-157">図 7。</span><span class="sxs-lookup"><span data-stu-id="8c0cb-157">Figure 7.</span></span> <span data-ttu-id="8c0cb-158">非同期サーバー、コールバックあり</span><span class="sxs-lookup"><span data-stu-id="8c0cb-158">Asynchronous server, with callback</span></span>  
  
 <span data-ttu-id="8c0cb-159">チャネル スタックは、"メッセージを受信" でクライアントをコールバックします。この処理のトレースは、"要求を処理" アクティビティ自体で出力されます。</span><span class="sxs-lookup"><span data-stu-id="8c0cb-159">The channel stack calls back the client on Message Receive: traces for this processing are emitted in the ProcessRequest activity itself.</span></span>  
  
## <a name="asynchronous-requestreply-with-errors"></a><span data-ttu-id="8c0cb-160">エラーを伴う非同期要求/応答</span><span class="sxs-lookup"><span data-stu-id="8c0cb-160">Asynchronous Request/Reply with Errors</span></span>  
 <span data-ttu-id="8c0cb-161">エラー メッセージは、`endCall` 中に受信されます。</span><span class="sxs-lookup"><span data-stu-id="8c0cb-161">Fault message errors are received during `endCall`.</span></span> <span data-ttu-id="8c0cb-162">この点を除き、アクティビティおよび転送は前のシナリオと同様です。</span><span class="sxs-lookup"><span data-stu-id="8c0cb-162">Otherwise, activities and transfers are similar to previous scenarios.</span></span>  
  
## <a name="asynchronous-one-way-with-or-without-errors"></a><span data-ttu-id="8c0cb-163">エラーを伴う/伴わない非同期一方向要求/応答</span><span class="sxs-lookup"><span data-stu-id="8c0cb-163">Asynchronous One-Way with or without Errors</span></span>  
 <span data-ttu-id="8c0cb-164">クライアントに返される応答やエラーはありません。</span><span class="sxs-lookup"><span data-stu-id="8c0cb-164">No response or fault is returned to the client.</span></span>
