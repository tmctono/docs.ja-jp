---
title: 信頼できるメッセージング プロトコル バージョン 1.1
ms.date: 03/30/2017
ms.assetid: 0da47b82-f8eb-42da-8bfe-e56ce7ba6f59
ms.openlocfilehash: 349c4dec8f127640d2709abcd63295aace6826df
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64754115"
---
# <a name="reliable-messaging-protocol-version-11"></a><span data-ttu-id="d07c8-102">信頼できるメッセージング プロトコル バージョン 1.1</span><span class="sxs-lookup"><span data-stu-id="d07c8-102">Reliable Messaging Protocol version 1.1</span></span>

<span data-ttu-id="d07c8-103">このトピックでは、Windows Communication Foundation (WCF) の実装の詳細を説明 WS-ReliableMessaging の 2007 年 2 月 (バージョン 1.1) プロトコルが HTTP トランスポートを使用して相互運用のために必要です。</span><span class="sxs-lookup"><span data-stu-id="d07c8-103">This topic covers Windows Communication Foundation (WCF) implementation details for the WS-ReliableMessaging February 2007 (version 1.1) protocol necessary for interoperation using the HTTP transport.</span></span> <span data-ttu-id="d07c8-104">WCF では、制約と明確にでは、このトピックで説明されている、WS-ReliableMessaging 仕様に従います。</span><span class="sxs-lookup"><span data-stu-id="d07c8-104">WCF follows the WS-ReliableMessaging specification with the constraints and clarifications explained in this topic.</span></span> <span data-ttu-id="d07c8-105">以降では、WS-ReliableMessaging のバージョン 1.1 プロトコルを実装することに注意してください、[!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="d07c8-105">Note that the WS-ReliableMessaging version 1.1 protocol is implemented starting with the [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)].</span></span>

<span data-ttu-id="d07c8-106">WS-ReliableMessaging 2007 年 2 月での WCF でプロトコルが実装されている、<xref:System.ServiceModel.Channels.ReliableSessionBindingElement>します。</span><span class="sxs-lookup"><span data-stu-id="d07c8-106">The WS-ReliableMessaging February 2007 protocol is implemented in WCF by the <xref:System.ServiceModel.Channels.ReliableSessionBindingElement>.</span></span>

<span data-ttu-id="d07c8-107">便宜上、ここでは次のロールを使用します。</span><span class="sxs-lookup"><span data-stu-id="d07c8-107">For convenience, the topic uses the following roles:</span></span>

- <span data-ttu-id="d07c8-108">発信側:Ws-reliable メッセージ シーケンスの作成を開始するクライアント。</span><span class="sxs-lookup"><span data-stu-id="d07c8-108">Initiator: The client that initiates WS-Reliable Message sequence creation.</span></span>

- <span data-ttu-id="d07c8-109">レスポンダー:イニシエーターの要求を受信するサービスです。</span><span class="sxs-lookup"><span data-stu-id="d07c8-109">Responder: The service that receives the initiator's requests.</span></span>

 <span data-ttu-id="d07c8-110">このドキュメントでは、次の表に示すプレフィックスと名前空間を使用します。</span><span class="sxs-lookup"><span data-stu-id="d07c8-110">This document uses the prefixes and namespaces in the following table.</span></span>

|<span data-ttu-id="d07c8-111">プレフィックス</span><span class="sxs-lookup"><span data-stu-id="d07c8-111">Prefix</span></span>|<span data-ttu-id="d07c8-112">名前空間</span><span class="sxs-lookup"><span data-stu-id="d07c8-112">Namespace</span></span>|
|-|-|
|<span data-ttu-id="d07c8-113">wsrm</span><span class="sxs-lookup"><span data-stu-id="d07c8-113">wsrm</span></span>|http://docs.oasis-open.org/ws-rx/wsrm/200702|
|<span data-ttu-id="d07c8-114">netrm</span><span class="sxs-lookup"><span data-stu-id="d07c8-114">netrm</span></span>|http://schemas.microsoft.com/ws/2006/05/rm|
|<span data-ttu-id="d07c8-115">s</span><span class="sxs-lookup"><span data-stu-id="d07c8-115">s</span></span>|http://www.w3.org/2003/05/soap-envelope|
|<span data-ttu-id="d07c8-116">wsa</span><span class="sxs-lookup"><span data-stu-id="d07c8-116">wsa</span></span>|http://schemas.xmlsoap.org/ws/2005/08/addressing|
|<span data-ttu-id="d07c8-117">wsse</span><span class="sxs-lookup"><span data-stu-id="d07c8-117">wsse</span></span>|http://docs.oasis-open.org/wss/2004/01/oasis-200401-wssecurity-secext-1.0.xsd|
|<span data-ttu-id="d07c8-118">wsrmp</span><span class="sxs-lookup"><span data-stu-id="d07c8-118">wsrmp</span></span>|http://docs.oasis-open.org/ws-rx/wsrmp/200702|
|<span data-ttu-id="d07c8-119">netrmp</span><span class="sxs-lookup"><span data-stu-id="d07c8-119">netrmp</span></span>|http://schemas.microsoft.com/ws-rx/wsrmp/200702|
|<span data-ttu-id="d07c8-120">wsp</span><span class="sxs-lookup"><span data-stu-id="d07c8-120">wsp</span></span>|<span data-ttu-id="d07c8-121">(WS-Policy 1.2 または WS-Policy 1.5 のいずれか)</span><span class="sxs-lookup"><span data-stu-id="d07c8-121">(Either WS-Policy 1.2 or WS-Policy 1.5)</span></span>|

## <a name="messaging"></a><span data-ttu-id="d07c8-122">メッセージング</span><span class="sxs-lookup"><span data-stu-id="d07c8-122">Messaging</span></span>

### <a name="sequence-creation"></a><span data-ttu-id="d07c8-123">シーケンスの作成</span><span class="sxs-lookup"><span data-stu-id="d07c8-123">Sequence Creation</span></span>

<span data-ttu-id="d07c8-124">WCF 実装`CreateSequence`と`CreateSequenceResponse`信頼性の高いメッセージングを確立するためにメッセージのシーケンスします。</span><span class="sxs-lookup"><span data-stu-id="d07c8-124">WCF implements `CreateSequence` and `CreateSequenceResponse` messages to establish a reliable messaging sequence.</span></span> <span data-ttu-id="d07c8-125">以下の制約が適用されます。</span><span class="sxs-lookup"><span data-stu-id="d07c8-125">The following constraints apply:</span></span>

- <span data-ttu-id="d07c8-126">B1101:WCF イニシエーターとして同じエンドポイント参照を使用して、`CreateSequence`メッセージの`ReplyTo`、`AcksTo`と`Offer/Endpoint`します。</span><span class="sxs-lookup"><span data-stu-id="d07c8-126">B1101: The WCF Initiator uses the same endpoint reference as the `CreateSequence` message’s `ReplyTo`, `AcksTo` and `Offer/Endpoint`.</span></span>

- <span data-ttu-id="d07c8-127">R1102:`AcksTo`、`ReplyTo`と`Offer/Endpoint`エンドポイント参照、`CreateSequence`オクテットと一致するようにメッセージがまったく同じ文字列表現のアドレス値をいる必要があります。</span><span class="sxs-lookup"><span data-stu-id="d07c8-127">R1102: The `AcksTo`, `ReplyTo` and `Offer/Endpoint` endpoint references in the `CreateSequence` message must have address values with identical string representations such that they match the octet-wise.</span></span>

  - <span data-ttu-id="d07c8-128">確認します WCF 応答側の URI 部分、 `AcksTo`、`ReplyTo`と`Endpoint`シーケンスを作成する前に、エンドポイント参照は同じです。</span><span class="sxs-lookup"><span data-stu-id="d07c8-128">The WCF Responder verifies that the URI portion of the `AcksTo`, `ReplyTo` and `Endpoint` endpoint references are identical before creating a sequence.</span></span>

- <span data-ttu-id="d07c8-129">R1103:`AcksTo`、`ReplyTo`と`Offer/Endpoint`エンドポイント参照、`CreateSequence`メッセージは、参照パラメーターの同じセットを持つ必要があります。</span><span class="sxs-lookup"><span data-stu-id="d07c8-129">R1103: The `AcksTo`, `ReplyTo` and `Offer/Endpoint` endpoint references in the `CreateSequence` message should have the same set of reference parameters.</span></span>

  - <span data-ttu-id="d07c8-130">WCF は強制されませんが、その参照を前提としていますのパラメーター、 `AcksTo`、`ReplyTo`と`Offer/Endpoint`エンドポイント参照にで`CreateSequence`と同じですが、参照パラメーターを使用して、`ReplyTo`のエンドポイント参照受信確認と逆方向シーケンス メッセージ。</span><span class="sxs-lookup"><span data-stu-id="d07c8-130">WCF does not enforce, but assumes that reference parameters of the `AcksTo`, `ReplyTo` and `Offer/Endpoint` endpoint references on `CreateSequence` are identical and uses reference parameters from the `ReplyTo` endpoint reference for acknowledgements and converse sequence messages.</span></span>

- <span data-ttu-id="d07c8-131">B1104:WCF のイニシエーターは、省略可能なは生成されません`Expires`または`Offer/Expires`内の要素、`CreateSequence`メッセージ。</span><span class="sxs-lookup"><span data-stu-id="d07c8-131">B1104: The WCF Initiator does not generate the optional `Expires` or `Offer/Expires` element in the `CreateSequence` message.</span></span>

- <span data-ttu-id="d07c8-132">B1105:アクセスするとき、 `CreateSequence` WCF レスポンダーは、メッセージ、`Expires`値、`CreateSequence`要素として、`Expires`値、`CreateSequenceResponse`要素。</span><span class="sxs-lookup"><span data-stu-id="d07c8-132">B1105: When accessing the `CreateSequence` message, the WCF Responder uses the `Expires` value in the `CreateSequence` element as the `Expires` value in the `CreateSequenceResponse` element.</span></span> <span data-ttu-id="d07c8-133">それ以外の場合、WCF 応答側の読み取り、無視、`Expires`と`Offer/Expires`値。</span><span class="sxs-lookup"><span data-stu-id="d07c8-133">Otherwise, the WCF Responder reads and ignores the `Expires` and `Offer/Expires` values.</span></span>

- <span data-ttu-id="d07c8-134">B1106:アクセスするとき、`CreateSequenceResponse`メッセージ、WCF のイニシエーターは省略可能な読み取り`Expires`値が、これを使用しません。</span><span class="sxs-lookup"><span data-stu-id="d07c8-134">B1106: When accessing the `CreateSequenceResponse` message, the WCF Initiator reads the optional `Expires` value but does not use it.</span></span>

- <span data-ttu-id="d07c8-135">B1107:WCF のイニシエーターおよびレスポンダーは生成常に省略可能な`IncompleteSequenceBehavior`内の要素、`CreateSequence/Offer`と`CreateSequenceResponse`要素。</span><span class="sxs-lookup"><span data-stu-id="d07c8-135">B1107: The WCF Initiator and Responder always generate the optional `IncompleteSequenceBehavior` element in the `CreateSequence/Offer` and `CreateSequenceResponse` elements.</span></span>

