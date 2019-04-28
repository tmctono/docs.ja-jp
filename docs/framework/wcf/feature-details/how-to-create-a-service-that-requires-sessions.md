---
title: '方法: セッションを必要とするサービスを作成する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8a7613ef-0df9-47c3-b8dc-47f42cb1fd8b
ms.openlocfilehash: 53b6c809103a2a32d544b8317164a5fa3aa81596
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61787635"
---
# <a name="how-to-create-a-service-that-requires-sessions"></a><span data-ttu-id="0220e-102">方法: セッションを必要とするサービスを作成する</span><span class="sxs-lookup"><span data-stu-id="0220e-102">How to: Create a Service That Requires Sessions</span></span>
<span data-ttu-id="0220e-103">セッションでは、複数のエンドポイント間で共有される状態が作成されます。これにより、クライアントとサービス インスタンス間でのコールバック、マルチホップ セキュリティ、関連付けなどの便利な機能を使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="0220e-103">Sessions create a shared state between two or more endpoints that enables useful features such as callbacks, multi-hop security, and associations between clients and service instances.</span></span> <span data-ttu-id="0220e-104">Windows Communication Foundation (WCF) アプリケーションでセッションの詳細については、次を参照してください。[を使用してセッション](../../../../docs/framework/wcf/using-sessions.md)します。</span><span class="sxs-lookup"><span data-stu-id="0220e-104">For more information about sessions in Windows Communication Foundation (WCF) applications, see [Using Sessions](../../../../docs/framework/wcf/using-sessions.md).</span></span>  
  
### <a name="to-specify-that-a-contract-require-its-binding-to-support-sessions"></a><span data-ttu-id="0220e-105">バインディングによるセッションのサポートを要求するコントラクトを指定するには</span><span class="sxs-lookup"><span data-stu-id="0220e-105">To specify that a contract require its binding to support sessions</span></span>  
  
1. <span data-ttu-id="0220e-106">操作を 1 つ以上含むサービス コントラクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="0220e-106">Create a service contract with at least one operation.</span></span> <span data-ttu-id="0220e-107">サービス コントラクトを作成する方法の例は、次を参照してください。[方法。サービス コントラクトを定義する](../../../../docs/framework/wcf/how-to-define-a-wcf-service-contract.md)します。</span><span class="sxs-lookup"><span data-stu-id="0220e-107">For an example of how to create a service contract, see [How to: Define a Service Contract](../../../../docs/framework/wcf/how-to-define-a-wcf-service-contract.md).</span></span>  
  
2. <span data-ttu-id="0220e-108">コントラクトを宣言する <xref:System.ServiceModel.ServiceContractAttribute?displayProperty=nameWithType> を変更します。<xref:System.ServiceModel.ServiceContractAttribute.SessionMode%2A?displayProperty=nameWithType> プロパティを次のいずれかに設定します。</span><span class="sxs-lookup"><span data-stu-id="0220e-108">Modify the <xref:System.ServiceModel.ServiceContractAttribute?displayProperty=nameWithType> that declares the contract by setting the <xref:System.ServiceModel.ServiceContractAttribute.SessionMode%2A?displayProperty=nameWithType> property to either:</span></span>  
  
    - <span data-ttu-id="0220e-109">セッション内でこのコントラクトの実行を要求する場合は <xref:System.ServiceModel.SessionMode.Required?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="0220e-109"><xref:System.ServiceModel.SessionMode.Required?displayProperty=nameWithType> if this contract must be run within a session.</span></span>  
  
    - <span data-ttu-id="0220e-110">セッション内でこのコントラクトを実行できる場合は <xref:System.ServiceModel.SessionMode.Allowed?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="0220e-110"><xref:System.ServiceModel.SessionMode.Allowed?displayProperty=nameWithType> if this contract can be run within a session.</span></span>  
  
    - <span data-ttu-id="0220e-111">セッション内でこのコントラクトの実行を許可しない場合は <xref:System.ServiceModel.SessionMode.NotAllowed?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="0220e-111"><xref:System.ServiceModel.SessionMode.NotAllowed?displayProperty=nameWithType> if this contract must not be run within a session.</span></span>  
  
3. <span data-ttu-id="0220e-112">セッションをサポートするバインディングを使用するようにサービス エンドポイントを構成します。</span><span class="sxs-lookup"><span data-stu-id="0220e-112">Configure your service endpoint to use a binding that supports sessions.</span></span> <span data-ttu-id="0220e-113">次の構成例は、WS<xref:System.ServiceModel.WSDualHttpBinding?displayProperty=nameWithType>ReliableMessaging セッションをサポートする `-` の使用方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="0220e-113">The following configuration example shows the use of the <xref:System.ServiceModel.WSDualHttpBinding?displayProperty=nameWithType>, which supports a WS`-`ReliableMessaging session.</span></span>  
  
     [!code-xml[SCA.Session#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/sca.session/cs/hostapplication.exe.config#2)]   
  
## <a name="example"></a><span data-ttu-id="0220e-114">例</span><span class="sxs-lookup"><span data-stu-id="0220e-114">Example</span></span>  
 <span data-ttu-id="0220e-115">コントラクト レベルのセッション要件を指定し、構成ファイルを使用して、その要件を <xref:System.ServiceModel.WSDualHttpBinding?displayProperty=nameWithType> バインディングでサポートする方法を、次のコード例に示します。</span><span class="sxs-lookup"><span data-stu-id="0220e-115">The following example code shows how to specify a contract-level session requirement and use a configuration file to support that requirement with the <xref:System.ServiceModel.WSDualHttpBinding?displayProperty=nameWithType> binding.</span></span>  
  
 [!code-csharp[SCA.Session#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/sca.session/cs/services.cs#1)] 
 [!code-vb[SCA.Session#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/sca.session/vb/services.vb#1)]      
 [!code-xml[SCA.Session#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/sca.session/cs/hostapplication.exe.config#2)]     
  
## <a name="see-also"></a><span data-ttu-id="0220e-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="0220e-116">See also</span></span>

- <xref:System.ServiceModel.ServiceContractAttribute?displayProperty=nameWithType>
- <xref:System.ServiceModel.ServiceContractAttribute.SessionMode%2A?displayProperty=nameWithType>
- <xref:System.ServiceModel.SessionMode?displayProperty=nameWithType>
