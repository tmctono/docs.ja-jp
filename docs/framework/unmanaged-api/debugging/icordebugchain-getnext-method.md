---
title: ICorDebugChain::GetNext メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugChain.GetNext
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain::GetNext
helpviewer_keywords:
- GetNext method [.NET Framework debugging]
- ICorDebugChain::GetNext method [.NET Framework debugging]
ms.assetid: 8d9744a5-e08b-4ab2-9855-5c22711cc1e6
topic_type:
- apiref
ms.openlocfilehash: 47a90ed63ae217cb150f392ad9196f8d0d5764e3
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2020
ms.locfileid: "82894641"
---
# <a name="icordebugchaingetnext-method"></a><span data-ttu-id="151d0-102">ICorDebugChain::GetNext メソッド</span><span class="sxs-lookup"><span data-stu-id="151d0-102">ICorDebugChain::GetNext Method</span></span>
<span data-ttu-id="151d0-103">スレッドの次のフレームのチェーンを取得します。</span><span class="sxs-lookup"><span data-stu-id="151d0-103">Gets the next chain of frames for the thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="151d0-104">構文</span><span class="sxs-lookup"><span data-stu-id="151d0-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNext (  
    [out] ICorDebugChain     **ppChain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="151d0-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="151d0-105">Parameters</span></span>  
 `ppChain`  
 <span data-ttu-id="151d0-106">入出力スレッドの次のフレームのチェーンを表す、テキストチェーンオブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="151d0-106">[out] A pointer to the address of an ICorDebugChain object that represents the next chain of frames for the thread.</span></span> <span data-ttu-id="151d0-107">このチェーンが最後のチェーンの場合`ppChain` 、は null です。</span><span class="sxs-lookup"><span data-stu-id="151d0-107">If this chain is the last chain, `ppChain` is null.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="151d0-108">必要条件</span><span class="sxs-lookup"><span data-stu-id="151d0-108">Requirements</span></span>  
 <span data-ttu-id="151d0-109">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="151d0-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="151d0-110">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="151d0-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="151d0-111">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="151d0-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="151d0-112">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="151d0-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
