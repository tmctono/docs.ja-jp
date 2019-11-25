---
title: 信頼できるメッセージング プロトコル バージョン 1.1
ms.date: 03/30/2017
ms.assetid: 0da47b82-f8eb-42da-8bfe-e56ce7ba6f59
ms.openlocfilehash: 9320787317131f42c4a82c6114a16fdea87567f4
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283313"
---
# <a name="reliable-messaging-protocol-version-11"></a><span data-ttu-id="c85b5-102">信頼できるメッセージング プロトコル バージョン 1.1</span><span class="sxs-lookup"><span data-stu-id="c85b5-102">Reliable Messaging Protocol version 1.1</span></span>

<span data-ttu-id="c85b5-103">このトピックでは、HTTP トランスポートを使用した相互運用に必要な Ws-reliablemessaging 2007 (バージョン 1.1) プロトコルの Windows Communication Foundation (WCF) 実装の詳細について説明します。</span><span class="sxs-lookup"><span data-stu-id="c85b5-103">This topic covers Windows Communication Foundation (WCF) implementation details for the WS-ReliableMessaging February 2007 (version 1.1) protocol necessary for interoperation using the HTTP transport.</span></span> <span data-ttu-id="c85b5-104">WCF は、このトピックで説明する制約と説明を使用して、ws-reliablemessaging 仕様に従います。</span><span class="sxs-lookup"><span data-stu-id="c85b5-104">WCF follows the WS-ReliableMessaging specification with the constraints and clarifications explained in this topic.</span></span> <span data-ttu-id="c85b5-105">Ws-reliablemessaging バージョン1.1 プロトコルは .NET Framework 3.5 以降で実装されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="c85b5-105">Note that the WS-ReliableMessaging version 1.1 protocol is implemented starting with .NET Framework 3.5.</span></span>

<span data-ttu-id="c85b5-106">Ws-reliablemessaging 2 月2007プロトコルは、<xref:System.ServiceModel.Channels.ReliableSessionBindingElement>によって WCF に実装されます。</span><span class="sxs-lookup"><span data-stu-id="c85b5-106">The WS-ReliableMessaging February 2007 protocol is implemented in WCF by the <xref:System.ServiceModel.Channels.ReliableSessionBindingElement>.</span></span>

<span data-ttu-id="c85b5-107">便宜上、ここでは次のロールを使用します。</span><span class="sxs-lookup"><span data-stu-id="c85b5-107">For convenience, the topic uses the following roles:</span></span>

- <span data-ttu-id="c85b5-108">イニシエーター : WS-Reliable メッセージ シーケンスの作成を開始するクライアント。</span><span class="sxs-lookup"><span data-stu-id="c85b5-108">Initiator: The client that initiates WS-Reliable Message sequence creation.</span></span>

- <span data-ttu-id="c85b5-109">レスポンダー : イニシエーターの要求を受け取るサービス。</span><span class="sxs-lookup"><span data-stu-id="c85b5-109">Responder: The service that receives the initiator's requests.</span></span>

 <span data-ttu-id="c85b5-110">このドキュメントでは、次の表に示すプレフィックスと名前空間を使用します。</span><span class="sxs-lookup"><span data-stu-id="c85b5-110">This document uses the prefixes and namespaces in the following table.</span></span>

|<span data-ttu-id="c85b5-111">プレフィックス</span><span class="sxs-lookup"><span data-stu-id="c85b5-111">Prefix</span></span>|<span data-ttu-id="c85b5-112">Namespace</span><span class="sxs-lookup"><span data-stu-id="c85b5-112">Namespace</span></span>|
|-|-|
|<span data-ttu-id="c85b5-113">wsrm</span><span class="sxs-lookup"><span data-stu-id="c85b5-113">wsrm</span></span>|http://docs.oasis-open.org/ws-rx/wsrm/200702|
|<span data-ttu-id="c85b5-114">netrm</span><span class="sxs-lookup"><span data-stu-id="c85b5-114">netrm</span></span>|http://schemas.microsoft.com/ws/2006/05/rm|
|<span data-ttu-id="c85b5-115">s</span><span class="sxs-lookup"><span data-stu-id="c85b5-115">s</span></span>|http://www.w3.org/2003/05/soap-envelope|
|<span data-ttu-id="c85b5-116">wsa</span><span class="sxs-lookup"><span data-stu-id="c85b5-116">wsa</span></span>|http://schemas.xmlsoap.org/ws/2005/08/addressing|
|<span data-ttu-id="c85b5-117">wsse</span><span class="sxs-lookup"><span data-stu-id="c85b5-117">wsse</span></span>|http://docs.oasis-open.org/wss/2004/01/oasis-200401-wssecurity-secext-1.0.xsd|
|<span data-ttu-id="c85b5-118">wsrmp</span><span class="sxs-lookup"><span data-stu-id="c85b5-118">wsrmp</span></span>|http://docs.oasis-open.org/ws-rx/wsrmp/200702|
|<span data-ttu-id="c85b5-119">netrmp</span><span class="sxs-lookup"><span data-stu-id="c85b5-119">netrmp</span></span>|http://schemas.microsoft.com/ws-rx/wsrmp/200702|
|<span data-ttu-id="c85b5-120">wsp</span><span class="sxs-lookup"><span data-stu-id="c85b5-120">wsp</span></span>|<span data-ttu-id="c85b5-121">(WS-Policy 1.2 または WS-Policy 1.5 のいずれか)</span><span class="sxs-lookup"><span data-stu-id="c85b5-121">(Either WS-Policy 1.2 or WS-Policy 1.5)</span></span>|

## <a name="messaging"></a><span data-ttu-id="c85b5-122">メッセージング</span><span class="sxs-lookup"><span data-stu-id="c85b5-122">Messaging</span></span>

### <a name="sequence-creation"></a><span data-ttu-id="c85b5-123">シーケンスの作成</span><span class="sxs-lookup"><span data-stu-id="c85b5-123">Sequence Creation</span></span>

<span data-ttu-id="c85b5-124">WCF では、`CreateSequence` メッセージと `CreateSequenceResponse` メッセージを実装して、信頼できるメッセージシーケンスを確立します。</span><span class="sxs-lookup"><span data-stu-id="c85b5-124">WCF implements `CreateSequence` and `CreateSequenceResponse` messages to establish a reliable messaging sequence.</span></span> <span data-ttu-id="c85b5-125">以下の制約が適用されます。</span><span class="sxs-lookup"><span data-stu-id="c85b5-125">The following constraints apply:</span></span>

- <span data-ttu-id="c85b5-126">B1101: WCF イニシエーターは、`CreateSequence` メッセージの `ReplyTo`、`AcksTo`、および `Offer/Endpoint`と同じエンドポイント参照を使用します。</span><span class="sxs-lookup"><span data-stu-id="c85b5-126">B1101: The WCF Initiator uses the same endpoint reference as the `CreateSequence` message’s `ReplyTo`, `AcksTo` and `Offer/Endpoint`.</span></span>

- <span data-ttu-id="c85b5-127">R1102: `AcksTo` メッセージの `ReplyTo`、`Offer/Endpoint`、および `CreateSequence` の各エンドポイント参照には、オクテット単位で一致する同じ文字列表現のアドレス値が必要です。</span><span class="sxs-lookup"><span data-stu-id="c85b5-127">R1102: The `AcksTo`, `ReplyTo` and `Offer/Endpoint` endpoint references in the `CreateSequence` message must have address values with identical string representations such that they match the octet-wise.</span></span>

  - <span data-ttu-id="c85b5-128">WCF レスポンダーは、シーケンスを作成する前に、`AcksTo`、`ReplyTo`、および `Endpoint` エンドポイント参照の URI 部分が同一であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="c85b5-128">The WCF Responder verifies that the URI portion of the `AcksTo`, `ReplyTo` and `Endpoint` endpoint references are identical before creating a sequence.</span></span>

- <span data-ttu-id="c85b5-129">R1103: `AcksTo` メッセージの `ReplyTo`、`Offer/Endpoint`、および `CreateSequence` の各エンドポイント参照には、同一の参照パラメーターのセットが必要です。</span><span class="sxs-lookup"><span data-stu-id="c85b5-129">R1103: The `AcksTo`, `ReplyTo` and `Offer/Endpoint` endpoint references in the `CreateSequence` message should have the same set of reference parameters.</span></span>

  - <span data-ttu-id="c85b5-130">WCF では強制されませんが、`CreateSequence` の `AcksTo`、`ReplyTo`、および `Offer/Endpoint` のエンドポイント参照の参照パラメーターが同一であることを前提としており、`ReplyTo` エンドポイント参照の参照パラメーターを使用して受信確認と逆方向シーケンスメッセージを使用していることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="c85b5-130">WCF does not enforce, but assumes that reference parameters of the `AcksTo`, `ReplyTo` and `Offer/Endpoint` endpoint references on `CreateSequence` are identical and uses reference parameters from the `ReplyTo` endpoint reference for acknowledgements and converse sequence messages.</span></span>

- <span data-ttu-id="c85b5-131">B1104: WCF イニシエーターは、`CreateSequence` メッセージにオプションの `Expires` または `Offer/Expires` 要素を生成しません。</span><span class="sxs-lookup"><span data-stu-id="c85b5-131">B1104: The WCF Initiator does not generate the optional `Expires` or `Offer/Expires` element in the `CreateSequence` message.</span></span>

- <span data-ttu-id="c85b5-132">B1105: `CreateSequence` メッセージにアクセスする場合、WCF レスポンダーは `CreateSequence` 要素の `Expires` 値を `CreateSequenceResponse` 要素の `Expires` 値として使用します。</span><span class="sxs-lookup"><span data-stu-id="c85b5-132">B1105: When accessing the `CreateSequence` message, the WCF Responder uses the `Expires` value in the `CreateSequence` element as the `Expires` value in the `CreateSequenceResponse` element.</span></span> <span data-ttu-id="c85b5-133">それ以外の場合、WCF レスポンダーは `Expires` と `Offer/Expires` の値を読み取り、無視します。</span><span class="sxs-lookup"><span data-stu-id="c85b5-133">Otherwise, the WCF Responder reads and ignores the `Expires` and `Offer/Expires` values.</span></span>

