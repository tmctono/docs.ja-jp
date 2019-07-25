---
title: x:FieldModifier ディレクティブ
ms.date: 03/30/2017
helpviewer_keywords:
- FieldModifier attribute in XAML [XAML Services]
- x:FieldModifier attribute [XAML Services]
- XAML [XAML Services], x:FieldModifier attribute
ms.assetid: ed427cd4-2f35-4d24-bd2f-0fa7b71ec248
ms.openlocfilehash: 646ad1ca99d83f9fb2994f3c394eca27a60c0eac
ms.sourcegitcommit: 4b9c2d893b45d47048c6598b4182ba87759b1b59
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/25/2019
ms.locfileid: "68484720"
---
# <a name="xfieldmodifier-directive"></a><span data-ttu-id="d2691-102">x:FieldModifier ディレクティブ</span><span class="sxs-lookup"><span data-stu-id="d2691-102">x:FieldModifier Directive</span></span>
<span data-ttu-id="d2691-103">名前付きオブジェクト参照のフィールドが<xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>既定の動作ではなくアクセスで定義されるように、XAML コンパイル動作を変更します。</span><span class="sxs-lookup"><span data-stu-id="d2691-103">Modifies XAML compilation behavior so that fields for named object references are defined with <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> access instead of the <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> default behavior.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="d2691-104">XAML 属性の使用方法</span><span class="sxs-lookup"><span data-stu-id="d2691-104">XAML Attribute Usage</span></span>  
  
