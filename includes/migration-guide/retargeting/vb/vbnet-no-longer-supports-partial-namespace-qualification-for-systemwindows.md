---
ms.openlocfilehash: cef8096c971da8ae245ff974697022f350cb9195
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85616076"
---
### <a name="vbnet-no-longer-supports-partial-namespace-qualification-for-systemwindows-apis"></a><span data-ttu-id="a03ef-101">VB.NET は、System.Windows Api の部分的な名前空間の修飾をサポートしなくなりました</span><span class="sxs-lookup"><span data-stu-id="a03ef-101">VB.NET no longer supports partial namespace qualification for System.Windows APIs</span></span>

#### <a name="details"></a><span data-ttu-id="a03ef-102">説明</span><span class="sxs-lookup"><span data-stu-id="a03ef-102">Details</span></span>

<span data-ttu-id="a03ef-103">.NET Framework 4.5.2 以降では、VB.NET プロジェクトは、部分的に修飾された名前空間で System.Windows API を指定できません。</span><span class="sxs-lookup"><span data-stu-id="a03ef-103">Beginning in .NET Framework 4.5.2, VB.NET projects cannot specify System.Windows APIs with partially-qualified namespaces.</span></span> <span data-ttu-id="a03ef-104">たとえば、`Windows.Forms.DialogResult` の参照は失敗します。</span><span class="sxs-lookup"><span data-stu-id="a03ef-104">For example, referring to `Windows.Forms.DialogResult` will fail.</span></span> <span data-ttu-id="a03ef-105">代わりに、コードは、完全修飾名 (<xref:System.Windows.Forms.DialogResult>) を参照するか、特定の名前空間をインポートして、<xref:System.Windows.Forms.DialogResult?displayProperty=fullName> を参照する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a03ef-105">Instead, code must refer to the fully qualified name (<xref:System.Windows.Forms.DialogResult>) or import the specific namespace and refer simply to <xref:System.Windows.Forms.DialogResult?displayProperty=fullName>.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="a03ef-106">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="a03ef-106">Suggestion</span></span>

<span data-ttu-id="a03ef-107">`System.Windows` API を単純な名前で参照するか (および関連する名前空間をインポートする)、完全修飾名で参照するように、コードを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a03ef-107">Code should be updated to refer to `System.Windows` APIs either with simple names (and importing the relevant namespace) or with fully qualified names.</span></span>

| <span data-ttu-id="a03ef-108">名前</span><span class="sxs-lookup"><span data-stu-id="a03ef-108">Name</span></span>    | <span data-ttu-id="a03ef-109">[値]</span><span class="sxs-lookup"><span data-stu-id="a03ef-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="a03ef-110">スコープ</span><span class="sxs-lookup"><span data-stu-id="a03ef-110">Scope</span></span>   | <span data-ttu-id="a03ef-111">マイナー</span><span class="sxs-lookup"><span data-stu-id="a03ef-111">Minor</span></span>       |
| <span data-ttu-id="a03ef-112">バージョン</span><span class="sxs-lookup"><span data-stu-id="a03ef-112">Version</span></span> | <span data-ttu-id="a03ef-113">4.5.2</span><span class="sxs-lookup"><span data-stu-id="a03ef-113">4.5.2</span></span>       |
| <span data-ttu-id="a03ef-114">種類</span><span class="sxs-lookup"><span data-stu-id="a03ef-114">Type</span></span>    | <span data-ttu-id="a03ef-115">再ターゲット中</span><span class="sxs-lookup"><span data-stu-id="a03ef-115">Retargeting</span></span> |
