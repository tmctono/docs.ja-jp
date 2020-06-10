---
title: '方法: Metadata Exchange コントラクトと共にサービス モニカーを使用する'
ms.date: 03/30/2017
ms.assetid: c41a07e5-cb9d-45d6-9ea4-34511e227faf
ms.openlocfilehash: 04a940a6e8f010e5cd851684c5fc62bab2a1a034
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84601167"
---
# <a name="how-to-use-a-service-moniker-with-metadata-exchange-contracts"></a><span data-ttu-id="e5723-102">方法: Metadata Exchange コントラクトと共にサービス モニカーを使用する</span><span class="sxs-lookup"><span data-stu-id="e5723-102">How to: Use a Service Moniker with Metadata Exchange Contracts</span></span>
<span data-ttu-id="e5723-103">新しい WCF サービスを開発した後、これらのサービスをスクリプトまたは Visual Basic 6.0 アプリケーションから呼び出すことができるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="e5723-103">After developing some new WCF services, you may decide that you want to be able to call these services from a script or a Visual Basic 6.0 application.</span></span> <span data-ttu-id="e5723-104">1つの方法として、WCF クライアントアセンブリを生成し、アセンブリを COM に登録し、アセンブリを GAC にインストールしてから、Visual Basic コードから COM 型を参照する方法があります。</span><span class="sxs-lookup"><span data-stu-id="e5723-104">One method would be to generate a WCF client assembly, register the assembly with COM, install the assembly in the GAC, and then reference the COM types from your Visual Basic code.</span></span> <span data-ttu-id="e5723-105">アプリケーションを配布する場合は、WCF クライアントアセンブリも配布する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e5723-105">When you distribute the application, you will have to distribute the WCF Client assembly as well.</span></span> <span data-ttu-id="e5723-106">次にユーザーは COM を使用して WCF クライアント アセンブリを登録し、それを GAC に配置する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e5723-106">The user will then have to register the WCF client assembly with COM and place it in the GAC.</span></span> <span data-ttu-id="e5723-107">WCF COM 相互運用機能を使用すると、WCF クライアントアセンブリに依存することなく、同じサービス呼び出しを行うこともできます。</span><span class="sxs-lookup"><span data-stu-id="e5723-107">WCF COM Interop also allows you to make the same service calls without relying on a WCF client assembly.</span></span> <span data-ttu-id="e5723-108">WCF モニカーを使用すると、サービスモニカーがサービスに関する型情報を抽出するために使用する metadata exchange (Mex) エンドポイント URI を指定することで、任意の COM 互換言語 (Visual Basic、VBScript、Visual Basic for Applications (VBA) など) から任意の WCF サービスを呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="e5723-108">The WCF moniker allows you to call any WCF service from any COM-compatible language (Visual Basic, VBScript, Visual Basic for Applications (VBA), and so on) by specifying a metadata exchange (Mex) endpoint URI that the service moniker uses to extract type information about the service.</span></span> <span data-ttu-id="e5723-109">このトピックでは、Mex エンドポイントを指定する WCF モニカーを使用してはじめに WCF サンプルを呼び出す方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="e5723-109">This topic describes how to call the Getting Started WCF sample using a WCF moniker that specifies a Mex endpoint.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e5723-110">WCF クライアントアセンブリによって定義された型は、実際にはインスタンス化されません。</span><span class="sxs-lookup"><span data-stu-id="e5723-110">The types defined by the WCF client assembly are never actually instantiated.</span></span> <span data-ttu-id="e5723-111">アセンブリはメタデータにのみ使用されます。</span><span class="sxs-lookup"><span data-stu-id="e5723-111">The assembly is used only for metadata.</span></span>  
  
### <a name="using-the-service-moniker-with-a-mex-address"></a><span data-ttu-id="e5723-112">Mex アドレスを使うサービス モニカーの使用</span><span class="sxs-lookup"><span data-stu-id="e5723-112">Using the service moniker with a Mex address</span></span>  
  
1. <span data-ttu-id="e5723-113">はじめにサンプルをビルドし、Internet Explorer を使用してその URL () を参照し `http://localhost/ServiceModelSamples/Service.svc` 、サービスが動作していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="e5723-113">Build the Getting Started sample and use Internet Explorer to browse to its URL (`http://localhost/ServiceModelSamples/Service.svc`) to ensure that the service is working.</span></span>  
  
2. <span data-ttu-id="e5723-114">Visual Basic スクリプトまたは Visual Basic アプリケーションを作成し、次のコードを記述します。</span><span class="sxs-lookup"><span data-stu-id="e5723-114">Create a Visual Basic script or Visual Basic application that contains the following code:</span></span>  
  
    ```vb
    monString = "service:mexaddress=http://localhost/ServiceModelSamples/Service.svc/MEX"  
    monString = monString + ", address=http://localhost/ServiceModelSamples/Service.svc"  
    monString = monString + ", contract=ICalculator, contractNamespace=http://Microsoft.ServiceModel.Samples"  
    monString = monString + ", binding=WSHttpBinding_ICalculator, bindingNamespace=http://Microsoft.ServiceModel.Samples"  
  
    Set calc = GetObject(monString)  
    MsgBox calc.Add(3, 4)  
    ```  
  
3. <span data-ttu-id="e5723-115">作成した Visual Basic アプリケーションまたはスクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="e5723-115">Run the Visual Basic application or script.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="e5723-116">モニカーがサービスのメタデータを読み取るには、呼び出すサービスで、Mex エンドポイントが公開されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="e5723-116">The service you are calling must expose a Mex endpoint for the moniker to be able to read the metadata from the service.</span></span> <span data-ttu-id="e5723-117">詳細については、「[方法: 構成ファイルを使用してサービスのメタデータを公開](how-to-publish-metadata-for-a-service-using-a-configuration-file.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e5723-117">For more information, see [How to: Publish Metadata for a Service Using a Configuration File](how-to-publish-metadata-for-a-service-using-a-configuration-file.md).</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="e5723-118">モニカーの形式が正しくないか、`GetObject` を呼び出せない場合は、"構文が無効です" というメッセージが返されます。</span><span class="sxs-lookup"><span data-stu-id="e5723-118">If the moniker is malformed or if the service is unavailable, the call to `GetObject` will return an error saying "Invalid Syntax."</span></span>  <span data-ttu-id="e5723-119">このエラーが発生した場合は、使用しているモニカーが正しく、サービスが使用可能であることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="e5723-119">If you receive this error, make sure the moniker you are using is correct and the service is available.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5723-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="e5723-120">See also</span></span>

- [<span data-ttu-id="e5723-121">方法: 未登録で Windows Communication Foundation のサービス モニカーを使用する</span><span class="sxs-lookup"><span data-stu-id="e5723-121">How to: Use the Windows Communication Foundation Service Moniker without Registration</span></span>](use-the-wcf-service-moniker-without-registration.md)
- [<span data-ttu-id="e5723-122">方法: WSDL コントラクトと共にサービス モニカーを使用する</span><span class="sxs-lookup"><span data-stu-id="e5723-122">How to: Use a Service Moniker with WSDL Contracts</span></span>](how-to-use-a-service-moniker-with-wsdl-contracts.md)
