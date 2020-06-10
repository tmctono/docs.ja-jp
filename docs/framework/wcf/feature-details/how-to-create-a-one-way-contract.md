---
title: '方法: 一方向コントラクトを作成する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 85084cd9-31cc-4e95-b667-42ef01336622
ms.openlocfilehash: 42c056c9b56ed1245290cd66833cc6565f517b66
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84593452"
---
# <a name="how-to-create-a-one-way-contract"></a><span data-ttu-id="fec91-102">方法: 一方向コントラクトを作成する</span><span class="sxs-lookup"><span data-stu-id="fec91-102">How to: Create a One-Way Contract</span></span>
<span data-ttu-id="fec91-103">ここでは、一方向コントラクトを使用するメソッドを作成するための基本手順を示します。</span><span class="sxs-lookup"><span data-stu-id="fec91-103">This topic shows the basic steps to create methods that use a one-way contract.</span></span> <span data-ttu-id="fec91-104">このようなメソッドは、クライアントから Windows Communication Foundation (WCF) サービスに対して操作を呼び出しますが、応答を想定していません。</span><span class="sxs-lookup"><span data-stu-id="fec91-104">Such methods invoke operations on a Windows Communication Foundation (WCF) service from a client but do not expect a reply.</span></span> <span data-ttu-id="fec91-105">この種のコントラクトは、たとえば、多数のサブスクライバーに対して通知を発行するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="fec91-105">This type of contract can be used, for example, to publish notifications to many subscribers.</span></span> <span data-ttu-id="fec91-106">一方向コントラクトは、二重のコントラクトを作成する場合にも使用できます。その場合は、クライアントとサーバーが互いに独立して通信できるため、どちらからでも相手の呼び出しを開始できます。</span><span class="sxs-lookup"><span data-stu-id="fec91-106">You can also use one-way contracts when creating a duplex (two-way) contract, which allows clients and servers to communicate with each other independently so that either can initiate calls to the other.</span></span> <span data-ttu-id="fec91-107">これにより、特にサーバーは、クライアントがイベントとして処理できる一方向の呼び出しをクライアントに対して実行できます。</span><span class="sxs-lookup"><span data-stu-id="fec91-107">This can allow, in particular, the server to make one-way calls to the client that the client can treat as events.</span></span> <span data-ttu-id="fec91-108">一方向メソッドの指定の詳細については、<xref:System.ServiceModel.OperationContractAttribute.IsOneWay%2A> プロパティおよび <xref:System.ServiceModel.OperationContractAttribute> クラスのトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="fec91-108">For detailed information about specifying one-way methods, see the <xref:System.ServiceModel.OperationContractAttribute.IsOneWay%2A> property and the <xref:System.ServiceModel.OperationContractAttribute> class.</span></span>  
  
 <span data-ttu-id="fec91-109">双方向コントラクト用のクライアントアプリケーションを作成する方法の詳細については、「[方法: 一方向コントラクトと要求/応答コントラクトを使用してサービスにアクセスする](how-to-access-wcf-services-with-one-way-and-request-reply-contracts.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fec91-109">For more information about creating a client application for a duplex contract, see [How to: Access Services with One-Way and Request-Reply Contracts](how-to-access-wcf-services-with-one-way-and-request-reply-contracts.md).</span></span> <span data-ttu-id="fec91-110">実際のサンプルについては、[一方向](../samples/one-way.md)のサンプルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="fec91-110">For a working sample, see the [One-Way](../samples/one-way.md) sample.</span></span>  
  
### <a name="to-create-a-one-way-contract"></a><span data-ttu-id="fec91-111">一方向コントラクトを作成するには</span><span class="sxs-lookup"><span data-stu-id="fec91-111">To create a one-way contract</span></span>  
  
1. <span data-ttu-id="fec91-112">サービスにより実装されるメソッドを定義するインターフェイスに <xref:System.ServiceModel.ServiceContractAttribute> クラスを適用することにより、サービス コントラクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="fec91-112">Create the service contract by applying the <xref:System.ServiceModel.ServiceContractAttribute> class to the interface that defines the methods the service is to implement.</span></span>  
  
2. <span data-ttu-id="fec91-113"><xref:System.ServiceModel.OperationContractAttribute> クラスをメソッドに適用する際に、クライアントが呼び出すことのできるインターフェイスのメソッドを指定します。</span><span class="sxs-lookup"><span data-stu-id="fec91-113">Indicate which methods in the interface a client can invoked by applying the <xref:System.ServiceModel.OperationContractAttribute> class to them.</span></span>  
  
3. <span data-ttu-id="fec91-114"><xref:System.ServiceModel.OperationContractAttribute.IsOneWay%2A> プロパティを `true` に設定することにより、出力を行わない (戻り値および出力または参照パラメーターを持たない) 一方向の操作を指定します。</span><span class="sxs-lookup"><span data-stu-id="fec91-114">Designate operations that must have no output (no return value and no out or ref parameters) as one-way by setting the <xref:System.ServiceModel.OperationContractAttribute.IsOneWay%2A> property to `true`.</span></span> <span data-ttu-id="fec91-115"><xref:System.ServiceModel.OperationContractAttribute> プロパティの既定値は <xref:System.ServiceModel.OperationContractAttribute.IsOneWay%2A> であるため、`false` クラスを持つ操作では、既定で要求/応答コントラクトが満たされることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="fec91-115">Note that the operations that carry the <xref:System.ServiceModel.OperationContractAttribute> class satisfy a request-reply contract by default because the <xref:System.ServiceModel.OperationContractAttribute.IsOneWay%2A> property is `false` by default.</span></span> <span data-ttu-id="fec91-116">したがって、このメソッドに一方向コントラクトが必要な場合は、この属性プロパティの値を明示的に `true` に指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fec91-116">So you must explicitly specify the value of the attribute property to be `true` if you want a one-way contract for the method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fec91-117">例</span><span class="sxs-lookup"><span data-stu-id="fec91-117">Example</span></span>  
 <span data-ttu-id="fec91-118">複数の一方向メソッドを含むサービスのコントラクトを定義する方法を次のコード例に示します。</span><span class="sxs-lookup"><span data-stu-id="fec91-118">The following code example defines a contract for a service that includes several one-way methods.</span></span> <span data-ttu-id="fec91-119">`Equals` (既定で応答/要求コントラクトに設定され、結果を返します) を除き、すべてのメソッドは一方向コントラクトを持ちます。</span><span class="sxs-lookup"><span data-stu-id="fec91-119">All of the methods have one-way contracts except `Equals`, which defaults to request-reply and returns a result.</span></span>  
  
 [!code-csharp[S_Service_Session#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_service_session/cs/service.cs#1)]
 [!code-vb[S_Service_Session#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_service_session/vb/service.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="fec91-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="fec91-120">See also</span></span>

- <xref:System.ServiceModel.ServiceContractAttribute>
- <xref:System.ServiceModel.OperationContractAttribute>
- [<span data-ttu-id="fec91-121">サービスの設計と実装</span><span class="sxs-lookup"><span data-stu-id="fec91-121">Designing and Implementing Services</span></span>](../designing-and-implementing-services.md)
- [<span data-ttu-id="fec91-122">方法: サービス コントラクトを定義する</span><span class="sxs-lookup"><span data-stu-id="fec91-122">How to: Define a Service Contract</span></span>](../how-to-define-a-wcf-service-contract.md)
- [<span data-ttu-id="fec91-123">セッション</span><span class="sxs-lookup"><span data-stu-id="fec91-123">Session</span></span>](../samples/session.md)
- [<span data-ttu-id="fec91-124">方法: 双方向コントラクトを作成する</span><span class="sxs-lookup"><span data-stu-id="fec91-124">How to: Create a Duplex Contract</span></span>](how-to-create-a-duplex-contract.md)
