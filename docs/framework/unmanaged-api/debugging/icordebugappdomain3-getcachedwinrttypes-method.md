---
title: ICorDebugAppDomain3::GetCachedWinRTTypes メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain3.GetCachedWinRTTypes
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain3::GetCachedWinRTTypes
helpviewer_keywords:
- ICorDebugAppDomain3::GetCachedWinRTTypes method [.NET Framework debugging]
- GetCachedWinRTTypes method, ICorDebugAppDomain3 interface [.NET Framework debugging]
ms.assetid: 9afd0e04-a403-41e2-9528-a6dcbcdcbd4d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c7e2685d17f3dd32db295f926fc19121d29e1752
ms.sourcegitcommit: 5bc85ad81d96b8dc2a90ce53bada475ee5662c44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/12/2019
ms.locfileid: "67025920"
---
# <a name="icordebugappdomain3getcachedwinrttypes-method"></a><span data-ttu-id="476d9-102">ICorDebugAppDomain3::GetCachedWinRTTypes メソッド</span><span class="sxs-lookup"><span data-stu-id="476d9-102">ICorDebugAppDomain3::GetCachedWinRTTypes Method</span></span>
<span data-ttu-id="476d9-103">キャッシュされたすべての Windows ランタイム型の列挙子を取得します。</span><span class="sxs-lookup"><span data-stu-id="476d9-103">Gets an enumerator for all cached Windows Runtime types.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="476d9-104">構文</span><span class="sxs-lookup"><span data-stu-id="476d9-104">Syntax</span></span>  
  
```  
HRESULT GetCachedWinRTTypes (   
    [out] ICorDebugGuidToTypeEnum **ppGuidToTypeEnum)  
;  
```  
  
## <a name="parameters"></a><span data-ttu-id="476d9-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="476d9-105">Parameters</span></span>  
 `ppGuidToTypeEnum`  
 <span data-ttu-id="476d9-106">[out]ポインター、 [ICorDebugGuidToTypeEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugguidtotypeenum-interface.md)アプリケーション ドメインで現在の Windows ランタイム型のマネージ表現を列挙できるインターフェイス オブジェクトが読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="476d9-106">[out] A pointer to an [ICorDebugGuidToTypeEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugguidtotypeenum-interface.md) interface object that can enumerate the managed representations of Windows Runtime types currently loaded in the application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="476d9-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="476d9-107">Requirements</span></span>  
 <span data-ttu-id="476d9-108">**プラットフォーム:** Windows ランタイム</span><span class="sxs-lookup"><span data-stu-id="476d9-108">**Platforms:** Windows Runtime</span></span>  
  
 <span data-ttu-id="476d9-109">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="476d9-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="476d9-110">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="476d9-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="476d9-111">**.NET Framework のバージョン:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="476d9-111">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="476d9-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="476d9-112">See also</span></span>

- [<span data-ttu-id="476d9-113">ICorDebugAppDomain3 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="476d9-113">ICorDebugAppDomain3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-interface.md)
