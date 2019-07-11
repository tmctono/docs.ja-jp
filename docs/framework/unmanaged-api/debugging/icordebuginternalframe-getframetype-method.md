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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2a5461cc6a78347cdbe0d0b13f8111cb24c11006
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67760048"
---
# <a name="icordebuginternalframegetframetype-method"></a><span data-ttu-id="60561-102">ICorDebugInternalFrame::GetFrameType メソッド</span><span class="sxs-lookup"><span data-stu-id="60561-102">ICorDebugInternalFrame::GetFrameType Method</span></span>
<span data-ttu-id="60561-103">この内部フレームの種類を取得します。</span><span class="sxs-lookup"><span data-stu-id="60561-103">Gets the type of this internal frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="60561-104">構文</span><span class="sxs-lookup"><span data-stu-id="60561-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFrameType (  
    [out] CorDebugInternalFrameType  *pType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="60561-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="60561-105">Parameters</span></span>  
 `pType`  
 <span data-ttu-id="60561-106">[out]これによって表される内部のフレームの種類を示す CorDebugInternalFrameType 列挙型の値へのポインター`ICorDebugInternalFrame`オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="60561-106">[out] A pointer to a value of the CorDebugInternalFrameType enumeration that indicates the type of internal frame represented by this `ICorDebugInternalFrame` object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="60561-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="60561-107">Remarks</span></span>  
 <span data-ttu-id="60561-108">内部フレームの種類には、STUBFRAME_NONE はできません。</span><span class="sxs-lookup"><span data-stu-id="60561-108">The internal frame type will never be STUBFRAME_NONE.</span></span> <span data-ttu-id="60561-109">デバッガーは適切に認識されていない内部フレームの種類を無視します。</span><span class="sxs-lookup"><span data-stu-id="60561-109">Debuggers should gracefully ignore unrecognized internal frame types.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="60561-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="60561-110">Requirements</span></span>  
 <span data-ttu-id="60561-111">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="60561-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="60561-112">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="60561-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="60561-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="60561-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="60561-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="60561-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
