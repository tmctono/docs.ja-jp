---
title: '方法: セキュリティ モードを設定する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Mode property
- WCF, security mode
- WCF, security
ms.assetid: 6e01dd9f-b5dd-4474-b24c-06e124de4ff7
ms.openlocfilehash: 5a4550e4c914dcdbc9908e766c67a2efa53e6e9e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59339386"
---
# <a name="how-to-set-the-security-mode"></a><span data-ttu-id="f21c7-102">方法: セキュリティ モードを設定する</span><span class="sxs-lookup"><span data-stu-id="f21c7-102">How to: Set the Security Mode</span></span>
<span data-ttu-id="f21c7-103">Windows Communication Foundation (WCF) のセキュリティは、ほとんどの定義済みバインド上にある 3 つの一般的なセキュリティ モード: トランスポート、メッセージ、および「メッセージ資格情報付きトランスポート」。</span><span class="sxs-lookup"><span data-stu-id="f21c7-103">Windows Communication Foundation (WCF) security has three common security modes that are found on most predefined bindings: transport, message, and "transport with message credential."</span></span> <span data-ttu-id="f21c7-104">これ以外に、2 つのバインディングに固有の 2 つのモードがあります。<xref:System.ServiceModel.BasicHttpBinding> の "トランスポート資格情報専用" モードと、<xref:System.ServiceModel.NetMsmqBinding> の "両方" モードです。</span><span class="sxs-lookup"><span data-stu-id="f21c7-104">Two additional modes are specific to two bindings: the "transport-credential only" mode found on the <xref:System.ServiceModel.BasicHttpBinding>, and the "Both" mode, found on the <xref:System.ServiceModel.NetMsmqBinding>.</span></span> <span data-ttu-id="f21c7-105">ここでは、3 つの共通のセキュリティモードである <xref:System.ServiceModel.SecurityMode.Transport>、<xref:System.ServiceModel.SecurityMode.Message>、および <xref:System.ServiceModel.SecurityMode.TransportWithMessageCredential> に重点を置いて説明します。</span><span class="sxs-lookup"><span data-stu-id="f21c7-105">However, this topic concentrates on the three common security modes: <xref:System.ServiceModel.SecurityMode.Transport>, <xref:System.ServiceModel.SecurityMode.Message>, and <xref:System.ServiceModel.SecurityMode.TransportWithMessageCredential>.</span></span>  
  
 <span data-ttu-id="f21c7-106">ただし、これらのモードがすべての定義済みバインディングでサポートされるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="f21c7-106">Note that not every predefined binding supports all of these modes.</span></span> <span data-ttu-id="f21c7-107">ここでは、<xref:System.ServiceModel.WSHttpBinding> クラスと <xref:System.ServiceModel.NetTcpBinding> クラスでモードを設定し、プログラムと構成の両方を使用してモードを設定する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="f21c7-107">This topic sets the mode with the <xref:System.ServiceModel.WSHttpBinding> and <xref:System.ServiceModel.NetTcpBinding> classes and demonstrates how to set the mode both programmatically and through configuration.</span></span>  
  
 <span data-ttu-id="f21c7-108">詳細についてを参照してください、WCF のセキュリティを参照してください。[セキュリティの概要](../../../docs/framework/wcf/feature-details/security-overview.md)、 [Securing Services](../../../docs/framework/wcf/securing-services.md)、と[Securing Services and Clients](../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)します。</span><span class="sxs-lookup"><span data-stu-id="f21c7-108">For more information, see WCF security, see [Security Overview](../../../docs/framework/wcf/feature-details/security-overview.md), [Securing Services](../../../docs/framework/wcf/securing-services.md), and [Securing Services and Clients](../../../docs/framework/wcf/feature-details/securing-services-and-clients.md).</span></span> <span data-ttu-id="f21c7-109">トランスポート モードとメッセージの詳細については、次を参照してください。[トランスポート セキュリティ](../../../docs/framework/wcf/feature-details/transport-security.md)と[メッセージ セキュリティ](../../../docs/framework/wcf/feature-details/message-security-in-wcf.md)します。</span><span class="sxs-lookup"><span data-stu-id="f21c7-109">For more information about transport mode and message, see [Transport Security](../../../docs/framework/wcf/feature-details/transport-security.md) and [Message Security](../../../docs/framework/wcf/feature-details/message-security-in-wcf.md).</span></span>  
  
