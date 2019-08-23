---
title: <reliableSession>
ms.date: 03/30/2017
ms.assetid: 129b4a59-37f0-4030-b664-03795d257d29
ms.openlocfilehash: 548c4884ecd2f4b9a71fcc9d6647a9e258b183c1
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69934248"
---
# <a name="reliablesession"></a><span data-ttu-id="db044-101">\<reliableSession ></span><span class="sxs-lookup"><span data-stu-id="db044-101">\<reliableSession></span></span>
<span data-ttu-id="db044-102">WS-ReliableMessaging の設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="db044-102">Defines setting for WS-Reliable Messaging.</span></span> <span data-ttu-id="db044-103">この要素がカスタム バインドに追加される場合、その結果となるチャネルにより、正確に 1 回の配信保証をサポートできます。</span><span class="sxs-lookup"><span data-stu-id="db044-103">When this element is added to a custom binding, the resulting channel can support exactly-once delivery assurances.</span></span>  
  
 <span data-ttu-id="db044-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="db044-104">\<system.serviceModel></span></span>  
<span data-ttu-id="db044-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="db044-105">\<bindings></span></span>  
<span data-ttu-id="db044-106">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="db044-106">\<customBinding></span></span>  
<span data-ttu-id="db044-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="db044-107">\<binding></span></span>  
<span data-ttu-id="db044-108">\<reliableSession ></span><span class="sxs-lookup"><span data-stu-id="db044-108">\<reliableSession></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="db044-109">構文</span><span class="sxs-lookup"><span data-stu-id="db044-109">Syntax</span></span>  
  
