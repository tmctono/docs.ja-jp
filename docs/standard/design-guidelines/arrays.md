---
title: 配列
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- class library design guidelines [.NET Framework], arrays
- arrays [.NET Framework], usage guidelines
- empty arrays
ms.assetid: 66a1b3d8-6f3f-4715-b235-e1ff95e32d8e
author: KrzysztofCwalina
ms.openlocfilehash: dd30cdee0440553a9f955f0b3f4ee420e938b9ea
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61864118"
---
# <a name="arrays"></a><span data-ttu-id="0a9ef-102">配列</span><span class="sxs-lookup"><span data-stu-id="0a9ef-102">Arrays</span></span>
<span data-ttu-id="0a9ef-103">**✓ DO** パブリック Api で配列にコレクションの使用を優先します。</span><span class="sxs-lookup"><span data-stu-id="0a9ef-103">**✓ DO** prefer using collections over arrays in public APIs.</span></span> <span data-ttu-id="0a9ef-104">[コレクション](../../../docs/standard/design-guidelines/guidelines-for-collections.md)セクション コレクションと配列の間で選択する方法について詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="0a9ef-104">The [Collections](../../../docs/standard/design-guidelines/guidelines-for-collections.md) section provides details about how to choose between collections and arrays.</span></span>  
  
 <span data-ttu-id="0a9ef-105">**X DO NOT** 読み取り専用配列フィールドを使用します。</span><span class="sxs-lookup"><span data-stu-id="0a9ef-105">**X DO NOT** use read-only array fields.</span></span> <span data-ttu-id="0a9ef-106">フィールド自体は読み取り専用と、変更できない配列内の要素を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="0a9ef-106">The field itself is read-only and can't be changed, but elements in the array can be changed.</span></span>  
  
 <span data-ttu-id="0a9ef-107">**✓ CONSIDER** 多次元配列ではなくジャグ配列を使用します。</span><span class="sxs-lookup"><span data-stu-id="0a9ef-107">**✓ CONSIDER** using jagged arrays instead of multidimensional arrays.</span></span>  
  
 <span data-ttu-id="0a9ef-108">ジャグ配列は、要素も配列を含む配列です。</span><span class="sxs-lookup"><span data-stu-id="0a9ef-108">A jagged array is an array with elements that are also arrays.</span></span> <span data-ttu-id="0a9ef-109">配列の要素を構成するには、多次元配列と比較データ (スパース マトリックスなど) のいくつかのセットに対して無駄な小さい領域に、さまざまなサイズを指定できます。</span><span class="sxs-lookup"><span data-stu-id="0a9ef-109">The arrays that make up the elements can be of different sizes, leading to less wasted space for some sets of data (e.g., sparse matrix) compared to multidimensional arrays.</span></span> <span data-ttu-id="0a9ef-110">さらに、いくつかのシナリオで実行時パフォーマンスの向上を発生する可能性がありますので、CLR は、ジャグ配列のインデックス操作を最適化します。</span><span class="sxs-lookup"><span data-stu-id="0a9ef-110">Furthermore, the CLR optimizes index operations on jagged arrays, so they might exhibit better runtime performance in some scenarios.</span></span>  
  
 <span data-ttu-id="0a9ef-111">*Portions © 2005, 2009 Microsoft Corporation.All rights reserved.*</span><span class="sxs-lookup"><span data-stu-id="0a9ef-111">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="0a9ef-112">*Pearson Education, Inc. からのアクセス許可によって了承を得て転載[Framework デザイン ガイドライン。規則、手法、および再利用可能な .NET ライブラリの第 2 版のパターン](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)Krzysztof Cwalina、Brad 内容では、Microsoft Windows の開発シリーズの一部として、Addison-wesley Professional、2008 年 10 月 22日を公開します。*</span><span class="sxs-lookup"><span data-stu-id="0a9ef-112">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a9ef-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="0a9ef-113">See also</span></span>

- <xref:System.Array>
- [<span data-ttu-id="0a9ef-114">フレームワーク デザインのガイドライン</span><span class="sxs-lookup"><span data-stu-id="0a9ef-114">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
- [<span data-ttu-id="0a9ef-115">使用方法のガイドライン</span><span class="sxs-lookup"><span data-stu-id="0a9ef-115">Usage Guidelines</span></span>](../../../docs/standard/design-guidelines/usage-guidelines.md)
