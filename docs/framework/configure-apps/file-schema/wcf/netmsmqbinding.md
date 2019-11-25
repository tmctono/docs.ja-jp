---
title: <netMsmqBinding>
ms.date: 03/30/2017
ms.assetid: a68b44d7-7799-43a3-9e63-f07c782810a6
ms.openlocfilehash: 7456c6373c64e07b73e15e7e2bb229dce4032121
ms.sourcegitcommit: fbb8a593a511ce667992502a3ce6d8f65c594edf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/16/2019
ms.locfileid: "74140739"
---
# <a name="netmsmqbinding"></a><span data-ttu-id="58f9f-101">\<netMsmqBinding ></span><span class="sxs-lookup"><span data-stu-id="58f9f-101">\<netMsmqBinding></span></span>
<span data-ttu-id="58f9f-102">複数コンピューターの通信に適しているキューに置かれたバインディングを定義します。</span><span class="sxs-lookup"><span data-stu-id="58f9f-102">Defines a queued binding suitable for cross-machine communication.</span></span>  
  
<span data-ttu-id="58f9f-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="58f9f-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="58f9f-104">&nbsp; &nbsp;[ **\<system >** ](system-servicemodel.md) </span><span class="sxs-lookup"><span data-stu-id="58f9f-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="58f9f-105">&nbsp;&nbsp;&nbsp;&nbsp;\<[**バインド**](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="58f9f-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="58f9f-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**netMsmqBinding >**</span><span class="sxs-lookup"><span data-stu-id="58f9f-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<netMsmqBinding>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="58f9f-107">構文</span><span class="sxs-lookup"><span data-stu-id="58f9f-107">Syntax</span></span>  
  
