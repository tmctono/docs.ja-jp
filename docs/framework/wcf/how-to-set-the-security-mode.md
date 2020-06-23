---
title: '方法: セキュリティ モードを設定する'
description: ほとんどの定義済みバインディングで、トランスポート、メッセージ、および TransportWithMessageCredential の3つの一般的な WCF セキュリティモードを設定する方法について説明します。
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Mode property
- WCF, security mode
- WCF, security
ms.assetid: 6e01dd9f-b5dd-4474-b24c-06e124de4ff7
ms.openlocfilehash: 2f834e1930b7676592f6cbc29a577424d75ebc01
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/23/2020
ms.locfileid: "85244544"
---
# <a name="how-to-set-the-security-mode"></a><span data-ttu-id="b8357-103">方法: セキュリティ モードを設定する</span><span class="sxs-lookup"><span data-stu-id="b8357-103">How to: Set the Security Mode</span></span>

<span data-ttu-id="b8357-104">Windows Communication Foundation (WCF) セキュリティには、トランスポート、メッセージ、および "メッセージ資格情報によるトランスポート" のほとんどの定義済みバインディングで検出された3つの一般的なセキュリティモードがあります。</span><span class="sxs-lookup"><span data-stu-id="b8357-104">Windows Communication Foundation (WCF) security has three common security modes that are found on most predefined bindings: transport, message, and "transport with message credential."</span></span> <span data-ttu-id="b8357-105">これ以外に、2 つのバインディングに固有の 2 つのモードがあります。<xref:System.ServiceModel.BasicHttpBinding> の "トランスポート資格情報専用" モードと、<xref:System.ServiceModel.NetMsmqBinding> の "両方" モードです。</span><span class="sxs-lookup"><span data-stu-id="b8357-105">Two additional modes are specific to two bindings: the "transport-credential only" mode found on the <xref:System.ServiceModel.BasicHttpBinding>, and the "Both" mode, found on the <xref:System.ServiceModel.NetMsmqBinding>.</span></span> <span data-ttu-id="b8357-106">ここでは、3 つの共通のセキュリティモードである <xref:System.ServiceModel.SecurityMode.Transport>、<xref:System.ServiceModel.SecurityMode.Message>、および <xref:System.ServiceModel.SecurityMode.TransportWithMessageCredential> に重点を置いて説明します。</span><span class="sxs-lookup"><span data-stu-id="b8357-106">However, this topic concentrates on the three common security modes: <xref:System.ServiceModel.SecurityMode.Transport>, <xref:System.ServiceModel.SecurityMode.Message>, and <xref:System.ServiceModel.SecurityMode.TransportWithMessageCredential>.</span></span>

<span data-ttu-id="b8357-107">ただし、これらのモードがすべての定義済みバインディングでサポートされるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="b8357-107">Note that not every predefined binding supports all of these modes.</span></span> <span data-ttu-id="b8357-108">ここでは、<xref:System.ServiceModel.WSHttpBinding> クラスと <xref:System.ServiceModel.NetTcpBinding> クラスでモードを設定し、プログラムと構成の両方を使用してモードを設定する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="b8357-108">This topic sets the mode with the <xref:System.ServiceModel.WSHttpBinding> and <xref:System.ServiceModel.NetTcpBinding> classes and demonstrates how to set the mode both programmatically and through configuration.</span></span>

<span data-ttu-id="b8357-109">詳細については、「WCF セキュリティ」、「[セキュリティの概要](./feature-details/security-overview.md)」、「[サービス](securing-services.md)のセキュリティ保護」、および「[サービスとクライアント](./feature-details/securing-services-and-clients.md)のセキュリティ保護」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b8357-109">For more information, see WCF security, see [Security Overview](./feature-details/security-overview.md), [Securing Services](securing-services.md), and [Securing Services and Clients](./feature-details/securing-services-and-clients.md).</span></span> <span data-ttu-id="b8357-110">トランスポートモードとメッセージの詳細については、「[トランスポートセキュリティ](./feature-details/transport-security.md)と[メッセージセキュリティ](./feature-details/message-security-in-wcf.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b8357-110">For more information about transport mode and message, see [Transport Security](./feature-details/transport-security.md) and [Message Security](./feature-details/message-security-in-wcf.md).</span></span>

## <a name="to-set-the-security-mode-in-code"></a><span data-ttu-id="b8357-111">コードでセキュリティ モードを設定するには</span><span class="sxs-lookup"><span data-stu-id="b8357-111">To set the security mode in code</span></span>

