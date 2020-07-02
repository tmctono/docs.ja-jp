---
ms.openlocfilehash: 2d0798917b639bc90bf3f78f6fb9f19d0eaf2c71
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614821"
---
### <a name="incorrect-implementation-of-memberdescriptorequals"></a><span data-ttu-id="565a9-101">MemberDescriptor.Equals の不適切な実装</span><span class="sxs-lookup"><span data-stu-id="565a9-101">Incorrect implementation of MemberDescriptor.Equals</span></span>

#### <a name="details"></a><span data-ttu-id="565a9-102">説明</span><span class="sxs-lookup"><span data-stu-id="565a9-102">Details</span></span>

<span data-ttu-id="565a9-103"><xref:System.ComponentModel.MemberDescriptor.Equals%2A?displayProperty=nameWithType> メソッドの元の実装によって、比較対象のオブジェクトからの 2 つの異なる文字列プロパティである、カテゴリ名と説明文字列が比較されます。</span><span class="sxs-lookup"><span data-stu-id="565a9-103">The original implementation of the <xref:System.ComponentModel.MemberDescriptor.Equals%2A?displayProperty=nameWithType> method compares two different string properties from the objects being compared: the category name and the description string.</span></span> <span data-ttu-id="565a9-104">この修正は、最初のオブジェクトの <xref:System.ComponentModel.MemberDescriptor.Category> と 2 番目のオブジェクトの <xref:System.ComponentModel.MemberDescriptor.Category> を比較し、最初のオブジェクトの <xref:System.ComponentModel.MemberDescriptor.Description> と 2 番目のオブジェクトの <xref:System.ComponentModel.MemberDescriptor.Description> を比較するものです。</span><span class="sxs-lookup"><span data-stu-id="565a9-104">The fix is to compare the <xref:System.ComponentModel.MemberDescriptor.Category> of the first object to the <xref:System.ComponentModel.MemberDescriptor.Category> of the second one, and the <xref:System.ComponentModel.MemberDescriptor.Description> of the first to the <xref:System.ComponentModel.MemberDescriptor.Description> of the second.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="565a9-105">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="565a9-105">Suggestion</span></span>

<span data-ttu-id="565a9-106">記述子が等しいときに `false` を返すことがある <xref:System.ComponentModel.MemberDescriptor.Equals%2A?displayProperty=nameWithType> にアプリケーションが依存しているとき、.NET Framework のバージョン 4.6.2 以降を対象とする場合、いくつかの選択肢があります。</span><span class="sxs-lookup"><span data-stu-id="565a9-106">If your application depends on <xref:System.ComponentModel.MemberDescriptor.Equals%2A?displayProperty=nameWithType> sometimes returning `false` when descriptors are equivalent, and you are targeting the .NET Framework 4.6.2 or later, you have several options:</span></span>

- <span data-ttu-id="565a9-107">コードを変更し、<xref:System.ComponentModel.MemberDescriptor.Equals%2A?displayProperty=nameWithType> メソッドの呼び出しに加え、<xref:System.ComponentModel.MemberDescriptor.Category> フィールドと <xref:System.ComponentModel.MemberDescriptor.Description> フィールドを手動で比較します。</span><span class="sxs-lookup"><span data-stu-id="565a9-107">Make code changes to compare the <xref:System.ComponentModel.MemberDescriptor.Category> and <xref:System.ComponentModel.MemberDescriptor.Description> fields manually in addition to calling the <xref:System.ComponentModel.MemberDescriptor.Equals%2A?displayProperty=nameWithType> method.</span></span>
- <span data-ttu-id="565a9-108">app.config ファイルに次の値を追加し、この変更を無効にします。</span><span class="sxs-lookup"><span data-stu-id="565a9-108">Opt out of this change by adding the following value to the app.config file:</span></span>

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.MemberDescriptorEqualsReturnsFalseIfEquivalent=true" />
</runtime>
```

<span data-ttu-id="565a9-109">アプリケーションの対象が .NET Framework 4.6.1 以前であるが .NET Framework 4.6.2 以降で実行しているとき、この変更を有効にする場合、app.config ファイルに次の値を追加することで互換性スイッチを `false` に設定します。</span><span class="sxs-lookup"><span data-stu-id="565a9-109">If your application targets .NET Framework 4.6.1 or earlier and is running on the .NET Framework 4.6.2 or later and you want this change enabled, you can set the compatibility switch to `false` by adding the following value to the app.config file:</span></span>

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.MemberDescriptorEqualsReturnsFalseIfEquivalent=false" />
</runtime>
```

| <span data-ttu-id="565a9-110">名前</span><span class="sxs-lookup"><span data-stu-id="565a9-110">Name</span></span>    | <span data-ttu-id="565a9-111">値</span><span class="sxs-lookup"><span data-stu-id="565a9-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="565a9-112">スコープ</span><span class="sxs-lookup"><span data-stu-id="565a9-112">Scope</span></span>   | <span data-ttu-id="565a9-113">エッジ</span><span class="sxs-lookup"><span data-stu-id="565a9-113">Edge</span></span>        |
| <span data-ttu-id="565a9-114">バージョン</span><span class="sxs-lookup"><span data-stu-id="565a9-114">Version</span></span> | <span data-ttu-id="565a9-115">4.6.2</span><span class="sxs-lookup"><span data-stu-id="565a9-115">4.6.2</span></span>       |
| <span data-ttu-id="565a9-116">種類</span><span class="sxs-lookup"><span data-stu-id="565a9-116">Type</span></span>    | <span data-ttu-id="565a9-117">再ターゲット中</span><span class="sxs-lookup"><span data-stu-id="565a9-117">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="565a9-118">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="565a9-118">Affected APIs</span></span>

- <xref:System.ComponentModel.MemberDescriptor.Equals(System.Object)?displayProperty=nameWithType>
