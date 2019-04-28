---
title: '方法: セキュリティ コンテキストを調べる'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ServiceSecurityContext class
- WCF, security
- Claimset class
ms.assetid: 389b5a57-4175-4bc0-ada0-fc750d51149f
ms.openlocfilehash: c6c36641463a45b79d437ae3910bbe7474d425cb
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61929299"
---
# <a name="how-to-examine-the-security-context"></a><span data-ttu-id="d13fe-102">方法: セキュリティ コンテキストを調べる</span><span class="sxs-lookup"><span data-stu-id="d13fe-102">How to: Examine the Security Context</span></span>
<span data-ttu-id="d13fe-103">Windows Communication Foundation (WCF) サービスをプログラミングする場合、サービス セキュリティ コンテキストでは、クライアント資格情報と、サービスで認証するために使用するクレームの詳細を確認することができます。</span><span class="sxs-lookup"><span data-stu-id="d13fe-103">When programming Windows Communication Foundation (WCF) services, the service security context enables you to determine details about the client credentials and claims used to authenticate with the service.</span></span> <span data-ttu-id="d13fe-104">これは、<xref:System.ServiceModel.ServiceSecurityContext> クラスのプロパティを使用することで可能になります。</span><span class="sxs-lookup"><span data-stu-id="d13fe-104">This is done by using the properties of the <xref:System.ServiceModel.ServiceSecurityContext> class.</span></span>  
  
 <span data-ttu-id="d13fe-105">たとえば、<xref:System.ServiceModel.ServiceSecurityContext.PrimaryIdentity%2A> プロパティまたは <xref:System.ServiceModel.ServiceSecurityContext.WindowsIdentity%2A> プロパティを使用すると、現在のクライアントの ID を取得できます。</span><span class="sxs-lookup"><span data-stu-id="d13fe-105">For example, you can retrieve the identity of the current client by using the <xref:System.ServiceModel.ServiceSecurityContext.PrimaryIdentity%2A> or the <xref:System.ServiceModel.ServiceSecurityContext.WindowsIdentity%2A> property.</span></span> <span data-ttu-id="d13fe-106">クライアントが匿名であるかどうかを確認するには、<xref:System.ServiceModel.ServiceSecurityContext.IsAnonymous%2A> プロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="d13fe-106">To determine whether the client is anonymous, use the <xref:System.ServiceModel.ServiceSecurityContext.IsAnonymous%2A> property.</span></span>  
  
 <span data-ttu-id="d13fe-107">また、<xref:System.ServiceModel.ServiceSecurityContext.AuthorizationContext%2A> プロパティにあるクレームのコレクションを反復処理することによって、クライアントのためにどのようなクレームが作成されているのかを確認することもできます。</span><span class="sxs-lookup"><span data-stu-id="d13fe-107">You can also determine what claims are being made on behalf of the client by iterating through the collection of claims in the <xref:System.ServiceModel.ServiceSecurityContext.AuthorizationContext%2A> property.</span></span>  
  
### <a name="to-get-the-current-security-context"></a><span data-ttu-id="d13fe-108">現在のセキュリティ コンテキストを取得するには</span><span class="sxs-lookup"><span data-stu-id="d13fe-108">To get the current security context</span></span>  
  
- <span data-ttu-id="d13fe-109">現在のセキュリティ コンテキストを取得するためには、静的プロパティ <xref:System.ServiceModel.ServiceSecurityContext.Current%2A> にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="d13fe-109">Access the static property <xref:System.ServiceModel.ServiceSecurityContext.Current%2A> to get the current security context.</span></span> <span data-ttu-id="d13fe-110">参照から現在のコンテキストの任意のプロパティを調べます。</span><span class="sxs-lookup"><span data-stu-id="d13fe-110">Examine any of the properties of the current context from the reference.</span></span>  
  
### <a name="to-determine-the-identity-of-the-caller"></a><span data-ttu-id="d13fe-111">呼び出し元の ID を確認するには</span><span class="sxs-lookup"><span data-stu-id="d13fe-111">To determine the identity of the caller</span></span>  
  
1. <span data-ttu-id="d13fe-112"><xref:System.ServiceModel.ServiceSecurityContext.PrimaryIdentity%2A> プロパティおよび <xref:System.ServiceModel.ServiceSecurityContext.WindowsIdentity%2A> プロパティの値を表示します。</span><span class="sxs-lookup"><span data-stu-id="d13fe-112">Print the value of the <xref:System.ServiceModel.ServiceSecurityContext.PrimaryIdentity%2A> and <xref:System.ServiceModel.ServiceSecurityContext.WindowsIdentity%2A> properties.</span></span>  
  
