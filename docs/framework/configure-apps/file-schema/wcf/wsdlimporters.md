---
title: <wsdlImporters>
ms.date: 03/30/2017
ms.assetid: 270c7f93-eab7-47b6-8b94-ac3f5b7f17e4
ms.openlocfilehash: 75f88219ab73d321b3e04c140bbfe964aed0b83a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61785477"
---
# <a name="wsdlimporters"></a><span data-ttu-id="0250f-101">\<wsdlImporters></span><span class="sxs-lookup"><span data-stu-id="0250f-101">\<wsdlImporters></span></span>
<span data-ttu-id="0250f-102">この構成要素は、WS-Policy が添付された Web サービス記述言語 (WSDL) 1.1 メタデータをインポートするすべての WSDL インポートを指定します。</span><span class="sxs-lookup"><span data-stu-id="0250f-102">This configuration element specifies all the WSDL importers that imports Web Services Description Language (WSDL) 1.1 metadata with WS-Policy attachments.</span></span> <span data-ttu-id="0250f-103">各子要素は、<`wsdlImporter`> メタデータをインポート、その情報をコントラクトおよびエンドポイント情報を表すさまざまなクラスに変換する方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="0250f-103">Each child element is a <`wsdlImporter`> that specifies the way to import metadata as well as convert that information into various classes that represent contract and endpoint information.</span></span> <span data-ttu-id="0250f-104">コントラクトおよびエンドポイントの情報やプロパティを選択的にインポートできます。これらは、任意のインポート エラーを公開し、インポートおよび変換プロセスに関連する型情報を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="0250f-104">It can selectively import contract and endpoint information and properties that expose any import errors and accept type information relevant to the import and conversion process.</span></span> <span data-ttu-id="0250f-105">また、任意のポリシー ドキュメント、WSDL ドキュメント、WSDL 拡張、および XML スキーマ ドキュメントにアクセスするためのバインディング情報およびプロパティのインポートもサポートします。</span><span class="sxs-lookup"><span data-stu-id="0250f-105">It also supports importing binding information and properties that provide access to any policy documents, WSDL documents, WSDL extensions, and XML schema documents.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0250f-106">関連項目</span><span class="sxs-lookup"><span data-stu-id="0250f-106">See also</span></span>

- <xref:System.ServiceModel.Configuration.MetadataElement>
- <xref:System.ServiceModel.Configuration.WsdlImporterElementCollection>
- <xref:System.ServiceModel.Description.MetadataImporter>
- <xref:System.ServiceModel.Description.WsdlImporter>
- [<span data-ttu-id="0250f-107">WCF クライアントの構成</span><span class="sxs-lookup"><span data-stu-id="0250f-107">WCF Client Configuration</span></span>](../../../../../docs/framework/wcf/feature-details/client-configuration.md)
- [<span data-ttu-id="0250f-108">クライアント</span><span class="sxs-lookup"><span data-stu-id="0250f-108">Clients</span></span>](../../../../../docs/framework/wcf/feature-details/clients.md)
