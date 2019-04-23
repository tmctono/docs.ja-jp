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
ms.openlocfilehash: 7fa90aff73d94baf2cbf7d01f41710cb2aa10213
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59178738"
---
# <a name="icordebugthreadgetobject-method"></a><span data-ttu-id="0084d-102">ICorDebugThread::GetObject メソッド</span><span class="sxs-lookup"><span data-stu-id="0084d-102">ICorDebugThread::GetObject Method</span></span>
<span data-ttu-id="0084d-103">共通言語ランタイム (CLR) スレッドにインターフェイス ポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="0084d-103">Gets an interface pointer to the common language runtime (CLR) thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0084d-104">構文</span><span class="sxs-lookup"><span data-stu-id="0084d-104">Syntax</span></span>  
  
```  
HRESULT GetObject (  
    [out] ICorDebugValue   **ppObject  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0084d-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="0084d-105">Parameters</span></span>  
 `ppObject`  
 <span data-ttu-id="0084d-106">[out]CLR スレッドを表す ICorDebugValue インターフェイス オブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="0084d-106">[out] A pointer to the address of an ICorDebugValue interface object that represents the CLR thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0084d-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="0084d-107">Requirements</span></span>  
 <span data-ttu-id="0084d-108">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="0084d-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0084d-109">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0084d-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0084d-110">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0084d-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0084d-111">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0084d-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0084d-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="0084d-112">See also</span></span>

- <xref:System.Threading.Thread>
