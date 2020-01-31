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
ms.openlocfilehash: 8210e67f4bdd615ff65d9bd3474043fc45fd8883
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791258"
---
# <a name="icordebugtype-interface"></a><span data-ttu-id="3a1a9-102">ICorDebugType インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3a1a9-102">ICorDebugType Interface</span></span>
<span data-ttu-id="3a1a9-103">基本または複合 (つまり、ユーザー定義) のいずれかの型を表します。</span><span class="sxs-lookup"><span data-stu-id="3a1a9-103">Represents a type, either basic or complex (that is, user-defined).</span></span> <span data-ttu-id="3a1a9-104">型がジェネリックの場合、`ICorDebugType` はインスタンス化されたジェネリック型を表します。</span><span class="sxs-lookup"><span data-stu-id="3a1a9-104">If the type is generic, `ICorDebugType` represents the instantiated generic type.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3a1a9-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="3a1a9-105">Methods</span></span>  
  
|<span data-ttu-id="3a1a9-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="3a1a9-106">Method</span></span>|<span data-ttu-id="3a1a9-107">説明</span><span class="sxs-lookup"><span data-stu-id="3a1a9-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3a1a9-108">EnumerateTypeParameters メソッド</span><span class="sxs-lookup"><span data-stu-id="3a1a9-108">EnumerateTypeParameters Method</span></span>](icordebugtype-enumeratetypeparameters-method.md)|<span data-ttu-id="3a1a9-109">この `ICorDebugType`によって参照されるクラスのジェネリック <xref:System.Type> パラメーターを参照する、ツールのインターフェイスポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="3a1a9-109">Gets an interface pointer to an ICorDebugTypeEnum that references the generic <xref:System.Type> parameters of the class referenced by this `ICorDebugType`.</span></span>|  
|[<span data-ttu-id="3a1a9-110">GetBase メソッド</span><span class="sxs-lookup"><span data-stu-id="3a1a9-110">GetBase Method</span></span>](icordebugtype-getbase-method.md)|<span data-ttu-id="3a1a9-111">この `ICorDebugType`によって参照されるクラスの基底クラスが存在する場合は、その基底クラスを参照する `ICorDebugType` へのインターフェイスポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="3a1a9-111">Gets an interface pointer to an `ICorDebugType` that references the base class of the class referenced by this `ICorDebugType`, if one exists.</span></span>|  
|[<span data-ttu-id="3a1a9-112">GetClass メソッド</span><span class="sxs-lookup"><span data-stu-id="3a1a9-112">GetClass Method</span></span>](icordebugtype-getclass-method.md)|<span data-ttu-id="3a1a9-113">この `ICorDebugType`の型指定されたコンストラクターを参照する、のクラスへのインターフェイスポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="3a1a9-113">Gets an interface pointer to an ICorDebugClass that references the typed constructor of this `ICorDebugType`.</span></span>|  
|[<span data-ttu-id="3a1a9-114">GetFirstTypeParameter メソッド</span><span class="sxs-lookup"><span data-stu-id="3a1a9-114">GetFirstTypeParameter Method</span></span>](icordebugtype-getfirsttypeparameter-method.md)|<span data-ttu-id="3a1a9-115">この `ICorDebugType`によって参照されるクラスのコンストラクターの最初のジェネリック <xref:System.Type> パラメーターを参照する `ICorDebugType` へのインターフェイスポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="3a1a9-115">Gets an interface pointer to an `ICorDebugType` that references the first generic <xref:System.Type> parameter for the constructor of the class referenced by this `ICorDebugType`.</span></span>|  
|[<span data-ttu-id="3a1a9-116">GetRank メソッド</span><span class="sxs-lookup"><span data-stu-id="3a1a9-116">GetRank Method</span></span>](icordebugtype-getrank-method.md)|<span data-ttu-id="3a1a9-117">配列型の次元数を取得します。</span><span class="sxs-lookup"><span data-stu-id="3a1a9-117">Gets the number of dimensions in an array type.</span></span>|  
|[<span data-ttu-id="3a1a9-118">GetStaticFieldValue メソッド</span><span class="sxs-lookup"><span data-stu-id="3a1a9-118">GetStaticFieldValue Method</span></span>](icordebugtype-getstaticfieldvalue-method.md)|<span data-ttu-id="3a1a9-119">指定したスタックフレーム内の指定したフィールドトークンによって参照される静的フィールドの値を格納する、ICorDebugValue へのインターフェイスポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="3a1a9-119">Gets an interface pointer to an ICorDebugValue that contains the value of the static field referenced by the specified field token in the specified stack frame.</span></span>|  
|[<span data-ttu-id="3a1a9-120">GetType メソッド</span><span class="sxs-lookup"><span data-stu-id="3a1a9-120">GetType Method</span></span>](icordebugtype-gettype-method.md)|<span data-ttu-id="3a1a9-121">この `ICorDebugType`によって参照される共通言語ランタイム <xref:System.Type> のネイティブ型を記述する CorElementType 値を取得します。</span><span class="sxs-lookup"><span data-stu-id="3a1a9-121">Gets a CorElementType value that describes the native type of the common language runtime <xref:System.Type> referenced by this `ICorDebugType`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3a1a9-122">コメント</span><span class="sxs-lookup"><span data-stu-id="3a1a9-122">Remarks</span></span>  
 <span data-ttu-id="3a1a9-123">型がジェネリックの場合、`ICorDebugClass` はインスタンス型を表します。</span><span class="sxs-lookup"><span data-stu-id="3a1a9-123">If the type is generic, `ICorDebugClass` represents the uninstantiated type.</span></span> <span data-ttu-id="3a1a9-124">`ICorDebugType` インターフェイスは、インスタンス化されたジェネリック型を表します。</span><span class="sxs-lookup"><span data-stu-id="3a1a9-124">The `ICorDebugType` interface represents an instantiated generic type.</span></span> <span data-ttu-id="3a1a9-125">たとえば、Hashtable\<K、V > は `ICorDebugClass`によって表されますが、Hashtable\<Int32、String > は `ICorDebugType`によって表されます。</span><span class="sxs-lookup"><span data-stu-id="3a1a9-125">For example, Hashtable\<K, V> would be represented by `ICorDebugClass`, whereas Hashtable\<Int32, String> would be represented by `ICorDebugType`.</span></span>  
  
 <span data-ttu-id="3a1a9-126">非ジェネリック型は、`ICorDebugClass` と `ICorDebugType`の両方で表されます。</span><span class="sxs-lookup"><span data-stu-id="3a1a9-126">Non-generic types are represented by both `ICorDebugClass` and `ICorDebugType`.</span></span> <span data-ttu-id="3a1a9-127">後者のインターフェイスは、型のインスタンス化を処理するために .NET Framework バージョン2.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="3a1a9-127">The latter interface was introduced in the .NET Framework version 2.0 to deal with type instantiation.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3a1a9-128">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="3a1a9-128">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3a1a9-129">要件</span><span class="sxs-lookup"><span data-stu-id="3a1a9-129">Requirements</span></span>  
 <span data-ttu-id="3a1a9-130">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3a1a9-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3a1a9-131">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3a1a9-131">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3a1a9-132">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3a1a9-132">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3a1a9-133">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3a1a9-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a1a9-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="3a1a9-134">See also</span></span>

- [<span data-ttu-id="3a1a9-135">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3a1a9-135">Debugging Interfaces</span></span>](debugging-interfaces.md)
