---
ms.openlocfilehash: f42da00487735acdcc60f876c75e1dfd17103008
ms.sourcegitcommit: 1cbd77da54405ea7dba343ac0334fb03237d25d2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/11/2020
ms.locfileid: "84702445"
---
### <a name="winforms-properties-now-throw-argumentoutofrangeexception"></a><span data-ttu-id="23062-101">WinForms プロパティによる ArgumentOutOfRangeException のスロー</span><span class="sxs-lookup"><span data-stu-id="23062-101">WinForms properties now throw ArgumentOutOfRangeException</span></span>

<span data-ttu-id="23062-102">一部の Windows フォーム プロパティで、無効な引数に対して <xref:System.ArgumentOutOfRangeException> がスローされるようになりました。以前はスローされませんでした。</span><span class="sxs-lookup"><span data-stu-id="23062-102">Some Windows Forms properties now throw an <xref:System.ArgumentOutOfRangeException> for invalid arguments, where previously they did not.</span></span>

#### <a name="change-description"></a><span data-ttu-id="23062-103">変更の説明</span><span class="sxs-lookup"><span data-stu-id="23062-103">Change description</span></span>

<span data-ttu-id="23062-104">以前は、これらのプロパティでは、範囲外の引数が渡されたときに <xref:System.NullReferenceException>、<xref:System.IndexOutOfRangeException>、<xref:System.ArgumentException> などのさまざまな例外がスローされていました。</span><span class="sxs-lookup"><span data-stu-id="23062-104">Previously, these properties threw various exceptions, such as <xref:System.NullReferenceException>, <xref:System.IndexOutOfRangeException>, or <xref:System.ArgumentException>, when passed out-of-range arguments.</span></span> <span data-ttu-id="23062-105">.NET 5.0 以降、これらのプロパティでは、範囲外の引数が渡されたときに <xref:System.ArgumentOutOfRangeException> がスローされるようになりました。</span><span class="sxs-lookup"><span data-stu-id="23062-105">Starting in .NET 5.0, these properties now throw an <xref:System.ArgumentOutOfRangeException> when passed arguments that are out of range.</span></span>

<span data-ttu-id="23062-106"><xref:System.ArgumentOutOfRangeException> をスローすることは、.NET ランタイムの動作に準拠しています。</span><span class="sxs-lookup"><span data-stu-id="23062-106">Throwing an <xref:System.ArgumentOutOfRangeException> conforms to the behavior of the .NET runtime.</span></span> <span data-ttu-id="23062-107">また、どの引数が無効であるのかが明確に伝えられることで、デバッグ エクスペリエンスも向上します。</span><span class="sxs-lookup"><span data-stu-id="23062-107">It also improves the debugging experience by clearly communicating which argument is invalid.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="23062-108">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="23062-108">Version introduced</span></span>

<span data-ttu-id="23062-109">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="23062-109">.NET 5.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="23062-110">推奨アクション</span><span class="sxs-lookup"><span data-stu-id="23062-110">Recommended action</span></span>

- <span data-ttu-id="23062-111">無効な引数を渡さないようにコードを更新します。</span><span class="sxs-lookup"><span data-stu-id="23062-111">Update the code to prevent passing invalid arguments.</span></span>
- <span data-ttu-id="23062-112">必要に応じて、プロパティを設定するときに <xref:System.ArgumentOutOfRangeException> を処理します。</span><span class="sxs-lookup"><span data-stu-id="23062-112">If necessary, handle an <xref:System.ArgumentOutOfRangeException> when setting the property.</span></span>

#### <a name="category"></a><span data-ttu-id="23062-113">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="23062-113">Category</span></span>

<span data-ttu-id="23062-114">Windows フォーム</span><span class="sxs-lookup"><span data-stu-id="23062-114">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="23062-115">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="23062-115">Affected APIs</span></span>

<span data-ttu-id="23062-116">次の表に、影響を受けるプロパティとパラメーターの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="23062-116">The following table lists the affected properties and parameters:</span></span>

> [!div class="mx-tdBreakAll"]
> | <span data-ttu-id="23062-117">プロパティ</span><span class="sxs-lookup"><span data-stu-id="23062-117">Property</span></span> | <span data-ttu-id="23062-118">パラメーター名</span><span class="sxs-lookup"><span data-stu-id="23062-118">Parameter name</span></span> | <span data-ttu-id="23062-119">追加されたバージョン</span><span class="sxs-lookup"><span data-stu-id="23062-119">Version added</span></span> |
> |-|-|-|
> | <xref:System.Windows.Forms.ListBox.IntegerCollection.Item(System.Int32)?displayProperty=nameWithType> | `index` | <span data-ttu-id="23062-120">5.0 Preview 5</span><span class="sxs-lookup"><span data-stu-id="23062-120">5.0 Preview 5</span></span> |
> | <xref:System.Windows.Forms.TreeNode.ImageIndex?displayProperty=nameWithType> | `value` | <span data-ttu-id="23062-121">5.0 Preview 6</span><span class="sxs-lookup"><span data-stu-id="23062-121">5.0 Preview 6</span></span> |
> | <xref:System.Windows.Forms.TreeNode.SelectedImageIndex?displayProperty=nameWithType> | `value` | <span data-ttu-id="23062-122">5.0 Preview 6</span><span class="sxs-lookup"><span data-stu-id="23062-122">5.0 Preview 6</span></span> |

<!-- 

#### Affected APIs

- `P:System.Windows.Forms.ListBox.IntegerCollection.Item(System.Int32)`
- `P:System.Windows.Forms.TreeNode.ImageIndex`
- `P:System.Windows.Forms.TreeNode.SelectedImageIndex`

-->
