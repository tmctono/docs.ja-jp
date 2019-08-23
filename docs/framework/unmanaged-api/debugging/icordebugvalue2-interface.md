---
title: ICorDebugValue2 インターフェイス
ms.date: 03/30/2017
api_name:
- ICorDebugValue2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValue2
helpviewer_keywords:
- ICorDebugValue2 interface [.NET Framework debugging]
ms.assetid: 3ff2ad2a-da5a-461b-8627-1a8eba49df9c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0925cf217afafe57abf82cf51a77b1992bad5152
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69966829"
---
# <a name="icordebugvalue2-interface"></a><span data-ttu-id="fbdcb-102">ICorDebugValue2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="fbdcb-102">ICorDebugValue2 Interface</span></span>
<span data-ttu-id="fbdcb-103">"ICorDebugValue" インターフェイスを拡張して "テキスト" オブジェクトのサポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="fbdcb-103">Extends the "ICorDebugValue" interface to provide support for "ICorDebugType" objects.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="fbdcb-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="fbdcb-104">Methods</span></span>  
  
|<span data-ttu-id="fbdcb-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="fbdcb-105">Method</span></span>|<span data-ttu-id="fbdcb-106">説明</span><span class="sxs-lookup"><span data-stu-id="fbdcb-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="fbdcb-107">GetExactType メソッド</span><span class="sxs-lookup"><span data-stu-id="fbdcb-107">GetExactType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue2-getexacttype-method.md)|<span data-ttu-id="fbdcb-108">この値`ICorDebugType` <xref:System.Type>のを表すオブジェクトへのインターフェイスポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="fbdcb-108">Gets an interface pointer to an `ICorDebugType` object that represents the <xref:System.Type> of this value.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fbdcb-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="fbdcb-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="fbdcb-110">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="fbdcb-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fbdcb-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="fbdcb-111">Requirements</span></span>  
 <span data-ttu-id="fbdcb-112">**・** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="fbdcb-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fbdcb-113">**ヘッダー:** CorDebug .idl、CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="fbdcb-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fbdcb-114">**ライブラリ**CorGuids .lib</span><span class="sxs-lookup"><span data-stu-id="fbdcb-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fbdcb-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fbdcb-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fbdcb-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="fbdcb-116">See also</span></span>

- [<span data-ttu-id="fbdcb-117">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="fbdcb-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)

- [<span data-ttu-id="fbdcb-118">ICorDebugValue3 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="fbdcb-118">ICorDebugValue3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-interface.md)
