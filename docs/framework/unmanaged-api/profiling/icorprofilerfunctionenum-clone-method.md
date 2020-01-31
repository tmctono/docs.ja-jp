---
title: ICorProfilerFunctionEnum::Clone メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerFunctionEnum.Clone Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerFunctionEnum::Clone
helpviewer_keywords:
- ICorProfilerFunctionEnum::Clone method [.NET Framework profiling]
- Clone method, ICorProfilerFunctionEnum interface [.NET Framework profiling]
ms.assetid: 0c3d4835-e111-4e82-af6d-53f140b8f2c9
topic_type:
- apiref
ms.openlocfilehash: 2faa7185202b46e77e501d69bb471391a7c6eb68
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2020
ms.locfileid: "76864623"
---
# <a name="icorprofilerfunctionenumclone-method"></a><span data-ttu-id="0e966-102">ICorProfilerFunctionEnum::Clone メソッド</span><span class="sxs-lookup"><span data-stu-id="0e966-102">ICorProfilerFunctionEnum::Clone Method</span></span>
<span data-ttu-id="0e966-103">この[ICorProfilerFunctionEnum](icorprofilerfunctionenum-interface.md)インターフェイスのコピーへのインターフェイスポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="0e966-103">Gets an interface pointer to a copy of this [ICorProfilerFunctionEnum](icorprofilerfunctionenum-interface.md) interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0e966-104">構文</span><span class="sxs-lookup"><span data-stu-id="0e966-104">Syntax</span></span>  
  
```cpp  
HRESULT Clone([out] ICorProfilerFunctionEnum **ppEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0e966-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="0e966-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="0e966-106">入出力インターフェイスポインターへのポインター。これにより、この[ICorProfilerFunctionEnum](icorprofilerfunctionenum-interface.md)インターフェイスのコピーが参照されます。</span><span class="sxs-lookup"><span data-stu-id="0e966-106">[out] A pointer to the interface pointer, which, in turn, points to the copy of this [ICorProfilerFunctionEnum](icorprofilerfunctionenum-interface.md) interface.</span></span> <span data-ttu-id="0e966-107">列挙子のコピーは、この列挙子とは別に独自の列挙状態を保持します。</span><span class="sxs-lookup"><span data-stu-id="0e966-107">The copy of the enumerator maintains its own enumeration state separately from this enumerator.</span></span> <span data-ttu-id="0e966-108">ただし、コピーの初期カーソル位置は、この列挙子の現在のカーソル位置と同じです。</span><span class="sxs-lookup"><span data-stu-id="0e966-108">However, the copy's initial cursor position is the same as this enumerator's current cursor position.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0e966-109">要件</span><span class="sxs-lookup"><span data-stu-id="0e966-109">Requirements</span></span>  
 <span data-ttu-id="0e966-110">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0e966-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0e966-111">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="0e966-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="0e966-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0e966-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0e966-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0e966-113">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e966-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="0e966-114">See also</span></span>

- [<span data-ttu-id="0e966-115">ICorProfilerFunctionEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="0e966-115">ICorProfilerFunctionEnum Interface</span></span>](icorprofilerfunctionenum-interface.md)
- [<span data-ttu-id="0e966-116">プロファイリングのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="0e966-116">Profiling Interfaces</span></span>](profiling-interfaces.md)
