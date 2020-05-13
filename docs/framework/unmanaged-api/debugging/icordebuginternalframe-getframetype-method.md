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
ms.openlocfilehash: 6b598352f734cf47514a82de1d0fca65d430a9ab
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/12/2020
ms.locfileid: "83209969"
---
# <a name="icordebuginternalframegetframetype-method"></a><span data-ttu-id="1a31b-102">ICorDebugInternalFrame::GetFrameType メソッド</span><span class="sxs-lookup"><span data-stu-id="1a31b-102">ICorDebugInternalFrame::GetFrameType Method</span></span>
<span data-ttu-id="1a31b-103">この内部フレームの型を取得します。</span><span class="sxs-lookup"><span data-stu-id="1a31b-103">Gets the type of this internal frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1a31b-104">構文</span><span class="sxs-lookup"><span data-stu-id="1a31b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFrameType (  
    [out] CorDebugInternalFrameType  *pType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1a31b-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="1a31b-105">Parameters</span></span>  
 `pType`  
 <span data-ttu-id="1a31b-106">入出力このオブジェクトによって表される内部フレームの種類を示す CorDebugInternalFrameType 列挙値へのポインター `ICorDebugInternalFrame` 。</span><span class="sxs-lookup"><span data-stu-id="1a31b-106">[out] A pointer to a value of the CorDebugInternalFrameType enumeration that indicates the type of internal frame represented by this `ICorDebugInternalFrame` object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1a31b-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="1a31b-107">Remarks</span></span>  
 <span data-ttu-id="1a31b-108">内部フレームの種類は STUBFRAME_NONE されません。</span><span class="sxs-lookup"><span data-stu-id="1a31b-108">The internal frame type will never be STUBFRAME_NONE.</span></span> <span data-ttu-id="1a31b-109">デバッガーは、認識されない内部フレーム型を正常に無視する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1a31b-109">Debuggers should gracefully ignore unrecognized internal frame types.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1a31b-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="1a31b-110">Requirements</span></span>  
 <span data-ttu-id="1a31b-111">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1a31b-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1a31b-112">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1a31b-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1a31b-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1a31b-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1a31b-114">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1a31b-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
