---
title: COM 相互運用のための .NET 型の要件
ms.date: 03/30/2017
helpviewer_keywords:
- exposing .NET Framework components to COM
- COM interop, qualifying .NET types
- qualifying .NET types for interoperation
- interoperation with unmanaged code, qualifying .NET types
- interoperation with unmanaged code, exposing .NET Framework components
- COM interop, exposing COM components
ms.assetid: 4b8afb52-fb8d-4e65-b47c-fd82956a3cdd
ms.openlocfilehash: f0b9bc03225ae3d2365a21fd3b78d09c08d4fc1a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73091581"
---
# <a name="qualifying-net-types-for-com-interoperation"></a><span data-ttu-id="c7a52-102">COM 相互運用のための .NET 型の要件</span><span class="sxs-lookup"><span data-stu-id="c7a52-102">Qualifying .NET Types for COM Interoperation</span></span>
<span data-ttu-id="c7a52-103">COM アプリケーションにアセンブリ内の型を公開する場合は、設計時に COM 相互運用の要件を検討する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c7a52-103">If you intend to expose types in an assembly to COM applications, consider the requirements of COM interop at design time.</span></span> <span data-ttu-id="c7a52-104">以下のガイドラインに従うと、マネージド型 (クラス、インターフェイス、構造体、列挙型) は COM の型とシームレスに統合します。</span><span class="sxs-lookup"><span data-stu-id="c7a52-104">Managed types (class, interface, structure, and enumeration) seamlessly integrate with COM types when you adhere to the following guidelines:</span></span>  
  