1. <span data-ttu-id="b8357-112">使用しているバインディング クラスのインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="b8357-112">Create an instance of the binding class that you are using.</span></span> <span data-ttu-id="b8357-113">定義済みバインディングの一覧については、「[システム指定のバインディング](system-provided-bindings.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b8357-113">For a list of predefined bindings, see [System-Provided Bindings](system-provided-bindings.md).</span></span> <span data-ttu-id="b8357-114">この例では、<xref:System.ServiceModel.WSHttpBinding> クラスのインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="b8357-114">This example creates an instance of the <xref:System.ServiceModel.WSHttpBinding> class.</span></span>

2. <span data-ttu-id="b8357-115">`Mode` プロパティから返されるオブジェクトの `Security` プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="b8357-115">Set the `Mode` property of the object returned by the `Security` property.</span></span>

     [!code-csharp[c_SettingSecurityMode#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_settingsecuritymode/cs/source.cs#1)]
     [!code-vb[c_SettingSecurityMode#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_settingsecuritymode/vb/source.vb#1)]

     <span data-ttu-id="b8357-116">または、モードを Message (メッセージ) に設定します。コードは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="b8357-116">Alternatively, set the mode to message, as shown in the following code.</span></span>

     [!code-csharp[c_SettingSecurityMode#2](../../../samples/snippets/csharp/VS_Snippets_CFX/c_settingsecuritymode/cs/source.cs#2)]
     [!code-vb[c_SettingSecurityMode#2](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_settingsecuritymode/vb/source.vb#2)]

     <span data-ttu-id="b8357-117">または、モードを TransportWithMessageCredential (メッセージ資格情報付きトランスポート) に設定します。コードは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="b8357-117">Or set the mode to transport with message credentials, as shown in the following code.</span></span>

     [!code-csharp[c_SettingSecurityMode#3](../../../samples/snippets/csharp/VS_Snippets_CFX/c_settingsecuritymode/cs/source.cs#3)]
     [!code-vb[c_SettingSecurityMode#3](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_settingsecuritymode/vb/source.vb#3)]

3. <span data-ttu-id="b8357-118">次のコードに示すように、バインディングのコンストラクターでモードを設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="b8357-118">You can also set the mode in the constructor of the binding, as shown in the following code.</span></span>

     [!code-csharp[c_SettingSecurityMode#4](../../../samples/snippets/csharp/VS_Snippets_CFX/c_settingsecuritymode/cs/source.cs#4)]
     [!code-vb[c_SettingSecurityMode#4](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_settingsecuritymode/vb/source.vb#4)]

## <a name="setting-the-clientcredentialtype-property"></a><span data-ttu-id="b8357-119">ClientCredentialType プロパティの設定</span><span class="sxs-lookup"><span data-stu-id="b8357-119">Setting the ClientCredentialType Property</span></span>

<span data-ttu-id="b8357-120">モードを上記の 3 つの値のいずれかに設定すると、`ClientCredentialType` プロパティの設定方法が決まります。</span><span class="sxs-lookup"><span data-stu-id="b8357-120">Setting the mode to one of the three values determines how you set the `ClientCredentialType` property.</span></span> <span data-ttu-id="b8357-121">たとえば、<xref:System.ServiceModel.WSHttpBinding> クラスを使用し、モードを `Transport` に設定した場合、<xref:System.ServiceModel.HttpTransportSecurity.ClientCredentialType%2A> クラスの <xref:System.ServiceModel.HttpTransportSecurity> プロパティを適切な値に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b8357-121">For example, using the <xref:System.ServiceModel.WSHttpBinding> class, setting the mode to `Transport` means you must set the <xref:System.ServiceModel.HttpTransportSecurity.ClientCredentialType%2A> property of the <xref:System.ServiceModel.HttpTransportSecurity> class to an appropriate value.</span></span>

### <a name="to-set-the-clientcredentialtype-property-for-transport-mode"></a><span data-ttu-id="b8357-122">トランスポート モードの ClientCredentialType プロパティを設定するには</span><span class="sxs-lookup"><span data-stu-id="b8357-122">To set the ClientCredentialType property for Transport mode</span></span>

1. <span data-ttu-id="b8357-123">バインディングのインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="b8357-123">Create an instance of the binding.</span></span>

2. <span data-ttu-id="b8357-124">`Mode` プロパティを `Transport`に設定します。</span><span class="sxs-lookup"><span data-stu-id="b8357-124">Set the `Mode` property to `Transport`.</span></span>

3. <span data-ttu-id="b8357-125">`ClientCredential` プロパティに適切な値を設定します。</span><span class="sxs-lookup"><span data-stu-id="b8357-125">Set the `ClientCredential` property to an appropriate value.</span></span> <span data-ttu-id="b8357-126">プロパティを `Windows` に設定するコードを次に示します。</span><span class="sxs-lookup"><span data-stu-id="b8357-126">The following code sets the property to `Windows`.</span></span>

     [!code-csharp[c_SettingSecurityMode#5](../../../samples/snippets/csharp/VS_Snippets_CFX/c_settingsecuritymode/cs/source.cs#5)]
     [!code-vb[c_SettingSecurityMode#5](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_settingsecuritymode/vb/source.vb#5)]

### <a name="to-set-the-clientcredentialtype-property-for-message-mode"></a><span data-ttu-id="b8357-127">メッセージ モードの ClientCredentialType プロパティを設定するには</span><span class="sxs-lookup"><span data-stu-id="b8357-127">To set the ClientCredentialType property for Message mode</span></span>

1. <span data-ttu-id="b8357-128">バインディングのインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="b8357-128">Create an instance of the binding.</span></span>

2. <span data-ttu-id="b8357-129">`Mode` プロパティを `Message`に設定します。</span><span class="sxs-lookup"><span data-stu-id="b8357-129">Set the `Mode` property to `Message`.</span></span>

3. <span data-ttu-id="b8357-130">`ClientCredential` プロパティに適切な値を設定します。</span><span class="sxs-lookup"><span data-stu-id="b8357-130">Set the `ClientCredential` property to an appropriate value.</span></span> <span data-ttu-id="b8357-131">プロパティを `Certificate` に設定するコードを次に示します。</span><span class="sxs-lookup"><span data-stu-id="b8357-131">The following code sets the property to `Certificate`.</span></span>

     [!code-csharp[c_SettingSecurityMode#6](../../../samples/snippets/csharp/VS_Snippets_CFX/c_settingsecuritymode/cs/source.cs#6)]
     [!code-vb[c_SettingSecurityMode#6](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_settingsecuritymode/vb/source.vb#6)]

### <a name="to-set-the-mode-and-clientcredentialtype-property-in-configuration"></a><span data-ttu-id="b8357-132">構成でモードと ClientCredentialType プロパティを設定するには</span><span class="sxs-lookup"><span data-stu-id="b8357-132">To set the Mode and ClientCredentialType property in configuration</span></span>

1. <span data-ttu-id="b8357-133">構成ファイルの要素に適切なバインド要素を追加 [\<bindings>](../configure-apps/file-schema/wcf/bindings.md) します。</span><span class="sxs-lookup"><span data-stu-id="b8357-133">Add an appropriate binding element to the [\<bindings>](../configure-apps/file-schema/wcf/bindings.md) element of the configuration file.</span></span> <span data-ttu-id="b8357-134">次の例では、要素を追加し [\<wsHttpBinding>](../configure-apps/file-schema/wcf/wshttpbinding.md) ます。</span><span class="sxs-lookup"><span data-stu-id="b8357-134">The following example adds a [\<wsHttpBinding>](../configure-apps/file-schema/wcf/wshttpbinding.md) element.</span></span>

2. <span data-ttu-id="b8357-135">要素を追加 `<binding>` し、その `name` 属性を適切な値に設定します。</span><span class="sxs-lookup"><span data-stu-id="b8357-135">Add a `<binding>` element and set its `name` attribute to an appropriate value.</span></span>

3. <span data-ttu-id="b8357-136">`<security>` 要素を追加し、`mode` 属性を `Message`、`Transport`、または `TransportWithMessageCredential` に設定します。</span><span class="sxs-lookup"><span data-stu-id="b8357-136">Add a `<security>` element and set the `mode` attribute to `Message`, `Transport`, or `TransportWithMessageCredential`.</span></span>

4. <span data-ttu-id="b8357-137">モードを `Transport` に設定した場合は、`<transport>` 要素を追加し、`clientCredential` 属性を適切な値に設定します。</span><span class="sxs-lookup"><span data-stu-id="b8357-137">If the mode is set to `Transport`, add a `<transport>` element and set the `clientCredential` attribute to an appropriate value.</span></span>

     <span data-ttu-id="b8357-138">モードを "`Transport"` に設定し、`clientCredentialType` 要素の `<transport>` 属性を "`Windows"` に設定する例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="b8357-138">The following example sets the mode to "`Transport"`, and then sets the `clientCredentialType` attribute of the `<transport>` element to "`Windows"`.</span></span>

    ```xml
    <wsHttpBinding>
    <binding name="TransportSecurity">
        <security mode="Transport" >
           <transport clientCredentialType = "Windows" />
        </security>
    </binding>
    </wsHttpBinding >
    ```

     <span data-ttu-id="b8357-139">または、`security mode` を "`Message"` に設定し、その後に `<"message">` 要素を指定します。</span><span class="sxs-lookup"><span data-stu-id="b8357-139">Alternatively, set the `security mode` to "`Message"`, followed by a `<"message">` element.</span></span> <span data-ttu-id="b8357-140">この例では、`clientCredentialType` を "`Certificate"` に設定しています。</span><span class="sxs-lookup"><span data-stu-id="b8357-140">This example sets the `clientCredentialType` to "`Certificate"`.</span></span>

    ```xml
    <wsHttpBinding>
    <binding name="MessageSecurity">
        <security mode="Message" >
           <message clientCredentialType = "Certificate" />
        </security>
    </binding>
    </wsHttpBinding >
    ```

     <span data-ttu-id="b8357-141">次に説明する <xref:System.ServiceModel.BasicHttpSecurityMode.TransportWithMessageCredential> 値は、特殊なケースで使用されます。</span><span class="sxs-lookup"><span data-stu-id="b8357-141">Using the <xref:System.ServiceModel.BasicHttpSecurityMode.TransportWithMessageCredential> value is a special case, and is explained below.</span></span>

### <a name="using-transportwithmessagecredential"></a><span data-ttu-id="b8357-142">TransportWithMessageCredential の使用</span><span class="sxs-lookup"><span data-stu-id="b8357-142">Using TransportWithMessageCredential</span></span>

<span data-ttu-id="b8357-143">セキュリティ モードを `TransportWithMessageCredential` に設定した場合、トランスポート レベルのセキュリティを提供する実際の機構はトランスポートによって決まります。</span><span class="sxs-lookup"><span data-stu-id="b8357-143">When setting the security mode to `TransportWithMessageCredential`, the transport determines the actual mechanism that provides the transport-level security.</span></span> <span data-ttu-id="b8357-144">たとえば、HTTP プロトコルでは SSL (Secure Sockets Layer) over HTTP (HTTPS) を使用します。</span><span class="sxs-lookup"><span data-stu-id="b8357-144">For example, the HTTP protocol uses Secure Sockets Layer (SSL) over HTTP (HTTPS).</span></span> <span data-ttu-id="b8357-145">このため、トランスポート セキュリティ オブジェクト (`ClientCredentialType` など) の <xref:System.ServiceModel.HttpTransportSecurity> プロパティを設定しても無視されます。</span><span class="sxs-lookup"><span data-stu-id="b8357-145">Therefore, setting the `ClientCredentialType` property of any transport security object (such as <xref:System.ServiceModel.HttpTransportSecurity>) is ignored.</span></span>  <span data-ttu-id="b8357-146">つまり、メッセージ セキュリティ オブジェクト (`ClientCredentialType` バインディングの場合は `WSHttpBinding` オブジェクト) の <xref:System.ServiceModel.NonDualMessageSecurityOverHttp> だけを設定できます。</span><span class="sxs-lookup"><span data-stu-id="b8357-146">In other words, you can only set the `ClientCredentialType` of the message security object (for the `WSHttpBinding` binding, the <xref:System.ServiceModel.NonDualMessageSecurityOverHttp> object).</span></span>

<span data-ttu-id="b8357-147">詳細については、「[方法: トランスポートセキュリティとメッセージ資格情報を使用](./feature-details/how-to-use-transport-security-and-message-credentials.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b8357-147">For more information, see [How to: Use Transport Security and Message Credentials](./feature-details/how-to-use-transport-security-and-message-credentials.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="b8357-148">関連項目</span><span class="sxs-lookup"><span data-stu-id="b8357-148">See also</span></span>

- [<span data-ttu-id="b8357-149">方法: SSL 証明書を使用してポートを構成する</span><span class="sxs-lookup"><span data-stu-id="b8357-149">How to: Configure a Port with an SSL Certificate</span></span>](./feature-details/how-to-configure-a-port-with-an-ssl-certificate.md)
- [<span data-ttu-id="b8357-150">方法: トランスポート セキュリティとメッセージ資格情報を使用する</span><span class="sxs-lookup"><span data-stu-id="b8357-150">How to: Use Transport Security and Message Credentials</span></span>](./feature-details/how-to-use-transport-security-and-message-credentials.md)
- [<span data-ttu-id="b8357-151">トランスポートセキュリティ</span><span class="sxs-lookup"><span data-stu-id="b8357-151">Transport Security</span></span>](./feature-details/transport-security.md)
- [<span data-ttu-id="b8357-152">メッセージのセキュリティ</span><span class="sxs-lookup"><span data-stu-id="b8357-152">Message Security</span></span>](./feature-details/message-security-in-wcf.md)
- [<span data-ttu-id="b8357-153">セキュリティの概要</span><span class="sxs-lookup"><span data-stu-id="b8357-153">Security Overview</span></span>](./feature-details/security-overview.md)
- [<span data-ttu-id="b8357-154">システム標準のバインディング</span><span class="sxs-lookup"><span data-stu-id="b8357-154">System-Provided Bindings</span></span>](system-provided-bindings.md)
- [\<security>](../configure-apps/file-schema/wcf/security-of-wshttpbinding.md)
- [\<security>](../configure-apps/file-schema/wcf/security-of-basichttpbinding.md)
- [\<security>](../configure-apps/file-schema/wcf/security-of-nettcpbinding.md)
