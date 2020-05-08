---
title: ICorDebugChain::GetStackRange メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugChain.GetStackRange
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain::GetStackRange
helpviewer_keywords:
- ICorDebugChain::GetStackRange method [.NET Framework debugging]
- GetStackRange method, ICorDebugChain interface [.NET Framework debugging]
ms.assetid: 554284e7-3f6c-4d40-8da5-1c9317fbd484
topic_type:
- apiref
ms.openlocfilehash: 40ecc183c32500ad9e88ceb1bfc0528d717430e8
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2020
ms.locfileid: "82894464"
---
# <a name="icordebugchaingetstackrange-method"></a><span data-ttu-id="70839-102">ICorDebugChain::GetStackRange メソッド</span><span class="sxs-lookup"><span data-stu-id="70839-102">ICorDebugChain::GetStackRange Method</span></span>
<span data-ttu-id="70839-103">このチェーンのスタックセグメントのアドレス範囲を取得します。</span><span class="sxs-lookup"><span data-stu-id="70839-103">Gets the address range of the stack segment for this chain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="70839-104">構文</span><span class="sxs-lookup"><span data-stu-id="70839-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStackRange (  
    [out] CORDB_ADDRESS      *pStart,
    [out] CORDB_ADDRESS      *pEnd  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="70839-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="70839-105">Parameters</span></span>  
 `pStart`  
 <span data-ttu-id="70839-106">入出力スタックセグメントの開始`CORDB_ADDRESS`アドレスを示す値へのポインター。</span><span class="sxs-lookup"><span data-stu-id="70839-106">[out] A pointer to a `CORDB_ADDRESS` value that is the starting address of the stack segment.</span></span>  
  
 `pEnd`  
 <span data-ttu-id="70839-107">入出力スタックセグメントの終了`CORDB_ADDRESS`アドレスを示す値へのポインター。</span><span class="sxs-lookup"><span data-stu-id="70839-107">[out] A pointer to a `CORDB_ADDRESS` value that is the ending address of the stack segment.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="70839-108">解説</span><span class="sxs-lookup"><span data-stu-id="70839-108">Remarks</span></span>  
 <span data-ttu-id="70839-109">数値の範囲は、スタックフレームの位置を比較する場合にのみ意味があります。</span><span class="sxs-lookup"><span data-stu-id="70839-109">The numeric range is meaningful only for comparison of stack frame locations.</span></span> <span data-ttu-id="70839-110">実際にスタックに格納されている内容について、想定を行うことはできません。</span><span class="sxs-lookup"><span data-stu-id="70839-110">You cannot make any assumptions about what is actually stored on the stack.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="70839-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="70839-111">Requirements</span></span>  
 <span data-ttu-id="70839-112">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="70839-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="70839-113">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="70839-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="70839-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="70839-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="70839-115">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="70839-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
