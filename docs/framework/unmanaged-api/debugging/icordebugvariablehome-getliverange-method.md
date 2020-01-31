---
title: 'いい変数 Home:: GetLiveRange メソッド'
ms.date: 03/30/2017
api_name:
- ICorDebugVariableHome.GetLiveRange
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHome::GetLiveRange
helpviewer_keywords:
- ICorDebugVariableHome::GetLiveRange method [.NET Framework debugging]
- GetLiveRange method, ICorDebugVariableFrame interface [.NET Framework debugging]
ms.assetid: 87277e1a-1595-4729-9e25-d1c3ac18ce5f
topic_type:
- apiref
ms.openlocfilehash: 28e41106ffcaf1ed2ed87166e641bb5e5f447e47
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791026"
---
# <a name="icordebugvariablehomegetliverange-method"></a><span data-ttu-id="072e5-102">いい変数 Home:: GetLiveRange メソッド</span><span class="sxs-lookup"><span data-stu-id="072e5-102">IcorDebugVariableHome::GetLiveRange Method</span></span>
<span data-ttu-id="072e5-103">この変数がライブであるネイティブ範囲を取得します。</span><span class="sxs-lookup"><span data-stu-id="072e5-103">Gets the native range over which this variable is live.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="072e5-104">構文</span><span class="sxs-lookup"><span data-stu-id="072e5-104">Syntax</span></span>  
  
```cpp  
HRESULT GetLiveRange(  
    [out] ULONG32* pStartOffset,  
    [out] ULONG32 *pEndOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="072e5-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="072e5-105">Parameters</span></span>  
 `pStartOffset`  
 <span data-ttu-id="072e5-106">入出力変数が最初にライブになる論理オフセット。</span><span class="sxs-lookup"><span data-stu-id="072e5-106">[out] The logical offset at which the variable is first live.</span></span>  
  
 `pEndOffset`  
 <span data-ttu-id="072e5-107">入出力変数が最後にライブになる位置の直後の論理オフセット。</span><span class="sxs-lookup"><span data-stu-id="072e5-107">[out] The logical offset immediately after the point at which the variable is last live.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="072e5-108">要件</span><span class="sxs-lookup"><span data-stu-id="072e5-108">Requirements</span></span>  
 <span data-ttu-id="072e5-109">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="072e5-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="072e5-110">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="072e5-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="072e5-111">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="072e5-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="072e5-112">**.NET Framework のバージョン:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="072e5-112">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="072e5-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="072e5-113">See also</span></span>

- [<span data-ttu-id="072e5-114">ICorDebugVariableHome インターフェイス</span><span class="sxs-lookup"><span data-stu-id="072e5-114">ICorDebugVariableHome Interface</span></span>](icordebugvariablehome-interface.md)
