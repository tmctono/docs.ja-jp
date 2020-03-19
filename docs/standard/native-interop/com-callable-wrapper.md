---
title: COM 呼び出し可能ラッパー
ms.date: 10/23/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- CCW
- COM interop, COM wrappers
- COM wrappers
- callable wrappers
- interoperation with unmanaged code, COM wrappers
- COM callable wrappers
ms.assetid: d04be3b5-27b9-4f5b-8469-a44149fabf78
ms.openlocfilehash: 6f2f4055a95dbcea8d7872b5c5fa3ccede8c2c8c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401173"
---
# <a name="com-callable-wrapper"></a><span data-ttu-id="4604b-102">COM 呼び出し可能ラッパー</span><span class="sxs-lookup"><span data-stu-id="4604b-102">COM Callable Wrapper</span></span>

<span data-ttu-id="4604b-103">COM クライアントが .NET オブジェクトを呼び出すと、共通言語ランタイムがマネージド オブジェクトとそのオブジェクトのための COM 呼び出し可能ラッパー (CCW: COM Callable Wrapper) を作成します。</span><span class="sxs-lookup"><span data-stu-id="4604b-103">When a COM client calls a .NET object, the common language runtime creates the managed object and a COM callable wrapper (CCW) for the object.</span></span> <span data-ttu-id="4604b-104">COM クライアントは .NET オブジェクトを直接参照できないため、CCW をマネージド オブジェクトのプロキシとして使用します。</span><span class="sxs-lookup"><span data-stu-id="4604b-104">Unable to reference a .NET object directly, COM clients use the CCW as a proxy for the managed object.</span></span>

<span data-ttu-id="4604b-105">ランタイムは、サービスを要求している COM クライアントの数に関係なく、1 つのマネージド オブジェクトに対して 1 つの CCW を作成します。</span><span class="sxs-lookup"><span data-stu-id="4604b-105">The runtime creates exactly one CCW for a managed object, regardless of the number of COM clients requesting its services.</span></span> <span data-ttu-id="4604b-106">次の図に示すように、複数の COM クライアントが、INew インターフェイスを公開する CCW への参照を保持できます。</span><span class="sxs-lookup"><span data-stu-id="4604b-106">As the following illustration shows, multiple COM clients can hold a reference to the CCW that exposes the INew interface.</span></span> <span data-ttu-id="4604b-107">CCW は、INew インターフェイスを実装するマネージド オブジェクトへの 1 つの参照を保持し、ガベージ コレクションされます。</span><span class="sxs-lookup"><span data-stu-id="4604b-107">The CCW, in turn, holds a single reference to the managed object that implements the interface and is garbage collected.</span></span> <span data-ttu-id="4604b-108">COM クライアントと .NET クライアントは、同一のマネージド オブジェジェクトに対して同時に要求できます。</span><span class="sxs-lookup"><span data-stu-id="4604b-108">Both COM and .NET clients can make requests on the same managed object simultaneously.</span></span>

![INew を公開する CCW への参照を保持している複数の COM クライアント。](./media/com-callable-wrapper/com-callable-wrapper-clients.gif)

<span data-ttu-id="4604b-110">COM 呼び出し可能ラッパーは、.NET ランタイム内で実行されている他のクラスからは見えません。</span><span class="sxs-lookup"><span data-stu-id="4604b-110">COM callable wrappers are invisible to other classes running within the .NET runtime.</span></span> <span data-ttu-id="4604b-111">CCW の主な目的は、マネージド コードとアンマネージド コードの間の呼び出しをマーシャリングすることですが、CCW は、CCW にラップされているマネージド オブジェクトのオブジェクト ID やオブジェクトの有効期間の管理も行います。</span><span class="sxs-lookup"><span data-stu-id="4604b-111">Their primary purpose is to marshal calls between managed and unmanaged code; however, CCWs also manage the object identity and object lifetime of the managed objects they wrap.</span></span>

## <a name="object-identity"></a><span data-ttu-id="4604b-112">オブジェクト ID</span><span class="sxs-lookup"><span data-stu-id="4604b-112">Object Identity</span></span>

<span data-ttu-id="4604b-113">ランタイムは、ランタイムのガベージ コレクション ヒープから .NET オブジェクトにメモリを割り当てます。これにより、ランタイムは、メモリ内で必要に応じてオブジェクトを移動させることができます。</span><span class="sxs-lookup"><span data-stu-id="4604b-113">The runtime allocates memory for the .NET object from its garbage-collected heap, which enables the runtime to move the object around in memory as necessary.</span></span> <span data-ttu-id="4604b-114">一方、CCW に対して、ランタイムは、コレクション ヒープ以外からメモリを割り当てます。これにより、COM クライアントはラッパーを直接参照できます。</span><span class="sxs-lookup"><span data-stu-id="4604b-114">In contrast, the runtime allocates memory for the CCW from a noncollected heap, making it possible for COM clients to reference the wrapper directly.</span></span>