- <span data-ttu-id="c7a52-105">クラスは、インターフェイスを明示的に実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c7a52-105">Classes should implement interfaces explicitly.</span></span>  
  
     <span data-ttu-id="c7a52-106">COM 相互運用は、クラスのすべてのメンバーとその基底クラスのメンバーを含むインターフェイスを自動的に生成するメカニズムを備えていますが、明示的なインターフェイスを提供する方がはるかによい方法です。</span><span class="sxs-lookup"><span data-stu-id="c7a52-106">Although COM interop provides a mechanism to automatically generate an interface containing all members of the class and the members of its base class, it is far better to provide explicit interfaces.</span></span> <span data-ttu-id="c7a52-107">自動的に生成されるインターフェイスは、クラス インターフェイスと呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="c7a52-107">The automatically generated interface is called the class interface.</span></span> <span data-ttu-id="c7a52-108">ガイドラインについては、「[クラス インターフェイスの概要](com-callable-wrapper.md#introducing-the-class-interface)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c7a52-108">For guidelines, see [Introducing the class interface](com-callable-wrapper.md#introducing-the-class-interface).</span></span>  
  
     <span data-ttu-id="c7a52-109">インターフェイス定義言語 (IDL) またはそれと同等のものを使う代わりに、Visual Basic、C#、C++ を使ってコードにインターフェイス定義を組み込むことができます。</span><span class="sxs-lookup"><span data-stu-id="c7a52-109">You can use Visual Basic, C#, and C++ to incorporate interface definitions in your code, instead of having to use Interface Definition Language (IDL) or its equivalent.</span></span> <span data-ttu-id="c7a52-110">構文の詳細については、言語のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c7a52-110">For syntax details, see your language documentation.</span></span>  
  
- <span data-ttu-id="c7a52-111">マネージド型はパブリックにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c7a52-111">Managed types must be public.</span></span>  
  
     <span data-ttu-id="c7a52-112">アセンブリ内のパブリック型のみが登録されて、タイプ ライブラリにエクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="c7a52-112">Only public types in an assembly are registered and exported to the type library.</span></span> <span data-ttu-id="c7a52-113">その結果、パブリック型のみが COM に表示されます。</span><span class="sxs-lookup"><span data-stu-id="c7a52-113">As a result, only public types are visible to COM.</span></span>  
  
     <span data-ttu-id="c7a52-114">マネージド型は、COM に公開されない可能性がある他のマネージド コードに機能を公開します。</span><span class="sxs-lookup"><span data-stu-id="c7a52-114">Managed types expose features to other managed code that might not be exposed to COM.</span></span> <span data-ttu-id="c7a52-115">たとえば、パラメーター化されたコンストラクター、静的メソッド、および定数フィールドは、COM クライアントに公開されません。</span><span class="sxs-lookup"><span data-stu-id="c7a52-115">For instance, parameterized constructors, static methods, and constant fields are not exposed to COM clients.</span></span> <span data-ttu-id="c7a52-116">さらに、ランタイムが、ある型に、またはある型からデータをマーシャリングすると、データがコピーまたは変換される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c7a52-116">Further, as the runtime marshals data in and out of a type, the data might be copied or transformed.</span></span>  
  
- <span data-ttu-id="c7a52-117">メソッド、プロパティ、フィールド、イベントは、パブリックである必要があります。</span><span class="sxs-lookup"><span data-stu-id="c7a52-117">Methods, properties, fields, and events must be public.</span></span>  
  
     <span data-ttu-id="c7a52-118">また、パブリック型のメンバーを COM に表示させる場合は、メンバーもパブリックにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c7a52-118">Members of public types must also be public if they are to be visible to COM.</span></span> <span data-ttu-id="c7a52-119">アセンブリ、パブリック型、またはパブリック型のパブリック メンバーの可視性は、<xref:System.Runtime.InteropServices.ComVisibleAttribute> を適用することにより制限できます。</span><span class="sxs-lookup"><span data-stu-id="c7a52-119">You can restrict the visibility of an assembly, a public type, or public members of a public type by applying the <xref:System.Runtime.InteropServices.ComVisibleAttribute>.</span></span> <span data-ttu-id="c7a52-120">既定では、すべてのパブリック型とメンバーが可視になります。</span><span class="sxs-lookup"><span data-stu-id="c7a52-120">By default, all public types and members are visible.</span></span>  
  
- <span data-ttu-id="c7a52-121">型では、パラメーターなしのパブリック コンストラクターを COM からアクティブ化する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c7a52-121">Types must have a public parameterless constructor to be activated from COM.</span></span>  
  
     <span data-ttu-id="c7a52-122">マネージド パブリック型のみが COM に表示されます。</span><span class="sxs-lookup"><span data-stu-id="c7a52-122">Managed, public types are visible to COM.</span></span> <span data-ttu-id="c7a52-123">ただし、パラメーターなしのパブリック コンストラクター (引数のないコンストラクター) がないと、COM クライアントでは型を作成できません。</span><span class="sxs-lookup"><span data-stu-id="c7a52-123">However, without a public parameterless constructor (a constructor with no arguments), COM clients cannot create the type.</span></span> <span data-ttu-id="c7a52-124">その場合でも、型が他の方法でアクティブ化されると、COM クライアントは型を使うことができます。</span><span class="sxs-lookup"><span data-stu-id="c7a52-124">COM clients can still use the type if it is activated by some other means.</span></span>  
  
- <span data-ttu-id="c7a52-125">型を抽象にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="c7a52-125">Types cannot be abstract.</span></span>  
  
     <span data-ttu-id="c7a52-126">COM クライアントも .NET クライアントも、抽象型は作成できません。</span><span class="sxs-lookup"><span data-stu-id="c7a52-126">Neither COM clients nor .NET clients can create abstract types.</span></span>  
  
 <span data-ttu-id="c7a52-127">COM にエクスポートされるとき、マネージド型の継承階層はフラット化されます。</span><span class="sxs-lookup"><span data-stu-id="c7a52-127">When exported to COM, the inheritance hierarchy of a managed type is flattened.</span></span> <span data-ttu-id="c7a52-128">マネージド環境とアンマネージド環境では、バージョン管理も異なります。</span><span class="sxs-lookup"><span data-stu-id="c7a52-128">Versioning also differs between managed and unmanaged environments.</span></span> <span data-ttu-id="c7a52-129">COM に公開された型は、他のマネージド型とバージョン管理特性が異なります。</span><span class="sxs-lookup"><span data-stu-id="c7a52-129">Types exposed to COM do not have the same versioning characteristics as other managed types.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7a52-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="c7a52-130">See also</span></span>

- <xref:System.Runtime.InteropServices.ComVisibleAttribute>
- [<span data-ttu-id="c7a52-131">COM への .NET Framework コンポーネントの公開</span><span class="sxs-lookup"><span data-stu-id="c7a52-131">Exposing .NET Framework Components to COM</span></span>](../../../docs/framework/interop/exposing-dotnet-components-to-com.md)
- [<span data-ttu-id="c7a52-132">クラス インターフェイスの概要</span><span class="sxs-lookup"><span data-stu-id="c7a52-132">Introducing the class interface</span></span>](com-callable-wrapper.md#introducing-the-class-interface)
- [<span data-ttu-id="c7a52-133">相互運用固有の属性の適用</span><span class="sxs-lookup"><span data-stu-id="c7a52-133">Applying Interop Attributes</span></span>](../../../docs/standard/native-interop/apply-interop-attributes.md)
- [<span data-ttu-id="c7a52-134">COM 用の .NET Framework アセンブリのパッケージ化</span><span class="sxs-lookup"><span data-stu-id="c7a52-134">Packaging a .NET Framework Assembly for COM</span></span>](../../../docs/framework/interop/packaging-an-assembly-for-com.md)
