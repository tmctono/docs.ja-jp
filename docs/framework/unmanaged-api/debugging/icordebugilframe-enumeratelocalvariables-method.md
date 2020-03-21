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
ms.openlocfilehash: c071a7ddb7d8d3f0e6487ab85284c45f9a7f0372
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178837"
---
# <a name="icordebugilframeenumeratelocalvariables-method"></a><span data-ttu-id="74f24-102">ICorDebugILFrame::EnumerateLocalVariables メソッド</span><span class="sxs-lookup"><span data-stu-id="74f24-102">ICorDebugILFrame::EnumerateLocalVariables Method</span></span>
<span data-ttu-id="74f24-103">このフレーム内のローカル変数の列挙子を取得します。</span><span class="sxs-lookup"><span data-stu-id="74f24-103">Gets an enumerator for the local variables in this frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="74f24-104">構文</span><span class="sxs-lookup"><span data-stu-id="74f24-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateLocalVariables(
    [out] ICorDebugValueEnum    **ppValueEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="74f24-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="74f24-105">Parameters</span></span>  
 `ppValueEnum`  
 <span data-ttu-id="74f24-106">[出力] このフレームのローカル変数の列挙子である ICorDebugValueEnum オブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="74f24-106">[out] A pointer to the address of an ICorDebugValueEnum object that is the enumerator for the local variables in this frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="74f24-107">解説</span><span class="sxs-lookup"><span data-stu-id="74f24-107">Remarks</span></span>  
 <span data-ttu-id="74f24-108">`EnumerateLocalVariables`この ICorDebugILFrame オブジェクトによって表される呼び出しフレームで使用できるローカル変数を一覧表示できる列挙子を取得します。</span><span class="sxs-lookup"><span data-stu-id="74f24-108">`EnumerateLocalVariables` gets an enumerator that can list the local variables available in the call frame that is represented by this ICorDebugILFrame object.</span></span> <span data-ttu-id="74f24-109">一部のローカル変数がアクティブでない可能性があるため、リストに実行中の関数にローカル変数の一部が含まれていない場合があります。</span><span class="sxs-lookup"><span data-stu-id="74f24-109">The list may not include all of the local variables in the running function, because some of them may not be active.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="74f24-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="74f24-110">Requirements</span></span>  
 <span data-ttu-id="74f24-111">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="74f24-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="74f24-112">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="74f24-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="74f24-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="74f24-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="74f24-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="74f24-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
