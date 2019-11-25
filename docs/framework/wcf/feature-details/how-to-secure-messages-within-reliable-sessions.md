---
title: '方法 : 信頼できるセッション内でメッセージをセキュリティで保護する'
ms.date: 03/30/2017
ms.assetid: aee33e50-936f-4486-9ca8-c1520c19a62d
ms.openlocfilehash: edff27fe9649387c1922c34e72ef59d615e52b90
ms.sourcegitcommit: fbb8a593a511ce667992502a3ce6d8f65c594edf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/16/2019
ms.locfileid: "74141668"
---
# <a name="how-to-secure-messages-within-reliable-sessions"></a><span data-ttu-id="ccfe0-102">方法 : 信頼できるセッション内でメッセージをセキュリティで保護する</span><span class="sxs-lookup"><span data-stu-id="ccfe0-102">How to: Secure Messages within Reliable Sessions</span></span>

<span data-ttu-id="ccfe0-103">ここでは、信頼できるセッション内で交換されるメッセージに対して、メッセージ レベルのセキュリティを有効にするために必要な手順について説明します。このとき、信頼できるセッションがオプションでサポートされているシステム指定のバインディングを使用します。</span><span class="sxs-lookup"><span data-stu-id="ccfe0-103">This topic outlines the steps required to enable message-level security for messages exchanged within a reliable session using one of the system-provided bindings that support such a session, but not by default.</span></span> <span data-ttu-id="ccfe0-104">コードを使用するか、構成ファイルで宣言によって、セキュリティで保護された信頼できるセッションを強制的に有効にします。</span><span class="sxs-lookup"><span data-stu-id="ccfe0-104">Enable a secure, reliable session either imperatively by using code or declaratively in the configuration file.</span></span> <span data-ttu-id="ccfe0-105">この手順では、クライアントとサービスの構成ファイルを使用して、セキュリティで保護された信頼できるセッションを有効にします。</span><span class="sxs-lookup"><span data-stu-id="ccfe0-105">This procedure uses the client and service configuration files to enable the secure, reliable session.</span></span>

<span data-ttu-id="ccfe0-106">この手順の主な部分は、次の 3 つのタスクで構成されます。</span><span class="sxs-lookup"><span data-stu-id="ccfe0-106">This procedure consists of the following three key tasks:</span></span>

1. <span data-ttu-id="ccfe0-107">クライアントとサービスのメッセージ交換は信頼できるセッション内で行うことを指定します。</span><span class="sxs-lookup"><span data-stu-id="ccfe0-107">Specify that the client and service exchange messages within a reliable session.</span></span>

1. <span data-ttu-id="ccfe0-108">信頼できるセッション内でメッセージ レベルのセキュリティを要求します。</span><span class="sxs-lookup"><span data-stu-id="ccfe0-108">Require message-level security within the reliable session.</span></span>

1. <span data-ttu-id="ccfe0-109">サービスに対する認証時にクライアントが使用する必要があるクライアント資格情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="ccfe0-109">Specify the client credential type that the client must use to be authenticated with the service.</span></span>

<span data-ttu-id="ccfe0-110">最初のタスクでは、エンドポイント構成要素に、(この例では `MessageSecurity`) という名前のバインディング構成を参照する `bindingConfiguration` 属性が含まれていることが重要です。</span><span class="sxs-lookup"><span data-stu-id="ccfe0-110">It's important in the first task that the endpoint configuration element contain a `bindingConfiguration` attribute that references a binding configuration named (in this example) `MessageSecurity`.</span></span> <span data-ttu-id="ccfe0-111">[ **\<binding >** ](../../configure-apps/file-schema/wcf/bindings.md) configuration 要素は、この名前を参照して、 [ **\<reliableSession >** ](https://docs.microsoft.com/previous-versions/ms731375(v=vs.90))要素の `enabled` 属性を `true`に設定することによって、信頼できるセッションを有効にします。</span><span class="sxs-lookup"><span data-stu-id="ccfe0-111">The [**\<binding>**](../../configure-apps/file-schema/wcf/bindings.md) configuration element then references this name to enable reliable sessions by setting the `enabled` attribute of the [**\<reliableSession>**](https://docs.microsoft.com/previous-versions/ms731375(v=vs.90)) element to `true`.</span></span> <span data-ttu-id="ccfe0-112">信頼できるセッション内で使用できる順序付き配信の保証は、`ordered` 属性を `true` に設定することによって要求できます。</span><span class="sxs-lookup"><span data-stu-id="ccfe0-112">You can require that the ordered delivery assurances are available within a reliable session by setting the `ordered` attribute to `true`.</span></span>

