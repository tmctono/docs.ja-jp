---
title: トランザクション プロトコル
ms.date: 03/30/2017
ms.assetid: 2820b0ec-2f32-430c-b299-1f0e95e1f2dc
ms.openlocfilehash: 3f4824ac6098f33b7bde4f29d3e0950783dfd213
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61918893"
---
# <a name="transaction-protocols"></a><span data-ttu-id="5afe7-102">トランザクション プロトコル</span><span class="sxs-lookup"><span data-stu-id="5afe7-102">Transaction Protocols</span></span>
<span data-ttu-id="5afe7-103">Windows Communication Foundation (WCF) は、Ws-atomic Transaction および Ws-coordination プロトコルを実装します。</span><span class="sxs-lookup"><span data-stu-id="5afe7-103">Windows Communication Foundation (WCF) implements WS-Atomic Transaction and WS-Coordination protocols.</span></span>  
  
|<span data-ttu-id="5afe7-104">仕様/ドキュメント</span><span class="sxs-lookup"><span data-stu-id="5afe7-104">Specification/Document</span></span>|<span data-ttu-id="5afe7-105">Version</span><span class="sxs-lookup"><span data-stu-id="5afe7-105">Version</span></span>|<span data-ttu-id="5afe7-106">リンク</span><span class="sxs-lookup"><span data-stu-id="5afe7-106">Link</span></span>|  
|-----------------------------|-------------|----------|  
|<span data-ttu-id="5afe7-107">WS-Coordination</span><span class="sxs-lookup"><span data-stu-id="5afe7-107">WS-Coordination</span></span>|<span data-ttu-id="5afe7-108">1</span><span class="sxs-lookup"><span data-stu-id="5afe7-108">1.0</span></span><br /><br /> <span data-ttu-id="5afe7-109">1.1</span><span class="sxs-lookup"><span data-stu-id="5afe7-109">1.1</span></span>|<https://go.microsoft.com/fwlink/?LinkId=96104><br /><br /> [https://go.microsoft.com/fwlink/?LinkId=96079](https://go.microsoft.com/fwlink/?LinkId=96079)|  
|<span data-ttu-id="5afe7-110">WS-AtomicTransaction</span><span class="sxs-lookup"><span data-stu-id="5afe7-110">WS-AtomicTransaction</span></span>|<span data-ttu-id="5afe7-111">1</span><span class="sxs-lookup"><span data-stu-id="5afe7-111">1.0</span></span><br /><br /> <span data-ttu-id="5afe7-112">1.1</span><span class="sxs-lookup"><span data-stu-id="5afe7-112">1.1</span></span>|<https://go.microsoft.com/fwlink/?LinkId=96080><br /><br /> https://go.microsoft.com/fwlink/?LinkId=96081|  
  
 <span data-ttu-id="5afe7-113">これらのプロトコル仕様の相互運用性は、アプリケーション間とトランザクション マネージャー間の 2 つのレベルで必要です (次の図を参照)。</span><span class="sxs-lookup"><span data-stu-id="5afe7-113">Interoperability on these protocol specifications is required at two levels: between applications and between transaction managers (see the following figure).</span></span> <span data-ttu-id="5afe7-114">仕様では、相互運用性の両方のレベルについて、メッセージ形式とメッセージ交換が詳細に説明されます。</span><span class="sxs-lookup"><span data-stu-id="5afe7-114">Specifications describe in great detail the message formats and message exchange for both interoperability levels.</span></span> <span data-ttu-id="5afe7-115">アプリケーション間での交換に必要な一定のセキュリティ、信頼性、およびエンコーディングは、通常のアプリケーションによる交換にも当てはまります。</span><span class="sxs-lookup"><span data-stu-id="5afe7-115">Certain security, reliability, and encodings for application-to-application exchange apply as they do for regular application exchange.</span></span> <span data-ttu-id="5afe7-116">ただし、トランザクション マネージャー間で適切な相互運用性を実現するには、特定のバインディングを使用するという合意が必要となります。通常、バインディングはユーザーによって構成されないためです。</span><span class="sxs-lookup"><span data-stu-id="5afe7-116">However, successful interoperability between transaction managers requires agreement on the particular binding, because it is usually not configured by the user.</span></span>  
  
 <span data-ttu-id="5afe7-117">ここでは、WS-AtomicTransaction (WS-AT) 仕様のセキュリティに関する構成と、トランザクション マネージャー間の通信に使用されるセキュリティで保護されたバインディングについて説明します。</span><span class="sxs-lookup"><span data-stu-id="5afe7-117">This topic describes a composition of the WS-Atomic Transaction (WS-AT) specification with security and describes the secure binding used for communication between transaction managers.</span></span> <span data-ttu-id="5afe7-118">このドキュメントで説明されているアプローチは、IBM、IONA、Sun Microsystems などを含む WS-AT および WS-Coordination の各種の実装でテスト済みのものです。</span><span class="sxs-lookup"><span data-stu-id="5afe7-118">The approach described in this document has been successfully tested with other implementations of WS-AT and WS-Coordination including IBM, IONA, Sun Microsystems, and others.</span></span>  
  
 <span data-ttu-id="5afe7-119">次の図は、Transaction Manager 1 と Transaction Manager 2 では、2 つのトランザクション マネージャーとアプリケーションの 1 とアプリケーション 2 の 2 つのアプリケーション間の相互運用性を示しています。</span><span class="sxs-lookup"><span data-stu-id="5afe7-119">The following figure depicts the interoperability between two transaction managers, Transaction Manager 1 and Transaction Manager 2, and two applications, Application 1 and Application 2:</span></span>  
  
 ![マネージャーのトランザクション間の相互作用を示すスクリーン ショット。](./media/transaction-protocols/transaction-managers-flow.gif)  
  
 <span data-ttu-id="5afe7-121">1 つのイニシエーター (I) と 1 つの参加要素 (P) を持つ、一般的な WS-Coordination/WS-AtomicTransaction のシナリオを考えます。</span><span class="sxs-lookup"><span data-stu-id="5afe7-121">Consider a typical WS-Coordination/WS-Atomic Transaction scenario with one Initiator (I) and one Participant (P).</span></span> <span data-ttu-id="5afe7-122">イニシエーターと参加要素の両方にトランザクション マネージャー (それぞれ ITM および PTM と呼びます) があります。</span><span class="sxs-lookup"><span data-stu-id="5afe7-122">Both Initiator and Participant have Transaction Managers, (ITM and PTM, respectively).</span></span> <span data-ttu-id="5afe7-123">2 フェーズ コミットは、このトピックでは 2PC と呼びます。</span><span class="sxs-lookup"><span data-stu-id="5afe7-123">Two-phase commit is referred to as 2PC in this topic.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="5afe7-124">1.CreateCoordinationContext</span><span class="sxs-lookup"><span data-stu-id="5afe7-124">1. CreateCoordinationContext</span></span>|<span data-ttu-id="5afe7-125">12.アプリケーション メッセージ応答</span><span class="sxs-lookup"><span data-stu-id="5afe7-125">12. Application Message Response</span></span>|  
