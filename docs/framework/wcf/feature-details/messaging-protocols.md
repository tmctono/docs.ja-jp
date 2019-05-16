---
title: メッセージング プロトコル
ms.date: 03/30/2017
ms.assetid: 5b20bca7-87b3-4c8f-811b-f215b5987104
ms.openlocfilehash: 70972f6a211d60d9fd330277040428ef783e9668
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2019
ms.locfileid: "65631523"
---
# <a name="messaging-protocols"></a><span data-ttu-id="a2e76-102">メッセージング プロトコル</span><span class="sxs-lookup"><span data-stu-id="a2e76-102">Messaging Protocols</span></span>

<span data-ttu-id="a2e76-103">Windows Communication Foundation (WCF) チャネル スタックには、内部メッセージ表現をワイヤ形式に変換し、特定のトランスポートを使用して送信するエンコーディングとトランスポート チャネルが採用しています。</span><span class="sxs-lookup"><span data-stu-id="a2e76-103">The Windows Communication Foundation (WCF) channel stack employs encoding and transport channels to transform internal message representation into its wire format and send it by using a particular transport.</span></span> <span data-ttu-id="a2e76-104">Web サービスの相互運用性を確保するために、最も一般的に使用されるトランスポートは HTTP です。また、Web サービスが使用する最も一般的なエンコーディングは、XML ベースの SOAP 1.1、SOAP 1.2、および MTOM (Message Transmission Optimization Mechanism) です。</span><span class="sxs-lookup"><span data-stu-id="a2e76-104">The most common transport used for Web services interoperability is HTTP, and the most common encodings used by Web services are XML-based SOAP 1.1, SOAP 1.2, and Message Transmission Optimization Mechanism (MTOM).</span></span>

<span data-ttu-id="a2e76-105">このトピックの内容で採用されている次のプロトコルの実装の詳細を WCF<xref:System.ServiceModel.Channels.HttpTransportBindingElement>します。</span><span class="sxs-lookup"><span data-stu-id="a2e76-105">This topic covers WCF implementation details for the following protocols employed by <xref:System.ServiceModel.Channels.HttpTransportBindingElement>.</span></span>

<span data-ttu-id="a2e76-106">仕様/ドキュメント:</span><span class="sxs-lookup"><span data-stu-id="a2e76-106">Specification/document:</span></span>

