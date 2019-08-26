---
title: オブジェクトに対する既定のマーシャリング
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- objects, interop marshaling
- interop marshaling, objects
ms.assetid: c2ef0284-b061-4e12-b6d3-6a502b9cc558
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9bc165c6f1a7cdc6b8a03db0b7648583d75cd7a0
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69946657"
---
# <a name="default-marshaling-for-objects"></a><span data-ttu-id="97ce7-102">オブジェクトに対する既定のマーシャリング</span><span class="sxs-lookup"><span data-stu-id="97ce7-102">Default Marshaling for Objects</span></span>
<span data-ttu-id="97ce7-103"><xref:System.Object?displayProperty=nameWithType> として型指定されているパラメーターおよびフィールドを、次のいずれかの型としてアンマネージ コードに公開できます。</span><span class="sxs-lookup"><span data-stu-id="97ce7-103">Parameters and fields typed as <xref:System.Object?displayProperty=nameWithType> can be exposed to unmanaged code as one of the following types:</span></span>  
  
- <span data-ttu-id="97ce7-104">オブジェクトがパラメーターの場合にはバリアント。</span><span class="sxs-lookup"><span data-stu-id="97ce7-104">A variant when the object is a parameter.</span></span>  
  
- <span data-ttu-id="97ce7-105">オブジェクトが構造体フィールドの場合にはインターフェイス。</span><span class="sxs-lookup"><span data-stu-id="97ce7-105">An interface when the object is a structure field.</span></span>  
  
 <span data-ttu-id="97ce7-106">オブジェクト型のマーシャリングは COM 相互運用機能のみでサポートされます。</span><span class="sxs-lookup"><span data-stu-id="97ce7-106">Only COM interop supports marshaling for object types.</span></span> <span data-ttu-id="97ce7-107">既定の動作では、オブジェクトは COM バリアントにマーシャリングされます。</span><span class="sxs-lookup"><span data-stu-id="97ce7-107">The default behavior is to marshal objects to COM variants.</span></span> <span data-ttu-id="97ce7-108">これらの規則は **Object** 型のみに適用され、**Object** クラスから派生した、厳密に型指定されたオブジェクトには適用されません。</span><span class="sxs-lookup"><span data-stu-id="97ce7-108">These rules apply only to the type **Object** and do not apply to strongly typed objects that derive from the **Object** class.</span></span>  
  
## <a name="marshaling-options"></a><span data-ttu-id="97ce7-109">マーシャリング オプション</span><span class="sxs-lookup"><span data-stu-id="97ce7-109">Marshaling Options</span></span>  
 <span data-ttu-id="97ce7-110">**Object** データ型のマーシャリング オプションを次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="97ce7-110">The following table shows the marshaling options for the **Object** data type.</span></span> <span data-ttu-id="97ce7-111"><xref:System.Runtime.InteropServices.MarshalAsAttribute> 属性は、オブジェクトをマーシャリングするための <xref:System.Runtime.InteropServices.UnmanagedType> 列挙値をいくつか提供します。</span><span class="sxs-lookup"><span data-stu-id="97ce7-111">The <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute provides several <xref:System.Runtime.InteropServices.UnmanagedType> enumeration values to marshal objects.</span></span>  
  
|<span data-ttu-id="97ce7-112">列挙型</span><span class="sxs-lookup"><span data-stu-id="97ce7-112">Enumeration type</span></span>|<span data-ttu-id="97ce7-113">アンマネージ形式の説明</span><span class="sxs-lookup"><span data-stu-id="97ce7-113">Description of unmanaged format</span></span>|  
|----------------------|-------------------------------------|  
|<span data-ttu-id="97ce7-114">**UnmanagedType.Struct**</span><span class="sxs-lookup"><span data-stu-id="97ce7-114">**UnmanagedType.Struct**</span></span><br /><br /> <span data-ttu-id="97ce7-115">(パラメーターの既定値)</span><span class="sxs-lookup"><span data-stu-id="97ce7-115">(default for parameters)</span></span>|<span data-ttu-id="97ce7-116">COM スタイルのバリアント。</span><span class="sxs-lookup"><span data-stu-id="97ce7-116">A COM-style variant.</span></span>|  
|<span data-ttu-id="97ce7-117">**UnmanagedType.Interface**</span><span class="sxs-lookup"><span data-stu-id="97ce7-117">**UnmanagedType.Interface**</span></span>|<span data-ttu-id="97ce7-118">可能な場合は **IDispatch** インターフェイス。それ以外の場合は **IUnknown** インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="97ce7-118">An **IDispatch** interface, if possible; otherwise, an **IUnknown** interface.</span></span>|  
|<span data-ttu-id="97ce7-119">**UnmanagedType.IUnknown**</span><span class="sxs-lookup"><span data-stu-id="97ce7-119">**UnmanagedType.IUnknown**</span></span><br /><br /> <span data-ttu-id="97ce7-120">(フィールドの既定値)</span><span class="sxs-lookup"><span data-stu-id="97ce7-120">(default for fields)</span></span>|<span data-ttu-id="97ce7-121">**IUnknown** インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="97ce7-121">An **IUnknown** interface.</span></span>|  
|<span data-ttu-id="97ce7-122">**UnmanagedType.IDispatch**</span><span class="sxs-lookup"><span data-stu-id="97ce7-122">**UnmanagedType.IDispatch**</span></span>|<span data-ttu-id="97ce7-123">**IDispatch** インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="97ce7-123">An **IDispatch** interface.</span></span>|  
  
 <span data-ttu-id="97ce7-124">次の例は、`MarshalObject` のマネージド インターフェイス定義を示しています。</span><span class="sxs-lookup"><span data-stu-id="97ce7-124">The following example shows the managed interface definition for `MarshalObject`.</span></span>  
  
```vb  
Interface MarshalObject  
   Sub SetVariant(o As Object)  
   Sub SetVariantRef(ByRef o As Object)  
   Function GetVariant() As Object  
  
   Sub SetIDispatch( <MarshalAs(UnmanagedType.IDispatch)> o As Object)  
   Sub SetIDispatchRef(ByRef <MarshalAs(UnmanagedType.IDispatch)> o _  
      As Object)  
   Function GetIDispatch() As <MarshalAs(UnmanagedType.IDispatch)> Object  
   Sub SetIUnknown( <MarshalAs(UnmanagedType.IUnknown)> o As Object)  
   Sub SetIUnknownRef(ByRef <MarshalAs(UnmanagedType.IUnknown)> o _  
      As Object)  
   Function GetIUnknown() As <MarshalAs(UnmanagedType.IUnknown)> Object  
End Interface  
```  
  
```csharp  
interface MarshalObject {  
   void SetVariant(Object o);  
   void SetVariantRef(ref Object o);  
   Object GetVariant();  
  
   void SetIDispatch ([MarshalAs(UnmanagedType.IDispatch)]Object o);  
   void SetIDispatchRef([MarshalAs(UnmanagedType.IDispatch)]ref Object o);  
   [MarshalAs(UnmanagedType.IDispatch)] Object GetIDispatch();  
   void SetIUnknown ([MarshalAs(UnmanagedType.IUnknown)]Object o);  
   void SetIUnknownRef([MarshalAs(UnmanagedType.IUnknown)]ref Object o);  
   [MarshalAs(UnmanagedType.IUnknown)] Object GetIUnknown();  
}  
```  
  
 <span data-ttu-id="97ce7-125">次のコードでは、`MarshalObject` インターフェイスをタイプ ライブラリにエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="97ce7-125">The following code exports the `MarshalObject` interface to a type library.</span></span>  
  
```  
interface MarshalObject {  
   HRESULT SetVariant([in] VARIANT o);  
   HRESULT SetVariantRef([in,out] VARIANT *o);  
   HRESULT GetVariant([out,retval] VARIANT *o)   
   HRESULT SetIDispatch([in] IDispatch *o);  
   HRESULT SetIDispatchRef([in,out] IDispatch **o);  
   HRESULT GetIDispatch([out,retval] IDispatch **o)   
   HRESULT SetIUnknown([in] IUnknown *o);  
   HRESULT SetIUnknownRef([in,out] IUnknown **o);  
   HRESULT GetIUnknown([out,retval] IUnknown **o)   
}  
```  
  
