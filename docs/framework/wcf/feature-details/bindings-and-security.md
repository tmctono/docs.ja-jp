---
title: バインディングとセキュリティ
description: セキュリティニーズに合った適切なバインドを選択する方法について説明します。 WCF に含まれるシステム指定のバインディングを使用すると、WCF アプリケーションをすばやくプログラミングできます。
ms.date: 03/30/2017
helpviewer_keywords:
- bindings [WCF], security
- WCF security
- Windows Communication Foundation, security
- bindings [WCF]
ms.assetid: 4de03dd3-968a-4e65-af43-516e903d7f95
ms.openlocfilehash: 86b9a1d7b0c772a308b9f059bb31c1f489635300
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/15/2020
ms.locfileid: "90559403"
---
# <a name="bindings-and-security"></a><span data-ttu-id="1599f-104">バインディングとセキュリティ</span><span class="sxs-lookup"><span data-stu-id="1599f-104">Bindings and Security</span></span>

<span data-ttu-id="1599f-105">Windows Communication Foundation (WCF) に含まれるシステム指定のバインディングを使用すると、WCF アプリケーションをすばやくプログラミングできます。</span><span class="sxs-lookup"><span data-stu-id="1599f-105">The system-provided bindings included with Windows Communication Foundation (WCF) offer a quick way to program WCF applications.</span></span> <span data-ttu-id="1599f-106">1 つの例外を除き、すべてのバインディングにはセキュリティ スキームが含まれており、既定で有効になっています。</span><span class="sxs-lookup"><span data-stu-id="1599f-106">With one exception, all the bindings have a default security scheme enabled.</span></span> <span data-ttu-id="1599f-107">ここでは、セキュリティ ニーズに適した正しいバインディングの選択方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="1599f-107">This topic helps you select the right binding for your security needs.</span></span>

