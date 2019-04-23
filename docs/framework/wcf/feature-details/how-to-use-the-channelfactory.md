---
title: '方法: ChannelFactory を使用する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d48f01b5-582b-4c8b-b547-8adddae7e371
ms.openlocfilehash: 7d542a3dcae514e75194b49c23a8dec5dd7e8c3b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59773728"
---
# <a name="how-to-use-the-channelfactory"></a><span data-ttu-id="75a9b-102">方法: ChannelFactory を使用する</span><span class="sxs-lookup"><span data-stu-id="75a9b-102">How to: Use the ChannelFactory</span></span>
<span data-ttu-id="75a9b-103"><xref:System.ServiceModel.ChannelFactory%601> ジェネリック クラスは、複数チャネルの作成に使用できるチャネル ファクトリの作成を必要とする高度なシナリオで使用します。</span><span class="sxs-lookup"><span data-stu-id="75a9b-103">The generic <xref:System.ServiceModel.ChannelFactory%601> class is used in advanced scenarios that require the creation of a channel factory that can be used to create more than one channel.</span></span>  
  
### <a name="to-create-and-use-the-channelfactory-class"></a><span data-ttu-id="75a9b-104">ChannelFactory クラスの作成方法と使用方法</span><span class="sxs-lookup"><span data-stu-id="75a9b-104">To create and use the ChannelFactory class</span></span>  
  
1. <span data-ttu-id="75a9b-105">ビルドして、Windows Communication Foundation (WCF) サービスを実行します。</span><span class="sxs-lookup"><span data-stu-id="75a9b-105">Build and run an Windows Communication Foundation (WCF) service.</span></span> <span data-ttu-id="75a9b-106">詳細については、次を参照してください。[のデザインと実装サービス](../../../../docs/framework/wcf/designing-and-implementing-services.md)、[サービスを構成する](../../../../docs/framework/wcf/configuring-services.md)、および[ホスティング サービス](../../../../docs/framework/wcf/hosting-services.md)します。</span><span class="sxs-lookup"><span data-stu-id="75a9b-106">For more information, see [Designing and Implementing Services](../../../../docs/framework/wcf/designing-and-implementing-services.md), [Configuring Services](../../../../docs/framework/wcf/configuring-services.md), and [Hosting Services](../../../../docs/framework/wcf/hosting-services.md).</span></span>  
  
2. <span data-ttu-id="75a9b-107">使用して、 [ServiceModel メタデータ ユーティリティ ツール (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)クライアントのコントラクト (インターフェイス) を生成します。</span><span class="sxs-lookup"><span data-stu-id="75a9b-107">Use the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) to generate the contract (interface) for the client.</span></span>  
  
3. <span data-ttu-id="75a9b-108">クライアント コード内で、<xref:System.ServiceModel.ChannelFactory%601> クラスを使用して複数のエンドポイント リスナーを作成します。</span><span class="sxs-lookup"><span data-stu-id="75a9b-108">In the client code, use the <xref:System.ServiceModel.ChannelFactory%601> class to create multiple endpoint listeners.</span></span>  
  
## <a name="example"></a><span data-ttu-id="75a9b-109">例</span><span class="sxs-lookup"><span data-stu-id="75a9b-109">Example</span></span>  
 [!code-csharp[c_HowToUseChannelFactory#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howtousechannelfactory/cs/source.cs#1)]
 [!code-vb[c_HowToUseChannelFactory#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howtousechannelfactory/vb/source.vb#1)]