- <span data-ttu-id="d07c8-136">B1108:WCF を使用してのみ、`DiscardFollowingFirstGap`と`NoDiscard`値、`IncompleteSequenceBehavior`要素。</span><span class="sxs-lookup"><span data-stu-id="d07c8-136">B1108: WCF uses only the `DiscardFollowingFirstGap` and `NoDiscard` values in the `IncompleteSequenceBehavior` element.</span></span>

  - <span data-ttu-id="d07c8-137">WS-ReliableMessaging では、セッションを形成する、相関する 2 つの逆方向シーケンスを確立するために、`Offer` 機構を利用しています。</span><span class="sxs-lookup"><span data-stu-id="d07c8-137">WS-ReliableMessaging utilizes the `Offer` mechanism to establish the two converse correlated sequences that form a session.</span></span>

- <span data-ttu-id="d07c8-138">B1109:場合`CreateSequence`が含まれています、`Offer`で応答することの要素、一方向の WCF レスポンダー拒否シーケンス、`CreateSequenceResponse`せず、`Accept`要素。</span><span class="sxs-lookup"><span data-stu-id="d07c8-138">B1109: If `CreateSequence` contains an `Offer` element, the one way WCF Responder rejects the offered sequence by responding with a `CreateSequenceResponse` without an `Accept` element.</span></span>

- <span data-ttu-id="d07c8-139">B1110:信頼できるメッセージング レスポンダーは、シーケンスを拒否する場合、WCF イニシエーター障害新しく確立されたシーケンスにします。</span><span class="sxs-lookup"><span data-stu-id="d07c8-139">B1110: If a Reliable Messaging Responder rejects the offered sequence, the WCF Initiator faults the newly established sequence.</span></span>

- <span data-ttu-id="d07c8-140">B1111:場合`CreateSequence`が含まれていない、`Offer`で応答することの要素、双方向の WCF レスポンダー拒否シーケンス、`CreateSequenceRefused`エラー。</span><span class="sxs-lookup"><span data-stu-id="d07c8-140">B1111: If `CreateSequence` does not contain an `Offer` element, the two-way WCF Responder rejects the offered sequence by responding with a `CreateSequenceRefused` fault.</span></span>

- <span data-ttu-id="d07c8-141">R1112:使用して 2 つの逆方向シーケンスが確立されたときに、`Offer`メカニズム、`[address]`のプロパティ、`CreateSequenceResponse/Accept/AcksTo`エンドポイント参照は送信先 URI と一致する必要がありますの`CreateSequence`バイトのメッセージのバイト。</span><span class="sxs-lookup"><span data-stu-id="d07c8-141">R1112: When two converse sequences are established using the `Offer` mechanism, the `[address]` property of the `CreateSequenceResponse/Accept/AcksTo` endpoint reference must match the destination URI of the `CreateSequence` message byte for byte.</span></span>

- <span data-ttu-id="d07c8-142">R1113:使用して 2 つの逆方向シーケンスが確立されたときに、`Offer`メカニズム、イニシエーターからレスポンダーに送られて、両方のシーケンスのすべてのメッセージは、同じエンドポイント参照に送信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d07c8-142">R1113: When two converse sequences are established using the `Offer` mechanism, all messages on both sequences flowing from the Initiator to the Responder must be sent to the same endpoint reference.</span></span>

<span data-ttu-id="d07c8-143">WCF では、WS-ReliableMessaging を使用して、イニシエーターとレスポンダー間の信頼できるセッションを確立します。</span><span class="sxs-lookup"><span data-stu-id="d07c8-143">WCF uses WS-ReliableMessaging to establish reliable sessions between the Initiator and the Responder.</span></span> <span data-ttu-id="d07c8-144">WCF の WS-ReliableMessaging 実装は、一方向、要求/応答、信頼できるセッションを提供します。 双方向メッセージング パターン。</span><span class="sxs-lookup"><span data-stu-id="d07c8-144">The WCF WS-ReliableMessaging implementation provides a reliable session for one-way, request-reply and full duplex messaging patterns.</span></span> <span data-ttu-id="d07c8-145">`Offer` および `CreateSequence` で WS-ReliableMessaging の `CreateSequenceResponse` 機構を使用すると、相関する 2 つの逆方向シーケンスを確立できます。また、Offer 機構は、すべてのメッセージ エンドポイントに適したセッション プロトコルを提供します。</span><span class="sxs-lookup"><span data-stu-id="d07c8-145">The WS-ReliableMessaging `Offer` mechanism on `CreateSequence` and `CreateSequenceResponse` lets you establish two correlated converse sequences and provides a session protocol that is suitable for all message endpoints.</span></span> <span data-ttu-id="d07c8-146">WCF では、セッションのセッションの整合性をエンド ツー エンドの保護などのセキュリティ保証を提供するため、同じパーティ宛てのメッセージが同じ送信先に到達することを確認するは実用的です。</span><span class="sxs-lookup"><span data-stu-id="d07c8-146">Because WCF provides a security guarantee for such a session including end-to-end protection for session integrity, it is practical to ensure that messages intended for the same party arrive at the same destination.</span></span> <span data-ttu-id="d07c8-147">また、これにより、アプリケーション メッセージにシーケンス受信確認を抱き合わせることができます。</span><span class="sxs-lookup"><span data-stu-id="d07c8-147">This also allows "piggy-backing" of sequence acknowledgements on application messages.</span></span> <span data-ttu-id="d07c8-148">そのため、R1102、R1112、および R1113 の制約は、WCF に適用されます。</span><span class="sxs-lookup"><span data-stu-id="d07c8-148">Therefore, constraints R1102, R1112, and R1113 apply to WCF.</span></span>

<span data-ttu-id="d07c8-149">`CreateSequence` メッセージの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="d07c8-149">An example of a `CreateSequence` message.</span></span>

```xml
<s:Envelope>
  <s:Header>
    <wsa:Action s:mustUnderstand="1">http://docs.oasis-open.org/ws-rx/wsrm/200702/CreateSequence</wsa:Action>
    <wsa:MessageID>urn:uuid:949cca61-8813-42ff-ab33-18d9e3fa82fa</wsa:MessageID>
    <wsa:ReplyTo>
        <wsa:Address>http://Business456.com/clientA</wsa:Address>
    </wsa:ReplyTo>
    <wsa:To s:mustUnderstand="1">http://BusinessABC.com/serviceA</wsa:To>
  </s:Header>
  <s:Body>
    <wsrm:CreateSequence>
      <wsrm:AcksTo>
        <wsa:Address>http://Business456.com/clientA</wsa:Address>
      </wsrm:AcksTo>
      <wsrm:Offer>
        <wsrm:Identifier>urn:uuid:066b4730-fc82-458a-a5c1-210be4fb4e4e</wsrm:Identifier>
        <wsrm:Endpoint>
          <wsa:Address>http://Business456.com/clientA</wsa:Address>
        </wsrm:Endpoint>
        <wsrm:IncompleteSequenceBehavior>DiscardFollowingFirstGap</wsrm:IncompleteSequenceBehavior>
      </wsrm:Offer>
    </wsrm:CreateSequence>
  </s:Body>
</s:Envelope>
```

<span data-ttu-id="d07c8-150">`CreateSequenceResponse` メッセージの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="d07c8-150">An example of a `CreateSequenceResponse` message.</span></span>

```xml
<s:Envelope>
  <s:Header>
    <wsa:Action s:mustUnderstand="1">http://docs.oasis-open.org/ws-rx/wsrm/200702/CreateSequenceResponse</wsa:Action>
    <wsa:RelatesTo>urn:uuid:949cca61-8813-42ff-ab33-18d9e3fa82fa</wsa:RelatesTo>
    <wsa:To s:mustUnderstand="1">http://Business456.com/clientA</wsa:To>
  </s:Header>
  <s:Body>
    <wsrm:CreateSequenceResponse>
      <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>
      <wsrm:IncompleteSequenceBehavior>DiscardFollowingFirstGap</wsrm:IncompleteSequenceBehavior>
      <wsrm:Accept>
        <wsrm:AcksTo>
          <wsa:Address>http://BusinessABC.com/serviceA</wsa:Address>
        </wsrm:AcksTo>
      </wsrm:Accept>
    </wsrm:CreateSequenceResponse>
  </s:Body>
</s:Envelope>
```

### <a name="closing-a-sequence"></a><span data-ttu-id="d07c8-151">シーケンスを閉じる</span><span class="sxs-lookup"><span data-stu-id="d07c8-151">Closing a Sequence</span></span>

<span data-ttu-id="d07c8-152">WCF を使用して、`CloseSequence`と`CloseSequenceResponse`信頼性の高いメッセージング ソースが開始したシャット ダウンのメッセージ。</span><span class="sxs-lookup"><span data-stu-id="d07c8-152">WCF uses the `CloseSequence` and `CloseSequenceResponse` messages for a Reliable Messaging source-initiated shutdown.</span></span> <span data-ttu-id="d07c8-153">WCF の信頼できるメッセージング送信先はシャット ダウンを開始していないと、WCF の信頼性の高いメッセージの送信元が信頼できるメッセージング送信先が開始したシャット ダウンをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="d07c8-153">The WCF Reliable Messaging destination does not initiate shutdown and the WCF Reliable Messaging source does not support a Reliable Messaging destination-initiated shutdown.</span></span> <span data-ttu-id="d07c8-154">以下の制約が適用されます。</span><span class="sxs-lookup"><span data-stu-id="d07c8-154">The following constraints apply:</span></span>

- <span data-ttu-id="d07c8-155">B1201:WCF の信頼性の高いメッセージの送信元を常に送信、`CloseSequence`メッセージ シーケンスをシャット ダウンします。</span><span class="sxs-lookup"><span data-stu-id="d07c8-155">B1201: The WCF Reliable Messaging source always sends a `CloseSequence` message to shut down the sequence.</span></span>

- <span data-ttu-id="d07c8-156">B1202:信頼性の高いメッセージの送信元が送信する前に、シーケンス メッセージの完全な範囲の確認を待機、`CloseSequence`メッセージ。</span><span class="sxs-lookup"><span data-stu-id="d07c8-156">B1202: The Reliable Messaging source waits for acknowledgement of the full range of sequence messages before sending the `CloseSequence` message.</span></span>

- <span data-ttu-id="d07c8-157">B1203:信頼できるメッセージング ソースに常には、省略可能な`LastMsgNumber`要素シーケンスにメッセージが含まれていない場合を除き、します。</span><span class="sxs-lookup"><span data-stu-id="d07c8-157">B1203: The Reliable Messaging source always includes the optional `LastMsgNumber` element unless the sequence does not contain messages.</span></span>

- <span data-ttu-id="d07c8-158">R1204:信頼性の高いメッセージの送信先を送信してシャット ダウンを開始する必要がありますいないを`CloseSequence`メッセージ。</span><span class="sxs-lookup"><span data-stu-id="d07c8-158">R1204: The Reliable Messaging destination must not initiate shutdown by sending a `CloseSequence` message.</span></span>