<span data-ttu-id="ccfe0-113">この構成手順の基になっている例のソースコピーについては、「 [WS Reliable Session](../../../../docs/framework/wcf/samples/ws-reliable-session.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ccfe0-113">For the source copy of the example on which this configuration procedure is based, see the [WS Reliable Session](../../../../docs/framework/wcf/samples/ws-reliable-session.md).</span></span>

<span data-ttu-id="ccfe0-114">2番目のタスクの重要な項目は、クライアントとサービスの **\<binding >** 要素に含まれる **\<セキュリティ >** 要素の `mode` 属性を `Message`に設定することによって実現されます。</span><span class="sxs-lookup"><span data-stu-id="ccfe0-114">The essential items of the second task are accomplished by setting the `mode` attribute of the **\<security>** element contained in the **\<binding>** element of the client and service to `Message`.</span></span>

<span data-ttu-id="ccfe0-115">3番目のタスクの重要な項目は、クライアントとサービスの **\<セキュリティ >** 要素に含まれる **\<メッセージ >** 要素の `clientCredentialType` 属性を `Certificate`に設定することによって実現されます。</span><span class="sxs-lookup"><span data-stu-id="ccfe0-115">The essential items of the third task are accomplished by setting the `clientCredentialType` attribute of the **\<message>** element contained in the **\<security>** element of the client and service to `Certificate`.</span></span>

> [!NOTE]
> <span data-ttu-id="ccfe0-116">信頼できるセッションでメッセージセキュリティを使用する場合、信頼できるメッセージは、最初のエラー時に例外をスローするのではなく、タイムアウトが発生するまで、認証されていないクライアントの認証を試みます。</span><span class="sxs-lookup"><span data-stu-id="ccfe0-116">When using message security with reliable sessions, Reliable Messaging attempts to authenticate an unauthenticated client until a timeout occurs instead of throwing an exception upon first failure.</span></span>

### <a name="configure-the-service-with-a-wshttpbinding-to-use-a-reliable-session"></a><span data-ttu-id="ccfe0-117">信頼できるセッションを使用するようにサービスを WSHttpBinding で構成する</span><span class="sxs-lookup"><span data-stu-id="ccfe0-117">Configure the service with a WSHttpBinding to use a reliable session</span></span>

<span data-ttu-id="ccfe0-118">この手順については[、「方法: 信頼できるセッション内でメッセージを交換](../../../../docs/framework/wcf/feature-details/how-to-exchange-messages-within-a-reliable-session.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ccfe0-118">This procedure is described in [How to: Exchange Messages Within a Reliable Session](../../../../docs/framework/wcf/feature-details/how-to-exchange-messages-within-a-reliable-session.md).</span></span>

### <a name="configure-the-client-with-a-wshttpbinding-to-use-a-reliable-session"></a><span data-ttu-id="ccfe0-119">信頼できるセッションを使用するようにクライアントを WSHttpBinding で構成する</span><span class="sxs-lookup"><span data-stu-id="ccfe0-119">Configure the client with a WSHttpBinding to use a reliable session</span></span>

<span data-ttu-id="ccfe0-120">この手順については[、「方法: 信頼できるセッション内でメッセージを交換](../../../../docs/framework/wcf/feature-details/how-to-exchange-messages-within-a-reliable-session.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ccfe0-120">This procedure is described in [How to: Exchange Messages Within a Reliable Session](../../../../docs/framework/wcf/feature-details/how-to-exchange-messages-within-a-reliable-session.md).</span></span>

### <a name="set-the-mode-and-clientcredentialtype-in-configuration"></a><span data-ttu-id="ccfe0-121">構成にモードと ClientCredentialType を設定する</span><span class="sxs-lookup"><span data-stu-id="ccfe0-121">Set the mode and ClientCredentialType in configuration</span></span>

1. <span data-ttu-id="ccfe0-122">構成ファイルの[ **\<バインド >** ](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)要素に適切なバインド要素を追加します。</span><span class="sxs-lookup"><span data-stu-id="ccfe0-122">Add an appropriate binding element to the [**\<bindings>**](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) element of the configuration file.</span></span> <span data-ttu-id="ccfe0-123">次の例では、 [ **\<wsHttpBinding >** ](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)要素を追加します。</span><span class="sxs-lookup"><span data-stu-id="ccfe0-123">The following example adds a [**\<wsHttpBinding>**](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) element.</span></span>

1. <span data-ttu-id="ccfe0-124">**\<バインド >** 要素を追加し、その `name` 属性を適切な値に設定します。</span><span class="sxs-lookup"><span data-stu-id="ccfe0-124">Add a **\<binding>** element and set its `name` attribute to an appropriate value.</span></span> <span data-ttu-id="ccfe0-125">この例では、`MessageSecurity`という名前を使用します。</span><span class="sxs-lookup"><span data-stu-id="ccfe0-125">The example uses the name `MessageSecurity`.</span></span>

1. <span data-ttu-id="ccfe0-126">**\<セキュリティ >** 要素を追加し、`mode` 属性を `Message`に設定します。</span><span class="sxs-lookup"><span data-stu-id="ccfe0-126">Add a **\<security>** element and set the `mode` attribute to `Message`.</span></span>

1. <span data-ttu-id="ccfe0-127">**\<security >** 要素内に **\<message >** 要素を追加し、`clientCredentialType` 属性を `Certificate`に設定します。</span><span class="sxs-lookup"><span data-stu-id="ccfe0-127">Within the **\<security>** element, add a **\<message>** element and set the `clientCredentialType` attribute to `Certificate`.</span></span>

```xml
<wsHttpBinding>
  <binding name="MessageSecurity">
    <security mode="Message">
      <message clientCredentialType="Certificate" />
    </security>
  </binding>
</wsHttpBinding>
```