- <span data-ttu-id="c85b5-134">B1106: `CreateSequenceResponse` メッセージにアクセスする場合、WCF イニシエーターは省略可能な `Expires` 値を読み取りますが、この値は使用しません。</span><span class="sxs-lookup"><span data-stu-id="c85b5-134">B1106: When accessing the `CreateSequenceResponse` message, the WCF Initiator reads the optional `Expires` value but does not use it.</span></span>

- <span data-ttu-id="c85b5-135">B1107: WCF の開始側と応答側は、常に `CreateSequence/Offer` 要素と `CreateSequenceResponse` 要素内のオプションの `IncompleteSequenceBehavior` 要素を生成します。</span><span class="sxs-lookup"><span data-stu-id="c85b5-135">B1107: The WCF Initiator and Responder always generate the optional `IncompleteSequenceBehavior` element in the `CreateSequence/Offer` and `CreateSequenceResponse` elements.</span></span>

- <span data-ttu-id="c85b5-136">B1108: WCF は `IncompleteSequenceBehavior` 要素の `DiscardFollowingFirstGap` と `NoDiscard` の値のみを使用します。</span><span class="sxs-lookup"><span data-stu-id="c85b5-136">B1108: WCF uses only the `DiscardFollowingFirstGap` and `NoDiscard` values in the `IncompleteSequenceBehavior` element.</span></span>

  - <span data-ttu-id="c85b5-137">WS-ReliableMessaging では、セッションを形成する、相関する 2 つの逆方向シーケンスを確立するために、`Offer` 機構を利用しています。</span><span class="sxs-lookup"><span data-stu-id="c85b5-137">WS-ReliableMessaging utilizes the `Offer` mechanism to establish the two converse correlated sequences that form a session.</span></span>

- <span data-ttu-id="c85b5-138">B1109: `CreateSequence` に `Offer` 要素が含まれている場合、WCF レスポンダーの一方向は、`Accept` 要素のない `CreateSequenceResponse` で応答することによって、提供されたシーケンスを拒否します。</span><span class="sxs-lookup"><span data-stu-id="c85b5-138">B1109: If `CreateSequence` contains an `Offer` element, the one way WCF Responder rejects the offered sequence by responding with a `CreateSequenceResponse` without an `Accept` element.</span></span>

- <span data-ttu-id="c85b5-139">B1110: 信頼できるメッセージングレスポンダーが提供されたシーケンスを拒否する場合、WCF イニシエーターは新しく確立されたシーケンスをエラーにします。</span><span class="sxs-lookup"><span data-stu-id="c85b5-139">B1110: If a Reliable Messaging Responder rejects the offered sequence, the WCF Initiator faults the newly established sequence.</span></span>

- <span data-ttu-id="c85b5-140">B1111: `CreateSequence` に `Offer` 要素が含まれていない場合、双方向の WCF レスポンダーは `CreateSequenceRefused` エラーで応答することによって提供されたシーケンスを拒否します。</span><span class="sxs-lookup"><span data-stu-id="c85b5-140">B1111: If `CreateSequence` does not contain an `Offer` element, the two-way WCF Responder rejects the offered sequence by responding with a `CreateSequenceRefused` fault.</span></span>

- <span data-ttu-id="c85b5-141">R1112: 2 つの逆方向シーケンスが `Offer` 機構を使用して確立された場合、`[address]` エンドポイント参照の `CreateSequenceResponse/Accept/AcksTo` プロパティは、バイト単位で `CreateSequence` メッセージの送信先 URI と一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c85b5-141">R1112: When two converse sequences are established using the `Offer` mechanism, the `[address]` property of the `CreateSequenceResponse/Accept/AcksTo` endpoint reference must match the destination URI of the `CreateSequence` message byte for byte.</span></span>

- <span data-ttu-id="c85b5-142">R1113: 2 つの逆方向シーケンスが `Offer` 機構を使用して確立された場合、イニシエーターからレスポンダーに流れる両方のシーケンスにあるすべてのメッセージは、同じエンドポイント参照に送信される必要があります。</span><span class="sxs-lookup"><span data-stu-id="c85b5-142">R1113: When two converse sequences are established using the `Offer` mechanism, all messages on both sequences flowing from the Initiator to the Responder must be sent to the same endpoint reference.</span></span>

<span data-ttu-id="c85b5-143">WCF では、ws-reliablemessaging を使用して、イニシエーターとレスポンダーの間に信頼できるセッションを確立します。</span><span class="sxs-lookup"><span data-stu-id="c85b5-143">WCF uses WS-ReliableMessaging to establish reliable sessions between the Initiator and the Responder.</span></span> <span data-ttu-id="c85b5-144">WCF Ws-reliablemessaging 実装は、一方向、要求/応答、および全二重のメッセージングパターンに対して信頼できるセッションを提供します。</span><span class="sxs-lookup"><span data-stu-id="c85b5-144">The WCF WS-ReliableMessaging implementation provides a reliable session for one-way, request-reply and full duplex messaging patterns.</span></span> <span data-ttu-id="c85b5-145">`Offer` および `CreateSequence` で WS-ReliableMessaging の `CreateSequenceResponse` 機構を使用すると、相関する 2 つの逆方向シーケンスを確立できます。また、Offer 機構は、すべてのメッセージ エンドポイントに適したセッション プロトコルを提供します。</span><span class="sxs-lookup"><span data-stu-id="c85b5-145">The WS-ReliableMessaging `Offer` mechanism on `CreateSequence` and `CreateSequenceResponse` lets you establish two correlated converse sequences and provides a session protocol that is suitable for all message endpoints.</span></span> <span data-ttu-id="c85b5-146">WCF では、セッション整合性に対するエンドツーエンドの保護を含むこのようなセッションに対してセキュリティ保証が提供されるため、同じパーティを対象としたメッセージが同じ送信先に到着することを確認することが実用的です。</span><span class="sxs-lookup"><span data-stu-id="c85b5-146">Because WCF provides a security guarantee for such a session including end-to-end protection for session integrity, it is practical to ensure that messages intended for the same party arrive at the same destination.</span></span> <span data-ttu-id="c85b5-147">また、これにより、アプリケーション メッセージにシーケンス受信確認を抱き合わせることができます。</span><span class="sxs-lookup"><span data-stu-id="c85b5-147">This also allows "piggy-backing" of sequence acknowledgements on application messages.</span></span> <span data-ttu-id="c85b5-148">したがって、制約 R1102、R1112、および R1113 は WCF に適用されます。</span><span class="sxs-lookup"><span data-stu-id="c85b5-148">Therefore, constraints R1102, R1112, and R1113 apply to WCF.</span></span>

<span data-ttu-id="c85b5-149">`CreateSequence` メッセージの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="c85b5-149">An example of a `CreateSequence` message.</span></span>

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

<span data-ttu-id="c85b5-150">`CreateSequenceResponse` メッセージの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="c85b5-150">An example of a `CreateSequenceResponse` message.</span></span>

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

### <a name="closing-a-sequence"></a><span data-ttu-id="c85b5-151">シーケンスを閉じる</span><span class="sxs-lookup"><span data-stu-id="c85b5-151">Closing a Sequence</span></span>

<span data-ttu-id="c85b5-152">WCF では、`CloseSequence` メッセージと `CloseSequenceResponse` メッセージを使用して、信頼性の高いメッセージングソースによるシャットダウンを実行します。</span><span class="sxs-lookup"><span data-stu-id="c85b5-152">WCF uses the `CloseSequence` and `CloseSequenceResponse` messages for a Reliable Messaging source-initiated shutdown.</span></span> <span data-ttu-id="c85b5-153">WCF の信頼できるメッセージの送信先はシャットダウンを開始せず、WCF Reliable Messaging source は、信頼できるメッセージングの送信先が開始したシャットダウンをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="c85b5-153">The WCF Reliable Messaging destination does not initiate shutdown and the WCF Reliable Messaging source does not support a Reliable Messaging destination-initiated shutdown.</span></span> <span data-ttu-id="c85b5-154">以下の制約が適用されます。</span><span class="sxs-lookup"><span data-stu-id="c85b5-154">The following constraints apply:</span></span>

- <span data-ttu-id="c85b5-155">B1201: WCF Reliable Messaging ソースは、シーケンスをシャットダウンするために常に `CloseSequence` メッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="c85b5-155">B1201: The WCF Reliable Messaging source always sends a `CloseSequence` message to shut down the sequence.</span></span>

- <span data-ttu-id="c85b5-156">B1202: 信頼できるメッセージの送信元は、`CloseSequence` メッセージを送信する前に、すべてのシーケンス メッセージの受信確認を待機します。</span><span class="sxs-lookup"><span data-stu-id="c85b5-156">B1202: The Reliable Messaging source waits for acknowledgement of the full range of sequence messages before sending the `CloseSequence` message.</span></span>

- <span data-ttu-id="c85b5-157">B1203: 信頼できるメッセージの送信元は、シーケンスにメッセージが含まれない場合を除き、常にオプションの `LastMsgNumber` 要素を含めます。</span><span class="sxs-lookup"><span data-stu-id="c85b5-157">B1203: The Reliable Messaging source always includes the optional `LastMsgNumber` element unless the sequence does not contain messages.</span></span>

- <span data-ttu-id="c85b5-158">R1204: 信頼できるメッセージの送信先は、`CloseSequence` メッセージを送信してシャットダウンを開始することはできません。</span><span class="sxs-lookup"><span data-stu-id="c85b5-158">R1204: The Reliable Messaging destination must not initiate shutdown by sending a `CloseSequence` message.</span></span>

- <span data-ttu-id="c85b5-159">B1205: `CloseSequence` メッセージを受信すると、WCF Reliable Messaging ソースはシーケンスが未完了と見なされ、エラーが送信されます。</span><span class="sxs-lookup"><span data-stu-id="c85b5-159">B1205: Upon receiving a `CloseSequence` message, the WCF Reliable Messaging source considers the sequence incomplete and sends a fault.</span></span>

 <span data-ttu-id="c85b5-160">`CloseSequence` メッセージの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="c85b5-160">An example of a `CloseSequence` message.</span></span>

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

