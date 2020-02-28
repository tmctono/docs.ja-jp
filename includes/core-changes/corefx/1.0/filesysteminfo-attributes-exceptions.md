---
ms.openlocfilehash: 4091bdcf7d9ed8872aed5faa6e6d3ed143903787
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "77449404"
---
### <a name="unauthorizedaccessexception-thrown-by-filesysteminfoattributes"></a><span data-ttu-id="ad02d-101">FileSystemInfo.Attributes によってスローされる UnauthorizedAccessException</span><span class="sxs-lookup"><span data-stu-id="ad02d-101">UnauthorizedAccessException thrown by FileSystemInfo.Attributes</span></span>

<span data-ttu-id="ad02d-102">.NET Core では、呼び出し元がファイル属性値を設定しようとして、書き込みアクセス許可がない場合、<xref:System.UnauthorizedAccessException> がスローされます。</span><span class="sxs-lookup"><span data-stu-id="ad02d-102">In .NET Core, an <xref:System.UnauthorizedAccessException> is thrown when the caller attempts to set a file attribute value but doesn't have write permission.</span></span>

#### <a name="change-description"></a><span data-ttu-id="ad02d-103">変更の説明</span><span class="sxs-lookup"><span data-stu-id="ad02d-103">Change description</span></span>

<span data-ttu-id="ad02d-104">.NET Framework では、呼び出し元が <xref:System.IO.FileSystemInfo.Attributes?displayProperty=nameWithType> でファイル属性値を設定しようとして、書き込みアクセス許可がない場合、<xref:System.ArgumentException> がスローされます。</span><span class="sxs-lookup"><span data-stu-id="ad02d-104">In .NET Framework, an <xref:System.ArgumentException> is thrown when the caller attempts to set a file attribute value in <xref:System.IO.FileSystemInfo.Attributes?displayProperty=nameWithType> but doesn't have write permission.</span></span> <span data-ttu-id="ad02d-105">.NET Core では、代わりに <xref:System.UnauthorizedAccessException> がスローされます</span><span class="sxs-lookup"><span data-stu-id="ad02d-105">In .NET Core, an <xref:System.UnauthorizedAccessException> is thrown instead.</span></span> <span data-ttu-id="ad02d-106">(.NET Core では、呼び出し元が無効なファイル属性を設定しようとした場合でも <xref:System.ArgumentException> がスローされます)。</span><span class="sxs-lookup"><span data-stu-id="ad02d-106">(In .NET Core, an <xref:System.ArgumentException> is still thrown if the caller attempts to set an invalid file attribute.)</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="ad02d-107">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="ad02d-107">Version introduced</span></span>

<span data-ttu-id="ad02d-108">1</span><span class="sxs-lookup"><span data-stu-id="ad02d-108">1.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="ad02d-109">推奨アクション</span><span class="sxs-lookup"><span data-stu-id="ad02d-109">Recommended action</span></span>

<span data-ttu-id="ad02d-110">必要に応じて、<xref:System.ArgumentException> の代わりに、または追加として、<xref:System.UnauthorizedAccessException> をキャッチするように `catch` ステートメントを変更します。</span><span class="sxs-lookup"><span data-stu-id="ad02d-110">Modify any `catch` statements to catch an <xref:System.UnauthorizedAccessException> instead of, or in addition to, an <xref:System.ArgumentException>, as necessary.</span></span>

#### <a name="category"></a><span data-ttu-id="ad02d-111">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="ad02d-111">Category</span></span>

<span data-ttu-id="ad02d-112">CoreFx</span><span class="sxs-lookup"><span data-stu-id="ad02d-112">CoreFx</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="ad02d-113">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="ad02d-113">Affected APIs</span></span>

- <xref:System.IO.FileSystemInfo.Attributes?displayProperty=nameWithType>

<!--

#### Affected APIs

- `P:System.IO.FileSystemInfo.Attributes`

-->