## <a name="object-lifetime"></a><span data-ttu-id="4604b-115">オブジェクトの有効期間</span><span class="sxs-lookup"><span data-stu-id="4604b-115">Object Lifetime</span></span>

<span data-ttu-id="4604b-116">CCW にラップされている .NET クライアントとは異なり、CCW は、従来の COM 方式で参照カウントを使用します。</span><span class="sxs-lookup"><span data-stu-id="4604b-116">Unlike the .NET client it wraps, the CCW is reference-counted in traditional COM fashion.</span></span> <span data-ttu-id="4604b-117">CCW の参照カウントが 0 (ゼロ) に達すると、ラッパーはマネージド オブジェクトの参照を解放します。</span><span class="sxs-lookup"><span data-stu-id="4604b-117">When the reference count on the CCW reaches zero, the wrapper releases its reference on the managed object.</span></span> <span data-ttu-id="4604b-118">参照が残っていないマネージド オブジェクトは、次のガベージ コレクション サイクルで収集されます。</span><span class="sxs-lookup"><span data-stu-id="4604b-118">A managed object with no remaining references is collected during the next garbage-collection cycle.</span></span>

## <a name="simulating-com-interfaces"></a><span data-ttu-id="4604b-119">COM インターフェイスのシミュレート</span><span class="sxs-lookup"><span data-stu-id="4604b-119">Simulating COM interfaces</span></span>

<span data-ttu-id="4604b-120">CCW は、パブリックで COM から参照できるすべてのインターフェイス、データ型、および戻り値を、COM によるインターフェイス ベースの対話の適用と整合性のある方法で COM クライアントに公開します。</span><span class="sxs-lookup"><span data-stu-id="4604b-120">CCW exposes all public, COM-visible interfaces, data types, and return values to COM clients in a manner that is consistent with COM's enforcement of interface-based interaction.</span></span> <span data-ttu-id="4604b-121">COM クライアントの場合、.NET オブジェクトのメソッドを呼び出すことは、COM オブジェクトのメソッドを呼び出すことと同じです。</span><span class="sxs-lookup"><span data-stu-id="4604b-121">For a COM client, invoking methods on a .NET object is identical to invoking methods on a COM object.</span></span>

<span data-ttu-id="4604b-122">このシームレスなアプローチを実現するために、CCW は **IUnknown** や **IDispatch** などの従来の COM インターフェイスを製造します。</span><span class="sxs-lookup"><span data-stu-id="4604b-122">To create this seamless approach, the CCW manufactures traditional COM interfaces, such as **IUnknown** and **IDispatch**.</span></span> <span data-ttu-id="4604b-123">次の図が示すように、CCW は、ラップしている .NET オブジェクトの 1 つの参照を保持します。</span><span class="sxs-lookup"><span data-stu-id="4604b-123">As the following illustration shows, the CCW maintains a single reference on the .NET object that it wraps.</span></span> <span data-ttu-id="4604b-124">COM クライアントと .NET オブジェクトの両方は、CCW のプロキシとスタブ構築を介して相互に対話します。</span><span class="sxs-lookup"><span data-stu-id="4604b-124">Both the COM client and the .NET object interact with each other through the proxy and stub construction of the CCW.</span></span>

![CCW が COM インターフェイスを製造する方法を示す図。](./media/com-callable-wrapper/com-callable-wrapper-interfaces.gif)

<span data-ttu-id="4604b-126">マネージド環境でクラスによって明示的に実装されるインターフェイスを公開するだけでなく、.NET ランタイムは、オブジェクトの代わりに、次の表に一覧表示されている COM インターフェイスの実装を提供します。</span><span class="sxs-lookup"><span data-stu-id="4604b-126">In addition to exposing the interfaces that are explicitly implemented by a class in the managed environment, the .NET runtime supplies implementations of the COM interfaces listed in the following table on behalf of the object.</span></span> <span data-ttu-id="4604b-127">.NET クラスは、これらのインターフェイスの独自の実装を提供することで、既定の動作をオーバーライドできます。</span><span class="sxs-lookup"><span data-stu-id="4604b-127">A .NET class can override the default behavior by providing its own implementation of these interfaces.</span></span> <span data-ttu-id="4604b-128">ただし、ランタイムは **IUnknown** と **IDispatch** インターフェイス実装を常に提供します。</span><span class="sxs-lookup"><span data-stu-id="4604b-128">However, the runtime always provides the implementation for the **IUnknown** and **IDispatch** interfaces.</span></span>