- <span data-ttu-id="d07c8-159">B1205:受信すると、`CloseSequence`メッセージ、WCF の信頼性の高いメッセージの送信元は不完全な順序を考慮し、エラーを送信します。</span><span class="sxs-lookup"><span data-stu-id="d07c8-159">B1205: Upon receiving a `CloseSequence` message, the WCF Reliable Messaging source considers the sequence incomplete and sends a fault.</span></span>

 <span data-ttu-id="d07c8-160">`CloseSequence` メッセージの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="d07c8-160">An example of a `CloseSequence` message.</span></span>

```xml
<s:Envelope>
  <s:Header>
    <wsa:Action s:mustUnderstand="1">http://docs.oasis-open.org/ws-rx/wsrm/200702/CloseSequence</wsa:Action>
    <wsa:MessageID>urn:uuid:6ce1d4c3-e1c1-474f-a8c9-4210e37f7877</wsa:MessageID>
    <wsa:ReplyTo>
      <wsa:Address>http://Business456.com/clientA</wsa:Address>
    </wsa:ReplyTo>
    <wsa:To s:mustUnderstand="1">http://BusinessABC.com/serviceA</wsa:To>
  </s:Header>
  <s:Body>
    <wsrm:CloseSequence>
      <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>
      <wsrm:LastMsgNumber>30</wsrm:LastMsgNumber>
    </wsrm:CloseSequence>
  </s:Body>
</s:Envelope>
```

<span data-ttu-id="d07c8-161">例`CloseSequenceResponse`メッセージ。</span><span class="sxs-lookup"><span data-stu-id="d07c8-161">Example `CloseSequenceResponse` message:</span></span>

```xml
<s:Envelope>
  <s:Header>
    <wsrm:SequenceAcknowledgement>
      <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>
      <wsrm:AcknowledgementRange Lower="1" Upper="30"></wsrm:AcknowledgementRange>
      <wsrm:Final></wsrm:Final>
      <netrm:BufferRemaining>8</netrm:BufferRemaining>
    </wsrm:SequenceAcknowledgement>
    <wsa:Action s:mustUnderstand="1">http://docs.oasis-open.org/ws-rx/wsrm/200702/CloseSequenceResponse</wsa:Action>
    <wsa:RelatesTo>urn:uuid:6ce1d4c3-e1c1-474f-a8c9-4210e37f7877</wsa:RelatesTo>
    <wsa:To s:mustUnderstand="1">http://Business456.com/clientA</wsa:To>
  </s:Header>
  <s:Body>
    <wsrm:CloseSequenceResponse>
      <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>
    </wsrm:CloseSequenceResponse>
  </s:Body>
</s:Envelope>
```

### <a name="sequence-termination"></a><span data-ttu-id="d07c8-162">シーケンスの終了</span><span class="sxs-lookup"><span data-stu-id="d07c8-162">Sequence Termination</span></span>

<span data-ttu-id="d07c8-163">WCF は主に使用して、`TerminateSequence/TerminateSequenceResponse`ハンドシェイクが完了した後、`CloseSequence/CloseSequenceResponse`ハンドシェイクです。</span><span class="sxs-lookup"><span data-stu-id="d07c8-163">WCF primarily uses the `TerminateSequence/TerminateSequenceResponse` handshake after completing the `CloseSequence/CloseSequenceResponse` handshake.</span></span> <span data-ttu-id="d07c8-164">WCF の信頼できるメッセージング送信先は終了を開始していないと、信頼性の高いメッセージの送信元が信頼できるメッセージング送信先が開始終了をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="d07c8-164">The WCF Reliable Messaging destination does not initiate termination and the Reliable Messaging source does not support a Reliable Messaging destination-initiated termination.</span></span> <span data-ttu-id="d07c8-165">以下の制約が適用されます。</span><span class="sxs-lookup"><span data-stu-id="d07c8-165">The following constraints apply:</span></span>

- <span data-ttu-id="d07c8-166">B1301:WCF イニシエーターのみを送信、`TerminateSequence`メッセージが正常に完了した後、`CloseSequence/CloseSequenceResponse`ハンドシェイクです。</span><span class="sxs-lookup"><span data-stu-id="d07c8-166">B1301: The WCF Initiator only sends the `TerminateSequence` message after the successful completion of the `CloseSequence/CloseSequenceResponse` handshake.</span></span>

- <span data-ttu-id="d07c8-167">R1302:WCF の点を検証、`LastMsgNumber`要素がすべて間で一貫性のある`CloseSequence`と`TerminateSequence`特定のシーケンスのメッセージ。</span><span class="sxs-lookup"><span data-stu-id="d07c8-167">R1302: WCF validates that the `LastMsgNumber` element is consistent across all `CloseSequence` and `TerminateSequence` messages for a given sequence.</span></span> <span data-ttu-id="d07c8-168">つまり、`LastMsgNumber` は、すべての `CloseSequence` メッセージおよび `TerminateSequence` メッセージに存在しないか、すべての `CloseSequence` メッセージおよび `TerminateSequence` メッセージに存在し、同一であるかのいずれかです。</span><span class="sxs-lookup"><span data-stu-id="d07c8-168">This means that `LastMsgNumber` is either not present on all `CloseSequence` and `TerminateSequence` messages, or it is present and identical on all `CloseSequence` and `TerminateSequence` messages.</span></span>

- <span data-ttu-id="d07c8-169">B1303:受信するときに、`TerminateSequence`メッセージの後に、`CloseSequence/CloseSequenceResponse`ハンドシェイクで応答を信頼性の高いメッセージの送信先を`TerminateSequenceResponse`メッセージ。</span><span class="sxs-lookup"><span data-stu-id="d07c8-169">B1303: When receiving a `TerminateSequence` message after the `CloseSequence/CloseSequenceResponse` handshake, the Reliable Messaging destination responds with a `TerminateSequenceResponse` message.</span></span> <span data-ttu-id="d07c8-170">信頼できるメッセージの配信元は、`TerminateSequence` メッセージを送信する前に最終受信確認を受けるため、信頼できるメッセージの送信先ではシーケンスが終了したことが確実にわかり、すぐにリソースを再要求します。</span><span class="sxs-lookup"><span data-stu-id="d07c8-170">Because the Reliable Messaging source has the final acknowledgement before sending the `TerminateSequence` message, the Reliable Messaging destination knows without doubt that the sequence ends, and reclaims resources immediately.</span></span>

- <span data-ttu-id="d07c8-171">B1304:受信するときに、`TerminateSequence`メッセージより前のバージョンを`CloseSequence/CloseSequenceResponse`ハンドシェイクで応答を WCF の信頼性の高いメッセージの送信先を`TerminateSequenceResponse`メッセージ。</span><span class="sxs-lookup"><span data-stu-id="d07c8-171">B1304: When receiving a `TerminateSequence` message prior to the `CloseSequence/CloseSequenceResponse` handshake, the WCF Reliable Messaging destination responds with a `TerminateSequenceResponse` message.</span></span> <span data-ttu-id="d07c8-172">信頼できるメッセージの送信先でシーケンスが一貫していると判断した場合、信頼できるメッセージの送信先は、リソースを再要求する前にアプリケーションの送信先で指定された時間待機し、クライアントが最終受信確認を受け取ることができるようにします。</span><span class="sxs-lookup"><span data-stu-id="d07c8-172">If the Reliable Messaging destination determines that there are no inconsistencies in the sequence, the Reliable Messaging destination waits for an application destination-specified time before reclaiming resources, to allow the client the chance to receive the final acknowledgement.</span></span> <span data-ttu-id="d07c8-173">それ以外の場合は、信頼できるメッセージの送信先はすぐにリソースを再要求し、`Faulted` イベントを発生させて、不明なシーケンスの終了をアプリケーションの送信先に示します。</span><span class="sxs-lookup"><span data-stu-id="d07c8-173">Otherwise, the Reliable Messaging destination reclaims resources immediately and indicates to the application destination that the sequence ends with doubt by raising the `Faulted` event.</span></span>

<span data-ttu-id="d07c8-174">`TerminateSequence` メッセージの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="d07c8-174">An example of a `TerminateSequence` message.</span></span>

```xml
<s:Envelope>
  <s:Header>
    <wsa:Action s:mustUnderstand="1">http://docs.oasis-open.org/ws-rx/wsrm/200702/TerminateSequence</wsa:Action>
    <wsa:MessageID>urn:uuid:3597a398-4f3c-40f4-9335-8f1515572fdf</wsa:MessageID>
    <wsa:ReplyTo>
      <wsa:Address>http://Business456.com/clientA</wsa:Address>
    </wsa:ReplyTo>
    <wsa:To s:mustUnderstand="1">http://BusinessABC.com/serviceA</wsa:To>
  </s:Header>
  <s:Body>
    <wsrm:TerminateSequence>
      <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>
      <wsrm:LastMsgNumber>30</wsrm:LastMsgNumber>
      </wsrm:TerminateSequence>
  </s:Body>
</s:Envelope>
```

<span data-ttu-id="d07c8-175">例`TerminateSequenceResponse`メッセージ。</span><span class="sxs-lookup"><span data-stu-id="d07c8-175">Example `TerminateSequenceResponse` message:</span></span>

```xml
<s:Envelope>
  <s:Header>
    <wsrm:SequenceAcknowledgement>
      <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>
      <wsrm:AcknowledgementRange Lower="1" Upper="30"></wsrm:AcknowledgementRange>
      <wsrm:Final></wsrm:Final>
      <netrm:BufferRemaining>8</netrm:BufferRemaining>
    </wsrm:SequenceAcknowledgement>
    <wsa:Action s:mustUnderstand="1">http://docs.oasis-open.org/ws-rx/wsrm/200702/TerminateSequenceResponse</wsa:Action>
    <wsa:RelatesTo>urn:uuid:3597a398-4f3c-40f4-9335-8f1515572fdf</wsa:RelatesTo>
    <wsa:To s:mustUnderstand="1">://Business456.com/clientA</wsa:To>
  </s:Header>
  <s:Body>
    <wsrm:TerminateSequenceResponse>
      <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>
    </wsrm:TerminateSequenceResponse>
  </s:Body>
</s:Envelope>
```

### <a name="sequences"></a><span data-ttu-id="d07c8-176">シーケンス</span><span class="sxs-lookup"><span data-stu-id="d07c8-176">Sequences</span></span>

<span data-ttu-id="d07c8-177">シーケンスに適用される制約を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="d07c8-177">The following is a list of constraints that apply to sequences:</span></span>

- <span data-ttu-id="d07c8-178">B1401:WCF を生成し、アクセスのシーケンス番号より`xs:long`の最大の包含値 9223372036854775807 します。</span><span class="sxs-lookup"><span data-stu-id="d07c8-178">B1401:WCF generates and accesses sequence numbers no higher than `xs:long`’s maximum inclusive value, 9223372036854775807.</span></span>

<span data-ttu-id="d07c8-179">`Sequence` ヘッダーの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="d07c8-179">An example of a `Sequence` header.</span></span>

```xml
<wsrm:Sequence s:mustUnderstand="1">
  <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>
  <wsrm:MessageNumber>1</wsrm:MessageNumber>
</wsrm:Sequence>
```

