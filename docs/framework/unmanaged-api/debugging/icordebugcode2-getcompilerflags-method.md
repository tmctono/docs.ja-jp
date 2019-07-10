---
title: ICorDebugCode2::GetCompilerFlags メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugCode2.GetCompilerFlags
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode2::GetCompilerFlags
helpviewer_keywords:
- GetCompilerFlags method [.NET Framework debugging]
- ICorDebugCode2::GetCompilerFlags method [.NET Framework debugging]
ms.assetid: 532e9dfd-d114-4c75-b952-1accce102643
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 95ba19ae908dbf37052c0a74ef8f99090f3313ba
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67748568"
---
# <a name="icordebugcode2getcompilerflags-method"></a><span data-ttu-id="06818-102">ICorDebugCode2::GetCompilerFlags メソッド</span><span class="sxs-lookup"><span data-stu-id="06818-102">ICorDebugCode2::GetCompilerFlags Method</span></span>
<span data-ttu-id="06818-103">このコード オブジェクトが Just-In-Time (JIT) コンパイルされたとき、またはネイティブ イメージ ジェネレーター (Ngen.exe) を使用して生成されたときの条件を指定するフラグを取得します。</span><span class="sxs-lookup"><span data-stu-id="06818-103">Gets the flags that specify the conditions under which this code object was either just-in-time (JIT) compiled or generated using the native image generator (Ngen.exe).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="06818-104">構文</span><span class="sxs-lookup"><span data-stu-id="06818-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCompilerFlags (  
    [out] DWORD *pdwFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="06818-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="06818-105">Parameters</span></span>  
 `pdwFlags`  
 <span data-ttu-id="06818-106">[out]値へのポインター、 [CorDebugJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md) JIT コンパイラまたはネイティブ イメージ ジェネレーターの動作を指定する列挙体。</span><span class="sxs-lookup"><span data-stu-id="06818-106">[out] A pointer to a value of the [CorDebugJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md) enumeration that specifies the behavior of the JIT compiler or the native image generator.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="06818-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="06818-107">Requirements</span></span>  
 <span data-ttu-id="06818-108">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="06818-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="06818-109">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="06818-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="06818-110">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="06818-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="06818-111">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="06818-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06818-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="06818-112">See also</span></span>
