---
ms.openlocfilehash: 61d5885c19e39b138090c1a98fa26348724893c5
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497829"
---
### <a name="workflow-now-throws-original-exception-instead-of-nullreferenceexception-in-some-cases"></a><span data-ttu-id="9d706-101">場合によって、ワークフローで NullReferenceException ではなく、元の例外がスローされるようになった</span><span class="sxs-lookup"><span data-stu-id="9d706-101">Workflow now throws original exception instead of NullReferenceException in some cases</span></span>

#### <a name="details"></a><span data-ttu-id="9d706-102">説明</span><span class="sxs-lookup"><span data-stu-id="9d706-102">Details</span></span>

<span data-ttu-id="9d706-103">.NET Framework 4.6.2 ワークフロー アクティビティの Execute メソッドを使用して例外をスローした場合、以前のバージョンで、<code>null</code>値を<xref:System.Exception.Message>プロパティ、System.Activities ワークフロー ランタイムは、スロー、 <xref:System.NullReferenceException?displayProperty=fullName>、マスク、元の例外。 .NET Framework 4.7 以前マスクは、例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="9d706-103">In the .NET Framework 4.6.2 and earlier versions, when the Execute method of a workflow activity throws an exception with a <code>null</code> value for the <xref:System.Exception.Message> property, the System.Activities Workflow runtime throws a <xref:System.NullReferenceException?displayProperty=fullName>, masking the original exception.In the .NET Framework 4.7, the previously masked exception is thrown.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="9d706-104">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="9d706-104">Suggestion</span></span>

<span data-ttu-id="9d706-105">コードが <xref:System.NullReferenceException?displayProperty=fullName> の処理に依存する場合は、カスタム アクティビティからスローされる可能性のある例外をキャッチするように変更します。</span><span class="sxs-lookup"><span data-stu-id="9d706-105">If your code relies on handling the <xref:System.NullReferenceException?displayProperty=fullName>, change it to catch the exceptions that could be thrown from your custom activities.</span></span>

| <span data-ttu-id="9d706-106">名前</span><span class="sxs-lookup"><span data-stu-id="9d706-106">Name</span></span>    | <span data-ttu-id="9d706-107">値</span><span class="sxs-lookup"><span data-stu-id="9d706-107">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="9d706-108">スコープ</span><span class="sxs-lookup"><span data-stu-id="9d706-108">Scope</span></span>   |<span data-ttu-id="9d706-109">マイナー</span><span class="sxs-lookup"><span data-stu-id="9d706-109">Minor</span></span>|
|<span data-ttu-id="9d706-110">バージョン</span><span class="sxs-lookup"><span data-stu-id="9d706-110">Version</span></span>|<span data-ttu-id="9d706-111">4.7</span><span class="sxs-lookup"><span data-stu-id="9d706-111">4.7</span></span>|
|<span data-ttu-id="9d706-112">種類</span><span class="sxs-lookup"><span data-stu-id="9d706-112">Type</span></span>|<span data-ttu-id="9d706-113">ランタイム</span><span class="sxs-lookup"><span data-stu-id="9d706-113">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="9d706-114">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="9d706-114">Affected APIs</span></span>

- <xref:System.Activities.CodeActivity.Execute(System.Activities.CodeActivityContext)?displayProperty=nameWithType>
- <xref:System.Activities.AsyncCodeActivity.BeginExecute(System.Activities.AsyncCodeActivityContext,System.AsyncCallback,System.Object)?displayProperty=nameWithType>
- <xref:System.Activities.AsyncCodeActivity%601.BeginExecute(System.Activities.AsyncCodeActivityContext,System.AsyncCallback,System.Object)?displayProperty=nameWithType>
- <xref:System.Activities.WorkflowInvoker.Invoke?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Activities.CodeActivity.Execute(System.Activities.CodeActivityContext)`
- `M:System.Activities.AsyncCodeActivity.BeginExecute(System.Activities.AsyncCodeActivityContext,System.AsyncCallback,System.Object)`
- ``M:System.Activities.AsyncCodeActivity`1.BeginExecute(System.Activities.AsyncCodeActivityContext,System.AsyncCallback,System.Object)``
- `M:System.Activities.WorkflowInvoker.Invoke`

-->