> [!NOTE]
> <span data-ttu-id="97ce7-126">相互運用マーシャラーは、バリアント内に割り当てられたオブジェクトがある場合は、呼び出しの後で自動的にそのオブジェクトを解放します。</span><span class="sxs-lookup"><span data-stu-id="97ce7-126">The interop marshaler automatically frees any allocated object inside the variant after the call.</span></span>  
  
 <span data-ttu-id="97ce7-127">次の例は、フォーマットされた値型を示しています。</span><span class="sxs-lookup"><span data-stu-id="97ce7-127">The following example shows a formatted value type.</span></span>  
  
```vb  
Public Structure ObjectHolder  
   Dim o1 As Object  
   <MarshalAs(UnmanagedType.IDispatch)> Public o2 As Object  
End Structure  
```  
  
```csharp  
public struct ObjectHolder {  
   Object o1;  
   [MarshalAs(UnmanagedType.IDispatch)]public Object o2;  
}  
```  
  
 <span data-ttu-id="97ce7-128">次のコードでは、フォーマットされた型をタイプ ライブラリにエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="97ce7-128">The following code exports the formatted type to a type library.</span></span>  
  
```  
struct ObjectHolder {  
   VARIANT o1;  
   IDispatch *o2;  
}  
```  
  
## <a name="marshaling-object-to-interface"></a><span data-ttu-id="97ce7-129">インターフェイスへのオブジェクトのマーシャリング</span><span class="sxs-lookup"><span data-stu-id="97ce7-129">Marshaling Object to Interface</span></span>  
 <span data-ttu-id="97ce7-130">オブジェクトがインターフェイスとして COM に公開される場合、そのインターフェイスはマネージド型 <xref:System.Object> 用のクラス インターフェイス ( **_Object** インターフェイス) となります。</span><span class="sxs-lookup"><span data-stu-id="97ce7-130">When an object is exposed to COM as an interface, that interface is the class interface for the managed type <xref:System.Object> (the **_Object** interface).</span></span> <span data-ttu-id="97ce7-131">このインターフェイスは、結果のタイプ ライブラリでは、**IDispatch** (<xref:System.Runtime.InteropServices.UnmanagedType>) または **IUnknown** (**UnmanagedType.IUnknown**) として型指定されます。</span><span class="sxs-lookup"><span data-stu-id="97ce7-131">This interface is typed as an **IDispatch** (<xref:System.Runtime.InteropServices.UnmanagedType>) or an **IUnknown** (**UnmanagedType.IUnknown**) in the resulting type library.</span></span> <span data-ttu-id="97ce7-132">COM クライアントは、マネージド クラスのメンバー、または派生クラスによって実装されるメンバーを **_Object** インターフェイス経由で動的に呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="97ce7-132">COM clients can dynamically invoke the members of the managed class or any members implemented by its derived classes through the **_Object** interface.</span></span> <span data-ttu-id="97ce7-133">クライアントは **QueryInterface** を呼び出して、マネージド型によって明示的に実装された他の任意のインターフェイスを取得することもできます。</span><span class="sxs-lookup"><span data-stu-id="97ce7-133">The client can also call **QueryInterface** to obtain any other interface explicitly implemented by the managed type.</span></span>  
  
## <a name="marshaling-object-to-variant"></a><span data-ttu-id="97ce7-134">バリアントへのオブジェクトのマーシャリング</span><span class="sxs-lookup"><span data-stu-id="97ce7-134">Marshaling Object to Variant</span></span>  
 <span data-ttu-id="97ce7-135">オブジェクトがバリアントにマーシャリングされる場合、内部バリアント型は次の規則に従って実行時に決定されます。</span><span class="sxs-lookup"><span data-stu-id="97ce7-135">When an object is marshaled to a variant, the internal variant type is determined at run time, based on the following rules:</span></span>  
  
- <span data-ttu-id="97ce7-136">オブジェクト参照が null (Visual Basic では **Nothing**) の場合、オブジェクトは **VT_EMPTY** 型のバリアントにマーシャリングされます。</span><span class="sxs-lookup"><span data-stu-id="97ce7-136">If the object reference is null (**Nothing** in Visual Basic), the object is marshaled to a variant of type **VT_EMPTY**.</span></span>  
  
- <span data-ttu-id="97ce7-137">オブジェクトが、次の表にリストされているいずれかの型のインスタンスである場合、結果として生成されるバリアント型は、表に示されている、マーシャラーに組み込まれている規則によって決定されます。</span><span class="sxs-lookup"><span data-stu-id="97ce7-137">If the object is an instance of any type listed in the following table, the resulting variant type is determined by the rules built into the marshaler and shown in the table.</span></span>  
  
- <span data-ttu-id="97ce7-138">マーシャリング動作を明示的に制御する必要があるその他のオブジェクトは、<xref:System.IConvertible> インターフェイスを実装できます。</span><span class="sxs-lookup"><span data-stu-id="97ce7-138">Other objects that need to explicitly control the marshaling behavior can implement the <xref:System.IConvertible> interface.</span></span> <span data-ttu-id="97ce7-139">その場合、バリアント型は <xref:System.IConvertible.GetTypeCode%2A?displayProperty=nameWithType> メソッドから返される型コードによって決定されます。</span><span class="sxs-lookup"><span data-stu-id="97ce7-139">In that case, the variant type is determined by the type code returned from the <xref:System.IConvertible.GetTypeCode%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="97ce7-140">それ以外の場合、オブジェクトは **VT_UNKNOWN** 型のバリアントとしてマーシャリングされます。</span><span class="sxs-lookup"><span data-stu-id="97ce7-140">Otherwise, the object is marshaled as a variant of type **VT_UNKNOWN**.</span></span>  
  
### <a name="marshaling-system-types-to-variant"></a><span data-ttu-id="97ce7-141">バリアントへのシステム型のマーシャリング</span><span class="sxs-lookup"><span data-stu-id="97ce7-141">Marshaling System Types to Variant</span></span>  
 <span data-ttu-id="97ce7-142">次の表に、マネージド オブジェクト型とそれに対応する COM バリアント型を示します。</span><span class="sxs-lookup"><span data-stu-id="97ce7-142">The following table shows managed object types and their corresponding COM variant types.</span></span> <span data-ttu-id="97ce7-143">これらの型は、呼び出されるメソッドのシグネチャが <xref:System.Object?displayProperty=nameWithType> 型の場合にのみ変換されます。</span><span class="sxs-lookup"><span data-stu-id="97ce7-143">These types are converted only when the signature of the method being called is of type <xref:System.Object?displayProperty=nameWithType>.</span></span>  
  