### <a name="request-acknowledgement"></a><span data-ttu-id="d07c8-180">受信確認の要求</span><span class="sxs-lookup"><span data-stu-id="d07c8-180">Request Acknowledgement</span></span>

<span data-ttu-id="d07c8-181">WCF を使用して、 `AckRequested` keep-alive 機構としてヘッダー。</span><span class="sxs-lookup"><span data-stu-id="d07c8-181">WCF uses the `AckRequested` header as a keep-alive mechanism.</span></span>

<span data-ttu-id="d07c8-182">`AckRequested` ヘッダーの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="d07c8-182">An example of an `AckRequested` header.</span></span>

```xml
<wsrm:AckRequested>
  <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>
</wsrm:AckRequested>
```

### <a name="sequenceacknowledgement"></a><span data-ttu-id="d07c8-183">SequenceAcknowledgement</span><span class="sxs-lookup"><span data-stu-id="d07c8-183">SequenceAcknowledgement</span></span>

<span data-ttu-id="d07c8-184">WCF では、Ws-reliable Messaging で提供されているシーケンス受信確認の「抱き合わせ」メカニズムを使用します。</span><span class="sxs-lookup"><span data-stu-id="d07c8-184">WCF uses a "piggy-back" mechanism for sequence acknowledgements provided in WS-Reliable Messaging.</span></span> <span data-ttu-id="d07c8-185">以下の制約が適用されます。</span><span class="sxs-lookup"><span data-stu-id="d07c8-185">The following constraints apply:</span></span>

- <span data-ttu-id="d07c8-186">R1601:使用して 2 つの逆方向シーケンスが確立されたときに、`Offer`メカニズム、`SequenceAcknowledgement`目的の受信者に送信アプリケーション メッセージ ヘッダーを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="d07c8-186">R1601: When two converse sequences are established using the `Offer` mechanism, the `SequenceAcknowledgement` header may be included in any application message transmitted to the intended recipient.</span></span> <span data-ttu-id="d07c8-187">リモートのエンドポイントは、追加された `SequenceAcknowledgement` ヘッダーにアクセスできる必要があります。</span><span class="sxs-lookup"><span data-stu-id="d07c8-187">The remote endpoint must be able to access a piggybacked `SequenceAcknowledgement` header.</span></span>

- <span data-ttu-id="d07c8-188">B1602:WCF は生成されません`SequenceAcknowledgement`ヘッダーが含まれている`Nack`要素。</span><span class="sxs-lookup"><span data-stu-id="d07c8-188">B1602: WCF does not generate `SequenceAcknowledgement` headers that contain `Nack` elements.</span></span> <span data-ttu-id="d07c8-189">WCF では、その各を検証`Nack`要素は、シーケンス番号が含まれていますが、それ以外の場合は無視されます、`Nack`要素と値。</span><span class="sxs-lookup"><span data-stu-id="d07c8-189">WCF validates that each `Nack` element contains a sequence number, but otherwise ignores the `Nack` element and value.</span></span>

 <span data-ttu-id="d07c8-190">`SequenceAcknowledgement` ヘッダーの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="d07c8-190">An example of a `SequenceAcknowledgement` header.</span></span>

```xml
<wsrm:SequenceAcknowledgement>
  <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>
  <wsrm:AcknowledgementRange Lower="1" Upper="1"></wsrm:AcknowledgementRange>
</wsrm:SequenceAcknowledgement>
```

### <a name="ws-reliablemessaging-faults"></a><span data-ttu-id="d07c8-191">WS-ReliableMessaging エラー</span><span class="sxs-lookup"><span data-stu-id="d07c8-191">WS-ReliableMessaging Faults</span></span>

<span data-ttu-id="d07c8-192">次は、WS-ReliableMessaging エラーの WCF 実装に適用される制約の一覧です。</span><span class="sxs-lookup"><span data-stu-id="d07c8-192">The following is a list of constraints that apply to the WCF implementation of WS-ReliableMessaging faults.</span></span> <span data-ttu-id="d07c8-193">以下の制約が適用されます。</span><span class="sxs-lookup"><span data-stu-id="d07c8-193">The following constraints apply:</span></span>

- <span data-ttu-id="d07c8-194">B1701:WCF は生成されません`MessageNumberRollover`エラー。</span><span class="sxs-lookup"><span data-stu-id="d07c8-194">B1701: WCF does not generate `MessageNumberRollover` faults.</span></span>

- <span data-ttu-id="d07c8-195">B1702:SOAP 1.2 では、経由でサービス エンドポイントは、接続の上限に達するし、新しい接続を処理することはできません WCF が生成されます、入れ子になった`CreateSequenceRefused`エラー サブコード`netrm:ConnectionLimitReached`次の例のようにします。</span><span class="sxs-lookup"><span data-stu-id="d07c8-195">B1702: Over SOAP 1.2, when the service endpoint reaches its connection limit and cannot process new connections, WCF generates a nested `CreateSequenceRefused` fault subcode, `netrm:ConnectionLimitReached`, as shown in the following example.</span></span>

```xml
<s:Envelope>
  <s:Header>
    <wsa:Action>http://docs.oasis-open.org/ws-rx/wsrm/200702/fault</wsa:Action>
  </s:Header>
  <s:Body>
    <s:Fault>
      <s:Code>
        <s:Value>s:Receiver</s:Value>
        <s:Subcode>
          <s:Value>wsrm:CreateSequenceRefused</s:Value>
          <s:Subcode>
            <s:Value>netrm:ConnectionLimitReached</s:Value>
          </s:Subcode>
        </s:Subcode>
      </s:Code>
      <s:Reason>
        <s:Text xml:lang="en">Server 'http://BusinessABC.com/serviceA' is too busy to process this request. Try again later.</s:Text>
      </s:Reason>
    </s:Fault>
  </s:Body>
</s:Envelope>
```

### <a name="ws-addressing-faults"></a><span data-ttu-id="d07c8-196">WS-Addressing エラー</span><span class="sxs-lookup"><span data-stu-id="d07c8-196">WS-Addressing Faults</span></span>

<span data-ttu-id="d07c8-197">WS-ReliableMessaging は Ws-addressing を使用しているため、WCF の WS-ReliableMessaging 実装を生成して Ws-addressing エラーを送信する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d07c8-197">Because WS-ReliableMessaging uses WS-Addressing, the WCF WS-ReliableMessaging implementation may generate and transmit WS-Addressing faults.</span></span> <span data-ttu-id="d07c8-198">このセクションでは、WCF は、明示的に生成し、WS-ReliableMessaging レイヤーで送信する Ws-addressing エラーについて説明します。</span><span class="sxs-lookup"><span data-stu-id="d07c8-198">This section covers the WS-Addressing faults that WCF explicitly generates and transmits at the WS-ReliableMessaging layer:</span></span>

- <span data-ttu-id="d07c8-199">B1801:WCF 生成し、送信、`Message Addressing Header Required`障害、次のいずれかが true の場合。</span><span class="sxs-lookup"><span data-stu-id="d07c8-199">B1801:WCF generates and transmits the `Message Addressing Header Required` fault when one of the following is true:</span></span>

  - <span data-ttu-id="d07c8-200">`CreateSequence`、`CloseSequence`、または `TerminateSequence` メッセージに `MessageId` ヘッダーがない。</span><span class="sxs-lookup"><span data-stu-id="d07c8-200">A `CreateSequence`, `CloseSequence` or `TerminateSequence` message is missing a `MessageId` header.</span></span>

  - <span data-ttu-id="d07c8-201">`CreateSequence`、`CloseSequence`、または `TerminateSequence` メッセージに `ReplyTo` ヘッダーがない。</span><span class="sxs-lookup"><span data-stu-id="d07c8-201">A `CreateSequence`, `CloseSequence` or `TerminateSequence` message is missing a `ReplyTo` header.</span></span>

  - <span data-ttu-id="d07c8-202">`CreateSequenceResponse`、`CloseSequenceResponse`、または `TerminateSequenceResponse` メッセージに `RelatesTo` ヘッダーがない。</span><span class="sxs-lookup"><span data-stu-id="d07c8-202">A `CreateSequenceResponse`, `CloseSequenceResponse`, or `TerminateSequenceResponse` message is missing a `RelatesTo` header.</span></span>

- <span data-ttu-id="d07c8-203">B1802:WCF 生成し、送信、`Endpoint Unavailable`をリッスンしているエンドポイントがないことを示すエラーでアドレス指定ヘッダーの検査に基づいてシーケンスを処理することができます、`CreateSequence`メッセージ。</span><span class="sxs-lookup"><span data-stu-id="d07c8-203">B1802:WCF generates and transmits the `Endpoint Unavailable` fault to indicate there is no endpoint listening that can process the sequence based on examination of the addressing headers in the `CreateSequence` message.</span></span>

## <a name="protocol-composition"></a><span data-ttu-id="d07c8-204">プロトコル コンポジション</span><span class="sxs-lookup"><span data-stu-id="d07c8-204">Protocol Composition</span></span>

### <a name="composition-with-ws-addressing"></a><span data-ttu-id="d07c8-205">WS-Addressing によるコンポジション</span><span class="sxs-lookup"><span data-stu-id="d07c8-205">Composition with WS-Addressing</span></span>

<span data-ttu-id="d07c8-206">WCF には、Ws-addressing の 2 つのバージョンがサポートされています。Ws-addressing 2004/08 [WS-ADDR] と W3C Ws-addressing 1.0 の推奨事項 [WS ADDR コア] と [WS ADDR SOAP]。</span><span class="sxs-lookup"><span data-stu-id="d07c8-206">WCF supports two versions of WS-Addressing: WS-Addressing 2004/08 [WS-ADDR] and W3C WS-Addressing 1.0 Recommendations [WS-ADDR-CORE] and [WS-ADDR-SOAP].</span></span>

<span data-ttu-id="d07c8-207">WS-ReliableMessaging 仕様に記載されているのは、WS-Addressing 2004/08 だけですが、使用する WS-Addressing のバージョンが制限されているわけではありません。</span><span class="sxs-lookup"><span data-stu-id="d07c8-207">While the WS-ReliableMessaging specification mentions only WS-Addressing 2004/08, it does not restrict the WS-Addressing version to be used.</span></span> <span data-ttu-id="d07c8-208">WCF に適用される制約の一覧を次には。</span><span class="sxs-lookup"><span data-stu-id="d07c8-208">The following is a list of constraints that apply to WCF:</span></span>

- <span data-ttu-id="d07c8-209">R2101:Ws-addressing 2004/08 と Ws-addressing 1.0 の両方を Ws-reliablemessaging で使用できます。</span><span class="sxs-lookup"><span data-stu-id="d07c8-209">R2101: Both WS-Addressing 2004/08 and WS-Addressing 1.0 can be used with WS-Reliable Messaging.</span></span>

- <span data-ttu-id="d07c8-210">R2102:特定の WS-ReliableMessaging シーケンス、またはを使用して関連付けられた逆方向シーケンスのペアを 1 つのバージョンの Ws-addressing を使用する必要があります、`Offer`メカニズム。</span><span class="sxs-lookup"><span data-stu-id="d07c8-210">R2102: A single version of WS-Addressing must be used throughout a given WS-ReliableMessaging sequence or a pair of converse sequences correlated by using the `Offer` mechanism.</span></span>

