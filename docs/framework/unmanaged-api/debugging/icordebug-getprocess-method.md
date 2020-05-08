---
title: ICorDebug::GetProcess メソッド
ms.date: 03/30/2017
api_name:
- ICorDebug.GetProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebug::GetProcess
helpviewer_keywords:
- GetProcess method, ICorDebug interface [.NET Framework debugging]
- ICorDebug::GetProcess method [.NET Framework debugging]
ms.assetid: 10a40ba0-1b65-4721-bd11-cf12d57b280d
topic_type:
- apiref
ms.openlocfilehash: 59afc8ae7d66e81e4dca3923f9c6f7ff3a3a6605
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2020
ms.locfileid: "82895384"
---
# <a name="icordebuggetprocess-method"></a><span data-ttu-id="e4650-102">ICorDebug::GetProcess メソッド</span><span class="sxs-lookup"><span data-stu-id="e4650-102">ICorDebug::GetProcess Method</span></span>
<span data-ttu-id="e4650-103">指定されたプロセスの "いいプロセス" インスタンスへのポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="e4650-103">Gets a pointer to the "ICorDebugProcess" instance for the specified process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e4650-104">構文</span><span class="sxs-lookup"><span data-stu-id="e4650-104">Syntax</span></span>  
  
```cpp  
HRESULT GetProcess (  
    [in] DWORD               dwProcessId,  
    [out] ICorDebugProcess   **ppProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e4650-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e4650-105">Parameters</span></span>  
 `dwProcessId`  
 <span data-ttu-id="e4650-106">からプロセスの ID。</span><span class="sxs-lookup"><span data-stu-id="e4650-106">[in] The ID of the process.</span></span>  
  
 `ppProcess`  
 <span data-ttu-id="e4650-107">入出力指定されたプロセスの`ICorDebugProcess`インスタンスのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="e4650-107">[out] A pointer to the address of a `ICorDebugProcess` instance for the specified process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e4650-108">必要条件</span><span class="sxs-lookup"><span data-stu-id="e4650-108">Requirements</span></span>  
 <span data-ttu-id="e4650-109">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e4650-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e4650-110">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e4650-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e4650-111">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e4650-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e4650-112">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e4650-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4650-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="e4650-113">See also</span></span>

- [<span data-ttu-id="e4650-114">ICorDebug インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e4650-114">ICorDebug Interface</span></span>](icordebug-interface.md)
