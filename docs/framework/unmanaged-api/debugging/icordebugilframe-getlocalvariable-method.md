---
title: ICorDebugILFrame::GetLocalVariable メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame.GetLocalVariable
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame::GetLocalVariable
helpviewer_keywords:
- ICorDebugILFrame::GetLocalVariable method [.NET Framework debugging]
- GetLocalVariable method [.NET Framework debugging]
ms.assetid: c8706356-d50b-4f87-a40c-39c3b7f4fd38
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 29fc1b491aa4e340c3d8ad6f761d0d6d901649ac
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67758554"
---
# <a name="icordebugilframegetlocalvariable-method"></a><span data-ttu-id="7afb2-102">ICorDebugILFrame::GetLocalVariable メソッド</span><span class="sxs-lookup"><span data-stu-id="7afb2-102">ICorDebugILFrame::GetLocalVariable Method</span></span>
<span data-ttu-id="7afb2-103">この Microsoft intermediate language (MSIL) のスタック フレーム内には、指定されたローカル変数の値を取得します。</span><span class="sxs-lookup"><span data-stu-id="7afb2-103">Gets the value of the specified local variable in this Microsoft intermediate language (MSIL) stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7afb2-104">構文</span><span class="sxs-lookup"><span data-stu-id="7afb2-104">Syntax</span></span>  
  
```cpp  
HRESULT GetLocalVariable (  
    [in] DWORD                  dwIndex,  
    [out] ICorDebugValue        **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7afb2-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="7afb2-105">Parameters</span></span>  
 `dwIndex`  
 <span data-ttu-id="7afb2-106">[in]この MSIL のスタック フレームでローカル変数のインデックス。</span><span class="sxs-lookup"><span data-stu-id="7afb2-106">[in] The index of the local variable in this MSIL stack frame.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="7afb2-107">[out]取得した値を表す ICorDebugValue オブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="7afb2-107">[out] A pointer to the address of an ICorDebugValue object that represents the retrieved value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7afb2-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="7afb2-108">Remarks</span></span>  
 <span data-ttu-id="7afb2-109">`GetLocalVariable` MSIL のスタック フレームまたは・ イン タイム (JIT) コンパイル済みのフレームで、メソッドを使用できます。</span><span class="sxs-lookup"><span data-stu-id="7afb2-109">The `GetLocalVariable` method can be used either in an MSIL stack frame or in a just-in-time (JIT) compiled frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7afb2-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="7afb2-110">Requirements</span></span>  
 <span data-ttu-id="7afb2-111">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="7afb2-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7afb2-112">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7afb2-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7afb2-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7afb2-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7afb2-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7afb2-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