### <a name="composition-with-soap"></a><span data-ttu-id="d07c8-211">SOAP によるコンポジション</span><span class="sxs-lookup"><span data-stu-id="d07c8-211">Composition with SOAP</span></span>

<span data-ttu-id="d07c8-212">WCF では、SOAP 1.1 と Ws-reliablemessaging で SOAP 1.2 の両方の使用をサポートします。</span><span class="sxs-lookup"><span data-stu-id="d07c8-212">WCF supports the use of both SOAP 1.1 and SOAP 1.2 with WS-Reliable Messaging.</span></span>

### <a name="composition-with-ws-security-and-ws-secureconversation"></a><span data-ttu-id="d07c8-213">WS-Security と WS-SecureConversation によるコンポジション</span><span class="sxs-lookup"><span data-stu-id="d07c8-213">Composition with WS-Security and WS-SecureConversation</span></span>

<span data-ttu-id="d07c8-214">WCF は、Ws-secure Conversation をセキュリティで保護されたトランスポート (HTTPS)、Ws-security によるコンポジション、およびコンポジションを使用して、WS-ReliableMessaging シーケンスを保護を提供します。</span><span class="sxs-lookup"><span data-stu-id="d07c8-214">WCF provides protection for WS-ReliableMessaging sequences by using secure Transport (HTTPS), composition with WS-Security, and composition with WS-Secure Conversation.</span></span> <span data-ttu-id="d07c8-215">WS-ReliableMessaging 1.1 プロトコル、WS-Security 1.1、および WS-Secure Conversation 1.3 プロトコルは一緒に使う必要があります。</span><span class="sxs-lookup"><span data-stu-id="d07c8-215">The WS-ReliableMessaging 1.1 protocol, WS-Security 1.1 and WS-Secure Conversation 1.3 protocol should be used together.</span></span> <span data-ttu-id="d07c8-216">WCF に適用される制約の一覧を次には。</span><span class="sxs-lookup"><span data-stu-id="d07c8-216">The following is a list of constraints that apply to WCF:</span></span>

- <span data-ttu-id="d07c8-217">R2301:WCF では、個々 のメッセージの整合性だけでなく、WS-ReliableMessaging シーケンスの整合性と機密性を保護するには、Ws-secure Conversation を使用する必要がある必要があります。</span><span class="sxs-lookup"><span data-stu-id="d07c8-217">R2301: To protect the integrity of a WS-ReliableMessaging sequence in addition to the integrity and confidentiality of individual messages, WCF requires that WS-Secure Conversation must be used.</span></span>

- <span data-ttu-id="d07c8-218">R2302:AWS-WS-ReliableMessaging シーケンスを確立する前にメッセージ交換をセキュリティで保護されたセッションを確立する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d07c8-218">R2302:AWS-Secure Conversation session must be established prior to establishing WS-ReliableMessaging sequence(s).</span></span>

- <span data-ttu-id="d07c8-219">R2303:WS-ReliableMessaging シーケンスの有効期間がセッションの有効期間、Ws-secure Conversation を超えた場合、 `SecurityContextToken` Ws-secure Conversation は、対応する Ws-secure Conversation の更新のバインドを使用して更新する必要がありますを使用して確立されます。</span><span class="sxs-lookup"><span data-stu-id="d07c8-219">R2303: If the WS-ReliableMessaging sequence lifetime exceeds the WS-Secure Conversation session’s lifetime, the `SecurityContextToken` established by using WS-Secure Conversation must be renewed by using the corresponding WS-Secure Conversation Renewal binding.</span></span>

- <span data-ttu-id="d07c8-220">B2304:WS-ReliableMessaging シーケンスまたは相関する逆方向シーケンスのペアは、常に 1 つが Ws-secureconversation セッションにバインドします。</span><span class="sxs-lookup"><span data-stu-id="d07c8-220">B2304:WS-ReliableMessaging sequence or a pair of correlated converse sequences are always bound to a single WS-SecureConversation session.</span></span>

- <span data-ttu-id="d07c8-221">R2305:WCF 応答側がある必要がありますで Ws-secure Conversation で構成されているときに、`CreateSequence`メッセージが含まれて、`wsse:SecurityTokenReference`要素と`wsrm:UsesSequenceSTR`ヘッダー。</span><span class="sxs-lookup"><span data-stu-id="d07c8-221">R2305: When composed with WS-Secure Conversation, the WCF responder requires that the `CreateSequence` message contain the `wsse:SecurityTokenReference` element and the `wsrm:UsesSequenceSTR` header.</span></span>

 <span data-ttu-id="d07c8-222">`UsesSequenceSTR` ヘッダーの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="d07c8-222">An example of a `UsesSequenceSTR` header.</span></span>

```xml
<wsrm:UsesSequenceSTR></wsrm:UsesSequenceSTR>
```

### <a name="composition-with-ssltls-sessions"></a><span data-ttu-id="d07c8-223">SSL/TLS セッションによるコンポジション</span><span class="sxs-lookup"><span data-stu-id="d07c8-223">Composition with SSL/TLS sessions</span></span>

<span data-ttu-id="d07c8-224">WCF は、SSL/TLS セッションによるコンポジションをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="d07c8-224">WCF does not support composition with SSL/TLS sessions:</span></span>

- <span data-ttu-id="d07c8-225">B2401:WCF は生成されません、`wsrm:UsesSequenceSSL`ヘッダー。</span><span class="sxs-lookup"><span data-stu-id="d07c8-225">B2401: WCF does not generate the `wsrm:UsesSequenceSSL` header.</span></span>

- <span data-ttu-id="d07c8-226">R2402:信頼性の高いメッセージングの発信側が送信する必要があります、`CreateSequence`メッセージである、 `wsrm:UsesSequenceSSL` WCF レスポンダーにヘッダー。</span><span class="sxs-lookup"><span data-stu-id="d07c8-226">R2402: A Reliable Messaging Initiator must not send a `CreateSequence` message with a `wsrm:UsesSequenceSSL` header to a WCF Responder.</span></span>

### <a name="composition-with-ws-policy"></a><span data-ttu-id="d07c8-227">WS-Policy によるコンポジション</span><span class="sxs-lookup"><span data-stu-id="d07c8-227">Composition with WS-Policy</span></span>

<span data-ttu-id="d07c8-228">WCF には、Ws-policy の 2 つのバージョンがサポートされています。Ws-policy 1.2 および Ws-policy 1.5 の場合は。</span><span class="sxs-lookup"><span data-stu-id="d07c8-228">WCF supports two versions of WS-Policy: WS-Policy 1.2 and WS-Policy 1.5.</span></span>

## <a name="ws-reliablemessaging-ws-policy-assertion"></a><span data-ttu-id="d07c8-229">WS-ReliableMessaging の WS-Policy アサーション</span><span class="sxs-lookup"><span data-stu-id="d07c8-229">WS-ReliableMessaging WS-Policy Assertion</span></span>

<span data-ttu-id="d07c8-230">WS-ReliableMessaging の Ws-policy アサーションを使用する WCF`wsrm:RMAssertion`エンドポイントの機能を記述します。</span><span class="sxs-lookup"><span data-stu-id="d07c8-230">WCF uses WS-ReliableMessaging WS-Policy Assertion `wsrm:RMAssertion` to describe endpoints capabilities.</span></span> <span data-ttu-id="d07c8-231">WCF に適用される制約の一覧を次には。</span><span class="sxs-lookup"><span data-stu-id="d07c8-231">The following is a list of constraints that apply to WCF:</span></span>

- <span data-ttu-id="d07c8-232">B3001:WCF のアタッチ`wsrmn:RMAssertion`Ws-policy アサーションを`wsdl:binding`要素。</span><span class="sxs-lookup"><span data-stu-id="d07c8-232">B3001: WCF attaches `wsrmn:RMAssertion` WS-Policy Assertion to `wsdl:binding` elements.</span></span> <span data-ttu-id="d07c8-233">WCF では、両方の添付ファイルを`wsdl:binding`と`wsdl:port`要素。</span><span class="sxs-lookup"><span data-stu-id="d07c8-233">WCF supports both attachments to `wsdl:binding` and `wsdl:port` elements.</span></span>

- <span data-ttu-id="d07c8-234">B3002:WCF では生成されません、`wsp:Optional`タグ。</span><span class="sxs-lookup"><span data-stu-id="d07c8-234">B3002: WCF never generates the `wsp:Optional` tag.</span></span>

- <span data-ttu-id="d07c8-235">B3003:アクセスするとき、 `wsrmp:RMAssertion` Ws-policy アサーションでは、WCF は無視されます、`wsp:Optional`タグ付けし、WS-RM ポリシーを必須として扱われます。</span><span class="sxs-lookup"><span data-stu-id="d07c8-235">B3003: When accessing the `wsrmp:RMAssertion` WS-Policy Assertion, WCF ignores the `wsp:Optional` tag and treats the WS-RM policy as mandatory.</span></span>

- <span data-ttu-id="d07c8-236">R3004:WCF を指定するポリシーを受け付けません WCF は、SSL/TLS セッションでは構成できません、ため`wsrmp:SequenceTransportSecurity`します。</span><span class="sxs-lookup"><span data-stu-id="d07c8-236">R3004: Because WCF does not compose with SSL/TLS sessions, WCF does not accept policy that specifies `wsrmp:SequenceTransportSecurity`.</span></span>

- <span data-ttu-id="d07c8-237">B3005:WCF は常に生成、`wsrmp:DeliveryAssurance`要素。</span><span class="sxs-lookup"><span data-stu-id="d07c8-237">B3005: WCF always generates the `wsrmp:DeliveryAssurance` element.</span></span>

- <span data-ttu-id="d07c8-238">B3006:WCF は常を指定します、`wsrmp:ExactlyOnce`配信が保証されます。</span><span class="sxs-lookup"><span data-stu-id="d07c8-238">B3006: WCF always specifies the `wsrmp:ExactlyOnce` delivery assurance.</span></span>

- <span data-ttu-id="d07c8-239">B3007:WCF が生成されます、WS-ReliableMessaging アサーションの以下のプロパティを読み取るし、WCF の上にコントロールを提供します`ReliableSessionBindingElement`:。</span><span class="sxs-lookup"><span data-stu-id="d07c8-239">B3007: WCF generates and reads the following properties of the WS-ReliableMessaging assertion and provides control over them on the WCF`ReliableSessionBindingElement`:</span></span>

  - `netrmp:InactivityTimeout`

  - `netrmp:AcknowledgementInterval`

  <span data-ttu-id="d07c8-240">`RMAssertion` の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="d07c8-240">An example of a `RMAssertion`.</span></span>

  ```xml
  <wsrmp:RMAssertion>
    <wsp:Policy>
      <wsrmp:SequenceSTR/>
      <wsrmp:DeliveryAssurance>
        <wsp:Policy>
          <wsrmp:ExactlyOnce/>
          <wsrmp:InOrder/>
        </wsp:Policy>
      </wsrmp:DeliveryAssurance>
    </wsp:Policy>
    <netrmp:InactivityTimeout Milliseconds="600000"/>
    <netrmp:AcknowledgementInterval Milliseconds="200"/>
  </wsrmp:RMAssertion>
  ```

