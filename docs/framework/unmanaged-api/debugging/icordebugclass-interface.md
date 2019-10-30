---
title: ICorDebugClass インターフェイス
ms.date: 03/30/2017
api_name:
- ICorDebugClass
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugClass
helpviewer_keywords:
- ICorDebugClass interface [.NET Framework debugging]
ms.assetid: 03a6facb-f12f-49be-9839-e73b9c791cd5
topic_type:
- apiref
ms.openlocfilehash: 5714597b5e5ca2936aad53217ae934684e75585c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125750"
---
# <a name="icordebugclass-interface"></a><span data-ttu-id="03488-102">ICorDebugClass インターフェイス</span><span class="sxs-lookup"><span data-stu-id="03488-102">ICorDebugClass Interface</span></span>

<span data-ttu-id="03488-103">基本型または複合型 (つまり、ユーザー定義) のいずれかの型を表します。</span><span class="sxs-lookup"><span data-stu-id="03488-103">Represents a type, which can be either basic or complex (that is, user-defined).</span></span> <span data-ttu-id="03488-104">型がジェネリックの場合、`ICorDebugClass` はインスタンス化されないジェネリック型を表します。</span><span class="sxs-lookup"><span data-stu-id="03488-104">If the type is generic, `ICorDebugClass` represents the uninstantiated generic type.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="03488-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="03488-105">Methods</span></span>  
  
|<span data-ttu-id="03488-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="03488-106">Method</span></span>|<span data-ttu-id="03488-107">説明</span><span class="sxs-lookup"><span data-stu-id="03488-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="03488-108">GetModule メソッド</span><span class="sxs-lookup"><span data-stu-id="03488-108">GetModule Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-getmodule-method.md)|<span data-ttu-id="03488-109">このクラスを定義するモジュールを取得します。</span><span class="sxs-lookup"><span data-stu-id="03488-109">Gets the module that defines this class.</span></span>|  
|[<span data-ttu-id="03488-110">GetStaticFieldValue メソッド</span><span class="sxs-lookup"><span data-stu-id="03488-110">GetStaticFieldValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-getstaticfieldvalue-method.md)|<span data-ttu-id="03488-111">指定された静的フィールドの値を取得します。</span><span class="sxs-lookup"><span data-stu-id="03488-111">Gets the value of the specified static field.</span></span>|  
|[<span data-ttu-id="03488-112">GetToken メソッド</span><span class="sxs-lookup"><span data-stu-id="03488-112">GetToken Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-gettoken-method.md)|<span data-ttu-id="03488-113">このクラスの `TypeDef` メタデータトークンを取得します。</span><span class="sxs-lookup"><span data-stu-id="03488-113">Gets the `TypeDef` metadata token for this class.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="03488-114">Remarks</span><span class="sxs-lookup"><span data-stu-id="03488-114">Remarks</span></span>  
 <span data-ttu-id="03488-115">`ICorDebugClass` インターフェイスは、インスタンスジェネリック型を表します。</span><span class="sxs-lookup"><span data-stu-id="03488-115">The `ICorDebugClass` interface represents an uninstantiated generic type.</span></span> <span data-ttu-id="03488-116">は、インスタンス化されたジェネリック型を表します。</span><span class="sxs-lookup"><span data-stu-id="03488-116">The ICorDebugType interface represents an instantiated generic type.</span></span> <span data-ttu-id="03488-117">たとえば、`Hashtable<K, V>` は `ICorDebugClass`によって表されるのに対し、`Hashtable<Int32, String>` は `ICorDebugType`で表されます。</span><span class="sxs-lookup"><span data-stu-id="03488-117">For example, `Hashtable<K, V>` would be represented by `ICorDebugClass`, whereas `Hashtable<Int32, String>` would be represented by `ICorDebugType`.</span></span>  
  
 <span data-ttu-id="03488-118">非ジェネリック型は、`ICorDebugClass` と `ICorDebugType`の両方で表されます。</span><span class="sxs-lookup"><span data-stu-id="03488-118">Non-generic types are represented by both `ICorDebugClass` and `ICorDebugType`.</span></span> <span data-ttu-id="03488-119">後者のインターフェイスは、型のインスタンス化を処理するために .NET Framework バージョン2.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="03488-119">The latter interface was introduced in the .NET Framework version 2.0 to deal with type instantiation.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="03488-120">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="03488-120">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="03488-121">［要件］</span><span class="sxs-lookup"><span data-stu-id="03488-121">Requirements</span></span>  
 <span data-ttu-id="03488-122">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="03488-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="03488-123">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="03488-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="03488-124">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="03488-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="03488-125">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="03488-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03488-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="03488-126">See also</span></span>

- [<span data-ttu-id="03488-127">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="03488-127">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
