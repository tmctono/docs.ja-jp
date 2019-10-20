---
ms.openlocfilehash: 3d0a90a57c2b1c2759b8420e74c284668d54e9cb
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2019
ms.locfileid: "72526757"
---
### <a name="duplicated-apis-removed-from-windows-forms"></a><span data-ttu-id="25854-101">Windows フォームからの重複する API の削除</span><span class="sxs-lookup"><span data-stu-id="25854-101">Duplicated APIs removed from Windows Forms</span></span>

<span data-ttu-id="25854-102">.NET Core 3.0 Preview 4 以降、<xref:System.Windows.Forms?displayProperty=fullName> 名前空間で誤って重複していた多数の API が .NET Core 3.0 RC1 で削除されました。</span><span class="sxs-lookup"><span data-stu-id="25854-102">A number of APIs accidentally duplicated in the <xref:System.Windows.Forms?displayProperty=fullName> namespace starting in .NET Core 3.0 Preview 4 have been removed in .NET Core 3.0 RC1.</span></span>

#### <a name="change-description"></a><span data-ttu-id="25854-103">変更の説明</span><span class="sxs-lookup"><span data-stu-id="25854-103">Change description</span></span>

<span data-ttu-id="25854-104">.NET Core 3.0 Preview 4 には、<xref:System.ComponentModel.Design?displayProperty=fullName> 名前空間に既にある <xref:System.Windows.Forms?displayProperty=fullName> 名前空間の複数の型が、誤って重複しています。</span><span class="sxs-lookup"><span data-stu-id="25854-104">.NET Core 3.0 Preview 4 inadvertently duplicated a number of types in the <xref:System.Windows.Forms?displayProperty=fullName> namespace that already existed in the <xref:System.ComponentModel.Design?displayProperty=fullName> namespace.</span></span> <span data-ttu-id="25854-105">.NET Core 3.0 RC1 以降、重複するこれらの型はなくなります。</span><span class="sxs-lookup"><span data-stu-id="25854-105">Starting with .NET Core 3.0 RC1, these duplicated types are no longer available.</span></span> <span data-ttu-id="25854-106">次の表に、元の型とその重複する型の一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="25854-106">The following table shows lists the original type and its duplicated type:</span></span>

|<span data-ttu-id="25854-107">元の型</span><span class="sxs-lookup"><span data-stu-id="25854-107">Original type</span></span>|<span data-ttu-id="25854-108">重複する型</span><span class="sxs-lookup"><span data-stu-id="25854-108">Duplicated type</span></span>|
|---|---|
|<xref:System.ComponentModel.Design.DesignerActionListsChangedEventArgs?displayProperty=fullName>|`System.Windows.Forms.DesignerActionListsChangedEventArgs`|
|<xref:System.ComponentModel.Design.DesignerActionListsChangedEventHandler?displayProperty=fullName>|`System.Windows.Forms.DesignerActionListsChangedEventHandler`|
|<xref:System.ComponentModel.Design.DesignerActionListsChangedType?displayProperty=fullName>|`System.Windows.Forms.DesignerActionListsChangedType`|
|<xref:System.ComponentModel.Design.DesignerActionUIService?displayProperty=fullName>|`System.Windows.Forms.DesignerActionUIService`|
|<xref:System.ComponentModel.Design.DesignerCommandSet?displayProperty=fullName>|`System.Windows.Forms.DesignerCommandSet`|

#### <a name="version-introduced"></a><span data-ttu-id="25854-109">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="25854-109">Version introduced</span></span>

<span data-ttu-id="25854-110">3.0 RC1</span><span class="sxs-lookup"><span data-stu-id="25854-110">3.0 RC1</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="25854-111">推奨される操作</span><span class="sxs-lookup"><span data-stu-id="25854-111">Recommended action</span></span>

<span data-ttu-id="25854-112">元の型を参照するように、表の「**元の型**」列のとおりコードを更新してください。</span><span class="sxs-lookup"><span data-stu-id="25854-112">Update the code to reference the original type, as shown in the **Original type** column of the table.</span></span>

#### <a name="category"></a><span data-ttu-id="25854-113">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="25854-113">Category</span></span>

<span data-ttu-id="25854-114">Windows フォーム</span><span class="sxs-lookup"><span data-stu-id="25854-114">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="25854-115">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="25854-115">Affected APIs</span></span>

- <span data-ttu-id="25854-116">API 分析では検出できません。</span><span class="sxs-lookup"><span data-stu-id="25854-116">Not detectable via API analysis.</span></span>

<!--

### Affected APIs

- Not detectable via API analysis.

-->
