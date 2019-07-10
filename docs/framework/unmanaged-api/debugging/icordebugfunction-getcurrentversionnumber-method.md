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
ms.openlocfilehash: be66e0e2c9aff788d1003878891b8d64d6353500
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67754701"
---
# <a name="icordebugfunctiongetcurrentversionnumber-method"></a><span data-ttu-id="923e1-102">ICorDebugFunction::GetCurrentVersionNumber メソッド</span><span class="sxs-lookup"><span data-stu-id="923e1-102">ICorDebugFunction::GetCurrentVersionNumber Method</span></span>
<span data-ttu-id="923e1-103">ICorDebugFunction オブジェクトによって表される関数に対して行われた最新の編集のバージョン番号を取得します。</span><span class="sxs-lookup"><span data-stu-id="923e1-103">Gets the version number of the latest edit made to the function represented by this ICorDebugFunction object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="923e1-104">構文</span><span class="sxs-lookup"><span data-stu-id="923e1-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCurrentVersionNumber (  
    [out] ULONG32 *pnCurrentVersion  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="923e1-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="923e1-105">Parameters</span></span>  
 `pnCurrentVersion`  
 <span data-ttu-id="923e1-106">[out]この関数に対して行われた最後の編集のバージョンの数を表す整数値へのポインター。</span><span class="sxs-lookup"><span data-stu-id="923e1-106">[out] A pointer to an integer value that is the version number of the latest edit made to this function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="923e1-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="923e1-107">Remarks</span></span>  
 <span data-ttu-id="923e1-108">この関数に対して行われた最新の編集のバージョン番号は、関数自体のバージョン番号より大きくすることがあります。</span><span class="sxs-lookup"><span data-stu-id="923e1-108">The version number of the latest edit made to this function may be greater than the version number of the function itself.</span></span> <span data-ttu-id="923e1-109">いずれかを使用して、 [icordebugfunction 2::getversionnumber](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction2-getversionnumber-method.md)メソッドまたは[icordebugcode::getversionnumber](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getversionnumber-method.md)関数のバージョン番号を取得します。</span><span class="sxs-lookup"><span data-stu-id="923e1-109">Use either the [ICorDebugFunction2::GetVersionNumber](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction2-getversionnumber-method.md) method or the [ICorDebugCode::GetVersionNumber](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getversionnumber-method.md) method to retrieve the version number of the function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="923e1-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="923e1-110">Requirements</span></span>  
 <span data-ttu-id="923e1-111">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="923e1-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="923e1-112">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="923e1-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="923e1-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="923e1-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="923e1-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="923e1-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
