---
title: '方法: 時刻のずれの最大値を設定する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- MaxClockSkew property
- WCF, custom bindings
ms.assetid: 491d1705-eb29-43c2-a44c-c0cf996f74eb
ms.openlocfilehash: 3bcd128e6e9f53f662dd3fc99336b5b45faebf5f
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69943115"
---
# <a name="how-to-set-a-max-clock-skew"></a><span data-ttu-id="0dc9c-102">方法: 時刻のずれの最大値を設定する</span><span class="sxs-lookup"><span data-stu-id="0dc9c-102">How to: Set a Max Clock Skew</span></span>
<span data-ttu-id="0dc9c-103">時刻が重要な要素となる機能は、2 台のコンピューターで時刻の設定が異なっていると失敗する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0dc9c-103">Time-critical functions can be derailed if the clock settings on two computers are different.</span></span> <span data-ttu-id="0dc9c-104">この可能性を減らすには、`MaxClockSkew` プロパティを <xref:System.TimeSpan> に設定します。</span><span class="sxs-lookup"><span data-stu-id="0dc9c-104">To mitigate this possibility, you can set the `MaxClockSkew` property to a <xref:System.TimeSpan>.</span></span> <span data-ttu-id="0dc9c-105">このプロパティは、次の 2 つのクラスで使用できます。</span><span class="sxs-lookup"><span data-stu-id="0dc9c-105">This property is available on two classes:</span></span>  
  
 <xref:System.ServiceModel.Channels.LocalClientSecuritySettings>  
  
 <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings>  
  
> [!IMPORTANT]
> <span data-ttu-id="0dc9c-106">セキュリティで保護された通信を`MaxClockSkew`行うには、サービスまたはクライアントをブートストラップするときに、プロパティに対する変更を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="0dc9c-106">For a secure conversation, changes to the `MaxClockSkew` property  must be made when the service or client is bootstrapped.</span></span> <span data-ttu-id="0dc9c-107">これを行うには、 <xref:System.ServiceModel.Channels.SecurityBindingElement> <xref:System.ServiceModel.Security.Tokens.SecureConversationSecurityTokenParameters.BootstrapSecurityBindingElement%2A?displayProperty=nameWithType>プロパティによって返されるのプロパティを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0dc9c-107">To do this, you must set the property on the <xref:System.ServiceModel.Channels.SecurityBindingElement> returned by the <xref:System.ServiceModel.Security.Tokens.SecureConversationSecurityTokenParameters.BootstrapSecurityBindingElement%2A?displayProperty=nameWithType> property.</span></span>  
  
 <span data-ttu-id="0dc9c-108">システム提供のバインディングの 1 つでこのプロパティを変更するには、バインディングのコレクションでセキュリティ バインド要素を見つけて、`MaxClockSkew` プロパティを新しい値に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0dc9c-108">To change the property on one of the system-provided bindings, you must find the security binding element in the collection of bindings and set the `MaxClockSkew` property to a new value.</span></span> <span data-ttu-id="0dc9c-109"><xref:System.ServiceModel.Channels.SecurityBindingElement> から派生される 2 つのクラスは、<xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> クラスおよび <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement> クラスです。</span><span class="sxs-lookup"><span data-stu-id="0dc9c-109">Two classes derive from the <xref:System.ServiceModel.Channels.SecurityBindingElement>: <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> and <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>.</span></span> <span data-ttu-id="0dc9c-110">コレクションからセキュリティ バインディングを取得する場合は、`MaxClockSkew` プロパティを正しく設定するために、これらの型のどちらかにキャストする必要があります。</span><span class="sxs-lookup"><span data-stu-id="0dc9c-110">When retrieving the security binding from the collection, you must cast to one of these types in order to correctly set the `MaxClockSkew` property.</span></span> <span data-ttu-id="0dc9c-111">次の例では、<xref:System.ServiceModel.WSHttpBinding> を使用していますが、これは <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> を使用します。</span><span class="sxs-lookup"><span data-stu-id="0dc9c-111">The following example uses a <xref:System.ServiceModel.WSHttpBinding>, which uses the <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>.</span></span> <span data-ttu-id="0dc9c-112">システム指定の各バインディングで使用するセキュリティバインディングの種類を指定する一覧については、「[システム指定](../../../../docs/framework/wcf/system-provided-bindings.md)のバインディング」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0dc9c-112">For a list that specifies which type of security binding to use in each system-provided binding, see [System-Provided Bindings](../../../../docs/framework/wcf/system-provided-bindings.md).</span></span>  
  
## <a name="to-create-a-custom-binding-with-a-new-clock-skew-value-in-code"></a><span data-ttu-id="0dc9c-113">コードを使用して時刻のずれの新しい値を持つカスタム バインドを作成するには</span><span class="sxs-lookup"><span data-stu-id="0dc9c-113">To create a custom binding with a new clock skew value in code</span></span>  
  
