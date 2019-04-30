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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 77f4e745e4bd45be51b497fdd5bab95cd24c9685
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61994813"
---
# <a name="icordebugmodule2getjitcompilerflags-method"></a><span data-ttu-id="11958-102">ICorDebugModule2::GetJITCompilerFlags メソッド</span><span class="sxs-lookup"><span data-stu-id="11958-102">ICorDebugModule2::GetJITCompilerFlags Method</span></span>
<span data-ttu-id="11958-103">この ICorDebugModule2 の・ イン タイム (JIT) コンパイルを制御するフラグを取得します。</span><span class="sxs-lookup"><span data-stu-id="11958-103">Gets the flags that control the just-in-time (JIT) compilation of this ICorDebugModule2.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="11958-104">構文</span><span class="sxs-lookup"><span data-stu-id="11958-104">Syntax</span></span>  
  
```  
HRESULT GetJITCompilerFlags (  
    [out] DWORD   *pdwFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="11958-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="11958-105">Parameters</span></span>  
 `pdwFlags`  
 <span data-ttu-id="11958-106">[out]値へのポインター、 [CorDebugJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md) JIT コンパイルを制御する列挙体。</span><span class="sxs-lookup"><span data-stu-id="11958-106">[out] A pointer to a value of the [CorDebugJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md) enumeration that controls the JIT compilation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="11958-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="11958-107">Requirements</span></span>  
 <span data-ttu-id="11958-108">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="11958-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="11958-109">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="11958-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="11958-110">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="11958-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="11958-111">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="11958-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