|<span data-ttu-id="97ce7-144">オブジェクトの種類</span><span class="sxs-lookup"><span data-stu-id="97ce7-144">Object type</span></span>|<span data-ttu-id="97ce7-145">COM バリアント型</span><span class="sxs-lookup"><span data-stu-id="97ce7-145">COM variant type</span></span>|  
|-----------------|----------------------|  
|<span data-ttu-id="97ce7-146">null オブジェクト参照 (Visual Basic では **Nothing**)。</span><span class="sxs-lookup"><span data-stu-id="97ce7-146">Null object reference (**Nothing** in Visual Basic).</span></span>|<span data-ttu-id="97ce7-147">**VT_EMPTY**</span><span class="sxs-lookup"><span data-stu-id="97ce7-147">**VT_EMPTY**</span></span>|  
|<xref:System.DBNull?displayProperty=nameWithType>|<span data-ttu-id="97ce7-148">**VT_NULL**</span><span class="sxs-lookup"><span data-stu-id="97ce7-148">**VT_NULL**</span></span>|  
|<xref:System.Runtime.InteropServices.ErrorWrapper?displayProperty=nameWithType>|<span data-ttu-id="97ce7-149">**VT_ERROR**</span><span class="sxs-lookup"><span data-stu-id="97ce7-149">**VT_ERROR**</span></span>|  
|<xref:System.Reflection.Missing?displayProperty=nameWithType>|<span data-ttu-id="97ce7-150">**VT_ERROR** と **E_PARAMNOTFOUND**</span><span class="sxs-lookup"><span data-stu-id="97ce7-150">**VT_ERROR** with **E_PARAMNOTFOUND**</span></span>|  
|<xref:System.Runtime.InteropServices.DispatchWrapper?displayProperty=nameWithType>|<span data-ttu-id="97ce7-151">**VT_DISPATCH**</span><span class="sxs-lookup"><span data-stu-id="97ce7-151">**VT_DISPATCH**</span></span>|  
|<xref:System.Runtime.InteropServices.UnknownWrapper?displayProperty=nameWithType>|<span data-ttu-id="97ce7-152">**VT_UNKNOWN**</span><span class="sxs-lookup"><span data-stu-id="97ce7-152">**VT_UNKNOWN**</span></span>|  
|<xref:System.Runtime.InteropServices.CurrencyWrapper?displayProperty=nameWithType>|<span data-ttu-id="97ce7-153">**VT_CY**</span><span class="sxs-lookup"><span data-stu-id="97ce7-153">**VT_CY**</span></span>|  
|<xref:System.Boolean?displayProperty=nameWithType>|<span data-ttu-id="97ce7-154">**VT_BOOL**</span><span class="sxs-lookup"><span data-stu-id="97ce7-154">**VT_BOOL**</span></span>|  
|<xref:System.SByte?displayProperty=nameWithType>|<span data-ttu-id="97ce7-155">**VT_I1**</span><span class="sxs-lookup"><span data-stu-id="97ce7-155">**VT_I1**</span></span>|  
|<xref:System.Byte?displayProperty=nameWithType>|<span data-ttu-id="97ce7-156">**VT_UI1**</span><span class="sxs-lookup"><span data-stu-id="97ce7-156">**VT_UI1**</span></span>|  
|<xref:System.Int16?displayProperty=nameWithType>|<span data-ttu-id="97ce7-157">**VT_I2**</span><span class="sxs-lookup"><span data-stu-id="97ce7-157">**VT_I2**</span></span>|  
|<xref:System.UInt16?displayProperty=nameWithType>|<span data-ttu-id="97ce7-158">**VT_UI2**</span><span class="sxs-lookup"><span data-stu-id="97ce7-158">**VT_UI2**</span></span>|  
|<xref:System.Int32?displayProperty=nameWithType>|<span data-ttu-id="97ce7-159">**VT_I4**</span><span class="sxs-lookup"><span data-stu-id="97ce7-159">**VT_I4**</span></span>|  
|<xref:System.UInt32?displayProperty=nameWithType>|<span data-ttu-id="97ce7-160">**VT_UI4**</span><span class="sxs-lookup"><span data-stu-id="97ce7-160">**VT_UI4**</span></span>|  
|<xref:System.Int64?displayProperty=nameWithType>|<span data-ttu-id="97ce7-161">**VT_I8**</span><span class="sxs-lookup"><span data-stu-id="97ce7-161">**VT_I8**</span></span>|  
|<xref:System.UInt64?displayProperty=nameWithType>|<span data-ttu-id="97ce7-162">**VT_UI8**</span><span class="sxs-lookup"><span data-stu-id="97ce7-162">**VT_UI8**</span></span>|  
|<xref:System.Single?displayProperty=nameWithType>|<span data-ttu-id="97ce7-163">**VT_R4**</span><span class="sxs-lookup"><span data-stu-id="97ce7-163">**VT_R4**</span></span>|  
|<xref:System.Double?displayProperty=nameWithType>|<span data-ttu-id="97ce7-164">**VT_R8**</span><span class="sxs-lookup"><span data-stu-id="97ce7-164">**VT_R8**</span></span>|  
|<xref:System.Decimal?displayProperty=nameWithType>|<span data-ttu-id="97ce7-165">**VT_DECIMAL**</span><span class="sxs-lookup"><span data-stu-id="97ce7-165">**VT_DECIMAL**</span></span>|  
|<xref:System.DateTime?displayProperty=nameWithType>|<span data-ttu-id="97ce7-166">**VT_DATE**</span><span class="sxs-lookup"><span data-stu-id="97ce7-166">**VT_DATE**</span></span>|  
|<xref:System.String?displayProperty=nameWithType>|<span data-ttu-id="97ce7-167">**VT_BSTR**</span><span class="sxs-lookup"><span data-stu-id="97ce7-167">**VT_BSTR**</span></span>|  
|<xref:System.IntPtr?displayProperty=nameWithType>|<span data-ttu-id="97ce7-168">**VT_INT**</span><span class="sxs-lookup"><span data-stu-id="97ce7-168">**VT_INT**</span></span>|  
|<xref:System.UIntPtr?displayProperty=nameWithType>|<span data-ttu-id="97ce7-169">**VT_UINT**</span><span class="sxs-lookup"><span data-stu-id="97ce7-169">**VT_UINT**</span></span>|  
|<xref:System.Array?displayProperty=nameWithType>|<span data-ttu-id="97ce7-170">**VT_ARRAY**</span><span class="sxs-lookup"><span data-stu-id="97ce7-170">**VT_ARRAY**</span></span>|  
  
 <span data-ttu-id="97ce7-171">上の例で定義した `MarshalObject` インターフェイスを使用して、次のコード例ではさまざまな型のバリアントを COM サーバーに渡す方法を示します。</span><span class="sxs-lookup"><span data-stu-id="97ce7-171">Using the `MarshalObject` interface defined in the previous example, the following code example demonstrates how to pass various types of variants to a COM server.</span></span>  
  
```vb  
Dim mo As New MarshalObject()  
mo.SetVariant(Nothing)         ' Marshal as variant of type VT_EMPTY.  
mo.SetVariant(System.DBNull.Value) ' Marshal as variant of type VT_NULL.  
mo.SetVariant(CInt(27))        ' Marshal as variant of type VT_I2.  
mo.SetVariant(CLng(27))        ' Marshal as variant of type VT_I4.  
mo.SetVariant(CSng(27.0))      ' Marshal as variant of type VT_R4.  
mo.SetVariant(CDbl(27.0))      ' Marshal as variant of type VT_R8.  
```  
  
```csharp  
MarshalObject mo = new MarshalObject();  
mo.SetVariant(null);            // Marshal as variant of type VT_EMPTY.  
mo.SetVariant(System.DBNull.Value); // Marshal as variant of type VT_NULL.  
mo.SetVariant((int)27);          // Marshal as variant of type VT_I2.  
mo.SetVariant((long)27);          // Marshal as variant of type VT_I4.  
mo.SetVariant((single)27.0);   // Marshal as variant of type VT_R4.  
mo.SetVariant((double)27.0);   // Marshal as variant of type VT_R8.  
```  
  
 <span data-ttu-id="97ce7-172"><xref:System.Runtime.InteropServices.ErrorWrapper>、<xref:System.Runtime.InteropServices.DispatchWrapper>、<xref:System.Runtime.InteropServices.UnknownWrapper>、および <xref:System.Runtime.InteropServices.CurrencyWrapper> などのラッパー クラスを使用すると、対応するマネージド型を持たない COM 型をマーシャリングできます。</span><span class="sxs-lookup"><span data-stu-id="97ce7-172">COM types that do not have corresponding managed types can be marshaled using wrapper classes such as <xref:System.Runtime.InteropServices.ErrorWrapper>, <xref:System.Runtime.InteropServices.DispatchWrapper>, <xref:System.Runtime.InteropServices.UnknownWrapper>, and <xref:System.Runtime.InteropServices.CurrencyWrapper>.</span></span> <span data-ttu-id="97ce7-173">次のコード例では、これらのラッパーを使用して、さまざまな型のバリアントを COM サーバーに渡す方法を示します。</span><span class="sxs-lookup"><span data-stu-id="97ce7-173">The following code example demonstrates how to use these wrappers to pass various types of variants to a COM server.</span></span>  
  
```vb  
Imports System.Runtime.InteropServices  
' Pass inew as a variant of type VT_UNKNOWN interface.  
mo.SetVariant(New UnknownWrapper(inew))  
' Pass inew as a variant of type VT_DISPATCH interface.  
mo.SetVariant(New DispatchWrapper(inew))  
' Pass a value as a variant of type VT_ERROR interface.  
mo.SetVariant(New ErrorWrapper(&H80054002))  
' Pass a value as a variant of type VT_CURRENCY interface.  
mo.SetVariant(New CurrencyWrapper(New Decimal(5.25)))  
```  
  
