---
ms.openlocfilehash: f61cf21f9f30662cc8e383bb3aeb5c642f1665b8
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497784"
---
### <a name="deadlock-may-result-when-using-reentrant-services"></a><span data-ttu-id="228ca-101">再入可能なサービスを使用していると、デッドロックが発生する可能性がある</span><span class="sxs-lookup"><span data-stu-id="228ca-101">Deadlock may result when using Reentrant services</span></span>

#### <a name="details"></a><span data-ttu-id="228ca-102">説明</span><span class="sxs-lookup"><span data-stu-id="228ca-102">Details</span></span>

<span data-ttu-id="228ca-103">サービスのインスタンスの実行が一度に 1 つのスレッドに制限される再入可能なサービスでは、デッドロックが発生します。</span><span class="sxs-lookup"><span data-stu-id="228ca-103">A deadlock may result in a Reentrant service, which restricts instances of the service to one thread of execution at a time.</span></span> <span data-ttu-id="228ca-104">この問題が発生しやすいサービスのコードには、次の <xref:System.ServiceModel.ServiceBehaviorAttribute> が含まれています。</span><span class="sxs-lookup"><span data-stu-id="228ca-104">Services prone to encounter this problem will have the following <xref:System.ServiceModel.ServiceBehaviorAttribute> in their code:</span></span>

```csharp
[ServiceBehavior(ConcurrencyMode = ConcurrencyMode.Reentrant)]
```

#### <a name="suggestion"></a><span data-ttu-id="228ca-105">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="228ca-105">Suggestion</span></span>

<span data-ttu-id="228ca-106">この問題に対処するために、次の操作を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="228ca-106">To address this issue, you can do the following:</span></span>

- <span data-ttu-id="228ca-107">サービスのコンカレンシー モードを <xref:System.ServiceModel.ConcurrencyMode.Single?displayProperty=nameWithType> または <xref:System.ServiceModel.ConcurrencyMode.Multiple?displayProperty=nameWithType> に設定します。</span><span class="sxs-lookup"><span data-stu-id="228ca-107">Set the service's concurrency mode to <xref:System.ServiceModel.ConcurrencyMode.Single?displayProperty=nameWithType> or <xref:System.ServiceModel.ConcurrencyMode.Multiple?displayProperty=nameWithType>.</span></span> <span data-ttu-id="228ca-108">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="228ca-108">For example:</span></span>

```csharp
[ServiceBehavior(ConcurrencyMode = ConcurrencyMode.Reentrant)]
```

- <span data-ttu-id="228ca-109">最新の更新プログラムを .NET framework 4.6.2 にインストールするか、最新バージョンの .NET Framework にアップグレードします。</span><span class="sxs-lookup"><span data-stu-id="228ca-109">Install the latest update to the .NET Framework 4.6.2, or upgrade to a later version of the .NET Framework.</span></span> <span data-ttu-id="228ca-110">これにより、<xref:System.ServiceModel.OperationContext.Current?displayProperty=nameWithType> の <xref:System.Threading.ExecutionContext> のフローが無効になります。</span><span class="sxs-lookup"><span data-stu-id="228ca-110">This disables the flow of the <xref:System.Threading.ExecutionContext> in <xref:System.ServiceModel.OperationContext.Current?displayProperty=nameWithType>.</span></span> <span data-ttu-id="228ca-111">この動作は構成可能です。構成ファイルに次のアプリ設定を追加することと同じです。</span><span class="sxs-lookup"><span data-stu-id="228ca-111">This behavior is configurable; it is equivalent to adding the following app setting to your configuration file:</span></span>

```xml
<appSettings>
  <add key="Switch.System.ServiceModel.DisableOperationContextAsyncFlow" value="true" />
</appSettings>
```

<span data-ttu-id="228ca-112">Reentrant サービスの場合、`Switch.System.ServiceModel.DisableOperationContextAsyncFlow` の値は `false` に設定しないでください。</span><span class="sxs-lookup"><span data-stu-id="228ca-112">The value of `Switch.System.ServiceModel.DisableOperationContextAsyncFlow` should never be set to `false` for Reentrant services.</span></span>

| <span data-ttu-id="228ca-113">名前</span><span class="sxs-lookup"><span data-stu-id="228ca-113">Name</span></span>    | <span data-ttu-id="228ca-114">[値]</span><span class="sxs-lookup"><span data-stu-id="228ca-114">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="228ca-115">スコープ</span><span class="sxs-lookup"><span data-stu-id="228ca-115">Scope</span></span>   | <span data-ttu-id="228ca-116">マイナー</span><span class="sxs-lookup"><span data-stu-id="228ca-116">Minor</span></span>       |
| <span data-ttu-id="228ca-117">バージョン</span><span class="sxs-lookup"><span data-stu-id="228ca-117">Version</span></span> | <span data-ttu-id="228ca-118">4.6.2</span><span class="sxs-lookup"><span data-stu-id="228ca-118">4.6.2</span></span>       |
| <span data-ttu-id="228ca-119">種類</span><span class="sxs-lookup"><span data-stu-id="228ca-119">Type</span></span>    | <span data-ttu-id="228ca-120">再ターゲット中</span><span class="sxs-lookup"><span data-stu-id="228ca-120">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="228ca-121">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="228ca-121">Affected APIs</span></span>

- <xref:System.ServiceModel.ServiceBehaviorAttribute?displayProperty=nameWithType>
- <xref:System.ServiceModel.ConcurrencyMode.Reentrant?displayProperty=nameWithType>
