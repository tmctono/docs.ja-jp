---
title: '方法: クラスを使用して Windows Communication Foundation コントラクトを作成する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 1ad69393-3915-4e7f-9b91-b6fc59c6f5ba
ms.openlocfilehash: 2cd757107d9f62ce749d98db1d4968c02a09c5d2
ms.sourcegitcommit: 37616676fde89153f563a485fc6159fc57326fc2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/23/2019
ms.locfileid: "69988746"
---
# <a name="how-to-create-a-windows-communication-foundation-contract-with-a-class"></a><span data-ttu-id="46c8b-102">方法: クラスを使用して Windows Communication Foundation コントラクトを作成する</span><span class="sxs-lookup"><span data-stu-id="46c8b-102">How to: Create a Windows Communication Foundation Contract with a Class</span></span>
<span data-ttu-id="46c8b-103">Windows Communication Foundation (WCF) コントラクトを作成する場合は、インターフェイスを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="46c8b-103">The preferred way of creating a Windows Communication Foundation (WCF) contract is by using an interface.</span></span> <span data-ttu-id="46c8b-104">詳細については、「[方法 :サービスコントラクト](../../../../docs/framework/wcf/how-to-define-a-wcf-service-contract.md)を定義します。</span><span class="sxs-lookup"><span data-stu-id="46c8b-104">For more information, see [How to: Define a Service Contract](../../../../docs/framework/wcf/how-to-define-a-wcf-service-contract.md).</span></span> <span data-ttu-id="46c8b-105">ここで説明する代替方法では、クラスを作成してから、<xref:System.ServiceModel.ServiceContractAttribute> 属性を直接そのクラスに適用し、<xref:System.ServiceModel.OperationContractAttribute> 属性をコントラクトに含まれるクラス内の各メソッドに適用します。</span><span class="sxs-lookup"><span data-stu-id="46c8b-105">An alternative, outlined here, is to create a class and then apply the <xref:System.ServiceModel.ServiceContractAttribute> attribute to the class directly and the <xref:System.ServiceModel.OperationContractAttribute> attribute to each of the methods in the class that are part of the contract.</span></span>  
  
> [!WARNING]
> <span data-ttu-id="46c8b-106">`[ServiceContract]` と `[ServiceContractAttribute]` は、同じことを行います。</span><span class="sxs-lookup"><span data-stu-id="46c8b-106">`[ServiceContract]` and `[ServiceContractAttribute]` do the same thing.</span></span> <span data-ttu-id="46c8b-107">`[OperationContract]` と`[OperationContractAttribute]`についても同じことが当てはまります。</span><span class="sxs-lookup"><span data-stu-id="46c8b-107">The same thing is true for `[OperationContract]` and `[OperationContractAttribute]`.</span></span> <span data-ttu-id="46c8b-108">どちらの場合も、前者は後者の短縮形です。</span><span class="sxs-lookup"><span data-stu-id="46c8b-108">In each case, the former is shorthand for the latter.</span></span>  
  
 <span data-ttu-id="46c8b-109">サービスコントラクトの詳細については、「[サービスコントラクトの設計](../../../../docs/framework/wcf/designing-service-contracts.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="46c8b-109">For more information about service contracts, see [Designing Service Contracts](../../../../docs/framework/wcf/designing-service-contracts.md).</span></span>  
  
### <a name="creating-a-windows-communication-foundation-contract-with-a-class"></a><span data-ttu-id="46c8b-110">クラスを使用した Windows Communication Foundation コントラクトの作成</span><span class="sxs-lookup"><span data-stu-id="46c8b-110">Creating a Windows Communication Foundation contract with a class</span></span>  
  
1. <span data-ttu-id="46c8b-111">Visual Basic、 C#、またはその他の共通言語ランタイム言語を使用して、新しいクラスを作成します。</span><span class="sxs-lookup"><span data-stu-id="46c8b-111">Create a new class using Visual Basic, C#, or any other common language runtime language.</span></span>  
  
2. <span data-ttu-id="46c8b-112">クラスに <xref:System.ServiceModel.ServiceContractAttribute> クラスを適用します。</span><span class="sxs-lookup"><span data-stu-id="46c8b-112">Apply the <xref:System.ServiceModel.ServiceContractAttribute> class to the class.</span></span>  
  
3. <span data-ttu-id="46c8b-113">クラスでメソッドを作成します。</span><span class="sxs-lookup"><span data-stu-id="46c8b-113">Create methods in the class.</span></span>  
  
4. <span data-ttu-id="46c8b-114">パブリック WCF コントラクトの一部として公開する必要がある各メソッドにクラスを適用します。<xref:System.ServiceModel.OperationContractAttribute></span><span class="sxs-lookup"><span data-stu-id="46c8b-114">Apply the <xref:System.ServiceModel.OperationContractAttribute> class to each method that must be exposed as part of the public WCF contract.</span></span>  
  
## <a name="example"></a><span data-ttu-id="46c8b-115">例</span><span class="sxs-lookup"><span data-stu-id="46c8b-115">Example</span></span>  
 <span data-ttu-id="46c8b-116">次のコード例は、サービス コントラクトを定義するクラスを示しています。</span><span class="sxs-lookup"><span data-stu-id="46c8b-116">The following code example shows a class that defines a service contract.</span></span>  
  
 [!code-csharp[c_HowTo_CreateContractWithClass#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createcontractwithclass/cs/source.cs#1)]
 [!code-vb[c_HowTo_CreateContractWithClass#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_createcontractwithclass/vb/source.vb#1)]  
  
 <span data-ttu-id="46c8b-117"><xref:System.ServiceModel.OperationContractAttribute> クラスが適用されたメソッドは、既定で要求/応答メッセージ パターンを使用します。</span><span class="sxs-lookup"><span data-stu-id="46c8b-117">The methods that have the <xref:System.ServiceModel.OperationContractAttribute> class applied use a request-reply message pattern by default.</span></span> <span data-ttu-id="46c8b-118">このメッセージパターンの詳細については[、「」を参照してください。要求/応答コントラクト](../../../../docs/framework/wcf/feature-details/how-to-create-a-request-reply-contract.md)を作成します。</span><span class="sxs-lookup"><span data-stu-id="46c8b-118">For more information about this message pattern, see [How to: Create a Request-Reply Contract](../../../../docs/framework/wcf/feature-details/how-to-create-a-request-reply-contract.md).</span></span> <span data-ttu-id="46c8b-119">属性のプロパティを設定することにより、他のメッセージ パターンを作成および使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="46c8b-119">You can also create and use other message patterns by setting properties of the attribute.</span></span> <span data-ttu-id="46c8b-120">その他の例については、「[方法:一方向コントラクト](../../../../docs/framework/wcf/feature-details/how-to-create-a-one-way-contract.md)を作成し[、次の操作を行います。双方向コントラクトを作成する](../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md)します。</span><span class="sxs-lookup"><span data-stu-id="46c8b-120">For more examples, see [How to: Create a One-Way Contract](../../../../docs/framework/wcf/feature-details/how-to-create-a-one-way-contract.md) and [How to: Create a Duplex Contract](../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46c8b-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="46c8b-121">See also</span></span>

- <xref:System.ServiceModel.ServiceContractAttribute>
- <xref:System.ServiceModel.OperationContractAttribute>
