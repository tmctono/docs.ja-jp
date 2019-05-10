---
title: x:FieldModifier ディレクティブ
ms.date: 03/30/2017
helpviewer_keywords:
- FieldModifier attribute in XAML [XAML Services]
- x:FieldModifier attribute [XAML Services]
- XAML [XAML Services], x:FieldModifier attribute
ms.assetid: ed427cd4-2f35-4d24-bd2f-0fa7b71ec248
ms.openlocfilehash: 0394522b8a006d6b187219c8ef7dfccd6556ffca
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64617072"
---
# <a name="xfieldmodifier-directive"></a><span data-ttu-id="9a1b5-102">x:FieldModifier ディレクティブ</span><span class="sxs-lookup"><span data-stu-id="9a1b5-102">x:FieldModifier Directive</span></span>
<span data-ttu-id="9a1b5-103">名前付きオブジェクトの参照フィールドが定義されているように、XAML のコンパイルの動作を変更します<xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType>へのアクセスの代わりに、<xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>既定の動作。</span><span class="sxs-lookup"><span data-stu-id="9a1b5-103">Modifies XAML compilation behavior so that fields for named object references are defined with <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> access instead of the <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> default behavior.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="9a1b5-104">XAML 属性の使用方法</span><span class="sxs-lookup"><span data-stu-id="9a1b5-104">XAML Attribute Usage</span></span>  
  
