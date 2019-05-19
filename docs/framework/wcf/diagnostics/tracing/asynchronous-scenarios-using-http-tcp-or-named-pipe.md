---
title: HTTP、TCP、または名前付きパイプを使用した非同期シナリオ
ms.date: 03/30/2017
ms.assetid: a4d62402-43a4-48a4-9ced-220633ebc4ce
ms.openlocfilehash: 48957ec0abd1b4b0623f9b613fcd94912a38845b
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2019
ms.locfileid: "65881700"
---
# <a name="asynchronous-scenarios-using-http-tcp-or-named-pipe"></a><span data-ttu-id="c6a76-102">HTTP、TCP、または名前付きパイプを使用した非同期シナリオ</span><span class="sxs-lookup"><span data-stu-id="c6a76-102">Asynchronous Scenarios using HTTP, TCP, or Named-Pipe</span></span>
<span data-ttu-id="c6a76-103">ここでは、マルチスレッド要求で HTTP、TCP、または名前付きパイプを使用したときの、さまざまな非同期要求/応答シナリオでのアクティビティおよび転送について説明します。</span><span class="sxs-lookup"><span data-stu-id="c6a76-103">This topic describes the activities and transfers for different asynchronous request/reply scenarios, with multithreaded requests using HTTP, TCP, or named pipe.</span></span>  
  
## <a name="asynchronous-requestreply-without-errors"></a><span data-ttu-id="c6a76-104">エラーを伴わない非同期要求/応答</span><span class="sxs-lookup"><span data-stu-id="c6a76-104">Asynchronous Request/Reply without Errors</span></span>  
 <span data-ttu-id="c6a76-105">ここでは、マルチスレッド クライアントを使用したときの、非同期要求/応答シナリオでのアクティビティおよび転送について説明します。</span><span class="sxs-lookup"><span data-stu-id="c6a76-105">This section describes the activities and transfers for an asynchronous request/reply scenario, with multithreaded clients.</span></span>  
  
 <span data-ttu-id="c6a76-106">呼び出し元アクティビティは、`beginCall` が返され、`endCall` が返されると終了します。</span><span class="sxs-lookup"><span data-stu-id="c6a76-106">The caller activity terminates when `beginCall` returns, and `endCall` returns.</span></span> <span data-ttu-id="c6a76-107">コールバックが呼び出されたときは、そのコールバックが返されます。</span><span class="sxs-lookup"><span data-stu-id="c6a76-107">If a callback is called, the callback returns.</span></span>  
  
 <span data-ttu-id="c6a76-108">呼び出されたアクティビティは、`beginCall` が返され、`endCall` が返されると終了します。または、そのアクティビティからコールバックが呼び出された場合は、コールバックが返されると終了します。</span><span class="sxs-lookup"><span data-stu-id="c6a76-108">The called activity terminates when `beginCall` returns, `endCall` returns, or when the callback returns if it was called from that activity.</span></span>  
  
### <a name="asynchronous-client-without-callback"></a><span data-ttu-id="c6a76-109">コールバックを伴わない非同期クライアント</span><span class="sxs-lookup"><span data-stu-id="c6a76-109">Asynchronous Client without Callback</span></span>  
  
#### <a name="propagation-is-enabled-on-both-sides-using-http"></a><span data-ttu-id="c6a76-110">HTTP を使用して、両方の側で伝達が有効になっている場合</span><span class="sxs-lookup"><span data-stu-id="c6a76-110">Propagation is Enabled on Both Sides, using HTTP</span></span>  
 ![PropagateActivity に設定されていないコールバックを伴う非同期クライアント両方の側では true。](./media/asynchronous-scenarios-using-http-tcp-or-named-pipe/asynchronous-client-no-callback.gif)   
  
 <span data-ttu-id="c6a76-112">場合`propagateActivity` = `true`ProcessMessage は ProcessAction アクティビティへの転送を示します。</span><span class="sxs-lookup"><span data-stu-id="c6a76-112">If `propagateActivity`=`true`, ProcessMessage indicates which ProcessAction activity to transfer to.</span></span>  
  
 <span data-ttu-id="c6a76-113">HTTP ベースのシナリオでは、最初に送信するメッセージで "バイトを受信" が呼び出され、要求の有効期間だけ存在します。</span><span class="sxs-lookup"><span data-stu-id="c6a76-113">For HTTP-based scenarios, ReceiveBytes is invoked on the first message to send, and exists for the lifetime of the request.</span></span>  
  
