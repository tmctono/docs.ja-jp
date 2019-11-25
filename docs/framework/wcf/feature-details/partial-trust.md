---
title: 部分信頼
ms.date: 03/30/2017
ms.assetid: 489b1587-9909-4d0e-8c1a-5e83c8f8292b
ms.openlocfilehash: fa496718d6c2a7f725c880d932c48d0f5d4bb7a4
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283323"
---
# <a name="partial-trust"></a><span data-ttu-id="51ed9-102">部分信頼</span><span class="sxs-lookup"><span data-stu-id="51ed9-102">Partial Trust</span></span>

<span data-ttu-id="51ed9-103">.NET Framework 3.5 以降では、部分的に信頼された呼び出し元は、<xref:System.ServiceModel>、<xref:System.Runtime.Serialization>、および <xref:System.ServiceModel.Web>で実装されているパブリック型とメソッドにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="51ed9-103">Starting with the .NET Framework 3.5, partially trusted callers can access public types and methods implemented in <xref:System.ServiceModel>, <xref:System.Runtime.Serialization>, and <xref:System.ServiceModel.Web>.</span></span> <span data-ttu-id="51ed9-104">このセクションでは、部分的に信頼されたアプリケーション内で Windows Communication Foundation (WCF) を使用するためのサポートされるシナリオと、コードアクセスセキュリティ (CAS) が制限されたを実行するアプリケーションで使用できる WCF 機能の限られたサブセットについて説明します。許可.</span><span class="sxs-lookup"><span data-stu-id="51ed9-104">This section describes supported scenarios for using Windows Communication Foundation (WCF) within a partially trusted application as well as the limited subset of WCF functionality available to applications running with reduced code access security (CAS) permissions.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="51ed9-105">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="51ed9-105">In This Section</span></span>  
 [<span data-ttu-id="51ed9-106">サポートされている配置シナリオ</span><span class="sxs-lookup"><span data-stu-id="51ed9-106">Supported Deployment Scenarios</span></span>](../../../../docs/framework/wcf/feature-details/supported-deployment-scenarios.md)  
 <span data-ttu-id="51ed9-107">WCF を実行するための主な部分信頼のシナリオについて説明します。</span><span class="sxs-lookup"><span data-stu-id="51ed9-107">Describes the main partial trust scenarios for running WCF.</span></span>  
  
 [<span data-ttu-id="51ed9-108">部分信頼機能の互換性</span><span class="sxs-lookup"><span data-stu-id="51ed9-108">Partial Trust Feature Compatibility</span></span>](../../../../docs/framework/wcf/feature-details/partial-trust-feature-compatibility.md)  
 <span data-ttu-id="51ed9-109">部分信頼で使用できない WCF 機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="51ed9-109">Describes the WCF features that cannot be used with partial trust.</span></span>  
  
 [<span data-ttu-id="51ed9-110">T:System.Runtime.Serialization.DataContractSerializer</span><span class="sxs-lookup"><span data-stu-id="51ed9-110">Partial Trust Best Practices</span></span>](../../../../docs/framework/wcf/feature-details/partial-trust-best-practices.md)  
 <span data-ttu-id="51ed9-111">部分的に信頼されたアプリケーションで WCF を使用するためのベストプラクティスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="51ed9-111">Contains best practices for using WCF in partially trusted applications.</span></span>