<span data-ttu-id="c85b5-161">`CloseSequenceResponse` メッセージの例:</span><span class="sxs-lookup"><span data-stu-id="c85b5-161">Example `CloseSequenceResponse` message:</span></span>

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

### <a name="sequence-termination"></a><span data-ttu-id="c85b5-162">シーケンスの終了</span><span class="sxs-lookup"><span data-stu-id="c85b5-162">Sequence Termination</span></span>

<span data-ttu-id="c85b5-163">WCF は、主に `CloseSequence/CloseSequenceResponse` ハンドシェイクの完了後に `TerminateSequence/TerminateSequenceResponse` ハンドシェイクを使用します。</span><span class="sxs-lookup"><span data-stu-id="c85b5-163">WCF primarily uses the `TerminateSequence/TerminateSequenceResponse` handshake after completing the `CloseSequence/CloseSequenceResponse` handshake.</span></span> <span data-ttu-id="c85b5-164">WCF の信頼できるメッセージの送信先は、終了を開始せず、信頼できるメッセージの送信元は、信頼できるメッセージの送信先が開始した終了をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="c85b5-164">The WCF Reliable Messaging destination does not initiate termination and the Reliable Messaging source does not support a Reliable Messaging destination-initiated termination.</span></span> <span data-ttu-id="c85b5-165">以下の制約が適用されます。</span><span class="sxs-lookup"><span data-stu-id="c85b5-165">The following constraints apply:</span></span>

- <span data-ttu-id="c85b5-166">B1301: WCF イニシエーターは、`CloseSequence/CloseSequenceResponse` ハンドシェイクが正常に完了した後、`TerminateSequence` メッセージのみを送信します。</span><span class="sxs-lookup"><span data-stu-id="c85b5-166">B1301: The WCF Initiator only sends the `TerminateSequence` message after the successful completion of the `CloseSequence/CloseSequenceResponse` handshake.</span></span>

- <span data-ttu-id="c85b5-167">R1302: WCF は、`LastMsgNumber` 要素が、指定されたシーケンスのすべての `CloseSequence` と `TerminateSequence` メッセージ間で一貫しているかどうかを検証します。</span><span class="sxs-lookup"><span data-stu-id="c85b5-167">R1302: WCF validates that the `LastMsgNumber` element is consistent across all `CloseSequence` and `TerminateSequence` messages for a given sequence.</span></span> <span data-ttu-id="c85b5-168">つまり、`LastMsgNumber` は、すべての `CloseSequence` メッセージおよび `TerminateSequence` メッセージに存在しないか、すべての `CloseSequence` メッセージおよび `TerminateSequence` メッセージに存在し、同一であるかのいずれかです。</span><span class="sxs-lookup"><span data-stu-id="c85b5-168">This means that `LastMsgNumber` is either not present on all `CloseSequence` and `TerminateSequence` messages, or it is present and identical on all `CloseSequence` and `TerminateSequence` messages.</span></span>

- <span data-ttu-id="c85b5-169">B1303: `TerminateSequence` ハンドシェイクの後、`CloseSequence/CloseSequenceResponse` メッセージを受け取ると、信頼できるメッセージの送信先が `TerminateSequenceResponse` メッセージで応答します。</span><span class="sxs-lookup"><span data-stu-id="c85b5-169">B1303: When receiving a `TerminateSequence` message after the `CloseSequence/CloseSequenceResponse` handshake, the Reliable Messaging destination responds with a `TerminateSequenceResponse` message.</span></span> <span data-ttu-id="c85b5-170">信頼できるメッセージの配信元は、`TerminateSequence` メッセージを送信する前に最終受信確認を受けるため、信頼できるメッセージの送信先ではシーケンスが終了したことが確実にわかり、すぐにリソースを再要求します。</span><span class="sxs-lookup"><span data-stu-id="c85b5-170">Because the Reliable Messaging source has the final acknowledgement before sending the `TerminateSequence` message, the Reliable Messaging destination knows without doubt that the sequence ends, and reclaims resources immediately.</span></span>

- <span data-ttu-id="c85b5-171">B1304: `CloseSequence/CloseSequenceResponse` ハンドシェイクの前に `TerminateSequence` メッセージを受信すると、WCF の信頼できるメッセージの送信先は `TerminateSequenceResponse` メッセージで応答します。</span><span class="sxs-lookup"><span data-stu-id="c85b5-171">B1304: When receiving a `TerminateSequence` message prior to the `CloseSequence/CloseSequenceResponse` handshake, the WCF Reliable Messaging destination responds with a `TerminateSequenceResponse` message.</span></span> <span data-ttu-id="c85b5-172">信頼できるメッセージの送信先でシーケンスが一貫していると判断した場合、信頼できるメッセージの送信先は、リソースを再要求する前にアプリケーションの送信先で指定された時間待機し、クライアントが最終受信確認を受け取ることができるようにします。</span><span class="sxs-lookup"><span data-stu-id="c85b5-172">If the Reliable Messaging destination determines that there are no inconsistencies in the sequence, the Reliable Messaging destination waits for an application destination-specified time before reclaiming resources, to allow the client the chance to receive the final acknowledgement.</span></span> <span data-ttu-id="c85b5-173">それ以外の場合は、信頼できるメッセージの送信先はすぐにリソースを再要求し、`Faulted` イベントを発生させて、不明なシーケンスの終了をアプリケーションの送信先に示します。</span><span class="sxs-lookup"><span data-stu-id="c85b5-173">Otherwise, the Reliable Messaging destination reclaims resources immediately and indicates to the application destination that the sequence ends with doubt by raising the `Faulted` event.</span></span>

<span data-ttu-id="c85b5-174">`TerminateSequence` メッセージの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="c85b5-174">An example of a `TerminateSequence` message.</span></span>

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

<span data-ttu-id="c85b5-175">`TerminateSequenceResponse` メッセージの例:</span><span class="sxs-lookup"><span data-stu-id="c85b5-175">Example `TerminateSequenceResponse` message:</span></span>

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

### <a name="sequences"></a><span data-ttu-id="c85b5-176">シーケンス</span><span class="sxs-lookup"><span data-stu-id="c85b5-176">Sequences</span></span>

<span data-ttu-id="c85b5-177">シーケンスに適用される制約を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="c85b5-177">The following is a list of constraints that apply to sequences:</span></span>

- <span data-ttu-id="c85b5-178">B1401: WCF は、`xs:long`の最大包括値9223372036854775807を超えるシーケンス番号を生成し、それにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="c85b5-178">B1401:WCF generates and accesses sequence numbers no higher than `xs:long`’s maximum inclusive value, 9223372036854775807.</span></span>

<span data-ttu-id="c85b5-179">`Sequence` ヘッダーの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="c85b5-179">An example of a `Sequence` header.</span></span>

```xml
<wsrm:Sequence s:mustUnderstand="1">
  <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>
  <wsrm:MessageNumber>1</wsrm:MessageNumber>
</wsrm:Sequence>
```

### <a name="request-acknowledgement"></a><span data-ttu-id="c85b5-180">受信確認の要求</span><span class="sxs-lookup"><span data-stu-id="c85b5-180">Request Acknowledgement</span></span>

<span data-ttu-id="c85b5-181">WCF では、`AckRequested` ヘッダーをキープアライブメカニズムとして使用します。</span><span class="sxs-lookup"><span data-stu-id="c85b5-181">WCF uses the `AckRequested` header as a keep-alive mechanism.</span></span>

<span data-ttu-id="c85b5-182">`AckRequested` ヘッダーの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="c85b5-182">An example of an `AckRequested` header.</span></span>

```xml
<wsrm:AckRequested>
  <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>
</wsrm:AckRequested>
```

### <a name="sequenceacknowledgement"></a><span data-ttu-id="c85b5-183">SequenceAcknowledgement</span><span class="sxs-lookup"><span data-stu-id="c85b5-183">SequenceAcknowledgement</span></span>

<span data-ttu-id="c85b5-184">WCF では、WS-RELIABLEMESSAGING で提供されるシーケンス受信確認に "豚" メカニズムを使用します。</span><span class="sxs-lookup"><span data-stu-id="c85b5-184">WCF uses a "piggy-back" mechanism for sequence acknowledgements provided in WS-Reliable Messaging.</span></span> <span data-ttu-id="c85b5-185">以下の制約が適用されます。</span><span class="sxs-lookup"><span data-stu-id="c85b5-185">The following constraints apply:</span></span>

- <span data-ttu-id="c85b5-186">R1601: `Offer` 機構を使用して2つの逆方向シーケンスを確立すると、目的の受信者に送信されるアプリケーションメッセージに `SequenceAcknowledgement` ヘッダーが含まれる場合があります。</span><span class="sxs-lookup"><span data-stu-id="c85b5-186">R1601: When two converse sequences are established using the `Offer` mechanism, the `SequenceAcknowledgement` header may be included in any application message transmitted to the intended recipient.</span></span> <span data-ttu-id="c85b5-187">リモートのエンドポイントは、追加された `SequenceAcknowledgement` ヘッダーにアクセスできる必要があります。</span><span class="sxs-lookup"><span data-stu-id="c85b5-187">The remote endpoint must be able to access a piggybacked `SequenceAcknowledgement` header.</span></span>

- <span data-ttu-id="c85b5-188">B1602: WCF は、`Nack` 要素を含む `SequenceAcknowledgement` ヘッダーを生成しません。</span><span class="sxs-lookup"><span data-stu-id="c85b5-188">B1602: WCF does not generate `SequenceAcknowledgement` headers that contain `Nack` elements.</span></span> <span data-ttu-id="c85b5-189">WCF は、各 `Nack` 要素にシーケンス番号が含まれていることを検証しますが、それ以外の場合は `Nack` の要素と値を無視します。</span><span class="sxs-lookup"><span data-stu-id="c85b5-189">WCF validates that each `Nack` element contains a sequence number, but otherwise ignores the `Nack` element and value.</span></span>

 <span data-ttu-id="c85b5-190">`SequenceAcknowledgement` ヘッダーの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="c85b5-190">An example of a `SequenceAcknowledgement` header.</span></span>

