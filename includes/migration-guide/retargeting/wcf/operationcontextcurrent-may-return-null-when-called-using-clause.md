---
ms.openlocfilehash: d25c14f93da5fe8acf06269554fed30ddc6bc95d
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614756"
---
### <a name="operationcontextcurrent-may-return-null-when-called-in-a-using-clause"></a><span data-ttu-id="98fa9-101">OperationContext.Current が using 句で呼びされたときに null を返す場合がある</span><span class="sxs-lookup"><span data-stu-id="98fa9-101">OperationContext.Current may return null when called in a using clause</span></span>

#### <a name="details"></a><span data-ttu-id="98fa9-102">説明</span><span class="sxs-lookup"><span data-stu-id="98fa9-102">Details</span></span>

<span data-ttu-id="98fa9-103">次のすべての条件が満たされている場合は、<xref:System.ServiceModel.OperationContext.Current?displayProperty=nameWithType> が `null` を返し、<xref:System.NullReferenceException> が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="98fa9-103"><xref:System.ServiceModel.OperationContext.Current?displayProperty=nameWithType> may return `null` and a <xref:System.NullReferenceException> may result if all of the following conditions are true:</span></span>

- <span data-ttu-id="98fa9-104"><xref:System.Threading.Tasks.Task> または <xref:System.Threading.Tasks.Task%601> を返すメソッドで <xref:System.ServiceModel.OperationContext.Current?displayProperty=nameWithType> プロパティの値を取得します。</span><span class="sxs-lookup"><span data-stu-id="98fa9-104">You retrieve the value of the <xref:System.ServiceModel.OperationContext.Current?displayProperty=nameWithType> property in a method that returns a <xref:System.Threading.Tasks.Task> or <xref:System.Threading.Tasks.Task%601>.</span></span>
- <span data-ttu-id="98fa9-105">`using` 句で <xref:System.ServiceModel.OperationContextScope> オブジェクトをインスタンス化します。</span><span class="sxs-lookup"><span data-stu-id="98fa9-105">You instantiate the <xref:System.ServiceModel.OperationContextScope> object in a `using` clause.</span></span>
- <span data-ttu-id="98fa9-106">`using statement` 内で <xref:System.ServiceModel.OperationContext.Current?displayProperty=nameWithType> プロパティの値を取得します。</span><span class="sxs-lookup"><span data-stu-id="98fa9-106">You retrieve the value of the <xref:System.ServiceModel.OperationContext.Current?displayProperty=nameWithType> property within the `using statement`.</span></span> <span data-ttu-id="98fa9-107">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="98fa9-107">For example:</span></span>

```csharp
using (new OperationContextScope(OperationContext.Current))
{
    // OperationContext.Current is null.
    OperationContext context = OperationContext.Current;

    // ...
}
```

#### <a name="suggestion"></a><span data-ttu-id="98fa9-108">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="98fa9-108">Suggestion</span></span>

<span data-ttu-id="98fa9-109">この問題に対処するために、次の操作を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="98fa9-109">To address this issue, you can do the following:</span></span>

- <span data-ttu-id="98fa9-110">次のようにコードを変更して、新しい `null` 以外の <xref:System.ServiceModel.OperationContext.Current%2A> オブジェクトをインスタンス化します。</span><span class="sxs-lookup"><span data-stu-id="98fa9-110">Modify your code as follows to instantiate a new non- `null` <xref:System.ServiceModel.OperationContext.Current%2A> object:</span></span>

    ```csharp
    OperationContext ocx = OperationContext.Current;
    using (new OperationContextScope(OperationContext.Current))
    {
        OperationContext.Current = new OperationContext(ocx.Channel);

        // ...
    }
    ```

- <span data-ttu-id="98fa9-111">最新の更新プログラムを .NET framework 4.6.2 にインストールするか、最新バージョンの .NET Framework にアップグレードします。</span><span class="sxs-lookup"><span data-stu-id="98fa9-111">Install the latest update to the .NET Framework 4.6.2, or upgrade to a later version of the .NET Framework.</span></span> <span data-ttu-id="98fa9-112">これにより、<xref:System.ServiceModel.OperationContext.Current?displayProperty=nameWithType> で <xref:System.Threading.ExecutionContext> のフローが無効になり、.NET Framework 4.6.1 以前のバージョンで WCF アプリケーションの動作が復元されます。</span><span class="sxs-lookup"><span data-stu-id="98fa9-112">This disables the flow of the <xref:System.Threading.ExecutionContext> in <xref:System.ServiceModel.OperationContext.Current?displayProperty=nameWithType> and restores the behavior of WCF applications in the .NET Framework 4.6.1 and earlier versions.</span></span> <span data-ttu-id="98fa9-113">この動作は構成可能です。構成ファイルに次のアプリ設定を追加することと同じです。</span><span class="sxs-lookup"><span data-stu-id="98fa9-113">This behavior is configurable; it is equivalent to adding the following app setting to your configuration file:</span></span>

    ```xml
    <appSettings>
      <add key="Switch.System.ServiceModel.DisableOperationContextAsyncFlow" value="true" />
    </appSettings>
    ```

    <span data-ttu-id="98fa9-114">この変更が望ましくなく、アプリケーションが操作コンテキスト間の実行コンテキスト フローに依存している場合は、次のようにそのフローを有効にできます。</span><span class="sxs-lookup"><span data-stu-id="98fa9-114">If this change is undesirable and your application depends on execution context flowing between operation contexts, you can enable its flow as follows:</span></span>

    ```xml
    <appSettings>
      <add key="Switch.System.ServiceModel.DisableOperationContextAsyncFlow" value="false" />
    </appSettings>
    ```

| <span data-ttu-id="98fa9-115">名前</span><span class="sxs-lookup"><span data-stu-id="98fa9-115">Name</span></span>    | <span data-ttu-id="98fa9-116">[値]</span><span class="sxs-lookup"><span data-stu-id="98fa9-116">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="98fa9-117">スコープ</span><span class="sxs-lookup"><span data-stu-id="98fa9-117">Scope</span></span>   | <span data-ttu-id="98fa9-118">エッジ</span><span class="sxs-lookup"><span data-stu-id="98fa9-118">Edge</span></span>        |
| <span data-ttu-id="98fa9-119">バージョン</span><span class="sxs-lookup"><span data-stu-id="98fa9-119">Version</span></span> | <span data-ttu-id="98fa9-120">4.6.2</span><span class="sxs-lookup"><span data-stu-id="98fa9-120">4.6.2</span></span>       |
| <span data-ttu-id="98fa9-121">種類</span><span class="sxs-lookup"><span data-stu-id="98fa9-121">Type</span></span>    | <span data-ttu-id="98fa9-122">再ターゲット中</span><span class="sxs-lookup"><span data-stu-id="98fa9-122">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="98fa9-123">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="98fa9-123">Affected APIs</span></span>

- <xref:System.ServiceModel.OperationContext.Current?displayProperty=nameWithType>
