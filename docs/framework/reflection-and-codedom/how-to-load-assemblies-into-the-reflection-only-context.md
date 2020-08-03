---
title: '方法: リフレクションのみのコンテキストにアセンブリを読み込む'
description: .NET でリフレクションのみのコンテキストにアセンブリを読み込む方法の例について確認します。 他のプラットフォームまたは .NET バージョン用にコンパイルされたアセンブリを確認します。
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- reflection, reflection-only loader context
- assemblies [.NET Framework], loading for reflection
- attributes [.NET Framework], retrieving
- assemblies [.NET Framework], reflection-only loader context
- reflection-only loader context
ms.assetid: 9818b660-52f5-423d-a9af-e75163aa7068
ms.openlocfilehash: 92f847f6c61ba39bf8621af6080baccfdabe514a
ms.sourcegitcommit: 3d84eac0818099c9949035feb96bbe0346358504
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/21/2020
ms.locfileid: "86865074"
---
# <a name="how-to-load-assemblies-into-the-reflection-only-context"></a><span data-ttu-id="7f294-104">方法: リフレクションのみのコンテキストにアセンブリを読み込む</span><span class="sxs-lookup"><span data-stu-id="7f294-104">How to: Load Assemblies into the Reflection-Only Context</span></span>

<span data-ttu-id="7f294-105">リフレクションのみの読み込みコンテキストでは、他のプラットフォームや .NET Framework の他のバージョン用にコンパイルされたアセンブリを検査できます。</span><span class="sxs-lookup"><span data-stu-id="7f294-105">The reflection-only load context allows you to examine assemblies compiled for other platforms or for other versions of the .NET Framework.</span></span> <span data-ttu-id="7f294-106">このコンテキストに読み込まれたコードは検査のみ可能で、実行できません。</span><span class="sxs-lookup"><span data-stu-id="7f294-106">Code loaded into this context can only be examined; it cannot be executed.</span></span> <span data-ttu-id="7f294-107">つまり、コンストラクターを実行できないので、オブジェクトは作成できません。</span><span class="sxs-lookup"><span data-stu-id="7f294-107">This means that objects cannot be created, because constructors cannot be executed.</span></span> <span data-ttu-id="7f294-108">また、コードを実行できないため、依存関係は自動的には読み込まれません。</span><span class="sxs-lookup"><span data-stu-id="7f294-108">Because the code cannot be executed, dependencies are not automatically loaded.</span></span> <span data-ttu-id="7f294-109">依存関係を検査する必要がある場合は、依存関係を独自に読み込む必要があります。</span><span class="sxs-lookup"><span data-stu-id="7f294-109">If you need to examine them, you must load them yourself.</span></span>

## <a name="to-load-an-assembly-into-the-reflection-only-load-context"></a><span data-ttu-id="7f294-110">リフレクションのみの読み込みのコンテキストにアセンブリを読み込むには</span><span class="sxs-lookup"><span data-stu-id="7f294-110">To load an assembly into the reflection-only load context</span></span>

1. <span data-ttu-id="7f294-111">表示名が指定されたアセンブリを読み込むには、<xref:System.Reflection.Assembly.ReflectionOnlyLoad%28System.String%29> メソッド オーバーロードを使用し、パスが指定されたアセンブリを読み込むには、<xref:System.Reflection.Assembly.ReflectionOnlyLoadFrom%2A> メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="7f294-111">Use the <xref:System.Reflection.Assembly.ReflectionOnlyLoad%28System.String%29> method overload to load the assembly given its display name, or the <xref:System.Reflection.Assembly.ReflectionOnlyLoadFrom%2A> method to load the assembly given its path.</span></span> <span data-ttu-id="7f294-112">アセンブリがバイナリ イメージの場合は、<xref:System.Reflection.Assembly.ReflectionOnlyLoad%28System.Byte%5B%5D%29> メソッド オーバーロードを使用します。</span><span class="sxs-lookup"><span data-stu-id="7f294-112">If the assembly is a binary image, use the <xref:System.Reflection.Assembly.ReflectionOnlyLoad%28System.Byte%5B%5D%29> method overload.</span></span>

    > [!NOTE]
    > <span data-ttu-id="7f294-113">リフレクションのみのコンテキストを使用して、実行コンテキストのバージョン以外の .NET Framework のバージョンから mscorlib.dll のバージョンを読み込むことはできません。</span><span class="sxs-lookup"><span data-stu-id="7f294-113">You cannot use the reflection-only context to load a version of mscorlib.dll from a version of the .NET Framework other than the version in the execution context.</span></span>

2. <span data-ttu-id="7f294-114">アセンブリに依存関係がある場合、<xref:System.Reflection.Assembly.ReflectionOnlyLoad%2A> メソッドは依存関係を読み込みません。</span><span class="sxs-lookup"><span data-stu-id="7f294-114">If the assembly has dependencies, the <xref:System.Reflection.Assembly.ReflectionOnlyLoad%2A> method does not load them.</span></span> <span data-ttu-id="7f294-115">依存関係を検査する必要がある場合は、依存関係を独自に読み込む必要があります。</span><span class="sxs-lookup"><span data-stu-id="7f294-115">If you need to examine them, you must load them yourself.</span></span>