#### <a name="propagation-is-disabled-on-either-sides-using-http"></a><span data-ttu-id="c6a76-114">HTTP を使用して、両方の側で伝達が無効になっている場合</span><span class="sxs-lookup"><span data-stu-id="c6a76-114">Propagation is Disabled on Either Sides, using HTTP</span></span>  
 <span data-ttu-id="c6a76-115">場合`propagateActivity` = `false`いずれかの側では、ProcessMessage は示しませんアクティビティへの転送を示しません。</span><span class="sxs-lookup"><span data-stu-id="c6a76-115">If `propagateActivity`=`false` on either side, ProcessMessage does not indicate which ProcessAction activity to transfer to.</span></span> <span data-ttu-id="c6a76-116">したがって、新しい ID を使用して、新しい一時的な "アクションを処理" アクティビティが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="c6a76-116">Therefore, a new temporary ProcessAction activity with a new ID is invoked.</span></span> <span data-ttu-id="c6a76-117">非同期応答と ServiceModel コード内の要求が一致する場合は、アクティビティ ID をローカル コンテキストから取得できます。</span><span class="sxs-lookup"><span data-stu-id="c6a76-117">When the asynchronous response is matched to the request in ServiceModel code, the Activity ID can be retrieved from the local context.</span></span> <span data-ttu-id="c6a76-118">その ID を使用して、実際の "アクションを処理" アクティビティに転送できます。</span><span class="sxs-lookup"><span data-stu-id="c6a76-118">The actual ProcessAction activity can be transferred to with that ID.</span></span>  
  
 ![非同期クライアント propagateActivity を右辺でも左辺でも false に設定されているコールバックなし。](./media/asynchronous-scenarios-using-http-tcp-or-named-pipe/asynchronous-scenario-propagation-disabled-either-side.gif)  
    
 <span data-ttu-id="c6a76-120">HTTP ベースのシナリオでは、最初に送信するメッセージで "バイトを受信" が呼び出され、要求の有効期間だけ存在します。</span><span class="sxs-lookup"><span data-stu-id="c6a76-120">For HTTP-based scenarios, ReceiveBytes is invoked on the first message to send, and exists for the lifetime of the request.</span></span>  
  
 <span data-ttu-id="c6a76-121">プロセスのアクション アクティビティが、非同期クライアントで作成されたときに`propagateActivity` = `false`呼び出し元または呼び出し先、および応答メッセージに Action ヘッダーが含まれていない場合。</span><span class="sxs-lookup"><span data-stu-id="c6a76-121">A Process Action activity is created on an asynchronous client when `propagateActivity`=`false` at the caller or callee, and when the response message does not include an Action header.</span></span>  
  
#### <a name="propagation-is-enabled-on-both-sides-using-tcp-or-named-pipe"></a><span data-ttu-id="c6a76-122">TCP または名前付きパイプを使用して、両方の側で伝達が有効になっている場合</span><span class="sxs-lookup"><span data-stu-id="c6a76-122">Propagation is Enabled on Both Sides, using TCP or Named Pipe</span></span>  
 ![非同期のクライアントにコールバックが propagateActivity が両方の側で true と名前付きに設定されていない/TCP パイプします。](./media/asynchronous-scenarios-using-http-tcp-or-named-pipe/asynchronous-scenario-propagation-enabled-using-tcp.gif)  
  
 <span data-ttu-id="c6a76-124">名前付きパイプまたは TCP ベースのシナリオでは、クライアントが開かれるときに "バイトを受信" が呼び出され、接続の有効期間だけ存在します。</span><span class="sxs-lookup"><span data-stu-id="c6a76-124">For a Named-Pipe or TCP-based scenario, ReceiveBytes is invoked when the client is opened, and exists for the lifetime of the connection.</span></span>  
  
 <span data-ttu-id="c6a76-125">最初の図のような場合は`propagateActivity` = `true`ProcessMessage は ProcessAction アクティビティへの転送を示します。</span><span class="sxs-lookup"><span data-stu-id="c6a76-125">Similar to the first image, if `propagateActivity`=`true`, ProcessMessage indicates which ProcessAction activity to transfer to.</span></span>  
  
