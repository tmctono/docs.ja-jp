---
title: 'x:Code 組み込み XAML 型 '
ms.date: 03/30/2017
f1_keywords:
- Code
- x:Code
- xCode
helpviewer_keywords:
- Code directive in XAML [XAML Services]
- x:Code XAML directive element [XAML Services]
- XAML [XAML Services], x:Code directive element
ms.assetid: 87986b13-1a2e-4830-ae36-15f9dc5629e8
ms.openlocfilehash: 4da72ed630c1df001e3fd6c7e55f866b94c4d9b1
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/27/2020
ms.locfileid: "81432804"
---
# <a name="xcode-intrinsic-xaml-type"></a><span data-ttu-id="a488b-102">x:Code 組み込み XAML 型 </span><span class="sxs-lookup"><span data-stu-id="a488b-102">x:Code Intrinsic XAML Type</span></span>
<span data-ttu-id="a488b-103">XAML 運用環境内でコードを配置できます。</span><span class="sxs-lookup"><span data-stu-id="a488b-103">Allows placement of code within a XAML production.</span></span> <span data-ttu-id="a488b-104">このようなコードは、XAML をコンパイルする任意の XAML プロセッサ実装によってコンパイルすることも、ランタイムによる解釈など、後で使用するために XAML の運用環境に残してコンパイルすることもできます。</span><span class="sxs-lookup"><span data-stu-id="a488b-104">Such code can either be compiled by any XAML processor implementation that compiles XAML, or left in the XAML production for later uses such as interpretation by a runtime.</span></span>

## <a name="xaml-object-element-usage"></a><span data-ttu-id="a488b-105">XAML オブジェクト要素の使用方法</span><span class="sxs-lookup"><span data-stu-id="a488b-105">XAML Object Element Usage</span></span>

```xaml
<x:Code>
   // code instructions, usually enclosed by CDATA...
</x:Code>
```

## <a name="remarks"></a><span data-ttu-id="a488b-106">解説</span><span class="sxs-lookup"><span data-stu-id="a488b-106">Remarks</span></span>

<span data-ttu-id="a488b-107">XAML ディレクティブ要素`x:Code`内のコードは、一般的な XML 名前空間と提供される XAML 名前空間内で解釈されます。</span><span class="sxs-lookup"><span data-stu-id="a488b-107">The code within the `x:Code` XAML directive element is still interpreted within the general XML namespace and the XAML namespaces provided.</span></span> <span data-ttu-id="a488b-108">したがって、通常は、セグメント内で使用されるコードを`x:Code`囲む必要`CDATA`があります。</span><span class="sxs-lookup"><span data-stu-id="a488b-108">Therefore, it is usually necessary to enclose the code used for `x:Code` inside a `CDATA` segment.</span></span>

<span data-ttu-id="a488b-109">`x:Code`XAML の運用環境で可能なすべての展開メカニズムに対して許可されていません。</span><span class="sxs-lookup"><span data-stu-id="a488b-109">`x:Code` is not permitted for all possible deployment mechanisms of a XAML production.</span></span> <span data-ttu-id="a488b-110">特定のフレームワーク (たとえば、WPF) では、コードをコンパイルする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a488b-110">In specific frameworks (for example WPF) the code must be compiled.</span></span> <span data-ttu-id="a488b-111">他のフレームワークでは、`x:Code`一般的に使用が許可されない場合があります。</span><span class="sxs-lookup"><span data-stu-id="a488b-111">In other frameworks, `x:Code` usage might be generally disallowed.</span></span>

<span data-ttu-id="a488b-112">マネージ`x:Code`コンテンツを許可するフレームワークでは、`x:Code`コンテンツに使用する適切な言語コンパイラは、アプリケーションのコンパイルに使用される、含まれているプロジェクトの設定とターゲットによって決定されます。</span><span class="sxs-lookup"><span data-stu-id="a488b-112">For frameworks that permit managed `x:Code` content, the correct language compiler to use for `x:Code` content is determined by settings and targets of the containing project that is used to compile the application.</span></span>

## <a name="wpf-usage-notes"></a><span data-ttu-id="a488b-113">WPF の使用上の注意</span><span class="sxs-lookup"><span data-stu-id="a488b-113">WPF Usage Notes</span></span>

