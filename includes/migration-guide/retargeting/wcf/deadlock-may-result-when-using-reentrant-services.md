---
ms.openlocfilehash: dd7d3e445772e4b5ec148576ccd1374d56e251bd
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614781"
---
### <a name="deadlock-may-result-when-using-reentrant-services"></a><span data-ttu-id="a4770-101">再入可能なサービスを使用していると、デッドロックが発生する可能性がある</span><span class="sxs-lookup"><span data-stu-id="a4770-101">Deadlock may result when using Reentrant services</span></span>

#### <a name="details"></a><span data-ttu-id="a4770-102">説明</span><span class="sxs-lookup"><span data-stu-id="a4770-102">Details</span></span>

<span data-ttu-id="a4770-103">サービスのインスタンスの実行が一度に 1 つのスレッドに制限される再入可能なサービスでは、デッドロックが発生します。</span><span class="sxs-lookup"><span data-stu-id="a4770-103">A deadlock may result in a Reentrant service, which restricts instances of the service to one thread of execution at a time.</span></span> <span data-ttu-id="a4770-104">この問題が発生しやすいサービスのコードには、次の <xref:System.ServiceModel.ServiceBehaviorAttribute> が含まれています。</span><span class="sxs-lookup"><span data-stu-id="a4770-104">Services prone to encounter this problem will have the following <xref:System.ServiceModel.ServiceBehaviorAttribute> in their code:</span></span>

```csharp
[ServiceBehavior(ConcurrencyMode = ConcurrencyMode.Reentrant)]
```

#### <a name="suggestion"></a><span data-ttu-id="a4770-105">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="a4770-105">Suggestion</span></span>

<span data-ttu-id="a4770-106">この問題に対処するために、次の操作を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="a4770-106">To address this issue, you can do the following:</span></span>

- <span data-ttu-id="a4770-107">サービスのコンカレンシー モードを <xref:System.ServiceModel.ConcurrencyMode.Single?displayProperty=nameWithType> または &lt;System.ServiceModel.ConcurrencyMode.Multiple?displayProperty=nameWithType&gt; に設定します。</span><span class="sxs-lookup"><span data-stu-id="a4770-107">Set the service's concurrency mode to <xref:System.ServiceModel.ConcurrencyMode.Single?displayProperty=nameWithType> or &lt;System.ServiceModel.ConcurrencyMode.Multiple?displayProperty=nameWithType&gt;.</span></span> <span data-ttu-id="a4770-108">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="a4770-108">For example:</span></span>

```csharp
[ServiceBehavior(ConcurrencyMode = ConcurrencyMode.Reentrant)]
```

- <span data-ttu-id="a4770-109">最新の更新プログラムを .NET framework 4.6.2 にインストールするか、最新バージョンの .NET Framework にアップグレードします。</span><span class="sxs-lookup"><span data-stu-id="a4770-109">Install the latest update to the .NET Framework 4.6.2, or upgrade to a later version of the .NET Framework.</span></span> <span data-ttu-id="a4770-110">これにより、<xref:System.ServiceModel.OperationContext.Current?displayProperty=nameWithType> の <xref:System.Threading.ExecutionContext> のフローが無効になります。</span><span class="sxs-lookup"><span data-stu-id="a4770-110">This disables the flow of the <xref:System.Threading.ExecutionContext> in <xref:System.ServiceModel.OperationContext.Current?displayProperty=nameWithType>.</span></span> <span data-ttu-id="a4770-111">この動作は構成可能です。構成ファイルに次のアプリ設定を追加することと同じです。</span><span class="sxs-lookup"><span data-stu-id="a4770-111">This behavior is configurable; it is equivalent to adding the following app setting to your configuration file:</span></span>

```xml
<appSettings>
  <add key="Switch.System.ServiceModel.DisableOperationContextAsyncFlow" value="true" />
</appSettings>
```

<span data-ttu-id="a4770-112">Reentrant サービスの場合、`Switch.System.ServiceModel.DisableOperationContextAsyncFlow` の値は `false` に設定しないでください。</span><span class="sxs-lookup"><span data-stu-id="a4770-112">The value of `Switch.System.ServiceModel.DisableOperationContextAsyncFlow` should never be set to `false` for Reentrant services.</span></span>

| <span data-ttu-id="a4770-113">名前</span><span class="sxs-lookup"><span data-stu-id="a4770-113">Name</span></span>    | <span data-ttu-id="a4770-114">[値]</span><span class="sxs-lookup"><span data-stu-id="a4770-114">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="a4770-115">スコープ</span><span class="sxs-lookup"><span data-stu-id="a4770-115">Scope</span></span>   | <span data-ttu-id="a4770-116">マイナー</span><span class="sxs-lookup"><span data-stu-id="a4770-116">Minor</span></span>       |
| <span data-ttu-id="a4770-117">バージョン</span><span class="sxs-lookup"><span data-stu-id="a4770-117">Version</span></span> | <span data-ttu-id="a4770-118">4.6.2</span><span class="sxs-lookup"><span data-stu-id="a4770-118">4.6.2</span></span>       |
| <span data-ttu-id="a4770-119">種類</span><span class="sxs-lookup"><span data-stu-id="a4770-119">Type</span></span>    | <span data-ttu-id="a4770-120">再ターゲット中</span><span class="sxs-lookup"><span data-stu-id="a4770-120">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="a4770-121">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="a4770-121">Affected APIs</span></span>

- <xref:System.ServiceModel.ServiceBehaviorAttribute?displayProperty=nameWithType>
- <xref:System.ServiceModel.ConcurrencyMode.Reentrant?displayProperty=nameWithType>