> [!WARNING]
> <span data-ttu-id="0dc9c-114">コード内の次の名前空間への参照<xref:System.ServiceModel.Channels>を追加<xref:System.Security.Permissions>します<xref:System.ServiceModel.Security.Tokens>。、 <xref:System.ServiceModel.Description>、、および。</span><span class="sxs-lookup"><span data-stu-id="0dc9c-114">Add references to the following namespaces in your code: <xref:System.ServiceModel.Channels>, <xref:System.ServiceModel.Description>, <xref:System.Security.Permissions>, and <xref:System.ServiceModel.Security.Tokens>.</span></span>  
  
1. <span data-ttu-id="0dc9c-115"><xref:System.ServiceModel.WSHttpBinding> クラスのインスタンスを作成し、セキュリティ モードを <xref:System.ServiceModel.SecurityMode.Message?displayProperty=nameWithType> に設定します。</span><span class="sxs-lookup"><span data-stu-id="0dc9c-115">Create an instance of a <xref:System.ServiceModel.WSHttpBinding> class and set its security mode to <xref:System.ServiceModel.SecurityMode.Message?displayProperty=nameWithType>.</span></span>  
  
2. <span data-ttu-id="0dc9c-116"><xref:System.ServiceModel.Channels.BindingElementCollection> メソッドを呼び出して、<xref:System.ServiceModel.WSHttpBinding.CreateBindingElements%2A> クラスの新しいインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="0dc9c-116">Create a new instance of the <xref:System.ServiceModel.Channels.BindingElementCollection> class by calling the <xref:System.ServiceModel.WSHttpBinding.CreateBindingElements%2A> method.</span></span>  
  
3. <span data-ttu-id="0dc9c-117"><xref:System.ServiceModel.Channels.BindingElementCollection.Find%2A> クラスの <xref:System.ServiceModel.Channels.BindingElementCollection> メソッドを使用して、セキュリティ バインド要素を検索します。</span><span class="sxs-lookup"><span data-stu-id="0dc9c-117">Use the <xref:System.ServiceModel.Channels.BindingElementCollection.Find%2A> method of the <xref:System.ServiceModel.Channels.BindingElementCollection> class to find the security binding element.</span></span>  
  
4. <span data-ttu-id="0dc9c-118"><xref:System.ServiceModel.Channels.BindingElementCollection.Find%2A> メソッドを使用する場合には、実際の型にキャストします。</span><span class="sxs-lookup"><span data-stu-id="0dc9c-118">When using the <xref:System.ServiceModel.Channels.BindingElementCollection.Find%2A> method, cast to the actual type.</span></span> <span data-ttu-id="0dc9c-119">次の例では <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> 型にキャストしています。</span><span class="sxs-lookup"><span data-stu-id="0dc9c-119">The example below casts to the <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> type.</span></span>  
  
5. <span data-ttu-id="0dc9c-120">セキュリティ バインド要素の <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings.MaxClockSkew%2A> プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="0dc9c-120">Set the <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings.MaxClockSkew%2A> property on the security binding element.</span></span>  
  
6. <span data-ttu-id="0dc9c-121">適切なサービス型とベース アドレスを使用して、<xref:System.ServiceModel.ServiceHost> を作成します。</span><span class="sxs-lookup"><span data-stu-id="0dc9c-121">Create a <xref:System.ServiceModel.ServiceHost> with an appropriate service type and base address.</span></span>  
  
