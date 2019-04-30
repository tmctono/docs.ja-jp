---
title: .NET Standard のオブジェクトがシリアル化可能なかどうかを判断する方法
description: 実行時に .NET Standard の型をシリアル化できるかどうかを確認する方法を示します。
ms.date: 10/20/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- serializing objects
- objects, serializing steps
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 196e99ab1f1a0baae53c6a1dc295b135e36fbfe0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62018760"
---
# <a name="how-to-determine-if-a-net-standard-object-is-serializable"></a><span data-ttu-id="cca58-103">.NET Standard のオブジェクトがシリアル化可能なかどうかを判断する方法</span><span class="sxs-lookup"><span data-stu-id="cca58-103">How to determine if a .NET Standard object is serializable</span></span>

<span data-ttu-id="cca58-104">.NET Standard は、型とそのバージョンの標準に準拠している特定の .NET 実装に存在する必要があるメンバーを定義する仕様です。</span><span class="sxs-lookup"><span data-stu-id="cca58-104">The .NET Standard is a specification that defines the types and members that must be present on specific .NET implementations that conform to that version of the standard.</span></span> <span data-ttu-id="cca58-105">ただし、.NET Standard 定義しません、型をシリアル化するかどうか。</span><span class="sxs-lookup"><span data-stu-id="cca58-105">However, the .NET Standard does not define whether a type is serializable.</span></span> <span data-ttu-id="cca58-106">.NET 標準ライブラリで定義された型がでマークされていない、<xref:System.SerializableAttribute>属性。</span><span class="sxs-lookup"><span data-stu-id="cca58-106">The types defined in the .NET Standard Library are not marked with the <xref:System.SerializableAttribute> attribute.</span></span> <span data-ttu-id="cca58-107">代わりに、.NET Framework、.NET Core などの特定の .NET 実装が自由に、特定の型がシリアル化できるかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="cca58-107">Instead, specific .NET implementations, such as the .NET Framework and .NET Core, are free to determine whether a particular type is serializable.</span></span> 

<span data-ttu-id="cca58-108">対象とする .NET Standard のライブラリを開発した場合は、.NET Standard をサポートする任意の .NET 実装によって、ライブラリを使用できます。</span><span class="sxs-lookup"><span data-stu-id="cca58-108">If you've developed a library that targets the .NET Standard, your library can be consumed by any .NET implementation that supports the .NET Standard.</span></span> <span data-ttu-id="cca58-109">つまり、ことはできませんがわかっている事前に特定の型がシリアル化できるかどうかのみ、実行時にシリアル化可能なことがあるかどうかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="cca58-109">This means that you cannot know in advance whether a particular type is serializable; you can only determine whether it is serializable at run time.</span></span>

<span data-ttu-id="cca58-110">値を取得することによって、オブジェクトが実行時にシリアル化可能かどうかを判断できます、<xref:System.Type.IsSerializable>のプロパティを<xref:System.Type>そのオブジェクトの型を表すオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="cca58-110">You can determine whether an object is serializable at runtime by retrieving the value of the <xref:System.Type.IsSerializable> property of a <xref:System.Type> object that represents that object's type.</span></span> <span data-ttu-id="cca58-111">次の例では、1 つの実装を提供します。</span><span class="sxs-lookup"><span data-stu-id="cca58-111">The following example provides one implementation.</span></span> <span data-ttu-id="cca58-112">定義、`IsSerializable(Object)`拡張メソッドを示すかどうか、<xref:System.Object>インスタンスをシリアル化することができます。</span><span class="sxs-lookup"><span data-stu-id="cca58-112">It defines an `IsSerializable(Object)` extension method that indicates whether any <xref:System.Object> instance can be serialized.</span></span>

[!code-csharp[is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/csharp/program.cs#2)]
[!code-vb[is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/vb/library.vb#2)]

<span data-ttu-id="cca58-113">任意のオブジェクトにするかどうかをシリアル化でき、次の例として、現在の .NET 実装に逆シリアル化を判断するメソッドを渡します。</span><span class="sxs-lookup"><span data-stu-id="cca58-113">You can then pass any object to the method to determine whether it can be serialized and deserialized on the current .NET implementation, as the following example shows:</span></span>

[!code-csharp[test-is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/csharp/program.cs#1)]
[!code-vb[test-is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/vb/program.vb#1)]

## <a name="see-also"></a><span data-ttu-id="cca58-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="cca58-114">See also</span></span>

- [<span data-ttu-id="cca58-115">バイナリ シリアル化</span><span class="sxs-lookup"><span data-stu-id="cca58-115">Binary serialization</span></span>](binary-serialization.md)
- <xref:System.SerializableAttribute?displayProperty=nameWithType>
- <xref:System.Type.IsSerializable?displayProperty=nameWithType>
