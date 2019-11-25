---
title: WCF Web HTTP エラー処理
ms.date: 03/30/2017
ms.assetid: 02891563-0fce-4c32-84dc-d794b1a5c040
ms.openlocfilehash: 34912bccaefb645541f47d083c5c307b20ff77c5
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/12/2019
ms.locfileid: "73975956"
---
# <a name="wcf-web-http-error-handling"></a><span data-ttu-id="af9c2-102">WCF Web HTTP エラー処理</span><span class="sxs-lookup"><span data-stu-id="af9c2-102">WCF Web HTTP Error Handling</span></span>
<span data-ttu-id="af9c2-103">Windows Communication Foundation (WCF) Web HTTP エラー処理を使用すると、HTTP 状態コードを指定し、操作と同じ形式 (XML、JSON など) を使用してエラーの詳細を返す WCF Web HTTP サービスからエラーを返すことができます。</span><span class="sxs-lookup"><span data-stu-id="af9c2-103">Windows Communication Foundation (WCF) Web HTTP error handling enables you to return errors from WCF Web HTTP services that specify an HTTP status code and return error details using the same format as the operation (for example, XML or JSON).</span></span>  
  
## <a name="wcf-web-http-error-handling"></a><span data-ttu-id="af9c2-104">WCF Web HTTP エラー処理</span><span class="sxs-lookup"><span data-stu-id="af9c2-104">WCF Web HTTP Error Handling</span></span>  
 <span data-ttu-id="af9c2-105"><xref:System.ServiceModel.Web.WebFaultException> クラスは、HTTP 状態コードを指定できるようにするコンストラクターを定義します。</span><span class="sxs-lookup"><span data-stu-id="af9c2-105">The <xref:System.ServiceModel.Web.WebFaultException> class defines a constructor that allows you to specify an HTTP status code.</span></span> <span data-ttu-id="af9c2-106">この状態コードは、クライアントに返されます。</span><span class="sxs-lookup"><span data-stu-id="af9c2-106">This status code is then returned to the client.</span></span> <span data-ttu-id="af9c2-107"><xref:System.ServiceModel.Web.WebFaultException> クラスのジェネリック バージョンである <xref:System.ServiceModel.Web.WebFaultException%601> を使用すると、発生したエラーに関する情報を格納しているユーザー定義型を返すことができます。</span><span class="sxs-lookup"><span data-stu-id="af9c2-107">A generic version of the <xref:System.ServiceModel.Web.WebFaultException> class, <xref:System.ServiceModel.Web.WebFaultException%601> enables you to return a user-defined type that contains information about the error that occurred.</span></span> <span data-ttu-id="af9c2-108">このカスタム オブジェクトは、操作で定義された形式を使用してシリアル化され、クライアントに返されます。</span><span class="sxs-lookup"><span data-stu-id="af9c2-108">This custom object is serialized using the format specified by the operation and returned to the client.</span></span> <span data-ttu-id="af9c2-109">次の例は、HTTP 状態コードを返す方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="af9c2-109">The following example shows how to return an HTTP status code.</span></span>  
  
```csharp
public string Operation1()
{
    // Operation logic  
   // ...
   throw new WebFaultException(HttpStatusCode.Forbidden);
}  
```  
  
 <span data-ttu-id="af9c2-110">次の例は、HTTP 状態コードおよび追加情報をユーザー定義型で返す方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="af9c2-110">The following example shows how to return an HTTP status code and extra information in a user-defined type.</span></span> <span data-ttu-id="af9c2-111">`MyErrorDetail` は、発生したエラーに関する追加情報を格納しているユーザー定義型です。</span><span class="sxs-lookup"><span data-stu-id="af9c2-111">`MyErrorDetail` is a user-defined type that contains extra information about the error that occurred.</span></span>  
  
```csharp
public string Operation2()
{
   // Operation logic  
   // ...
   MyErrorDetail detail = new MyErrorDetail()
   {  
      Message = "Error Message",  
      ErrorCode = 123,  
   }  
   throw new WebFaultException<MyErrorDetail>(detail, HttpStatusCode.Forbidden);  
}  
```  
  
 <span data-ttu-id="af9c2-112">このコードは、禁止されている状態コード、および `MyErrorDetails` オブジェクトのインスタンスを格納している本文と共に、HTTP 応答を返します。</span><span class="sxs-lookup"><span data-stu-id="af9c2-112">The preceding code returns an HTTP response with the forbidden status code and a body that contains an instance of the `MyErrorDetails` object.</span></span> <span data-ttu-id="af9c2-113">`MyErrorDetails` オブジェクトの形式は、次の値によって決まります。</span><span class="sxs-lookup"><span data-stu-id="af9c2-113">The format of the `MyErrorDetails` object is determined by:</span></span>  
  
