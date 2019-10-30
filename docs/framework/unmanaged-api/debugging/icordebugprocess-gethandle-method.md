---
title: ICorDebugProcess::GetHandle メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.GetHandle
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::GetHandle
helpviewer_keywords:
- GetHandle method, ICorDebugProcess interface [.NET Framework debugging]
- ICorDebugProcess::GetHandle method [.NET Framework debugging]
ms.assetid: e7d3ecf5-09d2-4d94-abb6-ff3483deebb6
topic_type:
- apiref
ms.openlocfilehash: e4061580d59b0cf2a6e6e481d5242005e9452caf
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73128869"
---
# <a name="icordebugprocessgethandle-method"></a><span data-ttu-id="2dc16-102">ICorDebugProcess::GetHandle メソッド</span><span class="sxs-lookup"><span data-stu-id="2dc16-102">ICorDebugProcess::GetHandle Method</span></span>
<span data-ttu-id="2dc16-103">プロセスを処理するハンドルを取得します。</span><span class="sxs-lookup"><span data-stu-id="2dc16-103">Gets a handle to the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2dc16-104">構文</span><span class="sxs-lookup"><span data-stu-id="2dc16-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHandle([out] HPROCESS *phProcessHandle);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2dc16-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="2dc16-105">Parameters</span></span>  
 `phProcessHandle`  
 <span data-ttu-id="2dc16-106">入出力プロセスを処理するハンドルである `HPROCESS` へのポインター。</span><span class="sxs-lookup"><span data-stu-id="2dc16-106">[out] A pointer to an `HPROCESS` that is the handle to the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2dc16-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="2dc16-107">Remarks</span></span>  
 <span data-ttu-id="2dc16-108">取得したハンドルは、デバッグインターフェイスによって所有されています。</span><span class="sxs-lookup"><span data-stu-id="2dc16-108">The retrieved handle is owned by the debugging interface.</span></span> <span data-ttu-id="2dc16-109">デバッガーは、使用する前にハンドルを複製する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2dc16-109">The debugger should duplicate the handle before using it.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2dc16-110">［要件］</span><span class="sxs-lookup"><span data-stu-id="2dc16-110">Requirements</span></span>  
 <span data-ttu-id="2dc16-111">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2dc16-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2dc16-112">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2dc16-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2dc16-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2dc16-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2dc16-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2dc16-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
