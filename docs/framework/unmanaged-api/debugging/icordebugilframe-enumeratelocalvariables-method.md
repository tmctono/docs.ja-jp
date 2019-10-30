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
ms.openlocfilehash: 07331a512dd513a94a7d8c3a8d8b0754d998b94b
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131001"
---
# <a name="icordebugilframeenumeratelocalvariables-method"></a><span data-ttu-id="b2c52-102">ICorDebugILFrame::EnumerateLocalVariables メソッド</span><span class="sxs-lookup"><span data-stu-id="b2c52-102">ICorDebugILFrame::EnumerateLocalVariables Method</span></span>
<span data-ttu-id="b2c52-103">このフレーム内のローカル変数の列挙子を取得します。</span><span class="sxs-lookup"><span data-stu-id="b2c52-103">Gets an enumerator for the local variables in this frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b2c52-104">構文</span><span class="sxs-lookup"><span data-stu-id="b2c52-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateLocalVariables(   
    [out] ICorDebugValueEnum    **ppValueEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b2c52-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="b2c52-105">Parameters</span></span>  
 `ppValueEnum`  
 <span data-ttu-id="b2c52-106">入出力このフレーム内のローカル変数の列挙子である、の各オブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="b2c52-106">[out] A pointer to the address of an ICorDebugValueEnum object that is the enumerator for the local variables in this frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b2c52-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="b2c52-107">Remarks</span></span>  
 <span data-ttu-id="b2c52-108">`EnumerateLocalVariables` は、このテキストボックスオブジェクトで表される呼び出しフレームで使用可能なローカル変数を一覧表示できる列挙子を取得します。</span><span class="sxs-lookup"><span data-stu-id="b2c52-108">`EnumerateLocalVariables` gets an enumerator that can list the local variables available in the call frame that is represented by this ICorDebugILFrame object.</span></span> <span data-ttu-id="b2c52-109">この一覧には、一部のローカル変数がアクティブでない可能性があるため、実行中の関数のすべてのローカル変数を含めることはできません。</span><span class="sxs-lookup"><span data-stu-id="b2c52-109">The list may not include all of the local variables in the running function, because some of them may not be active.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b2c52-110">［要件］</span><span class="sxs-lookup"><span data-stu-id="b2c52-110">Requirements</span></span>  
 <span data-ttu-id="b2c52-111">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b2c52-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b2c52-112">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b2c52-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b2c52-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b2c52-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b2c52-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b2c52-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