## <a name="flow-control-ws-reliablemessaging-extension"></a><span data-ttu-id="d07c8-241">WS-ReliableMessaging のフロー制御拡張</span><span class="sxs-lookup"><span data-stu-id="d07c8-241">Flow Control WS-ReliableMessaging Extension</span></span>

<span data-ttu-id="d07c8-242">WCF では、WS-ReliableMessaging の機能拡張を使用して、シーケンス メッセージ フローを省略可能なさらに厳密な制御を提供します。</span><span class="sxs-lookup"><span data-stu-id="d07c8-242">WCF uses WS-ReliableMessaging extensibility to provide optional additional tighter control over sequence message flow.</span></span>

<span data-ttu-id="d07c8-243">フロー制御が有効になって、<xref:System.ServiceModel.Channels.ReliableSessionBindingElement.FlowControlEnabled?displayProperty=nameWithType>プロパティを`true`します。</span><span class="sxs-lookup"><span data-stu-id="d07c8-243">Flow control is enabled by setting the <xref:System.ServiceModel.Channels.ReliableSessionBindingElement.FlowControlEnabled?displayProperty=nameWithType> property to `true`.</span></span> <span data-ttu-id="d07c8-244">WCF に適用される制約の一覧を次には。</span><span class="sxs-lookup"><span data-stu-id="d07c8-244">The following is a list of constraints that apply to WCF:</span></span>

- <span data-ttu-id="d07c8-245">B4001:信頼できるメッセージング フロー制御を有効にすると、WCF が生成されます、`netrm:BufferRemaining`内の要素拡張の要素、`SequenceAcknowledgement`ヘッダー、次の例に示すようにします。</span><span class="sxs-lookup"><span data-stu-id="d07c8-245">B4001: When Reliable Messaging Flow Control is enabled, WCF generates a `netrm:BufferRemaining` element in the element extensibility of the `SequenceAcknowledgement` header, as shown in the following example.</span></span>

  ```xml
  <wsrm:SequenceAcknowledgement>
    <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>
    <wsrm:AcknowledgementRange Upper="1" Lower="1"/>
    <netrm:BufferRemaining>8</netrm:BufferRemaining>
  </wsrm:SequenceAcknowledgement>
  ```

- <span data-ttu-id="d07c8-246">B4002:信頼できるメッセージング フロー制御が有効になっている場合でも、WCF は必要ありません、`netrm:BufferRemaining`内の要素、`SequenceAcknowledgement`ヘッダー。</span><span class="sxs-lookup"><span data-stu-id="d07c8-246">B4002: Even when Reliable Messaging Flow Control is enabled, WCF does not require a `netrm:BufferRemaining` element in the `SequenceAcknowledgement` header.</span></span>

- <span data-ttu-id="d07c8-247">B4003:信頼できるメッセージング送信先の WCF を使用して`netrm:BufferRemaining`を新しいメッセージの数にする方法を示すために入れることができます。</span><span class="sxs-lookup"><span data-stu-id="d07c8-247">B4003: WCF Reliable Messaging Destination uses `netrm:BufferRemaining` to indicate how many new messages it can buffer.</span></span>

- <span data-ttu-id="d07c8-248">B4004:When 信頼できるメッセージング フロー制御が有効になっているの値を使用する WCF の信頼性の高いメッセージング ソース`netrm:BufferRemaining`スロットル メッセージを転送します。</span><span class="sxs-lookup"><span data-stu-id="d07c8-248">B4004:When Reliable Messaging Flow Control is enabled, the WCF Reliable Messaging Source uses the value of `netrm:BufferRemaining` to throttle message transmission.</span></span>

- <span data-ttu-id="d07c8-249">B4005:WCF が生成されます`netrm:BufferRemaining`整数 0 ~ 4096 の範囲、範囲の値し、0 までの整数値を読み取ると`xs:int`の`maxInclusive`214748364 の値します。</span><span class="sxs-lookup"><span data-stu-id="d07c8-249">B4005: WCF generates `netrm:BufferRemaining` integer values between 0 and 4096 inclusive, and reads integer values between 0 and `xs:int`’s `maxInclusive` value 214748364 inclusive.</span></span>

## <a name="message-exchange-patterns"></a><span data-ttu-id="d07c8-250">メッセージ交換パターン</span><span class="sxs-lookup"><span data-stu-id="d07c8-250">Message Exchange Patterns</span></span>

<span data-ttu-id="d07c8-251">このセクションでは、WS-ReliableMessaging をさまざまなメッセージ交換パターンを使用する場合、WCF の動作が説明します。</span><span class="sxs-lookup"><span data-stu-id="d07c8-251">This section describes WCF's behavior when WS-ReliableMessaging is used for different Message Exchange Patterns.</span></span> <span data-ttu-id="d07c8-252">各メッセージ交換パターンについて、次の 2 つの展開シナリオを考えます。</span><span class="sxs-lookup"><span data-stu-id="d07c8-252">For each Message Exchange Pattern the following two deployments scenarios are considered:</span></span>

- <span data-ttu-id="d07c8-253">アドレス不可能なイニシエーター:イニシエーターが; ファイアウォールの背後にはレスポンダーは、HTTP 応答でのみイニシエーターにメッセージを配信できます。</span><span class="sxs-lookup"><span data-stu-id="d07c8-253">Non-Addressable Initiator: Initiator is behind a firewall; Responder can deliver messages to the Initiator only on HTTP responses.</span></span>

- <span data-ttu-id="d07c8-254">アドレス指定可能なイニシエーター:イニシエーターおよびレスポンダーは HTTP 要求を送信します。つまり、2 つの逆方向の HTTP 接続を確立できます。</span><span class="sxs-lookup"><span data-stu-id="d07c8-254">Addressable Initiator: Initiator and Responder both can be sent HTTP requests; in other words, two converse HTTP connections can be established.</span></span>

### <a name="one-way-non-addressable-initiator"></a><span data-ttu-id="d07c8-255">一方向 : アドレス不可能なイニシエーター</span><span class="sxs-lookup"><span data-stu-id="d07c8-255">One-way, Non-addressable Initiator</span></span>

#### <a name="binding"></a><span data-ttu-id="d07c8-256">バインディング</span><span class="sxs-lookup"><span data-stu-id="d07c8-256">Binding</span></span>

<span data-ttu-id="d07c8-257">WCF には、1 つの HTTP チャネル経由で 1 つのシーケンスを使用して、一方向メッセージ交換パターンが用意されています。</span><span class="sxs-lookup"><span data-stu-id="d07c8-257">WCF provides a one-way message exchange pattern using one sequence over one HTTP channel.</span></span> <span data-ttu-id="d07c8-258">WCF では、HTTP 要求を使用してレスポンダーからイニシエーターにすべてのメッセージを送信する応答側および HTTP 応答に、発信側からのすべてメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="d07c8-258">WCF uses HTTP requests to transmit all messages from the Initiator to the Responder and HTTP responses to transmit all messages from the Responder to the Initiator.</span></span>

#### <a name="createsequence-exchange"></a><span data-ttu-id="d07c8-259">CreateSequence の交換</span><span class="sxs-lookup"><span data-stu-id="d07c8-259">CreateSequence Exchange</span></span>

<span data-ttu-id="d07c8-260">WCF 発信側が送信を`CreateSequence`なしでメッセージ`Offer`要素は、HTTP 要求で想定されている、 `CreateSequenceResponse` HTTP 応答でメッセージ。</span><span class="sxs-lookup"><span data-stu-id="d07c8-260">The WCF Initiator transmits a `CreateSequence` message with no `Offer` element on an HTTP request and expects the `CreateSequenceResponse` message on the HTTP response.</span></span> <span data-ttu-id="d07c8-261">WCF 応答側はシーケンスを作成し、送信、`CreateSequenceResponse`のないメッセージ`Accept`HTTP 応答での要素。</span><span class="sxs-lookup"><span data-stu-id="d07c8-261">The WCF Responder creates a sequence and transmits the `CreateSequenceResponse` message with no `Accept` element on the HTTP response.</span></span>

#### <a name="sequenceacknowledgement"></a><span data-ttu-id="d07c8-262">SequenceAcknowledgement</span><span class="sxs-lookup"><span data-stu-id="d07c8-262">SequenceAcknowledgement</span></span>

<span data-ttu-id="d07c8-263">WCF のイニシエーターを除くすべてのメッセージの返信の受信確認の処理、`CreateSequence`メッセージとエラー メッセージ。</span><span class="sxs-lookup"><span data-stu-id="d07c8-263">The WCF Initiator processes acknowledgements on the reply of all messages except the `CreateSequence` message and fault messages.</span></span> <span data-ttu-id="d07c8-264">WCF 応答側が常にすべてのシーケンスに、HTTP 応答でスタンドアロンの受信確認を送信し、`AckRequested`メッセージ。</span><span class="sxs-lookup"><span data-stu-id="d07c8-264">The WCF Responder always transmits a stand-alone acknowledgement on the HTTP response to all sequence and `AckRequested` messages.</span></span>

#### <a name="closesequence-exchange"></a><span data-ttu-id="d07c8-265">CloseSequence の交換</span><span class="sxs-lookup"><span data-stu-id="d07c8-265">CloseSequence Exchange</span></span>

<span data-ttu-id="d07c8-266">WCF の発信側の送信、 `CloseSequence` 、HTTP 要求でメッセージ、 `CreateSequenceResponse` HTTP 応答でメッセージ。</span><span class="sxs-lookup"><span data-stu-id="d07c8-266">The WCF Initiator transmits a `CloseSequence` message on an HTTP request and expects the `CreateSequenceResponse` message on the HTTP response.</span></span> <span data-ttu-id="d07c8-267">WCF 応答側の送信、`CloseSequenceResponse`で HTTP 応答メッセージ。</span><span class="sxs-lookup"><span data-stu-id="d07c8-267">The WCF Responder transmits the `CloseSequenceResponse` message on the HTTP response.</span></span>

#### <a name="terminatesequence-exchange"></a><span data-ttu-id="d07c8-268">TerminateSequence の交換</span><span class="sxs-lookup"><span data-stu-id="d07c8-268">TerminateSequence Exchange</span></span>

<span data-ttu-id="d07c8-269">WCF の発信側の送信、 `TerminateSequence` 、HTTP 要求でメッセージ、 `TerminateSequenceResponse` HTTP 応答でメッセージ。</span><span class="sxs-lookup"><span data-stu-id="d07c8-269">The WCF Initiator transmits a `TerminateSequence` message on an HTTP request and expects the `TerminateSequenceResponse` message on the HTTP response.</span></span> <span data-ttu-id="d07c8-270">WCF 応答側の送信、`TerminateSequenceResponse`で HTTP 応答メッセージ。</span><span class="sxs-lookup"><span data-stu-id="d07c8-270">The WCF Responder transmits the `TerminateSequenceResponse` message on the HTTP response.</span></span>

### <a name="one-way-addressable-initiator"></a><span data-ttu-id="d07c8-271">一方向 : アドレス可能なイニシエーター</span><span class="sxs-lookup"><span data-stu-id="d07c8-271">One Way, Addressable Initiator</span></span>

