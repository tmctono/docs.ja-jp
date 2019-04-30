---
title: '方法: 信頼できるセッション内でメッセージをセキュリティで保護する'
ms.date: 03/30/2017
ms.assetid: aee33e50-936f-4486-9ca8-c1520c19a62d
ms.openlocfilehash: ee35f2a36ca08814423b5a3d0b1432bacd28c2e5
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61973005"
---
# <a name="how-to-secure-messages-within-reliable-sessions"></a><span data-ttu-id="e9a4d-102">方法: 信頼できるセッション内でメッセージをセキュリティで保護する</span><span class="sxs-lookup"><span data-stu-id="e9a4d-102">How to: Secure Messages within Reliable Sessions</span></span>

<span data-ttu-id="e9a4d-103">ここでは、信頼できるセッション内で交換されるメッセージに対して、メッセージ レベルのセキュリティを有効にするために必要な手順について説明します。このとき、信頼できるセッションがオプションでサポートされているシステム指定のバインディングを使用します。</span><span class="sxs-lookup"><span data-stu-id="e9a4d-103">This topic outlines the steps required to enable message-level security for messages exchanged within a reliable session using one of the system-provided bindings that support such a session, but not by default.</span></span> <span data-ttu-id="e9a4d-104">コードを使用して強制的に行う、または構成ファイルで宣言によって、セキュリティで保護された、信頼できるセッションを有効にします。</span><span class="sxs-lookup"><span data-stu-id="e9a4d-104">Enable a secure, reliable session either imperatively by using code or declaratively in the configuration file.</span></span> <span data-ttu-id="e9a4d-105">この手順では、クライアントとサービスの構成ファイルを使用して、セキュリティで保護された信頼できるセッションを有効にします。</span><span class="sxs-lookup"><span data-stu-id="e9a4d-105">This procedure uses the client and service configuration files to enable the secure, reliable session.</span></span>

<span data-ttu-id="e9a4d-106">この手順の主な部分は、次の 3 つのタスクで構成されます。</span><span class="sxs-lookup"><span data-stu-id="e9a4d-106">This procedure consists of the following three key tasks:</span></span>

1. <span data-ttu-id="e9a4d-107">クライアントとサービスのメッセージ交換は信頼できるセッション内で行うことを指定します。</span><span class="sxs-lookup"><span data-stu-id="e9a4d-107">Specify that the client and service exchange messages within a reliable session.</span></span>

1. <span data-ttu-id="e9a4d-108">信頼できるセッション内でメッセージ レベルのセキュリティを要求します。</span><span class="sxs-lookup"><span data-stu-id="e9a4d-108">Require message-level security within the reliable session.</span></span>

1. <span data-ttu-id="e9a4d-109">サービスに対する認証時にクライアントが使用する必要があるクライアント資格情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="e9a4d-109">Specify the client credential type that the client must use to be authenticated with the service.</span></span>

<span data-ttu-id="e9a4d-110">エンドポイントの構成要素が含まれている最初のタスクで重要ですが、 `bindingConfiguration` (この例では) でという名前のバインド構成を参照する属性`MessageSecurity`。</span><span class="sxs-lookup"><span data-stu-id="e9a4d-110">It's important in the first task that the endpoint configuration element contain a `bindingConfiguration` attribute that references a binding configuration named (in this example) `MessageSecurity`.</span></span> <span data-ttu-id="e9a4d-111">[ **\<バインド >** ](../../../../docs/framework/misc/binding.md)構成要素を設定して、信頼できるセッションを有効にするには、この名前を参照し、`enabled`の属性、 [  **\<reliableSession >** ](https://docs.microsoft.com/previous-versions/ms731375(v=vs.90))要素`true`します。</span><span class="sxs-lookup"><span data-stu-id="e9a4d-111">The [**\<binding>**](../../../../docs/framework/misc/binding.md) configuration element then references this name to enable reliable sessions by setting the `enabled` attribute of the [**\<reliableSession>**](https://docs.microsoft.com/previous-versions/ms731375(v=vs.90)) element to `true`.</span></span> <span data-ttu-id="e9a4d-112">信頼できるセッション内で使用できる順序付き配信の保証は、`ordered` 属性を `true` に設定することによって要求できます。</span><span class="sxs-lookup"><span data-stu-id="e9a4d-112">You can require that the ordered delivery assurances are available within a reliable session by setting the `ordered` attribute to `true`.</span></span>

<span data-ttu-id="e9a4d-113">この構成手順は、基になる例のソースのコピーを次を参照してください。、 [WS 信頼できるセッション](../../../../docs/framework/wcf/samples/ws-reliable-session.md)します。</span><span class="sxs-lookup"><span data-stu-id="e9a4d-113">For the source copy of the example on which this configuration procedure is based, see the [WS Reliable Session](../../../../docs/framework/wcf/samples/ws-reliable-session.md).</span></span>

<span data-ttu-id="e9a4d-114">2 番目のタスクの必要な項目は、設定によって実現されます、`mode`の属性、 **\<セキュリティ >** 要素に含まれている、 **\<バインド >** 要素は、クライアントとサービスの`Message`します。</span><span class="sxs-lookup"><span data-stu-id="e9a4d-114">The essential items of the second task are accomplished by setting the `mode` attribute of the **\<security>** element contained in the **\<binding>** element of the client and service to `Message`.</span></span>