|<span data-ttu-id="5afe7-126">2.CreateCoordinationContextResponse</span><span class="sxs-lookup"><span data-stu-id="5afe7-126">2. CreateCoordinationContextResponse</span></span>|<span data-ttu-id="5afe7-127">13.Commit (完了)</span><span class="sxs-lookup"><span data-stu-id="5afe7-127">13. Commit (Completion)</span></span>|  
|<span data-ttu-id="5afe7-128">3.Register (完了)</span><span class="sxs-lookup"><span data-stu-id="5afe7-128">3. Register (Completion)</span></span>|<span data-ttu-id="5afe7-129">14.Prepare (2PC)</span><span class="sxs-lookup"><span data-stu-id="5afe7-129">14. Prepare (2PC)</span></span>|  
|<span data-ttu-id="5afe7-130">4.RegisterResponse</span><span class="sxs-lookup"><span data-stu-id="5afe7-130">4. RegisterResponse</span></span>|<span data-ttu-id="5afe7-131">15.Prepare (2PC)</span><span class="sxs-lookup"><span data-stu-id="5afe7-131">15. Prepare (2PC)</span></span>|  
|<span data-ttu-id="5afe7-132">5.アプリケーション メッセージ</span><span class="sxs-lookup"><span data-stu-id="5afe7-132">5. Application Message</span></span>|<span data-ttu-id="5afe7-133">16.Prepared (2PC)</span><span class="sxs-lookup"><span data-stu-id="5afe7-133">16. Prepared (2PC)</span></span>|  
|<span data-ttu-id="5afe7-134">6.CreateCoordinationContext with Context</span><span class="sxs-lookup"><span data-stu-id="5afe7-134">6. CreateCoordinationContext with Context</span></span>|<span data-ttu-id="5afe7-135">17.Prepared (2PC)</span><span class="sxs-lookup"><span data-stu-id="5afe7-135">17. Prepared (2PC)</span></span>|  
|<span data-ttu-id="5afe7-136">7.Register (永続的)</span><span class="sxs-lookup"><span data-stu-id="5afe7-136">7. Register (Durable)</span></span>|<span data-ttu-id="5afe7-137">18.Committed (完了)</span><span class="sxs-lookup"><span data-stu-id="5afe7-137">18. Committed (Completion)</span></span>|  
|<span data-ttu-id="5afe7-138">8.RegisterResponse</span><span class="sxs-lookup"><span data-stu-id="5afe7-138">8. RegisterResponse</span></span>|<span data-ttu-id="5afe7-139">19.Commit (2PC)</span><span class="sxs-lookup"><span data-stu-id="5afe7-139">19. Commit (2PC)</span></span>|  
|<span data-ttu-id="5afe7-140">9.CreateCoordinationContextResponse</span><span class="sxs-lookup"><span data-stu-id="5afe7-140">9. CreateCoordinationContextResponse</span></span>|<span data-ttu-id="5afe7-141">20.Commit (2PC)</span><span class="sxs-lookup"><span data-stu-id="5afe7-141">20. Commit (2PC)</span></span>|  
|<span data-ttu-id="5afe7-142">10.Register (永続的)</span><span class="sxs-lookup"><span data-stu-id="5afe7-142">10. Register (Durable)</span></span>|<span data-ttu-id="5afe7-143">21.Committed (2PC)</span><span class="sxs-lookup"><span data-stu-id="5afe7-143">21. Committed (2PC)</span></span>|  
|<span data-ttu-id="5afe7-144">11.RegisterResponse</span><span class="sxs-lookup"><span data-stu-id="5afe7-144">11. RegisterResponse</span></span>|<span data-ttu-id="5afe7-145">22.Committed (2PC)</span><span class="sxs-lookup"><span data-stu-id="5afe7-145">22. Committed (2PC)</span></span>|  
  
 <span data-ttu-id="5afe7-146">このドキュメントでは、WS-AtomicTransaction 仕様のセキュリティに関する構成と、トランザクション マネージャー間の通信に使用されるセキュリティで保護されたバインディングについて説明します。</span><span class="sxs-lookup"><span data-stu-id="5afe7-146">This document describes a composition of the WS-AtomicTransaction specification with security and describes the secure binding used for communication between transaction managers.</span></span> <span data-ttu-id="5afe7-147">このドキュメントで説明されているアプローチは、WS-AT および WS-Coordination の各種の実装でテスト済みのものです。</span><span class="sxs-lookup"><span data-stu-id="5afe7-147">The approach described in this document has been successfully tested with other implementations of WS-AT and WS-Coordination.</span></span>  
  
 <span data-ttu-id="5afe7-148">この図および表では、セキュリティの観点から見た次の 4 つのクラスのメッセージを示しています。</span><span class="sxs-lookup"><span data-stu-id="5afe7-148">The figure and table illustrate four classes of messages from the viewpoint of security:</span></span>  
  
- <span data-ttu-id="5afe7-149">アクティベーション メッセージ (CreateCoordinationContext と CreateCoordinationContextResponse)</span><span class="sxs-lookup"><span data-stu-id="5afe7-149">Activation messages (CreateCoordinationContext and CreateCoordinationContextResponse).</span></span>  
  
- <span data-ttu-id="5afe7-150">登録メッセージ (Register と RegisterResponse)</span><span class="sxs-lookup"><span data-stu-id="5afe7-150">Registration messages (Register and RegisterResponse)</span></span>  
  
- <span data-ttu-id="5afe7-151">プロトコル メッセージ (Prepare、Rollback、Commit、Aborted など)</span><span class="sxs-lookup"><span data-stu-id="5afe7-151">Protocol messages (Prepare, Rollback, Commit, Aborted, and so on).</span></span>  
  
- <span data-ttu-id="5afe7-152">アプリケーション メッセージ</span><span class="sxs-lookup"><span data-stu-id="5afe7-152">Application messages.</span></span>  
  
 <span data-ttu-id="5afe7-153">最初の 3 つのメッセージ クラスはトランザクション マネージャーのメッセージと考えられます。これらのクラスのバインド構成については、後の「アプリケーション メッセージ交換」で説明します。</span><span class="sxs-lookup"><span data-stu-id="5afe7-153">The first three message classes are considered Transaction Manager messages and their binding configuration is described in the "Application Message Exchange" later in this topic.</span></span> <span data-ttu-id="5afe7-154">4 番目のメッセージ クラスは、アプリケーション間のメッセージであり、後の「メッセージの例」で説明します。</span><span class="sxs-lookup"><span data-stu-id="5afe7-154">The fourth class of message is application to application messages and is described in the "Message Examples" section later in this topic.</span></span> <span data-ttu-id="5afe7-155">このセクションでは、WCF によって使用されるこれらのクラスの各プロトコル バインディングについて説明します。</span><span class="sxs-lookup"><span data-stu-id="5afe7-155">This section describes the protocol bindings used for each of these classes by WCF.</span></span>  
  
 <span data-ttu-id="5afe7-156">このドキュメントでは、次の XML 名前空間と関連付けられたプレフィックスが使用されます。</span><span class="sxs-lookup"><span data-stu-id="5afe7-156">The following XML Namespaces and associated prefixes are used throughout this document.</span></span>  
  