```xml  
<netMsmqBinding>
  <binding closeTimeout="TimeSpan"
           customDeadLetterQueue="Uri"
           deadLetterQueue="Uri"
           durable="Boolean"
           exactlyOnce="Boolean"
           maxBufferPoolSize="Integer"
           maxReceivedMessageSize="Integer"
           maxRetryCycles="Integer"
           name="String"
           openTimeout="TimeSpan"
           poisonMessageHandling="Disabled/EnabledIfSupported"
           queueTransferProtocol="Native/Srmp/SrmpSecure"
           receiveErrorHandling="Drop/Fault/Move/Reject"
           receiveTimeout="TimeSpan"
           receiveRetryCount="Integer"
           rejectAfterLastRetry="Boolean"
           retryCycleDelay="TimeSpan"
           sendTimeout="TimeSpan"
           timeToLive="TimeSpan"
           useActiveDirectory="Boolean"
           useMsmqTracing="Boolean"
           useSourceJournal="Boolean">
    <security>
      <message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
               clientCredentialType="None/Windows/UserName/Certificate/InfoCard" />
      <transport msmqAuthenticationMode="None/WindowsDomain/Certificate"
                 msmqEncryptionAlgorithm="RC4Stream/AES"
                 msmqProtectionLevel="None/Sign/EncryptAndSign"
                 msmqSecureHashAlgorithm="MD5/SHA1/SHA256/SHA512" />
    </security>
    <readerQuotas maxArrayLength="Integer"
                  maxBytesPerRead="Integer"
                  maxDepth="Integer"
                  maxNameTableCharCount="Integer"
                  maxStringContentLength="Integer" />
  </binding>
</netMsmqBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="58f9f-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="58f9f-108">Attributes and Elements</span></span>  
 <span data-ttu-id="58f9f-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="58f9f-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="58f9f-110">属性</span><span class="sxs-lookup"><span data-stu-id="58f9f-110">Attributes</span></span>  
  
|<span data-ttu-id="58f9f-111">属性</span><span class="sxs-lookup"><span data-stu-id="58f9f-111">Attribute</span></span>|<span data-ttu-id="58f9f-112">説明</span><span class="sxs-lookup"><span data-stu-id="58f9f-112">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="58f9f-113">クローズ操作が完了するまでの期間を指定する <xref:System.TimeSpan> 値。</span><span class="sxs-lookup"><span data-stu-id="58f9f-113">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="58f9f-114">この値は必ず <xref:System.TimeSpan.Zero> 以上である必要があります。</span><span class="sxs-lookup"><span data-stu-id="58f9f-114">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="58f9f-115">既定値は 00:01:00 です。</span><span class="sxs-lookup"><span data-stu-id="58f9f-115">The default is 00:01:00.</span></span>|  
|`customDeadLetterQueue`|<span data-ttu-id="58f9f-116">アプリケーションごとの配信不能キューの場所が含まれている URI です。ここには、期限切れのメッセージや、転送または配信に失敗したメッセージが配置されます。</span><span class="sxs-lookup"><span data-stu-id="58f9f-116">A URI that contains the location of the per-application dead letter queue, where messages that have expired or that have failed transfer or delivery are placed.</span></span><br /><br /> <span data-ttu-id="58f9f-117">配信不能キューは、送信元アプリケーションのキュー マネージャーにある、配信に失敗した期限切れメッセージのキューです。</span><span class="sxs-lookup"><span data-stu-id="58f9f-117">The dead letter queue is a queue on the queue manager of the sending application for expired messages that have failed to be delivered.</span></span><br /><br /> <span data-ttu-id="58f9f-118"><xref:System.ServiceModel.MsmqBindingBase.CustomDeadLetterQueue%2A> によって指定される URI は、net.msmq スキームを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="58f9f-118">The URI that is specified by <xref:System.ServiceModel.MsmqBindingBase.CustomDeadLetterQueue%2A> must use the net.msmq scheme.</span></span>|  
|`deadLetterQueue`|<span data-ttu-id="58f9f-119">使用する配信不能キューがある場合にその種類を指定する <xref:System.ServiceModel.MsmqBindingBase.DeadLetterQueue%2A> 値。</span><span class="sxs-lookup"><span data-stu-id="58f9f-119">A <xref:System.ServiceModel.MsmqBindingBase.DeadLetterQueue%2A> value specifying which type of dead-letter queue to use, if any.</span></span><br /><br /> <span data-ttu-id="58f9f-120">配信不能キューは、アプリケーションへの配信に失敗したメッセージが転送される場所です。</span><span class="sxs-lookup"><span data-stu-id="58f9f-120">A dead-letter queue is the place where messages that have failed to be delivered to the application will be transferred.</span></span><br /><br /> <span data-ttu-id="58f9f-121">`exactlyOnce` 保証が必要なメッセージ (つまり、`exactlyOnce` 属性が `true` に設定される) の場合、この属性は、既定で MSMQ のトランザクション システム全体の配信不能キューになります。</span><span class="sxs-lookup"><span data-stu-id="58f9f-121">For messages that require `exactlyOnce` assurance (that is, the `exactlyOnce` attribute is set to `true`), this attribute defaults to the system-wide transactional dead-letter queue in MSMQ.</span></span><br /><br /> <span data-ttu-id="58f9f-122">保証が必要ないメッセージの場合、この属性の既定値は `null` です。</span><span class="sxs-lookup"><span data-stu-id="58f9f-122">For messages that require no assurances, this attribute defaults to `null`.</span></span>|  
|`durable`|<span data-ttu-id="58f9f-123">メッセージがキューで非揮発性か揮発性かを示すブール値です。</span><span class="sxs-lookup"><span data-stu-id="58f9f-123">A Boolean value that indicates whether the message is durable or volatile in the queue.</span></span> <span data-ttu-id="58f9f-124">非揮発性メッセージは、キュー マネージャーがクラッシュしても残り、揮発性メッセージは失われます。</span><span class="sxs-lookup"><span data-stu-id="58f9f-124">A durable message survives a queue manager crash, while a volatile message does not.</span></span> <span data-ttu-id="58f9f-125">アプリケーションで待ち時間の短縮が要求され、場合によってはメッセージが失われてもかまわない場合は、揮発性メッセージが適しています。</span><span class="sxs-lookup"><span data-stu-id="58f9f-125">Volatile messages are useful when applications require lower latency and can tolerate occasional lost messages.</span></span> <span data-ttu-id="58f9f-126">`exactlyOnce` 属性が `true` に設定されている場合、メッセージは永続的にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="58f9f-126">If the `exactlyOnce` attribute is set to `true`, the messages must be durable.</span></span> <span data-ttu-id="58f9f-127">既定値は、 `true`です。</span><span class="sxs-lookup"><span data-stu-id="58f9f-127">The default is `true`.</span></span>|  
|`exactlyOnce`|<span data-ttu-id="58f9f-128">このバインディングで処理される各メッセージが 1 回だけ受信されるかどうかを示すブール値です。</span><span class="sxs-lookup"><span data-stu-id="58f9f-128">A Boolean value that indicates whether each message processed by this binding is delivered only once.</span></span> <span data-ttu-id="58f9f-129">その後、送信側に配信エラーが通知されます。</span><span class="sxs-lookup"><span data-stu-id="58f9f-129">The sender will then be notified of delivery failures.</span></span> <span data-ttu-id="58f9f-130">`durable` が `false` の場合、この属性は無視されて、配信が保証されずにメッセージが転送されます。</span><span class="sxs-lookup"><span data-stu-id="58f9f-130">When `durable` is `false`, this attribute is ignored and messages are transferred without delivery assurance.</span></span> <span data-ttu-id="58f9f-131">既定値は、 `true`です。</span><span class="sxs-lookup"><span data-stu-id="58f9f-131">The default is `true`.</span></span> <span data-ttu-id="58f9f-132">詳細については、「<xref:System.ServiceModel.MsmqBindingBase.ExactlyOnce%2A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="58f9f-132">For more information, see <xref:System.ServiceModel.MsmqBindingBase.ExactlyOnce%2A>.</span></span>|  
|`maxBufferPoolSize`|<span data-ttu-id="58f9f-133">このバインディングに使用するバッファー プール サイズの上限を指定する整数。</span><span class="sxs-lookup"><span data-stu-id="58f9f-133">An integer that specifies the maximum buffer pool size for this binding.</span></span> <span data-ttu-id="58f9f-134">既定値は 8 です。</span><span class="sxs-lookup"><span data-stu-id="58f9f-134">The default is 8.</span></span>|  
|`maxReceivedMessageSize`|<span data-ttu-id="58f9f-135">このバインディングにより処理される最大メッセージ サイズ (ヘッダーを含む) をバイト単位で定義する正の整数です。</span><span class="sxs-lookup"><span data-stu-id="58f9f-135">A positive integer that defines the maximum message size, in bytes, including headers, that is processed by this binding.</span></span> <span data-ttu-id="58f9f-136">この制限を超えるメッセージの送信者が、SOAP エラーを受信します。</span><span class="sxs-lookup"><span data-stu-id="58f9f-136">The sender of a message exceeding this limit will receive a SOAP fault.</span></span> <span data-ttu-id="58f9f-137">メッセージは受信者によってドロップされ、トレース ログにこのイベントのエントリが作成されます。</span><span class="sxs-lookup"><span data-stu-id="58f9f-137">The receiver drops the message and creates an entry of the event in the trace log.</span></span> <span data-ttu-id="58f9f-138">既定値は 65536 です。</span><span class="sxs-lookup"><span data-stu-id="58f9f-138">The default is 65536.</span></span> <span data-ttu-id="58f9f-139">このメッセージ サイズの制限は、サービス拒否 (DoS) 攻撃への露出を制限するためのものです。</span><span class="sxs-lookup"><span data-stu-id="58f9f-139">This bound on message size is intended to limit exposure to Denial of Service (DoS) attacks.</span></span>|  
|`maxRetryCycles`|<span data-ttu-id="58f9f-140">有害メッセージ検出機能により使用される再試行サイクルの回数を示す整数です。</span><span class="sxs-lookup"><span data-stu-id="58f9f-140">An integer that indicates the number of retry cycles used by the poison-message detection feature.</span></span> <span data-ttu-id="58f9f-141">すべてのサイクルの配信試行にすべて失敗すると、メッセージは有害メッセージになります。</span><span class="sxs-lookup"><span data-stu-id="58f9f-141">A message becomes a poison message when it fails all delivery attempts of all cycles.</span></span> <span data-ttu-id="58f9f-142">既定値は 3 です。</span><span class="sxs-lookup"><span data-stu-id="58f9f-142">The default is 3.</span></span> <span data-ttu-id="58f9f-143">詳細については、「<xref:System.ServiceModel.MsmqBindingBase.MaxRetryCycles%2A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="58f9f-143">For more information, see <xref:System.ServiceModel.MsmqBindingBase.MaxRetryCycles%2A>.</span></span>|  
|`name`|<span data-ttu-id="58f9f-144">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="58f9f-144">Required attribute.</span></span> <span data-ttu-id="58f9f-145">バインディングの構成名を格納する文字列です。</span><span class="sxs-lookup"><span data-stu-id="58f9f-145">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="58f9f-146">この値は、バインディングの ID として使用されるため、一意にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="58f9f-146">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="58f9f-147">.NET Framework 4 以降では、バインドと動作に名前を付ける必要はありません。</span><span class="sxs-lookup"><span data-stu-id="58f9f-147">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="58f9f-148">既定の構成と無名のバインドおよび動作の詳細については、「 [WCF サービスの](../../../wcf/samples/simplified-configuration-for-wcf-services.md)構成と簡略化された構成の[簡略化](../../../wcf/simplified-configuration.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="58f9f-148">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|`openTimeout`|<span data-ttu-id="58f9f-149">実行中の操作が完了するまでの時間間隔を指定する <xref:System.TimeSpan> 値です。</span><span class="sxs-lookup"><span data-stu-id="58f9f-149">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="58f9f-150">この値は必ず <xref:System.TimeSpan.Zero> 以上である必要があります。</span><span class="sxs-lookup"><span data-stu-id="58f9f-150">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="58f9f-151">既定値は 00:01:00 です。</span><span class="sxs-lookup"><span data-stu-id="58f9f-151">The default is 00:01:00.</span></span>|  
|`QueueTransferProtocol`|<span data-ttu-id="58f9f-152">このバインディングが使用するキューに置かれた通信チャネルのトランスポートを指定する有効な <xref:System.ServiceModel.QueueTransferProtocol> 値。</span><span class="sxs-lookup"><span data-stu-id="58f9f-152">A valid <xref:System.ServiceModel.QueueTransferProtocol> value that specifies the queued communication channel transport that this binding uses.</span></span> <span data-ttu-id="58f9f-153">MSMQ は、SOAP リライアブル メッセージ プロトコルを使用する場合は Active Directory アドレス指定をサポートしません。</span><span class="sxs-lookup"><span data-stu-id="58f9f-153">MSMQ does not support Active Directory addressing when using SOAP Reliable Messaging Protocol.</span></span> <span data-ttu-id="58f9f-154">したがって、この属性を `Srmp` に設定したり、`useActiveDirectory` 属性が `true`に設定されているときに `Srmps` したりしないでください。</span><span class="sxs-lookup"><span data-stu-id="58f9f-154">Therefore, you should not set this attribute to `Srmp` or `Srmps` when the `useActiveDirectory` attribute is set to `true`.</span></span>|  
|`receiveErrorHandling`|<span data-ttu-id="58f9f-155">有害メッセージおよびディスパッチ不能メッセージの処理方法を指定する <xref:System.ServiceModel.ReceiveErrorHandling> 値。</span><span class="sxs-lookup"><span data-stu-id="58f9f-155">A <xref:System.ServiceModel.ReceiveErrorHandling> value that specifies how poison and nondispatchable messages are handled.</span></span>|  
|`receiveRetryCount`|<span data-ttu-id="58f9f-156">キュー マネージャーがメッセージを再試行キューに転送する前にメッセージ送信を試行する最大回数を指定する整数。</span><span class="sxs-lookup"><span data-stu-id="58f9f-156">An integer that specifies the maximum number of times the queue manager should attempt to send a message before transferring it to the retry queue.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="58f9f-157">受信操作が完了するまでの時間間隔を指定する <xref:System.TimeSpan> 値です。</span><span class="sxs-lookup"><span data-stu-id="58f9f-157">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="58f9f-158">この値は必ず <xref:System.TimeSpan.Zero> 以上である必要があります。</span><span class="sxs-lookup"><span data-stu-id="58f9f-158">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="58f9f-159">既定値は 00:10:00 です。</span><span class="sxs-lookup"><span data-stu-id="58f9f-159">The default is 00:10:00.</span></span>|  
|`retryCycleDelay`|<span data-ttu-id="58f9f-160">すぐに配信できなかったメッセージを配信しようとするときの、再試行サイクルの時間遅延を指定する TimeSpan 値です。</span><span class="sxs-lookup"><span data-stu-id="58f9f-160">A TimeSpan value that specifies the time delay between retry cycles when attempting to deliver a message that could not be delivered immediately.</span></span> <span data-ttu-id="58f9f-161">実際の待機時間はさらに長くなる場合があるため、この値で定義されるのは最小待機時間だけです。</span><span class="sxs-lookup"><span data-stu-id="58f9f-161">The value defines only the minimum wait time because actual wait time can be longer.</span></span> <span data-ttu-id="58f9f-162">既定値は、00:10:00 です。</span><span class="sxs-lookup"><span data-stu-id="58f9f-162">The default value is 00:10:00.</span></span> <span data-ttu-id="58f9f-163">詳細については、「<xref:System.ServiceModel.MsmqBindingBase.RetryCycleDelay%2A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="58f9f-163">For more information, see <xref:System.ServiceModel.MsmqBindingBase.RetryCycleDelay%2A>.</span></span>|  
|`sendTimeout`|<span data-ttu-id="58f9f-164">送信操作が完了するまでの時間間隔を指定する <xref:System.TimeSpan> 値です。</span><span class="sxs-lookup"><span data-stu-id="58f9f-164">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="58f9f-165">この値は必ず <xref:System.TimeSpan.Zero> 以上である必要があります。</span><span class="sxs-lookup"><span data-stu-id="58f9f-165">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="58f9f-166">既定値は 00:01:00 です。</span><span class="sxs-lookup"><span data-stu-id="58f9f-166">The default is 00:01:00.</span></span>|  
|`timeToLive`|<span data-ttu-id="58f9f-167">メッセージの期限が切れて、配信不能キューに入れられるまでのメッセージの有効期間を指定する TimeSpan 値です。</span><span class="sxs-lookup"><span data-stu-id="58f9f-167">A TimeSpan value that specifies how long the messages are valid before they are expired and put into the dead-letter queue.</span></span> <span data-ttu-id="58f9f-168">既定値は 1.00:00:00 です。</span><span class="sxs-lookup"><span data-stu-id="58f9f-168">The default is 1.00:00:00.</span></span><br /><br /> <span data-ttu-id="58f9f-169">この属性を設定すると、タイムリーなメッセージが受信側アプリケーションで処理される前に古くなることがなくなります。</span><span class="sxs-lookup"><span data-stu-id="58f9f-169">This attribute is set to ensure that time-sensitive messages do not become stale before they are processed by the receiving applications.</span></span> <span data-ttu-id="58f9f-170">キュー内のメッセージのうち、指定された期間内に受信アプリケーションで処理されなかったメッセージは、期限切れと呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="58f9f-170">A message in a queue that is not consumed by the receiving application within the time interval specified is said to be expired.</span></span> <span data-ttu-id="58f9f-171">期限切れのメッセージは、配信不能キューと呼ばれる特別なキューに送信されます。</span><span class="sxs-lookup"><span data-stu-id="58f9f-171">Expired messages are sent to special queue called the dead letter queue.</span></span> <span data-ttu-id="58f9f-172">配信不能キューの場所は、保証の内容に基づいて、`DeadLetterQueue` 属性を使用して設定されるか、適切な既定値に設定されます。</span><span class="sxs-lookup"><span data-stu-id="58f9f-172">The location of the dead letter queue is set with the `DeadLetterQueue` attribute or to the appropriate default, based on assurances.</span></span>|  
|`usingActiveDirectory`|<span data-ttu-id="58f9f-173">キューのアドレスを Active Directory を使用して変換する必要があるかどうかを指定するブール値。</span><span class="sxs-lookup"><span data-stu-id="58f9f-173">A Boolean value that specifies if queue addresses should be converted using Active Directory.</span></span><br /><br /> <span data-ttu-id="58f9f-174">MSMQ キューのアドレスは、パス名または直接形式名で構成できます。</span><span class="sxs-lookup"><span data-stu-id="58f9f-174">MSMQ queue addresses can consist of path names or direct format names.</span></span> <span data-ttu-id="58f9f-175">直接形式名を使用する場合、MSMQ は、DNS、NetBIOS、または IP を使用してコンピューター名を解決します。</span><span class="sxs-lookup"><span data-stu-id="58f9f-175">With a direct format name, MSMQ resolves the computer name using DNS, NetBIOS or IP.</span></span> <span data-ttu-id="58f9f-176">パス名を使用する場合、MSMQ は、Active Directory を使用してコンピューター名を解決します。</span><span class="sxs-lookup"><span data-stu-id="58f9f-176">With a path name, MSMQ resolves the computer name using Active Directory.</span></span><br /><br /> <span data-ttu-id="58f9f-177">既定では、Windows Communication Foundation (WCF) のキューに置かれたトランスポートは、メッセージキューの URI を直接形式名に変換します。</span><span class="sxs-lookup"><span data-stu-id="58f9f-177">By default, Windows Communication Foundation (WCF) queued transport converts the URI of a message queue to a direct format name.</span></span> <span data-ttu-id="58f9f-178">`UseActiveDirectory` プロパティを true に設定すると、キューに置かれているトランスポートが DNS、NetBIOS、または IP ではなく Active Directory を使用してコンピューター名を解決する必要があることを、アプリケーションで指定できます。</span><span class="sxs-lookup"><span data-stu-id="58f9f-178">By setting the `UseActiveDirectory` property to true, an application can specify that the queued transport should resolve the computer name using Active Directory rather than DNS, NetBIOS, or IP.</span></span>|  
|`useMsmqTracing`|<span data-ttu-id="58f9f-179">このバインディングにより処理されるメッセージをトレースするかどうかを指定するブール値です。</span><span class="sxs-lookup"><span data-stu-id="58f9f-179">A Boolean value that specifies whether messages processed by this binding should be traced.</span></span> <span data-ttu-id="58f9f-180">既定値は、 `false`です。</span><span class="sxs-lookup"><span data-stu-id="58f9f-180">The default is `false`.</span></span> <span data-ttu-id="58f9f-181">トレースが有効な場合、メッセージ キュー コンピューターでメッセージが送受信されるたびに、レポート メッセージが作成され、レポート キューに送信されます。</span><span class="sxs-lookup"><span data-stu-id="58f9f-181">When tracing is enabled, report messages are created and sent to the report queue each time the message leaves or arrives at a Message Queuing computer.</span></span>|  
|`useSourceJournal`|<span data-ttu-id="58f9f-182">このバインディングにより処理されるメッセージのコピーをソース ジャーナルに保存するかどうかを指定するブール値です。</span><span class="sxs-lookup"><span data-stu-id="58f9f-182">A Boolean value that specifies copies of messages processed by this binding should be stored in the source journal.</span></span> <span data-ttu-id="58f9f-183">既定値は、 `false`です。</span><span class="sxs-lookup"><span data-stu-id="58f9f-183">The default is `false`.</span></span><br /><br /> <span data-ttu-id="58f9f-184">キューに置かれたアプリケーションでは、コンピューターの発信キューから送信されたメッセージの記録を残す場合は、メッセージをジャーナル キューにコピーできます。</span><span class="sxs-lookup"><span data-stu-id="58f9f-184">Queued applications that want to keep a record of messages that have left the computer's outgoing queue can copy the messages to a journal queue.</span></span> <span data-ttu-id="58f9f-185">メッセージが発信キューから送信され、送信先のコンピューターで受信されたという応答を受け取ると、メッセージのコピーが送信元のコンピューターのシステム ジャーナル キューに保持されます。</span><span class="sxs-lookup"><span data-stu-id="58f9f-185">Once a message leaves the outgoing queue and an acknowledgment is received that the message was received on the destination computer, a copy of the message is kept in the sending computer's system journal queue.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="58f9f-186">子要素</span><span class="sxs-lookup"><span data-stu-id="58f9f-186">Child Elements</span></span>  
  
|<span data-ttu-id="58f9f-187">要素</span><span class="sxs-lookup"><span data-stu-id="58f9f-187">Element</span></span>|<span data-ttu-id="58f9f-188">説明</span><span class="sxs-lookup"><span data-stu-id="58f9f-188">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="58f9f-189">[readerQuotas > の \<](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="58f9f-189">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span></span>|<span data-ttu-id="58f9f-190">このバインドを使用して設定されるエンドポイントにより処理可能な、SOAP メッセージの複雑さに対する制約を定義します。</span><span class="sxs-lookup"><span data-stu-id="58f9f-190">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="58f9f-191">この要素は <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="58f9f-191">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
|[<span data-ttu-id="58f9f-192">\<セキュリティ ></span><span class="sxs-lookup"><span data-stu-id="58f9f-192">\<security></span></span>](security-of-netmsmqbinding.md)|<span data-ttu-id="58f9f-193">バインディングのセキュリティ設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="58f9f-193">Defines the security settings for the binding.</span></span> <span data-ttu-id="58f9f-194">この要素は <xref:System.ServiceModel.Configuration.NetMsmqSecurityElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="58f9f-194">This element is of type <xref:System.ServiceModel.Configuration.NetMsmqSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="58f9f-195">親要素</span><span class="sxs-lookup"><span data-stu-id="58f9f-195">Parent Elements</span></span>  
  
|<span data-ttu-id="58f9f-196">要素</span><span class="sxs-lookup"><span data-stu-id="58f9f-196">Element</span></span>|<span data-ttu-id="58f9f-197">説明</span><span class="sxs-lookup"><span data-stu-id="58f9f-197">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="58f9f-198">\<バインド ></span><span class="sxs-lookup"><span data-stu-id="58f9f-198">\<bindings></span></span>](bindings.md)|<span data-ttu-id="58f9f-199">この要素には、標準バインディングおよびカスタム バインドのコレクションが保持されます。</span><span class="sxs-lookup"><span data-stu-id="58f9f-199">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="58f9f-200">Remarks</span><span class="sxs-lookup"><span data-stu-id="58f9f-200">Remarks</span></span>  
 <span data-ttu-id="58f9f-201">`netMsmqBinding` バインディングは、Microsoft Message Queuing (MSMQ) をトランスポートとして使用したキューのサポートを提供し、疎結合アプリケーション、失敗の切り分け、読み込みの均一化、および切断操作のサポートを有効にします。</span><span class="sxs-lookup"><span data-stu-id="58f9f-201">The `netMsmqBinding` binding provides support for queuing by leveraging Microsoft Message Queuing (MSMQ) as a transport and enables support for loosely coupled applications, failure isolation, load leveling and disconnected operations.</span></span> <span data-ttu-id="58f9f-202">これらの機能の詳細については、「 [WCF のキュー](../../../wcf/feature-details/queues-in-wcf.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="58f9f-202">For a discussion of these features, see [Queues in WCF](../../../wcf/feature-details/queues-in-wcf.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="58f9f-203">例</span><span class="sxs-lookup"><span data-stu-id="58f9f-203">Example</span></span>  
  
```xml  
<configuration>
  <system.ServiceModel>
    <bindings>
      <netMsmqBinding>
        <binding closeTimeout="00:00:10"
                 openTimeout="00:00:20"
                 receiveTimeout="00:00:30"
                 sendTimeout="00:00:40"
                 deadLetterQueue="net.msmq://localhost/blah"
                 durable="true"
                 exactlyOnce="true"
                 maxReceivedMessageSize="1000"
                 maxRetries="11"
                 maxRetryCycles="12"
                 poisonMessageHandling="Disabled"
                 rejectAfterLastRetry="false"
                 retryCycleDelay="00:05:55"
                 timeToLive="00:11:11"
                 sourceJournal="true"
                 useMsmqTracing="true"
                 useActiveDirectory="true">
          <security>
            <message clientCredentialType="Windows" />
          </security>
        </binding>
      </netMsmqBinding>
    </bindings>
  </system.ServiceModel>
</configuration>
```  
  
## <a name="see-also"></a><span data-ttu-id="58f9f-204">関連項目</span><span class="sxs-lookup"><span data-stu-id="58f9f-204">See also</span></span>

- <xref:System.ServiceModel.NetMsmqBinding>
- <xref:System.ServiceModel.Configuration.NetMsmqBindingElement>
- [<span data-ttu-id="58f9f-205">\<バインド ></span><span class="sxs-lookup"><span data-stu-id="58f9f-205">\<binding></span></span>](bindings.md)
- [<span data-ttu-id="58f9f-206">バインディング</span><span class="sxs-lookup"><span data-stu-id="58f9f-206">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="58f9f-207">システムが提供するバインディングの構成</span><span class="sxs-lookup"><span data-stu-id="58f9f-207">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="58f9f-208">サービスとクライアントを構成するためのバインディングの使用</span><span class="sxs-lookup"><span data-stu-id="58f9f-208">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="58f9f-209">WCF のキュー</span><span class="sxs-lookup"><span data-stu-id="58f9f-209">Queues in WCF</span></span>](../../../wcf/feature-details/queues-in-wcf.md)
