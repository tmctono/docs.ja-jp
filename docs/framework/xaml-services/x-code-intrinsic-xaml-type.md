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
ms.openlocfilehash: 7bb78b05be7b3edc4471bc276010eabd92a07a14
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61971848"
---
# <a name="xcode-intrinsic-xaml-type"></a><span data-ttu-id="241b2-102">x:Code 組み込み XAML 型 </span><span class="sxs-lookup"><span data-stu-id="241b2-102">x:Code Intrinsic XAML Type</span></span>
<span data-ttu-id="241b2-103">XAML の運用環境でコードを配置をできます。</span><span class="sxs-lookup"><span data-stu-id="241b2-103">Allows placement of code within a XAML production.</span></span> <span data-ttu-id="241b2-104">XAML、またはランタイムによって解釈など、後から使用の XAML の運用環境で左側をコンパイルする任意の XAML プロセッサ実装によってこのようなコードをコンパイルすることができますか。</span><span class="sxs-lookup"><span data-stu-id="241b2-104">Such code can either be compiled by any XAML processor implementation that compiles XAML, or left in the XAML production for later uses such as interpretation by a runtime.</span></span>  
  
## <a name="xaml-object-element-usage"></a><span data-ttu-id="241b2-105">XAML オブジェクト要素の使用方法</span><span class="sxs-lookup"><span data-stu-id="241b2-105">XAML Object Element Usage</span></span>  
  
```  
<x:Code>  
   // code instructions, usually enclosed by CDATA...  
</x:Code>  
```  
  
## <a name="remarks"></a><span data-ttu-id="241b2-106">Remarks</span><span class="sxs-lookup"><span data-stu-id="241b2-106">Remarks</span></span>  
 <span data-ttu-id="241b2-107">内のコード、 `x:Code` XAML ディレクティブ要素は、一般的な XML 名前空間内で解釈のままと XAML 名前空間を提供します。</span><span class="sxs-lookup"><span data-stu-id="241b2-107">The code within the `x:Code` XAML directive element is still interpreted within the general XML namespace and the XAML namespaces provided.</span></span> <span data-ttu-id="241b2-108">したがって、用のコードを囲むために必要な通常は`x:Code`内で、`CDATA`セグメント。</span><span class="sxs-lookup"><span data-stu-id="241b2-108">Therefore, it is usually necessary to enclose the code used for `x:Code` inside a `CDATA` segment.</span></span>  
  
 <span data-ttu-id="241b2-109">`x:Code` XAML の運用環境のすべての可能な展開メカニズムは許可されません。</span><span class="sxs-lookup"><span data-stu-id="241b2-109">`x:Code` is not permitted for all possible deployment mechanisms of a XAML production.</span></span> <span data-ttu-id="241b2-110">特定のフレームワーク (WPF など) では、コードをコンパイルする必要があります。</span><span class="sxs-lookup"><span data-stu-id="241b2-110">In specific frameworks (for example WPF) the code must be compiled.</span></span> <span data-ttu-id="241b2-111">その他のフレームワークで`x:Code`使用状況を通常許可されない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="241b2-111">In other frameworks, `x:Code` usage might be generally disallowed.</span></span>  
  
 <span data-ttu-id="241b2-112">管理を許可するフレームワーク`x:Code`コンテンツに使用する適切な言語コンパイラ`x:Code`コンテンツが設定およびアプリケーションをコンパイルするために使用を含むプロジェクトのターゲットによって決定されます。</span><span class="sxs-lookup"><span data-stu-id="241b2-112">For frameworks that permit managed `x:Code` content, the correct language compiler to use for `x:Code` content is determined by settings and targets of the containing project that is used to compile the application.</span></span>  
  
## <a name="wpf-usage-notes"></a><span data-ttu-id="241b2-113">WPF の使用上の注意</span><span class="sxs-lookup"><span data-stu-id="241b2-113">WPF Usage Notes</span></span>  
 <span data-ttu-id="241b2-114">内で宣言されているコード`x:Code`は WPF がいくつかの注目すべき制限があります。</span><span class="sxs-lookup"><span data-stu-id="241b2-114">Code declared within `x:Code` for WPF has several notable limitations:</span></span>  
  
