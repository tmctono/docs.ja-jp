---
ms.openlocfilehash: e77312605ee367c159171e305d8f69429f9ac58b
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/15/2020
ms.locfileid: "90539598"
---
### <a name="identity-adddefaultui-method-overload-removed"></a>ID:AddDefaultUI メソッド オーバーロードが削除されました

ASP.NET Core 3.0 以降では、[IdentityBuilderUIExtensions.AddDefaultUI(IdentityBuilder,UIFramework)](/dotnet/api/microsoft.aspnetcore.identity.identitybuilderuiextensions.adddefaultui?view=aspnetcore-2.2#Microsoft_AspNetCore_Identity_IdentityBuilderUIExtensions_AddDefaultUI_Microsoft_AspNetCore_Identity_IdentityBuilder_Microsoft_AspNetCore_Identity_UI_UIFramework_) メソッド オーバーロードはなくなりました。

#### <a name="version-introduced"></a>導入されたバージョン

3.0

#### <a name="reason-for-change"></a>変更理由

この変更は、静的 Web アセット機能が導入された結果でした。

#### <a name="recommended-action"></a>推奨アクション

2 つの引数を取るオーバーロードの代わりに <xref:Microsoft.AspNetCore.Identity.IdentityBuilderUIExtensions.AddDefaultUI(Microsoft.AspNetCore.Identity.IdentityBuilder)?displayProperty=nameWithType> を呼び出します。 ブートストラップ 3 を使用している場合、プロジェクト ファイルの `<PropertyGroup>` 要素に次の行も追加します。

```xml
<IdentityUIFrameworkVersion>Bootstrap3</IdentityUIFrameworkVersion>
```

#### <a name="category"></a>カテゴリ

ASP.NET Core

#### <a name="affected-apis"></a>影響を受ける API

[IdentityBuilderUIExtensions.AddDefaultUI(IdentityBuilder,UIFramework)](/dotnet/api/microsoft.aspnetcore.identity.identitybuilderuiextensions.adddefaultui?view=aspnetcore-2.2#Microsoft_AspNetCore_Identity_IdentityBuilderUIExtensions_AddDefaultUI_Microsoft_AspNetCore_Identity_IdentityBuilder_Microsoft_AspNetCore_Identity_UI_UIFramework_)

<!--

#### Affected APIs

`M:Microsoft.AspNetCore.Identity.IdentityBuilderUIExtensions.AddDefaultUI(Microsoft.AspNetCore.Identity.IdentityBuilder,Microsoft.AspNetCore.Identity.UI.UIFramework)`

-->
