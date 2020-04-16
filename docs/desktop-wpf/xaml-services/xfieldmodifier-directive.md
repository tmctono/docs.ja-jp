---
title: x:FieldModifier ディレクティブ
ms.date: 03/30/2017
helpviewer_keywords:
- FieldModifier attribute in XAML [XAML Services]
- x:FieldModifier attribute [XAML Services]
- XAML [XAML Services], x:FieldModifier attribute
ms.assetid: ed427cd4-2f35-4d24-bd2f-0fa7b71ec248
ms.openlocfilehash: 3e104b4c464d545e048f29901701c1c3dbb68229
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/27/2020
ms.locfileid: "81432780"
---
# <a name="xfieldmodifier-directive"></a><span data-ttu-id="5bf58-102">x:FieldModifier ディレクティブ</span><span class="sxs-lookup"><span data-stu-id="5bf58-102">x:FieldModifier Directive</span></span>
<span data-ttu-id="5bf58-103">XAML コンパイル動作を変更して、名前付きオブジェクト参照のフィールド<xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType>が<xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>既定の動作ではなくアクセスで定義されるようにします。</span><span class="sxs-lookup"><span data-stu-id="5bf58-103">Modifies XAML compilation behavior so that fields for named object references are defined with <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> access instead of the <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> default behavior.</span></span>

## <a name="xaml-attribute-usage"></a><span data-ttu-id="5bf58-104">XAML 属性の使用方法</span><span class="sxs-lookup"><span data-stu-id="5bf58-104">XAML Attribute Usage</span></span>

```xaml
<object x:FieldModifier="Public".../>
```

## <a name="xaml-values"></a><span data-ttu-id="5bf58-105">XAML 値</span><span class="sxs-lookup"><span data-stu-id="5bf58-105">XAML Values</span></span>

|||
|-|-|
|<span data-ttu-id="5bf58-106">*パブリック*</span><span class="sxs-lookup"><span data-stu-id="5bf58-106">*Public*</span></span>|<span data-ttu-id="5bf58-107">指定する文字列と<xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType><xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>指定する文字列は、使用する分離コード プログラミング言語によって異なります。</span><span class="sxs-lookup"><span data-stu-id="5bf58-107">The exact string you pass to specify <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> versus <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> varies, depending on the code-behind programming language that is used.</span></span> <span data-ttu-id="5bf58-108">「解説」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5bf58-108">See Remarks.</span></span>|

## <a name="dependencies"></a><span data-ttu-id="5bf58-109">依存関係</span><span class="sxs-lookup"><span data-stu-id="5bf58-109">Dependencies</span></span>

 <span data-ttu-id="5bf58-110">XAML の運用環境で`x:FieldModifier`任意の場所を使用する場合、その XAML の運用環境のルート要素は[、x: Class ディレクティブ](xclass-directive.md)を宣言する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5bf58-110">If a XAML production uses `x:FieldModifier` anywhere, the root element of that XAML production must declare an [x:Class Directive](xclass-directive.md).</span></span>

## <a name="remarks"></a><span data-ttu-id="5bf58-111">解説</span><span class="sxs-lookup"><span data-stu-id="5bf58-111">Remarks</span></span>

<span data-ttu-id="5bf58-112">`x:FieldModifier`クラスまたはそのメンバーの一般的なアクセス レベルを宣言する場合は、そのレベルは関係ありません。</span><span class="sxs-lookup"><span data-stu-id="5bf58-112">`x:FieldModifier` is not relevant for declaring the general access level of a class or its members.</span></span> <span data-ttu-id="5bf58-113">これは、XAML の処理動作に関連する XAML の一部である特定の XAML オブジェクトが処理され、アプリケーションのオブジェクト グラフでアクセス可能なオブジェクトになる可能性があるオブジェクトになります。</span><span class="sxs-lookup"><span data-stu-id="5bf58-113">It is relevant only for XAML-processing behavior when a particular XAML object that is part of a XAML production is processed, and becomes an object that is potentially accessible in the object graph of an application.</span></span> <span data-ttu-id="5bf58-114">既定では、このようなオブジェクトのフィールド参照はプライベートに保たれ、コントロール のコンシューマーがオブジェクト グラフを直接変更できないようにします。</span><span class="sxs-lookup"><span data-stu-id="5bf58-114">By default, the field reference for such an object is kept private, which prevents control consumers from modifying the object graph directly.</span></span> <span data-ttu-id="5bf58-115">代わりに、コントロール コンシューマーは、レイアウト ルート、子要素コレクション、専用のパブリック プロパティなどを取得するなど、プログラミング モデルによって有効になる標準パターンを使用してオブジェクト グラフを変更することが期待されます。</span><span class="sxs-lookup"><span data-stu-id="5bf58-115">Instead, control consumers are expected to modify the object graph by using standard patterns that are enabled by programming models, such as by obtaining the layout root, the child element collections, the dedicated public properties, and so on.</span></span>

<span data-ttu-id="5bf58-116">属性の`x:FieldModifier`値はプログラミング言語によって異なり、その目的は特定のフレームワークによって異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="5bf58-116">The value for the `x:FieldModifier` attribute varies by programming language, and its purpose can vary in specific frameworks.</span></span> <span data-ttu-id="5bf58-117">使用する文字列は、各言語が実装<xref:System.CodeDom.Compiler.CodeDomProvider>する方法と、その言語が返す型コンバーターによって、 および<xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType><xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>の意味を定義するかどうか、およびその言語で大文字と小文字が区別されるかどうかによって異なります。</span><span class="sxs-lookup"><span data-stu-id="5bf58-117">The string to use depends on how each language implements its <xref:System.CodeDom.Compiler.CodeDomProvider> and the type converters it returns to define the meanings for <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> and <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>, and whether that language is case sensitive.</span></span>

