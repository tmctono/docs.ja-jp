---
ms.openlocfilehash: 1ea2d70a7cfe04cc4c4b9b58ea6bb6fa0226b245
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2020
ms.locfileid: "83721548"
---
### <a name="change-of-access-for-accessibleobjectruntimeidfirstitem"></a><span data-ttu-id="fcbb0-101">AccessibleObject.RuntimeIDFirstItem のアクセスに対する変更</span><span class="sxs-lookup"><span data-stu-id="fcbb0-101">Change of access for AccessibleObject.RuntimeIDFirstItem</span></span>

<span data-ttu-id="fcbb0-102">.NET Core 3.0 RC1 以降、`AccessibleObject.RuntimeIDFirstItem` に対するアクセスが `protected` から `internal`に変更されました。</span><span class="sxs-lookup"><span data-stu-id="fcbb0-102">Starting in .NET Core 3.0 RC1, the accessibility of `AccessibleObject.RuntimeIDFirstItem` has changed from `protected` to `internal`.</span></span>

#### <a name="change-description"></a><span data-ttu-id="fcbb0-103">変更の説明</span><span class="sxs-lookup"><span data-stu-id="fcbb0-103">Change description</span></span>

<span data-ttu-id="fcbb0-104">.NET Core 3.0 Preview 4 以降、`AccessibleObject.RuntimeIDFirstItem` フィールドは `protected` でした。</span><span class="sxs-lookup"><span data-stu-id="fcbb0-104">Starting with .NET Core 3.0 Preview 4, the `AccessibleObject.RuntimeIDFirstItem` field was `protected`.</span></span> <span data-ttu-id="fcbb0-105">これは .NET Core 3.0 RC1 以降では、.NET Framework のフィールドと同じアクセスである `protected` から `internal` に変更されました。</span><span class="sxs-lookup"><span data-stu-id="fcbb0-105">Starting with .NET Core 3.0 RC1, it has changed from `protected` to `internal` to align with the accessibility of the field in the .NET Framework.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="fcbb0-106">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="fcbb0-106">Version introduced</span></span>

<span data-ttu-id="fcbb0-107">3.0 RC1</span><span class="sxs-lookup"><span data-stu-id="fcbb0-107">3.0 RC1</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="fcbb0-108">推奨アクション</span><span class="sxs-lookup"><span data-stu-id="fcbb0-108">Recommended action</span></span>

<span data-ttu-id="fcbb0-109">この変更は、開発した .NET Core アプリが、<xref:System.Windows.Forms.AccessibleObject> から派生し、`RuntimeIDFirstItem` フィールドにアクセスする型を使用している場合に影響がある可能性があります。</span><span class="sxs-lookup"><span data-stu-id="fcbb0-109">The change can affect you if you've developed a .NET Core app with a type that derives from <xref:System.Windows.Forms.AccessibleObject> and accesses the `RuntimeIDFirstItem` field.</span></span> <span data-ttu-id="fcbb0-110">この場合、次のようにローカル定数を定義してください。</span><span class="sxs-lookup"><span data-stu-id="fcbb0-110">If this is the case, you can define a local constant as follows:</span></span>

```csharp
const int RuntimeIDFirstItem = 0x2a;
```

#### <a name="category"></a><span data-ttu-id="fcbb0-111">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="fcbb0-111">Category</span></span>

<span data-ttu-id="fcbb0-112">Windows フォーム</span><span class="sxs-lookup"><span data-stu-id="fcbb0-112">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="fcbb0-113">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="fcbb0-113">Affected APIs</span></span>

- <span data-ttu-id="fcbb0-114">API 分析では検出できません。</span><span class="sxs-lookup"><span data-stu-id="fcbb0-114">Not detectable via API analysis.</span></span>

<!-- 

#### Affected APIs

- Not detectable via API analysis.

-->
