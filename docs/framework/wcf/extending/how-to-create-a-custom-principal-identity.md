---
title: '方法: カスタム プリンシパル ID を作成する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- IPrincipal
- IAuthorizationPolicy
- PrincipalPermissionMode
- PrincipalPermissionAttribute
ms.assetid: c4845fca-0ed9-4adf-bbdc-10812be69b61
ms.openlocfilehash: 9b8b18f6c66fdb8f2446d3ddc5c584c5bad44ef3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61767274"
---
# <a name="how-to-create-a-custom-principal-identity"></a><span data-ttu-id="cda02-102">方法: カスタム プリンシパル ID を作成する</span><span class="sxs-lookup"><span data-stu-id="cda02-102">How to: Create a Custom Principal Identity</span></span>
<span data-ttu-id="cda02-103"><xref:System.Security.Permissions.PrincipalPermissionAttribute> は、サービス メソッドへのアクセスを宣言によって制御する手段として使用できます。</span><span class="sxs-lookup"><span data-stu-id="cda02-103">The <xref:System.Security.Permissions.PrincipalPermissionAttribute> is a declarative means of controlling access to service methods.</span></span> <span data-ttu-id="cda02-104">この属性を使用する場合、承認チェックを実行するためのモードが <xref:System.ServiceModel.Description.PrincipalPermissionMode> 列挙体で指定されます。</span><span class="sxs-lookup"><span data-stu-id="cda02-104">When using this attribute, the <xref:System.ServiceModel.Description.PrincipalPermissionMode> enumeration specifies the mode for performing authorization checks.</span></span> <span data-ttu-id="cda02-105">このモードが <xref:System.ServiceModel.Description.PrincipalPermissionMode.Custom> に設定されている場合、ユーザーは、<xref:System.Security.Principal.IPrincipal> プロパティから返されるカスタムの <xref:System.Threading.Thread.CurrentPrincipal%2A> クラスを指定できます。</span><span class="sxs-lookup"><span data-stu-id="cda02-105">When this mode is set to <xref:System.ServiceModel.Description.PrincipalPermissionMode.Custom>, it enables the user to specify a custom <xref:System.Security.Principal.IPrincipal> class returned by the <xref:System.Threading.Thread.CurrentPrincipal%2A> property.</span></span> <span data-ttu-id="cda02-106">ここでは、<xref:System.ServiceModel.Description.PrincipalPermissionMode.Custom> を、カスタム承認ポリシーおよびカスタム プリンシパルと組み合わせて使用する場合のシナリオを説明します。</span><span class="sxs-lookup"><span data-stu-id="cda02-106">This topic illustrates the scenario when <xref:System.ServiceModel.Description.PrincipalPermissionMode.Custom> is used in combination with a custom authorization policy and a custom principal.</span></span>  
  
 <span data-ttu-id="cda02-107">使用しての詳細については、<xref:System.Security.Permissions.PrincipalPermissionAttribute>を参照してください[方法。PrincipalPermissionAttribute クラスでアクセスを制限する](../../../../docs/framework/wcf/how-to-restrict-access-with-the-principalpermissionattribute-class.md)します。</span><span class="sxs-lookup"><span data-stu-id="cda02-107">For more information about using the <xref:System.Security.Permissions.PrincipalPermissionAttribute>, see [How to: Restrict Access with the PrincipalPermissionAttribute Class](../../../../docs/framework/wcf/how-to-restrict-access-with-the-principalpermissionattribute-class.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="cda02-108">例</span><span class="sxs-lookup"><span data-stu-id="cda02-108">Example</span></span>  
 [!code-csharp[PrincipalPermissionMode#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/principalpermissionmode/cs/source.cs#8)]
 [!code-vb[PrincipalPermissionMode#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/principalpermissionmode/vb/source.vb#8)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="cda02-109">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="cda02-109">Compiling the Code</span></span>  
 <span data-ttu-id="cda02-110">このコードをコンパイルするには、次の名前空間へ参照が必要です。</span><span class="sxs-lookup"><span data-stu-id="cda02-110">References to the following namespaces are needed to compile the code:</span></span>  
  
- <xref:System>  
  
- <xref:System.Collections.Generic>  
  
- <xref:System.Security.Permissions>  
  
- <xref:System.Security.Principal>  
  
- <xref:System.Threading>  
  
- <xref:System.ServiceModel>  
  
- <xref:System.ServiceModel.Channels>  
  
- <xref:System.ServiceModel.Description>  
  
- <xref:System.IdentityModel.Claims>  
  
- <xref:System.IdentityModel.Policy>  
  
## <a name="see-also"></a><span data-ttu-id="cda02-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="cda02-111">See also</span></span>

- <xref:System.ServiceModel.Description.PrincipalPermissionMode>
- <xref:System.Security.Permissions.PrincipalPermissionAttribute>
- [<span data-ttu-id="cda02-112">方法: サービスで ASP.NET ロール プロバイダーを使用します。</span><span class="sxs-lookup"><span data-stu-id="cda02-112">How to: Use the ASP.NET Role Provider with a Service</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md)
- [<span data-ttu-id="cda02-113">方法: PrincipalPermissionAttribute クラスでアクセスを制限します。</span><span class="sxs-lookup"><span data-stu-id="cda02-113">How to: Restrict Access with the PrincipalPermissionAttribute Class</span></span>](../../../../docs/framework/wcf/how-to-restrict-access-with-the-principalpermissionattribute-class.md)
