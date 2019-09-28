---
title: メンバーのオーバーロード
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- default arguments
- members [.NET Framework], overloaded
- member design guidelines [.NET Framework], overloading
- overloaded members
- signatures, members
ms.assetid: 964ba19e-8b94-4b5b-b1e3-5a0b531a0bb1
author: KrzysztofCwalina
ms.openlocfilehash: 4caa0ae78d168b23fd2862153bef0e3960d3ea42
ms.sourcegitcommit: da2dd2772fcf32b44eb18b1cbe8affd17b1753c9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/27/2019
ms.locfileid: "71392948"
---
# <a name="member-overloading"></a><span data-ttu-id="36ece-102">メンバーのオーバーロード</span><span class="sxs-lookup"><span data-stu-id="36ece-102">Member Overloading</span></span>
<span data-ttu-id="36ece-103">メンバーのオーバーロードとは、同じ型に複数のメンバーを作成し、パラメーターの数または型だけではなく、同じ名前を持つことを意味します。</span><span class="sxs-lookup"><span data-stu-id="36ece-103">Member overloading means creating two or more members on the same type that differ only in the number or type of parameters but have the same name.</span></span> <span data-ttu-id="36ece-104">たとえば、次の例では、`WriteLine` メソッドがオーバーロードされています。</span><span class="sxs-lookup"><span data-stu-id="36ece-104">For example, in the following, the `WriteLine` method is overloaded:</span></span>  
  
