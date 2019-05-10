---
title: UriTemplate テーブル ディスパッチャーのサンプル
ms.date: 03/30/2017
ms.assetid: 3b32975d-ba90-4c5c-83bc-2fbb48f11c0c
ms.openlocfilehash: 4c5f7172543f575655faafad781a272e355224b6
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64662416"
---
# <a name="uritemplate-table-dispatcher-sample"></a><span data-ttu-id="7313d-102">UriTemplate テーブル ディスパッチャーのサンプル</span><span class="sxs-lookup"><span data-stu-id="7313d-102">UriTemplate Table Dispatcher Sample</span></span>
<span data-ttu-id="7313d-103"><xref:System.UriTemplateTable> クラスには、<xref:System.UriTemplate> インスタンスのセットを使用するための、ディクショナリに似た結合テーブル構造が用意されています。</span><span class="sxs-lookup"><span data-stu-id="7313d-103">The <xref:System.UriTemplateTable> class provides a dictionary-like associative table structure for working with a set of <xref:System.UriTemplate> instances.</span></span> <span data-ttu-id="7313d-104">このサンプルでは、`UriTemplateTable` クラスの一般的な使用シナリオとして、`UriTemplateTable` を使用してビルドされた基本的なディスパッチ エンジンを示します。</span><span class="sxs-lookup"><span data-stu-id="7313d-104">This sample demonstrates a basic dispatching engine built using `UriTemplateTable`, a common usage scenario for the `UriTemplateTable` class.</span></span>  
  
 <span data-ttu-id="7313d-105">このサンプルでは、次の `UriTemplateTable` クラスに関連する重要な概念を示します。</span><span class="sxs-lookup"><span data-stu-id="7313d-105">This sample demonstrates the following key concepts for the `UriTemplateTable` class:</span></span>  
  
- <span data-ttu-id="7313d-106">`UriTemplates` の `UriTemplateTable` とのデリゲートの関連付け。</span><span class="sxs-lookup"><span data-stu-id="7313d-106">Associating delegates with `UriTemplates` in a `UriTemplateTable`.</span></span>  
  
- <span data-ttu-id="7313d-107"><xref:System.UriTemplateTable.MatchSingle%2A> を使用した特定の URI の正しいハンドラ デリゲートの取得。</span><span class="sxs-lookup"><span data-stu-id="7313d-107">Using <xref:System.UriTemplateTable.MatchSingle%2A> to obtain the correct handler delegate for a particular URI.</span></span>  
  
- <span data-ttu-id="7313d-108">要求を処理するためのハンドラー デリゲートの呼び出し。</span><span class="sxs-lookup"><span data-stu-id="7313d-108">Invoking the handler delegate to process the request.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="7313d-109">サンプルをセットアップ、ビルド、および実行するには</span><span class="sxs-lookup"><span data-stu-id="7313d-109">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="7313d-110">ソリューションの C# 版または Visual Basic .NET 版をビルドするには、「 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)」の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="7313d-110">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
2. <span data-ttu-id="7313d-111">1 つまたは複数コンピュータ構成では、サンプルを実行する手順については、 [Windows Communication Foundation サンプルの実行](../../../../docs/framework/wcf/samples/running-the-samples.md)します。</span><span class="sxs-lookup"><span data-stu-id="7313d-111">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="7313d-112">サンプルは、既にコンピューターにインストールされている場合があります。</span><span class="sxs-lookup"><span data-stu-id="7313d-112">The samples may already be installed on your machine.</span></span> <span data-ttu-id="7313d-113">続行する前に、次の (既定の) ディレクトリを確認してください。</span><span class="sxs-lookup"><span data-stu-id="7313d-113">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="7313d-114">このディレクトリが存在しない場合に移動[Windows Communication Foundation (WCF) と .NET Framework 4 向けの Windows Workflow Foundation (WF) サンプル](https://go.microsoft.com/fwlink/?LinkId=150780)すべて Windows Communication Foundation (WCF) をダウンロードして[!INCLUDE[wf1](../../../../includes/wf1-md.md)]サンプル。</span><span class="sxs-lookup"><span data-stu-id="7313d-114">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="7313d-115">このサンプルは、次のディレクトリに格納されます。</span><span class="sxs-lookup"><span data-stu-id="7313d-115">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Web\UriTemplateDispatcher`  
  
## <a name="see-also"></a><span data-ttu-id="7313d-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="7313d-116">See also</span></span>

- [<span data-ttu-id="7313d-117">UriTemplate テーブル</span><span class="sxs-lookup"><span data-stu-id="7313d-117">UriTemplate Table</span></span>](../../../../docs/framework/wcf/samples/uritemplate-table-sample.md)
- [<span data-ttu-id="7313d-118">UriTemplate</span><span class="sxs-lookup"><span data-stu-id="7313d-118">UriTemplate</span></span>](../../../../docs/framework/wcf/samples/uritemplate-sample.md)