|<span data-ttu-id="5afe7-157">プレフィックス</span><span class="sxs-lookup"><span data-stu-id="5afe7-157">Prefix</span></span>|<span data-ttu-id="5afe7-158">Version</span><span class="sxs-lookup"><span data-stu-id="5afe7-158">Version</span></span>|<span data-ttu-id="5afe7-159">名前空間の URI</span><span class="sxs-lookup"><span data-stu-id="5afe7-159">Namespace URI</span></span>|  
|------------|-------------|-------------------|  
|<span data-ttu-id="5afe7-160">s11</span><span class="sxs-lookup"><span data-stu-id="5afe7-160">s11</span></span>||<https://go.microsoft.com/fwlink/?LinkId=96014>|  
|<span data-ttu-id="5afe7-161">wsa</span><span class="sxs-lookup"><span data-stu-id="5afe7-161">wsa</span></span>|<span data-ttu-id="5afe7-162">1.0 より前</span><span class="sxs-lookup"><span data-stu-id="5afe7-162">Pre-1.0</span></span><br /><br /> <span data-ttu-id="5afe7-163">1</span><span class="sxs-lookup"><span data-stu-id="5afe7-163">1.0</span></span>|http://www.w3.org/2004/08/addressing<br /><br /> <https://go.microsoft.com/fwlink/?LinkId=96022>|  
|<span data-ttu-id="5afe7-164">wscoor</span><span class="sxs-lookup"><span data-stu-id="5afe7-164">wscoor</span></span>|<span data-ttu-id="5afe7-165">1</span><span class="sxs-lookup"><span data-stu-id="5afe7-165">1.0</span></span><br /><br /> <span data-ttu-id="5afe7-166">1.1</span><span class="sxs-lookup"><span data-stu-id="5afe7-166">1.1</span></span>|<https://go.microsoft.com/fwlink/?LinkId=96078><br /><br /> [https://go.microsoft.com/fwlink/?LinkId=96079](https://go.microsoft.com/fwlink/?LinkId=96079)|  
|<span data-ttu-id="5afe7-167">wsat</span><span class="sxs-lookup"><span data-stu-id="5afe7-167">wsat</span></span>|<span data-ttu-id="5afe7-168">1</span><span class="sxs-lookup"><span data-stu-id="5afe7-168">1.0</span></span><br /><br /> <span data-ttu-id="5afe7-169">1.1</span><span class="sxs-lookup"><span data-stu-id="5afe7-169">1.1</span></span>|<https://go.microsoft.com/fwlink/?LinkId=96080><br /><br /> [https://go.microsoft.com/fwlink/?LinkId=96081](https://go.microsoft.com/fwlink/?LinkId=96081)|  
|<span data-ttu-id="5afe7-170">t</span><span class="sxs-lookup"><span data-stu-id="5afe7-170">t</span></span>|<span data-ttu-id="5afe7-171">1.3 より前</span><span class="sxs-lookup"><span data-stu-id="5afe7-171">Pre-1.3</span></span><br /><br /> <span data-ttu-id="5afe7-172">1.3</span><span class="sxs-lookup"><span data-stu-id="5afe7-172">1.3</span></span>|<https://go.microsoft.com/fwlink/?LinkId=96082><br /><br /> [https://go.microsoft.com/fwlink/?LinkId=96100](https://go.microsoft.com/fwlink/?LinkId=96100)|  
|<span data-ttu-id="5afe7-173">o</span><span class="sxs-lookup"><span data-stu-id="5afe7-173">o</span></span>||<https://go.microsoft.com/fwlink/?LinkId=96101>|  
|<span data-ttu-id="5afe7-174">xsd</span><span class="sxs-lookup"><span data-stu-id="5afe7-174">xsd</span></span>||<https://go.microsoft.com/fwlink/?LinkId=96102>|  
  
## <a name="transaction-manager-bindings"></a><span data-ttu-id="5afe7-175">トランザクション マネージャー バインディング</span><span class="sxs-lookup"><span data-stu-id="5afe7-175">Transaction Manager Bindings</span></span>  
 <span data-ttu-id="5afe7-176">R1001:WS-AT 1.0 のトランザクションに参加しているトランザクション マネージャーでは、Ws-atomic Transaction、および Ws-coordination メッセージ交換の SOAP 1.1、Ws-addressing 2004/08 を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5afe7-176">R1001: Transaction Managers participating in a WS-AT 1.0 transaction must use SOAP 1.1 and WS-Addressing 2004/08 for WS-Atomic Transaction and WS-Coordination message exchanges.</span></span>  
  
 <span data-ttu-id="5afe7-177">R1002:WS-AT 1.1 トランザクションに参加しているトランザクション マネージャーは、SOAP 1.1、Ws-addressing 2005/08 for Ws-atomic Transaction および Ws-coordination メッセージ交換を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5afe7-177">R1002: Transaction Managers participating in a WS-AT 1.1 transaction must use SOAP 1.1 and WS-Addressing 2005/08 for WS-Atomic Transaction and WS-Coordination message exchanges.</span></span>  
  
 <span data-ttu-id="5afe7-178">アプリケーション メッセージは、後で説明するように、これらのバインディングに制限されません。</span><span class="sxs-lookup"><span data-stu-id="5afe7-178">Application messages are not constrained to these bindings and are described later.</span></span>  
  
### <a name="transaction-manager-https-binding"></a><span data-ttu-id="5afe7-179">トランザクション マネージャー HTTPS バインディング</span><span class="sxs-lookup"><span data-stu-id="5afe7-179">Transaction Manager HTTPS Binding</span></span>  
 <span data-ttu-id="5afe7-180">トランザクション マネージャー HTTPS バインディングは、セキュリティを実現してトランザクション ツリー内の送信者と受信者の各ペア間で信頼を確立するトランスポート セキュリティにのみ依存します。</span><span class="sxs-lookup"><span data-stu-id="5afe7-180">The transaction manager HTTPS binding relies solely on transport security to achieve security and establish trust between each sender-receiver pair in the transaction tree.</span></span>  
  
#### <a name="https-transport-configuration"></a><span data-ttu-id="5afe7-181">HTTPS トランスポート構成</span><span class="sxs-lookup"><span data-stu-id="5afe7-181">HTTPS Transport Configuration</span></span>  
 <span data-ttu-id="5afe7-182">トランザクション マネージャー ID を確立するために X.509 証明書が使用されます。</span><span class="sxs-lookup"><span data-stu-id="5afe7-182">X.509 certificates are used to establish Transaction Manager Identity.</span></span> <span data-ttu-id="5afe7-183">クライアントおよびサーバーの承認が必要です。クライアントおよびサーバーの承認は、以下のような実装詳細の状態にしておきます。</span><span class="sxs-lookup"><span data-stu-id="5afe7-183">Client/server authentication is required, and client/server authorization is left as an implementation detail:</span></span>  
  
- <span data-ttu-id="5afe7-184">R1111:発信元コンピューターの完全修飾ドメイン名 (FQDN) に一致するサブジェクト名、ネットワーク経由で提示された X.509 証明書が必要です。</span><span class="sxs-lookup"><span data-stu-id="5afe7-184">R1111: X.509 certificates presented over the wire must have a subject name that matches the fully qualified domain name (FQDN) of the originating machine.</span></span>  
  
- <span data-ttu-id="5afe7-185">B1112:DNS は、機能を正常に X.509 のサブジェクト名のチェックのシステムで各送信者と受信者ペアの間である必要があります。</span><span class="sxs-lookup"><span data-stu-id="5afe7-185">B1112: DNS must be functional between each sender-receiver pair in the system for X.509 subject name checks to succeed.</span></span>  
  
