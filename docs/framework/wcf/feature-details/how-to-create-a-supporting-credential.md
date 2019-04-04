---
title: '方法: サポート資格情報を作成します。'
ms.date: 03/30/2017
ms.assetid: d0952919-8bb4-4978-926c-9cc108f89806
ms.openlocfilehash: 1e56d595b389f2217f4c50db1242f418742a5d56
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54539806"
---
# <a name="how-to-create-a-supporting-credential"></a><span data-ttu-id="96317-102">方法: サポート資格情報を作成します。</span><span class="sxs-lookup"><span data-stu-id="96317-102">How to: Create a Supporting Credential</span></span>
<span data-ttu-id="96317-103">カスタムのセキュリティ スキームでは、複数の資格情報が必要になることがあります。</span><span class="sxs-lookup"><span data-stu-id="96317-103">It is possible to have a custom security scheme that requires more than one credential.</span></span> <span data-ttu-id="96317-104">たとえば、サービスが、ユーザー名とパスワードだけでなく、クライアントが 18 歳以上であることを証明する資格情報もクライアントに要求することがあります。</span><span class="sxs-lookup"><span data-stu-id="96317-104">For example, a service may demand from the client not just a user name and password, but also a credential that proves the client is over the age of 18.</span></span> <span data-ttu-id="96317-105">2 番目の資格情報が、*資格情報をサポートしている*します。</span><span class="sxs-lookup"><span data-stu-id="96317-105">The second credential is a *supporting credential*.</span></span> <span data-ttu-id="96317-106">このトピックでは、Windows Communication Foundation (WCF) クライアントでこのような資格情報を実装する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="96317-106">This topic explains how to implement such credentials in an Windows Communication Foundation (WCF) client.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="96317-107">サポート資格情報の仕様は、WS-SecurityPolicy 仕様の一部です。</span><span class="sxs-lookup"><span data-stu-id="96317-107">The specification for supporting credentials is part of the WS-SecurityPolicy specification.</span></span> <span data-ttu-id="96317-108">詳細については、[Web サービス セキュリティ仕様](https://go.microsoft.com/fwlink/?LinkId=88537)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="96317-108">For more information, see [Web Services Security Specifications](https://go.microsoft.com/fwlink/?LinkId=88537).</span></span>  
  
## <a name="supporting-tokens"></a><span data-ttu-id="96317-109">トークンのサポート</span><span class="sxs-lookup"><span data-stu-id="96317-109">Supporting Tokens</span></span>  
 <span data-ttu-id="96317-110">メッセージのセキュリティを使用する場合に簡単に言うと、*プライマリ資格情報*は常に (たとえば、X.509 証明書または Kerberos チケット) メッセージをセキュリティで保護するために使用します。</span><span class="sxs-lookup"><span data-stu-id="96317-110">In brief, when you use message security, a *primary credential* is always used to secure the message (for example, an X.509 certificate or a Kerberos ticket).</span></span>  
  
 <span data-ttu-id="96317-111">セキュリティ バインディングを使用して、仕様で定義された、*トークン*メッセージ交換をセキュリティで保護します。</span><span class="sxs-lookup"><span data-stu-id="96317-111">As defined by the specification, a security binding uses *tokens* to secure the message exchange.</span></span> <span data-ttu-id="96317-112">A*トークン*はセキュリティ資格情報を表したものです。</span><span class="sxs-lookup"><span data-stu-id="96317-112">A *token* is a representation of a security credential.</span></span>  
  
 <span data-ttu-id="96317-113">セキュリティ バインディングは、セキュリティ バインディング ポリシーで特定されたプライマリ トークンを使用して、署名を作成します。</span><span class="sxs-lookup"><span data-stu-id="96317-113">The security binding uses a primary token identified in the security binding policy to create a signature.</span></span> <span data-ttu-id="96317-114">この署名と呼ばれます、*メッセージ署名*します。</span><span class="sxs-lookup"><span data-stu-id="96317-114">This signature is referred to as the *message signature*.</span></span>  
  
 <span data-ttu-id="96317-115">メッセージ署名に関連付けられたトークンによって提供されるクレームを増やすために、追加のトークンを指定できます。</span><span class="sxs-lookup"><span data-stu-id="96317-115">Additional tokens can be specified to augment the claims provided by the token associated with the message signature.</span></span>  
  
## <a name="endorsing-signing-and-encrypting"></a><span data-ttu-id="96317-116">保証、署名、および暗号化</span><span class="sxs-lookup"><span data-stu-id="96317-116">Endorsing, Signing, and Encrypting</span></span>  
 <span data-ttu-id="96317-117">サポート資格情報の結果、*サポート トークン*メッセージ内で送信されます。</span><span class="sxs-lookup"><span data-stu-id="96317-117">A supporting credential results in a *supporting token* transmitted inside the message.</span></span> <span data-ttu-id="96317-118">WS-SecurityPolicy 仕様では、次の表に示すように、サポート トークンをメッセージに追加する方法が 4 つ定義されています。</span><span class="sxs-lookup"><span data-stu-id="96317-118">The WS-SecurityPolicy specification defines four ways to attach a supporting token to the message, as described in the following table.</span></span>  
  
|<span data-ttu-id="96317-119">目的</span><span class="sxs-lookup"><span data-stu-id="96317-119">Purpose</span></span>|<span data-ttu-id="96317-120">説明</span><span class="sxs-lookup"><span data-stu-id="96317-120">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="96317-121">符号付き</span><span class="sxs-lookup"><span data-stu-id="96317-121">Signed</span></span>|<span data-ttu-id="96317-122">サポート トークンはセキュリティ ヘッダーに追加され、メッセージ署名によって署名されます。</span><span class="sxs-lookup"><span data-stu-id="96317-122">The supporting token is included in the security header and is signed by the message signature.</span></span>|  
|<span data-ttu-id="96317-123">保証</span><span class="sxs-lookup"><span data-stu-id="96317-123">Endorsing</span></span>|<span data-ttu-id="96317-124">*保証トークン*メッセージ署名します。</span><span class="sxs-lookup"><span data-stu-id="96317-124">An *endorsing token* signs the message signature.</span></span>|  
|<span data-ttu-id="96317-125">署名および保証</span><span class="sxs-lookup"><span data-stu-id="96317-125">Signed and Endorsing</span></span>|<span data-ttu-id="96317-126">署名付き保証トークンは、メッセージ署名から生成された `ds:Signature` 要素全体を署名し、それ自体がこのメッセージ署名によって署名されます。つまり、両方のトークン (メッセージ署名に使用されるトークンと署名付き保証トークン) がお互いに署名します。</span><span class="sxs-lookup"><span data-stu-id="96317-126">Signed, endorsing tokens sign the entire `ds:Signature` element produced from the message signature and are themselves signed by that message signature; that is, both tokens (the token used for the message signature and the signed endorsing token) sign each other.</span></span>|  
|<span data-ttu-id="96317-127">署名および暗号化</span><span class="sxs-lookup"><span data-stu-id="96317-127">Signed and Encrypting</span></span>|<span data-ttu-id="96317-128">暗号化された署名付きサポート トークンは、`wsse:SecurityHeader` に表示されたときに暗号化されている署名付きサポート トークンです。</span><span class="sxs-lookup"><span data-stu-id="96317-128">Signed, encrypted supporting tokens are signed supporting tokens that are also encrypted when they appear in the `wsse:SecurityHeader`.</span></span>|  
  
## <a name="programming-supporting-credentials"></a><span data-ttu-id="96317-129">サポート資格情報のプログラミング</span><span class="sxs-lookup"><span data-stu-id="96317-129">Programming Supporting Credentials</span></span>  
 <span data-ttu-id="96317-130">サポート トークンを作成する必要がありますを使用するサービスを作成する、 [ \<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)します。</span><span class="sxs-lookup"><span data-stu-id="96317-130">To create a service that uses supporting tokens you must create a [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md).</span></span> <span data-ttu-id="96317-131">(詳細については、次を参照してください。[方法。SecurityBindingElement を使用してカスタム バインディングを作成する](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md))。</span><span class="sxs-lookup"><span data-stu-id="96317-131">(For more information, see [How to: Create a Custom Binding Using the SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md).)</span></span>  
  
 <span data-ttu-id="96317-132">カスタム バインドを作成する最初の手順は、次の 3 種類のいずれかのセキュリティ バインド要素を作成することです。</span><span class="sxs-lookup"><span data-stu-id="96317-132">The first step when creating a custom binding is to create a security binding element, which can be one of three types:</span></span>  
  
-   <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>  
  
-   <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>  
  
-   <xref:System.ServiceModel.Channels.TransportSecurityBindingElement>  
  
 <span data-ttu-id="96317-133">すべてのクラスは、次の 4 つの関連プロパティを備えた <xref:System.ServiceModel.Channels.SecurityBindingElement> から継承します。</span><span class="sxs-lookup"><span data-stu-id="96317-133">All classes inherit from the <xref:System.ServiceModel.Channels.SecurityBindingElement>, which includes four relevant properties:</span></span>  
  
-   <xref:System.ServiceModel.Channels.SecurityBindingElement.EndpointSupportingTokenParameters%2A>  
  
-   <xref:System.ServiceModel.Channels.SecurityBindingElement.OperationSupportingTokenParameters%2A>  
  
-   <xref:System.ServiceModel.Channels.SecurityBindingElement.OptionalEndpointSupportingTokenParameters%2A>  
  
-   <xref:System.ServiceModel.Channels.SecurityBindingElement.OptionalOperationSupportingTokenParameters%2A>  
  
#### <a name="scopes"></a><span data-ttu-id="96317-134">スコープ</span><span class="sxs-lookup"><span data-stu-id="96317-134">Scopes</span></span>  
 <span data-ttu-id="96317-135">サポート資格情報には、次の 2 つのスコープがあります。</span><span class="sxs-lookup"><span data-stu-id="96317-135">Two scopes exist for supporting credentials:</span></span>  
  
-   <span data-ttu-id="96317-136">*エンドポイント サポート トークン*エンドポイントのすべての操作をサポートします。</span><span class="sxs-lookup"><span data-stu-id="96317-136">*Endpoint supporting tokens* support all operations of an endpoint.</span></span> <span data-ttu-id="96317-137">つまり、サポート トークンによって表される資格情報は、エンドポイントの任意の操作が呼び出されたときにいつでも使用できます。</span><span class="sxs-lookup"><span data-stu-id="96317-137">That is, the credential that the supporting token represents can be used whenever any endpoint operations are invoked.</span></span>  
  
-   <span data-ttu-id="96317-138">*操作サポート トークン*特定のエンドポイントの操作のみをサポートします。</span><span class="sxs-lookup"><span data-stu-id="96317-138">*Operation supporting tokens* support only a specific endpoint operation.</span></span>  
  
 <span data-ttu-id="96317-139">プロパティ名に示されているように、サポート資格情報は必須またはオプションのどちらかになることができます。</span><span class="sxs-lookup"><span data-stu-id="96317-139">As indicated by the property names, supporting credentials can be either required or optional.</span></span> <span data-ttu-id="96317-140">つまり、サポート資格情報は必須ではありませんが、存在する場合は使用され、存在しない場合も認証は失敗しません。</span><span class="sxs-lookup"><span data-stu-id="96317-140">That is, if the supporting credential is used if it is present, although it is not necessary, but the authentication will not fail if it is not present.</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="96317-141">手順</span><span class="sxs-lookup"><span data-stu-id="96317-141">Procedures</span></span>  
  
#### <a name="to-create-a-custom-binding-that-includes-supporting-credentials"></a><span data-ttu-id="96317-142">サポート資格情報を備えたカスタム バインディングを作成するには</span><span class="sxs-lookup"><span data-stu-id="96317-142">To create a custom binding that includes supporting credentials</span></span>  
  
1.  <span data-ttu-id="96317-143">セキュリティ バインド要素を作成します。</span><span class="sxs-lookup"><span data-stu-id="96317-143">Create a security binding element.</span></span> <span data-ttu-id="96317-144">次の例では、<xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> 認証モードで `UserNameForCertificate` を作成します。</span><span class="sxs-lookup"><span data-stu-id="96317-144">The example below creates a <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> with the `UserNameForCertificate` authentication mode.</span></span> <span data-ttu-id="96317-145"><xref:System.ServiceModel.Channels.SecurityBindingElement.CreateUserNameForCertificateBindingElement%2A> メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="96317-145">Use the <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateUserNameForCertificateBindingElement%2A> method.</span></span>  
  
2.  <span data-ttu-id="96317-146">サポート パラメーターを対応するプロパティ (`Endorsing`、`Signed`、`SignedEncrypted`、または `SignedEndorsed`) によって返される型のコレクションに追加します。</span><span class="sxs-lookup"><span data-stu-id="96317-146">Add the supporting parameter to the collection of types returned by the appropriate property (`Endorsing`, `Signed`, `SignedEncrypted`, or `SignedEndorsed`).</span></span> <span data-ttu-id="96317-147"><xref:System.ServiceModel.Security.Tokens> 名前空間に存在する型には、<xref:System.ServiceModel.Security.Tokens.X509SecurityTokenParameters> など、一般的に使用される型があります。</span><span class="sxs-lookup"><span data-stu-id="96317-147">The types in the <xref:System.ServiceModel.Security.Tokens> namespace include commonly used types, such as the <xref:System.ServiceModel.Security.Tokens.X509SecurityTokenParameters>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="96317-148">例</span><span class="sxs-lookup"><span data-stu-id="96317-148">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="96317-149">説明</span><span class="sxs-lookup"><span data-stu-id="96317-149">Description</span></span>  
 <span data-ttu-id="96317-150"><xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> のインスタンスを作成し、<xref:System.ServiceModel.Security.Tokens.KerberosSecurityTokenParameters> クラスのインスタンスを、Endorsing プロパティによって返されるコレクションに追加する例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="96317-150">The following example creates an instance of the <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> and adds an instance of the <xref:System.ServiceModel.Security.Tokens.KerberosSecurityTokenParameters> class to the collection the Endorsing property returned.</span></span>  
  
### <a name="code"></a><span data-ttu-id="96317-151">コード</span><span class="sxs-lookup"><span data-stu-id="96317-151">Code</span></span>  
 [!code-csharp[c_SupportingCredential#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_supportingcredential/cs/source.cs#1)]  
  
## <a name="see-also"></a><span data-ttu-id="96317-152">関連項目</span><span class="sxs-lookup"><span data-stu-id="96317-152">See also</span></span>
- [<span data-ttu-id="96317-153">方法: SecurityBindingElement を使用してカスタム バインディングを作成します。</span><span class="sxs-lookup"><span data-stu-id="96317-153">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)
