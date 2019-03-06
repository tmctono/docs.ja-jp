---
title: ICorDebugFunction::GetCurrentVersionNumber メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugFunction.GetCurrentVersionNumber
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction::GetCurrentVersionNumber
helpviewer_keywords:
- GetCurrentVersionNumber method [.NET Framework debugging]
- ICorDebugFunction::GetCurrentVersionNumber method [.NET Framework debugging]
ms.assetid: c3af1575-cbe6-457a-bc08-c53460edcbc8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ea615eacb30fd4e7a0fd7d730094c2ab4f9dc285
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57478480"
---
# <a name="icordebugfunctiongetcurrentversionnumber-method"></a><span data-ttu-id="e454e-102">ICorDebugFunction::GetCurrentVersionNumber メソッド</span><span class="sxs-lookup"><span data-stu-id="e454e-102">ICorDebugFunction::GetCurrentVersionNumber Method</span></span>
<span data-ttu-id="e454e-103">ICorDebugFunction オブジェクトによって表される関数に対して行われた最新の編集のバージョン番号を取得します。</span><span class="sxs-lookup"><span data-stu-id="e454e-103">Gets the version number of the latest edit made to the function represented by this ICorDebugFunction object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e454e-104">構文</span><span class="sxs-lookup"><span data-stu-id="e454e-104">Syntax</span></span>  
  
```  
HRESULT GetCurrentVersionNumber (  
    [out] ULONG32 *pnCurrentVersion  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e454e-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e454e-105">Parameters</span></span>  
 `pnCurrentVersion`  
 <span data-ttu-id="e454e-106">[out]この関数に対して行われた最後の編集のバージョンの数を表す整数値へのポインター。</span><span class="sxs-lookup"><span data-stu-id="e454e-106">[out] A pointer to an integer value that is the version number of the latest edit made to this function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e454e-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="e454e-107">Remarks</span></span>  
 <span data-ttu-id="e454e-108">この関数に対して行われた最新の編集のバージョン番号は、関数自体のバージョン番号より大きくすることがあります。</span><span class="sxs-lookup"><span data-stu-id="e454e-108">The version number of the latest edit made to this function may be greater than the version number of the function itself.</span></span> <span data-ttu-id="e454e-109">いずれかを使用して、 [icordebugfunction 2::getversionnumber](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction2-getversionnumber-method.md)メソッドまたは[icordebugcode::getversionnumber](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getversionnumber-method.md)関数のバージョン番号を取得します。</span><span class="sxs-lookup"><span data-stu-id="e454e-109">Use either the [ICorDebugFunction2::GetVersionNumber](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction2-getversionnumber-method.md) method or the [ICorDebugCode::GetVersionNumber](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getversionnumber-method.md) method to retrieve the version number of the function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e454e-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="e454e-110">Requirements</span></span>  
 <span data-ttu-id="e454e-111">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e454e-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e454e-112">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e454e-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e454e-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e454e-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e454e-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e454e-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
