---
title: インターセプター (WCF Data Services)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, customizing
- query interceptors [WCF Data Services]
ms.assetid: e33ae8dc-8069-41d0-99a0-75ff28db7050
ms.openlocfilehash: 7decfdd738e71a01afa8cb32604953142b46e588
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70790439"
---
# <a name="interceptors-wcf-data-services"></a><span data-ttu-id="38ab4-102">インターセプター (WCF Data Services)</span><span class="sxs-lookup"><span data-stu-id="38ab4-102">Interceptors (WCF Data Services)</span></span>
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]<span data-ttu-id="38ab4-103">操作にカスタムロジックを追加できるように、アプリケーションが要求メッセージを受け取ることができるようにします。</span><span class="sxs-lookup"><span data-stu-id="38ab4-103">enables an application to intercept request messages so that you can add custom logic to an operation.</span></span> <span data-ttu-id="38ab4-104">このカスタムロジックを使用して、受信メッセージのデータを検証できます。</span><span class="sxs-lookup"><span data-stu-id="38ab4-104">You can use this custom logic to validate data in incoming messages.</span></span> <span data-ttu-id="38ab4-105">このカスタム ロジックを使用して、クエリ要求の範囲をさらに制限することもできます (カスタム認証ポリシーを要求ごとに挿入するなど)。</span><span class="sxs-lookup"><span data-stu-id="38ab4-105">You can also use it to further restrict the scope of a query request, such as to insert a custom authorization policy on a per request basis.</span></span>  
  
 <span data-ttu-id="38ab4-106">先に取得するには、データ サービスで特別なメソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="38ab4-106">Interception is performed by specially attributed methods in the data service.</span></span> <span data-ttu-id="38ab4-107">これらのメソッドは、メッセージ処理の適切なポイントで [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] によって呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="38ab4-107">These methods are called by [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] at the appropriate point in message processing.</span></span> <span data-ttu-id="38ab4-108">インターセプターはエンティティセットごとに定義されます。インターセプターメソッドは、サービス操作のように要求からのパラメーターを受け取ることはできません。</span><span class="sxs-lookup"><span data-stu-id="38ab4-108">Interceptors are defined on a per-entity set basis, and interceptor methods cannot accept parameters from the request like service operations can.</span></span> <span data-ttu-id="38ab4-109">HTTP GET 要求を処理するときに呼び出されるクエリインターセプターメソッドは、インターセプターのエンティティセットのインスタンスがクエリの結果によって返される必要があるかどうかを判断するラムダ式を返す必要があります。</span><span class="sxs-lookup"><span data-stu-id="38ab4-109">Query interceptor methods, which are called when processing an HTTP GET request, must return a lambda expression that determines whether an instance of the interceptor's entity set should be returned by the query results.</span></span> <span data-ttu-id="38ab4-110">この式は、要求された操作をさらに絞り込むためにデータ サービスによって使用されます。</span><span class="sxs-lookup"><span data-stu-id="38ab4-110">This expression is used by the data service to further refine the requested operation.</span></span> <span data-ttu-id="38ab4-111">次の例は、クエリ インターセプターの定義の例を示します。</span><span class="sxs-lookup"><span data-stu-id="38ab4-111">The following is an example definition of a query interceptor.</span></span>  
  
 [!code-csharp[Astoria Northwind Service#QueryInterceptorDef](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_service/cs/northwind2.svc.cs#queryinterceptordef)]
 [!code-vb[Astoria Northwind Service#QueryInterceptorDef](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_service/vb/northwind2.svc.vb#queryinterceptordef)]  
  
 <span data-ttu-id="38ab4-112">詳細については、「[方法 :データサービスメッセージ](how-to-intercept-data-service-messages-wcf-data-services.md)をインターセプトします。</span><span class="sxs-lookup"><span data-stu-id="38ab4-112">For more information, see [How to: Intercept Data Service Messages](how-to-intercept-data-service-messages-wcf-data-services.md).</span></span>  
  
 <span data-ttu-id="38ab4-113">クエリ以外の操作を処理するときに呼び出される変更インターセプターは、`void` (Visual Basic の場合は `Nothing`) を返す必要があります。</span><span class="sxs-lookup"><span data-stu-id="38ab4-113">Change interceptors, which are called when processing non-query operations, must return `void` (`Nothing` in Visual Basic).</span></span> <span data-ttu-id="38ab4-114">変更インターセプター メソッドは、次の 2 つのパラメーターを受け取る必要があります。</span><span class="sxs-lookup"><span data-stu-id="38ab4-114">Change interceptor methods must accept the following two parameters:</span></span>  
  
1. <span data-ttu-id="38ab4-115">エンティティ セットのエンティティ型との互換性がある型のパラメーター。</span><span class="sxs-lookup"><span data-stu-id="38ab4-115">A parameter of a type that is compatible with the entity type of the entity set.</span></span> <span data-ttu-id="38ab4-116">データ サービスが変更インターセプターを呼び出すとき、このパラメーターの値には、要求によって送信されたエンティティ情報が反映されます。</span><span class="sxs-lookup"><span data-stu-id="38ab4-116">When the data service invokes the change interceptor, the value of this parameter will reflect the entity information that is sent by the request.</span></span>  
  
2. <span data-ttu-id="38ab4-117">型 <xref:System.Data.Services.UpdateOperations> のパラメーター。</span><span class="sxs-lookup"><span data-stu-id="38ab4-117">A parameter of type <xref:System.Data.Services.UpdateOperations>.</span></span> <span data-ttu-id="38ab4-118">データ サービスが変更インターセプターを呼び出すとき、このパラメーターの値には、要求が実行しようとしている操作が反映されます。</span><span class="sxs-lookup"><span data-stu-id="38ab4-118">When the data service invokes the change interceptor, the value of this parameter will reflect the operation that the request is trying to perform.</span></span>  
  
 <span data-ttu-id="38ab4-119">次の例は、変更インターセプターの定義の例を示します。</span><span class="sxs-lookup"><span data-stu-id="38ab4-119">The following is an example definition of a change interceptor.</span></span>  
  
 [!code-csharp[Astoria Northwind Service#ChangeInterceptorDef](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_service/cs/northwind2.svc.cs#changeinterceptordef)]
 [!code-vb[Astoria Northwind Service#ChangeInterceptorDef](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_service/vb/northwind2.svc.vb#changeinterceptordef)]  
  
 <span data-ttu-id="38ab4-120">詳細については、「[方法 :データサービスメッセージ](how-to-intercept-data-service-messages-wcf-data-services.md)をインターセプトします。</span><span class="sxs-lookup"><span data-stu-id="38ab4-120">For more information, see [How to: Intercept Data Service Messages](how-to-intercept-data-service-messages-wcf-data-services.md).</span></span>  
  
 <span data-ttu-id="38ab4-121">先に取得する処理には、次の属性がサポートされます。</span><span class="sxs-lookup"><span data-stu-id="38ab4-121">The following attributes are supported for interception.</span></span>  
  
 <span data-ttu-id="38ab4-122">**[QueryInterceptor(** *EntitySetName* **)]**</span><span class="sxs-lookup"><span data-stu-id="38ab4-122">**[QueryInterceptor(** *EntitySetName* **)]**</span></span>  
 <span data-ttu-id="38ab4-123">ターゲットのエンティティ セット リソースに対する HTTP GET 要求が受信されると、<xref:System.Data.Services.QueryInterceptorAttribute> 属性が適用されたメソッドが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="38ab4-123">Methods with the <xref:System.Data.Services.QueryInterceptorAttribute> attribute applied are called when an HTTP GET request is received for the targeted entity set resource.</span></span> <span data-ttu-id="38ab4-124">これらのメソッドは、常に `Expression<Func<T,bool>>` の形式のラムダ式を返す必要があります。</span><span class="sxs-lookup"><span data-stu-id="38ab4-124">These methods must always return a lambda expression in the form of `Expression<Func<T,bool>>`.</span></span>  
  
 <span data-ttu-id="38ab4-125">**[ChangeInterceptor(** *EntitySetName* **)]**</span><span class="sxs-lookup"><span data-stu-id="38ab4-125">**[ChangeInterceptor(** *EntitySetName* **)]**</span></span>  
 <span data-ttu-id="38ab4-126">ターゲットのエンティティ セット リソースに対する HTTP GET 以外の HTTP 要求が受信されると、<xref:System.Data.Services.ChangeInterceptorAttribute> 属性が適用されたメソッドが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="38ab4-126">Methods with the <xref:System.Data.Services.ChangeInterceptorAttribute> attribute applied are called when an HTTP request other than HTTP GET request is received for the targeted entity set resource.</span></span> <span data-ttu-id="38ab4-127">これらのメソッドは、常に `void` (Visual Basic の場合は `Nothing`) を返します。</span><span class="sxs-lookup"><span data-stu-id="38ab4-127">These methods must always return `void` (`Nothing` in Visual Basic).</span></span>  
  
 <span data-ttu-id="38ab4-128">詳細については、「[方法 :データサービスメッセージ](how-to-intercept-data-service-messages-wcf-data-services.md)をインターセプトします。</span><span class="sxs-lookup"><span data-stu-id="38ab4-128">For more information, see [How to: Intercept Data Service Messages](how-to-intercept-data-service-messages-wcf-data-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38ab4-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="38ab4-129">See also</span></span>

- [<span data-ttu-id="38ab4-130">サービス操作</span><span class="sxs-lookup"><span data-stu-id="38ab4-130">Service Operations</span></span>](service-operations-wcf-data-services.md)
