---
ms.openlocfilehash: 5083403a24a4a695d6970ef9c7a006796f41a86b
ms.sourcegitcommit: 97405ed212f69b0a32faa66a5d5fae7e76628b68
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2020
ms.locfileid: "91609300"
---
### <a name="mvc-objectmodelvalidator-calls-a-new-overload-of-validationvisitorvalidate"></a><span data-ttu-id="2b903-101">MVC:ObjectModelValidator は、ValidationVisitor.Validate の新しいオーバーロードを呼び出す</span><span class="sxs-lookup"><span data-stu-id="2b903-101">MVC: ObjectModelValidator calls a new overload of ValidationVisitor.Validate</span></span>

<span data-ttu-id="2b903-102">ASP.NET Core 5.0 で、<xref:Microsoft.AspNetCore.Mvc.ModelBinding.Validation.ValidationVisitor.Validate%2A?displayProperty=nameWithType> のオーバーロードが追加されました。</span><span class="sxs-lookup"><span data-stu-id="2b903-102">In ASP.NET Core 5.0, an overload of the <xref:Microsoft.AspNetCore.Mvc.ModelBinding.Validation.ValidationVisitor.Validate%2A?displayProperty=nameWithType> was added.</span></span> <span data-ttu-id="2b903-103">新しいオーバーロードは、次のプロパティを含む最上位レベルのモデル インスタンスを受け入れます。</span><span class="sxs-lookup"><span data-stu-id="2b903-103">The new overload accepts the top-level model instance that contains properties:</span></span>

```diff
  bool Validate(ModelMetadata metadata, string key, object model, bool alwaysValidateAtTopLevel);
+ bool Validate(ModelMetadata metadata, string key, object model, bool alwaysValidateAtTopLevel, object container);
```

<span data-ttu-id="2b903-104"><xref:Microsoft.AspNetCore.Mvc.ModelBinding.ObjectModelValidator> は検証を実行するためにこの `ValidationVisitor` の新しいオーバーロードを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="2b903-104"><xref:Microsoft.AspNetCore.Mvc.ModelBinding.ObjectModelValidator> invokes this new overload of `ValidationVisitor` to perform validation.</span></span> <span data-ttu-id="2b903-105">この新しいオーバーロードは、検証ライブラリが ASP.NET Core MVC のモデル検証システムと統合されている場合に関連します。</span><span class="sxs-lookup"><span data-stu-id="2b903-105">This new overload is pertinent if your validation library integrates with ASP.NET Core MVC's model validation system.</span></span>

<span data-ttu-id="2b903-106">ディスカッションについては、GitHub イシュー [dotnet/aspnetcore#26020](https://github.com/dotnet/aspnetcore/issues/26020) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2b903-106">For discussion, see GitHub issue [dotnet/aspnetcore#26020](https://github.com/dotnet/aspnetcore/issues/26020).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="2b903-107">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="2b903-107">Version introduced</span></span>

<span data-ttu-id="2b903-108">5.0</span><span class="sxs-lookup"><span data-stu-id="2b903-108">5.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="2b903-109">以前の動作</span><span class="sxs-lookup"><span data-stu-id="2b903-109">Old behavior</span></span>

<span data-ttu-id="2b903-110">`ObjectModelValidator` は、モデル検証中に、次のオーバーロードを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="2b903-110">`ObjectModelValidator` invokes the following overload during model validation:</span></span>

```csharp
ValidationVisitor.Validate(ModelMetadata metadata, string key, object model, bool alwaysValidateAtTopLevel)
```

#### <a name="new-behavior"></a><span data-ttu-id="2b903-111">新しい動作</span><span class="sxs-lookup"><span data-stu-id="2b903-111">New behavior</span></span>

<span data-ttu-id="2b903-112">`ObjectModelValidator` は、モデル検証中に、次のオーバーロードを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="2b903-112">`ObjectModelValidator` invokes the following overload during model validation:</span></span>

```csharp
ValidationVisitor.Validate(ModelMetadata metadata, string key, object model, bool alwaysValidateAtTopLevel, object container)
```

#### <a name="reason-for-change"></a><span data-ttu-id="2b903-113">変更理由</span><span class="sxs-lookup"><span data-stu-id="2b903-113">Reason for change</span></span>

<span data-ttu-id="2b903-114">この変更は、他のプロパティの検査に依存する、<xref:System.ComponentModel.DataAnnotations.CompareAttribute> などの検証コントロールをサポートするために導入されました。</span><span class="sxs-lookup"><span data-stu-id="2b903-114">This change was introduced to support validators, such as <xref:System.ComponentModel.DataAnnotations.CompareAttribute>, that rely on inspection of other properties.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="2b903-115">推奨アクション</span><span class="sxs-lookup"><span data-stu-id="2b903-115">Recommended action</span></span>

<span data-ttu-id="2b903-116">`ValidationVisitor` の既存のオーバーロードを呼び出すために `ObjectModelValidator` に依存する検証フレームワークは、.NET 5.0 以降を対象とする場合に、新しいメソッドをオーバーライドする必要があります。</span><span class="sxs-lookup"><span data-stu-id="2b903-116">Validation frameworks that rely on `ObjectModelValidator` to invoke the existing overload of `ValidationVisitor` must override the new method when targeting .NET 5.0 or later:</span></span>

```csharp
public class MyCustomValidationVisitor : ValidationVisitor
{
+  public override bool Validate(ModelMetadata metadata, string key, object model, bool alwaysValidateAtTopLevel, object container)
+  {
+    ...
}
```

#### <a name="category"></a><span data-ttu-id="2b903-117">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="2b903-117">Category</span></span>

<span data-ttu-id="2b903-118">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="2b903-118">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="2b903-119">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="2b903-119">Affected APIs</span></span>

<xref:Microsoft.AspNetCore.Mvc.ModelBinding.Validation.ValidationVisitor.Validate%2A?displayProperty=nameWithType>

<!--

#### Affected APIs

`Overload:Microsoft.AspNetCore.Mvc.ModelBinding.Validation.ValidationVisitor.Validate`

-->