```xml
<wsrm:SequenceAcknowledgement>
  <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>
  <wsrm:AcknowledgementRange Lower="1" Upper="1"></wsrm:AcknowledgementRange>
</wsrm:SequenceAcknowledgement>
```

### <a name="ws-reliablemessaging-faults"></a><span data-ttu-id="c85b5-191">WS-ReliableMessaging エラー</span><span class="sxs-lookup"><span data-stu-id="c85b5-191">WS-ReliableMessaging Faults</span></span>

<span data-ttu-id="c85b5-192">次に、WS-RELIABLEMESSAGING エラーの WCF 実装に適用される制約の一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="c85b5-192">The following is a list of constraints that apply to the WCF implementation of WS-ReliableMessaging faults.</span></span> <span data-ttu-id="c85b5-193">以下の制約が適用されます。</span><span class="sxs-lookup"><span data-stu-id="c85b5-193">The following constraints apply:</span></span>

- <span data-ttu-id="c85b5-194">B1701: WCF は `MessageNumberRollover` エラーを生成しません。</span><span class="sxs-lookup"><span data-stu-id="c85b5-194">B1701: WCF does not generate `MessageNumberRollover` faults.</span></span>

- <span data-ttu-id="c85b5-195">B1702: SOAP 1.2 では、サービスエンドポイントが接続制限に達し、新しい接続を処理できない場合、WCF は、次の例に示すように、入れ子になった `CreateSequenceRefused` fault サブコード `netrm:ConnectionLimitReached`を生成します。</span><span class="sxs-lookup"><span data-stu-id="c85b5-195">B1702: Over SOAP 1.2, when the service endpoint reaches its connection limit and cannot process new connections, WCF generates a nested `CreateSequenceRefused` fault subcode, `netrm:ConnectionLimitReached`, as shown in the following example.</span></span>

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

### <a name="ws-addressing-faults"></a><span data-ttu-id="c85b5-196">WS-Addressing エラー</span><span class="sxs-lookup"><span data-stu-id="c85b5-196">WS-Addressing Faults</span></span>

<span data-ttu-id="c85b5-197">Ws-reliablemessaging では WS-ADDRESSING を使用するため、WCF の Ws-reliablemessaging 実装で WS-ADDRESSING エラーが生成され、送信されることがあります。</span><span class="sxs-lookup"><span data-stu-id="c85b5-197">Because WS-ReliableMessaging uses WS-Addressing, the WCF WS-ReliableMessaging implementation may generate and transmit WS-Addressing faults.</span></span> <span data-ttu-id="c85b5-198">このセクションでは、WCF が明示的に生成し、ws-reliablemessaging 層で送信する WS-ADDRESSING エラーについて説明します。</span><span class="sxs-lookup"><span data-stu-id="c85b5-198">This section covers the WS-Addressing faults that WCF explicitly generates and transmits at the WS-ReliableMessaging layer:</span></span>

- <span data-ttu-id="c85b5-199">B1801: WCF は、次のいずれかに該当する場合に `Message Addressing Header Required` エラーを生成して送信します。</span><span class="sxs-lookup"><span data-stu-id="c85b5-199">B1801:WCF generates and transmits the `Message Addressing Header Required` fault when one of the following is true:</span></span>

  - <span data-ttu-id="c85b5-200">`CreateSequence`、`CloseSequence`、または `TerminateSequence` メッセージに `MessageId` ヘッダーがない。</span><span class="sxs-lookup"><span data-stu-id="c85b5-200">A `CreateSequence`, `CloseSequence` or `TerminateSequence` message is missing a `MessageId` header.</span></span>

  - <span data-ttu-id="c85b5-201">`CreateSequence`、`CloseSequence`、または `TerminateSequence` メッセージに `ReplyTo` ヘッダーがない。</span><span class="sxs-lookup"><span data-stu-id="c85b5-201">A `CreateSequence`, `CloseSequence` or `TerminateSequence` message is missing a `ReplyTo` header.</span></span>

  - <span data-ttu-id="c85b5-202">`CreateSequenceResponse`、`CloseSequenceResponse`、または `TerminateSequenceResponse` メッセージに `RelatesTo` ヘッダーがない。</span><span class="sxs-lookup"><span data-stu-id="c85b5-202">A `CreateSequenceResponse`, `CloseSequenceResponse`, or `TerminateSequenceResponse` message is missing a `RelatesTo` header.</span></span>

- <span data-ttu-id="c85b5-203">B1802: WCF は、`Endpoint Unavailable` エラーを生成して送信し、`CreateSequence` メッセージのアドレス指定ヘッダーの検査に基づいて、シーケンスを処理できるエンドポイントがリッスンしていないことを示します。</span><span class="sxs-lookup"><span data-stu-id="c85b5-203">B1802:WCF generates and transmits the `Endpoint Unavailable` fault to indicate there is no endpoint listening that can process the sequence based on examination of the addressing headers in the `CreateSequence` message.</span></span>

## <a name="protocol-composition"></a><span data-ttu-id="c85b5-204">プロトコル コンポジション</span><span class="sxs-lookup"><span data-stu-id="c85b5-204">Protocol Composition</span></span>

### <a name="composition-with-ws-addressing"></a><span data-ttu-id="c85b5-205">WS-Addressing によるコンポジション</span><span class="sxs-lookup"><span data-stu-id="c85b5-205">Composition with WS-Addressing</span></span>

<span data-ttu-id="c85b5-206">WCF は、ws-addressing の2つのバージョンをサポートしています。 ws-addressing 2004/08 [WS-ADDRESSING] と W3C WS-ADDRESSING 1.0 の推奨事項 [WS-FEDERATION-CORE] と [WS-FEDERATION-SOAP]。</span><span class="sxs-lookup"><span data-stu-id="c85b5-206">WCF supports two versions of WS-Addressing: WS-Addressing 2004/08 [WS-ADDR] and W3C WS-Addressing 1.0 Recommendations [WS-ADDR-CORE] and [WS-ADDR-SOAP].</span></span>

<span data-ttu-id="c85b5-207">WS-ReliableMessaging 仕様に記載されているのは、WS-Addressing 2004/08 だけですが、使用する WS-Addressing のバージョンが制限されているわけではありません。</span><span class="sxs-lookup"><span data-stu-id="c85b5-207">While the WS-ReliableMessaging specification mentions only WS-Addressing 2004/08, it does not restrict the WS-Addressing version to be used.</span></span> <span data-ttu-id="c85b5-208">WCF に適用される制約の一覧を次に示します。</span><span class="sxs-lookup"><span data-stu-id="c85b5-208">The following is a list of constraints that apply to WCF:</span></span>

- <span data-ttu-id="c85b5-209">R2101: WS-Addressing 2004/08 と WS-Addressing 1.0 の両方を WS-ReliableMessaging で使用できます。</span><span class="sxs-lookup"><span data-stu-id="c85b5-209">R2101: Both WS-Addressing 2004/08 and WS-Addressing 1.0 can be used with WS-Reliable Messaging.</span></span>

- <span data-ttu-id="c85b5-210">R2102: 特定の WS-ReliableMessaging シーケンス、または `Offer` 機構を使用して関連付けられた逆方向シーケンスのペアでは、同じバージョンの WS-Addressing を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c85b5-210">R2102: A single version of WS-Addressing must be used throughout a given WS-ReliableMessaging sequence or a pair of converse sequences correlated by using the `Offer` mechanism.</span></span>

### <a name="composition-with-soap"></a><span data-ttu-id="c85b5-211">SOAP によるコンポジション</span><span class="sxs-lookup"><span data-stu-id="c85b5-211">Composition with SOAP</span></span>

<span data-ttu-id="c85b5-212">WCF では、WS-TRUST Messaging で SOAP 1.1 と SOAP 1.2 の両方を使用できます。</span><span class="sxs-lookup"><span data-stu-id="c85b5-212">WCF supports the use of both SOAP 1.1 and SOAP 1.2 with WS-Reliable Messaging.</span></span>

### <a name="composition-with-ws-security-and-ws-secureconversation"></a><span data-ttu-id="c85b5-213">WS-Security と WS-SecureConversation によるコンポジション</span><span class="sxs-lookup"><span data-stu-id="c85b5-213">Composition with WS-Security and WS-SecureConversation</span></span>

<span data-ttu-id="c85b5-214">WCF は、セキュリティで保護されたトランスポート (HTTPS)、WS-SECURITY によるコンポジション、および WS-SECURITY によるメッセージ交換を使用した構成を使用して、ws-reliablemessaging シーケンスを保護します。</span><span class="sxs-lookup"><span data-stu-id="c85b5-214">WCF provides protection for WS-ReliableMessaging sequences by using secure Transport (HTTPS), composition with WS-Security, and composition with WS-Secure Conversation.</span></span> <span data-ttu-id="c85b5-215">WS-ReliableMessaging 1.1 プロトコル、WS-Security 1.1、および WS-Secure Conversation 1.3 プロトコルは一緒に使う必要があります。</span><span class="sxs-lookup"><span data-stu-id="c85b5-215">The WS-ReliableMessaging 1.1 protocol, WS-Security 1.1 and WS-Secure Conversation 1.3 protocol should be used together.</span></span> <span data-ttu-id="c85b5-216">WCF に適用される制約の一覧を次に示します。</span><span class="sxs-lookup"><span data-stu-id="c85b5-216">The following is a list of constraints that apply to WCF:</span></span>

- <span data-ttu-id="c85b5-217">R2301: 個々のメッセージの整合性と機密性だけでなく、ws-reliablemessaging シーケンスの整合性を保護するために、WCF では、WS-SECURITY メッセージ交換を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c85b5-217">R2301: To protect the integrity of a WS-ReliableMessaging sequence in addition to the integrity and confidentiality of individual messages, WCF requires that WS-Secure Conversation must be used.</span></span>

- <span data-ttu-id="c85b5-218">R2302: AWS-Ws-reliablemessaging シーケンスを確立する前に、セキュリティで保護されたメッセージ交換セッションを確立する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c85b5-218">R2302:AWS-Secure Conversation session must be established prior to establishing WS-ReliableMessaging sequence(s).</span></span>

