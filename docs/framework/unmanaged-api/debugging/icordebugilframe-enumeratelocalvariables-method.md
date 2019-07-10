---
title: ICorDebugILFrame::EnumerateLocalVariables メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame.EnumerateLocalVariables
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame::EnumerateLocalVariables
helpviewer_keywords:
- EnumerateLocalVariables method [.NET Framework debugging]
- ICorDebugILFrame::EnumerateLocalVariables method [.NET Framework debugging]
ms.assetid: 1a67fa1b-2419-4cd0-aad4-6f46a0719b4b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c18f2fce23e979f27d9116e74b6c6b007cd33bf0
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67752886"
---
# <a name="icordebugilframeenumeratelocalvariables-method"></a><span data-ttu-id="5bfef-102">ICorDebugILFrame::EnumerateLocalVariables メソッド</span><span class="sxs-lookup"><span data-stu-id="5bfef-102">ICorDebugILFrame::EnumerateLocalVariables Method</span></span>
<span data-ttu-id="5bfef-103">このフレームでローカル変数の列挙子を取得します。</span><span class="sxs-lookup"><span data-stu-id="5bfef-103">Gets an enumerator for the local variables in this frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5bfef-104">構文</span><span class="sxs-lookup"><span data-stu-id="5bfef-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateLocalVariables(   
    [out] ICorDebugValueEnum    **ppValueEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5bfef-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="5bfef-105">Parameters</span></span>  
 `ppValueEnum`  
 <span data-ttu-id="5bfef-106">[out]このフレームのローカル変数の列挙子である ICorDebugValueEnum オブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="5bfef-106">[out] A pointer to the address of an ICorDebugValueEnum object that is the enumerator for the local variables in this frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5bfef-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="5bfef-107">Remarks</span></span>  
 <span data-ttu-id="5bfef-108">`EnumerateLocalVariables` ICorDebugILFrame オブジェクトによって表される呼び出しフレームで使用できるローカル変数を表示できる列挙子を取得します。</span><span class="sxs-lookup"><span data-stu-id="5bfef-108">`EnumerateLocalVariables` gets an enumerator that can list the local variables available in the call frame that is represented by this ICorDebugILFrame object.</span></span> <span data-ttu-id="5bfef-109">リストが含まれない場合ローカル変数の実行中の関数では、アクティブなものはない可能性が。</span><span class="sxs-lookup"><span data-stu-id="5bfef-109">The list may not include all of the local variables in the running function, because some of them may not be active.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5bfef-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="5bfef-110">Requirements</span></span>  
 <span data-ttu-id="5bfef-111">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5bfef-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5bfef-112">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5bfef-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5bfef-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5bfef-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5bfef-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5bfef-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
