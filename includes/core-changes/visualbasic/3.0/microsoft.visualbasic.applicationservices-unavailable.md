---
ms.openlocfilehash: 09027863ff2f0009a14578db35db870c27369726
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2020
ms.locfileid: "83721227"
---
### <a name="types-in-microsoftvisualbasicapplicationservices-namespace-not-available"></a><span data-ttu-id="26313-101">Microsoft.VisualBasic.ApplicationServices 名前空間の型は使用できません</span><span class="sxs-lookup"><span data-stu-id="26313-101">Types in Microsoft.VisualBasic.ApplicationServices namespace not available</span></span>

<span data-ttu-id="26313-102"><xref:Microsoft.VisualBasic.ApplicationServices?displayProperty=fullName> 名前空間の型は使用できません。</span><span class="sxs-lookup"><span data-stu-id="26313-102">The types in the <xref:Microsoft.VisualBasic.ApplicationServices?displayProperty=fullName> namespace are not available.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="26313-103">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="26313-103">Version introduced</span></span>

<span data-ttu-id="26313-104">.NET Core 3.0 Preview 8</span><span class="sxs-lookup"><span data-stu-id="26313-104">.NET Core 3.0 Preview 8</span></span>

#### <a name="change-description"></a><span data-ttu-id="26313-105">変更の説明</span><span class="sxs-lookup"><span data-stu-id="26313-105">Change description</span></span>

<span data-ttu-id="26313-106"><xref:Microsoft.VisualBasic.ApplicationServices?displayProperty=fullName> 名前空間の型は、一部の .NET Core 3.0 プレビュー リリースで使用できました。</span><span class="sxs-lookup"><span data-stu-id="26313-106">The types in the <xref:Microsoft.VisualBasic.ApplicationServices?displayProperty=fullName> namespace were available in some .NET Core 3.0 Preview releases.</span></span> <span data-ttu-id="26313-107">それらは、.NET Core 3.0 Preview 9 以降では使用できなくなりました。</span><span class="sxs-lookup"><span data-stu-id="26313-107">They are no longer available starting with .NET Core 3.0 Preview 9.</span></span>

<span data-ttu-id="26313-108">これらの型は、今後のリリースでの不要なアセンブリの依存関係や破壊的変更を回避するために削除されました。</span><span class="sxs-lookup"><span data-stu-id="26313-108">The types were removed to avoid unnecessary assembly dependencies or breaking changes in subsequent releases.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="26313-109">推奨アクション</span><span class="sxs-lookup"><span data-stu-id="26313-109">Recommended action</span></span>

<span data-ttu-id="26313-110">コードが <xref:Microsoft.VisualBasic.ApplicationServices> 型とそのメンバーの使用に依存している場合は、.NET クラス ライブラリ内の対応する型またはメンバーを使用できる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="26313-110">If your code depends on the use of <xref:Microsoft.VisualBasic.ApplicationServices> types and their members, you may be able to use a corresponding type or member in the .NET class library.</span></span> <span data-ttu-id="26313-111">たとえば、一部の <xref:System.Environment?displayProperty=nameWithType> および <xref:System.Security.Principal.WindowsIdentity?displayProperty=nameWithType> メンバーには、<xref:Microsoft.VisualBasic.ApplicationServices.User?displayProperty=nameWithType> クラスのプロパティと同等の機能が用意されています。</span><span class="sxs-lookup"><span data-stu-id="26313-111">For example, some <xref:System.Environment?displayProperty=nameWithType> and <xref:System.Security.Principal.WindowsIdentity?displayProperty=nameWithType> members provide equivalent functionality to the properties of the <xref:Microsoft.VisualBasic.ApplicationServices.User?displayProperty=nameWithType> class.</span></span>

#### <a name="category"></a><span data-ttu-id="26313-112">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="26313-112">Category</span></span>

<span data-ttu-id="26313-113">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="26313-113">Visual Basic</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="26313-114">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="26313-114">Affected APIs</span></span>

- <xref:Microsoft.VisualBasic.ApplicationServices?displayProperty=fullName>

<!--

#### Affected APIs

- `N:Microsoft.VisualBasic.ApplicationServices`

-->