7. <span data-ttu-id="0dc9c-122"><xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A> メソッドを使用してエンドポイントを追加し、<xref:System.ServiceModel.Channels.CustomBinding> を含めます。</span><span class="sxs-lookup"><span data-stu-id="0dc9c-122">Use the <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A> method to add an endpoint and include the <xref:System.ServiceModel.Channels.CustomBinding>.</span></span>  
  
     [!code-csharp[c_MaxClockSkew#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_maxclockskew/cs/source.cs#1)]
     [!code-vb[c_MaxClockSkew#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_maxclockskew/vb/source.vb#1)]  
  
## <a name="to-set-the-maxclockskew-in-configuration"></a><span data-ttu-id="0dc9c-123">構成で MaxClockSkew を設定するには</span><span class="sxs-lookup"><span data-stu-id="0dc9c-123">To set the MaxClockSkew in configuration</span></span>  
  
1. <span data-ttu-id="0dc9c-124">Bindings > 要素セクションに[> customBinding \<](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)を作成します。 [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)</span><span class="sxs-lookup"><span data-stu-id="0dc9c-124">Create a [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) in the [\<bindings>](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) element section.</span></span>  
  
2. <span data-ttu-id="0dc9c-125">バインド > 要素を作成し、属性を適切な値に設定します。`name` [ \<](../../../../docs/framework/misc/binding.md)</span><span class="sxs-lookup"><span data-stu-id="0dc9c-125">Create a [\<binding>](../../../../docs/framework/misc/binding.md) element and set the `name` attribute to an appropriate value.</span></span> <span data-ttu-id="0dc9c-126">`MaxClockSkewBinding` に設定する方法の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="0dc9c-126">The following example sets it to `MaxClockSkewBinding`.</span></span>  
  
3. <span data-ttu-id="0dc9c-127">エンコーディング要素を追加します。</span><span class="sxs-lookup"><span data-stu-id="0dc9c-127">Add an encoding element.</span></span> <span data-ttu-id="0dc9c-128">次の例では、 [ \<textmessageencoding >](../../../../docs/framework/configure-apps/file-schema/wcf/textmessageencoding.md)を追加します。</span><span class="sxs-lookup"><span data-stu-id="0dc9c-128">The example below adds a [\<textMessageEncoding>](../../../../docs/framework/configure-apps/file-schema/wcf/textmessageencoding.md).</span></span>  
  
4. <span data-ttu-id="0dc9c-129">セキュリティ > 要素を追加し、属性を適切な設定に設定します。`authenticationMode` [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="0dc9c-129">Add a [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element and set the `authenticationMode` attribute to an appropriate setting.</span></span> <span data-ttu-id="0dc9c-130">次の例では、この属性を `Kerberos` に設定して、サービスが Windows 認証を使用するように指定しています。</span><span class="sxs-lookup"><span data-stu-id="0dc9c-130">The following example set the attribute to `Kerberos` to specify that the service use Windows authentication.</span></span>  
  
5. <span data-ttu-id="0dc9c-131">`maxClockSkew` `"##:##:##"` [ Localservicesettings>を追加し、属性を\<](../../../../docs/framework/configure-apps/file-schema/wcf/localservicesettings-element.md)の形式の値に設定します。</span><span class="sxs-lookup"><span data-stu-id="0dc9c-131">Add a [\<localServiceSettings>](../../../../docs/framework/configure-apps/file-schema/wcf/localservicesettings-element.md) and set the `maxClockSkew` attribute to a value in the form of `"##:##:##"`.</span></span> <span data-ttu-id="0dc9c-132">次の例では 7 分に設定しています。</span><span class="sxs-lookup"><span data-stu-id="0dc9c-132">The following example sets it to 7 minutes.</span></span> <span data-ttu-id="0dc9c-133">必要に応じて、 [ \<localservicesettings >](../../../../docs/framework/configure-apps/file-schema/wcf/localservicesettings-element.md)を追加`maxClockSkew`し、属性を適切な設定に設定します。</span><span class="sxs-lookup"><span data-stu-id="0dc9c-133">Optionally, add a [\<localServiceSettings>](../../../../docs/framework/configure-apps/file-schema/wcf/localservicesettings-element.md) and set the `maxClockSkew` attribute to an appropriate setting.</span></span>  
  
6. <span data-ttu-id="0dc9c-134">transport 要素を追加します。</span><span class="sxs-lookup"><span data-stu-id="0dc9c-134">Add a transport element.</span></span> <span data-ttu-id="0dc9c-135">次の例では、 [ \<httptransport >](../../../../docs/framework/configure-apps/file-schema/wcf/httptransport.md)を使用します。</span><span class="sxs-lookup"><span data-stu-id="0dc9c-135">The following example uses an [\<httpTransport>](../../../../docs/framework/configure-apps/file-schema/wcf/httptransport.md).</span></span>  
  
7. <span data-ttu-id="0dc9c-136">セキュリティで保護された通信を行うには、 [ \<secureConversationBootstrap >](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md)要素のブートストラップでセキュリティ設定を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="0dc9c-136">For a secure conversation, the security settings must occur at the bootstrap in the [\<secureConversationBootstrap>](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) element.</span></span>  
  
    ```xml  
    <bindings>  
      <customBinding>  
        <binding name="MaxClockSkewBinding">  
            <textMessageEncoding />  
            <security authenticationMode="Kerberos">  
               <localClientSettings maxClockSkew="00:07:00" />  
               <localServiceSettings maxClockSkew="00:07:00" />  
               <secureConversationBootstrap>  
                  <localClientSettings maxClockSkew="00:30:00" />  
                  <localServiceSettings maxClockSkew="00:30:00" />  
               </secureConversationBootstrap>  
            </security>  
            <httpTransport />  
        </binding>  
      </customBinding>  
    </bindings>  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="0dc9c-137">関連項目</span><span class="sxs-lookup"><span data-stu-id="0dc9c-137">See also</span></span>

- <xref:System.ServiceModel.Channels.LocalClientSecuritySettings>
- <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="0dc9c-138">方法: 設定を使用してカスタムバインディングを作成する</span><span class="sxs-lookup"><span data-stu-id="0dc9c-138">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)
