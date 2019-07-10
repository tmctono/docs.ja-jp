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
ms.openlocfilehash: b293a3e166bb2614b5d0b064485178f5a569db48
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67774141"
---
# <a name="icordebugvariablehomegetliverange-method"></a><span data-ttu-id="b63f2-102">IcorDebugVariableHome::GetLiveRange メソッド</span><span class="sxs-lookup"><span data-stu-id="b63f2-102">IcorDebugVariableHome::GetLiveRange Method</span></span>
<span data-ttu-id="b63f2-103">この変数はライブのネイティブの範囲を取得します。</span><span class="sxs-lookup"><span data-stu-id="b63f2-103">Gets the native range over which this variable is live.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b63f2-104">構文</span><span class="sxs-lookup"><span data-stu-id="b63f2-104">Syntax</span></span>  
  
```cpp  
HRESULT GetLiveRange(  
    [out] ULONG32* pStartOffset,  
    [out] ULONG32 *pEndOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b63f2-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="b63f2-105">Parameters</span></span>  
 `pStartOffset`  
 <span data-ttu-id="b63f2-106">[out]これで、変数が最初ライブ論理オフセット。</span><span class="sxs-lookup"><span data-stu-id="b63f2-106">[out] The logical offset at which the variable is first live.</span></span>  
  
 `pEndOffset`  
 <span data-ttu-id="b63f2-107">[out]位置、変数が最後ライブ後すぐに論理オフセット。</span><span class="sxs-lookup"><span data-stu-id="b63f2-107">[out] The logical offset immediately after the point at which the variable is last live.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b63f2-108">必要条件</span><span class="sxs-lookup"><span data-stu-id="b63f2-108">Requirements</span></span>  
 <span data-ttu-id="b63f2-109">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b63f2-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b63f2-110">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b63f2-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b63f2-111">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b63f2-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b63f2-112">**.NET Framework のバージョン:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b63f2-112">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b63f2-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="b63f2-113">See also</span></span>

- [<span data-ttu-id="b63f2-114">ICorDebugVariableHome インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b63f2-114">ICorDebugVariableHome Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)
