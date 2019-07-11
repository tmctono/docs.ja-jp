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
ms.openlocfilehash: 3695f150797e6a59a2fb1d58c99f233a35d687ce
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67771839"
---
# <a name="icordebugthreadgetobject-method"></a><span data-ttu-id="6a059-102">ICorDebugThread::GetObject メソッド</span><span class="sxs-lookup"><span data-stu-id="6a059-102">ICorDebugThread::GetObject Method</span></span>
<span data-ttu-id="6a059-103">共通言語ランタイム (CLR) スレッドにインターフェイス ポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="6a059-103">Gets an interface pointer to the common language runtime (CLR) thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6a059-104">構文</span><span class="sxs-lookup"><span data-stu-id="6a059-104">Syntax</span></span>  
  
```cpp  
HRESULT GetObject (  
    [out] ICorDebugValue   **ppObject  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6a059-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="6a059-105">Parameters</span></span>  
 `ppObject`  
 <span data-ttu-id="6a059-106">[out]CLR スレッドを表す ICorDebugValue インターフェイス オブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="6a059-106">[out] A pointer to the address of an ICorDebugValue interface object that represents the CLR thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6a059-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="6a059-107">Requirements</span></span>  
 <span data-ttu-id="6a059-108">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6a059-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6a059-109">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6a059-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6a059-110">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6a059-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6a059-111">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6a059-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a059-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="6a059-112">See also</span></span>

- <xref:System.Threading.Thread>
