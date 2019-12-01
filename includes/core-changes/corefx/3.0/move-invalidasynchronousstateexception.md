---
ms.openlocfilehash: 82835915efa0e113e81bb09bd5062ee3252f2a64
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2019
ms.locfileid: "74568233"
---
### <a name="invalidasynchronousstateexception-moved-to-another-assembly"></a><span data-ttu-id="09a12-101">InvalidAsynchronousStateException が別のアセンブリに移動された</span><span class="sxs-lookup"><span data-stu-id="09a12-101">InvalidAsynchronousStateException moved to another assembly</span></span>

<span data-ttu-id="09a12-102"><xref:System.ComponentModel.InvalidAsynchronousStateException> クラスは移動されました。</span><span class="sxs-lookup"><span data-stu-id="09a12-102">The <xref:System.ComponentModel.InvalidAsynchronousStateException> class has been moved.</span></span>

#### <a name="change-description"></a><span data-ttu-id="09a12-103">変更の説明</span><span class="sxs-lookup"><span data-stu-id="09a12-103">Change description</span></span>

<span data-ttu-id="09a12-104">.NET Core 2.2 およびそれ以前のバージョンでは、<xref:System.ComponentModel.InvalidAsynchronousStateException> クラスは *System.ComponentModel.TypeConverter* アセンブリにあります。</span><span class="sxs-lookup"><span data-stu-id="09a12-104">In .NET Core 2.2 and earlier versions, the <xref:System.ComponentModel.InvalidAsynchronousStateException> class is found in the *System.ComponentModel.TypeConverter* assembly.</span></span>

<span data-ttu-id="09a12-105">.NET Core 3.0 以降では、*System.ComponentModel.Primitives* アセンブリに含まれています。</span><span class="sxs-lookup"><span data-stu-id="09a12-105">Starting with .NET Core 3.0, it is found in the *System.ComponentModel.Primitives* assembly.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="09a12-106">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="09a12-106">Version introduced</span></span>

<span data-ttu-id="09a12-107">3.0</span><span class="sxs-lookup"><span data-stu-id="09a12-107">3.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="09a12-108">推奨される操作</span><span class="sxs-lookup"><span data-stu-id="09a12-108">Recommended action</span></span>

<span data-ttu-id="09a12-109">この変更によって影響を受けるのは、リフレクションを使用し、<xref:System.Reflection.Assembly.GetType%2A?displayProperty=nameWithType> などのメソッドや、型が特定のアセンブリにあることを想定している <xref:System.Activator.CreateInstance%2A?displayProperty=nameWithType> のオーバーロードを呼び出すことによって、<xref:System.ComponentModel.InvalidAsynchronousStateException> を読み込んでいるアプリケーションのみです。</span><span class="sxs-lookup"><span data-stu-id="09a12-109">This change only affects applications that use reflection to load the <xref:System.ComponentModel.InvalidAsynchronousStateException> by calling a method such as <xref:System.Reflection.Assembly.GetType%2A?displayProperty=nameWithType> or an overload of <xref:System.Activator.CreateInstance%2A?displayProperty=nameWithType> that assumes the type is in a particular assembly.</span></span> <span data-ttu-id="09a12-110">その場合は、メソッドの呼び出しで参照されているアセンブリを、型の新しいアセンブリの場所を反映するように更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="09a12-110">If that is the case, the assembly the assembly referenced in the method call should be updated to reflect the type's new assembly location.</span></span>

#### <a name="category"></a><span data-ttu-id="09a12-111">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="09a12-111">Category</span></span>

<span data-ttu-id="09a12-112">CoreFx</span><span class="sxs-lookup"><span data-stu-id="09a12-112">CoreFx</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="09a12-113">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="09a12-113">Affected APIs</span></span>

- <span data-ttu-id="09a12-114">なし</span><span class="sxs-lookup"><span data-stu-id="09a12-114">None</span></span>

<!--

### Affected APIs

- Not detectable via API analysis

-->
