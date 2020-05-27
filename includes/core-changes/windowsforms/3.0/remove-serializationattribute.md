---
ms.openlocfilehash: b35e99b1516c3236d07153cf0b69dae55a4bff7d
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2020
ms.locfileid: "83721178"
---
### <a name="serializableattribute-removed-from-some-windows-forms-types"></a><span data-ttu-id="e6dea-101">SerializableAttribute が一部の Windows フォーム型から削除された</span><span class="sxs-lookup"><span data-stu-id="e6dea-101">SerializableAttribute removed from some Windows Forms types</span></span>

<span data-ttu-id="e6dea-102"><xref:System.SerializableAttribute> が、既知のバイナリ シリアル化シナリオを持たない一部の Windows フォームのクラスから削除されています。</span><span class="sxs-lookup"><span data-stu-id="e6dea-102">The <xref:System.SerializableAttribute> has been removed from some Windows Forms classes that have no known binary serialization scenarios.</span></span>

#### <a name="change-description"></a><span data-ttu-id="e6dea-103">変更の説明</span><span class="sxs-lookup"><span data-stu-id="e6dea-103">Change description</span></span>

<span data-ttu-id="e6dea-104">次の型は .NET Framework では <xref:System.SerializableAttribute> で修飾されていますが、その属性は .NET Core では削除されています。</span><span class="sxs-lookup"><span data-stu-id="e6dea-104">The following types are decorated with the <xref:System.SerializableAttribute> in .NET Framework, but the attribute has been removed in .NET Core:</span></span>

- `System.InvariantComparer`
- <xref:System.ComponentModel.Design.ExceptionCollection?displayProperty=nameWithType>
- <xref:System.ComponentModel.Design.Serialization.CodeDomSerializerException?displayProperty=nameWithType>
- `System.ComponentModel.Design.Serialization.CodeDomComponentSerializationService.CodeDomSerializationStore`
- <xref:System.Drawing.Design.ToolboxItem?displayProperty=nameWithType>
- `System.Resources.ResXNullRef`
- `System.Resources.ResXDataNode`
- `System.Resources.ResXFileRef`
- <xref:System.Windows.Forms.Cursor?displayProperty=nameWithType>
- `System.Windows.Forms.NativeMethods.MSOCRINFOSTRUCT`
- `System.Windows.Forms.NativeMethods.MSG`

<span data-ttu-id="e6dea-105">従来、このシリアル化メカニズムには、メンテナンスとセキュリティに関して重大な問題がありました。</span><span class="sxs-lookup"><span data-stu-id="e6dea-105">Historically, this serialization mechanism has had serious maintenance and security concerns.</span></span> <span data-ttu-id="e6dea-106">型の `SerializableAttribute` を維持するということは、それらの型ではバージョン間でシリアル化の変更をテストする必要があることを意味し、場合にっよってはフレームワーク間でも必要です。</span><span class="sxs-lookup"><span data-stu-id="e6dea-106">Maintaining `SerializableAttribute` on types means those types must be tested for version-to-version serialization changes and potentially framework-to-framework serialization changes.</span></span> <span data-ttu-id="e6dea-107">これにより、それらの型を進化させることが難しくなり、保守コストが高くなる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e6dea-107">This makes it harder to evolve those types and can be costly to maintain.</span></span> <span data-ttu-id="e6dea-108">これらの型には既知のバイナリ シリアル化のシナリオがないため、属性を削除しても影響は最小限です。</span><span class="sxs-lookup"><span data-stu-id="e6dea-108">These types have no known binary serialization scenarios, which minimizes the impact of removing the attribute.</span></span>

<span data-ttu-id="e6dea-109">詳細については、「[バイナリ シリアル化](~/docs/standard/serialization/binary-serialization.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e6dea-109">For more information, see [Binary serialization](~/docs/standard/serialization/binary-serialization.md).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="e6dea-110">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="e6dea-110">Version introduced</span></span>

<span data-ttu-id="e6dea-111">3.0 Preview 9</span><span class="sxs-lookup"><span data-stu-id="e6dea-111">3.0 Preview 9</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="e6dea-112">推奨アクション</span><span class="sxs-lookup"><span data-stu-id="e6dea-112">Recommended action</span></span>

<span data-ttu-id="e6dea-113">これらの型に依存する可能性のあるすべてのコードを、シリアル化可能としてマークするように更新します。</span><span class="sxs-lookup"><span data-stu-id="e6dea-113">Update any code that may depend on these types being marked as serializable.</span></span>

#### <a name="category"></a><span data-ttu-id="e6dea-114">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="e6dea-114">Category</span></span>

<span data-ttu-id="e6dea-115">Windows フォーム</span><span class="sxs-lookup"><span data-stu-id="e6dea-115">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="e6dea-116">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="e6dea-116">Affected APIs</span></span>

- <span data-ttu-id="e6dea-117">なし</span><span class="sxs-lookup"><span data-stu-id="e6dea-117">None</span></span>

<!--

#### Affected APIs

- Not detectable via API analysis

-->