### <a name="to-set-the-security-mode-in-code"></a><span data-ttu-id="f21c7-110">コードでセキュリティ モードを設定するには</span><span class="sxs-lookup"><span data-stu-id="f21c7-110">To set the security mode in code</span></span>  
  
1. <span data-ttu-id="f21c7-111">使用しているバインディング クラスのインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="f21c7-111">Create an instance of the binding class that you are using.</span></span> <span data-ttu-id="f21c7-112">定義済みバインディングの一覧は、次を参照してください。 [System-Provided Bindings](../../../docs/framework/wcf/system-provided-bindings.md)します。</span><span class="sxs-lookup"><span data-stu-id="f21c7-112">For a list of predefined bindings, see [System-Provided Bindings](../../../docs/framework/wcf/system-provided-bindings.md).</span></span> <span data-ttu-id="f21c7-113">この例では、<xref:System.ServiceModel.WSHttpBinding> クラスのインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="f21c7-113">This example creates an instance of the <xref:System.ServiceModel.WSHttpBinding> class.</span></span>  
  
2. <span data-ttu-id="f21c7-114">`Mode` プロパティから返されるオブジェクトの `Security` プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="f21c7-114">Set the `Mode` property of the object returned by the `Security` property.</span></span>  
  
     [!code-csharp[c_SettingSecurityMode#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_settingsecuritymode/cs/source.cs#1)]
     [!code-vb[c_SettingSecurityMode#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_settingsecuritymode/vb/source.vb#1)]  
  
     <span data-ttu-id="f21c7-115">または、モードを Message (メッセージ) に設定します。コードは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="f21c7-115">Alternatively, set the mode to message, as shown in the following code.</span></span>  
  
     [!code-csharp[c_SettingSecurityMode#2](../../../samples/snippets/csharp/VS_Snippets_CFX/c_settingsecuritymode/cs/source.cs#2)]
     [!code-vb[c_SettingSecurityMode#2](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_settingsecuritymode/vb/source.vb#2)]  
  
     <span data-ttu-id="f21c7-116">または、モードを TransportWithMessageCredential (メッセージ資格情報付きトランスポート) に設定します。コードは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="f21c7-116">Or set the mode to transport with message credentials, as shown in the following code.</span></span>  
  
     [!code-csharp[c_SettingSecurityMode#3](../../../samples/snippets/csharp/VS_Snippets_CFX/c_settingsecuritymode/cs/source.cs#3)]
     [!code-vb[c_SettingSecurityMode#3](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_settingsecuritymode/vb/source.vb#3)]  
  
3. <span data-ttu-id="f21c7-117">次のコードに示すように、バインディングのコンストラクターでモードを設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="f21c7-117">You can also set the mode in the constructor of the binding, as shown in the following code.</span></span>  
  
     [!code-csharp[c_SettingSecurityMode#4](../../../samples/snippets/csharp/VS_Snippets_CFX/c_settingsecuritymode/cs/source.cs#4)]
     [!code-vb[c_SettingSecurityMode#4](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_settingsecuritymode/vb/source.vb#4)]  
  
## <a name="setting-the-clientcredentialtype-property"></a><span data-ttu-id="f21c7-118">ClientCredentialType プロパティの設定</span><span class="sxs-lookup"><span data-stu-id="f21c7-118">Setting the ClientCredentialType Property</span></span>  
 <span data-ttu-id="f21c7-119">モードを上記の 3 つの値のいずれかに設定すると、`ClientCredentialType` プロパティの設定方法が決まります。</span><span class="sxs-lookup"><span data-stu-id="f21c7-119">Setting the mode to one of the three values determines how you set the `ClientCredentialType` property.</span></span> <span data-ttu-id="f21c7-120">たとえば、<xref:System.ServiceModel.WSHttpBinding> クラスを使用し、モードを `Transport` に設定した場合、<xref:System.ServiceModel.HttpTransportSecurity.ClientCredentialType%2A> クラスの <xref:System.ServiceModel.HttpTransportSecurity> プロパティを適切な値に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f21c7-120">For example, using the <xref:System.ServiceModel.WSHttpBinding> class, setting the mode to `Transport` means you must set the <xref:System.ServiceModel.HttpTransportSecurity.ClientCredentialType%2A> property of the <xref:System.ServiceModel.HttpTransportSecurity> class to an appropriate value.</span></span>  
  
#### <a name="to-set-the-clientcredentialtype-property-for-transport-mode"></a><span data-ttu-id="f21c7-121">トランスポート モードの ClientCredentialType プロパティを設定するには</span><span class="sxs-lookup"><span data-stu-id="f21c7-121">To set the ClientCredentialType property for Transport mode</span></span>  
  
1. <span data-ttu-id="f21c7-122">バインディングのインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="f21c7-122">Create an instance of the binding.</span></span>  
  
2. <span data-ttu-id="f21c7-123">`Mode` プロパティを `Transport`に設定します。</span><span class="sxs-lookup"><span data-stu-id="f21c7-123">Set the `Mode` property to `Transport`.</span></span>  
  
3. <span data-ttu-id="f21c7-124">`ClientCredential` プロパティに適切な値を設定します。</span><span class="sxs-lookup"><span data-stu-id="f21c7-124">Set the `ClientCredential` property to an appropriate value.</span></span> <span data-ttu-id="f21c7-125">プロパティを `Windows` に設定するコードを次に示します。</span><span class="sxs-lookup"><span data-stu-id="f21c7-125">The following code sets the property to `Windows`.</span></span>  
  
     [!code-csharp[c_SettingSecurityMode#5](../../../samples/snippets/csharp/VS_Snippets_CFX/c_settingsecuritymode/cs/source.cs#5)]
     [!code-vb[c_SettingSecurityMode#5](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_settingsecuritymode/vb/source.vb#5)]  
  
#### <a name="to-set-the-clientcredentialtype-property-for-message-mode"></a><span data-ttu-id="f21c7-126">メッセージ モードの ClientCredentialType プロパティを設定するには</span><span class="sxs-lookup"><span data-stu-id="f21c7-126">To set the ClientCredentialType property for Message mode</span></span>  
  
1. <span data-ttu-id="f21c7-127">バインディングのインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="f21c7-127">Create an instance of the binding.</span></span>  
  
2. <span data-ttu-id="f21c7-128">`Mode` プロパティを `Message`に設定します。</span><span class="sxs-lookup"><span data-stu-id="f21c7-128">Set the `Mode` property to `Message`.</span></span>  
  
3. <span data-ttu-id="f21c7-129">`ClientCredential` プロパティに適切な値を設定します。</span><span class="sxs-lookup"><span data-stu-id="f21c7-129">Set the `ClientCredential` property to an appropriate value.</span></span> <span data-ttu-id="f21c7-130">プロパティを `Certificate` に設定するコードを次に示します。</span><span class="sxs-lookup"><span data-stu-id="f21c7-130">The following code sets the property to `Certificate`.</span></span>  
  
     [!code-csharp[c_SettingSecurityMode#6](../../../samples/snippets/csharp/VS_Snippets_CFX/c_settingsecuritymode/cs/source.cs#6)]
     [!code-vb[c_SettingSecurityMode#6](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_settingsecuritymode/vb/source.vb#6)]  
  
#### <a name="to-set-the-mode-and-clientcredentialtype-property-in-configuration"></a><span data-ttu-id="f21c7-131">構成でモードと ClientCredentialType プロパティを設定するには</span><span class="sxs-lookup"><span data-stu-id="f21c7-131">To set the Mode and ClientCredentialType property in configuration</span></span>  
  
1. <span data-ttu-id="f21c7-132">適切なバインド要素を追加、 [\<バインド >](../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)構成ファイルの要素。</span><span class="sxs-lookup"><span data-stu-id="f21c7-132">Add an appropriate binding element to the [\<bindings>](../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) element of the configuration file.</span></span> <span data-ttu-id="f21c7-133">次の例では、追加、 [ \<wsHttpBinding >](../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)要素。</span><span class="sxs-lookup"><span data-stu-id="f21c7-133">The following example adds a [\<wsHttpBinding>](../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) element.</span></span>  
  
2. <span data-ttu-id="f21c7-134">追加、`<binding>`要素とその`name`属性に適切な値。</span><span class="sxs-lookup"><span data-stu-id="f21c7-134">Add a `<binding>` element and set its `name` attribute to an appropriate value.</span></span>  
  
3. <span data-ttu-id="f21c7-135">`<security>` 要素を追加し、`mode` 属性を `Message`、`Transport`、または `TransportWithMessageCredential` に設定します。</span><span class="sxs-lookup"><span data-stu-id="f21c7-135">Add a `<security>` element and set the `mode` attribute to `Message`, `Transport`, or `TransportWithMessageCredential`.</span></span>  
  
4. <span data-ttu-id="f21c7-136">モードを `Transport` に設定した場合は、`<transport>` 要素を追加し、`clientCredential` 属性を適切な値に設定します。</span><span class="sxs-lookup"><span data-stu-id="f21c7-136">If the mode is set to `Transport`, add a `<transport>` element and set the `clientCredential` attribute to an appropriate value.</span></span>  
  
     <span data-ttu-id="f21c7-137">モードを "`Transport"` に設定し、`clientCredentialType` 要素の `<transport>` 属性を "`Windows"` に設定する例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="f21c7-137">The following example sets the mode to "`Transport"`, and then sets the `clientCredentialType` attribute of the `<transport>` element to "`Windows"`.</span></span>  
  
    ```xml  
    <wsHttpBinding>  
    <binding name="TransportSecurity">  
        <security mode="Transport" >  
           <transport clientCredentialType = "Windows" />  
        </security>  
    </binding>  
    </wsHttpBinding >  
    ```  
  
     <span data-ttu-id="f21c7-138">または、`security mode` を "`Message"` に設定し、その後に `<"message">` 要素を指定します。</span><span class="sxs-lookup"><span data-stu-id="f21c7-138">Alternatively, set the `security mode` to "`Message"`, followed by a `<"message">` element.</span></span> <span data-ttu-id="f21c7-139">この例では、`clientCredentialType` を "`Certificate"` に設定しています。</span><span class="sxs-lookup"><span data-stu-id="f21c7-139">This example sets the `clientCredentialType` to "`Certificate"`.</span></span>  
  
    ```xml  
    <wsHttpBinding>  
    <binding name="MessageSecurity">  
        <security mode="Message" >  
           <message clientCredentialType = "Certificate" />  
        </security>  
    </binding>  
    </wsHttpBinding >  
    ```  
  
     <span data-ttu-id="f21c7-140">次に説明する <xref:System.ServiceModel.BasicHttpSecurityMode.TransportWithMessageCredential> 値は、特殊なケースで使用されます。</span><span class="sxs-lookup"><span data-stu-id="f21c7-140">Using the <xref:System.ServiceModel.BasicHttpSecurityMode.TransportWithMessageCredential> value is a special case, and is explained below.</span></span>  
  
### <a name="using-transportwithmessagecredential"></a><span data-ttu-id="f21c7-141">TransportWithMessageCredential の使用</span><span class="sxs-lookup"><span data-stu-id="f21c7-141">Using TransportWithMessageCredential</span></span>  
 <span data-ttu-id="f21c7-142">セキュリティ モードを `TransportWithMessageCredential` に設定した場合、トランスポート レベルのセキュリティを提供する実際の機構はトランスポートによって決まります。</span><span class="sxs-lookup"><span data-stu-id="f21c7-142">When setting the security mode to `TransportWithMessageCredential`, the transport determines the actual mechanism that provides the transport-level security.</span></span> <span data-ttu-id="f21c7-143">たとえば、HTTP プロトコルでは SSL (Secure Sockets Layer) over HTTP (HTTPS) を使用します。</span><span class="sxs-lookup"><span data-stu-id="f21c7-143">For example, the HTTP protocol uses Secure Sockets Layer (SSL) over HTTP (HTTPS).</span></span> <span data-ttu-id="f21c7-144">このため、トランスポート セキュリティ オブジェクト (`ClientCredentialType` など) の <xref:System.ServiceModel.HttpTransportSecurity> プロパティを設定しても無視されます。</span><span class="sxs-lookup"><span data-stu-id="f21c7-144">Therefore, setting the `ClientCredentialType` property of any transport security object (such as <xref:System.ServiceModel.HttpTransportSecurity>) is ignored.</span></span>  <span data-ttu-id="f21c7-145">つまり、メッセージ セキュリティ オブジェクト (`ClientCredentialType` バインディングの場合は `WSHttpBinding` オブジェクト) の <xref:System.ServiceModel.NonDualMessageSecurityOverHttp> だけを設定できます。</span><span class="sxs-lookup"><span data-stu-id="f21c7-145">In other words, you can only set the `ClientCredentialType` of the message security object (for the `WSHttpBinding` binding, the <xref:System.ServiceModel.NonDualMessageSecurityOverHttp> object).</span></span>  
  
 <span data-ttu-id="f21c7-146">詳細については、「[方法 :トランスポート セキュリティの使用とメッセージ資格情報](../../../docs/framework/wcf/feature-details/how-to-use-transport-security-and-message-credentials.md)します。</span><span class="sxs-lookup"><span data-stu-id="f21c7-146">For more information, see [How to: Use Transport Security and Message Credentials](../../../docs/framework/wcf/feature-details/how-to-use-transport-security-and-message-credentials.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f21c7-147">関連項目</span><span class="sxs-lookup"><span data-stu-id="f21c7-147">See also</span></span>

- [<span data-ttu-id="f21c7-148">方法: SSL 証明書でポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="f21c7-148">How to: Configure a Port with an SSL Certificate</span></span>](../../../docs/framework/wcf/feature-details/how-to-configure-a-port-with-an-ssl-certificate.md)
- [<span data-ttu-id="f21c7-149">方法: トランスポート セキュリティの使用とメッセージ資格情報</span><span class="sxs-lookup"><span data-stu-id="f21c7-149">How to: Use Transport Security and Message Credentials</span></span>](../../../docs/framework/wcf/feature-details/how-to-use-transport-security-and-message-credentials.md)
- [<span data-ttu-id="f21c7-150">トランスポート セキュリティ</span><span class="sxs-lookup"><span data-stu-id="f21c7-150">Transport Security</span></span>](../../../docs/framework/wcf/feature-details/transport-security.md)
- [<span data-ttu-id="f21c7-151">メッセージのセキュリティ</span><span class="sxs-lookup"><span data-stu-id="f21c7-151">Message Security</span></span>](../../../docs/framework/wcf/feature-details/message-security-in-wcf.md)
- [<span data-ttu-id="f21c7-152">セキュリティの概要</span><span class="sxs-lookup"><span data-stu-id="f21c7-152">Security Overview</span></span>](../../../docs/framework/wcf/feature-details/security-overview.md)
- [<span data-ttu-id="f21c7-153">システム標準のバインディング</span><span class="sxs-lookup"><span data-stu-id="f21c7-153">System-Provided Bindings</span></span>](../../../docs/framework/wcf/system-provided-bindings.md)
- [<span data-ttu-id="f21c7-154">\<security></span><span class="sxs-lookup"><span data-stu-id="f21c7-154">\<security></span></span>](../../../docs/framework/configure-apps/file-schema/wcf/security-of-wshttpbinding.md)
- [<span data-ttu-id="f21c7-155">\<security></span><span class="sxs-lookup"><span data-stu-id="f21c7-155">\<security></span></span>](../../../docs/framework/configure-apps/file-schema/wcf/security-of-basichttpbinding.md)
- [<span data-ttu-id="f21c7-156">\<security></span><span class="sxs-lookup"><span data-stu-id="f21c7-156">\<security></span></span>](../../../docs/framework/configure-apps/file-schema/wcf/security-of-nettcpbinding.md)
