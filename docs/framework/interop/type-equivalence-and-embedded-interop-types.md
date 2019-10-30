---
title: 型の等価性と埋め込まれた相互運用機能型
ms.date: 03/30/2017
helpviewer_keywords:
- type equivalence
- embedded interop types
- primary interop assemblies,not necessary in CLR version 4
- NoPIA
ms.assetid: 78892eba-2a58-4165-b4b1-0250ee2f41dc
ms.openlocfilehash: ee9d2d94d62f262ef61edc66ce915e1227532d67
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73126391"
---
# <a name="type-equivalence-and-embedded-interop-types"></a><span data-ttu-id="f06aa-102">型の等価性と埋め込まれた相互運用機能型</span><span class="sxs-lookup"><span data-stu-id="f06aa-102">Type equivalence and embedded interop types</span></span>

<span data-ttu-id="f06aa-103">.NET Framework 4 以降、共通言語ランタイムでは、マネージド アセンブリに COM 型の型情報を直接埋め込めるようになりました。マネージド アセンブリで相互運用アセンブリから COM 型の型情報を取得する必要がありません。</span><span class="sxs-lookup"><span data-stu-id="f06aa-103">Beginning with the .NET Framework 4, the common language runtime supports embedding type information for COM types directly into managed assemblies, instead of requiring the managed assemblies to obtain type information for COM types from interop assemblies.</span></span> <span data-ttu-id="f06aa-104">埋め込まれる型情報にはマネージド アセンブリに実際に使用される型とメンバーのみが含まれるため、2 つのマネージド アセンブリで同じ COM 型の表示が非常に異なることが考えられます。</span><span class="sxs-lookup"><span data-stu-id="f06aa-104">Because the embedded type information includes only the types and members that are actually used by a managed assembly, two managed assemblies might have very different views of the same COM type.</span></span> <span data-ttu-id="f06aa-105">マネージド アセンブリごとに、COM 型の表示を表す異なる <xref:System.Type> オブジェクトが与えられます。</span><span class="sxs-lookup"><span data-stu-id="f06aa-105">Each managed assembly has a different <xref:System.Type> object to represent its view of the COM type.</span></span> <span data-ttu-id="f06aa-106">共通言語ランタイムでは、インターフェイス、構造、列挙、委任といった異なる表示間で型の等価性が与えられます。</span><span class="sxs-lookup"><span data-stu-id="f06aa-106">The common language runtime supports type equivalence between these different views for interfaces, structures, enumerations, and delegates.</span></span>

<span data-ttu-id="f06aa-107">型の等価性とは、マネージド アセンブリ間で渡される COM オブジェクトを受け取り側のアセンブリで適切なマネージド型に変換できることを意味します。</span><span class="sxs-lookup"><span data-stu-id="f06aa-107">Type equivalence means that a COM object that is passed from one managed assembly to another can be cast to the appropriate managed type in the receiving assembly.</span></span>

> [!NOTE]
> <span data-ttu-id="f06aa-108">型の等価性と埋め込まれた相互運用機能型により、COM コンポーネントを利用するアプリケーションとアドインの展開が簡単になります。アプリケーションで相互運用アセンブリを展開する必要がないためです。</span><span class="sxs-lookup"><span data-stu-id="f06aa-108">Type equivalence and embedded interop types simplify the deployment of applications and add-ins that use COM components, because it is not necessary to deploy interop assemblies with the applications.</span></span> <span data-ttu-id="f06aa-109">ただし、以前のバージョンの .NET Framework でコンポーネントを利用する場合、共有 COM コンポーネントの開発者はプライマリ相互運用アセンブリ (PIA) を作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f06aa-109">Developers of shared COM components still have to create primary interop assemblies (PIAs) if they want their components to be used by earlier versions of the .NET Framework.</span></span>

## <a name="type-equivalence"></a><span data-ttu-id="f06aa-110">型の等価性</span><span class="sxs-lookup"><span data-stu-id="f06aa-110">Type equivalence</span></span>

 <span data-ttu-id="f06aa-111">COM 型の等価性は、インターフェイス、構造、列挙、委任でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="f06aa-111">Equivalence of COM types is supported for interfaces, structures, enumerations, and delegates.</span></span> <span data-ttu-id="f06aa-112">COM 型は、次のすべてに該当する場合に等価となります。</span><span class="sxs-lookup"><span data-stu-id="f06aa-112">COM types qualify as equivalent if all of the following are true:</span></span>