|<span data-ttu-id="4604b-129">インターフェイス</span><span class="sxs-lookup"><span data-stu-id="4604b-129">Interface</span></span>|<span data-ttu-id="4604b-130">説明</span><span class="sxs-lookup"><span data-stu-id="4604b-130">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="4604b-131">**Idispatch**</span><span class="sxs-lookup"><span data-stu-id="4604b-131">**IDispatch**</span></span>|<span data-ttu-id="4604b-132">型への遅延バインディングのメカニズムを提供します。</span><span class="sxs-lookup"><span data-stu-id="4604b-132">Provides a mechanism for late binding to type.</span></span>|
|<span data-ttu-id="4604b-133">**IErrorInfo**</span><span class="sxs-lookup"><span data-stu-id="4604b-133">**IErrorInfo**</span></span>|<span data-ttu-id="4604b-134">エラー、そのソース、ヘルプ ファイル、ヘルプ コンテキスト、およびエラーを定義したインターフェイスの GUID (.NET クラスでは常に **GUID_NULL**) に関する説明文を示します。</span><span class="sxs-lookup"><span data-stu-id="4604b-134">Provides a textual description of the error, its source, a Help file, Help context, and the GUID of the interface that defined the error (always **GUID_NULL** for .NET classes).</span></span>|
|<span data-ttu-id="4604b-135">**IProvideClassInfo**</span><span class="sxs-lookup"><span data-stu-id="4604b-135">**IProvideClassInfo**</span></span>|<span data-ttu-id="4604b-136">マネージド クラスによって実装される **ITypeInfo** インターフェイスに COM クライアントがアクセスできるようにします。</span><span class="sxs-lookup"><span data-stu-id="4604b-136">Enables COM clients to gain access to the **ITypeInfo** interface implemented by a managed class.</span></span> <span data-ttu-id="4604b-137">COM からインポートされていない型については、.NET Core 上で `COR_E_NOTSUPPORTED` を返します。</span><span class="sxs-lookup"><span data-stu-id="4604b-137">Returns `COR_E_NOTSUPPORTED` on .NET Core for types not imported from COM.</span></span> |
|<span data-ttu-id="4604b-138">**ISupportErrorInfo**</span><span class="sxs-lookup"><span data-stu-id="4604b-138">**ISupportErrorInfo**</span></span>|<span data-ttu-id="4604b-139">マネージド オブジェクトが **IErrorInfo** インターフェイスをサポートするかどうかを COM クライアントが判別できるようにします。</span><span class="sxs-lookup"><span data-stu-id="4604b-139">Enables a COM client to determine whether the managed object supports the **IErrorInfo** interface.</span></span> <span data-ttu-id="4604b-140">その場合は、クライアントが最新の例外オブジェクトへのポインターを取得できるようにします。</span><span class="sxs-lookup"><span data-stu-id="4604b-140">If so, enables the client to obtain a pointer to the latest exception object.</span></span> <span data-ttu-id="4604b-141">すべてのマネージド型は、**IErrorInfo** インターフェイスをサポートします。</span><span class="sxs-lookup"><span data-stu-id="4604b-141">All managed types support the **IErrorInfo** interface.</span></span>|
|<span data-ttu-id="4604b-142">**ITypeInfo** (.NET Framework のみ)</span><span class="sxs-lookup"><span data-stu-id="4604b-142">**ITypeInfo** (.NET Framework Only)</span></span>|<span data-ttu-id="4604b-143">Tlbexp.exe によって生成された型情報と完全に等しい、クラスの型情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="4604b-143">Provides type information for a class that is exactly the same as the type information produced by Tlbexp.exe.</span></span>|
|<span data-ttu-id="4604b-144">**IUnknown**</span><span class="sxs-lookup"><span data-stu-id="4604b-144">**IUnknown**</span></span>|<span data-ttu-id="4604b-145">COM クライアントが CCW の有効期間を管理し、強制型変換を提供するための、**IUnknown** インターフェイスの標準的な実装を提供します。</span><span class="sxs-lookup"><span data-stu-id="4604b-145">Provides the standard implementation of the **IUnknown** interface with which the COM client manages the lifetime of the CCW and provides type coercion.</span></span>|

 <span data-ttu-id="4604b-146">マネージド クラスは、次の表で説明されている COM インターフェイスを提供することもできます。</span><span class="sxs-lookup"><span data-stu-id="4604b-146">A managed class can also provide the COM interfaces described in the following table.</span></span>

