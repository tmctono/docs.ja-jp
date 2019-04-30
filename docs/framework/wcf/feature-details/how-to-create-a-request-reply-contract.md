---
title: '方法: 要求/応答コントラクトを作成する'
ms.date: 03/30/2017
ms.assetid: 801d90da-3d45-4284-9c9f-56c8aadb4060
ms.openlocfilehash: 7a446db49dcc6a12b900292f1b19c9973835f2c1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62000988"
---
# <a name="how-to-create-a-request-reply-contract"></a><span data-ttu-id="0e092-102">方法: 要求/応答コントラクトを作成する</span><span class="sxs-lookup"><span data-stu-id="0e092-102">How to: Create a Request-Reply Contract</span></span>
<span data-ttu-id="0e092-103">要求/応答コントラクトは、応答を返すメソッドを指定します。</span><span class="sxs-lookup"><span data-stu-id="0e092-103">A request-reply contract specifies a method that returns a reply.</span></span> <span data-ttu-id="0e092-104">応答が送信され、このコントラクトの条件の下で要求に関連付けられる必要があります。</span><span class="sxs-lookup"><span data-stu-id="0e092-104">The reply must be sent and correlated to the request under the terms of this contract.</span></span> <span data-ttu-id="0e092-105">メソッドが応答を返さない場合 (C# の場合は `void` または Visual Basic の場合は `Sub`) でも、インフラストラクチャは、空のメッセージを作成して送信することで、メソッドが返ったことを呼び出し元に示します。</span><span class="sxs-lookup"><span data-stu-id="0e092-105">Even if the method returns no reply (`void` in C#, or a `Sub` in Visual Basic), the infrastructure creates and sends an empty message to the caller.</span></span> <span data-ttu-id="0e092-106">空の応答メッセージが送信されるのを防ぐには、操作で 1 方向コントラクトを使用します。</span><span class="sxs-lookup"><span data-stu-id="0e092-106">To prevent the sending of an empty reply message, use a one-way contract for the operation.</span></span>  
  
### <a name="to-create-a-request-reply-contract"></a><span data-ttu-id="0e092-107">要求/応答コントラクトを作成するには</span><span class="sxs-lookup"><span data-stu-id="0e092-107">To create a request-reply contract</span></span>  
  
1. <span data-ttu-id="0e092-108">選択したプログラミング言語でインターフェイスを作成します。</span><span class="sxs-lookup"><span data-stu-id="0e092-108">Create an interface in the programming language of your choice.</span></span>  
  
2. <span data-ttu-id="0e092-109">インターフェイスに <xref:System.ServiceModel.ServiceContractAttribute> 属性を適用します。</span><span class="sxs-lookup"><span data-stu-id="0e092-109">Apply the <xref:System.ServiceModel.ServiceContractAttribute> attribute to the interface.</span></span>  
  
3. <span data-ttu-id="0e092-110">クライアントが呼び出すことのできる各メソッドに <xref:System.ServiceModel.OperationContractAttribute> 属性を適用します。</span><span class="sxs-lookup"><span data-stu-id="0e092-110">Apply the <xref:System.ServiceModel.OperationContractAttribute> attribute to each method that clients can invoke.</span></span>  
  
4. <span data-ttu-id="0e092-111">任意。</span><span class="sxs-lookup"><span data-stu-id="0e092-111">Optional.</span></span> <span data-ttu-id="0e092-112"><xref:System.ServiceModel.OperationContractAttribute.IsOneWay%2A> プロパティの値を `true` に設定して、空の応答メッセージが送信されることを防止します。</span><span class="sxs-lookup"><span data-stu-id="0e092-112">Set the value of the <xref:System.ServiceModel.OperationContractAttribute.IsOneWay%2A> property to `true` to prevent the sending of an empty reply message.</span></span> <span data-ttu-id="0e092-113">既定では、すべての操作は要求/応答コントラクトです。</span><span class="sxs-lookup"><span data-stu-id="0e092-113">By default, all operations are request-reply contracts.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0e092-114">例</span><span class="sxs-lookup"><span data-stu-id="0e092-114">Example</span></span>  
 <span data-ttu-id="0e092-115">次のサンプルは、`Add` メソッドと `Subtract` メソッドを提供する電卓サービスのコントラクトを定義します。</span><span class="sxs-lookup"><span data-stu-id="0e092-115">The following sample defines a contract for a calculator service that provides `Add` and `Subtract` methods.</span></span> <span data-ttu-id="0e092-116">`Multiply` メソッドは <xref:System.ServiceModel.OperationContractAttribute> クラスでマークされていないため、このコントラクトの一部ではありません。したがって、クライアントからはアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="0e092-116">The `Multiply` method is not part of the contract because it is not marked by the <xref:System.ServiceModel.OperationContractAttribute> class and so it is not accessible to clients.</span></span>  
  
```csharp
using System.ServiceModel;

[ServiceContract]
public interface ICalculator
{
    [OperationContract]
    // It would be equivalent to write explicitly:
    // [OperationContract(IsOneWay=false)]
    int Add(int a, int b);
    
    [OperationContract]
    int Subtract(int a, int b);
    
    int Multiply(int a, int b)
}
```
  
- <span data-ttu-id="0e092-117">操作コントラクトを指定する方法の詳細については、次を参照してください。、<xref:System.ServiceModel.OperationContractAttribute>クラスおよび<xref:System.ServiceModel.OperationContractAttribute.IsOneWay%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="0e092-117">For more information about how to specify operation contracts, see the <xref:System.ServiceModel.OperationContractAttribute> class and the <xref:System.ServiceModel.OperationContractAttribute.IsOneWay%2A> property.</span></span>  
  
- <span data-ttu-id="0e092-118"><xref:System.ServiceModel.ServiceContractAttribute> 属性と <xref:System.ServiceModel.OperationContractAttribute> 属性を適用すると、サービスを展開した後に Web サービス記述言語 (WSDL) ドキュメントでサービス コントラクト定義が自動的に生成されます。</span><span class="sxs-lookup"><span data-stu-id="0e092-118">Applying the <xref:System.ServiceModel.ServiceContractAttribute> and <xref:System.ServiceModel.OperationContractAttribute> attributes causes the automatic generation of service contract definitions in a Web Services Description Language (WSDL) document once the service is deployed.</span></span> <span data-ttu-id="0e092-119">ドキュメントは、サービスの HTTP ベース アドレスに `?wsdl` を付け加えてしてダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="0e092-119">The document is downloaded by appending `?wsdl` to the HTTP base address for the service.</span></span> <span data-ttu-id="0e092-120">たとえば、`http://microsoft/CalculatorService?wsdl`</span><span class="sxs-lookup"><span data-stu-id="0e092-120">For example, `http://microsoft/CalculatorService?wsdl`</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e092-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="0e092-121">See also</span></span>

- <xref:System.ServiceModel.OperationContractAttribute>
- [<span data-ttu-id="0e092-122">サービス コントラクトの設計</span><span class="sxs-lookup"><span data-stu-id="0e092-122">Designing Service Contracts</span></span>](../../../../docs/framework/wcf/designing-service-contracts.md)
- [<span data-ttu-id="0e092-123">方法: 双方向コントラクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="0e092-123">How to: Create a Duplex Contract</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md)