```csharp  
public static class Console {  
    public void WriteLine();  
    public void WriteLine(string value);  
    public void WriteLine(bool value);  
    ...  
}  
```  
  
 <span data-ttu-id="36ece-105">パラメーターを持つことができるのはメソッド、コンストラクター、およびインデックス付きプロパティだけなので、これらのメンバーのみをオーバーロードできます。</span><span class="sxs-lookup"><span data-stu-id="36ece-105">Because only methods, constructors, and indexed properties can have parameters, only those members can be overloaded.</span></span>  
  
 <span data-ttu-id="36ece-106">オーバーロードは、再利用可能なライブラリのユーザビリティ、生産性、および読みやすさを向上させるための最も重要な手法の1つです。</span><span class="sxs-lookup"><span data-stu-id="36ece-106">Overloading is one of the most important techniques for improving usability, productivity, and readability of reusable libraries.</span></span> <span data-ttu-id="36ece-107">パラメーターの数をオーバーロードすることで、コンストラクターとメソッドのより単純なバージョンを提供できるようになります。</span><span class="sxs-lookup"><span data-stu-id="36ece-107">Overloading on the number of parameters makes it possible to provide simpler versions of constructors and methods.</span></span> <span data-ttu-id="36ece-108">パラメーターの型をオーバーロードすると、選択した異なる型のセットに対して同じ操作を実行するメンバーに対して同じメンバー名を使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="36ece-108">Overloading on the parameter type makes it possible to use the same member name for members performing identical operations on a selected set of different types.</span></span>  
  
 <span data-ttu-id="36ece-109">**✓ DO** 短いオーバー ロードで使用される既定値を示すためにわかりやすいパラメーター名を使用しようとしています。</span><span class="sxs-lookup"><span data-stu-id="36ece-109">**✓ DO** try to use descriptive parameter names to indicate the default used by shorter overloads.</span></span>  
  
 <span data-ttu-id="36ece-110">**X AVOID** オーバー ロードのパラメーター名は任意で変更します。</span><span class="sxs-lookup"><span data-stu-id="36ece-110">**X AVOID** arbitrarily varying parameter names in overloads.</span></span> <span data-ttu-id="36ece-111">1つのオーバーロード内のパラメーターが、別のオーバーロード内のパラメーターと同じ入力を表している場合、パラメーターの名前は同じである必要があります。</span><span class="sxs-lookup"><span data-stu-id="36ece-111">If a parameter in one overload represents the same input as a parameter in another overload, the parameters should have the same name.</span></span>  
  
 <span data-ttu-id="36ece-112">**X AVOID** メンバーをオーバー ロードされているのパラメーターの順序で一貫していません。</span><span class="sxs-lookup"><span data-stu-id="36ece-112">**X AVOID** being inconsistent in the ordering of parameters in overloaded members.</span></span> <span data-ttu-id="36ece-113">同じ名前のパラメーターは、すべてのオーバーロードで同じ位置に出現します。</span><span class="sxs-lookup"><span data-stu-id="36ece-113">Parameters with the same name should appear in the same position in all overloads.</span></span>  
  
 <span data-ttu-id="36ece-114">**✓ DO** (拡張機能が必要な場合)、最長のオーバー ロードだけの仮想を作成します。</span><span class="sxs-lookup"><span data-stu-id="36ece-114">**✓ DO** make only the longest overload virtual (if extensibility is required).</span></span> <span data-ttu-id="36ece-115">より短いオーバーロードでは、より長いオーバーロードに対してを呼び出すだけで済みます。</span><span class="sxs-lookup"><span data-stu-id="36ece-115">Shorter overloads should simply call through to a longer overload.</span></span>  
  
 <span data-ttu-id="36ece-116">**X DO NOT** 使用`ref`または`out`メンバーをオーバー ロードする修飾子です。</span><span class="sxs-lookup"><span data-stu-id="36ece-116">**X DO NOT** use `ref` or `out` modifiers to overload members.</span></span>  
  
 <span data-ttu-id="36ece-117">一部の言語では、このようなオーバーロードの呼び出しを解決できません。</span><span class="sxs-lookup"><span data-stu-id="36ece-117">Some languages cannot resolve calls to overloads like this.</span></span> <span data-ttu-id="36ece-118">また、通常、このようなオーバーロードには完全に異なるセマンティクスがあり、オーバーロードは使用できませんが、2つの異なるメソッドを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="36ece-118">In addition, such overloads usually have completely different semantics and probably should not be overloads but two separate methods instead.</span></span>  
  
 <span data-ttu-id="36ece-119">**X DO NOT** 同じ位置と類似した種類のパラメーターを使用してまだセマンティクスが異なるオーバー ロードがあります。</span><span class="sxs-lookup"><span data-stu-id="36ece-119">**X DO NOT** have overloads with parameters at the same position and similar types yet with different semantics.</span></span>  
  
 <span data-ttu-id="36ece-120">**✓ DO** 許可`null`省略可能な引数に渡されます。</span><span class="sxs-lookup"><span data-stu-id="36ece-120">**✓ DO**  allow `null` to be passed for optional arguments.</span></span>  
  
 <span data-ttu-id="36ece-121">**✓ DO** メンバーの既定の引数を持つメンバーを定義するのではなく、オーバー ロードを使用します。</span><span class="sxs-lookup"><span data-stu-id="36ece-121">**✓ DO** use member overloading rather than defining members with default arguments.</span></span>  
  
 <span data-ttu-id="36ece-122">既定の引数は CLS に準拠していません。</span><span class="sxs-lookup"><span data-stu-id="36ece-122">Default arguments are not CLS compliant.</span></span>  
  
 <span data-ttu-id="36ece-123">*Portions © 2005, 2009 Microsoft Corporation.All rights reserved.*</span><span class="sxs-lookup"><span data-stu-id="36ece-123">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="36ece-124">[ Framework のデザインガイドラインから、ピアソン教育, Inc. のアクセス許可によって @no__t。再利用可能な .NET ライブラリの規則、表現、パターン、2番目のエディション @ no__t-0 by Krzysztof Cwalina、および Addison-Wesley Professional によって Microsoft Windows 開発シリーズの一部として2008年10月22日に公開さ @no__t れました。</span><span class="sxs-lookup"><span data-stu-id="36ece-124">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36ece-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="36ece-125">See also</span></span>

- [<span data-ttu-id="36ece-126">メンバーのデザインのガイドライン</span><span class="sxs-lookup"><span data-stu-id="36ece-126">Member Design Guidelines</span></span>](../../../docs/standard/design-guidelines/member.md)
- [<span data-ttu-id="36ece-127">フレームワーク デザインのガイドライン</span><span class="sxs-lookup"><span data-stu-id="36ece-127">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