### <a name="to-parse-the-claims-of-a-caller"></a><span data-ttu-id="d13fe-113">呼び出し元のクレームを解析するには</span><span class="sxs-lookup"><span data-stu-id="d13fe-113">To parse the claims of a caller</span></span>  
  
1. <span data-ttu-id="d13fe-114">現在の <xref:System.IdentityModel.Policy.AuthorizationContext> クラスを返します。</span><span class="sxs-lookup"><span data-stu-id="d13fe-114">Return the current <xref:System.IdentityModel.Policy.AuthorizationContext> class.</span></span> <span data-ttu-id="d13fe-115"><xref:System.ServiceModel.ServiceSecurityContext.Current%2A> プロパティを使用して、現在のサービス セキュリティ コンテキストを返し、次に `AuthorizationContext` プロパティを使用して <xref:System.ServiceModel.ServiceSecurityContext.AuthorizationContext%2A> を返します。</span><span class="sxs-lookup"><span data-stu-id="d13fe-115">Use the <xref:System.ServiceModel.ServiceSecurityContext.Current%2A> property to return the current service security context, then return the `AuthorizationContext` using the <xref:System.ServiceModel.ServiceSecurityContext.AuthorizationContext%2A> property.</span></span>  
  
2. <span data-ttu-id="d13fe-116"><xref:System.IdentityModel.Claims.ClaimSet> クラスの <xref:System.IdentityModel.Policy.AuthorizationContext.ClaimSets%2A> プロパティによって返された <xref:System.IdentityModel.Policy.AuthorizationContext> オブジェクトのコレクションを解析します。</span><span class="sxs-lookup"><span data-stu-id="d13fe-116">Parse the collection of <xref:System.IdentityModel.Claims.ClaimSet> objects returned by the <xref:System.IdentityModel.Policy.AuthorizationContext.ClaimSets%2A> property of the <xref:System.IdentityModel.Policy.AuthorizationContext> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d13fe-117">例</span><span class="sxs-lookup"><span data-stu-id="d13fe-117">Example</span></span>  
 <span data-ttu-id="d13fe-118">次の例では、現在のセキュリティ コンテキストの <xref:System.ServiceModel.ServiceSecurityContext.WindowsIdentity%2A> プロパティおよび <xref:System.ServiceModel.ServiceSecurityContext.PrimaryIdentity%2A> プロパティの値、<xref:System.IdentityModel.Claims.Claim.ClaimType%2A> プロパティの値、クレームのリソース値、および現在のセキュリティ コンテキストのすべてのクレームの <xref:System.IdentityModel.Claims.Claim.Right%2A> プロパティを表示します。</span><span class="sxs-lookup"><span data-stu-id="d13fe-118">The following example prints the values of the <xref:System.ServiceModel.ServiceSecurityContext.WindowsIdentity%2A> and <xref:System.ServiceModel.ServiceSecurityContext.PrimaryIdentity%2A> properties of the current security context and the <xref:System.IdentityModel.Claims.Claim.ClaimType%2A> property, the resource value of the claim, and the <xref:System.IdentityModel.Claims.Claim.Right%2A> property of every claim in the current security context.</span></span>  
  
 [!code-csharp[c_PrincipalPermissionAttribute#4](../../../samples/snippets/csharp/VS_Snippets_CFX/c_principalpermissionattribute/cs/source.cs#4)]
 [!code-vb[c_PrincipalPermissionAttribute#4](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_principalpermissionattribute/vb/source.vb#4)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="d13fe-119">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="d13fe-119">Compiling the Code</span></span>  
 <span data-ttu-id="d13fe-120">コードでは、次の名前空間を使用します。</span><span class="sxs-lookup"><span data-stu-id="d13fe-120">The code uses the following namespaces:</span></span>  
  
- <xref:System>  
  
- <xref:System.ServiceModel>  
  
- <xref:System.IdentityModel.Policy>  
  
- <xref:System.IdentityModel.Claims>  
  
## <a name="see-also"></a><span data-ttu-id="d13fe-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="d13fe-121">See also</span></span>

- [<span data-ttu-id="d13fe-122">サービスのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="d13fe-122">Securing Services</span></span>](../../../docs/framework/wcf/securing-services.md)
- [<span data-ttu-id="d13fe-123">サービス ID と認証</span><span class="sxs-lookup"><span data-stu-id="d13fe-123">Service Identity and Authentication</span></span>](../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
