---
title: 使用ガイドライン
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- class library design guidelines [.NET Framework], usage guidelines
ms.assetid: 42215ffa-a099-4a26-b14e-fb2bdb6f95b7
author: KrzysztofCwalina
ms.openlocfilehash: 23b1520a864d41e5ef59377cc9cca34cbdf22b64
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/01/2019
ms.locfileid: "73423046"
---
# <a name="usage-guidelines"></a><span data-ttu-id="6625b-102">使用ガイドライン</span><span class="sxs-lookup"><span data-stu-id="6625b-102">Usage guidelines</span></span>

<span data-ttu-id="6625b-103">このセクションでは、一般公開されている Api で共通型を使用するためのガイドラインを示します。</span><span class="sxs-lookup"><span data-stu-id="6625b-103">This section contains guidelines for using common types in publicly accessible APIs.</span></span> <span data-ttu-id="6625b-104">組み込みのフレームワーク型 (シリアル化属性など) の直接使用と、一般的な演算子のオーバーロードを扱っています。</span><span class="sxs-lookup"><span data-stu-id="6625b-104">It deals with direct usage of built-in Framework types (e.g., serialization attributes) and overloading common operators.</span></span>
  
<span data-ttu-id="6625b-105"><xref:System.IDisposable?displayProperty=nameWithType> インターフェイスについては、このセクションでは説明しませんが、「 [Dispose Pattern](../garbage-collection/implementing-dispose.md) 」セクションで説明します。</span><span class="sxs-lookup"><span data-stu-id="6625b-105">The <xref:System.IDisposable?displayProperty=nameWithType> interface is not covered in this section, but is discussed in the [Dispose Pattern](../garbage-collection/implementing-dispose.md) section.</span></span>

> [!NOTE]
> <span data-ttu-id="6625b-106">その他の一般的な組み込み .NET Framework 型のガイドラインと追加情報については、<xref:System.DateTime?displayProperty=nameWithType>、<xref:System.DateTimeOffset?displayProperty=nameWithType>、<xref:System.ICloneable?displayProperty=nameWithType>、<xref:System.IComparable%601?displayProperty=nameWithType>、<xref:System.IEquatable%601?displayProperty=nameWithType>、<xref:System.Nullable%601?displayProperty=nameWithType>、<xref:System.Object?displayProperty=nameWithType>、<xref:System.Uri?displayProperty=nameWithType>のリファレンストピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6625b-106">For guidelines and additional information about other common, built-in .NET Framework types, see the reference topics for the following: <xref:System.DateTime?displayProperty=nameWithType>, <xref:System.DateTimeOffset?displayProperty=nameWithType>, <xref:System.ICloneable?displayProperty=nameWithType>, <xref:System.IComparable%601?displayProperty=nameWithType>, <xref:System.IEquatable%601?displayProperty=nameWithType>, <xref:System.Nullable%601?displayProperty=nameWithType>, <xref:System.Object?displayProperty=nameWithType>, <xref:System.Uri?displayProperty=nameWithType>.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="6625b-107">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="6625b-107">In this section</span></span>

[<span data-ttu-id="6625b-108">配列</span><span class="sxs-lookup"><span data-stu-id="6625b-108">Arrays</span></span>](arrays.md)  
[<span data-ttu-id="6625b-109">属性</span><span class="sxs-lookup"><span data-stu-id="6625b-109">Attributes</span></span>](attributes.md)  
[<span data-ttu-id="6625b-110">コレクション</span><span class="sxs-lookup"><span data-stu-id="6625b-110">Collections</span></span>](guidelines-for-collections.md)  
[<span data-ttu-id="6625b-111">シリアル化</span><span class="sxs-lookup"><span data-stu-id="6625b-111">Serialization</span></span>](serialization.md)  
[<span data-ttu-id="6625b-112">System.Xml の使用法</span><span class="sxs-lookup"><span data-stu-id="6625b-112">System.Xml Usage</span></span>](system-xml-usage.md)  
[<span data-ttu-id="6625b-113">等値演算子</span><span class="sxs-lookup"><span data-stu-id="6625b-113">Equality Operators</span></span>](equality-operators.md)  

<span data-ttu-id="6625b-114">*©2005、2009 Microsoft Corporation の部分。すべての権限が予約されています。*</span><span class="sxs-lookup"><span data-stu-id="6625b-114">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

<span data-ttu-id="6625b-115">*2008 年 10 月 22 日に Microsoft Windows Development シリーズの一部として、Addison-Wesley Professional によって発行された、Krzysztof Cwalina および Brad Abrams による「[Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)」 (フレームワーク デザイン ガイドライン: 再利用可能な .NET ライブラリの規則、用法、パターン、第 2 版) から Pearson Education, Inc. の許可を得て再印刷されています。*</span><span class="sxs-lookup"><span data-stu-id="6625b-115">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>
  
## <a name="see-also"></a><span data-ttu-id="6625b-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="6625b-116">See also</span></span>

- [<span data-ttu-id="6625b-117">フレームワーク デザインのガイドライン</span><span class="sxs-lookup"><span data-stu-id="6625b-117">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
