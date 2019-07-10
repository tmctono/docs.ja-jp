---
title: ICorDebug::EnumerateProcesses メソッド
ms.date: 03/30/2017
api_name:
- ICorDebug.EnumerateProcesses
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- EnumerateProcesses
helpviewer_keywords:
- EnumerateProcesses method [.NET Framework debugging]
- ICorDebug::EnumerateProcesses method [.NET Framework debugging]
ms.assetid: ba25d166-1d28-4f1d-aca2-de298bbca669
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e1a4da6df58c928582a830ef92d286437cb5003c
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67738219"
---
# <a name="icordebugenumerateprocesses-method"></a><span data-ttu-id="5a495-102">ICorDebug::EnumerateProcesses メソッド</span><span class="sxs-lookup"><span data-stu-id="5a495-102">ICorDebug::EnumerateProcesses Method</span></span>
<span data-ttu-id="5a495-103">デバッグ中のプロセスの列挙子を取得します。</span><span class="sxs-lookup"><span data-stu-id="5a495-103">Gets an enumerator for the processes that are being debugged.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5a495-104">構文</span><span class="sxs-lookup"><span data-stu-id="5a495-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateProcesses (  
    [out] ICorDebugProcessEnum      **ppProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5a495-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="5a495-105">Parameters</span></span>  
 `ppProcess`  
 <span data-ttu-id="5a495-106">デバッグ中のプロセスの列挙子である ICorDebugProcessEnum オブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="5a495-106">A pointer to the address of an ICorDebugProcessEnum object that is the enumerator for the processes being debugged.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5a495-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="5a495-107">Requirements</span></span>  
 <span data-ttu-id="5a495-108">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5a495-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5a495-109">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5a495-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5a495-110">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5a495-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5a495-111">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5a495-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a495-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="5a495-112">See also</span></span>

- [<span data-ttu-id="5a495-113">ICorDebug インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5a495-113">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
