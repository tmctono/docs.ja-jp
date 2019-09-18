---
title: WIF API リファレンス
ms.date: 03/30/2017
ms.assetid: a027d902-9314-4bfd-b172-4e81847b1d68
author: BrucePerlerMS
ms.openlocfilehash: fd7f34e619626ddca63074a89ec7253fd818ab55
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2019
ms.locfileid: "71045150"
---
# <a name="wif-api-reference"></a><span data-ttu-id="353e1-102">WIF API リファレンス</span><span class="sxs-lookup"><span data-stu-id="353e1-102">WIF API Reference</span></span>
<span data-ttu-id="353e1-103">Windows Identity Foundation (WIF) クラスは、`mscorlib` (mscorlib.dll)、`System.IdentityModel` (System.IdentityModel.dll)、`System.IdentityModel.Services` (System.IdentityModel.Services.dll)、および `System.ServiceModel` (System.ServiceModel.dll) というアセンブリに分割されています。</span><span class="sxs-lookup"><span data-stu-id="353e1-103">Windows Identity Foundation (WIF) classes are split across the following assemblies: `mscorlib` (mscorlib.dll), `System.IdentityModel` (System.IdentityModel.dll), `System.IdentityModel.Services` (System.IdentityModel.Services.dll), and `System.ServiceModel` (System.ServiceModel.dll).</span></span> <span data-ttu-id="353e1-104">このトピックでは、WIF 名前空間のリンクを紹介し、各名前空間に含まれるクラスについて簡単に説明します。</span><span class="sxs-lookup"><span data-stu-id="353e1-104">This topic provides links to the WIF namespaces and brief explanations of the classes that each namespace contains.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="353e1-105">`System.IdentityModel`、<xref:System.IdentityModel.Claims?displayProperty=nameWithType>、および <xref:System.IdentityModel.Policy?displayProperty=nameWithType> という <xref:System.IdentityModel.Selectors?displayProperty=nameWithType> 名前空間には、WCF クレーム ベースの ID モデルを実装するクラスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="353e1-105">The following `System.IdentityModel` namespaces contain classes that implement the WCF claims-based identity model: <xref:System.IdentityModel.Claims?displayProperty=nameWithType>, <xref:System.IdentityModel.Policy?displayProperty=nameWithType>, and <xref:System.IdentityModel.Selectors?displayProperty=nameWithType>.</span></span> <span data-ttu-id="353e1-106">.NET Framework 4.5 以降、WCF クレーム ベース ID モデルは WIF に置き換えられています。</span><span class="sxs-lookup"><span data-stu-id="353e1-106">Starting with .NET Framework 4.5, the WCF claims-based identity model is superseded by WIF.</span></span> <span data-ttu-id="353e1-107">WIF に基づいてソリューションをビルドする際は、これら 3 つの名前空間でクラスを使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="353e1-107">You should not use classes in these three namespaces when building solutions based on WIF.</span></span>  
  
 <xref:System.IdentityModel?displayProperty=nameWithType>  
 <span data-ttu-id="353e1-108">クッキーの変換、セキュリティ トークン サービス、および特殊な XML ディクショナリ リーダーを表すクラスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="353e1-108">Contains classes that represent cookie transforms, security token services, and specialized XML dictionary readers.</span></span>  
  
 <xref:System.IdentityModel.Configuration?displayProperty=nameWithType>  
 <span data-ttu-id="353e1-109">Windows Identity Foundation (WIF) を使用して構築されたアプリケーションとサービスの構成を提供するクラスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="353e1-109">Contains classes that provide configuration for applications and services built using the Windows Identity Foundation (WIF).</span></span> <span data-ttu-id="353e1-110">この名前空間のクラスは、[\<identityConfiguration>](../configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) 要素の設定を表しています。</span><span class="sxs-lookup"><span data-stu-id="353e1-110">The classes in this namespace represent settings under the [\<identityConfiguration>](../configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) element.</span></span>  
  
 <xref:System.IdentityModel.Metadata?displayProperty=nameWithType>  
 <span data-ttu-id="353e1-111">フェデレーション メタデータ ドキュメントの要素を表すクラスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="353e1-111">Contains classes that represent elements in a Federation Metadata document.</span></span>  
  
 <xref:System.IdentityModel.Protocols.WSTrust?displayProperty=nameWithType>  
 <span data-ttu-id="353e1-112">WS-Trust 成果物を表すクラスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="353e1-112">Contains classes that represent WS-Trust artifacts.</span></span>  
  
 <xref:System.IdentityModel.Services?displayProperty=nameWithType>  
 <span data-ttu-id="353e1-113">受動的な (WS-Federation) シナリオで使用されるクラスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="353e1-113">Contains classes that are used in passive (WS-Federation) scenarios.</span></span> <span data-ttu-id="353e1-114">また、[\<system.identityModel.services>](../configure-apps/file-schema/windows-identity-foundation/system-identitymodel-services.md) 要素の設定を表すクラスもいくつか含まれています。</span><span class="sxs-lookup"><span data-stu-id="353e1-114">Also contains some classes that represent settings under the [\<system.identityModel.services>](../configure-apps/file-schema/windows-identity-foundation/system-identitymodel-services.md) element.</span></span> <span data-ttu-id="353e1-115">この要素の設定で、アプリケーションの WS-Federation を構成します。</span><span class="sxs-lookup"><span data-stu-id="353e1-115">Settings under this element configure WS-Federation for applications.</span></span> <span data-ttu-id="353e1-116">`System.IdentityModel.Services.Configuration` 名前空間には、WS-Federation の構成に使用されるほとんどのクラスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="353e1-116">The `System.IdentityModel.Services.Configuration` namespace contains most of the classes that are used to configure WS-Federation.</span></span>  
  
 <xref:System.IdentityModel.Services.Configuration?displayProperty=nameWithType>  
 <span data-ttu-id="353e1-117">WS-Federation プロトコルを使用する WIF アプリケーションに構成を提供するクラスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="353e1-117">Contains classes that provide configuration for WIF applications that use the WS-Federation protocol.</span></span> <span data-ttu-id="353e1-118">この名前空間内のクラスは、[\<system.identityModel.services>](../configure-apps/file-schema/windows-identity-foundation/system-identitymodel-services.md) 要素の設定を表します。</span><span class="sxs-lookup"><span data-stu-id="353e1-118">The classes in this namespace represent settings under the [\<system.identityModel.services>](../configure-apps/file-schema/windows-identity-foundation/system-identitymodel-services.md) element.</span></span> <span data-ttu-id="353e1-119">また、`System.IdentityModel.Services` 名前空間には、WS-Federation の構成に使用されるいくつかのクラスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="353e1-119">The `System.IdentityModel.Services` namespace also contains some classes that are used to configure WS-Federation.</span></span>  
  
 <xref:System.IdentityModel.Services.Tokens?displayProperty=nameWithType>  
 <span data-ttu-id="353e1-120">Web ファーム シナリオの特殊なセキュリティ トークン ハンドラーが含まれます。</span><span class="sxs-lookup"><span data-stu-id="353e1-120">Contains specialized security token handlers for Web farm scenarios.</span></span>  
  
 <xref:System.IdentityModel.Tokens?displayProperty=nameWithType>  
 <span data-ttu-id="353e1-121">セキュリティ トークン、セキュリティ トークン ハンドラー、およびその他のセキュリティ トークンの成果物を表すクラスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="353e1-121">Contains classes that represent security tokens, security token handlers, and other security token artifacts.</span></span>  
  
 <xref:System.Security.Claims?displayProperty=nameWithType>  
 <span data-ttu-id="353e1-122">クレーム、クレーム ベースの ID、クレーム ベースの原則、およびその他のクレーム ベースの ID モデル成果物を表すクラスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="353e1-122">Contains classes that represent claims, claims-based identities, claims-based principals, and other claims-based identity model artifacts.</span></span>  
  
 <xref:System.ServiceModel.Security?displayProperty=nameWithType>  
 <span data-ttu-id="353e1-123">アクティブな (WS-Trust) シナリオで使用される WCF のコントラクト、チャネル、サービス ホスト、およびその他の成果物を表すクラスが含まれています。</span><span class="sxs-lookup"><span data-stu-id="353e1-123">Contains classes that represent WCF contracts, channels, service hosts and other artifacts that are used in active (WS-Trust) scenarios.</span></span> <span data-ttu-id="353e1-124">この名前空間には、Windows Communication Foundation (WCF) 固有で、WIF が使用していないクラスも含まれています。</span><span class="sxs-lookup"><span data-stu-id="353e1-124">This namespace also contains classes that are specific to Windows Communication Foundation (WCF) and that are not used by WIF.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="353e1-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="353e1-125">See also</span></span>

- [<span data-ttu-id="353e1-126">WIF 構成のリファレンス</span><span class="sxs-lookup"><span data-stu-id="353e1-126">WIF Configuration Reference</span></span>](wif-configuration-reference.md)
- [<span data-ttu-id="353e1-127">WIF 3.5 と WIF 4.5 間での名前空間マッピング</span><span class="sxs-lookup"><span data-stu-id="353e1-127">Namespace Mapping between WIF 3.5 and WIF 4.5</span></span>](namespace-mapping-between-wif-3-5-and-wif-4-5.md)