```csharp  
using System.Runtime.InteropServices;  
// Pass inew as a variant of type VT_UNKNOWN interface.  
mo.SetVariant(new UnknownWrapper(inew));  
// Pass inew as a variant of type VT_DISPATCH interface.  
mo.SetVariant(new DispatchWrapper(inew));  
// Pass a value as a variant of type VT_ERROR interface.  
mo.SetVariant(new ErrorWrapper(0x80054002));  
// Pass a value as a variant of type VT_CURRENCY interface.  
mo.SetVariant(new CurrencyWrapper(new Decimal(5.25)));  
```  
  
 <span data-ttu-id="97ce7-174">ラッパー クラスは、<xref:System.Runtime.InteropServices> 名前空間で定義されます。</span><span class="sxs-lookup"><span data-stu-id="97ce7-174">The wrapper classes are defined in the <xref:System.Runtime.InteropServices> namespace.</span></span>  
  
### <a name="marshaling-the-iconvertible-interface-to-variant"></a><span data-ttu-id="97ce7-175">バリアントへの IConvertible インターフェイスのマーシャリング</span><span class="sxs-lookup"><span data-stu-id="97ce7-175">Marshaling the IConvertible Interface to Variant</span></span>  
 <span data-ttu-id="97ce7-176">前のセクションでリストしたもの以外の型は、<xref:System.IConvertible> インターフェイスを実装することにより、型のマーシャリング方法を制御できます。</span><span class="sxs-lookup"><span data-stu-id="97ce7-176">Types other than those listed in the previous section can control how they are marshaled by implementing the <xref:System.IConvertible> interface.</span></span> <span data-ttu-id="97ce7-177">オブジェクトが **IConvertible** インターフェイスを実装する場合、その COM バリアント型は <xref:System.IConvertible.GetTypeCode%2A?displayProperty=nameWithType> メソッドから返された <xref:System.TypeCode> 列挙体の値によって実行時に決定されます。</span><span class="sxs-lookup"><span data-stu-id="97ce7-177">If the object implements the **IConvertible** interface, the COM variant type is determined at run time by the value of the <xref:System.TypeCode> enumeration returned from the <xref:System.IConvertible.GetTypeCode%2A?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="97ce7-178">次の表に、**TypeCode** 列挙体に対して有効な値と、それぞれの値に対応する COM バリアント型を示します。</span><span class="sxs-lookup"><span data-stu-id="97ce7-178">The following table shows the possible values for the **TypeCode** enumeration and the corresponding COM variant type for each value.</span></span>  
  
|<span data-ttu-id="97ce7-179">TypeCode</span><span class="sxs-lookup"><span data-stu-id="97ce7-179">TypeCode</span></span>|<span data-ttu-id="97ce7-180">COM バリアント型</span><span class="sxs-lookup"><span data-stu-id="97ce7-180">COM variant type</span></span>|  
|--------------|----------------------|  
|<span data-ttu-id="97ce7-181">**TypeCode.Empty**</span><span class="sxs-lookup"><span data-stu-id="97ce7-181">**TypeCode.Empty**</span></span>|<span data-ttu-id="97ce7-182">**VT_EMPTY**</span><span class="sxs-lookup"><span data-stu-id="97ce7-182">**VT_EMPTY**</span></span>|  
|<span data-ttu-id="97ce7-183">**TypeCode.Object**</span><span class="sxs-lookup"><span data-stu-id="97ce7-183">**TypeCode.Object**</span></span>|<span data-ttu-id="97ce7-184">**VT_UNKNOWN**</span><span class="sxs-lookup"><span data-stu-id="97ce7-184">**VT_UNKNOWN**</span></span>|  
|<span data-ttu-id="97ce7-185">**TypeCode.DBNull**</span><span class="sxs-lookup"><span data-stu-id="97ce7-185">**TypeCode.DBNull**</span></span>|<span data-ttu-id="97ce7-186">**VT_NULL**</span><span class="sxs-lookup"><span data-stu-id="97ce7-186">**VT_NULL**</span></span>|  
|<span data-ttu-id="97ce7-187">**TypeCode.Boolean**</span><span class="sxs-lookup"><span data-stu-id="97ce7-187">**TypeCode.Boolean**</span></span>|<span data-ttu-id="97ce7-188">**VT_BOOL**</span><span class="sxs-lookup"><span data-stu-id="97ce7-188">**VT_BOOL**</span></span>|  
|<span data-ttu-id="97ce7-189">**TypeCode.Char**</span><span class="sxs-lookup"><span data-stu-id="97ce7-189">**TypeCode.Char**</span></span>|<span data-ttu-id="97ce7-190">**VT_UI2**</span><span class="sxs-lookup"><span data-stu-id="97ce7-190">**VT_UI2**</span></span>|  
|<span data-ttu-id="97ce7-191">**TypeCode.Sbyte**</span><span class="sxs-lookup"><span data-stu-id="97ce7-191">**TypeCode.Sbyte**</span></span>|<span data-ttu-id="97ce7-192">**VT_I1**</span><span class="sxs-lookup"><span data-stu-id="97ce7-192">**VT_I1**</span></span>|  
|<span data-ttu-id="97ce7-193">**TypeCode.Byte**</span><span class="sxs-lookup"><span data-stu-id="97ce7-193">**TypeCode.Byte**</span></span>|<span data-ttu-id="97ce7-194">**VT_UI1**</span><span class="sxs-lookup"><span data-stu-id="97ce7-194">**VT_UI1**</span></span>|  
|<span data-ttu-id="97ce7-195">**TypeCode.Int16**</span><span class="sxs-lookup"><span data-stu-id="97ce7-195">**TypeCode.Int16**</span></span>|<span data-ttu-id="97ce7-196">**VT_I2**</span><span class="sxs-lookup"><span data-stu-id="97ce7-196">**VT_I2**</span></span>|  
|<span data-ttu-id="97ce7-197">**TypeCode.UInt16**</span><span class="sxs-lookup"><span data-stu-id="97ce7-197">**TypeCode.UInt16**</span></span>|<span data-ttu-id="97ce7-198">**VT_UI2**</span><span class="sxs-lookup"><span data-stu-id="97ce7-198">**VT_UI2**</span></span>|  
|<span data-ttu-id="97ce7-199">**TypeCode.Int32**</span><span class="sxs-lookup"><span data-stu-id="97ce7-199">**TypeCode.Int32**</span></span>|<span data-ttu-id="97ce7-200">**VT_I4**</span><span class="sxs-lookup"><span data-stu-id="97ce7-200">**VT_I4**</span></span>|  
|<span data-ttu-id="97ce7-201">**TypeCode.UInt32**</span><span class="sxs-lookup"><span data-stu-id="97ce7-201">**TypeCode.UInt32**</span></span>|<span data-ttu-id="97ce7-202">**VT_UI4**</span><span class="sxs-lookup"><span data-stu-id="97ce7-202">**VT_UI4**</span></span>|  
|<span data-ttu-id="97ce7-203">**TypeCode.Int64**</span><span class="sxs-lookup"><span data-stu-id="97ce7-203">**TypeCode.Int64**</span></span>|<span data-ttu-id="97ce7-204">**VT_I8**</span><span class="sxs-lookup"><span data-stu-id="97ce7-204">**VT_I8**</span></span>|  
|<span data-ttu-id="97ce7-205">**TypeCode.UInt64**</span><span class="sxs-lookup"><span data-stu-id="97ce7-205">**TypeCode.UInt64**</span></span>|<span data-ttu-id="97ce7-206">**VT_UI8**</span><span class="sxs-lookup"><span data-stu-id="97ce7-206">**VT_UI8**</span></span>|  
|<span data-ttu-id="97ce7-207">**TypeCode.Single**</span><span class="sxs-lookup"><span data-stu-id="97ce7-207">**TypeCode.Single**</span></span>|<span data-ttu-id="97ce7-208">**VT_R4**</span><span class="sxs-lookup"><span data-stu-id="97ce7-208">**VT_R4**</span></span>|  
|<span data-ttu-id="97ce7-209">**TypeCode.Double**</span><span class="sxs-lookup"><span data-stu-id="97ce7-209">**TypeCode.Double**</span></span>|<span data-ttu-id="97ce7-210">**VT_R8**</span><span class="sxs-lookup"><span data-stu-id="97ce7-210">**VT_R8**</span></span>|  
|<span data-ttu-id="97ce7-211">**TypeCode.Decimal**</span><span class="sxs-lookup"><span data-stu-id="97ce7-211">**TypeCode.Decimal**</span></span>|<span data-ttu-id="97ce7-212">**VT_DECIMAL**</span><span class="sxs-lookup"><span data-stu-id="97ce7-212">**VT_DECIMAL**</span></span>|  
|<span data-ttu-id="97ce7-213">**TypeCode.DateTime**</span><span class="sxs-lookup"><span data-stu-id="97ce7-213">**TypeCode.DateTime**</span></span>|<span data-ttu-id="97ce7-214">**VT_DATE**</span><span class="sxs-lookup"><span data-stu-id="97ce7-214">**VT_DATE**</span></span>|  
|<span data-ttu-id="97ce7-215">**TypeCode.String**</span><span class="sxs-lookup"><span data-stu-id="97ce7-215">**TypeCode.String**</span></span>|<span data-ttu-id="97ce7-216">**VT_BSTR**</span><span class="sxs-lookup"><span data-stu-id="97ce7-216">**VT_BSTR**</span></span>|  
|<span data-ttu-id="97ce7-217">サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="97ce7-217">Not supported.</span></span>|<span data-ttu-id="97ce7-218">**VT_INT**</span><span class="sxs-lookup"><span data-stu-id="97ce7-218">**VT_INT**</span></span>|  
|<span data-ttu-id="97ce7-219">サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="97ce7-219">Not supported.</span></span>|<span data-ttu-id="97ce7-220">**VT_UINT**</span><span class="sxs-lookup"><span data-stu-id="97ce7-220">**VT_UINT**</span></span>|  
|<span data-ttu-id="97ce7-221">サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="97ce7-221">Not supported.</span></span>|<span data-ttu-id="97ce7-222">**VT_ARRAY**</span><span class="sxs-lookup"><span data-stu-id="97ce7-222">**VT_ARRAY**</span></span>|  
|<span data-ttu-id="97ce7-223">サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="97ce7-223">Not supported.</span></span>|<span data-ttu-id="97ce7-224">**VT_RECORD**</span><span class="sxs-lookup"><span data-stu-id="97ce7-224">**VT_RECORD**</span></span>|  
|<span data-ttu-id="97ce7-225">サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="97ce7-225">Not supported.</span></span>|<span data-ttu-id="97ce7-226">**VT_CY**</span><span class="sxs-lookup"><span data-stu-id="97ce7-226">**VT_CY**</span></span>|  
|<span data-ttu-id="97ce7-227">サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="97ce7-227">Not supported.</span></span>|<span data-ttu-id="97ce7-228">**VT_VARIANT**</span><span class="sxs-lookup"><span data-stu-id="97ce7-228">**VT_VARIANT**</span></span>|  
  
 <span data-ttu-id="97ce7-229">COM バリアントの値は、**IConvertible.To** *Type* インターフェイスを呼び出すことによって決定されます。この **To** *Type* は、**IConvertible.GetTypeCode** から返された型に対応する変換ルーチンです。</span><span class="sxs-lookup"><span data-stu-id="97ce7-229">The value of the COM variant is determined by calling the **IConvertible.To** *Type* interface, where **To** *Type* is the conversion routine that corresponds to the type that was returned from **IConvertible.GetTypeCode**.</span></span> <span data-ttu-id="97ce7-230">たとえば、**IConvertible.GetTypeCode** から **TypeCode.Double** を返すオブジェクトは、**VT_R8** 型の COM バリアントとしてマーシャリングされます。</span><span class="sxs-lookup"><span data-stu-id="97ce7-230">For example, an object that returns **TypeCode.Double** from **IConvertible.GetTypeCode** is marshaled as a COM variant of type **VT_R8**.</span></span> <span data-ttu-id="97ce7-231">バリアントの値 (COM バリアントの **dblVal** フィールド内に格納される) は、**IConvertible** インターフェイスにキャストし、<xref:System.IConvertible.ToDouble%2A> メソッドを呼び出すことで取得できます。</span><span class="sxs-lookup"><span data-stu-id="97ce7-231">You can obtain the value of the variant (stored in the **dblVal** field of the COM variant) by casting to the **IConvertible** interface and calling the <xref:System.IConvertible.ToDouble%2A> method.</span></span>  
  