|<span data-ttu-id="4604b-147">インターフェイス</span><span class="sxs-lookup"><span data-stu-id="4604b-147">Interface</span></span>|<span data-ttu-id="4604b-148">説明</span><span class="sxs-lookup"><span data-stu-id="4604b-148">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="4604b-149">クラス\_*名*クラスインタフェース</span><span class="sxs-lookup"><span data-stu-id="4604b-149">The (\_*classname*) class interface</span></span>|<span data-ttu-id="4604b-150">マネージド オブジェクトで明示的に公開されている、すべてのパブリック インターフェイス、メソッド、プロパティ、およびフィールドを公開する、ランタイムによって公開され、明示的に定義されていない、インターフェイス、</span><span class="sxs-lookup"><span data-stu-id="4604b-150">Interface, exposed by the runtime and not explicitly defined, that exposes all public interfaces, methods, properties, and fields that are explicitly exposed on a managed object.</span></span>|
|<span data-ttu-id="4604b-151">**I 接続ポイント**と**I 接続ポイントコンテナ**</span><span class="sxs-lookup"><span data-stu-id="4604b-151">**IConnectionPoint** and **IConnectionPointContainer**</span></span>|<span data-ttu-id="4604b-152">デリゲート ベースのソース イベント (イベント サブスクライバーを登録するためのインターフェイス) を供給するオブジェクトのインターフェイス。</span><span class="sxs-lookup"><span data-stu-id="4604b-152">Interface for objects that source delegate-based events (an interface for registering event subscribers).</span></span>|
|<span data-ttu-id="4604b-153">**IDispatchEx** (.NET Framework のみ)</span><span class="sxs-lookup"><span data-stu-id="4604b-153">**IDispatchEx** (.NET Framework Only)</span></span>|<span data-ttu-id="4604b-154">クラスが **IExpando** を実装する場合、ランタイムによって提供されているインターフェイス。</span><span class="sxs-lookup"><span data-stu-id="4604b-154">Interface supplied by the runtime if the class implements **IExpando**.</span></span> <span data-ttu-id="4604b-155">**IDispatchEx** インターフェイスは、**IDispatch** インターフェイスの拡張版で、**IDispatch** とは異なり、列挙、追加、削除、および大文字小文字を区別したメンバーの呼び出しが可能になります。</span><span class="sxs-lookup"><span data-stu-id="4604b-155">The **IDispatchEx** interface is an extension of the **IDispatch** interface that, unlike **IDispatch**, enables enumeration, addition, deletion, and case-sensitive calling of members.</span></span>|
|<span data-ttu-id="4604b-156">**IEnumVARIANT**</span><span class="sxs-lookup"><span data-stu-id="4604b-156">**IEnumVARIANT**</span></span>|<span data-ttu-id="4604b-157">クラスが **IEnumerable** を実装する場合、コレクション内のオブジェクトを列挙するコレクション型クラスのインターフェイス。</span><span class="sxs-lookup"><span data-stu-id="4604b-157">Interface for collection-type classes, which enumerates the objects in the collection if the class implements **IEnumerable**.</span></span>|

## <a name="introducing-the-class-interface"></a><span data-ttu-id="4604b-158">クラス インターフェイスの概要</span><span class="sxs-lookup"><span data-stu-id="4604b-158">Introducing the class interface</span></span>

<span data-ttu-id="4604b-159">マネージド コードで明示的に定義されていないクラス インターフェイスは、.NET オブジェクトで明示的に公開されるすべてのパブリック メソッド、プロパティ、フィールド、およびイベントを公開するインターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="4604b-159">The class interface, which is not explicitly defined in managed code, is an interface that exposes all public methods, properties, fields, and events that are explicitly exposed on the .NET object.</span></span> <span data-ttu-id="4604b-160">このインターフェイスは、デュアルまたはディスパッチ専用インターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="4604b-160">This interface can be a dual or dispatch-only interface.</span></span> <span data-ttu-id="4604b-161">クラス インターフェイスは、前にアンダー スコアの付いた、.NET クラス自体の名前を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="4604b-161">The class interface receives the name of the .NET class itself, preceded by an underscore.</span></span> <span data-ttu-id="4604b-162">たとえば、クラス Mammal の場合、クラス インターフェイスは \_Mammal です。</span><span class="sxs-lookup"><span data-stu-id="4604b-162">For example, for class Mammal, the class interface is \_Mammal.</span></span>

<span data-ttu-id="4604b-163">派生クラスの場合、クラス インターフェイスは、基本クラスのすべてのパブリック メソッド、プロパティ、およびフィールドも公開します。</span><span class="sxs-lookup"><span data-stu-id="4604b-163">For derived classes, the class interface also exposes all public methods, properties, and fields of the base class.</span></span> <span data-ttu-id="4604b-164">派生クラスは、各基本クラスのクラス インターフェイスも公開します。</span><span class="sxs-lookup"><span data-stu-id="4604b-164">The derived class also exposes a class interface for each base class.</span></span> <span data-ttu-id="4604b-165">たとえば、クラス Mammal がクラス MammalSuperclass を拡張し、そのクラスがさらに System.Object を拡張する場合、.NET オブジェクトは COM クライアントに \_Mammal、\_MammalSuperclass、および \_Object という名前の 3 つのクラス インターフェイスを公開します。</span><span class="sxs-lookup"><span data-stu-id="4604b-165">For example, if class Mammal extends class MammalSuperclass, which itself extends System.Object, the .NET object exposes to COM clients three class interfaces named \_Mammal, \_MammalSuperclass, and \_Object.</span></span>