- <span data-ttu-id="241b2-115">`x:Code`ディレクティブ要素は XAML の運用環境のルート要素の直接の子要素である必要があります。</span><span class="sxs-lookup"><span data-stu-id="241b2-115">The `x:Code` directive element must be an immediate child element of the root element of the XAML production.</span></span>  
  
- <span data-ttu-id="241b2-116">[X:class ディレクティブ](x-class-directive.md)親ルート要素に提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="241b2-116">[x:Class Directive](x-class-directive.md) must be provided on the parent root element.</span></span>  
  
- <span data-ttu-id="241b2-117">コード内に配置`x:Code`は、その XAML ページを既に作成されている部分クラスのスコープ内にあるコンパイルで扱われます。</span><span class="sxs-lookup"><span data-stu-id="241b2-117">The code placed within `x:Code` will be treated by compilation to be within the scope of the partial class that is already being created for that XAML page.</span></span> <span data-ttu-id="241b2-118">したがってすべてのコードを定義するには、その部分クラスのメンバーまたは変数があります。</span><span class="sxs-lookup"><span data-stu-id="241b2-118">Therefore all code you define must be members or variables of that partial class.</span></span>  
  
- <span data-ttu-id="241b2-119">部分クラス内にクラスを入れ子にして他よりも、追加のクラスを定義することはできません (入れ子が許可されているが、XAML で入れ子になったクラスは参照できないために、通常ではありません)。</span><span class="sxs-lookup"><span data-stu-id="241b2-119">You cannot define additional classes, other than by nesting a class inside the partial class (nesting is allowed, but it is not typical because nested classes cannot be referenced in XAML).</span></span> <span data-ttu-id="241b2-120">既存の部分クラスに使用される名前空間以外の CLR 名前空間を定義またはに追加できません。</span><span class="sxs-lookup"><span data-stu-id="241b2-120">CLR namespaces other than the namespace that is used for the existing partial class cannot be defined or added to.</span></span>  
  
- <span data-ttu-id="241b2-121">部分クラスの CLR 名前空間の外部のコード エンティティを参照する必要がありますすべて完全修飾します。</span><span class="sxs-lookup"><span data-stu-id="241b2-121">References to code entities outside the partial class CLR namespace must all be fully qualified.</span></span> <span data-ttu-id="241b2-122">部分クラスのオーバーライド可能なメンバーをオーバーライド メンバーが宣言されている場合は、これを言語固有の override キーワードを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="241b2-122">If members being declared are overrides to the partial class overridable members, this must be specified with the language-specific override keyword.</span></span> <span data-ttu-id="241b2-123">メンバーが宣言されている場合`x:Code`XAML から作成された部分クラスのメンバーと競合するスコープ、このような方法で、コンパイラが、競合を報告する XAML ファイルことはできませんコンパイルまたは読み込みます。</span><span class="sxs-lookup"><span data-stu-id="241b2-123">If members declared in `x:Code` scope conflict with members of the partial class created out of the XAML, in such a way that the compiler reports the conflict, the XAML file cannot compile or load.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="241b2-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="241b2-124">See also</span></span>

- [<span data-ttu-id="241b2-125">x:Class ディレクティブ</span><span class="sxs-lookup"><span data-stu-id="241b2-125">x:Class Directive</span></span>](x-class-directive.md)
- [<span data-ttu-id="241b2-126">WPF における分離コードと XAML</span><span class="sxs-lookup"><span data-stu-id="241b2-126">Code-Behind and XAML in WPF</span></span>](../wpf/advanced/code-behind-and-xaml-in-wpf.md)
- [<span data-ttu-id="241b2-127">XAML の概要 (WPF)</span><span class="sxs-lookup"><span data-stu-id="241b2-127">XAML Overview (WPF)</span></span>](../wpf/advanced/xaml-overview-wpf.md)
