---
title: ICorDebugThread::GetObject メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugThread.GetObject
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetObject
helpviewer_keywords:
- GetObject method, ICorDebugThread interface [.NET Framework debugging]
- ICorDebugThread::GetObject method [.NET Framework debugging]
ms.assetid: 1590febe-96c2-4046-97db-d81d81d67e01
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4cd5a7696e7630b21c8bdfa7e4d2f902d6f36995
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57490256"
---
# <a name="icordebugthreadgetobject-method"></a><span data-ttu-id="68d44-102">ICorDebugThread::GetObject メソッド</span><span class="sxs-lookup"><span data-stu-id="68d44-102">ICorDebugThread::GetObject Method</span></span>
<span data-ttu-id="68d44-103">共通言語ランタイム (CLR) スレッドにインターフェイス ポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="68d44-103">Gets an interface pointer to the common language runtime (CLR) thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="68d44-104">構文</span><span class="sxs-lookup"><span data-stu-id="68d44-104">Syntax</span></span>  
  
```  
HRESULT GetObject (  
    [out] ICorDebugValue   **ppObject  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="68d44-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="68d44-105">Parameters</span></span>  
 `ppObject`  
 <span data-ttu-id="68d44-106">[out]CLR スレッドを表す ICorDebugValue インターフェイス オブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="68d44-106">[out] A pointer to the address of an ICorDebugValue interface object that represents the CLR thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="68d44-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="68d44-107">Requirements</span></span>  
 <span data-ttu-id="68d44-108">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="68d44-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="68d44-109">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="68d44-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="68d44-110">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="68d44-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="68d44-111">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="68d44-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68d44-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="68d44-112">See also</span></span>
- <xref:System.Threading.Thread>