- <span data-ttu-id="c85b5-219">R2303: WS-ReliableMessaging シーケンスの有効期間が WS-SecureConversation セッションの有効期間よりも長い場合は、対応する WS-SecureConversation Renewal バインディングを使用して、WS-SecureConversation によって確立された `SecurityContextToken` を更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c85b5-219">R2303: If the WS-ReliableMessaging sequence lifetime exceeds the WS-Secure Conversation session’s lifetime, the `SecurityContextToken` established by using WS-Secure Conversation must be renewed by using the corresponding WS-Secure Conversation Renewal binding.</span></span>

- <span data-ttu-id="c85b5-220">B2304: ws-reliablemessaging シーケンスまたは相関した逆方向シーケンスのペアは、常に1つの Ws-secureconversation セッションにバインドされます。</span><span class="sxs-lookup"><span data-stu-id="c85b5-220">B2304:WS-ReliableMessaging sequence or a pair of correlated converse sequences are always bound to a single WS-SecureConversation session.</span></span>

- <span data-ttu-id="c85b5-221">R2305: セキュリティで保護されたメッセージ交換で構成されている場合、WCF レスポンダーでは、`CreateSequence` メッセージに `wsse:SecurityTokenReference` 要素と `wsrm:UsesSequenceSTR` ヘッダーが含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="c85b5-221">R2305: When composed with WS-Secure Conversation, the WCF responder requires that the `CreateSequence` message contain the `wsse:SecurityTokenReference` element and the `wsrm:UsesSequenceSTR` header.</span></span>

 <span data-ttu-id="c85b5-222">`UsesSequenceSTR` ヘッダーの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="c85b5-222">An example of a `UsesSequenceSTR` header.</span></span>

```xml
<wsrm:UsesSequenceSTR></wsrm:UsesSequenceSTR>
```

### <a name="composition-with-ssltls-sessions"></a><span data-ttu-id="c85b5-223">SSL/TLS セッションによるコンポジション</span><span class="sxs-lookup"><span data-stu-id="c85b5-223">Composition with SSL/TLS sessions</span></span>

<span data-ttu-id="c85b5-224">WCF では、SSL/TLS セッションを使用した構成はサポートされません。</span><span class="sxs-lookup"><span data-stu-id="c85b5-224">WCF does not support composition with SSL/TLS sessions:</span></span>

- <span data-ttu-id="c85b5-225">B2401: WCF は `wsrm:UsesSequenceSSL` ヘッダーを生成しません。</span><span class="sxs-lookup"><span data-stu-id="c85b5-225">B2401: WCF does not generate the `wsrm:UsesSequenceSSL` header.</span></span>

- <span data-ttu-id="c85b5-226">R2402: 信頼できるメッセージングイニシエーターは、`wsrm:UsesSequenceSSL` ヘッダーを持つ `CreateSequence` メッセージを WCF レスポンダーに送信することはできません。</span><span class="sxs-lookup"><span data-stu-id="c85b5-226">R2402: A Reliable Messaging Initiator must not send a `CreateSequence` message with a `wsrm:UsesSequenceSSL` header to a WCF Responder.</span></span>

### <a name="composition-with-ws-policy"></a><span data-ttu-id="c85b5-227">WS-Policy によるコンポジション</span><span class="sxs-lookup"><span data-stu-id="c85b5-227">Composition with WS-Policy</span></span>

<span data-ttu-id="c85b5-228">WCF では、ws-policy 1.2 と WS-POLICY 1.5 の2つのバージョンがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="c85b5-228">WCF supports two versions of WS-Policy: WS-Policy 1.2 and WS-Policy 1.5.</span></span>

## <a name="ws-reliablemessaging-ws-policy-assertion"></a><span data-ttu-id="c85b5-229">WS-ReliableMessaging の WS-Policy アサーション</span><span class="sxs-lookup"><span data-stu-id="c85b5-229">WS-ReliableMessaging WS-Policy Assertion</span></span>

<span data-ttu-id="c85b5-230">WCF では、ws-reliablemessaging の ws-policy アサーション `wsrm:RMAssertion` を使用して、エンドポイントの機能を記述します。</span><span class="sxs-lookup"><span data-stu-id="c85b5-230">WCF uses WS-ReliableMessaging WS-Policy Assertion `wsrm:RMAssertion` to describe endpoints capabilities.</span></span> <span data-ttu-id="c85b5-231">WCF に適用される制約の一覧を次に示します。</span><span class="sxs-lookup"><span data-stu-id="c85b5-231">The following is a list of constraints that apply to WCF:</span></span>

- <span data-ttu-id="c85b5-232">B3001: WCF `wsrmn:RMAssertion` WS-POLICY アサーションを `wsdl:binding` の要素にアタッチします。</span><span class="sxs-lookup"><span data-stu-id="c85b5-232">B3001: WCF attaches `wsrmn:RMAssertion` WS-Policy Assertion to `wsdl:binding` elements.</span></span> <span data-ttu-id="c85b5-233">WCF では、`wsdl:binding` の添付ファイルと `wsdl:port` 要素の両方がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="c85b5-233">WCF supports both attachments to `wsdl:binding` and `wsdl:port` elements.</span></span>

- <span data-ttu-id="c85b5-234">B3002: WCF は `wsp:Optional` タグを生成しません。</span><span class="sxs-lookup"><span data-stu-id="c85b5-234">B3002: WCF never generates the `wsp:Optional` tag.</span></span>

- <span data-ttu-id="c85b5-235">B3003: WS-POLICY アサーション `wsrmp:RMAssertion` アクセスすると、WCF は `wsp:Optional` タグを無視し、WS-FEDERATION ポリシーを必須として扱います。</span><span class="sxs-lookup"><span data-stu-id="c85b5-235">B3003: When accessing the `wsrmp:RMAssertion` WS-Policy Assertion, WCF ignores the `wsp:Optional` tag and treats the WS-RM policy as mandatory.</span></span>

- <span data-ttu-id="c85b5-236">R3004: WCF は SSL/TLS セッションで構成されないため、WCF は `wsrmp:SequenceTransportSecurity`を指定するポリシーを受け入れません。</span><span class="sxs-lookup"><span data-stu-id="c85b5-236">R3004: Because WCF does not compose with SSL/TLS sessions, WCF does not accept policy that specifies `wsrmp:SequenceTransportSecurity`.</span></span>

- <span data-ttu-id="c85b5-237">B3005: WCF は常に `wsrmp:DeliveryAssurance` 要素を生成します。</span><span class="sxs-lookup"><span data-stu-id="c85b5-237">B3005: WCF always generates the `wsrmp:DeliveryAssurance` element.</span></span>

- <span data-ttu-id="c85b5-238">B3006: WCF は常に `wsrmp:ExactlyOnce` 配信保証を指定します。</span><span class="sxs-lookup"><span data-stu-id="c85b5-238">B3006: WCF always specifies the `wsrmp:ExactlyOnce` delivery assurance.</span></span>

- <span data-ttu-id="c85b5-239">B3007: WCF は、ws-reliablemessaging アサーションの次のプロパティを生成して読み取り、WCF`ReliableSessionBindingElement`でそれらを制御します。</span><span class="sxs-lookup"><span data-stu-id="c85b5-239">B3007: WCF generates and reads the following properties of the WS-ReliableMessaging assertion and provides control over them on the WCF`ReliableSessionBindingElement`:</span></span>

  - `netrmp:InactivityTimeout`

  - `netrmp:AcknowledgementInterval`

  <span data-ttu-id="c85b5-240">`RMAssertion` の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="c85b5-240">An example of a `RMAssertion`.</span></span>

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

## <a name="flow-control-ws-reliablemessaging-extension"></a><span data-ttu-id="c85b5-241">WS-ReliableMessaging のフロー制御拡張</span><span class="sxs-lookup"><span data-stu-id="c85b5-241">Flow Control WS-ReliableMessaging Extension</span></span>

<span data-ttu-id="c85b5-242">WCF では、ws-reliablemessaging 拡張機能を使用して、シーケンスメッセージフローに対してさらに厳密な制御を提供します。</span><span class="sxs-lookup"><span data-stu-id="c85b5-242">WCF uses WS-ReliableMessaging extensibility to provide optional additional tighter control over sequence message flow.</span></span>

<span data-ttu-id="c85b5-243">フロー制御を有効にするには、<xref:System.ServiceModel.Channels.ReliableSessionBindingElement.FlowControlEnabled?displayProperty=nameWithType> プロパティを `true`に設定します。</span><span class="sxs-lookup"><span data-stu-id="c85b5-243">Flow control is enabled by setting the <xref:System.ServiceModel.Channels.ReliableSessionBindingElement.FlowControlEnabled?displayProperty=nameWithType> property to `true`.</span></span> <span data-ttu-id="c85b5-244">WCF に適用される制約の一覧を次に示します。</span><span class="sxs-lookup"><span data-stu-id="c85b5-244">The following is a list of constraints that apply to WCF:</span></span>

- <span data-ttu-id="c85b5-245">B4001: 信頼できるメッセージングフロー制御が有効になっている場合、WCF は、次の例に示すように、`SequenceAcknowledgement` ヘッダーの要素拡張に `netrm:BufferRemaining` 要素を生成します。</span><span class="sxs-lookup"><span data-stu-id="c85b5-245">B4001: When Reliable Messaging Flow Control is enabled, WCF generates a `netrm:BufferRemaining` element in the element extensibility of the `SequenceAcknowledgement` header, as shown in the following example.</span></span>

  ```xml
  <wsrm:SequenceAcknowledgement>
    <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>
    <wsrm:AcknowledgementRange Upper="1" Lower="1"/>
    <netrm:BufferRemaining>8</netrm:BufferRemaining>
  </wsrm:SequenceAcknowledgement>
  ```