```xaml  
<object x:FieldModifier="Public".../>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="9a1b5-105">XAML 値</span><span class="sxs-lookup"><span data-stu-id="9a1b5-105">XAML Values</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="9a1b5-106">*Public*</span><span class="sxs-lookup"><span data-stu-id="9a1b5-106">*Public*</span></span>|<span data-ttu-id="9a1b5-107">正確な文字列の指定に渡す<xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType>と<xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>は使用する分離コードのプログラミング言語によって異なります。</span><span class="sxs-lookup"><span data-stu-id="9a1b5-107">The exact string you pass to specify <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> versus <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> varies, depending on the code-behind programming language that is used.</span></span> <span data-ttu-id="9a1b5-108">「解説」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9a1b5-108">See Remarks.</span></span>|  
  
## <a name="dependencies"></a><span data-ttu-id="9a1b5-109">依存関係</span><span class="sxs-lookup"><span data-stu-id="9a1b5-109">Dependencies</span></span>  
 <span data-ttu-id="9a1b5-110">XAML の運用環境で使用する場合`x:FieldModifier`どこでも、その XAML 運用環境のルート要素を宣言する必要があります、 [X:class ディレクティブ](x-class-directive.md)します。</span><span class="sxs-lookup"><span data-stu-id="9a1b5-110">If a XAML production uses `x:FieldModifier` anywhere, the root element of that XAML production must declare an [x:Class Directive](x-class-directive.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9a1b5-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="9a1b5-111">Remarks</span></span>  
 <span data-ttu-id="9a1b5-112">`x:FieldModifier` クラスまたはそのメンバーの一般的なアクセス レベルを宣言するのには関係ありません。</span><span class="sxs-lookup"><span data-stu-id="9a1b5-112">`x:FieldModifier` is not relevant for declaring the general access level of a class or its members.</span></span> <span data-ttu-id="9a1b5-113">XAML の運用環境の一部である、特定の XAML オブジェクトが処理され、アプリケーションのオブジェクト グラフにアクセス可能であるオブジェクトになりますが XAML 処理の動作にのみ関連します。</span><span class="sxs-lookup"><span data-stu-id="9a1b5-113">It is relevant only for XAML-processing behavior when a particular XAML object that is part of a XAML production is processed, and becomes an object that is potentially accessible in the object graph of an application.</span></span> <span data-ttu-id="9a1b5-114">既定では、このようなオブジェクトのフィールド参照は厳重に保管され、コントロールのコンシューマーは、オブジェクト グラフを直接変更できなきます。</span><span class="sxs-lookup"><span data-stu-id="9a1b5-114">By default, the field reference for such an object is kept private, which prevents control consumers from modifying the object graph directly.</span></span> <span data-ttu-id="9a1b5-115">代わりに、コントロールのコンシューマーは、レイアウトのルートの子要素のコレクション、専用のパブリック プロパティを取得することによってなどのプログラミング モデル、によって実現される標準のパターンを使用して、オブジェクト グラフを変更する必要があり、具合です。</span><span class="sxs-lookup"><span data-stu-id="9a1b5-115">Instead, control consumers are expected to modify the object graph by using standard patterns that are enabled by programming models, such as by obtaining the layout root, the child element collections, the dedicated public properties, and so on.</span></span>  
  
 <span data-ttu-id="9a1b5-116">値、`x:FieldModifier`属性は、プログラミング言語によって異なるし、特定のフレームワークでの目的が異なることができます。</span><span class="sxs-lookup"><span data-stu-id="9a1b5-116">The value for the `x:FieldModifier` attribute varies by programming language, and its purpose can vary in specific frameworks.</span></span> <span data-ttu-id="9a1b5-117">使用する文字列は、各言語の実装に依存、<xref:System.CodeDom.Compiler.CodeDomProvider>よぶ型コンバーターを返しますの意味を定義する<xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType>と<xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>、その言語が、大文字小文字を区別するかどうか。</span><span class="sxs-lookup"><span data-stu-id="9a1b5-117">The string to use depends on how each language implements its <xref:System.CodeDom.Compiler.CodeDomProvider> and the type converters it returns to define the meanings for <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> and <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>, and whether that language is case sensitive.</span></span>  
  
- <span data-ttu-id="9a1b5-118">C# の場合、文字列を指定する渡す<xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType>は`public`します。</span><span class="sxs-lookup"><span data-stu-id="9a1b5-118">For C#, the string to pass to designate <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> is `public`.</span></span>  
  
- <span data-ttu-id="9a1b5-119">Microsoft Visual Basic .net の指定に渡す文字列<xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType>は`Public`します。</span><span class="sxs-lookup"><span data-stu-id="9a1b5-119">For Microsoft Visual Basic .NET, the string to pass to designate <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> is `Public`.</span></span>  
  
- <span data-ttu-id="9a1b5-120">[!INCLUDE[TLA2#tla_cppcli](../../../includes/tla2sharptla-cppcli-md.md)]XAML のターゲットを現在存在しません。 以外に渡す文字列が定義されているため、します。</span><span class="sxs-lookup"><span data-stu-id="9a1b5-120">For [!INCLUDE[TLA2#tla_cppcli](../../../includes/tla2sharptla-cppcli-md.md)], no targets for XAML currently exist; therefore, the string to pass is undefined.</span></span>  
  
 <span data-ttu-id="9a1b5-121">指定することも<xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>(`internal`でC#、 `Friend` Visual Basic で) が指定する<xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>通常でないため、`NotPublic`動作は、既定では既に。</span><span class="sxs-lookup"><span data-stu-id="9a1b5-121">You can also specify <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> (`internal` in C#, `Friend` in Visual Basic) but specifying <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> is unusual because `NotPublic` as the behavior is already the default.</span></span>  
  
 <span data-ttu-id="9a1b5-122"><xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> XAML が作成した要素へのアクセスを XAML がコンパイルされるアセンブリの外側のコードが必要があることを頻繁にではないために、既定の動作です。</span><span class="sxs-lookup"><span data-stu-id="9a1b5-122"><xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> is the default behavior because it is infrequent that code outside the assembly that compiled the XAML needs access to a XAML-created element.</span></span> <span data-ttu-id="9a1b5-123">具体的に設定していない場合は、XAML のコンパイル動作と WPF のセキュリティ アーキテクチャに、public 要素のインスタンスを格納するフィールドは宣言しません、`x:FieldModifier`パブリック アクセスを許可します。</span><span class="sxs-lookup"><span data-stu-id="9a1b5-123">WPF security architecture together with XAML compilation behavior will not declare fields that store element instances as public, unless you specifically set the `x:FieldModifier` to allow public access.</span></span>  
  
 <span data-ttu-id="9a1b5-124">`x:FieldModifier` のみを持つ要素の関係、 [X:name ディレクティブ](x-name-directive.md)その名前がパブリックになった後にフィールドを参照に使用されるためです。</span><span class="sxs-lookup"><span data-stu-id="9a1b5-124">`x:FieldModifier` is only relevant for elements with an [x:Name Directive](x-name-directive.md) because that name is used to reference the field after it is public.</span></span>  
  
 <span data-ttu-id="9a1b5-125">既定では、ルート要素の部分クラスはパブリックです。ただし、行うことができます、非公開を使用して、 [X:classmodifier ディレクティブ](x-classmodifier-directive.md)します。</span><span class="sxs-lookup"><span data-stu-id="9a1b5-125">By default, the partial class for the root element is public; however, you can make it nonpublic by using the [x:ClassModifier Directive](x-classmodifier-directive.md).</span></span> <span data-ttu-id="9a1b5-126">[X:classmodifier ディレクティブ](x-classmodifier-directive.md)ルート要素クラスのインスタンスのアクセス レベルにも影響します。</span><span class="sxs-lookup"><span data-stu-id="9a1b5-126">The [x:ClassModifier Directive](x-classmodifier-directive.md) also affects the access level of the instance of the root element class.</span></span> <span data-ttu-id="9a1b5-127">両方を配置できる`x:Name`と`x:FieldModifier`ルートに要素が、これだけパブリック フィールドのコピーを作成真のルート要素クラスのアクセス レベルも、ルート要素によって制御される[X:classmodifier ディレクティブ](x-classmodifier-directive.md)。</span><span class="sxs-lookup"><span data-stu-id="9a1b5-127">You can put both `x:Name` and `x:FieldModifier` on the root element, but this only makes a public field copy of the root element, with the true root element class access level still controlled by [x:ClassModifier Directive](x-classmodifier-directive.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a1b5-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="9a1b5-128">See also</span></span>

- [<span data-ttu-id="9a1b5-129">WPF における XAML とカスタム クラス</span><span class="sxs-lookup"><span data-stu-id="9a1b5-129">XAML and Custom Classes for WPF</span></span>](../wpf/advanced/xaml-and-custom-classes-for-wpf.md)
- [<span data-ttu-id="9a1b5-130">WPF における分離コードと XAML</span><span class="sxs-lookup"><span data-stu-id="9a1b5-130">Code-Behind and XAML in WPF</span></span>](../wpf/advanced/code-behind-and-xaml-in-wpf.md)
- [<span data-ttu-id="9a1b5-131">x:Name ディレクティブ</span><span class="sxs-lookup"><span data-stu-id="9a1b5-131">x:Name Directive</span></span>](x-name-directive.md)
- [<span data-ttu-id="9a1b5-132">WPF アプリケーション (WPF) のビルド</span><span class="sxs-lookup"><span data-stu-id="9a1b5-132">Building a WPF Application (WPF)</span></span>](../wpf/app-development/building-a-wpf-application-wpf.md)
- [<span data-ttu-id="9a1b5-133">x:ClassModifier ディレクティブ</span><span class="sxs-lookup"><span data-stu-id="9a1b5-133">x:ClassModifier Directive</span></span>](x-classmodifier-directive.md)
