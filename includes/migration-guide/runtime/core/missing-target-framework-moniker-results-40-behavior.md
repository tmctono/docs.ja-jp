---
ms.openlocfilehash: 26a001ec2009a1a66dd9038b9bd3a42d7bcefb73
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620255"
---
### <a name="missing-target-framework-moniker-results-in-40-behavior"></a><span data-ttu-id="03206-101">ターゲット フレームワーク モニカーがないと、4.0 の動作になる</span><span class="sxs-lookup"><span data-stu-id="03206-101">Missing Target Framework Moniker results in 4.0 behavior</span></span>

#### <a name="details"></a><span data-ttu-id="03206-102">説明</span><span class="sxs-lookup"><span data-stu-id="03206-102">Details</span></span>

<span data-ttu-id="03206-103">アセンブリ レベルで <xref:System.Runtime.Versioning.TargetFrameworkAttribute?displayProperty=fullName> が適用されていないアプリケーションは、自動的に .NET Framework 4.0 のセマンティクス (quirks) を使用して実行します。</span><span class="sxs-lookup"><span data-stu-id="03206-103">Applications without a <xref:System.Runtime.Versioning.TargetFrameworkAttribute?displayProperty=fullName> applied at the assembly level will automatically run using the semantics (quirks) of the .NET Framework 4.0.</span></span> <span data-ttu-id="03206-104">高い品質を確保するには、すべてのバイナリを、ビルドされた .NET Framework のバージョンを示す <xref:System.Runtime.Versioning.TargetFrameworkAttribute?displayProperty=fullName> で明示的に属性指定することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="03206-104">To ensure high quality, it is recommended that all binaries be explicitly attributed with a <xref:System.Runtime.Versioning.TargetFrameworkAttribute?displayProperty=fullName> indicating the version of the .NET Framework they were built with.</span></span> <span data-ttu-id="03206-105">プロジェクト ファイルでターゲット フレームワーク モニカーを使用すると、MSBuid は <xref:System.Runtime.Versioning.TargetFrameworkAttribute?displayProperty=fullName> を自動的に適用します。</span><span class="sxs-lookup"><span data-stu-id="03206-105">Note that using a target framework moniker in a project file will cause MSBuild to automatically apply a <xref:System.Runtime.Versioning.TargetFrameworkAttribute?displayProperty=fullName>.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="03206-106">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="03206-106">Suggestion</span></span>

<span data-ttu-id="03206-107"><xref:System.Runtime.Versioning.TargetFrameworkAttribute?displayProperty=fullName> は、属性をアセンブリに直接追加するか、[プロジェクト ファイルで、または Visual Studio のプロジェクト プロパティ GUI](https://devblogs.microsoft.com/visualstudio/visual-studio-managed-multi-targeting-part-1-concepts-target-framework-moniker-target-framework/) でターゲット フレームワークを指定することによって指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="03206-107">A <xref:System.Runtime.Versioning.TargetFrameworkAttribute?displayProperty=fullName> should be supplied, either through adding the attribute directly to the assembly or by specifying a target framework in the [project file or through Visual Studio's project properties GUI](https://devblogs.microsoft.com/visualstudio/visual-studio-managed-multi-targeting-part-1-concepts-target-framework-moniker-target-framework/).</span></span>

| <span data-ttu-id="03206-108">名前</span><span class="sxs-lookup"><span data-stu-id="03206-108">Name</span></span>    | <span data-ttu-id="03206-109">[値]</span><span class="sxs-lookup"><span data-stu-id="03206-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="03206-110">スコープ</span><span class="sxs-lookup"><span data-stu-id="03206-110">Scope</span></span>   |<span data-ttu-id="03206-111">Major</span><span class="sxs-lookup"><span data-stu-id="03206-111">Major</span></span>|
|<span data-ttu-id="03206-112">バージョン</span><span class="sxs-lookup"><span data-stu-id="03206-112">Version</span></span>|<span data-ttu-id="03206-113">4.5</span><span class="sxs-lookup"><span data-stu-id="03206-113">4.5</span></span>|
|<span data-ttu-id="03206-114">種類</span><span class="sxs-lookup"><span data-stu-id="03206-114">Type</span></span>|<span data-ttu-id="03206-115">ランタイム</span><span class="sxs-lookup"><span data-stu-id="03206-115">Runtime</span></span>|
