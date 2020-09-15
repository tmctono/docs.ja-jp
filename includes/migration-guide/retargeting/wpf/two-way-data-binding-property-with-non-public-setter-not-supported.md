---
ms.openlocfilehash: 5f1a8af37a305ab0904801002dd99e17e8eca62e
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85616123"
---
### <a name="two-way-data-binding-to-a-property-with-a-non-public-setter-is-not-supported"></a><span data-ttu-id="d8457-101">非パブリック セッターを持つプロパティへの双方向データ バインドはサポートされません</span><span class="sxs-lookup"><span data-stu-id="d8457-101">Two-way data-binding to a property with a non-public setter is not supported</span></span>

#### <a name="details"></a><span data-ttu-id="d8457-102">説明</span><span class="sxs-lookup"><span data-stu-id="d8457-102">Details</span></span>

<span data-ttu-id="d8457-103">パブリック セッターを持たないプロパティへのデータ バインドを試みることは、サポートされるシナリオではありません。</span><span class="sxs-lookup"><span data-stu-id="d8457-103">Attempting to data bind to a property without a public setter has never been a supported scenario.</span></span> <span data-ttu-id="d8457-104">.NET framework 4.5.1 以降では、このシナリオでは <xref:System.InvalidOperationException?displayProperty=fullName> がスローされます。</span><span class="sxs-lookup"><span data-stu-id="d8457-104">Beginning in the .NET Framework 4.5.1, this scenario will throw an <xref:System.InvalidOperationException?displayProperty=fullName>.</span></span> <span data-ttu-id="d8457-105">この新しい例外は、具体的に .NET Framework 4.5.1 を対象とするアプリでのみスローされることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="d8457-105">Note that this new exception will only be thrown for apps that specifically target the .NET Framework 4.5.1.</span></span> <span data-ttu-id="d8457-106">アプリが .NET Framework 4.5 をターゲットとしている場合、この呼び出しは許されます。</span><span class="sxs-lookup"><span data-stu-id="d8457-106">If an app targets the .NET Framework 4.5, the call will be allowed.</span></span> <span data-ttu-id="d8457-107">アプリが特定のバージョンの .NET Framework をターゲットにしていない場合、バインドは一方向として扱われます。</span><span class="sxs-lookup"><span data-stu-id="d8457-107">If the app does not target a particular .NET Framework version, the binding will be treated as one-way.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="d8457-108">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="d8457-108">Suggestion</span></span>

<span data-ttu-id="d8457-109">一方向のバインドを使用するか、プロパティのセッターを公開するように、アプリを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d8457-109">The app should be updated to either use one-way binding, or expose the property's setter publicly.</span></span> <span data-ttu-id="d8457-110">または、.NET Framework 4.5 をターゲットにすると、アプリは以前の動作を示すようになります。</span><span class="sxs-lookup"><span data-stu-id="d8457-110">Alternatively, targeting the .NET Framework 4.5 will cause the app to exhibit the old behavior.</span></span>

| <span data-ttu-id="d8457-111">名前</span><span class="sxs-lookup"><span data-stu-id="d8457-111">Name</span></span>    | <span data-ttu-id="d8457-112">[値]</span><span class="sxs-lookup"><span data-stu-id="d8457-112">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="d8457-113">スコープ</span><span class="sxs-lookup"><span data-stu-id="d8457-113">Scope</span></span>   | <span data-ttu-id="d8457-114">マイナー</span><span class="sxs-lookup"><span data-stu-id="d8457-114">Minor</span></span>       |
| <span data-ttu-id="d8457-115">バージョン</span><span class="sxs-lookup"><span data-stu-id="d8457-115">Version</span></span> | <span data-ttu-id="d8457-116">4.5.1</span><span class="sxs-lookup"><span data-stu-id="d8457-116">4.5.1</span></span>       |
| <span data-ttu-id="d8457-117">種類</span><span class="sxs-lookup"><span data-stu-id="d8457-117">Type</span></span>    | <span data-ttu-id="d8457-118">再ターゲット中</span><span class="sxs-lookup"><span data-stu-id="d8457-118">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="d8457-119">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="d8457-119">Affected APIs</span></span>

- <xref:System.Windows.Data.BindingMode.TwoWay?displayProperty=nameWithType>
