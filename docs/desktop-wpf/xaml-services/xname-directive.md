---
title: x:Name ディレクティブ
ms.date: 03/30/2017
f1_keywords:
- x:Name
- xName
- Name
helpviewer_keywords:
- x:Name attribute [XAML Services]
- XAML [XAML Services], x:Name attribute
- Name attribute in XAML [XAML Services]
ms.assetid: b7e61222-e8cf-48d2-acd0-6df3b7685d48
ms.openlocfilehash: ddaa35b18d1c632fc49b18dabf0d992dc1c78fcc
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/15/2020
ms.locfileid: "90549484"
---
# <a name="xname-directive"></a>x:Name ディレクティブ

Xaml 名前スコープ内の XAML で定義された要素を一意に識別します。 XAML 名前スコープとその一意モデルは、インスタンス化されたオブジェクトに適用できます。フレームワークが Api を提供する場合や、実行時に XAML で作成されたオブジェクトグラフにアクセスする動作を実装する場合です。

## <a name="xaml-attribute-usage"></a>XAML 属性の使用方法

```xaml
<object x:Name="XAMLNameValue".../>
```

## <a name="xaml-values"></a>XAML 値

|||
|-|-|
|`XAMLNameValue`|[XamlName 文法](xamlname-grammar.md)の制限に準拠する文字列。|

## <a name="remarks"></a>Remarks

`x:Name`がフレームワークのバッキングプログラミングモデルに適用された後、名前は、オブジェクト参照を保持する変数、またはコンストラクターによって返されるインスタンスに相当します。

ディレクティブの使用の値は、 `x:Name` XAML 名前スコープ内で一意である必要があります。 既定では、.NET XAML サービス API によって使用されるとき、プライマリ XAML 名前スコープは、1つの XAML 運用環境の XAML ルート要素で定義され、その XAML 運用環境に含まれる要素を含みます。 1つの XAML 運用環境で発生する可能性のある個別の XAML 名前スコープは、特定のシナリオに対応するためにフレームワークによって定義できます。 たとえば、WPF では、新しい XAML 名前スコープが定義され、その XAML 運用環境でも定義されている任意のテンプレートによって作成されます。 XAML 名前スコープの詳細については (WPF 用に記述されていますが、多くの XAML 名前スコープの概念に関連します)、「 [WPF Xaml 名前スコープ](/dotnet/desktop/wpf/advanced/wpf-xaml-namescopes)」をご覧ください。

一般に、 `x:Name` も使用する状況では適用しないでください `x:Key` 。 特定の既存のフレームワークによる XAML の実装では、との間に代替概念が導入されてい `x:Key` `x:Name` ますが、これは推奨される方法ではありません。 .NET XAML サービスでは、やなどの名前/キー情報を処理するときに、このような置換の概念はサポートされません <xref:System.Windows.Markup.INameScope> <xref:System.Windows.Markup.DictionaryKeyPropertyAttribute> 。

Permittance の規則 `x:Name` と名前の一意性の強制は、特定の実装フレームワークによって定義される可能性があります。 ただし、.NET XAML サービスで使用できるようにするには、XAML 名前スコープの一意性のフレームワーク定義がこのドキュメントの情報の定義と一致している必要があり <xref:System.Windows.Markup.INameScope> ます。また、情報が適用される場所についても同じ規則を使用する必要があります。 たとえば、実装では、 [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] さまざまなマークアップ要素を <xref:System.Windows.NameScope> リソースディクショナリ、ページレベルの xaml によって作成された論理ツリー、テンプレート、その他の遅延コンテンツなどの異なる範囲に分割し、xaml 名前空間のそれぞれに xaml 名の一意性を適用します。

.NET XAML サービス XAML オブジェクトライターを使用するカスタム型の場合、型のにマップされるプロパティを `x:Name` 確立または変更できます。 この動作を定義するには、型定義コードのにマップするプロパティの名前を参照し <xref:System.Windows.Markup.RuntimeNamePropertyAttribute> ます。  <xref:System.Windows.Markup.RuntimeNamePropertyAttribute> は、型レベルの属性です。

Using.NET XAML サービスでは、XAML 名前スコープのサポートのバッキングロジックは、インターフェイスを実装することによって、フレームワークに依存しない方法で定義できます <xref:System.Windows.Markup.INameScope> 。

## <a name="wpf-usage-notes"></a>WPF の使用上の注意

[!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)]XAML、部分クラス、および分離コードを使用するアプリケーションの標準ビルド構成では、指定されたは、 `x:Name` マークアップコンパイルビルドタスクによって処理されるときに、基になるコードで作成されるフィールドの名前になり [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] ます。また、そのフィールドはオブジェクトへの参照を保持します。 既定では、作成されたフィールドは internal です。 フィールドへのアクセスを変更するには、 [x:FieldModifier 属性](xfieldmodifier-directive.md)を指定します。 WPF と Silverlight では、マークアップコンパイルが部分クラスのフィールドを定義して名前を指定しますが、この値は最初は空です。 次に、という名前の生成されたメソッド `InitializeComponent` が、クラスコンストラクター内から呼び出されます。 `InitializeComponent``FindName` `x:Name` 部分クラスの XAML で定義された部分に存在する各値を入力文字列として使用する呼び出しで構成されます。 その後、戻り値は、like 名前のフィールド参照に割り当てられ、XAML 解析から作成されたオブジェクトでフィールド値が設定されます。 の実行に `InitializeComponent` より、/フィールド名を使用して実行時のオブジェクトグラフを直接参照できるようになり `x:Name` ます。これは、 `FindName` XAML で定義されたオブジェクトへの参照が必要になるたびに明示的に呼び出す必要はありません。

