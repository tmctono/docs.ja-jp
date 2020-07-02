---
ms.openlocfilehash: 57f68c10d5d1edc9b8deaca2f4fe7edda2dd69b0
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620395"
---
### <a name="systemservicemodelwebwebservicehost-object-no-longer-adds-a-default-endpoint"></a><span data-ttu-id="f9e83-101">System.ServiceModel.Web.WebServiceHost オブジェクトは、既定のエンドポイントを追加しなくなりました</span><span class="sxs-lookup"><span data-stu-id="f9e83-101">System.ServiceModel.Web.WebServiceHost object no longer adds a default endpoint</span></span>

#### <a name="details"></a><span data-ttu-id="f9e83-102">説明</span><span class="sxs-lookup"><span data-stu-id="f9e83-102">Details</span></span>

<span data-ttu-id="f9e83-103"><xref:System.ServiceModel.Web.WebServiceHost> オブジェクトでは、アプリケーション コードによって明示的なエンドポイントが追加された場合に、既定のエンドポイントが追加されなくなりました。</span><span class="sxs-lookup"><span data-stu-id="f9e83-103">The <xref:System.ServiceModel.Web.WebServiceHost> object no longer adds a default endpoint if an explicit endpoint has been added by application code.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="f9e83-104">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="f9e83-104">Suggestion</span></span>

<span data-ttu-id="f9e83-105">ユーザーが既定のエンドポイントに接続できることを期待していて、他の明示的なエンドポイントが <xref:System.ServiceModel.Web.WebServiceHost?displayProperty=fullName> に追加されている場合は、既定のエンドポイントも明示的に追加する必要があります (<xref:System.ServiceModel.ServiceHostBase.AddDefaultEndpoints?displayProperty=fullName> を使用して)。</span><span class="sxs-lookup"><span data-stu-id="f9e83-105">If users will expect to be able to connect to a default endpoint and other explicit endpoints have been added to the <xref:System.ServiceModel.Web.WebServiceHost?displayProperty=fullName>, default endpoints should also be added explicitly (using <xref:System.ServiceModel.ServiceHostBase.AddDefaultEndpoints?displayProperty=fullName>).</span></span>

| <span data-ttu-id="f9e83-106">名前</span><span class="sxs-lookup"><span data-stu-id="f9e83-106">Name</span></span>    | <span data-ttu-id="f9e83-107">[値]</span><span class="sxs-lookup"><span data-stu-id="f9e83-107">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="f9e83-108">スコープ</span><span class="sxs-lookup"><span data-stu-id="f9e83-108">Scope</span></span>   |<span data-ttu-id="f9e83-109">マイナー</span><span class="sxs-lookup"><span data-stu-id="f9e83-109">Minor</span></span>|
|<span data-ttu-id="f9e83-110">バージョン</span><span class="sxs-lookup"><span data-stu-id="f9e83-110">Version</span></span>|<span data-ttu-id="f9e83-111">4.5</span><span class="sxs-lookup"><span data-stu-id="f9e83-111">4.5</span></span>|
|<span data-ttu-id="f9e83-112">種類</span><span class="sxs-lookup"><span data-stu-id="f9e83-112">Type</span></span>|<span data-ttu-id="f9e83-113">ランタイム</span><span class="sxs-lookup"><span data-stu-id="f9e83-113">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="f9e83-114">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="f9e83-114">Affected APIs</span></span>

-<xref:System.ServiceModel.ServiceHost.AddServiceEndpoint(System.Type,System.ServiceModel.Channels.Binding,System.String)?displayProperty=nameWithType></li><li><xref:System.ServiceModel.ServiceHost.AddServiceEndpoint(System.Type,System.ServiceModel.Channels.Binding,System.Uri)?displayProperty=nameWithType></li><li><xref:System.ServiceModel.ServiceHost.AddServiceEndpoint(System.Type,System.ServiceModel.Channels.Binding,System.String,System.Uri)?displayProperty=nameWithType></li><li><xref:System.ServiceModel.ServiceHost.AddServiceEndpoint(System.Type,System.ServiceModel.Channels.Binding,System.Uri,System.Uri)?displayProperty=nameWithType></li><li><xref:System.ServiceModel.ServiceHost.AddServiceEndpoint(System.Type,System.ServiceModel.Channels.Binding,System.Uri,System.Uri)?displayProperty=nameWithType></li><li><xref:System.ServiceModel.ServiceHostBase.AddServiceEndpoint(System.ServiceModel.Description.ServiceEndpoint)?displayProperty=nameWithType></li><li><xref:System.ServiceModel.ServiceHostBase.AddServiceEndpoint(System.String,System.ServiceModel.Channels.Binding,System.String)?displayProperty=nameWithType></li><li><xref:System.ServiceModel.ServiceHostBase.AddServiceEndpoint(System.String,System.ServiceModel.Channels.Binding,System.Uri)?displayProperty=nameWithType></li><li><xref:System.ServiceModel.ServiceHostBase.AddServiceEndpoint(System.String,System.ServiceModel.Channels.Binding,System.String,System.Uri)?displayProperty=nameWithType></li><li><xref:System.ServiceModel.ServiceHostBase.AddServiceEndpoint(System.String,System.ServiceModel.Channels.Binding,System.Uri,System.Uri)?displayProperty=nameWithType></li></ul>|
