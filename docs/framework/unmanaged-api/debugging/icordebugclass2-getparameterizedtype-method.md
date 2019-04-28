---
title: ICorDebugClass2::GetParameterizedType メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugClass2.GetParameterizedType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugClass2::GetParameterizedType
helpviewer_keywords:
- GetParameterizedType method [.NET Framework debugging]
- ICorDebugClass2::GetParameterizedType method [.NET Framework debugging]
ms.assetid: 94b591c4-9302-4af2-a510-089496afb036
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5e1734ca91fd48cc15b8dbf25f11518ed0455b6f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61750775"
---
# <a name="icordebugclass2getparameterizedtype-method"></a><span data-ttu-id="0c669-102">ICorDebugClass2::GetParameterizedType メソッド</span><span class="sxs-lookup"><span data-stu-id="0c669-102">ICorDebugClass2::GetParameterizedType Method</span></span>
<span data-ttu-id="0c669-103">このクラスの型宣言を取得します。</span><span class="sxs-lookup"><span data-stu-id="0c669-103">Gets the type declaration for this class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0c669-104">構文</span><span class="sxs-lookup"><span data-stu-id="0c669-104">Syntax</span></span>  
  
```  
HRESULT GetParameterizedType (  
    [in] CorElementType                      elementType,  
    [in] ULONG32                             nTypeArgs,  
    [in, size_is(nTypeArgs)] ICorDebugType  *ppTypeArgs[],  
    [out] ICorDebugType                    **ppType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0c669-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="0c669-105">Parameters</span></span>  
 `elementType`  
 <span data-ttu-id="0c669-106">[in]このクラスの要素の型を指定する CorElementType 列挙型の値:この ICorDebugClass2 が値型を表している場合は、この値を ELEMENT_TYPE_VALUETYPE に設定します。</span><span class="sxs-lookup"><span data-stu-id="0c669-106">[in] A value of the CorElementType enumeration that specifies the element type for this class: Set this value to ELEMENT_TYPE_VALUETYPE if this ICorDebugClass2 represents a value type.</span></span> <span data-ttu-id="0c669-107">この場合、この値を ELEMENT_TYPE_CLASS に設定`ICorDebugClass2`複合型を表します。</span><span class="sxs-lookup"><span data-stu-id="0c669-107">Set this value to ELEMENT_TYPE_CLASS if this `ICorDebugClass2` represents a complex type.</span></span>  
  
 `nTypeArgs`  
 <span data-ttu-id="0c669-108">[in]型がジェネリックの場合、型パラメーターの数。</span><span class="sxs-lookup"><span data-stu-id="0c669-108">[in] The number of type parameters, if the type is generic.</span></span> <span data-ttu-id="0c669-109">型パラメーター (ある場合) の数は、クラスに必要な数と一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0c669-109">The number of type parameters (if any) must match the number required by the class.</span></span>  
  
 `ppTypeArgs`  
 <span data-ttu-id="0c669-110">[in]型パラメーターを表す ICorDebugType オブジェクトを指す各ポインターの配列。</span><span class="sxs-lookup"><span data-stu-id="0c669-110">[in] An array of pointers, each of which points to an ICorDebugType object that represents a type parameter.</span></span> <span data-ttu-id="0c669-111">クラスが非ジェネリックの場合は、この値が null です。</span><span class="sxs-lookup"><span data-stu-id="0c669-111">If the class is non-generic, this value is null.</span></span>  
  
 `ppType`  
 <span data-ttu-id="0c669-112">[out]アドレスへのポインター、`ICorDebugType`型宣言を表すオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="0c669-112">[out] A pointer to the address of an `ICorDebugType` object that represents the type declaration.</span></span> <span data-ttu-id="0c669-113">このオブジェクトが等しく、<xref:System.Type>マネージ コード内のオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="0c669-113">This object is equivalent to a <xref:System.Type> object in managed code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0c669-114">Remarks</span><span class="sxs-lookup"><span data-stu-id="0c669-114">Remarks</span></span>  
 <span data-ttu-id="0c669-115">クラスは非ジェネリックは、型のパラメーターが存在しない場合`GetParameterizedType`単にクラスに対応するランタイム型のオブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="0c669-115">If the class is non-generic, that is, if it has no type parameters, `GetParameterizedType` simply gets the runtime type object corresponding to the class.</span></span> <span data-ttu-id="0c669-116">`elementType`クラスの適切な要素の型にパラメーターを設定する必要があります。ELEMENT_TYPE_VALUETYPE クラスが値型である場合それ以外の場合、ELEMENT_TYPE_CLASS します。</span><span class="sxs-lookup"><span data-stu-id="0c669-116">The `elementType` parameter should be set to the correct element type for the class: ELEMENT_TYPE_VALUETYPE if the class is a value type; otherwise, ELEMENT_TYPE_CLASS.</span></span>  
  
 <span data-ttu-id="0c669-117">クラスが型パラメーターを受け入れる場合 (たとえば、 `ArrayList<T>`)、使用することができます`GetParameterizedType`などの型のインスタンスの型のオブジェクトを構築する`ArrayList<int>`します。</span><span class="sxs-lookup"><span data-stu-id="0c669-117">If the class accepts type parameters (for example, `ArrayList<T>`), you can use `GetParameterizedType` to construct a type object for an instantiated type such as `ArrayList<int>`.</span></span>  
  
## <a name="background-information"></a><span data-ttu-id="0c669-118">背景情報</span><span class="sxs-lookup"><span data-stu-id="0c669-118">Background Information</span></span>  
 <span data-ttu-id="0c669-119">.NET Framework バージョン 1.0 および 1.1 では、メタデータ内のすべての型を直接実行中のプロセス内の型にマップする。</span><span class="sxs-lookup"><span data-stu-id="0c669-119">In the .NET Framework versions 1.0 and 1.1, every type in the metadata could be directly mapped to a type in the running process.</span></span> <span data-ttu-id="0c669-120">したがって、メタデータの種類と、ランタイム型は、実行中のプロセスで 1 つの表現必要があります。</span><span class="sxs-lookup"><span data-stu-id="0c669-120">Thus, a metadata type and a runtime type had a single representation in the running process.</span></span> <span data-ttu-id="0c669-121">ただし、メタデータ内の 1 つのジェネリック型は、実行中のプロセスでの型の複数の異なるインスタンスにマップできます。</span><span class="sxs-lookup"><span data-stu-id="0c669-121">However, one generic type in metadata can be mapped to many different instantiations of the type in the running process.</span></span> <span data-ttu-id="0c669-122">たとえば、メタデータ型`SortedList<K,V>`にマップできます`SortedList<String, EmployeeRecord>`、 `SortedList<Int32, String>`、`SortedList<String,Array<Int32>>`など。</span><span class="sxs-lookup"><span data-stu-id="0c669-122">For example, the metadata type `SortedList<K,V>` can map to `SortedList<String, EmployeeRecord>`, `SortedList<Int32, String>`, `SortedList<String,Array<Int32>>`, and so on.</span></span> <span data-ttu-id="0c669-123">そのため、型のインスタンス化を処理する方法をする必要があります。</span><span class="sxs-lookup"><span data-stu-id="0c669-123">Thus, you need a way to handle type instantiation.</span></span>  
  
 <span data-ttu-id="0c669-124">.NET Framework version 2.0 では、`ICorDebugType`インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="0c669-124">The .NET Framework version 2.0 introduces the `ICorDebugType` interface.</span></span> <span data-ttu-id="0c669-125">ジェネリック型の場合、`ICorDebugClass`または`ICorDebugClass2`オブジェクトがインスタンス化されていない型を表します (`SortedList<K,V>`)、および`ICorDebugType`オブジェクトは、さまざまなインスタンス化された型を表します。</span><span class="sxs-lookup"><span data-stu-id="0c669-125">For a generic type, an `ICorDebugClass` or `ICorDebugClass2` object represents the uninstantiated type (`SortedList<K,V>`), and an `ICorDebugType` object represents the various instantiated types.</span></span> <span data-ttu-id="0c669-126">指定された、`ICorDebugClass`または`ICorDebugClass2`オブジェクトを作成することができます、`ICorDebugType`オブジェクトのすべてのインスタンス化を呼び出して、`ICorDebugClass2::GetParameterizedType`メソッド。</span><span class="sxs-lookup"><span data-stu-id="0c669-126">Given an `ICorDebugClass` or `ICorDebugClass2` object, you can create an `ICorDebugType` object for any instantiation by calling the `ICorDebugClass2::GetParameterizedType` method.</span></span> <span data-ttu-id="0c669-127">作成することも、 `ICorDebugType` Int32 などの単純型または非ジェネリックの種類のオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="0c669-127">You can also create an `ICorDebugType` object for a simple type, such as Int32, or for a non-generic type.</span></span>  
  
 <span data-ttu-id="0c669-128">導入に伴い、`ICorDebugType`型の実行時の概念を表すオブジェクトが、API 全体に影響します。</span><span class="sxs-lookup"><span data-stu-id="0c669-128">The introduction of the `ICorDebugType` object to represent the run-time notion of a type has a ripple effect throughout the API.</span></span> <span data-ttu-id="0c669-129">かかっていた関数、`ICorDebugClass`または`ICorDebugClass2`オブジェクトまたはであっても、`CorElementType`を値が汎用化されて、`ICorDebugType`オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="0c669-129">Functions that previously took an `ICorDebugClass` or `ICorDebugClass2` object or even a `CorElementType` value are generalized to take an `ICorDebugType` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0c669-130">必要条件</span><span class="sxs-lookup"><span data-stu-id="0c669-130">Requirements</span></span>  
 <span data-ttu-id="0c669-131">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="0c669-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0c669-132">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0c669-132">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0c669-133">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0c669-133">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0c669-134">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0c669-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