<span data-ttu-id="4604b-166">たとえば、次の .NET クラスを考えます。</span><span class="sxs-lookup"><span data-stu-id="4604b-166">For example, consider the following .NET class:</span></span>

```vb
' Applies the ClassInterfaceAttribute to set the interface to dual.
<ClassInterface(ClassInterfaceType.AutoDual)> _
' Implicitly extends System.Object.
Public Class Mammal
    Sub Eat()
    Sub Breathe()
    Sub Sleep()
End Class
```

```csharp
// Applies the ClassInterfaceAttribute to set the interface to dual.
[ClassInterface(ClassInterfaceType.AutoDual)]
// Implicitly extends System.Object.
public class Mammal
{
    public void Eat() {}
    public void Breathe() {}
    public void Sleep() {}
}
```

<span data-ttu-id="4604b-167">COM クライアントは、`_Mammal` という名前のクラス インターフェイスへのポインターを取得できます。</span><span class="sxs-lookup"><span data-stu-id="4604b-167">The COM client can obtain a pointer to a class interface named `_Mammal`.</span></span> <span data-ttu-id="4604b-168">.NET Framework では、[タイプ ライブラリ エクスポーター (Tlbexp.exe)](../../framework/tools/tlbexp-exe-type-library-exporter.md) ツールを使用して、`_Mammal`インターフェイス定義を含むタイプ ライブラリを生成できます。</span><span class="sxs-lookup"><span data-stu-id="4604b-168">On .NET Framework, you can use the [Type Library Exporter (Tlbexp.exe)](../../framework/tools/tlbexp-exe-type-library-exporter.md) tool to generate a type library containing the `_Mammal` interface definition.</span></span> <span data-ttu-id="4604b-169">タイプ ライブラリ エクスポーターは、.NET Core ではサポートされません。</span><span class="sxs-lookup"><span data-stu-id="4604b-169">The Type Library Exporter is not supported on .NET Core.</span></span> <span data-ttu-id="4604b-170">`Mammal` クラスが 1 つ以上のインターフェイスを実装した場合、それらのインターフェイスはコクラスの下に表示されます。</span><span class="sxs-lookup"><span data-stu-id="4604b-170">If the `Mammal` class implemented one or more interfaces, the interfaces would appear under the coclass.</span></span>

```console
[odl, uuid(…), hidden, dual, nonextensible, oleautomation]
interface _Mammal : IDispatch
{
    [id(0x00000000), propget] HRESULT ToString([out, retval] BSTR*
        pRetVal);
    [id(0x60020001)] HRESULT Equals([in] VARIANT obj, [out, retval]
        VARIANT_BOOL* pRetVal);
    [id(0x60020002)] HRESULT GetHashCode([out, retval] short* pRetVal);
    [id(0x60020003)] HRESULT GetType([out, retval] _Type** pRetVal);
    [id(0x6002000d)] HRESULT Eat();
    [id(0x6002000e)] HRESULT Breathe();
    [id(0x6002000f)] HRESULT Sleep();
}
[uuid(…)]
coclass Mammal
{
    [default] interface _Mammal;
}
```

<span data-ttu-id="4604b-171">クラス インターフェイスの生成はオプションです。</span><span class="sxs-lookup"><span data-stu-id="4604b-171">Generating the class interface is optional.</span></span> <span data-ttu-id="4604b-172">既定では、COM 相互運用が、タイプ ライブラリにエクスポートするクラスごとにディスパッチ専用インターフェイスを生成します。</span><span class="sxs-lookup"><span data-stu-id="4604b-172">By default, COM interop generates a dispatch-only interface for each class you export to a type library.</span></span> <span data-ttu-id="4604b-173"><xref:System.Runtime.InteropServices.ClassInterfaceAttribute> をクラスに適用することによって、このインターフェイスの自動作成を防止または変更することができます。</span><span class="sxs-lookup"><span data-stu-id="4604b-173">You can prevent or modify the automatic creation of this interface by applying the <xref:System.Runtime.InteropServices.ClassInterfaceAttribute> to your class.</span></span> <span data-ttu-id="4604b-174">クラス インターフェイスにより、マネージド クラスを COM に公開するタスクを軽減できますが、その使用は制限されています。</span><span class="sxs-lookup"><span data-stu-id="4604b-174">Although the class interface can ease the task of exposing managed classes to COM, its uses are limited.</span></span>