Microsoft Visual Basic ターゲットを使用し、ビルドアクションを含む XAML ファイルが含まれている WPF アプリケーションの場合 `Page` 、コンパイル時に個別の参照プロパティが作成されます。これは、を `WithEvents` 持つすべての要素にキーワードを追加して `x:Name` 、 `Handles` イベントハンドラーデリゲートの構文をサポートします。 このプロパティは常にパブリックです。 詳細については、「[Visual Basic と WPF のイベント処理](/dotnet/desktop/wpf/advanced/visual-basic-and-wpf-event-handling)」を参照してください。

`x:Name` は、読み込み時に XAML 名前スコープに名前を登録するために WPF XAML プロセッサによって使用されます。これは、ページがビルドアクションによってマークアップコンパイルされていない場合 (リソースディクショナリの疎 XAML など) であっても同様です。 この動作の理由の1つは、 `x:Name` バインディングにが必要になる可能性があるためです <xref:System.Windows.Data.Binding.ElementName%2A> 。 詳細については、「 [データバインディングの概要](../data/data-binding-overview.md)」を参照してください。

前述のように、 `x:Name` (または `Name` ) も使用する状況では適用しないでください `x:Key` 。 は、 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.ResourceDictionary> それ自体を XAML 名前スコープとして定義する特殊な動作を持ちますが、 <xref:System.Windows.Markup.INameScope> この動作を強制する方法として、api に対して実装されていない値または null 値を返します。 WPF XAML パーサーでまたは XAML で定義されている場合、 `Name` `x:Name` 名前は <xref:System.Windows.ResourceDictionary> どの xaml 名前スコープにも追加されません。 任意の XAML 名前スコープからその名前を見つけようとすると、 `FindName` 有効な結果が返されません。

### <a name="xname-and-name"></a>x:Name と名前

多くの WPF アプリケーションのシナリオでは、属性の使用を避けることができます `x:Name` `Name` 。これは、などの重要な基本クラス (やなど) の既定の XAML 名前空間で指定されている依存関係プロパティが <xref:System.Windows.FrameworkElement> <xref:System.Windows.FrameworkContentElement> 同じ目的を満たすためです。 フレームワークレベルでプロパティを持たない要素へのコードアクセスが重要である一般的な XAML と WPF のシナリオもいくつかあり `Name` ます。 たとえば、特定のアニメーションとストーリーボードのサポートクラスはプロパティをサポートしていません `Name` が、多くの場合、アニメーションを制御するためにコード内で参照する必要があります。 `x:Name`後でコードから参照する場合は、XAML で作成されたタイムラインおよび変換の属性としてを指定する必要があります。

を <xref:System.Windows.FrameworkElement.Name%2A> クラスのプロパティとして使用できる場合、 <xref:System.Windows.FrameworkElement.Name%2A> およびは `x:Name` 属性として同義に使用できますが、両方が同じ要素に指定されていると、解析例外が発生します。 XAML がマークアップコンパイルされている場合は、マークアップコンパイル時に例外が発生します。それ以外の場合は、読み込み時に発生します。

<xref:System.Windows.FrameworkElement.Name%2A> は、XAML 属性構文とを使用して設定でき <xref:System.Windows.DependencyObject.SetValue%2A> ます。ただし、コードでプロパティを設定しても、xaml <xref:System.Windows.FrameworkElement.Name%2A> が既に読み込まれているほとんどの状況で、xaml 名前スコープ内で代表的なフィールド参照が作成されるわけではありません。 コードでを設定するのではなく、 <xref:System.Windows.FrameworkElement.Name%2A> <xref:System.Windows.NameScope> 適切な名前スコープに対してコードからメソッドを使用します。

<xref:System.Windows.FrameworkElement.Name%2A> また、プロパティ要素構文を内部テキストと共に使用して設定することもできますが、これは一般的ではありません。 これに対し、は、 `x:Name` XAML プロパティ要素構文またはを使用したコードでは設定できません <xref:System.Windows.DependencyObject.SetValue%2A> 。これは、オブジェクトの属性構文を使用してのみ設定できます。これは、ディレクティブであるためです。

## <a name="silverlight-usage-notes"></a>Silverlight の使用上の注意

Silverlight 用の `x:Name` に関しては、別途ドキュメントが用意されています。 詳細については、「 [XAML 名前空間 (x:)」を参照してください。言語機能 (Silverlight)](/previous-versions/windows/silverlight/dotnet-windows-silverlight/cc188995(v=vs.95))。

## <a name="see-also"></a>関連項目

- <xref:System.Windows.FrameworkElement.Name%2A?displayProperty=nameWithType>
- <xref:System.Windows.FrameworkContentElement.Name%2A?displayProperty=nameWithType>
- [WPF のツリー](/dotnet/desktop/wpf/advanced/trees-in-wpf)
