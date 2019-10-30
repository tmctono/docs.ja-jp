---
title: ICorDebugInternalFrame::GetFrameType メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugInternalFrame.GetFrameType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugInternalFrame::GetFrameType
helpviewer_keywords:
- GetFrameType method [.NET Framework debugging]
- ICorDebugInternalFrame::GetFrameType method [.NET Framework debugging]
ms.assetid: da278a29-dc2e-4bf7-96ce-801bdc4d7025
topic_type:
- apiref
ms.openlocfilehash: b7a33fd6e2178e0e9188b81f516b231702fb6460
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122716"
---
# <a name="icordebuginternalframegetframetype-method"></a><span data-ttu-id="8dbcc-102">ICorDebugInternalFrame::GetFrameType メソッド</span><span class="sxs-lookup"><span data-stu-id="8dbcc-102">ICorDebugInternalFrame::GetFrameType Method</span></span>
<span data-ttu-id="8dbcc-103">この内部フレームの型を取得します。</span><span class="sxs-lookup"><span data-stu-id="8dbcc-103">Gets the type of this internal frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8dbcc-104">構文</span><span class="sxs-lookup"><span data-stu-id="8dbcc-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFrameType (  
    [out] CorDebugInternalFrameType  *pType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8dbcc-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="8dbcc-105">Parameters</span></span>  
 `pType`  
 <span data-ttu-id="8dbcc-106">入出力この `ICorDebugInternalFrame` オブジェクトによって表される内部フレームの種類を示す CorDebugInternalFrameType 列挙値へのポインター。</span><span class="sxs-lookup"><span data-stu-id="8dbcc-106">[out] A pointer to a value of the CorDebugInternalFrameType enumeration that indicates the type of internal frame represented by this `ICorDebugInternalFrame` object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8dbcc-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="8dbcc-107">Remarks</span></span>  
 <span data-ttu-id="8dbcc-108">内部フレームの種類が STUBFRAME_NONE になることはありません。</span><span class="sxs-lookup"><span data-stu-id="8dbcc-108">The internal frame type will never be STUBFRAME_NONE.</span></span> <span data-ttu-id="8dbcc-109">デバッガーは、認識されない内部フレーム型を正常に無視する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8dbcc-109">Debuggers should gracefully ignore unrecognized internal frame types.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8dbcc-110">［要件］</span><span class="sxs-lookup"><span data-stu-id="8dbcc-110">Requirements</span></span>  
 <span data-ttu-id="8dbcc-111">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8dbcc-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8dbcc-112">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8dbcc-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8dbcc-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8dbcc-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8dbcc-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8dbcc-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
