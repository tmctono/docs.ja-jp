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
ms.openlocfilehash: d74c5a6f966201c8ca9d2854de2e9986e7f1d0fa
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131027"
---
# <a name="icordebugilframeenumeratearguments-method"></a><span data-ttu-id="08089-102">ICorDebugILFrame::EnumerateArguments メソッド</span><span class="sxs-lookup"><span data-stu-id="08089-102">ICorDebugILFrame::EnumerateArguments Method</span></span>
<span data-ttu-id="08089-103">このフレーム内の引数の列挙子を取得します。</span><span class="sxs-lookup"><span data-stu-id="08089-103">Gets an enumerator for the arguments in this frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="08089-104">構文</span><span class="sxs-lookup"><span data-stu-id="08089-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateArguments (  
    [out] ICorDebugValueEnum    **ppValueEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="08089-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="08089-105">Parameters</span></span>  
 `ppValueEnum`  
 <span data-ttu-id="08089-106">入出力このフレーム内の引数の列挙子である、の各オブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="08089-106">[out] A pointer to the address of an ICorDebugValueEnum object that is the enumerator for the arguments in this frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="08089-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="08089-107">Remarks</span></span>  
 <span data-ttu-id="08089-108">`EnumerateArguments` このテキストボックスオブジェクトで表される呼び出しフレームで使用可能な引数を一覧表示できる列挙子を取得します。</span><span class="sxs-lookup"><span data-stu-id="08089-108">`EnumerateArguments` gets an enumerator that can list the arguments available in the call frame that is represented by this ICorDebugILFrame object.</span></span> <span data-ttu-id="08089-109">この一覧には、 [vararg](/cpp/windows/vararg)である引数 (可変個の引数) と、`vararg`でない引数が含まれます。</span><span class="sxs-lookup"><span data-stu-id="08089-109">The list will include arguments that are [vararg](/cpp/windows/vararg) (that is, a variable number of arguments) as well as arguments that are not `vararg`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="08089-110">［要件］</span><span class="sxs-lookup"><span data-stu-id="08089-110">Requirements</span></span>  
 <span data-ttu-id="08089-111">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="08089-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="08089-112">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="08089-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="08089-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="08089-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="08089-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="08089-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