## <a name="marshaling-variant-to-object"></a><span data-ttu-id="97ce7-232">オブジェクトへのバリアントのマーシャリング</span><span class="sxs-lookup"><span data-stu-id="97ce7-232">Marshaling Variant to Object</span></span>  
 <span data-ttu-id="97ce7-233">バリアントをオブジェクトにマーシャリングする場合、マーシャリングされるバリアントの型、および場合によっては値で、生成されるオブジェクトの型が決まります。</span><span class="sxs-lookup"><span data-stu-id="97ce7-233">When marshaling a variant to an object, the type, and sometimes the value, of the marshaled variant determines the type of object produced.</span></span> <span data-ttu-id="97ce7-234">次の表に、各バリアント型とそれに対応するオブジェクト型を示します。オブジェクト型はバリアントが COM から .NET Framework に渡されるときにマーシャラーによって作成されます。</span><span class="sxs-lookup"><span data-stu-id="97ce7-234">The following table identifies each variant type and the corresponding object type that the marshaler creates when a variant is passed from COM to the .NET Framework.</span></span>  
  
|<span data-ttu-id="97ce7-235">COM バリアント型</span><span class="sxs-lookup"><span data-stu-id="97ce7-235">COM variant type</span></span>|<span data-ttu-id="97ce7-236">オブジェクトの種類</span><span class="sxs-lookup"><span data-stu-id="97ce7-236">Object type</span></span>|  
|----------------------|-----------------|  
|<span data-ttu-id="97ce7-237">**VT_EMPTY**</span><span class="sxs-lookup"><span data-stu-id="97ce7-237">**VT_EMPTY**</span></span>|<span data-ttu-id="97ce7-238">null オブジェクト参照 (Visual Basic では **Nothing**)。</span><span class="sxs-lookup"><span data-stu-id="97ce7-238">Null object reference (**Nothing** in Visual Basic).</span></span>|  
|<span data-ttu-id="97ce7-239">**VT_NULL**</span><span class="sxs-lookup"><span data-stu-id="97ce7-239">**VT_NULL**</span></span>|<xref:System.DBNull?displayProperty=nameWithType>|  
|<span data-ttu-id="97ce7-240">**VT_DISPATCH**</span><span class="sxs-lookup"><span data-stu-id="97ce7-240">**VT_DISPATCH**</span></span>|<span data-ttu-id="97ce7-241">**System.__ComObject**、または (pdispVal == null) の場合は null</span><span class="sxs-lookup"><span data-stu-id="97ce7-241">**System.__ComObject** or null if (pdispVal == null)</span></span>|  
|<span data-ttu-id="97ce7-242">**VT_UNKNOWN**</span><span class="sxs-lookup"><span data-stu-id="97ce7-242">**VT_UNKNOWN**</span></span>|<span data-ttu-id="97ce7-243">**System.__ComObject**、または (punkVal == null) の場合は null</span><span class="sxs-lookup"><span data-stu-id="97ce7-243">**System.__ComObject** or null if (punkVal == null)</span></span>|  
|<span data-ttu-id="97ce7-244">**VT_ERROR**</span><span class="sxs-lookup"><span data-stu-id="97ce7-244">**VT_ERROR**</span></span>|<xref:System.UInt32?displayProperty=nameWithType>|  
|<span data-ttu-id="97ce7-245">**VT_BOOL**</span><span class="sxs-lookup"><span data-stu-id="97ce7-245">**VT_BOOL**</span></span>|<xref:System.Boolean?displayProperty=nameWithType>|  
|<span data-ttu-id="97ce7-246">**VT_I1**</span><span class="sxs-lookup"><span data-stu-id="97ce7-246">**VT_I1**</span></span>|<xref:System.SByte?displayProperty=nameWithType>|  
|<span data-ttu-id="97ce7-247">**VT_UI1**</span><span class="sxs-lookup"><span data-stu-id="97ce7-247">**VT_UI1**</span></span>|<xref:System.Byte?displayProperty=nameWithType>|  
|<span data-ttu-id="97ce7-248">**VT_I2**</span><span class="sxs-lookup"><span data-stu-id="97ce7-248">**VT_I2**</span></span>|<xref:System.Int16?displayProperty=nameWithType>|  
|<span data-ttu-id="97ce7-249">**VT_UI2**</span><span class="sxs-lookup"><span data-stu-id="97ce7-249">**VT_UI2**</span></span>|<xref:System.UInt16?displayProperty=nameWithType>|  
|<span data-ttu-id="97ce7-250">**VT_I4**</span><span class="sxs-lookup"><span data-stu-id="97ce7-250">**VT_I4**</span></span>|<xref:System.Int32?displayProperty=nameWithType>|  
|<span data-ttu-id="97ce7-251">**VT_UI4**</span><span class="sxs-lookup"><span data-stu-id="97ce7-251">**VT_UI4**</span></span>|<xref:System.UInt32?displayProperty=nameWithType>|  
|<span data-ttu-id="97ce7-252">**VT_I8**</span><span class="sxs-lookup"><span data-stu-id="97ce7-252">**VT_I8**</span></span>|<xref:System.Int64?displayProperty=nameWithType>|  
|<span data-ttu-id="97ce7-253">**VT_UI8**</span><span class="sxs-lookup"><span data-stu-id="97ce7-253">**VT_UI8**</span></span>|<xref:System.UInt64?displayProperty=nameWithType>|  
|<span data-ttu-id="97ce7-254">**VT_R4**</span><span class="sxs-lookup"><span data-stu-id="97ce7-254">**VT_R4**</span></span>|<xref:System.Single?displayProperty=nameWithType>|  
|<span data-ttu-id="97ce7-255">**VT_R8**</span><span class="sxs-lookup"><span data-stu-id="97ce7-255">**VT_R8**</span></span>|<xref:System.Double?displayProperty=nameWithType>|  
|<span data-ttu-id="97ce7-256">**VT_DECIMAL**</span><span class="sxs-lookup"><span data-stu-id="97ce7-256">**VT_DECIMAL**</span></span>|<xref:System.Decimal?displayProperty=nameWithType>|  
|<span data-ttu-id="97ce7-257">**VT_DATE**</span><span class="sxs-lookup"><span data-stu-id="97ce7-257">**VT_DATE**</span></span>|<xref:System.DateTime?displayProperty=nameWithType>|  
|<span data-ttu-id="97ce7-258">**VT_BSTR**</span><span class="sxs-lookup"><span data-stu-id="97ce7-258">**VT_BSTR**</span></span>|<xref:System.String?displayProperty=nameWithType>|  
|<span data-ttu-id="97ce7-259">**VT_INT**</span><span class="sxs-lookup"><span data-stu-id="97ce7-259">**VT_INT**</span></span>|<xref:System.Int32?displayProperty=nameWithType>|  
|<span data-ttu-id="97ce7-260">**VT_UINT**</span><span class="sxs-lookup"><span data-stu-id="97ce7-260">**VT_UINT**</span></span>|<xref:System.UInt32?displayProperty=nameWithType>|  
|<span data-ttu-id="97ce7-261">**VT_ARRAY** &#124; **VT_** \*</span><span class="sxs-lookup"><span data-stu-id="97ce7-261">**VT_ARRAY** &#124; **VT_**\*</span></span>|<xref:System.Array?displayProperty=nameWithType>|  
|<span data-ttu-id="97ce7-262">**VT_CY**</span><span class="sxs-lookup"><span data-stu-id="97ce7-262">**VT_CY**</span></span>|<xref:System.Decimal?displayProperty=nameWithType>|  
|<span data-ttu-id="97ce7-263">**VT_RECORD**</span><span class="sxs-lookup"><span data-stu-id="97ce7-263">**VT_RECORD**</span></span>|<span data-ttu-id="97ce7-264">対応するボックス化された値型。</span><span class="sxs-lookup"><span data-stu-id="97ce7-264">Corresponding boxed value type.</span></span>|  
|<span data-ttu-id="97ce7-265">**VT_VARIANT**</span><span class="sxs-lookup"><span data-stu-id="97ce7-265">**VT_VARIANT**</span></span>|<span data-ttu-id="97ce7-266">サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="97ce7-266">Not supported.</span></span>|  
  
 <span data-ttu-id="97ce7-267">COM からマネージド コードに渡された後で COM に返されるバリアント型が、呼び出し中に同じバリアント型を維持しないことがあります。</span><span class="sxs-lookup"><span data-stu-id="97ce7-267">Variant types passed from COM to managed code and then back to COM might not retain the same variant type for the duration of the call.</span></span> <span data-ttu-id="97ce7-268">**VT_DISPATCH** 型のバリアントが COM から .NET Framework に渡される場合、どのようになるかを考えてみましょう。</span><span class="sxs-lookup"><span data-stu-id="97ce7-268">Consider what happens when a variant of type **VT_DISPATCH** is passed from COM to the .NET Framework.</span></span> <span data-ttu-id="97ce7-269">マーシャリング時に、バリアントは <xref:System.Object?displayProperty=nameWithType> に変換されます。</span><span class="sxs-lookup"><span data-stu-id="97ce7-269">During marshaling, the variant is converted to a <xref:System.Object?displayProperty=nameWithType>.</span></span> <span data-ttu-id="97ce7-270">その後、**Object** が COM に返される場合は、**VT_UNKNOWN** 型のバリアントにマーシャリングされます。</span><span class="sxs-lookup"><span data-stu-id="97ce7-270">If the **Object** is then passed back to COM, it is marshaled back to a variant of type **VT_UNKNOWN**.</span></span> <span data-ttu-id="97ce7-271">オブジェクトをマネージド コードから COM にマーシャリングするときに、生成されるバリアントの型が、最初にオブジェクトを生成するときに使用したバリアントの型と同じになる保証はありません。</span><span class="sxs-lookup"><span data-stu-id="97ce7-271">There is no guarantee that the variant produced when an object is marshaled from managed code to COM will be the same type as the variant initially used to produce the object.</span></span>  
  
