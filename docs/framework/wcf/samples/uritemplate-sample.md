---
title: UriTemplate サンプル
ms.date: 03/30/2017
ms.assetid: 0aaf91d0-ce18-468d-8006-bc9bc2e48231
ms.openlocfilehash: e08333235b22e3c24fc6f4855fec43ef8b95fa5a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79183267"
---
# <a name="uritemplate-sample"></a><span data-ttu-id="bc21a-102">UriTemplate サンプル</span><span class="sxs-lookup"><span data-stu-id="bc21a-102">UriTemplate Sample</span></span>
<span data-ttu-id="bc21a-103"><xref:System.UriTemplate> クラスには、共通構造を共有する URI のセットを使用するためのメソッドが用意されています。</span><span class="sxs-lookup"><span data-stu-id="bc21a-103">The <xref:System.UriTemplate> class provides methods for working with sets of URIs that share a common structure.</span></span> <span data-ttu-id="bc21a-104">このサンプルでは、次の `UriTemplate` に関連する重要な概念を示します。</span><span class="sxs-lookup"><span data-stu-id="bc21a-104">This sample demonstrates the following key concepts relating to `UriTemplate`:</span></span>  
  
- <span data-ttu-id="bc21a-105">テンプレートを作成するための構文</span><span class="sxs-lookup"><span data-stu-id="bc21a-105">Syntax for creating templates.</span></span>  
  
- <span data-ttu-id="bc21a-106">`UriTemplate` および <xref:System.UriTemplate.BindByName%2A> を使用した、<xref:System.UriTemplate.BindByPosition%2A> からの URI のインスタンス化</span><span class="sxs-lookup"><span data-stu-id="bc21a-106">Instantiating URIs from a `UriTemplate` using <xref:System.UriTemplate.BindByName%2A> and <xref:System.UriTemplate.BindByPosition%2A>.</span></span>  
  
- <span data-ttu-id="bc21a-107"><xref:System.UriTemplateTable.Match%2A> および `BindByName` の逆の操作である `BindByPosition`</span><span class="sxs-lookup"><span data-stu-id="bc21a-107"><xref:System.UriTemplateTable.Match%2A>, which is the inverse operation of `BindByName` and `BindByPosition`.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="bc21a-108">サンプルをセットアップ、ビルド、および実行するには</span><span class="sxs-lookup"><span data-stu-id="bc21a-108">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="bc21a-109">ソリューションの C# 版または Visual Basic .NET 版をビルドするには、「 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)」の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="bc21a-109">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
2. <span data-ttu-id="bc21a-110">単一または複数のコンピューターにまたがる構成でサンプルを実行するには[、「Windows コミュニケーション ファウンデーション サンプルの実行」の手順に](../../../../docs/framework/wcf/samples/running-the-samples.md)従います。</span><span class="sxs-lookup"><span data-stu-id="bc21a-110">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="bc21a-111">サンプルは、既にコンピューターにインストールされている場合があります。</span><span class="sxs-lookup"><span data-stu-id="bc21a-111">The samples may already be installed on your computer.</span></span> <span data-ttu-id="bc21a-112">続行する前に、次の (既定の) ディレクトリを確認してください。</span><span class="sxs-lookup"><span data-stu-id="bc21a-112">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="bc21a-113">このディレクトリが存在しない場合は[、.NET Framework 4 の Windows コミュニケーション ファウンデーション (WCF) および Windows ワークフローファウンデーション (WF) サンプル](https://www.microsoft.com/download/details.aspx?id=21459)に移動して、すべての Windows 通信基盤 (WCF) とサンプルを[!INCLUDE[wf1](../../../../includes/wf1-md.md)]ダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="bc21a-113">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="bc21a-114">このサンプルは、次のディレクトリに格納されます。</span><span class="sxs-lookup"><span data-stu-id="bc21a-114">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Web\UriTemplate`  
  
## <a name="see-also"></a><span data-ttu-id="bc21a-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="bc21a-115">See also</span></span>

- [<span data-ttu-id="bc21a-116">UriTemplate テーブル</span><span class="sxs-lookup"><span data-stu-id="bc21a-116">UriTemplate Table</span></span>](../../../../docs/framework/wcf/samples/uritemplate-table-sample.md)
- [<span data-ttu-id="bc21a-117">UriTemplate テーブル ディスパッチャー</span><span class="sxs-lookup"><span data-stu-id="bc21a-117">UriTemplate Table Dispatcher</span></span>](../../../../docs/framework/wcf/samples/uritemplate-table-dispatcher-sample.md)