#### <a name="binding"></a><span data-ttu-id="d07c8-272">バインディング</span><span class="sxs-lookup"><span data-stu-id="d07c8-272">Binding</span></span>

<span data-ttu-id="d07c8-273">WCF は、1 つに 1 つのシーケンスを使用して一方向メッセージ交換パターンを提供します。 受信と送信の 1 つの HTTP チャネル。</span><span class="sxs-lookup"><span data-stu-id="d07c8-273">WCF provides a one-way message exchange pattern using one sequence over one inbound and one outbound HTTP channel.</span></span> <span data-ttu-id="d07c8-274">WCF では、HTTP 要求を使用して、すべてのメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="d07c8-274">WCF uses the HTTP requests to transmit all messages.</span></span> <span data-ttu-id="d07c8-275">すべての HTTP 応答に、空の本文と HTTP 202 ステータス コードが含まれます。</span><span class="sxs-lookup"><span data-stu-id="d07c8-275">All HTTP responses have an empty body and HTTP 202 status code.</span></span>

#### <a name="createsequence-exchange"></a><span data-ttu-id="d07c8-276">CreateSequence の交換</span><span class="sxs-lookup"><span data-stu-id="d07c8-276">CreateSequence Exchange</span></span>

<span data-ttu-id="d07c8-277">WCF の発信側が送信を`CreateSequence`メッセージなしで`Offer`HTTP 要求での要素。</span><span class="sxs-lookup"><span data-stu-id="d07c8-277">The WCF Initiator transmits a `CreateSequence` message with no `Offer` element on an HTTP request.</span></span> <span data-ttu-id="d07c8-278">WCF 応答側はシーケンスを作成し、送信、`CreateSequenceResponse`メッセージなしで`Accept`HTTP 要求での要素。</span><span class="sxs-lookup"><span data-stu-id="d07c8-278">The WCF Responder creates a sequence and transmits the `CreateSequenceResponse` message with no `Accept` element on an HTTP request.</span></span>

### <a name="duplex-addressable-initiator"></a><span data-ttu-id="d07c8-279">双方向 : アドレス可能なイニシエーター</span><span class="sxs-lookup"><span data-stu-id="d07c8-279">Duplex, Addressable Initiator</span></span>

#### <a name="binding"></a><span data-ttu-id="d07c8-280">バインディング</span><span class="sxs-lookup"><span data-stu-id="d07c8-280">Binding</span></span>

<span data-ttu-id="d07c8-281">WCF では、2 つを使用して、完全に非同期の双方向メッセージ交換パターンをシーケンス 1 つ以上用意されています受信と送信の 1 つの HTTP チャネル。</span><span class="sxs-lookup"><span data-stu-id="d07c8-281">WCF provides a fully-asynchronous, two-way message exchange pattern using two sequences over one inbound and one outbound HTTP channel.</span></span> <span data-ttu-id="d07c8-282">このメッセージ交換パターンは、限定された方法で `Request/Reply`、`Addressable` イニシエーター メッセージ交換パターンに組み込むことができます。</span><span class="sxs-lookup"><span data-stu-id="d07c8-282">This message exchange pattern can be mixed with the `Request/Reply`, `Addressable` Initiator message exchange pattern in a limited way.</span></span> <span data-ttu-id="d07c8-283">WCF では、HTTP 要求を使用して、すべてのメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="d07c8-283">WCF uses HTTP requests to transmit all messages.</span></span> <span data-ttu-id="d07c8-284">すべての HTTP 応答に、空の本文と HTTP 202 ステータス コードが含まれます。</span><span class="sxs-lookup"><span data-stu-id="d07c8-284">All HTTP responses have an empty body and HTTP 202 status code.</span></span>

#### <a name="createsequence-exchange"></a><span data-ttu-id="d07c8-285">CreateSequence の交換</span><span class="sxs-lookup"><span data-stu-id="d07c8-285">CreateSequence Exchange</span></span>

<span data-ttu-id="d07c8-286">WCF の発信側が送信を`CreateSequence`メッセージである、 `Offer` HTTP 要求での要素。</span><span class="sxs-lookup"><span data-stu-id="d07c8-286">The WCF Initiator transmits a `CreateSequence` message with an `Offer` element on an HTTP request.</span></span> <span data-ttu-id="d07c8-287">WCF 応答側により、`CreateSequence`が、`Offer`要素: シーケンスを作成し、送信、`CreateSequenceResponse`メッセージである、`Accept`要素。</span><span class="sxs-lookup"><span data-stu-id="d07c8-287">The WCF Responder ensures that the `CreateSequence` has an `Offer` element, then creates a sequence and transmits the `CreateSequenceResponse` message with an `Accept` element.</span></span>

#### <a name="sequence-lifetime"></a><span data-ttu-id="d07c8-288">シーケンスの有効期間</span><span class="sxs-lookup"><span data-stu-id="d07c8-288">Sequence Lifetime</span></span>

<span data-ttu-id="d07c8-289">2 つのシーケンスは、WCF は、1 つの完全な双方向セッションとして扱います。</span><span class="sxs-lookup"><span data-stu-id="d07c8-289">WCF treats the two sequences as one fully-duplex session.</span></span>

<span data-ttu-id="d07c8-290">1 つのシーケンスをフォールトするエラーを生成すると WCF には、両方のシーケンスをフォールトするリモート エンドポイントが必要です。</span><span class="sxs-lookup"><span data-stu-id="d07c8-290">Upon generating a fault that faults one sequence, WCF expects the remote endpoint to fault both sequences.</span></span> <span data-ttu-id="d07c8-291">WCF の障害を 1 つのシーケンスをフォールトするエラーを読んだときに両方のシーケンスします。</span><span class="sxs-lookup"><span data-stu-id="d07c8-291">Upon reading a fault that faults one sequence, WCF faults both sequences.</span></span>

<span data-ttu-id="d07c8-292">WCF は、送信シーケンスを閉じるし、受信シーケンスでのメッセージの処理を続行することができます。</span><span class="sxs-lookup"><span data-stu-id="d07c8-292">WCF can close its outbound sequence and continue to process messages on its inbound sequence.</span></span> <span data-ttu-id="d07c8-293">逆に、WCF は、受信シーケンスの終了を処理して、送信シーケンスでメッセージを送信し続けます。</span><span class="sxs-lookup"><span data-stu-id="d07c8-293">Conversely, WCF can process the close of the inbound sequence and continue to send messages on its outbound sequence.</span></span>

### <a name="request-reply-and-one-way-non-addressable-initiator"></a><span data-ttu-id="d07c8-294">要求/応答および一方向のアドレス不可能なイニシエーター</span><span class="sxs-lookup"><span data-stu-id="d07c8-294">Request-Reply and One-Way, Non-Addressable Initiator</span></span>

#### <a name="binding"></a><span data-ttu-id="d07c8-295">バインディング</span><span class="sxs-lookup"><span data-stu-id="d07c8-295">Binding</span></span>

<span data-ttu-id="d07c8-296">WCF は、一方向と、要求/応答メッセージ交換のパターンを使用して 2 つのシーケンスの 1 つの HTTP チャネル。</span><span class="sxs-lookup"><span data-stu-id="d07c8-296">WCF provides a one-way and request-reply message exchange pattern using two sequences over one HTTP channel.</span></span> <span data-ttu-id="d07c8-297">WCF では、HTTP 要求を使用してレスポンダーからイニシエーターにすべてのメッセージを送信する応答側および HTTP 応答に、発信側からのすべてメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="d07c8-297">WCF uses HTTP requests to transmit all messages from the Initiator to the Responder and HTTP responses to transmit all messages from the Responder to the Initiator.</span></span>

#### <a name="createsequence-exchange"></a><span data-ttu-id="d07c8-298">CreateSequence の交換</span><span class="sxs-lookup"><span data-stu-id="d07c8-298">CreateSequence Exchange</span></span>

<span data-ttu-id="d07c8-299">WCF の発信側が送信、`CreateSequence`メッセージである、 `Offer` 、HTTP 要求で要素が必要ですが、 `CreateSequenceResponse` HTTP 応答でメッセージ。</span><span class="sxs-lookup"><span data-stu-id="d07c8-299">The WCF Initiator transmits a `CreateSequence` message with an `Offer` element on an HTTP request and expects the `CreateSequenceResponse` message on the HTTP response.</span></span> <span data-ttu-id="d07c8-300">WCF 応答側はシーケンスを作成し、送信、`CreateSequenceResponse`メッセージである、 `Accept` HTTP 応答での要素。</span><span class="sxs-lookup"><span data-stu-id="d07c8-300">The WCF Responder creates a sequence and transmits the `CreateSequenceResponse` message with an `Accept` element on the HTTP response.</span></span>

#### <a name="one-way-message"></a><span data-ttu-id="d07c8-301">一方向のメッセージ</span><span class="sxs-lookup"><span data-stu-id="d07c8-301">One-way Message</span></span>

<span data-ttu-id="d07c8-302">一方向メッセージ交換を正常に完了するには、WCF のイニシエーターは HTTP 要求で要求シーケンス メッセージ送信し、スタンドアロンの受信`SequenceAcknowledgement`で HTTP 応答メッセージ。</span><span class="sxs-lookup"><span data-stu-id="d07c8-302">To complete a one-way message exchange successfully, the WCF Initiator transmits a request sequence message on the HTTP request and receives a standalone `SequenceAcknowledgement` message on the HTTP response.</span></span> <span data-ttu-id="d07c8-303">`SequenceAcknowledgement` は、送信されたメッセージの受信確認を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="d07c8-303">The `SequenceAcknowledgement` must acknowledge the message transmitted.</span></span>

<span data-ttu-id="d07c8-304">WCF 応答側は、受信確認、エラー、または空の本文と HTTP 202 ステータス コードを含む応答で要求に返信があります。</span><span class="sxs-lookup"><span data-stu-id="d07c8-304">The WCF Responder may reply to the request with an acknowledgement, a fault, or a response with an empty body and HTTP 202 status code.</span></span>

#### <a name="two-way-messages"></a><span data-ttu-id="d07c8-305">双方向のメッセージ</span><span class="sxs-lookup"><span data-stu-id="d07c8-305">Two Way Messages</span></span>

<span data-ttu-id="d07c8-306">双方向のメッセージ交換プロトコルを正常に完了するは、WCF イニシエーターは、HTTP 要求で要求シーケンス メッセージを送信し、HTTP 応答で応答シーケンス メッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="d07c8-306">To complete a two way message exchange protocol successfully, the WCF Initiator transmits a request sequence message on the HTTP request and receives a reply sequence message on the HTTP response.</span></span> <span data-ttu-id="d07c8-307">応答では、送信された要求シーケンス メッセージの受信確認を行う `SequenceAcknowledgement` を送信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d07c8-307">The response must carry a `SequenceAcknowledgement` acknowledging the request sequence message transmitted.</span></span>

<span data-ttu-id="d07c8-308">WCF 応答側は、アプリケーション応答、エラー、または空の本文と HTTP 202 ステータス コードを含む応答で要求に返信があります。</span><span class="sxs-lookup"><span data-stu-id="d07c8-308">The WCF Responder may reply to the request with an application reply, a fault or a response with an empty body and HTTP 202 status code.</span></span>

