---
title: ICorDebugModule2::GetJITCompilerFlags メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugModule2.GetJITCompilerFlags
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule2::GetJITCompilerFlags
helpviewer_keywords:
- GetJITCompilerFlags method [.NET Framework debugging]
- ICorDebugModule2::GetJITCompilerFlags method [.NET Framework debugging]
ms.assetid: 7212d9f4-989b-44e3-b8d4-ffc35922f6a0
topic_type:
- apiref
ms.openlocfilehash: 1216629fc7e1c3e720d5f296b9293b3c4b7f8721
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127891"
---
# <a name="icordebugmodule2getjitcompilerflags-method"></a><span data-ttu-id="1f892-102">ICorDebugModule2::GetJITCompilerFlags メソッド</span><span class="sxs-lookup"><span data-stu-id="1f892-102">ICorDebugModule2::GetJITCompilerFlags Method</span></span>
<span data-ttu-id="1f892-103">この ICorDebugModule2 の just-in-time (JIT) コンパイルを制御するフラグを取得します。</span><span class="sxs-lookup"><span data-stu-id="1f892-103">Gets the flags that control the just-in-time (JIT) compilation of this ICorDebugModule2.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1f892-104">構文</span><span class="sxs-lookup"><span data-stu-id="1f892-104">Syntax</span></span>  
  
```cpp  
HRESULT GetJITCompilerFlags (  
    [out] DWORD   *pdwFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1f892-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="1f892-105">Parameters</span></span>  
 `pdwFlags`  
 <span data-ttu-id="1f892-106">入出力JIT コンパイルを制御する[CorDebugJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md)列挙体の値へのポインター。</span><span class="sxs-lookup"><span data-stu-id="1f892-106">[out] A pointer to a value of the [CorDebugJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md) enumeration that controls the JIT compilation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1f892-107">［要件］</span><span class="sxs-lookup"><span data-stu-id="1f892-107">Requirements</span></span>  
 <span data-ttu-id="1f892-108">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1f892-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1f892-109">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1f892-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1f892-110">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1f892-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1f892-111">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1f892-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