<span data-ttu-id="1599f-108">WCF セキュリティの概要については、「 [セキュリティの概要](security-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1599f-108">For an overview of WCF security, see [Security Overview](security-overview.md).</span></span> <span data-ttu-id="1599f-109">バインディングを使用した WCF のプログラミングの詳細については、「 [Wcf セキュリティのプログラミング](programming-wcf-security.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1599f-109">For more information about programming WCF using bindings, see [Programming WCF Security](programming-wcf-security.md).</span></span>

<span data-ttu-id="1599f-110">バインディングを既に選択している場合は、セキュリティ [動作](security-behaviors-in-wcf.md)のセキュリティに関連付けられている実行時の動作の詳細を確認できます。</span><span class="sxs-lookup"><span data-stu-id="1599f-110">If you have already selected a binding, you can find out more about the run-time behaviors that are associated with security in [Security Behaviors](security-behaviors-in-wcf.md).</span></span>

<span data-ttu-id="1599f-111">セキュリティ機能のなかには、システム指定のバインディングを使用してプログラミングできないものがあります。</span><span class="sxs-lookup"><span data-stu-id="1599f-111">Some security functions are not programmable using the system-provided bindings.</span></span> <span data-ttu-id="1599f-112">カスタムバインドを使用した詳細な制御については、「 [カスタムバインドを使用したセキュリティ機能](security-capabilities-with-custom-bindings.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1599f-112">For more control using a custom binding, see [Security Capabilities with Custom Bindings](security-capabilities-with-custom-bindings.md).</span></span>

## <a name="security-functions-of-bindings"></a><span data-ttu-id="1599f-113">バインディングのセキュリティ機能</span><span class="sxs-lookup"><span data-stu-id="1599f-113">Security Functions of Bindings</span></span>

<span data-ttu-id="1599f-114">WCF には、ほとんどのニーズを満たすシステム指定のバインディングが多数用意されています。</span><span class="sxs-lookup"><span data-stu-id="1599f-114">WCF includes a number of system-provided bindings that meet most needs.</span></span> <span data-ttu-id="1599f-115">特定のバインディングでは不十分な場合は、カスタム バインディングを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="1599f-115">If a particular binding does not suffice, you can also create a custom binding.</span></span> <span data-ttu-id="1599f-116">システム指定のバインディングの一覧については、「 [システム指定のバインディング](../system-provided-bindings.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1599f-116">For a list of system-provided bindings, see [System-Provided Bindings](../system-provided-bindings.md).</span></span> <span data-ttu-id="1599f-117">カスタムバインディングの詳細については、「 [カスタムバインド](../extending/custom-bindings.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1599f-117">For more information about custom bindings, see [Custom Bindings](../extending/custom-bindings.md).</span></span>

<span data-ttu-id="1599f-118">WCF のすべてのバインドには、API として、構成ファイルで使用される XML 要素として、という2つの形式があります。</span><span class="sxs-lookup"><span data-stu-id="1599f-118">Every binding in WCF has two forms: as an API and as an XML element used in a configuration file.</span></span> <span data-ttu-id="1599f-119">たとえば、 `WSHttpBinding` (API) には、に対応するがあり [\<wsHttpBinding>](../../configure-apps/file-schema/wcf/wshttpbinding.md) ます。</span><span class="sxs-lookup"><span data-stu-id="1599f-119">For example, the `WSHttpBinding` (API) has a counterpart in the [\<wsHttpBinding>](../../configure-apps/file-schema/wcf/wshttpbinding.md).</span></span>

<span data-ttu-id="1599f-120">以下のセクションでは、各バインディングについて両方の形式を示し、セキュリティ機能の概要を説明します。</span><span class="sxs-lookup"><span data-stu-id="1599f-120">The following section lists both forms for each binding and summarizes the security features.</span></span>

### <a name="basichttp"></a><span data-ttu-id="1599f-121">BasicHttp</span><span class="sxs-lookup"><span data-stu-id="1599f-121">BasicHttp</span></span>

<span data-ttu-id="1599f-122">コードでは、クラスを使用し <xref:System.ServiceModel.BasicHttpBinding> ます。構成では、を使用し [\<basicHttpBinding>](../../configure-apps/file-schema/wcf/basichttpbinding.md) ます。</span><span class="sxs-lookup"><span data-stu-id="1599f-122">In code, use the <xref:System.ServiceModel.BasicHttpBinding> class; in configuration, use the [\<basicHttpBinding>](../../configure-apps/file-schema/wcf/basichttpbinding.md).</span></span>

<span data-ttu-id="1599f-123">このバインディングは、次のような既存のさまざまなテクノロジと共に使用できるようにデザインされています。</span><span class="sxs-lookup"><span data-stu-id="1599f-123">This binding is designed for use with a range of existing technologies, including the following:</span></span>

- <span data-ttu-id="1599f-124">ASP.NET Web サービス (ASMX) Version 1</span><span class="sxs-lookup"><span data-stu-id="1599f-124">ASP.NET Web services (ASMX), version 1.</span></span>

- <span data-ttu-id="1599f-125">Web サービス拡張 (WSE) アプリケーション</span><span class="sxs-lookup"><span data-stu-id="1599f-125">Web Service Enhancements (WSE) applications.</span></span>

- <span data-ttu-id="1599f-126">Web Services 相互運用性 (WS-I) 仕様 () で定義されている基本プロファイル <https://go.microsoft.com/fwlink/?LinkId=38955> 。</span><span class="sxs-lookup"><span data-stu-id="1599f-126">Basic Profile as defined in the Web Services Interoperability (WS-I) specification (<https://go.microsoft.com/fwlink/?LinkId=38955>).</span></span>

- <span data-ttu-id="1599f-127">WS-I で定義されている基本セキュリティ プロファイル</span><span class="sxs-lookup"><span data-stu-id="1599f-127">Basic security profile as defined in WS-I.</span></span>

<span data-ttu-id="1599f-128">既定では、このバインディングはセキュリティで保護されません。</span><span class="sxs-lookup"><span data-stu-id="1599f-128">By default, this binding is not secure.</span></span> <span data-ttu-id="1599f-129">ASMX サービスと相互運用するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="1599f-129">It is designed to interoperate with ASMX services.</span></span> <span data-ttu-id="1599f-130">セキュリティを有効にした場合、このバインディングは、インターネット インフォメーション サービス (IIS: Internet Information Services) のセキュリティ機構 (基本認証、ダイジェスト、Windows 統合セキュリティなど) とシームレスに相互運用できるように設計されています。</span><span class="sxs-lookup"><span data-stu-id="1599f-130">When security is enabled, the binding is designed for seamless interoperation with Internet Information Services (IIS) security mechanisms, such as basic authentication, digest, and integrated Windows security.</span></span> <span data-ttu-id="1599f-131">詳細については、「 [トランスポートセキュリティの概要](transport-security-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1599f-131">For more information, see [Transport Security Overview](transport-security-overview.md).</span></span> <span data-ttu-id="1599f-132">このバインディングでは、以下をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="1599f-132">This binding supports the following:</span></span>

- <span data-ttu-id="1599f-133">HTTPS トランスポート セキュリティ</span><span class="sxs-lookup"><span data-stu-id="1599f-133">HTTPS transport security.</span></span>

- <span data-ttu-id="1599f-134">HTTP 基本認証</span><span class="sxs-lookup"><span data-stu-id="1599f-134">HTTP basic authentication.</span></span>

- <span data-ttu-id="1599f-135">WS-Security。</span><span class="sxs-lookup"><span data-stu-id="1599f-135">WS-Security.</span></span>

<span data-ttu-id="1599f-136">詳細については、「<xref:System.ServiceModel.BasicHttpSecurity>」、「<xref:System.ServiceModel.BasicHttpMessageSecurity>」、「<xref:System.ServiceModel.BasicHttpMessageCredentialType>」、および「<xref:System.ServiceModel.BasicHttpSecurityMode>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1599f-136">For more information, see <xref:System.ServiceModel.BasicHttpSecurity>, <xref:System.ServiceModel.BasicHttpMessageSecurity>, <xref:System.ServiceModel.BasicHttpMessageCredentialType>, and <xref:System.ServiceModel.BasicHttpSecurityMode>.</span></span>

### <a name="wshttpbinding"></a><span data-ttu-id="1599f-137">WSHttpBinding</span><span class="sxs-lookup"><span data-stu-id="1599f-137">WSHttpBinding</span></span>

<span data-ttu-id="1599f-138">コードでは、クラスを使用し <xref:System.ServiceModel.WSHttpBinding> ます。構成では、を使用し [\<wsHttpBinding>](../../configure-apps/file-schema/wcf/wshttpbinding.md) ます。</span><span class="sxs-lookup"><span data-stu-id="1599f-138">In code, use the <xref:System.ServiceModel.WSHttpBinding> class; in configuration, use the [\<wsHttpBinding>](../../configure-apps/file-schema/wcf/wshttpbinding.md).</span></span>

<span data-ttu-id="1599f-139">既定では、このバインディングは WS-Security 仕様を実装しており、WS-\* 仕様を実装するサービスとの相互運用性があります。</span><span class="sxs-lookup"><span data-stu-id="1599f-139">By default, this binding implements the WS-Security specification and provides interoperability with services that implement the WS-\* specifications.</span></span> <span data-ttu-id="1599f-140">次のセキュリティをサポートします。</span><span class="sxs-lookup"><span data-stu-id="1599f-140">It supports the following:</span></span>

- <span data-ttu-id="1599f-141">HTTPS トランスポート セキュリティ</span><span class="sxs-lookup"><span data-stu-id="1599f-141">HTTPS transport security.</span></span>

- <span data-ttu-id="1599f-142">WS-Security。</span><span class="sxs-lookup"><span data-stu-id="1599f-142">WS-Security.</span></span>

- <span data-ttu-id="1599f-143">SOAP メッセージ資格情報セキュリティを使用した、HTTPS トランスポート保護による呼び出し元の認証。</span><span class="sxs-lookup"><span data-stu-id="1599f-143">HTTPS transport protection with SOAP message credential security for authenticating the caller.</span></span>

<span data-ttu-id="1599f-144">詳細については、「」、「」、「」、「」、および「」を参照してください <xref:System.ServiceModel.WSHttpSecurity> <xref:System.ServiceModel.MessageSecurityOverHttp> <xref:System.ServiceModel.MessageCredentialType> <xref:System.ServiceModel.SecurityMode> <xref:System.ServiceModel.HttpTransportSecurity> <xref:System.ServiceModel.HttpClientCredentialType> <xref:System.ServiceModel.HttpProxyCredentialType> 。</span><span class="sxs-lookup"><span data-stu-id="1599f-144">For more information, see <xref:System.ServiceModel.WSHttpSecurity>, <xref:System.ServiceModel.MessageSecurityOverHttp>, <xref:System.ServiceModel.MessageCredentialType>, <xref:System.ServiceModel.SecurityMode>, <xref:System.ServiceModel.HttpTransportSecurity>, <xref:System.ServiceModel.HttpClientCredentialType>, and <xref:System.ServiceModel.HttpProxyCredentialType>.</span></span>

### <a name="wsdualhttpbinding"></a><span data-ttu-id="1599f-145">WSDualHttpBinding</span><span class="sxs-lookup"><span data-stu-id="1599f-145">WSDualHttpBinding</span></span>

<span data-ttu-id="1599f-146">コードでは、クラスを使用し <xref:System.ServiceModel.WSDualHttpBinding> ます。構成では、を使用し [\<wsDualHttpBinding>](../../configure-apps/file-schema/wcf/wsdualhttpbinding.md) ます。</span><span class="sxs-lookup"><span data-stu-id="1599f-146">In code, use the <xref:System.ServiceModel.WSDualHttpBinding> class; in configuration, use the [\<wsDualHttpBinding>](../../configure-apps/file-schema/wcf/wsdualhttpbinding.md).</span></span>

<span data-ttu-id="1599f-147">このバインディングは、双方向サービス アプリケーションを有効にするために設計されています。</span><span class="sxs-lookup"><span data-stu-id="1599f-147">This binding is designed to enable duplex service applications.</span></span> <span data-ttu-id="1599f-148">このバインディングは、メッセージ ベースの転送セキュリティ用に WS-Security 仕様を実装しています。</span><span class="sxs-lookup"><span data-stu-id="1599f-148">This binding implements the WS-Security specification for message-based transfer security.</span></span> <span data-ttu-id="1599f-149">トランスポート セキュリティは使用できません。</span><span class="sxs-lookup"><span data-stu-id="1599f-149">Transport security is not available.</span></span> <span data-ttu-id="1599f-150">既定では、次の機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="1599f-150">By default, it provides the following features:</span></span>

- <span data-ttu-id="1599f-151">WS-ReliableMessaging を実装して信頼性を確保します。</span><span class="sxs-lookup"><span data-stu-id="1599f-151">Implements WS-Reliable Messaging for reliability.</span></span>

- <span data-ttu-id="1599f-152">WS-Security を実装して転送セキュリティおよび認証を実現します。</span><span class="sxs-lookup"><span data-stu-id="1599f-152">Implements WS-Security for transfer security and authentication.</span></span>

- <span data-ttu-id="1599f-153">HTTP を使用してメッセージを配信します。</span><span class="sxs-lookup"><span data-stu-id="1599f-153">Uses HTTP for message delivery.</span></span>

- <span data-ttu-id="1599f-154">テキスト/XML メッセージ エンコーディングを使用します。</span><span class="sxs-lookup"><span data-stu-id="1599f-154">Uses text/XML message encoding.</span></span>

 <span data-ttu-id="1599f-155">バインディングで WS-Security (メッセージ層セキュリティ) を使用すると、次のパラメーターを構成できるようになります。</span><span class="sxs-lookup"><span data-stu-id="1599f-155">Using WS-Security (message-layer security), the binding allows you to configure the following parameters:</span></span>

- <span data-ttu-id="1599f-156">暗号アルゴリズムを決定するためのセキュリティ アルゴリズム スイート</span><span class="sxs-lookup"><span data-stu-id="1599f-156">The security algorithm suite to determine the cryptographic algorithm.</span></span>

- <span data-ttu-id="1599f-157">以下を行うためのバインディング オプション</span><span class="sxs-lookup"><span data-stu-id="1599f-157">Binding options for the following:</span></span>

  - <span data-ttu-id="1599f-158">クライアントで帯域外で使用可能なサービス資格情報の提供</span><span class="sxs-lookup"><span data-stu-id="1599f-158">Providing service credentials available out-of-band at the client.</span></span>

  - <span data-ttu-id="1599f-159">チャネル セットアップの一部としてサービスからネゴシエートされるサービス資格情報の提供</span><span class="sxs-lookup"><span data-stu-id="1599f-159">Providing service credentials negotiated from the service as part of channel setup.</span></span>

<span data-ttu-id="1599f-160">詳細については、次のトピックを参照してください。 <xref:System.ServiceModel.WSDualHttpSecurity> および <xref:System.ServiceModel.WSDualHttpSecurityMode></span><span class="sxs-lookup"><span data-stu-id="1599f-160">For more information, see <xref:System.ServiceModel.WSDualHttpSecurity> and <xref:System.ServiceModel.WSDualHttpSecurityMode>.</span></span>

### <a name="nettcpbinding"></a><span data-ttu-id="1599f-161">NetTcpBinding</span><span class="sxs-lookup"><span data-stu-id="1599f-161">NetTcpBinding</span></span>

<span data-ttu-id="1599f-162">コードでは、クラスを使用し <xref:System.ServiceModel.NetTcpBinding> ます。構成では、を使用し [\<netTcpBinding>](../../configure-apps/file-schema/wcf/nettcpbinding.md) ます。</span><span class="sxs-lookup"><span data-stu-id="1599f-162">In code, use the <xref:System.ServiceModel.NetTcpBinding> class; in configuration, use the [\<netTcpBinding>](../../configure-apps/file-schema/wcf/nettcpbinding.md).</span></span>

<span data-ttu-id="1599f-163">このバインディングは複数のコンピューター間での通信に最適化されています。</span><span class="sxs-lookup"><span data-stu-id="1599f-163">This binding is optimized for cross-machine communication.</span></span> <span data-ttu-id="1599f-164">既定では、次の特性があります。</span><span class="sxs-lookup"><span data-stu-id="1599f-164">By default, it has the following characteristics:</span></span>

- <span data-ttu-id="1599f-165">トランスポート層セキュリティを実装します。</span><span class="sxs-lookup"><span data-stu-id="1599f-165">Implements transport-layer security.</span></span>

- <span data-ttu-id="1599f-166">Windows セキュリティを利用して、転送セキュリティと認証を確保します。</span><span class="sxs-lookup"><span data-stu-id="1599f-166">Leverages Windows security for transfer security and authentication.</span></span>

- <span data-ttu-id="1599f-167">トランスポートに TCP を使用します。</span><span class="sxs-lookup"><span data-stu-id="1599f-167">Uses TCP for transport.</span></span>

- <span data-ttu-id="1599f-168">バイナリ メッセージのエンコードを実装します。</span><span class="sxs-lookup"><span data-stu-id="1599f-168">Implements binary message encoding.</span></span>

- <span data-ttu-id="1599f-169">WS-ReliableMessaging を実装します。</span><span class="sxs-lookup"><span data-stu-id="1599f-169">Implements WS-Reliable Messaging.</span></span>

<span data-ttu-id="1599f-170">選択できる方法は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="1599f-170">Options include the following:</span></span>

- <span data-ttu-id="1599f-171">メッセージ層セキュリティ (WS-Security を使用)</span><span class="sxs-lookup"><span data-stu-id="1599f-171">Message-layer security (using WS-Security).</span></span>

- <span data-ttu-id="1599f-172">メッセージ資格情報を使用するトランスポート セキュリティ (TLS (Transport Layer Security) over TCP によって実現される機密性と整合性、および WS-Security によって提供される承認に使用する資格情報)</span><span class="sxs-lookup"><span data-stu-id="1599f-172">Transport security with message credential—confidentiality and integrity provided by Transport Layer Security (TLS) over TCP, and credentials for authorization provided by WS-Security.</span></span>

<span data-ttu-id="1599f-173">詳細については、「」、「」、「」、および「」を参照してください <xref:System.ServiceModel.NetTcpSecurity> <xref:System.ServiceModel.TcpTransportSecurity> <xref:System.ServiceModel.TcpClientCredentialType> <xref:System.ServiceModel.MessageSecurityOverTcp> <xref:System.ServiceModel.MessageCredentialType> 。</span><span class="sxs-lookup"><span data-stu-id="1599f-173">For more information, see <xref:System.ServiceModel.NetTcpSecurity>, <xref:System.ServiceModel.TcpTransportSecurity>, <xref:System.ServiceModel.TcpClientCredentialType>, <xref:System.ServiceModel.MessageSecurityOverTcp>, and <xref:System.ServiceModel.MessageCredentialType>.</span></span>

### <a name="netnamedpipebinding"></a><span data-ttu-id="1599f-174">NetNamedPipeBinding</span><span class="sxs-lookup"><span data-stu-id="1599f-174">NetNamedPipeBinding</span></span>

<span data-ttu-id="1599f-175">コードでは、クラスを使用し <xref:System.ServiceModel.NetNamedPipeBinding> ます。構成では、を使用し [\<netNamedPipeBinding>](../../configure-apps/file-schema/wcf/netnamedpipebinding.md) ます。</span><span class="sxs-lookup"><span data-stu-id="1599f-175">In code, use the <xref:System.ServiceModel.NetNamedPipeBinding> class; in configuration, use the [\<netNamedPipeBinding>](../../configure-apps/file-schema/wcf/netnamedpipebinding.md).</span></span>

<span data-ttu-id="1599f-176">このバインディングは、(通常では同じコンピューター上の) 複数プロセス間の通信に最適化されています。</span><span class="sxs-lookup"><span data-stu-id="1599f-176">This binding is optimized for cross-process communication (usually on the same machine).</span></span> <span data-ttu-id="1599f-177">既定では、このバインディングには次の特性があります。</span><span class="sxs-lookup"><span data-stu-id="1599f-177">By default, this binding has the following characteristics:</span></span>

- <span data-ttu-id="1599f-178">トランスポート セキュリティを使用して、メッセージ転送と認証を実現します。</span><span class="sxs-lookup"><span data-stu-id="1599f-178">Uses transport security for message transfer and authentication.</span></span>

- <span data-ttu-id="1599f-179">名前付きパイプを使用してメッセージを配信します。</span><span class="sxs-lookup"><span data-stu-id="1599f-179">Uses named pipes for message delivery.</span></span>

- <span data-ttu-id="1599f-180">バイナリ メッセージのエンコードを実装します。</span><span class="sxs-lookup"><span data-stu-id="1599f-180">Implements binary message encoding.</span></span>

- <span data-ttu-id="1599f-181">暗号化とメッセージの署名を使用します。</span><span class="sxs-lookup"><span data-stu-id="1599f-181">Encryption and message signing.</span></span>

<span data-ttu-id="1599f-182">選択できる方法は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="1599f-182">Options include the following:</span></span>

- <span data-ttu-id="1599f-183">Windows セキュリティを使用した認証</span><span class="sxs-lookup"><span data-stu-id="1599f-183">Authentication using Windows security.</span></span>

<span data-ttu-id="1599f-184">詳細については、「<xref:System.ServiceModel.NetNamedPipeSecurity>「<xref:System.ServiceModel.NetNamedPipeSecurityMode>および「<xref:System.ServiceModel.NamedPipeTransportSecurity>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1599f-184">For more information, see <xref:System.ServiceModel.NetNamedPipeSecurity>, <xref:System.ServiceModel.NetNamedPipeSecurityMode>, and <xref:System.ServiceModel.NamedPipeTransportSecurity>.</span></span>

### <a name="msmqintegrationbinding"></a><span data-ttu-id="1599f-185">MsmqIntegrationBinding</span><span class="sxs-lookup"><span data-stu-id="1599f-185">MsmqIntegrationBinding</span></span>

<span data-ttu-id="1599f-186">コードでは、クラスを使用し <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding> ます。構成では、を使用し [\<msmqIntegrationBinding>](../../configure-apps/file-schema/wcf/msmqintegrationbinding.md) ます。</span><span class="sxs-lookup"><span data-stu-id="1599f-186">In code, use the <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding> class; in configuration, use the [\<msmqIntegrationBinding>](../../configure-apps/file-schema/wcf/msmqintegrationbinding.md).</span></span>

<span data-ttu-id="1599f-187">このバインディングは、wcf 以外の Microsoft Message Queuing (MSMQ) エンドポイントと相互運用する WCF クライアントおよびサービスを作成するために最適化されています。</span><span class="sxs-lookup"><span data-stu-id="1599f-187">This binding is optimized for creating WCF clients and services that interoperate with non-WCF Microsoft Message Queuing (MSMQ) endpoints.</span></span>

<span data-ttu-id="1599f-188">既定では、このバインディングはトランスポート セキュリティを使用し、次のセキュリティ特性があります。</span><span class="sxs-lookup"><span data-stu-id="1599f-188">By default, this binding uses transport security and provides the following security characteristics:</span></span>

- <span data-ttu-id="1599f-189">セキュリティは無効 (なし) にできます。</span><span class="sxs-lookup"><span data-stu-id="1599f-189">Security can be disabled (None).</span></span>

- <span data-ttu-id="1599f-190">MSMQ トランスポート セキュリティ (トランスポート)。</span><span class="sxs-lookup"><span data-stu-id="1599f-190">MSMQ transport security (Transport).</span></span>

<span data-ttu-id="1599f-191">詳細については、次のトピックを参照してください。 <xref:System.ServiceModel.NetMsmqSecurity> および <xref:System.ServiceModel.NetMsmqSecurityMode></span><span class="sxs-lookup"><span data-stu-id="1599f-191">For more information, see <xref:System.ServiceModel.NetMsmqSecurity> and <xref:System.ServiceModel.NetMsmqSecurityMode>.</span></span>

### <a name="netmsmqbinding"></a><span data-ttu-id="1599f-192">NetMsmqBinding</span><span class="sxs-lookup"><span data-stu-id="1599f-192">NetMsmqBinding</span></span>

<span data-ttu-id="1599f-193">コードでは、クラスを使用し <xref:System.ServiceModel.NetMsmqBinding> ます。構成では、を使用し [\<netMsmqBinding>](../../configure-apps/file-schema/wcf/netmsmqbinding.md) ます。</span><span class="sxs-lookup"><span data-stu-id="1599f-193">In code, use the <xref:System.ServiceModel.NetMsmqBinding> class; in configuration, use the [\<netMsmqBinding>](../../configure-apps/file-schema/wcf/netmsmqbinding.md).</span></span>

<span data-ttu-id="1599f-194">このバインディングは、MSMQ のキューに置かれたメッセージのサポートを必要とする WCF サービスを作成するときに使用することを意図しています。</span><span class="sxs-lookup"><span data-stu-id="1599f-194">This binding is intended for use when creating WCF services that require MSMQ queued message support.</span></span>

<span data-ttu-id="1599f-195">既定では、このバインディングはトランスポート セキュリティを使用し、次のセキュリティ特性があります。</span><span class="sxs-lookup"><span data-stu-id="1599f-195">By default, this binding uses transport security and provides the following security characteristics:</span></span>

- <span data-ttu-id="1599f-196">セキュリティは無効 (なし) にできます。</span><span class="sxs-lookup"><span data-stu-id="1599f-196">Security can be disabled (None).</span></span>

- <span data-ttu-id="1599f-197">MSMQ トランスポート セキュリティ (トランスポート)。</span><span class="sxs-lookup"><span data-stu-id="1599f-197">MSMQ transport security (Transport).</span></span>

- <span data-ttu-id="1599f-198">SOAP に基づくメッセージ セキュリティ (メッセージ)。</span><span class="sxs-lookup"><span data-stu-id="1599f-198">SOAP-based message security (Message).</span></span>

- <span data-ttu-id="1599f-199">トランスポート セキュリティとメッセージ セキュリティ (両方)。</span><span class="sxs-lookup"><span data-stu-id="1599f-199">Simultaneous Transport and Message security (Both).</span></span>

- <span data-ttu-id="1599f-200">サポートされるクライアント資格情報の種類 : なし、Windows、UserName、証明書、IssuedToken。</span><span class="sxs-lookup"><span data-stu-id="1599f-200">Client Credential Types supported: None, Windows, UserName, Certificate, IssuedToken.</span></span>

<span data-ttu-id="1599f-201"><xref:System.ServiceModel.MessageCredentialType.Certificate> 資格情報は、セキュリティ モードが <xref:System.ServiceModel.NetMsmqSecurityMode.Both> または <xref:System.ServiceModel.NetMsmqSecurityMode.Message> に設定されている場合にのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="1599f-201">The <xref:System.ServiceModel.MessageCredentialType.Certificate> credential is supported only when the security mode is set to either <xref:System.ServiceModel.NetMsmqSecurityMode.Both> or <xref:System.ServiceModel.NetMsmqSecurityMode.Message>.</span></span>

<span data-ttu-id="1599f-202">詳細については、次のトピックを参照してください。 <xref:System.ServiceModel.MessageSecurityOverMsmq> および <xref:System.ServiceModel.MsmqTransportSecurity></span><span class="sxs-lookup"><span data-stu-id="1599f-202">For more information, see <xref:System.ServiceModel.MessageSecurityOverMsmq> and <xref:System.ServiceModel.MsmqTransportSecurity>.</span></span>

### <a name="wsfederationhttpbinding"></a><span data-ttu-id="1599f-203">WSFederationHttpBinding</span><span class="sxs-lookup"><span data-stu-id="1599f-203">WSFederationHttpBinding</span></span>

<span data-ttu-id="1599f-204">コードでは、クラスを使用し <xref:System.ServiceModel.WSFederationHttpBinding> ます。構成では、を使用し [\<wsFederationHttpBinding>](../../configure-apps/file-schema/wcf/wsfederationhttpbinding.md) ます。</span><span class="sxs-lookup"><span data-stu-id="1599f-204">In code, use the <xref:System.ServiceModel.WSFederationHttpBinding> class; in configuration, use the [\<wsFederationHttpBinding>](../../configure-apps/file-schema/wcf/wsfederationhttpbinding.md).</span></span>

<span data-ttu-id="1599f-205">既定では、このバインディングは WS-Security (メッセージ層セキュリティ) を使用します。</span><span class="sxs-lookup"><span data-stu-id="1599f-205">By default, this binding uses WS-Security (message-layer security).</span></span>

<span data-ttu-id="1599f-206">詳細については、「 [Federation](federation.md)、」、および「」を参照してください <xref:System.ServiceModel.WSFederationHttpSecurity> <xref:System.ServiceModel.WSFederationHttpSecurityMode> 。</span><span class="sxs-lookup"><span data-stu-id="1599f-206">For more information, see [Federation](federation.md), <xref:System.ServiceModel.WSFederationHttpSecurity>, and <xref:System.ServiceModel.WSFederationHttpSecurityMode>.</span></span>

## <a name="custom-bindings"></a><span data-ttu-id="1599f-207">カスタム バインディング</span><span class="sxs-lookup"><span data-stu-id="1599f-207">Custom Bindings</span></span>

<span data-ttu-id="1599f-208">システム指定のバインディングがいずれも要件を満たさない場合は、カスタム セキュリティ バインド要素を使用してカスタム バインディングを作成できます。</span><span class="sxs-lookup"><span data-stu-id="1599f-208">If none of the system-provided bindings meets you requirements, you can create a custom binding with a custom security binding element.</span></span> <span data-ttu-id="1599f-209">詳細については、「 [カスタムバインドを使用したセキュリティ機能](security-capabilities-with-custom-bindings.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1599f-209">For more information, see [Security Capabilities with Custom Bindings](security-capabilities-with-custom-bindings.md).</span></span>

## <a name="binding-choices"></a><span data-ttu-id="1599f-210">バインディングの選択肢</span><span class="sxs-lookup"><span data-stu-id="1599f-210">Binding Choices</span></span>

<span data-ttu-id="1599f-211">次の表は、セキュリティ モード設定で提供される機能をまとめたものです。つまり、セキュリティ モードを `Transport`、`Message`、または `TransportWithMessageCredential` に設定したときに使用できる機能の一覧です。</span><span class="sxs-lookup"><span data-stu-id="1599f-211">The following table summarizes the features offered in the security mode setting, that is, it lists the features available when the security mode is set to `Transport`, `Message`, or `TransportWithMessageCredential`.</span></span> <span data-ttu-id="1599f-212">アプリケーションで必要なセキュリティ機能を決定するときに、この表を参考にしてください。</span><span class="sxs-lookup"><span data-stu-id="1599f-212">Use this table to help you find the security features your application requires.</span></span>

|<span data-ttu-id="1599f-213">設定</span><span class="sxs-lookup"><span data-stu-id="1599f-213">Setting</span></span>|<span data-ttu-id="1599f-214">特徴</span><span class="sxs-lookup"><span data-stu-id="1599f-214">Features</span></span>|
|-------------|--------------|
|<span data-ttu-id="1599f-215">トランスポート</span><span class="sxs-lookup"><span data-stu-id="1599f-215">Transport</span></span>|<span data-ttu-id="1599f-216">サーバー認証</span><span class="sxs-lookup"><span data-stu-id="1599f-216">Server authentication</span></span><br /><br /> <span data-ttu-id="1599f-217">クライアント認証</span><span class="sxs-lookup"><span data-stu-id="1599f-217">Client authentication</span></span><br /><br /> <span data-ttu-id="1599f-218">Point-to-Point のセキュリティ</span><span class="sxs-lookup"><span data-stu-id="1599f-218">Point-to-point security</span></span><br /><br /> <span data-ttu-id="1599f-219">相互運用性</span><span class="sxs-lookup"><span data-stu-id="1599f-219">Interoperability</span></span><br /><br /> <span data-ttu-id="1599f-220">ハードウェアの高速化</span><span class="sxs-lookup"><span data-stu-id="1599f-220">Hardware acceleration</span></span><br /><br /> <span data-ttu-id="1599f-221">高スループット</span><span class="sxs-lookup"><span data-stu-id="1599f-221">High throughput</span></span><br /><br /> <span data-ttu-id="1599f-222">セキュリティで保護されたファイアウォール</span><span class="sxs-lookup"><span data-stu-id="1599f-222">Secure firewall</span></span><br /><br /> <span data-ttu-id="1599f-223">待ち時間の長いアプリケーション</span><span class="sxs-lookup"><span data-stu-id="1599f-223">High-latency applications</span></span><br /><br /> <span data-ttu-id="1599f-224">複数のホップでの再暗号化</span><span class="sxs-lookup"><span data-stu-id="1599f-224">Re-encryption across multiple hops</span></span>|
|<span data-ttu-id="1599f-225">メッセージ</span><span class="sxs-lookup"><span data-stu-id="1599f-225">Message</span></span>|<span data-ttu-id="1599f-226">サーバー認証</span><span class="sxs-lookup"><span data-stu-id="1599f-226">Server authentication</span></span><br /><br /> <span data-ttu-id="1599f-227">クライアント認証</span><span class="sxs-lookup"><span data-stu-id="1599f-227">Client authentication</span></span><br /><br /> <span data-ttu-id="1599f-228">エンドツーエンドのセキュリティ</span><span class="sxs-lookup"><span data-stu-id="1599f-228">End-to-end security</span></span><br /><br /> <span data-ttu-id="1599f-229">相互運用性</span><span class="sxs-lookup"><span data-stu-id="1599f-229">Interoperability</span></span><br /><br /> <span data-ttu-id="1599f-230">多様なクレーム</span><span class="sxs-lookup"><span data-stu-id="1599f-230">Rich claims</span></span><br /><br /> <span data-ttu-id="1599f-231">フェデレーション</span><span class="sxs-lookup"><span data-stu-id="1599f-231">Federation</span></span><br /><br /> <span data-ttu-id="1599f-232">多要素認証</span><span class="sxs-lookup"><span data-stu-id="1599f-232">Multifactor authentication</span></span><br /><br /> <span data-ttu-id="1599f-233">カスタム トークン</span><span class="sxs-lookup"><span data-stu-id="1599f-233">Custom tokens</span></span><br /><br /> <span data-ttu-id="1599f-234">Notary/Timestamp サービス</span><span class="sxs-lookup"><span data-stu-id="1599f-234">Notary/timestamp service</span></span><br /><br /> <span data-ttu-id="1599f-235">待ち時間の長いアプリケーション</span><span class="sxs-lookup"><span data-stu-id="1599f-235">High-latency applications</span></span><br /><br /> <span data-ttu-id="1599f-236">メッセージ署名の永続化</span><span class="sxs-lookup"><span data-stu-id="1599f-236">Persistence of message signatures</span></span>|
|<span data-ttu-id="1599f-237">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="1599f-237">TransportWithMessageCredential</span></span>|<span data-ttu-id="1599f-238">サーバー認証</span><span class="sxs-lookup"><span data-stu-id="1599f-238">Server authentication</span></span><br /><br /> <span data-ttu-id="1599f-239">クライアント認証</span><span class="sxs-lookup"><span data-stu-id="1599f-239">Client authentication</span></span><br /><br /> <span data-ttu-id="1599f-240">Point-to-Point のセキュリティ</span><span class="sxs-lookup"><span data-stu-id="1599f-240">Point-to-point security</span></span><br /><br /> <span data-ttu-id="1599f-241">相互運用性</span><span class="sxs-lookup"><span data-stu-id="1599f-241">Interoperability</span></span><br /><br /> <span data-ttu-id="1599f-242">ハードウェアの高速化</span><span class="sxs-lookup"><span data-stu-id="1599f-242">Hardware acceleration</span></span><br /><br /> <span data-ttu-id="1599f-243">高スループット</span><span class="sxs-lookup"><span data-stu-id="1599f-243">High throughput</span></span><br /><br /> <span data-ttu-id="1599f-244">多様なクライアント クレーム</span><span class="sxs-lookup"><span data-stu-id="1599f-244">Rich client claims</span></span><br /><br /> <span data-ttu-id="1599f-245">フェデレーション</span><span class="sxs-lookup"><span data-stu-id="1599f-245">Federation</span></span><br /><br /> <span data-ttu-id="1599f-246">多要素認証</span><span class="sxs-lookup"><span data-stu-id="1599f-246">Multifactor authentication</span></span><br /><br /> <span data-ttu-id="1599f-247">カスタム トークン</span><span class="sxs-lookup"><span data-stu-id="1599f-247">Custom tokens</span></span><br /><br /> <span data-ttu-id="1599f-248">セキュリティで保護されたファイアウォール</span><span class="sxs-lookup"><span data-stu-id="1599f-248">Secure firewall</span></span><br /><br /> <span data-ttu-id="1599f-249">待ち時間の長いアプリケーション</span><span class="sxs-lookup"><span data-stu-id="1599f-249">High-latency applications</span></span><br /><br /> <span data-ttu-id="1599f-250">複数のホップでの再暗号化</span><span class="sxs-lookup"><span data-stu-id="1599f-250">Re-encryption across multiple hops</span></span>|

<span data-ttu-id="1599f-251">さまざまなモード設定をサポートするバインディングを次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="1599f-251">The following table lists the bindings that support the various mode settings.</span></span> <span data-ttu-id="1599f-252">サービス エンドポイントを作成するときは、使用するバインディングをこの表から選択してください。</span><span class="sxs-lookup"><span data-stu-id="1599f-252">Select a binding from the table to use to create your service endpoint.</span></span>

|<span data-ttu-id="1599f-253">バインド</span><span class="sxs-lookup"><span data-stu-id="1599f-253">Binding</span></span>|<span data-ttu-id="1599f-254">トランスポート モードのサポート</span><span class="sxs-lookup"><span data-stu-id="1599f-254">Transport mode support</span></span>|<span data-ttu-id="1599f-255">メッセージ モードのサポート</span><span class="sxs-lookup"><span data-stu-id="1599f-255">Message mode support</span></span>|<span data-ttu-id="1599f-256">TransportWithMessageCredential のサポート</span><span class="sxs-lookup"><span data-stu-id="1599f-256">TransportWithMessageCredential support</span></span>|
|-------------|----------------------------|--------------------------|--------------------------------------------|
|`BasicHttpBinding`|<span data-ttu-id="1599f-257">はい</span><span class="sxs-lookup"><span data-stu-id="1599f-257">Yes</span></span>|<span data-ttu-id="1599f-258">はい</span><span class="sxs-lookup"><span data-stu-id="1599f-258">Yes</span></span>|<span data-ttu-id="1599f-259">はい</span><span class="sxs-lookup"><span data-stu-id="1599f-259">Yes</span></span>|
|`WSHttpBinding`|<span data-ttu-id="1599f-260">はい</span><span class="sxs-lookup"><span data-stu-id="1599f-260">Yes</span></span>|<span data-ttu-id="1599f-261">はい</span><span class="sxs-lookup"><span data-stu-id="1599f-261">Yes</span></span>|<span data-ttu-id="1599f-262">はい</span><span class="sxs-lookup"><span data-stu-id="1599f-262">Yes</span></span>|
|`WSDualHttpBinding`|<span data-ttu-id="1599f-263">いいえ</span><span class="sxs-lookup"><span data-stu-id="1599f-263">No</span></span>|<span data-ttu-id="1599f-264">はい</span><span class="sxs-lookup"><span data-stu-id="1599f-264">Yes</span></span>|<span data-ttu-id="1599f-265">いいえ</span><span class="sxs-lookup"><span data-stu-id="1599f-265">No</span></span>|
|`NetTcpBinding`|<span data-ttu-id="1599f-266">はい</span><span class="sxs-lookup"><span data-stu-id="1599f-266">Yes</span></span>|<span data-ttu-id="1599f-267">はい</span><span class="sxs-lookup"><span data-stu-id="1599f-267">Yes</span></span>|<span data-ttu-id="1599f-268">はい</span><span class="sxs-lookup"><span data-stu-id="1599f-268">Yes</span></span>|
|`NetNamedPipeBinding`|<span data-ttu-id="1599f-269">はい</span><span class="sxs-lookup"><span data-stu-id="1599f-269">Yes</span></span>|<span data-ttu-id="1599f-270">いいえ</span><span class="sxs-lookup"><span data-stu-id="1599f-270">No</span></span>|<span data-ttu-id="1599f-271">いいえ</span><span class="sxs-lookup"><span data-stu-id="1599f-271">No</span></span>|
|`NetMsmqBinding`|<span data-ttu-id="1599f-272">はい</span><span class="sxs-lookup"><span data-stu-id="1599f-272">Yes</span></span>|<span data-ttu-id="1599f-273">はい</span><span class="sxs-lookup"><span data-stu-id="1599f-273">Yes</span></span>|<span data-ttu-id="1599f-274">いいえ</span><span class="sxs-lookup"><span data-stu-id="1599f-274">No</span></span>|
|`MsmqIntegrationBinding`|<span data-ttu-id="1599f-275">はい</span><span class="sxs-lookup"><span data-stu-id="1599f-275">Yes</span></span>|<span data-ttu-id="1599f-276">いいえ</span><span class="sxs-lookup"><span data-stu-id="1599f-276">No</span></span>|<span data-ttu-id="1599f-277">いいえ</span><span class="sxs-lookup"><span data-stu-id="1599f-277">No</span></span>|
|`wsFederationHttpBinding`|<span data-ttu-id="1599f-278">いいえ</span><span class="sxs-lookup"><span data-stu-id="1599f-278">No</span></span>|<span data-ttu-id="1599f-279">はい</span><span class="sxs-lookup"><span data-stu-id="1599f-279">Yes</span></span>|<span data-ttu-id="1599f-280">はい</span><span class="sxs-lookup"><span data-stu-id="1599f-280">Yes</span></span>|

## <a name="transport-credentials-in-bindings"></a><span data-ttu-id="1599f-281">バインディングにおけるトランスポート資格情報</span><span class="sxs-lookup"><span data-stu-id="1599f-281">Transport Credentials in Bindings</span></span>

<span data-ttu-id="1599f-282">トランスポート セキュリティ モードで `BasicHttpBinding` または `WSHttpBinding` を使用するときに使用できるクライアント資格情報の種類を、次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="1599f-282">The following table lists the client credential types available when using either `BasicHttpBinding` or `WSHttpBinding` in transport security mode.</span></span>

|<span data-ttu-id="1599f-283">種類</span><span class="sxs-lookup"><span data-stu-id="1599f-283">Type</span></span>|<span data-ttu-id="1599f-284">説明</span><span class="sxs-lookup"><span data-stu-id="1599f-284">Description</span></span>|
|----------|-----------------|
|<span data-ttu-id="1599f-285">なし</span><span class="sxs-lookup"><span data-stu-id="1599f-285">None</span></span>|<span data-ttu-id="1599f-286">クライアントが資格情報を提示する必要がないことを指定します。</span><span class="sxs-lookup"><span data-stu-id="1599f-286">Specifies that the client does not need to present any credential.</span></span> <span data-ttu-id="1599f-287">匿名クライアントであると解釈されます。</span><span class="sxs-lookup"><span data-stu-id="1599f-287">This translates to an anonymous client.</span></span>|
|<span data-ttu-id="1599f-288">Basic</span><span class="sxs-lookup"><span data-stu-id="1599f-288">Basic</span></span>|<span data-ttu-id="1599f-289">基本認証です。</span><span class="sxs-lookup"><span data-stu-id="1599f-289">Basic authentication.</span></span> <span data-ttu-id="1599f-290">詳細については、「RFC 2617 – HTTP 認証: 基本認証とダイジェスト認証」を参照してください <https://go.microsoft.com/fwlink/?LinkId=84023> 。</span><span class="sxs-lookup"><span data-stu-id="1599f-290">For more information, see RFC 2617 – HTTP Authentication: Basic and Digest Authentication, available at <https://go.microsoft.com/fwlink/?LinkId=84023>.</span></span>|
|<span data-ttu-id="1599f-291">ダイジェスト</span><span class="sxs-lookup"><span data-stu-id="1599f-291">Digest</span></span>|<span data-ttu-id="1599f-292">ダイジェスト認証です。</span><span class="sxs-lookup"><span data-stu-id="1599f-292">Digest authentication.</span></span> <span data-ttu-id="1599f-293">詳細については、「RFC 2617 – HTTP 認証: 基本認証とダイジェスト認証」を参照してください <https://go.microsoft.com/fwlink/?LinkId=84023> 。</span><span class="sxs-lookup"><span data-stu-id="1599f-293">For more information, see RFC 2617 – HTTP Authentication: Basic and Digest Authentication, available at <https://go.microsoft.com/fwlink/?LinkId=84023>.</span></span>|
|<span data-ttu-id="1599f-294">NTLM</span><span class="sxs-lookup"><span data-stu-id="1599f-294">NTLM</span></span>|<span data-ttu-id="1599f-295">NTLM (NT LAN Manager) 認証です。</span><span class="sxs-lookup"><span data-stu-id="1599f-295">NT LAN Manager (NTLM) authentication.</span></span>|
|<span data-ttu-id="1599f-296">Windows</span><span class="sxs-lookup"><span data-stu-id="1599f-296">Windows</span></span>|<span data-ttu-id="1599f-297">Windows 認証です。</span><span class="sxs-lookup"><span data-stu-id="1599f-297">Windows authentication.</span></span>|
|<span data-ttu-id="1599f-298">Certificate</span><span class="sxs-lookup"><span data-stu-id="1599f-298">Certificate</span></span>|<span data-ttu-id="1599f-299">証明書を使用して実行される認証です。</span><span class="sxs-lookup"><span data-stu-id="1599f-299">Authentication performed using a certificate.</span></span>|
|<span data-ttu-id="1599f-300">IssuedToken</span><span class="sxs-lookup"><span data-stu-id="1599f-300">IssuedToken</span></span>|<span data-ttu-id="1599f-301">サービスが、Security Token Service または CardSpace によって発行されたトークンを使用して、クライアントの認証を要求できるようにします。</span><span class="sxs-lookup"><span data-stu-id="1599f-301">Allows the service to require that the client be authenticated using a token issued by a security token service or by CardSpace.</span></span> <span data-ttu-id="1599f-302">詳細については、「 [フェデレーションと発行済みトークン](federation-and-issued-tokens.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1599f-302">For more information, see [Federation and Issued Tokens](federation-and-issued-tokens.md).</span></span>|

### <a name="message-client-credentials-in-bindings"></a><span data-ttu-id="1599f-303">バインディングにおけるメッセージ クライアント資格情報</span><span class="sxs-lookup"><span data-stu-id="1599f-303">Message Client Credentials in Bindings</span></span>

<span data-ttu-id="1599f-304">メッセージ セキュリティ モードでバインディングを使用するときに使用できるクライアント資格情報の種類を次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="1599f-304">The following table lists the client credential types available when using a binding in Message security mode.</span></span>

|<span data-ttu-id="1599f-305">種類</span><span class="sxs-lookup"><span data-stu-id="1599f-305">Type</span></span>|<span data-ttu-id="1599f-306">説明</span><span class="sxs-lookup"><span data-stu-id="1599f-306">Description</span></span>|
|----------|-----------------|
|<span data-ttu-id="1599f-307">なし</span><span class="sxs-lookup"><span data-stu-id="1599f-307">None</span></span>|<span data-ttu-id="1599f-308">サービスが匿名クライアントとやり取りを行うことが可能になります。</span><span class="sxs-lookup"><span data-stu-id="1599f-308">Allows the service to interact with anonymous clients.</span></span>|
|<span data-ttu-id="1599f-309">Windows</span><span class="sxs-lookup"><span data-stu-id="1599f-309">Windows</span></span>|<span data-ttu-id="1599f-310">Windows 資格情報の認証済みコンテキストの制御下で SOAP メッセージ交換を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="1599f-310">Allows SOAP message exchanges to be made under the authenticated context of a Windows credential.</span></span>|
|<span data-ttu-id="1599f-311">UserName</span><span class="sxs-lookup"><span data-stu-id="1599f-311">UserName</span></span>|<span data-ttu-id="1599f-312">サービスが、ユーザー名資格情報を使用したクライアントの認証を要求できるようにします。</span><span class="sxs-lookup"><span data-stu-id="1599f-312">Allows the service to require that the client be authenticated using a user name credential.</span></span> <span data-ttu-id="1599f-313">セキュリティモードがに設定されている場合 `TransportWithMessageCredential` 、WCF では、パスワードダイジェストの送信や、パスワードを使用したキーの派生、およびメッセージモードセキュリティのためのこのようなキーの使用はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="1599f-313">Note that when the security mode is set to `TransportWithMessageCredential`, WCF does not support sending a password digest or deriving keys using password and using such keys for Message mode security.</span></span> <span data-ttu-id="1599f-314">そのため、ユーザー名の資格情報を使用する場合、WCF はトランスポートがセキュリティで保護されることを強制します。</span><span class="sxs-lookup"><span data-stu-id="1599f-314">As such, WCF enforces that the transport is secured when using user name credentials.</span></span>|
|<span data-ttu-id="1599f-315">Certificate</span><span class="sxs-lookup"><span data-stu-id="1599f-315">Certificate</span></span>|<span data-ttu-id="1599f-316">証明書を使用したクライアントの認証を、サービスで要求することが可能になります。</span><span class="sxs-lookup"><span data-stu-id="1599f-316">Allows the service to require that the client be authenticated using a certificate.</span></span>|
|<span data-ttu-id="1599f-317">IssuedToken</span><span class="sxs-lookup"><span data-stu-id="1599f-317">IssuedToken</span></span>|<span data-ttu-id="1599f-318">サービスは、セキュリティ トークン サービスを使用してカスタム トークンを提供できます。</span><span class="sxs-lookup"><span data-stu-id="1599f-318">Allows the service to use a security token service to supply a custom token.</span></span>|

## <a name="see-also"></a><span data-ttu-id="1599f-319">関連項目</span><span class="sxs-lookup"><span data-stu-id="1599f-319">See also</span></span>

- [<span data-ttu-id="1599f-320">セキュリティの概要</span><span class="sxs-lookup"><span data-stu-id="1599f-320">Security Overview</span></span>](security-overview.md)
- [<span data-ttu-id="1599f-321">サービスおよびクライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="1599f-321">Securing Services and Clients</span></span>](securing-services-and-clients.md)
- [<span data-ttu-id="1599f-322">資格情報の種類の選択</span><span class="sxs-lookup"><span data-stu-id="1599f-322">Selecting a Credential Type</span></span>](selecting-a-credential-type.md)
- [<span data-ttu-id="1599f-323">カスタム バインディングを使用したセキュリティ機能</span><span class="sxs-lookup"><span data-stu-id="1599f-323">Security Capabilities with Custom Bindings</span></span>](security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="1599f-324">セキュリティ動作</span><span class="sxs-lookup"><span data-stu-id="1599f-324">Security Behaviors</span></span>](security-behaviors-in-wcf.md)
- <span data-ttu-id="1599f-325">[Windows Server AppFabric のセキュリティ モデル](/previous-versions/appfabric/ee677202(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="1599f-325">[Security Model for Windows Server App Fabric](/previous-versions/appfabric/ee677202(v=azure.10))</span></span>
