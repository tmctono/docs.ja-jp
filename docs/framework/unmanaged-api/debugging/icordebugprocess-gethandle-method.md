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
ms.openlocfilehash: ed7110cb2e2b7a91ed81d2d81c2989d1733c1ee6
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/12/2020
ms.locfileid: "83207313"
---
# <a name="icordebugprocessgethandle-method"></a><span data-ttu-id="54e58-102">ICorDebugProcess::GetHandle メソッド</span><span class="sxs-lookup"><span data-stu-id="54e58-102">ICorDebugProcess::GetHandle Method</span></span>
<span data-ttu-id="54e58-103">プロセスを処理するハンドルを取得します。</span><span class="sxs-lookup"><span data-stu-id="54e58-103">Gets a handle to the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="54e58-104">構文</span><span class="sxs-lookup"><span data-stu-id="54e58-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHandle([out] HPROCESS *phProcessHandle);  
```  
  
## <a name="parameters"></a><span data-ttu-id="54e58-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="54e58-105">Parameters</span></span>  
 `phProcessHandle`  
 <span data-ttu-id="54e58-106">入出力プロセスを指すハンドルであるへのポインター `HPROCESS` 。</span><span class="sxs-lookup"><span data-stu-id="54e58-106">[out] A pointer to an `HPROCESS` that is the handle to the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="54e58-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="54e58-107">Remarks</span></span>  
 <span data-ttu-id="54e58-108">取得したハンドルは、デバッグインターフェイスによって所有されています。</span><span class="sxs-lookup"><span data-stu-id="54e58-108">The retrieved handle is owned by the debugging interface.</span></span> <span data-ttu-id="54e58-109">デバッガーは、使用する前にハンドルを複製する必要があります。</span><span class="sxs-lookup"><span data-stu-id="54e58-109">The debugger should duplicate the handle before using it.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="54e58-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="54e58-110">Requirements</span></span>  
 <span data-ttu-id="54e58-111">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="54e58-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="54e58-112">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="54e58-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="54e58-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="54e58-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="54e58-114">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="54e58-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
