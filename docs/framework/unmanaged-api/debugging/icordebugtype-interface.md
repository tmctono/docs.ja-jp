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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b830af5d59c0eb177d815451ecedbdc14121aaad
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69964757"
---
# <a name="icordebugtype-interface"></a><span data-ttu-id="66070-102">ICorDebugType インターフェイス</span><span class="sxs-lookup"><span data-stu-id="66070-102">ICorDebugType Interface</span></span>
<span data-ttu-id="66070-103">基本または複合 (つまり、ユーザー定義) のいずれかの型を表します。</span><span class="sxs-lookup"><span data-stu-id="66070-103">Represents a type, either basic or complex (that is, user-defined).</span></span> <span data-ttu-id="66070-104">型がジェネリックの場合、`ICorDebugType` はインスタンス化されたジェネリック型を表します。</span><span class="sxs-lookup"><span data-stu-id="66070-104">If the type is generic, `ICorDebugType` represents the instantiated generic type.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="66070-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="66070-105">Methods</span></span>  
  
|<span data-ttu-id="66070-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="66070-106">Method</span></span>|<span data-ttu-id="66070-107">説明</span><span class="sxs-lookup"><span data-stu-id="66070-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="66070-108">EnumerateTypeParameters メソッド</span><span class="sxs-lookup"><span data-stu-id="66070-108">EnumerateTypeParameters Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-enumeratetypeparameters-method.md)|<span data-ttu-id="66070-109"><xref:System.Type> この`ICorDebugType`によって参照されるクラスのジェネリックパラメーターを参照する、ツールのインターフェイスポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="66070-109">Gets an interface pointer to an ICorDebugTypeEnum that references the generic <xref:System.Type> parameters of the class referenced by this `ICorDebugType`.</span></span>|  
|[<span data-ttu-id="66070-110">GetBase メソッド</span><span class="sxs-lookup"><span data-stu-id="66070-110">GetBase Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getbase-method.md)|<span data-ttu-id="66070-111">`ICorDebugType` この`ICorDebugType`によって参照されるクラス (存在する場合) の基本クラスを参照するへのインターフェイスポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="66070-111">Gets an interface pointer to an `ICorDebugType` that references the base class of the class referenced by this `ICorDebugType`, if one exists.</span></span>|  
|[<span data-ttu-id="66070-112">GetClass メソッド</span><span class="sxs-lookup"><span data-stu-id="66070-112">GetClass Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getclass-method.md)|<span data-ttu-id="66070-113">この`ICorDebugType`の型指定されたコンストラクターを参照する、によるクラスへのインターフェイスポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="66070-113">Gets an interface pointer to an ICorDebugClass that references the typed constructor of this `ICorDebugType`.</span></span>|  
|[<span data-ttu-id="66070-114">GetFirstTypeParameter メソッド</span><span class="sxs-lookup"><span data-stu-id="66070-114">GetFirstTypeParameter Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getfirsttypeparameter-method.md)|<span data-ttu-id="66070-115">この<xref:System.Type> `ICorDebugType` によって参照されるクラスのコンストラクターの最初のジェネリックパラメーターを参照するへのインターフェイスポインターを取得します。`ICorDebugType`</span><span class="sxs-lookup"><span data-stu-id="66070-115">Gets an interface pointer to an `ICorDebugType` that references the first generic <xref:System.Type> parameter for the constructor of the class referenced by this `ICorDebugType`.</span></span>|  
|[<span data-ttu-id="66070-116">GetRank メソッド</span><span class="sxs-lookup"><span data-stu-id="66070-116">GetRank Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getrank-method.md)|<span data-ttu-id="66070-117">配列型の次元数を取得します。</span><span class="sxs-lookup"><span data-stu-id="66070-117">Gets the number of dimensions in an array type.</span></span>|  
|[<span data-ttu-id="66070-118">GetStaticFieldValue メソッド</span><span class="sxs-lookup"><span data-stu-id="66070-118">GetStaticFieldValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getstaticfieldvalue-method.md)|<span data-ttu-id="66070-119">指定したスタックフレーム内の指定したフィールドトークンによって参照される静的フィールドの値を格納する、ICorDebugValue へのインターフェイスポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="66070-119">Gets an interface pointer to an ICorDebugValue that contains the value of the static field referenced by the specified field token in the specified stack frame.</span></span>|  
|[<span data-ttu-id="66070-120">GetType メソッド</span><span class="sxs-lookup"><span data-stu-id="66070-120">GetType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-gettype-method.md)|<span data-ttu-id="66070-121"><xref:System.Type> この`ICorDebugType`によって参照される共通言語ランタイムのネイティブ型を記述する corelementtype 値を取得します。</span><span class="sxs-lookup"><span data-stu-id="66070-121">Gets a CorElementType value that describes the native type of the common language runtime <xref:System.Type> referenced by this `ICorDebugType`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="66070-122">Remarks</span><span class="sxs-lookup"><span data-stu-id="66070-122">Remarks</span></span>  
 <span data-ttu-id="66070-123">型がジェネリックの場合、 `ICorDebugClass`はインスタンス型を表します。</span><span class="sxs-lookup"><span data-stu-id="66070-123">If the type is generic, `ICorDebugClass` represents the uninstantiated type.</span></span> <span data-ttu-id="66070-124">インターフェイス`ICorDebugType`は、インスタンス化されたジェネリック型を表します。</span><span class="sxs-lookup"><span data-stu-id="66070-124">The `ICorDebugType` interface represents an instantiated generic type.</span></span> <span data-ttu-id="66070-125">たとえば、ハッシュテーブル\<K、V > はで`ICorDebugClass`表されますが、\<hashtable Int32、String > はによっ`ICorDebugType`て表されます。</span><span class="sxs-lookup"><span data-stu-id="66070-125">For example, Hashtable\<K, V> would be represented by `ICorDebugClass`, whereas Hashtable\<Int32, String> would be represented by `ICorDebugType`.</span></span>  
  
 <span data-ttu-id="66070-126">非ジェネリック型は、と`ICorDebugClass` `ICorDebugType`の両方で表されます。</span><span class="sxs-lookup"><span data-stu-id="66070-126">Non-generic types are represented by both `ICorDebugClass` and `ICorDebugType`.</span></span> <span data-ttu-id="66070-127">後者のインターフェイスは、型のインスタンス化を処理するために .NET Framework バージョン2.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="66070-127">The latter interface was introduced in the .NET Framework version 2.0 to deal with type instantiation.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="66070-128">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="66070-128">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="66070-129">必要条件</span><span class="sxs-lookup"><span data-stu-id="66070-129">Requirements</span></span>  
 <span data-ttu-id="66070-130">**・** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="66070-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="66070-131">**ヘッダー:** CorDebug .idl、CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="66070-131">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="66070-132">**ライブラリ**CorGuids .lib</span><span class="sxs-lookup"><span data-stu-id="66070-132">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="66070-133">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="66070-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66070-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="66070-134">See also</span></span>

- [<span data-ttu-id="66070-135">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="66070-135">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