## <a name="marshaling-byref-variants"></a><span data-ttu-id="97ce7-272">ByRef バリアントのマーシャリング</span><span class="sxs-lookup"><span data-stu-id="97ce7-272">Marshaling ByRef Variants</span></span>  
 <span data-ttu-id="97ce7-273">バリアント自体を値渡し、または参照渡しすることはできますが、**VT_BYREF** フラグを任意のバリアント型と併用した場合は、そのバリアントの内容を値渡しではなく、参照渡しすることを指定できます。</span><span class="sxs-lookup"><span data-stu-id="97ce7-273">Although variants themselves can be passed by value or by reference, the **VT_BYREF** flag can also be used with any variant type to indicate that the contents of the variant are being passed by reference instead of by value.</span></span> <span data-ttu-id="97ce7-274">バリアントの参照渡しによるマーシャリングと、**VT_BYREF** フラグの設定によるバリアントのマーシャリングとの違いがわかりづらい場合がああります。</span><span class="sxs-lookup"><span data-stu-id="97ce7-274">The difference between marshaling variants by reference and marshaling a variant with the **VT_BYREF** flag set can be confusing.</span></span> <span data-ttu-id="97ce7-275">その違いを次の図で明確にします。</span><span class="sxs-lookup"><span data-stu-id="97ce7-275">The following illustration clarifies the differences:</span></span>  
  
 ![スタックに渡されたバリアントを示す図。](./media/default-marshaling-for-objects/interop-variant-passed-value-reference.gif)  
