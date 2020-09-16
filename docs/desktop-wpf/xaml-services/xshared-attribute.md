---
title: x:Shared 属性
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [XAML Services], x:Shared attribute
- x:Shared attribute [XAML Services]
- Shared attribute in XAML [XAML Services]
ms.assetid: c8cff434-2785-405f-9f95-16deb34c9e64
ms.openlocfilehash: d5000b51d83066ec2d529db2033d8ac54f7ad329
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/15/2020
ms.locfileid: "90557789"
---
# <a name="xshared-attribute"></a>x:Shared 属性

に設定すると `false` 、WPF リソース取得動作を変更して、属性を持つリソースの要求で、すべての要求に対して同じインスタンスを共有するのではなく、各要求に対して新しいインスタンスを作成します。

## <a name="xaml-attribute-usage"></a>XAML 属性の使用方法

```xaml
<ResourceDictionary>
  <object x:Shared="false".../>
</ResourceDictionary>
```

## <a name="remarks"></a>Remarks

`x:Shared` は XAML 言語の XAML 名前空間にマップされ、.NET XAML サービスとその XAML リーダーによって有効な XAML 言語要素として認識されます。 ただし、に示されている機能は、 `x:Shared` wpf アプリケーションと WPF XAML パーサーにのみ関連します。 WPF で `x:Shared` は、は、wpf 内に存在するオブジェクトに適用されるときに、属性としてのみ役立ち <xref:System.Windows.ResourceDictionary> ます。 その他の使用方法では、解析例外やその他のエラーはスローされませんが、効果はありません。

の意味 `x:Shared` は、XAML 言語仕様では指定されていません。 .NET XAML サービス上に構築されるようなその他の XAML 実装は、必ずしもリソース共有のサポートを提供するわけではありません。 このような XAML 実装は、値を使用するサポートフレームワークでも同様の動作を提供する可能性が `x:Shared` あります。

WPF で `x:Shared` は、リソースの既定の条件は `true` です。 この条件は、特定のリソース要求が常に同じインスタンスを返すことを意味します。

リソース API によって返されたオブジェクト (など) を変更し <xref:System.Windows.FrameworkElement.FindResource%2A> たり、内で直接オブジェクトを変更したりすると <xref:System.Windows.ResourceDictionary> 、元のリソースが変更されます。 そのリソースへの参照が動的リソース参照であった場合、そのリソースのコンシューマーは、変更されたリソースを取得します。

リソースへの参照が静的リソース参照であった場合、処理時間後のリソースへの変更 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] は関係ありません。 静的リソース参照と動的リソース参照の詳細については、「 [XAML Resources](../fundamentals/xaml-resources-define.md)」を参照してください。

が明示的に指定され `x:Shared="true"` ていることはほとんどありません。これは既に既定値であるためです。 WPF オブジェクトモデルでは、に相当する直接コードはありません `x:Shared` 。 XAML の使用法でのみ指定できます。また、.NET Xaml サービスとその xaml リーダーを使用して処理する場合は、読み込みパスの既定の WPF の動作または中間の xaml ノードストリームで処理する必要があります。

のシナリオは、 `x:Shared="false"` またはの派生クラスをリソースとして定義し、 <xref:System.Windows.FrameworkElement> <xref:System.Windows.FrameworkContentElement> 要素リソースをコンテンツモデルに導入する場合です。 `x:Shared="false"` 要素リソースを同じコレクション (など) に複数回導入できるように <xref:System.Windows.Controls.UIElementCollection> します。 `x:Shared="false"`コレクションがその内容の一意性を強制するため、これは無効です。 ただし、 `x:Shared="false"` 同じインスタンスを返す代わりに、この動作によってリソースの同じインスタンスがもう1つ作成されます。

のもう1つのシナリオ `x:Shared="false"` は、 <xref:System.Windows.Freezable> アニメーション値にリソースを使用し、アニメーションごとにリソースを変更する場合です。

の文字列処理で `false` は、大文字と小文字が区別されません。

WPF で `x:Shared` は、は次の条件下でのみ有効です。

- <xref:System.Windows.ResourceDictionary>を持つ項目を格納しているを `x:Shared` コンパイルする必要があります。 を <xref:System.Windows.ResourceDictionary> ルース XAML の内側に配置したり、テーマに使用したりすることはできません。

- <xref:System.Windows.ResourceDictionary>項目を含むを別の内で入れ子にすることはできません <xref:System.Windows.ResourceDictionary> 。 たとえば、 `x:Shared` <xref:System.Windows.ResourceDictionary> <xref:System.Windows.Style> 既に項目である内の項目に対してを使用することはできません <xref:System.Windows.ResourceDictionary> 。

## <a name="see-also"></a>関連項目

- <xref:System.Windows.ResourceDictionary>
- [XAML リソース](../fundamentals/xaml-resources-define.md)
- [基本要素](/dotnet/desktop/wpf/advanced/base-elements)
