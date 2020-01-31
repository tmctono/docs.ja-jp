---
title: 配列
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- class library design guidelines [.NET Framework], arrays
- arrays [.NET Framework], usage guidelines
- empty arrays
ms.assetid: 66a1b3d8-6f3f-4715-b235-e1ff95e32d8e
ms.openlocfilehash: d4a1f379a88231654c710b1df7b505316377c915
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741806"
---
# <a name="arrays"></a><span data-ttu-id="3d89c-102">配列</span><span class="sxs-lookup"><span data-stu-id="3d89c-102">Arrays</span></span>
<span data-ttu-id="3d89c-103">✔️は、パブリック Api で配列に対してコレクションを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="3d89c-103">✔️ DO prefer using collections over arrays in public APIs.</span></span> <span data-ttu-id="3d89c-104">コレクション[セクションで](../../../docs/standard/design-guidelines/guidelines-for-collections.md)は、コレクションと配列のどちらかを選択する方法について詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="3d89c-104">The [Collections](../../../docs/standard/design-guidelines/guidelines-for-collections.md) section provides details about how to choose between collections and arrays.</span></span>

 <span data-ttu-id="3d89c-105">❌ 読み取り専用の配列フィールドは使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="3d89c-105">❌ DO NOT use read-only array fields.</span></span> <span data-ttu-id="3d89c-106">フィールド自体は読み取り専用であり、変更することはできませんが、配列内の要素は変更できます。</span><span class="sxs-lookup"><span data-stu-id="3d89c-106">The field itself is read-only and can't be changed, but elements in the array can be changed.</span></span>

 <span data-ttu-id="3d89c-107">✔️多次元配列の代わりにジャグ配列を使用することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="3d89c-107">✔️ CONSIDER using jagged arrays instead of multidimensional arrays.</span></span>

 <span data-ttu-id="3d89c-108">ジャグ配列は、配列でもある要素を含む配列です。</span><span class="sxs-lookup"><span data-stu-id="3d89c-108">A jagged array is an array with elements that are also arrays.</span></span> <span data-ttu-id="3d89c-109">要素を構成する配列は、さまざまなサイズになることがあり、一部のデータセット (スパースマトリックスなど) では、多次元配列と比較して無駄になる領域が少なくなります。</span><span class="sxs-lookup"><span data-stu-id="3d89c-109">The arrays that make up the elements can be of different sizes, leading to less wasted space for some sets of data (e.g., sparse matrix) compared to multidimensional arrays.</span></span> <span data-ttu-id="3d89c-110">さらに、CLR はジャグ配列に対するインデックス操作を最適化するため、一部のシナリオでは実行時のパフォーマンスが向上する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="3d89c-110">Furthermore, the CLR optimizes index operations on jagged arrays, so they might exhibit better runtime performance in some scenarios.</span></span>

 <span data-ttu-id="3d89c-111">*©2005、2009 Microsoft Corporation の部分。すべての権限が予約されています。*</span><span class="sxs-lookup"><span data-stu-id="3d89c-111">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="3d89c-112">*2008 年 10 月 22 日に Microsoft Windows Development シリーズの一部として、Addison-Wesley Professional によって発行された、Krzysztof Cwalina および Brad Abrams による「[Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)」 (フレームワーク デザイン ガイドライン: 再利用可能な .NET ライブラリの規則、用法、パターン、第 2 版) から Pearson Education, Inc. の許可を得て再印刷されています。*</span><span class="sxs-lookup"><span data-stu-id="3d89c-112">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="3d89c-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="3d89c-113">See also</span></span>

- <xref:System.Array>
- [<span data-ttu-id="3d89c-114">フレームワーク デザインのガイドライン</span><span class="sxs-lookup"><span data-stu-id="3d89c-114">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
- [<span data-ttu-id="3d89c-115">使用方法のガイドライン</span><span class="sxs-lookup"><span data-stu-id="3d89c-115">Usage Guidelines</span></span>](../../../docs/standard/design-guidelines/usage-guidelines.md)
