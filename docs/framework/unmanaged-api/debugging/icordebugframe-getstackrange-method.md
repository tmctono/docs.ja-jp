---
title: ICorDebugFrame::GetStackRange メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugFrame.GetStackRange
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrame::GetStackRange
helpviewer_keywords:
- GetStackRange method, ICorDebugFrame interface [.NET Framework debugging]
- ICorDebugFrame::GetStackRange method [.NET Framework debugging]
ms.assetid: fab037cb-fda6-40fb-9367-921e435dd5a0
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 43532888d181adcb7a7e3760f2a5e3d8f664a35c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61995814"
---
# <a name="icordebugframegetstackrange-method"></a><span data-ttu-id="59857-102">ICorDebugFrame::GetStackRange メソッド</span><span class="sxs-lookup"><span data-stu-id="59857-102">ICorDebugFrame::GetStackRange Method</span></span>
<span data-ttu-id="59857-103">このスタック フレームの絶対アドレスの範囲を取得します。</span><span class="sxs-lookup"><span data-stu-id="59857-103">Gets the absolute address range of this stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="59857-104">構文</span><span class="sxs-lookup"><span data-stu-id="59857-104">Syntax</span></span>  
  
```  
HRESULT GetStackRange (  
    [out] CORDB_ADDRESS      *pStart,   
    [out] CORDB_ADDRESS      *pEnd  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="59857-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="59857-105">Parameters</span></span>  
 `pStart`  
 <span data-ttu-id="59857-106">[out]ポインターを`CORDB_ADDRESS`これによって表されるスタック フレームの開始アドレスを指定する`ICorDebugFrame`オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="59857-106">[out] A pointer to a `CORDB_ADDRESS` that specifies the starting address of the stack frame represented by this `ICorDebugFrame` object.</span></span>  
  
 `pEnd`  
 <span data-ttu-id="59857-107">[out]ポインターを`CORDB_ADDRESS`これによって表されるスタック フレームの終了アドレスを指定する`ICorDebugFrame`オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="59857-107">[out] A pointer to a `CORDB_ADDRESS` that specifies the ending address of the stack frame represented by this `ICorDebugFrame` object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="59857-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="59857-108">Remarks</span></span>  
 <span data-ttu-id="59857-109">スタックのアドレス範囲は、複数のデバッグ エンジンから収集されたスタック トレースをつなぎ合わせた適しています。</span><span class="sxs-lookup"><span data-stu-id="59857-109">The address range of the stack is useful for piecing together interleaved stack traces gathered from multiple debugging engines.</span></span> <span data-ttu-id="59857-110">数値の範囲には、スタック フレームの内容に関する情報は含まれません。</span><span class="sxs-lookup"><span data-stu-id="59857-110">The numeric range provides no information about the contents of the stack frame.</span></span> <span data-ttu-id="59857-111">スタック フレームの場所の比較だけに有効になります。</span><span class="sxs-lookup"><span data-stu-id="59857-111">It is meaningful only for comparison of stack frame locations.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="59857-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="59857-112">Requirements</span></span>  
 <span data-ttu-id="59857-113">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="59857-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="59857-114">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="59857-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="59857-115">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="59857-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="59857-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="59857-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
