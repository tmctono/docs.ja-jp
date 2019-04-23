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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5c6ef901f43cd6568f17657ed8e58bc2cc2cc0a1
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59186057"
---
# <a name="icordebugappdomain2-interface"></a><span data-ttu-id="56c55-102">ICorDebugAppDomain2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="56c55-102">ICorDebugAppDomain2 Interface</span></span>

<span data-ttu-id="56c55-103">配列、ポインター、関数ポインター、および参照型を使用するメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="56c55-103">Provides methods to work with arrays, pointers, function pointers, and reference types.</span></span> <span data-ttu-id="56c55-104">このインターフェイスは、ICorDebugAppDomain インターフェイスの拡張機能です。</span><span class="sxs-lookup"><span data-stu-id="56c55-104">This interface is an extension of the ICorDebugAppDomain interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="56c55-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="56c55-105">Methods</span></span>  
  
|<span data-ttu-id="56c55-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="56c55-106">Method</span></span>|<span data-ttu-id="56c55-107">説明</span><span class="sxs-lookup"><span data-stu-id="56c55-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="56c55-108">GetArrayOrPointerType メソッド</span><span class="sxs-lookup"><span data-stu-id="56c55-108">GetArrayOrPointerType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain2-getarrayorpointertype-method.md)|<span data-ttu-id="56c55-109">指定した型、ポインター、または指定した型への参照の配列を取得します。</span><span class="sxs-lookup"><span data-stu-id="56c55-109">Gets an array of the specified type, or a pointer or reference to the specified type.</span></span>|  
|[<span data-ttu-id="56c55-110">GetFunctionPointerType</span><span class="sxs-lookup"><span data-stu-id="56c55-110">GetFunctionPointerType</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain2-getfunctionpointertype-method.md)|<span data-ttu-id="56c55-111">指定されたシグネチャを持つ関数へのポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="56c55-111">Gets a pointer to a function that has a given signature.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="56c55-112">Remarks</span><span class="sxs-lookup"><span data-stu-id="56c55-112">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="56c55-113">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="56c55-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="56c55-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="56c55-114">Requirements</span></span>  
 <span data-ttu-id="56c55-115">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="56c55-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="56c55-116">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="56c55-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="56c55-117">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="56c55-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="56c55-118">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="56c55-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56c55-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="56c55-119">See also</span></span>

- [<span data-ttu-id="56c55-120">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="56c55-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