#### <a name="activation-and-registration-binding-configuration"></a><span data-ttu-id="5afe7-186">アクティベーションと登録のバインド構成</span><span class="sxs-lookup"><span data-stu-id="5afe7-186">Activation and Registration Binding Configuration</span></span>  
 <span data-ttu-id="5afe7-187">WCF では、HTTPS 経由での相関関係で要求/応答の二重バインディングが必要です。</span><span class="sxs-lookup"><span data-stu-id="5afe7-187">WCF requires request/reply duplex binding with correlation over HTTPS.</span></span> <span data-ttu-id="5afe7-188">(関連付けと要求/応答メッセージ交換パターンの詳細については、WS-AtomicTransaction 仕様のセクション 8 を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="5afe7-188">(For more information about correlation and descriptions of the request/reply message exchange patterns, see WS-Atomic Transaction, Section 8.)</span></span>  
  
#### <a name="2pc-protocol-binding-configuration"></a><span data-ttu-id="5afe7-189">2PC プロトコルのバインディング構成</span><span class="sxs-lookup"><span data-stu-id="5afe7-189">2PC Protocol Binding Configuration</span></span>  
 <span data-ttu-id="5afe7-190">WCF では、HTTPS 経由で一方向 (データグラム) メッセージをサポートします。</span><span class="sxs-lookup"><span data-stu-id="5afe7-190">WCF supports one-way (datagram) messages over HTTPS.</span></span> <span data-ttu-id="5afe7-191">メッセージ間の関連付けは、実装詳細の状態にしておきます。</span><span class="sxs-lookup"><span data-stu-id="5afe7-191">Correlation among the messages is left as an implementation detail.</span></span>  
  
 <span data-ttu-id="5afe7-192">B1131:実装をサポートする必要があります`wsa:ReferenceParameters`Ws-addressing WCF の 2 pc メッセージの関連付けを実現するために記載されています。</span><span class="sxs-lookup"><span data-stu-id="5afe7-192">B1131: Implementations must support `wsa:ReferenceParameters` as described in WS-Addressing to achieve correlation of WCF’s 2PC messages.</span></span>  
  
### <a name="transaction-manager-mixed-security-binding"></a><span data-ttu-id="5afe7-193">トランザクション マネージャーによる混合セキュリティ バインディング</span><span class="sxs-lookup"><span data-stu-id="5afe7-193">Transaction Manager Mixed Security Binding</span></span>  
 <span data-ttu-id="5afe7-194">これは、ID を確立するために、トランスポート セキュリティを WS-Coordination 発行済みトークン モデルと組み合わせて使用する代替の (混合モードの) バインディングです。</span><span class="sxs-lookup"><span data-stu-id="5afe7-194">This is an alternate (mixed mode) binding that uses transport security combined with the WS-Coordination Issued Token model for identity establishment purposes.</span></span> <span data-ttu-id="5afe7-195">2 つのバインディングを区別する要素は、アクティベーションと登録のみです。</span><span class="sxs-lookup"><span data-stu-id="5afe7-195">Activation and Registration are the only elements that differ between the two bindings.</span></span>  
  
#### <a name="https-transport-configuration"></a><span data-ttu-id="5afe7-196">HTTPS トランスポート構成</span><span class="sxs-lookup"><span data-stu-id="5afe7-196">HTTPS Transport Configuration</span></span>  
 <span data-ttu-id="5afe7-197">トランザクション マネージャー ID を確立するために X.509 証明書が使用されます。</span><span class="sxs-lookup"><span data-stu-id="5afe7-197">X.509 certificates are used to establish Transaction Manager Identity.</span></span> <span data-ttu-id="5afe7-198">クライアントおよびサーバーの承認が必要です。クライアントおよびサーバーの承認は、以下のような実装詳細の状態にしておきます。</span><span class="sxs-lookup"><span data-stu-id="5afe7-198">Client/Server authentication is required, and client/server authorization is left as an implementation detail.</span></span>  
  
#### <a name="activation-message-binding-configuration"></a><span data-ttu-id="5afe7-199">アクティベーション メッセージのバインド構成</span><span class="sxs-lookup"><span data-stu-id="5afe7-199">Activation Message Binding Configuration</span></span>  
 <span data-ttu-id="5afe7-200">アクティベーション メッセージは通常、アプリケーションとローカルのトランザクション マネージャー間で発生するため、相互運用には参加しません。</span><span class="sxs-lookup"><span data-stu-id="5afe7-200">Activation Messages usually do not participate in interoperability because they typically occur between an application and its local Transaction Manager.</span></span>  
  
 <span data-ttu-id="5afe7-201">B1221:WCF が双方向の HTTPS バインドを使用して (で説明されている[メッセージング プロトコル](../../../../docs/framework/wcf/feature-details/messaging-protocols.md)) アクティベーション メッセージ。</span><span class="sxs-lookup"><span data-stu-id="5afe7-201">B1221: WCF uses duplex HTTPS binding (described in [Messaging Protocols](../../../../docs/framework/wcf/feature-details/messaging-protocols.md)) for Activation messages.</span></span> <span data-ttu-id="5afe7-202">要求/応答メッセージは、WS-AT 1.0 の WS-Addressing 2004/08 と WS-AT 1.1 の WS-Addressing 2005/08 を使用して関連付けられます。</span><span class="sxs-lookup"><span data-stu-id="5afe7-202">Request and Reply messages are correlated using WS-Addressing 2004/08 for WS-AT 1.0 and WS-Addressing 2005/08 for WS-AT 1.1.</span></span>  
  
 <span data-ttu-id="5afe7-203">WS-AtomicTransaction 仕様のセクション 8 では、関連付けとメッセージ交換のパターンについて詳細に説明されています。</span><span class="sxs-lookup"><span data-stu-id="5afe7-203">WS-Atomic Transaction specification, Section 8, describes further details about correlation and the message exchange patterns.</span></span>  
  
- <span data-ttu-id="5afe7-204">R1222:受信すると、 `CreateCoordinationContext`、コーディネーターを発行する必要があります、`SecurityContextToken`関連付けられているシークレットを使用して`STx`します。</span><span class="sxs-lookup"><span data-stu-id="5afe7-204">R1222: Upon receiving a `CreateCoordinationContext`, the Coordinator must issue a `SecurityContextToken` with associated secret `STx`.</span></span> <span data-ttu-id="5afe7-205">このトークンは、WS-Trust の仕様に従って、`t:IssuedTokens` ヘッダー内に返されます。</span><span class="sxs-lookup"><span data-stu-id="5afe7-205">This token is returned inside a `t:IssuedTokens` header following WS-Trust specification.</span></span>  
  
- <span data-ttu-id="5afe7-206">R1223:既存のコーディネーション コンテキスト内でアクティブ化が発生した場合、`t:IssuedTokens`ヘッダーを`SecurityContextToken`に関連付けられた既存のコンテキストをフローする必要があります、`CreateCoordinationContext`メッセージ。</span><span class="sxs-lookup"><span data-stu-id="5afe7-206">R1223: If Activation occurs within an existing Coordination Context, the `t:IssuedTokens` header with the `SecurityContextToken` associated with existing Context must flow on the `CreateCoordinationContext` message.</span></span>  
  
 <span data-ttu-id="5afe7-207">新しい`t:IssuedTokens`への送信のヘッダーを生成する`wscoor:CreateCoordinationContextResponse`メッセージ。</span><span class="sxs-lookup"><span data-stu-id="5afe7-207">A new `t:IssuedTokens` header should be generated for attaching to the outgoing `wscoor:CreateCoordinationContextResponse` message.</span></span>  
  
#### <a name="registration-message-binding-configuration"></a><span data-ttu-id="5afe7-208">登録メッセージのバインディング構成</span><span class="sxs-lookup"><span data-stu-id="5afe7-208">Registration Message Binding Configuration</span></span>  
 <span data-ttu-id="5afe7-209">B1231:WCF が双方向の HTTPS バインドを使用して (で説明されている[メッセージング プロトコル](../../../../docs/framework/wcf/feature-details/messaging-protocols.md))。</span><span class="sxs-lookup"><span data-stu-id="5afe7-209">B1231: WCF uses duplex HTTPS binding (described in [Messaging Protocols](../../../../docs/framework/wcf/feature-details/messaging-protocols.md)).</span></span> <span data-ttu-id="5afe7-210">要求/応答メッセージは、WS-AT 1.0 の WS-Addressing 2004/08 と WS-AT 1.1 の WS-Addressing 2005/08 を使用して関連付けられます。</span><span class="sxs-lookup"><span data-stu-id="5afe7-210">Request and Reply messages are correlated using WS-Addressing 2004/08 for WS-AT 1.0 and WS-Addressing 2005/08 for WS-AT 1.1.</span></span>  
  
 <span data-ttu-id="5afe7-211">WS-AtomicTransaction 仕様のセクション 8 では、関連付けとメッセージ交換のパターンについて詳細に説明されています。</span><span class="sxs-lookup"><span data-stu-id="5afe7-211">WS-AtomicTransaction, Section 8, describes further details about correlation and descriptions of the message exchange patterns.</span></span>  
  
 <span data-ttu-id="5afe7-212">R1232:送信`wscoor:Register`メッセージを使用する必要があります、`IssuedTokenOverTransport`で説明されている認証モード[セキュリティ プロトコル](../../../../docs/framework/wcf/feature-details/security-protocols.md)します。</span><span class="sxs-lookup"><span data-stu-id="5afe7-212">R1232: Outgoing `wscoor:Register` messages must use the `IssuedTokenOverTransport` authentication mode described in [Security Protocols](../../../../docs/framework/wcf/feature-details/security-protocols.md).</span></span>  
  
 <span data-ttu-id="5afe7-213">`wsse:Timestamp`要素を使用して署名する必要があります、`SecurityContextToken STx`発行します。</span><span class="sxs-lookup"><span data-stu-id="5afe7-213">The `wsse:Timestamp` element must be signed using the `SecurityContextToken STx` issued.</span></span> <span data-ttu-id="5afe7-214">この署名は特定のトランザクションに関連付けられたトークンを所有していることの証明であり、トランザクションに登録されている参加要素の認証で使用されます。</span><span class="sxs-lookup"><span data-stu-id="5afe7-214">This signature is a proof of possession of the token associated with particular transaction and is used to authenticate a participant enlisting in the transaction.</span></span> <span data-ttu-id="5afe7-215">RegistrationResponse メッセージは、HTTPS を使用して返信されます。</span><span class="sxs-lookup"><span data-stu-id="5afe7-215">The RegistrationResponse message is sent back over HTTPS.</span></span>  
  
#### <a name="2pc-protocol-binding-configuration"></a><span data-ttu-id="5afe7-216">2PC プロトコルのバインディング構成</span><span class="sxs-lookup"><span data-stu-id="5afe7-216">2PC Protocol Binding Configuration</span></span>  
 <span data-ttu-id="5afe7-217">WCF では、HTTPS 経由で一方向 (データグラム) メッセージをサポートします。</span><span class="sxs-lookup"><span data-stu-id="5afe7-217">WCF supports one-way (datagram) messages over HTTPS.</span></span> <span data-ttu-id="5afe7-218">メッセージ間の関連付けは、実装詳細の状態にしておきます。</span><span class="sxs-lookup"><span data-stu-id="5afe7-218">Correlation among the messages is left as an implementation detail.</span></span>  
  
 <span data-ttu-id="5afe7-219">B1241:実装をサポートする必要があります`wsa:ReferenceParameters`Ws-addressing WCF の 2 pc メッセージの関連付けを実現するために記載されています。</span><span class="sxs-lookup"><span data-stu-id="5afe7-219">B1241: Implementations must support `wsa:ReferenceParameters` as described in WS-Addressing to achieve correlation of WCF’s 2PC messages.</span></span>  
  
## <a name="application-message-exchange"></a><span data-ttu-id="5afe7-220">アプリケーション メッセージ交換</span><span class="sxs-lookup"><span data-stu-id="5afe7-220">Application Message Exchange</span></span>  
 <span data-ttu-id="5afe7-221">アプリケーションでは、バインディングが次のセキュリティ要件を満たしている限り、アプリケーション間メッセージに任意のバインディングを使用できます。</span><span class="sxs-lookup"><span data-stu-id="5afe7-221">Applications are free to use any particular binding for application-to-application messages, as long as the binding meets the following security requirements:</span></span>  
  
- <span data-ttu-id="5afe7-222">R2001:アプリケーション間メッセージをフローする必要があります、`t:IssuedTokens`ヘッダーと共に、`CoordinationContext`メッセージのヘッダー。</span><span class="sxs-lookup"><span data-stu-id="5afe7-222">R2001: Application-to-application messages must flow the `t:IssuedTokens` header along with the `CoordinationContext` in the header of the message.</span></span>  
  
- <span data-ttu-id="5afe7-223">R2002:整合性と機密性`t:IssuedToken`提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5afe7-223">R2002: Integrity and confidentiality of `t:IssuedToken` must be provided.</span></span>  
  
 <span data-ttu-id="5afe7-224">`CoordinationContext` ヘッダーには `wscoor:Identifier` が含まれます。</span><span class="sxs-lookup"><span data-stu-id="5afe7-224">The `CoordinationContext` header contains `wscoor:Identifier`.</span></span> <span data-ttu-id="5afe7-225">定義`xsd:AnyURI`、絶対と相対 Uri を使用できるように WCF のみをサポート`wscoor:Identifiers`、絶対 Uri であります。</span><span class="sxs-lookup"><span data-stu-id="5afe7-225">While the definition of `xsd:AnyURI` allows the use of both absolute and relative URIs, WCF supports only `wscoor:Identifiers`, which are absolute URIs.</span></span>  
  
 <span data-ttu-id="5afe7-226">B2003:場合、`wscoor:Identifier`の`wscoor:CoordinationContext`は相対 URI では、トランザクションの WCF サービスからエラーが返されます。</span><span class="sxs-lookup"><span data-stu-id="5afe7-226">B2003: If the `wscoor:Identifier` of the `wscoor:CoordinationContext` is a relative URI, faults will be returned from transactional WCF services.</span></span>  
  
## <a name="message-examples"></a><span data-ttu-id="5afe7-227">メッセージの例</span><span class="sxs-lookup"><span data-stu-id="5afe7-227">Message Examples</span></span>  
  
### <a name="createcoordinationcontext-requestresponse-messages"></a><span data-ttu-id="5afe7-228">CreateCoordinationContext 要求/応答メッセージ</span><span class="sxs-lookup"><span data-stu-id="5afe7-228">CreateCoordinationContext Request/Response Messages</span></span>  
 <span data-ttu-id="5afe7-229">次のメッセージは、要求/応答のパターンに従います。</span><span class="sxs-lookup"><span data-stu-id="5afe7-229">The following messages follow a request/response pattern.</span></span>  
  
#### <a name="createcoordinationcontext-with-wscoor-10"></a><span data-ttu-id="5afe7-230">WSCoor 1.0 での CreateCoordinationContext</span><span class="sxs-lookup"><span data-stu-id="5afe7-230">CreateCoordinationContext with WSCoor 1.0</span></span>  
  
```xml  
<s:Envelope>  
  <s:Header>  
    <a:Action>http://.../ws/2004/10/wscoor/CreateCoordinationContext</Action>  
    <a:MessageID>urn:uuid:069f5104-fd88-4264-9f99-60032a82854e</MessageID>  
    <a:ReplyTo>  
      <Address>https://...</a:Address>  
    </a:ReplyTo>  
    <a:To>https://...</a:To>  
    <wsse:Security>  
      <u:Timestamp>  
        <wsu:Created>2005-12-15T23:36:09.921Z</u:Created>  
        <wsu:Expires>2005-12-15T23:41:09.921Z</u:Expires>  
      </u:Timestamp>  
    </wsse:Security>  
  </s:Header>  
  <s:Body xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">  
    <wscoor:CreateCoordinationContext>  
      <wscoor:CoordinationType>...</wscoor:CoordinationType>  
    </wscoor:CreateCoordinationContext>  
  </s:Body>  
</s11:Envelope>  
```  
  
#### <a name="createcoordinationcontext-with-wscoor-11"></a><span data-ttu-id="5afe7-231">WSCoor 1.1 での CreateCoordinationContext</span><span class="sxs-lookup"><span data-stu-id="5afe7-231">CreateCoordinationContext with WSCoor 1.1</span></span>  
  
```xml  
<s:Envelope>   
<s:Header>  
<a:Action>http://docs.oasis-open.org/ws-tx/wscoor/2006/06/CreateCoordinationContext</Action>  
<a:MessageID>urn:uuid:069f5104-fd88-4264-9f99-60032a82854e</MessageID>  
<a:ReplyTo>   
<Address>https://...</a:Address>   
</a:ReplyTo>   
<a:To>https://...</a:To>   
<wsse:Security>  
 <u:Timestamp>  
<wsu:Created>2005-12-15T23:36:09.921Z</u:Created>  
<wsu:Expires>2005-12-15T23:41:09.921Z</u:Expires>  
</u:Timestamp>   
</wsse:Security>   
</s:Header>   
<s:Body xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">  
<wscoor:CreateCoordinationContext>  
<wscoor:CoordinationType>...</wscoor:CoordinationType>  
</wscoor:CreateCoordinationContext>  
 </s:Body>  
</s11:Envelope>  
```  
  
#### <a name="createcoordinationcontextresponse-with-trust-pre-13-and-wscoor-10"></a><span data-ttu-id="5afe7-232">Trust Pre-1.3 および WSCoor 1.0 での CreateCoordinationContextResponse</span><span class="sxs-lookup"><span data-stu-id="5afe7-232">CreateCoordinationContextResponse with Trust Pre-1.3 and WSCoor 1.0</span></span>  
  
```xml  
<s:Envelope>  
  <!-- Data below is shown in the clear for  
       illustration purposes only. -->  
  <s:Header>  
    <a:Action>./ws/2004/10/wscoor/CreateCoordinationContextResponse </a:Action>  
    <a:RelatesTo>urn:uuid:069f5104-fd88-4264-9f99-60032a82854e</a:RelatesTo>  
    <a:To s:mustUnderstand="1">https://... </a:To>  
    <t:IssuedTokens>  
 <wst:RequestSecurityTokenResponse     
    xmlns:wsse="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"  
    xmlns:wssu="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-utility-1.0.xsd"   
    xmlns:wst="http://schemas.xmlsoap.org/ws/2005/02/trust"  
    xmlns:wsc="http://schemas.xmlsoap.org/ws/2005/02/sc"  
    xmlns:wsp="http://schemas.xmlsoap.org/ws/2004/09/policy">  
    <wst:TokenType>http://schemas.xmlsoap.org/ws/2005/02/sc/sct</wst:TokenType>  
    <wst:RequestedSecurityToken>  
      <wsc:SecurityContextToken>  
        <wssu:Identifier>  
          http://fabrikam123.com/SCTi  
        </wssu:Identifier>  
      </wsc:SecurityContextToken>   
    </wst:RequestedSecurityToken>  
    <wsp:AppliesTo>  
        http://fabrikam123.com/CCi  
    </wsp:AppliesTo>    
    <wst:RequestedAttachedReference>  
      <wsse:SecurityTokenReference >  
        <wsse:Reference   
           ValueType="http://schemas.xmlsoap.org/ws/2005/02/sc/sct"  
           URI="http://fabrikam123.com/SCTi"/>  
      </wsse:SecurityTokenReference>  
    </wst:RequestedAttachedReference>  
    <wst:RequestedUnattachedReference>  
      <wsse:SecurityTokenReference>  
        <wsse:Reference   
          ValueType="http://schemas.xmlsoap.org/ws/2005/02/sc/sct"  
          URI="http://fabrikam123.com/SCTi"/>  
      </wsse:SecurityTokenReference>  
    </wst:RequestedUnattachedReference>  
    <wst:RequestedProofToken>  
      <wst:BinarySecret   
        Type="http://schemas.xmlsoap.org/ws/2005/02/trust/SymmetricKey">  
        <!-- base64 encoded value -->  
      </wst:BinarySecret>  
    </wst:RequestedProofToken>  
    <wst:Lifetime>  
      <wssu:Created>2005-10-24T20:19:26.526Z</wssu:Created>  
      <wssu:Expires>2005-10-25T06:24:26.526Z</wssu:Expires>  
    </wst:Lifetime>  
    <wst:KeySize>256</wst:KeySize>  
</wst:RequestSecurityTokenResponse>  
    </t:IssuedTokens>  
    <o:Security xmlns:o="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd">  
      <u:Timestamp u:Id="_0">  
        <u:Created>2005-12-15T23:36:12.015Z</u:Created>  
        <u:Expires>2005-12-15T23:41:12.015Z</u:Expires>  
      </u:Timestamp>  
    </o:Security>  
  </s:Header>  
  <s:Body>  
    <wscoor:CreateCoordinationContextResponse>  
      <wscoor:CoordinationContext>  
        <wscoor:Identifier>  
     http://fabrikam123.com/CCi  
      </wscoor:Identifier>  
        <wscoor:Expires>...</wscoor:Expires>  
        <wscoor:CoordinationType>...</wscoor:CoordinationType>  
        <wscoor:RegistrationService>  
          <a:Address>https://...</a:Address>  
          <a:ReferenceParameters>  
             ...  
          </a:ReferenceParameters>  
        </wscoor:RegistrationService>  
      </wscoor:CoordinationContext>  
    </wscoor:CreateCoordinationContextResponse>  
  </s:Body>  
</s:Envelope>  
```  
  
#### <a name="createcoordinationcontextresponse-with-trust-13-and-wscoor-11"></a><span data-ttu-id="5afe7-233">Trust 1.3 および WSCoor 1.1 での CreateCoordinationContextResponse</span><span class="sxs-lookup"><span data-stu-id="5afe7-233">CreateCoordinationContextResponse with Trust 1.3 and WSCoor 1.1</span></span>  
  
```xml  
<s:Envelope>  
<!-- Data below is shown in the clear for illustration purposes only. -->   
<s:Header>   
<a:Action>http://docs.oasis-open.org/ws-tx/wscoor/2006/06/CreateCoordinationContextResponse </a:Action>  
<a:RelatesTo>urn:uuid:069f5104-fd88-4264-9f99-60032a82854e</a:RelatesTo>  
<a:To s:mustUnderstand="1">https://... </a:To>   
<t:IssuedTokens>   
<wst:RequestSecurityTokenResponse   
xmlns:wsse="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"   
xmlns:wssu="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-utility-1.0.xsd"   
xmlns:wst="http://docs.oasis-open.org/ws-sx/ws-trust/200512"  
xmlns:wsc="http://schemas.xmlsoap.org/ws/2005/02/sc"  
xmlns:wsp="http://schemas.xmlsoap.org/ws/2004/09/policy">  
<wst:TokenType>http://schemas.xmlsoap.org/ws/2005/02/sc/sct</wst:TokenType>  
<wst:RequestedSecurityToken>   
<wsc:SecurityContextToken>   
<wssu:Identifier> http://fabrikam123.com/SCTi  
</wssu:Identifier>   
</wsc:SecurityContextToken>   
</wst:RequestedSecurityToken>   
<wsp:AppliesTo> http://fabrikam123.com/CCi </wsp:AppliesTo>  
<wst:RequestedAttachedReference>   
<wsse:SecurityTokenReference >   
<wsse:Reference  
  ValueType="http://schemas.xmlsoap.org/ws/2005/02/sc/sct"  
  URI="http://fabrikam123.com/SCTi"/>  
</wsse:SecurityTokenReference>   
</wst:RequestedAttachedReference>   
<wst:RequestedUnattachedReference>   
<wsse:SecurityTokenReference>   
<wsse:Reference  
 ValueType="http://schemas.xmlsoap.org/ws/2005/02/sc/sct"  
 URI="http://fabrikam123.com/SCTi"/>  
</wsse:SecurityTokenReference>   
</wst:RequestedUnattachedReference>   
<wst:RequestedProofToken>   
<wst:BinarySecret  
  Type="http://docs.oasis-open.org/ws-sx/ws-trust/200512/SymmetricKey">  
  <!-- base64 encoded value -->   
</wst:BinarySecret>   
</wst:RequestedProofToken>   
<wst:Lifetime>   
<wssu:Created>2005-10-24T20:19:26.526Z</wssu:Created>  
<wssu:Expires>2005-10-25T06:24:26.526Z</wssu:Expires>  
</wst:Lifetime>   
<wst:KeySize>256</wst:KeySize>   
</wst:RequestSecurityTokenResponse>   
</t:IssuedTokens>   
<o:Security xmlns:o="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd">   
<u:Timestamp u:Id="_0">   
<u:Created>2005-12-15T23:36:12.015Z</u:Created>   
<u:Expires>2005-12-15T23:41:12.015Z</u:Expires>   
</u:Timestamp>   
</o:Security>   
</s:Header>   
<s:Body>   
<wscoor:CreateCoordinationContextResponse>   
<wscoor:CoordinationContext>   
<wscoor:Identifier> http://fabrikam123.com/CCi  
</wscoor:Identifier>   
<wscoor:Expires>...</wscoor:Expires>  
<wscoor:CoordinationType>...</wscoor:CoordinationType>  
<wscoor:RegistrationService>   
<a:Address>https://...</a:Address>  
<a:ReferenceParameters> ...  
</a:ReferenceParameters>  
</wscoor:RegistrationService>   
</wscoor:CoordinationContext>   
</wscoor:CreateCoordinationContextResponse>   
</s:Body>   
</s:Envelope>  
```  
  
### <a name="registration-messages"></a><span data-ttu-id="5afe7-234">登録メッセージ</span><span class="sxs-lookup"><span data-stu-id="5afe7-234">Registration Messages</span></span>  
 <span data-ttu-id="5afe7-235">次のメッセージは、登録メッセージです。</span><span class="sxs-lookup"><span data-stu-id="5afe7-235">The following messages are registration messages.</span></span>  
  
#### <a name="register-with-wscoor-10"></a><span data-ttu-id="5afe7-236">WSCoor 1.0 での register します。</span><span class="sxs-lookup"><span data-stu-id="5afe7-236">Register with WSCoor 1.0</span></span>  
  
```xml  
<s:Envelope>  
  <s:Header>  
    <a:Action>http://schemas.xmlsoap.org/ws/2004/10/wscoor/Register</a:Action>  
    <a:MessageID>urn:uuid:ed418b86-a75e-4aea-9d4e-a5d0cb5c088e</a:MessageID>  
    <a:ReplyTo>  
      <a:Address>https://...</a:Address>        
    </a:ReplyTo>  
    <a:To>https://...</a:To>  
    <wsse:Security   
      s:mustUnderstand="1"   
      xmlns:wsse="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"  
      xmlns:wssu="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-utility-1.0.xsd">  
      <wssu:Timestamp wssu:Id="_0" >  
        <wssu:Created>2005-12-15T23:36:13.827Z</wssu:Created>  
        <wssu:Expires>2005-12-15T23:41:13.827Z</wssu:Expires>  
      </wssu:Timestamp>  
      <wsc:SecurityContextToken>  
      <wssu:Identifier>  
          http://fabrikam123.com/SCTi  
      </wssu:Identifier>  
      </wsc:SecurityContextToken>  
      <!-- supporting signature over the timestamp -->  
      <wsse:Signature xmlns:ds="http://www.w3.org/2000/09/xmldsig#">  
        <ds:SignedInfo>  
          <ds:CanonicalizationMethod Algorithm="http://www.w3.org/2001/10/xml-exc-c14n#"/>  
          <ds:SignatureMethod Algorithm="http://www.w3.org/2000/09/xmldsig#hmac-sha1"/>  
          <ds:Reference URI="#_0">  
            <ds:Transforms>  
              <ds:Transform Algorithm="http://www.w3.org/2001/10/xml-exc-c14n#"/>  
            </ds:Transforms>  
            <ds:DigestMethod Algorithm="http://www.w3.org/2000/09/xmldsig#sha1"/>  
            <ds:DigestValue>  
              alRzyhjLgoUOYoh8cx4n75eTcUk=  
            </ds:DigestValue>  
          </ds:Reference>  
        </ds:SignedInfo>  
        <ds:SignatureValue>YZYjnVvSOVasAQqQxaaviTSWtqI=</ds:SignatureValue>  
        <ds:KeyInfo>  
          <wsse:SecurityTokenReference  
            xmlns:wsse="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd">  
            <wsse:Reference   
              URI="http://fabrikam123.com/SCTi"/>  
          </wsse:SecurityTokenReference>  
        </ds:KeyInfo>  
      </wsse:Signature>  
    </wsse:Security>  
  </s:Header>  
  <s:Body xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">  
    <wscoor:Register>  
      <wscoor:ProtocolIdentifier>...</wscoor:ProtocolIdentifier>  
      <wscoor:ParticipantProtocolService>  
        <a:Address>https://... </a:Address>  
      </wscoor:ParticipantProtocolService>  
    </wscoor:Register>  
  </s:Body>  
</s:Envelope>  
```  
  
#### <a name="register-with-wscoor-11"></a><span data-ttu-id="5afe7-237">WSCoor 1.1 での Register</span><span class="sxs-lookup"><span data-stu-id="5afe7-237">Register with WSCoor 1.1</span></span>  
  
```xml  
<s:Envelope>  
<s:Header>   
<a:Action>http://docs.oasis-open.org/ws-tx/wscoor/2006/06/Register</a:Action>   
<a:MessageID>urn:uuid:ed418b86-a75e-4aea-9d4e-a5d0cb5c088e</a:MessageID>  
<a:ReplyTo>   
<a:Address>https://...</a:Address>   
</a:ReplyTo>  
<a:To>https://...</a:To>   
<wsse:Security   
s:mustUnderstand="1"   
xmlns:wsse="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"   
xmlns:wssu="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-utility-1.0.xsd">  
<wssu:Timestamp wssu:Id="_0" >   
<wssu:Created>2005-12-15T23:36:13.827Z</wssu:Created>  
<wssu:Expires>2005-12-15T23:41:13.827Z</wssu:Expires>  
</wssu:Timestamp>   
<wsc:SecurityContextToken>   
<wssu:Identifier> http://fabrikam123.com/SCTi  
</wssu:Identifier>   
</wsc:SecurityContextToken>   
<!-- supporting signature over the timestamp -->  
<wsse:Signature xmlns:ds="http://www.w3.org/2000/09/xmldsig#">  
<ds:SignedInfo>   
<ds:CanonicalizationMethod Algorithm="http://www.w3.org/2001/10/xml-exc-c14n#"/>   
<ds:SignatureMethod Algorithm="http://www.w3.org/2000/09/xmldsig#hmac-sha1"/>   
<ds:Reference URI="#_0">   
<ds:Transforms>   
<ds:Transform Algorithm="http://www.w3.org/2001/10/xml-exc-c14n#"/>   
</ds:Transforms>   
<ds:DigestMethod  
Algorithm="http://www.w3.org/2000/09/xmldsig#sha1"/>   
<ds:DigestValue> alRzyhjLgoUOYoh8cx4n75eTcUk=  
</ds:DigestValue>   
</ds:Reference>   
</ds:SignedInfo>  
<ds:SignatureValue>YZYjnVvSOVasAQqQxaaviTSWtqI=  
</ds:SignatureValue>  
<ds:KeyInfo>   
<wsse:SecurityTokenReference xmlns:wsse="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd">  
  <wsse:Reference URI="http://fabrikam123.com/SCTi"/>  
</wsse:SecurityTokenReference>   
</ds:KeyInfo>   
</wsse:Signature>   
</wsse:Security>   
</s:Header>   
<s:Body xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">   
<wscoor:Register>   
<wscoor:ProtocolIdentifier>...</wscoor:ProtocolIdentifier>  
<wscoor:ParticipantProtocolService>   
<a:Address>https://... </a:Address>  
</wscoor:ParticipantProtocolService>   
</wscoor:Register>   
</s:Body>   
</s:Envelope>  
```  
  
#### <a name="register-response-with-wscoor-10"></a><span data-ttu-id="5afe7-238">WSCoor 1.0 での register Response</span><span class="sxs-lookup"><span data-stu-id="5afe7-238">Register Response with WSCoor 1.0</span></span>  
  
```xml  
<s:Envelope>  
  <s:Header>  
    <a:Action>  
      http://schemas.xmlsoap.org/ws/2004/10/wscoor/RegisterResponse  
    </a:Action>  
    <a:MessageID>urn:uuid:ed418b86-a75e-4aea-9d4e-a5d0cb5c088d</a:MessageID>  
    <a:RelatesTo>  
      urn:uuid:ed418b86-a75e-4aea-9d4e-a5d0cb5c088e        
    </a:RelatesTo>  
    <a:To>https://...</a:To>  
    <wsse:Security   
      s:mustUnderstand="1"   
      xmlns:wsse="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"  
      xmlns:wssu="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-utility-1.0.xsd">  
      <wssu:Timestamp>  
        <wssu:Created>2005-12-15T23:36:13.827Z</wssu:Created>  
        <wssu:Expires>2005-12-15T23:41:13.827Z</wssu:Expires>  
      </wssu:Timestamp>  
    </wsse:Security>  
  </s:Header>  
  <s:Body xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">  
    <wscoor:RegisterResponse>  
      <wscoor:CoordinatorProtocolService>  
        <a:Address>https://...</a:Address>  
        <a:ReferenceParameters>  
          ...  
        </a:ReferenceParameters>  
      </wscoor:CoordinatorProtocolService>  
    </wscoor:RegisterResponse>  
  </s:Body>  
</s:Envelope>  
```  
  
#### <a name="register-response-with-wscoor-11"></a><span data-ttu-id="5afe7-239">WSCoor 1.1 での Register Response</span><span class="sxs-lookup"><span data-stu-id="5afe7-239">Register Response with WSCoor 1.1</span></span>  
  
```xml  
<s:Envelope>  
<s:Header>   
<a:Action> http://docs.oasis-open.org/ws-tx/wscoor/2006/06/RegisterResponse  
</a:Action>   
<a:MessageID>urn:uuid:ed418b86-a75e-4aea-9d4e-a5d0cb5c088d</a:MessageID>  
<a:RelatesTo> urn:uuid:ed418b86-a75e-4aea-9d4e-a5d0cb5c088e </a:RelatesTo>  
<a:To>https://...</a:To>   
<wsse:Security   
s:mustUnderstand="1"   
xmlns:wsse="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"   
xmlns:wssu="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-utility-1.0.xsd">   
<wssu:Timestamp>   
<wssu:Created>2005-12-15T23:36:13.827Z</wssu:Created>  
<wssu:Expires>2005-12-15T23:41:13.827Z</wssu:Expires>  
</wssu:Timestamp>   
</wsse:Security>   
</s:Header>   
<s:Body xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">   
<wscoor:RegisterResponse>   
<wscoor:CoordinatorProtocolService>  
<a:Address>https://...</a:Address>  
<a:ReferenceParameters> ... </a:ReferenceParameters>  
</wscoor:CoordinatorProtocolService>   
</wscoor:RegisterResponse>   
</s:Body>   
</s:Envelope>  
```  
  
### <a name="two-phase-commit-protocol-messages"></a><span data-ttu-id="5afe7-240">2 フェーズ コミット プロトコル メッセージ</span><span class="sxs-lookup"><span data-stu-id="5afe7-240">Two Phase Commit Protocol Messages</span></span>  
 <span data-ttu-id="5afe7-241">次のメッセージは、2 フェーズ コミット (2PC) プロトコルに関連しています。</span><span class="sxs-lookup"><span data-stu-id="5afe7-241">The following message relates to the two-phase commit (2PC) protocol.</span></span>  
  
#### <a name="commit-with-wsat-10"></a><span data-ttu-id="5afe7-242">WSAT 1.0 とコミットします。</span><span class="sxs-lookup"><span data-stu-id="5afe7-242">Commit with WSAT 1.0</span></span>  
  
```xml  
<s:Envelope>  
  <s:Header>  
    <a:Action>http://.../ws/2004/10/wsat/Commit</a:Action>  
    <a:To>https://...</a:To>  
    <wsse:Security   
      s:mustUnderstand="1"   
      xmlns:wsse="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"  
      xmlns:wssu="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-utility-1.0.xsd">  
      <wssu:Timestamp wssu:Id="_0" >  
        <wssu:Created>2005-12-15T23:36:13.827Z</wssu:Created>  
        <wssu:Expires>2005-12-15T23:41:13.827Z</wssu:Expires>  
      </wssu:Timestamp>  
   </wsse:Security>  
  </s:Header>  
  <s:Body xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">  
    <wsat:Commit />  
  </s:Body>  
</s:Envelope>  
```  
  
#### <a name="commit-with-wsat-11"></a><span data-ttu-id="5afe7-243">WSAT 1.1 での Commit</span><span class="sxs-lookup"><span data-stu-id="5afe7-243">Commit with WSAT 1.1</span></span>  
  
```xml  
<s:Envelope>  
<s:Header>   
<a:Action>http://docs.oasis-open.org/ws-tx/wsat/2006/06</a:Action>  
<a:To>https://...</a:To>   
<wsse:Security   
s:mustUnderstand="1"   
xmlns:wsse="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"   
xmlns:wssu="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-utility-1.0.xsd">   
<wssu:Timestamp wssu:Id="_0" >   
<wssu:Created>2005-12-15T23:36:13.827Z</wssu:Created>  
<wssu:Expires>2005-12-15T23:41:13.827Z</wssu:Expires>  
</wssu:Timestamp>   
</wsse:Security>   
</s:Header>   
<s:Body xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">   
<wsat:Commit />   
</s:Body>   
</s:Envelope>  
```  
  
### <a name="application-messages"></a><span data-ttu-id="5afe7-244">アプリケーション メッセージ</span><span class="sxs-lookup"><span data-stu-id="5afe7-244">Application Messages</span></span>  
 <span data-ttu-id="5afe7-245">次のメッセージは、アプリケーション メッセージです。</span><span class="sxs-lookup"><span data-stu-id="5afe7-245">The following messages are application messages.</span></span>  
  
#### <a name="application-message-request"></a><span data-ttu-id="5afe7-246">アプリケーション メッセージ (要求)</span><span class="sxs-lookup"><span data-stu-id="5afe7-246">Application message-Request</span></span>  
  
```xml  
<s:Envelope>  
  <s:Header>  
<!-- Addressing headers, all signed-->  
    <wsse:Security s:mustUnderstand="1">  
      <wssu:Timestamp wssu:Id="timestamp">   
        <wssu:Created>2005-10-25T06:29:18.703Z</wssu:Created>  
        <wssu:Expires>2005-10-25T06:34:18.703Z</wssu:Expires>  
      </wssu:Timestamp>  
      <wsse:BinarySecurityToken   
          wssu:Id="IA_Certificate"   
          ValueType="...#X509v3"   
          EncodingType="...#Base64Binary">  
        <!-- IA certificate -->  
      </wsse:BinarySecurityToken>  
      <e:EncryptedKey Id="encrypted_key">  
            <!-- ephemeral key encrypted for PA certificate -->    
        <e:ReferenceList xmlns:e="http://www.w3.org/2001/04/xmlenc#">  
          <e:DataReference URI="#encrypted_body"/>  
          <e:DataReference URI="#encrypted_CCi"/>  
          <e:DataReference URI="#encrypted_issuedtokens"/>  
        </e:ReferenceList>  
      </e:EncryptedKey>  
      <Signature xmlns="http://www.w3.org/2000/09/xmldsig#">  
        <!-- signature over Addressing headers, Timestamp, and Body -->  
      </Signature>  
    </wsse:Security>  
    <wsse11:EncryptedHeader >  
     <!-- encrypted wscoor:CoordinationContext header containing CCi -->  
    </wsse11:EncryptedHeader>  
    <wsse11:EncryptedHeader   
      <!-- encrypted wst:IssuedTokens header containing SCTi -->  
      <!-- wst:IssuedTokens header is taken verbatim from message #2 above, omitted for brevity -->  
    </wsse11:EncryptedHeader>  
  </s:Header>  
  <s:Body wssu:Id="body">  
    <!-- encrypted content of the Body element of the application message -->      
    <e:EncryptedData Id="encrypted_body"   
           Type="http://www.w3.org/2001/04/xmlenc#Content"   
           xmlns:e="http://www.w3.org/2001/04/xmlenc#">  
...  
    </e:EncryptedData>  
  </s:Body>  
</s:Envelope>  
```
