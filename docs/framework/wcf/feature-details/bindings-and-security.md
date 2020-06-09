---
title: バインディングとセキュリティ
ms.date: 03/30/2017
helpviewer_keywords:
- bindings [WCF], security
- WCF security
- Windows Communication Foundation, security
- bindings [WCF]
ms.assetid: 4de03dd3-968a-4e65-af43-516e903d7f95
ms.openlocfilehash: 0c41f357d63158979e448c2cc36f1e80b74b18d4
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84587509"
---
# <a name="bindings-and-security"></a><span data-ttu-id="c8b8e-102">バインディングとセキュリティ</span><span class="sxs-lookup"><span data-stu-id="c8b8e-102">Bindings and Security</span></span>

<span data-ttu-id="c8b8e-103">Windows Communication Foundation (WCF) に含まれるシステム指定のバインディングを使用すると、WCF アプリケーションをすばやくプログラミングできます。</span><span class="sxs-lookup"><span data-stu-id="c8b8e-103">The system-provided bindings included with Windows Communication Foundation (WCF) offer a quick way to program WCF applications.</span></span> <span data-ttu-id="c8b8e-104">1 つの例外を除き、すべてのバインディングにはセキュリティ スキームが含まれており、既定で有効になっています。</span><span class="sxs-lookup"><span data-stu-id="c8b8e-104">With one exception, all the bindings have a default security scheme enabled.</span></span> <span data-ttu-id="c8b8e-105">ここでは、セキュリティ ニーズに適した正しいバインディングの選択方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c8b8e-105">This topic helps you select the right binding for your security needs.</span></span>

