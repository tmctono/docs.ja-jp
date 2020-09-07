---
ms.openlocfilehash: 0c3876d30a80501a89f3a37ce24e2f71122c1b44
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496473"
---
### <a name="systemservicemodelwebwebservicehost-object-no-longer-adds-a-default-endpoint"></a><span data-ttu-id="8bc52-101">System.ServiceModel.Web.WebServiceHost オブジェクトは、既定のエンドポイントを追加しなくなりました</span><span class="sxs-lookup"><span data-stu-id="8bc52-101">System.ServiceModel.Web.WebServiceHost object no longer adds a default endpoint</span></span>

#### <a name="details"></a><span data-ttu-id="8bc52-102">説明</span><span class="sxs-lookup"><span data-stu-id="8bc52-102">Details</span></span>

<span data-ttu-id="8bc52-103"><xref:System.ServiceModel.Web.WebServiceHost> オブジェクトでは、アプリケーション コードによって明示的なエンドポイントが追加された場合に、既定のエンドポイントが追加されなくなりました。</span><span class="sxs-lookup"><span data-stu-id="8bc52-103">The <xref:System.ServiceModel.Web.WebServiceHost> object no longer adds a default endpoint if an explicit endpoint has been added by application code.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="8bc52-104">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="8bc52-104">Suggestion</span></span>

<span data-ttu-id="8bc52-105">ユーザーが既定のエンドポイントに接続できることを期待していて、他の明示的なエンドポイントが <xref:System.ServiceModel.Web.WebServiceHost?displayProperty=fullName> に追加されている場合は、既定のエンドポイントも明示的に追加する必要があります (<xref:System.ServiceModel.ServiceHostBase.AddDefaultEndpoints?displayProperty=fullName> を使用して)。</span><span class="sxs-lookup"><span data-stu-id="8bc52-105">If users will expect to be able to connect to a default endpoint and other explicit endpoints have been added to the <xref:System.ServiceModel.Web.WebServiceHost?displayProperty=fullName>, default endpoints should also be added explicitly (using <xref:System.ServiceModel.ServiceHostBase.AddDefaultEndpoints?displayProperty=fullName>).</span></span>

| <span data-ttu-id="8bc52-106">名前</span><span class="sxs-lookup"><span data-stu-id="8bc52-106">Name</span></span>    | <span data-ttu-id="8bc52-107">[値]</span><span class="sxs-lookup"><span data-stu-id="8bc52-107">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="8bc52-108">スコープ</span><span class="sxs-lookup"><span data-stu-id="8bc52-108">Scope</span></span>   |<span data-ttu-id="8bc52-109">マイナー</span><span class="sxs-lookup"><span data-stu-id="8bc52-109">Minor</span></span>|
|<span data-ttu-id="8bc52-110">バージョン</span><span class="sxs-lookup"><span data-stu-id="8bc52-110">Version</span></span>|<span data-ttu-id="8bc52-111">4.5</span><span class="sxs-lookup"><span data-stu-id="8bc52-111">4.5</span></span>|
|<span data-ttu-id="8bc52-112">種類</span><span class="sxs-lookup"><span data-stu-id="8bc52-112">Type</span></span>|<span data-ttu-id="8bc52-113">ランタイム</span><span class="sxs-lookup"><span data-stu-id="8bc52-113">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="8bc52-114">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="8bc52-114">Affected APIs</span></span>

- <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint(System.Type,System.ServiceModel.Channels.Binding,System.String)?displayProperty=nameWithType>
- <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint(System.Type,System.ServiceModel.Channels.Binding,System.Uri)?displayProperty=nameWithType>
- <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint(System.Type,System.ServiceModel.Channels.Binding,System.String,System.Uri)?displayProperty=nameWithType>
- <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint(System.Type,System.ServiceModel.Channels.Binding,System.Uri,System.Uri)?displayProperty=nameWithType>
- <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint(System.Type,System.ServiceModel.Channels.Binding,System.Uri,System.Uri)?displayProperty=nameWithType>
- <xref:System.ServiceModel.ServiceHostBase.AddServiceEndpoint(System.ServiceModel.Description.ServiceEndpoint)?displayProperty=nameWithType>
- <xref:System.ServiceModel.ServiceHostBase.AddServiceEndpoint(System.String,System.ServiceModel.Channels.Binding,System.String)?displayProperty=nameWithType>
- <xref:System.ServiceModel.ServiceHostBase.AddServiceEndpoint(System.String,System.ServiceModel.Channels.Binding,System.Uri)?displayProperty=nameWithType>
- <xref:System.ServiceModel.ServiceHostBase.AddServiceEndpoint(System.String,System.ServiceModel.Channels.Binding,System.String,System.Uri)?displayProperty=nameWithType>
- <xref:System.ServiceModel.ServiceHostBase.AddServiceEndpoint(System.String,System.ServiceModel.Channels.Binding,System.Uri,System.Uri)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.ServiceModel.ServiceHost.AddServiceEndpoint(System.Type,System.ServiceModel.Channels.Binding,System.String)`
- `M:System.ServiceModel.ServiceHost.AddServiceEndpoint(System.Type,System.ServiceModel.Channels.Binding,System.Uri)`
- `M:System.ServiceModel.ServiceHost.AddServiceEndpoint(System.Type,System.ServiceModel.Channels.Binding,System.String,System.Uri)`
- `M:System.ServiceModel.ServiceHost.AddServiceEndpoint(System.Type,System.ServiceModel.Channels.Binding,System.Uri,System.Uri)`
- `M:System.ServiceModel.ServiceHost.AddServiceEndpoint(System.Type,System.ServiceModel.Channels.Binding,System.Uri,System.Uri)`
- `M:System.ServiceModel.ServiceHostBase.AddServiceEndpoint(System.ServiceModel.Description.ServiceEndpoint)`
- `M:System.ServiceModel.ServiceHostBase.AddServiceEndpoint(System.String,System.ServiceModel.Channels.Binding,System.String)`
- `M:System.ServiceModel.ServiceHostBase.AddServiceEndpoint(System.String,System.ServiceModel.Channels.Binding,System.Uri)`
- `M:System.ServiceModel.ServiceHostBase.AddServiceEndpoint(System.String,System.ServiceModel.Channels.Binding,System.String,System.Uri)`
- `M:System.ServiceModel.ServiceHostBase.AddServiceEndpoint(System.String,System.ServiceModel.Channels.Binding,System.Uri,System.Uri)`

-->
