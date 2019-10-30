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
ms.openlocfilehash: d948fda048e724ad11c59bf7d4776ee2ca6c8d58
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125553"
---
# <a name="icordebugcode2getcompilerflags-method"></a><span data-ttu-id="31be9-102">ICorDebugCode2::GetCompilerFlags メソッド</span><span class="sxs-lookup"><span data-stu-id="31be9-102">ICorDebugCode2::GetCompilerFlags Method</span></span>

<span data-ttu-id="31be9-103">このコード オブジェクトが Just-In-Time (JIT) コンパイルされたとき、またはネイティブ イメージ ジェネレーター (Ngen.exe) を使用して生成されたときの条件を指定するフラグを取得します。</span><span class="sxs-lookup"><span data-stu-id="31be9-103">Gets the flags that specify the conditions under which this code object was either just-in-time (JIT) compiled or generated using the native image generator (Ngen.exe).</span></span>

## <a name="syntax"></a><span data-ttu-id="31be9-104">構文</span><span class="sxs-lookup"><span data-stu-id="31be9-104">Syntax</span></span>

```cpp
HRESULT GetCompilerFlags (
    [out] DWORD *pdwFlags
);
```

## <a name="parameters"></a><span data-ttu-id="31be9-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="31be9-105">Parameters</span></span>

`pdwFlags`  
<span data-ttu-id="31be9-106">入出力JIT コンパイラまたはネイティブイメージジェネレーターの動作を指定する[CorDebugJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md)列挙値へのポインター。</span><span class="sxs-lookup"><span data-stu-id="31be9-106">[out] A pointer to a value of the [CorDebugJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md) enumeration that specifies the behavior of the JIT compiler or the native image generator.</span></span>

## <a name="requirements"></a><span data-ttu-id="31be9-107">［要件］</span><span class="sxs-lookup"><span data-stu-id="31be9-107">Requirements</span></span>

<span data-ttu-id="31be9-108">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="31be9-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="31be9-109">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="31be9-109">**Header:** CorDebug.idl, CorDebug.h</span></span>

<span data-ttu-id="31be9-110">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="31be9-110">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="31be9-111">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="31be9-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