<span data-ttu-id="d07c8-309">一方向のメッセージが存在することと、アプリケーション応答のタイミングもあるため、要求シーケンス メッセージのシーケンス番号と応答メッセージのシーケンス番号には相関関係はありません。</span><span class="sxs-lookup"><span data-stu-id="d07c8-309">Because of the presence of one-way messages and the timing of application replies, the request sequence message’s sequence number and the response message’s sequence number have no correlation.</span></span>

#### <a name="retrying-replies"></a><span data-ttu-id="d07c8-310">応答の再試行</span><span class="sxs-lookup"><span data-stu-id="d07c8-310">Retrying Replies</span></span>

<span data-ttu-id="d07c8-311">WCF は、双方向メッセージ交換プロトコルの相関関係の HTTP 要求-応答の相関関係に依存します。</span><span class="sxs-lookup"><span data-stu-id="d07c8-311">WCF relies on HTTP request-reply correlation for two-way message exchange protocol correlation.</span></span> <span data-ttu-id="d07c8-312">このため、WCF のイニシエーターは、停止されませんが、要求シーケンス メッセージが受信確認されるときに、要求シーケンス メッセージの再試行ではなく HTTP 応答を実行すると、 `SequenceAcknowledgement`、アプリケーション応答、またはエラー。</span><span class="sxs-lookup"><span data-stu-id="d07c8-312">Because of this, the WCF Initiator does not stop retrying a request sequence message when the request sequence message is acknowledged but rather when the HTTP response carries a `SequenceAcknowledgement`, application reply, or fault.</span></span> <span data-ttu-id="d07c8-313">WCF 応答側は、応答が関連付けられている要求の HTTP 応答で応答を再試行します。</span><span class="sxs-lookup"><span data-stu-id="d07c8-313">The WCF Responder retries replies on the HTTP response of the request to which the reply is correlated.</span></span>

#### <a name="closesequence-exchange"></a><span data-ttu-id="d07c8-314">CloseSequence の交換</span><span class="sxs-lookup"><span data-stu-id="d07c8-314">CloseSequence Exchange</span></span>

<span data-ttu-id="d07c8-315">WCF のイニシエーターを送信するすべての応答シーケンス メッセージおよび一方向の要求シーケンスのすべてのメッセージに対する受信確認を受信した後、 `CloseSequence` 、HTTP 要求で要求シーケンス メッセージ、 `CloseSequenceResponse` HTTP 応答でします。</span><span class="sxs-lookup"><span data-stu-id="d07c8-315">After receiving all reply sequence messages and acknowledgements for all one way request sequence messages, the WCF Initiator transmits a `CloseSequence` message for the request sequence on an HTTP request and expects the `CloseSequenceResponse` on the HTTP response.</span></span>

<span data-ttu-id="d07c8-316">要求シーケンスを終了すると、暗黙的に応答シーケンスが終了します。</span><span class="sxs-lookup"><span data-stu-id="d07c8-316">Closing the request sequence implicitly closes the reply sequence.</span></span> <span data-ttu-id="d07c8-317">WCF イニシエーターには、応答シーケンスの最後が含まれています。 つまり`SequenceAcknowledgement`上、`CloseSequence`メッセージと応答シーケンスがない、 `CloseSequence` exchange。</span><span class="sxs-lookup"><span data-stu-id="d07c8-317">This means the WCF Initiator includes the reply sequence’s Final `SequenceAcknowledgement` on the `CloseSequence` message and the reply sequence does not have a `CloseSequence` exchange.</span></span>

<span data-ttu-id="d07c8-318">WCF 応答側により、すべての返信は、受信確認し、送信、`CloseSequenceResponse`で HTTP 応答メッセージ。</span><span class="sxs-lookup"><span data-stu-id="d07c8-318">The WCF Responder ensures all replies are acknowledged and transmits the `CloseSequenceResponse` message on the HTTP response.</span></span>

#### <a name="terminatesequence-exchange"></a><span data-ttu-id="d07c8-319">TerminateSequence の交換</span><span class="sxs-lookup"><span data-stu-id="d07c8-319">TerminateSequence Exchange</span></span>

<span data-ttu-id="d07c8-320">受信した後、`CloseSequenceResponse`メッセージ、WCF の発信側の送信、 `TerminateSequence` 、HTTP 要求で要求シーケンス メッセージ、 `TerminateSequenceResponse` HTTP 応答でします。</span><span class="sxs-lookup"><span data-stu-id="d07c8-320">After receiving the `CloseSequenceResponse` message, the WCF Initiator transmits a `TerminateSequence` message for the request sequence on an HTTP request and expects the `TerminateSequenceResponse` on the HTTP response.</span></span>

<span data-ttu-id="d07c8-321">`CloseSequence` 交換と同じように、要求シーケンスを終了すると、暗黙的に応答シーケンスが終了します。</span><span class="sxs-lookup"><span data-stu-id="d07c8-321">Like the `CloseSequence` exchange, terminating the request sequence implicitly terminates the reply sequence.</span></span> <span data-ttu-id="d07c8-322">WCF イニシエーターには、応答シーケンスの最後が含まれています。 つまり`SequenceAcknowledgement`上、`TerminateSequence`メッセージと応答シーケンスがない、 `TerminateSequence` exchange。</span><span class="sxs-lookup"><span data-stu-id="d07c8-322">This means the WCF Initiator includes the reply sequence’s final `SequenceAcknowledgement` on the `TerminateSequence` message and the reply sequence does not have a `TerminateSequence` exchange.</span></span>

<span data-ttu-id="d07c8-323">WCF 応答側の送信、`TerminateSequenceResponse`で HTTP 応答メッセージ。</span><span class="sxs-lookup"><span data-stu-id="d07c8-323">The WCF Responder transmits the `TerminateSequenceResponse` message on the HTTP response.</span></span>

### <a name="requestreply-addressable-initiator"></a><span data-ttu-id="d07c8-324">要求/応答 : アドレス可能なイニシエーター</span><span class="sxs-lookup"><span data-stu-id="d07c8-324">Request/Reply, Addressable Initiator</span></span>

#### <a name="binding"></a><span data-ttu-id="d07c8-325">バインディング</span><span class="sxs-lookup"><span data-stu-id="d07c8-325">Binding</span></span>

<span data-ttu-id="d07c8-326">WCF は、要求/応答メッセージ交換パターンを使用して 2 つのシーケンスの 1 つ以上受信と送信の 1 つの HTTP チャネル。</span><span class="sxs-lookup"><span data-stu-id="d07c8-326">WCF provides a request-reply message exchange pattern using two sequences over one inbound and one outbound HTTP channel.</span></span> <span data-ttu-id="d07c8-327">このメッセージ交換パターンは、限定された方法で `Duplex, Addressable` イニシエーター メッセージ交換パターンに組み込むことができます。</span><span class="sxs-lookup"><span data-stu-id="d07c8-327">This message exchange pattern can be mixed with the `Duplex, Addressable` Initiator message exchange pattern in a limited way.</span></span> <span data-ttu-id="d07c8-328">WCF では、HTTP 要求を使用して、すべてのメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="d07c8-328">WCF uses the HTTP requests to transmit all messages.</span></span> <span data-ttu-id="d07c8-329">すべての HTTP 応答に、空の本文と HTTP 202 ステータス コードが含まれます。</span><span class="sxs-lookup"><span data-stu-id="d07c8-329">All HTTP responses have an empty body and HTTP 202 status code.</span></span>

#### <a name="createsequence-exchange"></a><span data-ttu-id="d07c8-330">CreateSequence の交換</span><span class="sxs-lookup"><span data-stu-id="d07c8-330">CreateSequence Exchange</span></span>

<span data-ttu-id="d07c8-331">WCF の発信側が送信を`CreateSequence`メッセージである、 `Offer` HTTP 要求での要素。</span><span class="sxs-lookup"><span data-stu-id="d07c8-331">The WCF Initiator transmits a `CreateSequence` message with an `Offer` element on an HTTP request.</span></span> <span data-ttu-id="d07c8-332">WCF 応答側により、`CreateSequence`が、`Offer`要素: シーケンスを作成し、送信、`CreateSequenceResponse`メッセージである、`Accept`要素。</span><span class="sxs-lookup"><span data-stu-id="d07c8-332">The WCF Responder ensures that the `CreateSequence` has an `Offer` element then creates a sequence and transmits the `CreateSequenceResponse` message with an `Accept` element.</span></span>

#### <a name="requestreply-correlation"></a><span data-ttu-id="d07c8-333">要求/応答の相関関係</span><span class="sxs-lookup"><span data-stu-id="d07c8-333">Request/Reply Correlation</span></span>

<span data-ttu-id="d07c8-334">次の状況は、すべての相関関係にある要求/応答で発生します。</span><span class="sxs-lookup"><span data-stu-id="d07c8-334">The following applies to all correlated requests and replies:</span></span>

- <span data-ttu-id="d07c8-335">WCF により、すべてのアプリケーション要求メッセージの熊、`ReplyTo`エンドポイント参照と`MessageId`します。</span><span class="sxs-lookup"><span data-stu-id="d07c8-335">WCF ensures all application request messages bear a `ReplyTo` endpoint reference and a `MessageId`.</span></span>

- <span data-ttu-id="d07c8-336">WCF では、各アプリケーション要求メッセージのとしてローカル エンドポイント参照を適用`ReplyTo`します。</span><span class="sxs-lookup"><span data-stu-id="d07c8-336">WCF applies the local endpoint reference as each application request message’s `ReplyTo`.</span></span> <span data-ttu-id="d07c8-337">ローカル エンドポイント参照は、イニシエーターの `CreateSequence` メッセージの `ReplyTo` であり、レスポンダーの `CreateSequence` メッセージの `To` です。</span><span class="sxs-lookup"><span data-stu-id="d07c8-337">The local endpoint reference is the `CreateSequence` message’s `ReplyTo` for the Initiator and the `CreateSequence` message’s `To` for the Responder.</span></span>

- <span data-ttu-id="d07c8-338">WCF により、その着信要求メッセージの熊、`MessageId`と`ReplyTo`します。</span><span class="sxs-lookup"><span data-stu-id="d07c8-338">WCF ensures that incoming request messages bear a `MessageId` and a `ReplyTo`.</span></span>

- <span data-ttu-id="d07c8-339">WCF により、`ReplyTo`に定義されているすべてのアプリケーション要求メッセージのエンドポイント参照の URI がローカル エンドポイント参照に一致します。</span><span class="sxs-lookup"><span data-stu-id="d07c8-339">WCF ensures the `ReplyTo` endpoint reference’s URI of all application request messages match the local endpoint reference as defined earlier.</span></span>

- <span data-ttu-id="d07c8-340">WCF では、すべての応答が正しい負うことにより、`RelatesTo`と`To`に従ってヘッダー`wsa`要求/応答の相関ルール。</span><span class="sxs-lookup"><span data-stu-id="d07c8-340">WCF ensures that all replies bear the correct `RelatesTo` and `To` headers following `wsa` request/reply correlation rules.</span></span>
