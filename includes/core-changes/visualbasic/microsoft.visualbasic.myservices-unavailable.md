---
ms.openlocfilehash: d61e4da187b3ede5e49fa80903d6e4c3b40578b9
ms.sourcegitcommit: 56f1d1203d0075a461a10a301459d3aa452f4f47
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2019
ms.locfileid: "71216284"
---
### <a name="types-in-microsoftvisualbasicmyservices-namespace-not-available"></a><span data-ttu-id="4f39b-101">Microsoft.VisualBasic.MyServices 名前空間の型は使用できません</span><span class="sxs-lookup"><span data-stu-id="4f39b-101">Types in Microsoft.VisualBasic.MyServices namespace not available</span></span>

<span data-ttu-id="4f39b-102"><xref:Microsoft.VisualBasic.MyServices?displayProperty=fullName> 名前空間の型は使用できません。</span><span class="sxs-lookup"><span data-stu-id="4f39b-102">The types in the <xref:Microsoft.VisualBasic.MyServices?displayProperty=fullName> namespace are not available.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="4f39b-103">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="4f39b-103">Version introduced</span></span>

<span data-ttu-id="4f39b-104">.NET Core 3.0 Preview 8</span><span class="sxs-lookup"><span data-stu-id="4f39b-104">.NET Core 3.0 Preview 8</span></span>

#### <a name="details"></a><span data-ttu-id="4f39b-105">説明</span><span class="sxs-lookup"><span data-stu-id="4f39b-105">Details</span></span>

<span data-ttu-id="4f39b-106"><xref:Microsoft.VisualBasic.MyServices?displayProperty=fullName> 名前空間の型は、一部の .NET Core 3.0 プレビュー リリースで使用できました。</span><span class="sxs-lookup"><span data-stu-id="4f39b-106">The types in the <xref:Microsoft.VisualBasic.MyServices?displayProperty=fullName> namespace were available in some .NET Core 3.0 Preview releases.</span></span> <span data-ttu-id="4f39b-107">それらは、.NET Core 3.0 Preview 9 以降では使用できなくなりました。</span><span class="sxs-lookup"><span data-stu-id="4f39b-107">They are no longer available starting with .NET Core 3.0 Preview 9.</span></span>

<span data-ttu-id="4f39b-108">これらの型は、今後のリリースでの不要なアセンブリの依存関係や破壊的変更を回避するために削除されました。</span><span class="sxs-lookup"><span data-stu-id="4f39b-108">The types were removed to avoid unnecessary assembly dependencies or breaking changes in subsequent releases.</span></span>
 
#### <a name="recommended-action"></a><span data-ttu-id="4f39b-109">推奨される操作</span><span class="sxs-lookup"><span data-stu-id="4f39b-109">Recommended action</span></span>

<span data-ttu-id="4f39b-110">コードが **Microsoft.VisualBasic.MyServices** 型とそのメンバーの使用に依存している場合は、.NET クラス ライブラリに、対応する型とメンバーがあります。</span><span class="sxs-lookup"><span data-stu-id="4f39b-110">If your code depends on the use of **Microsoft.VisualBasic.MyServices** types and their members, there are corresponding types and members in the .NET class library.</span></span> <span data-ttu-id="4f39b-111">**Microsoft.VisualBasic.MyServices** の型と、それと同等の .NET クラス ライブラリの型との対応を次に示します。</span><span class="sxs-lookup"><span data-stu-id="4f39b-111">The following is a mapping of  **Microsoft.VisualBasic.MyServices** types to their equivalent .NET class library types:</span></span>

|<span data-ttu-id="4f39b-112">Microsoft.VisualBasic.MyServices の型</span><span class="sxs-lookup"><span data-stu-id="4f39b-112">Microsoft.VisualBasic.MyServices type</span></span>|<span data-ttu-id="4f39b-113">.NET クラス ライブラリの型</span><span class="sxs-lookup"><span data-stu-id="4f39b-113">.NET class library type</span></span>|
|--|--|
|<xref:Microsoft.VisualBasic.MyServices.ClipboardProxy>|<span data-ttu-id="4f39b-114">WPF アプリケーションの場合は <xref:System.Windows.Clipboard?displayProperty=nameWithType>、Windows フォーム アプリケーションの場合は <xref:System.Windows.Forms.Clipboard?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="4f39b-114"><xref:System.Windows.Clipboard?displayProperty=nameWithType> for WPF applications, <xref:System.Windows.Forms.Clipboard?displayProperty=nameWithType> for Windows Forms applications</span></span>| 
|<xref:Microsoft.VisualBasic.MyServices.FileSystemProxy>|<span data-ttu-id="4f39b-115"><xref:System.IO> 名前空間の型</span><span class="sxs-lookup"><span data-stu-id="4f39b-115">Types in the <xref:System.IO> namespace</span></span>|
|<xref:Microsoft.VisualBasic.MyServices.RegistryProxy>|<span data-ttu-id="4f39b-116"><xref:Microsoft.Win32> 名前空間のレジストリ関連の型</span><span class="sxs-lookup"><span data-stu-id="4f39b-116">Registry-related types in the <xref:Microsoft.Win32> namespace</span></span>|
|<xref:Microsoft.VisualBasic.MyServices.SpecialDirectoriesProxy>|<xref:System.Environment.GetFolderPath%2A?displayProperty=nameWithType>|

#### <a name="category"></a><span data-ttu-id="4f39b-117">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="4f39b-117">Category</span></span>

<span data-ttu-id="4f39b-118">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4f39b-118">Visual Basic</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="4f39b-119">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="4f39b-119">Affected APIs</span></span>

- <xref:Microsoft.VisualBasic.MyServices?displayProperty=fullName>

<!--

### Affected APIs

- `N:Microsoft.VisualBasic.MyServices`

-- >

