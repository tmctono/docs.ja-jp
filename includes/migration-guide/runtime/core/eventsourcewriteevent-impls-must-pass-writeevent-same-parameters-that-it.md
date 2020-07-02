---
ms.openlocfilehash: 662c140f019add66ff6605d47ad1f32c3f50d711
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620240"
---
### <a name="eventsourcewriteevent-impls-must-pass-writeevent-the-same-parameters-that-it-received-plus-id"></a><span data-ttu-id="c7434-101">EventSource.WriteEvent impls は、受け取ったのと同じパラメーター (と ID) を WriteEvent に渡す必要がある</span><span class="sxs-lookup"><span data-stu-id="c7434-101">EventSource.WriteEvent impls must pass WriteEvent the same parameters that it received (plus ID)</span></span>

#### <a name="details"></a><span data-ttu-id="c7434-102">説明</span><span class="sxs-lookup"><span data-stu-id="c7434-102">Details</span></span>

<span data-ttu-id="c7434-103">ランタイムは次の内容を指定するコントラクトを強制するようになりました。ETW イベント メソッドを定義する <xref:System.Diagnostics.Tracing.EventSource?displayProperty=fullName> から派生するクラスは、ETW イベント メソッドが渡された同じ引数が続くイベント ID の基底クラス <code>EventSource.WriteEvent</code> メソッドを呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="c7434-103">The runtime now enforces the contract that specifies the following: A class derived from <xref:System.Diagnostics.Tracing.EventSource?displayProperty=fullName> that defines an ETW event method must call the base class <code>EventSource.WriteEvent</code> method with the event ID followed by the same arguments that the ETW event method was passed.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="c7434-104">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="c7434-104">Suggestion</span></span>

<span data-ttu-id="c7434-105"><xref:System.IndexOutOfRangeException?displayProperty=fullName> 例外は、<xref:System.Diagnostics.Tracing.EventListener?displayProperty=fullName> がこのコントラクトに違反するイベント ソースのプロセスの <xref:System.Diagnostics.Tracing.EventSource?displayProperty=fullName> データを読み取るときに、スローされます。</span><span class="sxs-lookup"><span data-stu-id="c7434-105">An <xref:System.IndexOutOfRangeException?displayProperty=fullName> exception is thrown if an <xref:System.Diagnostics.Tracing.EventListener?displayProperty=fullName> reads <xref:System.Diagnostics.Tracing.EventSource?displayProperty=fullName> data in process for an event source that violates this contract.</span></span>

| <span data-ttu-id="c7434-106">名前</span><span class="sxs-lookup"><span data-stu-id="c7434-106">Name</span></span>    | <span data-ttu-id="c7434-107">[値]</span><span class="sxs-lookup"><span data-stu-id="c7434-107">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="c7434-108">スコープ</span><span class="sxs-lookup"><span data-stu-id="c7434-108">Scope</span></span>   |<span data-ttu-id="c7434-109">マイナー</span><span class="sxs-lookup"><span data-stu-id="c7434-109">Minor</span></span>|
|<span data-ttu-id="c7434-110">バージョン</span><span class="sxs-lookup"><span data-stu-id="c7434-110">Version</span></span>|<span data-ttu-id="c7434-111">4.5.1</span><span class="sxs-lookup"><span data-stu-id="c7434-111">4.5.1</span></span>|
|<span data-ttu-id="c7434-112">種類</span><span class="sxs-lookup"><span data-stu-id="c7434-112">Type</span></span>|<span data-ttu-id="c7434-113">ランタイム</span><span class="sxs-lookup"><span data-stu-id="c7434-113">Runtime</span></span>|
