---
title: 使用ガイドライン
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- class library design guidelines [.NET Framework], usage guidelines
ms.assetid: 42215ffa-a099-4a26-b14e-fb2bdb6f95b7
author: KrzysztofCwalina
ms.openlocfilehash: 761570b899a2a36391eb81dc7f42e13fff1f14ef
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61778808"
---
# <a name="usage-guidelines"></a><span data-ttu-id="316c1-102">使用ガイドライン</span><span class="sxs-lookup"><span data-stu-id="316c1-102">Usage guidelines</span></span>

<span data-ttu-id="316c1-103">このセクションには、パブリックにアクセスできる Api で一般的な種類の使用に関するガイドラインが含まれています。</span><span class="sxs-lookup"><span data-stu-id="316c1-103">This section contains guidelines for using common types in publicly accessible APIs.</span></span> <span data-ttu-id="316c1-104">組み込みフレームワーク型 (シリアル化属性など) および一般的な演算子のオーバー ロードの直接の使用状況を処理します。</span><span class="sxs-lookup"><span data-stu-id="316c1-104">It deals with direct usage of built-in Framework types (e.g., serialization attributes) and overloading common operators.</span></span>
  
<span data-ttu-id="316c1-105"><xref:System.IDisposable?displayProperty=nameWithType>インターフェイスは、このセクションでは説明しませんが、については、 [Dispose パターン](../../../docs/standard/design-guidelines/dispose-pattern.md)セクション。</span><span class="sxs-lookup"><span data-stu-id="316c1-105">The <xref:System.IDisposable?displayProperty=nameWithType> interface is not covered in this section, but is discussed in the [Dispose Pattern](../../../docs/standard/design-guidelines/dispose-pattern.md) section.</span></span>

> [!NOTE]
> <span data-ttu-id="316c1-106">組み込みの .NET Framework 型のガイドラインとその他の共通の詳細についてには、次の参照トピックを参照してください: <xref:System.DateTime?displayProperty=nameWithType>、 <xref:System.DateTimeOffset?displayProperty=nameWithType>、 <xref:System.ICloneable?displayProperty=nameWithType>、 <xref:System.IComparable%601?displayProperty=nameWithType>、 <xref:System.IEquatable%601?displayProperty=nameWithType>、 <xref:System.Nullable%601?displayProperty=nameWithType>、 <xref:System.Object?displayProperty=nameWithType>, <xref:System.Uri?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="316c1-106">For guidelines and additional information about other common, built-in .NET Framework types, see the reference topics for the following: <xref:System.DateTime?displayProperty=nameWithType>, <xref:System.DateTimeOffset?displayProperty=nameWithType>, <xref:System.ICloneable?displayProperty=nameWithType>, <xref:System.IComparable%601?displayProperty=nameWithType>, <xref:System.IEquatable%601?displayProperty=nameWithType>, <xref:System.Nullable%601?displayProperty=nameWithType>, <xref:System.Object?displayProperty=nameWithType>, <xref:System.Uri?displayProperty=nameWithType>.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="316c1-107">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="316c1-107">In this section</span></span>

[<span data-ttu-id="316c1-108">配列</span><span class="sxs-lookup"><span data-stu-id="316c1-108">Arrays</span></span>](arrays.md)  
[<span data-ttu-id="316c1-109">属性</span><span class="sxs-lookup"><span data-stu-id="316c1-109">Attributes</span></span>](attributes.md)  
[<span data-ttu-id="316c1-110">コレクション</span><span class="sxs-lookup"><span data-stu-id="316c1-110">Collections</span></span>](guidelines-for-collections.md)  
[<span data-ttu-id="316c1-111">シリアル化</span><span class="sxs-lookup"><span data-stu-id="316c1-111">Serialization</span></span>](serialization.md)  
[<span data-ttu-id="316c1-112">System.Xml の使用法</span><span class="sxs-lookup"><span data-stu-id="316c1-112">System.Xml Usage</span></span>](system-xml-usage.md)  
[<span data-ttu-id="316c1-113">等値演算子</span><span class="sxs-lookup"><span data-stu-id="316c1-113">Equality Operators</span></span>](equality-operators.md)  

<span data-ttu-id="316c1-114">*Portions © 2005, 2009 Microsoft Corporation.All rights reserved.*</span><span class="sxs-lookup"><span data-stu-id="316c1-114">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

<span data-ttu-id="316c1-115">*Pearson Education, Inc. からのアクセス許可によって了承を得て転載[Framework デザイン ガイドライン。規則、手法、および再利用可能な .NET ライブラリの第 2 版のパターン](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)Krzysztof Cwalina、Brad 内容では、Microsoft Windows の開発シリーズの一部として、Addison-wesley Professional、2008 年 10 月 22日を公開します。*</span><span class="sxs-lookup"><span data-stu-id="316c1-115">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>
  
## <a name="see-also"></a><span data-ttu-id="316c1-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="316c1-116">See also</span></span>

- [<span data-ttu-id="316c1-117">フレームワーク デザインのガイドライン</span><span class="sxs-lookup"><span data-stu-id="316c1-117">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