#### <a name="propagation-is-disabled-on-either-sides-using-tcp-or-named-pipe"></a><span data-ttu-id="c6a76-126">TCP または名前付きパイプを使用して、両方の側で伝達が無効になっている場合</span><span class="sxs-lookup"><span data-stu-id="c6a76-126">Propagation is Disabled on Either Sides, using TCP or Named Pipe</span></span>  
 <span data-ttu-id="c6a76-127">名前付きパイプまたは TCP ベースのシナリオでは、クライアントが開かれるときに "バイトを受信" が呼び出され、接続の有効期間だけ存在します。</span><span class="sxs-lookup"><span data-stu-id="c6a76-127">For a Named-Pipe or TCP-based scenario, ReceiveBytes is invoked when the client is opened, and exists for the lifetime of the connection.</span></span>  
  
 <span data-ttu-id="c6a76-128">2 番目の図のような場合は`propagateActivity` = `false`いずれかの側では、ProcessMessage は示しませんアクティビティへの転送を示しません。</span><span class="sxs-lookup"><span data-stu-id="c6a76-128">Similar to the second image, if `propagateActivity`=`false` on either side, ProcessMessage does not indicate which ProcessAction activity to transfer to.</span></span> <span data-ttu-id="c6a76-129">したがって、新しい ID を使用して、新しい一時的な "アクションを処理" アクティビティが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="c6a76-129">Therefore, a new temporary ProcessAction activity with a new ID is invoked.</span></span> <span data-ttu-id="c6a76-130">非同期応答と ServiceModel コード内の要求が一致する場合は、アクティビティ ID をローカル コンテキストから取得できます。</span><span class="sxs-lookup"><span data-stu-id="c6a76-130">When the asynchronous response is matched to the request in ServiceModel code, the Activity ID can be retrieved from the local context.</span></span> <span data-ttu-id="c6a76-131">その ID を使用して、実際の "アクションを処理" アクティビティに転送できます。</span><span class="sxs-lookup"><span data-stu-id="c6a76-131">The actual ProcessAction activity can be transferred to with that ID.</span></span>  
  
 ![非同期クライアント propagateActivity の右辺でも左辺でも false に設定し、パイプ/TCP という名前の場所、コールバックなし。](./media/asynchronous-scenarios-using-http-tcp-or-named-pipe/asynchronous-scenario-propagation-disabled-using-tcp.gif)  
    
