---
title: ICorDebugILFrame::EnumerateArguments メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame.EnumerateArguments
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame::EnumerateArguments
helpviewer_keywords:
- ICorDebugILFrame::EnumerateArguments method [.NET Framework debugging]
- EnumerateArguments method [.NET Framework debugging]
ms.assetid: 00ac81e2-a774-422a-bd88-54a4b3c99f73
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 499f58cc0a3f2d1b3c159435ed7d9b523f25e29e
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67757896"
---
# <a name="icordebugilframeenumeratearguments-method"></a><span data-ttu-id="6490e-102">ICorDebugILFrame::EnumerateArguments メソッド</span><span class="sxs-lookup"><span data-stu-id="6490e-102">ICorDebugILFrame::EnumerateArguments Method</span></span>
<span data-ttu-id="6490e-103">このフレームで、引数の列挙子を取得します。</span><span class="sxs-lookup"><span data-stu-id="6490e-103">Gets an enumerator for the arguments in this frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6490e-104">構文</span><span class="sxs-lookup"><span data-stu-id="6490e-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateArguments (  
    [out] ICorDebugValueEnum    **ppValueEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6490e-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="6490e-105">Parameters</span></span>  
 `ppValueEnum`  
 <span data-ttu-id="6490e-106">[out]このフレームの引数の列挙子である ICorDebugValueEnum オブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="6490e-106">[out] A pointer to the address of an ICorDebugValueEnum object that is the enumerator for the arguments in this frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6490e-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="6490e-107">Remarks</span></span>  
 <span data-ttu-id="6490e-108">`EnumerateArguments` ICorDebugILFrame オブジェクトによって表される呼び出しフレームで使用可能な引数を表示できる列挙子を取得します。</span><span class="sxs-lookup"><span data-stu-id="6490e-108">`EnumerateArguments` gets an enumerator that can list the arguments available in the call frame that is represented by this ICorDebugILFrame object.</span></span> <span data-ttu-id="6490e-109">一覧には引数は、 [vararg](/cpp/windows/vararg) (引数の変数番号) でない引数と`vararg`します。</span><span class="sxs-lookup"><span data-stu-id="6490e-109">The list will include arguments that are [vararg](/cpp/windows/vararg) (that is, a variable number of arguments) as well as arguments that are not `vararg`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6490e-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="6490e-110">Requirements</span></span>  
 <span data-ttu-id="6490e-111">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6490e-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6490e-112">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6490e-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6490e-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6490e-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6490e-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6490e-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