<span data-ttu-id="a488b-114">WPF`x:Code`で宣言されたコードには、次のようないくつかの特大な制限があります。</span><span class="sxs-lookup"><span data-stu-id="a488b-114">Code declared within `x:Code` for WPF has several notable limitations:</span></span>

- <span data-ttu-id="a488b-115">ディレクティブ`x:Code`要素は、XAML の運用環境のルート要素の直接の子要素である必要があります。</span><span class="sxs-lookup"><span data-stu-id="a488b-115">The `x:Code` directive element must be an immediate child element of the root element of the XAML production.</span></span>

- <span data-ttu-id="a488b-116">[x:クラスディレクティブ](xclass-directive.md)は、親ルート要素に指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a488b-116">[x:Class Directive](xclass-directive.md) must be provided on the parent root element.</span></span>

- <span data-ttu-id="a488b-117">内に`x:Code`配置されたコードは、その XAML ページに対して既に作成されている部分クラスのスコープ内に収まるように、コンパイルによって処理されます。</span><span class="sxs-lookup"><span data-stu-id="a488b-117">The code placed within `x:Code` will be treated by compilation to be within the scope of the partial class that is already being created for that XAML page.</span></span> <span data-ttu-id="a488b-118">したがって、定義するすべてのコードは、その部分クラスのメンバーまたは変数である必要があります。</span><span class="sxs-lookup"><span data-stu-id="a488b-118">Therefore all code you define must be members or variables of that partial class.</span></span>

- <span data-ttu-id="a488b-119">部分クラス内にクラスを入れ子にする以外に、追加のクラスを定義することはできません (入れ子は許可されますが、入れ子になったクラスは XAML では参照できないため、通常は使用できません)。</span><span class="sxs-lookup"><span data-stu-id="a488b-119">You cannot define additional classes, other than by nesting a class inside the partial class (nesting is allowed, but it is not typical because nested classes cannot be referenced in XAML).</span></span> <span data-ttu-id="a488b-120">既存の部分クラスに使用される名前空間以外の CLR 名前空間を定義または追加することはできません。</span><span class="sxs-lookup"><span data-stu-id="a488b-120">CLR namespaces other than the namespace that is used for the existing partial class cannot be defined or added to.</span></span>

- <span data-ttu-id="a488b-121">部分クラス CLR 名前空間の外部にあるコード エンティティへの参照はすべて完全修飾されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="a488b-121">References to code entities outside the partial class CLR namespace must all be fully qualified.</span></span> <span data-ttu-id="a488b-122">宣言されるメンバーが部分クラスオーバーライド可能なメンバーのオーバーライドである場合は、言語固有の override キーワードを使用して指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a488b-122">If members being declared are overrides to the partial class overridable members, this must be specified with the language-specific override keyword.</span></span> <span data-ttu-id="a488b-123">スコープで宣言された`x:Code`メンバーが XAML から作成された部分クラスのメンバーと競合する場合、コンパイラが競合を報告するような方法で、XAML ファイルをコンパイルまたは読み込むことができません。</span><span class="sxs-lookup"><span data-stu-id="a488b-123">If members declared in `x:Code` scope conflict with members of the partial class created out of the XAML, in such a way that the compiler reports the conflict, the XAML file cannot compile or load.</span></span>

## <a name="see-also"></a><span data-ttu-id="a488b-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="a488b-124">See also</span></span>

- [<span data-ttu-id="a488b-125">x:Class ディレクティブ</span><span class="sxs-lookup"><span data-stu-id="a488b-125">x:Class Directive</span></span>](xclass-directive.md)
- [<span data-ttu-id="a488b-126">WPF における分離コードと XAML</span><span class="sxs-lookup"><span data-stu-id="a488b-126">Code-Behind and XAML in WPF</span></span>](../../framework/wpf/advanced/code-behind-and-xaml-in-wpf.md)
- [<span data-ttu-id="a488b-127">XAML の概要 (WPF)</span><span class="sxs-lookup"><span data-stu-id="a488b-127">XAML Overview (WPF)</span></span>](../fundamentals/xaml.md)
