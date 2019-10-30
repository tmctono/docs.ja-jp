---
title: ICorDebugFrameEnum::Next メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugFrameEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrameEnum::Next
helpviewer_keywords:
- ICorDebugFrameEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugFrameEnum interface [.NET Framework debugging]
ms.assetid: 0bc96acb-6179-4328-a447-cda562ce9e98
topic_type:
- apiref
ms.openlocfilehash: ff74a9849b74b8a8e6b8c03f1fc4e7c7eee1ec14
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124054"
---
# <a name="icordebugframeenumnext-method"></a><span data-ttu-id="6fd96-102">ICorDebugFrameEnum::Next メソッド</span><span class="sxs-lookup"><span data-stu-id="6fd96-102">ICorDebugFrameEnum::Next Method</span></span>
<span data-ttu-id="6fd96-103">現在の位置から開始して、指定された数の表示フレームインスタンスを取得します。</span><span class="sxs-lookup"><span data-stu-id="6fd96-103">Gets the specified number of ICorDebugFrame instances, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6fd96-104">構文</span><span class="sxs-lookup"><span data-stu-id="6fd96-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in] ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugFrame *frames[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6fd96-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="6fd96-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="6fd96-106">から取得する `ICorDebugFrame` インスタンスの数。</span><span class="sxs-lookup"><span data-stu-id="6fd96-106">[in] The number of `ICorDebugFrame` instances to be retrieved.</span></span>  
  
 `frames`  
 <span data-ttu-id="6fd96-107">入出力ポインターの配列。それぞれが `ICorDebugFrame` オブジェクトを指します。</span><span class="sxs-lookup"><span data-stu-id="6fd96-107">[out] An array of pointers, each of which points to an `ICorDebugFrame` object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="6fd96-108">入出力実際に返された `ICorDebugFrame` インスタンスの数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="6fd96-108">[out] A pointer to the number of `ICorDebugFrame` instances actually returned.</span></span> <span data-ttu-id="6fd96-109">`celt` が1の場合、この値は null になります。</span><span class="sxs-lookup"><span data-stu-id="6fd96-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6fd96-110">［要件］</span><span class="sxs-lookup"><span data-stu-id="6fd96-110">Requirements</span></span>  
 <span data-ttu-id="6fd96-111">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6fd96-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6fd96-112">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6fd96-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6fd96-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6fd96-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6fd96-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6fd96-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
