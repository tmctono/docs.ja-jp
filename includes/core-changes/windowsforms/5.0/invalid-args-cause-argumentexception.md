---
ms.openlocfilehash: f1fc70075ef09a4f036c69788342c07ee51d72ce
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2020
ms.locfileid: "83702501"
---
### <a name="winforms-methods-now-throw-argumentexception"></a><span data-ttu-id="16d98-101">WinForms メソッドで ArgumentException がスローされるようになった</span><span class="sxs-lookup"><span data-stu-id="16d98-101">WinForms methods now throw ArgumentException</span></span>

<span data-ttu-id="16d98-102">一部の Windows フォーム メソッドで、無効な引数に対して <xref:System.ArgumentException> がスローされるようになりました。以前はスローされませんでした。</span><span class="sxs-lookup"><span data-stu-id="16d98-102">Some Windows Forms methods now throw an <xref:System.ArgumentException> for invalid arguments, where previously they did not.</span></span>

#### <a name="change-description"></a><span data-ttu-id="16d98-103">変更の説明</span><span class="sxs-lookup"><span data-stu-id="16d98-103">Change description</span></span>

<span data-ttu-id="16d98-104">以前は、予期しない型または不適切な型の引数を特定の Windows フォーム メソッドに渡すと、不確定な状態になりました。</span><span class="sxs-lookup"><span data-stu-id="16d98-104">Previously, passing arguments of an unexpected or incorrect type to certain Windows Forms methods would result in an indeterminate state.</span></span> <span data-ttu-id="16d98-105">.NET 5.0 以降では、そのようなメソッドに無効な引数を渡すと、<xref:System.ArgumentException> がスローされるようになりました。</span><span class="sxs-lookup"><span data-stu-id="16d98-105">Starting in .NET 5.0, these methods now throw an <xref:System.ArgumentException> when passed invalid arguments.</span></span>

<span data-ttu-id="16d98-106"><xref:System.ArgumentException> をスローすることは、.NET ランタイムの動作に準拠しています。</span><span class="sxs-lookup"><span data-stu-id="16d98-106">Throwing an <xref:System.ArgumentException> conforms to the behavior of the .NET runtime.</span></span> <span data-ttu-id="16d98-107">また、どの引数が無効であるのかが明確に伝えられることで、デバッグ エクスペリエンスも向上します。</span><span class="sxs-lookup"><span data-stu-id="16d98-107">It also improves the debugging experience by clearly communicating which argument is invalid.</span></span>

<span data-ttu-id="16d98-108">次の表では、影響を受けるメソッドとパラメーターを示します。</span><span class="sxs-lookup"><span data-stu-id="16d98-108">The following table lists the affected methods and parameters:</span></span>

| <span data-ttu-id="16d98-109">メソッド</span><span class="sxs-lookup"><span data-stu-id="16d98-109">Method</span></span> | <span data-ttu-id="16d98-110">パラメーター名</span><span class="sxs-lookup"><span data-stu-id="16d98-110">Parameter name</span></span> | <span data-ttu-id="16d98-111">条件</span><span class="sxs-lookup"><span data-stu-id="16d98-111">Condition</span></span> | <span data-ttu-id="16d98-112">追加されたバージョン</span><span class="sxs-lookup"><span data-stu-id="16d98-112">Version added</span></span> |
|-|-|-|
| <xref:System.Windows.Forms.TabControl.GetToolTipText(System.Object)?displayProperty=fullName> | `item` | <span data-ttu-id="16d98-113">引数が <xref:System.Windows.Forms.TabPage> 型ではありません。</span><span class="sxs-lookup"><span data-stu-id="16d98-113">Argument is not of type <xref:System.Windows.Forms.TabPage>.</span></span> | <span data-ttu-id="16d98-114">5.0 Preview 1</span><span class="sxs-lookup"><span data-stu-id="16d98-114">5.0 Preview 1</span></span> |

#### <a name="version-introduced"></a><span data-ttu-id="16d98-115">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="16d98-115">Version introduced</span></span>

<span data-ttu-id="16d98-116">.NET 5.0 Preview 1</span><span class="sxs-lookup"><span data-stu-id="16d98-116">.NET 5.0 Preview 1</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="16d98-117">推奨アクション</span><span class="sxs-lookup"><span data-stu-id="16d98-117">Recommended action</span></span>

- <span data-ttu-id="16d98-118">無効な引数を渡さないようにコードを更新します。</span><span class="sxs-lookup"><span data-stu-id="16d98-118">Update the code to prevent passing invalid arguments.</span></span>
- <span data-ttu-id="16d98-119">必要に応じて、メソッドを呼び出したときの <xref:System.ArgumentException> を処理します。</span><span class="sxs-lookup"><span data-stu-id="16d98-119">If necessary, handle an <xref:System.ArgumentException> when calling the method.</span></span>

#### <a name="category"></a><span data-ttu-id="16d98-120">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="16d98-120">Category</span></span>

<span data-ttu-id="16d98-121">Windows フォーム</span><span class="sxs-lookup"><span data-stu-id="16d98-121">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="16d98-122">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="16d98-122">Affected APIs</span></span>

- <xref:System.Windows.Forms.TabControl.GetToolTipText(System.Object)?displayProperty=fullName>

<!-- 

#### Affected APIs

- `M:System.Windows.Forms.TabControl.GetToolTipText(System.Object)`

-->
