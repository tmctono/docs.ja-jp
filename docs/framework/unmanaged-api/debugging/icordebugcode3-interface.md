---
title: ICorDebugCode3 インターフェイス
ms.date: 03/30/2017
api_name:
- ICorDebugCode3
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode3
helpviewer_keywords:
- ICorDebugCode3 interface [.NET Framework debugging]
ms.assetid: 70f07c9e-0614-4bee-ac34-09fe6c51c5a9
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4efcf6d477ab006e179e283ca4ce7b62c27018a6
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69960763"
---
# <a name="icordebugcode3-interface"></a><span data-ttu-id="eaf2a-102">ICorDebugCode3 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="eaf2a-102">ICorDebugCode3 Interface</span></span>
<span data-ttu-id="eaf2a-103">"" のコード "と" ICorDebugCode2 "を拡張して、マネージ戻り値に関する情報を提供するメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="eaf2a-103">Provides a method that extends "ICorDebugCode" and "ICorDebugCode2" to provide information about a managed return value.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="eaf2a-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="eaf2a-104">Methods</span></span>  
  
|<span data-ttu-id="eaf2a-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="eaf2a-105">Method</span></span>|<span data-ttu-id="eaf2a-106">説明</span><span class="sxs-lookup"><span data-stu-id="eaf2a-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="eaf2a-107">GetReturnValueLiveOffSet メソッド</span><span class="sxs-lookup"><span data-stu-id="eaf2a-107">GetReturnValueLiveOffset Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-getreturnvalueliveoffset-method.md)|<span data-ttu-id="eaf2a-108">指定した IL オフセットについて、デバッガーが関数からの戻り値を取得できるように、ブレークポイントを配置する必要があるネイティブなオフセットを取得します。</span><span class="sxs-lookup"><span data-stu-id="eaf2a-108">For a specified IL offset, gets the native offsets where a breakpoint should be placed so that the debugger can obtain the return value from a function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="eaf2a-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="eaf2a-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="eaf2a-110">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="eaf2a-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eaf2a-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="eaf2a-111">Requirements</span></span>  
 <span data-ttu-id="eaf2a-112">**・** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="eaf2a-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eaf2a-113">**ヘッダー:** CorDebug .idl、CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="eaf2a-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="eaf2a-114">**ライブラリ**CorGuids .lib</span><span class="sxs-lookup"><span data-stu-id="eaf2a-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="eaf2a-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v451plus](../../../../includes/net-current-v451plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eaf2a-115">**.NET Framework Versions:** [!INCLUDE[net_current_v451plus](../../../../includes/net-current-v451plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eaf2a-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="eaf2a-116">See also</span></span>

- [<span data-ttu-id="eaf2a-117">ICorDebugILFrame3 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="eaf2a-117">ICorDebugILFrame3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe3-interface.md)
- [<span data-ttu-id="eaf2a-118">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="eaf2a-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
