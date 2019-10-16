---
title: '方法 : 非同期サービス操作を実装する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 4e5d2ea5-d8f8-4712-bd18-ea3c5461702c
ms.openlocfilehash: b706ec49db123f33b3fc1ab0f420ed9a47e32f67
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72320945"
---
# <a name="how-to-implement-an-asynchronous-service-operation"></a><span data-ttu-id="6ab37-102">方法 : 非同期サービス操作を実装する</span><span class="sxs-lookup"><span data-stu-id="6ab37-102">How to: Implement an Asynchronous Service Operation</span></span>
<span data-ttu-id="6ab37-103">Windows Communication Foundation (WCF) アプリケーションでは、サービス操作の呼び出し方法をクライアントに指示することなく、非同期または同期的に実装できます。</span><span class="sxs-lookup"><span data-stu-id="6ab37-103">In Windows Communication Foundation (WCF) applications, a service operation can be implemented asynchronously or synchronously without dictating to the client how to call it.</span></span> <span data-ttu-id="6ab37-104">たとえば、非同期サービス操作を同期的に呼び出すことができ、同期サービス操作を非同期的に呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="6ab37-104">For example, asynchronous service operations can be called synchronously, and synchronous service operations can be called asynchronously.</span></span> <span data-ttu-id="6ab37-105">クライアントアプリケーションで操作を非同期に呼び出す方法を示す例については、「[方法: サービス操作を非同期に呼び出す](./feature-details/how-to-call-wcf-service-operations-asynchronously.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6ab37-105">For an example that shows how to call an operation asynchronously in a client application, see [How to: Call Service Operations Asynchronously](./feature-details/how-to-call-wcf-service-operations-asynchronously.md).</span></span> <span data-ttu-id="6ab37-106">同期操作と非同期操作の詳細については、「[サービスコントラクトの設計](designing-service-contracts.md)」および「[同期および非同期操作](synchronous-and-asynchronous-operations.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6ab37-106">For more information about synchronous and asynchronous operations, see [Designing Service Contracts](designing-service-contracts.md) and [Synchronous and Asynchronous Operations](synchronous-and-asynchronous-operations.md).</span></span> <span data-ttu-id="6ab37-107">このトピックでは、非同期サービス操作の基本構造について説明します。コードは部分的なコードです。</span><span class="sxs-lookup"><span data-stu-id="6ab37-107">This topic describes the basic structure of an asynchronous service operation, the code is not complete.</span></span> <span data-ttu-id="6ab37-108">サービス側とクライアント側の両方の完全な例については、「[非同期](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms751505(v=vs.100))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6ab37-108">For a complete example of both the service and client sides, see [Asynchronous](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms751505(v=vs.100)).</span></span>  
  
### <a name="implement-a-service-operation-asynchronously"></a><span data-ttu-id="6ab37-109">非同期サービス操作の実装</span><span class="sxs-lookup"><span data-stu-id="6ab37-109">Implement a service operation asynchronously</span></span>  
  
1. <span data-ttu-id="6ab37-110">サービス コントラクトで、.NET 非同期デザイン ガイドラインに従って非同期メソッドのペアを宣言します。</span><span class="sxs-lookup"><span data-stu-id="6ab37-110">In your service contract, declare an asynchronous method pair according to the .NET asynchronous design guidelines.</span></span> <span data-ttu-id="6ab37-111">`Begin` メソッドは、パラメーター、コールバック オブジェクト、状態オブジェクトを受け取って <xref:System.IAsyncResult?displayProperty=nameWithType> を返し、組になる `End` メソッドは <xref:System.IAsyncResult?displayProperty=nameWithType> を受け取って戻り値を返します。</span><span class="sxs-lookup"><span data-stu-id="6ab37-111">The `Begin` method takes a parameter, a callback object, and a state object, and returns a <xref:System.IAsyncResult?displayProperty=nameWithType> and a matching `End` method that takes a <xref:System.IAsyncResult?displayProperty=nameWithType> and returns the return value.</span></span> <span data-ttu-id="6ab37-112">非同期呼び出しの詳細については、「[非同期プログラミングのデザインパターン](https://go.microsoft.com/fwlink/?LinkId=248221)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6ab37-112">For more information about asynchronous calls, see [Asynchronous Programming Design Patterns](https://go.microsoft.com/fwlink/?LinkId=248221).</span></span>  
  
2. <span data-ttu-id="6ab37-113">非同期メソッド ペアの `Begin` メソッドを <xref:System.ServiceModel.OperationContractAttribute?displayProperty=nameWithType> 属性を使用してマークし、<xref:System.ServiceModel.OperationContractAttribute.AsyncPattern%2A?displayProperty=nameWithType> プロパティを `true` に設定します。</span><span class="sxs-lookup"><span data-stu-id="6ab37-113">Mark the `Begin` method of the asynchronous method pair with the <xref:System.ServiceModel.OperationContractAttribute?displayProperty=nameWithType> attribute and set the <xref:System.ServiceModel.OperationContractAttribute.AsyncPattern%2A?displayProperty=nameWithType> property to `true`.</span></span> <span data-ttu-id="6ab37-114">たとえば、次のコード例では手順 1. と 2. を実行します。</span><span class="sxs-lookup"><span data-stu-id="6ab37-114">For example, the following code performs steps 1 and 2.</span></span>  
  
     [!code-csharp[C_SyncAsyncClient#6](../../../samples/snippets/csharp/VS_Snippets_CFX/c_syncasyncclient/cs/services.cs#6)]
     [!code-vb[C_SyncAsyncClient#6](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_syncasyncclient/vb/services.vb#6)]  
  
3. <span data-ttu-id="6ab37-115">非同期デザインのガイドラインに従って、`Begin/End` メソッド ペアをサービス クラスに実装します。</span><span class="sxs-lookup"><span data-stu-id="6ab37-115">Implement the `Begin/End` method pair in your service class according to the asynchronous design guidelines.</span></span> <span data-ttu-id="6ab37-116">たとえば、次のコード例では、非同期サービス操作の `Begin` および `End` の両方の部分の文字列がコンソールに書き出され、`End` 操作の戻り値がクライアントに返される実装を示します。</span><span class="sxs-lookup"><span data-stu-id="6ab37-116">For example, the following code example shows an implementation in which a string is written to the console in both the `Begin` and `End` portions of the asynchronous service operation, and the return value of the `End` operation is returned to the client.</span></span> <span data-ttu-id="6ab37-117">コード例全体については、「使用例」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6ab37-117">For the complete code example, see the Example section.</span></span>  
  
     [!code-csharp[C_SyncAsyncClient#3](../../../samples/snippets/csharp/VS_Snippets_CFX/c_syncasyncclient/cs/services.cs#3)]
     [!code-vb[C_SyncAsyncClient#3](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_syncasyncclient/vb/services.vb#3)]  
  
## <a name="example"></a><span data-ttu-id="6ab37-118">例</span><span class="sxs-lookup"><span data-stu-id="6ab37-118">Example</span></span>  
 <span data-ttu-id="6ab37-119">このコード例では次のものが示されます。</span><span class="sxs-lookup"><span data-stu-id="6ab37-119">The following code examples show:</span></span>  
  
1. <span data-ttu-id="6ab37-120">次の操作とのサービス コントラクト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6ab37-120">A service contract interface with:</span></span>  
  
    1. <span data-ttu-id="6ab37-121">同期 `SampleMethod` 操作</span><span class="sxs-lookup"><span data-stu-id="6ab37-121">A synchronous `SampleMethod` operation.</span></span>  
  
    2. <span data-ttu-id="6ab37-122">非同期 `BeginSampleMethod` 操作</span><span class="sxs-lookup"><span data-stu-id="6ab37-122">An asynchronous `BeginSampleMethod` operation.</span></span>  
  
    3. <span data-ttu-id="6ab37-123">非同期 `BeginServiceAsyncMethod` @ no__t @ no__t 操作のペア。</span><span class="sxs-lookup"><span data-stu-id="6ab37-123">An asynchronous `BeginServiceAsyncMethod`/`EndServiceAsyncMethod` operation pair.</span></span>  
  
2. <span data-ttu-id="6ab37-124"><xref:System.IAsyncResult?displayProperty=nameWithType> オブジェクトを使用したサービスの実装</span><span class="sxs-lookup"><span data-stu-id="6ab37-124">A service implementation using a <xref:System.IAsyncResult?displayProperty=nameWithType> object.</span></span>  
  
 [!code-csharp[C_SyncAsyncClient#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_syncasyncclient/cs/services.cs#1)]
 [!code-vb[C_SyncAsyncClient#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_syncasyncclient/vb/services.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="6ab37-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="6ab37-125">See also</span></span>

- [<span data-ttu-id="6ab37-126">サービス コントラクトの設計</span><span class="sxs-lookup"><span data-stu-id="6ab37-126">Designing Service Contracts</span></span>](designing-service-contracts.md)
- [<span data-ttu-id="6ab37-127">同期操作と非同期操作</span><span class="sxs-lookup"><span data-stu-id="6ab37-127">Synchronous and Asynchronous Operations</span></span>](synchronous-and-asynchronous-operations.md)
