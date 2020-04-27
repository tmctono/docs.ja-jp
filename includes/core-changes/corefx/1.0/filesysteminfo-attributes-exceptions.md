---
ms.openlocfilehash: 2ea9abca7578c2ddf92712a1c597f8f1ff4a5c0c
ms.sourcegitcommit: 348bb052d5cef109a61a3d5253faa5d7167d55ac
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "82021820"
---
### <a name="unauthorizedaccessexception-thrown-by-filesysteminfoattributes"></a><span data-ttu-id="e7f74-101">FileSystemInfo.Attributes によってスローされる UnauthorizedAccessException</span><span class="sxs-lookup"><span data-stu-id="e7f74-101">UnauthorizedAccessException thrown by FileSystemInfo.Attributes</span></span>

<span data-ttu-id="e7f74-102">.NET Core では、呼び出し元がファイル属性値を設定しようとして、書き込みアクセス許可がない場合、<xref:System.UnauthorizedAccessException> がスローされます。</span><span class="sxs-lookup"><span data-stu-id="e7f74-102">In .NET Core, an <xref:System.UnauthorizedAccessException> is thrown when the caller attempts to set a file attribute value but doesn't have write permission.</span></span>

#### <a name="change-description"></a><span data-ttu-id="e7f74-103">変更の説明</span><span class="sxs-lookup"><span data-stu-id="e7f74-103">Change description</span></span>

<span data-ttu-id="e7f74-104">.NET Framework では、呼び出し元が <xref:System.IO.FileSystemInfo.Attributes?displayProperty=nameWithType> でファイル属性値を設定しようとして、書き込みアクセス許可がない場合、<xref:System.ArgumentException> がスローされます。</span><span class="sxs-lookup"><span data-stu-id="e7f74-104">In .NET Framework, an <xref:System.ArgumentException> is thrown when the caller attempts to set a file attribute value in <xref:System.IO.FileSystemInfo.Attributes?displayProperty=nameWithType> but doesn't have write permission.</span></span> <span data-ttu-id="e7f74-105">.NET Core では、代わりに <xref:System.UnauthorizedAccessException> がスローされます</span><span class="sxs-lookup"><span data-stu-id="e7f74-105">In .NET Core, an <xref:System.UnauthorizedAccessException> is thrown instead.</span></span> <span data-ttu-id="e7f74-106">(.NET Core では、呼び出し元が無効なファイル属性を設定しようとした場合でも <xref:System.ArgumentException> がスローされます)。</span><span class="sxs-lookup"><span data-stu-id="e7f74-106">(In .NET Core, an <xref:System.ArgumentException> is still thrown if the caller attempts to set an invalid file attribute.)</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="e7f74-107">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="e7f74-107">Version introduced</span></span>

<span data-ttu-id="e7f74-108">1</span><span class="sxs-lookup"><span data-stu-id="e7f74-108">1.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="e7f74-109">推奨アクション</span><span class="sxs-lookup"><span data-stu-id="e7f74-109">Recommended action</span></span>

<span data-ttu-id="e7f74-110">必要に応じて、<xref:System.ArgumentException> の代わりに、または追加として、<xref:System.UnauthorizedAccessException> をキャッチするように `catch` ステートメントを変更します。</span><span class="sxs-lookup"><span data-stu-id="e7f74-110">Modify any `catch` statements to catch an <xref:System.UnauthorizedAccessException> instead of, or in addition to, an <xref:System.ArgumentException>, as necessary.</span></span>

#### <a name="category"></a><span data-ttu-id="e7f74-111">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="e7f74-111">Category</span></span>

<span data-ttu-id="e7f74-112">Core .NET ライブラリ</span><span class="sxs-lookup"><span data-stu-id="e7f74-112">Core .NET libraries</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="e7f74-113">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="e7f74-113">Affected APIs</span></span>

- <xref:System.IO.FileSystemInfo.Attributes?displayProperty=nameWithType>

<!--

#### Affected APIs

- `P:System.IO.FileSystemInfo.Attributes`

-->