- <span data-ttu-id="c85b5-246">B4002: 信頼できるメッセージングフロー制御が有効になっている場合でも、WCF では `SequenceAcknowledgement` ヘッダーに `netrm:BufferRemaining` 要素は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="c85b5-246">B4002: Even when Reliable Messaging Flow Control is enabled, WCF does not require a `netrm:BufferRemaining` element in the `SequenceAcknowledgement` header.</span></span>

- <span data-ttu-id="c85b5-247">B4003: WCF Reliable Messaging Destination は `netrm:BufferRemaining` を使用して、バッファーできる新しいメッセージの数を示します。</span><span class="sxs-lookup"><span data-stu-id="c85b5-247">B4003: WCF Reliable Messaging Destination uses `netrm:BufferRemaining` to indicate how many new messages it can buffer.</span></span>

- <span data-ttu-id="c85b5-248">B4004: 信頼できるメッセージングフロー制御を有効にすると、WCF Reliable Messaging Source は `netrm:BufferRemaining` の値を使用してメッセージ転送を調整します。</span><span class="sxs-lookup"><span data-stu-id="c85b5-248">B4004:When Reliable Messaging Flow Control is enabled, the WCF Reliable Messaging Source uses the value of `netrm:BufferRemaining` to throttle message transmission.</span></span>

- <span data-ttu-id="c85b5-249">B4005: WCF では、0 ~ 4096 の整数値 `netrm:BufferRemaining` 生成され、0 ~ `xs:int`の `maxInclusive` 値214748364を含む整数値が読み取られます。</span><span class="sxs-lookup"><span data-stu-id="c85b5-249">B4005: WCF generates `netrm:BufferRemaining` integer values between 0 and 4096 inclusive, and reads integer values between 0 and `xs:int`’s `maxInclusive` value 214748364 inclusive.</span></span>

## <a name="message-exchange-patterns"></a><span data-ttu-id="c85b5-250">メッセージ交換パターン</span><span class="sxs-lookup"><span data-stu-id="c85b5-250">Message Exchange Patterns</span></span>

<span data-ttu-id="c85b5-251">このセクションでは、ws-reliablemessaging をさまざまなメッセージ交換パターンに使用する場合の WCF の動作について説明します。</span><span class="sxs-lookup"><span data-stu-id="c85b5-251">This section describes WCF's behavior when WS-ReliableMessaging is used for different Message Exchange Patterns.</span></span> <span data-ttu-id="c85b5-252">各メッセージ交換パターンについて、次の 2 つの展開シナリオを考えます。</span><span class="sxs-lookup"><span data-stu-id="c85b5-252">For each Message Exchange Pattern the following two deployments scenarios are considered:</span></span>

- <span data-ttu-id="c85b5-253">アドレス不可能なイニシエーター : イニシエーターはファイアウォールの内側にあります。レスポンダーは HTTP 応答でのみイニシエーターにメッセージを配信できます。</span><span class="sxs-lookup"><span data-stu-id="c85b5-253">Non-Addressable Initiator: Initiator is behind a firewall; Responder can deliver messages to the Initiator only on HTTP responses.</span></span>

- <span data-ttu-id="c85b5-254">アドレス可能なイニシエーター : イニシエーターとレスポンダーの両方に HTTP 要求を送信できます。つまり、逆方向の 2 つの HTTP 接続を確立できます。</span><span class="sxs-lookup"><span data-stu-id="c85b5-254">Addressable Initiator: Initiator and Responder both can be sent HTTP requests; in other words, two converse HTTP connections can be established.</span></span>

### <a name="one-way-non-addressable-initiator"></a><span data-ttu-id="c85b5-255">一方向 : アドレス不可能なイニシエーター</span><span class="sxs-lookup"><span data-stu-id="c85b5-255">One-way, Non-addressable Initiator</span></span>

#### <a name="binding"></a><span data-ttu-id="c85b5-256">Binding</span><span class="sxs-lookup"><span data-stu-id="c85b5-256">Binding</span></span>

<span data-ttu-id="c85b5-257">WCF は、1つの HTTP チャネルで1つのシーケンスを使用して、一方向のメッセージ交換パターンを提供します。</span><span class="sxs-lookup"><span data-stu-id="c85b5-257">WCF provides a one-way message exchange pattern using one sequence over one HTTP channel.</span></span> <span data-ttu-id="c85b5-258">WCF は、HTTP 要求を使用して、発信側から応答側にすべてのメッセージを送信し、応答側から発信側にすべてのメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="c85b5-258">WCF uses HTTP requests to transmit all messages from the Initiator to the Responder and HTTP responses to transmit all messages from the Responder to the Initiator.</span></span>

#### <a name="createsequence-exchange"></a><span data-ttu-id="c85b5-259">CreateSequence の交換</span><span class="sxs-lookup"><span data-stu-id="c85b5-259">CreateSequence Exchange</span></span>

<span data-ttu-id="c85b5-260">WCF イニシエーターは、HTTP 要求に `Offer` 要素のない `CreateSequence` メッセージを転送し、HTTP 応答に `CreateSequenceResponse` メッセージを要求します。</span><span class="sxs-lookup"><span data-stu-id="c85b5-260">The WCF Initiator transmits a `CreateSequence` message with no `Offer` element on an HTTP request and expects the `CreateSequenceResponse` message on the HTTP response.</span></span> <span data-ttu-id="c85b5-261">WCF レスポンダーは、シーケンスを作成し、HTTP 応答に `Accept` 要素を持たない `CreateSequenceResponse` メッセージを転送します。</span><span class="sxs-lookup"><span data-stu-id="c85b5-261">The WCF Responder creates a sequence and transmits the `CreateSequenceResponse` message with no `Accept` element on the HTTP response.</span></span>

#### <a name="sequenceacknowledgement"></a><span data-ttu-id="c85b5-262">SequenceAcknowledgement</span><span class="sxs-lookup"><span data-stu-id="c85b5-262">SequenceAcknowledgement</span></span>

<span data-ttu-id="c85b5-263">WCF イニシエーターは、`CreateSequence` メッセージとエラーメッセージを除くすべてのメッセージの応答に対する受信確認を処理します。</span><span class="sxs-lookup"><span data-stu-id="c85b5-263">The WCF Initiator processes acknowledgements on the reply of all messages except the `CreateSequence` message and fault messages.</span></span> <span data-ttu-id="c85b5-264">WCF レスポンダーは、すべてのシーケンスメッセージと `AckRequested` メッセージに対して、HTTP 応答に対してスタンドアロンの受信確認を常に転送します。</span><span class="sxs-lookup"><span data-stu-id="c85b5-264">The WCF Responder always transmits a stand-alone acknowledgement on the HTTP response to all sequence and `AckRequested` messages.</span></span>

#### <a name="closesequence-exchange"></a><span data-ttu-id="c85b5-265">CloseSequence の交換</span><span class="sxs-lookup"><span data-stu-id="c85b5-265">CloseSequence Exchange</span></span>

<span data-ttu-id="c85b5-266">WCF イニシエーターは、HTTP 要求で `CloseSequence` メッセージを送信し、HTTP 応答で `CreateSequenceResponse` メッセージを想定します。</span><span class="sxs-lookup"><span data-stu-id="c85b5-266">The WCF Initiator transmits a `CloseSequence` message on an HTTP request and expects the `CreateSequenceResponse` message on the HTTP response.</span></span> <span data-ttu-id="c85b5-267">WCF レスポンダーは、HTTP 応答で `CloseSequenceResponse` メッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="c85b5-267">The WCF Responder transmits the `CloseSequenceResponse` message on the HTTP response.</span></span>

#### <a name="terminatesequence-exchange"></a><span data-ttu-id="c85b5-268">TerminateSequence の交換</span><span class="sxs-lookup"><span data-stu-id="c85b5-268">TerminateSequence Exchange</span></span>

<span data-ttu-id="c85b5-269">WCF イニシエーターは、HTTP 要求で `TerminateSequence` メッセージを送信し、HTTP 応答で `TerminateSequenceResponse` メッセージを想定します。</span><span class="sxs-lookup"><span data-stu-id="c85b5-269">The WCF Initiator transmits a `TerminateSequence` message on an HTTP request and expects the `TerminateSequenceResponse` message on the HTTP response.</span></span> <span data-ttu-id="c85b5-270">WCF レスポンダーは、HTTP 応答で `TerminateSequenceResponse` メッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="c85b5-270">The WCF Responder transmits the `TerminateSequenceResponse` message on the HTTP response.</span></span>

### <a name="one-way-addressable-initiator"></a><span data-ttu-id="c85b5-271">一方向 : アドレス可能なイニシエーター</span><span class="sxs-lookup"><span data-stu-id="c85b5-271">One Way, Addressable Initiator</span></span>

#### <a name="binding"></a><span data-ttu-id="c85b5-272">Binding</span><span class="sxs-lookup"><span data-stu-id="c85b5-272">Binding</span></span>

<span data-ttu-id="c85b5-273">WCF では、1つの受信と送信の HTTP チャネルを1つのシーケンスを使用して、一方向のメッセージ交換パターンを提供します。</span><span class="sxs-lookup"><span data-stu-id="c85b5-273">WCF provides a one-way message exchange pattern using one sequence over one inbound and one outbound HTTP channel.</span></span> <span data-ttu-id="c85b5-274">WCF は、HTTP 要求を使用してすべてのメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="c85b5-274">WCF uses the HTTP requests to transmit all messages.</span></span> <span data-ttu-id="c85b5-275">すべての HTTP 応答に、空の本文と HTTP 202 ステータス コードが含まれます。</span><span class="sxs-lookup"><span data-stu-id="c85b5-275">All HTTP responses have an empty body and HTTP 202 status code.</span></span>

#### <a name="createsequence-exchange"></a><span data-ttu-id="c85b5-276">CreateSequence の交換</span><span class="sxs-lookup"><span data-stu-id="c85b5-276">CreateSequence Exchange</span></span>

<span data-ttu-id="c85b5-277">WCF イニシエーターは、HTTP 要求に `Offer` 要素のない `CreateSequence` メッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="c85b5-277">The WCF Initiator transmits a `CreateSequence` message with no `Offer` element on an HTTP request.</span></span> <span data-ttu-id="c85b5-278">WCF レスポンダーは、シーケンスを作成し、HTTP 要求に `Accept` 要素を持たない `CreateSequenceResponse` メッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="c85b5-278">The WCF Responder creates a sequence and transmits the `CreateSequenceResponse` message with no `Accept` element on an HTTP request.</span></span>