- [<span data-ttu-id="a2e76-107">HTTP 1.1</span><span class="sxs-lookup"><span data-stu-id="a2e76-107">HTTP 1.1</span></span>](https://www.ietf.org/rfc/rfc2616.txt)
- <span data-ttu-id="a2e76-108">[SOAP 1.1 HTTP バインディング](https://www.w3.org/TR/2000/NOTE-SOAP-20000508)セクション 7</span><span class="sxs-lookup"><span data-stu-id="a2e76-108">[SOAP 1.1 HTTP Binding](https://www.w3.org/TR/2000/NOTE-SOAP-20000508), Section 7</span></span>
- <span data-ttu-id="a2e76-109">[SOAP 1.2 HTTP バインディング](https://www.w3.org/TR/soap12-part2)セクション 7</span><span class="sxs-lookup"><span data-stu-id="a2e76-109">[SOAP 1.2 HTTP Binding](https://www.w3.org/TR/soap12-part2) Section 7</span></span>

<span data-ttu-id="a2e76-110">このトピックで説明する以下のプロトコルの WCF 実装の詳細<xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>と<xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement>を使用します。</span><span class="sxs-lookup"><span data-stu-id="a2e76-110">This topic covers WCF implementation details for the following protocols  that <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement> and <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement> employ.</span></span>

<span data-ttu-id="a2e76-111">仕様/ドキュメント:</span><span class="sxs-lookup"><span data-stu-id="a2e76-111">Specification/Document:</span></span>

- [<span data-ttu-id="a2e76-112">XML</span><span class="sxs-lookup"><span data-stu-id="a2e76-112">XML</span></span>](https://www.w3.org/TR/REC-xml)
- [<span data-ttu-id="a2e76-113">SOAP 1.1</span><span class="sxs-lookup"><span data-stu-id="a2e76-113">SOAP 1.1</span></span>](https://www.w3.org/TR/2000/NOTE-SOAP-20000508/)
- [<span data-ttu-id="a2e76-114">SOAP 1.2 コア</span><span class="sxs-lookup"><span data-stu-id="a2e76-114">SOAP 1.2 Core</span></span>](https://www.w3.org/TR/soap12-part1/)
- [<span data-ttu-id="a2e76-115">Ws-addressing 2004/08</span><span class="sxs-lookup"><span data-stu-id="a2e76-115">WS-Addressing 2004/08</span></span>](https://www.w3.org/Submission/2004/SUBM-ws-addressing-20040810/)
- [<span data-ttu-id="a2e76-116">W3C Web Services Addressing 1.0 - コア</span><span class="sxs-lookup"><span data-stu-id="a2e76-116">W3C Web Services Addressing 1.0 - Core</span></span>](https://www.w3.org/TR/2006/REC-ws-addr-core-20060509)
- [<span data-ttu-id="a2e76-117">W3C Web Services Addressing 1.0 - SOAP バインディング</span><span class="sxs-lookup"><span data-stu-id="a2e76-117">W3C Web Services Addressing 1.0 - SOAP Binding</span></span>](https://www.w3.org/TR/2006/REC-ws-addr-soap-20060509)
- [<span data-ttu-id="a2e76-118">W3C Web Services Addressing 1.0 - WSDL バインディング</span><span class="sxs-lookup"><span data-stu-id="a2e76-118">W3C Web Services Addressing 1.0 - WSDL Binding</span></span>](https://www.w3.org/TR/2006/CR-ws-addr-wsdl-20060529/)
- [<span data-ttu-id="a2e76-119">W3C Web Services Addressing 1.0 - メタデータ</span><span class="sxs-lookup"><span data-stu-id="a2e76-119">W3C Web Services Addressing 1.0 - Metadata</span></span>](https://www.w3.org/TR/ws-addr-metadata/)
- [<span data-ttu-id="a2e76-120">WSDL SOAP1.1 バインディング</span><span class="sxs-lookup"><span data-stu-id="a2e76-120">WSDL SOAP1.1 Binding</span></span>](https://www.w3.org/TR/wsdl/)
- [<span data-ttu-id="a2e76-121">WSDL SOAP1.2 バインディング</span><span class="sxs-lookup"><span data-stu-id="a2e76-121">WSDL SOAP1.2 Binding</span></span>](https://www.w3.org/Submission/wsdl11soap12/)

<span data-ttu-id="a2e76-122">このトピックで説明する以下のプロトコルの WCF 実装の詳細<xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement>を採用しています。</span><span class="sxs-lookup"><span data-stu-id="a2e76-122">This topic covers WCF implementation details for the following protocols that <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement> employs.</span></span>

<span data-ttu-id="a2e76-123">仕様/ドキュメント:</span><span class="sxs-lookup"><span data-stu-id="a2e76-123">Specification/document:</span></span>

- [<span data-ttu-id="a2e76-124">XOP</span><span class="sxs-lookup"><span data-stu-id="a2e76-124">XOP</span></span>](https://www.w3.org/TR/xop10/)
- [<span data-ttu-id="a2e76-125">MTOM および SOAP 1.2 バインディング</span><span class="sxs-lookup"><span data-stu-id="a2e76-125">MTOM + SOAP 1.2 Binding</span></span>](https://www.w3.org/TR/soap12-mtom/)
- [<span data-ttu-id="a2e76-126">MTOM SOAP 1.1 バインディング</span><span class="sxs-lookup"><span data-stu-id="a2e76-126">MTOM SOAP 1.1 Binding</span></span>](https://www.w3.org/Submission/soap11mtom10/)
- [<span data-ttu-id="a2e76-127">MTOM Ws-policy アサーション</span><span class="sxs-lookup"><span data-stu-id="a2e76-127">MTOM WS-Policy Assertion</span></span>](https://www.w3.org/Submission/2006/SUBM-WS-MTOMPolicy-20061101/)

<span data-ttu-id="a2e76-128">このトピックでは、次の XML 名前空間と関連付けられたプレフィックスが使用されます。</span><span class="sxs-lookup"><span data-stu-id="a2e76-128">The following XML namespaces and associated prefixes are used throughout this topic:</span></span>

| <span data-ttu-id="a2e76-129">プレフィックス</span><span class="sxs-lookup"><span data-stu-id="a2e76-129">Prefix</span></span> | <span data-ttu-id="a2e76-130">名前空間 URI (Uniform Resource Identifier)</span><span class="sxs-lookup"><span data-stu-id="a2e76-130">Namespace Uniform Resource Identifier (URI)</span></span> |
|------------|---------------------------------------------------|
| <span data-ttu-id="a2e76-131">s11</span><span class="sxs-lookup"><span data-stu-id="a2e76-131">s11</span></span> | `http://schemas.xmlsoap.org/soap/envelope` |
| <span data-ttu-id="a2e76-132">s12</span><span class="sxs-lookup"><span data-stu-id="a2e76-132">s12</span></span> |`http://www.w3.org/2003/05/soap-envelope` |
| <span data-ttu-id="a2e76-133">wsa</span><span class="sxs-lookup"><span data-stu-id="a2e76-133">wsa</span></span> |`http://www.w3.org/2004/08/addressing` |
| <span data-ttu-id="a2e76-134">wsam</span><span class="sxs-lookup"><span data-stu-id="a2e76-134">wsam</span></span> |`http://www.w3.org/2007/05/addressing/metadata` |
| <span data-ttu-id="a2e76-135">wsap</span><span class="sxs-lookup"><span data-stu-id="a2e76-135">wsap</span></span> |`http://schemas.xmlsoap.org/ws/2004/09/policy/addressing` |
| <span data-ttu-id="a2e76-136">wsa10</span><span class="sxs-lookup"><span data-stu-id="a2e76-136">wsa10</span></span> |`http://www.w3.org/2005/08/addressing` |
| <span data-ttu-id="a2e76-137">wsaw10</span><span class="sxs-lookup"><span data-stu-id="a2e76-137">wsaw10</span></span> |`http://www.w3.org/2006/05/addressing/wsdl` |
| <span data-ttu-id="a2e76-138">xop</span><span class="sxs-lookup"><span data-stu-id="a2e76-138">xop</span></span> |`http://www.w3.org/2004/08/xop/include` |
| <span data-ttu-id="a2e76-139">xmime</span><span class="sxs-lookup"><span data-stu-id="a2e76-139">xmime</span></span> |`http://www.w3.org/2004/06/xmlmime`<br /><br /> `http://www.w3.org/2005/05/xmlmime` |
| <span data-ttu-id="a2e76-140">dp</span><span class="sxs-lookup"><span data-stu-id="a2e76-140">dp</span></span> |`http://schemas.microsoft.com/net/2006/06/duplex` |

## <a name="soap-11-and-soap-12"></a><span data-ttu-id="a2e76-141">SOAP 1.1 と SOAP 1.2</span><span class="sxs-lookup"><span data-stu-id="a2e76-141">SOAP 1.1 and SOAP 1.2</span></span>

### <a name="envelope-and-processing-model"></a><span data-ttu-id="a2e76-142">エンベロープと処理モデル</span><span class="sxs-lookup"><span data-stu-id="a2e76-142">Envelope and Processing Model</span></span>
<span data-ttu-id="a2e76-143">WCF では、Basic Profile 1.1 (BP11) および Basic Profile 1.0 (SSBP10) に従って SOAP 1.1 エンベロープの処理を実装します。</span><span class="sxs-lookup"><span data-stu-id="a2e76-143">WCF implements SOAP 1.1 envelope processing following Basic Profile 1.1 (BP11) and Basic Profile 1.0 (SSBP10).</span></span> <span data-ttu-id="a2e76-144">SOAP 1.2 エンベロープの処理は、SOAP12-Part1 に従って実装されます。</span><span class="sxs-lookup"><span data-stu-id="a2e76-144">SOAP 1.2 Envelope processing is implemented following SOAP12-Part1.</span></span>

<span data-ttu-id="a2e76-145">このセクションでは、BP11 および SOAP12 パート 1 に関して、WCF によって実行される特定の実装の選択肢について説明します。</span><span class="sxs-lookup"><span data-stu-id="a2e76-145">This section explains certain implementation choices taken by WCF with regard to BP11 and SOAP12-Part1.</span></span>

#### <a name="mandatory-header-processing"></a><span data-ttu-id="a2e76-146">必須のヘッダー処理</span><span class="sxs-lookup"><span data-stu-id="a2e76-146">Mandatory Header Processing</span></span>
<span data-ttu-id="a2e76-147">マークされたヘッダーの処理の規則に従います WCF`mustUnderstand`次のバリエーションと、SOAP 1.1 と SOAP 1.2 仕様で説明されています。</span><span class="sxs-lookup"><span data-stu-id="a2e76-147">WCF follows rules for processing headers marked `mustUnderstand` described in the SOAP 1.1 and SOAP 1.2 specifications, with the following variations.</span></span>

<span data-ttu-id="a2e76-148">WCF チャネル スタックが入力したメッセージは、たとえば、関連付けられたバインド要素で構成されている個々 のチャネル、テキスト メッセージ エンコーディング、セキュリティ、信頼性の高いメッセージング、およびトランザクションで処理されます。</span><span class="sxs-lookup"><span data-stu-id="a2e76-148">A message that enters the WCF channel stack is processed by individual channels configured by associated binding elements, for example, Text Message Encoding, Security, Reliable Messaging, and Transactions.</span></span> <span data-ttu-id="a2e76-149">各チャネルは、関連付けられた名前空間からヘッダーを認識し、認識済みとしてマークします。</span><span class="sxs-lookup"><span data-stu-id="a2e76-149">Each channel recognizes headers from the associated namespace and marks them as understood.</span></span> <span data-ttu-id="a2e76-150">メッセージがディスパッチャーに入ると、操作フォーマッタは対応するメッセージ コントラクトと操作コントラクトで想定されたヘッダーを読み取り、認識済みとしてマークします。</span><span class="sxs-lookup"><span data-stu-id="a2e76-150">Once a message enters the dispatcher, the operation formatter reads headers expected by the corresponding message/operation contract and marks them understood.</span></span> <span data-ttu-id="a2e76-151">次に、ディスパッチャーは、`mustUnderstand` としてマークされているにもかかわらず、認識されていないヘッダーが残っていないかどうかを検証し、例外をスローします。</span><span class="sxs-lookup"><span data-stu-id="a2e76-151">Then the dispatcher verifies whether any remaining headers are not understood but marked as `mustUnderstand` and throws an exception.</span></span> <span data-ttu-id="a2e76-152">受信者を対象とする `mustUnderstand` ヘッダーが含まれたメッセージが、受信者のアプリケーション コードで処理されることはありません。</span><span class="sxs-lookup"><span data-stu-id="a2e76-152">Messages that contain `mustUnderstand` headers that are targeted at the recipient are not processed by recipient application code.</span></span>

<span data-ttu-id="a2e76-153">このようなレイヤー化された処理により、SOAP ノードのインフラストラクチャ レイヤーとアプリケーション レイヤーを次のように分離することが可能になります。</span><span class="sxs-lookup"><span data-stu-id="a2e76-153">Such layered processing allows for separation between infrastructure layers and application layers of the SOAP node:</span></span>

- <span data-ttu-id="a2e76-154">B1111:メッセージが WCF インフラストラクチャのチャネル スタックによって処理された後、アプリケーションによって処理される前に、認識されないヘッダーが検出されました</span><span class="sxs-lookup"><span data-stu-id="a2e76-154">B1111: Headers that are not understood are detected after the message is processed by the WCF infrastructure channel stack, but before it is processed by application</span></span>

     <span data-ttu-id="a2e76-155">`mustUnderstand` ヘッダーの値は、SOAP 1.1 と SOAP 1.2 で異なります。</span><span class="sxs-lookup"><span data-stu-id="a2e76-155">The `mustUnderstand` header value differs between SOAP 1.1 and SOAP 1.2.</span></span> <span data-ttu-id="a2e76-156">Basic Profile 1.1 では、SOAP 1.1 メッセージの `mustUnderstand` の値が 0 または 1 である必要があります。</span><span class="sxs-lookup"><span data-stu-id="a2e76-156">Basic Profile 1.1 requires that the `mustUnderstand` value be 0 or 1 for SOAP 1.1 messages.</span></span> <span data-ttu-id="a2e76-157">SOAP 1.2 では、値として 0、1、`false`、および `true` を使用できますが、`xs:boolean` 値の正規表現 (`false`、`true`) を出力することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="a2e76-157">SOAP 1.2 allows 0, 1, `false`, and `true` as values, but recommends emitting a canonical representation of `xs:boolean` values (`false`, `true`).</span></span>

- <span data-ttu-id="a2e76-158">B1112:WCF が出力`mustUnderstand`SOAP エンベロープの値を 0 と 1 を SOAP 1.1 と SOAP 1.2 の両方のバージョン。</span><span class="sxs-lookup"><span data-stu-id="a2e76-158">B1112: WCF emits `mustUnderstand` values 0 and 1 for both SOAP 1.1 and SOAP 1.2 versions of the SOAP envelope.</span></span> <span data-ttu-id="a2e76-159">WCF の全体の値の空白を受け入れる`xs:boolean`の`mustUnderstand`ヘッダー (0, 1, `false`、 `true`)</span><span class="sxs-lookup"><span data-stu-id="a2e76-159">WCF accepts the entire value space of `xs:boolean` for the `mustUnderstand` header (0, 1, `false`, `true`)</span></span>

#### <a name="soap-faults"></a><span data-ttu-id="a2e76-160">SOAP エラー</span><span class="sxs-lookup"><span data-stu-id="a2e76-160">SOAP Faults</span></span>
<span data-ttu-id="a2e76-161">次に特定の WCF SOAP エラー実装の一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="a2e76-161">The following is a list of WCF-specific SOAP fault implementations.</span></span>

- <span data-ttu-id="a2e76-162">B2121:WCF は、次の SOAP 1.1 エラー コードを返します: `s11:mustUnderstand`、 `s11:Client`、および`s11:Server`します。</span><span class="sxs-lookup"><span data-stu-id="a2e76-162">B2121: WCF returns the following SOAP 1.1 Fault Codes: `s11:mustUnderstand`, `s11:Client`, and `s11:Server`.</span></span>

- <span data-ttu-id="a2e76-163">B2122:WCF は、次の SOAP 1.2 エラー コードを返します: `s12:MustUnderstand`、 `s12:Sender`、および`s12:Receiver`します。</span><span class="sxs-lookup"><span data-stu-id="a2e76-163">B2122: WCF returns the following SOAP 1.2 Fault Codes: `s12:MustUnderstand`, `s12:Sender`, and `s12:Receiver`.</span></span>

### <a name="http-binding"></a><span data-ttu-id="a2e76-164">HTTP バインディング</span><span class="sxs-lookup"><span data-stu-id="a2e76-164">HTTP Binding</span></span>

#### <a name="soap-11-http-binding"></a><span data-ttu-id="a2e76-165">SOAP 1.1 HTTP バインディング</span><span class="sxs-lookup"><span data-stu-id="a2e76-165">SOAP 1.1 HTTP Binding</span></span>
<span data-ttu-id="a2e76-166">WCF は、Basic Profile 1.1 仕様の説明を次のセクション 3.4 に従って、SOAP1.1 HTTP バインディングを実装します。</span><span class="sxs-lookup"><span data-stu-id="a2e76-166">WCF implements SOAP1.1 HTTP binding following the Basic Profile 1.1 specification section 3.4 with the following clarifications:</span></span>

- <span data-ttu-id="a2e76-167">B2211:WCF サービスは、HTTP POST 要求のリダイレクトを実装していません。</span><span class="sxs-lookup"><span data-stu-id="a2e76-167">B2211: WCF service does not implement redirection of HTTP POST requests.</span></span>

- <span data-ttu-id="a2e76-168">B2212:WCF クライアントは、3.4.8 に従って HTTP クッキーをサポートします。</span><span class="sxs-lookup"><span data-stu-id="a2e76-168">B2212: WCF clients support HTTP Cookies in accordance with 3.4.8.</span></span>

#### <a name="soap-12-http-binding"></a><span data-ttu-id="a2e76-169">SOAP 1.2 HTTP バインディング</span><span class="sxs-lookup"><span data-stu-id="a2e76-169">SOAP 1.2 HTTP Binding</span></span>
<span data-ttu-id="a2e76-170">WCF は、SOAP 1.2-part 2 (SOAP12Part2) 仕様次の説明」の説明に従って、SOAP 1.2 HTTP バインディングを実装します。</span><span class="sxs-lookup"><span data-stu-id="a2e76-170">WCF implements SOAP 1.2 HTTP binding as described in the SOAP 1.2-part 2 (SOAP12Part2) specification with the following clarifications.</span></span>

<span data-ttu-id="a2e76-171">SOAP 1.2 では、`application/soap+xml` メディア タイプの省略可能なアクション パラメーターが導入されました。</span><span class="sxs-lookup"><span data-stu-id="a2e76-171">SOAP 1.2 introduced an optional action parameter for the `application/soap+xml` media type.</span></span> <span data-ttu-id="a2e76-172">このパラメーターは、WS-Addressing を使用していない場合に、SOAP メッセージの本文を解析する必要なく、メッセージ ディスパッチを最適化する際に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="a2e76-172">This parameter is useful to optimize message dispatch without requiring that the body of the SOAP message be parsed when WS-Addressing is not used.</span></span>

- <span data-ttu-id="a2e76-173">R2221:`application/soap+xml` SOAP 1.2 要求に存在する場合、アクション パラメーターに一致する必要があります、`soapAction`属性を`wsoap12:operation`対応する WSDL バインディング内の要素。</span><span class="sxs-lookup"><span data-stu-id="a2e76-173">R2221: The `application/soap+xml` action parameter, when present on a SOAP 1.2 request, must match the `soapAction` attribute on the `wsoap12:operation` element inside the corresponding WSDL binding.</span></span>

- <span data-ttu-id="a2e76-174">R2222:`application/soap+xml`が SOAP 1.2 メッセージに存在する場合、アクション パラメーターに一致する必要があります`wsa:Action`Ws-addressing 2004/08 または Ws-addressing 1.0 を使用する場合。</span><span class="sxs-lookup"><span data-stu-id="a2e76-174">R2222: The `application/soap+xml` action parameter, when present on a SOAP 1.2 message, must match `wsa:Action` when WS-Addressing 2004/08 or WS-Addressing 1.0 are used.</span></span>

<span data-ttu-id="a2e76-175">WS-Addressing が無効になっているときに、受信要求にアクション パラメーターが含まれていない場合、メッセージの `Action` は指定されていないものと見なされます。</span><span class="sxs-lookup"><span data-stu-id="a2e76-175">When WS-Addressing is disabled and an incoming request does not contain an action parameter, message `Action` is considered not specified.</span></span>

## <a name="ws-addressing"></a><span data-ttu-id="a2e76-176">WS-Addressing</span><span class="sxs-lookup"><span data-stu-id="a2e76-176">WS-Addressing</span></span>
<span data-ttu-id="a2e76-177">WCF には、3 つのバージョンの Ws-addressing が実装されています。</span><span class="sxs-lookup"><span data-stu-id="a2e76-177">WCF implements 3 versions of WS-Addressing:</span></span>

- <span data-ttu-id="a2e76-178">WS-Addressing 2004/08</span><span class="sxs-lookup"><span data-stu-id="a2e76-178">WS-Addressing 2004/08</span></span>

- <span data-ttu-id="a2e76-179">W3C Web Services Addressing 1.0 コア (ADDR10-CORE) - SOAP バインディング (ADDR10-SOAP)</span><span class="sxs-lookup"><span data-stu-id="a2e76-179">W3C Web Services Addressing 1.0 Core  (ADDR10-CORE) and SOAP Binding (ADDR10-SOAP)</span></span>

- <span data-ttu-id="a2e76-180">WS-Addressing 1.0 - メタデータ</span><span class="sxs-lookup"><span data-stu-id="a2e76-180">WS-Addressing 1.0 - Metadata</span></span>

### <a name="endpoint-references"></a><span data-ttu-id="a2e76-181">エンドポイント参照</span><span class="sxs-lookup"><span data-stu-id="a2e76-181">Endpoint References</span></span>
<span data-ttu-id="a2e76-182">Ws-addressing の WCF 実装するすべてのバージョンでは、エンドポイント参照を使用してエンドポイントを記述します。</span><span class="sxs-lookup"><span data-stu-id="a2e76-182">All versions of WS-Addressing that WCF implements use endpoint references to describe endpoints.</span></span>

#### <a name="endpoint-references-and-ws-addressing-versions"></a><span data-ttu-id="a2e76-183">エンドポイント参照と WS-Addressing のバージョン</span><span class="sxs-lookup"><span data-stu-id="a2e76-183">Endpoint References and WS-Addressing Versions</span></span>
<span data-ttu-id="a2e76-184">WCF は Ws-addressing を使用するためのインフラストラクチャ プロトコルの特定の数を実装して、`EndpointReference`要素と`W3C.WsAddressing.EndpointReferenceType`クラス (WS-ReliableMessaging、Ws-secureconversation、Ws-trust など)。</span><span class="sxs-lookup"><span data-stu-id="a2e76-184">WCF implements a number of the infrastructure protocols that use WS-Addressing and in particular the `EndpointReference` element and `W3C.WsAddressing.EndpointReferenceType` class (for example, WS-ReliableMessaging, WS-SecureConversation, and WS-Trust).</span></span> <span data-ttu-id="a2e76-185">WCF では、どちらのバージョンの Ws-addressing を他のインフラストラクチャ プロトコルの使用をサポートします。</span><span class="sxs-lookup"><span data-stu-id="a2e76-185">WCF supports the use of either version of WS-Addressing with other infrastructure protocols.</span></span> <span data-ttu-id="a2e76-186">WCF エンドポイントは、エンドポイントごとに Ws-addressing の 1 つのバージョンをサポートします。</span><span class="sxs-lookup"><span data-stu-id="a2e76-186">WCF endpoints support one version of WS-Addressing per endpoint.</span></span>

<span data-ttu-id="a2e76-187">R3111 での名前空間、`EndpointReference`要素または WCF エンドポイントと交換されるメッセージで使用される型がこのエンドポイントで実装されている Ws-addressing のバージョンに一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a2e76-187">For R3111, the namespace for the `EndpointReference` element or type used in messages exchanged with a WCF endpoint must match the version of WS-Addressing implemented by this endpoint.</span></span>

<span data-ttu-id="a2e76-188">例では、WCF エンドポイントが WS-ReliableMessaging を実装している場合、`AcksTo`内のようなエンドポイントから返されるヘッダー `CreateSequenceResponse` Ws-addressing のバージョンを使用する、`EncodingBinding`要素は、このエンドポイントを指定します。</span><span class="sxs-lookup"><span data-stu-id="a2e76-188">For example, if a WCF endpoint implements WS-ReliableMessaging, the `AcksTo` header returned by such an endpoint inside `CreateSequenceResponse` uses the WS-Addressing version that the `EncodingBinding` element specifies for this endpoint.</span></span>

#### <a name="endpoint-references-and-metadata"></a><span data-ttu-id="a2e76-189">エンドポイント参照とメタデータ</span><span class="sxs-lookup"><span data-stu-id="a2e76-189">Endpoint References and Metadata</span></span>
<span data-ttu-id="a2e76-190">多くのシナリオでは、指定されたエンドポイントのメタデータまたはメタデータへの参照を伝達する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a2e76-190">A number of scenarios require communicating metadata or a reference to metadata for a given endpoint.</span></span>

<span data-ttu-id="a2e76-191">B3121:WCF は、Ws-metadataexchange (MEX) 仕様を値渡しまたは参照によって、エンドポイント参照のメタデータを含めるセクション 6 で説明されているメカニズムを使用します。</span><span class="sxs-lookup"><span data-stu-id="a2e76-191">B3121: WCF employs mechanisms described in the WS-MetadataExchange (MEX) specification Section 6 to include metadata for endpoint references by value or by reference.</span></span>

<span data-ttu-id="a2e76-192">WCF サービスであるトークン発行者によって発行された Security Assertions Markup Language (SAML) トークンを使用して認証が必要な場合を考えます `http://sts.fabrikam123.com` です。</span><span class="sxs-lookup"><span data-stu-id="a2e76-192">Consider a scenario where a WCF service requires authentication using a Security Assertions Markup Language (SAML) token issued by the token issuer at `http://sts.fabrikam123.com`.</span></span> <span data-ttu-id="a2e76-193">WCF エンドポイントを使用してこの認証要件を説明する`sp:IssuedToken`アサーションが入れ子になった`sp:Issuer`アサーション トークンの発行者をポイントします。</span><span class="sxs-lookup"><span data-stu-id="a2e76-193">The WCF endpoint describes this authentication requirement by using `sp:IssuedToken` assertion with a nested `sp:Issuer` assertion pointing to the token issuer.</span></span> <span data-ttu-id="a2e76-194">`sp:Issuer` アサーションにアクセスするクライアント アプリケーションは、トークン発行者のエンドポイントとの通信方法を知る必要があります。</span><span class="sxs-lookup"><span data-stu-id="a2e76-194">Client applications that access the `sp:Issuer` assertion need to know how to communicate with the token issuer endpoint.</span></span> <span data-ttu-id="a2e76-195">クライアントは、トークン発行者に関するメタデータを知る必要があります。</span><span class="sxs-lookup"><span data-stu-id="a2e76-195">The client needs to know metadata about the token issuer.</span></span> <span data-ttu-id="a2e76-196">MEX で定義されているエンドポイント参照のメタデータ拡張を使用して、WCF は、トークン発行者のメタデータへの参照を提供します。</span><span class="sxs-lookup"><span data-stu-id="a2e76-196">Using the endpoint reference metadata extensions defined in MEX, WCF provides a reference to the token issuer metadata.</span></span>

```xml
<sp:IssuedToken>
  <sp:Issuer>
    <wsa10:Address>
      http://sts.fabrikam123.com
    </wsa10:Address>
    <wsa10:Metadata>
      <mex:Metadata>
        <mex:MetadataSection>
          <mex:MetadataReference>
            <wsa10:Address>
              http://sts.fabrikam123.com/mex
            </wsa10:Address>
          </mex:MetadataReference>
        </mex:MetadataSection>
      </mex:Metadata>
    </wsa10:Metadata>
  </sp:Issuer>
</sp:IssuedToken>
```

### <a name="message-addressing-headers"></a><span data-ttu-id="a2e76-197">メッセージのアドレス指定ヘッダー</span><span class="sxs-lookup"><span data-stu-id="a2e76-197">Message Addressing Headers</span></span>

#### <a name="message-headers"></a><span data-ttu-id="a2e76-198">メッセージ ヘッダー</span><span class="sxs-lookup"><span data-stu-id="a2e76-198">Message Headers</span></span>
<span data-ttu-id="a2e76-199">両方の Ws-addressing のバージョンでは、WCF を使用して、次のメッセージ ヘッダー仕様で規定された`wsa:To`、 `wsa:ReplyTo`、 `wsa:Action`、 `wsa:MessageID`、および`wsa:RelatesTo`します。</span><span class="sxs-lookup"><span data-stu-id="a2e76-199">For both WS-Addressing versions, WCF uses the following message headers as prescribed by the specifications `wsa:To`, `wsa:ReplyTo`, `wsa:Action`, `wsa:MessageID`,and `wsa:RelatesTo`.</span></span>

<span data-ttu-id="a2e76-200">B3211:すべての Ws-addressing のバージョンでは、WCF しますが、すぐに使える Ws-addressing メッセージ ヘッダーは生成されません`wsa:FaultTo`と`wsa:From`します。</span><span class="sxs-lookup"><span data-stu-id="a2e76-200">B3211: For all WS-Addressing versions, WCF honors, but does not produce out of the box, WS-Addressing message headers `wsa:FaultTo` and `wsa:From`.</span></span>

<span data-ttu-id="a2e76-201">WCF アプリケーションと対話するアプリケーションでは、これらのメッセージ ヘッダーと WCF は適切に処理を追加できます。</span><span class="sxs-lookup"><span data-stu-id="a2e76-201">Applications that interact with WCF applications can add these message headers and WCF will process them accordingly.</span></span>

#### <a name="reference-parameters-and-properties"></a><span data-ttu-id="a2e76-202">参照パラメーターと参照プロパティ</span><span class="sxs-lookup"><span data-stu-id="a2e76-202">Reference Parameters and Properties</span></span>

<span data-ttu-id="a2e76-203">WCF では、エンドポイント参照のパラメーターとそれぞれの仕様に従って参照プロパティの処理を実装します。</span><span class="sxs-lookup"><span data-stu-id="a2e76-203">WCF implements processing of endpoint reference parameters and reference properties in accordance with respective specifications.</span></span>

<span data-ttu-id="a2e76-204">B3221:Ws-addressing 2004/08 を使用するよう構成する、WCF エンドポイントを区別せず参照プロパティと参照パラメーターを処理します。</span><span class="sxs-lookup"><span data-stu-id="a2e76-204">B3221: When configured to use WS-Addressing 2004/08, WCF endpoints do not differentiate between processing Reference Properties and Reference Parameters.</span></span>

### <a name="message-exchange-patterns"></a><span data-ttu-id="a2e76-205">メッセージ交換パターン</span><span class="sxs-lookup"><span data-stu-id="a2e76-205">Message Exchange Patterns</span></span>
<span data-ttu-id="a2e76-206">Web サービス操作の呼び出しに関連するメッセージのシーケンスとして参照されます、*メッセージ交換パターン*します。</span><span class="sxs-lookup"><span data-stu-id="a2e76-206">The sequence of messages involved in the Web service operation invocation is referred to as the *message exchange pattern*.</span></span> <span data-ttu-id="a2e76-207">WCF のサポートが一方向、要求/応答、および双方向メッセージ交換のパターンを実行します。</span><span class="sxs-lookup"><span data-stu-id="a2e76-207">WCF supports one-way, request-reply, and duplex message exchange patterns.</span></span> <span data-ttu-id="a2e76-208">このセクションでは、使用するメッセージ交換パターンによって異なるメッセージ処理に関する WS-Addressing の要件について説明します。</span><span class="sxs-lookup"><span data-stu-id="a2e76-208">This section clarifies WS-Addressing requirements on message processing depending on the message exchange pattern being used.</span></span>

<span data-ttu-id="a2e76-209">このセクション全体を通して、リクエスターが最初のメッセージを送信し、レスポンダーが最初のメッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="a2e76-209">Throughout this section, the requester sends the first message and the responder receives the first message.</span></span>

#### <a name="one-way-message"></a><span data-ttu-id="a2e76-210">一方向のメッセージ</span><span class="sxs-lookup"><span data-stu-id="a2e76-210">One-Way Message</span></span>
<span data-ttu-id="a2e76-211">メッセージをサポートするために WCF エンドポイントを構成するとき、指定された`Action`WCF エンドポイントが、次の動作と要件に依存する一方向パターンには、します。</span><span class="sxs-lookup"><span data-stu-id="a2e76-211">When a WCF endpoint is configured to support messages with a given `Action` to follow a one-way pattern, the WCF endpoint follows the following behaviors and requirements.</span></span> <span data-ttu-id="a2e76-212">指定しない場合、両方のバージョンの Ws-addressing で WCF ではサポートされている動作とルールが適用されます。</span><span class="sxs-lookup"><span data-stu-id="a2e76-212">Unless otherwise specified, behaviors and rules apply for both versions of WS-Addressing supported in WCF:</span></span>

- <span data-ttu-id="a2e76-213">R3311:要求元を含める必要があります`wsa:To`、 `wsa:Action`、およびエンドポイント参照によって指定された参照パラメーターのすべてのヘッダー。</span><span class="sxs-lookup"><span data-stu-id="a2e76-213">R3311: The requester must include `wsa:To`, `wsa:Action`, and headers for all reference parameters specified by the endpoint reference.</span></span> <span data-ttu-id="a2e76-214">WS-Addressing 2004/08 を使用し、エンドポイント参照によって参照プロパティが指定されている場合、対応するヘッダーもメッセージに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a2e76-214">When WS-Addressing 2004/08 is used and [reference properties] are specified by the endpoint reference, the corresponding headers must be added to the message too.</span></span>

- <span data-ttu-id="a2e76-215">B3312:要求元を含めることができます`MessageID`、 `ReplyTo`、および`FaultTo`ヘッダー。</span><span class="sxs-lookup"><span data-stu-id="a2e76-215">B3312: The requester may include `MessageID`, `ReplyTo`, and `FaultTo` headers.</span></span> <span data-ttu-id="a2e76-216">受信側のインフラストラクチャはこれらのヘッダーを無視し、ヘッダーはアプリケーションに渡されます。</span><span class="sxs-lookup"><span data-stu-id="a2e76-216">The receiver infrastructure will ignore them, and they will be passed to the application.</span></span>

- <span data-ttu-id="a2e76-217">R3313:HTTP を使用すると、HTTP 応答レッグで送信されるメッセージがない、応答側は空の本文と HTTP 202 ステータス コードの HTTP 応答を送信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a2e76-217">R3313: When HTTP is used and no message is being sent on the HTTP response leg, the responder must send an HTTP response with an empty body and an HTTP 202 status code.</span></span>

     <span data-ttu-id="a2e76-218">HTTP トランスポートを使用しており、操作コントラクトで一方向のメッセージが宣言されている場合でも、HTTP 応答を使用してインフラストラクチャ メッセージを送信できます。たとえば、信頼できるメッセージングでは、HTTP 応答で `SequenceAcknowledgement` メッセージを送信できます。</span><span class="sxs-lookup"><span data-stu-id="a2e76-218">When the HTTP transport is in use and the operation contract declares a message one-way, the HTTP response can still be used for sending infrastructure messages—for example, reliable messaging can send a `SequenceAcknowledgement` message on an HTTP response.</span></span>

- <span data-ttu-id="a2e76-219">B3314:WCF 応答側では、一方向メッセージへの応答でエラー メッセージを送信しません。</span><span class="sxs-lookup"><span data-stu-id="a2e76-219">B3314: The WCF responder does not send a fault message in response to a one-way message.</span></span>

#### <a name="request-reply"></a><span data-ttu-id="a2e76-220">要求/応答</span><span class="sxs-lookup"><span data-stu-id="a2e76-220">Request-Reply</span></span>
<span data-ttu-id="a2e76-221">メッセージで WCF エンドポイントを構成するときに、指定された`Action`の動作と要件を次に、要求/応答パターンは、WCF エンドポイントに依存します。</span><span class="sxs-lookup"><span data-stu-id="a2e76-221">When a WCF endpoint is configured for a message with a given `Action` to follow the request-reply pattern, the WCF endpoint follows the behaviors and requirements below.</span></span> <span data-ttu-id="a2e76-222">未指定の場合、両方のバージョンの Ws-addressing で WCF ではサポートされている動作とルールが適用されます。</span><span class="sxs-lookup"><span data-stu-id="a2e76-222">Unless specified otherwise, behaviors and rules apply for both versions of WS-Addressing supported in WCF:</span></span>

- <span data-ttu-id="a2e76-223">R3321:依頼者が要求に含める必要があります`wsa:To`、 `wsa:Action`、 `wsa:MessageID`、およびすべての参照パラメーターまたは参照プロパティ (またはその両方)、エンドポイント参照によって指定されたヘッダー。</span><span class="sxs-lookup"><span data-stu-id="a2e76-223">R3321: The requester must include in the request `wsa:To`, `wsa:Action`, `wsa:MessageID`, and headers for all reference parameters or reference properties (or both) specified by the endpoint reference.</span></span>

- <span data-ttu-id="a2e76-224">R3322:Ws-addressing 2004/08 を使用すると、ときに`ReplyTo`要求も含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="a2e76-224">R3322: When WS-Addressing 2004/08 is used, `ReplyTo` must also be included in the request.</span></span>

- <span data-ttu-id="a2e76-225">R3323:Ws-addressing 1.0 を使用する場合と`ReplyTo`が既定のエンドポイント参照に等しい [アドレス] プロパティを使用して、要求に存在しない`http://www.w3.org/2005/08/addressing/anonymous`使用されます。</span><span class="sxs-lookup"><span data-stu-id="a2e76-225">R3323: When WS-Addressing 1.0 is used and `ReplyTo` is not present in the request, a default endpoint reference with the [address] property equal to `http://www.w3.org/2005/08/addressing/anonymous` is used.</span></span>

- <span data-ttu-id="a2e76-226">R3324:要求元を含める必要があります`wsa:To`、 `wsa:Action`、および`wsa:RelatesTo`のすべての参照パラメーターまたは参照プロパティ (またはその両方) で指定されたヘッダーと応答メッセージのヘッダー、`ReplyTo`要求のエンドポイント参照。</span><span class="sxs-lookup"><span data-stu-id="a2e76-226">R3324: The requester must include `wsa:To`, `wsa:Action`, and `wsa:RelatesTo` headers in the reply message, as well as headers for all reference parameters or reference properties (or both) specified by the `ReplyTo` endpoint reference in the request.</span></span>

### <a name="web-services-addressing-faults"></a><span data-ttu-id="a2e76-227">Web Services Addressing エラー</span><span class="sxs-lookup"><span data-stu-id="a2e76-227">Web Services Addressing Faults</span></span>
<span data-ttu-id="a2e76-228">R3411:WCF では、Ws-addressing 2004/08 で定義された次のエラーを生成します。</span><span class="sxs-lookup"><span data-stu-id="a2e76-228">R3411: WCF produces the following faults defined by WS-Addressing 2004/08.</span></span>

| <span data-ttu-id="a2e76-229">コード</span><span class="sxs-lookup"><span data-stu-id="a2e76-229">Code</span></span> | <span data-ttu-id="a2e76-230">原因</span><span class="sxs-lookup"><span data-stu-id="a2e76-230">Cause</span></span> |
|----------|-----------|
| `wsa:DestinationUnreachable` | <span data-ttu-id="a2e76-231">このチャネル用に確立された応答アドレスとは異なる `ReplyTo` を使用してメッセージが到着しました。To ヘッダーに指定されたアドレスをリッスンしているエンドポイントはありません。</span><span class="sxs-lookup"><span data-stu-id="a2e76-231">The message arrived with a `ReplyTo` that is different from the reply address established for this channel; there is no endpoint listening at the address specified in the To header.</span></span> |
| `wsa:ActionNotSupported` | <span data-ttu-id="a2e76-232">`Action` ヘッダーに指定されたアクションは、エンドポイントに関連付けられたインフラストラクチャ チャネルまたはディスパッチャーによって認識されません。</span><span class="sxs-lookup"><span data-stu-id="a2e76-232">the infrastructure channels or dispatcher associated with the endpoint do not recognize the action specified in the `Action` header.</span></span> |

<span data-ttu-id="a2e76-233">R3412:WCF では、Ws-addressing 1.0 で定義された次のエラーを生成します。</span><span class="sxs-lookup"><span data-stu-id="a2e76-233">R3412: WCF produces the following faults defined by WS-Addressing 1.0.</span></span>

| <span data-ttu-id="a2e76-234">コード</span><span class="sxs-lookup"><span data-stu-id="a2e76-234">Code</span></span> | <span data-ttu-id="a2e76-235">原因</span><span class="sxs-lookup"><span data-stu-id="a2e76-235">Cause</span></span> |
|----------|-----------|
| `wsa10:InvalidAddressingHeader` | <span data-ttu-id="a2e76-236">重複する`wsa:To`、 `wsa:ReplyTo`、`wsa:From`または`wsa:MessageID`します。</span><span class="sxs-lookup"><span data-stu-id="a2e76-236">Duplicate `wsa:To`, `wsa:ReplyTo`, `wsa:From` or `wsa:MessageID`.</span></span> <span data-ttu-id="a2e76-237">重複する`wsa:RelatesTo`同じ`RelationshipType`します。</span><span class="sxs-lookup"><span data-stu-id="a2e76-237">Duplicate `wsa:RelatesTo` with the same `RelationshipType`.</span></span> |
| `wsa10:MessageAddressingHeaderRequired` | <span data-ttu-id="a2e76-238">必須の Addressing ヘッダーがありません。</span><span class="sxs-lookup"><span data-stu-id="a2e76-238">The required Addressing header is missing.</span></span> |
| `wsa10:DestinationUnreachable` | <span data-ttu-id="a2e76-239">このチャネル用に確立された応答アドレスとは異なる `ReplyTo` を使用してメッセージが到着しました。</span><span class="sxs-lookup"><span data-stu-id="a2e76-239">The message arrived with a `ReplyTo` that is different from the reply address established for this channel.</span></span> <span data-ttu-id="a2e76-240">To ヘッダーに指定されたアドレスをリッスンしているエンドポイントはありません。</span><span class="sxs-lookup"><span data-stu-id="a2e76-240">There is no endpoint listening at the address specified in the To header.</span></span> |
| `wsa10:ActionNotSupported` | <span data-ttu-id="a2e76-241">`Action` ヘッダーに指定されたアクションは、エンドポイントに関連付けられたインフラストラクチャ チャネルまたはディスパッチャーによって認識されません。</span><span class="sxs-lookup"><span data-stu-id="a2e76-241">An action specified in the `Action` header is not recognized by the infrastructure channels or dispatcher associated with the endpoint.</span></span> |
| `wsa10:EndpointUnavailable` | <span data-ttu-id="a2e76-242">RM チャネルは、`CreateSequence` メッセージのアドレス指定ヘッダーの検査に基づいて、エンドポイントでシーケンスが処理されないことを示すために、このエラーを返しました。</span><span class="sxs-lookup"><span data-stu-id="a2e76-242">The RM channel sends this fault back, indicating the endpoint will not process the sequence based upon examination of the `CreateSequence` message’s addressing headers.</span></span> |

<span data-ttu-id="a2e76-243">上記の 2 つの表に示すコードは、SOAP 1.1 の `FaultCode`、および SOAP 1.2 の `SubCode` (Code=Sender) に対応付けられています。</span><span class="sxs-lookup"><span data-stu-id="a2e76-243">Code in the preceding tables maps to `FaultCode` in SOAP 1.1 and `SubCode` (with Code=Sender) in SOAP 1.2.</span></span>

### <a name="wsdl-11-binding-and-ws-policy-assertions"></a><span data-ttu-id="a2e76-244">WSDL 1.1 バインディングと WS-Policy アサーション</span><span class="sxs-lookup"><span data-stu-id="a2e76-244">WSDL 1.1 Binding and WS-Policy Assertions</span></span>

#### <a name="indicating-use-of-ws-addressing"></a><span data-ttu-id="a2e76-245">WS-Addressing の使用の提示</span><span class="sxs-lookup"><span data-stu-id="a2e76-245">Indicating Use of WS-Addressing</span></span>
<span data-ttu-id="a2e76-246">WCF では、ポリシー アサーションを使用して、特定の Ws-addressing のバージョンのエンドポイントのサポートを示します。</span><span class="sxs-lookup"><span data-stu-id="a2e76-246">WCF uses policy assertions to indicate endpoint support for a particular WS-Addressing version.</span></span>

<span data-ttu-id="a2e76-247">次のポリシー アサーションには、エンドポイント ポリシー サブジェクト [WS-PA] が含まれており、そのエンドポイントで送受信されるメッセージでは WS-Addressing 2004/08 を使用する必要があることを示しています。</span><span class="sxs-lookup"><span data-stu-id="a2e76-247">The following policy assertion has Endpoint Policy Subject [WS-PA] and indicates messages sent and received from the endpoint must use WS-Addressing 2004/08.</span></span>

```xml
<wsap:UsingAddressing />
```

<span data-ttu-id="a2e76-248">このポリシー アサーションは、WS-Addressing 2004/08 仕様を補うものです。</span><span class="sxs-lookup"><span data-stu-id="a2e76-248">This policy assertion augments the WS-Addressing 2004/08 specification.</span></span>

<span data-ttu-id="a2e76-249">次のポリシー アサーションは、送受信されるメッセージでは WS-Addressing 1.0 を使用する必要があることを示しています。</span><span class="sxs-lookup"><span data-stu-id="a2e76-249">The following policy assertion this indicates that messages sent/received must use WS-Addressing 1.0.</span></span>

```xml
<wsam:Addressing/>
```

<span data-ttu-id="a2e76-250">次のポリシー アサーションには、エンドポイント ポリシー サブジェクト [WS-PA] が含まれており、そのエンドポイントで送受信されるメッセージでは WS-Addressing 2004/08 を使用する必要があることを示しています。</span><span class="sxs-lookup"><span data-stu-id="a2e76-250">The following policy assertion has an Endpoint Policy Subject [WS-PA] and indicates that messages sent and received from the endpoint must use WS-Addressing 2004/08.</span></span>

```xml
<wsaw10:UsingAddressing />
```

<span data-ttu-id="a2e76-251">`wsaw10:UsingAddressing` 要素は、WS-Addressing-WSDL から借用したものです。この要素は、この仕様のセクション 3.1.2 に従って、WS-Policy のコンテキストで使用されます。</span><span class="sxs-lookup"><span data-stu-id="a2e76-251">The `wsaw10:UsingAddressing` element is borrowed from [WS-Addressing-WSDL] and is used in the context of WS-Policy in compliance with that specification, section 3.1.2.</span></span>

<span data-ttu-id="a2e76-252">Addressing を使用しても、WSDL 1.1、SOAP 1.1、および SOAP 1.2 HTTP バインディングのセマンティクスが変更されるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="a2e76-252">Use of Addressing does not alter the semantics of WSDL 1.1, SOAP 1.1, and SOAP 1.2 HTTP Bindings.</span></span> <span data-ttu-id="a2e76-253">たとえば、Addressing と WSDL SOAP 1.x HTTP バインディングを使用するエンドポイントに送信する要求に対して応答が求められている場合、この応答は HTTP 応答を使用して送信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a2e76-253">For example, if a reply is expected to a request that is sent to an endpoint that uses Addressing and WSDL SOAP 1.x HTTP binding, the reply must be sent by using the HTTP response.</span></span>

<span data-ttu-id="a2e76-254">HTTP 応答を使用して送信された応答の場合、WS-AM アサーションは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="a2e76-254">For replies sent over the http response, the WS-AM assertion is:</span></span>

```xml
<wsam:AnonymousResponses/>
```

<span data-ttu-id="a2e76-255">完全なポリシー アサーションは次のようになる場合があります。</span><span class="sxs-lookup"><span data-stu-id="a2e76-255">The complete policy assertion might look like this:</span></span>

```xml
<wsam:Addressing>
    <wsp:Policy>
        <wsam:AnonymousResponses />
    </wsp:Policy>
</wsam:Addressing>
```

<span data-ttu-id="a2e76-256">ただし、リクエスターとレスポンダー間で 2 つの独立した逆方向の HTTP 接続を確立することによってメリットのあるメッセージ交換パターンがあります。たとえば、レスポンダーによって送信される要求されていない一方向のメッセージなどです。</span><span class="sxs-lookup"><span data-stu-id="a2e76-256">However, there are message exchange patterns that benefit from having two independent converse HTTP connections established between the requester and the responder, for example, unsolicited one-way messages sent by the responder.</span></span>

<span data-ttu-id="a2e76-257">WCF では、入力メッセージの 1 つのチャネルが使用される、他の出力メッセージを使用する複合二重チャネルを 2 つの基になるトランスポート チャネルから形成できます機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="a2e76-257">WCF offers a feature by which two underlying transport channels can form a Composite Duplex channel, where one channel is used for input messages and the other is used for output messages.</span></span> <span data-ttu-id="a2e76-258">HTTP トランスポートの場合、複合二重によって 2 つの逆方向の HTTP 接続が実現します。</span><span class="sxs-lookup"><span data-stu-id="a2e76-258">In the case of the HTTP Transport, Composite Duplex provides two converse HTTP connections.</span></span> <span data-ttu-id="a2e76-259">一方の接続はリクエスターがレスポンダーにメッセージを送信するために使用し、もう一方はレスポンダーがリクエスターにメッセージを返すために使用します。</span><span class="sxs-lookup"><span data-stu-id="a2e76-259">The requester uses one connection to send messages to the responder, and the responder uses the other to send messages back to the requester.</span></span>

<span data-ttu-id="a2e76-260">個別の HTTP 要求を使用して送信された応答の場合、WS-AM アサーションは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="a2e76-260">For replies sent over separate http requests, the ws-am assertion is</span></span>

```xml
<wsam:NonAnonymousResponses/>
```

<span data-ttu-id="a2e76-261">完全なポリシー アサーションは次のようになる場合があります。</span><span class="sxs-lookup"><span data-stu-id="a2e76-261">The complete policy assertion might look like this:</span></span>

```xml
<wsam:Addressing>
    <wsp:Policy>
        <wsam:NonAnonymousResponses />
    </wsp:Policy>
</wsam:Addressing>
```

<span data-ttu-id="a2e76-262">WSDL 1.1 SOAP 1.x HTTP バインディングを使用するエンドポイントで、エンドポイント ポリシー サブジェクト [WS-PA] を含む次のアサーションを使用する場合、リクエスターからレスポンダーおよびレスポンダーからリクエスターへのメッセージ フローにそれぞれ別の逆方向の HTTP 接続を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a2e76-262">Use of the following assertion that has Endpoint Policy Subject [WS-PA] on endpoints that use WSDL 1.1 SOAP 1.x HTTP bindings requires two separate converse HTTP connections to be used for messages flowing from requester to responder and responder to requester, respectively.</span></span>

```xml
<cdp:CompositeDuplex/>
```

<span data-ttu-id="a2e76-263">上記のステートメントにより、要求メッセージの `wsa:ReplyTo` ヘッダーに関する以下の要件が発生します。</span><span class="sxs-lookup"><span data-stu-id="a2e76-263">The previous statement leads to the following requirements on the `wsa:ReplyTo` header for request messages:</span></span>

- <span data-ttu-id="a2e76-264">R3514:要求のメッセージをエンドポイントに送信する必要がありますが、`ReplyTo`ヘッダーを`[address]`プロパティが等しくない`http://www.w3.org/2005/08/addressing/anonymous`エンドポイントが WSDL 1.1 SOAP 1.x HTTP バインディングを使用して、使用ポリシー代替手段を持つ場合、`wsap10:UsingAddressing`または`wsap:UsingAddressing`アサーション組み合わせて`cdp:CompositeDuplex`アタッチします。</span><span class="sxs-lookup"><span data-stu-id="a2e76-264">R3514: Request messages sent to an endpoint must have a `ReplyTo` header with the `[address]` property not equal to `http://www.w3.org/2005/08/addressing/anonymous` if the endpoint uses a WSDL 1.1 SOAP 1.x HTTP binding and has a policy alternative with a `wsap10:UsingAddressing` or `wsap:UsingAddressing` assertion coupled with `cdp:CompositeDuplex` attached.</span></span>

- <span data-ttu-id="a2e76-265">R3515:要求のメッセージをエンドポイントに送信する必要がありますが、`ReplyTo`ヘッダーを`[address]`プロパティを等しく`http://www.w3.org/2005/08/addressing/anonymous`、かがありません、`ReplyTo`場合は、エンドポイントが WSDL 1.1 SOAP 1.x HTTP バインディングを使用してし、 、ポリシー代替手段を持つすべてのヘッダー`wsap10:UsingAddressing`アサーションと no`cdp:CompositeDuplex`アサーション。</span><span class="sxs-lookup"><span data-stu-id="a2e76-265">R3515: Request messages sent to an endpoint must have a `ReplyTo` header with the `[address]` property equal to `http://www.w3.org/2005/08/addressing/anonymous`, or not have a `ReplyTo` header at all, if the endpoint uses a WSDL 1.1 SOAP 1.x HTTP binding and has a policy alternative with `wsap10:UsingAddressing` assertion and no `cdp:CompositeDuplex` assertion attached.</span></span>

- <span data-ttu-id="a2e76-266">R3516:要求のメッセージをエンドポイントに送信する必要がありますが、`ReplyTo`ヘッダーを`[address]`プロパティを等しく`http://www.w3.org/2005/08/addressing/anonymous`エンドポイントが WSDL 1.1 SOAP 1.x HTTP バインディングを使用して、使用ポリシー代替手段を持つ場合`wsap:UsingAddressing`アサーションと no `cdp:CompositeDuplex`接続されているアサーションです。</span><span class="sxs-lookup"><span data-stu-id="a2e76-266">R3516: Request messages sent to an endpoint must have a `ReplyTo` header with an `[address]` property equal to `http://www.w3.org/2005/08/addressing/anonymous` if the endpoint uses a WSDL 1.1 SOAP 1.x HTTP binding and has a policy alternative with `wsap:UsingAddressing` assertion and no `cdp:CompositeDuplex` assertion attached.</span></span>

<span data-ttu-id="a2e76-267">WS-Addressing の WSDL 仕様では、`<wsaw:Anonymous/>` ヘッダーの要件を示す 3 つのテキスト値 (required、optional、および prohibited) を持つ `wsa:ReplyTo` 要素を導入することにより、同様のプロトコル バインディングを記述することを試みています (セクション 3.2)。</span><span class="sxs-lookup"><span data-stu-id="a2e76-267">The WS-addressing WSDL specification attempts to describe similar protocol bindings by introducing an element `<wsaw:Anonymous/>` with three textual values (required, optional, and prohibited) to indicate requirements on the `wsa:ReplyTo` header (section 3.2).</span></span> <span data-ttu-id="a2e76-268">残念ながら、このような要素の定義では、要素をアサーションとして使用する代替手段の共通部分をサポートするために、ドメイン固有の拡張を必要とするため、特に WS-Policy のコンテキストではアサーションとして使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="a2e76-268">Unfortunately, such element definition is not particularly usable as an assertion in the context of WS-Policy, because it requires domain-specific extensions to support the intersection of alternatives using such an element as an assertion.</span></span> <span data-ttu-id="a2e76-269">また、このような要素の定義は、ネットワーク上のエンドポイントの動作に相反する `ReplyTo` ヘッダーの値を示すため、HTTP トランスポートに固有のものになります。</span><span class="sxs-lookup"><span data-stu-id="a2e76-269">Such element definition also indicates the value of the `ReplyTo` header as opposed to the endpoint behavior on the wire, which makes it specific to HTTP transport.</span></span>

#### <a name="action-definition"></a><span data-ttu-id="a2e76-270">アクション定義</span><span class="sxs-lookup"><span data-stu-id="a2e76-270">Action Definition</span></span>
<span data-ttu-id="a2e76-271">WS-Addressing 2004/08 では、`wsa:Action` 要素の `wsdl:portType/wsdl:operation/[wsdl:input | wsdl:output | wsdl:fault]` 属性が定義されています。</span><span class="sxs-lookup"><span data-stu-id="a2e76-271">WS-Addressing 2004/08 defines a `wsa:Action` attribute for the `wsdl:portType/wsdl:operation/[wsdl:input | wsdl:output | wsdl:fault]` elements.</span></span> <span data-ttu-id="a2e76-272">WS-Addressing 1.0 WSDL バインディング (WS-ADDR10-WSDL) では、同様の属性として `wsaw10:Action` が定義されています。</span><span class="sxs-lookup"><span data-stu-id="a2e76-272">WS-Addressing 1.0 WSDL Binding (WS-ADDR10-WSDL) defines a similar attribute, `wsaw10:Action`.</span></span>

<span data-ttu-id="a2e76-273">この 2 つの属性の唯一の違いは、既定の Action パターンのセマンティクスです。これは、WS-ADDR のセクション 3.3.2 および WS-ADDR10-WSDL のセクション 4.4.4 にそれぞれ記載されています。</span><span class="sxs-lookup"><span data-stu-id="a2e76-273">The only difference between the two is the default Action pattern semantics described in section 3.3.2 of WS-ADDR and section 4.4.4 of WS-ADDR10-WSDL, respectively.</span></span>

<span data-ttu-id="a2e76-274">同じを共有する 2 つのエンドポイントが適切では`portType`(または WCF 用語では、コントラクト) が、異なるバージョンの Ws-addressing を使用します。</span><span class="sxs-lookup"><span data-stu-id="a2e76-274">It is a reasonable to have two endpoints that share the same `portType` (or contract, in WCF terminology) but using different versions of WS-Addressing.</span></span> <span data-ttu-id="a2e76-275">しかし、Action は `portType` によって定義され、`portType` を実装するエンドポイント間で変更できないことを考えると、両方の既定のアクション パターンをサポートすることは不可能になります。</span><span class="sxs-lookup"><span data-stu-id="a2e76-275">But given that Action is defined by the `portType` and should not change across the endpoints that implement the `portType`, it becomes impossible to support both default action patterns.</span></span>

<span data-ttu-id="a2e76-276">この問題を解決するのには、WCF は、の 1 つのバージョンをサポートしています。、`Action`属性。</span><span class="sxs-lookup"><span data-stu-id="a2e76-276">To resolve this controversy, WCF supports a single version of the `Action` attribute.</span></span>

<span data-ttu-id="a2e76-277">B3521:WCF を使用して、`wsaw10:Action`属性`wsdl:portType/wsdl:operation/[wsdl:input | wsdl:output | wsdl:fault]`WS ADDR10-WSDL を判断で定義されている要素、`Action`エンドポイントによって使用される Ws-addressing のバージョンに関係なく、対応するメッセージの URI。</span><span class="sxs-lookup"><span data-stu-id="a2e76-277">B3521: WCF uses the `wsaw10:Action` attribute on `wsdl:portType/wsdl:operation/[wsdl:input | wsdl:output | wsdl:fault]` elements as defined in WS-ADDR10-WSDL to determine the `Action` URI for the corresponding messages irrespective of the WS-Addressing version used by the endpoint.</span></span>

#### <a name="use-endpoint-reference-inside-wsdl-port"></a><span data-ttu-id="a2e76-278">WSDL ポート内でのエンドポイント参照の使用</span><span class="sxs-lookup"><span data-stu-id="a2e76-278">Use Endpoint Reference Inside WSDL Port</span></span>
<span data-ttu-id="a2e76-279">WS-ADDR10-WSDL のセクション 4.1 では、`wsdl:port` 要素を拡張して、WS-Addressing の観点でエンドポイントを記述する `<wsa10:EndpointReference…/>` 子要素を含めています。</span><span class="sxs-lookup"><span data-stu-id="a2e76-279">WS-ADDR10-WSDL section 4.1 extends the `wsdl:port` element to include the `<wsa10:EndpointReference…/>` child element to describe the endpoint in WS-Addressing terms.</span></span> <span data-ttu-id="a2e76-280">WCF は Ws-addressing 2004/08 のこのユーティリティを展開できるように`<wsa:EndpointReference…/>`の子要素として表示する`wsdl:port`します。</span><span class="sxs-lookup"><span data-stu-id="a2e76-280">WCF expands this utility on WS-Addressing 2004/08, allowing `<wsa:EndpointReference…/>` to appear as a child element of `wsdl:port`.</span></span>

- <span data-ttu-id="a2e76-281">R3531:エンドポイントがある接続されているポリシー代替手段を持つ場合、`<wsaw10:UsingAddressing/>`ポリシー アサーションを対応する`wsdl:port`要素が子要素を含めることができます`<wsa10:EndpointReference …/>`します。</span><span class="sxs-lookup"><span data-stu-id="a2e76-281">R3531: If an endpoint has an attached policy alternative with a `<wsaw10:UsingAddressing/>` policy assertion, the corresponding `wsdl:port` element can contain a child element `<wsa10:EndpointReference …/>`.</span></span>

- <span data-ttu-id="a2e76-282">R3532:場合、`wsdl:port`子要素を含む`<wsa10:EndpointReference …/>`、`wsa10:EndpointReference/wsa10:Address`子要素の値の値に一致する必要があります、`@address`の兄弟の属性`wsdl:port` / `wsdl:location`要素。</span><span class="sxs-lookup"><span data-stu-id="a2e76-282">R3532: If a `wsdl:port` contains a child element `<wsa10:EndpointReference …/>`, the `wsa10:EndpointReference/wsa10:Address` child element value must match the value of the `@address` attribute of the sibling `wsdl:port`/`wsdl:location` element.</span></span>

- <span data-ttu-id="a2e76-283">R3533:エンドポイントがある接続されているポリシー代替手段を持つ場合`<wsap:UsingAddressing/>`ポリシー アサーションを対応する`wsdl:port`要素が子要素を含めることができます`<wsa:EndpointReference …/>`します。</span><span class="sxs-lookup"><span data-stu-id="a2e76-283">R3533: If an endpoint has an attached policy alternative with `<wsap:UsingAddressing/>` policy assertion, the corresponding `wsdl:port` element can contain a child element `<wsa:EndpointReference …/>`.</span></span>

- <span data-ttu-id="a2e76-284">R3534:場合、`wsdl:port`子要素を含む`<wsa:EndpointReference …/>`、`wsa:EndpointReference/wsa:Address`子要素の値の値に一致する必要があります、`@address`の兄弟の属性`wsdl:port` / `wsdl:location`要素。</span><span class="sxs-lookup"><span data-stu-id="a2e76-284">R3534: If a `wsdl:port` contains a child element `<wsa:EndpointReference …/>`, the `wsa:EndpointReference/wsa:Address` child element value must match the value of the `@address` attribute of the sibling `wsdl:port`/`wsdl:location` element.</span></span>

### <a name="composition-with-ws-security"></a><span data-ttu-id="a2e76-285">WS-Security によるコンポジション</span><span class="sxs-lookup"><span data-stu-id="a2e76-285">Composition with WS-Security</span></span>
<span data-ttu-id="a2e76-286">WS-ADDR および WS-ADDR10 のセキュリティに関する考慮事項のセクションに従って、メッセージ本文と共にすべてのアドレス指定メッセージ ヘッダーに署名し、これらをバインドすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="a2e76-286">According to security consideration sections in WS-ADDR and WS-ADDR10, all addressing message headers are recommended to be signed together with the message body to bind them together.</span></span>

<span data-ttu-id="a2e76-287">メッセージの整合性を保護するために WS-Security を使用する場合は、メッセージの本文と共に、WS-Addressing メッセージ ヘッダーと、参照パラメーターまたは参照プロパティ (または両方) によって生成されたヘッダーに署名する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a2e76-287">When WS-Security is used for message integrity protection, WS-Addressing message headers as well as headers resulted from reference parameters or properties (or both) must be signed together with the body of the message.</span></span>

### <a name="examples"></a><span data-ttu-id="a2e76-288">使用例</span><span class="sxs-lookup"><span data-stu-id="a2e76-288">Examples</span></span>

#### <a name="one-way-message"></a><span data-ttu-id="a2e76-289">一方向のメッセージ</span><span class="sxs-lookup"><span data-stu-id="a2e76-289">One-Way Message</span></span>
<span data-ttu-id="a2e76-290">このシナリオでは、送信者は一方向のメッセージを受信者に送信します。</span><span class="sxs-lookup"><span data-stu-id="a2e76-290">In this scenario, the sender sends a one-way message to the receiver.</span></span> <span data-ttu-id="a2e76-291">SOAP 1.2、HTTP 1.1、および W3C WS-Addressing 1.0 を使用します。</span><span class="sxs-lookup"><span data-stu-id="a2e76-291">SOAP 1.2, HTTP 1.1, and W3C WS-Addressing 1.0 are used.</span></span>

<span data-ttu-id="a2e76-292">要求メッセージの構造:メッセージ ヘッダーが含まれる`wsa10:To`と`wsa10:Action`要素。</span><span class="sxs-lookup"><span data-stu-id="a2e76-292">The Request Message Structure: The message headers include `wsa10:To` and `wsa10:Action` elements.</span></span> <span data-ttu-id="a2e76-293">メッセージ本文には、アプリケーション名前空間の特定の `<app:Ping>` 要素が含まれます。</span><span class="sxs-lookup"><span data-stu-id="a2e76-293">The message body includes a specific `<app:Ping>` element from the application namespace.</span></span>

<span data-ttu-id="a2e76-294">HTTP ヘッダー:POST の送信先の URI の一致、`wsa10:To`要素。</span><span class="sxs-lookup"><span data-stu-id="a2e76-294">HTTP Headers: The destination in POST matches the URI in the `wsa10:To` element.</span></span>

<span data-ttu-id="a2e76-295">Content-Type ヘッダーには、SOAP 1.2 で必要とされる値 `application/soap+xml` が含まれます。</span><span class="sxs-lookup"><span data-stu-id="a2e76-295">The Content-Type header has the value of `application/soap+xml` as required by SOAP 1.2.</span></span> <span data-ttu-id="a2e76-296">また、`charset` パラメーターと `action` パラメーターも含まれます。</span><span class="sxs-lookup"><span data-stu-id="a2e76-296">Parameters `charset` and `action` are included.</span></span> <span data-ttu-id="a2e76-297">Content-Type ヘッダーの `action` パラメーターは、`wsa10:Action` メッセージ ヘッダーの値に一致します。</span><span class="sxs-lookup"><span data-stu-id="a2e76-297">The `action` parameter of the Content-Type header matches the value of the `wsa10:Action` message header.</span></span>

```
POST http://fabrikam123.com/Service HTTP/1.1
Content-Type: application/soap+xml; charset=utf-8;  
              action="http://fabrikam123.com/Service/OneWay"
Host: 131.107.72.15
Content-Length: 1501
Expect: 100-continue
Proxy-Connection: Keep-Alive
<s12:Envelope>
  <s12:Header>
    <wsa10:To s12:mustUnderstand="1">
        http://fabrikam123.com/Service
    </wsa10:To>
    <wsa10:Action s12:mustUnderstand="1">
        http://fabrikam123.com/Service/OneWay 
    </wsa10:Action>
  </s12:Header>
  <s12:Body>
    <Ping xmlns="http://fabrikam123.com/Service/">
      <Text>Hello World</Text>
    </Ping>
  </s12:Body>
</s12:Envelope>
```

<span data-ttu-id="a2e76-298">受信側は、空の HTTP 応答と 202 ステータスで応答します。</span><span class="sxs-lookup"><span data-stu-id="a2e76-298">The receiver responds with an empty HTTP response and status 202.</span></span> <span data-ttu-id="a2e76-299">HTTP 応答の一例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="a2e76-299">An example of the HTTP response:</span></span>

```
HTTP/1.1 202 Accepted
Date: Fri, 15 Jul 2005 08:56:07 GMT
Server: Microsoft-IIS/6.0
MicrosoftOfficeWebServer: 5.0_Pub
X-Powered-By: ASP.NET
X-AspNet-Version: 2.0.50215
Cache-Control: private
Content-Length: 0
```

## <a name="soap-message-transmission-optimization-mechanism"></a><span data-ttu-id="a2e76-300">SOAP Message Transmission Optimization Mechanism</span><span class="sxs-lookup"><span data-stu-id="a2e76-300">SOAP Message Transmission Optimization Mechanism</span></span>
<span data-ttu-id="a2e76-301">このセクションでは、HTTP SOAP MTOM の WCF 実装の詳細について説明します。</span><span class="sxs-lookup"><span data-stu-id="a2e76-301">This section describes the WCF implementation details for the HTTP SOAP MTOM.</span></span> <span data-ttu-id="a2e76-302">MTOM テクノロジは、従来の TEXT/XML エンコーディングまたは WCF バイナリ エンコーディングと同じクラスの SOAP メッセージのエンコーディング機構です。</span><span class="sxs-lookup"><span data-stu-id="a2e76-302">MTOM technology is SOAP message encoding mechanism of the same class as traditional text/XML encoding or WCF Binary encoding.</span></span> <span data-ttu-id="a2e76-303">MTOM には、次のような機能があります。</span><span class="sxs-lookup"><span data-stu-id="a2e76-303">MTOM includes the following:</span></span>

- <span data-ttu-id="a2e76-304">XOP によって記述された XML エンコーディングおよびパッケージング機構。XOP は、Base64 で個別のバイナリ部分にエンコードされたバイナリ データを含む XML 情報項目を最適化します。</span><span class="sxs-lookup"><span data-stu-id="a2e76-304">An XML encoding and packaging mechanism described by [XOP] that optimizes XML information items containing base64-encoded binary data into separate binary parts.</span></span>

- <span data-ttu-id="a2e76-305">XML Infoset と XOP パッケージの各バイナリ部分を個別の MIME パートにシリアル化する、XOP パッケージの MIME カプセル化。</span><span class="sxs-lookup"><span data-stu-id="a2e76-305">A MIME encapsulation of the XOP package that serializes the XML Infoset and each binary part of the XOP package into a separate MIME part.</span></span>

- <span data-ttu-id="a2e76-306">SOAP 1.x エンベロープに適用される MIME XOP エンコーディング。</span><span class="sxs-lookup"><span data-stu-id="a2e76-306">A MIME XOP encoding applied to SOAP 1.x Envelope.</span></span>

- <span data-ttu-id="a2e76-307">HTTP トランスポート バインディング。</span><span class="sxs-lookup"><span data-stu-id="a2e76-307">An HTTP transport binding.</span></span>

<span data-ttu-id="a2e76-308">WCF を使用した HTTP 以外のトランスポートで MTOM を使用することになります。</span><span class="sxs-lookup"><span data-stu-id="a2e76-308">It is possible to use MTOM with non-HTTP transports with WCF.</span></span> <span data-ttu-id="a2e76-309">しかし、ここでは HTTP に焦点を合わせます。</span><span class="sxs-lookup"><span data-stu-id="a2e76-309">However, in this topic we will focus on HTTP.</span></span>

<span data-ttu-id="a2e76-310">MTOM 形式では、MTOM 自体、XOP、および MIME に適用されるさまざまな仕様を利用します。</span><span class="sxs-lookup"><span data-stu-id="a2e76-310">The MTOM format leverages a large set of specifications covering MTOM itself, XOP, and MIME.</span></span> <span data-ttu-id="a2e76-311">この仕様セットのモジュール性により、形式と処理のセマンティクスの要件を正確に再構築することが若干難しくなります。</span><span class="sxs-lookup"><span data-stu-id="a2e76-311">Modularity of this specification set makes it somewhat difficult to reconstruct exact requirements on the format and processing semantics.</span></span> <span data-ttu-id="a2e76-312">このセクションでは、MTOM HTTP バインディングの形式と処理の要件について説明します。</span><span class="sxs-lookup"><span data-stu-id="a2e76-312">This section describes the format and processing requirements for MTOM HTTP binding.</span></span>

### <a name="mtom-message-encoding"></a><span data-ttu-id="a2e76-313">MTOM メッセージ エンコーディング</span><span class="sxs-lookup"><span data-stu-id="a2e76-313">MTOM Message Encoding</span></span>

#### <a name="generating-mtom-messages"></a><span data-ttu-id="a2e76-314">MTOM メッセージの生成</span><span class="sxs-lookup"><span data-stu-id="a2e76-314">Generating MTOM messages</span></span>
<span data-ttu-id="a2e76-315">XOP のセクション 3.1 には、Base64 値を抽象的に定義された XOP パッケージに格納する要素情報項目を使用して、XML をエンコーディングするプロセスが記載されています。</span><span class="sxs-lookup"><span data-stu-id="a2e76-315">The [XOP] section 3.1 describes the process of encoding XML with element information items that contain base64 values into an abstractly defined XOP package.</span></span>

<span data-ttu-id="a2e76-316">次の一連の手順は、MTOM 固有のエンコーディング プロセスを示しています。</span><span class="sxs-lookup"><span data-stu-id="a2e76-316">The following sequence of steps describes the MTOM-specific encoding process:</span></span>

1. <span data-ttu-id="a2e76-317">エンコードする SOAP エンベロープに記述されている要素情報項目が含まれていないことを確認、`[namespace name]`の`http://www.w3.org/2004/08/xop/include`と`[local name]`の`Include`します。</span><span class="sxs-lookup"><span data-stu-id="a2e76-317">Ensure that the SOAP Envelope to be encoded contains no element information item with a `[namespace name]` of `http://www.w3.org/2004/08/xop/include` and a `[local name]` of `Include`.</span></span>

2. <span data-ttu-id="a2e76-318">空の MIME パッケージを作成します。</span><span class="sxs-lookup"><span data-stu-id="a2e76-318">Create an empty MIME package.</span></span>

3. <span data-ttu-id="a2e76-319">元の XML Infoset 内で、最適化する要素情報項目を特定します。</span><span class="sxs-lookup"><span data-stu-id="a2e76-319">Identify within the Original XML Infoset the element information items to be optimized.</span></span> <span data-ttu-id="a2e76-320">最適化されるアイテムの文字を構成する、`[children]`要素情報項目がの正規の形式である必要があります`xs:base64Binary`(XSD 2 3.2.16 参照 base64Binary) 前に、インラインで、任意の空白文字を含めることはできませんまたは次の空白以外のコンテンツ。</span><span class="sxs-lookup"><span data-stu-id="a2e76-320">For the items to be optimized, the characters that make up the `[children]` of the element information item must be in the canonical form of `xs:base64Binary` (see XSD-2, 3.2.16 base64Binary) and must not contain any white-space characters preceding, inline with, or following the non-white-space content.</span></span>

4. <span data-ttu-id="a2e76-321">元の SOAP エンベロープのコピーである XOP SOAP エンベロープを作成します。ただし、このコピーには、前の手順で特定した各要素情報項目の子が含まれます。これらの子は、以下の手順に従って構築された `xop:Include` 要素情報項目に置き換えられています。</span><span class="sxs-lookup"><span data-stu-id="a2e76-321">Create an XOP SOAP Envelope that is a copy of the Original SOAP Envelope, but with the children of each element information item identified in the previous step replaced by an `xop:Include` element information item constructed as follows:</span></span>

    1. <span data-ttu-id="a2e76-322">置換対象の文字を Base64 でエンコードされたデータとして処理することにより、バイナリ データに変換します。</span><span class="sxs-lookup"><span data-stu-id="a2e76-322">Transform the replaced characters into binary data by processing them as base64-encoded data.</span></span>

    2. <span data-ttu-id="a2e76-323">R3133 および R3134 の各要件を満たす Content-ID ヘッダーの一意の値を生成します。</span><span class="sxs-lookup"><span data-stu-id="a2e76-323">Generate a unique Content-ID header value that satisfies requirements R3133 and R3134.</span></span>

    3. <span data-ttu-id="a2e76-324">バイナリ値を使用して、Content-Transfer-Encoding MIME ヘッダーを生成します。</span><span class="sxs-lookup"><span data-stu-id="a2e76-324">Generate a Content-Transfer-Encoding MIME header with the value binary.</span></span>

    4. <span data-ttu-id="a2e76-325">最適化する要素情報項目 (新しく挿入する `xop:Include` 要素情報項目の [parent]) に、`xmime:contentType` 属性情報項目が含まれている場合、`xmime:contentType` 属性の値を使用して Content-Type MIME ヘッダーを生成します。</span><span class="sxs-lookup"><span data-stu-id="a2e76-325">If the element information item being optimized (the [parent] of the newly inserted `xop:Include` element information item) has an `xmime:contentType` attribute information item, generate a Content-Type MIME header with the value of the `xmime:contentType` attribute.</span></span>

    5. <span data-ttu-id="a2e76-326">Base64 として処理された置換対象文字からデコードされたバイナリ データ、Content-ID ヘッダー (手順 4b. で生成)、Content- Transfer-Encoding ヘッダー (手順 4c. で生成)、および Content-Type ヘッダー (手順 4d. で生成した場合) で構成されたコンテンツを含む、新しいバイナリ MIME パートを生成します。</span><span class="sxs-lookup"><span data-stu-id="a2e76-326">Generate a new binary MIME part with content formed by binary data decoded from the replaced characters processed as base64, Content-ID header from 4b, Content- Transfer-Encoding header from 4c, Content-Type header if generated in step 4d.</span></span>

    6. <span data-ttu-id="a2e76-327">値 cid: uri を持つ `href` 要素に `xop:Include` 属性を追加します。uri は、手順 4b. で生成した Content-ID ヘッダーの値から派生したものです。</span><span class="sxs-lookup"><span data-stu-id="a2e76-327">Add an `href` attribute to the `xop:Include` element with the value cid: uri derived from Content-ID header value generated in step 4b.</span></span> <span data-ttu-id="a2e76-328">囲んでいるを削除"\<"と">"文字を URL エスケープ文字列、およびプレフィックスを追加、残り`cid:`します。</span><span class="sxs-lookup"><span data-stu-id="a2e76-328">Remove the enclosing "\<" and ">" characters, URL-escape the remaining string, and add the prefix `cid:`.</span></span> <span data-ttu-id="a2e76-329">RFC1738 と RFC2396 に従って、次の最小限の文字セットをエスケープする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a2e76-329">The following minimum character set is required to be escaped by RFC1738 and RFC2396.</span></span> <span data-ttu-id="a2e76-330">その他の文字もエスケープすることができます。</span><span class="sxs-lookup"><span data-stu-id="a2e76-330">Other characters can be escaped.</span></span>

        ```
        Hexadecimal 00-1F , 7F, 20, "<" | ">" | "#" | "%" | <">
        "{" | "}" | "|" | "\" | "^" | "[" | "]" | "`" | "~" | "^"
        ```

5. <span data-ttu-id="a2e76-331">手順 4. の XOP SOAP エンベロープを含むルート MIME パートを作成します。</span><span class="sxs-lookup"><span data-stu-id="a2e76-331">Create a root MIME part with the XOP SOAP Envelope from step 4.</span></span>

6. <span data-ttu-id="a2e76-332">HTTP Content-Type ヘッダーなどの HTTP ヘッダーを書き込みます。</span><span class="sxs-lookup"><span data-stu-id="a2e76-332">Write the HTTP headers, including the HTTP Content-Type header.</span></span>

7. <span data-ttu-id="a2e76-333">MIME パッケージを書き込みます。</span><span class="sxs-lookup"><span data-stu-id="a2e76-333">Write the MIME package.</span></span>

#### <a name="processing-mtom-messages"></a><span data-ttu-id="a2e76-334">MTOM メッセージの処理</span><span class="sxs-lookup"><span data-stu-id="a2e76-334">Processing MTOM messages</span></span>
<span data-ttu-id="a2e76-335">MTOM メッセージの処理は、前述の「MTOM メッセージの生成」で説明したプロセスと正反対のプロセスになります。</span><span class="sxs-lookup"><span data-stu-id="a2e76-335">Processing of an MTOM message is the exact reverse of the process described in the preceding "Generating MTOM messages" section:</span></span>

1. <span data-ttu-id="a2e76-336">ルート MIME パートに Content-Type `application/xop+xml` が含まれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="a2e76-336">Ensure the root MIME part has the Content-Type `application/xop+xml`.</span></span>

2. <span data-ttu-id="a2e76-337">パッケージのルート MIME パートを XML ドキュメントとして解析して、SOAP エンベロープを作成します。</span><span class="sxs-lookup"><span data-stu-id="a2e76-337">Construct a SOAP Envelope by parsing the root MIME part of the package as an XML document.</span></span> <span data-ttu-id="a2e76-338">文字エンコーディングは、ルート MIME パートの Content-Type の `charset` パラメーターによって決まります。</span><span class="sxs-lookup"><span data-stu-id="a2e76-338">Character encoding is determined by the `charset` parameter of the Content-Type of the root MIME part.</span></span>

3. <span data-ttu-id="a2e76-339">作成した SOAP エンベロープ内の各要素情報項目について、以下の処理を行います。これらの要素情報項目には、[children] プロパティの唯一のメンバーとして、`xop:Include` 要素情報項目が含まれています。</span><span class="sxs-lookup"><span data-stu-id="a2e76-339">For each element information item in the constructed SOAP Envelope, which has, as the sole member of its [children] property, an `xop:Include` element information item:</span></span>

    1. <span data-ttu-id="a2e76-340">プレフィックス `cid:` を削除し、`@href` 要素の `xop:Include` 属性の値に含まれるすべての URI エスケープ シーケンスのエスケープを解除します (RFC 2396)。</span><span class="sxs-lookup"><span data-stu-id="a2e76-340">Remove the `cid:` prefix and unescape all URI-escape sequences (RFC 2396) in the value of the `@href` attribute of the `xop:Include` element.</span></span> <span data-ttu-id="a2e76-341">結果の文字列を囲む"\<"、">"。</span><span class="sxs-lookup"><span data-stu-id="a2e76-341">Enclose the result string in "\<", ">".</span></span>

    2. <span data-ttu-id="a2e76-342">Content-ID ヘッダーの値が手順 3a. で取得した文字列に一致する MIME パートを検索します。</span><span class="sxs-lookup"><span data-stu-id="a2e76-342">Locate the MIME part with the Content-ID header value that matches the string derived in step 3a.</span></span>

    3. <span data-ttu-id="a2e76-343">各項目の `xop:Include` プロパティに出現する `children` 要素情報項目を、手順 3b. で特定した MIME パートのエンティティ本体の正規 Base64 エンコーディング (XSD-2 セクション 3.2.16 の base64Binary を参照) を表す文字情報項目に置き換えます (`xop:Include` 要素情報項目をパッケージ パーツから再構築したデータに効率的に置き換えます)。</span><span class="sxs-lookup"><span data-stu-id="a2e76-343">Replace the `xop:Include` element information item that appears in the `children` property of each item with the character information items that represent the canonical base64 encoding (see XSD-2, 3.2.16 base64Binary) of the entity body of the MIME part identified in step 3b (effectively replace the `xop:Include` element information item with the data reconstructed from the package part).</span></span>

#### <a name="http-content-type-header"></a><span data-ttu-id="a2e76-344">HTTP Content-Type ヘッダー</span><span class="sxs-lookup"><span data-stu-id="a2e76-344">HTTP Content-Type Header</span></span>
<span data-ttu-id="a2e76-345">次は、SOAP 1.x MTOM でエンコードされたメッセージ、MTOM 仕様に記載された要件の HTTP Content-type ヘッダーの形式については、WCF の説明の一覧を示しますされ、MTOM および RFC 2387 から派生されます。</span><span class="sxs-lookup"><span data-stu-id="a2e76-345">The following is a list of WCF clarifications for the format of the HTTP Content-Type header of a SOAP 1.x MTOM-encoded message derived from requirements stated in the MTOM specification itself and are derived from MTOM and RFC 2387.</span></span>

- <span data-ttu-id="a2e76-346">R4131:マルチパート/関連 (大文字) の値とそのパラメーター、HTTP Content-type ヘッダーが必要です。</span><span class="sxs-lookup"><span data-stu-id="a2e76-346">R4131: An HTTP Content-Type header must have the value of multipart/related (case-insensitive) and its parameters.</span></span> <span data-ttu-id="a2e76-347">パラメーター名では、大文字と小文字は区別されません。</span><span class="sxs-lookup"><span data-stu-id="a2e76-347">Parameter names are case-insensitive.</span></span> <span data-ttu-id="a2e76-348">パラメーターの順序は重要ではありません。</span><span class="sxs-lookup"><span data-stu-id="a2e76-348">Parameter order is not significant.</span></span>

- <span data-ttu-id="a2e76-349">MIME メッセージの Content-Type ヘッダーのすべての Backus-Naur Form (BNF) については、RFC 2045 のセクション 5.1 に記載されています。</span><span class="sxs-lookup"><span data-stu-id="a2e76-349">The full Backus-Naur Form (BNF) of the Content-Type header for MIME messages is listed in RFC 2045, section 5.1.</span></span>

- <span data-ttu-id="a2e76-350">R4132:HTTP Content-type ヘッダーの値の型パラメーターが必要`application/xop+xml`二重引用符で囲まれています。</span><span class="sxs-lookup"><span data-stu-id="a2e76-350">R4132: An HTTP Content-Type header must have a type parameter with the value `application/xop+xml` enclosed in double quotation marks.</span></span>

<span data-ttu-id="a2e76-351">ほとんどの場合などの予約文字を含むすべての multipart/related メディアの種類のパラメーターは、テキストを監視は、二重引用符を使用するという要件は RFC 2387 に明示的ではありません"\@"または「/」の二重引用符必要があります。マークを付けます。</span><span class="sxs-lookup"><span data-stu-id="a2e76-351">While the requirement to use double quotation marks is not explicit in RFC 2387, the text observes that all of the multipart/related media type parameters most likely contain reserved characters like "\@" or "/" and therefore need double quotation marks.</span></span>

- <span data-ttu-id="a2e76-352">R4133:HTTP Content-type ヘッダーを SOAP を含む MIME パートの CONTENT-ID ヘッダーの値は、start パラメーターが必要 1.x エンベロープを二重引用符で囲まれています。</span><span class="sxs-lookup"><span data-stu-id="a2e76-352">R4133: An HTTP Content-Type header should have a start parameter with the value of the Content-ID header of the MIME part that contains the SOAP 1.x Envelope, enclosed in double quotation marks.</span></span> <span data-ttu-id="a2e76-353">start パラメーターを省略する場合は、最初の MIME パートに SOAP 1.x エンベロープを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="a2e76-353">If the start parameter is omitted, the first MIME part must contain the SOAP 1.x Envelope.</span></span>

- <span data-ttu-id="a2e76-354">R4134:SOAP 1.1 MTOM でエンコードされたメッセージの HTTP Content-type ヘッダーには、text/xml を二重引用符で囲まれた値の開始情報パラメーターを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="a2e76-354">R4134: An HTTP Content-Type header for a SOAP 1.1 MTOM encoded message must include the start-info parameter with the value of text/xml, enclosed in double quotation marks.</span></span>

- <span data-ttu-id="a2e76-355">R4135:SOAP 1.2 MTOM でエンコードされたメッセージの HTTP Content-type ヘッダーの値の開始情報パラメーターを含める必要があります`application/soap+xml`二重引用符で囲んで指定します。</span><span class="sxs-lookup"><span data-stu-id="a2e76-355">R4135: An HTTP Content-Type header for a SOAP 1.2 MTOM-encoded message must include the start-info parameter with the value of `application/soap+xml`, enclosed in double quotation marks.</span></span>

- <span data-ttu-id="a2e76-356">R4136:SOAP 1.x MTOM でエンコードされたメッセージの HTTP Content-type ヘッダーでは、RFC 2046 のセクション 5.1.1 で定義されている BNF MIME 境界に一致する (二重引用符で囲まれた) 値を境界パラメーターがあります。</span><span class="sxs-lookup"><span data-stu-id="a2e76-356">R4136: HTTP Content-Type header for a SOAP 1.x MTOM-encoded message must have the boundary parameter with the value (enclosed in double quotation marks) that matches the MIME boundary BNF defined in RFC 2046, section 5.1.1</span></span>

    ```
    boundary := 0*69<bchars> bcharsnospace 
    bchars := bcharsnospace / " " 
    bcharsnospace :=    DIGIT / ALPHA / "'" / "(" / ")" / "+" 
                        / "_" / "," / "-" / "." / "/" / ":" / "=" / "?"
    ```

     <span data-ttu-id="a2e76-357">次に例を示します。 </span><span class="sxs-lookup"><span data-stu-id="a2e76-357">Examples:</span></span>

     <span data-ttu-id="a2e76-358">正</span><span class="sxs-lookup"><span data-stu-id="a2e76-358">CORRECT</span></span>

    ```
    Content-Type: multipart/related; type="application/xop+xml";start=" <part0@tempuri.org>";boundary="uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=1";start-info="text/xml"
    ```

     <span data-ttu-id="a2e76-359">正</span><span class="sxs-lookup"><span data-stu-id="a2e76-359">CORRECT</span></span>

    ```
    Content-Type: Multipart/Related; type="application/xop+xml";start-info="text/xml";boundary="uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=1"
    ```

     <span data-ttu-id="a2e76-360">誤</span><span class="sxs-lookup"><span data-stu-id="a2e76-360">INCORRECT</span></span>

    ```
    Content-Type: Multipart/Related; type=application/xop+xml;start=" <part0@tempuri.org>";start-info="text/xml";boundary="uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=1" 
    ```

#### <a name="infoset-mime-part"></a><span data-ttu-id="a2e76-361">Infoset MIME パート</span><span class="sxs-lookup"><span data-stu-id="a2e76-361">Infoset MIME Part</span></span>
<span data-ttu-id="a2e76-362">SOAP 1.x エンベロープは、XOP MIME パッケージのルート部分としてカプセル化され、多くの場合、`infoset` パートと呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="a2e76-362">The SOAP 1.x Envelope is encapsulated as a root part of the XOP MIME package and is often called the `infoset` part.</span></span>

- <span data-ttu-id="a2e76-363">R4141:SOAP 1.x エンベロープと呼ばれる、XOP MIME パッケージのルート部分としてカプセル化する必要があります、`infoset`一部である HTTP Content-type から参照されています。</span><span class="sxs-lookup"><span data-stu-id="a2e76-363">R4141: The SOAP 1.x Envelope must be encapsulated as a root part of the XOP MIME package, called the `infoset` part and referenced from the HTTP Content-Type.</span></span>

- <span data-ttu-id="a2e76-364">R4142:SOAP`Infoset`部分は、次の MIME ヘッダーを含める必要があります: `Content-ID`、 `Content-Transfer-Encoding`、および`Content-Type`します。</span><span class="sxs-lookup"><span data-stu-id="a2e76-364">R4142: The SOAP `Infoset` part must include the following MIME headers: `Content-ID`, `Content-Transfer-Encoding`, and `Content-Type`.</span></span>

<span data-ttu-id="a2e76-365">Content-ID ヘッダーの形式は、RFC 2045 で次のように定義されています。</span><span class="sxs-lookup"><span data-stu-id="a2e76-365">The format of the Content-ID header is defined by RFC 2045 as</span></span>

```
"Content-ID" ":" msg-id
```

<span data-ttu-id="a2e76-366">ここで、`msg-id` は、RFC 2822 で次のように定義されています (RFC 2045 で参照されている RFC 822 は、RFC 2822 に置き換えられています)。</span><span class="sxs-lookup"><span data-stu-id="a2e76-366">where `msg-id` is defined in RFC 2822 (that supersedes RFC 822, referenced in RFC 2045) as:</span></span>

```
msg-id    =       [CFWS] "<" id-left "@" id-right ">" [CFWS]
```

<span data-ttu-id="a2e76-367">実質的に、電子メール アドレスで囲まれたと"\<"と">"。</span><span class="sxs-lookup"><span data-stu-id="a2e76-367">and is effectively an email address enclosed within "\<" and  ">".</span></span> <span data-ttu-id="a2e76-368">`[CFWS]` プレフィックスとサフィックスは、コメントを伝達するために RFC 2822 で追加されたものですが、相互運用性を維持する場合は、使用しないことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="a2e76-368">The `[CFWS]` prefix and suffix were added in RFC 2822 to carry comments and should not be used to preserve interoperability.</span></span>

<span data-ttu-id="a2e76-369">R4143:Infoset MIME パートの CONTENT-ID ヘッダーの値が従う必要があります`msg-id`RFC 2822 から運用、`[CFWS]`プレフィックスとサフィックスの部分を省略するとします。</span><span class="sxs-lookup"><span data-stu-id="a2e76-369">R4143: The value of the Content-ID header for the Infoset MIME part must follow `msg-id` production from RFC 2822 with the `[CFWS]` prefix and suffix parts omitted.</span></span>

<span data-ttu-id="a2e76-370">多くの MIME 実装で囲まれた値の要件を緩和する"\<"と">"電子メール アドレスを指定するために使用して`absoluteURI`で囲まれた"\<"、">"だけでなく、電子メール アドレス。</span><span class="sxs-lookup"><span data-stu-id="a2e76-370">A number of MIME implementations relaxed requirements for the value enclosed within "\<" and ">" to be an email address and used `absoluteURI` enclosed in "\<" , ">" in addition to the email address.</span></span> <span data-ttu-id="a2e76-371">このバージョンの WCF では、フォームの CONTENT-ID MIME ヘッダーの値を使用します。</span><span class="sxs-lookup"><span data-stu-id="a2e76-371">This version of WCF uses values of the Content-ID MIME header of the form:</span></span>

```
Content-ID: <http://tempuri.org/0> 
```

<span data-ttu-id="a2e76-372">R4144:MTOM プロセッサは CONTENT-ID ヘッダーの値に一致する、次の緩和を受け入れる必要があります`msg-id`します。</span><span class="sxs-lookup"><span data-stu-id="a2e76-372">R4144: MTOM processors should accept Content-ID header values that match the following relaxed `msg-id`.</span></span>

```
msg-id-relaxed =     [CFWS] "<" (absoluteURI | mail-address) ">" [CFWS]
mail-address   =     id-left "@" id-right
```

<span data-ttu-id="a2e76-373">MIME (RFC 2045) では、MIME パートのコンテンツのエンコーディングを伝達する Content-Transfer-Encoding ヘッダーを使用できます。</span><span class="sxs-lookup"><span data-stu-id="a2e76-373">MIME (RFC 2045) provides the Content-Transfer-Encoding header to communicate encoding of the content of the MIME part.</span></span> <span data-ttu-id="a2e76-374">Content-Transfer-Encoding に定義されている既定値は 7 ビットですが、これはほとんどの SOAP メッセージに適していません。そのため、Content-Transfer-Encoding ヘッダーの相互運用性を高めるために、以下を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="a2e76-374">The default defined for Content-Transfer-Encoding is 7-bit, which is not suitable for most SOAP messages, so the Content-Transfer-Encoding header is needed for greater interoperability:</span></span>

- <span data-ttu-id="a2e76-375">R4145:SOAP Infoset パートには、コンテンツ転送エンコード ヘッダーを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="a2e76-375">R4145: The SOAP Infoset part must contain the Content-Transfer-Encoding header.</span></span>

- <span data-ttu-id="a2e76-376">R4146:SOAP エンベロープの文字エンコーディングが utf-8 の場合、コンテンツ転送エンコード ヘッダーの値は 8 ビットである必要があります。</span><span class="sxs-lookup"><span data-stu-id="a2e76-376">R4146: If the SOAP Envelope character encoding is UTF-8, the value of the Content-Transfer-Encoding header must be 8-bit.</span></span>

- <span data-ttu-id="a2e76-377">R4147:SOAP エンベロープの文字エンコーディングが utf-16 の場合、コンテンツ転送エンコード ヘッダーの値はバイナリである必要があります。</span><span class="sxs-lookup"><span data-stu-id="a2e76-377">R4147: If the SOAP Envelope character encoding is UTF-16, the value of the Content-Transfer-Encoding header must be binary.</span></span>

- <span data-ttu-id="a2e76-378">以下の要件は、XOP のセクション 5 に基づいています。</span><span class="sxs-lookup"><span data-stu-id="a2e76-378">According to [XOP] section 5,</span></span>

- <span data-ttu-id="a2e76-379">R4148:SOAP1.1 Infoset パートに Content-type ヘッダーのメディアの種類のアプリケーション/xop + xml を含める必要があり、パラメーターの入力"text/xml"および文字セットを =</span><span class="sxs-lookup"><span data-stu-id="a2e76-379">R4148: SOAP1.1 Infoset part must contain Content-Type header with media type application/xop+xml and parameters type="text/xml" and charset</span></span>

    ```
    Content-Type: application/xop+xml;
                  charset=utf-8;type="text/xml"
    ```

- <span data-ttu-id="a2e76-380">R4149:SOAP 1.2 Infoset パートは、メディアの種類のコンテンツ タイプ ヘッダーを含める必要があります`application/xop+xml`パラメーター入力 ="`application/soap+xml`"と`charset`します。</span><span class="sxs-lookup"><span data-stu-id="a2e76-380">R4149: The SOAP 1.2 Infoset part must contain the Content-Type header with media type `application/xop+xml` and parameters type="`application/soap+xml`" and `charset`.</span></span>

    ```
    Content-Type: application/xop+xml;
                  charset=utf-8;type="application/soap+xml"
    ```

     <span data-ttu-id="a2e76-381">XOP では、`charset` の `application/xop+xml` パラメーターは省略可能と定義されていますが、`charset` メディア タイプの `text/xml` パラメーターについては、BP 1.1 の要件と同様の相互運用性が必要とされます。</span><span class="sxs-lookup"><span data-stu-id="a2e76-381">While XOP defines the `charset` parameter for `application/xop+xml` to be optional, it is needed for interoperability similar to the BP 1.1 requirement on the `charset` parameter for the `text/xml` media type.</span></span>

- <span data-ttu-id="a2e76-382">R41410:`type`と`charset`パラメーターは、SOAP 1.x Infoset パートの Content-type ヘッダーに存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a2e76-382">R41410: The `type` and `charset` parameters must be present on the Content-Type header of the SOAP 1.x Infoset part.</span></span>

#### <a name="wcf-endpoint-support-for-mtom"></a><span data-ttu-id="a2e76-383">WCF エンドポイントによる MTOM のサポート</span><span class="sxs-lookup"><span data-stu-id="a2e76-383">WCF Endpoint Support for MTOM</span></span>
<span data-ttu-id="a2e76-384">MTOM の目的は、SOAP メッセージをエンコードして、Base64 でエンコードされたデータを最適化することです。</span><span class="sxs-lookup"><span data-stu-id="a2e76-384">The purpose of MTOM is to encode a SOAP message to optimize base64-encoded data.</span></span> <span data-ttu-id="a2e76-385">制約は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="a2e76-385">The following is a list of constraints:</span></span>

- <span data-ttu-id="a2e76-386">R4151:Base64 でエンコードされたデータを含む任意の要素情報項目を最適化することがあります。</span><span class="sxs-lookup"><span data-stu-id="a2e76-386">R4151: Any element information item that contains base64-encoded data may be optimized.</span></span>

- <span data-ttu-id="a2e76-387">B4152:WCF では、base64 でエンコードされたデータを含むことが 1,024 バイトの長さを超える要素情報項目を最適化します。</span><span class="sxs-lookup"><span data-stu-id="a2e76-387">B4152: WCF optimizes element information items that contain base64-encoded data and exceed 1024 bytes in length.</span></span>

<span data-ttu-id="a2e76-388">MTOM を使用するように構成の WCF エンドポイントでは、MTOM でエンコードされたメッセージは常に送信します。</span><span class="sxs-lookup"><span data-stu-id="a2e76-388">A WCF endpoint configured to use MTOM will always send MTOM-encoded messages.</span></span> <span data-ttu-id="a2e76-389">必要な条件を満たすパートがない場合でも、メッセージは MTOM でエンコードされます (SOAP エンベロープを含む単一の MIME パートを持つ MIME パッケージとしてシリアル化されます)。</span><span class="sxs-lookup"><span data-stu-id="a2e76-389">Even if no parts meet the required criteria, the message is still MTOM-encoded (serialized as a MIME package with a single MIME part containing the SOAP envelope).</span></span>

### <a name="ws-policy-assertion-for-mtom"></a><span data-ttu-id="a2e76-390">MTOM の WS-Policy アサーション</span><span class="sxs-lookup"><span data-stu-id="a2e76-390">WS-Policy Assertion for MTOM</span></span>
<span data-ttu-id="a2e76-391">WCF では、次のポリシー アサーションを使用して、エンドポイントで MTOM の使用方法を示します。</span><span class="sxs-lookup"><span data-stu-id="a2e76-391">WCF uses the following policy assertion to indicate MTOM usage by endpoint:</span></span>

```xml
<wsoma:OptimizedMimeSerialization ... />
```

- <span data-ttu-id="a2e76-392">R4211:上記のポリシー アサーションには、エンドポイント ポリシー サブジェクトがあり、MTOM を使用して、エンドポイントから送受信されたすべてのメッセージを最適化する必要がありますを指定します。</span><span class="sxs-lookup"><span data-stu-id="a2e76-392">R4211: The preceding policy assertion has an Endpoint Policy Subject and specifies that all messages sent to and received from the endpoint must be optimized using MTOM.</span></span>

- <span data-ttu-id="a2e76-393">B4212:WCF エンドポイントが、対応する関連付けられているポリシーに MTOM ポリシー アサーションを追加します MTOM の最適化を使用するように構成、`wsdl:binding`します。</span><span class="sxs-lookup"><span data-stu-id="a2e76-393">B4212: When configured to use MTOM optimization, an WCF endpoint adds an MTOM Policy assertion to the policy attached to the corresponding `wsdl:binding`.</span></span>

### <a name="composition-with-ws-security"></a><span data-ttu-id="a2e76-394">WS-Security によるコンポジション</span><span class="sxs-lookup"><span data-stu-id="a2e76-394">Composition with WS-Security</span></span>
<span data-ttu-id="a2e76-395">MTOM は、次のような実現するエンコード メカニズム`text/xml`および WCF バイナリ XML。</span><span class="sxs-lookup"><span data-stu-id="a2e76-395">MTOM is an encoding mechanism that is similar to `text/xml` and WCF Binary XML.</span></span> <span data-ttu-id="a2e76-396">MTOM は、WS-Security とその他の WS-\* プロトコルによる自然なコンポジションを提供します。WS-Security を使用してセキュリティ保護されたメッセージは、MTOM を使用して最適化できます。</span><span class="sxs-lookup"><span data-stu-id="a2e76-396">MTOM offers natural composition with WS-Security and other WS-\* protocols: a message secured using WS-Security can be optimized using MTOM.</span></span>

### <a name="examples"></a><span data-ttu-id="a2e76-397">使用例</span><span class="sxs-lookup"><span data-stu-id="a2e76-397">Examples</span></span>

#### <a name="wcf-soap-11-message-encoded-using-mtom"></a><span data-ttu-id="a2e76-398">MTOM を使用してエンコードされた WCF SOAP 1.1 メッセージ</span><span class="sxs-lookup"><span data-stu-id="a2e76-398">WCF SOAP 1.1 Message Encoded Using MTOM</span></span>

```
POST http://131.107.72.15/Mtom/svc/service.svc/Soap11MtomUTF8 HTTP/1.1
SOAPAction: "http://xmlsoap.org/echoBinaryAsString"
Content-Type: multipart/related;type="application/xop+xml";
              start="<http://tempuri.org/0>";start-info="text/xml";
       boundary="uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=1"
Host: 131.107.72.15
Content-Length: 1501
--uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=1
Content-ID: <http://tempuri.org/0>
Content-Transfer-Encoding: 8bit
Content-Type: application/xop+xml;charset=utf-8;type="text/xml"
<s:Envelope xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Body>
    <EchoBinaryAsString xmlns="http://xmlsoap.org/Ping">
      <array>
        <xop:Include
         href="cid:http%3A%2F%2Ftempuri.org%2F1%2F632618206521093670"
         xmlns:xop="http://www.w3.org/2004/08/xop/include"/>
      </array>
    </EchoBinaryAsString>
  </s:Body>
</s:Envelope>
--uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=1
Content-ID: <http://tempuri.org/1/632618206521093670>
Content-Transfer-Encoding: binary
Content-Type: application/octet-stream
…Binary Content..
--uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=1
```

#### <a name="wcf-secure-soap-12-message-encoded-using-mtom"></a><span data-ttu-id="a2e76-399">MTOM を使用してエンコードされた WCF Secure SOAP 1.2 メッセージ</span><span class="sxs-lookup"><span data-stu-id="a2e76-399">WCF Secure SOAP 1.2 Message Encoded Using MTOM</span></span>
<span data-ttu-id="a2e76-400">この例では、WS-Security を使用して保護されたメッセージを MTOM と SOAP 1.2 を使用してエンコードします。</span><span class="sxs-lookup"><span data-stu-id="a2e76-400">In this example, a message is encoded using MTOM and SOAP 1.2 that is protected using WS-Security.</span></span> <span data-ttu-id="a2e76-401">エンコーディングの対象として特定されたバイナリ部分は、`BinarySecurityToken`、暗号化された署名に対応する `CipherValue` の `EncryptedData`、および暗号化された本文の内容です。</span><span class="sxs-lookup"><span data-stu-id="a2e76-401">The binary parts identified for encoding are the contents of the `BinarySecurityToken`, `CipherValue` of the `EncryptedData` corresponding to the encrypted signature and encrypted body.</span></span> <span data-ttu-id="a2e76-402">なお、`CipherValue`の`EncryptedKey`特定されなかった最適化のため、WCF、その長さが 1024 バイト未満であるためです。</span><span class="sxs-lookup"><span data-stu-id="a2e76-402">Note that the `CipherValue` of the `EncryptedKey` was not identified for optimization by WCF, because its length is less then 1024 bytes.</span></span>

```
POST http://131.107.72.15/Mtom/service.svc/Soap12MtomSecureSignEncrypt HTTP/1.1
Content-Type: multipart/related; type="application/xop+xml";
              start="<http://tempuri.org/0>";
            boundary="uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=3";
              start-info="application/soap+xml"; 
              action="http://xmlsoap.org/echoBinaryAsString"
Host: 131.107.72.15
Content-Length: 1941
--uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=3
Content-ID: <http://tempuri.org/0>
Content-Transfer-Encoding: 8bit
Content-Type: application/xop+xml;charset=utf-8;type="application/soap+xml"
<s:Envelope xmlns:s="http://schemas.xmlsoap.org/soap/envelope/" xmlns:u="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-utility-1.0.xsd">
  <s:Header>
    <o:Security s:mustUnderstand="1" xmlns:o="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd">
      <u:Timestamp u:Id="uuid-4d4ee765-5717-4d53-9ac9-99bddc07df6c-5">
        <u:Created>2005-09-09T06:57:32.488Z</u:Created>
        <u:Expires>2005-09-09T07:02:32.488Z</u:Expires>
      </u:Timestamp>
      <o:BinarySecurityToken u:Id="uuid-4d4ee765-5717-4d53-9ac9-99bddc07df6c-2" ValueType="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-x509-token-profile-1.0#X509v3" EncodingType="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-soap-message-security-1.0#Base64Binary">
        <xop:Include href="cid:http%3A%2F%2Ftempuri.org%2F1%2F632618206525089430" xmlns:xop="http://www.w3.org/2004/08/xop/include"/>
      </o:BinarySecurityToken>
      <e:EncryptedKey Id="_1" xmlns:e="http://www.w3.org/2001/04/xmlenc#">
        <e:EncryptionMethod Algorithm="http://www.w3.org/2001/04/xmlenc#rsa-oaep-mgf1p"/>
        <KeyInfo xmlns="http://www.w3.org/2000/09/xmldsig#">
          <o:SecurityTokenReference>
            <o:KeyIdentifier ValueType="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-x509-token-profile-1.0#X509SubjectKeyIdentifier">Xeg55vRyK3ZhAEhEf+YT0z986L0=</o:KeyIdentifier>
          </o:SecurityTokenReference>
        </KeyInfo>
        <e:CipherData>          <e:CipherValue>oQfpxwT8/SAGyZQzKE2b4yO6dXuQj7pwJ+5CGL3Rf7C06bQ5ttMoQ9GLJcQYkXTzin+WwHEgs5bj5ml9HKTW9QAU5JJ6lksdymmQvWP5ZtGPBVchO4sofEGoCKmBiZL/DYS/cnbzgnc/3a6NYnc10y2fWGaGLiqa00zijAw7o0Y=</e:CipherValue>
        </e:CipherData>
      </e:EncryptedKey>
      <c:DerivedKeyToken u:Id="_2" xmlns:c="http://schemas.xmlsoap.org/ws/2005/02/sc">
        <o:SecurityTokenReference>
          <o:Reference URI="#_1"/>
        </o:SecurityTokenReference>
        <c:Nonce>OrEPRX7fISIS4sXYWPMv3g==</c:Nonce>
      </c:DerivedKeyToken>
      <e:ReferenceList xmlns:e="http://www.w3.org/2001/04/xmlenc#">
        <e:DataReference URI="#_3"/>
        <e:DataReference URI="#_4"/>
      </e:ReferenceList>
      <e:EncryptedData Id="_4" Type="http://www.w3.org/2001/04/xmlenc#Element" xmlns:e="http://www.w3.org/2001/04/xmlenc#">
        <e:EncryptionMethod Algorithm="http://www.w3.org/2001/04/xmlenc#aes256-cbc"/>
        <KeyInfo xmlns="http://www.w3.org/2000/09/xmldsig#">
          <o:SecurityTokenReference>
            <o:Reference URI="#_2"/>
          </o:SecurityTokenReference>
        </KeyInfo>
        <e:CipherData>
          <e:CipherValue>
            <xop:Include href="cid:http%3A%2F%2Ftempuri.org%2F2%2F632618206525089430" xmlns:xop="http://www.w3.org/2004/08/xop/include"/>
          </e:CipherValue>
        </e:CipherData>
      </e:EncryptedData>
    </o:Security>
  </s:Header>
  <s:Body u:Id="_0">
    <e:EncryptedData Id="_3" Type="http://www.w3.org/2001/04/xmlenc#Content" xmlns:e="http://www.w3.org/2001/04/xmlenc#">
      <e:EncryptionMethod Algorithm="http://www.w3.org/2001/04/xmlenc#aes256-cbc"/>
      <KeyInfo xmlns="http://www.w3.org/2000/09/xmldsig#">
        <o:SecurityTokenReference xmlns:o="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd">
          <o:Reference URI="#_2"/>
        </o:SecurityTokenReference>
      </KeyInfo>
      <e:CipherData>
        <e:CipherValue>
          <xop:Include href="cid:http%3A%2F%2Ftempuri.org%2F3%2F632618206525089430" xmlns:xop="http://www.w3.org/2004/08/xop/include"/>
        </e:CipherValue>
      </e:CipherData>
    </e:EncryptedData>
  </s:Body>
</s:Envelope>
--uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=3
Content-ID: <http://tempuri.org/1/632618206525089430>
Content-Transfer-Encoding: binary
Content-Type: application/octet-stream
...Binary content of BinarySecurityToken - X509 Certificate...
--uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=3
Content-ID: <http://tempuri.org/2/632618206525089430>
Content-Transfer-Encoding: binary
Content-Type: application/octet-stream
...Binary serialization of the encrypted primary signature...
--uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=3
Content-ID: <http://tempuri.org/3/632618206525089430>
Content-Transfer-Encoding: binary
Content-Type: application/octet-stream
...Binary serialization of the encrypted Body...
--uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=3--
```
