---
title: カルチャを認識しない文字列操作の実行
ms.date: 08/22/2018
ms.technology: dotnet-standard
helpviewer_keywords:
- case mappings
- custom case mappings
- culture, custom sorting rules
- custom sorting rules
- culture-insensitive string operations, options for performing
- culture, custom case mappings
- culture-insensitive string operations, method overloads
ms.assetid: 579ef891-1f83-4c63-9ebd-2f40406b5b91
ms.openlocfilehash: 183078b1f7a3eb3530fea8af06dbb59055d7d25d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120798"
---
# <a name="performing-culture-insensitive-string-operations"></a><span data-ttu-id="41a32-102">カルチャを認識しない文字列操作の実行</span><span class="sxs-lookup"><span data-stu-id="41a32-102">Performing culture-insensitive string operations</span></span>
<span data-ttu-id="41a32-103">カルチャを認識する文字列操作を既定で実行するほとんどの .NET Framework メソッドには、<xref:System.Globalization.CultureInfo> パラメーターを渡すことによって使用するカルチャを明示的に指定できるメソッド オーバーロードが用意されています。</span><span class="sxs-lookup"><span data-stu-id="41a32-103">Most .NET Framework methods that perform culture-sensitive string operations by default provide method overloads that allow you to explicitly specify the culture to use by passing a <xref:System.Globalization.CultureInfo> parameter.</span></span> <span data-ttu-id="41a32-104">これらのオーバーロードによって、大文字小文字のマップおよび並べ替え規則のカルチャによる違いを排除し、カルチャを認識しない結果を確保できます。</span><span class="sxs-lookup"><span data-stu-id="41a32-104">These overloads allow you to eliminate cultural variations in case mappings and sorting rules and guarantee culture-insensitive results.</span></span>  
  
 <span data-ttu-id="41a32-105">ここでは、既定ではカルチャを認識する .NET Framework のメソッドを使用して、カルチャを認識しない文字列操作を実行する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="41a32-105">This section provides the following topics to demonstrate how to perform culture-insensitive string operations using .NET Framework methods that are culture-sensitive by default.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="41a32-106">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="41a32-106">In this section</span></span>  
 [<span data-ttu-id="41a32-107">カルチャを認識しない文字列比較の実行</span><span class="sxs-lookup"><span data-stu-id="41a32-107">Performing Culture-Insensitive String Comparisons</span></span>](../../../docs/standard/globalization-localization/performing-culture-insensitive-string-comparisons.md)  
 <span data-ttu-id="41a32-108"><xref:System.String.Compare%2A?displayProperty=nameWithType> メソッドと <xref:System.String.CompareTo%2A?displayProperty=nameWithType> メソッドを使用してカルチャを認識しない文字列比較を実行する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="41a32-108">Describes how to use the <xref:System.String.Compare%2A?displayProperty=nameWithType> and <xref:System.String.CompareTo%2A?displayProperty=nameWithType> methods to perform culture-insensitive string comparisons.</span></span>  
  
 [<span data-ttu-id="41a32-109">カルチャを認識しない大文字と小文字の変更の実行</span><span class="sxs-lookup"><span data-stu-id="41a32-109">Performing Culture-Insensitive Case Changes</span></span>](../../../docs/standard/globalization-localization/performing-culture-insensitive-case-changes.md)  
 <span data-ttu-id="41a32-110"><xref:System.String.ToUpper%2A?displayProperty=nameWithType>、<xref:System.String.ToLower%2A?displayProperty=nameWithType>、<xref:System.Char.ToUpper%2A?displayProperty=nameWithType>、<xref:System.Char.ToLower%2A?displayProperty=nameWithType> の各メソッドを使用してカルチャを認識しない大文字と小文字の変換を実行する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="41a32-110">Describes how to use the <xref:System.String.ToUpper%2A?displayProperty=nameWithType>, <xref:System.String.ToLower%2A?displayProperty=nameWithType>, <xref:System.Char.ToUpper%2A?displayProperty=nameWithType>, and <xref:System.Char.ToLower%2A?displayProperty=nameWithType> methods to perform culture-insensitive case changes.</span></span>  
  
 [<span data-ttu-id="41a32-111">カルチャを認識しないコレクションの操作の実行</span><span class="sxs-lookup"><span data-stu-id="41a32-111">Performing Culture-Insensitive String Operations in Collections</span></span>](../../../docs/standard/globalization-localization/performing-culture-insensitive-string-operations-in-collections.md)  
 <span data-ttu-id="41a32-112"><xref:System.Collections.CaseInsensitiveComparer>、<xref:System.Collections.CaseInsensitiveHashCodeProvider> クラス、<xref:System.Collections.SortedList>、<xref:System.Collections.ArrayList.Sort%2A?displayProperty=nameWithType>、<xref:System.Collections.Specialized.CollectionsUtil.CreateCaseInsensitiveHashtable%2A?displayProperty=nameWithType> を使用して、コレクションでカルチャを認識しない操作を実行する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="41a32-112">Describes how to use the <xref:System.Collections.CaseInsensitiveComparer>, <xref:System.Collections.CaseInsensitiveHashCodeProvider> class, <xref:System.Collections.SortedList>, <xref:System.Collections.ArrayList.Sort%2A?displayProperty=nameWithType> and <xref:System.Collections.Specialized.CollectionsUtil.CreateCaseInsensitiveHashtable%2A?displayProperty=nameWithType> to perform culture-insensitive operations in collections.</span></span>  
  
 [<span data-ttu-id="41a32-113">カルチャを認識しない配列の操作の実行</span><span class="sxs-lookup"><span data-stu-id="41a32-113">Performing Culture-Insensitive String Operations in Arrays</span></span>](../../../docs/standard/globalization-localization/performing-culture-insensitive-string-operations-in-arrays.md)  
 <span data-ttu-id="41a32-114"><xref:System.Array.Sort%2A?displayProperty=nameWithType> メソッドと <xref:System.Array.BinarySearch%2A?displayProperty=nameWithType> メソッドを使用してカルチャを認識しない配列の操作を実行する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="41a32-114">Describes how to use the <xref:System.Array.Sort%2A?displayProperty=nameWithType> and <xref:System.Array.BinarySearch%2A?displayProperty=nameWithType> methods to perform culture-insensitive operations in arrays.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="41a32-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="41a32-115">Related sections</span></span>  
 [<span data-ttu-id="41a32-116">カルチャを認識しない文字列操作</span><span class="sxs-lookup"><span data-stu-id="41a32-116">Culture-Insensitive String Operations</span></span>](../../../docs/standard/globalization-localization/culture-insensitive-string-operations.md)  
 <span data-ttu-id="41a32-117">文字列操作を実行する際にカルチャに注意する理由について説明し、カルチャを認識する操作を実行するときとカルチャを認識しない操作を実行するときのガイドラインを示します。</span><span class="sxs-lookup"><span data-stu-id="41a32-117">Describes why you should be aware of culture when performing operations on strings and provides guidelines for when to perform culture-sensitive operations and when to perform culture-insensitive operations.</span></span>

## <a name="see-also"></a><span data-ttu-id="41a32-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="41a32-118">See also</span></span>

- [<span data-ttu-id="41a32-119">並べ替え重みテーブル (Windows システム上の .NET 用)</span><span class="sxs-lookup"><span data-stu-id="41a32-119">Sorting Weight Tables (for .NET on Windows systems)</span></span>](https://www.microsoft.com/download/details.aspx?id=10921)
- [<span data-ttu-id="41a32-120">デフォルト Unicode 照合基本テーブル (Linux と macOS 上の .NET Core 用)</span><span class="sxs-lookup"><span data-stu-id="41a32-120">Default Unicode Collation Element Table (for .NET Core on Linux and macOS)</span></span>](https://www.unicode.org/Public/UCA/latest/allkeys.txt)