- <span data-ttu-id="f06aa-113">型がいずれもインターフェイスであるか、いずれも構造であるか、いずれも列挙であるか、いずれも委任である。</span><span class="sxs-lookup"><span data-stu-id="f06aa-113">The types are both interfaces, or both structures, or both enumerations, or both delegates.</span></span>

- <span data-ttu-id="f06aa-114">型の ID が同じである (次のセクションに詳細あり)。</span><span class="sxs-lookup"><span data-stu-id="f06aa-114">The types have the same identity, as described in the next section.</span></span>

- <span data-ttu-id="f06aa-115">いずれの型も、型の等価性に適合する (「[型の等価性の資格ありとして COM 型を設定する](#marking-com-types-for-type-equivalence)」セクションに詳細あり)。</span><span class="sxs-lookup"><span data-stu-id="f06aa-115">Both types are eligible for type equivalence, as described in the [Marking COM types for type equivalence](#marking-com-types-for-type-equivalence) section.</span></span>

### <a name="type-identity"></a><span data-ttu-id="f06aa-116">型の ID</span><span class="sxs-lookup"><span data-stu-id="f06aa-116">Type identity</span></span>

<span data-ttu-id="f06aa-117">範囲と ID が一致するとき、言い換えると、それぞれに <xref:System.Runtime.InteropServices.TypeIdentifierAttribute> 属性が含まれ、2 つの属性の <xref:System.Runtime.InteropServices.TypeIdentifierAttribute.Scope%2A> プロパティと <xref:System.Runtime.InteropServices.TypeIdentifierAttribute.Identifier%2A> プロパティが一致する場合、2 つの型の ID が同じであると判断されます。</span><span class="sxs-lookup"><span data-stu-id="f06aa-117">Two types are determined to have the same identity when their scopes and identities match, in other words, if they each have the <xref:System.Runtime.InteropServices.TypeIdentifierAttribute> attribute, and the two attributes have matching <xref:System.Runtime.InteropServices.TypeIdentifierAttribute.Scope%2A> and <xref:System.Runtime.InteropServices.TypeIdentifierAttribute.Identifier%2A> properties.</span></span> <span data-ttu-id="f06aa-118"><xref:System.Runtime.InteropServices.TypeIdentifierAttribute.Scope%2A> の比較では、大文字と小文字が区別されません。</span><span class="sxs-lookup"><span data-stu-id="f06aa-118">The comparison for <xref:System.Runtime.InteropServices.TypeIdentifierAttribute.Scope%2A> is case-insensitive.</span></span>

<span data-ttu-id="f06aa-119">型に <xref:System.Runtime.InteropServices.TypeIdentifierAttribute> 属性が含まれない場合、あるいは範囲や識別子を指定しない <xref:System.Runtime.InteropServices.TypeIdentifierAttribute> 属性が型に含まれる場合も、型は次のように等価性適用として考慮されます。</span><span class="sxs-lookup"><span data-stu-id="f06aa-119">If a type does not have the <xref:System.Runtime.InteropServices.TypeIdentifierAttribute> attribute, or if it has a <xref:System.Runtime.InteropServices.TypeIdentifierAttribute> attribute that does not specify scope and identifier, the type can still be considered for equivalence as follows:</span></span>

- <span data-ttu-id="f06aa-120">インターフェイスの場合、<xref:System.Runtime.InteropServices.GuidAttribute> の値が <xref:System.Runtime.InteropServices.TypeIdentifierAttribute.Scope%2A?displayProperty=nameWithType> プロパティの代わりに使用されます。<xref:System.Type.FullName%2A?displayProperty=nameWithType> プロパティ (つまり、名前空間を含む、型の名前) が <xref:System.Runtime.InteropServices.TypeIdentifierAttribute.Identifier%2A?displayProperty=nameWithType> プロパティの代わりに使用されます。</span><span class="sxs-lookup"><span data-stu-id="f06aa-120">For interfaces, the value of the <xref:System.Runtime.InteropServices.GuidAttribute> is used instead of the <xref:System.Runtime.InteropServices.TypeIdentifierAttribute.Scope%2A?displayProperty=nameWithType> property, and the <xref:System.Type.FullName%2A?displayProperty=nameWithType> property (that is, the type name, including the namespace) is used instead of the <xref:System.Runtime.InteropServices.TypeIdentifierAttribute.Identifier%2A?displayProperty=nameWithType> property.</span></span>

- <span data-ttu-id="f06aa-121">構造、列挙、委任の場合、含んでいるアセンブリの <xref:System.Runtime.InteropServices.GuidAttribute> が <xref:System.Runtime.InteropServices.TypeIdentifierAttribute.Scope%2A> プロパティの代わりに使用されます。<xref:System.Type.FullName%2A?displayProperty=nameWithType> プロパティが <xref:System.Runtime.InteropServices.TypeIdentifierAttribute.Identifier%2A> プロパティの代わりに使用されます。</span><span class="sxs-lookup"><span data-stu-id="f06aa-121">For structures, enumerations, and delegates, the <xref:System.Runtime.InteropServices.GuidAttribute> of the containing assembly is used instead of the <xref:System.Runtime.InteropServices.TypeIdentifierAttribute.Scope%2A> property, and the <xref:System.Type.FullName%2A?displayProperty=nameWithType> property is used instead of the <xref:System.Runtime.InteropServices.TypeIdentifierAttribute.Identifier%2A> property.</span></span>

### <a name="marking-com-types-for-type-equivalence"></a><span data-ttu-id="f06aa-122">型の等価性に適合するものとして COM 型を設定する</span><span class="sxs-lookup"><span data-stu-id="f06aa-122">Marking COM types for type equivalence</span></span>

 <span data-ttu-id="f06aa-123">型の等価性に適合するものとして 2 つの方法で型を設定できます。</span><span class="sxs-lookup"><span data-stu-id="f06aa-123">You can mark a type as eligible for type equivalence in two ways:</span></span>

- <span data-ttu-id="f06aa-124">型に <xref:System.Runtime.InteropServices.TypeIdentifierAttribute> 属性を適用します。</span><span class="sxs-lookup"><span data-stu-id="f06aa-124">Apply the <xref:System.Runtime.InteropServices.TypeIdentifierAttribute> attribute to the type.</span></span>

- <span data-ttu-id="f06aa-125">型を COM インポート型にします。</span><span class="sxs-lookup"><span data-stu-id="f06aa-125">Make the type a COM import type.</span></span> <span data-ttu-id="f06aa-126"><xref:System.Runtime.InteropServices.ComImportAttribute> 属性が与えられていると、インターフェイスは COM インポート型となります。</span><span class="sxs-lookup"><span data-stu-id="f06aa-126">An interface is a COM import type if it has the <xref:System.Runtime.InteropServices.ComImportAttribute> attribute.</span></span> <span data-ttu-id="f06aa-127">それが定義されているアセンブリに <xref:System.Runtime.InteropServices.ImportedFromTypeLibAttribute> 属性が含まれる場合、インターフェイス、構造、列挙、委任は COM インポート型となります。</span><span class="sxs-lookup"><span data-stu-id="f06aa-127">An interface, structure, enumeration, or delegate is a COM import type if the assembly in which it is defined has the <xref:System.Runtime.InteropServices.ImportedFromTypeLibAttribute> attribute.</span></span>

## <a name="see-also"></a><span data-ttu-id="f06aa-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="f06aa-128">See also</span></span>

- <xref:System.Type.IsEquivalentTo%2A>
- <span data-ttu-id="f06aa-129">[マネージド コードでの COM 型の使用](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/3y76b69k(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="f06aa-129">[Using COM Types in Managed Code](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/3y76b69k(v=vs.100))</span></span>
- [<span data-ttu-id="f06aa-130">タイプ ライブラリのアセンブリとしてのインポート</span><span class="sxs-lookup"><span data-stu-id="f06aa-130">Importing a Type Library as an Assembly</span></span>](importing-a-type-library-as-an-assembly.md)
