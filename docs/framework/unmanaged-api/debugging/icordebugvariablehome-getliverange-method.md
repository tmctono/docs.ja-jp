---
title: IcorDebugVariableHome::GetLiveRange メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugVariableHome.GetLiveRange
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHome::GetLiveRange
helpviewer_keywords:
- ICorDebugVariableHome::GetLiveRange method [.NET Framework debugging]
- GetLiveRange method, ICorDebugVariableFrame interface [.NET Framework debugging]
ms.assetid: 87277e1a-1595-4729-9e25-d1c3ac18ce5f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7e2c9e981f431bb87df61a71389abf3d42a6a507
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59123813"
---
# <a name="icordebugvariablehomegetliverange-method"></a><span data-ttu-id="9a696-102">IcorDebugVariableHome::GetLiveRange メソッド</span><span class="sxs-lookup"><span data-stu-id="9a696-102">IcorDebugVariableHome::GetLiveRange Method</span></span>
<span data-ttu-id="9a696-103">この変数はライブのネイティブの範囲を取得します。</span><span class="sxs-lookup"><span data-stu-id="9a696-103">Gets the native range over which this variable is live.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9a696-104">構文</span><span class="sxs-lookup"><span data-stu-id="9a696-104">Syntax</span></span>  
  
```  
HRESULT GetLiveRange(  
    [out] ULONG32* pStartOffset,  
    [out] ULONG32 *pEndOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9a696-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="9a696-105">Parameters</span></span>  
 `pStartOffset`  
 <span data-ttu-id="9a696-106">[out]これで、変数が最初ライブ論理オフセット。</span><span class="sxs-lookup"><span data-stu-id="9a696-106">[out] The logical offset at which the variable is first live.</span></span>  
  
 `pEndOffset`  
 <span data-ttu-id="9a696-107">[out]位置、変数が最後ライブ後すぐに論理オフセット。</span><span class="sxs-lookup"><span data-stu-id="9a696-107">[out] The logical offset immediately after the point at which the variable is last live.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9a696-108">必要条件</span><span class="sxs-lookup"><span data-stu-id="9a696-108">Requirements</span></span>  
 <span data-ttu-id="9a696-109">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="9a696-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9a696-110">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9a696-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9a696-111">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9a696-111">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="9a696-112">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="9a696-112">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="9a696-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="9a696-113">See also</span></span>

- [<span data-ttu-id="9a696-114">ICorDebugVariableHome インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9a696-114">ICorDebugVariableHome Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)
