---
title: x:Array のマークアップ拡張機能
ms.date: 03/30/2017
f1_keywords:
- x:Array
- xArray
helpviewer_keywords:
- x:Array [XAML Services]
- XAML [XAML Services], x:Array markup extension
ms.assetid: c5358e14-d24c-44c7-b5eb-6062a4fd981c
ms.openlocfilehash: b812939cbaa74576361de534c0d39ba45536cbcf
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/15/2020
ms.locfileid: "90555173"
---
# <a name="xarray-markup-extension"></a>x:Array のマークアップ拡張機能

マークアップ拡張機能を使用して、XAML のオブジェクトの配列に対する一般的なサポートを提供します。 これは、 `x:ArrayExtension` [MS xaml] の xaml 型に対応しています。

## <a name="xaml-object-element-usage"></a>XAML オブジェクト要素の使用方法

```xaml
<x:Array Type="typeName">
  arrayContents
</x:Array>
```

## <a name="xaml-values"></a>XAML 値

|||
|-|-|
|`typeName`|に格納される型の名前 `x:Array` 。 `typeName` xaml 型定義を含む XAML 名前空間の先頭に (多くの場合は) プレフィックスを付けることができます。|
|`arrayContents`|組み込みプロパティに割り当てられている項目の内容 `ArrayExtension.Items` 。 通常、これらの項目は、開始タグと終了タグ内に含まれる1つ以上のオブジェクト要素として指定され `x:Array` ます。 ここで指定されたオブジェクトは、で指定された XAML 型に割り当て可能である必要があり `typeName` ます。|

## <a name="remarks"></a>Remarks

`Type` は、すべてのオブジェクト要素に対して必須の属性です `x:Array` 。 `Type`パラメーター値は、マークアップ拡張機能を使用する必要はありません `x:Type` 。型の短い名前は XAML 型であり、これを文字列として指定できます。

.NET XAML サービスの実装では、入力 XAML 型と、 <xref:System.Type> 作成された配列の出力 CLR の関係は、マークアップ拡張機能のサービスコンテキストによって影響を受けます。 出力 <xref:System.Type> は、 <xref:System.Xaml.XamlType.UnderlyingType%2A> <xref:System.Xaml.XamlType> xaml スキーマコンテキストとコンテキストによって提供されるサービスに基づいて必要なを検索した後の入力 xaml 型のです <xref:System.Windows.Markup.IXamlTypeResolver> 。

処理されると、配列の内容が組み込みプロパティに割り当てられ `ArrayExtension.Items` ます。 実装で <xref:System.Windows.Markup.ArrayExtension> は、これはによって表され <xref:System.Windows.Markup.ArrayExtension.Items%2A?displayProperty=nameWithType> ます。

.NET XAML サービスの実装では、このマークアップ拡張機能の処理はクラスによって定義され <xref:System.Windows.Markup.ArrayExtension> ます。 <xref:System.Windows.Markup.ArrayExtension> はシールされていないため、カスタム配列型のマークアップ拡張機能の実装の基礎として使用できます。

`x:Array` は、XAML の一般的な言語の機能拡張を目的としています。 ただし、 `x:Array` xaml でサポートされるコレクションを構造化プロパティコンテンツとして受け取る特定のプロパティの xaml 値を指定する場合にも便利です。 たとえば、 <xref:System.Collections.IEnumerable> 使用法を使用してプロパティの内容を指定でき `x:Array` ます。

`x:Array` はマークアップ拡張機能です。 一般にマークアップ拡張機能を実装するのは、属性値をリテラル値やハンドラー名以外にエスケープする要件が存在し、その要件の適用範囲がグローバルで、特定の型やプロパティに型コンバーターを適用するだけにとどまらない場合です。 `x:Array` は、その規則に対して部分的な例外となります。これは、代替の属性値の処理を提供する代わりに、 `x:Array` 内部テキストの内容を別の方法で処理できるためです。 この動作により、既存のコンテンツモデルでサポートされていない型が配列にグループ化され、後で名前付き配列にアクセスすることによってコードビハインドで参照される可能性があります。メソッドを呼び出して、 <xref:System.Array> 個々の配列項目を取得できます。

XAML のすべてのマークアップ拡張は、中かっこ (属性構文) を使用します {,} `)` 。これは、マークアップ拡張機能が属性値を処理する必要があることを xaml プロセッサが認識する規則です。 マークアップ拡張機能全般の詳細については、「 [XAML の型コンバーターとマークアップ拡張機能](type-converters-and-markup-extensions.md)」を参照してください。

XAML 2009 で `x:Array` は、はマークアップ拡張ではなく言語プリミティブとして定義されています。 詳細については、「 [共通の XAML 言語プリミティブの組み込み型](types-for-primitives.md)」を参照してください。

## <a name="wpf-usage-notes"></a>WPF の使用上の注意

通常、に値を設定するオブジェクト要素 `x:Array` は、xaml 名前空間に存在する要素ではなく、 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 既定以外の xaml 名前空間に対するプレフィックスマッピングを必要とします。

たとえば、次の例では、2つの文字列の単純な配列を示してい `sys` ます。この配列のプレフィックス (および `x` ) は配列のレベルで定義されています。

```xaml
<x:Array Type="sys:String"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:sys="clr-namespace:System;assembly=mscorlib">
  <sys:String>Hello</sys:String>
  <sys:String>World</sys:String>
</x:Array>
```

配列要素として使用されるカスタム型の場合、クラスは XAML でオブジェクト要素としてインスタンス化するための要件もサポートする必要があります。 詳細については、「 [WPF の XAML およびカスタムクラス](/dotnet/desktop/wpf/advanced/xaml-and-custom-classes-for-wpf)」を参照してください。

## <a name="see-also"></a>関連項目

- [マークアップ拡張機能と WPF XAML](/dotnet/desktop/wpf/advanced/markup-extensions-and-wpf-xaml)
- [WPF から App.xaml に移行された型](/dotnet/desktop/wpf/advanced/types-migrated-from-wpf-to-system)
