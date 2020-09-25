---
title: <localServiceSettings> 要素
ms.date: 03/30/2017
ms.assetid: 0658549c-3f65-46dd-8c5c-9895441ed734
ms.openlocfilehash: 3043c07afd316d90cc5525a67bef144f33d9b136
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91204932"
---
# <a name="localservicesettings-element"></a><span data-ttu-id="988bd-102">\<localServiceSettings> 要素</span><span class="sxs-lookup"><span data-stu-id="988bd-102">\<localServiceSettings> element</span></span>

<span data-ttu-id="988bd-103">このバインディングのローカル サービスのセキュリティ設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="988bd-103">Specifies the security settings of a local service for this binding.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<localServiceSettings>**  
  
## <a name="syntax"></a><span data-ttu-id="988bd-104">構文</span><span class="sxs-lookup"><span data-stu-id="988bd-104">Syntax</span></span>  
  
```xml  
<security>
  <localServiceSettings detectReplays="Boolean"
                        inactivityTimeout="TimeSpan"
                        issuedCookieLifeTime="TimeSpan"
                        maxCachedCookies="Integer"
                        maxClockSkew="TimeSpan"
                        maxPendingSessions="Integer"
                        maxStatefulNegotiations="Integer"
                        negotiationTimeout="TimeSpan"
                        reconnectTransportOnFailure="Boolean"
                        replayCacheSize="Integer"
                        replayWindow="TimeSpan"
                        sessionKeyRenewalInterval="TimeSpan"
                        sessionKeyRolloverInterval="TimeSpan"
                        timestampValidityDuration="TimeSpan" />
</security>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="988bd-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="988bd-105">Attributes and Elements</span></span>  

 <span data-ttu-id="988bd-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="988bd-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="988bd-107">属性</span><span class="sxs-lookup"><span data-stu-id="988bd-107">Attributes</span></span>  
  
|<span data-ttu-id="988bd-108">属性</span><span class="sxs-lookup"><span data-stu-id="988bd-108">Attribute</span></span>|<span data-ttu-id="988bd-109">[説明]</span><span class="sxs-lookup"><span data-stu-id="988bd-109">Description</span></span>|  
|---------------|-----------------|  
|`detectReplays`|<span data-ttu-id="988bd-110">チャネルに対するリプレイ攻撃を検出し、自動的に処理するかどうかを指定するブール値です。</span><span class="sxs-lookup"><span data-stu-id="988bd-110">A Boolean value that specifies whether replay attacks against the channel are detected and dealt with automatically.</span></span> <span data-ttu-id="988bd-111">既定では、 `false`です。</span><span class="sxs-lookup"><span data-stu-id="988bd-111">The default is `false`.</span></span>|  
|`inactivityTimeout`|<span data-ttu-id="988bd-112"><xref:System.TimeSpan>チャネルがタイムアウトまで待機する非アクティブな時間を指定する正の。既定値は "01:00:00" です。</span><span class="sxs-lookup"><span data-stu-id="988bd-112">A positive <xref:System.TimeSpan> that specifies the duration of inactivity the channel waits before it times out. The default is "01:00:00".</span></span>|  
|`issuedCookieLifeTime`|<span data-ttu-id="988bd-113">すべての新しいセキュリティ クッキーに発行される有効期間を指定する <xref:System.TimeSpan>。</span><span class="sxs-lookup"><span data-stu-id="988bd-113">A <xref:System.TimeSpan> that specifies the lifetime issued to all new security cookies.</span></span> <span data-ttu-id="988bd-114">有効期間を超えるクッキーは、再利用され、再度ネゴシエートされる必要があります。</span><span class="sxs-lookup"><span data-stu-id="988bd-114">Cookies that exceed their lifetime are recycled and need to be negotiated again.</span></span> <span data-ttu-id="988bd-115">既定値は、"10:00:00" です。</span><span class="sxs-lookup"><span data-stu-id="988bd-115">The default value is "10:00:00".</span></span>|  
|`maxCachedCookies`|<span data-ttu-id="988bd-116">キャッシュできるクッキーの最大数を指定する正の整数。</span><span class="sxs-lookup"><span data-stu-id="988bd-116">A positive integer that specifies the maximum number of cookies that can be cached.</span></span> <span data-ttu-id="988bd-117">既定値は 1000 です。</span><span class="sxs-lookup"><span data-stu-id="988bd-117">The default is 1000.</span></span>|  
|`maxClockSkew`|<span data-ttu-id="988bd-118">通信している双方の 2 つのシステム クロックのずれの最長時間を指定する <xref:System.TimeSpan>。</span><span class="sxs-lookup"><span data-stu-id="988bd-118">A <xref:System.TimeSpan> that specifies the maximum time difference between the system clocks of the two communicating parties.</span></span> <span data-ttu-id="988bd-119">既定値は、"00:05:00" です。</span><span class="sxs-lookup"><span data-stu-id="988bd-119">The default value is "00:05:00".</span></span><br /><br /> <span data-ttu-id="988bd-120">この値が既定値に設定されている場合、受信側はメッセージが受信された時間より前後最大 5 分間の送信時間タイム スタンプを持つメッセージを受け入れます。</span><span class="sxs-lookup"><span data-stu-id="988bd-120">When this value is set to the default, the receiver accepts messages with send-time time stamps up to 5 minutes later or earlier than the time the message was received.</span></span> <span data-ttu-id="988bd-121">送信時間テストにパスしないメッセージは拒否されます。</span><span class="sxs-lookup"><span data-stu-id="988bd-121">Messages that do not pass the send-time test are rejected.</span></span> <span data-ttu-id="988bd-122">この設定は、`replayWindow` 属性と組み合わせて使用します。</span><span class="sxs-lookup"><span data-stu-id="988bd-122">This setting is used in conjunction with the `replayWindow` attribute.</span></span>|  
|`maxPendingSessions`|<span data-ttu-id="988bd-123">サービスがサポートする保留状態のセキュリティ セッションの最大数を指定する正の整数。</span><span class="sxs-lookup"><span data-stu-id="988bd-123">A positive integer that specifies the maximum number of pending security sessions that the service supports.</span></span> <span data-ttu-id="988bd-124">この制限に達すると、すべての新しいクライアントが SOAP エラーを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="988bd-124">When this limit is reached, all new clients receive SOAP faults.</span></span> <span data-ttu-id="988bd-125">既定値は 1000 です。</span><span class="sxs-lookup"><span data-stu-id="988bd-125">The default value is 1000.</span></span>|  
|`maxStatefulNegotiations`|<span data-ttu-id="988bd-126">同時にアクティブにできるセキュリティ ネゴシエーションの数を指定する正の整数。</span><span class="sxs-lookup"><span data-stu-id="988bd-126">A positive integer that specifies the number of security negotiations that can be active concurrently.</span></span> <span data-ttu-id="988bd-127">制限を超えるネゴシエーション セッションはキューに置かれ、制限内に空きができた場合にのみ完了できます。</span><span class="sxs-lookup"><span data-stu-id="988bd-127">Negotiation sessions in excess of the limit are queued and can only be completed when a space below the limit becomes available.</span></span> <span data-ttu-id="988bd-128">既定値は 1024 です。</span><span class="sxs-lookup"><span data-stu-id="988bd-128">The default value is 1024.</span></span>|  
|`negotiationTimeout`|<span data-ttu-id="988bd-129">チャネルによって使用されるセキュリティ ポリシーの有効期間を指定する <xref:System.TimeSpan>。</span><span class="sxs-lookup"><span data-stu-id="988bd-129">A <xref:System.TimeSpan> that specifies the lifetime of the security policy used by channel.</span></span> <span data-ttu-id="988bd-130">有効期間が切れると、チャネルは新しいセキュリティ ポリシーについてクライアントと再度ネゴシエートします。</span><span class="sxs-lookup"><span data-stu-id="988bd-130">When the time expires, the channel renegotiates with the client for a new security policy.</span></span> <span data-ttu-id="988bd-131">既定値は、"00:02:00" です。</span><span class="sxs-lookup"><span data-stu-id="988bd-131">The default value is "00:02:00".</span></span>|  
|`reconnectTransportOnFailure`|<span data-ttu-id="988bd-132">WS-ReliableMessaging を使用した接続が、トランスポート エラーの後再接続を試みるかどうかを指定するブール値です。</span><span class="sxs-lookup"><span data-stu-id="988bd-132">A Boolean value that specifies whether connections using WS-Reliable messaging will attempt to reconnect after transport failures.</span></span> <span data-ttu-id="988bd-133">既定値は `true` です。これは、再接続の試行が無限に行われることを意味します。</span><span class="sxs-lookup"><span data-stu-id="988bd-133">The default is `true`, which means that infinite attempts to reconnect are attempted.</span></span> <span data-ttu-id="988bd-134">循環は非アクティブ タイムアウトにより破棄され、再接続できない場合はチャネルが例外をスローします。</span><span class="sxs-lookup"><span data-stu-id="988bd-134">The cycle is broken by the inactivity time-out, which causes the channel to throw an exception when it cannot be reconnected.</span></span>|  
|`replayCacheSize`|<span data-ttu-id="988bd-135">リプレイ検証で使用される、キャッシュ済みの nonce 数を指定する正の整数。</span><span class="sxs-lookup"><span data-stu-id="988bd-135">A positive integer that specifies the number of cached nonces used for replay detection.</span></span> <span data-ttu-id="988bd-136">この制限を越えると、最も古い nonce が削除され、新しいメッセージ用に新しい nonce が作成されます。</span><span class="sxs-lookup"><span data-stu-id="988bd-136">If this limit is exceeded, the oldest nonce is removed and a new nonce is created for the new message.</span></span> <span data-ttu-id="988bd-137">既定値は 500000 です。</span><span class="sxs-lookup"><span data-stu-id="988bd-137">The default value is 500000.</span></span>|  
|`replayWindow`|<span data-ttu-id="988bd-138">個別のメッセージ nonce の有効期間を指定する <xref:System.TimeSpan>。</span><span class="sxs-lookup"><span data-stu-id="988bd-138">A <xref:System.TimeSpan> that specifies the duration in which individual message nonces are valid.</span></span><br /><br /> <span data-ttu-id="988bd-139">この期間が過ぎると、以前に送信されたメッセージと同じ nonce を持つメッセージは受け入れられません。</span><span class="sxs-lookup"><span data-stu-id="988bd-139">After this duration, a message sent with the same nonce as the one sent before will not be accepted.</span></span> <span data-ttu-id="988bd-140">この属性は、リプレイ攻撃を防ぐために `maxClockSkew` 属性と組み合わせて使用します。</span><span class="sxs-lookup"><span data-stu-id="988bd-140">This attribute is used in conjunction with the `maxClockSkew` attribute to prevent replay attacks.</span></span> <span data-ttu-id="988bd-141">攻撃者は、メッセージのリプレイ ウィンドウの期限が切れた後にメッセージをリプレイする可能性があります。</span><span class="sxs-lookup"><span data-stu-id="988bd-141">An attacker could replay a message after its replay window has expired.</span></span> <span data-ttu-id="988bd-142">ただし、このメッセージは `maxClockSkew` テストに失敗します。このテストは、メッセージが受信された時間の前後指定時間以内の送信時間タイムスタンプを持つメッセージを拒否します。</span><span class="sxs-lookup"><span data-stu-id="988bd-142">This message, however, would fail the `maxClockSkew` test which rejects messages with send-time timestamps up to a specified time later or earlier than the time the message was received.</span></span>|  
|`sessionKeyRenewalInterval`|<span data-ttu-id="988bd-143">イニシエーターがセキュリティ セッションのキーを更新するまでの期間を指定する <xref:System.TimeSpan>。</span><span class="sxs-lookup"><span data-stu-id="988bd-143">A <xref:System.TimeSpan> that specifies the duration after which the initiator will renew the key for the security session.</span></span> <span data-ttu-id="988bd-144">既定値は "10:00:00" です。</span><span class="sxs-lookup"><span data-stu-id="988bd-144">The default is "10:00:00".</span></span>|  
|`sessionKeyRolloverInterval`|<span data-ttu-id="988bd-145">キーの更新中に、前のセッション キーが受信メッセージで有効な時間間隔を指定する <xref:System.TimeSpan> です。</span><span class="sxs-lookup"><span data-stu-id="988bd-145">A <xref:System.TimeSpan> that specifies the time interval a previous session key is valid on incoming messages during a key renewal.</span></span> <span data-ttu-id="988bd-146">既定値は "00:05:00" です。</span><span class="sxs-lookup"><span data-stu-id="988bd-146">The default is "00:05:00".</span></span><br /><br /> <span data-ttu-id="988bd-147">キーの更新中、クライアントおよびサーバーは、常に、利用可能な最新のキーを使用してメッセージを送信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="988bd-147">During key renewal, the client and server must always send messages using the most current available key.</span></span> <span data-ttu-id="988bd-148">どちらのパーティも、ロールオーバー時間に達するまで、前のセッション キーで保護された受信メッセージを受け入れます。</span><span class="sxs-lookup"><span data-stu-id="988bd-148">Both parties will accept incoming messages secured with the previous session key until the rollover time expires.</span></span>|  
|`timestampValidityDuration`|<span data-ttu-id="988bd-149">タイムスタンプの有効期間を指定する正の <xref:System.TimeSpan>。</span><span class="sxs-lookup"><span data-stu-id="988bd-149">A positive <xref:System.TimeSpan> that specifies the duration in which a time stamp is valid.</span></span> <span data-ttu-id="988bd-150">既定値は "00:15:00" です。</span><span class="sxs-lookup"><span data-stu-id="988bd-150">The default is "00:15:00".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="988bd-151">子要素</span><span class="sxs-lookup"><span data-stu-id="988bd-151">Child Elements</span></span>  

 <span data-ttu-id="988bd-152">なし。</span><span class="sxs-lookup"><span data-stu-id="988bd-152">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="988bd-153">親要素</span><span class="sxs-lookup"><span data-stu-id="988bd-153">Parent Elements</span></span>  
  
|<span data-ttu-id="988bd-154">要素</span><span class="sxs-lookup"><span data-stu-id="988bd-154">Element</span></span>|<span data-ttu-id="988bd-155">説明</span><span class="sxs-lookup"><span data-stu-id="988bd-155">Description</span></span>|  
|-------------|-----------------|  
|[\<security>](security-of-custombinding.md)|<span data-ttu-id="988bd-156">カスタム バインドのセキュリティ オプションを指定します。</span><span class="sxs-lookup"><span data-stu-id="988bd-156">Specifies the security options for a custom binding.</span></span>|  
|[\<secureConversationBootstrap>](secureconversationbootstrap.md)|<span data-ttu-id="988bd-157">セキュリティで保護されたメッセージ交換サービスの開始に使用される既定値を指定します。</span><span class="sxs-lookup"><span data-stu-id="988bd-157">Specifies the default values used for initiating a secure conversation service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="988bd-158">解説</span><span class="sxs-lookup"><span data-stu-id="988bd-158">Remarks</span></span>  

 <span data-ttu-id="988bd-159">この設定は、サービスのセキュリティ ポリシーの一部として公開されず、クライアントのバインディングには影響を与えないため、ローカルです。</span><span class="sxs-lookup"><span data-stu-id="988bd-159">The settings are local because they are not published as part of the security policy of the service and do not affect the client's binding.</span></span>  
  
 <span data-ttu-id="988bd-160">`localServiceSecuritySettings` 要素の以下の属性は、サービス拒否 (DOS) セキュリティ攻撃を軽減するために役立ちます。</span><span class="sxs-lookup"><span data-stu-id="988bd-160">The following attributes of the `localServiceSecuritySettings` element can help mitigate a denial-of-service (DOS) security attack:</span></span>  
  
- <span data-ttu-id="988bd-161">`maxCachedCookies`: SPNEGO または SSL の各ネゴシエーションの実行後にサーバーによってキャッシュされる、期限付きの SecurityContextTokens の最大数を制御します。</span><span class="sxs-lookup"><span data-stu-id="988bd-161">`maxCachedCookies`: controls the maximum number of time-bounded SecurityContextTokens that are cached by the server after doing SPNEGO or SSL negotiation.</span></span>  
  
- <span data-ttu-id="988bd-162">`issuedCookieLifetime`: SPNEGO または SSL の各ネゴシエーションに続いてサーバーが発行する SecurityContextTokens の有効期限を制御します。</span><span class="sxs-lookup"><span data-stu-id="988bd-162">`issuedCookieLifetime`: controls the lifetime of the SecurityContextTokens that are issued by the server following SPNEGO or SSL negotiation.</span></span> <span data-ttu-id="988bd-163">サーバーは、この期間だけ SecurityContextTokens をキャッシュします。</span><span class="sxs-lookup"><span data-stu-id="988bd-163">The server caches the SecurityContextTokens for this period of time.</span></span>  
  
- <span data-ttu-id="988bd-164">`maxPendingSessions`: サーバーで確立されているが、そのアプリケーション メッセージが処理されていない、セキュリティで保護されたメッセージ交換の最大数を制御します。</span><span class="sxs-lookup"><span data-stu-id="988bd-164">`maxPendingSessions`: controls the maximum number of secure conversations that are established at the server but for which no application messages have been processed.</span></span> <span data-ttu-id="988bd-165">このクォータは、クライアントが、セキュリティで保護されたメッセージ交換をサービスで確立しないようにします。それによって、サービスはクライアントごとの状態を保持できますが、それらの状態を使用することはありません。</span><span class="sxs-lookup"><span data-stu-id="988bd-165">This quota prevents clients from establishing secure conversations at the service, thereby causing the service to maintain state for each client, but never using them.</span></span>  
  
- <span data-ttu-id="988bd-166">`inactivityTimeout`: サービスが、セキュリティで保護されたメッセージ交換を、それに対するアプリケーション メッセージを受信しなくても維持する最長時間を制御します。</span><span class="sxs-lookup"><span data-stu-id="988bd-166">`inactivityTimeout`: controls the maximum time that the service keeps a secure conversation alive without ever receiving an application message on it.</span></span> <span data-ttu-id="988bd-167">このクォータは、クライアントが、セキュリティで保護されたメッセージ交換をサービスで確立しないようにします。それによって、サービスはクライアントごとの状態を保持できますが、それらの状態を使用することはありません。</span><span class="sxs-lookup"><span data-stu-id="988bd-167">This quota prevents clients from establishing secure conversations at the service, thereby causing the service to maintain state for each client, but never using them.</span></span>  
  
 <span data-ttu-id="988bd-168">セキュリティで保護されたメッセージ交換セッションでは、バインディングの `inactivityTimeout` 属性および `receiveTimeout` 属性の両方が、セッション タイムアウトに影響します。</span><span class="sxs-lookup"><span data-stu-id="988bd-168">In a secure conversation session, note that both `inactivityTimeout` and the `receiveTimeout` attributes on the binding affect session timeout.</span></span> <span data-ttu-id="988bd-169">2 つのうち短い方が、タイムアウトが発生する時間を決定します。</span><span class="sxs-lookup"><span data-stu-id="988bd-169">The shorter of the two determines when timeouts occur.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="988bd-170">関連項目</span><span class="sxs-lookup"><span data-stu-id="988bd-170">See also</span></span>

- <xref:System.ServiceModel.Configuration.LocalServiceSecuritySettingsElement>
- <xref:System.ServiceModel.Configuration.SecurityElementBase.LocalServiceSettings%2A>
- <xref:System.ServiceModel.Channels.SecurityBindingElement.LocalServiceSettings%2A>
- <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="988bd-171">バインド</span><span class="sxs-lookup"><span data-stu-id="988bd-171">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="988bd-172">バインディングの拡張</span><span class="sxs-lookup"><span data-stu-id="988bd-172">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="988bd-173">カスタム バインディング</span><span class="sxs-lookup"><span data-stu-id="988bd-173">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
- [<span data-ttu-id="988bd-174">方法: SecurityBindingElement を使用してカスタム バインドを作成する</span><span class="sxs-lookup"><span data-stu-id="988bd-174">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)
- [<span data-ttu-id="988bd-175">カスタム バインディング セキュリティ</span><span class="sxs-lookup"><span data-stu-id="988bd-175">Custom Binding Security</span></span>](../../../wcf/samples/custom-binding-security.md)