> [!CAUTION]
> <span data-ttu-id="4604b-175">独自のものを明示的に定義する代わりにクラス インターフェイスを使用すると、マネージド クラスの将来のバージョン管理が複雑になることがあります。</span><span class="sxs-lookup"><span data-stu-id="4604b-175">Using the class interface, instead of explicitly defining your own, can complicate the future versioning of your managed class.</span></span> <span data-ttu-id="4604b-176">クラス インターフェイスを使用する前に、次のガイドラインを参照してください。</span><span class="sxs-lookup"><span data-stu-id="4604b-176">Please read the following guidelines before using the class interface.</span></span>

### <a name="define-an-explicit-interface-for-com-clients-to-use-rather-than-generating-the-class-interface"></a><span data-ttu-id="4604b-177">クラス インターフェイスを生成するのではなく、COM クライアントが使用する明示的なインターフェイスを定義します。</span><span class="sxs-lookup"><span data-stu-id="4604b-177">Define an explicit interface for COM clients to use rather than generating the class interface.</span></span>

<span data-ttu-id="4604b-178">COM 相互運用はクラス インターフェイスを自動的に生成するため、クラスにバージョン後の変更が生じると、共通言語ランタイムによって公開されているクラス インターフェイスのレイアウトが変更されることがあります。</span><span class="sxs-lookup"><span data-stu-id="4604b-178">Because COM interop generates a class interface automatically, post-version changes to your class can alter the layout of the class interface exposed by the common language runtime.</span></span> <span data-ttu-id="4604b-179">COM クライアントは通常、インターフェイスのレイアウトの変更を処理するように準備されていないため、クラスのメンバー レイアウトを変更した場合に、クライアントが破損します。</span><span class="sxs-lookup"><span data-stu-id="4604b-179">Since COM clients are typically unprepared to handle changes in the layout of an interface, they break if you change the member layout of the class.</span></span>

<span data-ttu-id="4604b-180">このガイドラインは、COM クライアントに公開されるインターフェイスは変更不可にしておく必要があるという概念を促進しています。</span><span class="sxs-lookup"><span data-stu-id="4604b-180">This guideline reinforces the notion that interfaces exposed to COM clients must remain unchangeable.</span></span> <span data-ttu-id="4604b-181">間違えてインターフェイスのレイアウトを並べ替えることで COM クライアントが破損するリスクを抑えるため、インターフェイスを明示的に定義して、クラスに対するすべての変更をインターフェイス レイアウトから分離します。</span><span class="sxs-lookup"><span data-stu-id="4604b-181">To reduce the risk of breaking COM clients by inadvertently reordering the interface layout, isolate all changes to the class from the interface layout by explicitly defining interfaces.</span></span>

<span data-ttu-id="4604b-182">**ClassInterfaceAttribute** を使用してクラス インターフェイスの自動生成を中止し、次のコード フラグメントに示すように、クラスの明示的なインターフェイスを実装します。</span><span class="sxs-lookup"><span data-stu-id="4604b-182">Use the **ClassInterfaceAttribute** to disengage the automatic generation of the class interface and implement an explicit interface for the class, as the following code fragment shows:</span></span>

```vb
<ClassInterface(ClassInterfaceType.None)>Public Class LoanApp
    Implements IExplicit
    Sub M() Implements IExplicit.M
…
End Class
```

```csharp
[ClassInterface(ClassInterfaceType.None)]
public class LoanApp : IExplicit
{
    int IExplicit.M() { return 0; }
}
```

<span data-ttu-id="4604b-183">**ClassInterfaceType.None** 値により、クラス メタデータをタイプ ライブラリにエクスポートするときに、クラス インターフェイスが生成されなくなります。</span><span class="sxs-lookup"><span data-stu-id="4604b-183">The **ClassInterfaceType.None** value prevents the class interface from being generated when the class metadata is exported to a type library.</span></span> <span data-ttu-id="4604b-184">前の例では、COM クライアントは `IExplicit` インターフェイスを通してのみ `LoanApp` クラスにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="4604b-184">In the preceding example, COM clients can access the `LoanApp` class only through the `IExplicit` interface.</span></span>

### <a name="avoid-caching-dispatch-identifiers-dispids"></a><span data-ttu-id="4604b-185">ディスパッチ識別子 (DISPID) をキャッシュしないようにします。</span><span class="sxs-lookup"><span data-stu-id="4604b-185">Avoid caching dispatch identifiers (DispIds)</span></span>

<span data-ttu-id="4604b-186">クラス インターフェイスの使用は、インターフェイス メンバーの DISPID をキャッシュしていないスクリプト化されたクライアント、Microsoft Visual Basic 6.0 クライアント、または遅延バインディング クライアントのために許容されるオプションです。</span><span class="sxs-lookup"><span data-stu-id="4604b-186">Using the class interface is an acceptable option for scripted clients, Microsoft Visual Basic 6.0 clients, or any late-bound client that does not cache the DispIds of interface members.</span></span> <span data-ttu-id="4604b-187">DISPID は遅延バインディングを有効にするインターフェイス メンバーを特定します。</span><span class="sxs-lookup"><span data-stu-id="4604b-187">DispIds identify interface members to enable late binding.</span></span>

