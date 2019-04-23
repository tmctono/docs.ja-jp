---
title: '方法: 承認中にメタデータ要求を許可する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- allowing metadata requests while authorizing [WCF]
ms.assetid: 90cec34f-b619-452b-a056-8b1c0de49d05
ms.openlocfilehash: bea4f7e90df29678697fe6708bdc6a73145522db
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59317702"
---
# <a name="how-to-allow-metadata-requests-while-authorizing"></a><span data-ttu-id="93981-102">方法: 承認中にメタデータ要求を許可する</span><span class="sxs-lookup"><span data-stu-id="93981-102">How To: Allow Metadata Requests While Authorizing</span></span>
<span data-ttu-id="93981-103">カスタム承認中に、メタデータの処理要求を許可することがあります。</span><span class="sxs-lookup"><span data-stu-id="93981-103">During custom authorization, it may be necessary to allow a request for metadata to be processed.</span></span> <span data-ttu-id="93981-104">ここでは、このような要求を検証する手順を示します。</span><span class="sxs-lookup"><span data-stu-id="93981-104">The following topic walks through the steps to validate such a request.</span></span>  
  
 <span data-ttu-id="93981-105">Windows Communication Foundation (WCF) の承認についての詳細については、次を参照してください。[承認](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md)します。</span><span class="sxs-lookup"><span data-stu-id="93981-105">For more information about Windows Communication Foundation (WCF) authorization, see [Authorization](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md).</span></span>  
  
### <a name="to-allow-metadata-requests-during-authorization"></a><span data-ttu-id="93981-106">承認中にメタデータ要求を許可するには</span><span class="sxs-lookup"><span data-stu-id="93981-106">To allow metadata requests during authorization</span></span>  
  
1. <span data-ttu-id="93981-107"><xref:System.ServiceModel.ServiceAuthorizationManager> クラスの拡張を作成します。</span><span class="sxs-lookup"><span data-stu-id="93981-107">Create an extension of the <xref:System.ServiceModel.ServiceAuthorizationManager> class.</span></span>  
  
2. <span data-ttu-id="93981-108"><xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%2A> メソッドをオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="93981-108">Override the <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%2A> method.</span></span> <span data-ttu-id="93981-109">このメソッドは、承認が許可されるかどうかによって、`true` または `false` を返します。</span><span class="sxs-lookup"><span data-stu-id="93981-109">The method returns `true` or `false` depending on whether authorization is allowed.</span></span> <span data-ttu-id="93981-110">現在のプロシージャに関する情報は、メソッドへのパラメーターとして渡される <xref:System.ServiceModel.OperationContext> にあります。</span><span class="sxs-lookup"><span data-stu-id="93981-110">Information about the current procedure is found in the <xref:System.ServiceModel.OperationContext> passed as a parameter to the method.</span></span>  
  
3. <span data-ttu-id="93981-111">オーバーライドで、コントラクト名、名前空間、およびアクションを確認します。次の例を参照してください。</span><span class="sxs-lookup"><span data-stu-id="93981-111">In the override, check the contract name, namespace, and the action as shown in the following example.</span></span> <span data-ttu-id="93981-112">条件が有効な場合は、`true.` を返します。</span><span class="sxs-lookup"><span data-stu-id="93981-112">If the conditions are valid, then return `true.`</span></span>  
  
4. <span data-ttu-id="93981-113">クラスを使用するための拡張ポイントを使用します。</span><span class="sxs-lookup"><span data-stu-id="93981-113">Use the extensibility point to employ the class.</span></span> <span data-ttu-id="93981-114">詳細については、「[方法 :サービスのカスタム承認マネージャーを作成する](../../../../docs/framework/wcf/extending/how-to-create-a-custom-authorization-manager-for-a-service.md)します。</span><span class="sxs-lookup"><span data-stu-id="93981-114">For more information, see [How to: Create a Custom Authorization Manager for a Service](../../../../docs/framework/wcf/extending/how-to-create-a-custom-authorization-manager-for-a-service.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="93981-115">例</span><span class="sxs-lookup"><span data-stu-id="93981-115">Example</span></span>  
 <span data-ttu-id="93981-116"><xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%2A> メソッドのオーバーライドを次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="93981-116">The following example shows an override of the <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%2A> method.</span></span>  
  
 [!code-csharp[C_HowtoCheckForMexRequestsInAuthorization#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howtocheckformexrequestsinauthorization/cs/source.cs#1)]
 [!code-vb[C_HowtoCheckForMexRequestsInAuthorization#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howtocheckformexrequestsinauthorization/vb/source.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="93981-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="93981-117">See also</span></span>

- <xref:System.ServiceModel.ServiceAuthorizationManager>
- [<span data-ttu-id="93981-118">承認</span><span class="sxs-lookup"><span data-stu-id="93981-118">Authorization</span></span>](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md)
- [<span data-ttu-id="93981-119">ID モデルを使用したクレームと承認の管理</span><span class="sxs-lookup"><span data-stu-id="93981-119">Managing Claims and Authorization with the Identity Model</span></span>](../../../../docs/framework/wcf/feature-details/managing-claims-and-authorization-with-the-identity-model.md)
