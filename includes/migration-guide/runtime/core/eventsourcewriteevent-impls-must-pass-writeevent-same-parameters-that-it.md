---
ms.openlocfilehash: 99a7fa0fcfce6d490a182f85709b5dd0e0e8c86f
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496505"
---
### <a name="eventsourcewriteevent-impls-must-pass-writeevent-the-same-parameters-that-it-received-plus-id"></a><span data-ttu-id="53ea6-101">EventSource.WriteEvent impls は、受け取ったのと同じパラメーター (と ID) を WriteEvent に渡す必要がある</span><span class="sxs-lookup"><span data-stu-id="53ea6-101">EventSource.WriteEvent impls must pass WriteEvent the same parameters that it received (plus ID)</span></span>

#### <a name="details"></a><span data-ttu-id="53ea6-102">説明</span><span class="sxs-lookup"><span data-stu-id="53ea6-102">Details</span></span>

<span data-ttu-id="53ea6-103">ランタイムは次の内容を指定するコントラクトを強制するようになりました。ETW イベント メソッドを定義する <xref:System.Diagnostics.Tracing.EventSource?displayProperty=fullName> から派生するクラスは、ETW イベント メソッドが渡された同じ引数が続くイベント ID の基底クラス <code>EventSource.WriteEvent</code> メソッドを呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="53ea6-103">The runtime now enforces the contract that specifies the following: A class derived from <xref:System.Diagnostics.Tracing.EventSource?displayProperty=fullName> that defines an ETW event method must call the base class <code>EventSource.WriteEvent</code> method with the event ID followed by the same arguments that the ETW event method was passed.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="53ea6-104">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="53ea6-104">Suggestion</span></span>

<span data-ttu-id="53ea6-105"><xref:System.IndexOutOfRangeException?displayProperty=fullName> 例外は、<xref:System.Diagnostics.Tracing.EventListener?displayProperty=fullName> がこのコントラクトに違反するイベント ソースのプロセスの <xref:System.Diagnostics.Tracing.EventSource?displayProperty=fullName> データを読み取るときに、スローされます。</span><span class="sxs-lookup"><span data-stu-id="53ea6-105">An <xref:System.IndexOutOfRangeException?displayProperty=fullName> exception is thrown if an <xref:System.Diagnostics.Tracing.EventListener?displayProperty=fullName> reads <xref:System.Diagnostics.Tracing.EventSource?displayProperty=fullName> data in process for an event source that violates this contract.</span></span>

| <span data-ttu-id="53ea6-106">名前</span><span class="sxs-lookup"><span data-stu-id="53ea6-106">Name</span></span>    | <span data-ttu-id="53ea6-107">[値]</span><span class="sxs-lookup"><span data-stu-id="53ea6-107">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="53ea6-108">スコープ</span><span class="sxs-lookup"><span data-stu-id="53ea6-108">Scope</span></span>   |<span data-ttu-id="53ea6-109">マイナー</span><span class="sxs-lookup"><span data-stu-id="53ea6-109">Minor</span></span>|
|<span data-ttu-id="53ea6-110">バージョン</span><span class="sxs-lookup"><span data-stu-id="53ea6-110">Version</span></span>|<span data-ttu-id="53ea6-111">4.5.1</span><span class="sxs-lookup"><span data-stu-id="53ea6-111">4.5.1</span></span>|
|<span data-ttu-id="53ea6-112">種類</span><span class="sxs-lookup"><span data-stu-id="53ea6-112">Type</span></span>|<span data-ttu-id="53ea6-113">ランタイム</span><span class="sxs-lookup"><span data-stu-id="53ea6-113">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="53ea6-114">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="53ea6-114">Affected APIs</span></span>

<span data-ttu-id="53ea6-115">API 分析では検出できません。</span><span class="sxs-lookup"><span data-stu-id="53ea6-115">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
