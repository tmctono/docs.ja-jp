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
ms.openlocfilehash: 89f45208550d49f214e763728ddc9eb1bfcd9800
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73088975"
---
# <a name="icordebugappdomain3getcachedwinrttypes-method"></a><span data-ttu-id="96d68-102">ICorDebugAppDomain3::GetCachedWinRTTypes メソッド</span><span class="sxs-lookup"><span data-stu-id="96d68-102">ICorDebugAppDomain3::GetCachedWinRTTypes Method</span></span>
<span data-ttu-id="96d68-103">キャッシュされているすべての Windows ランタイム型の列挙子を取得します。</span><span class="sxs-lookup"><span data-stu-id="96d68-103">Gets an enumerator for all cached Windows Runtime types.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="96d68-104">構文</span><span class="sxs-lookup"><span data-stu-id="96d68-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCachedWinRTTypes (   
    [out] ICorDebugGuidToTypeEnum **ppGuidToTypeEnum)  
;  
```  
  
## <a name="parameters"></a><span data-ttu-id="96d68-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="96d68-105">Parameters</span></span>  
 `ppGuidToTypeEnum`  
 <span data-ttu-id="96d68-106">入出力アプリケーションドメインに現在読み込まれている Windows ランタイム型のマネージ表現を列挙できる、コードの種類が表示され[たインターフェイスオブジェクト](../../../../docs/framework/unmanaged-api/debugging/icordebugguidtotypeenum-interface.md)へのポインター。</span><span class="sxs-lookup"><span data-stu-id="96d68-106">[out] A pointer to an [ICorDebugGuidToTypeEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugguidtotypeenum-interface.md) interface object that can enumerate the managed representations of Windows Runtime types currently loaded in the application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="96d68-107">［要件］</span><span class="sxs-lookup"><span data-stu-id="96d68-107">Requirements</span></span>  
 <span data-ttu-id="96d68-108">**プラットフォーム:** Windows ランタイム</span><span class="sxs-lookup"><span data-stu-id="96d68-108">**Platforms:** Windows Runtime</span></span>  
  
 <span data-ttu-id="96d68-109">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="96d68-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="96d68-110">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="96d68-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="96d68-111">**.NET Framework のバージョン:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="96d68-111">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96d68-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="96d68-112">See also</span></span>

- [<span data-ttu-id="96d68-113">ICorDebugAppDomain3 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="96d68-113">ICorDebugAppDomain3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-interface.md)