```xml  
<reliableSession acknowledgementInterval="TimeSpan"
                 flowControlEnabled="Boolean"
                 inactivityTimeout="TimeSpan"
                 maxPendingChannels="Integer"
                 maxRetryCount="Integer"
                 maxTransferWindowSize="Integer"
                 reliableMessagingVersion="Default/WSReliableMessagingFebruary2005/WSReliableMessaging11"
                 ordered="Boolean" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="db044-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="db044-110">Attributes and Elements</span></span>  
 <span data-ttu-id="db044-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="db044-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="db044-112">属性</span><span class="sxs-lookup"><span data-stu-id="db044-112">Attributes</span></span>  
  
|<span data-ttu-id="db044-113">属性</span><span class="sxs-lookup"><span data-stu-id="db044-113">Attribute</span></span>|<span data-ttu-id="db044-114">説明</span><span class="sxs-lookup"><span data-stu-id="db044-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="db044-115">acknowledgementInterval</span><span class="sxs-lookup"><span data-stu-id="db044-115">acknowledgementInterval</span></span>|<span data-ttu-id="db044-116">そのポイントまで受信したメッセージの受信確認の送信をチャネルが待機する最大時間間隔を含む <xref:System.TimeSpan>。</span><span class="sxs-lookup"><span data-stu-id="db044-116">A <xref:System.TimeSpan> that contains the maximum time interval the channel is going to wait to send an acknowledgment for messages received up to that point.</span></span> <span data-ttu-id="db044-117">既定値は 00:00:0.2 です。</span><span class="sxs-lookup"><span data-stu-id="db044-117">The default is 00:00:0.2.</span></span>|  
|<span data-ttu-id="db044-118">flowControlEnabled</span><span class="sxs-lookup"><span data-stu-id="db044-118">flowControlEnabled</span></span>|<span data-ttu-id="db044-119">高度なフロー制御を有効にするかどうかを示すブール値。WS-ReliableMessaging のフロー制御の Microsoft 固有の実装です。</span><span class="sxs-lookup"><span data-stu-id="db044-119">A Boolean value that indicates whether advanced flow control, a Microsoft-specific implementation of flow control for WS-Reliable messaging, is activated.</span></span> <span data-ttu-id="db044-120">既定値は、`true` です。</span><span class="sxs-lookup"><span data-stu-id="db044-120">The default is `true`.</span></span>|  
|<span data-ttu-id="db044-121">inactivityTimeout</span><span class="sxs-lookup"><span data-stu-id="db044-121">inactivityTimeout</span></span>|<span data-ttu-id="db044-122">他の通信相手がチャネルにメッセージを送信せずにいられる最長期間を指定する <xref:System.TimeSpan>。他の通信相手がメッセージを送信しない期間がこの値を超えると、チャネルでエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="db044-122">A <xref:System.TimeSpan> that specifies the maximum duration that the channel is going to allow the other communication party not to send any messages, before faulting the channel.</span></span> <span data-ttu-id="db044-123">既定値は 00:10:00 です。</span><span class="sxs-lookup"><span data-stu-id="db044-123">The default is 00:10:00.</span></span><br /><br /> <span data-ttu-id="db044-124">チャネルでのアクティビティは、アプリケーションまたはインフラストラクチャのメッセージを受信するように定義されています。</span><span class="sxs-lookup"><span data-stu-id="db044-124">Activity on a channel is defined as receiving an application or infrastructure messages.</span></span> <span data-ttu-id="db044-125">このプロパティは、アクティブでないセッションを維持する最長期間を制御します。</span><span class="sxs-lookup"><span data-stu-id="db044-125">This property controls the maximum amount of time to keep an inactive session alive.</span></span> <span data-ttu-id="db044-126">反応のない時間がこれより長く経過すると、インフラストラクチャによってセッションは中止され、チャネルはエラーとなります。</span><span class="sxs-lookup"><span data-stu-id="db044-126">If longer time passes with no activity, the session is aborted by the infrastructure and the channel faults.</span></span> <span data-ttu-id="db044-127">**注:** アプリケーションでは定期的にメッセージを送信して接続を維持する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="db044-127">**Note:**  It is not necessary for the application to periodically send messages to keep the connection alive.</span></span>|  
|<span data-ttu-id="db044-128">maxPendingChannels</span><span class="sxs-lookup"><span data-stu-id="db044-128">maxPendingChannels</span></span>|<span data-ttu-id="db044-129">受け入れるリスナーを待機できるチャネルの最大数を指定する整数。</span><span class="sxs-lookup"><span data-stu-id="db044-129">An integer that specifies the maximum number of channels that can wait on the listener to be accepted.</span></span> <span data-ttu-id="db044-130">この値は、1 ～ 16384 (1 と 16384を含む) のいずれかです。</span><span class="sxs-lookup"><span data-stu-id="db044-130">This value should be between 1 to 16384 inclusive.</span></span> <span data-ttu-id="db044-131">既定値は 4 です。</span><span class="sxs-lookup"><span data-stu-id="db044-131">The default is 4.</span></span><br /><br /> <span data-ttu-id="db044-132">チャネルは、受け入れを待っている間は保留状態になります。</span><span class="sxs-lookup"><span data-stu-id="db044-132">Channels are pending when they are waiting to be accepted.</span></span> <span data-ttu-id="db044-133">制限に達すると、チャネルは作成されなくなります。</span><span class="sxs-lookup"><span data-stu-id="db044-133">Once that limit is reached, no channels are created.</span></span> <span data-ttu-id="db044-134">正確には、この数が (保留状態のチャネルの受け入れによって) 減少するまで、保留モードにされます。</span><span class="sxs-lookup"><span data-stu-id="db044-134">Rather, they are put in pending mode until this number goes down (by accepting pending channels).</span></span> <span data-ttu-id="db044-135">これはファクトリごとの制限です。</span><span class="sxs-lookup"><span data-stu-id="db044-135">This is a per-factory limit.</span></span><br /><br /> <span data-ttu-id="db044-136">しきい値に達した後に、リモート アプリケーションが新しい信頼できるセッションを確立しようとした場合、要求は拒否され、この原因となる open 操作でエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="db044-136">When the threshold is reached and a remote application tries to establish a new reliable session, the request is denied and the open operation that prompted this faults.</span></span> <span data-ttu-id="db044-137">この制限は、保留状態の送信チャネルの数には適用されません。</span><span class="sxs-lookup"><span data-stu-id="db044-137">This limit does not apply to the number of pending outgoing channels.</span></span>|  
|<span data-ttu-id="db044-138">maxRetryCount</span><span class="sxs-lookup"><span data-stu-id="db044-138">maxRetryCount</span></span>|<span data-ttu-id="db044-139">基になるチャネルで Send を呼び出すことで、信頼できるチャネルが受信確認を受信していないメッセージの再転送を試みる最大回数を指定する整数。</span><span class="sxs-lookup"><span data-stu-id="db044-139">An integer that specifies the maximum number of times a reliable channel attempts to retransmit a message it has not received an acknowledgment for, by calling Send on its underlying channel.</span></span><br /><br /> <span data-ttu-id="db044-140">この値は、ゼロより大きい値である必要があります。</span><span class="sxs-lookup"><span data-stu-id="db044-140">This value should be greater than zero.</span></span> <span data-ttu-id="db044-141">既定値は 8 です。</span><span class="sxs-lookup"><span data-stu-id="db044-141">The default is 8.</span></span><br /><br /> <span data-ttu-id="db044-142">この値は、0 を超えた整数にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="db044-142">This value should be an integer greater than zero.</span></span> <span data-ttu-id="db044-143">最後の再転送後に受信確認が受信されない場合、チャネルでエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="db044-143">If an acknowledgment is not received after the last retransmission, the channel faults.</span></span><br /><br /> <span data-ttu-id="db044-144">メッセージは、受信側でその配信が確認されている場合、転送されたと見なされます。</span><span class="sxs-lookup"><span data-stu-id="db044-144">A message is considered to be transferred if its delivery at the recipient has been acknowledged by the recipient.</span></span><br /><br /> <span data-ttu-id="db044-145">転送済みのメッセージの受信確認が一定時間内に受信されない場合、インフラストラクチャは、自動的にそのメッセージを再転送します。</span><span class="sxs-lookup"><span data-stu-id="db044-145">If an acknowledgment has not been received within a certain amount of time for a message that has been transmitted, the infrastructure automatically retransmits the message.</span></span> <span data-ttu-id="db044-146">インフラストラクチャは、このプロパティで指定された回数まで、メッセージを再送信しようとします。</span><span class="sxs-lookup"><span data-stu-id="db044-146">The infrastructure tries to resend the message for at most the number of times specified by this property.</span></span> <span data-ttu-id="db044-147">最後の再転送後に受信確認が受信されない場合、チャネルでエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="db044-147">If an acknowledgment is not received after the last retransmission, the channel faults.</span></span><br /><br /> <span data-ttu-id="db044-148">インフラストラクチャは、指数バックオフ アルゴリズムを使用し、計算された平均ラウンドトリップ時間に基づいて、いつ再転送するかを判断します。</span><span class="sxs-lookup"><span data-stu-id="db044-148">The infrastructure uses an exponential back-off algorithm to determine when to retransmit, based on a computed average round-trip time.</span></span> <span data-ttu-id="db044-149">時間は、まず再転送の 1 秒前に開始され、試行ごとに遅延が 2 倍にされます。この結果、最初の転送試行から最後の再転送試行までに約 8.5 分かかります。</span><span class="sxs-lookup"><span data-stu-id="db044-149">The time initially starts at 1 second before retransmission and doubling the delay with every attempt, which results in approximately 8.5 minutes passing between the first transmission attempt and the last retransmission attempt.</span></span> <span data-ttu-id="db044-150">最初の再転送試行のタイミングは、計算されたラウンドトリップ時間に従って調整されるので、試行にかかる時間延長はさまざまです。</span><span class="sxs-lookup"><span data-stu-id="db044-150">The time for the first retransmission attempt is adjusted according to the calculated round-trip time and the resulting stretch of time that those attempts take varies accordingly.</span></span> <span data-ttu-id="db044-151">これにより、再転送のタイミングをさまざまなネットワーク条件に動的に適用できます。</span><span class="sxs-lookup"><span data-stu-id="db044-151">This allows the retransmission time to dynamically adapt to varying network conditions.</span></span>|  
|<span data-ttu-id="db044-152">maxTransferWindowSize</span><span class="sxs-lookup"><span data-stu-id="db044-152">maxTransferWindowSize</span></span>|<span data-ttu-id="db044-153">バッファーの最大サイズを指定する整数。</span><span class="sxs-lookup"><span data-stu-id="db044-153">An integer that specifies the maximum size of the buffer.</span></span> <span data-ttu-id="db044-154">有効値は 1 ～ 4096 の範囲です。</span><span class="sxs-lookup"><span data-stu-id="db044-154">Valid values are from 1 to 4096 inclusive.</span></span><br /><br /> <span data-ttu-id="db044-155">クライアントでは、この属性は、まだ受信側で受信が確認されていないメッセージを保持するために信頼できるチャネルが使用するバッファーの最大サイズを定義します。</span><span class="sxs-lookup"><span data-stu-id="db044-155">On the client, this attribute defines the maximum size of the buffer used by a reliable channel to hold messages not yet acknowledged by the receiver.</span></span> <span data-ttu-id="db044-156">クォータの単位はメッセージです。</span><span class="sxs-lookup"><span data-stu-id="db044-156">The unit of the quota is a message.</span></span> <span data-ttu-id="db044-157">バッファーがいっぱいになると、それ以降の SEND 操作がブロックされます。</span><span class="sxs-lookup"><span data-stu-id="db044-157">If the buffer is full, further SEND operations are blocked.</span></span><br /><br /> <span data-ttu-id="db044-158">受信側では、この属性は、まだアプリケーションにディスパッチされていない受信メッセージを格納するためにチャネルが使用するバッファーの最大サイズを定義します。</span><span class="sxs-lookup"><span data-stu-id="db044-158">On the receiver, this attribute defines the maximum size of the buffer used by the channel to store incoming messages not yet dispatched to the application.</span></span> <span data-ttu-id="db044-159">バッファーがいっぱいになると、それ以降のメッセージは、受信側によって通知なしに自動的に削除されるので、クライアントによる再転送が必要になります。</span><span class="sxs-lookup"><span data-stu-id="db044-159">If the buffer is full, further messages are silently dropped by the receiver and require retransmission by the client.</span></span>|  
|<span data-ttu-id="db044-160">ordered</span><span class="sxs-lookup"><span data-stu-id="db044-160">ordered</span></span>|<span data-ttu-id="db044-161">メッセージが送信された順序で到着されることを保証するかどうかを指定するブール値。</span><span class="sxs-lookup"><span data-stu-id="db044-161">A Boolean that specifies whether messages are guaranteed to arrive in the order they were sent.</span></span> <span data-ttu-id="db044-162">この設定が `false` の場合、メッセージは送信された順序で到着しません。</span><span class="sxs-lookup"><span data-stu-id="db044-162">If this setting is `false`, messages can arrive out of order.</span></span> <span data-ttu-id="db044-163">既定値は、`true` です。</span><span class="sxs-lookup"><span data-stu-id="db044-163">The default is `true`.</span></span>|  
|<span data-ttu-id="db044-164">reliableMessagingVersion</span><span class="sxs-lookup"><span data-stu-id="db044-164">reliableMessagingVersion</span></span>|<span data-ttu-id="db044-165">使用する WS-ReliableMessaging バージョンを指定する <xref:System.ServiceModel.ReliableMessagingVersion> の有効な値。</span><span class="sxs-lookup"><span data-stu-id="db044-165">A valid value from <xref:System.ServiceModel.ReliableMessagingVersion> that specifies the WS-ReliableMessaging version to be used.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="db044-166">子要素</span><span class="sxs-lookup"><span data-stu-id="db044-166">Child Elements</span></span>  
 <span data-ttu-id="db044-167">なし</span><span class="sxs-lookup"><span data-stu-id="db044-167">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="db044-168">親要素</span><span class="sxs-lookup"><span data-stu-id="db044-168">Parent Elements</span></span>  
  
|<span data-ttu-id="db044-169">要素</span><span class="sxs-lookup"><span data-stu-id="db044-169">Element</span></span>|<span data-ttu-id="db044-170">説明</span><span class="sxs-lookup"><span data-stu-id="db044-170">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="db044-171">\<binding></span><span class="sxs-lookup"><span data-stu-id="db044-171">\<binding></span></span>](../../../misc/binding.md)|<span data-ttu-id="db044-172">カスタム バインドのすべてのバインド機能を定義します。</span><span class="sxs-lookup"><span data-stu-id="db044-172">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="db044-173">Remarks</span><span class="sxs-lookup"><span data-stu-id="db044-173">Remarks</span></span>  
 <span data-ttu-id="db044-174">信頼できるセッションは、信頼できるメッセージとセッションに関する機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="db044-174">Reliable sessions provide features for reliable messaging and sessions.</span></span> <span data-ttu-id="db044-175">信頼できるメッセージは、エラー時に通信を再試行するほか、メッセージの順次到着などの配信の保証を指定できるようにします。</span><span class="sxs-lookup"><span data-stu-id="db044-175">Reliable messaging retries communication on failure and allows delivery assurances such as in-order arrival of messages to be specified.</span></span> <span data-ttu-id="db044-176">セッションでは、呼び出し間でクライアントの状態が保持されます。</span><span class="sxs-lookup"><span data-stu-id="db044-176">Sessions maintain state for clients between calls.</span></span> <span data-ttu-id="db044-177">この要素には、オプションとして、順序付けされたメッセージ配信を行う機能も用意されています。</span><span class="sxs-lookup"><span data-stu-id="db044-177">This element also optionally provides ordered message delivery.</span></span> <span data-ttu-id="db044-178">この実装されたセッションは、SOAP およびトランスポート中継局を通過できます。</span><span class="sxs-lookup"><span data-stu-id="db044-178">This implemented session can cross SOAP and transport intermediaries.</span></span>  
  
 <span data-ttu-id="db044-179">各バインド要素は、メッセージの送信または受信時の処理手順を表します。</span><span class="sxs-lookup"><span data-stu-id="db044-179">Each binding element represents a processing step when sending or receiving messages.</span></span> <span data-ttu-id="db044-180">実行時に、バインディング要素は、メッセージの送受信に求められる送信および受信チャネル スタックを作成するために必要なチャネル ファクトリとリスナーを作成します。</span><span class="sxs-lookup"><span data-stu-id="db044-180">At runtime, binding elements create the channel factories and listeners that are necessary to build outgoing and incoming channel stacks required to send and receive messages.</span></span> <span data-ttu-id="db044-181">`reliableSession` が提供するスタック内のオプションの層は、エンドポイント間に信頼できるセッションを確立し、このセッションの動作を構成することができます。</span><span class="sxs-lookup"><span data-stu-id="db044-181">The `reliableSession` provides an optional layer in the stack that can establish a reliable session between endpoints and configure the behavior of this session.</span></span>  
  
 <span data-ttu-id="db044-182">詳細については、「[信頼できるセッション](../../../wcf/feature-details/reliable-sessions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="db044-182">For more information, see [Reliable Sessions](../../../wcf/feature-details/reliable-sessions.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="db044-183">例</span><span class="sxs-lookup"><span data-stu-id="db044-183">Example</span></span>  
 <span data-ttu-id="db044-184">次の例では、さまざまなトランスポートとメッセージ エンコーディング要素を使用し、特に、クライアントの状態を保持し、配信順序を保証することを指定する、信頼できるセッションを有効化することによって、カスタム バインドを構成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="db044-184">The following example demonstrates how to configure a custom binding with various transport and message encoding elements, especially enabling reliable sessions, which maintains client state and specifies in-order delivery assurances.</span></span> <span data-ttu-id="db044-185">この機能は、クライアントとサービスのアプリケーション構成ファイルで構成されます。</span><span class="sxs-lookup"><span data-stu-id="db044-185">This feature is configured in the application configuration files for the client and service.</span></span> <span data-ttu-id="db044-186">サービスの構成の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="db044-186">The example show the service configuration.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
  <system.serviceModel>
    <services>
      <service name="Microsoft.ServiceModel.Samples.CalculatorService"
               behaviorConfiguration="CalculatorServiceBehavior">
        <!-- This endpoint is exposed at the base address provided by host: http://localhost/servicemodelsamples/service.svc -->
        <!-- specify customBinding binding and a binding configuration to use -->
        <endpoint address=""
                  binding="customBinding"
                  bindingConfiguration="Binding1"
                  contract="Microsoft.ServiceModel.Samples.ICalculator" />
        <!-- The mex endpoint is exposed at http://localhost/servicemodelsamples/service.svc/mex -->
        <endpoint address="mex"
                  binding="mexHttpBinding"
                  contract="IMetadataExchange" />
      </service>
    </services>
    <!-- custom binding configuration - configures HTTP transport, reliable sessions -->
    <bindings>
      <customBinding>
        <binding name="Binding1">
          <reliableSession />
          <security authenticationMode="SecureConversation"
                    requireSecurityContextCancellation="true">
          </security>
          <compositeDuplex />
          <oneWay />
          <textMessageEncoding messageVersion="Soap12WSAddressing10"
                               writeEncoding="utf-8" />
          <httpTransport authenticationScheme="Anonymous"
                         bypassProxyOnLocal="false"
                         hostNameComparisonMode="StrongWildcard"
                         proxyAuthenticationScheme="Anonymous"
                         realm=""
                         useDefaultWebProxy="true" />
        </binding>
      </customBinding>
    </bindings>
    <!--For debugging purposes set the includeExceptionDetailInFaults attribute to true-->
    <behaviors>
      <serviceBehaviors>
        <behavior name="CalculatorServiceBehavior">
          <serviceMetadata httpGetEnabled="True" />
          <serviceDebug includeExceptionDetailInFaults="False" />
        </behavior>
      </serviceBehaviors>
    </behaviors>
  </system.serviceModel>
</configuration>
```  
  
## <a name="see-also"></a><span data-ttu-id="db044-187">関連項目</span><span class="sxs-lookup"><span data-stu-id="db044-187">See also</span></span>

- <xref:System.ServiceModel.Configuration.ReliableSessionElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.ReliableSessionBindingElement>
- [<span data-ttu-id="db044-188">信頼できるセッション</span><span class="sxs-lookup"><span data-stu-id="db044-188">Reliable Sessions</span></span>](../../../wcf/feature-details/reliable-sessions.md)
- [<span data-ttu-id="db044-189">バインディング</span><span class="sxs-lookup"><span data-stu-id="db044-189">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="db044-190">バインディングの拡張</span><span class="sxs-lookup"><span data-stu-id="db044-190">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="db044-191">カスタム バインディング</span><span class="sxs-lookup"><span data-stu-id="db044-191">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="db044-192">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="db044-192">\<customBinding></span></span>](custombinding.md)
