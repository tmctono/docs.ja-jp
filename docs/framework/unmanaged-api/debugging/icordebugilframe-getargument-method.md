---
title: ICorDebugILFrame::GetArgument メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame.GetArgument
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame::GetArgument
helpviewer_keywords:
- GetArgument method [.NET Framework debugging]
- ICorDebugILFrame::GetArgument method [.NET Framework debugging]
ms.assetid: 4e2fd423-f643-4c27-ba5f-41b5ebc3b416
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 46852ed8ac53c3a7720edff4833f3dc3cce42bbb
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61995528"
---
# <a name="icordebugilframegetargument-method"></a><span data-ttu-id="93132-102">ICorDebugILFrame::GetArgument メソッド</span><span class="sxs-lookup"><span data-stu-id="93132-102">ICorDebugILFrame::GetArgument Method</span></span>
<span data-ttu-id="93132-103">この Microsoft intermediate language (MSIL) のスタック フレーム内には、指定された引数の値を取得します。</span><span class="sxs-lookup"><span data-stu-id="93132-103">Gets the value of the specified argument in this Microsoft intermediate language (MSIL) stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="93132-104">構文</span><span class="sxs-lookup"><span data-stu-id="93132-104">Syntax</span></span>  
  
```  
HRESULT GetArgument (  
    [in] DWORD                  dwIndex,  
    [out] ICorDebugValue        **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="93132-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="93132-105">Parameters</span></span>  
 `dwIndex`  
 <span data-ttu-id="93132-106">[in]この MSIL のスタック フレームの引数のインデックス。</span><span class="sxs-lookup"><span data-stu-id="93132-106">[in] The index of the argument in this MSIL stack frame.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="93132-107">[out]取得した値を表す ICorDebugValue オブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="93132-107">[out] A pointer to the address of an ICorDebugValue object that represents the retrieved value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="93132-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="93132-108">Remarks</span></span>  
 <span data-ttu-id="93132-109">`GetArgument` MSIL のスタック フレームまたは・ イン タイム (JIT) コンパイル済みのフレームで、メソッドを使用できます。</span><span class="sxs-lookup"><span data-stu-id="93132-109">The `GetArgument` method can be used either in an MSIL stack frame or in a just-in-time (JIT) compiled frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="93132-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="93132-110">Requirements</span></span>  
 <span data-ttu-id="93132-111">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="93132-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="93132-112">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="93132-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="93132-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="93132-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="93132-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="93132-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
