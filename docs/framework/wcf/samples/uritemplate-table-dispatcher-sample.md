---
title: UriTemplate テーブル ディスパッチャーのサンプル
ms.date: 03/30/2017
ms.assetid: 3b32975d-ba90-4c5c-83bc-2fbb48f11c0c
ms.openlocfilehash: aa4259f8c823bebf38b9689df92c45992cb55723
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79143682"
---
# <a name="uritemplate-table-dispatcher-sample"></a><span data-ttu-id="2d21c-102">UriTemplate テーブル ディスパッチャーのサンプル</span><span class="sxs-lookup"><span data-stu-id="2d21c-102">UriTemplate Table Dispatcher Sample</span></span>
<span data-ttu-id="2d21c-103"><xref:System.UriTemplateTable> クラスには、<xref:System.UriTemplate> インスタンスのセットを使用するための、ディクショナリに似た結合テーブル構造が用意されています。</span><span class="sxs-lookup"><span data-stu-id="2d21c-103">The <xref:System.UriTemplateTable> class provides a dictionary-like associative table structure for working with a set of <xref:System.UriTemplate> instances.</span></span> <span data-ttu-id="2d21c-104">このサンプルでは、`UriTemplateTable` クラスの一般的な使用シナリオとして、`UriTemplateTable` を使用してビルドされた基本的なディスパッチ エンジンを示します。</span><span class="sxs-lookup"><span data-stu-id="2d21c-104">This sample demonstrates a basic dispatching engine built using `UriTemplateTable`, a common usage scenario for the `UriTemplateTable` class.</span></span>  
  
 <span data-ttu-id="2d21c-105">このサンプルでは、次の `UriTemplateTable` クラスに関連する重要な概念を示します。</span><span class="sxs-lookup"><span data-stu-id="2d21c-105">This sample demonstrates the following key concepts for the `UriTemplateTable` class:</span></span>  
  
- <span data-ttu-id="2d21c-106">`UriTemplates` の `UriTemplateTable` とのデリゲートの関連付け。</span><span class="sxs-lookup"><span data-stu-id="2d21c-106">Associating delegates with `UriTemplates` in a `UriTemplateTable`.</span></span>  
  
- <span data-ttu-id="2d21c-107"><xref:System.UriTemplateTable.MatchSingle%2A> を使用した特定の URI の正しいハンドラ デリゲートの取得。</span><span class="sxs-lookup"><span data-stu-id="2d21c-107">Using <xref:System.UriTemplateTable.MatchSingle%2A> to obtain the correct handler delegate for a particular URI.</span></span>  
  
- <span data-ttu-id="2d21c-108">要求を処理するためのハンドラー デリゲートの呼び出し。</span><span class="sxs-lookup"><span data-stu-id="2d21c-108">Invoking the handler delegate to process the request.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="2d21c-109">サンプルをセットアップ、ビルド、および実行するには</span><span class="sxs-lookup"><span data-stu-id="2d21c-109">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="2d21c-110">ソリューションの C# 版または Visual Basic .NET 版をビルドするには、「 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)」の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="2d21c-110">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
2. <span data-ttu-id="2d21c-111">単一または複数のコンピューターにまたがる構成でサンプルを実行するには[、「Windows コミュニケーション ファウンデーション サンプルの実行」の手順に](../../../../docs/framework/wcf/samples/running-the-samples.md)従います。</span><span class="sxs-lookup"><span data-stu-id="2d21c-111">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="2d21c-112">サンプルは、既にコンピューターにインストールされている場合があります。</span><span class="sxs-lookup"><span data-stu-id="2d21c-112">The samples may already be installed on your machine.</span></span> <span data-ttu-id="2d21c-113">続行する前に、次の (既定の) ディレクトリを確認してください。</span><span class="sxs-lookup"><span data-stu-id="2d21c-113">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="2d21c-114">このディレクトリが存在しない場合は[、.NET Framework 4 の Windows コミュニケーション ファウンデーション (WCF) および Windows ワークフローファウンデーション (WF) サンプル](https://www.microsoft.com/download/details.aspx?id=21459)に移動して、すべての Windows 通信基盤 (WCF) とサンプルを[!INCLUDE[wf1](../../../../includes/wf1-md.md)]ダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="2d21c-114">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="2d21c-115">このサンプルは、次のディレクトリに格納されます。</span><span class="sxs-lookup"><span data-stu-id="2d21c-115">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Web\UriTemplateDispatcher`  
  
## <a name="see-also"></a><span data-ttu-id="2d21c-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="2d21c-116">See also</span></span>

- [<span data-ttu-id="2d21c-117">UriTemplate テーブル</span><span class="sxs-lookup"><span data-stu-id="2d21c-117">UriTemplate Table</span></span>](../../../../docs/framework/wcf/samples/uritemplate-table-sample.md)
- [<span data-ttu-id="2d21c-118">ウリテンプレート</span><span class="sxs-lookup"><span data-stu-id="2d21c-118">UriTemplate</span></span>](../../../../docs/framework/wcf/samples/uritemplate-sample.md)