- <span data-ttu-id="af9c2-114">サービス操作で指定された `ResponseFormat` 属性または <xref:System.ServiceModel.Web.WebGetAttribute> 属性の <xref:System.ServiceModel.Web.WebInvokeAttribute> パラメーターの値。</span><span class="sxs-lookup"><span data-stu-id="af9c2-114">The value of the `ResponseFormat` parameter of the <xref:System.ServiceModel.Web.WebGetAttribute> or <xref:System.ServiceModel.Web.WebInvokeAttribute> attribute specified on the service operation.</span></span>  
  
- <span data-ttu-id="af9c2-115"><xref:System.ServiceModel.Description.WebHttpBehavior.AutomaticFormatSelectionEnabled%2A> の値。</span><span class="sxs-lookup"><span data-stu-id="af9c2-115">The value of <xref:System.ServiceModel.Description.WebHttpBehavior.AutomaticFormatSelectionEnabled%2A>.</span></span>  
  
- <span data-ttu-id="af9c2-116"><xref:System.ServiceModel.Web.OutgoingWebResponseContext.Format%2A> プロパティの値 (<xref:System.ServiceModel.Web.OutgoingWebResponseContext> にアクセスして取得)。</span><span class="sxs-lookup"><span data-stu-id="af9c2-116">The value of the <xref:System.ServiceModel.Web.OutgoingWebResponseContext.Format%2A> property by accessing the <xref:System.ServiceModel.Web.OutgoingWebResponseContext>.</span></span>  
  
 <span data-ttu-id="af9c2-117">これらの値が操作の書式設定に与える影響の詳細については、「 [WCF WEB HTTP 書式設定](../../../../docs/framework/wcf/feature-details/wcf-web-http-formatting.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="af9c2-117">For more information about how these values affect the formatting of the operation, see [WCF Web HTTP Formatting](../../../../docs/framework/wcf/feature-details/wcf-web-http-formatting.md).</span></span>  
  
 <span data-ttu-id="af9c2-118"><xref:System.ServiceModel.Web.WebFaultException> は <xref:System.ServiceModel.FaultException> であるため、SOAP エンドポイントと Web HTTP エンドポイントを公開するサービスのエラー例外プログラミング モデルとして使用できます。</span><span class="sxs-lookup"><span data-stu-id="af9c2-118"><xref:System.ServiceModel.Web.WebFaultException> is a <xref:System.ServiceModel.FaultException> and therefore can be used as the fault exception programming model for services that expose SOAP endpoints as well as web HTTP endpoints.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af9c2-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="af9c2-119">See also</span></span>

- [<span data-ttu-id="af9c2-120">WCF Web HTTP プログラミング モデル</span><span class="sxs-lookup"><span data-stu-id="af9c2-120">WCF Web HTTP Programming Model</span></span>](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)
- [<span data-ttu-id="af9c2-121">WCF Web HTTP 形式</span><span class="sxs-lookup"><span data-stu-id="af9c2-121">WCF Web HTTP Formatting</span></span>](../../../../docs/framework/wcf/feature-details/wcf-web-http-formatting.md)
- [<span data-ttu-id="af9c2-122">エラーの定義と指定</span><span class="sxs-lookup"><span data-stu-id="af9c2-122">Defining and Specifying Faults</span></span>](../../../../docs/framework/wcf/defining-and-specifying-faults.md)
- [<span data-ttu-id="af9c2-123">例外とエラーの処理</span><span class="sxs-lookup"><span data-stu-id="af9c2-123">Handling Exceptions and Faults</span></span>](../../../../docs/framework/wcf/extending/handling-exceptions-and-faults.md)
- [<span data-ttu-id="af9c2-124">エラーの送受信</span><span class="sxs-lookup"><span data-stu-id="af9c2-124">Sending and Receiving Faults</span></span>](../../../../docs/framework/wcf/sending-and-receiving-faults.md)