<span data-ttu-id="4604b-188">クラス インターフェイスでは、インターフェイス内のメンバーの位置に基づいて DISPID が生成されます。</span><span class="sxs-lookup"><span data-stu-id="4604b-188">For the class interface, generation of DispIds is based on the position of the member in the interface.</span></span> <span data-ttu-id="4604b-189">メンバーの順序を変更してクラスをタイプ ライブラリにエクスポートすると、クラス インターフェイスで生成される DISPID が変更されます。</span><span class="sxs-lookup"><span data-stu-id="4604b-189">If you change the order of the member and export the class to a type library, you will alter the DispIds generated in the class interface.</span></span>

<span data-ttu-id="4604b-190">クラス インターフェイスを使用するとき、遅延バインドされた COM クライアントの中断を回避するには、**ClassInterfaceAttribute** に **ClassInterfaceType.AutoDispatch** 値を指定して適用します。</span><span class="sxs-lookup"><span data-stu-id="4604b-190">To avoid breaking late-bound COM clients when using the class interface, apply the **ClassInterfaceAttribute** with the **ClassInterfaceType.AutoDispatch** value.</span></span> <span data-ttu-id="4604b-191">この値は、ディスパッチ専用のクラスのインターフェイスを実装しますが、タイプ ライブラリからインターフェイスの説明を省略します。</span><span class="sxs-lookup"><span data-stu-id="4604b-191">This value implements a dispatch-only class interface, but omits the interface description from the type library.</span></span> <span data-ttu-id="4604b-192">インターフェイスの説明がないと、クライアントはコンパイル時に DISPID をキャッシュできません。</span><span class="sxs-lookup"><span data-stu-id="4604b-192">Without an interface description, clients are unable to cache DispIds at compile time.</span></span> <span data-ttu-id="4604b-193">これはクラス インターフェイスの既定のインターフェイス型ですが、属性値を明示的に適用することもできます。</span><span class="sxs-lookup"><span data-stu-id="4604b-193">Although this is the default interface type for the class interface, you can apply the attribute value explicitly.</span></span>

```vb
<ClassInterface(ClassInterfaceType.AutoDispatch)> Public Class LoanApp
    Implements IAnother
    Sub M() Implements IAnother.M
…
End Class
```

```csharp
[ClassInterface(ClassInterfaceType.AutoDispatch)]
public class LoanApp
{
    public int M() { return 0; }
}
```

<span data-ttu-id="4604b-194">実行時にインターフェイス メンバーの DISPID を取得するために、COM クライアントは **IDispatch.GetIdsOfNames** を呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="4604b-194">To get the DispId of an interface member at run time, COM clients can call **IDispatch.GetIdsOfNames**.</span></span> <span data-ttu-id="4604b-195">インターフェイスでメソッドを呼び出すには、返された DISPID を **IDispatch.Invoke** への引数として渡します。</span><span class="sxs-lookup"><span data-stu-id="4604b-195">To invoke a method on the interface, pass the returned DispId as an argument to **IDispatch.Invoke**.</span></span>

### <a name="restrict-using-the-dual-interface-option-for-the-class-interface"></a><span data-ttu-id="4604b-196">クラス インターフェイス用のデュアル インターフェイスのオプションの使用を制限します。</span><span class="sxs-lookup"><span data-stu-id="4604b-196">Restrict using the dual interface option for the class interface.</span></span>

<span data-ttu-id="4604b-197">デュアル インターフェイスは、COM クライアントによるインターフェイス メンバーへの事前バインディングと遅延バインディングを有効にします。</span><span class="sxs-lookup"><span data-stu-id="4604b-197">Dual interfaces enable early and late binding to interface members by COM clients.</span></span> <span data-ttu-id="4604b-198">デザイン時およびテスト中は、クラス インターフェイスをデュアルに設定すると役に立つ場合があります。</span><span class="sxs-lookup"><span data-stu-id="4604b-198">At design time and during testing, you might find it useful to set the class interface to dual.</span></span> <span data-ttu-id="4604b-199">変更されることのないマネージド クラス (およびその基本クラス) の場合、このオプションも使用できます。</span><span class="sxs-lookup"><span data-stu-id="4604b-199">For a managed class (and its base classes) that will never be modified, this option is also acceptable.</span></span> <span data-ttu-id="4604b-200">それ以外の場合はすべて、クラス インターフェイスをデュアルに設定しないでください。</span><span class="sxs-lookup"><span data-stu-id="4604b-200">In all other cases, avoid setting the class interface to dual.</span></span>

