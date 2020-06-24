---
ms.openlocfilehash: aab7d8538c875e35c832acc2a6c64beb84d4fb47
ms.sourcegitcommit: 1cbd77da54405ea7dba343ac0334fb03237d25d2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/11/2020
ms.locfileid: "84702444"
---
### <a name="winforms-methods-now-throw-argumentexception"></a><span data-ttu-id="dbd5e-101">WinForms メソッドで ArgumentException がスローされるようになった</span><span class="sxs-lookup"><span data-stu-id="dbd5e-101">WinForms methods now throw ArgumentException</span></span>

<span data-ttu-id="dbd5e-102">一部の Windows フォーム メソッドで、無効な引数に対して <xref:System.ArgumentException> がスローされるようになりました。以前はスローされませんでした。</span><span class="sxs-lookup"><span data-stu-id="dbd5e-102">Some Windows Forms methods now throw an <xref:System.ArgumentException> for invalid arguments, where previously they did not.</span></span>

#### <a name="change-description"></a><span data-ttu-id="dbd5e-103">変更の説明</span><span class="sxs-lookup"><span data-stu-id="dbd5e-103">Change description</span></span>

<span data-ttu-id="dbd5e-104">以前は、予期しない型または不適切な型の引数を特定の Windows フォーム メソッドに渡すと、不確定な状態になりました。</span><span class="sxs-lookup"><span data-stu-id="dbd5e-104">Previously, passing arguments of an unexpected or incorrect type to certain Windows Forms methods would result in an indeterminate state.</span></span> <span data-ttu-id="dbd5e-105">.NET 5.0 以降では、そのようなメソッドに無効な引数を渡すと、<xref:System.ArgumentException> がスローされるようになりました。</span><span class="sxs-lookup"><span data-stu-id="dbd5e-105">Starting in .NET 5.0, these methods now throw an <xref:System.ArgumentException> when passed invalid arguments.</span></span>

<span data-ttu-id="dbd5e-106"><xref:System.ArgumentException> をスローすることは、.NET ランタイムの動作に準拠しています。</span><span class="sxs-lookup"><span data-stu-id="dbd5e-106">Throwing an <xref:System.ArgumentException> conforms to the behavior of the .NET runtime.</span></span> <span data-ttu-id="dbd5e-107">また、どの引数が無効であるのかが明確に伝えられることで、デバッグ エクスペリエンスも向上します。</span><span class="sxs-lookup"><span data-stu-id="dbd5e-107">It also improves the debugging experience by clearly communicating which argument is invalid.</span></span>

<span data-ttu-id="dbd5e-108">次の表では、影響を受けるメソッドとパラメーターを示します。</span><span class="sxs-lookup"><span data-stu-id="dbd5e-108">The following table lists the affected methods and parameters:</span></span>

| <span data-ttu-id="dbd5e-109">メソッド</span><span class="sxs-lookup"><span data-stu-id="dbd5e-109">Method</span></span> | <span data-ttu-id="dbd5e-110">パラメーター名</span><span class="sxs-lookup"><span data-stu-id="dbd5e-110">Parameter name</span></span> | <span data-ttu-id="dbd5e-111">条件</span><span class="sxs-lookup"><span data-stu-id="dbd5e-111">Condition</span></span> | <span data-ttu-id="dbd5e-112">追加されたバージョン</span><span class="sxs-lookup"><span data-stu-id="dbd5e-112">Version added</span></span> |
|-|-|-|-|
| <xref:System.Windows.Forms.TabControl.GetToolTipText(System.Object)?displayProperty=fullName> | `item` | <span data-ttu-id="dbd5e-113">引数が <xref:System.Windows.Forms.TabPage> 型ではありません。</span><span class="sxs-lookup"><span data-stu-id="dbd5e-113">Argument is not of type <xref:System.Windows.Forms.TabPage>.</span></span> | <span data-ttu-id="dbd5e-114">5.0 Preview 1</span><span class="sxs-lookup"><span data-stu-id="dbd5e-114">5.0 Preview 1</span></span> |
| <xref:System.Windows.Forms.DataFormats.GetFormat(System.String)?displayProperty=fullName> | `format` | <span data-ttu-id="dbd5e-115">引数が `null`、<xref:System.String.Empty?displayProperty=nameWithType>、または空白です。</span><span class="sxs-lookup"><span data-stu-id="dbd5e-115">Argument is `null`, <xref:System.String.Empty?displayProperty=nameWithType>, or white space.</span></span> | <span data-ttu-id="dbd5e-116">5.0 Preview 5</span><span class="sxs-lookup"><span data-stu-id="dbd5e-116">5.0 Preview 5</span></span> |

#### <a name="version-introduced"></a><span data-ttu-id="dbd5e-117">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="dbd5e-117">Version introduced</span></span>

<span data-ttu-id="dbd5e-118">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="dbd5e-118">.NET 5.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="dbd5e-119">推奨アクション</span><span class="sxs-lookup"><span data-stu-id="dbd5e-119">Recommended action</span></span>

- <span data-ttu-id="dbd5e-120">無効な引数を渡さないようにコードを更新します。</span><span class="sxs-lookup"><span data-stu-id="dbd5e-120">Update the code to prevent passing invalid arguments.</span></span>
- <span data-ttu-id="dbd5e-121">必要に応じて、メソッドを呼び出したときの <xref:System.ArgumentException> を処理します。</span><span class="sxs-lookup"><span data-stu-id="dbd5e-121">If necessary, handle an <xref:System.ArgumentException> when calling the method.</span></span>

#### <a name="category"></a><span data-ttu-id="dbd5e-122">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="dbd5e-122">Category</span></span>

<span data-ttu-id="dbd5e-123">Windows フォーム</span><span class="sxs-lookup"><span data-stu-id="dbd5e-123">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="dbd5e-124">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="dbd5e-124">Affected APIs</span></span>

- <xref:System.Windows.Forms.TabControl.GetToolTipText(System.Object)?displayProperty=fullName>
- <xref:System.Windows.Forms.DataFormats.GetFormat(System.String)?displayProperty=fullName>

<!-- 

#### Affected APIs

- `M:System.Windows.Forms.TabControl.GetToolTipText(System.Object)`
- `M:System.Windows.Forms.DataFormats.GetFormat(System.String)`

-->
