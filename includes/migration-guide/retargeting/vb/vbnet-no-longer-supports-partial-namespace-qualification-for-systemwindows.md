---
ms.openlocfilehash: 8db115a46df3fcea103e8fa6896542d0116aa256
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59236731"
---
### <a name="vbnet-no-longer-supports-partial-namespace-qualification-for-systemwindows-apis"></a><span data-ttu-id="a7878-101">VB.NET は、System.Windows Api の部分的な名前空間の修飾をサポートしなくなりました</span><span class="sxs-lookup"><span data-stu-id="a7878-101">VB.NET no longer supports partial namespace qualification for System.Windows APIs</span></span>

|   |   |
|---|---|
|<span data-ttu-id="a7878-102">説明</span><span class="sxs-lookup"><span data-stu-id="a7878-102">Details</span></span>|<span data-ttu-id="a7878-103">.NET Framework 4.5.2 以降では、VB.NET プロジェクトは、部分的に修飾された名前空間で System.Windows API を指定できません。</span><span class="sxs-lookup"><span data-stu-id="a7878-103">Beginning in .NET Framework 4.5.2, VB.NET projects cannot specify System.Windows APIs with partially-qualified namespaces.</span></span> <span data-ttu-id="a7878-104">たとえば、<code>Windows.Forms.DialogResult</code> の参照は失敗します。</span><span class="sxs-lookup"><span data-stu-id="a7878-104">For example, referring to <code>Windows.Forms.DialogResult</code> will fail.</span></span> <span data-ttu-id="a7878-105">代わりに、コードは、完全修飾名 (<xref:System.Windows.Forms.DialogResult>) を参照するか、特定の名前空間をインポートして、<xref:System.Windows.Forms.DialogResult?displayProperty=name> を参照する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a7878-105">Instead, code must refer to the fully qualified name (<xref:System.Windows.Forms.DialogResult>) or import the specific namespace and refer simply to <xref:System.Windows.Forms.DialogResult?displayProperty=name>.</span></span>|
|<span data-ttu-id="a7878-106">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="a7878-106">Suggestion</span></span>|<span data-ttu-id="a7878-107"><code>System.Windows</code> API を単純な名前で参照するか (および関連する名前空間をインポートする)、完全修飾名で参照するように、コードを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a7878-107">Code should be updated to refer to <code>System.Windows</code> APIs either with simple names (and importing the relevant namespace) or with fully qualified names.</span></span>|
|<span data-ttu-id="a7878-108">スコープ</span><span class="sxs-lookup"><span data-stu-id="a7878-108">Scope</span></span>|<span data-ttu-id="a7878-109">マイナー</span><span class="sxs-lookup"><span data-stu-id="a7878-109">Minor</span></span>|
|<span data-ttu-id="a7878-110">Version</span><span class="sxs-lookup"><span data-stu-id="a7878-110">Version</span></span>|<span data-ttu-id="a7878-111">4.5.2</span><span class="sxs-lookup"><span data-stu-id="a7878-111">4.5.2</span></span>|
|<span data-ttu-id="a7878-112">型</span><span class="sxs-lookup"><span data-stu-id="a7878-112">Type</span></span>|<span data-ttu-id="a7878-113">再ターゲット中</span><span class="sxs-lookup"><span data-stu-id="a7878-113">Retargeting</span></span>|
