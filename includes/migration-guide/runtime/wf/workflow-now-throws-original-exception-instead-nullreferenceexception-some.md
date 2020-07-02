---
ms.openlocfilehash: ae0c7322b7415157838278b5568e6e49936e9a93
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621243"
---
### <a name="workflow-now-throws-original-exception-instead-of-nullreferenceexception-in-some-cases"></a><span data-ttu-id="7c41a-101">場合によって、ワークフローで NullReferenceException ではなく、元の例外がスローされるようになった</span><span class="sxs-lookup"><span data-stu-id="7c41a-101">Workflow now throws original exception instead of NullReferenceException in some cases</span></span>

#### <a name="details"></a><span data-ttu-id="7c41a-102">説明</span><span class="sxs-lookup"><span data-stu-id="7c41a-102">Details</span></span>

<span data-ttu-id="7c41a-103">.NET Framework 4.6.2 ワークフロー アクティビティの Execute メソッドを使用して例外をスローした場合、以前のバージョンで、<code>null</code>値を<xref:System.Exception.Message>プロパティ、System.Activities ワークフロー ランタイムは、スロー、 <xref:System.NullReferenceException?displayProperty=fullName>、マスク、元の例外。 .NET Framework 4.7 以前マスクは、例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="7c41a-103">In the .NET Framework 4.6.2 and earlier versions, when the Execute method of a workflow activity throws an exception with a <code>null</code> value for the <xref:System.Exception.Message> property, the System.Activities Workflow runtime throws a <xref:System.NullReferenceException?displayProperty=fullName>, masking the original exception.In the .NET Framework 4.7, the previously masked exception is thrown.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="7c41a-104">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="7c41a-104">Suggestion</span></span>

<span data-ttu-id="7c41a-105">コードが <xref:System.NullReferenceException?displayProperty=fullName> の処理に依存する場合は、カスタム アクティビティからスローされる可能性のある例外をキャッチするように変更します。</span><span class="sxs-lookup"><span data-stu-id="7c41a-105">If your code relies on handling the <xref:System.NullReferenceException?displayProperty=fullName>, change it to catch the exceptions that could be thrown from your custom activities.</span></span>

| <span data-ttu-id="7c41a-106">名前</span><span class="sxs-lookup"><span data-stu-id="7c41a-106">Name</span></span>    | <span data-ttu-id="7c41a-107">値</span><span class="sxs-lookup"><span data-stu-id="7c41a-107">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="7c41a-108">スコープ</span><span class="sxs-lookup"><span data-stu-id="7c41a-108">Scope</span></span>   |<span data-ttu-id="7c41a-109">マイナー</span><span class="sxs-lookup"><span data-stu-id="7c41a-109">Minor</span></span>|
|<span data-ttu-id="7c41a-110">バージョン</span><span class="sxs-lookup"><span data-stu-id="7c41a-110">Version</span></span>|<span data-ttu-id="7c41a-111">4.7</span><span class="sxs-lookup"><span data-stu-id="7c41a-111">4.7</span></span>|
|<span data-ttu-id="7c41a-112">種類</span><span class="sxs-lookup"><span data-stu-id="7c41a-112">Type</span></span>|<span data-ttu-id="7c41a-113">ランタイム</span><span class="sxs-lookup"><span data-stu-id="7c41a-113">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="7c41a-114">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="7c41a-114">Affected APIs</span></span>

-<xref:System.Activities.CodeActivity.Execute(System.Activities.CodeActivityContext)?displayProperty=nameWithType></li><li><xref:System.Activities.AsyncCodeActivity.BeginExecute(System.Activities.AsyncCodeActivityContext,System.AsyncCallback,System.Object)?displayProperty=nameWithType></li><li><xref:System.Activities.AsyncCodeActivity%601.BeginExecute(System.Activities.AsyncCodeActivityContext,System.AsyncCallback,System.Object)?displayProperty=nameWithType></li><li><xref:System.Activities.WorkflowInvoker.Invoke?displayProperty=nameWithType></li></ul>|