### <a name="duplex-addressable-initiator"></a><span data-ttu-id="c85b5-279">双方向 : アドレス可能なイニシエーター</span><span class="sxs-lookup"><span data-stu-id="c85b5-279">Duplex, Addressable Initiator</span></span>

#### <a name="binding"></a><span data-ttu-id="c85b5-280">Binding</span><span class="sxs-lookup"><span data-stu-id="c85b5-280">Binding</span></span>

<span data-ttu-id="c85b5-281">WCF は、1つの受信と1つの送信 HTTP チャネルに対して2つのシーケンスを使用して、完全に非同期の双方向メッセージ交換パターンを提供します。</span><span class="sxs-lookup"><span data-stu-id="c85b5-281">WCF provides a fully-asynchronous, two-way message exchange pattern using two sequences over one inbound and one outbound HTTP channel.</span></span> <span data-ttu-id="c85b5-282">このメッセージ交換パターンは、限定された方法で `Request/Reply`、`Addressable` イニシエーター メッセージ交換パターンに組み込むことができます。</span><span class="sxs-lookup"><span data-stu-id="c85b5-282">This message exchange pattern can be mixed with the `Request/Reply`, `Addressable` Initiator message exchange pattern in a limited way.</span></span> <span data-ttu-id="c85b5-283">WCF では、HTTP 要求を使用してすべてのメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="c85b5-283">WCF uses HTTP requests to transmit all messages.</span></span> <span data-ttu-id="c85b5-284">すべての HTTP 応答に、空の本文と HTTP 202 ステータス コードが含まれます。</span><span class="sxs-lookup"><span data-stu-id="c85b5-284">All HTTP responses have an empty body and HTTP 202 status code.</span></span>

#### <a name="createsequence-exchange"></a><span data-ttu-id="c85b5-285">CreateSequence の交換</span><span class="sxs-lookup"><span data-stu-id="c85b5-285">CreateSequence Exchange</span></span>

<span data-ttu-id="c85b5-286">WCF イニシエーターは、HTTP 要求で `Offer` 要素を使用して `CreateSequence` メッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="c85b5-286">The WCF Initiator transmits a `CreateSequence` message with an `Offer` element on an HTTP request.</span></span> <span data-ttu-id="c85b5-287">WCF レスポンダーは、`CreateSequence` が `Offer` 要素を持つことを保証し、シーケンスを作成し、`Accept` 要素を使用して `CreateSequenceResponse` メッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="c85b5-287">The WCF Responder ensures that the `CreateSequence` has an `Offer` element, then creates a sequence and transmits the `CreateSequenceResponse` message with an `Accept` element.</span></span>

#### <a name="sequence-lifetime"></a><span data-ttu-id="c85b5-288">シーケンスの有効期間</span><span class="sxs-lookup"><span data-stu-id="c85b5-288">Sequence Lifetime</span></span>

<span data-ttu-id="c85b5-289">WCF では、2つのシーケンスが1つの完全な二重セッションとして扱われます。</span><span class="sxs-lookup"><span data-stu-id="c85b5-289">WCF treats the two sequences as one fully-duplex session.</span></span>

<span data-ttu-id="c85b5-290">1つのシーケンスに障害が発生したエラーが生成されると、WCF は、リモートエンドポイントが両方のシーケンスをフォールトすることを想定しています。</span><span class="sxs-lookup"><span data-stu-id="c85b5-290">Upon generating a fault that faults one sequence, WCF expects the remote endpoint to fault both sequences.</span></span> <span data-ttu-id="c85b5-291">1つのシーケンスで障害が発生したエラーを読み取ると、WCF は両方のシーケンスをエラーにします。</span><span class="sxs-lookup"><span data-stu-id="c85b5-291">Upon reading a fault that faults one sequence, WCF faults both sequences.</span></span>

<span data-ttu-id="c85b5-292">WCF は、その送信シーケンスを終了し、受信シーケンスでメッセージを処理し続けることができます。</span><span class="sxs-lookup"><span data-stu-id="c85b5-292">WCF can close its outbound sequence and continue to process messages on its inbound sequence.</span></span> <span data-ttu-id="c85b5-293">逆に、WCF では、受信シーケンスの終了を処理し、送信シーケンスでメッセージを送信し続けることができます。</span><span class="sxs-lookup"><span data-stu-id="c85b5-293">Conversely, WCF can process the close of the inbound sequence and continue to send messages on its outbound sequence.</span></span>

### <a name="request-reply-and-one-way-non-addressable-initiator"></a><span data-ttu-id="c85b5-294">要求/応答および一方向のアドレス不可能なイニシエーター</span><span class="sxs-lookup"><span data-stu-id="c85b5-294">Request-Reply and One-Way, Non-Addressable Initiator</span></span>

#### <a name="binding"></a><span data-ttu-id="c85b5-295">Binding</span><span class="sxs-lookup"><span data-stu-id="c85b5-295">Binding</span></span>

<span data-ttu-id="c85b5-296">WCF は、1つの HTTP チャネルで2つのシーケンスを使用して、一方向および要求/応答メッセージ交換パターンを提供します。</span><span class="sxs-lookup"><span data-stu-id="c85b5-296">WCF provides a one-way and request-reply message exchange pattern using two sequences over one HTTP channel.</span></span> <span data-ttu-id="c85b5-297">WCF は、HTTP 要求を使用して、発信側から応答側にすべてのメッセージを送信し、応答側から発信側にすべてのメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="c85b5-297">WCF uses HTTP requests to transmit all messages from the Initiator to the Responder and HTTP responses to transmit all messages from the Responder to the Initiator.</span></span>

#### <a name="createsequence-exchange"></a><span data-ttu-id="c85b5-298">CreateSequence の交換</span><span class="sxs-lookup"><span data-stu-id="c85b5-298">CreateSequence Exchange</span></span>

<span data-ttu-id="c85b5-299">WCF イニシエーターは、HTTP 要求で `Offer` 要素を持つ `CreateSequence` メッセージを転送し、HTTP 応答に `CreateSequenceResponse` メッセージを要求します。</span><span class="sxs-lookup"><span data-stu-id="c85b5-299">The WCF Initiator transmits a `CreateSequence` message with an `Offer` element on an HTTP request and expects the `CreateSequenceResponse` message on the HTTP response.</span></span> <span data-ttu-id="c85b5-300">WCF レスポンダーは、シーケンスを作成し、HTTP 応答で `Accept` 要素を使用して `CreateSequenceResponse` メッセージを転送します。</span><span class="sxs-lookup"><span data-stu-id="c85b5-300">The WCF Responder creates a sequence and transmits the `CreateSequenceResponse` message with an `Accept` element on the HTTP response.</span></span>

#### <a name="one-way-message"></a><span data-ttu-id="c85b5-301">一方向のメッセージ</span><span class="sxs-lookup"><span data-stu-id="c85b5-301">One-way Message</span></span>

<span data-ttu-id="c85b5-302">一方向メッセージ交換を正常に完了するために、WCF イニシエーターは HTTP 要求で要求シーケンスメッセージを送信し、HTTP 応答でスタンドアロンの `SequenceAcknowledgement` メッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="c85b5-302">To complete a one-way message exchange successfully, the WCF Initiator transmits a request sequence message on the HTTP request and receives a standalone `SequenceAcknowledgement` message on the HTTP response.</span></span> <span data-ttu-id="c85b5-303">`SequenceAcknowledgement` は、送信されたメッセージの受信確認を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="c85b5-303">The `SequenceAcknowledgement` must acknowledge the message transmitted.</span></span>

<span data-ttu-id="c85b5-304">WCF レスポンダーは、受信確認、エラー、または空の本文と HTTP 202 状態コードを持つ応答で要求に応答できます。</span><span class="sxs-lookup"><span data-stu-id="c85b5-304">The WCF Responder may reply to the request with an acknowledgement, a fault, or a response with an empty body and HTTP 202 status code.</span></span>

#### <a name="two-way-messages"></a><span data-ttu-id="c85b5-305">双方向のメッセージ</span><span class="sxs-lookup"><span data-stu-id="c85b5-305">Two Way Messages</span></span>

<span data-ttu-id="c85b5-306">双方向メッセージ交換プロトコルを正常に完了するために、WCF イニシエーターは HTTP 要求で要求シーケンスメッセージを送信し、HTTP 応答で応答シーケンスメッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="c85b5-306">To complete a two way message exchange protocol successfully, the WCF Initiator transmits a request sequence message on the HTTP request and receives a reply sequence message on the HTTP response.</span></span> <span data-ttu-id="c85b5-307">応答では、送信された要求シーケンス メッセージの受信確認を行う `SequenceAcknowledgement` を送信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c85b5-307">The response must carry a `SequenceAcknowledgement` acknowledging the request sequence message transmitted.</span></span>

<span data-ttu-id="c85b5-308">WCF レスポンダーは、アプリケーション応答、エラー、または空の本文と HTTP 202 状態コードを持つ応答で要求に応答できます。</span><span class="sxs-lookup"><span data-stu-id="c85b5-308">The WCF Responder may reply to the request with an application reply, a fault or a response with an empty body and HTTP 202 status code.</span></span>

<span data-ttu-id="c85b5-309">一方向のメッセージが存在することと、アプリケーション応答のタイミングもあるため、要求シーケンス メッセージのシーケンス番号と応答メッセージのシーケンス番号には相関関係はありません。</span><span class="sxs-lookup"><span data-stu-id="c85b5-309">Because of the presence of one-way messages and the timing of application replies, the request sequence message’s sequence number and the response message’s sequence number have no correlation.</span></span>

#### <a name="retrying-replies"></a><span data-ttu-id="c85b5-310">応答の再試行</span><span class="sxs-lookup"><span data-stu-id="c85b5-310">Retrying Replies</span></span>