<span data-ttu-id="c8b8e-106">WCF セキュリティの概要については、「[セキュリティの概要](security-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c8b8e-106">For an overview of WCF security, see [Security Overview](security-overview.md).</span></span> <span data-ttu-id="c8b8e-107">バインディングを使用した WCF のプログラミングの詳細については、「 [Wcf セキュリティのプログラミング](programming-wcf-security.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c8b8e-107">For more information about programming WCF using bindings, see [Programming WCF Security](programming-wcf-security.md).</span></span>

<span data-ttu-id="c8b8e-108">バインディングを既に選択している場合は、セキュリティ[動作](security-behaviors-in-wcf.md)のセキュリティに関連付けられている実行時の動作の詳細を確認できます。</span><span class="sxs-lookup"><span data-stu-id="c8b8e-108">If you have already selected a binding, you can find out more about the run-time behaviors that are associated with security in [Security Behaviors](security-behaviors-in-wcf.md).</span></span>

<span data-ttu-id="c8b8e-109">セキュリティ機能のなかには、システム指定のバインディングを使用してプログラミングできないものがあります。</span><span class="sxs-lookup"><span data-stu-id="c8b8e-109">Some security functions are not programmable using the system-provided bindings.</span></span> <span data-ttu-id="c8b8e-110">カスタムバインドを使用した詳細な制御については、「[カスタムバインドを使用したセキュリティ機能](security-capabilities-with-custom-bindings.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c8b8e-110">For more control using a custom binding, see [Security Capabilities with Custom Bindings](security-capabilities-with-custom-bindings.md).</span></span>

## <a name="security-functions-of-bindings"></a><span data-ttu-id="c8b8e-111">バインディングのセキュリティ機能</span><span class="sxs-lookup"><span data-stu-id="c8b8e-111">Security Functions of Bindings</span></span>

<span data-ttu-id="c8b8e-112">WCF には、ほとんどのニーズを満たすシステム指定のバインディングが多数用意されています。</span><span class="sxs-lookup"><span data-stu-id="c8b8e-112">WCF includes a number of system-provided bindings that meet most needs.</span></span> <span data-ttu-id="c8b8e-113">特定のバインディングでは不十分な場合は、カスタム バインディングを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="c8b8e-113">If a particular binding does not suffice, you can also create a custom binding.</span></span> <span data-ttu-id="c8b8e-114">システム指定のバインディングの一覧については、「[システム指定のバインディング](../system-provided-bindings.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c8b8e-114">For a list of system-provided bindings, see [System-Provided Bindings](../system-provided-bindings.md).</span></span> <span data-ttu-id="c8b8e-115">カスタムバインディングの詳細については、「[カスタムバインド](../extending/custom-bindings.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c8b8e-115">For more information about custom bindings, see [Custom Bindings](../extending/custom-bindings.md).</span></span>

<span data-ttu-id="c8b8e-116">WCF のすべてのバインドには、API として、構成ファイルで使用される XML 要素として、という2つの形式があります。</span><span class="sxs-lookup"><span data-stu-id="c8b8e-116">Every binding in WCF has two forms: as an API and as an XML element used in a configuration file.</span></span> <span data-ttu-id="c8b8e-117">たとえば、 `WSHttpBinding` (API) には、に対応するがあり [\<wsHttpBinding>](../../configure-apps/file-schema/wcf/wshttpbinding.md) ます。</span><span class="sxs-lookup"><span data-stu-id="c8b8e-117">For example, the `WSHttpBinding` (API) has a counterpart in the [\<wsHttpBinding>](../../configure-apps/file-schema/wcf/wshttpbinding.md).</span></span>

<span data-ttu-id="c8b8e-118">以下のセクションでは、各バインディングについて両方の形式を示し、セキュリティ機能の概要を説明します。</span><span class="sxs-lookup"><span data-stu-id="c8b8e-118">The following section lists both forms for each binding and summarizes the security features.</span></span>

### <a name="basichttp"></a><span data-ttu-id="c8b8e-119">BasicHttp</span><span class="sxs-lookup"><span data-stu-id="c8b8e-119">BasicHttp</span></span>

<span data-ttu-id="c8b8e-120">コードでは、クラスを使用し <xref:System.ServiceModel.BasicHttpBinding> ます。構成では、を使用し [\<basicHttpBinding>](../../configure-apps/file-schema/wcf/basichttpbinding.md) ます。</span><span class="sxs-lookup"><span data-stu-id="c8b8e-120">In code, use the <xref:System.ServiceModel.BasicHttpBinding> class; in configuration, use the [\<basicHttpBinding>](../../configure-apps/file-schema/wcf/basichttpbinding.md).</span></span>

<span data-ttu-id="c8b8e-121">このバインディングは、次のような既存のさまざまなテクノロジと共に使用できるようにデザインされています。</span><span class="sxs-lookup"><span data-stu-id="c8b8e-121">This binding is designed for use with a range of existing technologies, including the following:</span></span>

- <span data-ttu-id="c8b8e-122">ASP.NET Web サービス (ASMX) Version 1</span><span class="sxs-lookup"><span data-stu-id="c8b8e-122">ASP.NET Web services (ASMX), version 1.</span></span>

- <span data-ttu-id="c8b8e-123">Web サービス拡張 (WSE) アプリケーション</span><span class="sxs-lookup"><span data-stu-id="c8b8e-123">Web Service Enhancements (WSE) applications.</span></span>

- <span data-ttu-id="c8b8e-124">Web Services 相互運用性 (WS-I) 仕様 () で定義されている基本プロファイル <https://go.microsoft.com/fwlink/?LinkId=38955> 。</span><span class="sxs-lookup"><span data-stu-id="c8b8e-124">Basic Profile as defined in the Web Services Interoperability (WS-I) specification (<https://go.microsoft.com/fwlink/?LinkId=38955>).</span></span>

- <span data-ttu-id="c8b8e-125">WS-I で定義されている基本セキュリティ プロファイル</span><span class="sxs-lookup"><span data-stu-id="c8b8e-125">Basic security profile as defined in WS-I.</span></span>

<span data-ttu-id="c8b8e-126">既定では、このバインディングはセキュリティで保護されません。</span><span class="sxs-lookup"><span data-stu-id="c8b8e-126">By default, this binding is not secure.</span></span> <span data-ttu-id="c8b8e-127">ASMX サービスと相互運用するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="c8b8e-127">It is designed to interoperate with ASMX services.</span></span> <span data-ttu-id="c8b8e-128">セキュリティを有効にした場合、このバインディングは、インターネット インフォメーション サービス (IIS: Internet Information Services) のセキュリティ機構 (基本認証、ダイジェスト、Windows 統合セキュリティなど) とシームレスに相互運用できるように設計されています。</span><span class="sxs-lookup"><span data-stu-id="c8b8e-128">When security is enabled, the binding is designed for seamless interoperation with Internet Information Services (IIS) security mechanisms, such as basic authentication, digest, and integrated Windows security.</span></span> <span data-ttu-id="c8b8e-129">詳細については、「[トランスポートセキュリティの概要](transport-security-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c8b8e-129">For more information, see [Transport Security Overview](transport-security-overview.md).</span></span> <span data-ttu-id="c8b8e-130">このバインディングでは、以下をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="c8b8e-130">This binding supports the following:</span></span>

- <span data-ttu-id="c8b8e-131">HTTPS トランスポート セキュリティ</span><span class="sxs-lookup"><span data-stu-id="c8b8e-131">HTTPS transport security.</span></span>

- <span data-ttu-id="c8b8e-132">HTTP 基本認証</span><span class="sxs-lookup"><span data-stu-id="c8b8e-132">HTTP basic authentication.</span></span>

- <span data-ttu-id="c8b8e-133">WS-Security。</span><span class="sxs-lookup"><span data-stu-id="c8b8e-133">WS-Security.</span></span>

<span data-ttu-id="c8b8e-134">詳細については、「<xref:System.ServiceModel.BasicHttpSecurity>」、「<xref:System.ServiceModel.BasicHttpMessageSecurity>」、「<xref:System.ServiceModel.BasicHttpMessageCredentialType>」、および「<xref:System.ServiceModel.BasicHttpSecurityMode>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c8b8e-134">For more information, see <xref:System.ServiceModel.BasicHttpSecurity>, <xref:System.ServiceModel.BasicHttpMessageSecurity>, <xref:System.ServiceModel.BasicHttpMessageCredentialType>, and <xref:System.ServiceModel.BasicHttpSecurityMode>.</span></span>

### <a name="wshttpbinding"></a><span data-ttu-id="c8b8e-135">WSHttpBinding</span><span class="sxs-lookup"><span data-stu-id="c8b8e-135">WSHttpBinding</span></span>

<span data-ttu-id="c8b8e-136">コードでは、クラスを使用し <xref:System.ServiceModel.WSHttpBinding> ます。構成では、を使用し [\<wsHttpBinding>](../../configure-apps/file-schema/wcf/wshttpbinding.md) ます。</span><span class="sxs-lookup"><span data-stu-id="c8b8e-136">In code, use the <xref:System.ServiceModel.WSHttpBinding> class; in configuration, use the [\<wsHttpBinding>](../../configure-apps/file-schema/wcf/wshttpbinding.md).</span></span>

<span data-ttu-id="c8b8e-137">既定では、このバインディングは WS-Security 仕様を実装しており、WS-\* 仕様を実装するサービスとの相互運用性があります。</span><span class="sxs-lookup"><span data-stu-id="c8b8e-137">By default, this binding implements the WS-Security specification and provides interoperability with services that implement the WS-\* specifications.</span></span> <span data-ttu-id="c8b8e-138">次のセキュリティをサポートします。</span><span class="sxs-lookup"><span data-stu-id="c8b8e-138">It supports the following:</span></span>

- <span data-ttu-id="c8b8e-139">HTTPS トランスポート セキュリティ</span><span class="sxs-lookup"><span data-stu-id="c8b8e-139">HTTPS transport security.</span></span>

- <span data-ttu-id="c8b8e-140">WS-Security。</span><span class="sxs-lookup"><span data-stu-id="c8b8e-140">WS-Security.</span></span>

- <span data-ttu-id="c8b8e-141">SOAP メッセージ資格情報セキュリティを使用した、HTTPS トランスポート保護による呼び出し元の認証。</span><span class="sxs-lookup"><span data-stu-id="c8b8e-141">HTTPS transport protection with SOAP message credential security for authenticating the caller.</span></span>

<span data-ttu-id="c8b8e-142">詳細については、「」、「」、「」、「」、および「」を参照してください <xref:System.ServiceModel.WSHttpSecurity> <xref:System.ServiceModel.MessageSecurityOverHttp> <xref:System.ServiceModel.MessageCredentialType> <xref:System.ServiceModel.SecurityMode> <xref:System.ServiceModel.HttpTransportSecurity> <xref:System.ServiceModel.HttpClientCredentialType> <xref:System.ServiceModel.HttpProxyCredentialType> 。</span><span class="sxs-lookup"><span data-stu-id="c8b8e-142">For more information, see <xref:System.ServiceModel.WSHttpSecurity>, <xref:System.ServiceModel.MessageSecurityOverHttp>, <xref:System.ServiceModel.MessageCredentialType>, <xref:System.ServiceModel.SecurityMode>, <xref:System.ServiceModel.HttpTransportSecurity>, <xref:System.ServiceModel.HttpClientCredentialType>, and <xref:System.ServiceModel.HttpProxyCredentialType>.</span></span>

### <a name="wsdualhttpbinding"></a><span data-ttu-id="c8b8e-143">WSDualHttpBinding</span><span class="sxs-lookup"><span data-stu-id="c8b8e-143">WSDualHttpBinding</span></span>

<span data-ttu-id="c8b8e-144">コードでは、クラスを使用し <xref:System.ServiceModel.WSDualHttpBinding> ます。構成では、を使用し [\<wsDualHttpBinding>](../../configure-apps/file-schema/wcf/wsdualhttpbinding.md) ます。</span><span class="sxs-lookup"><span data-stu-id="c8b8e-144">In code, use the <xref:System.ServiceModel.WSDualHttpBinding> class; in configuration, use the [\<wsDualHttpBinding>](../../configure-apps/file-schema/wcf/wsdualhttpbinding.md).</span></span>

<span data-ttu-id="c8b8e-145">このバインディングは、双方向サービス アプリケーションを有効にするために設計されています。</span><span class="sxs-lookup"><span data-stu-id="c8b8e-145">This binding is designed to enable duplex service applications.</span></span> <span data-ttu-id="c8b8e-146">このバインディングは、メッセージ ベースの転送セキュリティ用に WS-Security 仕様を実装しています。</span><span class="sxs-lookup"><span data-stu-id="c8b8e-146">This binding implements the WS-Security specification for message-based transfer security.</span></span> <span data-ttu-id="c8b8e-147">トランスポート セキュリティは使用できません。</span><span class="sxs-lookup"><span data-stu-id="c8b8e-147">Transport security is not available.</span></span> <span data-ttu-id="c8b8e-148">既定では、次の機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="c8b8e-148">By default, it provides the following features:</span></span>

- <span data-ttu-id="c8b8e-149">WS-ReliableMessaging を実装して信頼性を確保します。</span><span class="sxs-lookup"><span data-stu-id="c8b8e-149">Implements WS-Reliable Messaging for reliability.</span></span>

- <span data-ttu-id="c8b8e-150">WS-Security を実装して転送セキュリティおよび認証を実現します。</span><span class="sxs-lookup"><span data-stu-id="c8b8e-150">Implements WS-Security for transfer security and authentication.</span></span>

- <span data-ttu-id="c8b8e-151">HTTP を使用してメッセージを配信します。</span><span class="sxs-lookup"><span data-stu-id="c8b8e-151">Uses HTTP for message delivery.</span></span>

- <span data-ttu-id="c8b8e-152">テキスト/XML メッセージ エンコーディングを使用します。</span><span class="sxs-lookup"><span data-stu-id="c8b8e-152">Uses text/XML message encoding.</span></span>

 <span data-ttu-id="c8b8e-153">バインディングで WS-Security (メッセージ層セキュリティ) を使用すると、次のパラメーターを構成できるようになります。</span><span class="sxs-lookup"><span data-stu-id="c8b8e-153">Using WS-Security (message-layer security), the binding allows you to configure the following parameters:</span></span>

- <span data-ttu-id="c8b8e-154">暗号アルゴリズムを決定するためのセキュリティ アルゴリズム スイート</span><span class="sxs-lookup"><span data-stu-id="c8b8e-154">The security algorithm suite to determine the cryptographic algorithm.</span></span>

- <span data-ttu-id="c8b8e-155">以下を行うためのバインディング オプション</span><span class="sxs-lookup"><span data-stu-id="c8b8e-155">Binding options for the following:</span></span>

  - <span data-ttu-id="c8b8e-156">クライアントで帯域外で使用可能なサービス資格情報の提供</span><span class="sxs-lookup"><span data-stu-id="c8b8e-156">Providing service credentials available out-of-band at the client.</span></span>

  - <span data-ttu-id="c8b8e-157">チャネル セットアップの一部としてサービスからネゴシエートされるサービス資格情報の提供</span><span class="sxs-lookup"><span data-stu-id="c8b8e-157">Providing service credentials negotiated from the service as part of channel setup.</span></span>

<span data-ttu-id="c8b8e-158">詳細については、次のトピックを参照してください。 <xref:System.ServiceModel.WSDualHttpSecurity> および <xref:System.ServiceModel.WSDualHttpSecurityMode></span><span class="sxs-lookup"><span data-stu-id="c8b8e-158">For more information, see <xref:System.ServiceModel.WSDualHttpSecurity> and <xref:System.ServiceModel.WSDualHttpSecurityMode>.</span></span>

### <a name="nettcpbinding"></a><span data-ttu-id="c8b8e-159">NetTcpBinding</span><span class="sxs-lookup"><span data-stu-id="c8b8e-159">NetTcpBinding</span></span>

<span data-ttu-id="c8b8e-160">コードでは、クラスを使用し <xref:System.ServiceModel.NetTcpBinding> ます。構成では、を使用し [\<netTcpBinding>](../../configure-apps/file-schema/wcf/nettcpbinding.md) ます。</span><span class="sxs-lookup"><span data-stu-id="c8b8e-160">In code, use the <xref:System.ServiceModel.NetTcpBinding> class; in configuration, use the [\<netTcpBinding>](../../configure-apps/file-schema/wcf/nettcpbinding.md).</span></span>

<span data-ttu-id="c8b8e-161">このバインディングは複数のコンピューター間での通信に最適化されています。</span><span class="sxs-lookup"><span data-stu-id="c8b8e-161">This binding is optimized for cross-machine communication.</span></span> <span data-ttu-id="c8b8e-162">既定では、次の特性があります。</span><span class="sxs-lookup"><span data-stu-id="c8b8e-162">By default, it has the following characteristics:</span></span>

- <span data-ttu-id="c8b8e-163">トランスポート層セキュリティを実装します。</span><span class="sxs-lookup"><span data-stu-id="c8b8e-163">Implements transport-layer security.</span></span>

- <span data-ttu-id="c8b8e-164">Windows セキュリティを利用して、転送セキュリティと認証を確保します。</span><span class="sxs-lookup"><span data-stu-id="c8b8e-164">Leverages Windows security for transfer security and authentication.</span></span>

- <span data-ttu-id="c8b8e-165">トランスポートに TCP を使用します。</span><span class="sxs-lookup"><span data-stu-id="c8b8e-165">Uses TCP for transport.</span></span>

- <span data-ttu-id="c8b8e-166">バイナリ メッセージのエンコードを実装します。</span><span class="sxs-lookup"><span data-stu-id="c8b8e-166">Implements binary message encoding.</span></span>

- <span data-ttu-id="c8b8e-167">WS-ReliableMessaging を実装します。</span><span class="sxs-lookup"><span data-stu-id="c8b8e-167">Implements WS-Reliable Messaging.</span></span>

<span data-ttu-id="c8b8e-168">選択できる方法は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="c8b8e-168">Options include the following:</span></span>

- <span data-ttu-id="c8b8e-169">メッセージ層セキュリティ (WS-Security を使用)</span><span class="sxs-lookup"><span data-stu-id="c8b8e-169">Message-layer security (using WS-Security).</span></span>

- <span data-ttu-id="c8b8e-170">メッセージ資格情報を使用するトランスポート セキュリティ (TLS (Transport Layer Security) over TCP によって実現される機密性と整合性、および WS-Security によって提供される承認に使用する資格情報)</span><span class="sxs-lookup"><span data-stu-id="c8b8e-170">Transport security with message credential—confidentiality and integrity provided by Transport Layer Security (TLS) over TCP, and credentials for authorization provided by WS-Security.</span></span>

<span data-ttu-id="c8b8e-171">詳細については、「」、「」、「」、および「」を参照してください <xref:System.ServiceModel.NetTcpSecurity> <xref:System.ServiceModel.TcpTransportSecurity> <xref:System.ServiceModel.TcpClientCredentialType> <xref:System.ServiceModel.MessageSecurityOverTcp> <xref:System.ServiceModel.MessageCredentialType> 。</span><span class="sxs-lookup"><span data-stu-id="c8b8e-171">For more information, see <xref:System.ServiceModel.NetTcpSecurity>, <xref:System.ServiceModel.TcpTransportSecurity>, <xref:System.ServiceModel.TcpClientCredentialType>, <xref:System.ServiceModel.MessageSecurityOverTcp>, and <xref:System.ServiceModel.MessageCredentialType>.</span></span>

### <a name="netnamedpipebinding"></a><span data-ttu-id="c8b8e-172">NetNamedPipeBinding</span><span class="sxs-lookup"><span data-stu-id="c8b8e-172">NetNamedPipeBinding</span></span>

<span data-ttu-id="c8b8e-173">コードでは、クラスを使用し <xref:System.ServiceModel.NetNamedPipeBinding> ます。構成では、を使用し [\<netNamedPipeBinding>](../../configure-apps/file-schema/wcf/netnamedpipebinding.md) ます。</span><span class="sxs-lookup"><span data-stu-id="c8b8e-173">In code, use the <xref:System.ServiceModel.NetNamedPipeBinding> class; in configuration, use the [\<netNamedPipeBinding>](../../configure-apps/file-schema/wcf/netnamedpipebinding.md).</span></span>

<span data-ttu-id="c8b8e-174">このバインディングは、(通常では同じコンピューター上の) 複数プロセス間の通信に最適化されています。</span><span class="sxs-lookup"><span data-stu-id="c8b8e-174">This binding is optimized for cross-process communication (usually on the same machine).</span></span> <span data-ttu-id="c8b8e-175">既定では、このバインディングには次の特性があります。</span><span class="sxs-lookup"><span data-stu-id="c8b8e-175">By default, this binding has the following characteristics:</span></span>

- <span data-ttu-id="c8b8e-176">トランスポート セキュリティを使用して、メッセージ転送と認証を実現します。</span><span class="sxs-lookup"><span data-stu-id="c8b8e-176">Uses transport security for message transfer and authentication.</span></span>

- <span data-ttu-id="c8b8e-177">名前付きパイプを使用してメッセージを配信します。</span><span class="sxs-lookup"><span data-stu-id="c8b8e-177">Uses named pipes for message delivery.</span></span>

- <span data-ttu-id="c8b8e-178">バイナリ メッセージのエンコードを実装します。</span><span class="sxs-lookup"><span data-stu-id="c8b8e-178">Implements binary message encoding.</span></span>

- <span data-ttu-id="c8b8e-179">暗号化とメッセージの署名を使用します。</span><span class="sxs-lookup"><span data-stu-id="c8b8e-179">Encryption and message signing.</span></span>

<span data-ttu-id="c8b8e-180">選択できる方法は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="c8b8e-180">Options include the following:</span></span>

- <span data-ttu-id="c8b8e-181">Windows セキュリティを使用した認証</span><span class="sxs-lookup"><span data-stu-id="c8b8e-181">Authentication using Windows security.</span></span>

<span data-ttu-id="c8b8e-182">詳細については、「<xref:System.ServiceModel.NetNamedPipeSecurity>「<xref:System.ServiceModel.NetNamedPipeSecurityMode>および「<xref:System.ServiceModel.NamedPipeTransportSecurity>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c8b8e-182">For more information, see <xref:System.ServiceModel.NetNamedPipeSecurity>, <xref:System.ServiceModel.NetNamedPipeSecurityMode>, and <xref:System.ServiceModel.NamedPipeTransportSecurity>.</span></span>

### <a name="msmqintegrationbinding"></a><span data-ttu-id="c8b8e-183">MsmqIntegrationBinding</span><span class="sxs-lookup"><span data-stu-id="c8b8e-183">MsmqIntegrationBinding</span></span>

<span data-ttu-id="c8b8e-184">コードでは、クラスを使用し <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding> ます。構成では、を使用し [\<msmqIntegrationBinding>](../../configure-apps/file-schema/wcf/msmqintegrationbinding.md) ます。</span><span class="sxs-lookup"><span data-stu-id="c8b8e-184">In code, use the <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding> class; in configuration, use the [\<msmqIntegrationBinding>](../../configure-apps/file-schema/wcf/msmqintegrationbinding.md).</span></span>

<span data-ttu-id="c8b8e-185">このバインディングは、wcf 以外の Microsoft Message Queuing (MSMQ) エンドポイントと相互運用する WCF クライアントおよびサービスを作成するために最適化されています。</span><span class="sxs-lookup"><span data-stu-id="c8b8e-185">This binding is optimized for creating WCF clients and services that interoperate with non-WCF Microsoft Message Queuing (MSMQ) endpoints.</span></span>

<span data-ttu-id="c8b8e-186">既定では、このバインディングはトランスポート セキュリティを使用し、次のセキュリティ特性があります。</span><span class="sxs-lookup"><span data-stu-id="c8b8e-186">By default, this binding uses transport security and provides the following security characteristics:</span></span>

- <span data-ttu-id="c8b8e-187">セキュリティは無効 (なし) にできます。</span><span class="sxs-lookup"><span data-stu-id="c8b8e-187">Security can be disabled (None).</span></span>

- <span data-ttu-id="c8b8e-188">MSMQ トランスポート セキュリティ (トランスポート)。</span><span class="sxs-lookup"><span data-stu-id="c8b8e-188">MSMQ transport security (Transport).</span></span>

<span data-ttu-id="c8b8e-189">詳細については、次のトピックを参照してください。 <xref:System.ServiceModel.NetMsmqSecurity> および <xref:System.ServiceModel.NetMsmqSecurityMode></span><span class="sxs-lookup"><span data-stu-id="c8b8e-189">For more information, see <xref:System.ServiceModel.NetMsmqSecurity> and <xref:System.ServiceModel.NetMsmqSecurityMode>.</span></span>

### <a name="netmsmqbinding"></a><span data-ttu-id="c8b8e-190">NetMsmqBinding</span><span class="sxs-lookup"><span data-stu-id="c8b8e-190">NetMsmqBinding</span></span>

<span data-ttu-id="c8b8e-191">コードでは、クラスを使用し <xref:System.ServiceModel.NetMsmqBinding> ます。構成では、を使用し [\<netMsmqBinding>](../../configure-apps/file-schema/wcf/netmsmqbinding.md) ます。</span><span class="sxs-lookup"><span data-stu-id="c8b8e-191">In code, use the <xref:System.ServiceModel.NetMsmqBinding> class; in configuration, use the [\<netMsmqBinding>](../../configure-apps/file-schema/wcf/netmsmqbinding.md).</span></span>

<span data-ttu-id="c8b8e-192">このバインディングは、MSMQ のキューに置かれたメッセージのサポートを必要とする WCF サービスを作成するときに使用することを意図しています。</span><span class="sxs-lookup"><span data-stu-id="c8b8e-192">This binding is intended for use when creating WCF services that require MSMQ queued message support.</span></span>

<span data-ttu-id="c8b8e-193">既定では、このバインディングはトランスポート セキュリティを使用し、次のセキュリティ特性があります。</span><span class="sxs-lookup"><span data-stu-id="c8b8e-193">By default, this binding uses transport security and provides the following security characteristics:</span></span>

- <span data-ttu-id="c8b8e-194">セキュリティは無効 (なし) にできます。</span><span class="sxs-lookup"><span data-stu-id="c8b8e-194">Security can be disabled (None).</span></span>

- <span data-ttu-id="c8b8e-195">MSMQ トランスポート セキュリティ (トランスポート)。</span><span class="sxs-lookup"><span data-stu-id="c8b8e-195">MSMQ transport security (Transport).</span></span>

- <span data-ttu-id="c8b8e-196">SOAP に基づくメッセージ セキュリティ (メッセージ)。</span><span class="sxs-lookup"><span data-stu-id="c8b8e-196">SOAP-based message security (Message).</span></span>

- <span data-ttu-id="c8b8e-197">トランスポート セキュリティとメッセージ セキュリティ (両方)。</span><span class="sxs-lookup"><span data-stu-id="c8b8e-197">Simultaneous Transport and Message security (Both).</span></span>

- <span data-ttu-id="c8b8e-198">サポートされるクライアント資格情報の種類 : なし、Windows、UserName、証明書、IssuedToken。</span><span class="sxs-lookup"><span data-stu-id="c8b8e-198">Client Credential Types supported: None, Windows, UserName, Certificate, IssuedToken.</span></span>

<span data-ttu-id="c8b8e-199"><xref:System.ServiceModel.MessageCredentialType.Certificate> 資格情報は、セキュリティ モードが <xref:System.ServiceModel.NetMsmqSecurityMode.Both> または <xref:System.ServiceModel.NetMsmqSecurityMode.Message> に設定されている場合にのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="c8b8e-199">The <xref:System.ServiceModel.MessageCredentialType.Certificate> credential is supported only when the security mode is set to either <xref:System.ServiceModel.NetMsmqSecurityMode.Both> or <xref:System.ServiceModel.NetMsmqSecurityMode.Message>.</span></span>

<span data-ttu-id="c8b8e-200">詳細については、次のトピックを参照してください。 <xref:System.ServiceModel.MessageSecurityOverMsmq> および <xref:System.ServiceModel.MsmqTransportSecurity></span><span class="sxs-lookup"><span data-stu-id="c8b8e-200">For more information, see <xref:System.ServiceModel.MessageSecurityOverMsmq> and <xref:System.ServiceModel.MsmqTransportSecurity>.</span></span>

### <a name="wsfederationhttpbinding"></a><span data-ttu-id="c8b8e-201">WSFederationHttpBinding</span><span class="sxs-lookup"><span data-stu-id="c8b8e-201">WSFederationHttpBinding</span></span>

<span data-ttu-id="c8b8e-202">コードでは、クラスを使用し <xref:System.ServiceModel.WSFederationHttpBinding> ます。構成では、を使用し [\<wsFederationHttpBinding>](../../configure-apps/file-schema/wcf/wsfederationhttpbinding.md) ます。</span><span class="sxs-lookup"><span data-stu-id="c8b8e-202">In code, use the <xref:System.ServiceModel.WSFederationHttpBinding> class; in configuration, use the [\<wsFederationHttpBinding>](../../configure-apps/file-schema/wcf/wsfederationhttpbinding.md).</span></span>

<span data-ttu-id="c8b8e-203">既定では、このバインディングは WS-Security (メッセージ層セキュリティ) を使用します。</span><span class="sxs-lookup"><span data-stu-id="c8b8e-203">By default, this binding uses WS-Security (message-layer security).</span></span>

<span data-ttu-id="c8b8e-204">詳細については、「 [Federation](federation.md)、」、および「」を参照してください <xref:System.ServiceModel.WSFederationHttpSecurity> <xref:System.ServiceModel.WSFederationHttpSecurityMode> 。</span><span class="sxs-lookup"><span data-stu-id="c8b8e-204">For more information, see [Federation](federation.md), <xref:System.ServiceModel.WSFederationHttpSecurity>, and <xref:System.ServiceModel.WSFederationHttpSecurityMode>.</span></span>

## <a name="custom-bindings"></a><span data-ttu-id="c8b8e-205">カスタム バインディング</span><span class="sxs-lookup"><span data-stu-id="c8b8e-205">Custom Bindings</span></span>

<span data-ttu-id="c8b8e-206">システム指定のバインディングがいずれも要件を満たさない場合は、カスタム セキュリティ バインド要素を使用してカスタム バインディングを作成できます。</span><span class="sxs-lookup"><span data-stu-id="c8b8e-206">If none of the system-provided bindings meets you requirements, you can create a custom binding with a custom security binding element.</span></span> <span data-ttu-id="c8b8e-207">詳細については、「[カスタムバインドを使用したセキュリティ機能](security-capabilities-with-custom-bindings.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c8b8e-207">For more information, see [Security Capabilities with Custom Bindings](security-capabilities-with-custom-bindings.md).</span></span>

## <a name="binding-choices"></a><span data-ttu-id="c8b8e-208">バインディングの選択肢</span><span class="sxs-lookup"><span data-stu-id="c8b8e-208">Binding Choices</span></span>

<span data-ttu-id="c8b8e-209">次の表は、セキュリティ モード設定で提供される機能をまとめたものです。つまり、セキュリティ モードを `Transport`、`Message`、または `TransportWithMessageCredential` に設定したときに使用できる機能の一覧です。</span><span class="sxs-lookup"><span data-stu-id="c8b8e-209">The following table summarizes the features offered in the security mode setting, that is, it lists the features available when the security mode is set to `Transport`, `Message`, or `TransportWithMessageCredential`.</span></span> <span data-ttu-id="c8b8e-210">アプリケーションで必要なセキュリティ機能を決定するときに、この表を参考にしてください。</span><span class="sxs-lookup"><span data-stu-id="c8b8e-210">Use this table to help you find the security features your application requires.</span></span>

|<span data-ttu-id="c8b8e-211">設定</span><span class="sxs-lookup"><span data-stu-id="c8b8e-211">Setting</span></span>|<span data-ttu-id="c8b8e-212">特徴</span><span class="sxs-lookup"><span data-stu-id="c8b8e-212">Features</span></span>|
|-------------|--------------|
|<span data-ttu-id="c8b8e-213">トランスポート</span><span class="sxs-lookup"><span data-stu-id="c8b8e-213">Transport</span></span>|<span data-ttu-id="c8b8e-214">サーバー認証</span><span class="sxs-lookup"><span data-stu-id="c8b8e-214">Server authentication</span></span><br /><br /> <span data-ttu-id="c8b8e-215">クライアント認証</span><span class="sxs-lookup"><span data-stu-id="c8b8e-215">Client authentication</span></span><br /><br /> <span data-ttu-id="c8b8e-216">Point-to-Point のセキュリティ</span><span class="sxs-lookup"><span data-stu-id="c8b8e-216">Point-to-point security</span></span><br /><br /> <span data-ttu-id="c8b8e-217">相互運用性</span><span class="sxs-lookup"><span data-stu-id="c8b8e-217">Interoperability</span></span><br /><br /> <span data-ttu-id="c8b8e-218">ハードウェアの高速化</span><span class="sxs-lookup"><span data-stu-id="c8b8e-218">Hardware acceleration</span></span><br /><br /> <span data-ttu-id="c8b8e-219">高スループット</span><span class="sxs-lookup"><span data-stu-id="c8b8e-219">High throughput</span></span><br /><br /> <span data-ttu-id="c8b8e-220">セキュリティで保護されたファイアウォール</span><span class="sxs-lookup"><span data-stu-id="c8b8e-220">Secure firewall</span></span><br /><br /> <span data-ttu-id="c8b8e-221">待ち時間の長いアプリケーション</span><span class="sxs-lookup"><span data-stu-id="c8b8e-221">High-latency applications</span></span><br /><br /> <span data-ttu-id="c8b8e-222">複数のホップでの再暗号化</span><span class="sxs-lookup"><span data-stu-id="c8b8e-222">Re-encryption across multiple hops</span></span>|
|<span data-ttu-id="c8b8e-223">Message</span><span class="sxs-lookup"><span data-stu-id="c8b8e-223">Message</span></span>|<span data-ttu-id="c8b8e-224">サーバー認証</span><span class="sxs-lookup"><span data-stu-id="c8b8e-224">Server authentication</span></span><br /><br /> <span data-ttu-id="c8b8e-225">クライアント認証</span><span class="sxs-lookup"><span data-stu-id="c8b8e-225">Client authentication</span></span><br /><br /> <span data-ttu-id="c8b8e-226">エンドツーエンドのセキュリティ</span><span class="sxs-lookup"><span data-stu-id="c8b8e-226">End-to-end security</span></span><br /><br /> <span data-ttu-id="c8b8e-227">相互運用性</span><span class="sxs-lookup"><span data-stu-id="c8b8e-227">Interoperability</span></span><br /><br /> <span data-ttu-id="c8b8e-228">多様なクレーム</span><span class="sxs-lookup"><span data-stu-id="c8b8e-228">Rich claims</span></span><br /><br /> <span data-ttu-id="c8b8e-229">フェデレーション</span><span class="sxs-lookup"><span data-stu-id="c8b8e-229">Federation</span></span><br /><br /> <span data-ttu-id="c8b8e-230">多要素認証</span><span class="sxs-lookup"><span data-stu-id="c8b8e-230">Multifactor authentication</span></span><br /><br /> <span data-ttu-id="c8b8e-231">カスタム トークン</span><span class="sxs-lookup"><span data-stu-id="c8b8e-231">Custom tokens</span></span><br /><br /> <span data-ttu-id="c8b8e-232">Notary/Timestamp サービス</span><span class="sxs-lookup"><span data-stu-id="c8b8e-232">Notary/timestamp service</span></span><br /><br /> <span data-ttu-id="c8b8e-233">待ち時間の長いアプリケーション</span><span class="sxs-lookup"><span data-stu-id="c8b8e-233">High-latency applications</span></span><br /><br /> <span data-ttu-id="c8b8e-234">メッセージ署名の永続化</span><span class="sxs-lookup"><span data-stu-id="c8b8e-234">Persistence of message signatures</span></span>|
|<span data-ttu-id="c8b8e-235">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="c8b8e-235">TransportWithMessageCredential</span></span>|<span data-ttu-id="c8b8e-236">サーバー認証</span><span class="sxs-lookup"><span data-stu-id="c8b8e-236">Server authentication</span></span><br /><br /> <span data-ttu-id="c8b8e-237">クライアント認証</span><span class="sxs-lookup"><span data-stu-id="c8b8e-237">Client authentication</span></span><br /><br /> <span data-ttu-id="c8b8e-238">Point-to-Point のセキュリティ</span><span class="sxs-lookup"><span data-stu-id="c8b8e-238">Point-to-point security</span></span><br /><br /> <span data-ttu-id="c8b8e-239">相互運用性</span><span class="sxs-lookup"><span data-stu-id="c8b8e-239">Interoperability</span></span><br /><br /> <span data-ttu-id="c8b8e-240">ハードウェアの高速化</span><span class="sxs-lookup"><span data-stu-id="c8b8e-240">Hardware acceleration</span></span><br /><br /> <span data-ttu-id="c8b8e-241">高スループット</span><span class="sxs-lookup"><span data-stu-id="c8b8e-241">High throughput</span></span><br /><br /> <span data-ttu-id="c8b8e-242">多様なクライアント クレーム</span><span class="sxs-lookup"><span data-stu-id="c8b8e-242">Rich client claims</span></span><br /><br /> <span data-ttu-id="c8b8e-243">フェデレーション</span><span class="sxs-lookup"><span data-stu-id="c8b8e-243">Federation</span></span><br /><br /> <span data-ttu-id="c8b8e-244">多要素認証</span><span class="sxs-lookup"><span data-stu-id="c8b8e-244">Multifactor authentication</span></span><br /><br /> <span data-ttu-id="c8b8e-245">カスタム トークン</span><span class="sxs-lookup"><span data-stu-id="c8b8e-245">Custom tokens</span></span><br /><br /> <span data-ttu-id="c8b8e-246">セキュリティで保護されたファイアウォール</span><span class="sxs-lookup"><span data-stu-id="c8b8e-246">Secure firewall</span></span><br /><br /> <span data-ttu-id="c8b8e-247">待ち時間の長いアプリケーション</span><span class="sxs-lookup"><span data-stu-id="c8b8e-247">High-latency applications</span></span><br /><br /> <span data-ttu-id="c8b8e-248">複数のホップでの再暗号化</span><span class="sxs-lookup"><span data-stu-id="c8b8e-248">Re-encryption across multiple hops</span></span>|

<span data-ttu-id="c8b8e-249">さまざまなモード設定をサポートするバインディングを次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="c8b8e-249">The following table lists the bindings that support the various mode settings.</span></span> <span data-ttu-id="c8b8e-250">サービス エンドポイントを作成するときは、使用するバインディングをこの表から選択してください。</span><span class="sxs-lookup"><span data-stu-id="c8b8e-250">Select a binding from the table to use to create your service endpoint.</span></span>

|<span data-ttu-id="c8b8e-251">バインド</span><span class="sxs-lookup"><span data-stu-id="c8b8e-251">Binding</span></span>|<span data-ttu-id="c8b8e-252">トランスポート モードのサポート</span><span class="sxs-lookup"><span data-stu-id="c8b8e-252">Transport mode support</span></span>|<span data-ttu-id="c8b8e-253">メッセージ モードのサポート</span><span class="sxs-lookup"><span data-stu-id="c8b8e-253">Message mode support</span></span>|<span data-ttu-id="c8b8e-254">TransportWithMessageCredential のサポート</span><span class="sxs-lookup"><span data-stu-id="c8b8e-254">TransportWithMessageCredential support</span></span>|
|-------------|----------------------------|--------------------------|--------------------------------------------|
|`BasicHttpBinding`|<span data-ttu-id="c8b8e-255">はい</span><span class="sxs-lookup"><span data-stu-id="c8b8e-255">Yes</span></span>|<span data-ttu-id="c8b8e-256">はい</span><span class="sxs-lookup"><span data-stu-id="c8b8e-256">Yes</span></span>|<span data-ttu-id="c8b8e-257">はい</span><span class="sxs-lookup"><span data-stu-id="c8b8e-257">Yes</span></span>|
|`WSHttpBinding`|<span data-ttu-id="c8b8e-258">はい</span><span class="sxs-lookup"><span data-stu-id="c8b8e-258">Yes</span></span>|<span data-ttu-id="c8b8e-259">はい</span><span class="sxs-lookup"><span data-stu-id="c8b8e-259">Yes</span></span>|<span data-ttu-id="c8b8e-260">はい</span><span class="sxs-lookup"><span data-stu-id="c8b8e-260">Yes</span></span>|
|`WSDualHttpBinding`|<span data-ttu-id="c8b8e-261">いいえ</span><span class="sxs-lookup"><span data-stu-id="c8b8e-261">No</span></span>|<span data-ttu-id="c8b8e-262">はい</span><span class="sxs-lookup"><span data-stu-id="c8b8e-262">Yes</span></span>|<span data-ttu-id="c8b8e-263">いいえ</span><span class="sxs-lookup"><span data-stu-id="c8b8e-263">No</span></span>|
|`NetTcpBinding`|<span data-ttu-id="c8b8e-264">はい</span><span class="sxs-lookup"><span data-stu-id="c8b8e-264">Yes</span></span>|<span data-ttu-id="c8b8e-265">はい</span><span class="sxs-lookup"><span data-stu-id="c8b8e-265">Yes</span></span>|<span data-ttu-id="c8b8e-266">はい</span><span class="sxs-lookup"><span data-stu-id="c8b8e-266">Yes</span></span>|
|`NetNamedPipeBinding`|<span data-ttu-id="c8b8e-267">はい</span><span class="sxs-lookup"><span data-stu-id="c8b8e-267">Yes</span></span>|<span data-ttu-id="c8b8e-268">いいえ</span><span class="sxs-lookup"><span data-stu-id="c8b8e-268">No</span></span>|<span data-ttu-id="c8b8e-269">いいえ</span><span class="sxs-lookup"><span data-stu-id="c8b8e-269">No</span></span>|
|`NetMsmqBinding`|<span data-ttu-id="c8b8e-270">はい</span><span class="sxs-lookup"><span data-stu-id="c8b8e-270">Yes</span></span>|<span data-ttu-id="c8b8e-271">はい</span><span class="sxs-lookup"><span data-stu-id="c8b8e-271">Yes</span></span>|<span data-ttu-id="c8b8e-272">いいえ</span><span class="sxs-lookup"><span data-stu-id="c8b8e-272">No</span></span>|
|`MsmqIntegrationBinding`|<span data-ttu-id="c8b8e-273">はい</span><span class="sxs-lookup"><span data-stu-id="c8b8e-273">Yes</span></span>|<span data-ttu-id="c8b8e-274">いいえ</span><span class="sxs-lookup"><span data-stu-id="c8b8e-274">No</span></span>|<span data-ttu-id="c8b8e-275">いいえ</span><span class="sxs-lookup"><span data-stu-id="c8b8e-275">No</span></span>|
|`wsFederationHttpBinding`|<span data-ttu-id="c8b8e-276">いいえ</span><span class="sxs-lookup"><span data-stu-id="c8b8e-276">No</span></span>|<span data-ttu-id="c8b8e-277">はい</span><span class="sxs-lookup"><span data-stu-id="c8b8e-277">Yes</span></span>|<span data-ttu-id="c8b8e-278">はい</span><span class="sxs-lookup"><span data-stu-id="c8b8e-278">Yes</span></span>|

## <a name="transport-credentials-in-bindings"></a><span data-ttu-id="c8b8e-279">バインディングにおけるトランスポート資格情報</span><span class="sxs-lookup"><span data-stu-id="c8b8e-279">Transport Credentials in Bindings</span></span>

<span data-ttu-id="c8b8e-280">トランスポート セキュリティ モードで `BasicHttpBinding` または `WSHttpBinding` を使用するときに使用できるクライアント資格情報の種類を、次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="c8b8e-280">The following table lists the client credential types available when using either `BasicHttpBinding` or `WSHttpBinding` in transport security mode.</span></span>

|<span data-ttu-id="c8b8e-281">Type</span><span class="sxs-lookup"><span data-stu-id="c8b8e-281">Type</span></span>|<span data-ttu-id="c8b8e-282">説明</span><span class="sxs-lookup"><span data-stu-id="c8b8e-282">Description</span></span>|
|----------|-----------------|
|<span data-ttu-id="c8b8e-283">なし</span><span class="sxs-lookup"><span data-stu-id="c8b8e-283">None</span></span>|<span data-ttu-id="c8b8e-284">クライアントが資格情報を提示する必要がないことを指定します。</span><span class="sxs-lookup"><span data-stu-id="c8b8e-284">Specifies that the client does not need to present any credential.</span></span> <span data-ttu-id="c8b8e-285">匿名クライアントであると解釈されます。</span><span class="sxs-lookup"><span data-stu-id="c8b8e-285">This translates to an anonymous client.</span></span>|
|<span data-ttu-id="c8b8e-286">Basic</span><span class="sxs-lookup"><span data-stu-id="c8b8e-286">Basic</span></span>|<span data-ttu-id="c8b8e-287">基本認証です。</span><span class="sxs-lookup"><span data-stu-id="c8b8e-287">Basic authentication.</span></span> <span data-ttu-id="c8b8e-288">詳細については、「RFC 2617 – HTTP 認証: 基本認証とダイジェスト認証」を参照してください <https://go.microsoft.com/fwlink/?LinkId=84023> 。</span><span class="sxs-lookup"><span data-stu-id="c8b8e-288">For more information, see RFC 2617 – HTTP Authentication: Basic and Digest Authentication, available at <https://go.microsoft.com/fwlink/?LinkId=84023>.</span></span>|
|<span data-ttu-id="c8b8e-289">ダイジェスト</span><span class="sxs-lookup"><span data-stu-id="c8b8e-289">Digest</span></span>|<span data-ttu-id="c8b8e-290">ダイジェスト認証です。</span><span class="sxs-lookup"><span data-stu-id="c8b8e-290">Digest authentication.</span></span> <span data-ttu-id="c8b8e-291">詳細については、「RFC 2617 – HTTP 認証: 基本認証とダイジェスト認証」を参照してください <https://go.microsoft.com/fwlink/?LinkId=84023> 。</span><span class="sxs-lookup"><span data-stu-id="c8b8e-291">For more information, see RFC 2617 – HTTP Authentication: Basic and Digest Authentication, available at <https://go.microsoft.com/fwlink/?LinkId=84023>.</span></span>|
|<span data-ttu-id="c8b8e-292">NTLM</span><span class="sxs-lookup"><span data-stu-id="c8b8e-292">NTLM</span></span>|<span data-ttu-id="c8b8e-293">NTLM (NT LAN Manager) 認証です。</span><span class="sxs-lookup"><span data-stu-id="c8b8e-293">NT LAN Manager (NTLM) authentication.</span></span>|
|<span data-ttu-id="c8b8e-294">Windows</span><span class="sxs-lookup"><span data-stu-id="c8b8e-294">Windows</span></span>|<span data-ttu-id="c8b8e-295">Windows 認証です。</span><span class="sxs-lookup"><span data-stu-id="c8b8e-295">Windows authentication.</span></span>|
|<span data-ttu-id="c8b8e-296">Certificate</span><span class="sxs-lookup"><span data-stu-id="c8b8e-296">Certificate</span></span>|<span data-ttu-id="c8b8e-297">証明書を使用して実行される認証です。</span><span class="sxs-lookup"><span data-stu-id="c8b8e-297">Authentication performed using a certificate.</span></span>|
|<span data-ttu-id="c8b8e-298">IssuedToken</span><span class="sxs-lookup"><span data-stu-id="c8b8e-298">IssuedToken</span></span>|<span data-ttu-id="c8b8e-299">サービスが、Security Token Service または CardSpace によって発行されたトークンを使用して、クライアントの認証を要求できるようにします。</span><span class="sxs-lookup"><span data-stu-id="c8b8e-299">Allows the service to require that the client be authenticated using a token issued by a security token service or by CardSpace.</span></span> <span data-ttu-id="c8b8e-300">詳細については、「[フェデレーションと発行済みトークン](federation-and-issued-tokens.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c8b8e-300">For more information, see [Federation and Issued Tokens](federation-and-issued-tokens.md).</span></span>|

### <a name="message-client-credentials-in-bindings"></a><span data-ttu-id="c8b8e-301">バインディングにおけるメッセージ クライアント資格情報</span><span class="sxs-lookup"><span data-stu-id="c8b8e-301">Message Client Credentials in Bindings</span></span>

<span data-ttu-id="c8b8e-302">メッセージ セキュリティ モードでバインディングを使用するときに使用できるクライアント資格情報の種類を次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="c8b8e-302">The following table lists the client credential types available when using a binding in Message security mode.</span></span>

|<span data-ttu-id="c8b8e-303">Type</span><span class="sxs-lookup"><span data-stu-id="c8b8e-303">Type</span></span>|<span data-ttu-id="c8b8e-304">説明</span><span class="sxs-lookup"><span data-stu-id="c8b8e-304">Description</span></span>|
|----------|-----------------|
|<span data-ttu-id="c8b8e-305">なし</span><span class="sxs-lookup"><span data-stu-id="c8b8e-305">None</span></span>|<span data-ttu-id="c8b8e-306">サービスが匿名クライアントとやり取りを行うことが可能になります。</span><span class="sxs-lookup"><span data-stu-id="c8b8e-306">Allows the service to interact with anonymous clients.</span></span>|
|<span data-ttu-id="c8b8e-307">Windows</span><span class="sxs-lookup"><span data-stu-id="c8b8e-307">Windows</span></span>|<span data-ttu-id="c8b8e-308">Windows 資格情報の認証済みコンテキストの制御下で SOAP メッセージ交換を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="c8b8e-308">Allows SOAP message exchanges to be made under the authenticated context of a Windows credential.</span></span>|
|<span data-ttu-id="c8b8e-309">UserName</span><span class="sxs-lookup"><span data-stu-id="c8b8e-309">UserName</span></span>|<span data-ttu-id="c8b8e-310">サービスが、ユーザー名資格情報を使用したクライアントの認証を要求できるようにします。</span><span class="sxs-lookup"><span data-stu-id="c8b8e-310">Allows the service to require that the client be authenticated using a user name credential.</span></span> <span data-ttu-id="c8b8e-311">セキュリティモードがに設定されている場合 `TransportWithMessageCredential` 、WCF では、パスワードダイジェストの送信や、パスワードを使用したキーの派生、およびメッセージモードセキュリティのためのこのようなキーの使用はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="c8b8e-311">Note that when the security mode is set to `TransportWithMessageCredential`, WCF does not support sending a password digest or deriving keys using password and using such keys for Message mode security.</span></span> <span data-ttu-id="c8b8e-312">そのため、ユーザー名の資格情報を使用する場合、WCF はトランスポートがセキュリティで保護されることを強制します。</span><span class="sxs-lookup"><span data-stu-id="c8b8e-312">As such, WCF enforces that the transport is secured when using user name credentials.</span></span>|
|<span data-ttu-id="c8b8e-313">Certificate</span><span class="sxs-lookup"><span data-stu-id="c8b8e-313">Certificate</span></span>|<span data-ttu-id="c8b8e-314">証明書を使用したクライアントの認証を、サービスで要求することが可能になります。</span><span class="sxs-lookup"><span data-stu-id="c8b8e-314">Allows the service to require that the client be authenticated using a certificate.</span></span>|
|<span data-ttu-id="c8b8e-315">IssuedToken</span><span class="sxs-lookup"><span data-stu-id="c8b8e-315">IssuedToken</span></span>|<span data-ttu-id="c8b8e-316">サービスは、セキュリティ トークン サービスを使用してカスタム トークンを提供できます。</span><span class="sxs-lookup"><span data-stu-id="c8b8e-316">Allows the service to use a security token service to supply a custom token.</span></span>|

## <a name="see-also"></a><span data-ttu-id="c8b8e-317">関連項目</span><span class="sxs-lookup"><span data-stu-id="c8b8e-317">See also</span></span>

- [<span data-ttu-id="c8b8e-318">セキュリティの概要</span><span class="sxs-lookup"><span data-stu-id="c8b8e-318">Security Overview</span></span>](security-overview.md)
- [<span data-ttu-id="c8b8e-319">サービスおよびクライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="c8b8e-319">Securing Services and Clients</span></span>](securing-services-and-clients.md)
- [<span data-ttu-id="c8b8e-320">資格情報の種類の選択</span><span class="sxs-lookup"><span data-stu-id="c8b8e-320">Selecting a Credential Type</span></span>](selecting-a-credential-type.md)
- [<span data-ttu-id="c8b8e-321">カスタム バインディングを使用したセキュリティ機能</span><span class="sxs-lookup"><span data-stu-id="c8b8e-321">Security Capabilities with Custom Bindings</span></span>](security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="c8b8e-322">セキュリティ動作</span><span class="sxs-lookup"><span data-stu-id="c8b8e-322">Security Behaviors</span></span>](security-behaviors-in-wcf.md)
- <span data-ttu-id="c8b8e-323">[Windows Server AppFabric のセキュリティ モデル](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="c8b8e-323">[Security Model for Windows Server App Fabric](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))</span></span>