<span data-ttu-id="4604b-201">自動的に生成されたデュアル インターフェイスが適切な場合もまれにありますが、より多くの場合、それはバージョンに関連する複雑さを生じさせます。</span><span class="sxs-lookup"><span data-stu-id="4604b-201">An automatically generated dual interface might be appropriate in rare cases; however, more often it creates version-related complexity.</span></span> <span data-ttu-id="4604b-202">たとえば、派生クラスのクラス インターフェイスを使用する COM クライアントは、基本クラスが変更されると簡単に中断します。</span><span class="sxs-lookup"><span data-stu-id="4604b-202">For example, COM clients using the class interface of a derived class can easily break with changes to the base class.</span></span> <span data-ttu-id="4604b-203">サード パーティが基本クラスを提供するとき、クラス インターフェイスのレイアウトを自分で制御することはできません。</span><span class="sxs-lookup"><span data-stu-id="4604b-203">When a third party provides the base class, the layout of the class interface is out of your control.</span></span> <span data-ttu-id="4604b-204">さらに、ディスパッチ専用インターフェイスとは異なり、デュアル インターフェイス (**ClassInterfaceType.AutoDual**) は、エクスポートされたタイプ ライブラリ内にクラス インターフェイスの説明を提供します。</span><span class="sxs-lookup"><span data-stu-id="4604b-204">Further, unlike a dispatch-only interface, a dual interface (**ClassInterfaceType.AutoDual**) provides a description of the class interface in the exported type library.</span></span> <span data-ttu-id="4604b-205">そのような説明により、遅延バインディングのクライアントではコンパイル時に DISPID をキャッシュすることが促進されます。</span><span class="sxs-lookup"><span data-stu-id="4604b-205">Such a description encourages late-bound clients to cache DispIds at compile time.</span></span>

### <a name="ensure-that-all-com-event-notifications-are-late-bound"></a><span data-ttu-id="4604b-206">すべての COM イベント通知が遅延バインドされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="4604b-206">Ensure that all COM event notifications are late-bound.</span></span>

<span data-ttu-id="4604b-207">既定では、COM の型情報はマネージド アセンブリに直接埋め込まれているため、プライマリ相互運用アセンブリ (PIA) の必要はありません。</span><span class="sxs-lookup"><span data-stu-id="4604b-207">By default, COM type information is embedded directly into managed assemblies, which eliminates the need for primary interop assemblies (PIAs).</span></span> <span data-ttu-id="4604b-208">ただし、埋め込まれた型情報の制限の 1 つとして、早期にバインドされた vtable 呼び出しによる COM イベント通知の配信はサポートされず、遅延バインドされた `IDispatch::Invoke` 呼び出しのみがサポートされるということがあります。</span><span class="sxs-lookup"><span data-stu-id="4604b-208">However, one of the limitations of embedded type information is that it does not support delivery of COM event notifications by early-bound vtable calls, but only supports late-bound `IDispatch::Invoke` calls.</span></span>

<span data-ttu-id="4604b-209">アプリケーションから COM イベント インターフェイス メソッドに対して早期にバインドされた呼び出しが必要な場合は、Visual Studio の **[相互運用型の埋め込み]** プロパティを `true` に設定するか、プロジェクト ファイルに次の要素を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="4604b-209">If your application requires early-bound calls to COM event interface methods, you can set the **Embed Interop Types** property in Visual Studio to `true`, or include the following element in your project file:</span></span>

```xml
<EmbedInteropTypes>True</EmbedInteropTypes>
```

## <a name="see-also"></a><span data-ttu-id="4604b-210">関連項目</span><span class="sxs-lookup"><span data-stu-id="4604b-210">See also</span></span>

- <xref:System.Runtime.InteropServices.ClassInterfaceAttribute>
- [<span data-ttu-id="4604b-211">COM ラッパー</span><span class="sxs-lookup"><span data-stu-id="4604b-211">COM Wrappers</span></span>](com-wrappers.md)
- [<span data-ttu-id="4604b-212">COM への .NET Framework コンポーネントの公開</span><span class="sxs-lookup"><span data-stu-id="4604b-212">Exposing .NET Framework Components to COM</span></span>](../../framework/interop/exposing-dotnet-components-to-com.md)
- [<span data-ttu-id="4604b-213">COM への .NET Core コンポーネントの公開</span><span class="sxs-lookup"><span data-stu-id="4604b-213">Exposing .NET Core Components to COM</span></span>](../../core/native-interop/expose-components-to-com.md)
- [<span data-ttu-id="4604b-214">相互運用のための .NET 型の要件</span><span class="sxs-lookup"><span data-stu-id="4604b-214">Qualifying .NET Types for Interoperation</span></span>](qualify-net-types-for-interoperation.md)
- [<span data-ttu-id="4604b-215">ランタイム呼び出し可能ラッパー</span><span class="sxs-lookup"><span data-stu-id="4604b-215">Runtime Callable Wrapper</span></span>](runtime-callable-wrapper.md)
