---
title: '方法: Svcutil.exe を使用してコンパイル済みサービス コードを検証する'
ms.date: 03/30/2017
ms.assetid: d0d820fb-41c2-45b8-8f22-0fa5aeebbbaa
ms.openlocfilehash: 599f5624b7eb0c32cbcc0a78e6c7f989ce470b58
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62038754"
---
# <a name="how-to-use-svcutilexe-to-validate-compiled-service-code"></a><span data-ttu-id="40892-102">方法: Svcutil.exe を使用してコンパイル済みサービス コードを検証する</span><span class="sxs-lookup"><span data-stu-id="40892-102">How to: Use Svcutil.exe to Validate Compiled Service Code</span></span>
<span data-ttu-id="40892-103">使用することができます、 [ServiceModel メタデータ ユーティリティ ツール (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)サービスをホストせず、サービス実装と構成でエラーを検出します。</span><span class="sxs-lookup"><span data-stu-id="40892-103">You can use the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) to detect errors in service implementations and configurations without hosting the service.</span></span>  
  
### <a name="to-validate-a-service"></a><span data-ttu-id="40892-104">サービスを検証するには</span><span class="sxs-lookup"><span data-stu-id="40892-104">To validate a service</span></span>  
  
1. <span data-ttu-id="40892-105">サービスを実行可能ファイルおよび 1 つ以上の依存アセンブリにコンパイルします。</span><span class="sxs-lookup"><span data-stu-id="40892-105">Compile your service into an executable file and one or more dependent assemblies.</span></span>  
  
2. <span data-ttu-id="40892-106">SDK コマンド プロンプトを開きます。</span><span class="sxs-lookup"><span data-stu-id="40892-106">Open an SDK command prompt</span></span>  
  
3. <span data-ttu-id="40892-107">コマンド プロンプトで、次の形式を使用して Svcutil.exe ツールを起動します。</span><span class="sxs-lookup"><span data-stu-id="40892-107">At the command prompt, launch the Svcutil.exe tool using the following format.</span></span> <span data-ttu-id="40892-108">さまざまなパラメーターの詳細については、の「サービスの検証を参照してください、 [ServiceModel メタデータ ユーティリティ ツール (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)トピック。</span><span class="sxs-lookup"><span data-stu-id="40892-108">For more information on the various parameters, see the Service Validationsection of the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) topic.</span></span>  
  
    ```  
    svcutil.exe /validate /serviceName:<serviceConfigName>  <assemblyPath>*  
    ```  
  
     <span data-ttu-id="40892-109">`/serviceName` オプションを使用して、検証するサービスの構成名を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="40892-109">You must use the `/serviceName` option to indicate the configuration name of the service you want to validate.</span></span>  
  
     <span data-ttu-id="40892-110">`assemblyPath` 引数には、検証対象のサービスの実行可能ファイルへのパス、およびサービス型を格納している 1 つ以上のアセンブリへのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="40892-110">The `assemblyPath` argument specifies the path to the executable file for the service and one or more assemblies that contain the service types to be validated.</span></span> <span data-ttu-id="40892-111">実行可能アセンブリに、サービス構成を提供する関連構成ファイルが存在している必要があります。</span><span class="sxs-lookup"><span data-stu-id="40892-111">The executable assembly must have an associated configuration file to provide the service configuration.</span></span> <span data-ttu-id="40892-112">標準のコマンドライン ワイルドカードを使用して、複数のアセンブリを指定できます。</span><span class="sxs-lookup"><span data-stu-id="40892-112">You can use standard command-line wildcards to provide multiple assemblies.</span></span>  
  
## <a name="example"></a><span data-ttu-id="40892-113">例</span><span class="sxs-lookup"><span data-stu-id="40892-113">Example</span></span>  
 <span data-ttu-id="40892-114">次のコマンドでは、myServiceHost.exe 実行可能ファイルに実装されたサービス myServiceName を検証します。</span><span class="sxs-lookup"><span data-stu-id="40892-114">The following command the service myServiceName implemented in the myServiceHost.exe executable file.</span></span>  <span data-ttu-id="40892-115">サービスの構成ファイル (myServiceHost.exe.config) は自動的に読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="40892-115">The configuration file for the service (myServiceHost.exe.config) is automatically loaded.</span></span>  
  
```  
svcutil /validate /serviceName:myServiceName myServiceHost.exe  
```  
  
## <a name="see-also"></a><span data-ttu-id="40892-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="40892-116">See also</span></span>

- [<span data-ttu-id="40892-117">ServiceModel メタデータ ユーティリティ ツール (Svcutil.exe)</span><span class="sxs-lookup"><span data-stu-id="40892-117">ServiceModel Metadata Utility Tool (Svcutil.exe)</span></span>](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)
