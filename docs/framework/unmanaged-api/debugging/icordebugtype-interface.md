---
title: ICorDebugType インターフェイス
ms.date: 03/30/2017
api_name:
- ICorDebugType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugType
helpviewer_keywords:
- ICorDebugType interface [.NET Framework debugging]
ms.assetid: 94e02e31-67ea-4b00-8148-a46740a4571d
topic_type:
- apiref
ms.openlocfilehash: 4f3f553ed5dc93433610365e0dae5bee54863de5
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129625"
---
# <a name="icordebugtype-interface"></a><span data-ttu-id="95406-102">ICorDebugType インターフェイス</span><span class="sxs-lookup"><span data-stu-id="95406-102">ICorDebugType Interface</span></span>
<span data-ttu-id="95406-103">基本または複合 (つまり、ユーザー定義) のいずれかの型を表します。</span><span class="sxs-lookup"><span data-stu-id="95406-103">Represents a type, either basic or complex (that is, user-defined).</span></span> <span data-ttu-id="95406-104">型がジェネリックの場合、`ICorDebugType` はインスタンス化されたジェネリック型を表します。</span><span class="sxs-lookup"><span data-stu-id="95406-104">If the type is generic, `ICorDebugType` represents the instantiated generic type.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="95406-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="95406-105">Methods</span></span>  
  
|<span data-ttu-id="95406-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="95406-106">Method</span></span>|<span data-ttu-id="95406-107">説明</span><span class="sxs-lookup"><span data-stu-id="95406-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="95406-108">EnumerateTypeParameters メソッド</span><span class="sxs-lookup"><span data-stu-id="95406-108">EnumerateTypeParameters Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-enumeratetypeparameters-method.md)|<span data-ttu-id="95406-109">この `ICorDebugType`によって参照されるクラスのジェネリック <xref:System.Type> パラメーターを参照する、ツールのインターフェイスポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="95406-109">Gets an interface pointer to an ICorDebugTypeEnum that references the generic <xref:System.Type> parameters of the class referenced by this `ICorDebugType`.</span></span>|  
|[<span data-ttu-id="95406-110">GetBase メソッド</span><span class="sxs-lookup"><span data-stu-id="95406-110">GetBase Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getbase-method.md)|<span data-ttu-id="95406-111">この `ICorDebugType`によって参照されるクラスの基底クラスが存在する場合は、その基底クラスを参照する `ICorDebugType` へのインターフェイスポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="95406-111">Gets an interface pointer to an `ICorDebugType` that references the base class of the class referenced by this `ICorDebugType`, if one exists.</span></span>|  
|[<span data-ttu-id="95406-112">GetClass メソッド</span><span class="sxs-lookup"><span data-stu-id="95406-112">GetClass Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getclass-method.md)|<span data-ttu-id="95406-113">この `ICorDebugType`の型指定されたコンストラクターを参照する、のクラスへのインターフェイスポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="95406-113">Gets an interface pointer to an ICorDebugClass that references the typed constructor of this `ICorDebugType`.</span></span>|  
|[<span data-ttu-id="95406-114">GetFirstTypeParameter メソッド</span><span class="sxs-lookup"><span data-stu-id="95406-114">GetFirstTypeParameter Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getfirsttypeparameter-method.md)|<span data-ttu-id="95406-115">この `ICorDebugType`によって参照されるクラスのコンストラクターの最初のジェネリック <xref:System.Type> パラメーターを参照する `ICorDebugType` へのインターフェイスポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="95406-115">Gets an interface pointer to an `ICorDebugType` that references the first generic <xref:System.Type> parameter for the constructor of the class referenced by this `ICorDebugType`.</span></span>|  
|[<span data-ttu-id="95406-116">GetRank メソッド</span><span class="sxs-lookup"><span data-stu-id="95406-116">GetRank Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getrank-method.md)|<span data-ttu-id="95406-117">配列型の次元数を取得します。</span><span class="sxs-lookup"><span data-stu-id="95406-117">Gets the number of dimensions in an array type.</span></span>|  
|[<span data-ttu-id="95406-118">GetStaticFieldValue メソッド</span><span class="sxs-lookup"><span data-stu-id="95406-118">GetStaticFieldValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getstaticfieldvalue-method.md)|<span data-ttu-id="95406-119">指定したスタックフレーム内の指定したフィールドトークンによって参照される静的フィールドの値を格納する、ICorDebugValue へのインターフェイスポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="95406-119">Gets an interface pointer to an ICorDebugValue that contains the value of the static field referenced by the specified field token in the specified stack frame.</span></span>|  
|[<span data-ttu-id="95406-120">GetType メソッド</span><span class="sxs-lookup"><span data-stu-id="95406-120">GetType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-gettype-method.md)|<span data-ttu-id="95406-121">この `ICorDebugType`によって参照される共通言語ランタイム <xref:System.Type> のネイティブ型を記述する CorElementType 値を取得します。</span><span class="sxs-lookup"><span data-stu-id="95406-121">Gets a CorElementType value that describes the native type of the common language runtime <xref:System.Type> referenced by this `ICorDebugType`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="95406-122">Remarks</span><span class="sxs-lookup"><span data-stu-id="95406-122">Remarks</span></span>  
 <span data-ttu-id="95406-123">型がジェネリックの場合、`ICorDebugClass` はインスタンス型を表します。</span><span class="sxs-lookup"><span data-stu-id="95406-123">If the type is generic, `ICorDebugClass` represents the uninstantiated type.</span></span> <span data-ttu-id="95406-124">`ICorDebugType` インターフェイスは、インスタンス化されたジェネリック型を表します。</span><span class="sxs-lookup"><span data-stu-id="95406-124">The `ICorDebugType` interface represents an instantiated generic type.</span></span> <span data-ttu-id="95406-125">たとえば、Hashtable\<K、V > は `ICorDebugClass`によって表されますが、Hashtable\<Int32、String > は `ICorDebugType`によって表されます。</span><span class="sxs-lookup"><span data-stu-id="95406-125">For example, Hashtable\<K, V> would be represented by `ICorDebugClass`, whereas Hashtable\<Int32, String> would be represented by `ICorDebugType`.</span></span>  
  
 <span data-ttu-id="95406-126">非ジェネリック型は、`ICorDebugClass` と `ICorDebugType`の両方で表されます。</span><span class="sxs-lookup"><span data-stu-id="95406-126">Non-generic types are represented by both `ICorDebugClass` and `ICorDebugType`.</span></span> <span data-ttu-id="95406-127">後者のインターフェイスは、型のインスタンス化を処理するために .NET Framework バージョン2.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="95406-127">The latter interface was introduced in the .NET Framework version 2.0 to deal with type instantiation.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="95406-128">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="95406-128">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="95406-129">［要件］</span><span class="sxs-lookup"><span data-stu-id="95406-129">Requirements</span></span>  
 <span data-ttu-id="95406-130">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="95406-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="95406-131">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="95406-131">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="95406-132">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="95406-132">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="95406-133">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="95406-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95406-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="95406-134">See also</span></span>

- [<span data-ttu-id="95406-135">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="95406-135">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