<span data-ttu-id="c85b5-311">WCF は、双方向のメッセージ交換プロトコルの相関関係について、HTTP 要求/応答の相関関係に依存します。</span><span class="sxs-lookup"><span data-stu-id="c85b5-311">WCF relies on HTTP request-reply correlation for two-way message exchange protocol correlation.</span></span> <span data-ttu-id="c85b5-312">このため、要求シーケンスメッセージが受信確認されたときに、HTTP 応答に `SequenceAcknowledgement`、アプリケーション応答、またはエラーが含まれる場合、WCF イニシエーターは要求シーケンスメッセージの再試行を停止しません。</span><span class="sxs-lookup"><span data-stu-id="c85b5-312">Because of this, the WCF Initiator does not stop retrying a request sequence message when the request sequence message is acknowledged but rather when the HTTP response carries a `SequenceAcknowledgement`, application reply, or fault.</span></span> <span data-ttu-id="c85b5-313">WCF レスポンダーは、応答が関連付けられている要求の HTTP 応答で応答を再試行します。</span><span class="sxs-lookup"><span data-stu-id="c85b5-313">The WCF Responder retries replies on the HTTP response of the request to which the reply is correlated.</span></span>

#### <a name="closesequence-exchange"></a><span data-ttu-id="c85b5-314">CloseSequence の交換</span><span class="sxs-lookup"><span data-stu-id="c85b5-314">CloseSequence Exchange</span></span>

<span data-ttu-id="c85b5-315">WCF イニシエーターは、すべての一方向の要求シーケンスメッセージのすべての応答シーケンスメッセージと受信確認を受信した後、HTTP 要求で要求シーケンスの `CloseSequence` メッセージを転送し、HTTP 応答で `CloseSequenceResponse` を想定します。</span><span class="sxs-lookup"><span data-stu-id="c85b5-315">After receiving all reply sequence messages and acknowledgements for all one way request sequence messages, the WCF Initiator transmits a `CloseSequence` message for the request sequence on an HTTP request and expects the `CloseSequenceResponse` on the HTTP response.</span></span>

<span data-ttu-id="c85b5-316">要求シーケンスを終了すると、暗黙的に応答シーケンスが終了します。</span><span class="sxs-lookup"><span data-stu-id="c85b5-316">Closing the request sequence implicitly closes the reply sequence.</span></span> <span data-ttu-id="c85b5-317">これは、WCF イニシエーターが `CloseSequence` メッセージに応答シーケンスの最終 `SequenceAcknowledgement` を含め、応答シーケンスに `CloseSequence` 交換がないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="c85b5-317">This means the WCF Initiator includes the reply sequence’s Final `SequenceAcknowledgement` on the `CloseSequence` message and the reply sequence does not have a `CloseSequence` exchange.</span></span>

<span data-ttu-id="c85b5-318">WCF レスポンダーは、すべての応答が確認され、HTTP 応答で `CloseSequenceResponse` メッセージを送信することを保証します。</span><span class="sxs-lookup"><span data-stu-id="c85b5-318">The WCF Responder ensures all replies are acknowledged and transmits the `CloseSequenceResponse` message on the HTTP response.</span></span>

#### <a name="terminatesequence-exchange"></a><span data-ttu-id="c85b5-319">TerminateSequence の交換</span><span class="sxs-lookup"><span data-stu-id="c85b5-319">TerminateSequence Exchange</span></span>

<span data-ttu-id="c85b5-320">`CloseSequenceResponse` メッセージを受信すると、WCF イニシエーターは HTTP 要求で要求シーケンスの `TerminateSequence` メッセージを送信し、HTTP 応答に `TerminateSequenceResponse` を要求します。</span><span class="sxs-lookup"><span data-stu-id="c85b5-320">After receiving the `CloseSequenceResponse` message, the WCF Initiator transmits a `TerminateSequence` message for the request sequence on an HTTP request and expects the `TerminateSequenceResponse` on the HTTP response.</span></span>

<span data-ttu-id="c85b5-321">`CloseSequence` 交換と同じように、要求シーケンスを終了すると、暗黙的に応答シーケンスが終了します。</span><span class="sxs-lookup"><span data-stu-id="c85b5-321">Like the `CloseSequence` exchange, terminating the request sequence implicitly terminates the reply sequence.</span></span> <span data-ttu-id="c85b5-322">これは、WCF イニシエーターが `TerminateSequence` メッセージに応答シーケンスの最終 `SequenceAcknowledgement` を含め、応答シーケンスに `TerminateSequence` 交換がないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="c85b5-322">This means the WCF Initiator includes the reply sequence’s final `SequenceAcknowledgement` on the `TerminateSequence` message and the reply sequence does not have a `TerminateSequence` exchange.</span></span>

<span data-ttu-id="c85b5-323">WCF レスポンダーは、HTTP 応答で `TerminateSequenceResponse` メッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="c85b5-323">The WCF Responder transmits the `TerminateSequenceResponse` message on the HTTP response.</span></span>

### <a name="requestreply-addressable-initiator"></a><span data-ttu-id="c85b5-324">要求/応答 : アドレス可能なイニシエーター</span><span class="sxs-lookup"><span data-stu-id="c85b5-324">Request/Reply, Addressable Initiator</span></span>

#### <a name="binding"></a><span data-ttu-id="c85b5-325">Binding</span><span class="sxs-lookup"><span data-stu-id="c85b5-325">Binding</span></span>

<span data-ttu-id="c85b5-326">WCF は、1つの受信および1つの送信 HTTP チャネルに対して2つのシーケンスを使用して、要求/応答メッセージ交換パターンを提供します。</span><span class="sxs-lookup"><span data-stu-id="c85b5-326">WCF provides a request-reply message exchange pattern using two sequences over one inbound and one outbound HTTP channel.</span></span> <span data-ttu-id="c85b5-327">このメッセージ交換パターンは、限定された方法で `Duplex, Addressable` イニシエーター メッセージ交換パターンに組み込むことができます。</span><span class="sxs-lookup"><span data-stu-id="c85b5-327">This message exchange pattern can be mixed with the `Duplex, Addressable` Initiator message exchange pattern in a limited way.</span></span> <span data-ttu-id="c85b5-328">WCF は、HTTP 要求を使用してすべてのメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="c85b5-328">WCF uses the HTTP requests to transmit all messages.</span></span> <span data-ttu-id="c85b5-329">すべての HTTP 応答に、空の本文と HTTP 202 ステータス コードが含まれます。</span><span class="sxs-lookup"><span data-stu-id="c85b5-329">All HTTP responses have an empty body and HTTP 202 status code.</span></span>

#### <a name="createsequence-exchange"></a><span data-ttu-id="c85b5-330">CreateSequence の交換</span><span class="sxs-lookup"><span data-stu-id="c85b5-330">CreateSequence Exchange</span></span>

<span data-ttu-id="c85b5-331">WCF イニシエーターは、HTTP 要求で `Offer` 要素を使用して `CreateSequence` メッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="c85b5-331">The WCF Initiator transmits a `CreateSequence` message with an `Offer` element on an HTTP request.</span></span> <span data-ttu-id="c85b5-332">WCF レスポンダーは、`CreateSequence` に `Offer` 要素があることを確認し、シーケンスを作成し、`Accept` 要素を使用して `CreateSequenceResponse` メッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="c85b5-332">The WCF Responder ensures that the `CreateSequence` has an `Offer` element then creates a sequence and transmits the `CreateSequenceResponse` message with an `Accept` element.</span></span>

#### <a name="requestreply-correlation"></a><span data-ttu-id="c85b5-333">要求/応答の相関関係</span><span class="sxs-lookup"><span data-stu-id="c85b5-333">Request/Reply Correlation</span></span>

<span data-ttu-id="c85b5-334">次の状況は、すべての相関関係にある要求/応答で発生します。</span><span class="sxs-lookup"><span data-stu-id="c85b5-334">The following applies to all correlated requests and replies:</span></span>

- <span data-ttu-id="c85b5-335">WCF では、すべてのアプリケーション要求メッセージに `ReplyTo` エンドポイント参照と `MessageId`が確実に適用されます。</span><span class="sxs-lookup"><span data-stu-id="c85b5-335">WCF ensures all application request messages bear a `ReplyTo` endpoint reference and a `MessageId`.</span></span>

- <span data-ttu-id="c85b5-336">WCF は、各アプリケーション要求メッセージの `ReplyTo`としてローカルエンドポイント参照を適用します。</span><span class="sxs-lookup"><span data-stu-id="c85b5-336">WCF applies the local endpoint reference as each application request message’s `ReplyTo`.</span></span> <span data-ttu-id="c85b5-337">ローカル エンドポイント参照は、イニシエーターの `CreateSequence` メッセージの `ReplyTo` であり、レスポンダーの `CreateSequence` メッセージの `To` です。</span><span class="sxs-lookup"><span data-stu-id="c85b5-337">The local endpoint reference is the `CreateSequence` message’s `ReplyTo` for the Initiator and the `CreateSequence` message’s `To` for the Responder.</span></span>

- <span data-ttu-id="c85b5-338">WCF では、受信要求メッセージに `MessageId` と `ReplyTo`が確実に保持されます。</span><span class="sxs-lookup"><span data-stu-id="c85b5-338">WCF ensures that incoming request messages bear a `MessageId` and a `ReplyTo`.</span></span>

- <span data-ttu-id="c85b5-339">WCF は、すべてのアプリケーション要求メッセージの `ReplyTo` エンドポイント参照の URI が、前に定義したローカルエンドポイント参照と一致することを保証します。</span><span class="sxs-lookup"><span data-stu-id="c85b5-339">WCF ensures the `ReplyTo` endpoint reference’s URI of all application request messages match the local endpoint reference as defined earlier.</span></span>

- <span data-ttu-id="c85b5-340">WCF では、すべての応答に、`wsa` 要求/応答の相関関係規則に従って、正しい `RelatesTo` と `To` ヘッダーが確実に適用されます。</span><span class="sxs-lookup"><span data-stu-id="c85b5-340">WCF ensures that all replies bear the correct `RelatesTo` and `To` headers following `wsa` request/reply correlation rules.</span></span>
