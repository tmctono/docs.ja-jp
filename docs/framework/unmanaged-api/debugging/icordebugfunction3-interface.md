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
ms.openlocfilehash: 4c29d631f84ce2dd7532e32951e71d6597218ebb
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59088861"
---
# <a name="icordebugfunction3-interface"></a><span data-ttu-id="3e477-102">ICorDebugFunction3 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3e477-102">ICorDebugFunction3 Interface</span></span>
<span data-ttu-id="3e477-103">[.NET Framework 4.5.2 以降のバージョンでのみでサポート]</span><span class="sxs-lookup"><span data-stu-id="3e477-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="3e477-104">ReJIT 要求からコードへのアクセスを提供する ICorDebugFunction インターフェイスを論理的に拡張します。</span><span class="sxs-lookup"><span data-stu-id="3e477-104">Logically extends the ICorDebugFunction interface to provide access to code from a ReJIT request.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3e477-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="3e477-105">Methods</span></span>  
  
|<span data-ttu-id="3e477-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="3e477-106">Method</span></span>|<span data-ttu-id="3e477-107">説明</span><span class="sxs-lookup"><span data-stu-id="3e477-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3e477-108">GetActiveReJitRequestILCode メソッド</span><span class="sxs-lookup"><span data-stu-id="3e477-108">GetActiveReJitRequestILCode Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction3-getactiverejitrequestilcode-method.md)|<span data-ttu-id="3e477-109">インターフェイス ポインターを取得、 [ICorDebugILCode](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-interface.md)アクティブな ReJIT 要求から IL を格納しています。</span><span class="sxs-lookup"><span data-stu-id="3e477-109">Gets an interface pointer to an [ICorDebugILCode](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-interface.md) that contains the IL from an active ReJIT request.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3e477-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="3e477-110">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3e477-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="3e477-111">Requirements</span></span>  
 <span data-ttu-id="3e477-112">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3e477-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3e477-113">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3e477-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3e477-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3e477-114">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="3e477-115">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="3e477-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="3e477-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="3e477-116">See also</span></span>

- [<span data-ttu-id="3e477-117">デバッグのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="3e477-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="3e477-118">デバッグ</span><span class="sxs-lookup"><span data-stu-id="3e477-118">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="3e477-119">ReJIT:ハウツー ガイド</span><span class="sxs-lookup"><span data-stu-id="3e477-119">ReJIT: A How-To Guide</span></span>](https://blogs.msdn.com/b/davbr/archive/2011/10/12/rejit-a-how-to-guide.aspx)