```xaml  
<object x:FieldModifier="Public".../>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="d2691-105">XAML 値</span><span class="sxs-lookup"><span data-stu-id="d2691-105">XAML Values</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d2691-106">*Public*</span><span class="sxs-lookup"><span data-stu-id="d2691-106">*Public*</span></span>|<span data-ttu-id="d2691-107">を指定<xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>するために渡す文字列は、使用される分離コードプログラミング言語によって異なります。</span><span class="sxs-lookup"><span data-stu-id="d2691-107">The exact string you pass to specify <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> versus <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> varies, depending on the code-behind programming language that is used.</span></span> <span data-ttu-id="d2691-108">「解説」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d2691-108">See Remarks.</span></span>|  
  
## <a name="dependencies"></a><span data-ttu-id="d2691-109">依存関係</span><span class="sxs-lookup"><span data-stu-id="d2691-109">Dependencies</span></span>  
 <span data-ttu-id="d2691-110">Xaml の運用環境で`x:FieldModifier`任意の場所を使用する場合は、その xaml の運用環境のルート要素で[x:Class ディレクティブ](x-class-directive.md)を宣言する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d2691-110">If a XAML production uses `x:FieldModifier` anywhere, the root element of that XAML production must declare an [x:Class Directive](x-class-directive.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d2691-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="d2691-111">Remarks</span></span>  
 <span data-ttu-id="d2691-112">`x:FieldModifier`は、クラスまたはそのメンバーの一般アクセスレベルを宣言する場合には関係ありません。</span><span class="sxs-lookup"><span data-stu-id="d2691-112">`x:FieldModifier` is not relevant for declaring the general access level of a class or its members.</span></span> <span data-ttu-id="d2691-113">Xaml の運用環境に含まれる特定の XAML オブジェクトが処理され、アプリケーションのオブジェクトグラフでアクセスできる可能性があるオブジェクトになる場合にのみ、XAML 処理の動作に関連します。</span><span class="sxs-lookup"><span data-stu-id="d2691-113">It is relevant only for XAML-processing behavior when a particular XAML object that is part of a XAML production is processed, and becomes an object that is potentially accessible in the object graph of an application.</span></span> <span data-ttu-id="d2691-114">既定では、このようなオブジェクトのフィールド参照はプライベートに保持されるため、コントロールのコンシューマーがオブジェクトグラフを直接変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="d2691-114">By default, the field reference for such an object is kept private, which prevents control consumers from modifying the object graph directly.</span></span> <span data-ttu-id="d2691-115">代わりに、コントロールコンシューマーは、レイアウトルート、子要素コレクション、専用のパブリックプロパティなどを取得することによって、プログラミングモデルによって有効になる標準パターンを使用して、オブジェクトグラフを変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d2691-115">Instead, control consumers are expected to modify the object graph by using standard patterns that are enabled by programming models, such as by obtaining the layout root, the child element collections, the dedicated public properties, and so on.</span></span>  
  
 <span data-ttu-id="d2691-116">`x:FieldModifier`属性の値はプログラミング言語によって異なり、その目的は特定のフレームワークによって異なります。</span><span class="sxs-lookup"><span data-stu-id="d2691-116">The value for the `x:FieldModifier` attribute varies by programming language, and its purpose can vary in specific frameworks.</span></span> <span data-ttu-id="d2691-117">使用する文字列は、各言語がを実装<xref:System.CodeDom.Compiler.CodeDomProvider>する方法、およびが返す型コンバーターによって異なります。これにより、との<xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType>意味が定義され、その言語で大文字と<xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>小文字が区別されるかどうかが決まります。</span><span class="sxs-lookup"><span data-stu-id="d2691-117">The string to use depends on how each language implements its <xref:System.CodeDom.Compiler.CodeDomProvider> and the type converters it returns to define the meanings for <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> and <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>, and whether that language is case sensitive.</span></span>  
  
- <span data-ttu-id="d2691-118">C#では、を指定<xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType>するために渡す`public`文字列はです。</span><span class="sxs-lookup"><span data-stu-id="d2691-118">For C#, the string to pass to designate <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> is `public`.</span></span>  
  
- <span data-ttu-id="d2691-119">Microsoft Visual Basic .net の場合、指定<xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType>するために渡す文字列は`Public`です。</span><span class="sxs-lookup"><span data-stu-id="d2691-119">For Microsoft Visual Basic .NET, the string to pass to designate <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> is `Public`.</span></span>  
  
- <span data-ttu-id="d2691-120">/Cli C++の場合、現在 XAML のターゲットは存在しません。したがって、渡す文字列は定義されていません。</span><span class="sxs-lookup"><span data-stu-id="d2691-120">For C++/CLI, no targets for XAML currently exist; therefore, the string to pass is undefined.</span></span>  
  
 <span data-ttu-id="d2691-121"><xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> ( <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> `NotPublic`の Visual Basic場合`Friend`は) を指定することもできますが、動作は既に既定値であるため、を指定することはまれです。 C#`internal`</span><span class="sxs-lookup"><span data-stu-id="d2691-121">You can also specify <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> (`internal` in C#, `Friend` in Visual Basic) but specifying <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> is unusual because `NotPublic` as the behavior is already the default.</span></span>  
  
 <span data-ttu-id="d2691-122"><xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>は、XAML をコンパイルしたアセンブリの外部のコードが XAML で作成された要素にアクセスする必要があるため、既定の動作です。</span><span class="sxs-lookup"><span data-stu-id="d2691-122"><xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> is the default behavior because it is infrequent that code outside the assembly that compiled the XAML needs access to a XAML-created element.</span></span> <span data-ttu-id="d2691-123">WPF のセキュリティアーキテクチャは、パブリックアクセスを許可するように明示的に設定しない限り、XAML のコンパイル`x:FieldModifier`動作と共に、要素インスタンスをパブリックとして格納するフィールドを宣言しません。</span><span class="sxs-lookup"><span data-stu-id="d2691-123">WPF security architecture together with XAML compilation behavior will not declare fields that store element instances as public, unless you specifically set the `x:FieldModifier` to allow public access.</span></span>  
  
 <span data-ttu-id="d2691-124">`x:FieldModifier`は、public の後にフィールドを参照するために使用されるため、 [X:Name ディレクティブ](x-name-directive.md)を持つ要素にのみ関連します。</span><span class="sxs-lookup"><span data-stu-id="d2691-124">`x:FieldModifier` is only relevant for elements with an [x:Name Directive](x-name-directive.md) because that name is used to reference the field after it is public.</span></span>  
  
 <span data-ttu-id="d2691-125">既定では、ルート要素の部分クラスは public です。ただし、 [X:ClassModifier ディレクティブ](x-classmodifier-directive.md)を使用してパブリックにすることはできません。</span><span class="sxs-lookup"><span data-stu-id="d2691-125">By default, the partial class for the root element is public; however, you can make it nonpublic by using the [x:ClassModifier Directive](x-classmodifier-directive.md).</span></span> <span data-ttu-id="d2691-126">[X:ClassModifier ディレクティブ](x-classmodifier-directive.md)は、ルート要素クラスのインスタンスのアクセスレベルにも影響します。</span><span class="sxs-lookup"><span data-stu-id="d2691-126">The [x:ClassModifier Directive](x-classmodifier-directive.md) also affects the access level of the instance of the root element class.</span></span> <span data-ttu-id="d2691-127">ルート要素にと`x:Name` `x:FieldModifier`の両方を含めることができますが、これによってルート要素のパブリックフィールドコピーが作成されるだけで、 [x:ClassModifier ディレクティブ](x-classmodifier-directive.md)によって引き続き制御される true のルート要素クラスアクセスレベルが使用されます。</span><span class="sxs-lookup"><span data-stu-id="d2691-127">You can put both `x:Name` and `x:FieldModifier` on the root element, but this only makes a public field copy of the root element, with the true root element class access level still controlled by [x:ClassModifier Directive](x-classmodifier-directive.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2691-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="d2691-128">See also</span></span>

- [<span data-ttu-id="d2691-129">WPF における XAML とカスタム クラス</span><span class="sxs-lookup"><span data-stu-id="d2691-129">XAML and Custom Classes for WPF</span></span>](../wpf/advanced/xaml-and-custom-classes-for-wpf.md)
- [<span data-ttu-id="d2691-130">WPF における分離コードと XAML</span><span class="sxs-lookup"><span data-stu-id="d2691-130">Code-Behind and XAML in WPF</span></span>](../wpf/advanced/code-behind-and-xaml-in-wpf.md)
- [<span data-ttu-id="d2691-131">x:Name ディレクティブ</span><span class="sxs-lookup"><span data-stu-id="d2691-131">x:Name Directive</span></span>](x-name-directive.md)
- [<span data-ttu-id="d2691-132">WPF アプリケーション (WPF) のビルド</span><span class="sxs-lookup"><span data-stu-id="d2691-132">Building a WPF Application (WPF)</span></span>](../wpf/app-development/building-a-wpf-application-wpf.md)
- [<span data-ttu-id="d2691-133">x:ClassModifier ディレクティブ</span><span class="sxs-lookup"><span data-stu-id="d2691-133">x:ClassModifier Directive</span></span>](x-classmodifier-directive.md)
