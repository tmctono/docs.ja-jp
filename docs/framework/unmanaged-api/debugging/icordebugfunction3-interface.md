---
title: ICorDebugFunction3 インターフェイス
ms.date: 03/30/2017
api_name:
- ICorDebugFunction3
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: b22717b9-ead5-4eea-887e-789b52d613dc
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a3eebdf56796fe599ec6ff62d7008d1af3be796e
ms.sourcegitcommit: 33c8d6f7342a4bb2c577842b7f075b0e20a2fa40
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2019
ms.locfileid: "70926830"
---
# <a name="icordebugfunction3-interface"></a><span data-ttu-id="730d6-102">ICorDebugFunction3 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="730d6-102">ICorDebugFunction3 Interface</span></span>
<span data-ttu-id="730d6-103">[.NET Framework 4.5.2 以降のバージョンでのみでサポート]</span><span class="sxs-lookup"><span data-stu-id="730d6-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="730d6-104">により、再 Jit 要求からコードへのアクセスを提供するために、の関数インターフェイスを論理的に拡張します。</span><span class="sxs-lookup"><span data-stu-id="730d6-104">Logically extends the ICorDebugFunction interface to provide access to code from a ReJIT request.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="730d6-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="730d6-105">Methods</span></span>  
  
|<span data-ttu-id="730d6-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="730d6-106">Method</span></span>|<span data-ttu-id="730d6-107">説明</span><span class="sxs-lookup"><span data-stu-id="730d6-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="730d6-108">GetActiveReJitRequestILCode メソッド</span><span class="sxs-lookup"><span data-stu-id="730d6-108">GetActiveReJitRequestILCode Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction3-getactiverejitrequestilcode-method.md)|<span data-ttu-id="730d6-109">アクティブな ReJIT 要求から IL を含む、[コード](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-interface.md)へのインターフェイスポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="730d6-109">Gets an interface pointer to an [ICorDebugILCode](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-interface.md) that contains the IL from an active ReJIT request.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="730d6-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="730d6-110">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="730d6-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="730d6-111">Requirements</span></span>  
 <span data-ttu-id="730d6-112">**・** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="730d6-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="730d6-113">**ヘッダー:** CorDebug .idl、CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="730d6-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="730d6-114">**ライブラリ**CorGuids .lib</span><span class="sxs-lookup"><span data-stu-id="730d6-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="730d6-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="730d6-115">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="730d6-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="730d6-116">See also</span></span>

- [<span data-ttu-id="730d6-117">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="730d6-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="730d6-118">デバッグ</span><span class="sxs-lookup"><span data-stu-id="730d6-118">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="730d6-119">ReJITハウツーガイド</span><span class="sxs-lookup"><span data-stu-id="730d6-119">ReJIT: A How-To Guide</span></span>](https://blogs.msdn.microsoft.com/davbr/2011/10/12/rejit-a-how-to-guide/)