3. <span data-ttu-id="7f294-116">アセンブリの <xref:System.Reflection.Assembly.ReflectionOnly%2A> プロパティを使用して、アセンブリをリフレクションのみのコンテキストに読み込むかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="7f294-116">Determine whether an assembly is loaded into the reflection-only context by using the assembly's <xref:System.Reflection.Assembly.ReflectionOnly%2A> property.</span></span>

4. <span data-ttu-id="7f294-117">アセンブリまたはアセンブリ内の型に属性が適用されている場合は、<xref:System.Reflection.CustomAttributeData> クラスを使用してこれらの属性を検査し、リフレクションのみのコンテキストでコードが実行されないようにします。</span><span class="sxs-lookup"><span data-stu-id="7f294-117">If attributes have been applied to the assembly or to types in the assembly, examine those attributes by using the <xref:System.Reflection.CustomAttributeData> class to ensure that no attempt is made to execute code in the reflection-only context.</span></span> <span data-ttu-id="7f294-118"><xref:System.Reflection.CustomAttributeData.GetCustomAttributes%2A?displayProperty=nameWithType> メソッドの適切なオーバーロードを使用して、アセンブリ、メンバー、モジュール、またはパラメーターに適用されている属性を表す <xref:System.Reflection.CustomAttributeData> オブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="7f294-118">Use the appropriate overload of the <xref:System.Reflection.CustomAttributeData.GetCustomAttributes%2A?displayProperty=nameWithType> method to obtain <xref:System.Reflection.CustomAttributeData> objects representing the attributes applied to an assembly, member, module, or parameter.</span></span>

    > [!NOTE]
    > <span data-ttu-id="7f294-119">アセンブリまたはそのコンテンツに適用されている属性は、そのアセンブリで定義されている場合もあれば、リフレクションのみのコンテキストに読み込まれた別のアセンブリで定義されている場合もあります。</span><span class="sxs-lookup"><span data-stu-id="7f294-119">Attributes applied to the assembly or to its contents might be defined in the assembly, or they might be defined in another assembly loaded into the reflection-only context.</span></span> <span data-ttu-id="7f294-120">属性がどこに定義されているかを事前に確認する方法はありません。</span><span class="sxs-lookup"><span data-stu-id="7f294-120">There is no way to tell in advance where the attributes are defined.</span></span>

## <a name="example"></a><span data-ttu-id="7f294-121">例</span><span class="sxs-lookup"><span data-stu-id="7f294-121">Example</span></span>

<span data-ttu-id="7f294-122">リフレクションのみのコンテキストに読み込まれたアセンブリに適用されている属性を検査する方法を以下のコード例に示します。</span><span class="sxs-lookup"><span data-stu-id="7f294-122">The following code example shows how to examine the attributes applied to an assembly loaded into the reflection-only context.</span></span>

<span data-ttu-id="7f294-123">このコード例では、2 つのコンストラクターと 1 つのプロパティでカスタム属性を定義しています。</span><span class="sxs-lookup"><span data-stu-id="7f294-123">The code example defines a custom attribute with two constructors and one property.</span></span> <span data-ttu-id="7f294-124">この属性は、アセンブリ、アセンブリで宣言された型、型のメソッド、メソッドのパラメーターに適用されます。</span><span class="sxs-lookup"><span data-stu-id="7f294-124">The attribute is applied to the assembly, to a type declared in the assembly, to a method of the type, and to a parameter of the method.</span></span> <span data-ttu-id="7f294-125">このコード例を実行すると、アセンブリがそれ自体をリフレクションのみのコンテキストに読み込み、アセンブリとそれに含まれている型およびメンバーに適用されているカスタム属性に関する情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="7f294-125">When executed, the assembly loads itself into the reflection-only context and displays information about the custom attributes that were applied to it and to the types and members it contains.</span></span>

> [!NOTE]
> <span data-ttu-id="7f294-126">コード例を簡素にするために、アセンブリがそれ自体を読み込んで検査します。</span><span class="sxs-lookup"><span data-stu-id="7f294-126">To simplify the code example, the assembly loads and examines itself.</span></span> <span data-ttu-id="7f294-127">通常、同じアセンブリが実行コンテキストとリフレクションのみのコンテキストの両方に読み込まれることはありません。</span><span class="sxs-lookup"><span data-stu-id="7f294-127">Normally, you would not expect to find the same assembly loaded into both the execution context and the reflection-only context.</span></span>

[!code-cpp[CustomAttributeData#1](../../../samples/snippets/cpp/VS_Snippets_CLR/CustomAttributeData/CPP/source.cpp#1)]
[!code-csharp[CustomAttributeData#1](../../../samples/snippets/csharp/VS_Snippets_CLR/CustomAttributeData/CS/source.cs#1)]
[!code-vb[CustomAttributeData#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CustomAttributeData/VB/source.vb#1)]

## <a name="see-also"></a><span data-ttu-id="7f294-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="7f294-128">See also</span></span>

- <xref:System.Reflection.Assembly.ReflectionOnlyLoad%2A>
- <xref:System.Reflection.Assembly.ReflectionOnly%2A>
- <xref:System.Reflection.CustomAttributeData>
