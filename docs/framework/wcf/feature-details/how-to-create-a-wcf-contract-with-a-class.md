---
title: '方法: クラスを持つ、Windows Communication Foundation コントラクトを作成します。'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 1ad69393-3915-4e7f-9b91-b6fc59c6f5ba
ms.openlocfilehash: 37d0e6fae8ad0f3a91f1bead23fb5823fc52d420
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61787583"
---
# <a name="how-to-create-a-windows-communication-foundation-contract-with-a-class"></a><span data-ttu-id="f3a88-102">方法: クラスを持つ、Windows Communication Foundation コントラクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="f3a88-102">How to: Create a Windows Communication Foundation Contract with a Class</span></span>
<span data-ttu-id="f3a88-103">インターフェイスを使用する Windows Communication Foundation (WCF) コントラクトを作成することをお勧めです。</span><span class="sxs-lookup"><span data-stu-id="f3a88-103">The preferred way of creating a Windows Communication Foundation (WCF) contract is by using an interface.</span></span> <span data-ttu-id="f3a88-104">詳細については、「[方法 :サービス コントラクトを定義する](../../../../docs/framework/wcf/how-to-define-a-wcf-service-contract.md)します。</span><span class="sxs-lookup"><span data-stu-id="f3a88-104">For more information, see [How to: Define a Service Contract](../../../../docs/framework/wcf/how-to-define-a-wcf-service-contract.md).</span></span> <span data-ttu-id="f3a88-105">ここで説明する代替方法では、クラスを作成してから、<xref:System.ServiceModel.ServiceContractAttribute> 属性を直接そのクラスに適用し、<xref:System.ServiceModel.OperationContractAttribute> 属性をコントラクトに含まれるクラス内の各メソッドに適用します。</span><span class="sxs-lookup"><span data-stu-id="f3a88-105">An alternative, outlined here, is to create a class and then apply the <xref:System.ServiceModel.ServiceContractAttribute> attribute to the class directly and the <xref:System.ServiceModel.OperationContractAttribute> attribute to each of the methods in the class that are part of the contract.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="f3a88-106">`[ServiceContract]` と `[ServiceContractAttribute]` は、同じことを行います。</span><span class="sxs-lookup"><span data-stu-id="f3a88-106">`[ServiceContract]` and `[ServiceContractAttribute]` do the same thing.</span></span> <span data-ttu-id="f3a88-107">同じことが当てはまります`[OperationContract]`と`[OperationContractAttribute]`します。</span><span class="sxs-lookup"><span data-stu-id="f3a88-107">The same thing is true for `[OperationContract]` and `[OperationContractAttribute]`.</span></span> <span data-ttu-id="f3a88-108">各ケースでは、後者の短縮形です。</span><span class="sxs-lookup"><span data-stu-id="f3a88-108">In each case, the former is shorthand for the latter.</span></span>  
  
 <span data-ttu-id="f3a88-109">サービス コントラクトの詳細については、次を参照してください。 [Designing Service Contracts](../../../../docs/framework/wcf/designing-service-contracts.md)します。</span><span class="sxs-lookup"><span data-stu-id="f3a88-109">For more information about service contracts, see [Designing Service Contracts](../../../../docs/framework/wcf/designing-service-contracts.md).</span></span>  
  
### <a name="creating-a-windows-communication-foundation-contract-with-a-class"></a><span data-ttu-id="f3a88-110">クラスを使用した Windows Communication Foundation コントラクトの作成</span><span class="sxs-lookup"><span data-stu-id="f3a88-110">Creating a Windows Communication Foundation contract with a class</span></span>  
  
1. <span data-ttu-id="f3a88-111">Visual Basic を使用して新しいクラスを作成C#、またはその他の共通言語ランタイム言語。</span><span class="sxs-lookup"><span data-stu-id="f3a88-111">Create a new class using Visual Basic, C#, or any other common language runtime language.</span></span>  
  
2. <span data-ttu-id="f3a88-112">クラスに <xref:System.ServiceModel.ServiceContractAttribute> クラスを適用します。</span><span class="sxs-lookup"><span data-stu-id="f3a88-112">Apply the <xref:System.ServiceModel.ServiceContractAttribute> class to the class.</span></span>  
  
3. <span data-ttu-id="f3a88-113">クラスでメソッドを作成します。</span><span class="sxs-lookup"><span data-stu-id="f3a88-113">Create methods in the class.</span></span>  
  
4. <span data-ttu-id="f3a88-114">適用、<xref:System.ServiceModel.OperationContractAttribute>パブリックの WCF コントラクトの一部として公開する必要がある各メソッドにクラス。</span><span class="sxs-lookup"><span data-stu-id="f3a88-114">Apply the <xref:System.ServiceModel.OperationContractAttribute> class to each method that must be exposed as part of the public WCF contract.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f3a88-115">例</span><span class="sxs-lookup"><span data-stu-id="f3a88-115">Example</span></span>  
 <span data-ttu-id="f3a88-116">次のコード例は、サービス コントラクトを定義するクラスを示しています。</span><span class="sxs-lookup"><span data-stu-id="f3a88-116">The following code example shows a class that defines a service contract.</span></span>  
  
 [!code-csharp[c_HowTo_CreateContractWithClass#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createcontractwithclass/cs/source.cs#1)]
 [!code-vb[c_HowTo_CreateContractWithClass#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_createcontractwithclass/vb/source.vb#1)]  
  
 <span data-ttu-id="f3a88-117"><xref:System.ServiceModel.OperationContractAttribute> クラスが適用されたメソッドは、既定で要求/応答メッセージ パターンを使用します。</span><span class="sxs-lookup"><span data-stu-id="f3a88-117">The methods that have the <xref:System.ServiceModel.OperationContractAttribute> class applied use a request-reply message pattern by default.</span></span> <span data-ttu-id="f3a88-118">このメッセージ パターンの詳細については、次を参照してください。[方法。要求/応答コントラクトを作成する](../../../../docs/framework/wcf/feature-details/how-to-create-a-request-reply-contract.md)します。</span><span class="sxs-lookup"><span data-stu-id="f3a88-118">For more information about this message pattern, see [How to: Create a Request-Reply Contract](../../../../docs/framework/wcf/feature-details/how-to-create-a-request-reply-contract.md).</span></span> <span data-ttu-id="f3a88-119">属性のプロパティを設定することにより、他のメッセージ パターンを作成および使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="f3a88-119">You can also create and use other message patterns by setting properties of the attribute.</span></span> <span data-ttu-id="f3a88-120">その他の例については、「[方法:一方向コントラクトを作成する](../../../../docs/framework/wcf/feature-details/how-to-create-a-one-way-contract.md)と[方法。双方向コントラクトを作成する](../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md)します。</span><span class="sxs-lookup"><span data-stu-id="f3a88-120">For more examples, see [How to: Create a One-Way Contract](../../../../docs/framework/wcf/feature-details/how-to-create-a-one-way-contract.md) and [How to: Create a Duplex Contract](../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3a88-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="f3a88-121">See also</span></span>

- <xref:System.ServiceModel.ServiceContractAttribute>
- <xref:System.ServiceModel.OperationContractAttribute>
