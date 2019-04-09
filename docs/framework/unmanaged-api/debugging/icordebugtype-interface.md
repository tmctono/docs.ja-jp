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
ms.openlocfilehash: 74863af1096f8600b8095e593c1f3c820c512e9d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59166804"
---
# <a name="icordebugtype-interface"></a><span data-ttu-id="74505-102">ICorDebugType インターフェイス</span><span class="sxs-lookup"><span data-stu-id="74505-102">ICorDebugType Interface</span></span>
<span data-ttu-id="74505-103">型、基本または複雑な (つまり、ユーザー定義) を表します。</span><span class="sxs-lookup"><span data-stu-id="74505-103">Represents a type, either basic or complex (that is, user-defined).</span></span> <span data-ttu-id="74505-104">型がジェネリックの場合、`ICorDebugType` はインスタンス化されたジェネリック型を表します。</span><span class="sxs-lookup"><span data-stu-id="74505-104">If the type is generic, `ICorDebugType` represents the instantiated generic type.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="74505-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="74505-105">Methods</span></span>  
  
|<span data-ttu-id="74505-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="74505-106">Method</span></span>|<span data-ttu-id="74505-107">説明</span><span class="sxs-lookup"><span data-stu-id="74505-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="74505-108">EnumerateTypeParameters メソッド</span><span class="sxs-lookup"><span data-stu-id="74505-108">EnumerateTypeParameters Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-enumeratetypeparameters-method.md)|<span data-ttu-id="74505-109">ジェネリックを参照する、ICorDebugTypeEnum へのインターフェイス ポインターを取得<xref:System.Type>これによって参照されるクラスのパラメーター`ICorDebugType`します。</span><span class="sxs-lookup"><span data-stu-id="74505-109">Gets an interface pointer to an ICorDebugTypeEnum that references the generic <xref:System.Type> parameters of the class referenced by this `ICorDebugType`.</span></span>|  
|[<span data-ttu-id="74505-110">GetBase メソッド</span><span class="sxs-lookup"><span data-stu-id="74505-110">GetBase Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getbase-method.md)|<span data-ttu-id="74505-111">インターフェイス ポインターを取得、`ICorDebugType`これによって参照されるクラスの基底クラスを参照する`ICorDebugType`が存在する場合は、します。</span><span class="sxs-lookup"><span data-stu-id="74505-111">Gets an interface pointer to an `ICorDebugType` that references the base class of the class referenced by this `ICorDebugType`, if one exists.</span></span>|  
|[<span data-ttu-id="74505-112">GetClass メソッド</span><span class="sxs-lookup"><span data-stu-id="74505-112">GetClass Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getclass-method.md)|<span data-ttu-id="74505-113">この型指定されたコンス トラクターを参照する、ICorDebugClass へのインターフェイス ポインターを取得`ICorDebugType`します。</span><span class="sxs-lookup"><span data-stu-id="74505-113">Gets an interface pointer to an ICorDebugClass that references the typed constructor of this `ICorDebugType`.</span></span>|  
|[<span data-ttu-id="74505-114">GetFirstTypeParameter メソッド</span><span class="sxs-lookup"><span data-stu-id="74505-114">GetFirstTypeParameter Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getfirsttypeparameter-method.md)|<span data-ttu-id="74505-115">インターフェイス ポインターを取得、`ICorDebugType`を参照する最初のジェネリック<xref:System.Type>これによって参照されるクラスのコンス トラクターのパラメーター`ICorDebugType`します。</span><span class="sxs-lookup"><span data-stu-id="74505-115">Gets an interface pointer to an `ICorDebugType` that references the first generic <xref:System.Type> parameter for the constructor of the class referenced by this `ICorDebugType`.</span></span>|  
|[<span data-ttu-id="74505-116">GetRank メソッド</span><span class="sxs-lookup"><span data-stu-id="74505-116">GetRank Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getrank-method.md)|<span data-ttu-id="74505-117">配列型の次元数を取得します。</span><span class="sxs-lookup"><span data-stu-id="74505-117">Gets the number of dimensions in an array type.</span></span>|  
|[<span data-ttu-id="74505-118">GetStaticFieldValue メソッド</span><span class="sxs-lookup"><span data-stu-id="74505-118">GetStaticFieldValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getstaticfieldvalue-method.md)|<span data-ttu-id="74505-119">指定したスタック フレームでトークンを指定したフィールドによって参照される静的フィールドの値を格納インターフェイス ポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="74505-119">Gets an interface pointer to an ICorDebugValue that contains the value of the static field referenced by the specified field token in the specified stack frame.</span></span>|  
|[<span data-ttu-id="74505-120">GetType メソッド</span><span class="sxs-lookup"><span data-stu-id="74505-120">GetType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-gettype-method.md)|<span data-ttu-id="74505-121">共通言語ランタイムのネイティブな型を記述する CorElementType 値を取得します<xref:System.Type>これによって参照される`ICorDebugType`します。</span><span class="sxs-lookup"><span data-stu-id="74505-121">Gets a CorElementType value that describes the native type of the common language runtime <xref:System.Type> referenced by this `ICorDebugType`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="74505-122">Remarks</span><span class="sxs-lookup"><span data-stu-id="74505-122">Remarks</span></span>  
 <span data-ttu-id="74505-123">場合は、型がジェネリック`ICorDebugClass`インスタンス化されていない型を表します。</span><span class="sxs-lookup"><span data-stu-id="74505-123">If the type is generic, `ICorDebugClass` represents the uninstantiated type.</span></span> <span data-ttu-id="74505-124">`ICorDebugType`インターフェイスはジェネリック型のインスタンスを表します。</span><span class="sxs-lookup"><span data-stu-id="74505-124">The `ICorDebugType` interface represents an instantiated generic type.</span></span> <span data-ttu-id="74505-125">たとえば、ハッシュ テーブル\<K, V > で表されます`ICorDebugClass`一方、ハッシュ テーブル\<Int32, String > で表されます`ICorDebugType`します。</span><span class="sxs-lookup"><span data-stu-id="74505-125">For example, Hashtable\<K, V> would be represented by `ICorDebugClass`, whereas Hashtable\<Int32, String> would be represented by `ICorDebugType`.</span></span>  
  
 <span data-ttu-id="74505-126">非ジェネリック型は型が両方によって表される`ICorDebugClass`と`ICorDebugType`します。</span><span class="sxs-lookup"><span data-stu-id="74505-126">Non-generic types are represented by both `ICorDebugClass` and `ICorDebugType`.</span></span> <span data-ttu-id="74505-127">後者のインターフェイスは、型のインスタンス化を処理するには、.NET Framework version 2.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="74505-127">The latter interface was introduced in the .NET Framework version 2.0 to deal with type instantiation.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="74505-128">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="74505-128">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="74505-129">必要条件</span><span class="sxs-lookup"><span data-stu-id="74505-129">Requirements</span></span>  
 <span data-ttu-id="74505-130">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="74505-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="74505-131">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="74505-131">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="74505-132">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="74505-132">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="74505-133">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="74505-133">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="74505-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="74505-134">See also</span></span>

- [<span data-ttu-id="74505-135">デバッグのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="74505-135">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
