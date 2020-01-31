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
ms.openlocfilehash: 55d0b40bbdb5628f60090d9d70f7dccbebe9d58f
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76784995"
---
# <a name="icordebugappdomain3getcachedwinrttypes-method"></a><span data-ttu-id="d7f49-102">ICorDebugAppDomain3::GetCachedWinRTTypes メソッド</span><span class="sxs-lookup"><span data-stu-id="d7f49-102">ICorDebugAppDomain3::GetCachedWinRTTypes Method</span></span>
<span data-ttu-id="d7f49-103">キャッシュされているすべての Windows ランタイム型の列挙子を取得します。</span><span class="sxs-lookup"><span data-stu-id="d7f49-103">Gets an enumerator for all cached Windows Runtime types.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d7f49-104">構文</span><span class="sxs-lookup"><span data-stu-id="d7f49-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCachedWinRTTypes (   
    [out] ICorDebugGuidToTypeEnum **ppGuidToTypeEnum)  
;  
```  
  
## <a name="parameters"></a><span data-ttu-id="d7f49-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d7f49-105">Parameters</span></span>  
 `ppGuidToTypeEnum`  
 <span data-ttu-id="d7f49-106">入出力アプリケーションドメインに現在読み込まれている Windows ランタイム型のマネージ表現を列挙できる、コードの種類が表示され[たインターフェイスオブジェクト](icordebugguidtotypeenum-interface.md)へのポインター。</span><span class="sxs-lookup"><span data-stu-id="d7f49-106">[out] A pointer to an [ICorDebugGuidToTypeEnum](icordebugguidtotypeenum-interface.md) interface object that can enumerate the managed representations of Windows Runtime types currently loaded in the application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d7f49-107">要件</span><span class="sxs-lookup"><span data-stu-id="d7f49-107">Requirements</span></span>  
 <span data-ttu-id="d7f49-108">**プラットフォーム:** Windows ランタイム</span><span class="sxs-lookup"><span data-stu-id="d7f49-108">**Platforms:** Windows Runtime</span></span>  
  
 <span data-ttu-id="d7f49-109">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d7f49-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d7f49-110">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d7f49-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d7f49-111">**.NET Framework のバージョン:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d7f49-111">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7f49-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="d7f49-112">See also</span></span>

- [<span data-ttu-id="d7f49-113">ICorDebugAppDomain3 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d7f49-113">ICorDebugAppDomain3 Interface</span></span>](icordebugappdomain3-interface.md)