<span data-ttu-id="e9a4d-115">3 番目のタスクの必要な項目は、設定によって実現されます、`clientCredentialType`の属性、 **\<メッセージ >** 要素に含まれている、 **\<セキュリティ >** 要素は、クライアントとサービスの`Certificate`します。</span><span class="sxs-lookup"><span data-stu-id="e9a4d-115">The essential items of the third task are accomplished by setting the `clientCredentialType` attribute of the **\<message>** element contained in the **\<security>** element of the client and service to `Certificate`.</span></span>

> [!NOTE]
> <span data-ttu-id="e9a4d-116">メッセージ セキュリティを使用して、信頼できるセッションで、最初のエラーと例外をスローする代わりにタイムアウトが発生するまでに、認証されていないクライアントを認証すると信頼性の高いメッセージングされます。</span><span class="sxs-lookup"><span data-stu-id="e9a4d-116">When using message security with reliable sessions, Reliable Messaging attempts to authenticate an unauthenticated client until a timeout occurs instead of throwing an exception upon first failure.</span></span>

### <a name="configure-the-service-with-a-wshttpbinding-to-use-a-reliable-session"></a><span data-ttu-id="e9a4d-117">信頼できるセッションを使用する WSHttpBinding 使用サービスを構成します。</span><span class="sxs-lookup"><span data-stu-id="e9a4d-117">Configure the service with a WSHttpBinding to use a reliable session</span></span>

<span data-ttu-id="e9a4d-118">この手順で説明されて[方法。信頼できるセッション内でメッセージを交換](../../../../docs/framework/wcf/feature-details/how-to-exchange-messages-within-a-reliable-session.md)します。</span><span class="sxs-lookup"><span data-stu-id="e9a4d-118">This procedure is described in [How to: Exchange Messages Within a Reliable Session](../../../../docs/framework/wcf/feature-details/how-to-exchange-messages-within-a-reliable-session.md).</span></span>

### <a name="configure-the-client-with-a-wshttpbinding-to-use-a-reliable-session"></a><span data-ttu-id="e9a4d-119">信頼できるセッションを使用して、WSHttpBinding でクライアントを構成します。</span><span class="sxs-lookup"><span data-stu-id="e9a4d-119">Configure the client with a WSHttpBinding to use a reliable session</span></span>

<span data-ttu-id="e9a4d-120">この手順で説明されて[方法。信頼できるセッション内でメッセージを交換](../../../../docs/framework/wcf/feature-details/how-to-exchange-messages-within-a-reliable-session.md)します。</span><span class="sxs-lookup"><span data-stu-id="e9a4d-120">This procedure is described in [How to: Exchange Messages Within a Reliable Session](../../../../docs/framework/wcf/feature-details/how-to-exchange-messages-within-a-reliable-session.md).</span></span>

### <a name="set-the-mode-and-clientcredentialtype-in-configuration"></a><span data-ttu-id="e9a4d-121">構成でモードと ClientCredentialType を設定します。</span><span class="sxs-lookup"><span data-stu-id="e9a4d-121">Set the mode and ClientCredentialType in configuration</span></span>

1. <span data-ttu-id="e9a4d-122">適切なバインド要素を追加、 [ **\<バインド >** ](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)構成ファイルの要素。</span><span class="sxs-lookup"><span data-stu-id="e9a4d-122">Add an appropriate binding element to the [**\<bindings>**](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) element of the configuration file.</span></span> <span data-ttu-id="e9a4d-123">次の例では、追加、 [  **\<wsHttpBinding >** ](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)要素。</span><span class="sxs-lookup"><span data-stu-id="e9a4d-123">The following example adds a [**\<wsHttpBinding>**](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) element.</span></span>

1. <span data-ttu-id="e9a4d-124">追加、 **\<バインド >** 要素とその`name`属性に適切な値。</span><span class="sxs-lookup"><span data-stu-id="e9a4d-124">Add a **\<binding>** element and set its `name` attribute to an appropriate value.</span></span> <span data-ttu-id="e9a4d-125">例では、名前を使用して`MessageSecurity`します。</span><span class="sxs-lookup"><span data-stu-id="e9a4d-125">The example uses the name `MessageSecurity`.</span></span>

1. <span data-ttu-id="e9a4d-126">追加、 **\<セキュリティ >** 要素、`mode`属性を`Message`します。</span><span class="sxs-lookup"><span data-stu-id="e9a4d-126">Add a **\<security>** element and set the `mode` attribute to `Message`.</span></span>

1. <span data-ttu-id="e9a4d-127">内で、 **\<セキュリティ >** 要素を追加、 **\<メッセージ >** 要素、`clientCredentialType`属性を`Certificate`します。</span><span class="sxs-lookup"><span data-stu-id="e9a4d-127">Within the **\<security>** element, add a **\<message>** element and set the `clientCredentialType` attribute to `Certificate`.</span></span>

```xml
<wsHttpBinding>
  <binding name="MessageSecurity">
    <security mode="Message">
      <message clientCredentialType="Certificate" />
    </security>
  </binding>
</wsHttpBinding>
```
