---
title: ICorDebugAppDomain2 インターフェイス
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain2
helpviewer_keywords:
- ICorDebugAppDomain2 interface [.NET Framework debugging]
ms.assetid: 314d29f3-feb0-4a92-9530-b569c280cc31
topic_type:
- apiref
ms.openlocfilehash: bff270ff774692d058a36c7f47ab474b08bceb35
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73088957"
---
# <a name="icordebugappdomain2-interface"></a><span data-ttu-id="b8d96-102">ICorDebugAppDomain2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b8d96-102">ICorDebugAppDomain2 Interface</span></span>

<span data-ttu-id="b8d96-103">配列、ポインター、関数ポインター、および参照型を操作するメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="b8d96-103">Provides methods to work with arrays, pointers, function pointers, and reference types.</span></span> <span data-ttu-id="b8d96-104">このインターフェイスは、の機能を持つ Appdomain インターフェイスの拡張です。</span><span class="sxs-lookup"><span data-stu-id="b8d96-104">This interface is an extension of the ICorDebugAppDomain interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b8d96-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="b8d96-105">Methods</span></span>  
  
|<span data-ttu-id="b8d96-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="b8d96-106">Method</span></span>|<span data-ttu-id="b8d96-107">説明</span><span class="sxs-lookup"><span data-stu-id="b8d96-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b8d96-108">GetArrayOrPointerType メソッド</span><span class="sxs-lookup"><span data-stu-id="b8d96-108">GetArrayOrPointerType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain2-getarrayorpointertype-method.md)|<span data-ttu-id="b8d96-109">指定した型、または指定した型へのポインターまたは参照の配列を取得します。</span><span class="sxs-lookup"><span data-stu-id="b8d96-109">Gets an array of the specified type, or a pointer or reference to the specified type.</span></span>|  
|[<span data-ttu-id="b8d96-110">GetFunctionPointerType</span><span class="sxs-lookup"><span data-stu-id="b8d96-110">GetFunctionPointerType</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain2-getfunctionpointertype-method.md)|<span data-ttu-id="b8d96-111">指定されたシグネチャを持つ関数へのポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="b8d96-111">Gets a pointer to a function that has a given signature.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b8d96-112">Remarks</span><span class="sxs-lookup"><span data-stu-id="b8d96-112">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b8d96-113">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="b8d96-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b8d96-114">［要件］</span><span class="sxs-lookup"><span data-stu-id="b8d96-114">Requirements</span></span>  
 <span data-ttu-id="b8d96-115">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b8d96-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b8d96-116">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b8d96-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b8d96-117">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b8d96-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b8d96-118">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b8d96-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8d96-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="b8d96-119">See also</span></span>

- [<span data-ttu-id="b8d96-120">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b8d96-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