<span data-ttu-id="97ce7-277">値渡しされるバリアントと参照渡しされるバリアント</span><span class="sxs-lookup"><span data-stu-id="97ce7-277">Variants passed by value and by reference</span></span>  
  
 <span data-ttu-id="97ce7-278">**オブジェクトとバリアントを値渡しでマーシャリングする場合の既定の動作**</span><span class="sxs-lookup"><span data-stu-id="97ce7-278">**Default behavior for marshaling objects and variants by value**</span></span>  
  
- <span data-ttu-id="97ce7-279">オブジェクトをマネージド コードから COM に渡す場合、そのオブジェクトの内容は、「[バリアントへのオブジェクトのマーシャリング](#marshaling-object-to-variant)」で定義されている規則を使用して、マーシャラーによって作成される新しいバリアントにコピーされます。</span><span class="sxs-lookup"><span data-stu-id="97ce7-279">When passing objects from managed code to COM, the contents of the object are copied into a new variant created by the marshaler, using the rules defined in [Marshaling Object to Variant](#marshaling-object-to-variant).</span></span> <span data-ttu-id="97ce7-280">アンマネージ側でバリアントに対して行われた変更の内容は、呼び出しから制御が返されるときに、元のオブジェクトには反映されません。</span><span class="sxs-lookup"><span data-stu-id="97ce7-280">Changes made to the variant on the unmanaged side are not propagated back to the original object on return from the call.</span></span>  
  
- <span data-ttu-id="97ce7-281">バリアントを COM からマネージド コードに渡す場合、そのバリアントの内容は、「[オブジェクトへのバリアントのマーシャリング](#marshaling-variant-to-object)」で定義されている規則を使用して、新規作成されるオブジェクトにコピーされます。</span><span class="sxs-lookup"><span data-stu-id="97ce7-281">When passing variants from COM to managed code, the contents of the variant are copied to a newly created object, using the rules defined in [Marshaling Variant to Object](#marshaling-variant-to-object).</span></span> <span data-ttu-id="97ce7-282">マネージド側でオブジェクトに対して行われた変更の内容は、呼び出しから制御が返されるときに、元のバリアントには反映されません。</span><span class="sxs-lookup"><span data-stu-id="97ce7-282">Changes made to the object on the managed side are not propagated back to the original variant on return from the call.</span></span>  
  
 <span data-ttu-id="97ce7-283">**オブジェクトとバリアントを参照渡しでマーシャリングする場合の既定の動作**</span><span class="sxs-lookup"><span data-stu-id="97ce7-283">**Default behavior for marshaling objects and variants by reference**</span></span>  
  
 <span data-ttu-id="97ce7-284">変更内容を呼び出し元に反映させるには、パラメーターを参照渡しする必要があります。</span><span class="sxs-lookup"><span data-stu-id="97ce7-284">To propagate changes back to the caller, the parameters must be passed by reference.</span></span> <span data-ttu-id="97ce7-285">たとえば、C# でキーワード **ref** (Visual Basic マネージド コードの場合は **ByRef**) を使用すると、パラメーターを参照渡しできます。</span><span class="sxs-lookup"><span data-stu-id="97ce7-285">For example, you can use the **ref** keyword in C# (or **ByRef** in Visual Basic managed code) to pass parameters by reference.</span></span> <span data-ttu-id="97ce7-286">COM の場合、参照パラメーターは **variant \*** などのポインターを使用して渡されます。</span><span class="sxs-lookup"><span data-stu-id="97ce7-286">In COM, reference parameters are passed using a pointer such as a **variant \***.</span></span>  
  
- <span data-ttu-id="97ce7-287">オブジェクトを COM に参照渡しする場合、マーシャラーは呼び出しを行う前に新しいバリアントを作成し、オブジェクト参照の内容をそのバリアントにコピーします。</span><span class="sxs-lookup"><span data-stu-id="97ce7-287">When passing an object to COM by reference, the marshaler creates a new variant and copies the contents of the object reference into the variant before the call is made.</span></span> <span data-ttu-id="97ce7-288">このバリアントはアンマネージ関数に渡されます。ここで、バリアントの内容を自由に変更できます。</span><span class="sxs-lookup"><span data-stu-id="97ce7-288">The variant is passed to the unmanaged function where the user is free to change the contents of the variant.</span></span> <span data-ttu-id="97ce7-289">呼び出しから制御が返されるときに、アンマネージ側でバリアントが変更されている場合には、その内容が元のオブジェクトに反映されます。</span><span class="sxs-lookup"><span data-stu-id="97ce7-289">On return from the call, any changes made to the variant on the unmanaged side are propagated back to the original object.</span></span> <span data-ttu-id="97ce7-290">バリアントの型が、呼び出しに渡されたバリアントの型と異なる場合、変更内容は別の型のオブジェクトに反映されます。</span><span class="sxs-lookup"><span data-stu-id="97ce7-290">If the type of the variant differs from the type of the variant passed to the call, then the changes are propagated back to an object of a different type.</span></span> <span data-ttu-id="97ce7-291">つまり、呼び出しに渡したオブジェクトの型が、呼び出しから返されるオブジェクトの型と異なることがあります。</span><span class="sxs-lookup"><span data-stu-id="97ce7-291">That is, the type of the object passed into the call can differ from the type of the object returned from the call.</span></span>  
  
- <span data-ttu-id="97ce7-292">バリアントをマネージド コードに参照渡しする場合、マーシャラーは呼び出しを行う前に、新しいオブジェクトを作成し、バリアントの内容をそのオブジェクトにコピーします。</span><span class="sxs-lookup"><span data-stu-id="97ce7-292">When passing a variant to managed code by reference, the marshaler creates a new object and copies the contents of the variant into the object before making the call.</span></span> <span data-ttu-id="97ce7-293">オブジェクトへの参照がマネージド関数に渡されます。ここで、オブジェクトを自由に変更できます。</span><span class="sxs-lookup"><span data-stu-id="97ce7-293">A reference to the object is passed to the managed function, where the user is free to change the object.</span></span> <span data-ttu-id="97ce7-294">呼び出しから制御が返されるときに、参照先オブジェクトが変更されている場合には、その内容が元のバリアントに反映されます。</span><span class="sxs-lookup"><span data-stu-id="97ce7-294">On return from the call, any changes made to the referenced object are propagated back to the original variant.</span></span> <span data-ttu-id="97ce7-295">オブジェクトの型が、呼び出しに渡されたオブジェクトの型と異なる場合、元のバリアントの型が変更され、値がそのバリアントに反映されます。</span><span class="sxs-lookup"><span data-stu-id="97ce7-295">If the type of the object differs from the type of the object passed in to the call, the type of the original variant is changed and the value is propagated back into the variant.</span></span> <span data-ttu-id="97ce7-296">ここでも、呼び出しに渡されたバリアントの型が、呼び出しから返されるバリアントの型と異なることがあります。</span><span class="sxs-lookup"><span data-stu-id="97ce7-296">Again, the type of the variant passed into the call can differ from the type of the variant returned from the call.</span></span>  
  
 <span data-ttu-id="97ce7-297">**VT_BYREF フラグの設定によるバリアントのマーシャリングの既定の動作**</span><span class="sxs-lookup"><span data-stu-id="97ce7-297">**Default behavior for marshaling a variant with the VT_BYREF flag set**</span></span>  
  
- <span data-ttu-id="97ce7-298">マネージド コードに値渡しされるバリアントに **VT_BYREF** フラグを設定することにより、そのバリアントに値ではなく、参照が含まれることを示すことができます。</span><span class="sxs-lookup"><span data-stu-id="97ce7-298">A variant being passed to managed code by value can have the **VT_BYREF** flag set to indicate that the variant contains a reference instead of a value.</span></span> <span data-ttu-id="97ce7-299">この場合でも、バリアントは値渡しされるため、オブジェクトにマーシャリングされます。</span><span class="sxs-lookup"><span data-stu-id="97ce7-299">In this case, the variant is still marshaled to an object because the variant is being passed by value.</span></span> <span data-ttu-id="97ce7-300">呼び出しを行う前に、マーシャラーは自動的にバリアントの内容を逆参照し、その内容を新しく作成されるオブジェクトにコピーします。</span><span class="sxs-lookup"><span data-stu-id="97ce7-300">The marshaler automatically dereferences the contents of the variant and copies it into a newly created object before making the call.</span></span> <span data-ttu-id="97ce7-301">その後、オブジェクトはマネージド関数に渡されます。ただし、呼び出しから制御が返されるときに、このオブジェクトは元のバリアントには反映されません。</span><span class="sxs-lookup"><span data-stu-id="97ce7-301">The object is then passed into the managed function; however, on return from the call, the object is not propagated back into the original variant.</span></span> <span data-ttu-id="97ce7-302">マネージド オブジェクトに対する変更内容は失われます。</span><span class="sxs-lookup"><span data-stu-id="97ce7-302">Changes made to the managed object are lost.</span></span>  
  
    > [!CAUTION]
    >  <span data-ttu-id="97ce7-303">バリアントに **VT_BYREF** フラグが設定されていても、値渡しされるバリアントの値を変更する方法はありません。</span><span class="sxs-lookup"><span data-stu-id="97ce7-303">There is no way to change the value of a variant passed by value, even if the variant has the **VT_BYREF** flag set.</span></span>  
  
- <span data-ttu-id="97ce7-304">マネージド コードに参照渡しされるバリアントについても、**VT_BYREF** フラグを設定することで、バリアントに別の参照が含まれることを示すことができます。</span><span class="sxs-lookup"><span data-stu-id="97ce7-304">A variant being passed to managed code by reference can also have the **VT_BYREF** flag set to indicate that the variant contains another reference.</span></span> <span data-ttu-id="97ce7-305">このようにすると、バリアントは参照渡しされるため、**ref** オブジェクトにマーシャリングされます。</span><span class="sxs-lookup"><span data-stu-id="97ce7-305">If it does, the variant is marshaled to a **ref** object because the variant is being passed by reference.</span></span> <span data-ttu-id="97ce7-306">呼び出しを行う前に、マーシャラーは自動的にバリアントの内容を逆参照し、その内容を新しく作成されるオブジェクトにコピーします。</span><span class="sxs-lookup"><span data-stu-id="97ce7-306">The marshaler automatically dereferences the contents of the variant and copies it into a newly created object before making the call.</span></span> <span data-ttu-id="97ce7-307">呼び出しから制御が返されるときに、オブジェクトの値が元のバリアント内の参照に反映されるのは、そのオブジェクトの型が渡されたオブジェクトの型と同じ場合に限られます。</span><span class="sxs-lookup"><span data-stu-id="97ce7-307">On return from the call, the value of the object is propagated back to the reference within the original variant only if the object is the same type as the object passed in.</span></span> <span data-ttu-id="97ce7-308">つまり、**VT_BYREF** フラグが設定されたバリアントの型が反映によって変更されることはありません。</span><span class="sxs-lookup"><span data-stu-id="97ce7-308">That is, propagation does not change the type of a variant with the **VT_BYREF** flag set.</span></span> <span data-ttu-id="97ce7-309">呼び出しの間にオブジェクトの型が変更された場合、呼び出しから制御が返されるときに <xref:System.InvalidCastException> が発生します。</span><span class="sxs-lookup"><span data-stu-id="97ce7-309">If the type of the object is changed during the call, an <xref:System.InvalidCastException> occurs on return from the call.</span></span>  
  
 <span data-ttu-id="97ce7-310">バリアントとオブジェクトに関する反映規則を次の表にまとめます。</span><span class="sxs-lookup"><span data-stu-id="97ce7-310">The following table summarizes the propagation rules for variants and objects.</span></span>  
  
|<span data-ttu-id="97ce7-311">From</span><span class="sxs-lookup"><span data-stu-id="97ce7-311">From</span></span>|<span data-ttu-id="97ce7-312">終了</span><span class="sxs-lookup"><span data-stu-id="97ce7-312">To</span></span>|<span data-ttu-id="97ce7-313">変更内容の反映</span><span class="sxs-lookup"><span data-stu-id="97ce7-313">Changes propagated back</span></span>|  
|----------|--------|-----------------------------|  
|<span data-ttu-id="97ce7-314">**Variant**  *v*</span><span class="sxs-lookup"><span data-stu-id="97ce7-314">**Variant**  *v*</span></span>|<span data-ttu-id="97ce7-315">**Object**  *o*</span><span class="sxs-lookup"><span data-stu-id="97ce7-315">**Object**  *o*</span></span>|<span data-ttu-id="97ce7-316">Never</span><span class="sxs-lookup"><span data-stu-id="97ce7-316">Never</span></span>|  
|<span data-ttu-id="97ce7-317">**Object**  *o*</span><span class="sxs-lookup"><span data-stu-id="97ce7-317">**Object**  *o*</span></span>|<span data-ttu-id="97ce7-318">**Variant**  *v*</span><span class="sxs-lookup"><span data-stu-id="97ce7-318">**Variant**  *v*</span></span>|<span data-ttu-id="97ce7-319">Never</span><span class="sxs-lookup"><span data-stu-id="97ce7-319">Never</span></span>|  
|<span data-ttu-id="97ce7-320">**Variant**   ***\****  *pv*</span><span class="sxs-lookup"><span data-stu-id="97ce7-320">**Variant**   ***\****  *pv*</span></span>|<span data-ttu-id="97ce7-321">**Ref Object**  *o*</span><span class="sxs-lookup"><span data-stu-id="97ce7-321">**Ref Object**  *o*</span></span>|<span data-ttu-id="97ce7-322">Always</span><span class="sxs-lookup"><span data-stu-id="97ce7-322">Always</span></span>|  
|<span data-ttu-id="97ce7-323">**Ref object**  *o*</span><span class="sxs-lookup"><span data-stu-id="97ce7-323">**Ref object**  *o*</span></span>|<span data-ttu-id="97ce7-324">**Variant**   ***\****  *pv*</span><span class="sxs-lookup"><span data-stu-id="97ce7-324">**Variant**   ***\****  *pv*</span></span>|<span data-ttu-id="97ce7-325">Always</span><span class="sxs-lookup"><span data-stu-id="97ce7-325">Always</span></span>|  
|<span data-ttu-id="97ce7-326">**Variant**  *v* **(VT_BYREF** *&#124;* **VT_\*)**</span><span class="sxs-lookup"><span data-stu-id="97ce7-326">**Variant**  *v* **(VT_BYREF** *&#124;* **VT_\*)**</span></span>|<span data-ttu-id="97ce7-327">**Object**  *o*</span><span class="sxs-lookup"><span data-stu-id="97ce7-327">**Object**  *o*</span></span>|<span data-ttu-id="97ce7-328">Never</span><span class="sxs-lookup"><span data-stu-id="97ce7-328">Never</span></span>|  
|<span data-ttu-id="97ce7-329">**Variant**  *v* **(VT_BYREF** *&#124;* **VT_)**</span><span class="sxs-lookup"><span data-stu-id="97ce7-329">**Variant**  *v* **(VT_BYREF** *&#124;* **VT_)**</span></span>|<span data-ttu-id="97ce7-330">**Ref Object**  *o*</span><span class="sxs-lookup"><span data-stu-id="97ce7-330">**Ref Object**  *o*</span></span>|<span data-ttu-id="97ce7-331">型が変更されていない場合のみ。</span><span class="sxs-lookup"><span data-stu-id="97ce7-331">Only if the type has not changed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="97ce7-332">関連項目</span><span class="sxs-lookup"><span data-stu-id="97ce7-332">See also</span></span>

- [<span data-ttu-id="97ce7-333">既定のマーシャリング動作</span><span class="sxs-lookup"><span data-stu-id="97ce7-333">Default Marshaling Behavior</span></span>](default-marshaling-behavior.md)
- [<span data-ttu-id="97ce7-334">Blittable 型と非 Blittable 型</span><span class="sxs-lookup"><span data-stu-id="97ce7-334">Blittable and Non-Blittable Types</span></span>](blittable-and-non-blittable-types.md)
- <span data-ttu-id="97ce7-335">[方向属性](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/77e6taeh(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="97ce7-335">[Directional Attributes](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/77e6taeh(v=vs.100))</span></span>
- [<span data-ttu-id="97ce7-336">コピーと固定</span><span class="sxs-lookup"><span data-stu-id="97ce7-336">Copying and Pinning</span></span>](copying-and-pinning.md)
