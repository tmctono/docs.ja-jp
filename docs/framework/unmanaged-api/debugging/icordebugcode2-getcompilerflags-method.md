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
ms.openlocfilehash: 1605ee92c8743606ff0e958f112a2d90af43e03a
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2019
ms.locfileid: "71700717"
---
# <a name="icordebugcode2getcompilerflags-method"></a><span data-ttu-id="8c945-102">ICorDebugCode2::GetCompilerFlags メソッド</span><span class="sxs-lookup"><span data-stu-id="8c945-102">ICorDebugCode2::GetCompilerFlags Method</span></span>

<span data-ttu-id="8c945-103">このコード オブジェクトが Just-In-Time (JIT) コンパイルされたとき、またはネイティブ イメージ ジェネレーター (Ngen.exe) を使用して生成されたときの条件を指定するフラグを取得します。</span><span class="sxs-lookup"><span data-stu-id="8c945-103">Gets the flags that specify the conditions under which this code object was either just-in-time (JIT) compiled or generated using the native image generator (Ngen.exe).</span></span>

## <a name="syntax"></a><span data-ttu-id="8c945-104">構文</span><span class="sxs-lookup"><span data-stu-id="8c945-104">Syntax</span></span>

```cpp
HRESULT GetCompilerFlags (
    [out] DWORD *pdwFlags
);
```

## <a name="parameters"></a><span data-ttu-id="8c945-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="8c945-105">Parameters</span></span>

 `pdwFlags`  
 <span data-ttu-id="8c945-106">入出力JIT コンパイラまたはネイティブイメージジェネレーターの動作を指定する[CorDebugJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md)列挙値へのポインター。</span><span class="sxs-lookup"><span data-stu-id="8c945-106">[out] A pointer to a value of the [CorDebugJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md) enumeration that specifies the behavior of the JIT compiler or the native image generator.</span></span>

## <a name="requirements"></a><span data-ttu-id="8c945-107">要件</span><span class="sxs-lookup"><span data-stu-id="8c945-107">Requirements</span></span>

 <span data-ttu-id="8c945-108">**・** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8c945-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

 <span data-ttu-id="8c945-109">**ヘッダー:** CorDebug .idl、CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="8c945-109">**Header:** CorDebug.idl, CorDebug.h</span></span>

 <span data-ttu-id="8c945-110">**ライブラリ**CorGuids .lib</span><span class="sxs-lookup"><span data-stu-id="8c945-110">**Library:** CorGuids.lib</span></span>

 <span data-ttu-id="8c945-111">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8c945-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
 
