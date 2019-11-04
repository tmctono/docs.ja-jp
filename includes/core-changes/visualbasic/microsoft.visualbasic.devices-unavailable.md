---
ms.openlocfilehash: 4c47b95e98aca727d9f0eda54a167a71fd53afb9
ms.sourcegitcommit: 5a28f8eb071fcc09b045b0c4ae4b96898673192e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2019
ms.locfileid: "73198475"
---
### <a name="types-in-microsoftvisualbasicdevices-namespace-not-available"></a><span data-ttu-id="ff2de-101">Microsoft.VisualBasic.Devices 名前空間の型は使用できません</span><span class="sxs-lookup"><span data-stu-id="ff2de-101">Types in Microsoft.VisualBasic.Devices namespace not available</span></span>

<span data-ttu-id="ff2de-102"><xref:Microsoft.VisualBasic.Devices?displayProperty=fullName> 名前空間の型は使用できません。</span><span class="sxs-lookup"><span data-stu-id="ff2de-102">The types in the <xref:Microsoft.VisualBasic.Devices?displayProperty=fullName> namespace are not available.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="ff2de-103">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="ff2de-103">Version introduced</span></span>

<span data-ttu-id="ff2de-104">.NET Core 3.0 Preview 8</span><span class="sxs-lookup"><span data-stu-id="ff2de-104">.NET Core 3.0 Preview 8</span></span>

#### <a name="change-description"></a><span data-ttu-id="ff2de-105">変更の説明</span><span class="sxs-lookup"><span data-stu-id="ff2de-105">Change description</span></span>

<span data-ttu-id="ff2de-106"><xref:Microsoft.VisualBasic.Devices?displayProperty=fullName> 名前空間の型は、一部の .NET Core 3.0 プレビュー リリースで使用できました。</span><span class="sxs-lookup"><span data-stu-id="ff2de-106">The types in the <xref:Microsoft.VisualBasic.Devices?displayProperty=fullName> namespace were available in some .NET Core 3.0 Preview releases,.</span></span> <span data-ttu-id="ff2de-107">.NET Core 3.0 Preview 9 以降では使用できなくなりました。</span><span class="sxs-lookup"><span data-stu-id="ff2de-107">They are no longer available starting with .NET Core 3.0 Preview 9.</span></span>

<span data-ttu-id="ff2de-108">これらの型は、今後のリリースでの不要なアセンブリの依存関係や破壊的変更を回避するために削除されました。</span><span class="sxs-lookup"><span data-stu-id="ff2de-108">The types were removed to avoid unnecessary assembly dependencies or breaking changes in subsequent releases.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="ff2de-109">推奨される操作</span><span class="sxs-lookup"><span data-stu-id="ff2de-109">Recommended action</span></span>

<span data-ttu-id="ff2de-110">コードが <xref:Microsoft.VisualBasic.Devices> 型とそのメンバーの使用に依存している場合は、.NET クラス ライブラリ内の対応する型またはメンバーを使用できる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ff2de-110">If your code depends on the use of <xref:Microsoft.VisualBasic.Devices> types and their members, you may be able to use a corresponding type or member in the .NET class library.</span></span> <span data-ttu-id="ff2de-111">たとえば、<xref:Microsoft.VisualBasic.Devices.Clock?displayProperty=nameWithType> クラスと同等の機能は <xref:System.DateTime?displayProperty=nameWithType> および <xref:System.Environment?displayProperty=nameWithType> 型によって提供されており、<xref:Microsoft.VisualBasic.Devices.Ports?displayProperty=nameWithType> クラスと同等の機能は、<xref:System.IO.Ports?displayProperty=nameWithType> 名前空間の型によって提供されています。</span><span class="sxs-lookup"><span data-stu-id="ff2de-111">For example, equivalent functionality to the <xref:Microsoft.VisualBasic.Devices.Clock?displayProperty=nameWithType> class is provided by the <xref:System.DateTime?displayProperty=nameWithType> and <xref:System.Environment?displayProperty=nameWithType> types, and equivalent functionality to the <xref:Microsoft.VisualBasic.Devices.Ports?displayProperty=nameWithType> class is provided by types in the <xref:System.IO.Ports?displayProperty=nameWithType> namespace.</span></span>

#### <a name="category"></a><span data-ttu-id="ff2de-112">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="ff2de-112">Category</span></span>

<span data-ttu-id="ff2de-113">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ff2de-113">Visual Basic</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="ff2de-114">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="ff2de-114">Affected APIs</span></span>

- <xref:Microsoft.VisualBasic.Devices?displayProperty=fullName>

<!--

### Affected APIs

- `N:Microsoft.VisualBasic.Devices`

-- >