### <a name="asynchronous-client-with-callback"></a><span data-ttu-id="c6a76-133">コールバックを伴う非同期クライアント</span><span class="sxs-lookup"><span data-stu-id="c6a76-133">Asynchronous client with Callback</span></span>  
 <span data-ttu-id="c6a76-134">このシナリオでは、コールバックと `endCall` に対するアクティビティ G と A’、およびその転送 (送受信) が追加されています。</span><span class="sxs-lookup"><span data-stu-id="c6a76-134">This scenario adds activities G and A’, for the callback and `endCall`, and their transfers in/out.</span></span>  
  
 <span data-ttu-id="c6a76-135">このセクションでは HTTP との使用方法を示しますのみ`propragateActivity` =`true`します。</span><span class="sxs-lookup"><span data-stu-id="c6a76-135">This section only demonstrates using HTTP with `propragateActivity`=`true`.</span></span> <span data-ttu-id="c6a76-136">ただし、それ以外の場合にも適用の他のアクティビティおよび転送 (つまり、 `propagateActivity` = `false`、TCP または名前付きパイプを使用して)。</span><span class="sxs-lookup"><span data-stu-id="c6a76-136">However, the additional activities and transfers also apply to the other cases (that is, `propagateActivity`=`false`, using TCP or Named-Pipe).</span></span>  
  
 <span data-ttu-id="c6a76-137">クライアントがユーザー コードを呼び出して結果の準備が完了したことを通知すると、コールバックは新しいアクティビティ (G) を作成します。</span><span class="sxs-lookup"><span data-stu-id="c6a76-137">The callback creates a new activity (G) when the client calls user code to notify that results are ready.</span></span> <span data-ttu-id="c6a76-138">ユーザー コードは、次に、コールバック内 (図 5 を参照) またはコールバック外 (図 6 を参照) で `endCall` を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="c6a76-138">User code then calls `endCall` within the callback (as shown in Figure 5) or outside the callback (Figure 6).</span></span> <span data-ttu-id="c6a76-139">どのユーザー アクティビティが不明なので`endCall`が呼び出されるから、このアクティビティがというラベルが付いた`A’`します。</span><span class="sxs-lookup"><span data-stu-id="c6a76-139">Because it is not known which user activity `endCall` is being called from, this activity is labeled `A’`.</span></span> <span data-ttu-id="c6a76-140">A’ と A が同じである場合もありますし、異なる場合もあります。</span><span class="sxs-lookup"><span data-stu-id="c6a76-140">It is possible that A’ can be identical to or different from A.</span></span>  
  
 ![非同期コールバック、コールバックで endcall でクライアントを示しています。](./media/asynchronous-scenarios-using-http-tcp-or-named-pipe/asynchronous-client-callback-endcall-in-callback.gif)  
    
 ![非同期コールバック、endcall コールバック外でクライアントを示しています。](./media/asynchronous-scenarios-using-http-tcp-or-named-pipe/asynchronous-client-callback-endcall-outside-callback.gif)  
    
### <a name="asynchronous-server-with-callback"></a><span data-ttu-id="c6a76-143">コールバックを伴う非同期サーバー</span><span class="sxs-lookup"><span data-stu-id="c6a76-143">Asynchronous Server with Callback</span></span>  
 ![コールバックを伴う非同期サーバーを示しています。](./media/asynchronous-scenarios-using-http-tcp-or-named-pipe/asynchronous-server-callback.gif)  
    
 <span data-ttu-id="c6a76-145">チャネル スタックは、"メッセージを受信" でクライアントをコールバックします。この処理のトレースは、"要求を処理" アクティビティ自体で出力されます。</span><span class="sxs-lookup"><span data-stu-id="c6a76-145">The channel stack calls back the client on Message Receive: traces for this processing are emitted in the ProcessRequest activity itself.</span></span>  
  
## <a name="asynchronous-requestreply-with-errors"></a><span data-ttu-id="c6a76-146">エラーを伴う非同期要求/応答</span><span class="sxs-lookup"><span data-stu-id="c6a76-146">Asynchronous Request/Reply with Errors</span></span>  
 <span data-ttu-id="c6a76-147">エラー メッセージは、`endCall` 中に受信されます。</span><span class="sxs-lookup"><span data-stu-id="c6a76-147">Fault message errors are received during `endCall`.</span></span> <span data-ttu-id="c6a76-148">この点を除き、アクティビティおよび転送は前のシナリオと同様です。</span><span class="sxs-lookup"><span data-stu-id="c6a76-148">Otherwise, activities and transfers are similar to previous scenarios.</span></span>  
  
## <a name="asynchronous-one-way-with-or-without-errors"></a><span data-ttu-id="c6a76-149">エラーを伴う/伴わない非同期一方向要求/応答</span><span class="sxs-lookup"><span data-stu-id="c6a76-149">Asynchronous One-Way with or without Errors</span></span>  
 <span data-ttu-id="c6a76-150">クライアントに返される応答やエラーはありません。</span><span class="sxs-lookup"><span data-stu-id="c6a76-150">No response or fault is returned to the client.</span></span>
