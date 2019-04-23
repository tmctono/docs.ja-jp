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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7e1ad830e728fbe764085a5808a48e4cacedc595
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59133628"
---
# <a name="icordebugclass-interface"></a><span data-ttu-id="b3398-102">ICorDebugClass インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b3398-102">ICorDebugClass Interface</span></span>

<span data-ttu-id="b3398-103">基本型または複合型 (つまり、ユーザー定義) のいずれかの型を表します。</span><span class="sxs-lookup"><span data-stu-id="b3398-103">Represents a type, which can be either basic or complex (that is, user-defined).</span></span> <span data-ttu-id="b3398-104">型がジェネリックの場合、`ICorDebugClass` はインスタンス化されないジェネリック型を表します。</span><span class="sxs-lookup"><span data-stu-id="b3398-104">If the type is generic, `ICorDebugClass` represents the uninstantiated generic type.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b3398-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="b3398-105">Methods</span></span>  
  
|<span data-ttu-id="b3398-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="b3398-106">Method</span></span>|<span data-ttu-id="b3398-107">説明</span><span class="sxs-lookup"><span data-stu-id="b3398-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b3398-108">GetModule メソッド</span><span class="sxs-lookup"><span data-stu-id="b3398-108">GetModule Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-getmodule-method.md)|<span data-ttu-id="b3398-109">このクラスを定義するモジュールを取得します。</span><span class="sxs-lookup"><span data-stu-id="b3398-109">Gets the module that defines this class.</span></span>|  
|[<span data-ttu-id="b3398-110">GetStaticFieldValue メソッド</span><span class="sxs-lookup"><span data-stu-id="b3398-110">GetStaticFieldValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-getstaticfieldvalue-method.md)|<span data-ttu-id="b3398-111">指定された静的フィールドの値を取得します。</span><span class="sxs-lookup"><span data-stu-id="b3398-111">Gets the value of the specified static field.</span></span>|  
|[<span data-ttu-id="b3398-112">GetToken メソッド</span><span class="sxs-lookup"><span data-stu-id="b3398-112">GetToken Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-gettoken-method.md)|<span data-ttu-id="b3398-113">取得、`TypeDef`このクラスのメタデータ トークン。</span><span class="sxs-lookup"><span data-stu-id="b3398-113">Gets the `TypeDef` metadata token for this class.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b3398-114">Remarks</span><span class="sxs-lookup"><span data-stu-id="b3398-114">Remarks</span></span>  
 <span data-ttu-id="b3398-115">`ICorDebugClass`インターフェイスは、インスタンス化されていないジェネリック型を表します。</span><span class="sxs-lookup"><span data-stu-id="b3398-115">The `ICorDebugClass` interface represents an uninstantiated generic type.</span></span> <span data-ttu-id="b3398-116">ICorDebugType インターフェイスは、ジェネリック型のインスタンスを表します。</span><span class="sxs-lookup"><span data-stu-id="b3398-116">The ICorDebugType interface represents an instantiated generic type.</span></span> <span data-ttu-id="b3398-117">たとえば、`Hashtable<K, V>`で表されます`ICorDebugClass`であるのに対し`Hashtable<Int32, String>`で表されます`ICorDebugType`します。</span><span class="sxs-lookup"><span data-stu-id="b3398-117">For example, `Hashtable<K, V>` would be represented by `ICorDebugClass`, whereas `Hashtable<Int32, String>` would be represented by `ICorDebugType`.</span></span>  
  
 <span data-ttu-id="b3398-118">非ジェネリック型は型が両方によって表される`ICorDebugClass`と`ICorDebugType`します。</span><span class="sxs-lookup"><span data-stu-id="b3398-118">Non-generic types are represented by both `ICorDebugClass` and `ICorDebugType`.</span></span> <span data-ttu-id="b3398-119">後者のインターフェイスは、型のインスタンス化を処理するには、.NET Framework version 2.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="b3398-119">The latter interface was introduced in the .NET Framework version 2.0 to deal with type instantiation.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b3398-120">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="b3398-120">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b3398-121">必要条件</span><span class="sxs-lookup"><span data-stu-id="b3398-121">Requirements</span></span>  
 <span data-ttu-id="b3398-122">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b3398-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b3398-123">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b3398-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b3398-124">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b3398-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b3398-125">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b3398-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3398-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="b3398-126">See also</span></span>

- [<span data-ttu-id="b3398-127">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b3398-127">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