- <span data-ttu-id="5bf58-118">C# の場合、指定<xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType>に渡す文字列`public`は です。</span><span class="sxs-lookup"><span data-stu-id="5bf58-118">For C#, the string to pass to designate <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> is `public`.</span></span>

- <span data-ttu-id="5bf58-119">NET の場合、指定<xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType>に渡す文字列は`Public`です。</span><span class="sxs-lookup"><span data-stu-id="5bf58-119">For Microsoft Visual Basic .NET, the string to pass to designate <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> is `Public`.</span></span>

- <span data-ttu-id="5bf58-120">C++/CLI の場合、現在 XAML のターゲットは存在しません。したがって、渡す文字列は未定義です。</span><span class="sxs-lookup"><span data-stu-id="5bf58-120">For C++/CLI, no targets for XAML currently exist; therefore, the string to pass is undefined.</span></span>

<span data-ttu-id="5bf58-121">(Visual Basic <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> `internal`では C#`Friend`で) 指定することもできますが<xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>、動作は`NotPublic`既に既定であるため、指定は珍しいものです。</span><span class="sxs-lookup"><span data-stu-id="5bf58-121">You can also specify <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> (`internal` in C#, `Friend` in Visual Basic) but specifying <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> is unusual because `NotPublic` as the behavior is already the default.</span></span>

<span data-ttu-id="5bf58-122"><xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>XAML をコンパイルしたアセンブリの外部のコードが XAML で作成された要素にアクセスする必要がある場合は、そのコードが頻繁に発生するため、既定の動作です。</span><span class="sxs-lookup"><span data-stu-id="5bf58-122"><xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> is the default behavior because it is infrequent that code outside the assembly that compiled the XAML needs access to a XAML-created element.</span></span> <span data-ttu-id="5bf58-123">WPF セキュリティ アーキテクチャと XAML コンパイル動作を組み合わせて使用すると、パブリック アクセスを許可するように`x:FieldModifier`明示的に設定しない限り、要素インスタンスをパブリックとして格納するフィールドは宣言されません。</span><span class="sxs-lookup"><span data-stu-id="5bf58-123">WPF security architecture together with XAML compilation behavior will not declare fields that store element instances as public, unless you specifically set the `x:FieldModifier` to allow public access.</span></span>

<span data-ttu-id="5bf58-124">`x:FieldModifier`は、その名前がパブリックの後にフィールドを参照するために使用されるため[、x:Name ディレクティブ](xname-directive.md)を持つ要素にのみ関連します。</span><span class="sxs-lookup"><span data-stu-id="5bf58-124">`x:FieldModifier` is only relevant for elements with an [x:Name Directive](xname-directive.md) because that name is used to reference the field after it is public.</span></span>

<span data-ttu-id="5bf58-125">既定では、ルート要素の部分クラスはパブリックです。ただし[、x:ClassModifier ディレクティブ](xclassmodifier-directive.md)を使用して、これを非パブリックにできます。</span><span class="sxs-lookup"><span data-stu-id="5bf58-125">By default, the partial class for the root element is public; however, you can make it nonpublic by using the [x:ClassModifier Directive](xclassmodifier-directive.md).</span></span> <span data-ttu-id="5bf58-126">[x:ClassModifier ディレクティブ](xclassmodifier-directive.md)は、ルート要素クラスのインスタンスのアクセス レベルにも影響します。</span><span class="sxs-lookup"><span data-stu-id="5bf58-126">The [x:ClassModifier Directive](xclassmodifier-directive.md) also affects the access level of the instance of the root element class.</span></span> <span data-ttu-id="5bf58-127">ルート要素`x:FieldModifier`の両方`x:Name`を配置できますが、これはルート要素のパブリック フィールド コピーのみを作成します。 [x:ClassModifier Directive](xclassmodifier-directive.md)</span><span class="sxs-lookup"><span data-stu-id="5bf58-127">You can put both `x:Name` and `x:FieldModifier` on the root element, but this only makes a public field copy of the root element, with the true root element class access level still controlled by [x:ClassModifier Directive](xclassmodifier-directive.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="5bf58-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="5bf58-128">See also</span></span>

- [<span data-ttu-id="5bf58-129">WPF における XAML とカスタム クラス</span><span class="sxs-lookup"><span data-stu-id="5bf58-129">XAML and Custom Classes for WPF</span></span>](../../framework/wpf/advanced/xaml-and-custom-classes-for-wpf.md)
- [<span data-ttu-id="5bf58-130">WPF における分離コードと XAML</span><span class="sxs-lookup"><span data-stu-id="5bf58-130">Code-Behind and XAML in WPF</span></span>](../../framework/wpf/advanced/code-behind-and-xaml-in-wpf.md)
- [<span data-ttu-id="5bf58-131">x:Name ディレクティブ</span><span class="sxs-lookup"><span data-stu-id="5bf58-131">x:Name Directive</span></span>](xname-directive.md)
- [<span data-ttu-id="5bf58-132">WPF アプリケーションのビルド (WPF)</span><span class="sxs-lookup"><span data-stu-id="5bf58-132">Building a WPF Application (WPF)</span></span>](../../framework/wpf/app-development/building-a-wpf-application-wpf.md)
- [<span data-ttu-id="5bf58-133">x:ClassModifier ディレクティブ</span><span class="sxs-lookup"><span data-stu-id="5bf58-133">x:ClassModifier Directive</span></span>](xclassmodifier-directive.md)
