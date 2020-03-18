---
ms.openlocfilehash: d8cc506d60f3c24087ebde8ead345656fea0f484
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2020
ms.locfileid: "76116339"
---
### <a name="types-in-microsoftvisualbasicapplicationservices-namespace-not-available"></a><span data-ttu-id="91274-101">Microsoft.VisualBasic.ApplicationServices 名前空間の型は使用できません</span><span class="sxs-lookup"><span data-stu-id="91274-101">Types in Microsoft.VisualBasic.ApplicationServices namespace not available</span></span>

<span data-ttu-id="91274-102"><xref:Microsoft.VisualBasic.ApplicationServices?displayProperty=fullName> 名前空間の型は使用できません。</span><span class="sxs-lookup"><span data-stu-id="91274-102">The types in the <xref:Microsoft.VisualBasic.ApplicationServices?displayProperty=fullName> namespace are not available.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="91274-103">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="91274-103">Version introduced</span></span>

<span data-ttu-id="91274-104">.NET Core 3.0 Preview 8</span><span class="sxs-lookup"><span data-stu-id="91274-104">.NET Core 3.0 Preview 8</span></span>

#### <a name="change-description"></a><span data-ttu-id="91274-105">変更の説明</span><span class="sxs-lookup"><span data-stu-id="91274-105">Change description</span></span>

<span data-ttu-id="91274-106"><xref:Microsoft.VisualBasic.ApplicationServices?displayProperty=fullName> 名前空間の型は、一部の .NET Core 3.0 プレビュー リリースで使用できました。</span><span class="sxs-lookup"><span data-stu-id="91274-106">The types in the <xref:Microsoft.VisualBasic.ApplicationServices?displayProperty=fullName> namespace were available in some .NET Core 3.0 Preview releases.</span></span> <span data-ttu-id="91274-107">それらは、.NET Core 3.0 Preview 9 以降では使用できなくなりました。</span><span class="sxs-lookup"><span data-stu-id="91274-107">They are no longer available starting with .NET Core 3.0 Preview 9.</span></span>

<span data-ttu-id="91274-108">これらの型は、今後のリリースでの不要なアセンブリの依存関係や破壊的変更を回避するために削除されました。</span><span class="sxs-lookup"><span data-stu-id="91274-108">The types were removed to avoid unnecessary assembly dependencies or breaking changes in subsequent releases.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="91274-109">推奨アクション</span><span class="sxs-lookup"><span data-stu-id="91274-109">Recommended action</span></span>

<span data-ttu-id="91274-110">コードが <xref:Microsoft.VisualBasic.ApplicationServices> 型とそのメンバーの使用に依存している場合は、.NET クラス ライブラリ内の対応する型またはメンバーを使用できる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="91274-110">If your code depends on the use of <xref:Microsoft.VisualBasic.ApplicationServices> types and their members, you may be able to use a corresponding type or member in the .NET class library.</span></span> <span data-ttu-id="91274-111">たとえば、一部の <xref:System.Environment?displayProperty=nameWithType> および <xref:System.Security.Principal.WindowsIdentity?displayProperty=nameWithType> メンバーには、<xref:Microsoft.VisualBasic.ApplicationServices.User?displayProperty=nameWithType> クラスのプロパティと同等の機能が用意されています。</span><span class="sxs-lookup"><span data-stu-id="91274-111">For example, some <xref:System.Environment?displayProperty=nameWithType> and <xref:System.Security.Principal.WindowsIdentity?displayProperty=nameWithType> members provide equivalent functionality to the properties of the <xref:Microsoft.VisualBasic.ApplicationServices.User?displayProperty=nameWithType> class.</span></span>

#### <a name="category"></a><span data-ttu-id="91274-112">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="91274-112">Category</span></span>

<span data-ttu-id="91274-113">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="91274-113">Visual Basic</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="91274-114">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="91274-114">Affected APIs</span></span>

- <xref:Microsoft.VisualBasic.ApplicationServices?displayProperty=fullName>

<!--

### Affected APIs

- `N:Microsoft.VisualBasic.ApplicationServices`

-->
